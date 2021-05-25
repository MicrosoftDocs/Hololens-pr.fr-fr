---
title: Configurer HoloLens en tant que kiosque
description: Découvrez comment configurer et utiliser une configuration de kiosque pour verrouiller les applications sur les appareils HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397800"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurer HoloLens en tant que kiosque

Vous pouvez configurer un appareil HoloLens pour qu’il fonctionne comme un appareil à usage fixe, également appelé *kiosque*, en configurant l’appareil pour qu’il s’exécute en mode plein écran. Le mode plein écran limite les applications (ou utilisateurs) qui sont disponibles sur l’appareil. Le mode plein écran est une fonctionnalité pratique que vous pouvez utiliser pour dédier un appareil HoloLens à des applications d’entreprise, ou pour utiliser le périphérique HoloLens dans une démonstration d’application.

Cet article fournit des informations sur les aspects de la configuration de la kiosque qui sont propres aux appareils HoloLens. Pour obtenir des informations générales sur les différents types de kiosques Windows et sur la façon de les configurer, consultez [configurer des kiosques et des signes numériques sur les éditions Windows Desktop](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> Le mode plein écran détermine les applications qui sont disponibles lorsqu’un utilisateur se connecte à l’appareil. Toutefois, le mode plein écran n’est pas une méthode de sécurité. Elle n’empêche pas une application « autorisée » d’ouvrir une autre application qui n’est pas autorisée. Pour bloquer l’ouverture des applications ou des processus, utilisez [le fournisseur de services Windows Defender application Control (WDac)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) pour créer les stratégies appropriées.
>
> En savoir plus sur les services Microsoft pour fournir aux utilisateurs un niveau de sécurité avancé utilisé par HoloLens 2, en savoir plus sur la [séparation des États et les protections de l’isolation-Defender](security-state-separation-isolation.md#defender-protections). Ou apprenez à [utiliser WDac et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils HoloLens 2 avec Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Vous pouvez utiliser le mode plein écran dans une configuration à une ou plusieurs applications, et vous pouvez utiliser l’un des trois processus pour configurer et déployer la configuration de la kiosque.

> [!IMPORTANT]  
> La suppression de la configuration multi-applications supprime les profils User Lockdown créés par la fonctionnalité accès affecté. Toutefois, il ne restaure pas toutes les modifications de stratégie. Pour rétablir ces stratégies, vous devez réinitialiser les paramètres d’usine de l’appareil.

## <a name="plan-the-kiosk-deployment"></a>Planifier le déploiement de la borne

Lorsque vous planifiez votre kiosque, vous devez être en mesure de répondre aux questions suivantes. Voici quelques décisions à prendre en compte lors de la lecture de cette page et d’autres éléments à prendre en considération pour ces questions.
1. **Qui utilisera votre kiosque, et quel [type de compte](hololens-identity.md) utilisera-t-il ?** Il s’agit d’une décision que vous avez probablement déjà faite et ne doit pas être ajustée pour les besoins de votre kiosque, mais elle affectera la façon dont la borne est affectée ultérieurement.
1. **Avez-vous besoin de plusieurs bornes par utilisateur/groupe ou d’une borne non activée pour certains ?** Si c’est le cas, vous souhaiterez créer votre kiosque via XML. 
1. **Combien d’applications seront dans votre kiosque ?** Si vous avez plus d’une application, vous avez besoin d’une borne multi-application. 
1. **Quelles applications seront dans votre kiosque ?** Utilisez notre liste de AUMIDs ci-dessous pour ajouter des applications In-Box en plus de vos propres applications.
1. **Comment envisagez-vous de déployer votre kiosque ?** Si vous inscrit un appareil dans MDM, nous vous suggérons d’utiliser MDM pour déployer votre kiosque. Si vous n’utilisez pas MDM, le déploiement avec le package de provisionnement est disponible.  

### <a name="kiosk-mode-requirements"></a>Conditions requises pour le mode plein écran

Vous pouvez configurer n’importe quel appareil HoloLens 2 pour utiliser le mode plein écran.

> [!IMPORTANT]
> Le mode plein écran est disponible uniquement si l’appareil a Windows holographique for Business. Tous les appareils HoloLens 2 sont livrés avec Windows holographique for Business et il n’existe aucune autre édition. Tous les appareils HoloLens 2 sont en mesure d’exécuter le mode plein écran.
>
> Les appareils HoloLens (1er génération) doivent être mis à niveau en termes de version du système d’exploitation et de version du système d’exploitation. Voici plus d’informations sur la mise à jour d’un HoloLens (1ère génération) vers [Windows holographique for Business](hololens1-upgrade-enterprise.md) Edition. Pour mettre à jour un appareil HoloLens (1er génération) pour utiliser le mode plein écran, vous devez d’abord vous assurer que l’appareil exécute Windows 10, version 1803 ou une version ultérieure. Si vous avez utilisé l’outil de récupération des appareils Windows pour récupérer votre appareil HoloLens (1er génération) à sa version par défaut, ou si vous avez installé les mises à jour les plus récentes, votre appareil est prêt à être configuré.

> [!IMPORTANT]  
> Pour aider à protéger les appareils qui s’exécutent en mode plein écran, pensez à ajouter des stratégies de gestion des appareils qui désactivent les fonctionnalités telles que la connectivité USB. Vérifiez également les paramètres de l’anneau de mise à jour pour vous assurer que les mises à jour automatiques ne se produisent pas pendant les heures de bureau.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Choisir entre une borne à une seule application ou une borne à plusieurs applications

Une borne à une seule application démarre l’application spécifiée lorsque l’utilisateur se connecte à l’appareil. Le menu Démarrer est désactivé, comme c’est le cas de Cortana. Un appareil HoloLens 2 ne répond pas au geste de [démarrage](hololens2-basic-usage.md#start-gesture) . Un appareil HoloLens (1er génération) ne répond pas au geste de [floraison](hololens1-basic-usage.md) . Étant donné qu’une seule application peut s’exécuter, l’utilisateur ne peut pas placer d’autres applications.

Une borne multi-application affiche le menu démarrer lorsque l’utilisateur se connecte à l’appareil. La configuration plein écran détermine les applications qui sont disponibles dans le menu Démarrer. Vous pouvez utiliser une borne multi-application pour offrir une expérience facile à comprendre aux utilisateurs en leur fournissant uniquement les éléments qu’ils doivent utiliser et en supprimant les éléments qu’ils n’ont pas besoin d’utiliser.

Le tableau suivant répertorie les fonctionnalités des fonctionnalités dans les différents modes de kiosque.

| &nbsp; |Menu Démarrer |Menu actions rapides |Caméra et vidéo |Miracast |Cortana |Commandes vocales intégrées |
| --- | --- | --- | --- | --- | --- | --- | 
|Borne pour une seule application |Désactivé |Désactivé |Désactivé |Désactivé   |Désactivé |Activé<sup>1</sup> |
|Kiosque multi-application |activé |Activé<sup>2</sup> |Disponible<sup>2</sup> |Disponible<sup>2</sup> |<sup>2, 3</sup> disponibles  |Activé<sup>1</sup> |

> <sup>1</sup> les commandes vocales relatives aux fonctionnalités désactivées ne fonctionnent pas.  
> <sup>2</sup> pour plus d’informations sur la configuration de ces fonctionnalités, consultez [Sélectionner des applications Kiosk](#plan-kiosk-apps).  
> <sup>3</sup> même si Cortana est désactivée, les commandes vocales intégrées sont activées.

Le tableau suivant répertorie les fonctionnalités de prise en charge des utilisateurs des différents modes kiosque.

| &nbsp; |Types d’utilisateurs pris en charge | Connexion automatique | Plusieurs niveaux d’accès |
| --- | --- | --- | --- |
|Borne pour une seule application |Compte de service administré (MSA) dans Azure Active Directory (Azure AD) ou compte local |Oui |Non |
|Kiosque multi-application |Compte Azure AD |Non |Oui |

Pour obtenir des exemples d’utilisation de ces fonctionnalités, consultez le tableau suivant.

|Utilisez une borne à une seule application pour : |Utilisez une borne multi-application pour : |
| --- | --- |
|Appareil qui exécute uniquement un guide Dynamics 365 pour les nouveaux employés. |Un appareil qui exécute les deux guides et l’assistance à distance pour une gamme d’employés. |
|Périphérique qui exécute uniquement une application personnalisée. |Appareil qui fonctionne comme une borne pour la plupart des utilisateurs (exécutant uniquement une application personnalisée), mais fonctionne comme un appareil standard pour un groupe spécifique d’utilisateurs. |

### <a name="plan-kiosk-apps"></a>Planifier des applications plein écran

Pour obtenir des informations générales sur la façon de choisir des applications Kiosk, consultez [instructions pour choisir une application pour l’accès affecté (mode plein écran)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Si vous utilisez le portail des appareils Windows pour configurer une borne à une seule application, vous sélectionnez l’application pendant le processus d’installation.  

Si vous utilisez un système de gestion des appareils mobiles (MDM) ou un package d’approvisionnement pour configurer le mode plein écran, vous utilisez le [fournisseur de services de configuration (CSP) AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) pour spécifier les applications. Le CSP utilise des [ID de modèle d’utilisateur d’application (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) pour identifier les applications. Le tableau suivant répertorie les AUMIDs de certaines applications intégrées que vous pouvez utiliser dans une borne multi-application.

> [!IMPORTANT]
> Le mode plein écran détermine les applications qui sont disponibles lorsqu’un utilisateur se connecte à l’appareil. Toutefois, le mode plein écran n’est pas une méthode de sécurité. Elle n’empêche pas une application « autorisée » d’ouvrir une autre application qui n’est pas autorisée. Étant donné que nous n’avons pas limité ce comportement, les applications peuvent toujours être lancées à partir de Edge, de l’Explorateur de fichiers et des applications Microsoft Store. S’il existe des applications spécifiques que vous ne souhaitez pas lancer à partir d’une borne, utilisez [le CSP Windows Defender application Control (WDac)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) pour créer les stratégies appropriées. 
> 
> En outre, la page d’hébergement de la réalité mixte ne peut pas être définie en tant qu’application Kiosk.

<a id="aumids"></a>

|Nom de l’application |AUMID |
| --- | --- |
|Visionneuse 3D |Microsoft. Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendrier |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. les. Calendar |
|Appareil photo<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Application 8wekyb3d8bbwe Microsoft. 549981C3F5F10 \_ \! |
|Sélecteur d’appareils sur HoloLens (1ère génération) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Sélecteur d’appareils sur HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. repères \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub de commentaires &nbsp; |Application 8wekyb3d8bbwe Microsoft. WindowsFeedbackHub \_ \! |
|Explorateur de fichiers |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Messagerie |microsoft.windowscommunicationsapps_8wekyb3d8bbwe ! Microsoft. les. mail |
|Ancienne version de Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Nouveau Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe ! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|Films et TV |Microsoft. ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |application 8wekyb3d8bbwe Microsoft. microsoftskydrive \_ \! |
|Photo |Application 8wekyb3d8bbwe Microsoft. Windows. photos \_ \! |
|Anciens paramètres |HolographicSystemSettings_cw5n1h2txyewy ! Lancement |
|Nouveaux paramètres |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy ! Lancement |
|Conseils |HoloLensTips 8wekyb3d8bbwe Microsoft. HoloLensTips \_ \! |

> <sup>1</sup> pour activer la capture de photos ou de vidéos, vous devez activer l’application d’appareil photo en tant qu’application Kiosk.  
> <sup>2</sup> lorsque vous activez l’application d’appareil photo, tenez compte des conditions suivantes :
> - Le menu actions rapides comprend les boutons photo et vidéo.  
> - Vous devez également activer une application (par exemple, photos, courrier ou OneDrive) qui peut interagir avec les images ou les récupérer.  
>  
> <sup>3</sup> même si vous n’activez pas Cortana comme application Kiosk, les commandes vocales intégrées sont activées. Toutefois, les commandes associées aux fonctionnalités désactivées n’ont aucun effet.  
> <sup>4</sup> vous ne pouvez pas activer Miracast directement. Pour activer Miracast en tant qu’application Kiosk, activez l’application Camera et l’application Device Picker.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planifier des profils kiosque pour des utilisateurs ou des groupes

Lors de la création du fichier XML ou de l’utilisation de l’interface utilisateur d’Intune pour configurer une borne, vous devez prendre en compte la personne qui sera l’utilisateur de la borne. Une configuration de kiosque peut être limitée à un compte individuel ou à des groupes de Azure AD. 

En général, les bornes sont activées pour un utilisateur ou un groupe d’utilisateurs. Toutefois, si vous prévoyez d’écrire votre propre kiosque XML, vous souhaiterez peut-être envisager un accès global affecté, dans lequel la borne est appliquée au niveau de l’appareil, quelle que soit l’identité. Si vous [y êtes en savoir plus sur les bornes d’accès assignées à l’échelle mondiale.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Si vous créez un fichier XML :
-   Vous pouvez créer plusieurs profils kiosque et les affecter à des utilisateurs/groupes différents. Par exemple, une borne pour votre groupe de Azure AD avec de nombreuses applications et un visiteur qui a plusieurs bornes d’application avec une application unique.
-   La configuration de votre kiosque sera appelée **ID de profil** et possédera un GUID.
-   Vous allez attribuer ce profil dans la section configurations en spécifiant le type d’utilisateur et en utilisant le même GUID pour l' **ID DefaultProfile**.
- Un fichier XML peut être créé mais toujours appliqué à un appareil via MDM en créant un profil de configuration d’appareil URI OMA personnalisé et en l’appliquant au groupe d’appareils HoloLens à l’aide de la valeur d’URI :./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Si vous créez une borne dans Intune.
-   Chaque périphérique peut uniquement recevoir un seul profil Kiosk. sinon, il crée un conflit et ne reçoit aucune configuration de kiosque. 
    -   D’autres types de profils et de stratégies, tels que les restrictions d’appareil qui ne sont pas associées au profil de configuration Kiosk, ne sont pas en conflit avec le profil de configuration Kiosk.
-   La borne est activée pour tous les utilisateurs qui font partie du type d’ouverture de session de l’utilisateur, elle est définie avec un utilisateur ou un groupe de Azure AD. 
-   Une fois la configuration de la kiosque définie et le **type d’ouverture de session** de l’utilisateur (les utilisateurs qui peuvent se connecter à la borne) et les applications sont sélectionnés, la configuration de l’appareil doit toujours être affectée à un groupe. Le ou les groupes affectés déterminent les appareils qui reçoivent la configuration de l’appareil Kiosk, mais n’interagissent pas avec si la borne est activée ou non. 
    - Pour une présentation complète des effets de l’attribution de profils de configuration dans Intune, consultez [affecter des profils utilisateur et d’appareil dans Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Sélectionner une méthode de déploiement

Vous pouvez sélectionner l’une des méthodes suivantes pour déployer des configurations de kiosque :

- [Microsoft Intune ou un autre service de gestion des appareils mobiles (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Package d’approvisionnement](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Portail de périphériques Windows](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Étant donné que cette méthode exige que le mode développeur soit activé sur l’appareil, nous vous recommandons de l’utiliser uniquement pour les démonstrations.

Le tableau suivant répertorie les fonctionnalités et les avantages de chacune des méthodes de déploiement.

| &nbsp; |Déployer à l’aide du portail d’appareils Windows |Déployer à l’aide d’un package d’approvisionnement |Déployer à l’aide de MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Déployer des kiosques à une seule application   | Oui           | Oui                  | Oui  |
|Déployer des kiosques à plusieurs applications    | Non            | Oui                  | Oui  |
|Déployer sur des appareils locaux uniquement | Oui           | Oui                  | Non   |
|Déployer à l’aide du mode développeur |Obligatoire       | Non requis            | Non requis   |
|Déployer à l’aide de Azure Active Directory (Azure AD)  | Non requis            | Non requis                   | Obligatoire  |
|Déployer automatiquement      | Non            | Non                   | Oui  |
|Vitesse du déploiement            | Rapide       | Rapides                 | Lentes |
|Déployer à l’échelle | Non recommandé    | Recommandé        | Recommandé |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Utiliser Microsoft Intune ou d’autres MDM pour configurer une borne à une seule application ou à plusieurs applications

Pour configurer le mode plein écran à l’aide d’Microsoft Intune ou d’un autre système MDM, procédez comme suit.

1. [Préparez l’inscription des appareils](#mdmenroll).
1. [Créez un profil de configuration de kiosque](#mdmprofile).
1. Configurez l’kiosque.
   - [Configurez les paramètres d’une borne pour une seule application](#mdmconfigsingle).
   - [Configurez les paramètres d’une borne multi-application](#mdmconfigmulti).
1. [Affectez le profil de configuration Kiosk à un groupe](#mdmassign).
1. Déployez les appareils.
   - [Déployez une borne pour une seule application](#mdmsingledeploy).
   - [Déployez une borne multi-application](#mdmmultideploy).

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, étape 1 &ndash; préparer l’inscription des appareils

Vous pouvez configurer votre système MDM pour inscrire automatiquement des appareils HoloLens lorsque l’utilisateur se connecte pour la première fois, ou demander aux utilisateurs d’inscrire des appareils manuellement. Les appareils doivent également être joints à votre domaine Azure AD et être affectés aux groupes appropriés.

Pour plus d’informations sur l’inscription des appareils, consultez [inscrire HoloLens dans](hololens-enroll-mdm.md) les méthodes d’inscription MDM et [Intune pour les appareils Windows](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, étape 2 &ndash; créer un profil de configuration plein écran

1. Ouvrez le portail [Azure](https://portal.azure.com/) et connectez-vous à votre compte d’administrateur Intune.
1. Sélectionnez **Microsoft Intune**  >  **configuration de l’appareil-profils**  >  **créer un profil**.
1. Entrez un nom de profil.
1. Sélectionnez **plateforme**  >  **Windows 10 et versions ultérieures**, puis sélectionnez **type de profil** restrictions de l'  > **appareil**.
1. Sélectionnez **configurer**  >  une **borne**, puis sélectionnez l’une des options suivantes :
   - Pour créer une borne pour une seule application, sélectionnez kiosque **en mode plein**  >  **écran**.
   - Pour créer une borne multi-application, sélectionnez kiosque  >  **multi-application** en mode plein écran.
1. Pour démarrer la configuration de la borne, sélectionnez **Ajouter**.

Les étapes suivantes varient en fonction du type d’kiosque que vous souhaitez. Pour plus d’informations, sélectionnez l’une des options suivantes :  

- [Borne pour une seule application](#mdmconfigsingle)
- [Kiosque multi-application](#mdmconfigmulti)

Pour plus d’informations sur la création d’un profil de configuration plein écran, voir paramètres de l' [appareil Windows 10 et Windows holographique for Business pour s’exécuter en tant que kiosque dédié à l’aide d’Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, étape 3 (application unique) &ndash;  configurer les paramètres pour une borne d’application unique

Cette section résume les paramètres requis par une borne d’application unique. Pour plus d’informations, consultez les articles suivants :

- Pour plus d’informations sur la configuration d’un profil de configuration Kiosk dans Intune, consultez [Comment configurer le mode plein écran à l’aide de Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Pour plus d’informations sur les paramètres disponibles pour les kiosques à une seule application dans Intune, consultez [kiosques d’applications en plein écran uniques](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Pour les autres services MDM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous devez utiliser une configuration XML personnalisée pour configurer une borne dans votre service MDM, [créez un fichier XML qui définit la configuration de la borne](#ppkioskconfig).

1. Sélectionnez **connexion utilisateur type**  >  **compte d’utilisateur local**, puis entrez le nom d’utilisateur du compte local (périphérique) ou du compte Microsoft (MSA) qui peut se connecter à la borne.
   > [!NOTE]  
   > Les types de comptes d’utilisateur **Ouverture de session automatique** ne sont pas pris en charge sur Windows Holographic for Business.
1. Sélectionnez application du magasin de **types d’applications**  >  , puis sélectionnez une application dans la liste.

L’étape suivante consiste à [attribuer](#mdmassign) le profil à un groupe.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, étape 3 (multi-application) &ndash; configurer les paramètres pour une borne multi-application

Cette section résume les paramètres requis par une borne multi-application. Pour plus d’informations, voir les articles suivants :

- Pour plus d’informations sur la configuration d’un profil de configuration Kiosk dans Intune, consultez [Comment configurer le mode plein écran à l’aide de Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Pour plus d’informations sur les paramètres disponibles pour les bornes multi-applications dans Intune, consultez [bornes multi-applications](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) .
- Pour les autres services MDM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous devez utiliser une configuration XML personnalisée pour configurer une borne dans votre service MDM, [créez un fichier XML qui définit la configuration de la borne](#ppkioskconfig). Si vous utilisez un fichier XML, veillez à inclure la [disposition de démarrage](#start-layout-for-hololens).  
- Vous pouvez éventuellement utiliser une disposition de démarrage personnalisée avec Intune ou d’autres services MDM. Pour plus d’informations, consultez [fichier de disposition de démarrage pour MDM (Intune et autres)](#start-layout-file-for-mdm-intune-and-others).

1. Sélectionnez **target Windows 10 dans les appareils en mode S**  >  **non**.  
>[!NOTE]  
> Le mode S n’est pas pris en charge sur Windows Holographic for Business.

1. Sélectionnez **type d’ouverture de session de l’utilisateur**  >  **Azure ad utilisateur ou groupe** ou **utilisateur type d’ouverture de session**  >  **HoloLens visiteur**, puis ajoutez un ou plusieurs groupes d’utilisateurs ou comptes.  

   Seuls les utilisateurs qui appartiennent aux groupes ou aux comptes que vous spécifiez dans **type d’ouverture de session** de l’utilisateur peuvent utiliser l’expérience plein écran.

1. Sélectionnez une ou plusieurs applications à l’aide des options suivantes :
   - Pour ajouter une application métier chargée, sélectionnez **Ajouter une application** du Windows Store, puis sélectionnez l’application souhaitée.
   - Pour ajouter une application en spécifiant son identifiant AUMID, sélectionnez **Ajouter par identifiant aumid** , puis entrez le identifiant aumid de l’application. [Voir la liste des AUMIDs disponibles](#aumids)

L’étape suivante consiste à [attribuer](#mdmassign) le profil à un groupe.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, étape 4 &ndash; attribuer le profil de configuration Kiosk à un groupe

Utilisez la page **affectations** du profil de configuration plein écran pour définir l’emplacement où vous souhaitez déployer la configuration de la kiosque. Dans le cas le plus simple, vous affectez le profil de configuration Kiosk à un groupe qui contiendra l’appareil HoloLens lorsque l’appareil s’inscrit dans MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, étape 5 (application unique) &ndash; déployer une borne à une seule application

Lorsque vous utilisez un système MDM, vous pouvez inscrire l’appareil dans MDM pendant l’OOBE. Une fois l’exécution d’OOBE terminée, il est facile de se connecter à l’appareil.

Pendant l’OOBE, procédez comme suit :

1. Connectez-vous à l’aide du compte que vous avez spécifié dans le profil de configuration de kiosque.
1. Inscrivez le périphérique. Assurez-vous que l’appareil est ajouté au groupe auquel le profil de configuration plein écran est affecté.
1. Attendez la fin de l’exécution d’OOBE, pour le téléchargement et l’installation de l’application Windows Store et pour l’application des stratégies. Ensuite, redémarrez l’appareil.

La prochaine fois que vous vous connectez à l’appareil, l’application Kiosk doit démarrer automatiquement.

Si vous ne voyez pas la configuration de votre kiosque à ce stade, [Vérifiez l’état de l’attribution](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, étape 5 (multi-application) &ndash; déployer une borne multi-application

Lorsque vous utilisez un système MDM, vous pouvez joindre l’appareil à votre locataire Azure AD et inscrire l’appareil dans MDM au cours de l’OOBE. Le cas échéant, fournissez les informations d’inscription aux utilisateurs afin qu’ils soient disponibles pendant le processus OOBE.

> [!NOTE]  
> Si vous avez attribué le profil de configuration Kiosk à un groupe qui contient des utilisateurs, assurez-vous que l’un de ces comptes d’utilisateur est le premier compte à se connecter à l’appareil.

Pendant l’OOBE, procédez comme suit :

1. Connectez-vous à l’aide du compte qui appartient au groupe **type d’ouverture de session** de l’utilisateur.
1. Inscrivez le périphérique.
1. Attendez que toutes les applications qui font partie du profil de configuration Kiosk soient téléchargées et installées. En outre, attendez que les stratégies soient appliquées.  
1. Une fois OOBE terminé, vous pouvez installer des applications supplémentaires à partir du Microsoft Store ou de chargement. [Applications requises](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) pour le groupe auquel appartient l’appareil pour qu’il s’installe automatiquement.
1. Une fois l’installation terminée, redémarrez l’appareil.

La prochaine fois que vous vous connectez à l’appareil à l’aide d’un compte qui appartient au **type d’ouverture de session** de l’utilisateur, l’application Kiosk doit être lancée automatiquement.

Si vous ne voyez pas la configuration de votre kiosque à ce stade, [Vérifiez l’état de l’attribution](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Utiliser un package d’approvisionnement pour configurer une borne à application unique ou plusieurs applications

Pour configurer le mode plein écran à l’aide d’un package d’approvisionnement, procédez comme suit.

1. [Créez un fichier XML qui définit la configuration de la kiosque](#ppkioskconfig), y compris une [disposition de démarrage](#start-layout-for-hololens).
2. [Ajoutez le fichier XML à un package d’approvisionnement.](#ppconfigadd)
3. [Appliquez le package d’approvisionnement à HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Package d’approvisionnement, étape 1 &ndash; créer un fichier XML de configuration de kiosque

Suivez [les instructions générales pour créer un fichier XML de configuration de kiosque pour Windows Desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), à l’exception des éléments suivants :

- N’incluez pas d’applications Windows classiques (Win32). HoloLens ne prend pas en charge ces applications.
- Utilisez le [XML de disposition de début de l’espace réservé](#start-layout-for-hololens) pour HoloLens.
- Facultatif : ajouter un accès invité à la configuration de la borne

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Facultatif : ajouter un accès invité à la configuration de la borne

Dans la [section **configurations** du fichier XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), vous pouvez configurer un groupe spécial nommé **visiteur** pour autoriser les invités à utiliser la borne. Lorsque la borne est configurée pour prendre en charge le groupe spécial **visiteur** , une option «**invité**» est ajoutée à la page de connexion. Le compte **invité** ne nécessite pas de mot de passe et toutes les données associées au compte sont supprimées lorsque le compte se déconnecte.

Pour activer le compte **invité** , ajoutez l’extrait de code suivant à votre fichier XML de configuration de kiosque :

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Activer le logo automatique des visiteurs

Sur les builds [Windows holographique, version 21H1 et versions](hololens-release-notes.md#windows-holographic-version-21h1) ultérieures :
- Les configurations AAD et non-ADD prennent en charge les comptes de visiteur pour lesquels la connexion automatique est activée pour les modes plein écran.

##### <a name="non-aad-configuration"></a>Configuration non AAD

1. Créez un package d’approvisionnement qui :
    1. Configure les paramètres d’exécution/AssignedAccess pour autoriser les comptes de visiteur.
    1. Inscrit éventuellement l’appareil dans MDM (paramètres d’exécution/espace de travail/inscriptions) afin qu’il puisse être géré ultérieurement.
    1. Ne pas créer de compte local
2. [Appliquez le package d’approvisionnement](https://docs.microsoft.com/hololens/hololens-provisioning).

##### <a name="aad-configuration"></a>Configuration AAD

Les appareils joints à AAD configurés pour le mode plein écran peuvent se connecter à un compte visiteur à l’aide d’un appui sur un bouton à partir de l’écran de connexion. Une fois connecté au compte du visiteur, l’appareil ne demande pas de connexion tant que le visiteur n’est pas explicitement déconnecté du menu Démarrer ou que l’appareil n’a pas été redémarré.

L’ouverture de session automatique des visiteurs peut être gérée par le biais d' [une stratégie OMA-URI personnalisée](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10):

- Valeur de l’URI :./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Stratégie |Description |Configurations 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Permet à un visiteur de se connecter automatiquement à une borne. | 1 (oui), 0 (non, valeur par défaut.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Disposition de démarrage de l’espace réservé pour HoloLens

Si vous utilisez un [package d’approvisionnement](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) pour configurer une borne multi-application, la procédure requiert une disposition de démarrage. La personnalisation de la disposition de démarrage n’est pas prise en charge dans Windows holographique for Business. Par conséquent, vous devrez utiliser la disposition de démarrage d’un espace réservé.

> [!NOTE]  
> Étant donné qu’une borne à une seule application démarre l’application Kiosk quand un utilisateur se connecte, elle n’utilise pas de menu Démarrer et n’a pas besoin d’avoir une disposition de départ.

> [!NOTE]  
> Si vous utilisez [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) pour configurer une borne à plusieurs applications, vous pouvez éventuellement utiliser une disposition de démarrage. Pour plus d’informations, consultez [espace réservé pour le fichier de disposition de démarrage pour MDM (Intune et autres)](#start-layout-file-for-mdm-intune-and-others).

Pour la disposition Démarrer, ajoutez la section **StartLayout** suivante au fichier XML de provisionnement Kiosk :

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Fichier de disposition de début d’espace réservé pour MDM (Intune et autres)

Enregistrez l’exemple suivant sous la forme d’un fichier XML. Vous pouvez utiliser ce fichier lorsque vous configurez le kiosque à plusieurs applications dans Microsoft Intune (ou dans un autre service MDM qui fournit un profil Kiosk).

> [!NOTE]
> Si vous devez utiliser un paramètre personnalisé et une configuration XML complète pour configurer une borne dans votre service MDM, utilisez les [instructions de mise en page de démarrage pour un package d’approvisionnement](#start-layout-for-hololens).

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prouva. package, étape 2 : &ndash; Ajouter le fichier XML de configuration de kiosque à un package d’approvisionnement

1. Ouvrez le [Concepteur de configuration Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Sélectionnez **approvisionnement avancé**, entrez un nom pour votre projet, puis sélectionnez **suivant**.
1. Sélectionnez **Windows 10 holographique**, puis **suivant**.
1. Sélectionnez **Terminer**. L’espace de travail de votre package s’ouvre.
1. Sélectionnez **paramètres d’exécution**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. Dans le volet central, sélectionnez **Parcourir** pour rechercher et sélectionner le fichier XML de configuration de kiosque que vous avez créé.

   ![Capture d’écran du champ MultiAppAssignedAccessSettings dans le concepteur de configuration Windows](./images/multiappassignedaccesssettings.png)

1. **Facultatif**. (Si vous souhaitez appliquer le package d’approvisionnement après l’installation initiale de l’appareil et qu’un utilisateur administrateur est déjà disponible sur l’appareil plein écran, ignorez cette étape.) Sélectionnez **paramètres d’exécution** &gt; **comptes** &gt; **utilisateurs**, puis créez un compte d’utilisateur. Fournissez un nom d’utilisateur et un mot de passe, puis sélectionnez  >  **administrateurs** UserGroup.  
  
     À l’aide de ce compte, vous pouvez afficher l’État et les journaux d’approvisionnement.  
1. **Facultatif**. (Si vous disposez déjà d’un compte non-administrateur sur l’appareil plein écran, ignorez cette étape.) Sélectionnez **paramètres d’exécution** &gt; **comptes** &gt; **utilisateurs**, puis créez un compte d’utilisateur local. Assurez-vous que le nom d’utilisateur est le même que pour le compte que vous spécifiez dans le fichier XML de configuration. Sélectionnez   >  **utilisateurs standard** d’UserGroup.
1. Sélectionnez **fichier**  >  **Enregistrer**.
1. Sélectionnez **Exporter**  >  le **package de provisionnement**, puis sélectionnez **propriétaire**  >  **administrateur informatique**. Cela permet de définir la priorité de ce package d’approvisionnement plus élevée que les packages d’approvisionnement appliqués à cet appareil à partir d’autres sources.
1. Sélectionnez **Suivant**.
1. Sur la page **sécurité du package d’approvisionnement** , sélectionnez une option de sécurité.
   > [!IMPORTANT]  
   > Si vous sélectionnez **activer la signature de package**, vous devez également sélectionner un certificat valide à utiliser pour la signature du package. Pour ce faire, sélectionnez **Parcourir** et sélectionnez le certificat que vous souhaitez utiliser pour signer le package.
   
   > [!CAUTION]  
   > Ne sélectionnez pas **activer le chiffrement du package**. Sur les appareils HoloLens, ce paramètre entraîne l’échec de l’approvisionnement.
1. Sélectionnez **Suivant**.
1. Spécifiez l’emplacement de sortie où vous souhaitez que le package de configuration se trouve lors de sa génération. Par défaut, le concepteur de configuration Windows utilise le dossier du projet comme emplacement de sortie. Si vous souhaitez modifier l’emplacement de sortie, sélectionnez **Parcourir**. Quand vous avez terminé, cliquez sur **Suivant**.
1. Sélectionnez **Build** pour commencer à générer le package. La génération du package d’approvisionnement est rapide. La page générer affiche les informations du projet et la barre de progression indique l’état de la Build.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Package d’approvisionnement, étape 3 : &ndash; appliquer le package d’approvisionnement à HoloLens

L’article « configurer HoloLens à l’aide d’un package d’approvisionnement » fournit des instructions détaillées pour appliquer le package d’approvisionnement dans les circonstances suivantes :

- Vous pouvez initialement [appliquer un package d’approvisionnement à HoloLens au cours de l’installation](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Vous pouvez également [appliquer un package d’approvisionnement à HoloLens après l’installation](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Utiliser le portail de périphériques Windows pour configurer une borne pour une seule application

Pour configurer le mode plein écran à l’aide du portail des appareils Windows, procédez comme suit.

1. [Configurez l’appareil HoloLens pour utiliser le portail d’appareils Windows](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Le Device Portal est un serveur Web situé sur l'appareil auquel vous pouvez vous connecter depuis un navigateur Web sur votre PC.

    > [!CAUTION]
    > Quand vous configurez HoloLens pour utiliser le portail de l’appareil, vous devez activer le mode développeur sur l’appareil. Le mode développeur sur un appareil doté de Windows holographique for Business vous permet de charger des applications de manière autonome. Toutefois, ce paramètre crée un risque qu’un utilisateur puisse installer des applications qui n’ont pas été certifiées par le Microsoft Store. Les administrateurs peuvent bloquer la possibilité d’activer le mode développeur à l’aide du paramètre de **déverrouillage ApplicationManagement/AllowDeveloper** dans le [fournisseur de services de chiffrement de stratégie](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [En savoir plus sur le mode développeur.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Sur un ordinateur, connectez-vous au HoloLens à l’aide d’un [réseau Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Effectuez l’une des actions suivantes :
   - Si vous vous connectez au portail des appareils Windows pour la première fois, [créez un nom d’utilisateur et un mot de passe](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Entrez le nom d’utilisateur et le mot de passe que vous avez configurés précédemment.

    > [!TIP]
    > Si une erreur de certificat s'affiche dans le navigateur, [procédez comme suit pour résoudre le problème](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. Dans le portail de périphériques Windows, sélectionnez **mode plein écran**.

1. Sélectionnez **activer le mode plein écran**, sélectionnez une application à exécuter au démarrage de l’appareil, puis sélectionnez **Enregistrer**.

    ![Mode plein écran](images/kiosk.png)
1. Redémarrez HoloLens. Si la page du portail de votre appareil est toujours ouverte, vous pouvez sélectionner **redémarrer** en haut de la page.

> [!NOTE]
> Le mode plein écran peut être défini via l’API REST du portail de l’appareil en procédant à une publication sur/API/Holographic/KioskMode/Settings avec un paramètre de chaîne de requête obligatoire (« kioskModeEnabled » avec la valeur « true » ou « false ») et un paramètre facultatif (« startupApp » avec une valeur de nom de package). N’oubliez pas que le portail des appareils est destiné uniquement aux développeurs et qu’il ne doit pas être activé sur des appareils non-développeur. L’API REST est susceptible de changer dans les futures mises à jour/versions.

## <a name="more-information"></a>Plus d’informations

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Regardez comment configurer une borne à l’aide d’un package d’approvisionnement.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Accès global affecté – mode plein écran
- Réduction de la gestion des identités pour les bornes, en activant la nouvelle méthode Kiosk qui applique le mode plein écran au niveau du système.

Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode plein écran de plusieurs applications, applicable au niveau du système, n’a aucune affinité avec une identité sur le système et s’applique à tous les utilisateurs qui se connectent à l’appareil. Pour plus d’informations sur cette nouvelle fonctionnalité, consultez la documentation sur la [borne d’accès assignée globale HoloLens](hololens-global-assigned-access-kiosk.md) .

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Lancement automatique d’une application en mode plein écran à plusieurs applications 
- Expérience ciblée avec le lancement automatique d’applications, ce qui améliore davantage l’interface utilisateur et les sélections d’applications choisies pour les expériences en mode plein écran.

S’applique uniquement au mode plein écran à plusieurs applications et seule une application peut être désignée pour être lancée automatiquement à l’aide de l’attribut en surbrillance ci-dessous dans la configuration d’accès affectée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifications du comportement du mode plein écran pour la gestion des défaillances
En cas d’échec lors de l’application du mode plein écran, le comportement suivant s’affiche :

- Avant Windows holographique, version 20H2-HoloLens affiche toutes les applications dans le menu Démarrer.
- Windows holographique, version 20H2 : si un appareil possède une configuration de kiosque qui est une combinaison de l’accès global affecté et de l’accès affecté au membre du groupe AAD, si la détermination de l’appartenance au groupe AAD échoue, l’utilisateur verra le menu « rien ne s’affiche dans le menu Démarrer ».

![Image du mode plein écran à présent en cas d’échec.](images/hololens-kiosk-failure-behavior.png )


- À compter de [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), le mode plein écran recherche un accès global affecté avant d’illustrer un menu Démarrer vide. Le mode plein écran permet de revenir à une configuration de kiosque globale (le cas échéant) en cas de défaillances pendant le mode plein écran du groupe AAD.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Appartenance au groupe de Azure AD de cache pour une borne en mode hors connexion

- Mode plein écran sécurisé en éliminant les applications disponibles en cas de défaillance du mode plein écran.
- Activez les bornes hors connexion à utiliser avec les groupes de Azure AD pendant jusqu’à 60 jours.

Cette stratégie détermine le nombre de jours pendant lesquels le cache d’appartenance au groupe Azure AD peut être utilisé pour les configurations d’accès affectées ciblant les groupes de Azure AD pour l’utilisateur connecté. Une fois que cette valeur de stratégie est définie sur une valeur supérieure à 0, alors le cache est utilisé dans le cas contraire.  

Nom : AADGroupMembershipCacheValidityInDays URI value :./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 jours  
Max-60 jours 

Étapes pour utiliser cette stratégie correctement : 
1. Créez un profil de configuration d’appareil pour le ciblage de bornes Azure AD des groupes et affectez-le à un ou plusieurs appareils HoloLens. 
1. Créer une configuration d’appareil basée sur un URI OMA personnalisée qui définit cette valeur de stratégie sur le nombre de jours souhaité (> 0) et l’assigner au (x) appareil (s) HoloLens. 
    1. La valeur de l’URI doit être entrée dans la zone de texte OMA-URI en tant que./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. La valeur peut être comprise entre min/maximum autorisé.
1. Inscrire des appareils HoloLens et vérifier que les deux configurations sont appliquées à l’appareil. 
1. Autoriser Azure AD utilisateur 1 à se connecter quand Internet est disponible, une fois que l’utilisateur se connecte et que Azure AD appartenance au groupe est confirmée avec succès, le cache est créé. 
1. Désormais, Azure AD utilisateur 1 peut mettre HoloLens hors connexion et l’utiliser pour le mode plein écran tant que la valeur de la stratégie autorise un nombre de jours de X. 
1. Les étapes 4 et 5 peuvent être répétées pour tout autre Azure AD l’utilisateur N. point clé ici : tout utilisateur Azure AD doit se connecter à l’appareil à l’aide d’Internet, de sorte qu’au moins une fois, nous pouvons déterminer qu’ils sont membres du groupe Azure AD auquel la configuration de kiosque est destinée. 
 
> [!NOTE]
> Tant que l’étape 4 n’est pas exécutée pour un Azure AD utilisateur rencontre un comportement d’échec mentionné dans les environnements « déconnectés ». 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Exemples de code Kiosk XML pour HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Mode plein écran d’applications ciblant un groupe de Azure AD. 
Ce kiosque déploie une borne qui est activée pour les utilisateurs du groupe Azure AD, avec un kiosque activé qui comprend les 3 applications : paramètres, assistance à distance et Hub de commentaires. Pour modifier cet exemple et l’utiliser immédiatement, veillez à modifier le GUID mis en surbrillance ci-dessous pour qu’il corresponde à un groupe de Azure AD de votre choix. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Le mode plein écran à plusieurs applications ciblant Azure AD compte.
Ce kiosque déploie une borne pour un seul utilisateur. une borne est activée et comprend les 3 applications : paramètres, assistance à distance et Hub de commentaires. Pour modifier cet exemple et l’utiliser immédiatement, veillez à modifier le compte mis en surbrillance ci-dessous pour qu’il corresponde à un compte Azure AD de votre choix. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

