---
title: Version préliminaire d’Insider pour Microsoft HoloLens
description: Découvrez comment prendre en main les builds Insider et fournir des commentaires précieux pour la prochaine mise à jour majeure du système d’exploitation pour HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308864"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Version préliminaire d’Insider pour Microsoft HoloLens

Bienvenue dans les dernières versions préliminaires d’Insider pour HoloLens ! Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) précieux pour la prochaine mise à jour majeure du système d’exploitation pour HoloLens.

## <a name="windows-insider-release-notes"></a>Notes de publication de Windows Insider

Nous sommes ravis de commencer à effectuer le vol de nouvelles fonctionnalités vers Windows Insider. Les nouvelles builds feront l’d’un vol vers le canal de développement pour les dernières mises à jour. Nous continuerons à mettre à jour cette page à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider.  Soyez enthousiaste et prêt à mélanger ces mises à jour dans votre réalité.

Cette mise à jour de fonctionnalité contient des fonctionnalités pour deux audiences cibles. Fonctionnalités qui peuvent être utilisées par tout le monde sur un appareil par l’utilisateur final et les nouvelles options de gestion des appareils qui peuvent être configurées par les administrateurs informatiques. Le tableau de fonctionnalités ci-dessous précise l’audience qui peut utiliser chaque nouvelle fonctionnalité. Si vous êtes un administrateur informatique, consultez notre [liste de contrôle des mises à jour de l’administrateur informatique](#it-admin---update-checklist)

> [!IMPORTANT]
> Si vous utilisiez précédemment l’application paramètres ou l’application Microsoft Edge sur une borne, nous avons remplacé ces applications par de nouvelles applications qui utilisent un ID d’application différent. Nous vous encourageons vivement à lire [les nouvelles AUMIDs pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes) ci-dessous. Cela vous permet de continuer à avoir l’application paramètres dans votre kiosque ou d’inclure la nouvelle application Microsoft Edge.

<br>

| Nom de la fonctionnalité                                              | Description courte                                                                      | Public visé | Disponible dans la Build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Nouveau Microsoft Edge](#introducing-the-new-microsoft-edge) | Le nouveau Microsoft Edge basé sur le chrome est désormais disponible pour HoloLens 2                         | Utilisateur final | 20279,1006 |
| [Visionneuse WebXR et 360](#webxr-and-360-viewer)             | Essayez des expériences Web immersifs et une lecture vidéo de 360                                           | Utilisateur final | 20289,1000 |
| [Nouvelle application de paramètres](#new-settings-app)                     | L’application paramètres héritée est remplacée par une version mise à jour avec de nouvelles fonctionnalités et paramètres | Utilisateur final | 20279,1006 |
| [Étalonnage des couleurs d’affichage](#display-color-calibration)   | Sélectionner un autre profil de couleurs pour votre affichage HoloLens 2                                | Utilisateur final | 20293,1000 |
| [Sélecteur d’application par défaut](#default-app-picker)                 | Choisir l’application à lancer pour chaque type de fichier ou de lien                                      | Utilisateur final | 20279,1006 |
| [Contrôle du volume par application](#per-app-volume-control) |  Contrôler le volume au niveau de l’application indépendamment du volume système | Utilisateur final | 20293,1000 |
| [Application Web Office](#office-web-app)                         | Un raccourci vers l’application Web Office est maintenant listé dans « toutes les applications »                                   | Utilisateur final | 20279,1006 |
| [Faire glisser vers le type](#swipe-to-type)                           | Utilisez l’astuce de votre doigt pour « balayer » les mots sur le clavier holographique                        | Utilisateur final | 20279,1006 |
| [Menu alimenter à partir du menu Démarrer](#power-menu-from-start) | Dans le menu Démarrer, redémarrez et arrêtez l’appareil HoloLens. | Utilisateur final | 20293,1000 |
| [Plusieurs utilisateurs sont listés sur l’écran de connexion](#multiple-users-listed-on-sign-in-screen) | Afficher plusieurs comptes d’utilisateur sur l’écran de connexion | Utilisateur final | 20293,1000 |
| [Prise en charge du microphone externe USB-C](#usb-c-external-microphone-support) | Utilisez des microphones USB-C pour les applications et/ou l’assistance à distance.| Utilisateur final | 20279,1006 |
| [Ouverture de session automatique des visiteurs pour les bornes](#visitor-auto-logon-for-kiosks)                          | Active l’ouverture de session automatique sur les comptes de visiteur à utiliser pour les modes plein écran.                         | IT Admin | 20279,1006                 |
| [Nouvelle AUMIDs pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs pour les nouveaux paramètres et les applications Edge | IT Admin | 20279,1006 |
| [Gestion améliorée des échecs du mode plein écran](#kiosk-mode-behavior-changes-for-handling-of-failures) | Le mode plein écran recherche un accès global affecté avant le menu Démarrer vide. | IT Admin | 20279,1006 |
| [Nouvelle SettingsURIs pour la visibilité des paramètres de page](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | plus de 20 nouveaux SettingsURIs pour la stratégie paramètres/PageVisibilityList | IT Admin | 20289,1000 |
| [Configurer les diagnostics de secours](#configuring-fallback-diagnostics-via-settings-app) | Définition du comportement de diagnostic de secours dans l’application paramètres | IT Admin | 20279,1006 |
| [Partager des éléments avec des appareils proches](#share-things-with-nearby-devices) | Partager des fichiers ou des URL à partir d’un HoloLens sur un PC | Tous | 20279,1006 |
| [Nouveau dépanneur de mise à jour du système d’exploitation](#new-os-update-troubleshooter) | Nouvel utilitaire de résolution des problèmes dans les paramètres des mises à jour du système d’exploitation | IT Admin | 20279,1006 |
| [Aperçu de l’optimisation de la livraison](#delivery-optimization-preview) | Réduire la consommation de bande passante pour les téléchargements à partir de plusieurs appareils HoloLens | IT Admin | 20301,1000 |
| [Améliorations et correctifs de la mise à jour](#improvements-and-fixes-in-the-update) | Correctifs supplémentaires dans la mise à jour. | Tous | 20279,1006 |

### <a name="it-admin---update-checklist"></a>Administrateur informatique-liste de vérification des mises à jour

Cette liste de vérification vous aidera à connaître les nouveaux éléments que les fonctionnalités ajoutées dans cette mise à jour des fonctionnalités peuvent avoir un impact sur les configurations de gestion des appareils en cours ou sur les nouvelles fonctionnalités que vous pouvez utiliser.

#### <a name="updates-to-kiosk-mode"></a>Mises à jour du mode plein écran

[**Nouvelle AUMIDs pour les nouvelles applications en mode plein écran**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Si vous utilisiez précédemment l’application paramètres ou l’application Microsoft Edge sur une borne, nous avons remplacé ces applications par de nouvelles applications qui utilisent un ID d’application différent. Nous vous encourageons vivement à lire [les nouvelles AUMIDs pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes) ci-dessous. Cela vous permet de continuer à avoir l’application paramètres dans votre kiosque ou d’inclure la nouvelle application Microsoft Edge.

Ces modifications peuvent être effectuées maintenant et déployées sur tous les appareils et permettent une transition plus lisse lors de la mise à jour.

[**Ouverture de session automatique des visiteurs pour les bornes**](#visitor-auto-logon-for-kiosks)

Les visiteurs peuvent désormais être connectés automatiquement à une borne. Ce comportement est activé par défaut, mais peut être géré et désactivé.

[**Gestion améliorée des échecs du mode plein écran**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Si l’appartenance au groupe AAD de l’utilisateur AAD connecté n’est pas correctement déterminée, la configuration de l’kiosque global est utilisée pour le menu Démarrer (le cas échéant); sinon, l’utilisateur reçoit un menu Démarrer vide. Si le menu Démarrer vide n’est pas une configuration que vous pouvez définir directement, cette nouvelle gestion peut être utile pour informer votre service de support technique de si vous utilisez des bornes, car cela peut s’appliquer à vos configurations ou vous pouvez apporter de nouveaux ajustements aux configurations d’accès affectées.

#### <a name="updates-to-page-settings-visibility"></a>Mise à jour de la visibilité des paramètres de page

[**Nouvelle SettingsURIs pour la visibilité des paramètres de page**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Si vous utilisez actuellement la [visibilité des paramètres de page](settings-uri-list.md) , vous souhaiterez peut-être apporter des modifications à vos URI existants, que vous avez autorisés ou bloqués.

#### <a name="updates-for-your-wdac-policy"></a>Mises à jour pour votre stratégie WDAC

Si vous avez déjà bloqué Microsoft Edge via WDAC, vous souhaiterez mettre à jour votre stratégie WDAC. Vérifiez [les éléments suivants](#using-wdac-to-block-new-microsoft-edge) et utilisez l’exemple de code fourni.

#### <a name="enable-new-endpoints-for-edge"></a>Activer les nouveaux points de terminaison pour Edge

Si vous disposez d’une infrastructure qui implique la configuration de points de terminaison réseau tels que le proxy ou le pare-feu, [activez ces nouveaux points de terminaison pour la nouvelle application Microsoft Edge.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Éléments nouvellement configurables

- [Configurer les diagnostics de secours](#configuring-fallback-diagnostics-via-settings-app)
  - Vous pouvez configurer si et qui peuvent collecter des diagnostics de secours.
- [Partager des éléments avec des appareils proches](#share-things-with-nearby-devices)
  - Vous pouvez désactiver la nouvelle fonctionnalité de partage proche.
- [Configuration des paramètres de stratégie pour le nouveau Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Passez en revue les nouvelles configurations disponibles pour Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nouvel outil de diagnostic

- [Nouveau dépanneur de mise à jour du système d’exploitation](#new-os-update-troubleshooter)
  - Collecter les journaux liés aux mises à jour du système d’exploitation

### <a name="introducing-the-new-microsoft-edge"></a>Présentation du nouveau Microsoft Edge

![Animation du logo Microsoft Edge hérité vers le nouveau logo Microsoft Edge](images/new-edge.gif)

Le nouveau Microsoft Edge [adopte le projet open source de chrome](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) pour offrir une meilleure compatibilité pour les clients et une moindre fragmentation du Web pour les développeurs Web.

Grâce à cette version préliminaire, le nouveau Microsoft Edge est disponible pour les clients HoloLens 2 pour la première fois. Tandis que le nouveau Microsoft Edge remplacera l’ancien Microsoft Edge sur HoloLens 2, les deux navigateurs sont actuellement disponibles pour les Insiders. Partagez vos commentaires avec notre équipe via la fonctionnalité **Envoyer des commentaires** dans le nouveau Microsoft Edge ou via le [Hub de commentaires](hololens-feedback.md).

![Nouvelle capture d’écran Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Lancement du nouveau Microsoft Edge

Deux versions de Microsoft Edge sont disponibles pour les Insiders : la nouvelle icône Microsoft Edge ![ nouvelle Microsoft Edge ](images/new_edge_logo.png) (représentée par une icône de tourbillon bleue et bleue) et l’ancienne partie Microsoft Edge (représentée par l’icône « e » blanche). Le nouveau Microsoft Edge est épinglé au menu Démarrer et s’ouvre automatiquement lorsque vous activez un lien Web. Si vous souhaitez revenir à l’utilisation de Microsoft Edge hérité comme navigateur Web par défaut, consultez les instructions ci-dessous pour la [réinitialisation des applications par défaut](#default-app-picker).

> [!NOTE]
> Lorsque vous lancez pour la première fois le nouveau Microsoft Edge sur HoloLens 2, vos paramètres et données sont importés à partir de Microsoft Edge hérité. Si vous continuez à utiliser Microsoft Edge hérité après avoir lancé le nouveau Microsoft Edge, ces nouvelles données ne seront pas synchronisées à partir de Microsoft Edge hérité vers le nouveau Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuration des paramètres de stratégie pour le nouveau Microsoft Edge

Le nouveau Microsoft Edge offre aux administrateurs informatiques un ensemble plus large de stratégies de navigateur sur HoloLens 2 que celles précédemment disponibles avec Microsoft Edge hérité.

Voici quelques ressources utiles pour en savoir plus sur la gestion des paramètres de stratégie pour le nouveau Microsoft Edge :

- [Configurer les paramètres de stratégie Microsoft Edge avec Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mappage de la stratégie héritée Microsoft Edge à Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mappage de la stratégie Google Chrome vers Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentation complète de [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> En raison du volume de stratégies de navigateur prises en charge par le nouveau Microsoft Edge, notre équipe ne peut pas garantir que chaque nouvelle stratégie fonctionne sur HoloLens 2. Toutefois, nous avons testé et confirmé que la nouvelle fonction Microsoft Edge équivalente de chaque stratégie Microsoft Edge héritée précédemment prise en charge par HoloLens 2 fonctionnait comme prévu. Consultez [mappage de la stratégie héritée](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge à Microsoft Edge pour trouver le nouvel équivalent Microsoft Edge de chaque stratégie de navigateur Microsoft Edge héritée que vous utilisiez avec HoloLens 2.
>
> Au moins deux nouvelles stratégies Microsoft Edge ne fonctionneront *pas* avec HoloLens 2 :
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Ce qu’il faut attendre du nouveau Microsoft Edge sur HoloLens 2

Étant donné que le nouveau Microsoft Edge est une application Win32 native avec une nouvelle couche d’adaptateur UWP, ce qui lui permet de s’exécuter sur des appareils UWP tels que HoloLens 2, certaines fonctionnalités peuvent ne pas être immédiatement disponibles. Nous allons prendre en charge de nouveaux scénarios et fonctionnalités au cours des prochains mois. par conséquent, consultez cet espace pour obtenir des informations à jour.

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
- Wi-Fi les configurations de proxy, qui sont des stratégies de proxy ciblant des connexions Wi-Fi individuelles, ne fonctionnent pas actuellement avec le nouveau Microsoft Edge. Nous travaillons activement à débloquer ce problème avant la publication publique de la mise à jour du système d’exploitation.
- L’aperçu de la loupe dans le clavier holographique a été désactivé pour le nouveau Microsoft Edge. Nous espérons réactiver cette fonctionnalité dans une prochaine mise à jour, une fois que l’agrandissement fonctionnera correctement.
- Deux caractères sur le clavier japonais ne fonctionnent pas comme prévu dans le nouveau Microsoft Edge. Ce problème a été provoqué par la racine et devrait bientôt être corrigé.
- Les liens Web dans l’application Microsoft Store peuvent ne pas lancer le navigateur
- L’audio peut s’exécuter à partir d’une fenêtre de navigateur incorrecte si une autre fenêtre de navigateur est ouverte et active. Vous pouvez contourner ce problème en fermant l’autre fenêtre active qui n’est pas censée être en cours de lecture audio.
- Lors de la lecture de l’audio à partir d’une fenêtre de navigateur en [mode « suivre »](hololens2-basic-usage.md#follow-me-stop-following), l’audio continue de s’exécuter si vous désactivez le mode « suivre ». Vous pouvez contourner ce problème en arrêtant la lecture audio avant de désactiver le mode « suivre » ou en fermant la fenêtre avec le bouton **X** .
- L’interaction avec les fenêtres actives de Microsoft Edge peut entraîner la désactivation inattendue d’autres fenêtres d’application 2D. Vous pouvez réactiver ces fenêtres en les interagissant avec elles.
- L’ouverture d’un lien Web à partir d’une autre application ou de certains types de documents tels que des fichiers PDF peut entraîner l’ouverture d’un deuxième onglet vide dans le navigateur (en plus du nouvel onglet créé avec le contenu du lien Web ou du lien de fichier). Vous pouvez contourner ce problème en fermant l’onglet vide supplémentaire.

#### <a name="microsoft-edge-insider-channels"></a>Canaux Microsoft Edge Insider

L’équipe Microsoft Edge met à disposition trois canaux de préversion à la communauté Edge Insider : bêta, dev et Canaries. L’installation d’un canal de préversion ne désinstalle pas la version officielle de Microsoft Edge sur votre HoloLens 2, et vous pouvez en installer plusieurs en même temps. 

Visitez la [page d’accueil de Microsoft Edge Insider](https://www.microsoftedgeinsider.com) pour en savoir plus sur la communauté Edge Insider. Pour en savoir plus sur les différents canaux Edge Insider et sur la prise en main, visitez la [page de téléchargement de Edge Insider](https://www.microsoftedgeinsider.com/download).

Deux méthodes sont disponibles pour l’installation des canaux Microsoft Edge Insider sur HoloLens 2 :

**Installation directe sur l’appareil (actuellement disponible uniquement pour les appareils non gérés)**
  1. Sur votre HoloLens 2, accédez à la [page de téléchargement de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Sélectionnez le bouton **Télécharger pour HoloLens 2** pour le canal Edge Insider que vous souhaitez installer.
  1. Lancez le fichier. msix téléchargé à partir de la file d’attente de téléchargement Edge ou du dossier « downloads » de votre appareil (à l’aide de l’Explorateur de fichiers).
  1. Le [programme d’installation](app-deploy-app-installer.md) de l’application démarre.
  1. Sélectionnez le bouton **Installer**.
  1. Une fois l’installation réussie, vous trouverez Microsoft Edge Beta, dev ou Canaries sous la forme d’une entrée distincte dans la liste **toutes les applications** du menu Démarrer.

**Installer via un PC avec le portail d’appareils Windows (nécessite l’activation du [mode développeur](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) sur HoloLens 2)**
  1. Sur votre PC, accédez à la [page de téléchargement de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Sélectionnez le **bouton de la flèche déroulante** en regard du bouton « Télécharger pour Windows 10 » pour le canal Edge Insider que vous souhaitez installer.
  1. Sélectionnez **HoloLens 2** dans le menu déroulant.
  1. Enregistrez le fichier. msix dans le dossier « téléchargements » de votre ordinateur (ou dans un autre dossier que vous trouverez facilement).
  1. Utilisez le [portail d’appareils Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) sur votre PC pour installer le fichier. msix téléchargé sur HoloLens 2.
  1. Une fois l’installation réussie, vous trouverez Microsoft Edge Beta, dev ou Canaries sous la forme d’une entrée distincte dans la liste **toutes les applications** du menu Démarrer.

> [!NOTE]
> Au cours de cette version préliminaire de Windows Insider pour HoloLens 2, la version de Microsoft Edge sur votre appareil peut être plus élevée que celles disponibles dans une partie (ou la totalité) des canaux Microsoft Edge Insider. Cela permet de s’assurer que les nouvelles fonctionnalités et les corrections ciblant spécifiquement le navigateur Web sur HoloLens 2 s’accèdent à nos Windows Insiders aussi rapidement que possible. Peu après la publication publique de la prochaine mise à jour de Windows, les versions de Microsoft Edge Insider sont dépassées et sont conservées au-delà de la version de Microsoft Edge sur votre HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Utilisation de WDAC pour bloquer une nouvelle session Microsoft Edge

Pour les administrateurs informatiques qui cherchent à mettre à jour leur [stratégie WDac](windows-defender-application-control-wdac.md) pour bloquer la nouvelle application Microsoft Edge, vous devez ajouter ce qui suit à votre stratégie.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gestion des points de terminaison pour le nouveau Microsoft Edge

Certains environnements peuvent avoir des restrictions réseau à prendre en compte. Pour garantir une expérience sans heurts avec la nouvelle périphérie, [activez ces points de terminaison Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

En savoir plus sur les [points de terminaison actuellement disponibles pour HoloLens](hololens-offline.md).

### <a name="webxr-and-360-viewer"></a>Visionneuse WebXR et 360

*Ajouté dans la version 20289,1000 de Windows Insider*

Le nouveau Microsoft Edge prend en charge WebXR, qui est la nouvelle norme pour créer des expériences Web immersifs (en remplaçant WebVR). De nombreuses expériences Web immersifs ont été conçues avec VR à l’esprit (elles remplacent votre champ de vue par un environnement virtuel), mais ces expériences sont également prises en charge par HoloLens 2. La norme WebXR permet également des expériences Web immersifs enrichies et en réalité mixte qui utilisent votre environnement physique. À mesure que les développeurs consacrent plus de temps à WebXR, nous prévoyons de nouvelles expériences immersifs de la réalité accrue et de la réalité mixte pour les clients HoloLens 2 à essayer !

L’extension de visionneuse 360 est basée sur WebXR et s’installe automatiquement en même temps que le nouveau Microsoft Edge sur HoloLens 2. Cette extension Web vous donne la possibilité de vous plonger dans des vidéos de 360 degrés. YouTube offre la plus grande sélection de vidéos 360, nous vous encourageons donc à les démarrer.

#### <a name="how-to-use-webxr"></a>Utilisation de WebXR

1. Accédez à un site Web avec prise en charge de WebXR.
1. Sélectionnez le bouton **Enter VR** sur le site Web. L’emplacement et la représentation visuelle de ce bouton peuvent varier en fonction du site Web, mais peuvent ressembler à ceci :

    ![Exemple de bouton ENTER VR](images/75px-enter-vr.png)

1. La première fois que vous essayez de lancer une expérience WebXR sur un domaine spécifique, le navigateur vous demande le consentement d’entrer dans un affichage immersif, sélectionnez **autoriser**.
1. Utilisez les [gestes HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) pour manipuler l’expérience.
1. Si l’expérience n’a pas de bouton **quitter** , utilisez le [geste démarrer](hololens2-basic-usage.md#start-gesture) pour revenir à l’accueil.

**Exemples de WebXR recommandés**
- visionneuse 360 (voir la section suivante)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [Peinture WebXR](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Comment utiliser la visionneuse 360

1. Accédez à une vidéo de 360 degrés sur YouTube.
1. Dans l’image vidéo, sélectionnez le bouton casque de réalité mixte :

    ![Bouton pour activer la visionneuse 360](images/enter-360-viewer.jpg)

1. La première fois que vous essayez de lancer la visionneuse 360 sur un domaine spécifique, le navigateur vous demande le consentement d’entrer dans une vue immersive. Sélectionnez **Autoriser**.
1. [Appuyez](hololens2-basic-usage.md#select-using-air-tap) sur l’air pour afficher les contrôles de lecture. Utilisez les [rayons de main et le robinet d’air](hololens2-basic-usage.md#select-using-air-tap) pour la lecture/pause, les sauts vers l’avant/arrière, l’activation/désactivation des sous-titres ou l’arrêt de l’expérience (ce qui a pour conséquence de quitter l’affichage immersif). Les contrôles de lecture disparaissent après quelques secondes d’inactivité.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principaux problèmes connus de la visionneuse WebXR et 360
- En fonction de la complexité de l’expérience WebXR, les cadences peuvent chuter ou être saccadées.
- La prise en charge des articulations de la main dans WebXR n’est pas activée par défaut. Les développeurs peuvent activer la prise en charge via `edge://flags` en activant « WebXR main Input ».
- Lors de la sortie d’un WebXR ou d’une expérience de la visionneuse 360, il peut s’avérer nécessaire de disposer d’un maximum de 30 secondes pour les hologrammes de la réalité mixte.
- 360 les vidéos provenant de sites Web autres que YouTube peuvent ne pas fonctionner comme prévu.
- Les sous-titres sont actuellement désactivés dans la visionneuse 360 sur HoloLens 2. Nous prévoyons d’activer cette fonctionnalité dans une prochaine mise à jour.
- La suspension d’une vidéo dans la visionneuse 360 arrête la vidéo à partir du rendu (mais le choix du bouton lecture reprend correctement la lecture).
- Le bouton « vidéo suivante » de la visionneuse 360 ne fonctionne pas actuellement.
- Vous pouvez lire des vidéos 2D en mode « Théâtre » immersif, mais la cadence peut être inférieure à 30 i/s.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Envoi de commentaires sur WebXR et la visionneuse 360

Partagez vos commentaires avec notre équipe via la fonctionnalité **Envoyer des commentaires** du nouveau Microsoft Edge.

### <a name="new-settings-app"></a>Nouvelle application de paramètres

Avec cette version, nous allons introduire une nouvelle version de l’application paramètres. La nouvelle application paramètres comprend de nouvelles fonctionnalités et des paramètres développés pour HoloLens 2 dans les domaines suivants : son, Power & Sleep, réseau & Internet, applications, comptes, facilité d’accès et bien plus encore.

> [!NOTE]
> Étant donné que la nouvelle application de paramètres est distincte de l’application paramètres hérités, toutes les fenêtres de paramètres que vous avez placées précédemment dans votre environnement seront supprimées lors de la mise à jour.

![Page d’accueil de la nouvelle application paramètres](images/new-settings-app.png)

**Nouvelles fonctionnalités et paramètres**
- Recherche de paramètres : recherchez des paramètres à partir de la page d’accueil des paramètres à l’aide de mots clés ou du nom du paramètre.
- Son du > système :
  - Périphériques audio d’entrée et de sortie : choisissez indépendamment vos périphériques audio d’entrée et de sortie (par exemple, écoutez l’audio via un casque Bluetooth ou utilisez un microphone USB-C pour l’entrée audio).
    > [!NOTE]
    > Les microphones Bluetooth ne sont pas pris en charge par HoloLens 2.
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
- Les fenêtres de paramètres précédemment placées seront supprimées (voir la remarque ci-dessus).
- Vous ne pouvez plus renommer votre appareil avec l’application paramètres. Les administrateurs informatiques peuvent renommer des appareils à l’aide du modèle [Windows AutoPilot pour le modèle de nom de périphérique HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) ou du nœud MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) /Microsoft/DNSComputerName.
- La page Ethernet affiche un périphérique Ethernet virtuel (« UsbNcm ») à tout moment.
- L’utilisation de la batterie pour le nouveau Microsoft Edge peut ne pas être exacte, en raison de sa nature comme une application de bureau Win32 prise en charge par une couche d’adaptateur UWP (aucun correctif n’est bientôt prévu).

### <a name="display-color-calibration"></a>Étalonnage des couleurs d’affichage

*Ajouté dans la version 20293,1000 de Windows Insider*

Avec ce nouveau paramètre, vous pouvez sélectionner un autre profil de couleurs pour votre affichage HoloLens 2. Cela peut aider à obtenir des couleurs plus précises, en particulier des niveaux de luminosité d’affichage inférieurs. L’étalonnage des couleurs d’affichage se trouve dans l’application paramètres, sur la page système > étalonnage.

> [!NOTE]
> Étant donné que ce paramètre enregistre un nouveau profil de couleurs dans votre microprogramme d’affichage, il s’agit d’un paramètre par appareil (et non propre à chaque compte d’utilisateur).

#### <a name="how-to-use-display-color-calibration"></a>Comment utiliser l’étalonnage des couleurs d’affichage

1. Lancez l’application **paramètres** et accédez à **système > étalonnage**.
1. Sous **étalonnage des couleurs** de l’écran, sélectionnez le bouton **exécuter l’étalonnage des couleurs** .
1. L’expérience d’étalonnage des couleurs s’affiche et vous encourage à vous assurer que votre visière est bien à la bonne position.
1. Une fois que vous avez parcouru les boîtes de dialogue d’instruction, votre affichage est automatiquement grisé à 30%.
    > [!TIP]
    > Si vous ne parvenez pas à voir la scène estompée dans votre environnement, vous pouvez ajuster manuellement le niveau de luminosité de HoloLens 2 à l’aide des boutons de luminosité sur le côté gauche de l’appareil.
1. Sélectionnez les boutons 1-6 pour essayer instantanément chaque profil de couleurs et en trouver un qui ressemble le mieux à vos yeux (cela signifie généralement que le profil qui permet d’afficher la scène est le plus neutre, avec le modèle de nuances de gris et les tonalités de peau qui se présentent comme prévu).

    ![Scène d’étalonnage des couleurs d’affichage](images/color-cal-ui.png)
    
1. Quand vous êtes satisfait du profil sélectionné, cliquez sur le bouton **enregistrer & quitter**
1. Si vous préférez ne pas apporter de modifications, cliquez sur le bouton **annuler & quitter** . vos modifications seront rétablies

> [!TIP]
> Voici quelques conseils utiles à garder à l’esprit lors de l’utilisation du paramètre d’étalonnage des couleurs de l’écran :
> - Vous pouvez réexécuter l’étalonnage des couleurs d’affichage à partir des paramètres chaque fois que vous le souhaitez
> - Si une personne de l’appareil a déjà utilisé le paramètre pour modifier les profils de couleurs, la date/l’heure de la dernière modification sera reflétée dans la page Paramètres.
> - Lorsque vous réexécutez l’étalonnage des couleurs d’affichage, le profil de couleurs précédemment enregistré est mis en surbrillance et le profil 0 ne s’affiche pas (comme le profil 0 représente le profil de couleurs d’origine de l’affichage)
> - Si vous souhaitez rétablir le profil de couleurs d’origine de l’affichage, vous pouvez le faire à partir de la page Paramètres (voir [Comment réinitialiser le profil de couleurs](#how-to-reset-color-profile)).

#### <a name="how-to-reset-color-profile"></a>Comment réinitialiser le profil de couleurs

Si vous n’êtes pas satisfait du profil de couleurs personnalisé enregistré dans HoloLens 2, vous pouvez restaurer le profil de couleurs d’origine de l’appareil :
1. Lancez l’application **paramètres** et accédez à **système > étalonnage**.
1. Sous **étalonnage des couleurs** de l’écran, sélectionnez le bouton **rétablir le profil de couleurs par défaut** .
1. Quand la boîte de dialogue s’ouvre, sélectionnez **redémarrer** si vous êtes prêt à redémarrer HoloLens 2 et à appliquer vos modifications.

#### <a name="top-display-color-calibration-known-issues"></a>Problèmes connus d’étalonnage des couleurs de l’écran principal

- Dans la page Paramètres, la chaîne d’État qui indique à quel moment la dernière modification du profil de couleurs est obsolète jusqu’à ce que vous rechargeiez cette page de paramètres.
    - Solution de contournement : sélectionnez une autre page de paramètres, puis sélectionnez à nouveau la page d’étalonnage.

### <a name="default-app-picker"></a>Sélecteur d’application par défaut

Quand vous activez un lien hypertexte ou que vous ouvrez un type de fichier avec plusieurs applications installées, ce qui le prend en charge, une nouvelle fenêtre s’affiche pour vous inviter à sélectionner l’application installée qui doit gérer le type de fichier ou de lien. Dans cette fenêtre, vous pouvez également choisir d’utiliser l’application sélectionnée pour gérer le type de fichier ou de lien « une fois » ou « toujours ».

![Fenêtre du sélecteur d’application](images/default-app-picker.png)

Si vous choisissez « toujours », mais que vous souhaitez ultérieurement modifier l’application qui gère un type de fichier ou de lien particulier, vous pouvez réinitialiser vos valeurs par défaut enregistrées dans **paramètres > applications**. Faites défiler vers le bas de la page et sélectionnez le bouton **Effacer** sous « applications par défaut pour les types de fichiers » et/ou « applications par défaut pour les types de liens ». Contrairement au paramètre similaire sur les PC de bureau, vous ne pouvez pas réinitialiser les valeurs par défaut des types de fichiers individuels.

### <a name="per-app-volume-control"></a>Contrôle du volume par application

Désormais, dans cette version de Windows Insider, les utilisateurs peuvent ajuster manuellement le niveau de volume de chaque application. Cela permet aux utilisateurs de mieux se concentrer sur les applications dont ils ont besoin, ou de mieux les entendre lors de l’utilisation de plusieurs applications. Par exemple, la nécessité de désactiver le volume d’une application lors de l’appel d’une autre personne pour l’assistance à distance dans une autre.

Pour définir le volume d’une application individuelle, accédez à **paramètres**  ->    ->  **sons** système, puis sous options de son avancées, sélectionnez le volume de l' **application et les préférences de l’appareil**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Application Web Office

>[!NOTE]
>Depuis la version 20325,1000 de Windows Insider, Office Web App ne sera plus préinstallé (et ne sera pas préinstallé pour la prochaine version publique de la mise à jour du système d’exploitation. Pour installer l’application Web Office, visitez https://www.office.com et sélectionnez le bouton **application disponible** ou **installer Office** dans la barre d’adresses. Sélectionnez **installer** pour confirmer.

L’application Web Office a été ajoutée à la liste « toutes les applications » dans le menu Démarrer. Cette application Web peut également être épinglée pour démarrer ou être désinstallée. Étant donné qu’il s’agit d’une application Web, sa fonctionnalité correspond exactement à ce que vous auriez rencontré en visitant https://www.office.com . La fonctionnalité Office Web App n’est disponible que lorsque votre application HoloLens 2 dispose d’une connexion Internet active.

**Problème connu**
- La réinitialisation de votre appareil entraîne la suppression de l’application Web Office

### <a name="swipe-to-type"></a>Faire glisser vers le type

Certains clients le trouvent plus rapidement pour « taper » sur des claviers virtuels en passant la forme du mot qu’ils envisagent de taper, et nous prévoyons cette fonctionnalité pour le clavier holographique. Vous pouvez balayer un mot à la fois en passant la pointe de votre doigt dans le plan du clavier holographique, en balayant la forme du mot, puis en retirant l’extrémité de votre doigt du plan du clavier. Vous pouvez balayer les mots de suivi sans avoir à appuyer sur la barre d’espace en supprimant votre doigt du clavier entre les mots. Vous saurez que la fonctionnalité fonctionne si vous voyez une piste de balayage après le déplacement de votre doigt sur le clavier.

Veuillez noter que cette fonctionnalité peut être difficile à utiliser et à maîtriser en raison de la nature d’un clavier holographique dans lequel vous ne vous inquiétez pas de la résistance à votre doigt (contrairement à un affichage sur téléphone mobile). Nous évaluons cette fonctionnalité pour la version publique, donc vos commentaires sont importants. Si vous trouvez la fonctionnalité utile ou si vous avez des commentaires constructifs, faites-le nous savoir via le [Hub de commentaires](hololens-feedback.md).

### <a name="power-menu-from-start"></a>Menu alimenter à partir du menu Démarrer

Nouveau menu qui permet à l’utilisateur de se déconnecter, d’arrêter et de redémarrer l’appareil. Indicateur de l’écran de démarrage de HoloLens qui indique quand une mise à jour du système est disponible.

#### <a name="how-to-use"></a>Procédure d'utilisation

1. Ouvrez l’écran de démarrage de HoloLens à l’aide du [mouvement de début](hololens2-basic-usage.md#start-gesture) ou dites « aller à démarrer ».

2. Notez l’icône de points de suspension (...) en regard de l’image du profil utilisateur :

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Sélectionnez l’image de profil utilisateur à l’aide de vos mains ou de la commande vocale « Power ».

4. Un menu s’affiche avec les options de déconnexion, de redémarrage ou d’arrêt de l’appareil :

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Sélectionnez les options de menu à déconnecter, redémarrez ou arrêtez votre HoloLens. L’option de déconnexion peut ne pas être disponible si l’appareil est configuré pour un compte [Microsoft (MSA) ou un compte local unique](hololens-identity.md).

6. Faites disparaître le menu en touchant n’importe quel autre endroit ou en fermant le menu Démarrer avec le mouvement de début.

#### <a name="update-indicator"></a>Indicateur de mise à jour

Quand une mise à jour est disponible, l’icône de points de suspension s’affiche pour indiquer qu’un redémarrage installera les options de menu change également pour refléter la présence de la mise à jour.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Plusieurs utilisateurs sont listés sur l’écran de connexion

Auparavant, l’écran de connexion affichait uniquement l’utilisateur connecté le plus récemment, ainsi que le point d’entrée « autre utilisateur ». Nous avons reçu des commentaires des clients qui ne suffisent pas si plusieurs utilisateurs se sont connectés à l’appareil. Ils devaient encore retaper leur nom d’utilisateur, etc.

Introduite dans cette version de Windows Insider, lors de la sélection d’un **autre utilisateur** situé à droite du champ d’entrée du code confidentiel, l’écran de connexion affiche plusieurs utilisateurs ayant déjà été connectés à l’appareil. Cela permet aux utilisateurs de sélectionner leur profil utilisateur, puis de se connecter à l’aide de leurs informations d’identification Windows Hello. Un nouvel utilisateur peut également être ajouté à l’appareil à partir de la page autres utilisateurs via le bouton **Ajouter un compte** .

Quand vous êtes dans le menu autres utilisateurs, le bouton autres utilisateurs affiche le dernier utilisateur connecté à l’appareil. Sélectionnez ce bouton pour revenir à l’écran de connexion de cet utilisateur.

![Valeur par défaut de l’écran de connexion](./images/multiusers1.jpg)

<br>

![Écran de connexion d’autres utilisateurs](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Prise en charge du microphone externe USB-C

> [!IMPORTANT]
> Le branchement d' **un micro USB ne le définit pas automatiquement comme périphérique d’entrée**. Lors de la connexion à un ensemble d’utilisateurs de casque USB-C, l’audio du casque est automatiquement redirigé vers le casque, mais le système d’exploitation HoloLens hiérarchise le groupe de microphones interne au-dessus de tout autre périphérique d’entrée. **Pour utiliser un microphone USB-C, suivez les étapes ci-dessous.**

Les utilisateurs peuvent sélectionner des microphones externes connectés par USB-C à l’aide du panneau Paramètres du **son** . Les microphones USB-C peuvent être utilisés pour appeler, enregistrer, etc.

Ouvrez l’application **paramètres** et sélectionnez   >  **son** système.

![Paramètres audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pour utiliser des microphones externes avec l' **assistance à distance**, les utilisateurs doivent cliquer sur le lien hypertexte « gérer les périphériques audio ».
>
> Ensuite, utilisez la liste déroulante pour définir le microphone externe comme valeur **par défaut** ou **par défaut de communication.** Si vous choisissez la **valeur par défaut** , le microphone externe sera utilisé partout.
>
> Le choix de la **valeur par défaut** de la communication signifie que le microphone externe sera utilisé dans l’assistance à distance et d’autres applications de communication, mais que le tableau du MIC HoloLens peut toujours être utilisé pour d’autres tâches.

![Gérer les périphériques audio](images/usbc-mic-2.png)

<br>

![Définir le microphone par défaut](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Qu’en est-il de la prise en charge du microphone Bluetooth ?

Malheureusement, les microphones Bluetooth ne sont toujours pas pris en charge actuellement sur HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Résolution des problèmes de microphones USB-C

Sachez que certains microtéléphones USB-C se signalent incorrectement comme un microphone *et* un orateur. Il s’agit d’un problème avec le microphone et non avec HoloLens. Lors du branchement de l’un de ces microphones dans HoloLens, le son peut être perdu. Heureusement, il existe un correctif simple.  

Dans **paramètres**  ->    ->  **sons** système, définissez explicitement les haut-parleurs intégrés **(pilote audio de fonctionnalité analogique)** comme **périphérique par défaut**. HoloLens doit se souvenir de ce paramètre même si le microphone est supprimé et reconnecté ultérieurement.

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

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Utiliser les nouveaux paramètres et les applications de périphérie en mode plein écran

Lorsque vous incluez des applications dans des [kiosques](hololens-kiosk.md), un administrateur informatique ajoute souvent l’application à la borne, mais à l’aide de son ID de modèle d’utilisateur d’application (identifiant aumid). Étant donné que l’application de paramètres et l’application Microsoft Edge sont considérées comme de nouvelles applications et que les bornes des applications plus anciennes qui utilisent AUMIDs pour ces applications doivent être mises à jour pour utiliser le nouveau identifiant AUMID.

Lorsque vous modifiez une borne pour inclure les nouvelles applications, nous vous recommandons d’ajouter dans le nouveau identifiant AUMID et de quitter l’ancien. Cela permet de créer une transition facile lorsque les utilisateurs mettent à jour le système d’exploitation et n’ont pas besoin de recevoir de nouvelles stratégies pour continuer à utiliser la borne comme prévu.

| Application                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Ancienne application de paramètres       | HolographicSystemSettings_cw5n1h2txyewy ! Lancement            |
| Nouvelle application de paramètres       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy ! Lancement |
| Ancienne application Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nouvelle application Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe ! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifications du comportement du mode plein écran pour la gestion des défaillances

Dans les versions plus anciennes, si un appareil avait une configuration de kiosque, qui est une combinaison de l’accès attribué global et de l’accès affecté au membre du groupe AAD, si la détermination de l’appartenance au groupe AAD a échoué, l’utilisateur voit le menu «[rien ne s’affiche dans](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)le menu Démarrer ».

À compter de la version Windows Insider, l’expérience de la borne sera de secours à la configuration globale des kiosques (le cas échéant) en cas de défaillances pendant le mode plein écran du groupe AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Nouvelle SettingsURIs pour la visibilité des paramètres de page

Dans [Windows holographique, version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) nous avons ajouté la [stratégie Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages affichées dans l’application Settings. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher des pages spécifiques de l’application Paramètres système d’être visibles ou accessibles, ou de le faire pour toutes les pages, à l’exception de celles spécifiées.

Si vous accédez à la [visibilité des paramètres de page](settings-uri-list.md), vous trouverez des instructions sur l’utilisation de ce fournisseur de services de chiffrement et la liste des URI disponibles dans les versions précédentes.

Dans les builds Windows Insider, nous développons la liste des URI des paramètres disponibles, que les administrateurs peuvent gérer. Certains de ces URI concernent les zones nouvellement disponibles dans la nouvelle application de paramètres. Si vous utilisez la stratégie paramètres/PageVisibilityList, passez en revue la liste suivante et ajustez vos pages autorisées ou bloquées si nécessaire.

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
| Système de stockage > > configurer le sens du stockage         | `ms-settings:storagepolicies`                      |
| Date et & heure de la & > de la langue                        | `ms-settings:dateandtime`                          |
| & du clavier > Language                           | `ms-settings:keyboard`                             |
| Langue du > de la langue du &                           | `ms-settings:language`                             |
| Langue du > de la langue du &                           | `ms-settings:regionlanguage-languageoptions`       |
| Mettre à jour & sécurité > réinitialiser & récupération               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI mis à jour

Auparavant, les deux URI suivants n’empêchent pas l’utilisateur d’accéder directement aux pages indiquées, mais ont uniquement bloqué la page principale des mises à jour. Les éléments suivants ont été mis à jour pour diriger vers leurs pages :

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configuration des diagnostics de secours via l’application paramètres

Désormais, dans l’application paramètres, un utilisateur peut configurer le comportement des [Diagnostics de secours](hololens-diagnostic-logs.md). Dans l’application paramètres, accédez à la page de  ->  **résolution des problèmes** de confidentialité pour configurer ce paramètre.

> [!NOTE]
> Si une stratégie MDM est configurée pour l’appareil, l’utilisateur ne sera pas en mesure de remplacer ce comportement.  

### <a name="share-things-with-nearby-devices"></a>Partager des éléments avec des appareils proches

Partagez des éléments avec près des appareils Windows 10, y compris les PC et les autres appareils HoloLens 2 exécutant les builds de HoloLens Insider 20279.1006 +. Vous pouvez l’essayer dans **paramètres**  ->  **système**  ->  **partagé expériences** pour partager des fichiers ou des URL d’un HoloLens à un PC. Pour plus d’informations, consultez la rubrique Comment [partager des éléments avec des appareils proches dans Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Cette fonctionnalité peut être gérée via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-update-troubleshooter"></a>Nouveau dépanneur de mise à jour du système d’exploitation

En plus des dépannages précédents dans l’application paramètres, un nouvel utilitaire de résolution des problèmes a été ajouté avec l’ajout de la nouvelle application de paramètres pour les mises à jour du système d’exploitation. Accédez à **paramètres**  ->  **mettre à jour la &amp; sécurité**  >  **résoudre les problèmes**  >  **Windows Update** et sélectionnez **Démarrer**. Cela vous permet de collecter des traces tout en reproduisant votre problème avec les mises à jour du système d’exploitation afin d’améliorer la résolution des problèmes avec votre service informatique ou votre support technique.

### <a name="delivery-optimization-preview"></a>Aperçu de l’optimisation de la livraison

Avec cette mise à jour de la gestion des appareils mobiles, Windows holographique pour entreprises active une version préliminaire préliminaire des paramètres d’optimisation de la distribution pour réduire la consommation de bande passante pour les téléchargements à partir de plusieurs appareils HoloLens. Une description plus complète de cette fonctionnalité ainsi que la configuration réseau recommandée sont disponibles ici : [optimisation de la distribution pour les mises à jour de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

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

- La prise en charge de HoloLens est limitée dans cette version préliminaire uniquement aux mises à jour du système d’exploitation.
- Windows holographique for Business prend uniquement en charge les modes de téléchargement HTTP et les téléchargements à partir d’un [point de terminaison de cache connecté Microsoft](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). les modes de téléchargement d’égal à égal et les affectations de groupe ne sont pas pris en charge pour les appareils HoloLens pour l’instant.
- HoloLens ne prend pas en charge l’optimisation du déploiement ou de la distribution pour les points de terminaison Windows Server Update Services.
- La résolution des problèmes nécessite un diagnostic sur le serveur de cache connecté ou la collecte d’une trace sur hololens sur hololens via les **paramètres**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

### <a name="improvements-and-fixes-in-the-update"></a>Améliorations et correctifs de la mise à jour :

- Les [Diagnostics hors connexion](hololens-diagnostic-logs.md#offline-diagnostics) incluent également des informations supplémentaires sur l’appareil pour le numéro de série et la version du système d’exploitation.

### <a name="known-issues-and-work-around"></a>Problèmes connus et contournement

#### <a name="pairing-hololens-to-pc"></a>Appariement de HoloLens à PC

Avant la version 20325,1000 de Windows Insider, lorsqu’un utilisateur avait défini des informations d’identification de jumelage sur [Windows holographique, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou [Windows holographique, version 2004](hololens-release-notes.md#windows-holographic-version-2004) et mis à jour vers les builds Windows Insider, leurs informations d’identification précédentes pour le couplage du système HoloLens avec le PC à des fins de déploiement et de débogage d’applications comme via Visual Studio ne fonctionnaient plus Windows Insider Build 20325,1000 corrige ce problème et ne nécessite aucune action supplémentaire pour reprendre l’utilisation du portail de périphérique.

Les utilisateurs qui ont [flashé leur appareil avec une version Insider](#ffu-download-and-flash-directions) doivent à présent refaire clignoter leurs appareils (20325.1000 + ou version GA) pour associer leurs appareils à leur ordinateur.

Les utilisateurs qui n’ont pas été inscrits auprès de Windows Insider et qui effectuent la mise à jour des fonctionnalités lorsqu’ils sont mis à la disposition générale ne sont pas affectés.


## <a name="start-receiving-insider-builds"></a>Commencer à recevoir des builds Insider

> [!NOTE]
> Si vous n’avez pas récemment mis à jour votre appareil, redémarrez-le pour mettre à jour l’État et vous procurer la build la plus récente.
> - La commande vocale « reboot Device » fonctionne bien. 
> - Vous pouvez également choisir le bouton redémarrer dans paramètres/programme Windows Insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez pu rencontrer, ce qui vous permettra de revenir en arrière.

Sur un appareil HoloLens 2, accédez à **paramètres**  >  **mise à jour & sécurité**  >  **Windows Insider** , puis sélectionnez **prise en main**. Liez le compte que vous avez utilisé pour vous inscrire en tant que Windows Insider.

Windows Insider se déplace désormais vers les canaux. La sonnerie **rapide** deviendra le **canal de développement**, l’anneau **lent** deviendra le **canal bêta** et l’anneau de **version** préliminaire deviendra le **canal de version** préliminaire. Voici à quoi ressemble ce mappage :

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations, consultez [Présentation des canaux Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur les blogs Windows.

Ensuite, sélectionnez **développement actif de Windows**, indiquez si vous souhaitez recevoir des builds du canal de **développement** ou du **canal bêta** , et passez en revue les termes du programme.

Sélectionnez **confirmer > redémarrer maintenant** pour terminer. Une fois que votre appareil a redémarré, accédez à **paramètres > mettre à jour & sécurité > Rechercher les mises à jour** pour obtenir la build la plus récente.

### <a name="update-error-0x80070490-work-around"></a>Mettre à jour l’erreur de contournement 0x80070490
Si vous rencontrez une erreur de mise à jour 0x80070490 lors de la mise à jour sur le canal dev ou bêta, essayez le contournement à terme suivant. Il implique le déplacement de votre canal Insider, la sélection de la mise à jour, puis le déplacement de votre canal Insider.

#### <a name="stage-one---release-preview"></a>Version préliminaire de l’étape 1
1.  Paramètres, mettre à jour & Security, programme Windows Insider, sélectionner la **version préliminaire du canal**.
2.  Paramètres, mettre à jour & sécurité, Windows Update, **Rechercher les mises à jour**. Après la mise à jour, passez à l’étape 2.

#### <a name="stage-two---dev-channel"></a>Deuxième étape-canal de développement
1. Paramètres, mettre à jour & Security, programme Windows Insider, sélectionner un **canal de développement**.
2. Paramètres, mettre à jour & sécurité, Windows Update, **Rechercher les mises à jour**.

## <a name="ffu-download-and-flash-directions"></a>FFU téléchargement et itinéraires Flash
Pour effectuer un test avec un FFU signé par un vol, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU de vol signé.
1. Sur PC :

    1. Téléchargez FFU sur votre ordinateur à partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installez ARC (complément de récupération avancé) à partir du Microsoft Store : [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Sur HoloLens-Flight Unlock : ouvrir les **paramètres**  >  **mettre à jour &**  >  **programme Windows Insider** , puis s’inscrire et redémarrer l’appareil.

1. Flash FFU : vous pouvez désormais faire clignoter le FFU de vol signé à l’aide d’ARC.

## <a name="provide-feedback-and-report-issues"></a>Fournir des commentaires et signaler des problèmes

Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour fournir des commentaires et signaler des problèmes. L’utilisation de feedback Hub garantit que toutes les informations de diagnostic nécessaires sont incluses pour aider nos ingénieurs à déboguer et résoudre rapidement le problème.  Les problèmes liés à la version chinoise et japonaise de HoloLens doivent être signalés de la même façon.

> [!NOTE]
> Veillez à accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).

## <a name="note-for-developers"></a>Remarque pour les développeurs

Nous vous invitons à essayer de développer vos applications à l’aide des versions Insider de HoloLens.  Consultez la [documentation du développeur HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds d’initié de HoloLens.  Vous pouvez utiliser les mêmes builds Unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.

## <a name="stop-receiving-insider-builds"></a>Arrêter de recevoir les builds Insider

Si vous ne souhaitez plus recevoir les versions Insider de Windows holographique, vous pouvez choisir de vous désabonner quand votre HoloLens exécute une génération de production, ou vous pouvez [récupérer votre appareil](hololens-recovery.md) à l’aide de l’Assistant de récupération avancé pour récupérer votre appareil sur une version non-Insider de Windows holographique.

> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui annulent l’inscription à partir de la version préliminaire d’Insider, après la réinstallation manuelle d’une nouvelle version préliminaire, rencontrent un écran bleu. Ensuite, ils doivent récupérer manuellement leur appareil. Pour plus d’informations sur si vous pourriez être affecté ou non, consultez plus d’informations sur ce [problème connu](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Pour vérifier que votre HoloLens exécute une build de production :

1. Accédez à **paramètres > système > à propos** de et recherchez le numéro de Build.

1. [Consultez les notes de publication pour les numéros de version de production](hololens-release-notes.md).

Pour refuser les builds Insider :

1. Sur un HoloLens exécutant une build de production, accédez à **paramètres > mettre à jour & sécurité > programme Windows Insider**, puis sélectionnez **arrêter les builds Insider**.

1. Suivez les instructions pour désinscrire votre appareil.
