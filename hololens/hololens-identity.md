---
title: Gérer les identités et les connexions des utilisateurs pour HoloLens
description: apprenez à gérer l’identité des utilisateurs, la prise en charge multi-utilisateur, la sécurité, l’authentification d’entreprise et la connexion à HoloLens appareils.
keywords: HoloLens, utilisateur, compte, AAD, Azure AD, adfs, compte microsoft, msa, informations d’identification, référence
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e4c68ad6535293f916cc92c42204954110edc4fe
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189543"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gérer les identités et les connexions des utilisateurs pour HoloLens

> [!NOTE]
> Cet article est une référence technique pour les professionnels de l’informatique et les passionnés de technologies. si vous recherchez des instructions de configuration de HoloLens, consultez «[configuration de votre HoloLens (1er génération)](hololens1-start.md)» ou «[configuration de votre HoloLens 2](hololens2-start.md)».

comme les autres appareils Windows, HoloLens fonctionne toujours dans un contexte utilisateur. Il y a toujours une identité d’utilisateur. HoloLens traite l’identité de la même façon que les autres Windows appareils. cet article est une référence approfondie de l’identité sur HoloLens, et se concentre sur la façon dont HoloLens diffère des autres appareils Windows.

HoloLens prend en charge plusieurs types d’identités utilisateur. Vous pouvez utiliser un ou plusieurs comptes d’utilisateur pour vous connecter. Voici une vue d’ensemble des types d’identité et des options d’authentification sur HoloLens :

