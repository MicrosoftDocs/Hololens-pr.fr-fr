---
title: Configurer HoloLens en tant que kiosque
description: découvrez comment configurer et utiliser une configuration de kiosque pour verrouiller les applications sur des appareils HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 28c431397385c06fb94de410a0763e24e18e4509
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979370"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurer HoloLens en tant que kiosque

## <a name="what-is-kiosk-mode"></a>Qu’est-ce que le mode plein écran ?

Le mode plein écran est une fonctionnalité qui vous permet de contrôler les applications qui sont affichées dans le menu Démarrer quand un utilisateur se connecte à HoloLens. Il existe 2 scénarios pris en charge :

1. **Mode plein écran à application unique** – aucun menu Démarrer n’est affiché, et une application unique est lancée automatiquement quand l’utilisateur se connecte. <br> *exemples d’utilisation*: un appareil qui exécute uniquement Dynamics 365 Guides application.
2. **mode plein écran d’application** : menu Démarrer affiche uniquement les applications qui ont été spécifiées dans la configuration de la borne quand un utilisateur se connecte. Vous pouvez choisir de lancer automatiquement une application si vous le souhaitez. <br> *exemples d’utilisation*: un appareil qui affiche uniquement l’application du Store, le Hub de commentaires et l’application Paramètres dans le menu démarrer.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Description de l’expérience en mode plein écran lorsqu’un utilisateur se connecte

Le tableau suivant répertorie les fonctionnalités des fonctionnalités dans les différents modes de kiosque.

| &nbsp; |Menu Démarrer |Menu actions rapides |Caméra et vidéo |Miracast |Cortana |Commandes vocales intégrées |
| --- | --- | --- | --- | --- | --- | --- |
|Borne pour une seule application |Désactivé |Désactivé |Désactivé |Désactivé   |Désactivé |Désactivé |
|Kiosque multi-application |activé |Désactivé  |Téléchargé  |Téléchargé |Téléchargé   |Désactivé  |

\*pour plus d’informations sur la façon d’activer les fonctionnalités désactivées, ou sur la façon dont les commandes vocales interagissent avec les fonctionnalités désactivées et Cortana consultez [HoloLens AUMIDs pour les applications](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids).

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Considérations générales à prendre en compte avant de configurer le mode plein écran

1. déterminez le type de compte d’utilisateur qui se connecte à HoloLens dans votre environnement : HoloLens prend en charge les comptes Azure Active Directory (AAD), les comptes Microsoft (MSA) et les comptes locaux. En outre, les comptes créés temporairement, appelés invités/visiteurs, sont également pris en charge (uniquement pour les appareils de jonction AAD). [Pour plus d’informations, consultez gérer l’identité des utilisateurs et connexion pour HoloLens](hololens-identity.md).
2. Déterminez les cibles de l’expérience en mode plein écran, qu’il s’agisse de tout le monde, d’un seul utilisateur, de certains utilisateurs ou d’utilisateurs membres du groupe AAD, etc.
3. Pour le mode plein écran de l’application, déterminez la ou les applications à afficher dans le menu Démarrer. Pour chaque application, son [ID de modèle d’utilisateur d’application (identifiant aumid)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) est nécessaire.
4. déterminez si le mode plein écran sera appliqué à HoloLens via des packages d’approvisionnement d’exécution ou un serveur de gestion des appareils mobiles (MDM).

## <a name="security-considerations"></a>Considérations relatives à la sécurité

Le mode plein écran ne doit pas être considéré comme une méthode de sécurité, mais comme un moyen de contrôler l’expérience de démarrage lors de la connexion de l’utilisateur. Vous pouvez combiner l’expérience en mode plein écran avec les options mentionnées ci-dessous s’il existe des besoins spécifiques en matière de sécurité :

