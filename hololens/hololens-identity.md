---
title: Gérer l’identité utilisation et la connexion pour HoloLens
description: Découvrez comment gérer l’identité des utilisateurs, la prise en charge de plusieurs utilisateurs, la sécurité, l’authentification d’entreprise et la connectez-vous pour les appareils HoloLens.
keywords: HoloLens, utilisateur, compte, AAD, Azure AD, adfs, compte Microsoft, msa, informations d’identification, référence
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
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400684"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gérer l’identité utilisation et la connexion pour HoloLens

> [!NOTE]
> Cet article est une référence technique pour les professionnels de l’informatique et les passionnés de technologie. Si vous recherchez des instructions de configuration holoLens, lisez « Configuration de votre[HoloLens (1ère génération)](hololens1-start.md)» ou « Configuration de votre[HoloLens 2](hololens2-start.md)».

Comme les autres appareils Windows, HoloLens fonctionne toujours dans un contexte utilisateur. Il existe toujours une identité d’utilisateur. HoloLens traite l’identité presque de la même manière que les autres appareils Windows 10. Cet article est une référence approfondie de l’identité sur HoloLens et se concentre sur la différence entre HoloLens et les autres appareils Windows 10.

HoloLens prend en charge plusieurs types d’identités d’utilisateur. Vous pouvez utiliser un ou plusieurs comptes d’utilisateur pour vous inscrire. Voici une vue d’ensemble des types d’identité et des options d’authentification sur HoloLens :

