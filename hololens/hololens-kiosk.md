---
title: Configurer HoloLens en tant que kiosque
description: Découvrez comment configurer et utiliser une configuration kiosque pour verrouiller les applications sur les appareils HoloLens.
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
ms.openlocfilehash: 245de50fcaaf1235cce02cd1b6cae921b64f2851
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283985"
---
# Configurer HoloLens en tant que kiosque

Vous pouvez configurer un appareil HoloLens pour qu’il fonctionne comme un appareil à usage fixe, également appelé *kiosque,* en configurant l’appareil pour qu’il s’exécute en mode plein écran. Le mode plein écran limite les applications (ou utilisateurs) disponibles sur l’appareil. Le mode plein écran est une fonctionnalité pratique que vous pouvez utiliser pour dédier un appareil HoloLens aux applications d’entreprise ou pour utiliser l’appareil HoloLens dans une démonstration d’application.

Cet article fournit des informations sur les aspects de la configuration plein écran spécifiques aux appareils HoloLens. Pour obtenir des informations générales sur les différents types de kiosques Windows et sur leur configuration, voir Configurer des kiosques et des [signes numériques](https://docs.microsoft.com/windows/configuration/kiosk-methods)sur les éditions de bureau Windows.  

> [!IMPORTANT]  
> Le mode plein écran détermine les applications disponibles lorsqu’un utilisateur se connecté à l’appareil. Toutefois, le mode plein écran n’est pas une méthode de sécurité. Elle n’empêche pas une application « autorisée » d’ouvrir une autre application non autorisée. Pour empêcher l’ouverture d’applications ou de processus, [utilisez Windows Defender CSP WDAC (Application Control)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) pour créer des stratégies appropriées.
>
> En savoir plus sur les services Microsoft pour offrir aux utilisateurs un niveau de sécurité avancé utilisé par HoloLens 2, en savoir plus sur la séparation d’état et [l’isolation - Protections Defender](security-state-separation-isolation.md#defender-protections). Vous pouvez également apprendre à utiliser WDAC et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils [HoloLens 2 avec Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Vous pouvez utiliser le mode plein écran dans une configuration d’application unique ou multi-application, et vous pouvez utiliser l’un des trois processus pour configurer et déployer la configuration kiosque.

> [!IMPORTANT]  
> La suppression de la configuration multi-application supprime les profils de verrouillage utilisateur créés par la fonctionnalité d’accès affecté. Toutefois, il ne retourne pas toutes les modifications de stratégie. Pour rétablir ces stratégies, vous devez rétablir les paramètres d’usine de l’appareil.

## Planifier le déploiement kiosque

Lors de la planification de votre kiosque, vous devez être en mesure de répondre aux questions suivantes. Voici quelques décisions à prendre lors de la lecture de cette page et quelques considérations pour ces questions.
1. **Qui utilisera votre kiosque et quel type de [compte](hololens-identity.md) utilisera-t-il ?** Il s’agit d’une décision que vous avez probablement déjà prise et qui ne doit pas être ajustée dans le but de votre kiosque, mais qui affectera la façon dont le kiosque sera affecté ultérieurement.
1. **Avez-vous besoin de kiosques différents par utilisateur/groupe ou d’un kiosque non activé pour certains utilisateurs ?** Si c’est le cas, vous souhaiterez créer votre kiosque via XML. 
1. **Combien d’applications seront disponibles dans votre kiosque ?** Si vous avez plus d’une application, vous aurez besoin d’un kiosque multi-application. 
1. **Quelles applications seront dans votre kiosque ?** Veuillez utiliser notre liste d’aumids ci-dessous pour ajouter In-Box applications en plus des vôtres.
1. **Comment prévoyez-vous de déployer votre kiosque ?** Si vous inscrivez un appareil dans la gestion des périphériques de gestion des périphériques, nous vous suggérons d’utiliser la gestion des périphériques de gestion des périphériques pour déployer votre kiosque. Si vous n’utilisez pas la gestion des données de gestion des données, le déploiement avec le package d’approvisionnement est disponible.  

### Exigences en mode plein écran

Vous pouvez configurer n’importe quel appareil HoloLens 2 pour utiliser le mode plein écran.

> [!IMPORTANT]
> Le mode plein écran est disponible uniquement si l’appareil dispose de Windows Holographic for Business. Tous les appareils HoloLens 2 sont produits avec Windows Holographic for Business et il n’existe aucune autre édition. Tous les appareils HoloLens 2 peuvent exécuter le mode plein écran.
>
> Les appareils HoloLens (1ère génération) doivent être mis à niveau à la fois en termes de build de système d’exploitation et d’édition du système d’exploitation. Voici plus d’informations sur la mise à jour d’un HoloLens (1ère génération) vers [l’édition Windows Holographic for Business.](hololens1-upgrade-enterprise.md) Pour mettre à jour un appareil HoloLens (1ère génération) afin d’utiliser le mode plein écran, vous devez d’abord vous assurer que l’appareil exécute Windows 10, version 1803 ou une version ultérieure. Si vous avez utilisé l’outil de récupération d’appareil Windows pour récupérer votre appareil HoloLens (1ère génération) à sa version par défaut, ou si vous avez installé les mises à jour les plus récentes, votre appareil est prêt à être configuré.

> [!IMPORTANT]  
> Pour protéger les appareils qui s’exécutent en mode plein écran, envisagez d’ajouter des stratégies de gestion des appareils qui désactiver des fonctionnalités telles que la connectivité USB. En outre, vérifiez vos paramètres de sonnerie de mise à jour pour vous assurer que les mises à jour automatiques ne se produisent pas pendant les heures d’ouverture.

### Choisir entre une borne à application unique ou une borne multi-applications

Une borne à application unique démarre l’application spécifiée lorsque l’utilisateur se connecté à l’appareil. Le menu Démarrer est désactivé, tout comme Cortana. Un appareil HoloLens 2 ne répond pas au [mouvement de](hololens2-basic-usage.md#start-gesture) démarrage. Un appareil HoloLens (1ère génération) ne répond pas au [mouvement](hololens1-basic-usage.md) d’bloom. Étant donné qu’une seule application peut s’exécuter, l’utilisateur ne peut pas placer d’autres applications.

Une borne multi-applications affiche le menu Démarrer lorsque l’utilisateur se connecté à l’appareil. La configuration plein écran détermine les applications disponibles dans le menu Démarrer. Vous pouvez utiliser une borne multi-applications pour offrir une expérience facile à comprendre aux utilisateurs en leur présentant uniquement les éléments qu’ils doivent utiliser et en supprimant les éléments qu’ils n’ont pas besoin d’utiliser.

Le tableau suivant répertorie les fonctionnalités des différents modes plein affichage.

| &nbsp; |Menu Démarrer |Menu Actions rapides |Caméra et vidéo |Miracast |Cortana |Commandes vocales prédéfinies |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Kiosque à application unique |Désactivée |Désactivée   |Désactivée |Désactivée   |Désactivée |Activé <sup> 1</sup> |
|Borne à plusieurs applications |Activé |Activé <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2, 3</sup>  |Activé <sup> 1</sup> |

> <sup>1 </sup> Les commandes vocales liées aux fonctionnalités désactivées ne fonctionnent pas.  
> <sup>2 Pour plus d’informations sur la configuration de ces fonctionnalités, voir </sup> [Sélectionner des applications kiosque.](#plan-kiosk-apps)  
> <sup>3 Même si Cortana est désactivée, les commandes </sup> vocales intégrées sont activées.

Le tableau suivant répertorie les fonctionnalités de prise en charge des utilisateurs des différents modes plein affichage.

| &nbsp; |Types d’utilisateurs pris en charge | Connexion automatique | Plusieurs niveaux d’accès |
| --- | --- | --- | --- |
|Kiosque à application unique |Compte de service géré (MSA) dans Azure Active Directory (Azure AD) ou un compte local |Oui |Non |
|Borne à plusieurs applications |Compte Azure AD |Non |Oui |

Pour obtenir des exemples d’utilisation de ces fonctionnalités, consultez le tableau suivant.

|Utilisez une borne à application unique pour : |Utilisez une borne multi-applications pour : |
| --- | --- |
|Appareil qui exécute uniquement un guide Dynamics 365 pour les nouveaux employés. |Un appareil qui exécute les guides et l’assistance à distance pour une gamme d’employés. |
|Appareil qui exécute uniquement une application personnalisée. |Un appareil qui fonctionne comme une borne pour la plupart des utilisateurs (exécutant uniquement une application personnalisée), mais fonctionne comme un appareil standard pour un groupe spécifique d’utilisateurs. |

### Planifier des applications kiosque

Pour obtenir des informations générales sur la façon de choisir des applications kiosque, voir Recommandations en matière de choix d’une application pour un accès [affecté (mode plein écran).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Si vous utilisez Windows Device Portal pour configurer une borne à application unique, vous sélectionnez l’application pendant le processus d’installation.  

Si vous utilisez un système de gestion des périphériques mobiles (MDM) ou un package d’approvisionnement pour configurer le mode plein écran, vous utilisez le fournisseur de services de configuration [AssignedAccess (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) pour spécifier des applications. Le CSP utilise les ID de modèle [utilisateur d’application (AUMID)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) pour identifier les applications. Le tableau suivant répertorie les AUMID de certaines applications pré-box que vous pouvez utiliser dans une borne multi-applications.

> [!IMPORTANT]
> Le mode plein écran détermine les applications disponibles lorsqu’un utilisateur se connecté à l’appareil. Toutefois, le mode plein écran n’est pas une méthode de sécurité. Elle n’empêche pas une application « autorisée » d’ouvrir une autre application non autorisée. Étant donné que nous ne limitons pas ce comportement, les applications peuvent toujours être lancées à partir de Edge, de l’Explorateur de fichiers et des applications du Microsoft Store. S’il existe des applications spécifiques que vous ne souhaitez pas lancer à partir d’un kiosque, utilisez le [CSP Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) pour créer des stratégies appropriées. 
> 
> En outre, la maison virtuelle ne peut pas être définie en tant qu’application kiosque.

<a id="aumids"></a>

|Nom de l’application |AUMID |
| --- | --- |
|Visionneuse3D |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendrier |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Caméra <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! Application |
|Sélécateur d’appareil sur HoloLens (1ère génération) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Séléateur d’appareil sur HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Hub de &nbsp; commentaires |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! Application |
|Explorateur de fichiers |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|MicrosoftStore |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Films et TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! Application |
|Photos |Microsoft.Windows.Photos\_8wekyb3d8bbwe\! Application |
|Paramètres |HolographicSystemSettings\_cw5n1h2txyewy\! Application |
|Conseils |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 Pour activer la capture photo ou vidéo, vous devez activer l’application </sup> Caméra en tant qu’application kiosque.  
> <sup>2 </sup> Lorsque vous activez l’application Caméra, ez compte des conditions suivantes :
> - Le menu Actions rapides inclut les boutons Photo et Vidéo.  
> - Vous devez également activer une application (par exemple, Photos, Courrier ou OneDrive) qui peut interagir avec ou récupérer des images.  
>  
> <sup>3 Même si vous n’activez pas Cortana en tant qu’application kiosque, les commandes </sup> vocales intégrées sont activées. Toutefois, les commandes liées aux fonctionnalités désactivées n’ont aucun effet.  
> <sup>4 </sup> Vous ne pouvez pas activer Miracast directement. Pour activer Miracast en tant qu’application kiosque, activez l’application Appareil photo et l’application S picker d’appareil.

### Planifier les profils kiosque pour les utilisateurs ou les groupes

Lors de la création du fichier xml ou de l’utilisation de l’interface utilisateur d’Intune pour configurer un kiosque, vous devez tenir compte des utilisateurs du kiosque. Une configuration Kiosk peut être limitée à un compte individuel ou à des groupes Azure AD. 

En règle générale, les kiosques sont activés pour un utilisateur ou un groupe d’utilisateurs. Toutefois, si vous envisagez d’écrire votre propre kiosque XML, vous pouvez envisager l’accès affecté global, dans lequel le kiosque est appliqué au niveau de l’appareil, quelle que soit l’identité. Si cela vous demande d’en savoir plus sur [les kiosques d’accès affectés globaux.](hololens-global-assigned-access-kiosk.md)

#### Si vous créez un fichier XML :
-   Vous créez plusieurs profils Kiosk et vous les affectez à différents utilisateurs/groupes. Par exemple, un kiosque pour votre groupe Azure AD qui possède de nombreuses applications et un visiteur qui dispose d’une borne d’application multiple avec une application unique.
-   La configuration de votre kiosque sera appelée **ID** de profil et aura un GUID.
-   Vous affecterez ce profil dans la section configs en spécifiant le type d’utilisateur et en utilisant le même GUID pour **l’ID DefaultProfile**.
- Un fichier XML peut être créé, mais toujours appliqué à un appareil via la gestion des périphériques de gestion des périphériques en créant un profil de configuration d’appareil OMA personnalisé et en l’appliquant au groupe d’appareils HoloLens à l’aide de la valeur d’URI : ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Si vous créez un kiosque dans Intune.
-   Chaque appareil ne peut recevoir qu’un seul profil Kiosk, sinon il crée un conflit et ne reçoit aucune configuration Kiosk. 
    -   Les autres types de profils et de stratégies, tels que les restrictions d’appareil qui ne sont pas liées au profil de configuration plein écran, ne sont pas en conflit avec le profil de configuration plein écran.
-   Le kiosque sera activé pour tous les utilisateurs qui font partie du type d’accès utilisateur, ce qui sera activé avec un utilisateur ou un groupe Azure AD. 
-   Une fois la configuration kiosk définie et le **type** de connexion utilisateur (utilisateurs qui peuvent se connecter au kiosque) et les applications sélectionnées, la configuration de l’appareil doit toujours être affectée à un groupe. Le ou les groupes affecté(s) déterminent les appareils qui reçoivent la configuration de l’appareil Kiosk, mais n’interagit pas si le kiosque est activé ou non. 
    - Pour une discussion complète des effets de l’affectation de profils de configuration dans Intune, voir Attribuer des profils utilisateur et [d’appareil dans Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-profile-assign)

### Sélectionner une méthode de déploiement

Vous pouvez sélectionner l’une des méthodes suivantes pour déployer des configurations plein écran :

- [Microsoft Intune ou un autre service de gestion des périphériques mobiles (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Package d’approvisionnement](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [WindowsDevicePortal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Étant donné que cette méthode nécessite que le mode développeur soit activé sur l’appareil, nous vous recommandons de l’utiliser uniquement pour les démonstrations.

Le tableau suivant répertorie les fonctionnalités et les avantages de chacune des méthodes de déploiement.

| &nbsp; |Déployer à l’aide de Windows Device Portal |Déployer à l’aide d’un package d’approvisionnement |Déployer à l’aide de la gestion des données de gestion des données (MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Déployer des kiosques à application unique   | Oui           | Oui                  | Oui  |
|Déployer des kiosques multi-applications    | Non            | Oui                  | Oui  |
|Déployer sur des appareils locaux uniquement | Oui           | Oui                  | Non   |
|Déployer à l’aide du mode développeur |Requis       | Non requis            | Non requis   |
|Déployer à l’aide d’Azure Active Directory (Azure AD)  | Non requis            | Non requis                   | Requis  |
|Déployer automatiquement      | Non            | Non                   | Oui  |
|Vitesse de déploiement            | Rapide       | Rapide                 | Lent |
|Déployer à grande échelle | Non recommandé    | Nos recommandations        | Nos recommandations |

## Utiliser Microsoft Intune ou un autre mdM pour configurer une borne à application unique ou multi-application

Pour configurer le mode plein écran à l’aide de Microsoft Intune ou d’un autre système MDM, suivez ces étapes.

1. [Préparez-vous à inscrire les appareils.](#mdmenroll)
1. [Créez un profil de configuration kiosque.](#mdmprofile)
1. Configurez le kiosque.
   - [Configurez les paramètres d’une borne à application unique.](#mdmconfigsingle)
   - [Configurez les paramètres d’une borne multi-applications.](#mdmconfigmulti)
1. [Affectez le profil de configuration kiosque à un groupe.](#mdmassign)
1. Déployez les appareils.
   - [Déployez une borne à application unique.](#mdmsingledeploy)
   - [Déployez une borne multi-applications.](#mdmmultideploy)

### <a id="mdmenroll"></a>Gestion des périphériques mobiles, étape 1 &ndash; Préparer l’inscription des appareils

Vous pouvez configurer votre système de gestion des périphériques mobiles pour inscrire automatiquement les appareils HoloLens lorsque l’utilisateur se connecté pour la première fois, ou faire en sorte que les utilisateurs inscrivent les appareils manuellement. Les appareils doivent également être joints à votre domaine Azure AD et affectés aux groupes appropriés.

Pour plus d’informations sur l’inscription des appareils, voir Inscrire [HoloLens](hololens-enroll-mdm.md) dans la gestion des périphériques mobiles et les méthodes d’inscription [Intune pour les appareils Windows.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a id="mdmprofile"></a>MdM, étape 2 &ndash; Créer un profil de configuration plein écran

1. Ouvrez [le portail Azure](https://portal.azure.com/) et connectez-vous à votre compte d’administrateur Intune.
1. Select **Microsoft Intune**  >  **Device configuration - Profiles**Create  >  **profile**.
1. Entrez un nom de profil.
1. Sélectionnez ****  >  **Plateforme Windows 10 et ultérieures,** puis sélectionnez **Restrictions**d’appareil de type  > **profil.**
1. Sélectionnez **Configurer**  >  **Kiosk,** puis sélectionnez l’une des sélections suivantes :
   - Pour créer une borne à application unique, sélectionnez **Kiosque en mode**plein  >  **écran.**
   - Pour créer une borne multi-applications, sélectionnez **Kiosk Mode**  >  **Multi-app Kiosk.**
1. Pour commencer à configurer la borne, sélectionnez **Ajouter.**

Les étapes suivantes varient en fonction du type de kiosque que vous souhaitez. Pour plus d’informations, sélectionnez l’une des options suivantes :  

- [Kiosque à application unique](#mdmconfigsingle)
- [Borne à plusieurs applications](#mdmconfigmulti)

Pour plus d’informations sur la création d’un profil de configuration plein écran, voir les paramètres d’appareil Windows 10 et Windows Holographique Entreprise à exécuter en tant que borne dédiée à l’aide [d’Intune.](https://docs.microsoft.com/intune/configuration/kiosk-settings)

### <a id="mdmconfigsingle"></a>GESTION DES APPLICATIONS, étape 3 (application unique) Configurer les paramètres d’une borne &ndash;  à application unique

Cette section récapitule les paramètres dont une borne à application unique a besoin. Pour plus d’informations, voir les articles suivants :

- Pour plus d’informations sur la configuration d’un profil de configuration kiosque dans Intune, voir Comment configurer le mode plein écran à l’aide [de Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Pour plus d’informations sur les paramètres disponibles pour les kiosques à application unique dans Intune, voir Kiosques d’application [en](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) plein écran
- Pour d’autres services de GPM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous devez utiliser une configuration XML personnalisée pour configurer une borne dans votre service mdM, créez un fichier XML qui définit la [configuration kiosque.](#ppkioskconfig)

1. Sélectionnez Compte d’utilisateur de **type**d’utilisateur local, puis entrez le nom d’utilisateur du compte local (appareil) ou du compte  >  **** Microsoft (MSA) qui peut se connecter à la borne.
   > [!NOTE]  
   > Les types **de compte d’utilisateur autologon** ne sont pas pris en charge sur Windows Holographic for Business.
1. Sélectionnez **application du Store de types**  >  **d’applications,** puis sélectionnez une application dans la liste.

L’étape suivante consiste [à affecter](#mdmassign) le profil à un groupe.

### <a id="mdmconfigmulti"></a>GESTION DES APPLICATIONS, étape 3 (multi-application) Configurer les paramètres d’une borne &ndash; multi-applications

Cette section récapitule les paramètres dont une borne multi-applications a besoin. Pour plus d’informations, consultez les articles suivants :

- Pour plus d’informations sur la configuration d’un profil de configuration kiosque dans Intune, voir Comment configurer le mode plein écran à l’aide [de Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Pour plus d’informations sur les paramètres disponibles pour les kiosques multi-applications dans Intune, voir [kiosques multi-applications](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Pour d’autres services de GPM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous avez besoin d’utiliser une configuration XML personnalisée pour configurer une borne dans votre service mdM, créez un fichier XML qui définit la [configuration kiosque.](#ppkioskconfig) Si vous utilisez un fichier XML, veillez à inclure la disposition [de l’démarrer.](#start-layout-for-hololens)  
- Vous pouvez éventuellement utiliser une disposition de l’écran de démarrage personnalisée avec Intune ou d’autres services MDM. Pour plus d’informations, voir fichier de disposition de l’démarrer pour la gestion des données de gestion [des données (Intune, etc.).](#start-layout-file-for-mdm-intune-and-others)

1. Sélectionnez **Cibler Windows 10 en mode S non**  >  ****.  
   >[!NOTE]  
   > Le mode S n’est pas pris en charge sur Windows Holographic for Business.
1. Sélectionnez **le type**d’utilisateur ou de groupe Azure AD ou le type de compte  >  **** d’utilisateur ****  >  **HoloLens**visiteur, puis ajoutez un ou plusieurs groupes d’utilisateurs ou comptes.  

   Seuls les utilisateurs qui appartiennent aux groupes ou comptes que vous spécifiez dans le **type d’accès utilisateur** peuvent utiliser l’expérience kiosque.

1. Sélectionnez une ou plusieurs applications à l’aide des options suivantes :
   - Pour ajouter une application métier téléchargée, sélectionnez Ajouter une application du **Store,** puis l’application de votre choix.
   - Pour ajouter une application en spécifiant son AUMID, sélectionnez Ajouter par **AUMID,** puis entrez l’AUMID de l’application. [Voir la liste des AUMID disponibles](#aumids)

L’étape suivante consiste [à affecter](#mdmassign) le profil à un groupe.

### <a id="mdmassign"></a>MdM, étape 4 &ndash; Affecter le profil de configuration kiosque à un groupe

Utilisez la page **Affectations** du profil de configuration plein écran pour définir l’endroit où vous souhaitez que la configuration kiosque soit déployée. Dans le cas le plus simple, vous affectez le profil de configuration kiosque à un groupe qui contiendra l’appareil HoloLens lorsque l’appareil s’inscrit dans la gestion des périphériques de gestion des périphériques.

### <a id="mdmsingledeploy"></a>MDM, étape 5 (application unique) &ndash; Déployer une borne à application unique

Lorsque vous utilisez un système MDM, vous pouvez inscrire l’appareil dans la gestion des périphériques de gestion des périphériques en cours de la première utilisation. Une fois L’OOBE terminé, il est facile de se connecté à l’appareil.

Pendant la OOBE, suivez les étapes suivantes :

1. Connectez-vous à l’aide du compte que vous avez spécifié dans le profil de configuration plein écran.
1. Inscrivez l’appareil. Assurez-vous que l’appareil est ajouté au groupe à qui le profil de configuration kiosque est affecté.
1. Attendez la fin de la OOBE, le téléchargement et l’installation de l’application du Store, ainsi que l’application des stratégies. Redémarrez ensuite l’appareil.

La prochaine fois que vous vous connectez à l’appareil, l’application kiosque doit démarrer automatiquement.

Si vous ne voyez pas la configuration de votre kiosque à ce stade, [vérifiez l’état de l’affectation.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

### <a id="mdmmultideploy"></a>MDM, étape 5 (multi-application) &ndash; Déployer une borne multi-application

Lorsque vous utilisez un système MDM, vous pouvez joindre l’appareil à votre client Azure AD et inscrire l’appareil dans la gestion des périphériques de gestion des périphériques en cours de la première utilisation. Si nécessaire, fournissez les informations d’inscription aux utilisateurs afin qu’ils les disposent pendant le processus OOBE.

> [!NOTE]  
> Si vous avez affecté le profil de configuration kiosque à un groupe qui contient des utilisateurs, assurez-vous que l’un de ces comptes d’utilisateur est le premier compte à se connecter à l’appareil.

Durant la OOBE, suivez les étapes suivantes :

1. Connectez-vous à l’aide du compte qui appartient au groupe de **types d’inscription utilisateur.**
1. Inscrivez l’appareil.
1. Attendez le téléchargement et l’installation des applications faisant partie du profil de configuration plein écran. En outre, attendez que les stratégies soient appliquées.  
1. Une fois L’OOBE terminé, vous pouvez installer des applications supplémentaires à partir du Microsoft Store ou par chargement de version secondaire. [Applications requises](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) pour le groupe que l’appareil appartient à installer automatiquement.
1. Une fois l’installation terminé, redémarrez l’appareil.

La prochaine fois que vous vous connectez à l’appareil à l’aide d’un compte qui appartient au type de logo **utilisateur,** l’application kiosque doit se lancer automatiquement.

Si vous ne voyez pas la configuration de votre kiosque à ce stade, [vérifiez l’état de l’affectation.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

## Utiliser un package d’approvisionnement pour configurer une borne à application unique ou multi-application

Pour configurer le mode plein écran à l’aide d’un package d’approvisionnement, suivez ces étapes.

1. [Créez un fichier XML qui définit la configuration plein écran.](#ppkioskconfig), y compris une [disposition de l’écran de démarrage.](#start-layout-for-hololens)
2. [Ajoutez le fichier XML à un package d’approvisionnement.](#ppconfigadd)
3. [Appliquez le package d’approvisionnement à HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Package d’approvisionnement, étape 1 &ndash; Créer un fichier XML de configuration kiosque

Suivez [les instructions générales pour créer un](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)fichier XML de configuration kiosque pour le bureau Windows, sauf pour les suivants :

- N’incluez pas les applications Windows classiques (Win32). HoloLens ne prend pas en charge ces applications.
- Utilisez le [XML de disposition de l’espace](#start-layout-for-hololens) réservé de démarrage pour HoloLens.
- Facultatif : ajouter l’accès invité à la configuration plein écran

#### <a id="ppkioskguest"></a>Facultatif : ajouter l’accès invité à la configuration plein écran

Dans la section [ **Configs** du fichier XML,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)vous pouvez configurer un groupe spécial nommé **Visiteur** pour autoriser les invités à utiliser le kiosque. Lorsque la borne est configurée pour prendre**** en charge le groupe spécial Visiteur, une option « Invité » est ajoutée à la page de signature. **** Le **compte Invité** n’a pas besoin de mot de passe et toutes les données associées au compte sont supprimées lorsque le compte se dédesse.

Pour activer le **compte Invité,** ajoutez l’extrait de code suivant à votre code XML de configuration plein écran :

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Disposition de l’espace réservé de démarrage pour HoloLens

Si vous utilisez un [package d’approvisionnement](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) pour configurer une borne multi-applications, la procédure nécessite une disposition de l’démarrer. La personnalisation de la disposition de l’ordinateur de démarrage n’est pas prise en charge dans Windows Holographic for Business. Par conséquent, vous devez utiliser une disposition de l’espace réservé de l’espace réservé.

> [!NOTE]  
> Étant donné qu’une borne à application unique démarre l’application kiosque lorsqu’un utilisateur se ouvre, elle n’utilise pas de menu Démarrer et n’a pas besoin de disposition de l’démarrer.

> [!NOTE]  
> Si vous utilisez [la gestion des](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) applications multi-applications pour configurer une borne multi-applications, vous pouvez éventuellement utiliser une disposition de l’écran de démarrage. Pour plus d’informations, voir fichier de disposition de l’espace réservé pour la gestion des données de gestion des données [(Intune, etc.).](#start-layout-file-for-mdm-intune-and-others)

Pour la disposition de l’démarrer, ajoutez la section **StartLayout** suivante au fichier XML d’approvisionnement kiosque :

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Fichier de disposition de l’espace réservé à l’espace réservé pour la gestion des données de gestion des données (Intune, etc.)

Enregistrez l’exemple suivant en tant que fichier XML. Vous pouvez utiliser ce fichier lorsque vous configurez la borne multi-applications dans Microsoft Intune (ou dans un autre service MDM qui fournit un profil kiosque).

> [!NOTE]
> Si vous devez utiliser un paramètre personnalisé et une configuration XML complète pour configurer une borne dans votre service MDM, utilisez les instructions de disposition de l’écran de démarrage pour un [package d’approvisionnement.](#start-layout-for-hololens)

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

### <a id="ppconfigadd"></a>Prov. package, étape 2 Ajouter le fichier XML de configuration kiosque &ndash; à un package d’approvisionnement

1. Ouvrez [le Concepteur de configuration Windows.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Sélectionnez **approvisionnement avancé,** entrez un nom pour votre projet, puis sélectionnez **Suivant**.
1. Sélectionnez **Windows 10 Holographique,** puis sélectionnez **Suivant**.
1. Sélectionnez **Terminer.** L’espace de travail de votre package s’ouvre.
1. Sélectionnez **Paramètres d’runtime**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. Dans le volet central, sélectionnez **Parcourir** pour rechercher et sélectionner le fichier XML de configuration kiosque que vous avez créé.

   ![Capture d’écran du champ MultiAppAssignedAccessSettings dans le Concepteur de configuration Windows](./images/multiappassignedaccesssettings.png)

1. **Facultatif**. (Si vous souhaitez appliquer le package d’approvisionnement après la configuration initiale de l’appareil et qu’un utilisateur administrateur est déjà disponible sur l’appareil kiosque, ignorez cette étape.) Sélectionnez **Utilisateurs des comptes de paramètres d’runtime,** &gt; **** &gt; **** puis créez un compte d’utilisateur. Fournissez un nom d’utilisateur et un mot de passe, puis sélectionnez **Administrateurs du groupe**  >  **d’utilisateurs.**  
  
     À l’aide de ce compte, vous pouvez afficher l’état de mise en service et les journaux.  
1. **Facultatif**. (Si vous avez déjà un compte non administrateur sur l’appareil kiosque, ignorez cette étape.) Sélectionnez **Utilisateurs des comptes de paramètres d’runtime,** &gt; **** &gt; **** puis créez un compte d’utilisateur local. Assurez-vous que le nom d’utilisateur est le même que pour le compte que vous spécifiez dans le XML de configuration. Sélectionnez **UserGroup**  >  **Standard Users**.
1. Sélectionnez **Enregistrer**  >  **un fichier.**
1. Sélectionnez **Exporter**  >  **le package d’approvisionnement,** puis sélectionnez **Administrateur**  >  **informatique propriétaire.** Cela définit la priorité de ce package d’approvisionnement plus élevée que les packages d’approvisionnement qui sont appliqués à cet appareil à partir d’autres sources.
1. Sélectionnez **Suivant**.
1. Dans la page **Sécurité du package** d’approvisionnement, sélectionnez une option de sécurité.
   > [!IMPORTANT]  
   > Si vous **sélectionnez Activer la signature de package,** vous devez également sélectionner un certificat valide à utiliser pour signer le package. Pour ce faire, **sélectionnez Parcourir** et sélectionnez le certificat que vous souhaitez utiliser pour signer le package.
   
   > [!CAUTION]  
   > Ne sélectionnez pas **Activer le chiffrement de package.** Sur les appareils HoloLens, ce paramètre entraîne l’échec de l’approvisionnement.
1. Sélectionnez **Suivant**.
1. Spécifiez l’emplacement de sortie où vous souhaitez que le package d’approvisionnement soit mis en place lorsqu’il est créé. Par défaut, le Concepteur de configuration Windows utilise le dossier de projet comme emplacement de sortie. Si vous souhaitez modifier l’emplacement de sortie, sélectionnez **Parcourir.** Lorsque vous avez terminé, sélectionnez **Suivant.**
1. Sélectionnez **Build** pour commencer à créer le package. La génération du package d'approvisionnement est rapide. La page de build affiche les informations du projet et la barre de progression indique l’état de la build.

### <a id="ppapply"></a>Package d’approvisionnement, étape 3 &ndash; Appliquer le package d’approvisionnement à HoloLens

L’article « Configurer HoloLens à l’aide d’un package d’approvisionnement » fournit des instructions détaillées pour appliquer le package d’approvisionnement dans les circonstances suivantes :

- Vous pouvez [initialement appliquer un package d’approvisionnement à HoloLens lors de l’installation.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Vous pouvez également [appliquer un package d’approvisionnement à HoloLens après l’installation.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## Utiliser Windows Device Portal pour configurer une borne à application unique

Pour configurer le mode plein écran à l’aide de Windows Device Portal, suivez ces étapes.

1. [Configurer l’appareil HoloLens pour utiliser Windows Device Portal.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Le Device Portal est un serveur Web situé sur l'appareil auquel vous pouvez vous connecter depuis un navigateur Web sur votre PC.

    > [!CAUTION]
    > Lorsque vous définissez HoloLens pour utiliser Device Portal, vous devez activer le mode développeur sur l’appareil. Le mode développeur sur un appareil qui dispose de Windows Holographic for Business vous permet de charger des applications de façon indépendant. Toutefois, ce paramètre crée un risque qu’un utilisateur puisse installer des applications qui n’ont pas été certifiées par le Microsoft Store. Les administrateurs peuvent bloquer la possibilité d’activer le mode développeur à l’aide du paramètre Deverrouillage **ApplicationManagement/AllowDeveloper** dans le programme [CSP De stratégie.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [En savoir plus sur le mode développeur.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Sur un ordinateur, connectez-vous à HoloLens à l’aide du [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [usb.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Effectuez l'une des opérations suivantes:
   - Si vous vous connectez à Windows Device Portal pour la première fois, créez un [nom d’utilisateur et](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password) un mot de passe
   - Entrez le nom d’utilisateur et le mot de passe que vous avez précédemment configurer.

    > [!TIP]
    > Si une erreur de certificat s'affiche dans le navigateur, [procédez comme suit pour résoudre le problème](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. Dans Windows Device Portal, sélectionnez **Mode plein écran.**

1. Sélectionnez **Activer le mode**plein écran, sélectionnez une application à exécuter au démarrage de l’appareil, puis sélectionnez **Enregistrer.**

    ![Mode plein écran](images/kiosk.png)
1. Redémarrez HoloLens. Si votre page Device Portal est toujours ouverte, vous pouvez sélectionner **Redémarrer** en haut de la page.

> [!NOTE]
> Le mode plein écran peut être paramétrant via l’API REST de Device Portal en faisant une requête POST vers /api/holographic/kioskmode/settings avec un paramètre de chaîne de requête requis (« kioskModeEnabled » avec la valeur « true » ou « false ») et un paramètre facultatif (« startupApp » avec la valeur d’un nom de package). N’oubliez pas que Device Portal est destiné aux développeurs uniquement et ne doit pas être activé sur les appareils non-développeurs. L’API REST est sujette à modification dans les futures mises à jour/mises à jour.

## Informations supplémentaires

### Regardez comment configurer une borne à l’aide d’un package d’approvisionnement.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Accès affecté global – Mode plein écran
- Gestion réduite des identités pour Kiosk, en activant une nouvelle méthode Kiosk qui applique le mode plein écran au niveau du système.

Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode plein écran de plusieurs applications, qui s’applique au niveau du système, n’a aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se sont connectés à l’appareil. Pour plus [d’informations sur](hololens-global-assigned-access-kiosk.md) cette nouvelle fonctionnalité, consultez la documentation de kiosque à accès global affecté HoloLens.

### Lancement automatique d’une application en mode plein écran multi-application 
- Expérience axée sur le lancement automatique d’application, ce qui augmente davantage l’interface utilisateur et les sélections d’applications choisies pour les expériences en mode plein écran.

S’applique uniquement au mode plein écran de plusieurs applications et une seule application peut être désignée pour le lancement automatique à l’aide de l’attribut en surbrillation ci-dessous dans la configuration Accès affecté. 

L’application est lancée automatiquement lorsque l’utilisateur se ouvre. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Modifications du comportement du mode plein écran pour la gestion des défaillances
- Mode plein écran plus sécurisé en éliminant les applications disponibles en cas de défaillance du mode plein écran. 

Précédemment, lors de la rencontre d’échecs dans l’application du mode plein écran, HoloLens a utilisé pour afficher toutes les applications dans le menu Démarrer. Désormais, dans Windows Holographique version 20H2 en cas d’échec, aucune application ne s’affiche dans le menu Démarrer comme ci-dessous : 

![Image de l’apparence du mode plein écran en cas d’échec.](images/hololens-kiosk-failure-behavior.png )

### Mettre en cache l’appartenance au groupe Azure AD pour kiosque hors connexion
- Activé l’utilisation de bornes hors connexion avec des groupes Azure AD pendant 60 jours.

Cette stratégie contrôle le nombre de jours pendant combien de jours, le cache d’appartenance aux groupes Azure AD est autorisé à être utilisé pour les configurations d’accès affecté ciblant des groupes Azure AD pour l’utilisateur signé. Une fois que cette valeur de stratégie est définie sur une valeur supérieure à 0 uniquement, le cache n’est pas utilisé dans le cas contraire.  

Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 jour  
Max - 60 jours 

Étapes pour utiliser cette stratégie correctement : 
1. Créez un profil de configuration d’appareil pour un kiosque ciblant des groupes Azure AD et affectez-le à des appareils HoloLens. 
1. Créez une configuration d’appareil OMA URI personnalisée qui définit cette valeur de stratégie sur le nombre de jours souhaité (> 0) et affectez-la à des appareils HoloLens. 
    1. La valeur d’URI doit être entrée dans la zone de texte OMA-URI en tant que ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. La valeur peut être entre min /max autorisée.
1. Inscrivez les appareils HoloLens et vérifiez que les deux configurations sont appliquées à l’appareil. 
1. Laissez l’utilisateur Azure AD 1 se connecter lorsqu’Internet est disponible, une fois que l’utilisateur s’est connecté et que l’appartenance au groupe Azure AD a été confirmée, le cache est créé. 
1. Désormais, l’utilisateur Azure AD 1 peut déconnecter HoloLens et l’utiliser en mode plein écran tant que la valeur de stratégie autorise X nombre de jours. 
1. Les étapes 4 et 5 peuvent être répétées pour n’importe quel autre utilisateur Azure AD N. Ici, tout utilisateur Azure AD doit se connecter à l’appareil à l’aide d’Internet. Nous pouvons donc déterminer au moins une fois qu’ils sont membres du groupe Azure AD auquel la configuration Kiosk est ciblée. 
 
> [!NOTE]
> Jusqu’à ce que l’étape 4 soit effectuée pour un utilisateur Azure AD, le comportement d’échec mentionné dans les environnements « déconnectés » se produit. 


## Exemples de code kiosque XML pour HoloLens

### Plusieurs applications en mode plein écran ciblant un groupe Azure AD. 
Cette borne déploie un kiosque qui, pour les utilisateurs du groupe Azure AD, aura un kiosque activé qui inclut les 3 applications : Paramètres, Assistance à distance et Hub de commentaires. Pour modifier cet exemple afin qu’il soit utilisé immédiatement, veillez à modifier le GUID mis en évidence ci-dessous pour qu’il corresponde à votre propre groupe Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Plusieurs applications en mode plein écran ciblant un compte Azure AD.
Cette borne déploie un kiosque pour un seul utilisateur, avec un kiosque activé qui inclut les 3 applications : Paramètres, Assistance à distance et Hub de commentaires. Pour modifier cet exemple afin qu’il soit utilisé immédiatement, veillez à modifier le compte mis en évidence ci-dessous pour qu’il corresponde à votre propre compte Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

