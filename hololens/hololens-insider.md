---
title: Insider Preview pour MicrosoftHoloLens
description: Découvrez comment commencer avec les builds Insider et fournir des commentaires précieux pour notre prochaine mise à jour majeure du système d’exploitation pour HoloLens.
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
ms.date: 2/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 885f9a841c5f59f2816667256de0856f8a1f2612
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340536"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans les dernières builds Insider Preview pour HoloLens ! Il est simple de commencer [et](hololens-insider.md#start-receiving-insider-builds) de fournir des commentaires précieux pour notre prochaine mise à jour majeure du système d’exploitation pour HoloLens.

## Notes de publication de Windows Insider

Nous sommes ravis de commencer à faire une nouvelle fois la mise à l’essai de nouvelles fonctionnalités pour les Windows Insiders. Les nouvelles builds seront mises en version d’essai vers le canal de développement pour les dernières mises à jour. Nous continuerons à mettre à jour cette page à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider.  Soyez ravis et prêt à combiner ces mises à jour dans votre réalité.

> [!IMPORTANT]
> Si vous utilisiez précédemment l’application Paramètres ou l’application Microsoft Edge dans un kiosque, nous avons remplacé ces applications par de nouvelles applications qui utilisent un ID d’application différent. Nous vous encourageons vivement à lire les [nouveaux AUMID pour les nouvelles applications en mode plein](#use-the-new-settings-and-edge-apps-in-kiosk-modes) écran ci-dessous. Cela vous permet de continuer à avoir l’application Paramètres dans votre kiosque ou d’inclure la nouvelle application Microsoft Edge.

<br>

| Nom de la fonctionnalité                                              | Description courte                                                                      | Disponible dans build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nouveau MicrosoftEdge](#introducing-the-new-microsoft-edge) | Le nouveau Microsoft Edge basé sur Chromium est désormais disponible pour HoloLens 2                         | 20279.1006 |
| [WebXR et 360 Viewer](#webxr-and-360-viewer)             | Essayer les expériences web immersives et la lecture vidéo 360                                           | 20289.1000 |
| [Nouvelle application Paramètres](#new-settings-app)                     | L’application Paramètres héritée est remplacée par une version mise à jour avec de nouvelles fonctionnalités et de nouveaux paramètres | 20279.1006 |
| [Étalonnage des couleurs d’affichage](#display-color-calibration)   | Sélectionner un profil de couleur de remplacement pour votre affichage HoloLens 2                                | 20293.1000 |
| [S sélectionneur d’application par défaut](#default-app-picker)                 | Choisir l’application à lancer pour chaque type de fichier ou de lien                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Un raccourci vers l’application web Office est désormais répertorié dans « Toutes les applications »                                   | 20279.1006 |
| [Balayage pour taper](#swipe-to-type)                           | Utilisez la pointe de votre doigt pour « balayer » les mots sur le clavier holographique                        | 20279.1006 |
| [Prise en charge du microphone externe USB-C](#usb-c-external-microphone-support) | Utilisez des microphones USB-C pour les applications et/ou Remote Assist.| 20279.1006 |
| [Nouveaux AUMID pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs pour les nouvelles applications Paramètres et Edge | 20279.1006 |
| [New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Plus de 20 nouvelles paramètresURIs pour la stratégie Paramètres/PageVisibilityList | 20289.1000 |
| [Amélioration du mode plein écran lors de l’échec de la remise](#kiosk-mode-behavior-changes-for-handling-of-failures) | Le mode plein écran recherche l’accès affecté global avant le menu Démarrer vide. | 20279.1006 |
| [Configurer les diagnostics de retour](#configuring-fallback-diagnostics-via-settings-app) | Définition du comportement de diagnostic de retour dans l’application Paramètres | 20279.1006 |
| [Partager des éléments avec des appareils à proximité](#share-things-with-nearby-devices) | Partager des fichiers ou DES URL à partir d’un HoloLens sur un PC | 20279.1006 |
| [Nouvelle résolution des problèmes de mise à jour du système d’exploitation](#new-os-update-troubleshooter) | Nouvel dépannage dans paramètres pour les mises à jour du système d’exploitation | 20279.1006 |
| [Améliorations et correctifs de la mise à jour](#improvements-and-fixes-in-the-update) | Correctifs supplémentaires dans la mise à jour. | 20279.1006 |

### Présentation du nouveau Microsoft Edge

![Animation du logo Microsoft Edge hérité vers le nouveau logo Microsoft Edge](images/new-edge.gif)

Le nouveau Microsoft Edge adopte le projet [open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) pour améliorer la compatibilité pour les clients et réduire la fragmentation du web pour les développeurs web.

Avec cet aperçu Insider, le nouveau Microsoft Edge est disponible pour la première fois pour les clients HoloLens 2 ! Bien que le nouveau Microsoft Edge remplace finalement l’ancien Microsoft Edge sur HoloLens 2, les deux navigateurs sont actuellement disponibles pour les Insiders. Veuillez partager vos commentaires et **** bogues avec notre équipe via la fonctionnalité Envoyer des commentaires dans le nouveau Microsoft Edge ou via [le Hub de commentaires.](hololens-feedback.md)

![Nouvelle capture d’écran de Microsoft Edge](images/new-edge-ui.png)

#### Lancement du nouveau Microsoft Edge

Il existe deux versions de Microsoft Edge disponibles pour les Insiders : la nouvelle icône Microsoft Edge de Microsoft Edge (représentée par une icône bleu et vert de la maison) et l’icône ![ Microsoft Edge héritée (représentée par l’icône « e » ](images/new_edge_logo.png) blanche). Le nouveau Microsoft Edge est épinglé au menu Démarrer et se lance automatiquement lorsque vous activez un lien web. Si vous souhaitez revenir à l’utilisation de Microsoft Edge hérité en tant que navigateur web par défaut, consultez les instructions ci-dessous pour réinitialiser [les applications par défaut.](#default-app-picker)

> [!NOTE]
> Lorsque vous lancez le nouveau Microsoft Edge sur HoloLens 2 pour la première fois, vos paramètres et données sont importés à partir de Microsoft Edge hérité. Si vous continuez à utiliser l’ancien Microsoft Edge après avoir lancé le nouveau Microsoft Edge, ces nouvelles données ne seront pas synchronisées entre l’ancien microsoft Edge et le nouveau Microsoft Edge.

#### Configuration des paramètres de stratégie pour le nouveau Microsoft Edge

Le nouveau Microsoft Edge offre aux administrateurs informatiques un ensemble de stratégies de navigateur beaucoup plus large sur HoloLens 2 qu’auparavant disponible avec Microsoft Edge hérité.

Voici quelques ressources utiles pour en savoir plus sur la gestion des paramètres de stratégie pour le nouveau Microsoft Edge :

- [Configurer les paramètres de stratégie MicrosoftEdge avec MicrosoftIntune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mappage de l’Ancienne version de Microsoft Edge vers la stratégie Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mappage de Google Chrome vers la stratégie Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentation [complète de Microsoft Edge Entreprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> En raison du volume de stratégies de navigateur pris en charge par le nouveau Microsoft Edge, notre équipe ne peut pas garantir que chaque nouvelle stratégie fonctionne sur HoloLens 2. Toutefois, nous avons testé et confirmé que le nouvel équivalent Microsoft Edge de chaque stratégie Microsoft Edge héritée précédemment prise en charge sur HoloLens 2 fonctionne comme prévu. Voir [mappage des](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) stratégies héritées de Microsoft Edge avec Microsoft Edge pour trouver le nouvel équivalent Microsoft Edge de chaque stratégie de navigateur Microsoft Edge héritée que vous utilisiez avec HoloLens 2.
>
> Il existe au moins deux nouvelles stratégies Microsoft Edge dont nous savons qu’elles ne *fonctionneront* pas avec HoloLens 2 :
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### À quoi s’attendre du nouveau Microsoft Edge sur HoloLens 2

Étant donné que le nouveau Microsoft Edge est une application Win32 native avec une nouvelle couche d’adaptateur UWP qui lui permet de s’exécuter sur des appareils UWP uniquement tels que HoloLens 2, certaines fonctionnalités peuvent ne pas être immédiatement disponibles. Nous allons prendre en charge de nouveaux scénarios et fonctionnalités au cours des prochains mois. Vérifiez donc cet espace pour obtenir des informations à jour.

**Scénarios et fonctionnalités qui devraient fonctionner :**
- Première expérience d’utilisateur, se connectez au profil et synchronisez
- Les sites web doivent s’restituer et se comporter comme prévu
- La plupart des fonctionnalités de navigateur (Favoris, Historique, etc.) doivent fonctionner comme prévu.
- Mode sombre
- Installation d’applications web sur l’appareil
- Installation d’extensions (n’hésitez pas à nous faire savoir si vous utilisez des extensions qui ne fonctionnent pas correctement sur HoloLens 2)
- Affichage et marquage d’un fichier PDF
- Son spatial à partir d’une seule fenêtre de navigateur
- Mise à jour automatique et manuelle du navigateur
- Enregistrement d’un fichier PDF à partir du menu Imprimer (à l’aide de l’option « Enregistrer au PDF » )

**Scénarios et fonctionnalités bientôt à venir :**
- Extension WebXR et 360 Viewer
- Restauration de contenu pour corriger la fenêtre lors de la navigation dans plusieurs fenêtres placées dans votre environnement

**Scénarios et fonctionnalités qui ne devraient pas fonctionner :**
- Son spatial à partir de plusieurs fenêtres avec flux audio simultanés
- « Regardez- le, dites-le »
- Impression

**Principaux problèmes de navigateur connus :**
- La réinitialisation de votre appareil supprimera le nouveau Microsoft Edge
- L’aperçu de la loupe dans le clavier holographique affiche un contenu incorrect

#### Canaux Microsoft Edge Insider

L’équipe Microsoft Edge met trois canaux d’aperçu à la disposition de la communauté Edge Insider : Bêta, Dev et Canary. L’installation d’un canal d’aperçu ne désinstalle pas la version finale de Microsoft Edge sur votre HoloLens 2, et vous pouvez en installer plusieurs en même temps. 

Visitez la page [d’accueil du Microsoft Edge Insider](https://www.microsoftedgeinsider.com) pour en savoir plus sur la communauté Edge Insider. Pour en savoir plus sur les différents canaux Edge Insider et commencer, visitez la page de téléchargement [Edge Insider.](https://www.microsoftedgeinsider.com/download)

Il existe quelques méthodes disponibles pour l’installation des canaux Insider de Microsoft Edge sur HoloLens 2 :

**Installation directe sur l’appareil (actuellement disponible uniquement pour les appareils non utilisés)**
  1. Sur votre HoloLens 2, visitez la [page de téléchargement Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Sélectionnez **le bouton Télécharger pour HoloLens 2** pour le canal Edge Insider que vous souhaitez installer.
  1. Lancez le fichier .msix téléchargé à partir de la file d’attente de téléchargement Edge ou du dossier « Téléchargements » de votre appareil (à l’aide de l’Explorateur de fichiers).
  1. [Le programme d’installation](app-deploy-app-installer.md) de l’application se lance.
  1. Sélectionnez le **bouton** Installer.
  1. Une fois l’installation réussie, microsoft Edge Beta, Dev ou Canary est une entrée distincte dans la liste Toutes les applications du menu Démarrer. ****

**Installation via PC avec Windows Device Portal (nécessite que le [mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) développeur soit activé sur HoloLens 2)**
  1. Sur votre PC, visitez la [page de téléchargement Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Sélectionnez **le bouton de flèche** vers le bas en haut du bouton « Télécharger pour Windows 10 » pour le canal Edge Insider que vous souhaitez installer.
  1. Sélectionnez **HoloLens 2 dans** le menu déroulant.
  1. Enregistrez le fichier .msix dans le dossier « Téléchargements » de votre PC (ou un autre dossier que vous pouvez facilement trouver).
  1. Utilisez [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) sur votre PC pour installer le fichier .msix téléchargé sur HoloLens 2.
  1. Une fois l’installation réussie, microsoft Edge Beta, Dev ou Canary est une entrée distincte dans la liste Toutes les applications du menu Démarrer. ****

> [!NOTE]
> Pendant cette prévisualisation de Windows Insider pour HoloLens 2, la version de Microsoft Edge sur votre appareil peut être supérieure à celle disponible dans certains (ou tous) des canaux Microsoft Edge Insider. Cela permet de s’assurer que les nouvelles fonctionnalités et correctifs ciblant spécifiquement le navigateur web sur HoloLens 2 sont en train d’atteindre nos Windows Insiders aussi rapidement que possible. Peu de temps après la publication publique de la prochaine mise à jour Windows, les builds du canal Insider de Microsoft Edge dépasseront et resteront en avance sur la version de Microsoft Edge sur votre HoloLens 2.

### WebXR et 360 Viewer

*Ajouté dans Windows Insider build 20289.1000*

Le nouveau Microsoft Edge inclut la prise en charge de WebXR, qui est la nouvelle norme pour la création d’expériences web immersives (en remplaçant WebVR). De nombreuses expériences web immersives ont été conçues avec la vr à l’esprit (elles remplacent votre champ de vue par un environnement virtuel), mais ces expériences sont également pris en charge par HoloLens 2. La norme WebXR permet également des expériences web immersives augmentées et de réalité mixte qui utilisent votre environnement physique. À mesure que les développeurs passent plus de temps avec WebXR, nous prévoyons que de nouvelles expériences immersives de réalité mixte et augmentée arriveront pour que les clients HoloLens 2 essaient !

L’extension 360 Viewer repose sur WebXR et s’installe automatiquement avec le nouveau Microsoft Edge sur HoloLens 2. Cette extension web vous permet de vous plonger dans des vidéos à 360 degrés. YouTube propose la plus grande sélection de 360 vidéos. Nous vous encourageons donc à commencer par là.

#### Utilisation de WebXR

1. Accédez à un site web avec la prise en charge WebXR.
1. Sélectionnez **le bouton Entrer VR** sur le site web. L’emplacement et la représentation visuelle de ce bouton peuvent varier selon le site web, mais il peut ressembler à :

    ![Exemple de bouton Entrer vr](images/75px-enter-vr.png)

1. La première fois que vous essayez de lancer une expérience WebXR sur un domaine spécifique, le navigateur demande son consentement pour entrer une vue immersive, sélectionnez **Autoriser**.
1. Utilisez [les mouvements HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) pour manipuler l’expérience.
1. Si l’expérience ne comprend pas de bouton **Quitter,** utilisez [le](hololens2-basic-usage.md#start-gesture) mouvement de démarrage pour revenir à la maison.

**Exemples WebXR recommandés**
- Visionneuse 360 (voir la section suivante)
- [Dinosaures XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### Utilisation de la visionneuse 360

1. Accédez à une vidéo à 360 degrés sur YouTube.
1. Dans le cadre de la vidéo, sélectionnez le bouton du casque de réalité mixte :

    ![Bouton pour activer la visionneuse 360](images/enter-360-viewer.jpg)

1. La première fois que vous essayez de lancer 360 Viewer sur un domaine spécifique, le navigateur demande son consentement pour entrer une vue immersive. Sélectionnez **Autoriser**.
1. [Appuyez sur](hololens2-basic-usage.md#select-using-air-tap) l’air pour faire monter les contrôles de lecture. Utilisez les rayons de la main et [l’effet d’air](hololens2-basic-usage.md#select-using-air-tap) pour lire/suspendre, ignorer l’avant/l’arrière, activer/désactiver les légendes ou arrêter l’expérience (qui quitte la vue immersive). Les contrôles de lecture disparaîtront après quelques secondes d’inactivité.

#### Principaux problèmes connus de WebXR et de 360 visionneuses
- Dans les expériences WebXR, les hologrammes peuvent se déplacer ou s’incliner lorsque vous inclinez la tête ou que vous vous déplacez dans votre environnement.
- En fonction de la complexité de l’expérience WebXR, le framerate peut être bas ou saccadé.
- Les joints de main clairement exprimés ne sont pas encore disponibles dans WebXR.
- Lorsque vous quittez une expérience WebXR ou 360 Viewer, la réapparition des hologrammes dans la maison virtuelle peut prendre au moins 30 secondes.
- 360 vidéos provenant de sites web autres que YouTube peuvent ne pas fonctionner comme prévu.
- Si 360 vidéos n’entrent pas en vue immersive (ou si le bouton du casque de réalité mixte n’apparaît pas), essayez d’actualisation de la page.
- Les légendes ne sont pas encore visibles dans la visionneuse 360 sur HoloLens 2.
- La suspension d’une vidéo dans 360 Viewer empêche le rendu de la vidéo (mais la sélection du bouton lire reprend correctement la lecture).
- Le bouton « Vidéo suivante » dans 360 Viewer ne fonctionne pas actuellement.
- Vous pouvez lire des vidéos 2D dans un mode « salle de jeu » immersif, mais la trame sera inférieure à 30 fps.

#### Commentaires sur WebXR et la visionneuse 360

Veuillez partager vos commentaires et bogues avec notre équipe via la fonctionnalité **Envoyer des** commentaires dans le nouveau Microsoft Edge.

### Nouvelle application Paramètres

Avec cette version, nous introduisons une nouvelle version de l’application Paramètres. La nouvelle application Paramètres inclut de nouvelles fonctionnalités et des paramètres étendus pour HoloLens 2 dans les domaines suivants : son, veille power &, réseau & Internet, applications, comptes, options d’accès faciles, etc.

> [!NOTE]
> Étant donné que la nouvelle application Paramètres est distincte de l’application Paramètres héritée, toutes les fenêtres Paramètres que vous avez précédemment placées dans votre environnement seront supprimées lors de la mise à jour.

![Page d’accueil de l’application Nouveaux paramètres](images/new-settings-app.png)

**Nouvelles fonctionnalités et nouveaux paramètres**
- Recherche de paramètres : recherchez les paramètres de la page d’accueil Paramètres à l’aide de mots clés ou du nom du paramètre.
- Son système > :
  - Périphériques audio d’entrée et de sortie : choisissez indépendamment vos périphériques audio d’entrée et de sortie (par exemple, écoutez du contenu audio via un casque Bluetooth ou utilisez un microphone USB-C pour l’entrée audio).
    > [!NOTE]
    > Bluetooth microphones ne sont pas pris en charge par HoloLens 2.
  - Volume d’application : ajustez indépendamment le volume de chaque application.
- Le système > la & veille : choisissez quand l’appareil doit être en veille après une période d’inactivité.
- Système > batterie : activez manuellement le mode économiseur de batterie ou définissez un seuil de batterie à partir duquel le mode économiseur de batterie s’active automatiquement.
- Appareils > USB : vous pouvez désactiver les connexions USB par défaut.
- Réseau & Internet :
  - Les adaptateurs Ethernet USB-C apparaissent désormais dans le réseau & Internet.
  - Les paramètres d’adaptateur Ethernet USB-C sont désormais disponibles, y compris son adresse IP.
  - Vous pouvez désormais activer le mode avion sur HoloLens 2.
- Applications : vous pouvez réinitialiser les applications par défaut utilisées pour les types de fichiers et de liens. Pour plus d’informations, [voir s’il s’est s’il s’est choisi par défaut.](#default-app-picker)
- Les comptes > autres utilisateurs : les propriétaires d’appareils peuvent ajouter des utilisateurs, mettre à niveau les utilisateurs standard vers les propriétaires d’appareils, rétrograder les propriétaires d’appareils en utilisateurs standard et supprimer des utilisateurs.
- Facilité d’accès : modifier la taille du texte et certains effets visuels.

**Problèmes connus**
- Les fenêtres Paramètres précédemment placées seront supprimées (voir la remarque ci-dessus).
- La visite de la page Notifications peut créer un incident sur l’application Paramètres (en cours d’investigation).
- La page Ethernet ne s’affiche actuellement pas (pour être corrigée prochainement).
- Vous ne pouvez plus renommer votre appareil avec l’application Paramètres (les administrateurs informatiques peuvent utiliser des packages d’approvisionnement ou la gestion des périphériques mobiles pour renommer les appareils).
- L’utilisation de la batterie pour le nouveau Microsoft Edge peut ne pas être exacte, en raison de sa nature en tant qu’application de bureau Win32 prise en charge par une couche d’adaptateur UWP (aucun correctif prévu prochainement).

### Étalonnage des couleurs d’affichage

*Ajouté dans Windows Insider build 20293.1000*

Avec ce nouveau paramètre, vous pouvez sélectionner un profil de couleur de remplacement pour votre affichage HoloLens 2. Cela peut aider les couleurs à s’afficher plus précises, en particulier aux niveaux de luminosité d’affichage inférieurs. L’étalonnage de couleur d’affichage se trouve dans l’application Paramètres, sur la page > étalonnage du système.

#### Utilisation de l’étalonnage de couleur d’affichage

1. Lancez **l’application Paramètres** et accédez **à l’étalonnage > système.**
1. Sous **Étalonnage de couleur d’affichage,** sélectionnez le **bouton Exécuter l’étalonnage de couleur d’affichage.**
1. L’expérience d’étalonnage de couleur d’affichage s’affiche et vous encourage à vous assurer que votre visière est à la bonne position.
1. Une fois que vous avez suivi les boîtes de dialogue d’instructions, votre affichage est automatiquement estommé à 30 % de luminosité.
    > [!TIP]
    > Si vous avez des difficultés à voir la scène grisée dans votre environnement, vous pouvez ajuster manuellement le niveau de luminosité de HoloLens 2 à l’aide des boutons de luminosité sur le côté gauche de l’appareil.
1. Sélectionnez les boutons 1 à 6 pour tester instantanément chaque profil de couleur, puis recherchez-en un qui s’affiche le mieux pour vos yeux (cela signifie généralement que le profil qui permet à la scène d’apparaître le plus neutre, avec le motif de nuances de gris et les teintes de couleurs à l’apparence attendue.)

    ![Afficher la scène d’étalonnage des couleurs](images/color-cal-ui.png)
    
1. Lorsque vous êtes satisfait du profil sélectionné, sélectionnez le bouton **& quitter**
1. Si vous préférez ne pas apporter de modifications, sélectionnez le bouton **&** quitter et vos modifications seront annulées.

> [!TIP]
> Voici quelques conseils utiles à garder à l’esprit lors de l’utilisation du paramètre d’étalonnage de couleur d’affichage :
> - Vous pouvez ré-exécuter l’étalonnage de couleur d’affichage à partir des paramètres lorsque vous le souhaitez
> - Si une personne sur l’appareil a déjà utilisé le paramètre pour modifier les profils de couleurs, la date/l’heure de la dernière modification sera reflétée dans la page Paramètres.
> - Lorsque vous ré-exécutez l’étalonnage des couleurs d’affichage, le profil de couleur précédemment enregistré est mis en surbrillon et le profil 0 n’apparaît pas (comme le profil 0 représente le profil de couleur d’origine de l’affichage)
> - Si vous souhaitez rétablir le profil de couleur d’origine de l’affichage, vous pouvez le faire à partir de la page Paramètres (voir comment réinitialiser le [profil de couleur)](#how-to-reset-color-profile)

#### Comment réinitialiser le profil de couleur

Si vous n’êtes pas satisfait du profil de couleur personnalisé enregistré dans votre HoloLens 2, vous pouvez restaurer le profil de couleur d’origine de l’appareil :
1. Lancez **l’application Paramètres** et accédez **à l’étalonnage > système.**
1. Sous **Étalonnage des couleurs**d’affichage, sélectionnez le bouton Réinitialiser **le profil de couleur par** défaut.
1. Votre affichage sera éteint pendant plusieurs secondes lors de sa réinitialisation. Nous vous recommandons également de redémarrer votre appareil *une fois* que l’affichage s’est récommencé (voir [problèmes connus).](#top-display-color-calibration-known-issues)

#### Problèmes connus d’étalonnage de couleur de l’affichage supérieur

- Dans la page Paramètres, la chaîne d’état qui vous indique quand le profil de couleur a été modifié pour la dernière fois est mise à jour jusqu’à ce que vous rechargez cette page de paramètres. 
    - Solution de contournement : sélectionnez une autre page Paramètres, puis sélectionnez à nouveau la page Étalonnage.
- Le bouton « Rétablir le profil de couleur par défaut » ouvre une boîte de dialogue sans texte. Toutefois, le bouton « Réinitialiser » de la boîte de dialogue fonctionne comme prévu.
- Une fois que vous avez sélectionné le bouton « Réinitialiser », votre affichage peut être vide pendant 5 à 10 secondes et vous pouvez remarquer un comportement inattendu dans la maison virtuelle. Veuillez redémarrer votre appareil après avoir utilisé le bouton « Réinitialiser » (nous allons bientôt résoudre ce problème pour redémarrer automatiquement votre appareil et mettre à jour le texte paramètres en conséquence).
- Si votre HoloLens 2 est mis en veille lors de l’exécution de l’étalonnage de couleur d’affichage, il reprendra ultérieurement dans la maison virtuelle et votre niveau de luminosité d’affichage sera toujours estommé.
- Vous devrez peut-être essayer d’appuyer plusieurs fois sur les boutons de luminosité sur le côté gauche de votre appareil pour qu’ils fonctionnent comme prévu.

### S sélectionneur d’application par défaut

Lorsque vous activez un lien hypertexte ou ouvrez un type de fichier avec plusieurs applications installées, ce qui le prend en charge, une nouvelle fenêtre s’ouvre et vous invite à sélectionner l’application installée qui doit gérer le type de fichier ou de lien. Dans cette fenêtre, vous pouvez également choisir que l’application sélectionnée gère le fichier ou le type de lien « Une seule fois » ou « Toujours ».

![Fenêtre du s picker d’application](images/default-app-picker.png)

Si vous choisissez « Toujours », mais que vous souhaitez ultérieurement modifier l’application qui gère un fichier ou un type de lien particulier, vous pouvez réinitialiser vos valeurs par défaut enregistrées dans **Paramètres > Applications.** Faites défiler vers le bas **** de la page et sélectionnez le bouton Effacer sous « Applications par défaut pour les types de fichiers » et/ou « Applications par défaut pour les types de liens ». Contrairement au paramètre similaire sur les PC de bureau, vous ne pouvez pas réinitialiser les valeurs par défaut des types de fichiers individuels.

### Office Web App

L’application web Office a été ajoutée à la liste « Toutes les applications » dans le menu Démarrer. Cette application web peut également être épinglée au démarrage ou désinstallée. Étant donné qu’il s’agit d’une application web, sa fonctionnalité correspond exactement à ce que vous ariez fait en visitant https://www.office.com . La fonctionnalité d’Application web Office est disponible uniquement lorsque votre HoloLens 2 dispose d’une connexion Internet active.

### Balayage pour taper

Certains clients trouvent plus rapide de « taper » sur des claviers virtuels en faisant glisser la forme du mot qu’ils ont l’intention de taper, et nous prévisualiserons cette fonctionnalité pour le clavier holographique. Vous pouvez balayer un mot à la fois en passant la pointe de votre doigt dans le plan du clavier holographique, en faisant glisser la forme du mot, puis en retirez la pointe de votre doigt du plan du clavier. Vous pouvez balayer les mots de suivi sans avoir à appuyer sur la barre d’espace en supprimant votre doigt du clavier entre les mots. Vous savez que la fonctionnalité fonctionne si vous voyez une trace de balayage après le mouvement de votre doigt sur le clavier.

Notez que cette fonctionnalité peut être difficile à utiliser et à maîtriser en raison de la nature d’un clavier holographique dans lequel vous ne vous sentez pas résistant à votre doigt (contrairement à un affichage de téléphone mobile). Nous évaluons cette fonctionnalité pour la publication publique. Vos commentaires sont donc importants . que vous trouviez la fonctionnalité utile ou que vous avez des commentaires de votre part, faites-le nous savoir via [le Hub de commentaires.](hololens-feedback.md)

### Prise en charge du microphone externe USB-C

> [!IMPORTANT]
> Le branchement **d’un micro USB ne le définira**pas automatiquement comme périphérique d’entrée. Lorsque vous branchez un ensemble de casques USB-C, les utilisateurs observent que l’audio du casque est automatiquement redirigé vers le casque, mais le système d’exploitation HoloLens hiérarchise le groupe de microphones interne au-dessus de tout autre périphérique d’entrée. **Pour utiliser un microphone USB-C, suivez les étapes ci-dessous.**

Les utilisateurs peuvent sélectionner des microphones externes connectés USB-C à l’aide du **panneau** Paramètres sonores. Les microphones USB-C peuvent être utilisés pour les appels, l’enregistrement, etc.

Ouvrez **l’application Paramètres** et sélectionnez **Son**  ->  **système.**

![Paramètres audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pour utiliser des microphones externes avec **Remote Assist,** les utilisateurs doivent cliquer sur le lien hypertexte « Gérer les périphériques sonores ».
>
> Ensuite, utilisez la drop-down pour définir le microphone externe sur **Default ou** **Communications Default.** Le **choix** par défaut signifie que le microphone externe sera utilisé partout.
>
> Choisir **Communications Par** défaut signifie que le microphone externe sera utilisé dans Remote Assist et d’autres applications de communication, mais que le groupe de micros HoloLens peut toujours être utilisé pour d’autres tâches.

![Gérer les périphériques sonores](images/usbc-mic-2.png)

<br>

![Définir le microphone par défaut](images/usbc-mic-3.jpg)

#### Qu’en est-il Bluetooth prise en charge du microphone ?

Malheureusement, Bluetooth microphones ne sont toujours pas pris en charge actuellement sur HoloLens 2.

#### Résolution des problèmes de microphones USB-C

N’ignorez pas que certains microphones USB-C se signalent de manière incorrecte en tant que *microphone* et haut-parleur. Il s’agit d’un problème avec le microphone et non avec HoloLens. Lorsque vous branchez l’un de ces microphones dans HoloLens, le son peut être perdu. Heureusement, il existe un correctif simple.  

Dans **settings**System Sound , définissez explicitement les haut-parleurs intégrés  ->  ****  ->  **** **(pilote audio de** fonctionnalité analogique) comme **périphérique par défaut.** HoloLens doit mémoriser ce paramètre même si le microphone est supprimé et reconnecté ultérieurement.

![Résolution des problèmes de microphones USB-C](images/usbc-mic-4.png)

### Utiliser les nouvelles applications Paramètres et Edge en mode plein affichage

Lorsque vous ajoutez des applications dans des [kiosques,](hololens-kiosk.md)un administrateur informatique ajoute souvent l’application au kiosque, mais en utilisant son ID de modèle utilisateur d’application (AUMID). Étant donné que l’application Paramètres et l’application Microsoft Edge sont considérées comme de nouvelles applications et sont différentes des anciennes applications Kiosks qui utilisent des AUMID pour ces applications, elles devront être mises à jour pour utiliser le nouvel AUMID.

Lors de la modification d’un kiosque pour inclure les nouvelles applications, nous vous recommandons d’ajouter le nouvel AUMID et de laisser l’ancienne. Cela crée une transition facile lorsque les utilisateurs met à jour le système d’exploitation et n’ont pas besoin de recevoir de nouvelles stratégies pour continuer à utiliser le kiosque comme prévu.

| Application                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Ancienne application Paramètres       | HolographicSystemSettings_cw5n1h2txyewy ! Application            |
| Application Nouveaux paramètres       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Application |
| Ancienne application Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nouvelle application Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe ! MSEDGE    |

### New SettingsURIs for Page Settings Visibility

Dans [Windows Holographic, version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) nous avons ajouté la stratégie [Paramètres/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour limiter les pages visibles dans l’application Paramètres. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées.

Si vous visitez [La visibilité des paramètres](settings-uri-list.md)de page, vous trouverez des instructions pour utiliser ce CSP et la liste des URIs disponibles dans les versions précédentes.

Dans les builds Windows Insider, nous étendons la liste des URL de paramètres disponibles, que les administrateurs informatiques peuvent gérer. Certains de ces URIs sont pour les zones nouvellement disponibles dans la nouvelle application Paramètres. Si vous utilisez la stratégie Paramètres/PageVisibilityList, examinez la liste suivante et ajustez vos pages autorisées ou bloquées selon vos besoins.

> [!NOTE]
> **Deprecated: ms-settings:network-proxy**
>
> Une page de paramètres est dépréciée dans ces builds plus nouvelles. L’ancienne page **& proxy Internet**  >  **** n’est plus disponible en tant que paramètre global. Les nouveaux paramètres de proxy par connexion se trouvent sous Propriétés Réseau **&** Wi-Fi Internet ou Propriétés Réseau  >  ****  >  **** **&**  >  **Internet Ethernet**  >  ****.

<br>

| Page de paramètres                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Fonctionnalités > applications & applications                               | `ms-settings:appsfeatures`                         |
| Fonctionnalités > applications & applications > options avancées          | `ms-settings:appsfeatures-app`                     |
| Applications > cartes hors connexion                                  | `ms-settings:maps`                                 |
| Applications > cartes hors connexion > télécharger des cartes                  | `ms-settings:maps-downloadmaps`                    |
| Appareils > souris                                      | `ms-settings:mouse`                                |
| Appareils > USB                                        | `ms-settings:usb`                                  |
| Mode & internet > avion                   | `ms-settings:network-airplanemode`                 |
| Confidentialité > général                                    | `ms-settings:privacy-general`                      |
| Confidentialité et >'entrée manuscrite & personnalisation de la saisie             | `ms-settings:privacy-speechtyping`                 |
| Motion de > confidentialité                                     | `ms-settings:privacy-motion`                       |
| Bordures de la > de confidentialité                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Captures d’écran > confidentialité et applications                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batterie de > système                                     | `ms-settings:batterysaver`                         |
| Batterie de > système                                     | `ms-settings:batterysaver-settings`                |
| Son système >                                       | `ms-settings:sound`                                |
| Préférences de > système > volume d’application et d’appareil | `ms-settings:apps-volume`                          |
| Système > son > gérer les périphériques sonores              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Heure et & langue > date & heure                        | `ms-settings:dateandtime`                          |
| Heure &'> clavier                           | `ms-settings:keyboard`                             |
| Heure & langue > langue                           | `ms-settings:language`                             |
| Heure & langue > langue                           | `ms-settings:regionlanguage-languageoptions`       |
| Mettre à jour & sécurité et > réinitialiser & récupération               | `ms-settings:reset`                                |

#### URIs mis à jour

Auparavant, les deux URIs suivants ne dirigeaient pas un utilisateur directement vers les pages indiquées, mais bloquaient uniquement la page principale des mises à jour. Les éléments suivants ont été mis à jour pour être directement dans leurs pages :

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### Modifications du comportement du mode plein écran pour la gestion des défaillances

Dans les builds plus anciennes, si un appareil avait une configuration kiosque, qui est une combinaison d’accès affecté global et[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)d’accès affecté au membre du groupe AAD, en cas d’échec de la détermination de l’appartenance au groupe AAD, l’utilisateur ne voit « rien affiché dans le menu Démarrer ».

À partir de la version Windows Insider, l’expérience plein écran est de retour à la configuration kiosque globale (le cas présent) en cas de pannes pendant le mode plein écran du groupe AAD.

### Configuration des diagnostics de retour via l’application Paramètres

Désormais, dans l’application Paramètres, un utilisateur peut configurer le comportement des [diagnostics de base.](hololens-diagnostic-logs.md) Dans l’application Paramètres, **accédez**à la page Résolution des problèmes de confidentialité  ->  **** pour configurer ce paramètre.

> [!NOTE]
> Si une stratégie de gestion des périphériques de gestion des périphériques est configurée pour l’appareil, l’utilisateur ne peut pas remplacer ce comportement.  

### Partager des éléments avec des appareils à proximité

Partagez des éléments avec les appareils Windows 10 proches, y compris les PC et les autres appareils HoloLens 2 exécutant HoloLens Insider builds 20279.1006+. Vous pouvez l’essayer dans **Paramètres**System Shared Experiences pour partager des fichiers ou DES URL à partir  ->  ****  ->  **** d’un HoloLens sur un PC. Pour plus d’informations, voir comment partager des éléments avec des appareils à [proximité dans Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Cette fonctionnalité peut être gérée via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### Nouvelle résolution des problèmes de mise à jour du système d’exploitation

Outre les dépannages précédents dans l’application Paramètres, un nouvel dépannage a été ajouté avec l’ajout de la nouvelle application Paramètres pour les mises à jour du système d’exploitation. Accédez à **Paramètres -** Résoudre les problèmes  ->  ** &amp; de**sécurité  ->  **de**  ->  **Windows Update** et sélectionnez **Démarrer.** Cela vous permet de collecter des suivis lors de la reproduction de votre problème avec les mises à jour du système d’exploitation pour faciliter la résolution des problèmes avec votre support technique ou votre système d’exploitation.

### Améliorations et correctifs de la mise à jour :

- [Les diagnostics hors connexion incluent](hololens-diagnostic-logs.md#offline-diagnostics) également des informations supplémentaires sur l’appareil pour le numéro de série et la version du système d’exploitation.






## Commencer à recevoir des builds Insider

> [!NOTE]
> Si vous n’avez pas mis à jour récemment, redémarrez votre appareil pour mettre à jour l’état et obtenir la dernière build.
> - La commande vocale « Appareil de redémarrage » fonctionne bien. 
> - Vous pouvez également choisir le bouton de redémarrage dans Paramètres/Programme Windows Insider.
>
> Nous avons rencontré un bogue sur le back end que vous avez peut-être rencontré, ce qui vous permettra de reprendre le suivi.

Sur un appareil HoloLens 2, sélectionnez Mise à jour des **paramètres**& programme Windows Insider sécurité  >  ****  >  **** et **sélectionnez Commencer.** Liez le compte que vous avez utilisé pour vous inscrire en tant que Windows Insider.

Windows Insider est désormais en train de passer aux canaux. **L’anneau** Rapide deviendra le canal **** dev, **** l’anneau Lent deviendra le canal bêta **et**l’anneau Release **Preview** deviendra le canal d’aperçu de **publication.** Voici à quoi ressemble ce mappage :

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations, voir [Présentation des canaux Windows Insider sur](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) les blogs Windows.

Ensuite, sélectionnez **Développement actif de Windows,** choisissez **** si vous **** souhaitez recevoir les builds du canal de développement ou du canal bêta, puis examinez les termes du programme.

Sélectionnez **Confirmer > redémarrer maintenant** pour terminer. Une fois que votre appareil a redémarrage, rendez-vous sur **Paramètres >** Mise à jour & sécurité > recherchez les mises à jour pour obtenir la dernière build.

### Erreur de mise à jour 0x80070490 de travail
Si vous rencontrez une erreur de mise à 0x80070490 lors de la mise à jour sur le canal dev ou bêta, essayez la procédure à court terme suivante. Cela implique le déplacement de votre canal Insider, la sélection de la mise à jour, puis le déplacement de votre canal Insider.

#### Étape 1 - Version d’aperçu
1.  Paramètres, Mettre à jour & sécurité, programme Windows Insider, sélectionner **Canal release Preview**.
2.  Paramètres, Mise à jour & sécurité, Windows Update, **Vérifier les mises à jour**. Après la mise à jour, continuez à l’étape 2.

#### Étape 2 : Canal de développement
1. Paramètres, Mettre à jour & sécurité, programme Windows Insider, sélectionner **Canal de développement**.
2. Paramètres, Mise à jour & sécurité, Windows Update, **Vérifier les mises à jour**.

## Instructions de téléchargement et de flash FFU
Pour tester avec une ffu signée par vol, vous devez d’abord déverrouiller votre appareil avant de flasher la ffu signée par la vol.
1. Sur PC :

    1. Téléchargez ffu sur votre PC à partir [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) de .
    
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store : [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Sur HoloLens - Déverrouillage de version d’essai : ouvrez la mise à jour des **paramètres**& programme Windows Insider de sécurité, puis inscrivez-vous,  >  ****  >  **** redémarrez l’appareil.

1. Flash FFU : vous pouvez désormais flasher la FFU signée à l’aide d’ARC.

## Fournir des commentaires et signaler des problèmes

Veuillez utiliser [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour fournir des commentaires et signaler les problèmes. L’utilisation du Hub de commentaires garantit que toutes les informations de diagnostic nécessaires sont incluses pour aider nos ingénieurs à déboguer et résoudre rapidement le problème.  Les problèmes avec la version chinoise et japonaise de HoloLens doivent être signalés de la même façon.

> [!NOTE]
> N’oubliez pas d’accepter l’invite qui vous demande si vous souhaitez que le Hub de commentaires accède à votre dossier Documents (sélectionnez **Oui** lorsque vous y êtes invité).

## Remarque pour les développeurs

Nous vous invitons et vous encourageons à essayer de développer vos applications à l’aide des builds Insider de HoloLens.  Consultez la [documentation du développeur HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds Insider de HoloLens.  Vous pouvez utiliser les mêmes builds d’Unity Visual Studio que vous utilisez déjà pour le développement HoloLens.

## Arrêter la réception des builds Insider

Si vous ne souhaitez plus recevoir de builds Insider de Windows Holographic, vous pouvez refuser [](hololens-recovery.md) lorsque votre HoloLens exécute une build de production, ou vous pouvez récupérer votre appareil à l’aide de l’Advanced Recovery Companion pour récupérer votre appareil vers une version non Insider de Windows Holographic.

> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui se désscrivent des builds Insider Preview après avoir réinstallé manuellement une nouvelle version d’aperçu peuvent voir un écran bleu. Par la suite, ils doivent récupérer manuellement leur appareil. Pour plus d’informations sur le cas où vous seriez touché ou non, consultez plus d’informations sur [ce problème connu.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Pour vérifier que votre HoloLens exécute une build de production :

1. Go to **Settings > System > About**, and find the build number.

1. [Consultez les notes de publication pour les numéros de build de production.](hololens-release-notes.md)

Pour refuser les builds Insider :

1. Sur un HoloLens exécutant une build de production, sélectionnez Paramètres > Mise à jour & **sécurité > programme Windows Insider,** puis sélectionnez Arrêter les **builds Insider.**

1. Suivez les instructions pour refuser votre appareil.