| Type d’identité | Comptes par appareil | Options d’authentification |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (nécessite Azure AD Premium) | 64 | <ul><li>Fournisseur d’informations d’identification web Azure</li><li>Application Azure Authenticator</li><li>Biométrie (Iris) &ndash; HoloLens 2 uniquement <sup> 1</sup> </li><li>Code &ndash; confidentiel facultatif pour HoloLens (1ère génération), requis pour HoloLens 2</li><li>Mot de passe</li></ul> |
| [Compte Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biométrie (Iris) &ndash; HoloLens 2 uniquement</li><li>Code &ndash; confidentiel facultatif pour HoloLens (1ère génération), requis pour HoloLens 2</li><li>Mot de passe</li></ul> |
| [Compte local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Mot de passe |

Les comptes connectés au cloud (Azure AD et MSA) offrent davantage de fonctionnalités, car ils peuvent utiliser les services Azure.  

> [!NOTE]
> 1 - Alors qu’un appareil HoloLens 2 peut prendre en charge jusqu’à 64 comptes Azure AD, seuls 10 de ces comptes peuvent s’inscrire à l’authentification par iris. Ceci est aligné sur les autres [options d’authentification biométrique pour Windows Hello Entreprise.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Configuration des utilisateurs

Le moyen le plus courant de configurer un nouvel utilisateur est pendant l’expérience OOBE (Out-of-Box Experience) HoloLens. Pendant l’installation, HoloLens invite un utilisateur à se connecter à l’aide du compte qu’il souhaite utiliser sur l’appareil. Ce compte peut être un compte Microsoft grand public ou un compte d’entreprise qui a été configuré dans Azure. Voir Configuration de [votre HoloLens (1ère génération)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

À l’image de Windows sur d’autres appareils, la signature lors de l’installation crée un profil utilisateur sur l’appareil. Le profil utilisateur stocke les applications et les données. Le même compte fournit également l' sign-on unique pour les applications telles que Edge ou Skype à l’aide des API du Gestionnaire de comptes Windows.  

Si vous utilisez un compte d’entreprise ou d’organisation pour vous inscrire à HoloLens, HoloLens s’inscrit dans l’infrastructure informatique de l’organisation. Cette inscription permet à votre administrateur informatique de configurer la gestion des périphériques mobiles (MDM) pour envoyer des stratégies de groupe à votre HoloLens.

Par défaut, comme pour les autres appareils Windows 10, vous devez vous à nouveau vous connectez lorsque HoloLens redémarre ou reprend de la veille. Vous pouvez utiliser l’application Paramètres pour modifier ce comportement, ou le comportement peut être contrôlé par une stratégie de groupe.

### <a name="linked-accounts"></a>Comptes liés

Comme dans la version de bureau de Windows, vous pouvez lier des informations d’identification de compte web supplémentaires à votre compte HoloLens. Ces liens facilitent l’accès aux ressources dans ou au sein d’applications (telles que le Windows Store) ou de combiner l’accès aux ressources personnelles et de travail. Après avoir connecté un compte à l’appareil, vous pouvez accorder l’autorisation d’utiliser l’appareil aux applications afin de ne pas avoir à vous connecter à chaque application individuellement.

La liaison de comptes ne sépare pas les données utilisateur créées sur l’appareil, telles que les images ou les téléchargements.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configuration de la prise en charge multi-utilisateurs (Azure AD uniquement)

HoloLens prend en charge plusieurs utilisateurs du même client Azure AD. Pour utiliser cette fonctionnalité, vous devez utiliser un compte appartenant à votre organisation pour configurer l’appareil. Par la suite, d’autres utilisateurs du même client peuvent se connectent à l’appareil à partir de l’écran de se connecte ou en appuyant sur la vignette de l’utilisateur dans le panneau de démarrage. Un seul utilisateur peut être signé à la fois. Lorsqu’un utilisateur se signe, HoloLens se signe à l’utilisateur précédent. Le premier utilisateur de l’appareil est considéré comme le propriétaire de l’appareil, sauf dans le cas d’Azure AD Join, en savoir plus sur les propriétaires [d’appareils.](security-adminless-os.md#device-owner)

Tous les utilisateurs peuvent utiliser les applications installées sur l’appareil. Toutefois, chaque utilisateur a ses propres préférences et données d’application. La suppression d’une application de l’appareil la supprime pour tous les utilisateurs.  

Les appareils qui sont configurer avec des comptes Azure AD n’autorisent pas la signature de l’appareil avec un compte Microsoft. Tous les comptes suivants utilisés doivent être des comptes Azure AD du même client que l’appareil. Vous pouvez toujours [vous connectez à l’aide d’un compte Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) pour les applications qui le supportent (telles que le Microsoft Store). Pour modifier l’utilisation de comptes Azure AD vers des comptes Microsoft pour la signature de l’appareil, vous devez modifier [l’appareil.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1ère génération)** a commencé à prendre en charge plusieurs utilisateurs Azure AD dans la mise à jour [d’avril 2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) dans le cadre de [Windows Holographic for Business](hololens-upgrade-enterprise.md).

## <a name="removing-users"></a>Suppression d’utilisateurs

Vous pouvez supprimer un utilisateur de **** l’appareil en allant dans  >  **Paramètres Comptes**  >  **d’autres personnes.** Cette action récupère également de l’espace en supprimant toutes les données d’application de cet utilisateur de l’appareil.  

## <a name="using-single-sign-on-within-an-app"></a>Utilisation de l' sign-on unique au sein d’une application

En tant que développeur d’applications, vous pouvez tirer parti des identités liées sur HoloLens à l’aide des API du Gestionnaire de comptes [Windows,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)comme vous le feriez sur d’autres appareils Windows. Certains exemples de code pour ces API sont disponibles sur GitHub : exemple de gestion [de compte Web.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Les interruptions de compte qui peuvent se produire, telles que la demande de consentement de l’utilisateur pour les informations de compte, l’authentification à deux facteurs, etc., doivent être gérées lorsque l’application demande un jeton d’authentification.

Si votre application nécessite un type de compte spécifique qui n’a pas été lié précédemment, votre application peut demander au système d’en demander un à l’utilisateur. Cette demande déclenche le lancement du volet paramètres du compte en tant qu’enfant modal de votre application. Pour les applications 2D, cette fenêtre s’restituera directement au centre de votre application. Pour les applications Unity, cette demande sort brièvement l’utilisateur de votre application holographique pour restituer la fenêtre enfant. Pour plus d’informations sur la personnalisation des commandes et des actions sur ce volet, voir [WebAccountCommand Class](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Authentification d’entreprise et autre

Si votre application utilise d’autres types d’authentification, tels que NTLM, Basic ou Kerberos, vous pouvez utiliser l’interface utilisateur d’informations d’identification [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) pour collecter, traiter et stocker les informations d’identification de l’utilisateur. L’expérience utilisateur pour la collecte de ces informations d’identification est très similaire à d’autres interruptions de compte informatique et apparaît comme une application enfant au-dessus de votre application 2D ou suspend brièvement une application Unity pour afficher l’interface utilisateur.

## <a name="deprecated-apis"></a>API dépréciées

L’une des différences entre le développement pour HoloLens et le développement pour ordinateur de bureau est que l’API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) n’est pas entièrement prise en charge. Bien que l’API renvoie un jeton si le compte principal est en règle, les interruptions telles que celles décrites dans cet article n’affichent aucune interface utilisateur pour l’utilisateur et ne parviennent pas à authentifier correctement le compte.

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello Entreprise est-il pris en charge sur HoloLens (1ère génération) ?

Windows Hello Entreprise (qui prend en charge l’utilisation d’un code confidentiel pour se connecter) est pris en charge pour HoloLens (1ère génération). Pour autoriser la connectez-vous au code confidentiel Windows Hello Entreprise sur HoloLens :

1. L’appareil HoloLens doit être [géré par mdM](hololens-enroll-mdm.md).
1. Vous devez activer Windows Hello Entreprise pour l’appareil. ([Voir les instructions pour Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Sur HoloLens, l’utilisateur peut ensuite utiliser les options de signature **paramètres**Ajouter un code  >  ****  >  **** confidentiel pour configurer un code confidentiel.

> [!NOTE]
> Les **utilisateurs**qui se connectent à l’aide d’un compte Microsoft peuvent également configurer un code confidentiel dans paramètres Options de signature  >  ****  >  **Ajouter un code confidentiel**. Ce code confidentiel est associé [à Windows Hello,](https://support.microsoft.com/help/17215/windows-10-what-is-hello)plutôt qu’à [Windows Hello Entreprise.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Comment l’authentification biométrique Iris est-elle implémentée sur HoloLens 2 ?

HoloLens 2 prend en charge l’authentification par iris. L’iris est basé sur la technologie Windows Hello et est pris en charge par les comptes Azure Active Directory et Microsoft. L’iris est implémenté de la même manière que d’autres technologies Windows Hello et offre une sécurité biométrique de 1/100K.

Pour plus [d’informations,](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) voir les spécifications et exigences biométriques de Windows Hello. En savoir plus [sur Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) et Windows Hello [Entreprise.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Comment le type de compte affecte-t-il le comportement de la signature ?

Si vous appliquez des stratégies de connexion, elles sont toujours respectées. Si aucune stratégie de sign-in n’est appliquée, voici les comportements par défaut pour chaque type de compte :

- **Azure AD**: demande l’authentification par défaut et configurable par **paramètres** pour ne plus demander d’authentification.
- **Compte Microsoft :** le comportement de verrouillage est différent pour autoriser le déverrouillage automatique, mais l’authentification de la signature est toujours requise au redémarrage.
- **Compte local :** demande toujours l’authentification sous la forme d’un mot de passe, non configurable dans **paramètres**

> [!NOTE]
> Les timers d’inactivité ne sont actuellement pas pris en charge, ce qui signifie que la stratégie **AllowIdleReturnWithoutPassword** est respectée uniquement lorsque l’appareil passe en veille.

## <a name="additional-resources"></a>Ressources supplémentaires

En savoir plus sur la protection et l’authentification des identités utilisateur dans la documentation sur la sécurité [et l’identité Windows 10.](https://docs.microsoft.com/windows/security/identity-protection/)

En savoir plus sur la configuration de l’infrastructure d’identité hybride complète la documentation sur les [identités hybrides Azure.](https://docs.microsoft.com/azure/active-directory/hybrid/)
