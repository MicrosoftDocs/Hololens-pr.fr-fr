---
title: Notes de publication de HoloLens 2
description: restez à jour avec toutes les mises à jour de chaque nouvelle version de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: e0dd7d02ad923438134f2a45812db67f73fdcd8d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637181"
---
# <a name="hololens-2-release-notes"></a>Notes de publication de HoloLens 2

pour vous assurer que vous disposez d’une expérience productive avec vos appareils HoloLens, nous continuons à publier les mises à jour des fonctionnalités, des bogues et de la sécurité. sur cette page, vous pouvez voir les nouveautés de HoloLens chaque mois. pour obtenir la dernière mise à jour HoloLens 2, vous pouvez [rechercher des mises à jour et mettre à jour manuellement](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obtenir la mise à jour flash complète (FFU) pour [flasher votre appareil via le compagnon de récupération avancé](hololens-recovery.md#clean-reflash-the-device). Le [Téléchargement](https://aka.ms/hololens2download) est mis à jour et fournit la version la plus récente de la mise à la disposition générale.

> [!NOTE]
> l’annonce récente de Windows 11 était axée sur la version PC de Windows. nous avons récemment lancé une [mise à jour majeure du système d’exploitation](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) pour HoloLens 2 en mai 2021, et nous travaillons sur une prochaine version en fonction des commentaires des clients.

> [!IMPORTANT]
> en raison d’un [problème connu maintenant résolu dans notre build 21H1 qui affectait les utilisateurs de l’assistance à distance](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes), nous avons suspendu temporairement l’offre de Windows des mises à jour 21H1 holographiques. nous avions également modifié la version par défaut de l’ARC de récupération avancée (ARC) dans la [mise à jour Windows holographique, version 20H2-juin 2021](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). La build ARC reprend à présent le ciblage de la build 21H1.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographique, version 21H1-mise à jour de juin 2021
- Build 20348,1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive pour le chargement par progression de l’appareil photo professionnel ou scolaire

nous avons ajouté une nouvelle fonctionnalité à l’application HoloLens 2 Paramètres, qui permet aux clients de charger automatiquement des photos et des vidéos de réalité mixte à partir des images de l’appareil > dossier pellicule vers le OneDrive correspondant pour le dossier professionnel ou scolaire. cette fonctionnalité répond à un [écart de fonctionnalités au sein de l’application OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) sur HoloLens 2, qui prend uniquement en charge le chargement automatique de la restauration automatique sur le compte Microsoft personnel d’un client (et non sur son compte professionnel ou scolaire).

**Fonctionnement**

- visitez **Paramètres > système > caméra de la réalité mixte** pour activer le « chargement de l’appareil photo ».
- en définissant cette fonctionnalité sur la position **On** , toutes les photos ou vidéos de réalité mixte capturées sur votre appareil seront automatiquement mises en file d’attente pour téléchargement dans le dossier images > pellicule de OneDrive votre compte professionnel ou scolaire.
    >[!NOTE]
    >les Photos et les vidéos capturées avant l’activation de cette fonctionnalité *ne seront pas* mises en file d’attente pour le téléchargement et devront tout de même être téléchargées manuellement.
- un message d’état sur la page Paramètres affiche le nombre de fichiers en attente de chargement (ou la lecture de « OneDrive est à jour » lorsque tous les fichiers en attente ont été téléchargés.
- Si vous vous inquiétez de la bande passante ou souhaitez « suspendre » le téléchargement pour une raison quelconque, vous pouvez faire passer la fonctionnalité à la position **off** . La désactivation temporaire de la fonctionnalité garantit que la file d’attente de téléchargement continuera à augmenter lorsque vous ajouterez de nouveaux fichiers au dossier pellicule, mais que les fichiers ne seront pas téléchargés tant que vous n’aurez pas réactivé la fonctionnalité.
- Les fichiers les plus récents seront téléchargés en premier (dernière connexion, premier sorti).
- si votre compte OneDrive rencontre des problèmes (par exemple, après la modification de votre mot de passe), un bouton **corriger maintenant** s’affiche sur la page Paramètres.
- Il n’y a pas de taille de fichier maximale, mais notez que le chargement des fichiers volumineux prendra plus de temps (surtout si votre bande passante de chargement est limitée). Si vous « suspendez » ou si vous désactivez le téléchargement pendant le chargement d’un fichier volumineux, le téléchargement partiel est préservé. Si le téléchargement est réactivé dans plusieurs heures après avoir été « suspendu » ou désactivé, le téléchargement se poursuivra là où il s’était arrêté. Toutefois, si le chargement est réactivé après plusieurs heures, le chargement du fichier volumineux redémarrera à partir du début.

**Problèmes connus et avertissements**

- Ce paramètre n’a pas de limitation intégrée basée sur l’utilisation de la bande passante actuelle. Si vous avez besoin d’optimiser la bande passante pour un autre scénario, désactivez manuellement le paramètre. Télécharger seront suspendus, mais la fonctionnalité continuera à surveiller les fichiers récemment ajoutés à la pellicule. Réactivez le téléchargement lorsque vous êtes prêt à continuer.
- Cette fonctionnalité doit être activée pour chaque compte d’utilisateur sur l’appareil, et elle peut uniquement charger activement des fichiers pour l’utilisateur actuellement connecté à l’appareil.
- si vous prenez des photos ou des vidéos tout en regardant le nombre de téléchargements sur la page Paramètres en temps réel, notez que le nombre de fichiers en attente peut ne pas changer tant que le téléchargement du fichier actuel n’est pas terminé.
- Télécharger s’interrompt si votre appareil est en veille ou hors tension. pour vous assurer que vos téléchargements en attente sont terminés, utilisez activement l’appareil jusqu’à ce que la page Paramètres lise « OneDrive soit à jour » ou ajustez les paramètres de veille de l' **& d’alimentation** .
### <a name="added-support-for-some-telemetry-policies"></a>Ajout de la prise en charge de certaines stratégies de télémétrie

Les stratégies de télémétrie suivantes sont désormais prises en charge sur le HoloLens 2 :
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry et System\ConfigureTelemetryOptInSettingsUx doivent être utilisés ensemble pour avoir un contrôle total sur la télémétrie et le comportement dans l’application Paramètres.

Améliorations et correctifs de la mise à jour :
- Corrige une corruption vidéo importante avec l’étalonnage des couleurs.
- Résout un problème où le texte peut être tronqué dans le menu de l’alimentation.
- Active la prise en charge de la stratégie RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographique, version 20H2-mise à jour de juin 2021
- Build 19041,1154

### <a name="added-support-for-some-telemetry-policies"></a>Ajout de la prise en charge de certaines stratégies de télémétrie

Les stratégies de télémétrie suivantes sont désormais prises en charge sur le HoloLens 2 :
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry et System\ConfigureTelemetryOptInSettingsUx doivent être utilisés ensemble pour avoir un contrôle total sur la télémétrie et le comportement dans l’application Paramètres.

nous vous encourageons à essayer notre build la plus récente, Windows holographique, version 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographique, version 1903-mise à jour du 2021 du 1er juin
- Build 18362,1116

Améliorations et correctifs de la mise à jour :
- cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à essayer notre build la plus récente, Windows holographique, version 21H1.

>[!IMPORTANT]
> Cette Build ne sera plus en service.

## <a name="windows-holographic-version-21h1"></a>Windows Holographique, version 21H1
- Build 20346,1002

Cette mise à jour contient des fonctionnalités pour deux audiences cibles ; fonctionnalités qui peuvent être utilisées par tout le monde sur un appareil par l’utilisateur final et les nouvelles options de gestion des appareils qui peuvent être configurées par les administrateurs informatiques. Le tableau ci-dessous indique les fonctionnalités qui s’appliquent à chaque audience. Si vous êtes un administrateur informatique, jetez un coup d’œil à notre [liste de vérification des mises à jour de l’administrateur informatique](#it-admin---update-checklist).
>[!IMPORTANT]
>pour pouvoir effectuer la mise à jour vers cette build, HoloLens 2 appareil (s) doit exécuter la mise à jour du 2021 février (build 19041,1136) ou une version plus récente. Si vous ne voyez pas cette mise à jour de fonctionnalité disponible, mettez d’abord à jour votre appareil, puis réessayez.

>[!NOTE]
>aujourd’hui, Microsoft HoloLens 2 prend en charge les mises à jour de maintenance mensuelles (bogues et correctifs de sécurité) pour les versions suivantes :
>- Windows Holographique, version 20H2 (Build 19041.1128 +)
>- Windows Holographique, version 2004 (Build 19041.1103 +)
>- Windows Holographique, version 1903 (Build 18362 +) 
>
> avec l’introduction de Windows version holographique 21H1, **nous continuons de mettre à jour les mises à jour de maintenance mensuelles pour Windows version 1903 holographique**. Cela nous permet de nous concentrer sur les versions plus récentes et de continuer à fournir des améliorations importantes. 


| Nom de la fonctionnalité                                              | Description courte                                                                      | Public visé | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nouvelle Microsoft Edge](#introducing-the-new-microsoft-edge)  | le nouveau Microsoft Edge basé sur Chromium est désormais disponible pour HoloLens 2. | Utilisateur final | 
[Visionneuse WebXR et 360](#webxr-and-360-viewer) | Essayez des expériences Web immersifs et une lecture vidéo de 360. | Utilisateur final | 
[nouvelle Paramètres application](#new-settings-app) | l’application de Paramètres héritée est remplacée par une version mise à jour avec de nouvelles fonctionnalités et paramètres. | Utilisateur final |
[Étalonnage des couleurs d’affichage](#display-color-calibration) | sélectionnez un autre profil de couleurs pour votre affichage HoloLens 2. | Utilisateur final |
[Sélecteur d’application par défaut](#default-app-picker) | Choisissez l’application à lancer pour chaque type de fichier ou de lien. | Utilisateur final |
[Contrôle du volume par application](#per-app-volume-control) | Contrôlez le volume au niveau de l’application indépendamment du volume système. | Utilisateur final |
[Installer Web Apps](#install-web-apps) | installez web apps sur HoloLens 2, comme Microsoft Office, avec le nouveau navigateur de Microsoft Edge. | Utilisateur final |
[Faire glisser vers le type](#swipe-to-type) | Utilisez l’astuce de votre doigt pour « balayer » les mots sur le clavier holographique. | Utilisateur final |
[Menu alimenter à partir du menu Démarrer](#power-menu-from-start) | dans le Menu démarrer, redémarrez et arrêtez HoloLens appareil. | Utilisateur final |
[Plusieurs utilisateurs sont listés sur l’écran de connexion](#multiple-users-listed-on-sign-in-screen) | Affichez plusieurs comptes d’utilisateur sur l’écran de connexion. | Utilisateur final |
[Prise en charge du microphone externe USB-C](#usb-c-external-microphone-support) | Utilisez des microphones USB-C pour les applications et/ou l’assistance à distance. | Utilisateur final |
[Ouverture de session automatique des visiteurs pour les bornes](#visitor-auto-logon-for-kiosks) | Active l’ouverture de session automatique sur les comptes de visiteur à utiliser pour les modes plein écran. | IT Admin |
[Nouvelle AUMIDs pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs pour les nouvelles applications Paramètres et Edge. | IT Admin |
[Gestion améliorée des échecs du mode plein écran](#kiosk-mode-behavior-changes-for-handling-of-failures) | Le mode plein écran recherche un accès global affecté avant le menu Démarrer vide. | IT Admin |
[nouvelle SettingsURIs pour la visibilité de la Paramètres de Page](#new-settings-uris-for-page-settings-visibility) | plus de 20 nouveaux SettingsURIs pour Paramètres stratégie/PageVisibilityList. | IT Admin |
[Configurer les diagnostics de secours](#configuring-fallback-diagnostics-via-settings-app) | définition du comportement de Diagnostic de secours dans Paramètres application. | IT Admin |
[Partager des éléments avec des appareils proches](#share-things-with-nearby-devices) | partager des fichiers ou des url à partir d’un HoloLens sur un PC. | Tous |
[Nouvelles traces de diagnostic du système d’exploitation](#new-os-diagnostic-traces) | nouvel utilitaire de résolution des problèmes dans Paramètres pour les mises à jour du système d’exploitation. | IT Admin |
[Aperçu de l’optimisation de la livraison](#delivery-optimization-preview) | réduisez la consommation de bande passante pour les téléchargements à partir de plusieurs appareils HoloLens. | IT Admin |

Consultez les notes de publication associées :

- [visitez le HoloLens Emulator archive](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Présentation de la nouvelle Microsoft Edge

![Animation du logo de Microsoft Edge hérité sur le nouveau logo de Microsoft Edge](images/new-edge.gif)

le nouvel Microsoft Edge [adopte le Chromium projet open source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) pour créer une meilleure compatibilité pour les clients et moins de fragmentation du web pour les développeurs web.

> [!IMPORTANT]
> ce nouveau Microsoft Edge remplace automatiquement Microsoft Edge hérité, qui n’est [plus pris en charge](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) dans les nouvelles versions.

![capture d’écran nouvelle Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Lancement du nouveau Microsoft Edge

Le nouveau Microsoft Edge ![icône de nouvelle Microsoft Edge](images/new_edge_logo.png) (représenté par une icône de tourbillon bleue et bleue) est épinglé au menu Démarrer et s’ouvre automatiquement lorsque vous activez un lien web.

> [!NOTE]
> lorsque vous lancez pour la première fois le nouveau Microsoft Edge sur HoloLens 2, vos paramètres et données sont importés à partir des Microsoft Edge héritées. si vous continuez à utiliser les Microsoft Edge héritées après avoir lancé le nouveau Microsoft Edge, ces nouvelles données ne seront pas synchronisées à partir des Microsoft Edge héritées vers le nouveau Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuration des paramètres de stratégie pour le nouveau Microsoft Edge

la nouvelle Microsoft Edge offre aux administrateurs informatiques un ensemble plus large de stratégies de navigateur sur HoloLens 2 que celles précédemment disponibles avec les Microsoft Edge héritées.

Voici quelques ressources utiles pour en savoir plus sur la gestion des paramètres de stratégie pour le nouveau Microsoft Edge :

- [configurer les paramètres de stratégie de Microsoft Edge avec Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Version antérieure de Microsoft Edge Microsoft Edge mappage de stratégie](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [mappage de la stratégie Google Chrome à Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- documentation complète sur [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> en raison du volume de stratégies de navigateur prises en charge par le nouveau Microsoft Edge, notre équipe ne peut pas garantir que chaque nouvelle stratégie fonctionne sur HoloLens 2. toutefois, nous avons testé et confirmé que le nouvel Microsoft Edge équivalent de chaque stratégie de Microsoft Edge hérité précédemment prise en charge sur HoloLens 2 fonctionnent comme prévu. consultez [Version antérieure de Microsoft Edge à Microsoft Edge mappage de stratégie](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) pour trouver le nouvel équivalent Microsoft Edge de chaque stratégie de navigateur de Microsoft Edge héritée que vous utilisiez avec HoloLens 2.
>
> au moins deux nouvelles stratégies de Microsoft Edge que nous savons ne fonctionneront *pas* avec HoloLens 2 :
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>ce qu’il faut attendre du nouvel Microsoft Edge sur HoloLens 2

étant donné que le nouveau Microsoft Edge est une application Win32 native avec une nouvelle couche d’adaptateur uwp, ce qui lui permet de s’exécuter sur des appareils uwp tels que HoloLens 2, certaines fonctionnalités peuvent ne pas être immédiatement disponibles. Nous allons prendre en charge de nouveaux scénarios et fonctionnalités au cours des prochains mois. par conséquent, consultez cet espace pour obtenir des informations à jour.

**Les scénarios et les fonctionnalités devraient fonctionner :**
- Expérience de première exécution, connexion au profil et synchronisation
- Les sites Web doivent s’afficher et se comporter comme prévu
- La plupart des fonctionnalités du navigateur (favoris, historique, etc.) doivent fonctionner comme prévu
- Mode sombre
- Installation d’applications Web sur l’appareil
- Installation des extensions (faites-le nous savoir si vous utilisez des extensions qui ne fonctionnent pas correctement sur HoloLens 2)
- Affichage et marquage d’un fichier PDF
- Son spatial à partir d’une seule fenêtre de navigateur
- Mise à jour automatique et manuelle du navigateur
- Enregistrement d’un fichier PDF à partir du menu Imprimer (option « Enregistrer au format PDF »)
- Extension de la visionneuse WebXR et 360
- Restauration du contenu vers la fenêtre appropriée, lors de la navigation entre plusieurs fenêtres placées dans votre environnement

**Les scénarios et les fonctionnalités ne sont pas censés fonctionner :**
- Son spatial à partir de plusieurs fenêtres avec des flux audio simultanés
- « Regardez-le, dites-le »
- Impression

**Principaux problèmes connus du navigateur :**

- L’aperçu de la loupe dans le clavier holographique a été désactivé pour la nouvelle Microsoft Edge. Nous espérons réactiver cette fonctionnalité dans une prochaine mise à jour, une fois que l’agrandissement fonctionnera correctement.
- L’audio peut s’exécuter à partir d’une fenêtre de navigateur incorrecte si une autre fenêtre de navigateur est ouverte et active. Vous pouvez contourner ce problème en fermant l’autre fenêtre active qui n’est pas censée être en cours de lecture audio.
- Lors de la lecture de l’audio à partir d’une fenêtre de navigateur en [mode « suivre »](hololens2-basic-usage.md#follow-me-stop-following), l’audio continue de s’exécuter si vous désactivez le mode « suivre ». Vous pouvez contourner ce problème en arrêtant la lecture audio avant de désactiver le mode « suivre » ou en fermant la fenêtre avec le bouton **X** .
- l’interaction avec active Microsoft Edge windows peut entraîner l’inactivité des autres fenêtres d’application 2d. Vous pouvez réactiver ces fenêtres en les interagissant avec elles.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Canaux d’initiés

l’équipe Microsoft Edge met à disposition trois canaux de préversion à la communauté Edge insider : bêta, Dev et canaries. l’installation d’un canal de préversion ne désinstalle pas la version finale de Microsoft Edge sur votre HoloLens 2, et vous pouvez en installer plusieurs à la fois. 

visitez la [page d’accueil Microsoft Edge insider](https://www.microsoftedgeinsider.com) pour en savoir plus sur la communauté Edge insider. Pour en savoir plus sur les différents canaux Edge Insider et sur la prise en main, visitez la [page de téléchargement de Edge Insider](https://www.microsoftedgeinsider.com/download).

deux méthodes sont disponibles pour installer Microsoft Edge les canaux insider à HoloLens 2 :

**Installation directe sur l’appareil (actuellement disponible uniquement pour les appareils non gérés)**
  1. sur votre HoloLens 2, accédez à la [page de téléchargement de Edge insider](https://www.microsoftedgeinsider.com/download).
  1. sélectionnez le bouton **télécharger pour HoloLens 2** pour le canal Edge insider que vous souhaitez installer.
  1. Lancez le fichier. msix téléchargé à partir de la file d’attente de téléchargement Edge ou du dossier « downloads » de votre appareil (à l’aide de l’Explorateur de fichiers).
  1. Le [programme d’installation](app-deploy-app-installer.md) de l’application démarre.
  1. Sélectionnez le bouton **Installer**.
  1. une fois l’installation réussie, vous trouverez Microsoft Edge Beta, Dev ou canaries sous la forme d’une entrée distincte dans la liste **toutes les applications** du menu Démarrer.

**installer via un PC avec Windows portail des appareils (nécessite l’activation du [mode développeur](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) sur HoloLens 2)**
  1. Sur votre PC, accédez à la [page de téléchargement de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. sélectionnez le **bouton de la flèche déroulante** en regard du bouton « télécharger pour Windows 10 » pour le canal Edge insider que vous souhaitez installer.
  1. sélectionnez **HoloLens 2** dans le menu déroulant.
  1. Enregistrez le fichier. msix dans le dossier « téléchargements » de votre ordinateur (ou dans un autre dossier que vous trouverez facilement).
  1. utilisez [Windows Portal Device](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) sur votre PC pour installer le fichier. msix téléchargé sur HoloLens 2.
  1. une fois l’installation réussie, vous trouverez Microsoft Edge Beta, Dev ou canaries sous la forme d’une entrée distincte dans la liste **toutes les applications** du menu Démarrer.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Utilisation de WDAC pour bloquer les nouvelles Microsoft Edge

pour les administrateurs informatiques qui cherchent à mettre à jour leur [stratégie WDAC](windows-defender-application-control-wdac.md) pour bloquer le nouvel Microsoft Edge application, vous devez ajouter les éléments suivants à votre stratégie.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestion des points de terminaison pour le nouveau Microsoft Edge

Certains environnements peuvent avoir des restrictions réseau à prendre en compte. Pour garantir une expérience sans heurts avec la nouvelle périphérie, [activez ces points de terminaison Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

En savoir plus sur les [points de terminaison actuellement disponibles pour HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Installer Web Apps
 > [!Note]
>à partir de [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), l’application web Office ne sera plus installée.

vous pouvez utiliser le nouveau bord pour installer des applications web en même temps que des applications Microsoft Store. par exemple, vous pouvez installer l’application web Microsoft Office pour afficher et modifier des fichiers hébergés sur SharePoint ou OneDrive. pour installer l’application web Office, visitez https://www.office.com et sélectionnez le bouton **application disponible** ou **installer Office** dans la barre d’adresses. Sélectionnez **installer** pour confirmer.

> [!IMPORTANT]
> Office fonctionnalité d’application web n’est disponible que si votre HoloLens 2 dispose d’une connexion internet active.

### <a name="webxr-and-360-viewer"></a>Visionneuse WebXR et 360

le nouveau Microsoft Edge prend en charge WebXR, qui est la nouvelle norme pour créer des expériences web immersifs (en remplaçant WebVR). De nombreuses expériences Web immersifs ont été conçues avec VR à l’esprit (elles remplacent votre champ de vue par un environnement virtuel), mais ces expériences sont également prises en charge par HoloLens 2. La norme WebXR permet également des expériences Web immersifs enrichies et en réalité mixte qui utilisent votre environnement physique. à mesure que les développeurs consacrent plus de temps à WebXR, nous prévoyons de nouvelles expériences immersifs de réalité accrue et de la réalité mixte pour HoloLens 2 clients à essayer !

l’extension de visionneuse 360 est basée sur WebXR et s’installe automatiquement en même temps que le nouveau Microsoft Edge sur HoloLens 2. Cette extension Web vous donne la possibilité de vous plonger dans des vidéos de 360 degrés. YouTube offre la plus grande sélection de vidéos 360, nous vous encourageons donc à les démarrer.

#### <a name="how-to-use-webxr"></a>Utilisation de WebXR

1. Accédez à un site Web avec prise en charge de WebXR.
1. Sélectionnez le bouton **Enter VR** sur le site Web. L’emplacement et la représentation visuelle de ce bouton peuvent varier en fonction du site Web, mais peuvent ressembler à ceci :

    ![Exemple de bouton ENTER VR](images/75px-enter-vr.png)

1. La première fois que vous essayez de lancer une expérience WebXR sur un domaine spécifique, le navigateur vous demande le consentement d’entrer dans un affichage immersif, sélectionnez **autoriser**.
1. utilisez [HoloLens 2 les gestes](hololens2-basic-usage.md#the-hand-tracking-frame) pour manipuler l’expérience.
1. Si l’expérience n’a pas de bouton **quitter** , utilisez le [geste démarrer](hololens2-basic-usage.md#start-gesture) pour revenir à l’accueil.

**Exemples de WebXR recommandés**
- visionneuse 360 (voir la section suivante)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Comment utiliser la visionneuse 360

1. Accédez à une vidéo de 360 degrés sur YouTube.
1. Dans l’image vidéo, sélectionnez le bouton casque de réalité mixte :

    ![Bouton pour activer la visionneuse 360](images/enter-360-viewer.jpg)

1. La première fois que vous essayez de lancer la visionneuse 360 sur un domaine spécifique, le navigateur vous demande le consentement d’entrer dans une vue immersive. Sélectionnez **Autoriser**.
1. [Appuyez](hololens2-basic-usage.md#select-using-air-tap) sur l’air pour afficher les contrôles de lecture. Utilisez les [rayons de main et le robinet d’air](hololens2-basic-usage.md#select-using-air-tap) pour la lecture/pause, les sauts vers l’avant/arrière, l’activation/désactivation des sous-titres ou l’arrêt de l’expérience (ce qui a pour conséquence de quitter l’affichage immersif). Les contrôles de lecture disparaissent après quelques secondes d’inactivité.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principaux problèmes connus de la visionneuse WebXR et 360
- En fonction de la complexité de l’expérience WebXR, les cadences peuvent chuter ou être saccadées.
- La prise en charge des articulations de la main dans WebXR n’est pas activée par défaut. Les développeurs peuvent activer la prise en charge via `edge://flags` en activant « WebXR main Input ».
- 360 les vidéos provenant de sites Web autres que YouTube peuvent ne pas fonctionner comme prévu.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Envoi de commentaires sur WebXR et la visionneuse 360

Partagez vos commentaires avec notre équipe via la fonctionnalité **Envoyer des commentaires** du nouveau Microsoft Edge.

### <a name="new-settings-app"></a>nouvelle Paramètres application

avec cette version, nous allons introduire une nouvelle version de l’application Paramètres. la nouvelle Paramètres application comprend de nouvelles fonctionnalités et des paramètres étendus pour HoloLens 2 dans les domaines suivants : le son, Power & sleep, le réseau & Internet, les applications, les comptes, la facilité d’accès et bien plus encore.

> [!NOTE]
> étant donné que la nouvelle Paramètres application est distincte de l’application Paramètres héritée, toutes les fenêtres Paramètres que vous avez placées précédemment dans votre environnement seront supprimées lors de la mise à jour.

![nouvelle page d’accueil de l’application Paramètres](images/new-settings-app.png)

**Nouvelles fonctionnalités et paramètres**
- recherche Paramètres : recherchez des paramètres à partir de la page d’accueil Paramètres à l’aide de mots clés ou du nom du paramètre.
- Son du > système :
  - périphériques audio d’entrée et de sortie : choisissez indépendamment vos périphériques audio d’entrée et de sortie (par exemple, écoutez l’audio via Bluetooth casque ou utilisez un microphone USB-C pour l’entrée audio).
    > [!NOTE]
    > les microphones Bluetooth ne sont pas pris en charge par les HoloLens 2.
  - Volume de l’application : Ajustez indépendamment le volume de chaque application. Voir [contrôle du volume par application](#per-app-volume-control).
- Système > Power & Sleep : choisissez quand l’appareil doit être mis en veille après une période d’inactivité.
- Batterie du > système : activez manuellement le mode économiseur de batterie ou définissez un seuil de batterie à partir duquel le mode économiseur de batterie s’active automatiquement.
- Périphériques > USB : vous pouvez désactiver les connexions USB par défaut.
- Réseau & Internet :
  - Les adaptateurs Ethernet USB-C s’affichent désormais dans le réseau & Internet.
  - Les paramètres de la carte Ethernet USB-C sont désormais disponibles, y compris son adresse IP.
  - Vous pouvez maintenant activer le mode avion sur HoloLens 2.
- Applications : vous pouvez réinitialiser les applications par défaut utilisées pour les types de fichier et de lien. Pour plus d’informations, consultez [Sélecteur d’application par défaut](#default-app-picker).
- Comptes > autres utilisateurs : les propriétaires d’appareils peuvent ajouter des utilisateurs, mettre à niveau des utilisateurs standard vers des propriétaires d’appareils, rétrograder les propriétaires d’appareils aux utilisateurs standard et supprimer des utilisateurs.
- Facilité d’accès : modifiez la taille du texte et certains effets visuels.

**Problèmes connus**
- les fenêtres précédemment placées Paramètres seront supprimées (voir la remarque ci-dessus).
- vous ne pouvez plus renommer votre appareil avec l’application Paramètres. les administrateurs informatiques peuvent renommer des appareils à l’aide du [Windows autopilot pour](https://docs.microsoft.com/hololens/hololens2-autopilot) le modèle de nom de périphérique HoloLens 2 ou du nœud [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) /Microsoft/DNSComputerName.
- La page Ethernet affiche un périphérique Ethernet virtuel (« UsbNcm ») à tout moment.
- l’utilisation de la batterie pour le nouveau Microsoft Edge peut ne pas être exacte, en raison de sa nature comme une application de bureau Win32 prise en charge par une couche d’adaptateur UWP (aucun correctif anticipé prochainement).

#### <a name="display-color-calibration"></a>Étalonnage des couleurs d’affichage



avec ce nouveau paramètre, vous pouvez sélectionner un autre profil de couleurs pour votre HoloLens 2 affichage. Cela peut aider à obtenir des couleurs plus précises, en particulier des niveaux de luminosité d’affichage inférieurs. l’étalonnage des couleurs d’affichage se trouve dans l’application Paramètres, sur la page étalonnage du > système.

> [!NOTE]
> Étant donné que ce paramètre enregistre un nouveau profil de couleurs dans votre microprogramme d’affichage, il s’agit d’un paramètre par appareil (et non propre à chaque compte d’utilisateur).

##### <a name="how-to-use-display-color-calibration"></a>Comment utiliser l’étalonnage des couleurs d’affichage

1. lancez l’application **Paramètres** et accédez à **système > étalonnage**.
1. Sous **étalonnage des couleurs** de l’écran, sélectionnez le bouton **exécuter l’étalonnage des couleurs** .
1. L’expérience d’étalonnage des couleurs s’affiche et vous encourage à vous assurer que votre visière est bien à la bonne position.
1. Une fois que vous avez parcouru les boîtes de dialogue d’instruction, votre affichage est automatiquement grisé à 30%.
    > [!TIP]
    > si vous ne parvenez pas à voir la scène estompée dans votre environnement, vous pouvez ajuster manuellement le niveau de luminosité de HoloLens 2 à l’aide des boutons de luminosité sur le côté gauche de l’appareil.
1. Sélectionnez les boutons 1-6 pour essayer instantanément chaque profil de couleurs et en trouver un qui ressemble le mieux à vos yeux (cela signifie généralement que le profil qui permet d’afficher la scène est le plus neutre, avec le modèle de nuances de gris et les tonalités de peau qui se présentent comme prévu).

    ![Scène d’étalonnage des couleurs d’affichage](images/color-cal-ui.png)
    
1. Quand vous êtes satisfait du profil sélectionné, cliquez sur le bouton **enregistrer & quitter**
1. Si vous préférez ne pas apporter de modifications, cliquez sur le bouton **annuler & quitter** . vos modifications seront rétablies

> [!TIP]
> Voici quelques conseils utiles à garder à l’esprit lors de l’utilisation du paramètre d’étalonnage des couleurs de l’écran :
> - vous pouvez réexécuter l’étalonnage des couleurs d’affichage à partir de Paramètres chaque fois que vous le souhaitez
> - si une personne de l’appareil a déjà utilisé le paramètre pour modifier les profils de couleurs, la date/l’heure de la dernière modification sera reflétée sur la page de Paramètres
> - Lorsque vous réexécutez l’étalonnage des couleurs d’affichage, le profil de couleurs précédemment enregistré est mis en surbrillance et le profil 0 ne s’affiche pas (comme le profil 0 représente le profil de couleurs d’origine de l’affichage)
> - si vous souhaitez rétablir le profil de couleurs d’origine de l’affichage, vous pouvez le faire à partir de la page Paramètres (voir [comment réinitialiser le profil de couleurs](#how-to-reset-color-profile)).

##### <a name="how-to-reset-color-profile"></a>Comment réinitialiser le profil de couleurs 

si vous n’êtes pas satisfait du profil de couleurs personnalisé enregistré dans votre HoloLens 2, vous pouvez restaurer le profil de couleurs d’origine de l’appareil :
1. lancez l’application **Paramètres** et accédez à **système > étalonnage**.
1. Sous **étalonnage des couleurs** de l’écran, sélectionnez le bouton **rétablir le profil de couleurs par défaut** .
1. quand la boîte de dialogue s’ouvre, sélectionnez **redémarrer** si vous êtes prêt à redémarrer HoloLens 2 et à appliquer vos modifications.

#### <a name="top-display-color-calibration-known-issues"></a>Problèmes connus d’étalonnage des couleurs de l’écran principal

- dans la page Paramètres, la chaîne d’état qui indique à quel moment la dernière modification du profil de couleurs est obsolète jusqu’à ce que vous rechargeiez cette page de Paramètres.
    - solution de contournement : sélectionnez une autre page de Paramètres, puis sélectionnez à nouveau la page d’étalonnage.

#### <a name="default-app-picker"></a>Sélecteur d’application par défaut

Quand vous activez un lien hypertexte ou que vous ouvrez un type de fichier avec plusieurs applications installées, ce qui le prend en charge, une nouvelle fenêtre s’affiche pour vous inviter à sélectionner l’application installée qui doit gérer le type de fichier ou de lien. Dans cette fenêtre, vous pouvez également choisir d’utiliser l’application sélectionnée pour gérer le type de fichier ou de lien « une fois » ou « toujours ».

si vous choisissez « toujours », mais que vous souhaitez ultérieurement modifier l’application qui gère un type de fichier ou de lien particulier, vous pouvez réinitialiser vos valeurs par défaut enregistrées dans **Paramètres applications >**. Faites défiler vers le bas de la page et sélectionnez le bouton **Effacer** sous « applications par défaut pour les types de fichiers » et/ou « applications par défaut pour les types de liens ». Contrairement au paramètre similaire sur les PC de bureau, vous ne pouvez pas réinitialiser les valeurs par défaut des types de fichiers individuels.

#### <a name="per-app-volume-control"></a>Contrôle du volume par application

à présent, dans cette Windows build, les utilisateurs peuvent ajuster manuellement le niveau de volume de chaque application. Cela permet aux utilisateurs de mieux se concentrer sur les applications dont ils ont besoin, ou de mieux les entendre lors de l’utilisation de plusieurs applications. Par exemple, la nécessité de désactiver le volume d’une application lors de l’appel d’une autre personne pour l’assistance à distance dans une autre.

pour définir le volume d’une application individuelle, accédez à **Paramètres**  ->    ->  **son** système, puis sous options de son avancées, sélectionnez le volume de l' **application et les préférences de l’appareil**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Faire glisser vers le type

Certains clients le trouvent plus rapidement pour « taper » sur des claviers virtuels en passant la forme du mot qu’ils envisagent de taper, et nous prévoyons cette fonctionnalité pour le clavier holographique. Vous pouvez balayer un mot à la fois en passant la pointe de votre doigt dans le plan du clavier holographique, en balayant la forme du mot, puis en retirant l’extrémité de votre doigt du plan du clavier. Vous pouvez balayer les mots de suivi sans avoir à appuyer sur la barre d’espace en supprimant votre doigt du clavier entre les mots. Vous saurez que la fonctionnalité fonctionne si vous voyez une piste de balayage après le déplacement de votre doigt sur le clavier.

Veuillez noter que cette fonctionnalité peut être difficile à utiliser et à maîtriser en raison de la nature d’un clavier holographique dans lequel vous ne vous inquiétez pas de la résistance à votre doigt (contrairement à un affichage sur téléphone mobile). 

### <a name="power-menu-from-start"></a>Menu alimenter à partir du menu Démarrer

Nouveau menu qui permet à l’utilisateur de se déconnecter, d’arrêter et de redémarrer l’appareil. indicateur dans l’écran de démarrage HoloLens qui indique quand une mise à jour du système est disponible.

#### <a name="how-to-use"></a>Procédure d'utilisation

1. ouvrez l’écran de démarrage HoloLens à l’aide du [mouvement de début](hololens2-basic-usage.md#start-gesture) ou en disant « aller à démarrer ».

2. Notez l’icône de points de suspension (...) en regard de l’image du profil utilisateur :<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Sélectionnez l’image de profil utilisateur à l’aide de vos mains ou de la commande vocale « Power ».

4. Un menu s’affiche avec les options de déconnexion, de redémarrage ou d’arrêt de l’appareil :<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Sélectionnez les options de menu à déconnecter, redémarrez ou arrêtez votre HoloLens. L’option de déconnexion peut ne pas être disponible si l’appareil est configuré pour un compte [Microsoft (MSA) ou un compte local unique](hololens-identity.md).

6. faire disparaître le menu en touchant n’importe quel autre emplacement ou en fermant le menu Démarrer avec le mouvement de début.

#### <a name="update-indicator"></a>Indicateur de mise à jour

Quand une mise à jour est disponible, l’icône de points de suspension s’affiche pour indiquer qu’un redémarrage installera les options de menu change également pour refléter la présence de la mise à jour.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Plusieurs utilisateurs sont listés sur l’écran de connexion

Auparavant, l’écran de connexion affichait uniquement l’utilisateur connecté le plus récemment, ainsi que le point d’entrée « autre utilisateur ». Nous avons reçu des commentaires des clients qui ne suffisent pas si plusieurs utilisateurs se sont connectés à l’appareil. Ils devaient encore retaper leur nom d’utilisateur, etc.

dans cette Windows build, lors de la sélection d’un **autre utilisateur** situé à droite du champ d’entrée du code confidentiel, l’écran de connexion affiche plusieurs utilisateurs ayant déjà été connectés à l’appareil. cela permet aux utilisateurs de sélectionner leur profil utilisateur, puis de se connecter à l’aide de leurs informations d’identification de Windows Hello. Un nouvel utilisateur peut également être ajouté à l’appareil à partir de la page autres utilisateurs via le bouton **Ajouter un compte** .

Quand vous êtes dans le menu autres utilisateurs, le bouton autres utilisateurs affiche le dernier utilisateur connecté à l’appareil. Sélectionnez ce bouton pour revenir à l’écran de connexion de cet utilisateur.

![Valeur par défaut de l’écran de connexion](./images/multiusers1.jpg)

<br>

![Écran de connexion d’autres utilisateurs](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Prise en charge du microphone externe USB-C

> [!IMPORTANT]
> Le branchement d' **un micro USB ne le définit pas automatiquement comme périphérique d’entrée**. lors de la connexion à un ensemble d’utilisateurs de casque USB-C, l’audio du casque est automatiquement redirigé vers le casque, mais le système d’exploitation HoloLens hiérarchise le groupe de microphones interne au-dessus de tout autre périphérique d’entrée. **Pour utiliser un microphone USB-C, suivez les étapes ci-dessous.**

Les utilisateurs peuvent sélectionner des microphones externes connectés par USB-C à l’aide du panneau Paramètres du **son** . Les microphones USB-C peuvent être utilisés pour appeler, enregistrer, etc.

ouvrez l’application **Paramètres** et sélectionnez   >  **son** système.

![Paramètres audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pour utiliser des microphones externes avec l' **assistance à distance**, les utilisateurs doivent cliquer sur le lien hypertexte « gérer les périphériques audio ».
>
> Ensuite, utilisez la liste déroulante pour définir le microphone externe comme valeur **par défaut** ou **par défaut de communication.** Si vous choisissez la **valeur par défaut** , le microphone externe sera utilisé partout.
>
> le choix de la **valeur par défaut** de la communication signifie que le microphone externe sera utilisé dans l’assistance à distance et d’autres applications de communication, mais que le tableau HoloLens mic peut toujours être utilisé pour d’autres tâches.

![Gérer les périphériques audio](images/usbc-mic-2.png)

<br>

![Définir le microphone par défaut](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>qu’en est-il de la prise en charge de microphone Bluetooth ?

malheureusement Bluetooth les microphones ne sont pas encore pris en charge sur HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Résolution des problèmes de microphones USB-C

Sachez que certains microtéléphones USB-C se signalent incorrectement comme un microphone *et* un orateur. Il s’agit d’un problème avec le microphone et pas avec HoloLens. lors du branchement de l’un de ces microphones dans HoloLens, le son peut être perdu. Heureusement, il existe un correctif simple.  

dans **Paramètres**  ->    ->  **son** système, définissez explicitement les haut-parleurs intégrés **(pilote Audio de fonctionnalité analogique)** comme **périphérique par défaut**. HoloLens mémoriser ce paramètre même si le microphone est supprimé et reconnecté ultérieurement.

![Résolution des problèmes de microphones USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Ouverture de session automatique visiteur pour les bornes

Cette nouvelle fonctionnalité permet l’utilisation de l’ouverture de session automatique sur les comptes de visiteur pour les modes plein écran.

Pour une configuration non-AAD, pour configurer un appareil pour la connexion automatique des visiteurs :

1. Créez un package d’approvisionnement qui :
    1. Configure les **paramètres d’exécution/AssignedAccess** pour autoriser les comptes de visiteur.
    1. Inscrit éventuellement l’appareil dans MDM **(paramètres d’exécution/espace de travail/inscriptions)** afin qu’il puisse être géré ultérieurement.
    1. Ne pas créer de compte local
1. [Appliquez le package d’approvisionnement](hololens-provisioning.md).

Pour une configuration AAD, les utilisateurs peuvent obtenir un résultat semblable à celui-ci aujourd’hui sans cette modification. Les appareils joints à AAD configurés pour le mode plein écran peuvent se connecter à un compte visiteur à l’aide d’un appui sur un bouton à partir de l’écran de connexion. Une fois connecté au compte du visiteur, l’appareil ne demande pas de connexion tant que le visiteur n’est pas explicitement déconnecté du menu Démarrer ou que l’appareil n’a pas été redémarré.

L’ouverture de session automatique des visiteurs peut être gérée par le biais d' [une stratégie OMA-URI personnalisée](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) :

- Valeur de l’URI :./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Stratégie  | Description   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permet à un visiteur de se connecter automatiquement à une borne   | 1 (oui), 0 (non, valeur par défaut.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>utiliser les nouvelles applications de Paramètres et Edge en mode plein écran

Lorsque vous incluez des applications dans des [kiosques](hololens-kiosk.md), un administrateur informatique ajoute souvent l’application à la borne, mais à l’aide de son ID de modèle d’utilisateur d’application (identifiant aumid). étant donné que l’application Paramètres et l’application Microsoft Edge sont considérées comme de nouvelles applications et que les kiosques des applications plus anciennes qui utilisent AUMIDs pour ces applications doivent être mis à jour pour utiliser le nouveau identifiant aumid.

Lorsque vous modifiez une borne pour inclure les nouvelles applications, nous vous recommandons d’ajouter dans le nouveau identifiant AUMID et de quitter l’ancien. Cela permet de créer une transition facile lorsque les utilisateurs mettent à jour le système d’exploitation et n’ont pas besoin de recevoir de nouvelles stratégies pour continuer à utiliser la borne comme prévu.

| Application                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| ancienne application Paramètres       | HolographicSystemSettings_cw5n1h2txyewy ! Lancement            |
| nouvelle Paramètres application       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy ! Lancement |
| ancienne application Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| nouvelle Microsoft Edge application | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe ! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifications du comportement du mode plein écran pour la gestion des défaillances

Dans les versions plus anciennes, si un appareil avait une configuration de kiosque, qui est une combinaison de l’accès attribué global et de l’accès affecté au membre du groupe AAD, si la détermination de l’appartenance au groupe AAD a échoué, l’utilisateur voit le menu «[rien ne s’affiche dans](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)le menu Démarrer ».

à partir de cette version de Windows, l’expérience de la borne sera de secours à la configuration globale des kiosques (le cas échéant) en cas de défaillances pendant le mode plein écran du groupe AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>nouveaux uri de Paramètres pour la visibilité de Paramètres de Page

dans [Windows holographique, version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) nous avons ajouté la [stratégie Paramètres/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages affichées dans l’application Paramètres. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher des pages spécifiques du système Paramètres application d’être visibles ou accessibles, ou de le faire pour toutes les pages, à l’exception de celles spécifiées.

si vous visitez [Page Paramètres visibilité](settings-uri-list.md), vous trouverez des instructions sur l’utilisation de ce fournisseur de services de chiffrement et la liste des uri disponibles dans les versions précédentes.

nous développons la liste des uri Paramètres disponibles, que les administrateurs peuvent gérer. certains de ces uri sont destinés aux nouvelles zones disponibles au sein de la nouvelle application Paramètres. si vous utilisez Paramètres stratégie/PageVisibilityList, passez en revue la liste suivante et ajustez vos pages autorisées ou bloquées si nécessaire.

> [!NOTE]
> **Déconseillé : ms-Settings : réseau-proxy**
>
> Une page de paramètres est dépréciée dans ces builds plus récentes. L’ancienne page **réseau & Internet**  >  **proxy** n’est plus disponible en tant que paramètre global. Les nouveaux paramètres de proxy par connexion se trouvent sous **réseau &**  >  **les propriétés Wi-Fi** Internet  >   ou **Propriétés réseau & Internet**  >    >  .

<br>

| Page Paramètres                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Applications > applications & fonctionnalités                               | `ms-settings:appsfeatures`                         |
| Applications > applications & fonctionnalités > options avancées          | `ms-settings:appsfeatures-app`                     |
| Applications > cartes hors connexion                                  | `ms-settings:maps`                                 |
| Applications > cartes hors connexion > télécharger des cartes                  | `ms-settings:maps-downloadmaps`                    |
| Appareils > souris                                      | `ms-settings:mouse`                                |
| Périphériques > USB                                        | `ms-settings:usb`                                  |
| & réseau > Internet en mode avion                   | `ms-settings:network-airplanemode`                 |
| Confidentialité > général                                    | `ms-settings:privacy-general`                      |
| Confidentialité > la personnalisation de l’encre & saisie             | `ms-settings:privacy-speechtyping`                 |
| Confidentialité > motion                                     | `ms-settings:privacy-motion`                       |
| Confidentialité > bordures de capture d’écran                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Captures d’écran et applications de la confidentialité >                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batterie du > système                                     | `ms-settings:batterysaver`                         |
| Batterie du > système                                     | `ms-settings:batterysaver-settings`                |
| Système > son                                       | `ms-settings:sound`                                |
| Système > son > les préférences du volume et de l’appareil de l’application | `ms-settings:apps-volume`                          |
| Système > son > gérer les périphériques audio              | `ms-settings:sound-devices`                        |
| > système Stockage > configurer Stockage sens         | `ms-settings:storagepolicies`                      |
| Date et & heure de la & > de la langue                        | `ms-settings:dateandtime`                          |
| & du clavier > Language                           | `ms-settings:keyboard`                             |
| Langue du > de la langue du &                           | `ms-settings:language`                             |
| Langue du > de la langue du &                           | `ms-settings:regionlanguage-languageoptions`       |
| Mettre à jour & sécurité > réinitialiser & récupération               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI mis à jour

Auparavant, les deux URI suivants n’empêchent pas l’utilisateur d’accéder directement aux pages indiquées, mais ont uniquement bloqué la page principale des mises à jour. Les éléments suivants ont été mis à jour pour diriger vers leurs pages :

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>configuration des diagnostics de secours par le biais de Paramètres application

désormais, dans Paramètres application, un utilisateur peut configurer le comportement des [diagnostics de secours](hololens-diagnostic-logs.md). dans le Paramètres application, accédez à la page de  ->  **résolution des problèmes** de confidentialité pour configurer ce paramètre.

> [!NOTE]
> Si une stratégie MDM est configurée pour l’appareil, l’utilisateur ne sera pas en mesure de remplacer ce comportement.  

### <a name="share-things-with-nearby-devices"></a>Partager des éléments avec des appareils proches

partagez des choses avec près de Windows 10 appareils, y compris les pc et les autres appareils HoloLens 2. vous pouvez l’essayer dans **Paramètres** les  ->    ->  **expériences partagées** du système pour partager des fichiers ou des url d’un HoloLens à un PC. Pour plus d’informations, consultez la rubrique pour en savoir plus sur la façon de [partager des éléments avec des appareils proches dans Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Cette fonctionnalité peut être gérée via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nouvelles traces de diagnostic du système d’exploitation

en plus des dépannages précédents au sein de l’application Paramètres, un nouvel utilitaire de résolution des problèmes a été ajouté avec l’ajout de la nouvelle application Paramètres pour les mises à jour du système d’exploitation. accédez à **Paramètres**  ->  **mettre &amp; à jour**  >  **les problèmes** de sécurité  >  **Windows Update** et sélectionnez **démarrer**. Cela vous permet de collecter des traces tout en reproduisant votre problème avec les mises à jour du système d’exploitation afin d’améliorer la résolution des problèmes avec votre service informatique ou votre support technique.

### <a name="delivery-optimization-preview"></a>Aperçu de l’optimisation de la livraison

avec cette mise à jour HoloLens, Windows Holographic for Business active les paramètres d’optimisation de la remise pour réduire la consommation de bande passante pour les téléchargements à partir de plusieurs appareils HoloLens. une description plus complète de cette fonctionnalité ainsi que la configuration réseau recommandée sont disponibles ici : [optimisation de la distribution pour les mises à jour Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Les paramètres suivants sont activés dans le cadre de la surface de gestion et [peuvent être configurés à partir d’Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Quelques avertissements concernant cette offre préliminaire :

- la prise en charge de HoloLens est limitée dans cette version préliminaire uniquement aux mises à jour du système d’exploitation.
- Windows Holographic for Business prend en charge uniquement les modes de téléchargement HTTP et les téléchargements à partir d’un [point de terminaison de Cache connecté Microsoft](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); les modes de téléchargement d’égal à égal et les affectations de groupe ne sont pas pris en charge pour les appareils HoloLens à l’heure actuelle.
- HoloLens ne prend pas en charge l’optimisation du déploiement ou de la distribution pour les points de terminaison Windows Server Update Services.
- la résolution des problèmes nécessite des diagnostics sur le serveur de Cache connecté ou la collecte d’une trace sur HoloLens sur HoloLens via **Paramètres**  >  **Update &** la  >   **résolution des problèmes** de sécurité  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Administrateur informatique-liste de vérification des mises à jour

Cette liste de vérification vous aidera à connaître les nouveaux éléments que les fonctionnalités ajoutées dans cette mise à jour des fonctionnalités peuvent avoir un impact sur les configurations de gestion des appareils en cours ou sur les nouvelles fonctionnalités que vous pouvez utiliser.

#### <a name="updates-to-kiosk-mode"></a>Mises à jour du mode plein écran

✔️ de [**nouvelles AUMIDs pour les nouvelles applications en mode plein écran**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

si vous utilisiez précédemment l’application Paramètres ou Microsoft Edge application dans une borne, nous avons remplacé ces applications par de nouvelles applications qui utilisent un ID d’application différent. Nous vous encourageons vivement à lire [les nouvelles AUMIDs pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes) ci-dessous. cela vous permet de continuer à disposer de l’application Paramètres dans votre kiosque ou d’inclure la nouvelle application Microsoft Edge. Ces modifications peuvent être effectuées maintenant et déployées sur tous les appareils et permettent une transition plus lisse lors de la mise à jour.

✔️ l'[**ouverture de session automatique des visiteurs pour les bornes**](#visitor-auto-logon-for-kiosks): 

Les visiteurs peuvent désormais être connectés automatiquement à une borne. Ce comportement est activé par défaut, mais peut être géré et désactivé.

✔️ de la gestion des [**échecs du mode plein écran**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Si l’appartenance au groupe AAD de l’utilisateur AAD connecté n’est pas correctement déterminée, la configuration de l’kiosque global est utilisée pour le menu Démarrer (le cas échéant); sinon, l’utilisateur reçoit un menu Démarrer vide. Si le menu Démarrer vide n’est pas une configuration que vous pouvez définir directement, cette nouvelle gestion peut être utile pour informer votre service de support technique de si vous utilisez des bornes, car cela peut s’appliquer à vos configurations ou vous pouvez apporter de nouveaux ajustements aux configurations d’accès affectées.

#### <a name="updates-to-page-settings-visibility"></a>mises à jour de la Page Paramètres visibilité

✔️ [**de nouveaux uri Paramètres pour la visibilité de la Paramètres de Page**](#new-settings-uris-for-page-settings-visibility)

si vous utilisez actuellement une [Page Paramètres visibilité](settings-uri-list.md) , vous souhaiterez peut-être ajuster les uri existants que vous avez autorisés ou bloqués.

#### <a name="updates-for-your-wdac-policy"></a>Mises à jour pour votre stratégie WDAC
✔️ si vous aviez précédemment bloqué la Microsoft Edge via WDAC, vous souhaiterez mettre à jour votre stratégie wdac. Vérifiez les éléments suivants et utilisez l’exemple de code fourni.
#### <a name="enable-new-endpoints-for-edge"></a>Activer les nouveaux points de terminaison pour Edge
✔️ si vous disposez d’une infrastructure qui implique la configuration de points de terminaison réseau tels que le proxy ou le pare-feu, activez ces nouveaux points de terminaison pour la nouvelle application Microsoft Edge.

#### <a name="newly-configurable-items"></a>Éléments nouvellement configurables

✔️ [configurer les diagnostics de secours](#configuring-fallback-diagnostics-via-settings-app): vous pouvez configurer si et qui peuvent collecter des diagnostics de secours.

✔️[partager des éléments avec des appareils proches](#share-things-with-nearby-devices): vous pouvez désactiver la nouvelle fonctionnalité de partage proche.

✔️ la [configuration des paramètres de stratégie pour le nouveau Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge): passez en revue les nouvelles configurations disponibles pour la Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nouvel outil de diagnostic

✔️[de nouveaux suivis de diagnostic du système d’exploitation](#new-os-diagnostic-traces): collecte les journaux relatifs aux mises à jour du système d’exploitation.

### <a name="improvements-and-fixes-in-the-update"></a>Améliorations et correctifs de la mise à jour :

- Les [Diagnostics hors connexion](hololens-diagnostic-logs.md#offline-diagnostics) incluent également des informations supplémentaires sur l’appareil pour le numéro de série et la version du système d’exploitation.
- Résout un problème lié au déploiement d’applications métier à l’aide de packages de configuration de l’exécution.
- Résout un problème lié à la création de rapports d’état d’installation des applications métier.
- Résout un problème de la persistance des nouveaux packages d’application sur les réinitialisations d’appareils.
- Résout un problème qui peut entraîner la saisie de symboles incorrects dans Edge pour les clients japonais.
- Améliore la résilience des mises à jour du système d’exploitation autour des applications préinstallées telles que Edge. 
- Résout la fiabilité des mises à jour ayant un impact sur l’installation de Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographique, version 20H2 – mise à jour mai 2021
- Build 19041,1146

Améliorations et correctifs de la mise à jour :
- cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à essayer notre build la plus récente, Windows holographique, version 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographique, version 1903-mise à jour de mai 2021
- Build 18362,1110

Améliorations et correctifs de la mise à jour :
- Cette mise à jour de qualité mensuelle ne contient pas de modifications notables. **Cette build ne recevra plus les mises à jour mensuelles du service**. nous vous encourageons à essayer notre build la plus récente, Windows holographique, version 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographique, version 20H2-mise à jour 2021 d’avril
- Build 19041,1144

Améliorations et correctifs de la mise à jour :

- Résout un problème lié à la création de rapports d’état d’installation des applications métier.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographique, version 1903-mise à jour d’avril 2021
- Build 18362,1108

Améliorations et correctifs de la mise à jour :

- résout un problème où l’Paramètres application se bloque lors d’une tentative de modification d’un mot de passe pour un compte local.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographique, version 20H2-mise à jour de mars 2021
- Build 19041,1140

Améliorations et correctifs de la mise à jour :

- les clients qui utilisent AdvancedPhotoCapture ou LowLagPhotoCapture pour capturer des photos avec HoloLens 2 sont désormais en mesure de récupérer la caméra jusqu’à 3 secondes après la capture de la photo.
- Résolution d’une fuite de mémoire dans le service de portail des appareils, le problème a provoqué l’augmentation de l’utilisation de la mémoire par le service qui a provoqué l’échec de l’allocation de mémoire par d’autres applications.
- Résolution d’un problème où les utilisateurs inscrits au déploiement par étapes ne sont pas en mesure de se connecter à l’appareil.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographique, version 1903-mise à jour du 2021 du 1er mars
- Build 18362,1102

Améliorations et correctifs de la mise à jour :

- Résolution d’une fuite de mémoire dans le service de portail des appareils, le problème a provoqué l’augmentation de l’utilisation de la mémoire par le service qui a provoqué l’échec de l’allocation de mémoire par d’autres applications.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographique, version 20H2-mise à jour de février 2021
- Build 19041,1136

Améliorations et correctifs de la mise à jour :

- Résout un problème lié à la configuration initiale des appareils et aux mises à jour des applications du Store.
- résout un problème concernant les mises à niveau et les vols pour les versions ultérieures de HoloLens.
- suppression des certificats préinstallés inutilisés du magasin racine eSIM des appareils HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographique, version 1903-mise à jour du 2021 du 1er février
- Build 18362,1098

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières builds pour Windows holographique, version 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographique, version 20H2-mise à jour de janvier 2021
- Build 19041,1134

Améliorations et correctifs de la mise à jour :

- Amélioration des performances lors du démarrage, de la reprise et du changement d’utilisateur lorsqu’il y a de nombreux utilisateurs sur l’appareil.
- Ajout de la prise en charge de Arm32 pour le [mode Research](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographique, version 1903-mise à jour du 1er janvier 2021
- Build 18362,1091

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières builds pour Windows holographique, version 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographique, version 20H2-mise à jour de décembre 2020
- Build 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>installer des applications sur HoloLens 2 via le programme d’installation d’application

nous **ajoutons une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications de manière plus fluide** sur vos appareils HoloLens 2. La fonctionnalité est **activée par défaut pour les appareils non gérés**. Pour éviter toute interruption des entreprises, le programme d’installation de l’application ne sera **pas disponible pour les appareils gérés** à l’heure actuelle.  

Un appareil est considéré comme « géré » si l' **une** des conditions suivantes est vraie :
- MDM [inscrit](hololens-enroll-mdm.md)
- Configuré avec le [package d’approvisionnement](hololens-provisioning.md)
- L' [identité](hololens-identity.md) de l’utilisateur est Azure ad

Vous êtes maintenant en mesure d’installer des applications sans avoir à activer le mode développeur ou à l’aide du portail des appareils.  Téléchargez simplement (via USB ou via Edge) le bundle AppX sur votre appareil et accédez au Bundle AppX dans l’Explorateur de fichiers pour être invité à lancer l’installation.  Vous pouvez également [lancer une installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  tout comme les applications que vous installez à partir de la Microsoft Store ou chargement à l’aide de la fonctionnalité de déploiement d’applications métier MDM, les applications doivent être signées numériquement avec l' [outil sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour que l’application puisse être déployée.

**Instructions d’installation de l’application.**

1.  S’assurer que votre appareil n’est pas considéré comme géré
1.  vérifiez que votre appareil HoloLens 2 est sous tension et connecté à votre PC.
1.  vérifiez que vous êtes connecté à l’appareil HoloLens 2
1.  sur votre PC, accédez à votre application personnalisée et copiez votreapplication. appxbundle sur yourdevicename\Internal Stockage \Downloads.   Une fois que vous avez terminé de copier votre fichier, vous pouvez déconnecter votre appareil
1.  à partir de votre appareil HoloLens 2, ouvrez le Menu démarrer, sélectionnez toutes les applications, puis lancez l’application explorateur de fichiers.
1.  Accédez au dossier téléchargements. Vous devrez peut-être dans le volet gauche de l’application sélectionner cet appareil en premier, puis accéder à téléchargements.
1.  Sélectionnez le fichier VotreApplication. appxbundle.
1.  Le programme d’installation de l’application démarre. Sélectionnez le bouton installer pour installer votre application.
L’application installée sera automatiquement lancée à la fin de l’installation.

vous trouverez des exemples d’applications sur [Windows GitHub exemples universels](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) pour tester ce processus.

en savoir plus sur le processus complet d' [installation d’applications sur HoloLens 2 à l’aide du programme d’installation de l’application](app-deploy-app-installer.md).  

![Installation d’exemples MRTK via le programme d’installation d’application](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Améliorations et correctifs de la mise à jour :

- Le suivi des mains gère désormais le suivi dans de nombreux cas de figure où la main aurait été perdue précédemment.  Dans certains de ces nouveaux cas, seule la position du Palm continue à se mettre à jour en fonction de la main réelle de l’utilisateur, tandis que les autres jointures sont déduites en fonction d’une pose précédente.  Cette modification permet d’améliorer la cohérence du suivi des mouvements tels que flanque, la levée, la recherche et la applaudissements.  Elle est également utile dans les cas où la main est proche d’une surface ou maintient un objet.  Lorsque les articulations de la main sont déduites, la valeur de [précision conjointe](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) est définie sur « approximatif » au lieu de « High ».
- Correction d’un problème où la réinitialisation du code PIN pour les comptes Azure AD indique une erreur «un problème est survenu.
- Les utilisateurs doivent voir bien moins d’incidents OOBE après démarrage lors du lancement de, de l’iris à partir des paramètres application, nouvel utilisateur ou Toast de notification.
- Les utilisateurs doivent disposer d’un fuseau horaire correct sortant de OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographique, version 1903-mise à jour de décembre 2020
- Build 18362,1088

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à essayer notre dernière mise à jour Windows holographique, version 20H2-décembre 2020 et la nouvelle fonctionnalité de programme d’installation d’application ajoutée à la build.


## <a name="windows-holographic-version-20h2"></a>Windows Holographique, version 20H2
- Build 19041,1128

Windows holographique, version 20H2 est désormais disponible et offre un ensemble de nouvelles fonctionnalités pour HoloLens 2 les utilisateurs et les professionnels de l’informatique. du positionnement automatique, au gestionnaire de certificats dans Paramètres, à la fonctionnalité de Mode plein écran améliorée et aux nouvelles fonctionnalités de configuration de autopilot. cette nouvelle mise à jour permet aux équipes informatiques de bénéficier d’un contrôle plus granulaire de la configuration et de la gestion des appareils HoloLens, et offre aux utilisateurs des expériences holographiques encore plus fluides. 

Cette dernière version est une mise à jour mensuelle de la version 2004, mais cette fois, nous incluons de nouvelles fonctionnalités. le numéro de version majeure reste le même et Windows Update indique une version mensuelle de la version 2004 (build 19041). vous pouvez consulter votre numéro de build dans votre Paramètres > à propos de l’écran pour confirmer que vous êtes sur la dernière version disponible 19041.1128 +. pour effectuer une mise à jour vers la dernière version, ouvrez l’application Paramètres, accédez à update & Security, puis appuyez sur rechercher les mises à jour. pour plus d’informations sur la gestion des mises à jour HoloLens, visitez [cette page](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>nouveautés de Windows holographique, version 20H2  

| Fonctionnalité                                              | Description                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Prise en charge de la position oculaire automatique](hololens-release-notes.md#auto-eye-position-support) | Calcule activement les positions oculaires sans que les utilisateurs passent par l’étalonnage du suivi oculaire.   |
| [Gestionnaire de certificats](hololens-release-notes.md#certificate-manager)   | permet de nouvelles méthodes plus simples pour installer et supprimer des certificats de l’application Paramètres.     |
| [Lancement automatique de l’approvisionnement à partir d’USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | L’approvisionnement de packages sur des lecteurs USB invite automatiquement la page de configuration dans OOBE.                                                         |
| [Confirmer automatiquement les packages de provisionnement dans OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Les packages d’approvisionnement sont automatiquement appliqués lors de l’OOBE à partir de la page de configuration.                                                         |
| [Approvisionnement automatique sans interface utilisateur](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Comment combiner le lancement automatique et la confirmation automatique de l’approvisionnement. |
| [Utilisation de AutoPilot avec Wi-Fi connexion](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Utilisez AutoPilot à partir de Wi-Fi d’appareil sans carte Ethernet. |
| [CSP Tenantlockdown et Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Après l’inscription du locataire et la stratégie, l’appareil peut uniquement être inscrit dans ce locataire à chaque réinitialisation ou redémarrage de l’appareil. |
| [Accès global affecté](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nouvelle méthode de configuration pour le mode plein écran d’application qui applique la borne au niveau du système, en la rendant applicable à tous.                  |
| [Lancer automatiquement une application dans une borne multi-application](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Définit une application pour qu’elle démarre automatiquement lors de la connexion à un mode plein écran à plusieurs applications.                                                        |
| [Modifications du comportement du mode plein écran pour la gestion des défaillances](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L’échec du mode plein écran présente désormais une restriction de secours.                                                                                                |
| [HoloLens Directives](hololens-release-notes.md#hololens-policies)                                    | Nouvelles stratégies pour HoloLens.     |
| [Appartenance au groupe de Azure AD de cache pour une borne en mode hors connexion](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nouvelle stratégie permet aux utilisateurs d’utiliser le cache d’appartenance au groupe pour utiliser le mode plein écran pendant un nombre défini de jours.                                        |
| [Nouvelles stratégies de restriction d’appareil pour HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Les stratégies de gestion des appareils activées récemment pour HoloLens 2.                                                                                |
| [Nouvelles stratégies d’alimentation pour HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Stratégies nouvellement prises en charge pour les paramètres de délai d’attente.  |
| [Mettre à jour les stratégies](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Stratégies récemment activées autorisant le contrôle des mises à jour.           |
| [activation de la visibilité de page Paramètres pour HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | stratégie permettant de choisir les pages qui sont affichées dans Paramètres application.             |
| [Mode de recherche](hololens-release-notes.md#research-mode) | Utilisation du mode de recherche sur HoloLens 2. |
| [Durée d’enregistrement augmentée](hololens-release-notes.md#recording-length-increased) | Les enregistrements MRC ne sont plus limités à 5 minutes. |
| [Améliorations et correctifs de la mise à jour](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correctifs supplémentaires dans la mise à jour.   |

### <a name="auto-eye-position-support"></a>Prise en charge de la position oculaire automatique

dans HoloLens 2, les positions oculaires permettent un positionnement d’hologramme précis, une expérience d’affichage confortable et une meilleure qualité d’affichage. Les positions oculaires sont calculées en interne dans le cadre du calcul du suivi des yeux. Toutefois, cela nécessite que chaque utilisateur passe par l’étalonnage du suivi oculaire, même si l’expérience n’a pas besoin d’une entrée de regard oculaire.

La position de l' **œil automatique (AEP)** active ces scénarios avec une méthode sans interaction pour calculer les positions oculaires de l’utilisateur. La position de l’œil automatique commence à fonctionner en arrière-plan automatiquement à partir du moment où l’utilisateur place l’appareil. Si l’utilisateur n’a pas d’étalonnage de suivi visuel précédent, la position de l’œil automatique commence à fournir aux yeux de l’utilisateur le système d’affichage après un temps de traitement de 20-30 secondes. Les données utilisateur ne sont pas conservées sur l’appareil et, par conséquent, ce processus est répété si l’utilisateur le met hors tension, ou si l’appareil redémarre ou sort du mode veille.

Il y a quelques modifications de comportement du système avec la fonctionnalité de position d’oeil automatique lorsqu’un utilisateur non étalonné place sur l’appareil. Dans ce contexte, un utilisateur non étalonné fait référence à une personne qui n’a pas encore effectué le processus d’étalonnage du suivi oculaire sur l’appareil.

| Application active | Comportement précédent | comportement de Windows holographique, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Application sans point d’accès en regard ou interface holographique |La boîte de dialogue de l’invite d’étalonnage du suivi oculaire s’affiche. | Aucune invite ne s’affiche. |
| Application avec pointage en regard | La boîte de dialogue de l’invite d’étalonnage du suivi oculaire s’affiche. | L’invite d’étalonnage du suivi oculaire s’affiche uniquement quand l’application accède à un flux de regard visuel. |

Si l’utilisateur passe d’une application qui n’est pas activée pour la première fois à une application qui accède aux données de regard, l’invite d’étalonnage s’affiche. 

Tout autre comportement système est semblable à lorsque l’utilisateur actuel ne dispose pas d’un étalonnage de suivi oculaire actif. Par exemple, le mouvement de démarrage à la main n’est pas activé. Aucune modification n’est apportée à l’expérience d’installation initiale.

Pour les expériences nécessitant des données de regard visuelles ou un positionnement d’hologramme très précis, nous recommandons aux utilisateurs déétalonnés d’exécuter un étalonnage du suivi oculaire. elle est accessible à partir de l’invite d’étalonnage du suivi oculaire ou en lançant l’application Paramètres à partir du menu démarrer, puis en sélectionnant **système > étalonnage >** étalonnage de l’œil > exécution.

Ces informations peuvent être recherchées ultérieurement avec d' [autres informations d’étalonnage](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gestionnaire de certificats

- Amélioration de l’audit, du diagnostic et des outils de validation pour la sécurité et la conformité des appareils par le biais du nouveau gestionnaire de certificats. Cette fonctionnalité vous permettra de déployer, de dépanner et de valider vos certificats à grande échelle dans les environnements commerciaux.

dans Windows version holographique 20H2, nous ajoutons un gestionnaire de certificats à l’application HoloLens 2 Paramètres. accédez à **Paramètres > mettre à jour & les certificats > de sécurité**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs disposent désormais d’outils d’audit, de diagnostic et de validation améliorés pour garantir que les appareils restent sécurisés et conformes. 

-   **Audit :** Possibilité de valider le déploiement correct d’un certificat ou de confirmer qu’il a été supprimé de manière appropriée. 
-   **Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de faciliter la résolution des problèmes. 
-   **Validation :** Vérifier qu’un certificat est destiné à l’usage prévu et qu’il fonctionne, peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux avant de déployer des certificats à grande échelle.

Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher les propriétés d’un certificat, sélectionnez le certificat, puis cliquez sur **info**. 

L’installation de certificat prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats sur l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent s’installer que dans l’utilisateur actuel. les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur Paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

#### <a name="to-install-a-certificate"></a>Pour installer un certificat : 

1.  Connecter votre HoloLens 2 sur un PC.
1.  Placez le fichier de certificat que vous souhaitez installer à l’emplacement de votre HoloLens 2.
1.  accédez à **Paramètres application > mettre à jour & les certificats > de sécurité**, puis sélectionnez installer un certificat.
1.  Cliquez sur **Importer un fichier** et accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **emplacement du magasin**.
1.  Sélectionnez **magasin de certificats**.
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

#### <a name="to-remove-a-certificate"></a>Pour supprimer un certificat : 
1. accédez à **Paramètres application > des certificats de sécurité et de mise à jour >**.
1. Recherchez le certificat par son nom dans la zone de recherche.
1. Sélectionnez le certificat.
1. Cliquez sur **supprimer**
1. Lorsque vous êtes invité à confirmer l’opération, sélectionnez **Oui**.

![visionneuse de certificats dans l’application Paramètres](images/certificate-viewer-device.jpg)

![Image illustrant l’utilisation de l’interface utilisateur de certificat pour installer un certificat](images/certificate-device-install.jpg)

Ces informations peuvent être recherchées ultérieurement [dans une nouvelle page du gestionnaire de certificats](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Lancement automatique de l’approvisionnement à partir d’USB

- Processus automatisés permettant une utilisation moins importante de l’utilisateur quand des lecteurs USB avec des packages d’approvisionnement sont utilisés pendant l’OOBE.

Avant cette version, les utilisateurs devaient lancer l’écran d’approvisionnement manuellement lors de l’approvisionnement à l’aide d’une combinaison de boutons. Désormais, les utilisateurs peuvent ignorer la combinaison de boutons à l’aide d’un package d’approvisionnement sur un lecteur de stockage USB. 

1. Brancher le lecteur USB avec le package d’approvisionnement pendant la première heure d’interaction d’OOBE
1. Lorsque l’appareil est prêt à être approvisionné, il ouvre automatiquement l’invite avec la page de configuration. 

Remarque : si un lecteur USB reste branché pendant le démarrage de l’appareil, OOBE énumère les dispositifs de stockage USB existants, ainsi que des éléments supplémentaires qui sont connectés.

pour plus d’informations sur l’application de packages de provisionnement au cours d’OOBE, consultez la documentation relative à l' [approvisionnement de HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) .

pour plus d’informations sur l' [approvisionnement automatique à partir d’un lecteur USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) , consultez la documentation relative à l’approvisionnement de HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmer automatiquement les packages de provisionnement dans OOBE
- Processus automatisé autorisant moins d’intervention de l’utilisateur, lorsque la page package d’approvisionnement s’affiche, tous les packages répertoriés sont automatiquement appliqués.

Lorsque l’écran principal de configuration s’affiche, OOBE compte 10 secondes avant de commencer à appliquer automatiquement tous les packages d’approvisionnement. Les utilisateurs peuvent toujours [confirmer ou annuler](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) pendant ces 10 secondes après avoir vérifié les packages attendus.

### <a name="automatic-provisioning-without-using-ui"></a>Approvisionnement automatique sans interface utilisateur
- Processus automatiques combinés pour réduire les interactions de l’appareil pour l’approvisionnement. 

en associant le lancement automatique de l’approvisionnement à partir des périphériques USB et la confirmation automatique des packages de provisionnement, un utilisateur peut approvisionner HoloLens 2 appareils automatiquement sans utiliser l’interface utilisateur de l’appareil, ni même porter l’appareil. Vous pouvez continuer à utiliser le même lecteur USB et le même package de configuration pour plusieurs appareils. Cela est utile pour déployer plusieurs appareils à la fois dans la même zone. 

1. [créez un Package d’approvisionnement](hololens-provisioning.md) à l’aide de [Windows concepteur de Configuration](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiez le package sur un lecteur de stockage USB.
1. [flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) sur [19041,1361 ou une version plus récente](https://aka.ms/hololens2previewdownload). 
1. Lorsque l' [Assistant de récupération avancée](https://www.microsoft.com/store/productId/9P74Z35SFRS8) a terminé le clignotement de votre appareil, débranchez le câble USB-C. 
1. Branchez votre lecteur USB sur l’appareil.
1. lorsque l’appareil HoloLens 2 démarre dans OOBE, il détecte automatiquement le package d’approvisionnement sur le lecteur USB et lance la page de configuration.
1. Après 10 secondes, l’appareil applique automatiquement le package d’approvisionnement. 

Votre appareil est maintenant configuré et [affiche l’écran de réussite de l’approvisionnement](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Utilisation de AutoPilot avec Wi-Fi connexion
- Suppression de la nécessité d’utiliser des adaptateurs USB-C pour réduire les besoins en matériel, en activant AutoPilot pour fonctionner sur Wi-Fi appareils connectés.

désormais, pendant l’oobe, une fois que vous êtes connecté HoloLens 2 avec Wi-Fi, OOBE recherche un profil autopilot pour l’appareil. S’il en trouve un, il sera utilisé pour terminer le reste du processus d’inscription et de jonction AAD. En d’autres termes, l’utilisation d’Ethernet vers USB-C ou Wi-Fi vers l’adaptateur USB-C n’est plus une exigence, mais elle continue de fonctionner si elle est fournie au début d’OOBE. en savoir plus sur [autopilot pour les appareils HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP Tenantlockdown et Autopilot
- Conserve les appareils sur le locataire de l’organisation en les verrouillant sur le locataire, même via la réinitialisation ou le redémarrage de l’appareil. Avec une sécurité accrue en désaccordant la création de comptes dans via la configuration. 

les appareils HoloLens 2 prennent désormais en charge le CSP TenantLockdown à partir de [Windows version holographique 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) le fournisseur CSP permet à HoloLens 2 d’être lié à l’inscription MDM à l’aide d’autopilot uniquement. une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur la valeur true ou false (initialement défini) sur HoloLens 2, cette valeur reste sur l’appareil malgré le réclignotement, les mises à jour du système d’exploitation, etc. 

une fois que le nœud RequireNetworkInOOBE du csp TenantLockdown a la valeur true sur HoloLens 2, OOBE attend indéfiniment que le profil autopilot soit téléchargé et appliqué avec succès après une connexion réseau. 

une fois que le nœud RequireNetworkInOOBE du csp TenantLockdown a la valeur true sur HoloLens 2, les opérations suivantes ne sont pas autorisées dans OOBE : 
- Création d’un utilisateur local à l’aide de l’approvisionnement du Runtime 
- Exécution d’une opération de jointure Azure AD via l’approvisionnement du Runtime 
- Sélection du propriétaire de l’appareil dans l’expérience OOBE 

#### <a name="how-to-set-this-using-intune"></a>Comment définir cette configuration à l’aide d’Intune ? 
1. Créez un profil de configuration d’appareil URI OMA personnalisé et spécifiez true pour le nœud RequireNetworkInOOBE comme indiqué ci-dessous.
La valeur OMA-URI doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Définition du verrouillage utilisateurs locataires via OMA-URI](images/hololens-tenant-lockdown.png)

1. Créez un groupe et affectez le profil de configuration de l’appareil à ce groupe d’appareils. 

1. rendez le membre de l’appareil HoloLens 2 du groupe créé à l’étape précédente et déclenchez la synchronisation.  

Vérifiez dans le portail Intune que la configuration de l’appareil a été appliquée avec succès. une fois que la configuration de l’appareil s’applique correctement sur l’appareil HoloLens 2, les effets de TenantLockdown sont actifs.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>comment faire pour déTenantLockdownr RequireNetworkInOOBE d’un HoloLens 2 à l’aide d’Intune ? 
1. supprimez le HoloLens 2 du groupe d’appareils sur lequel la configuration d’appareil créée ci-dessus a été précédemment affectée. 

1. Créez un profil de configuration d’appareil basé sur un URI OMA personnalisé et spécifiez false pour RequireNetworkInOOBE comme indiqué ci-dessous. La valeur OMA-URI doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de la définition de RequireNetworkInOOBE sur false via un URI OMA dans Intune](images/hololens-tenant-lockdown-false.png)

1. Créez un groupe et affectez le profil de configuration de l’appareil à ce groupe d’appareils. 

1. rendez le membre de l’appareil HoloLens 2 du groupe créé à l’étape précédente et déclenchez la synchronisation.

Vérifiez dans le portail Intune que la configuration de l’appareil a été appliquée avec succès. une fois que la configuration de l’appareil s’applique correctement sur l’appareil HoloLens 2, les effets de TenantLockdown sont inactifs. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>que se passe-t-il lors de l’OOBE, si le profil autopilot n’est pas affecté sur une HoloLens une fois que TenantLockdown a été défini sur true ? 
OOBE attend indéfiniment que le chargement du profil AutoPilot et la boîte de dialogue suivante s’affichent. Pour supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit avec son locataire d’origine à l’aide de AutoPilot uniquement et RequireNetworkInOOBE doit être désactivé comme décrit dans l’étape précédente avant que les restrictions introduites par le CSP TenantLockdown soient supprimées. 

![Vue dans le périphérique pour lorsque la stratégie est appliquée sur l’appareil.](images/hololens-autopilot-lockdown.png)

Vous pouvez désormais trouver ces informations en même temps que le reste du pilote AutoPilot sous [TENANTLOCKDOWN CSP et AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Accès global affecté – mode plein écran
- Réduction de la gestion des identités pour les bornes, en activant la nouvelle méthode Kiosk qui applique le mode plein écran au niveau du système.

cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode plein écran de plusieurs applications, applicable au niveau du système, n’a aucune affinité avec l’identité du système et s’applique à tous les utilisateurs qui se connectent à l’appareil. en savoir plus sur cette nouvelle fonctionnalité en détail dans la [HoloLens borne d’accès assignée globale](hololens-global-assigned-access-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Lancement automatique d’une application en mode plein écran à plusieurs applications 
- Expérience ciblée avec le lancement automatique d’applications, ce qui améliore davantage l’interface utilisateur et les sélections d’applications choisies pour les expériences en mode plein écran.

S’applique uniquement au mode plein écran à plusieurs applications et seule une application peut être désignée pour être lancée automatiquement à l’aide de l’attribut en surbrillance ci-dessous dans la configuration d’accès affectée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifications du comportement du mode plein écran pour la gestion des défaillances
- Mode plein écran sécurisé en éliminant les applications disponibles en cas de défaillance du mode plein écran. 

plus haut en cas de défaillances lors de l’application du mode plein écran, HoloLens utilisé pour afficher toutes les applications dans le menu démarrer. maintenant, dans Windows holographique version 20H2 en cas d’échec, aucune application ne sera affichée dans le menu démarrer comme suit : 

![Image du mode plein écran à présent en cas d’échec.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Directives
- options de gestion des appareils spécifiques à HoloLens créées pour la gestion de l’appareil. 

de nouvelles stratégies de réalité mixte ont été créées pour HoloLens 2 appareils sur Windows version holographique 20H2. Les nouveaux paramètres contrôlables incluent : définition de la luminosité, définition du volume, désactivation de l’enregistrement audio dans les captures de réalité mixte, définition du moment où les diagnostics peuvent être collectés et mise en cache de l’appartenance au groupe AAD.  

| nouvelle stratégie de HoloLens                                | Description                                                                               | Remarques                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permet de désactiver les boutons de luminosité afin que le fait de cliquer dessus ne change pas de luminosité.       | 1 Oui, 0 non (par défaut)                                                |
| MixedReality\VolumeButtonDisabled                  | Permet de désactiver les boutons de volume afin que le fait d’appuyer sur le volume ne change pas.               | 1 Oui, 0 non (par défaut)                                                |
| MixedReality\MicrophoneDisabled                    | Désactive le microphone, de sorte qu’aucun enregistrement audio n’est possible sur HoloLens 2.                      | 1 Oui, 0 non (par défaut)                                                |
| MixedReality\FallbackDiagnostics                   | Contrôle le comportement de lorsque les journaux de diagnostic peuvent être collectés.                               | 0 désactivé, 1 activé pour les propriétaires d’appareils, 2 activé pour tout (par défaut) |
| MixedReality\HeadTrackingMode                      | Réservé pour un usage futur.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Contrôle le nombre de jours pendant lesquels le cache d’appartenance au groupe Azure AD est utilisé pour les groupes de Azure AD de ciblage Kiosk. | Voir ci-dessous.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Appartenance au groupe de Azure AD de cache pour une borne en mode hors connexion
- Activez les bornes hors connexion à utiliser avec les groupes AAD pendant jusqu’à 60 jours.

Cette stratégie détermine le nombre de jours pendant lesquels le cache d’appartenance au groupe Azure AD peut être utilisé pour les configurations d’accès affectées ciblant les groupes de Azure AD pour l’utilisateur connecté. Une fois que cette valeur de stratégie est définie sur une valeur supérieure à 0, alors le cache est utilisé dans le cas contraire.  

Nom : AADGroupMembershipCacheValidityInDays URI value :./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 jours  
Max-60 jours 

Étapes pour utiliser cette stratégie correctement : 
1. créez un profil de configuration d’appareil pour le ciblage de bornes Azure AD des groupes et affectez-le à HoloLens appareil (s). 
1. créez une configuration d’appareil basée sur un URI OMA personnalisée qui définit cette valeur de stratégie sur le nombre de jours souhaité (> 0) et attribuez-la à HoloLens appareil (s). 
    1. La valeur de l’URI doit être entrée dans la zone de texte OMA-URI en tant que./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. La valeur peut être comprise entre min/maximum autorisé.
1. inscrivez HoloLens appareils et vérifiez que les deux configurations sont appliquées à l’appareil. 
1. Autoriser Azure AD utilisateur 1 à se connecter quand Internet est disponible, une fois que l’utilisateur se connecte et que Azure AD appartenance au groupe est confirmée avec succès, le cache est créé. 
1. désormais, Azure AD utilisateur 1 peut mettre HoloLens hors connexion et l’utiliser pour le mode plein écran tant que la valeur de la stratégie autorise un nombre de jours de X. 
1. Les étapes 4 et 5 peuvent être répétées pour tout autre Azure AD l’utilisateur N. point clé ici : tout utilisateur Azure AD doit se connecter à l’appareil à l’aide d’Internet, de sorte qu’au moins une fois, nous pouvons déterminer qu’ils sont membres du groupe Azure AD auquel la configuration de kiosque est destinée. 
 
> [!NOTE]
> Tant que l’étape 4 n’est pas exécutée pour un Azure AD utilisateur rencontre un comportement d’échec mentionné dans les environnements « déconnectés ». 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nouvelles stratégies de restriction d’appareil pour HoloLens 2
- Permet aux utilisateurs de gérer des stratégies de gestion d’appareils spécifiques, telles que le blocage de l’ajout ou de la suppression de packages de provisionnement.

stratégies récemment activées qui permettent d’obtenir davantage d’options de gestion des appareils HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Ces deux nouvelles stratégies pour AllowAddProvisioningPackage et AllowRemoveProvisioningPackage sont ajoutées à nos restrictions d' [appareil courantes](hololens-common-device-restrictions.md).

> [!NOTE]
> en ce qui concerne [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), HoloLens prend en charge uniquement la configuration./Vendor/MSFT/RemoteLock/Lock. Les configurations associées à un code confidentiel, telles que la réinitialisation et la récupération, ne sont pas prises en charge.

### <a name="new-power-policies-for-hololens-2"></a>Nouvelles stratégies d’alimentation pour HoloLens 2
- plus d’options pour l’HoloLens de mise en veille ou de verrouillage par le biais de stratégies d’alimentation. 

Ces stratégies permettent aux administrateurs de contrôler les États d’alimentation, tels que le délai d’inactivité. Pour en savoir plus sur chaque stratégie individuelle, cliquez sur le lien correspondant à cette stratégie.

|     Lien vers la documentation sur les stratégies                |     Remarques                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     exemple de valeur à utiliser dans Windows concepteur de Configuration, c.-à-d.,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     exemple de valeur à utiliser dans Windows concepteur de Configuration, c.-à-d.,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  exemple de valeur à utiliser dans Windows concepteur de Configuration, par exemple 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     exemple de valeur à utiliser dans Windows concepteur de Configuration, par exemple 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     exemple de valeur à utiliser dans Windows concepteur de Configuration, c.-à-d.,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     exemple de valeur à utiliser dans Windows concepteur de Configuration, c.-à-d.,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Ces deux nouvelles stratégies pour DisplayOffTimeoutOnBattery et DisplayOffTimeoutPluggedIn sont ajoutées à nos restrictions d' [appareil courantes](hololens-common-device-restrictions.md).

> [!NOTE]
> pour une expérience cohérente sur HoloLens 2, assurez-vous que les valeurs pour DisplayOffTimeoutOnBattery et StandbyTimeoutOnBattery sont définies sur la même valeur. Il en va de même pour DisplayOffTimeoutPluggedIn et StandbyTimeoutPluggedIn. Pour plus d’informations sur la mise en veille moderne, reportez-vous à l' [affichage, à la mise en veille et](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) à la mise en veille prolongée.

### <a name="newly-enabled-update-policies-for-hololens"></a>Stratégies de mise à jour récemment activées pour HoloLens
- Plus d’options pour le moment où les mises à jour sont installées ou la désactivation du bouton suspendre les mises à jour pour garantir les mises à jour.

ces stratégies de mise à jour sont désormais activées sur les appareils HoloLens 2 :
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Mettre à jour/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

pour plus d’informations sur ces stratégies de mise à jour et leur utilisation pour les appareils HoloLens, consultez [gérer les mises à jour HoloLens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>activation de la visibilité de page Paramètres pour HoloLens 2
- contrôle accru de l’interface utilisateur dans l’application Paramètres, qui peut être confondu pour afficher une sélection limitée de pages.

nous avons maintenant activé une stratégie qui permet aux administrateurs informatiques d’empêcher des pages spécifiques du système Paramètres application d’être visibles ou accessibles, ou de le faire pour toutes les pages, à l’exception de celles spécifiées. Pour savoir comment personnaliser entièrement cette fonctionnalité, cliquez sur le lien ci-dessous.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

pour connaître les paramètres de page que vous pouvez personnaliser sur HoloLens 2, consultez la [page Paramètres uri](settings-uri-list.md). 
 
![capture d’écran des heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Mode de recherche
en Mode de recherche, le HoloLens 2 devient un outil puissant pour la recherche de vision par ordinateur. par rapport aux éditions précédentes, le Mode de recherche pour HoloLens 2 présente les avantages suivants :
-   en plus des capteurs exposés en Mode de recherche HoloLens (1er génération), nous fournissons maintenant un accès au capteur IMU, notamment un accéléromètre, un gyroscope et un magnétomètre.
-   HoloLens 2 fournit de nouvelles fonctionnalités qui peuvent être utilisées avec le Mode de recherche. En particulier, l’accès aux API articulées de suivi des mains et de suivi des yeux qui peuvent fournir un ensemble d’expériences plus riche.

les chercheurs ont désormais la possibilité d’activer le Mode de recherche sur leurs appareils HoloLens pour accéder à tous ces flux de capteurs d’images brutes externes. le Mode de recherche pour HoloLens 2 permet également d’accéder aux lectures accéléromètre, gyroscope et magnétomètre. Pour protéger la confidentialité des utilisateurs, les images de caméra de suivi oculaire brut ne sont pas disponibles par le biais du mode de recherche, mais la direction du point de vue des yeux est disponible via les API existantes.

Pour plus d’informations techniques, consultez la [documentation du mode de recherche](https://docs.microsoft.com/windows/mixed-reality/research-mode) .

### <a name="recording-length-increased"></a>Durée d’enregistrement augmentée
En raison des commentaires des clients, nous avons augmenté la durée d’enregistrement des [captures de réalité mixte](holographic-photos-and-videos.md). Les captures de réalité mixte ne seront plus limitées à 5 minutes par défaut, mais elles calculeront la longueur maximale d’enregistrement en fonction de l’espace disque disponible. L’appareil estime la durée maximale d’enregistrement vidéo en fonction de l’espace disque disponible, jusqu’à 80% de l’espace disque total.

> [!NOTE]
> le HoloLens utilise la longueur d’enregistrement vidéo par défaut (5 minutes) si l’un des éléments suivants se produit :
> - La durée d’enregistrement maximale estimée est inférieure à la valeur par défaut de 5 minutes.
> - L’espace disque disponible est inférieur à 20% de l’espace disque total.

Vous trouverez la configuration complète requise dans notre documentation sur les [photos et vidéos holographiques](holographic-photos-and-videos.md#maximum-recording-length) . 

### <a name="improvements-and-fixes-in-the-update"></a>Améliorations et correctifs de la mise à jour :
- D’autres écrans dans OOBE sont désormais en mode sombre.
- Pour plus d’informations, consultez la déclaration de confidentialité la plus récente en ligne.
- A résolu un problème où les utilisateurs ne pouvaient pas approvisionner des profils VPN par le biais de packages d’approvisionnement.
- Résolution d’un problème de configuration du proxy pour la connexion VPN.
- Mise à jour de la stratégie pour désactiver l’énumération des fonctions USB via MDM pour NCM pour AllowUsbConnection.
- a résolu un problème qui empêchait un appareil HoloLens de s’apparaître dans l’explorateur de fichiers via le protocole MTP (Media Transfer Protocol) lorsque l’appareil est configuré en tant que [kiosque à une seule application](hololens-kiosk.md). Notez que le MTP (et la connexion USB en général) peuvent toujours être désactivés à l’aide de la stratégie [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- correction d’un problème où les icônes du menu Démarrer ont été mises à l’échelle correctement en mode plein écran.
- Résolution d’un problème lié à la mise en cache HTTP interférant avec le mode plein écran ciblant les groupes de Azure AD.
- Résolution d’un problème où les utilisateurs ne pouvaient pas utiliser le bouton de paire après l’activation du mode développeur avec les packages d’approvisionnement, sauf s’ils ont désactivé et réactivé le mode développeur.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographique, version 1903-mise à jour du 2020 du 1er novembre
- Build 18362,1085

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à essayer notre version de la dernière version de fonctionnalité Windows holographique, version 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographique, version 2004-mise à jour d’octobre 2020
- Build 19041,1124
 
Améliorations et correctifs de la mise à jour :

- Suppression d’une vérification inutile qui provoquait une erreur du système d’exécution.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographique, version 1903-mise à jour d’octobre 2020
- Build 18362,1081

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières builds pour Windows holographique, version 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographique, version 2004-mise à jour de septembre 2020
- Build 19041,1117

Améliorations et correctifs de la mise à jour :

- résout un problème qui empêchait Visual Studio de déboguer une application quand SupportsMultipleInstances = "true" est présent dans appxmanifest.
- Cette version comprend le correctif de détection du proxy NCSI pour résoudre les échecs de détection Internet sur le proxy réseau. NCSI peut utiliser un proxy d’ordinateur et un proxy par profil pour la détection de la connectivité Internet. Le proxy par utilisateur sera pris en charge par NCSI dans la prochaine version.
- sur la plupart des appareils Windows Mixed Reality, le vecteur de direction vers l’avant est parallèle au sol lorsque la tête de l’utilisateur se trouve dans une position neutre à l’avenir. toutefois, les versions antérieures de HoloLens 2 alignées sur le vecteur de façon à ce qu’elle soit perpendiculaire aux panneaux d’affichage, ce qui est incliné vers le bas à quelques degrés par rapport à l’orientation idéale. les versions plus récentes de HoloLens 2 ont corrigé cela pour garantir la cohérence sémantique entre les différents facteurs de forme.
- Amélioration de la robustesse du suivi de la main qui entraîne moins de pertes de suivi dans des scénarios spécifiques.
- Cette version contient un correctif pour améliorer la qualité des horodateurs audio, qui peut avoir contribué à des problèmes de capture vidéo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographique, version 1903-mise à jour de septembre 2020
- Build 18362,1079

Améliorations et correctifs de la mise à jour :

- sur la plupart des appareils Windows Mixed Reality, le vecteur de direction vers l’avant est parallèle au sol lorsque la tête de l’utilisateur se trouve dans une position neutre à l’avenir. toutefois, les versions antérieures de HoloLens 2 alignées sur le vecteur de façon à ce qu’elle soit perpendiculaire aux panneaux d’affichage, ce qui est incliné vers le bas à quelques degrés par rapport à l’orientation idéale. les versions plus récentes de HoloLens 2 ont corrigé cela pour garantir la cohérence sémantique entre les différents facteurs de forme.
- Amélioration de la robustesse du suivi de la main qui entraîne moins de pertes de suivi dans des scénarios spécifiques.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographique, version 2004-mise à jour du 2020 août
- Build 19041,1113

Améliorations et correctifs de la mise à jour :

- Paramètres application ne suivra plus l’utilisateur de l’inscription par Iris ou de l’étalonnage du suivi oculaire.
- Correction d’un bogue dans lequel l’application d’un package d’approvisionnement au cours d’OOBE qui renomme l’appareil et effectue d’autres actions (telles que la connexion à un réseau) ne parviendrait pas à effectuer les autres actions après le redémarrage de l’appareil en raison d’un changement de nom.
- Modèle de couleurs modifié des flux d’installation initiaux des appareils pour améliorer la qualité visuelle.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographique, version 1903-mise à jour du 2020 août
- Build 18362,1074

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières builds pour Windows holographique, version 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographique, version 2004-mise à jour de juillet 2020
- Build 19041,1109

Améliorations et correctifs de la mise à jour :

- Les développeurs peuvent désormais choisir d’activer ou de désactiver le portail des appareils pour qu’ils requièrent une connexion sécurisée.
- Fiabilité améliorée pour les lancements d’applications après les mises à jour du système d’exploitation.
- Modification de la luminosité de la boîte de réception par défaut à 100 pour cent.
- a traité un problème concernant le transfert https pour le Windows le portail des appareils sur HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographique, version 1903-mise à jour de juillet 2020
- Build 18362,1071

Améliorations et correctifs de la mise à jour :

- Correction d’un problème qui pouvait entraîner la disparition des hologrammes dans les applications Unity lors de la perte ou de la réobtention du suivi.
- résolution d’un problème qui entraînait le blocage des applications HoloLens exclusives sur le shell lors de l’utilisation de l’HoloLens Emulator avec l’accélération matérielle sur certains appareils.
- a traité un problème concernant le transfert https pour le Windows le portail des appareils sur HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographique, version 2004-mise à jour du 2020 du 1er juin
- Build 19041,1106

Améliorations et correctifs de la mise à jour :

- Les enregistreurs MRC personnalisés ont désormais de nouvelles valeurs par défaut pour certaines propriétés s’ils ne sont pas spécifiés.
  - Sur l' *effet de la vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l' *effet audio MRC*:
    - LoopbackGain (la valeur actuelle « Gain Audio de l’application » sur la page de Capture de la réalité mixte dans Windows portail des appareils)
    - MicrophoneGain (la valeur actuelle « Gain Audio Mic » sur la page de Capture de la réalité mixte dans Windows portail des appareils)
- Correction d’un bogue pour améliorer la qualité audio dans les scénarios de capture de réalité mixte. Plus précisément, ce correctif doit éliminer les problèmes audio dans l’enregistrement lors de l’affichage du menu **Démarrer** .
- Amélioration de la stabilité des hologrammes dans les vidéos enregistrées.
- Résolution d’un problème où la capture de la réalité mixte n’a pas pu enregistrer la vidéo après que l’appareil a quitté l’état de veille pendant plusieurs jours.
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity. Ce comportement permet d’éviter un problème qui provoquait l’interruption de certaines applications lorsque le visière a été retournée, même si le paramètre « exécuter en arrière-plan » a été activé. L’API est maintenant activée pour Unity 2018.4.18 et versions ultérieures et 2019.3.4 et versions ultérieures.
- Quand vous accédez au portail des appareils via une connexion Wi-Fi, un navigateur Web peut empêcher l’accès à en raison d’un certificat non valide. Le navigateur peut signaler une erreur telle que « ERR_SSL_PROTOCOL_ERROR », même si le certificat de l’appareil a été approuvé précédemment. Dans ce cas, vous ne pouvez pas progresser vers le portail de l’appareil, car il n’est pas possible d’ignorer les avertissements de sécurité. Cette mise à jour a résolu le problème. Si le certificat de l’appareil a été précédemment téléchargé et approuvé sur un PC pour supprimer les avertissements de sécurité du navigateur et que l’erreur SSL se produit, le nouveau certificat doit être téléchargé et approuvé pour résoudre les avertissements de sécurité du navigateur.
- Activation de la possibilité de créer un package d’approvisionnement d’exécution qui peut installer une application à l’aide de packages MSIX.
- ajout d’un paramètre dans **Paramètres**  >    >  **Hologrammes** système qui permet aux utilisateurs de supprimer automatiquement tous les hologrammes de la réalité mixte lorsque l’appareil s’arrête.
- correction d’un problème qui provoquait HoloLens applications qui modifient leur format de pixel pour restituer le noir dans l’émulateur HoloLens.
- Correction d’un bogue qui provoquait un incident lors de la connexion à iris.
- Correction d’un problème concernant les téléchargements de magasins répétés pour les applications déjà en cours.
- correction d’un bogue pour empêcher les applications immersives de s’ouvrir Microsoft Edge à plusieurs reprises.
- correction d’un problème avec les lancements de l’application Photos lors des démarrages initiaux après la mise à jour à partir de la version 1903.
- Amélioration des performances et de la fiabilité.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographique, version 1903-mise à jour du 2020 du 1er juin
- Build 18362,1064

Améliorations et correctifs de la mise à jour :

- Les enregistreurs MRC personnalisés ont de nouvelles valeurs par défaut pour certaines propriétés s’ils ne sont pas spécifiés.
  - Sur l' *effet de la vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l' *effet audio MRC*:
    - LoopbackGain (la valeur actuelle « Gain Audio de l’application » sur la page de Capture de la réalité mixte dans Windows portail des appareils)
    - MicrophoneGain (la valeur actuelle « Gain Audio Mic » sur la page de Capture de la réalité mixte dans Windows portail des appareils)
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity. Ce comportement évite un problème qui provoque l’interruption de certaines applications lorsque le visière est retournée, même si le paramètre à exécuter en arrière-plan est activé. L’API est maintenant activée pour Unity 2018.4.18 et versions ultérieures, et 2019.3.4 et versions ultérieures.
- correction d’un problème qui provoquait HoloLens applications qui modifient leur format de pixel pour restituer le noir dans le Emulator HoloLens.
- correction d’un problème concernant les lancements de l’application Photos dans les démarrages initiaux après la mise à jour à partir de la version 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographique, version 2004  
- Build-19041,1103

la mise à jour logicielle de mai 2020 pour HoloLens 2, *Windows holographique, version 2004* , offre un grand nombre de nouvelles fonctionnalités passionnantes, telles que la prise en charge de Windows autopilot, le mode sombre de l’application, la prise en charge USB Ethernet pour les points d’accès 5 5g/LTE, et bien plus encore. pour effectuer une mise à jour vers la dernière version, ouvrez l’application **Paramètres**   , accédez à  **update & Security**, puis sélectionnez le bouton  **rechercher les mises à jour**   . 

|             Fonctionnalité                              |          Description                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          préconfigurer et configurer en toute transparence de nouveaux appareils pour la production à l’aide d’Windows autopilot                 |
|       Support « Rex 2 »                             |          Prise en charge des clés de sécurité FIDO2 pour activer l’authentification rapide et sécurisée pour les appareils partagés            |
|       Approvisionnement amélioré                      |          Appliquez en toute transparence un package d’approvisionnement à partir d’un lecteur USB à votre HoloLens                              |
|       État de l’installation de l’application                 |          vérifier l’état d’installation dans le Paramètres application pour les applications ont été poussées vers HoloLens 2 via MDM               |
|       Fournisseurs de services de configuration (CSP)   |          Ajout de nouveaux fournisseurs de service de configuration pour améliorer les fonctionnalités de contrôle d’administration                 |
|       Support USB 5G/LTE                       |          La fonctionnalité Ethernet USB étendue active la prise en charge de 5G/LTE                                    |
|       Mode d’application sombre                              |          Mode d’application sombre disponible pour les applications qui prennent en charge les modes sombre et clair, améliorant ainsi l’expérience d’affichage        |
|       Commandes vocales                             |          prise en charge d’autres commandes système vocales pour contrôler HoloLens mains libres                           |
|       Améliorations du suivi de la main                 |          Les améliorations du suivi de la main rendent les boutons et les interactions 2D ardoise plus précis                        |
|       Améliorations et correctifs de qualité                 |          Diverses améliorations des performances et de la fiabilité du système sur l’ensemble de la plateforme                            |

### <a name="support-for-windows-autopilot"></a>prise en charge de Windows autopilot

Windows autopilot pour HoloLens 2 permet au canal de vente de l’appareil de préinscrire des HoloLens dans votre locataire Intune. Lorsque les appareils arrivent, ils sont prêts à être déployés automatiquement en tant qu’appareils partagés sous votre locataire. Pour tirer parti du déploiement automatique, l’appareil doit se connecter à un réseau au premier écran de l’installation à l’aide d’une connexion USB-C à Ethernet.

Une fois qu’un utilisateur a démarré le processus de déploiement automatique AutoPilot, le processus effectue les étapes suivantes :

1. Joignez l’appareil à Azure Active Directory (Azure AD).
1. utilisez Azure AD pour inscrire l’appareil dans Microsoft Intune (ou un autre service MDM).
1. Téléchargez les stratégies ciblées par l’appareil, les certificats et les profils de mise en réseau.
1. Approvisionnez l’appareil.
1. Présentez l’écran de connexion à l’utilisateur.

pour plus d’informations, consultez le [guide d’évaluation Windows autopilot pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Contactez votre responsable de compte pour participer à la préversion de la version préliminaire AutoPilot. Les appareils AutoPilot-prêts seront bientôt expédiés.*

### <a name="fido2-security-key-support"></a>Prise en charge des clés de sécurité FIDO2

certains utilisateurs partagent un appareil HoloLens avec d’autres personnes dans un environnement professionnel ou scolaire. Il est donc important que les utilisateurs puissent facilement sans taper des noms d’utilisateur et des mots de passe longs. l’identité rapide en ligne (rex) permet à toute personne de votre organisation (Azure AD locataire) de se connecter en toute transparence à HoloLens sans entrer de nom d’utilisateur ou de mot de passe.

Les clés de sécurité FIDO2 sont une méthode d’authentification sans mot de passe basée sur des normes, qui peut se présenter sous n’importe quel facteur de forme. Le Rex est une norme ouverte pour l’authentification par mot de passe. Elle permet aux utilisateurs et aux organisations de se connecter à leurs ressources sans nom d’utilisateur ou mot de passe. Au lieu de cela, ils utilisent une clé de sécurité externe ou une clé de plateforme intégrée à un appareil.

Pour commencer, consultez Activer la connexion à la [clé de sécurité avec mot de passe](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Amélioration de l’inscription MDM via le package de provisionnement

les packages d’approvisionnement vous permettent de définir HoloLens configuration par le biais d’un fichier de configuration plutôt que par le biais de l’expérience HoloLens prête à l’emploi. auparavant, les packages d’approvisionnement devaient être copiés dans la mémoire interne du HoloLens. désormais, ils peuvent se trouver sur un lecteur USB afin d’être plus faciles à réutiliser sur plusieurs appareils HoloLens, et vous pouvez approvisionner des appareils en parallèle. Les packages d’approvisionnement prennent désormais également en charge un champ à inscrire dans la gestion des appareils. il n’y a donc pas de configuration manuelle après l’approvisionnement.

Pour essayer :

1. téléchargez la dernière version de Windows Configuration Designer à partir du Windows store sur votre PC.
1. sélectionnez **approvisionner HoloLens appareils**  >  **configurer des appareils HoloLens 2**.
2. Générez votre profil de configuration. Copiez ensuite tous les fichiers qui ont été créés sur un périphérique de stockage USB-C.
3. Branchez l’appareil USB-C dans un HoloLens actualisé. Appuyez ensuite sur les boutons de réduction de l’alimentation du **volume**  +   pour appliquer votre package d’approvisionnement.

### <a name="line-of-business-application-install-status"></a>État de l’installation des applications métier

Le déploiement et la gestion d’applications MDM pour les applications métier sont essentiels pour HoloLens. Les administrateurs et les utilisateurs doivent afficher l’état d’installation des applications pour l’audit et le diagnostic. dans cette version, nous avons ajouté plus de détails dans **Paramètres**  >  **comptes**  >  **accès professionnel ou scolaire**,  >  cliquez sur les informations de **votre compte**  >  .

### <a name="additional-csps-and-policies"></a>Fournisseurs de services de chiffrement et stratégies supplémentaires

Un [fournisseur de services de configuration (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) est une interface permettant de lire, de définir, de modifier ou de supprimer des paramètres de configuration sur un appareil. dans cette version, nous ajoutons la prise en charge d’un plus grand nombre de stratégies pour augmenter les administrateurs de contrôle sur les appareils HoloLens déployés. pour obtenir la liste des fournisseurs de services de chiffrement pris en charge par HoloLens, consultez [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Nouveautés dans cette version :

**Fournisseur CSP Policy** 

le fournisseur de services de configuration de stratégie permet à l’entreprise de configurer des stratégies sur les appareils Windows. dans cette version, nous avons ajouté de nouvelles stratégies pour HoloLens, qui sont répertoriées ici. Pour plus d’informations, consultez les [fournisseurs de services de stratégie pris en charge par HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**CSP NetworkQoSPolicy**

Le fournisseur de services de configuration NetworkQoSPolicy crée des stratégies de qualité de service (QoS) réseau. Une stratégie de QoS effectue un ensemble d’actions sur le trafic réseau en fonction d’un ensemble de conditions de correspondance. Pour plus d’informations, consultez [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Prise en charge Ethernet USB étendue pour les appareils attachés 5G/LTE

la prise en charge a été ajoutée pour activer certains périphériques haut débit mobile, tels que les téléphones 5g/LTE et les zones réactives Wi-Fi, lorsqu’ils sont attachés au HoloLens 2 via USB. Ces appareils sont désormais affichés dans **paramètres réseau** comme une autre connexion Ethernet. (Les périphériques haut débit mobile qui requièrent un pilote externe ne sont pas pris en charge.) Cette fonctionnalité permet des connexions à bande passante élevée lorsque Wi-Fi n’est pas disponible et que Wi-Fi la connexion n’est pas suffisamment performante. pour en savoir plus sur les périphériques usb pris en charge, consultez [Connecter pour Bluetooth et les périphériques usb-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Améliorations du suivi de la main

Cette version comprend plusieurs améliorations de suivi de la main :

- **Point de stabilité de pose :** Le système résiste maintenant au doigt de l’index lorsqu’il est bloqués par le Palm. Cette modification améliore la précision quand vous appuyez sur les boutons, tapez, faites défiler le contenu et bien plus encore. 
- **Réduction des pressions d’air accidentelles :** Nous avons amélioré la détection du mouvement d’appui sur l’air. Il y a maintenant moins d’activations accidentelles dans plusieurs scénarios courants, par exemple lorsque vous déposez vos mains sur vos côtés.
- **Fiabilité du changement d’utilisateur :** Le système est maintenant plus rapide et plus fiable lors de la mise à jour de la taille de la main lorsque vous partagez un appareil.
- **Réduction du vol de la main :** Nous avons amélioré la gestion des cas où il y a plus de deux mains en vue des capteurs. Si plusieurs personnes travaillent à proximité, il y a maintenant une plus grande probabilité que la main « passe » de l’utilisateur à la main d’une autre personne dans la scène.
- **Fiabilité du système :** Correction d’un problème qui entraînait l’arrêt du suivi de la main lorsque l’appareil est soumis à une charge élevée.

### <a name="dark-mode"></a>Mode sombre

de nombreuses applications Windows prennent désormais en charge les modes sombre et clair. HoloLens 2 utilisateurs peuvent choisir le mode par défaut pour les applications qui prennent en charge les deux. après la mise à jour, le mode d’application par défaut est « dark », mais vous pouvez facilement modifier ce paramètre : accédez à **Paramètres**  >    >  **couleurs** système  >  **choisissez votre mode d’application par défaut**. 

Ces applications « intégrées » prennent en charge le mode sombre : 

- Paramètres 
- Microsoft Store 
- Messagerie 
- Calendrier 
- Explorateur de fichiers 
- Hub de commentaires 
- OneDrive 
- Photo 
- Visionneuse 3D 
- Films et TV 

![Fenêtres en mode sombre en mosaïque](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Commandes vocales du système

Vous pouvez désormais utiliser des commandes vocales avec n’importe quelle application sur l’appareil. Pour plus d’informations, consultez [utiliser votre voix pour travailler HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Voir également [les langues prises en charge pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>mises à jour de Cortana

l’application mise à jour s’intègre à Microsoft 365 pour vous aider à mieux travailler sur vos appareils (actuellement en US-English uniquement). sur HoloLens 2, Cortana ne prend plus en charge certaines commandes spécifiques à l’appareil, telles que l’ajustement du volume ou le redémarrage. Ces options sont désormais prises en charge par les nouvelles commandes du système vocal. en savoir plus sur la nouvelle application Cortana dans notre [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Améliorations et correctifs de qualité

Améliorations et correctifs également dans la mise à jour :  
- A introduit un système d’étalonnage d’affichage actif. Cette fonctionnalité améliore la stabilité et l’alignement des hologrammes. Ils restent désormais en place lorsque vous déplacez votre tête d’un côté à l’autre.
- correction d’un bogue dans lequel Wi-Fi la diffusion en continu vers HoloLens ont été interrompues régulièrement. Si une application indique qu’elle a besoin d’une diffusion en continu à faible latence, implémentez le correctif en appelant la [fonction SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correction d’un blocage d’appareil qui s’est produit pendant le streaming en mode de recherche.
- Correction d’un bogue dans lequel, dans certains cas, l’utilisateur approprié ne s’affichait pas sur l’écran de connexion lors de la reprise d’une session.
- résolution d’un problème où les utilisateurs ne pouvaient pas exporter les journaux MDM via **Paramètres**.
- Correction d’un problème où la précision du suivi oculaire juste après la configuration out-of-Box peut être inférieure à celle attendue.
- Correction d’un problème où le sous-système de suivi oculaire n’a pas pu initialiser ou effectuer un étalonnage dans certaines conditions.
- Correction d’un problème où l’étalonnage oculaire serait invité à fournir un utilisateur déjà étalonné.
- Résolution d’un problème qui entraînait le blocage d’un pilote pendant l’étalonnage oculaire.
- Correction d’un problème où les pressions répétées du bouton d’alimentation pouvaient entraîner un incident système et un blocage de l’interpréteur de commandes de 60 secondes.
- Stabilité améliorée pour les mémoires tampons de profondeur.
- Ajout d’un bouton de **partage** dans le hub de commentaires afin que les utilisateurs puissent partager plus facilement les commentaires.
- Correction d’un bogue où RoboRaid wan’t a été correctement installé.

### <a name="known-issues"></a>Problèmes connus

- Un problème avec la langue du système zh-CN empêche les commandes vocales d’effectuer une capture de réalité mixte ou d’afficher l’adresse IP de l’appareil.
- un problème nécessite que vous lançiez l’application Cortana après le démarrage de l’appareil pour utiliser l’activation vocale « bonjour Cortana ». si vous avez mis à jour à partir d’une build 18362, vous pouvez également voir une deuxième vignette d’application pour la version précédente de l’application Cortana qui ne fonctionne plus dans **Start**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographique, version 1903-mise à jour de mai 2020 
- Build 18362,1061

cette mise à jour de qualité mensuelle ne contient pas de modifications notables, car l’équipe travaillait sur la Windows holographique version 2004 peut être mise à jour, comme décrit précédemment.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographique, version 1903-mise à jour d’avril 2020
- Build 18362,1059

**Mode sombre pour les applications prises en charge** 

de nombreuses applications Windows prennent en charge les modes dark et light. HoloLens 2 clients peuvent désormais choisir le mode par défaut pour les applications qui prennent en charge les deux modèles de couleurs. en fonction des commentaires des clients, nous définissons le mode d’application par défaut sur « dark », mais vous pouvez facilement modifier ce paramètre à tout moment : accédez à **Paramètres > système > couleurs** pour trouver **« choisissez votre mode d’application par défaut ».**

Ces applications « intégrées » prennent en charge le mode sombre :
- Paramètres
- Microsoft Store
- Messagerie
- Calendrier
- Explorateur de fichiers
- Hub de commentaires
- OneDrive
- Photo
- Visionneuse 3D
- Films et TV

**Améliorations et correctifs également dans la mise à jour :** 
- Assurez-vous que les superpositions de Shell sont incluses dans les captures de réalité mixte.
- Les développeurs non réels peuvent désormais utiliser la page de vue 3D du portail de l’appareil pour tester et déboguer leurs applications.
- Stabilité améliorée des hologrammes dans la capture de réalité mixte lorsque l’algorithme *HolographicDepthReprojectionMethod DepthReprojection* est utilisé.
- Correction de l’erreur « classe d’API IStreamSocketListener WinRT non inscrite » sur les applications ARM 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographique, version 1903-mise à jour du 2020 du 1er mars 
- Build 18362,1056

Améliorations et correctifs de la mise à jour :

- Stabilité améliorée des hologrammes dans la capture de réalité mixte lorsque l’algorithme *Autoplanaire HolographicDepthReprojectionMethod* est utilisé.
- Assurez-vous que le système de coordonnées attaché à un échantillon Depth MF est cohérent avec la documentation publique.
- Amélioration de la productivité des développeurs en permettant aux clients de coller de grandes quantités de texte via le portail des appareils.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographique, version 1903-mise à jour du 2020 du 1er février 
- Build 18362,1053

Améliorations et correctifs de la mise à jour :

- Désactivation temporaire de l’API HolographicSpace. UserPresence pour les applications Unity. Cette modification permet d’éviter un problème qui provoquait l’interruption de certaines applications lorsque le visière a été retournée, même si le paramètre « exécuter en arrière-plan » a été activé.
- Correction d’un incident utilisation À domicile aléatoire provoqué par le suivi des mains, dans lequel l’utilisateur a remarqué un blocage de l’interface utilisateur, puis revient au shell après plusieurs secondes.
- Amélioration du suivi de la main. ainsi, lorsque vous surveillez votre index, la partie supérieure de ce doigt est moins susceptible de s’effectuer de façon inattendue.
- Fiabilité améliorée du suivi des têtes, du mappage spatial et d’autres runtimes.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographique, version 1903-mise à jour du 1er janvier 2020 
- Build 18362,1043
 
Améliorations et correctifs de la mise à jour :

- stabilité améliorée pour les applications exclusives lors de l’utilisation de l’émulateur de HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographique, version 1903-mise à jour de décembre 2019 
- Build 18362,1042

Améliorations et correctifs de la mise à jour :

- A introduit les correctifs de la reproduction de dernière étape (LSR). Amélioration du rendu visuel des hologrammes pour un affichage plus stable et plus clair en tenant compte plus précisément de leur profondeur. Ce symptôme sera plus perceptible après cette mise à jour si les applications ne définissent pas correctement la profondeur des hologrammes.
- Correction de la stabilité des applications exclusives et de la navigation entre les applications exclusives.
- Résolution d’un problème où la capture de la réalité mixte n’a pas pu enregistrer la vidéo une fois que l’appareil était en état de veille pendant plusieurs jours.
- Stabilité améliorée de l’hologramme.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographique, version 1903-mise à jour du 2019 du 1er novembre 
- Build 18362,1039

Améliorations et correctifs de la mise à jour :

- Correction des fonctionnalités des commandes vocales **Select** lors de la configuration initiale de en-ca et en-au.
- amélioration de la qualité visuelle des objets placés loin dans la dernière version unity Shared Computer Toolkit (MRTK).
- résolution des problèmes d’adressage avec les applications holographiques bloquées à l’état suspendu au démarrage jusqu’à l’ouverture et la fermeture du menu Démarrer.
- les correctifs de conformité du runtime OpenXR et les améliorations apportées à HoloLens 2 et à l’émulateur.
