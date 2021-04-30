---
title: Gérer l’identité et la connexion des utilisateurs pour HoloLens
description: Apprenez à gérer l’identité des utilisateurs, la prise en charge multi-utilisateur, la sécurité, l’authentification d’entreprise et la connexion pour les appareils HoloLens.
keywords: HoloLens, utilisateur, compte, AAD, Azure AD, ADFS, compte Microsoft, MSA, informations d’identification, référence
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308976"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gérer l’identité et la connexion des utilisateurs pour HoloLens

> [!NOTE]
> Cet article est une référence technique pour les professionnels de l’informatique et les passionnés de technologies. Si vous recherchez des instructions de configuration de HoloLens, consultez «[configuration de votre hololens (1re génération)](hololens1-start.md)» ou «[configuration de votre hololens 2](hololens2-start.md)».

Comme les autres appareils Windows, HoloLens fonctionne toujours dans un contexte utilisateur. Il y a toujours une identité d’utilisateur. HoloLens traite l’identité de la même façon que les autres appareils Windows 10. Cet article est une référence approfondie de l’identité sur HoloLens, et se concentre sur la façon dont HoloLens diffère des autres appareils Windows 10.

HoloLens prend en charge plusieurs types d’identités utilisateur. Vous pouvez utiliser un ou plusieurs comptes d’utilisateur pour vous connecter. Voici une vue d’ensemble des types d’identité et des options d’authentification sur HoloLens :

