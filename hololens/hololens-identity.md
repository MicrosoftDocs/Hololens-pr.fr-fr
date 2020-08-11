---
title: Gérer l’identité utilisation et la connexion pour HoloLens
description: Gestion de l’identité, de la sécurité et de la connexion des utilisateurs pour HoloLens.
keywords: HoloLens, utilisateur, compte, AAD, ADFS, compte Microsoft, MSA, informations d’identification, référence
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 1/6/2020
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
ms.openlocfilehash: 9829b90445be7f73cfdc0e330d9d57af1ef0a44b
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919117"
---
# Gérer l’identité utilisation et la connexion pour HoloLens

> [!NOTE]
> Cet article est une référence technique pour les professionnels de l’informatique et les amateurs de technologie. Si vous recherchez les instructions de configuration de HoloLens, lisez «[configuration de votre hololens (1er génération)](hololens1-start.md)» ou «[configuration de votre hololens 2](hololens2-start.md)».

Comme d’autres appareils Windows, HoloLens fonctionne toujours dans un contexte utilisateur. Il existe toujours une identité d’utilisateur. HoloLens traite l’identité de la même manière que sur les autres appareils Windows 10. Cet article est une référence approfondie pour l’identité sur HoloLens et porte sur le fonctionnement de HoloLens par rapport aux autres appareils Windows 10.

HoloLens prend en charge plusieurs types d’identités utilisateur. Vous pouvez utiliser un ou plusieurs comptes d’utilisateur pour vous connecter. Voici une vue d’ensemble des types d’identité et des options d’authentification sur HoloLens:

