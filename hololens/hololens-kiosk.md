---
title: Configurer HoloLens en tant que kiosque
description: Utilisez une configuration Kiosk pour verrouiller les applications sur HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f5c45477ab33064afe30e275f8b0003bc6022eac
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929850"
---
# Configurer HoloLens en tant que kiosque

Vous pouvez configurer un appareil HoloLens pour qu’il fonctionne en tant qu’appareil à usage fixe, également appelé *borne*, en configurant l’appareil pour qu’il s’exécute en mode plein écran. Le mode plein écran limite les applications (ou utilisateurs) qui sont disponibles sur l’appareil. Le mode Kiosk est une fonctionnalité pratique qui vous permet de dédier un périphérique HoloLens aux applications métier ou d’utiliser le périphérique HoloLens dans une démonstration d’application.

Cet article fournit des informations sur les aspects de la configuration Kiosk spécifiques aux appareils HoloLens. Pour obtenir des informations générales sur les différents types de kiosques Windows et la façon de les configurer, voir [configurer des bornes et des signes numériques sur les éditions de bureau de Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> Le mode kiosque détermine les applications disponibles lorsqu’un utilisateur se connecte à l’appareil. Le mode Kiosk n’est toutefois pas une méthode de sécurité. Il n’y a pas d’arrêt d’une application «autorisée» pour l’ouverture d’une autre application qui n’est pas autorisée. Pour bloquer les applications ou les processus de l’ouverture, utilisez [le fournisseur de services d’application Windows Defender (WDac)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) pour créer des stratégies appropriées.  

Vous pouvez utiliser le mode plein écran dans une configuration à application unique ou à plusieurs applications, et vous pouvez utiliser l’un des trois processus suivants pour configurer et déployer la configuration Kiosk.

> [!IMPORTANT]  
> Si vous supprimez la configuration multi-App, les profils de verrouillage de l’utilisateur créés par l’utilisateur sont supprimés. Toutefois, elle ne restaure pas les modifications apportées à la stratégie. Pour rétablir ces stratégies, vous devez réinitialiser l’appareil aux paramètres d’usine.

## Planifier le déploiement de Kiosk

### Configuration requise du mode plein écran

Vous pouvez configurer n’importe quel appareil HoloLens 2 pour utiliser le mode plein écran.

Pour configurer un appareil HoloLens (1er génération) pour utiliser le mode plein écran, vous devez d’abord vous assurer que l’appareil exécute Windows 10, version 1803 ou une version ultérieure. Si vous avez utilisé l’outil de récupération d’appareils Windows pour récupérer votre appareil HoloLens (1er génération) sur sa Build par défaut, ou si vous avez installé les dernières mises à jour, votre appareil est prêt à être configuré.

> [!IMPORTANT]  
> Pour vous aider à protéger les appareils qui s’exécutent en mode plein écran, envisagez d’ajouter des stratégies de gestion des appareils qui désactivent les fonctionnalités telles que la connectivité USB. Vous pouvez également vérifier les paramètres de votre anneau de mise à jour pour vous assurer que les mises à jour automatiques ne se produisent pas pendant les heures d’activité.

### Choisir entre une borne d’application unique ou une borne multi-App

Une borne sur une seule application démarre l’application spécifiée lorsque l’utilisateur se connecte à l’appareil. Le menu Démarrer est désactivé, comme est Cortana. Un appareil HoloLens 2 ne répond pas au mouvement de [début](hololens2-basic-usage.md#start-gesture) . Un appareil HoloLens (1ère génération) ne répond pas au mouvement de [floraison](hololens1-basic-usage.md) . Dans la mesure où une seule application peut s’exécuter, l’utilisateur ne peut pas placer d’autres applications.

Un kiosque multi-application affiche le menu démarrer lorsque l’utilisateur se connecte à l’appareil. La configuration Kiosk détermine les applications qui sont disponibles dans le menu Démarrer. Vous pouvez utiliser un kiosque multi-application pour offrir une interface conviviale aux utilisateurs en leur proposant uniquement les éléments qu’ils utilisent, et en supprimant les éléments qu’ils n’ont pas besoin d’utiliser.

Le tableau suivant répertorie les fonctionnalités des différents modes Kiosk.

| &nbsp; |Menu Démarrer |Menu actions rapides |Caméra et vidéo |Miracast |Cortana |Commandes vocales prédéfinies |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Borne d’application unique |Désactivée |Désactivée   |Désactivée |Désactivée   |Désactivée |Activée <sup> 1</sup> |
|Kiosk multi-App |Activé |Option <sup> 2 activée</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2, 3</sup>  |Activée <sup> 1</sup> |

> <sup>1 les </sup> commandes vocales associées aux fonctionnalités désactivées ne fonctionnent pas.  
> <sup>2 </sup> pour plus d’informations sur la configuration de ces fonctionnalités, voir [Sélectionner des applications Kiosk](#plan-kiosk-apps).  
> <sup>3 </sup> même si Cortana est désactivée, les commandes vocales prédéfinies sont activées.

Le tableau suivant répertorie les fonctionnalités d’assistance utilisateur des différents modes Kiosk.

| &nbsp; |Types d’utilisateurs pris en charge | Connexion automatique | Plusieurs niveaux d’accès |
| --- | --- | --- | --- |
|Borne d’application unique |Compte de service géré (MSA) dans Azure Active Directory (AAD) ou un compte local |Oui |Non |
|Kiosk multi-App |Compte AAD |Non |Oui |

Pour obtenir des exemples d’utilisation de ces fonctionnalités, consultez le tableau suivant.

|Utilisez un kiosque d’application unique pour: |Utilisez un kiosque multi-application pour: |
| --- | --- |
|Un appareil qui ne exécute qu’un guide Dynamics 365 pour les nouveaux employés. |Un appareil qui exécute les repères et l’assistance à distance pour une gamme d’employés. |
|Appareil qui exécute une application personnalisée uniquement. |Appareil qui fonctionne comme une borne pour la plupart des utilisateurs (exécutant une application personnalisée uniquement), mais qui fonctionne comme un appareil standard pour un groupe d’utilisateurs spécifique. |

### Planifier des applications Kiosk

Pour obtenir des informations générales sur la façon de sélectionner des applications Kiosk, voir [recommandations en matière de choix d’une application pour l’accès affecté (mode plein écran)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Si vous utilisez Windows Device Portal pour configurer une borne sur une seule application, vous devez sélectionner l’application pendant le processus d’installation.  

Si vous utilisez un système de gestion des appareils mobiles ou de déploiement pour configurer le mode kiosque, vous devez utiliser le fournisseur de [services de configuration (CSP) AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) pour spécifier des applications. Le fournisseur de services d’application utilise des [ID de modèle d’application (aumid)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) pour identifier les applications. Le tableau suivant répertorie les Aumid de certaines applications prédéfinies que vous pouvez utiliser dans une borne multi-application.

> [!CAUTION]
> Vous ne pouvez pas sélectionner l’application Shell en tant qu’application Kiosk. Par ailleurs, il est recommandé de ne **pas** sélectionner Microsoft Edge, Microsoft Store ou l’Explorateur de fichiers en tant qu’application Kiosk.  

<a id="aumids"></a>

|Nom de l’application |AUMID |
| --- | --- |
|Visionneuse3D |Microsoft. Microsoft3DViewer \ _8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendrier |Microsoft. windowscommunicationsapps \ _8wekyb3d8bbwe \. Microsoft. windowslive. Calendar |
|Caméra <sup> 1, 2</sup> |HoloCamera \ _cw5n1h2txyewy \! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft. 549981C3F5F10 \ _8wekyb3d8bbwe \! Appli |
|Sélecteur d’appareil sur HoloLens (1er génération) |HoloDevicesFlow \ _cw5n1h2txyewy \! HoloDevicesFlow |
|Sélecteur d’appareil sur HoloLens 2 |Microsoft. Windows. DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. guides \ _8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \ _8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub de commentaires &nbsp; |Microsoft. WindowsFeedbackHub \ _8wekyb3d8bbwe \! Appli |
|Explorateur de fichiers |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |Microsoft. windowscommunicationsapps_8wekyb3d8bbwe. Microsoft. windowslive. mail |
|MicrosoftStore |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Films et TV |Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |Microsoft. microsoftskydrive \ _8wekyb3d8bbwe \! Appli |
|Photos |Microsoft. Windows. photos \ _8wekyb3d8bbwe \! Appli |
|Paramètres |HolographicSystemSettings \ _cw5n1h2txyewy \! Appli |
|Conseils |Microsoft. HoloLensTips \ _8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 </sup> pour activer la capture photo ou vidéo, vous devez activer l’application caméra en tant qu’application Kiosk.  
> <sup>2 </sup> lors de l’activation de l’application appareil photo, prenez en compte les conditions suivantes:
> - Le menu actions rapides inclut les boutons photo et vidéo.  
> - Vous devez également activer une application (par exemple, des photos, du courrier ou des OneDrive) qui peut interagir avec des images ou en récupérer.  
>  
> <sup>3 </sup> même si vous n’activez pas Cortana en tant qu’application Kiosk, les commandes vocales intégrées sont activées. Toutefois, les commandes associées aux fonctionnalités désactivées ne sont pas prises en compte.  
> <sup>4 </sup> vous ne pouvez pas activer le Miracast directement. Pour activer Miracast en tant qu’application Kiosk, activez l’application caméra et l’application de sélecteur d’appareil.

### Planifier les utilisateurs et les groupes d’appareils

Dans un environnement GPM, vous utilisez des groupes pour gérer les configurations d’appareils et l’accès utilisateur. 

Le profil de configuration Kiosk inclut le paramètre **type d’ouverture de session** de l’utilisateur. Le **type de connexion** de l’utilisateur identifie l’utilisateur (ou le groupe qui contient les utilisateurs) qui peut utiliser l’application ou les applications que vous ajoutez. Si un utilisateur se connecte à l’aide d’un compte qui n’est pas inclus dans le profil de configuration, il ne peut pas utiliser les applications sur la borne.  

> [!NOTE]  
> Le **type d’ouverture de session** d’une borne d’application unique spécifie un seul compte d’utilisateur. Il s’agit du contexte d’utilisateur sous lequel s’exécute la Kiosk. Le **type d’ouverture de session** d’une borne multi-App peut spécifier un ou plusieurs comptes d’utilisateurs ou groupes qui peuvent utiliser la borne.

Avant de pouvoir déployer la configuration Kiosk sur un appareil, vous devez *affecter* le profil de la configuration Kiosk à un groupe qui contient l’appareil ou un utilisateur qui peut se connecter à l’appareil. Ce paramètre génère un comportement tel que celui-ci.

- Si l’appareil est membre du groupe affecté, la configuration Kiosk est déployée sur le périphérique la première fois qu’un utilisateur se connecte à l’appareil.  
- Si l’appareil n’est pas membre du groupe affecté, mais qu’un utilisateur membre de ce groupe se connecte, la configuration Kiosk est déployée sur le périphérique à ce moment.

Pour plus d’informations sur les effets de l’attribution de profils de configuration dans Intune, voir [affecter des profils utilisateur et d’appareil dans Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

> [!NOTE]  
> Les exemples suivants décrivent des kiosques à plusieurs applications. Les bornes à application unique se comportent de la même façon, mais un seul compte d’utilisateur obtient l’interface Kiosk.

**Exemple1**

Vous utilisez un seul groupe (groupe 1) pour les appareils et les utilisateurs. Un appareil et les utilisateurs A, B et C sont membres de ce groupe. Vous pouvez configurer le profil de la configuration Kiosk comme suit:  

- **Type de connexion utilisateur**: groupe 1
- **Groupe affecté**: groupe 1

Quels que soient les utilisateurs qui se connectent d’abord à l’appareil (et passent par le biais de l’OOBE (out-of-Box Experience), la configuration Kiosk est déployée sur l’appareil. Les utilisateurs A, B et C peuvent se connecter à l’appareil et bénéficier de l’interface Kiosk.

**Exemple2**

Vous contractez des appareils pour deux fournisseurs différents qui ont besoin d’expériences Kiosk différentes. Les deux fournisseurs ont des utilisateurs et vous souhaitez que tous les utilisateurs puissent accéder aux kiosques de leur propre fournisseur et de l’autre fournisseur. Vous pouvez configurer les groupes comme suit:

- Groupe de périphériques 1:
  - Appareil 1 (fournisseur 1)
  - Appareil 2 (fournisseur 1)

- Groupe de périphériques 2:
  - Appareil 3 (fournisseur 2)
  - Appareil 4 (fournisseur 2)

- Groupe d’utilisateurs:
  - Utilisateur A (fournisseur 1)
  - Utilisateur B (fournisseur 2)

Vous créez deux profils de configuration Kiosk qui présentent les paramètres suivants:

- Profil Kiosk 1:
   - **Type de connexion utilisateur**: groupe d’utilisateurs
   - **Groupe affecté**: groupe de périphériques 1

- Profil Kiosk 2:
   - **Type de connexion utilisateur**: groupe d’utilisateurs
   - **Groupe affecté**: groupe de périphériques 2

Ces configurations génèrent les résultats suivants:

- Lorsqu’un utilisateur se connecte à l’appareil 1 ou à l’appareil 2, Intune déploie le profil Kiosk 1 sur cet appareil.
- Lorsqu’un utilisateur se connecte à l’appareil 3 ou à l’appareil 4, Intune déploie le profil Kiosk 2 sur cet appareil.
- Les utilisateurs A et B peuvent se connecter à l’un des quatre appareils suivants. S’il se connecte à l’appareil 1 ou à l’appareil 2, il voit l’interface du fabricant 1 Kiosk. S’il se connecte à l’appareil 3 ou à l’appareil 4, il voit l’interface du fabricant 2 Kiosk.

#### Conflits de profil

Si au moins deux profils de configuration Kiosk visent le même appareil, ils sont en conflit. Dans le cas des appareils gérés par Intune, Intune n’applique aucun des profils en conflit.

D’autres types de profils et de stratégies, tels que les restrictions d’appareil qui ne sont pas associées au profil de configuration Kiosk, n’entrent pas en conflit avec le profil de configuration Kiosk.

### Sélectionner une méthode de déploiement

Vous pouvez sélectionner l’une des méthodes suivantes pour déployer des configurations Kiosk:

- [Microsoft Intune ou service de gestion des périphériques mobiles (GPM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Package d’approvisionnement](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [WindowsDevicePortal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Étant donné que cette méthode nécessite que le mode développeur soit activé sur l’appareil, nous vous recommandons de l’utiliser uniquement pour les démonstrations.

Le tableau suivant répertorie les fonctionnalités et les avantages de chacune des méthodes de déploiement.

| &nbsp; |Déploiement à l’aide de Windows Device Portal |Déploiement à l’aide d’un package de mise à service |Déploiement à l’aide de la gestion des périphériques mobiles |
| --------------------------- | ------------- | -------------------- | ---- |
|Déploiement de bornes pour une seule application   | Oui           | Oui                  | Oui  |
|Déploiement de bornes multi-App    | Non            | Oui                  | Oui  |
|Déploiement sur les appareils locaux uniquement | Oui           | Oui                  | Non   |
|Déploiement via le mode développeur |Requis       | Non requis            | Non requis   |
|Déploiement à l’aide d’Azure Active Directory (AAD)  | Non requis            | Non requis                   | Requis  |
|Déployer automatiquement      | Non            | Non                   | Oui  |
|Vitesse de déploiement            | Aussi       | Rapide                 | Lent |
|Déploiement à l’échelle | Déconseillé    | Déconseillé        | Nos recommandations |

## Utiliser Microsoft Intune ou un autre GPM pour configurer une borne d’application unique ou multi-App

Pour configurer le mode plein écran à l’aide de Microsoft Intune ou d’un autre système de gestion des périphériques mobiles, procédez comme suit.

1. [Préparez-vous à inscrire les appareils](#mdmenroll).
1. [Créer un profil de configuration Kiosk](#mdmprofile).
1. Configurez la borne.
   - [Configurez les paramètres d’une borne pour une seule application](#mdmconfigsingle).
   - [Configurer les paramètres d’une borne multi-App](#mdmconfigmulti).
1. [Assignez le profil de la configuration Kiosk à un groupe](#mdmassign).
1. Déployez les appareils.
   - [Déploiement d’une borne pour une seule application](#mdmsingledeploy).
   - [Déploiement d’une borne multi-App](#mdmmultideploy).

### <a id="mdmenroll"></a>MDM, étape 1 &ndash; préparer l’inscription des appareils

Vous pouvez configurer votre système de gestion de périphériques mobiles pour qu’ils inscrivent automatiquement les appareils HoloLens lorsque l’utilisateur se connecte pour la première fois, ou qu’ils inscrivent les appareils manuellement. Les appareils doivent également être joints à votre domaine Azure AD et attribués aux groupes appropriés.

Pour plus d’informations sur la façon d’inscrire les appareils, voir [inscrire HoloLens dans](hololens-enroll-mdm.md) les [méthodes de déploiement de la gestion des appareils mobiles pour les appareils Windows](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a id="mdmprofile"></a>MDM, étape 2 &ndash; créer un profil de configuration Kiosk

1. Ouvrez le portail [Azure](https://portal.azure.com/) et connectez-vous à votre compte d’administrateur Intune.
1. Sélectionnez **Microsoft Intune**  >  **configuration de périphériques Microsoft Intune-profils**  >  **créer le profil**.
1. Entrez un nom de profil.
1. Sélectionnez **plateforme**  >  **Windows 10 et versions ultérieures**, puis sélectionnez restrictions d’appareil de **type de profil**  > **Device restrictions**.
1. Sélectionnez **configurer**  >  un**kiosque**, puis sélectionnez l’une des options suivantes:
   - Pour créer une borne pour une seule application, sélectionnez Kiosk **mode Kiosk**  >  **sur**une seule application.
   - Pour créer une borne multiapplication, sélectionnez **Kiosk Mode**  >  **Kiosk multi-App**en mode kiosque.
1. Pour commencer à configurer la borne, sélectionnez **Ajouter**.

Les étapes suivantes diffèrent selon le type de kiosque souhaité. Pour plus d’informations, sélectionnez l’une des options suivantes:  

- [Borne d’application unique](#mdmconfigsingle)
- [Kiosk multi-App](#mdmconfigmulti)

Pour plus d’informations sur la création d’un profil de configuration Kiosk, voir les paramètres de l' [appareil Windows 10 et Windows holographique pour les entreprises à exécuter comme borne dédiée à l’aide de Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a id="mdmconfigsingle"></a>MDM, étape 3 (application unique) &ndash;  configurer les paramètres d’une borne pour une seule application

Cette section résume les paramètres requis par un kiosque d’application unique. Pour plus d’informations, consultez les articles suivants:

- Pour plus d’informations sur la configuration d’un profil de configuration Kiosk dans Intune, voir [Comment configurer le mode plein écran à l’aide de Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Pour plus d’informations sur les paramètres disponibles pour les kiosques à une seule application dans Intune, voir les [kiosques d’application en mode plein écran](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) .
- Pour d’autres services de GPM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous devez utiliser une configuration XML personnalisée pour configurer une borne dans votre service de gestion des périphériques mobiles, [créez un fichier XML qui définit la configuration Kiosk](#ppkioskconfig).

1. Sélectionnez **ouverture de session**  >  de l’utilisateur, compte d'**utilisateur local**, puis entrez le nom d’utilisateur du compte local (appareil) ou du compte Microsoft (MSA) qui peut se connecter à la borne.
   > [!NOTE]  
   > Les types de comptes d’utilisateur **Autologon** ne sont pas pris en charge sur Windows holographique pour les entreprises.
1. Sélectionnez **Application type**application  >  du**magasin**de types d’application, puis sélectionnez une application dans la liste.

L’étape suivante consiste à [affecter](#mdmassign) le profil à un groupe.

### <a id="mdmconfigmulti"></a>Gestion des périphériques mobiles (GPM, l’étape 3) &ndash; configurer les paramètres d’une borne multipoint

Cette section résume les paramètres requis par un kiosque sur plusieurs applications. Pour obtenir des informations plus détaillées, consultez les articles suivants:

- Pour plus d’informations sur la configuration d’un profil de configuration Kiosk dans Intune, voir [Comment configurer le mode plein écran à l’aide de Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Pour plus d’informations sur les paramètres disponibles pour les kiosques multi-applications dans Intune, voir [kiosques multiples](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) de l’application.
- Pour d’autres services de GPM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous avez besoin d’utiliser une configuration XML personnalisée pour configurer une borne dans votre service de gestion des périphériques mobiles, [créez un fichier XML qui définit la configuration Kiosk](#ppkioskconfig). Si vous utilisez un fichier XML, veillez à inclure la [mise en page d’accueil](#start-layout-for-hololens).  
- Vous pouvez éventuellement utiliser une disposition de démarrage personnalisée avec Intune ou d’autres services de gestion des périphériques mobiles. Pour plus d’informations, voir [Démarrer le fichier de disposition pour la gestion des périphériques mobiles (Intune, etc.)](#start-layout-file-for-mdm-intune-and-others).

1. **Pour les appareils en mode S, sélectionnez Target Windows 10**  >  **No**.  
   >[!NOTE]  
   > Le mode S n’est pas pris en charge sur Windows holographique pour les entreprises.
1. Sélectionnez **ouverture de session de l’utilisateur**  >  **Azure ad utilisateur ou groupe** **d’ouverture de session d’utilisateur**  >  **HoloLens visiteur**, puis ajoutez un ou plusieurs groupes d’utilisateurs.  

   Seuls les utilisateurs qui appartiennent aux groupes ou comptes que vous spécifiez dans le **type d’ouverture de session** de l’utilisateur peuvent utiliser l’interface Kiosk.

1. Sélectionnez une ou plusieurs applications à l’aide des options suivantes:
   - Pour ajouter une application métier chargée, sélectionnez **Ajouter une application** du Windows Store, puis sélectionnez l’application de votre choix.
   - Pour ajouter une application en spécifiant son AUMID, sélectionnez **Ajouter par AUMID** puis entrez la AUMID de l’application. [Affichage de la liste des Aumid disponibles](#aumids)

L’étape suivante consiste à [affecter](#mdmassign) le profil à un groupe.

### <a id="mdmassign"></a>MDM, étape 4 &ndash; attribuez le profil de configuration Kiosk à un groupe.

Utilisez la page **Assignments** du profil de configuration Kiosk pour définir l’emplacement de déploiement de la configuration Kiosk. Dans le cas le plus simple, vous assignez le profil de la configuration Kiosk à un groupe qui contient l’appareil HoloLens lorsque l’appareil s’inscrit dans la gestion des périphériques mobiles.

### <a id="mdmsingledeploy"></a>Gestion des périphériques mobiles dans l’étape 5 (application unique) &ndash; déploiement d’une borne pour une seule application

Lorsque vous utilisez un système de gestion des appareils mobiles, vous pouvez inscrire l’appareil dans la gestion des périphériques mobiles dans OOBE. Lorsque OOBE est terminé, il est facile de se connecter à l’appareil.

Dans OOBE, procédez comme suit:

1. Connectez-vous à l’aide du compte que vous avez spécifié dans le profil de configuration Kiosk.
1. Inscrire l’appareil. Assurez-vous que le périphérique est ajouté au groupe auquel le profil de configuration Kiosk est attribué.
1. Attendez la fin de l’exécution du programme d’installation du Windows Store et des stratégies à appliquer. Redémarrez ensuite l’appareil.

Lors de votre prochaine connexion à l’appareil, l’application Kiosk doit démarrer automatiquement.

Si vous ne voyez pas votre configuration Kiosk à ce stade, [Vérifiez l’état de l’affectation](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a id="mdmmultideploy"></a>Gestion des périphériques mobiles dans le cadre de l’étape 5 (multi-App) &ndash;

Lorsque vous utilisez un système de gestion des appareils mobiles, vous pouvez joindre l’appareil à votre client Azure AD et inscrire l’appareil dans la gestion des périphériques mobiles dans OOBE. Le cas échéant, fournissez les informations d’inscription aux utilisateurs de telle sorte qu’ils soient disponibles lors du processus OOBE.

> [!NOTE]  
> Si vous avez attribué le profil de configuration Kiosk à un groupe qui contient des utilisateurs, assurez-vous que l’un de ces comptes d’utilisateur est le premier compte à se connecter à l’appareil.

Dans OOBE, procédez comme suit:

1. Connectez-vous à l’aide du compte qui appartient au groupe de **types d’ouverture de session** de l’utilisateur.
1. Inscrire l’appareil.
1. Attendez que les applications qui font partie du profil de configuration Kiosk soient téléchargées et installées. Par ailleurs, attendez que les stratégies soient appliquées.  
1. Après la fin de l’OOBE, vous pouvez installer des applications supplémentaires à partir du Microsoft Store ou de chargement indépendant. [Applications requises](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) pour le groupe auquel l’appareil appartient pour une installation automatique.
1. Une fois l’installation terminée, redémarrez l’appareil.

La prochaine fois que vous vous connectez à l’appareil à l’aide d’un compte qui appartient au **type d’ouverture de session**de l’utilisateur, l’application Kiosk doit démarrer automatiquement.

Si vous ne voyez pas votre configuration Kiosk à ce stade, [Vérifiez l’état de l’affectation](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## Utiliser un package de mise à niveau pour configurer une borne d’application unique ou multi-App

Pour configurer le mode plein écran à l’aide d’un package de mise en service, procédez comme suit.

1. [Créez un fichier XML qui définit la configuration Kiosk](#ppkioskconfig), y compris une [disposition de démarrage](#start-layout-for-hololens).
2. [Ajoutez le fichier XML à un package de mise à service.](#ppconfigadd)
3. [Appliquez le package de mise à service à HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Package de mise en service, étape 1: &ndash; créer un fichier XML de configuration Kiosk

Suivez [les instructions générales de création d’un fichier XML de configuration Kiosk pour ordinateur de bureau Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), à l’exception des suivants:

- N’incluez pas les applications Windows classiques (Win32). HoloLens n’est pas compatible avec ces applications.
- Utilisez le [code XML](#start-layout-for-hololens) de la disposition de début de l’espace réservé pour HoloLens.
- Facultatif: ajouter l’accès invité à la configuration Kiosk

#### <a id="ppkioskguest"></a>Facultatif: ajouter l’accès invité à la configuration Kiosk

Dans la [section **config** du fichier XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), vous pouvez configurer un groupe spécial intitulé **visiteur** pour autoriser les invités à utiliser la borne. Lorsque la borne est configurée pour prendre en charge le groupe spécial du **visiteur** , une option «**invité**» est ajoutée à la page de connexion. Le compte **invité** ne nécessite pas de mot de passe et toutes les données associées au compte sont supprimées lorsque le compte se déconnecte.

Pour activer le compte **invité** , ajoutez l’extrait de code suivant à votre fichier XML de configuration Kiosk:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Disposition de début de l’espace réservé pour HoloLens

Si vous utilisez un [package de mise en service](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) pour configurer une borne multi-App, la procédure nécessite une disposition de démarrage. La personnalisation de la disposition de démarrage n’est pas prise en charge dans Windows holographique pour les entreprises. Par conséquent, vous devez utiliser une disposition de démarrage d’espace réservé.

> [!NOTE]  
> Dans la mesure où une borne d’application unique démarre l’application Kiosk quand un utilisateur se connecte, il n’utilise pas de menu Démarrer et ne doit pas avoir de disposition de démarrage.

> [!NOTE]  
> Si vous utilisez la gestion des périphériques mobiles, vous pouvez éventuellement utiliser une [disposition de démarrage](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) . Pour plus d’informations, reportez-vous à la section [espace réservé de début de la présentation pour le GPM (Intune,](#start-layout-file-for-mdm-intune-and-others)etc.).

Pour la disposition de démarrage, ajoutez la section **StartLayout** suivante au fichier XML Kiosk disvisioning:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Fichier de disposition de début d’espace réservé pour le GPM (Intune, etc.)

Enregistrez l’exemple suivant sous la forme d’un fichier XML. Vous pouvez utiliser ce fichier lorsque vous configurez le kiosque multi-app dans Microsoft Intune (ou dans un autre service de gestion des applications mobiles qui fournit un profil Kiosk).

> [!NOTE]
> Si vous devez utiliser un paramètre personnalisé et une configuration XML complète pour configurer une borne dans votre service de gestion des périphériques mobiles, utilisez les [instructions de mise en page de démarrage d’un package de mise en service](#start-layout-for-hololens).

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a>Attest. étape 2: &ndash; Ajouter le fichier XML de configuration Kiosk à un package de mise en service

1. Ouvrez le [Concepteur de configuration de Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Sélectionnez **approvisionnement avancé**, entrez un nom pour votre projet, puis sélectionnez **suivant**.
1. Sélectionnez **Windows 10 holographique**, puis cliquez sur **suivant**.
1. Cliquez sur **Terminer**. L’espace de travail de votre package s’ouvre.
1. Sélectionnez **paramètres d’exécution**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. Dans le volet central, sélectionnez **Parcourir** pour rechercher et sélectionner le fichier XML de configuration Kiosk que vous avez créé.

   ![Capture d’écran du champ MultiAppAssignedAccessSettings dans le Concepteur de configuration Windows](./images/multiappassignedaccesssettings.png)

1. **Facultatif**. (Si vous souhaitez appliquer le package de mise à disponibilité après la configuration initiale de l’appareil, et qu’un utilisateur administrateur est déjà disponible sur le périphérique Kiosk, ignorez cette étape.) Sélectionnez utilisateurs de comptes de **paramètres d’exécution** &gt; **Accounts** &gt; **Users**, puis créez un compte d’utilisateur. Entrez un nom d’utilisateur et un mot de passe **UserGroup**, puis sélectionnez  >  **administrateurs**UserGroup.  
  
     En utilisant ce compte, vous pouvez afficher l’État et les journaux de la mise en service.  
1. **Facultatif**. (Si vous disposez déjà d’un compte autre que celui de l’administrateur sur votre appareil Kiosk, ignorez cette étape.) Sélectionnez utilisateurs de comptes de **paramètres d’exécution** &gt; **Accounts** &gt; **Users**, puis créez un compte d’utilisateur local. Vérifiez que le nom d’utilisateur est le même que celui que vous spécifiez dans le fichier XML de configuration. Sélectionnez **UserGroup**  >  **utilisateurs standard**UserGroup.
1. Sélectionnez **fichier**  >  **Enregistrer**.
1. Sélectionnez **Exporter**  >  le**package de mise en service**, puis sélectionnez **propriétaire**de l'  >  **administrateur**. Le niveau de priorité de ce package de mise en service est supérieur aux packages de mise en service appliqués à cet appareil à partir d’autres sources.
1. Sélectionnez **Suivant**.
1. Dans la page **sécurité du package de mise en service** , sélectionnez une option de sécurité.
   > [!IMPORTANT]  
   > Si vous sélectionnez **activer la signature de package**, vous devez également sélectionner un certificat valide à utiliser pour signer le package. Pour cela, sélectionnez **Parcourir** , puis sélectionnez le certificat que vous voulez utiliser pour signer le package.
   
   > [!CAUTION]  
   > Ne sélectionnez pas **activer le chiffrement de package**. Sur les appareils HoloLens, ce paramètre entraîne l’échec de la mise en service.
1. Sélectionnez **Suivant**.
1. Spécifiez l’emplacement de sortie dans lequel vous souhaitez que le package de mise en service soit placé lors de sa création. Par défaut, le Concepteur de configuration Windows utilise le dossier de projet comme emplacement de sortie. Si vous voulez modifier l’emplacement de sortie, sélectionnez **Parcourir**. Lorsque vous avez terminé, cliquez sur **suivant**.
1. Pour commencer à générer le package, sélectionnez **Build** . La génération du package d'approvisionnement est rapide. La page de génération affiche les informations du projet et la barre de progression indique l’état de la Build.

### <a id="ppapply"></a>Package de mise en service, étape 3 &ndash; appliquer le package de mise à service à HoloLens

L’article «configurer HoloLens à l’aide d’un package de mise à service» fournit des instructions détaillées pour appliquer le package de mise en service dans les cas suivants:

- Vous pouvez [appliquer un package de mise à service à HoloLens lors de l’installation](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Vous pouvez également [appliquer un package de mise à service à HoloLens après l’installation](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## Utiliser Windows Device Portal pour configurer une borne sur une seule application

Pour configurer le mode plein écran à l’aide de Windows Device Portal, procédez comme suit.

> [!IMPORTANT]
> Le mode kiosque est disponible uniquement si l’appareil est équipé [de Windows holographique pour les entreprises](hololens1-upgrade-enterprise.md) .

1. [Configurer l’appareil HoloLens pour qu’il utilise Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Le Device Portal est un serveur Web situé sur l'appareil auquel vous pouvez vous connecter depuis un navigateur Web sur votre PC.

    > [!CAUTION]
    > Lorsque vous configurez HoloLens pour utiliser Device Portal, vous devez activer le mode développeur sur l’appareil. Le mode développeur sur un appareil disposant de Windows holographique pour les entreprises vous permet d’effectuer des applications de charge latérale. Toutefois, ce paramètre génère un risque qu’un utilisateur puisse installer des applications qui n’ont pas été certifiées par le Microsoft Store. Les administrateurs peuvent bloquer la possibilité d’activer le mode développeur à l’aide du paramètre de **déverrouillage ApplicationManagement/AllowDeveloper** du [fournisseur de services de cryptographie](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)de la stratégie. [En savoir plus sur le mode développeur.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Sur un ordinateur, connectez-vous au HoloLens à l’aide du [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou du [bus USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Effectuez l'une des opérations suivantes:
   - Si vous vous connectez à Windows Device Portal pour la première fois, [créez un nom d’utilisateur et un mot de passe](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password) .
   - Entrez le nom d’utilisateur et le mot de passe que vous avez précédemment configurés.

    > [!TIP]
    > Si une erreur de certificat s'affiche dans le navigateur, [procédez comme suit pour résoudre le problème](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. Dans Windows Device Portal, sélectionnez **mode plein écran**.

1. Sélectionnez **activer le mode plein écran**, sélectionnez une application à exécuter au démarrage de l’appareil, puis sélectionnez **Enregistrer**.

    ![Mode plein écran](images/kiosk.png)
1. Redémarrez HoloLens. Si votre page Device Portal est encore ouverte, vous pouvez sélectionner **redémarrer** en haut de la page.

## Informations supplémentaires

Apprenez à configurer une borne à l’aide d’un package de mise en service.  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