| Type d'identité | Comptes par appareil | Options d’authentification |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (requiert Azure ad Premium) | 64 | <ul><li>Fournisseur d’informations d’identification Web Azure</li><li>Application Azure Authenticator</li><li>Biométrique (IRIS) &ndash; HoloLens 2 uniquement<sup>1</sup> </li><li>PIN &ndash; facultatif pour hololens (1re génération), requis pour hololens 2</li><li>Mot de passe</li></ul> |
| [Compte Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biométrique (IRIS) &ndash; HoloLens 2 uniquement</li><li>PIN &ndash; facultatif pour hololens (1re génération), requis pour hololens 2</li><li>Mot de passe</li></ul> |
| [Compte local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Mot de passe |

Les comptes connectés au Cloud (Azure AD et MSA) offrent davantage de fonctionnalités, car ils peuvent utiliser les services Azure.  

> [!NOTE]
> 1-si un appareil HoloLens 2 peut prendre en charge jusqu’à 64 comptes de Azure AD, seuls 10 de ces comptes peuvent s’inscrire à l’authentification IRIS. Cela est aligné avec d’autres [options d’authentification biométrique pour Windows Hello entreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

## <a name="setting-up-users"></a>Configuration des utilisateurs

La méthode la plus courante pour configurer un nouvel utilisateur est celle de l’expérience OOBE (out-of-Box Experience) HoloLens. Au cours de l’installation, HoloLens demande à un utilisateur de se connecter en utilisant le compte qu’il souhaite utiliser sur l’appareil. Ce compte peut être un consommateur compte Microsoft ou un compte d’entreprise qui a été configuré dans Azure. Consultez Configuration de votre [hololens (1re génération)](hololens1-start.md) ou [hololens 2](hololens2-start.md).

À l’instar de Windows sur d’autres appareils, la connexion au cours de l’installation crée un profil utilisateur sur l’appareil. Le profil utilisateur stocke les applications et les données. Le même compte fournit également une authentification unique pour les applications telles que Edge ou Skype à l’aide des API du gestionnaire de comptes Windows.  

Si vous utilisez un compte d’entreprise ou professionnel pour vous connecter à HoloLens, HoloLens s’inscrit dans l’infrastructure informatique de l’organisation. Cette inscription permet à votre administrateur informatique de configurer la gestion des appareils mobiles (MDM) pour envoyer des stratégies de groupe à votre HoloLens.

Par défaut, comme pour les autres appareils Windows 10, vous devez vous reconnecter lorsque HoloLens redémarre ou reprend à partir de la mise en veille. Vous pouvez utiliser l’application paramètres pour modifier ce comportement, ou le comportement peut être contrôlé par la stratégie de groupe.

### <a name="linked-accounts"></a>Comptes liés

Comme dans la version de bureau de Windows, vous pouvez lier des informations d’identification de compte Web supplémentaires à votre compte HoloLens. Cette liaison facilite l’accès aux ressources dans ou dans les applications (telles que le magasin) ou pour combiner l’accès aux ressources personnelles et professionnelles. Une fois que vous avez connecté un compte à l’appareil, vous pouvez accorder l’autorisation d’utiliser l’appareil aux applications afin de ne pas avoir à vous connecter individuellement à chaque application.

La liaison de comptes ne sépare pas les données utilisateur créées sur l’appareil, telles que les images ou les téléchargements.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configuration de la prise en charge multi-utilisateur (Azure AD uniquement)

HoloLens prend en charge plusieurs utilisateurs du même Azure AD locataire. Pour utiliser cette fonctionnalité, vous devez utiliser un compte qui appartient à votre organisation pour configurer l’appareil. Par la suite, les autres utilisateurs du même locataire peuvent se connecter à l’appareil à partir de l’écran de connexion ou en appuyant sur la vignette de l’utilisateur dans le panneau Démarrer. Un seul utilisateur peut être connecté à la fois. Lorsqu’un utilisateur se connecte, HoloLens déconnecte l’utilisateur précédent. Le premier utilisateur sur l’appareil est considéré comme le propriétaire de l’appareil, sauf dans le cas de Azure AD Join, [en savoir plus sur les propriétaires d’appareils](security-adminless-os.md#device-owner).

Tous les utilisateurs peuvent utiliser les applications installées sur l’appareil. Toutefois, chaque utilisateur possède ses propres données d’application et ses préférences. La suppression d’une application de l’appareil supprime celle-ci pour tous les utilisateurs.  

Les appareils configurés avec des comptes de Azure AD ne permettent pas de se connecter à l’appareil avec un compte Microsoft. Tous les comptes suivants utilisés doivent être Azure AD comptes du même locataire que l’appareil. Vous pouvez toujours vous [connecter à l’aide d’un compte Microsoft pour les applications](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) qui le prennent en charge (par exemple, le Microsoft Store). Pour passer de l’utilisation de comptes de Azure AD aux comptes Microsoft pour la connexion à l’appareil, vous devez refaire [clignoter l’appareil](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1ère génération)** a commencé à prendre en charge plusieurs utilisateurs Azure ad dans la [mise à jour 2018 de Windows 10 avril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) dans le cadre de [Windows holographique for Business](hololens-upgrade-enterprise.md).

## <a name="removing-users"></a>Suppression des utilisateurs

Vous pouvez supprimer un utilisateur de l’appareil en accédant à **paramètres**  >  **comptes**  >  **autres personnes**. Cette action libère également de l’espace en supprimant toutes les données d’application de cet utilisateur de l’appareil.  

## <a name="using-single-sign-on-within-an-app"></a>Utilisation de l’authentification unique dans une application

En tant que développeur d’applications, vous pouvez tirer parti des identités liées sur HoloLens en utilisant les [API du gestionnaire de comptes Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), comme vous le feriez sur d’autres appareils Windows. Des exemples de code pour ces API sont disponibles sur GitHub : [exemple de gestion de compte Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Les interruptions de compte susceptibles de se produire, telles que la demande de consentement de l’utilisateur pour les informations de compte, l’authentification à deux facteurs, etc., doivent être gérées lorsque l’application demande un jeton d’authentification.

Si votre application nécessite un type de compte spécifique qui n’a pas été lié précédemment, votre application peut demander au système d’inviter l’utilisateur à en ajouter une. Cette demande déclenche le lancement du volet Paramètres du compte en tant qu’enfant modal de votre application. Pour les applications 2D, cette fenêtre est restituée directement au centre de votre application. Pour les applications Unity, cette requête met brièvement l’utilisateur en dehors de votre application holographique pour afficher la fenêtre enfant. Pour plus d’informations sur la personnalisation des commandes et des actions dans ce volet, consultez [WebAccountCommand, classe](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Authentification d’entreprise et autres

Si votre application utilise d’autres types d’authentification, tels que NTLM, de base ou Kerberos, vous pouvez utiliser l' [interface utilisateur des informations d’identification Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) pour collecter, traiter et stocker les informations d’identification de l’utilisateur. L’expérience utilisateur pour la collecte de ces informations d’identification est très similaire à celle des autres interruptions de compte Cloud, et apparaît en tant qu’application enfant sur votre application 2D ou interrompt brièvement une application Unity pour afficher l’interface utilisateur.

## <a name="deprecated-apis"></a>API déconseillées

L’une des façons dont le développement pour HoloLens diffère du développement pour Desktop est que l’API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) n’est pas entièrement prise en charge. Bien que l’API retourne un jeton si le compte principal est en bonne position, les interruptions telles que celles décrites dans cet article n’affichent pas d’interface utilisateur pour l’utilisateur et ne parviennent pas à authentifier correctement le compte.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello entreprise est-il pris en charge sur HoloLens (1ère génération) ?

Windows Hello entreprise (qui prend en charge l’utilisation d’un code confidentiel pour la connexion) est pris en charge pour HoloLens (1ère génération). Pour autoriser la connexion du code confidentiel Windows Hello entreprise sur HoloLens :

1. L’appareil HoloLens doit être [géré par MDM](hololens-enroll-mdm.md).
1. Vous devez activer Windows Hello entreprise pour l’appareil. ([Voir les instructions pour Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Sur HoloLens, l’utilisateur peut ensuite utiliser les **paramètres**  >  **options de connexion**  >  **Ajouter un code** pin pour configurer un code confidentiel.

> [!NOTE]
> Les utilisateurs qui se connectent à l’aide d’un compte Microsoft peuvent également configurer un code confidentiel dans **paramètres**  >  **options de connexion**  >  **Ajouter un code PIN**. Ce code PIN est associé à [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), plutôt qu’à [Windows Hello entreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Comment l’authentification biométrique Iris est-elle implémentée sur HoloLens 2 ?

HoloLens 2 prend en charge l’authentification par Iris. Iris est basé sur la technologie Windows Hello et est pris en charge pour une utilisation par les Azure Active Directory et les comptes Microsoft. Iris est implémenté de la même façon que les autres technologies Windows Hello, et atteint la sécurité de la biométrie à une distance de 1/100 000.

Pour plus d’informations, consultez les [spécifications et spécifications biométriques pour Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . En savoir plus sur [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) et [Windows Hello entreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Comment le type de compte affecte-t-il le comportement de connexion ?

Si vous appliquez des stratégies pour la connexion, la stratégie est toujours respectée. Si aucune stratégie n’est appliquée pour la connexion, il s’agit des comportements par défaut pour chaque type de compte :

- **Azure ad**: demande l’authentification par défaut, et configurable par les **paramètres** pour ne plus demander l’authentification.
- **Compte Microsoft**: le comportement de verrouillage est différent en autorisant le déverrouillage automatique, mais l’authentification de connexion est toujours nécessaire au redémarrage.
- **Compte local**: demande toujours l’authentification sous la forme d’un mot de passe, non configurable dans les **paramètres**

> [!NOTE]
> Les minuteurs d’inactivité ne sont actuellement pas pris en charge, ce qui signifie que la stratégie **AllowIdleReturnWithoutPassword** n’est respectée que lorsque l’appareil passe en mode veille.

## <a name="additional-resources"></a>Ressources supplémentaires

En savoir plus sur la protection des identités des utilisateurs et l’authentification dans [la documentation sur la sécurité et l’identité de Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

En savoir plus sur la configuration d’une infrastructure d’identité hybride complète la [documentation d’identité hybride Azure](https://docs.microsoft.com/azure/active-directory/hybrid/).