| Type d'identité | Comptes par appareil | Options d’authentification |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Fournisseur d’informations d’identification Web Azure</li><li>application Azure Authenticator</li><li>biométrique (Iris) &ndash; HoloLens 2 uniquement<sup>2</sup> </li><li>Clé de sécurité FIDO2</li><li>PIN &ndash; facultatif pour HoloLens (1er génération), requis pour HoloLens 2</li><li>Mot de passe</li></ul> |
| [Compte Microsoft](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>biométrique (Iris) &ndash; HoloLens 2 uniquement</li><li>PIN &ndash; facultatif pour HoloLens (1er génération), requis pour HoloLens 2</li><li>Mot de passe</li></ul> |
| [Compte local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Mot de passe |

Les comptes connectés au Cloud (Azure AD et MSA) offrent davantage de fonctionnalités, car ils peuvent utiliser les services Azure.  
> [!IMPORTANT]
> 1-Azure AD Premium n’est pas nécessaire pour la connexion à l’appareil. Toutefois, elle est requise pour d’autres fonctionnalités d’un déploiement Cloud faiblement tactile, comme l’inscription automatique et Autopilot.

> [!NOTE]
> 2-même si un appareil HoloLens 2 peut prendre en charge jusqu’à 64 comptes Azure AD, seuls 31 de ces comptes peuvent s’inscrire à l’authentification Iris. cela est aligné avec d’autres [options d’authentification biométrique pour Windows Hello pour l’entreprise](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

> [!IMPORTANT]
> 3-un compte local ne peut être configuré que sur un appareil [via un package d’approvisionnement au cours d’OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup). il ne peut pas être ajouté ultérieurement dans l’application paramètres. Si vous souhaitez utiliser un compte local sur un appareil qui est déjà configuré, vous devez refaire [clignoter ou réinitialiser l’appareil.](hololens-recovery.md)

## <a name="setting-up-users"></a>Configuration des utilisateurs

Il existe deux façons de configurer un nouvel utilisateur sur le HoloLens. la méthode la plus courante est la HoloLens OOBE (out-of-box experience). si vous utilisez Azure Active Directory, [les autres utilisateurs peuvent se connecter](#setting-up-multi-user-support-azure-ad-only) après OOBE à l’aide de leurs informations d’identification Azure AD. les appareils HoloLens qui sont initialement configurés avec un compte MSA ou un compte local pendant OOBE ne prennent pas en charge plusieurs utilisateurs. consultez configuration de votre [HoloLens (1re génération)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

si vous utilisez un compte d’entreprise ou professionnel pour vous connecter à HoloLens, HoloLens s’inscrit dans l’infrastructure informatique de l’organisation. Cette inscription permet à votre administrateur informatique de configurer la gestion des appareils mobiles (MDM) pour envoyer des stratégies de groupe à votre HoloLens.

comme Windows sur d’autres appareils, la connexion lors de l’installation crée un profil utilisateur sur l’appareil. Le profil utilisateur stocke les applications et les données. le même compte fournit également l’authentification unique pour les applications, telles que Edge ou le Microsoft Store, à l’aide des api du gestionnaire de comptes Windows.

par défaut, comme pour les autres appareils Windows 10, vous devez vous reconnecter lorsque HoloLens redémarre ou reprend à partir de la mise en veille. vous pouvez utiliser l’application Paramètres pour modifier ce comportement, ou le comportement peut être contrôlé par la stratégie de groupe.

### <a name="linked-accounts"></a>Comptes liés

comme dans la version de bureau de Windows, vous pouvez lier des informations d’identification de compte web supplémentaires à votre compte HoloLens. Cette liaison facilite l’accès aux ressources dans ou dans les applications (telles que le magasin) ou pour combiner l’accès aux ressources personnelles et professionnelles. Une fois que vous avez connecté un compte à l’appareil, vous pouvez accorder l’autorisation d’utiliser l’appareil aux applications afin de ne pas avoir à vous connecter individuellement à chaque application.

La liaison de comptes ne sépare pas les données utilisateur créées sur l’appareil, telles que les images ou les téléchargements.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configuration de la prise en charge multi-utilisateur (Azure AD uniquement)

HoloLens prend en charge plusieurs utilisateurs du même locataire Azure AD. Pour utiliser cette fonctionnalité, vous devez utiliser un compte qui appartient à votre organisation pour configurer l’appareil. Par la suite, les autres utilisateurs du même locataire peuvent se connecter à l’appareil à partir de l’écran de connexion ou en appuyant sur la vignette de l’utilisateur dans le panneau Démarrer. Un seul utilisateur peut être connecté à la fois. lorsqu’un utilisateur se connecte, HoloLens déconnecte l’utilisateur précédent. 

>[!IMPORTANT]
> Le premier utilisateur sur l’appareil est considéré comme le propriétaire de l’appareil, sauf dans le cas de Azure AD Join, [en savoir plus sur les propriétaires d’appareils](security-adminless-os.md#device-owner).

Tous les utilisateurs peuvent utiliser les applications installées sur l’appareil. Toutefois, chaque utilisateur possède ses propres données d’application et ses préférences. La suppression d’une application de l’appareil supprime celle-ci pour tous les utilisateurs.  

Les appareils configurés avec des comptes de Azure AD ne permettent pas de se connecter à l’appareil avec un compte Microsoft. Tous les comptes suivants utilisés doivent être Azure AD comptes du même locataire que l’appareil. Vous pouvez toujours vous [connecter à l’aide d’un compte Microsoft pour les applications](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) qui le prennent en charge (par exemple, le Microsoft Store). Pour passer de l’utilisation de comptes de Azure AD aux comptes Microsoft pour la connexion à l’appareil, vous devez refaire [clignoter l’appareil](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1ère génération)** a commencé à prendre en charge plusieurs utilisateurs Azure AD dans la [Windows 10 mise à jour 2018 d’avril](/windows/mixed-reality/release-notes-april-2018) dans le cadre de [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Plusieurs utilisateurs sont listés sur l’écran de connexion

Auparavant, l’écran de connexion affichait uniquement l’utilisateur connecté le plus récemment, ainsi que le point d’entrée « autre utilisateur ». Nous avons reçu des commentaires des clients qui ne suffisent pas si plusieurs utilisateurs se sont connectés à l’appareil. Ils devaient encore retaper leur nom d’utilisateur, etc.

présenté dans [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), lors de la sélection d’un **autre utilisateur** situé à droite du champ d’entrée du code confidentiel, l’écran de connexion affiche plusieurs utilisateurs ayant déjà été connectés à l’appareil. cela permet aux utilisateurs de sélectionner leur profil utilisateur, puis de se connecter à l’aide de leurs informations d’identification de Windows Hello. Un nouvel utilisateur peut également être ajouté à l’appareil à partir de la page autres utilisateurs via le bouton **Ajouter un compte** .

Quand vous êtes dans le menu autres utilisateurs, le bouton autres utilisateurs affiche le dernier utilisateur connecté à l’appareil. Sélectionnez ce bouton pour revenir à l’écran de connexion de cet utilisateur.

![Écran de connexion par défaut.](./images/multiusers1.jpg)

<br>

![Écran de connexion d’autres utilisateurs.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Suppression des utilisateurs

vous pouvez supprimer un utilisateur de l’appareil en accédant à **Paramètres**  >  **comptes**  >  **autres personnes**. Cette action libère également de l’espace en supprimant toutes les données d’application de cet utilisateur de l’appareil.  

## <a name="using-single-sign-on-within-an-app"></a>Utilisation de l’authentification unique dans une application

en tant que développeur d’applications, vous pouvez tirer parti des identités liées sur HoloLens à l’aide des [api du gestionnaire de comptes Windows](/uwp/api/Windows.Security.Authentication.Web.Core), tout comme vous le feriez sur d’autres appareils Windows. des exemples de code pour ces api sont disponibles sur GitHub : [exemple de gestion de compte Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Les interruptions de compte susceptibles de se produire, telles que la demande de consentement de l’utilisateur pour les informations de compte, l’authentification à deux facteurs, etc., doivent être gérées lorsque l’application demande un jeton d’authentification.

Si votre application nécessite un type de compte spécifique qui n’a pas été lié précédemment, votre application peut demander au système d’inviter l’utilisateur à en ajouter une. Cette demande déclenche le lancement du volet Paramètres du compte en tant qu’enfant modal de votre application. Pour les applications 2D, cette fenêtre est restituée directement au centre de votre application. Pour les applications Unity, cette requête met brièvement l’utilisateur en dehors de votre application holographique pour afficher la fenêtre enfant. Pour plus d’informations sur la personnalisation des commandes et des actions dans ce volet, consultez [WebAccountCommand, classe](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise et d’autres authentifications

si votre application utilise d’autres types d’authentification, tels que NTLM, de base ou Kerberos, vous pouvez utiliser [Windows interface utilisateur des informations d’identification](/uwp/api/Windows.Security.Credentials.UI) pour collecter, traiter et stocker les informations d’identification de l’utilisateur. L’expérience utilisateur pour la collecte de ces informations d’identification est très similaire à celle des autres interruptions de compte Cloud, et apparaît en tant qu’application enfant sur votre application 2D ou interrompt brièvement une application Unity pour afficher l’interface utilisateur.

## <a name="deprecated-apis"></a>API déconseillées

l’une des façons dont le développement pour HoloLens diffère du développement pour Desktop est que l’API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) n’est pas entièrement prise en charge. Bien que l’API retourne un jeton si le compte principal est en bonne position, les interruptions telles que celles décrites dans cet article n’affichent pas d’interface utilisateur pour l’utilisateur et ne parviennent pas à authentifier correctement le compte.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>est-Windows Hello pour les entreprises prises en charge sur HoloLens (1ère génération) ?

Windows Hello pour les entreprises (qui prend en charge l’utilisation d’un code confidentiel pour la connexion) est pris en charge pour les HoloLens (1er génération). pour autoriser la connexion du code confidentiel Windows Hello pour l’entreprise sur HoloLens :

1. l’appareil HoloLens doit être [géré par MDM](hololens-enroll-mdm.md).
1. vous devez activer Windows Hello pour l’appareil. ([Voir les instructions pour Microsoft Intune.](/intune/windows-hello))
1. sur HoloLens, l’utilisateur peut ensuite utiliser **Paramètres**  >  **Options de connexion**  >  **ajouter un code** pin pour configurer un code pin.

> [!NOTE]
> les utilisateurs qui se connectent à l’aide d’un compte Microsoft peuvent également configurer un code pin dans **Paramètres**  >  **Options de connexion**  >  **ajouter un code pin**. ce code PIN est associé à [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)plutôt qu’à [des Windows Hello pour l’entreprise](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Comment l’authentification biométrique Iris est-elle implémentée sur HoloLens 2 ?

HoloLens 2 prend en charge l’authentification par Iris. Iris est basé sur la technologie Windows Hello et est pris en charge pour une utilisation par les comptes Azure Active Directory et Microsoft. Iris est implémenté de la même façon que les autres technologies de Windows Hello, et atteint la [sécurité de la biométrie à une distance de 1/100](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)000.

pour plus d’informations, consultez les [spécifications et spécifications biométriques pour Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . en savoir plus sur les [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) et les [Windows Hello pour les entreprises](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="where-is-iris-biometric-information-stored"></a>Où sont stockées les informations biométriques IRIS ?

les informations biométriques de l’Iris sont stockées localement sur chaque HoloLens par [Windows Hello spécifications](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Il n’est pas partagé et est protégé par deux couches de chiffrement. Il n’est pas accessible aux autres utilisateurs, même à un administrateur, car il n’existe aucun compte d’administrateur sur un HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Dois-je utiliser l’authentification IRIS ?
Non, vous pouvez ignorer cette étape lors de l’installation. 

![Configurer IRIS.](./images/setup-iris.png)

HoloLens 2 fournit de nombreuses options pour l’authentification, notamment les clés de sécurité FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Les informations de l’iris peuvent-elles être supprimées de la HoloLens ?
oui, vous pouvez le supprimer manuellement dans Paramètres.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Comment le type de compte affecte-t-il le comportement de connexion ?

Si vous appliquez des stratégies pour la connexion, la stratégie est toujours respectée. Si aucune stratégie n’est appliquée pour la connexion, il s’agit des comportements par défaut pour chaque type de compte :

- **Azure AD**: demande l’authentification par défaut et peut être configurée par **Paramètres** pour ne plus demander l’authentification.
- **Compte Microsoft**: le comportement de verrouillage est différent en autorisant le déverrouillage automatique, mais l’authentification de connexion est toujours nécessaire au redémarrage.
- **compte Local**: demande toujours l’authentification sous la forme d’un mot de passe, non configurable dans **Paramètres**

> [!NOTE]
> Les minuteurs d’inactivité ne sont actuellement pas pris en charge, ce qui signifie que la stratégie **AllowIdleReturnWithoutPassword** n’est respectée que lorsque l’appareil passe en mode veille.

## <a name="additional-resources"></a>Ressources supplémentaires

en savoir plus sur la protection des identités des utilisateurs et l’authentification dans [la documentation relative à la sécurité et à l’identité de Windows 10](/windows/security/identity-protection/).

En savoir plus sur la configuration d’une infrastructure d’identité hybride complète la [documentation d’identité hybride Azure](/azure/active-directory/hybrid/).