- lorsque Paramètres application est configurée pour s’afficher en mode plein écran et que vous souhaitez contrôler les pages qui s’affichent dans Paramètres application, reportez-vous à la [Page Paramètres visibilité](settings-uri-list.md)
- lorsque vous souhaitez contrôler l’accès à certaines fonctionnalités matérielles, par exemple, l’appareil photo, la Bluetooth, etc. pour certaines applications, etc., reportez-vous aux [stratégies du CSP de stratégie pris en charge par la gestion des clients HoloLens 2 Windows](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Vous pouvez consulter nos [restrictions d’appareil courantes](hololens-common-device-restrictions.md) pour obtenir des idées.
- Le mode plein écran ne bloque pas une application (configurée dans le cadre d’une expérience de kiosque) de lancer d’autres applications. lorsque vous souhaitez bloquer complètement le lancement de certaines applications/processus sur HoloLens, consultez la rubrique [utilisation du contrôle d’Application Windows Defender sur des appareils HoloLens 2 dans Microsoft Intune-Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Considérations techniques clés pour le mode plein écran pour HoloLens

S’applique uniquement si vous envisagez d’utiliser des packages de provisionnement du runtime ou de créer des configurations de kiosque manuellement. La configuration en mode plein écran utilise une structure hiérarchique basée sur XML :

- Un profil d’accès affecté définit les applications qui sont affichées dans le menu démarrer en mode plein écran. Vous pouvez définir plusieurs profils dans la même structure XML, qui peut être référencée ultérieurement.
- Une configuration d’accès assignée fait référence à un profil et à un ou plusieurs utilisateurs cibles de ce profil, par exemple, un utilisateur spécifique, ou un groupe ou un visiteur AAD, etc. Vous pouvez définir plusieurs configurations dans la même structure XML en fonction de la complexité de vos scénarios d’utilisation (voir la section scénarios pris en charge ci-dessous).
- Pour en savoir plus, consultez [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Scénarios pris en charge pour le mode plein écran basé sur le type d’identité

Consultez les [liens de référence](hololens-kiosk-reference.md#kiosk-xml-code-samples) pour obtenir des exemples basés sur votre scénario et les mettre à jour en fonction des besoins avant de copier-coller.

> [!NOTE]
> Utilisez XML uniquement si vous n’utilisez pas l’interface utilisateur d’Intune pour créer une configuration de kiosque.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Pour les utilisateurs qui se connectent en tant que compte local ou MSA

| **Expérience plein écran souhaitée** | **Configuration de kiosque recommandée** | **Méthodes de configuration**  | **Remarques** |
| --- | --- | --- | --- |
| Chaque utilisateur qui se connecte obtient l’expérience plein écran. | [Configurer un profil d’accès global affecté à plusieurs applications](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Approvisionnement du runtime-applications multiples](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | L’accès global affecté requiert [20H2 et les builds plus récentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Un utilisateur spécifique qui se connecte obtient l’expérience plein écran.  | [Configurez un profil d’accès affecté à une application unique ou multiple (si nécessaire) en spécifiant le nom d’un utilisateur spécifique.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Consultez les options prises en charge ci-dessous.](#steps-in-configuring-kiosk-mode-for-hololens) | Pour le mode plein écran à application unique, seul le compte d’utilisateur local ou le compte MSA est pris en charge sur HoloLens. <br> Pour le mode plein écran de plusieurs applications, seul le compte MSA ou le compte AAD est pris en charge sur HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Pour les utilisateurs qui se connectent en tant que compte AAD

| **Expérience plein écran souhaitée** | **Configuration de kiosque recommandée** | **Méthodes de configuration** | **Remarques** |
| --- | --- | --- | --- |
| Chaque utilisateur qui se connecte obtient l’expérience plein écran. | [Configurer un profil d’accès global affecté à plusieurs applications](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Approvisionnement du runtime-applications multiples](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | L’accès global affecté requiert [20H2 et les builds plus récentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Chaque utilisateur qui se connecte obtient l’expérience plein écran, à l’exception de certains utilisateurs. | [Configurez plusieurs profils d’accès affectés globaux de l’application en excluant certains utilisateurs (qui doivent être des propriétaires de périphériques)](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners). | • [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Approvisionnement du runtime-applications multiples](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | L’accès global affecté requiert [20H2 et les builds plus récentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Chaque utilisateur AAD obtient une expérience plein écran spécifique pour cet utilisateur. | [Configurez la configuration d’accès affectée pour chaque utilisateur en spécifiant son nom de compte AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Approvisionnement du runtime-applications multiples](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Les utilisateurs de différents groupes AAD ont l’expérience du mode plein écran uniquement pour leur groupe. | [Configurez la configuration d’accès affectée pour chaque groupe AAD souhaité.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Approvisionnement du runtime-applications multiples](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • lorsqu’un utilisateur se connecte et que HoloLens est connecté à Internet, si cet utilisateur est membre du groupe aad pour lequel la configuration de kiosque existe, l’utilisateur peut se connecter à un kiosque pour ce groupe aad. <br> • [si aucun internet n’est disponible lorsque l’utilisateur se connecte, alors l’utilisateur rencontrera HoloLens comportement du mode de défaillance.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Si la disponibilité Internet n’est pas garantie lorsque l’utilisateur se connecte et que le kiosque basé sur un groupe AAD doit être utilisé, [envisagez d’utiliser AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). |
| les utilisateurs qui doivent utiliser HoloLens à des fins temporaires bénéficient d’une expérience plein écran. | [Configurer la configuration d’accès affectée pour les visiteurs](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Approvisionnement du runtime-application unique](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • un compte d’utilisateur temporaire est créé automatiquement par HoloLens lors de la connexion et est supprimé lorsque l’utilisateur temporaire se déconnecte. <br> • Envisagez d’activer la [stratégie de connexion automatique des visiteurs](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience). |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Étapes de la configuration du mode plein écran pour HoloLens

Les configurations de kiosque peuvent être créées et appliquées de plusieurs façons :

1. Avec l’interface utilisateur du serveur MDM, par exemple les modèles kiosque d’Intune ou les configurations OMA-URI personnalisées, qui sont ensuite appliquées à distance à HoloLens.
2. Avec les packages d’approvisionnement du runtime, qui sont ensuite directement appliqués à HoloLens.

Voici les méthodes suivantes pour configurer, sélectionnez l’onglet correspondant au processus que vous souhaitez utiliser.

1. [Microsoft Intune modèle kiosque d’application unique](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune modèle kiosque d’applications multiples](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune modèle personnalisé](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Approvisionnement du runtime-applications multiples](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Approvisionnement du runtime-application unique](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Forum Aux Questions (FAQ)

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Comment les comptes des visiteurs peuvent-ils se connecter automatiquement à l’expérience plein écran ?

sur les builds [Windows holographique, version 21H1 et versions](hololens-release-notes.md#windows-holographic-version-21h1) ultérieures :

- Les configurations AAD et non-ADD prennent en charge les comptes de visiteur activés pour le mode plein écran.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>l’expérience des kiosques est-elle prise en charge sur HoloLens (1ère génération) ?

Le mode plein écran est disponible uniquement si l’appareil a Windows Holographic for Business. tous les appareils HoloLens 2 sont livrés avec Windows Holographic for Business et il n’existe aucune autre édition. chaque HoloLens 2 appareil est en mesure d’exécuter le mode plein écran.

les appareils HoloLens (1er génération) doivent être mis à niveau en termes de version du système d’exploitation et de version du système d’exploitation. voici plus d’informations sur la mise à jour d’un HoloLens (1er génération) vers [Windows Holographic for Business](hololens1-upgrade-enterprise.md) édition. pour mettre à jour un appareil HoloLens (1er génération) pour utiliser le mode plein écran, vous devez d’abord vous assurer que l’appareil s’exécute Windows 10, version 1803 ou version ultérieure. si vous avez utilisé l’outil de récupération des appareils Windows pour récupérer votre appareil HoloLens (1er génération) à sa version par défaut, ou si vous avez installé les mises à jour les plus récentes, votre appareil est prêt à être configuré.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Comment utiliser le portail de périphérique pour configurer une borne dans des environnements de non-production ?

configurez l' [appareil HoloLens pour utiliser le portail d’appareils Windows](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). Le Device Portal est un serveur Web situé sur l'appareil auquel vous pouvez vous connecter depuis un navigateur Web sur votre PC.

 > [!CAUTION]
 > quand vous configurez HoloLens pour utiliser le portail de l’appareil, vous devez activer le Mode développeur sur l’appareil. le Mode développeur sur un appareil disposant d’Windows Holographic for Business vous permet de charger des applications de manière autonome. Toutefois, ce paramètre crée un risque qu’un utilisateur puisse installer des applications qui n’ont pas été certifiées par le Microsoft Store. Les administrateurs peuvent bloquer la possibilité d’activer le mode développeur à l’aide du paramètre de **déverrouillage ApplicationManagement/AllowDeveloper** dans le [fournisseur de services de chiffrement de stratégie](/windows/client-management/mdm/policy-configuration-service-provider). [En savoir plus sur le mode développeur.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Le mode plein écran peut être défini via l’API REST du portail de l’appareil en procédant à une publication sur/API/Holographic/KioskMode/Settings avec un paramètre de chaîne de requête obligatoire (« kioskModeEnabled » avec la valeur « true » ou « false ») et un paramètre facultatif (« startupApp » avec une valeur de nom de package). N’oubliez pas que le portail des appareils est destiné aux développeurs uniquement et qu’il ne doit pas être activé sur des appareils non-développeur. L’API REST est susceptible de changer dans les futures mises à jour/versions.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problème-aucune application n’est affichée dans le menu démarrer en mode plein écran

**Symptômes**

En cas d’échec lors de l’application du mode plein écran, le comportement suivant s’affiche :

- avant Windows holographique, version 20H2-HoloLens affiche toutes les applications dans le menu Démarrer.
- Windows Holographique, version 20H2 : si un appareil possède une configuration de kiosque, qui est une combinaison de l’accès global affecté et de l’accès affecté au membre du groupe AAD, si la détermination de l’appartenance à un groupe AAD échoue, l’utilisateur voit le menu « rien ne s’affiche dans le menu Démarrer ».

    ![Image du mode plein écran à présent en cas d’échec.](images/hololens-kiosk-failure-behavior.png )

- à partir de [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), le mode plein écran recherche un accès Global affecté avant d’illustrer un menu démarrer vide. L’expérience plein écran reviendra à une configuration d’une borne globale (le cas échéant) en cas de défaillance pendant le mode plein écran du groupe AAD.

**Étapes de dépannage**

- Vérifiez que identifiant AUMID d’application est correctement spécifié et qu’il ne contient pas de versions. pour obtenir des exemples, reportez-vous à [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) pour les applications inbox.
- Assurez-vous que l’application est installée sur l’appareil pour cet utilisateur.
- Si la configuration de kiosque est basée sur des groupes AAD, vérifiez que la connectivité Internet est présente lorsque l’utilisateur AAD se connecte. Si vous le souhaitez, configurez la stratégie [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) pour que cela puisse fonctionner sans Internet.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problème : la création d’un package avec le mode plein écran a échoué

**Symptômes**

Une boîte de dialogue comme ci-dessous s’affiche.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Étapes de dépannage**

1. Cliquez sur le lien hypertexte affiché comme dans la boîte de dialogue ci-dessus.
1. Ouvrez ICD. log dans un éditeur de texte et son contenu doit indiquer l’erreur.

> [!NOTE]
> Si vous avez effectué plusieurs tentatives, vérifiez les horodatages dans le journal. Cela vous permet de vérifier uniquement les problèmes actuels.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problème : le package de configuration a été généré correctement mais n’a pas pu être appliqué.

**Symptômes**

Une erreur s’affiche lors de l’application du package de configuration sur Hololens

**Étapes de dépannage**

1. accédez au dossier dans lequel se trouve Windows projet du concepteur de Configuration pour le package d’approvisionnement du runtime.
1. Ouvrez ICD. log et assurez-vous qu’il n’y a pas d’erreurs dans le journal lors de la création du package d’approvisionnement. Certaines erreurs ne s’ouvrent pas lors de la génération, mais sont toujours consignées dans ICD. log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problème : plusieurs applications affectées à un groupe AAD ne fonctionnent pas

**Symptômes**

Dans le cas de la connexion de l’utilisateur AAD, l’appareil n’est pas en mode plein écran

**Étapes de dépannage**

- Vérifiez dans le fichier XML de configuration d’accès affecté que le GUID du groupe AAD dont l’utilisateur connecté est membre est utilisé et non le GUID de l’utilisateur AAD.
- Vérifiez que, dans le portail Intune, l’utilisateur AAD est effectivement indiqué comme membre du groupe AAD ciblé.