| Type d’identité | Comptes par appareil | Options d’authentification |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Fournisseur d’informations d’identification Web Azure</li><li>Application Azure Authenticator</li><li>Biométrique (IRIS)- &ndash; HoloLens 2 uniquement</li><li>Code confidentiel &ndash; facultatif pour hololens (1er génération) requis pour hololens 2</li><li>Mot de passe</li></ul> |
| [Compte Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biométrique (IRIS)- &ndash; HoloLens 2 uniquement</li><li>Code confidentiel &ndash; facultatif pour hololens (1er génération) requis pour hololens 2</li><li>Mot de passe</li></ul> |
| [Compte local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Mot de passe |

Les comptes connectés au Cloud (AAD et MSA) proposent davantage de fonctionnalités, car ils peuvent utiliser Azure services.  

## Configuration des utilisateurs

La méthode la plus courante pour configurer un nouvel utilisateur est celle de l’OOBE (out-of-Box Experience) de HoloLens. Lors de l’installation, HoloLens demande à un utilisateur de se connecter à l’aide du compte qu’il souhaite utiliser sur l’appareil. Il peut s’agir d’un compte Microsoft ou d’un compte professionnel configuré dans Azure. Voir Configuration de votre [hololens (1ère génération)](hololens1-start.md) ou [hololens 2](hololens2-start.md).

Comme Windows sur d’autres appareils, la connexion lors de l’installation crée un profil utilisateur sur l’appareil. Le profil utilisateur stocke les applications et les données. Le même compte fournit également une authentification unique pour les applications telles que Edge ou Skype à l’aide des API du gestionnaire de compte Windows.  

Si vous utilisez un compte d’entreprise ou professionnel pour vous connecter à HoloLens, HoloLens s’inscrit dans l’infrastructure informatique de l’organisation. Cet enregistrement permet à votre administrateur informatique de configurer la gestion des périphériques mobiles (GPM) pour l’envoi de stratégies de groupe vers votre HoloLens.

Par défaut, pour les autres appareils Windows 10, vous devez vous reconnecter lorsque HoloLens redémarre ou reprend à partir du mode veille. Vous pouvez utiliser l’application paramètres pour modifier ce comportement, ou le comportement peut être contrôlé par une stratégie de groupe.

### Comptes liés

Comme dans la version de bureau de Windows, vous pouvez lier des informations d’identification de compte Web supplémentaires à votre compte HoloLens. Ces liens permettent d’accéder plus facilement aux ressources au sein des applications ou à l’intérieur de celles-ci (par exemple, dans le Windows Store) ou de combiner l’accès aux ressources personnelles et professionnelles. Après avoir connecté un compte à l’appareil, vous pouvez accorder à des applications l’autorisation d’utiliser l’appareil pour que vous n’ayez pas à vous connecter à chaque application individuellement.

La liaison des comptes ne sépare pas les données utilisateur créées sur l’appareil, telles que les images ou les téléchargements.  

### Configuration de la prise en charge des utilisateurs multiples (AAD uniquement)

> [!NOTE]
> **HoloLens (1er génération)** a commencé à prendre en charge plusieurs utilisateurs AAD dans le cadre de la [mise à jour 2018 de Windows 10 d’avril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) dans le cadre de [Windows holographique pour les entreprises](hololens-upgrade-enterprise.md).

HoloLens prend en charge plusieurs utilisateurs du même client AAD. Pour utiliser cette fonctionnalité, vous devez utiliser un compte qui fait partie de votre organisation pour configurer l’appareil. Par la suite, les autres utilisateurs du même client peuvent se connecter à l’appareil à partir de l’écran de connexion ou en appuyant sur la vignette utilisateur dans le panneau Démarrer. Un seul utilisateur peut être connecté à la fois. Lorsqu’un utilisateur se connecte, le HoloLens déconnecte l’utilisateur précédent.  

Tous les utilisateurs peuvent utiliser les applications installées sur l’appareil. Toutefois, chaque utilisateur possède ses propres données et préférences d’application. La suppression d’une application de l’appareil supprime celle-ci pour tous les utilisateurs.  

## Supprimer des utilisateurs

Vous pouvez supprimer un utilisateur de l’appareil en accédant à **paramètres**de  >  **comptes**  >  **autres personnes**. Cette action récupère également de l’espace en supprimant l’ensemble des données d’application de cet utilisateur sur l’appareil.  

## Utilisation de l’authentification unique dans une application

En tant que développeur d’applications, vous pouvez tirer parti d’identités liées sur HoloLens en utilisant les [API du gestionnaire de comptes Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), de la même manière que sur d’autres appareils Windows. Certains exemples de code pour ces API sont disponibles [ici](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Les interruptions de compte qui peuvent se produire, par exemple pour demander l’autorisation d’un utilisateur pour les informations sur le compte, l’authentification à deux facteurs, etc., doivent être gérées lorsque l’application demande un jeton d’authentification.

Si votre application requiert un type de compte spécifique qui n’a pas encore été lié, votre application peut demander au système de lui demander d’en ajouter une. Cette demande déclenche le volet Paramètres du compte à lancer en tant qu’enfant modal de votre application. Pour les applications 2D, cette fenêtre s’affiche directement sur le centre de votre application. Dans le cas des applications Unity, cette requête permet de sortir l’utilisateur de votre application holographique afin d’afficher la fenêtre enfant. Pour plus d’informations sur la personnalisation des commandes et des actions dans ce volet, voir [classe WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Authentification entreprise et autre

Si votre application utilise d’autres types d’authentification, tels que NTLM, basique ou Kerberos, vous pouvez utiliser l' [interface utilisateur d’informations d’identification Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) pour collecter, traiter et stocker les informations d’identification de l’utilisateur. L’utilisation de ces informations d’identification est très similaire à celle d’autres interruptions de compte basées sur le Cloud, et elle apparaît sous la forme d’une application enfant au-dessus de votre application 2D ou interrompt brièvement une application Unity pour afficher l’interface utilisateur.

## API déconseillées

L’une des façons dont le développement pour HoloLens diffère du développement pour le bureau est que l’API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) n’est pas entièrement prise en charge. Même si l’API renvoie un jeton si le compte principal est en bon état, les interruptions telles que celles décrites dans cet article n’affichent pas d’interface utilisateur pour l’utilisateur et ne parviennent pas à authentifier correctement le compte.

## Forum Aux Questions

### Windows Hello entreprise est-il pris en charge sur HoloLens (1ère génération)?

Windows Hello entreprise (qui prend en charge l’utilisation d’un code confidentiel pour la connexion) est pris en charge pour HoloLens (1er génération). Pour autoriser la connexion à un code confidentiel Windows Hello entreprise sur HoloLens:

1. Le périphérique HoloLens doit être [géré par MDM](hololens-enroll-mdm.md).
1. Vous devez activer Windows Hello entreprise pour l’appareil. ([Voir instructions applicables à Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Sur HoloLens, l’utilisateur peut ensuite utiliser **Settings**les  >  **options de connexion**paramètres  >  **Ajouter un code** confidentiel pour configurer un code confidentiel.

> [!NOTE]
> Les utilisateurs qui se connectent à l’aide d’un compte Microsoft peuvent également configurer **Settings**un code confidentiel dans  >  **les options de connexion**paramètres  >  **Ajouter un code confidentiel**. Ce code confidentiel est associé à [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)plutôt qu’à [Windows Hello entreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### Comment l’authentification biométrique par Iris est-elle implémentée sur HoloLens 2?

HoloLens 2 prend en charge l’authentification par Iris. Iris repose sur la technologie Windows Hello et est pris en charge pour une utilisation par Azure Active Directory et des comptes Microsoft. Iris est implémenté de la même manière que d’autres technologies Windows Hello et atteint une sécurité biométrique de 1/100 000.

Vous pouvez en savoir plus sur les exigences et spécifications de biométrique pour [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) En savoir plus sur [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) et [Windows Hello entreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### Comment le type de compte affecte-t-il le comportement de connexion?

Si vous appliquez des stratégies de connexion, elles sont toujours respectées. Si aucune stratégie de connexion n’est appliquée, il s’agit des comportements par défaut de chaque type de compte:

- **Azure ad**: demande l’authentification par défaut et les paramètres configurables par **paramètres** ne demandent plus d’authentification.
- **Compte Microsoft**: le comportement de verrouillage est différent et autorise le déverrouillage automatique; Toutefois, l’authentification de connexion est toujours requise au redémarrage.
- **Compte local**: demande toujours d’authentification sous forme de mot de passe, mais pas de configuration dans les **paramètres**

> [!NOTE]
> Les minuteurs d’inactivité ne sont actuellement pas pris en charge, ce qui signifie que la stratégie **AllowIdleReturnWithoutPassword** est respectée uniquement lorsque l’appareil passe en mode veille.

## Ressources supplémentaires

En savoir plus sur la protection de l’identité des utilisateurs et l’authentification dans [la documentation relative à la sécurité et aux identités de Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

En savoir plus sur la configuration de l’infrastructure d’identité hybride, détaillée de la [documentation d’identité hybride Azure](https://docs.microsoft.com/azure/active-directory/hybrid/).
