---
title: Présentation du nouveau Microsoft Edge
description: En savoir plus sur la nouvelle application Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, navigateur
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427346"
---
# <a name="introducing-the-new-microsoft-edge"></a>Présentation du nouveau Microsoft Edge

![Animation du logo de l’ancienne version de Microsoft Edge vers le nouveau Microsoft Edge.](images/new-edge.gif)

Le nouveau Microsoft Edge [adopte le projet open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) afin de créer une meilleure compatibilité pour les clients et de réduire la fragmentation du web pour les développeurs web.

Avec [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), la nouvelle version de Microsoft Edge destinée aux clients HoloLens 2 est disponible pour la première fois. Partagez vos commentaires et bogues avec notre équipe via la fonctionnalité **Envoyer des commentaires** du nouveau Microsoft Edge ou via le [Hub de commentaires](hololens-feedback.md).

> [!IMPORTANT]
> Ce nouveau Microsoft Edge remplace automatiquement l’ancien Microsoft Edge, qui n’est [plus pris en charge](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) dans les nouvelles versions.

![Capture d’écran du nouveau Microsoft Edge.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Lancement du nouveau Microsoft Edge

Le nouveau Microsoft Edge ![Nouvelle icône Microsoft Edge.](images/new_edge_logo.png) (représenté par une icône de tourbillon verte et bleue) est épinglé au menu Démarrer et s’ouvre automatiquement lorsque vous activez un lien web.

> [!NOTE]
> Lorsque vous lancez le nouveau Microsoft Edge sur HoloLens 2 pour la première fois, vos paramètres et données sont importés à partir de l’ancienne version de Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuration des paramètres de stratégie pour le nouveau Microsoft Edge

Le nouveau Microsoft Edge offre aux administrateurs informatiques un plus large éventail de stratégies de navigateur sur HoloLens 2 que celles précédemment disponibles avec l’ancienne version de Microsoft Edge.

Voici quelques ressources utiles permettant d’en savoir plus sur la gestion des paramètres de stratégie pour le nouveau Microsoft Edge :

- [Configurer les paramètres de stratégie Microsoft Edge avec Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Mappage de stratégie de l’ancienne version de Microsoft Edge vers le nouveau Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mappage de stratégie de Google Chrome vers Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Documentation complète Microsoft Edge Entreprise](/deployedge/)

> [!IMPORTANT]
> Compte tenu du volume de stratégies de navigateur prises en charge par le nouveau Microsoft Edge, notre équipe n’est pas en mesure de garantir le bon fonctionnement de chaque nouvelle stratégie sur HoloLens 2. Pour autant, nous avons testé et vérifié que l’équivalent du nouveau Microsoft Edge de chaque stratégie de l’ancienne version de Microsoft Edge précédemment prise en charge sur HoloLens 2 fonctionne comme prévu. Consultez [Mappage de stratégie de l’ancienne version de Microsoft Edge vers le nouveau Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) pour trouver l’équivalent du nouveau Microsoft Edge de chaque stratégie de navigateur de l’ancienne version de Microsoft Edge que vous utilisiez avec HoloLens 2.
>
> Nous savons qu’au moins deux nouvelles stratégies Microsoft Edge ne fonctionnent *pas* avec HoloLens 2 :
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Ce qu’il faut attendre du nouveau Microsoft Edge sur HoloLens 2

Le nouveau Microsoft Edge étant une application Win32 native dotée d’une nouvelle couche d’adaptateur UWP qui lui permet de s’exécuter sur des appareils UWP tels que HoloLens 2, certaines fonctionnalités peuvent ne pas être immédiatement disponibles. Nous prendrons en charge de nouveaux scénarios et fonctionnalités au cours des mois à venir et vous invitons à consulter cet espace pour obtenir des informations à jour.

**Scénarios et fonctionnalités censés fonctionner :**
- Expérience de première exécution, connexion au profil et synchronisation
- Les sites web devraient s’afficher et se comporter comme prévu
- La plupart des fonctionnalités du navigateur (favoris, historique, etc.) devraient fonctionner comme prévu
- Mode sombre
- Installation d’applications web sur l’appareil
- Installation d’extensions (merci de nous informer si vous utilisez des extensions qui ne fonctionnent pas correctement sur HoloLens 2)
- Affichage et marquage d’un PDF
- Son spatial à partir d’une seule fenêtre de navigateur
- Mise à jour automatique et manuelle du navigateur
- Enregistrement d’un fichier PDF à partir du menu Imprimer (option « Enregistrer au format PDF »)
- Extension de la visionneuse WebXR et 360
- Restauration du contenu vers la fenêtre qui convient en cas de navigation entre plusieurs fenêtres placées dans votre environnement

**Scénarios et fonctionnalités non censés fonctionner :**
- Son spatial à partir de plusieurs fenêtres avec flux audio simultanés
- « Voir, prononcer »
- Impression

**Principaux problèmes connus du navigateur :**
- L’aperçu de loupe dans le clavier holographique a été désactivé pour le nouveau Microsoft Edge. Nous espérons réactiver cette fonctionnalité dans le cadre d’une prochaine mise à jour, lorsque l’agrandissement fonctionnera correctement.
- L’audio peut s’exécuter à partir d’une mauvaise fenêtre de navigateur si une autre fenêtre de navigateur est ouverte et active. Vous pouvez contourner ce problème en fermant l’autre fenêtre active non censée être en cours de lecture audio.
- Lors d’une lecture audio à partir d’une fenêtre de navigateur en mode « Me suivre », la lecture continue de s’exécuter si vous désactivez le mode « Me suivre ». Vous pouvez contourner ce problème en arrêtant la lecture audio avant de désactiver le mode « Me suivre » ou en fermant la fenêtre à l’aide du bouton X.
- L’interaction avec des fenêtres Microsoft Edge actives peut entraîner l’inactivité des autres fenêtres d’application 2D. Vous pouvez réactiver ces fenêtres en interagissant à nouveau avec elles.

## <a name="microsoft-edge-insider-channels"></a>Canaux Microsoft Edge Insider

L’équipe Microsoft Edge met à disposition trois canaux de préversion à la disposition de la communauté Edge Insider : Beta, Dev et Canary. L’installation d’un canal de préversion ne désinstalle pas la version finale de Microsoft Edge sur votre HoloLens 2, et vous pouvez en installer plusieurs à la fois. 

Consultez la [page d’accueil Microsoft Edge Insider](https://www.microsoftedgeinsider.com) pour en savoir plus sur la communauté Edge Insider. Pour en savoir plus sur les différents canaux Edge Insider et bien démarrer, consultez la [page de téléchargement Edge Insider](https://www.microsoftedgeinsider.com/download).

Plusieurs méthodes sont disponibles pour installer les canaux Microsoft Edge Insider sur HoloLens 2 :

**Installation directe sur l’appareil (actuellement réservée aux appareils non gérés)**
  1. Sur votre HoloLens 2, accédez à la [page de téléchargement Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Sélectionnez le bouton **Télécharger pour HoloLens 2** pour le canal Edge Insider que vous souhaitez installer.
  1. Lancez le fichier .msix téléchargé à partir de la file d’attente de téléchargement Edge ou du dossier « Téléchargements » de votre appareil (à l’aide de l’Explorateur de fichiers).
  1. Le [programme d’installation d’application](app-deploy-app-installer.md) démarre.
  1. Sélectionnez le bouton **Installer**.
  1. Une fois l’installation terminée, Microsoft Edge Beta, Dev ou Canary sont disponibles sous forme d’entrée distincte dans la liste **Toutes les applications** du menu Démarrer.

**Installer via un PC avec le Portail d'appareil Windows (requiert l’activation du [mode développeur](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) sur HoloLens 2)**
  1. Sur votre PC, accédez à la [page de téléchargement Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Sélectionnez le **bouton fléché déroulant** en regard du bouton « Télécharger pour Windows 10 » pour le canal Edge Insider que vous souhaitez installer.
  1. Sélectionnez **HoloLens 2** dans le menu déroulant.
  1. Enregistrez le fichier .msix dans le dossier « Téléchargements » de votre PC (ou dans un autre dossier que vous trouverez facilement).
  1. Utilisez le [Portail d'appareil Windows](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) sur votre PC pour installer le fichier .msix téléchargé sur HoloLens 2.
  1. Une fois l’installation terminée, Microsoft Edge Beta, Dev ou Canary sont disponibles sous forme d’entrée distincte dans la liste **Toutes les applications** du menu Démarrer.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Utilisation de WDAC pour bloquer le nouveau Microsoft Edge

Pour les administrateurs informatiques qui souhaitent mettre à jour leur [stratégie WDAC](windows-defender-application-control-wdac.md) afin de bloquer la nouvelle application Microsoft Edge, vous devez ajouter les éléments suivants à votre stratégie.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestion des points de terminaison pour le nouveau Microsoft Edge

Certains environnements peuvent présenter des restrictions réseau qu’il convient de prendre en compte. Pour une expérience fluide avec le nouveau Microsoft Edge, [activez ces points de terminaison Microsoft.](/deployedge/microsoft-edge-security-endpoints)

En savoir plus sur les [points de terminaison pour HoloLens](hololens-offline.md) actuellement disponibles.

## <a name="install-web-apps"></a>Installer des applications web
 > [!Note]
> À partir de [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), l’application web Office ne sera plus préinstallée. 

Vous pouvez utiliser le nouveau Microsoft Edge pour installer des applications web en même temps que des applications Microsoft Store. Par exemple, vous pouvez installer l’application web Microsoft Office pour afficher et modifier des fichiers hébergés sur SharePoint ou OneDrive. Pour installer l’application web Office, consultez https://www.office.com et sélectionnez le bouton **Application disponible** ou **Installer Office** dans la barre d’adresse. Sélectionnez **Installer** pour confirmer.
> [!IMPORTANT]
> La fonctionnalité d’application web Office n’est disponible que si votre HoloLens 2 dispose d’une connexion Internet active.

## <a name="webxr-and-360-viewer"></a>Visionneuse WebXR et 360


Le nouveau Microsoft Edge prend en charge WebXR, qui correspond à la nouvelle norme pour créer des expériences web immersives (et remplace WebVR). De nombreuses expériences web immersives ont été conçues avec VR à l’esprit (elles remplacent votre champ de vision par un environnement virtuel), mais ces expériences sont également prises en charge par HoloLens 2. En outre, la norme WebXR permet des expériences web immersives de réalité augmentée et mixte utilisant votre environnement physique. Alors que les développeurs consacrent plus de temps à WebXR, nous prévoyons de nouvelles expériences immersives de réalité augmentée et mixte pour HoloLens 2.

L’extension de visionneuse 360 est basée sur WebXR et s’installe automatiquement en même temps que le nouveau Microsoft Edge sur HoloLens 2. Cette extension web vous offre la possibilité de vous immerger dans des vidéos à 360 degrés. YouTube propose la plus grande sélection de vidéos à 360 degrés et constitue un bon point de départ.

### <a name="how-to-use-webxr"></a>Utiliser WebXR

1. Accédez à un site web avec prise en charge de WebXR.
1. Sélectionnez le bouton **Accéder à VR** sur le site web. L’emplacement et la représentation visuelle de ce bouton peuvent varier en fonction du site web, mais se présentent globalement comme suit :

    ![Exemple de bouton Accéder à VR.](images/75px-enter-vr.png)

1. La première fois que vous essayez de lancer une expérience WebXR sur un domaine spécifique, le navigateur vous demande de consentir à accéder à une vue immersive. Sélectionnez **Autoriser**.
1. Utilisez les [mouvements HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) pour manipuler l’expérience.
1. Si l’expérience ne dispose pas de bouton **Quitter**, utilisez le [mouvement associé au menu Démarrer](hololens2-basic-usage.md#start-gesture) pour revenir à l’accueil.

**Exemples WebXR recommandés**
- Visionneuse 360 (voir la section suivante)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Utiliser la visionneuse 360

1. Accédez à une vidéo à 360 degrés sur YouTube.
1. Dans l’image vidéo, sélectionnez le bouton de casque de réalité mixte :

    ![Bouton permettant d’activer la visionneuse 360.](images/enter-360-viewer.jpg)

1. La première fois que vous essayez de lancer la visionneuse 360 sur un domaine spécifique, le navigateur vous demande de consentir à accéder à une vue immersive. Sélectionnez **Autoriser**.
1. Effectuez un [clic aérien](hololens2-basic-usage.md#select-using-air-tap) pour afficher les contrôles de lecture. Utilisez les [rayons manuels et le clic aérien](hololens2-basic-usage.md#select-using-air-tap) pour ce qui suit : lecture/pause, avance/retour rapide, activation/désactivation des sous-titres, arrêt de l’expérience (ce qui a pour effet de quitter la vue immersive). Les contrôles de lecture disparaissent après quelques secondes d’inactivité.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Principaux problèmes connus de la visionneuse WebXR et 360
- Selon la complexité de l’expérience WebXR, le taux de trames peut baisser ou être saccadé.
- Dans WebXR, les articulations de la main ne sont pas prises en charge par défaut. Les développeurs peuvent permettre cette prise en charge via edge://flags en activant « Entrée manuelle WebXR ».
- Les vidéos à 360 degrés provenant de sites web autres que YouTube peuvent ne pas fonctionner comme prévu.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Envoi de commentaires sur la visionneuse WebXR et 360

Partagez vos commentaires avec notre équipe via la fonctionnalité **Envoyer des commentaires** du nouveau Microsoft Edge.
