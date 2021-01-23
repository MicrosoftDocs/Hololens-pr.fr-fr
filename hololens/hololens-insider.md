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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 5936f721c1279dce45fa3e92e160f10d880de207
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283195"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans les dernières builds Insider Preview pour HoloLens ! Il est simple de commencer [et](hololens-insider.md#start-receiving-insider-builds) de fournir des commentaires précieux pour notre prochaine mise à jour majeure du système d’exploitation pour HoloLens.

## Notes de publication de Windows Insider

Nous sommes ravis de commencer à lancer à nouveau la mise en flight de nouvelles fonctionnalités pour les Windows Insiders. Nous allons faire une version d’essai vers le canal de développement pour les dernières mises à jour. Nous continuerons à mettre à jour cette page à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider.  Soyez ravis et prêt à combiner ces mises à jour dans votre réalité.

| Nom de la fonctionnalité                                              | Description courte                                                                      | Disponible dans build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nouveau MicrosoftEdge](#introducing-the-new-microsoft-edge) | Le nouveau Microsoft Edge basé sur Chromium est désormais disponible pour HoloLens 2                         | 20279.1006 |
| [Nouvelle application Paramètres](#new-settings-app)                     | L’application Paramètres héritée est remplacée par une version mise à jour avec de nouvelles fonctionnalités et de nouveaux paramètres | 20279.1006 |
| [S sélectionneur d’application par défaut](#default-app-picker)                 | Choisir l’application à lancer pour chaque type de fichier ou de lien                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Un raccourci vers l’application web Office est désormais répertorié dans « Toutes les applications »                                   | 20279.1006 |
| [Balayage pour taper](#swipe-to-type)                           | Utilisez la pointe de votre doigt pour « balayer » les mots sur le clavier holographique                        | 20279.1006 |
| [Prise en charge du microphone externe USB-C](#usb-c-external-microphone-support) | Utilisez des microphones USB-C pour les applications et/ou Remote Assist.| 20279.1006 |
| [Nouveaux AUMID pour les nouvelles applications en mode plein écran](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs pour les nouvelles applications Paramètres et Edge | 20279.1006 |
| [Amélioration du mode plein écran lors de l’échec de la remise](#kiosk-mode-behavior-changes-for-handling-of-failures) | Le mode plein écran recherche l’accès affecté global avant le menu Démarrer vide. | 20279.1006 |
| [Configurer les diagnostics de retour](#configuring-fallback-diagnostics-via-settings-app) | Définition du comportement de diagnostic de retour dans l’application Paramètres | 20279.1006 |

### Présentation du nouveau Microsoft Edge

![Animation du logo Microsoft Edge hérité vers le nouveau logo Microsoft Edge](images/new-edge.gif)

Le nouveau Microsoft Edge adopte le projet [open source Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) pour créer une meilleure compatibilité pour les clients et moins de fragmentation du web pour les développeurs web.

Avec cet aperçu Insider, le nouveau Microsoft Edge est disponible pour la première fois pour les clients HoloLens 2 ! Bien que le nouveau Microsoft Edge remplace finalement l’ancien Microsoft Edge sur HoloLens 2, les deux navigateurs sont actuellement disponibles pour les Insiders. Veuillez partager vos commentaires et **** bogues avec notre équipe via la fonctionnalité Envoyer des commentaires dans le nouveau Microsoft Edge ou via [le Hub de commentaires.](hololens-feedback.md)

![Nouvelle capture d’écran de Microsoft Edge](images/new-edge-ui.png)

#### Lancement du nouveau Microsoft Edge

Il existe deux versions de Microsoft Edge disponibles pour les Insiders : la nouvelle icône Microsoft Edge de Microsoft Edge (représentée par une icône bleu et vert de la maison) et l’icône ![ Microsoft Edge héritée (représentée par l’icône « e » ](images/new_edge_logo.png) blanche). Le nouveau Microsoft Edge est épinglé au menu Démarrer et se lance automatiquement lorsque vous activez un lien web. Si vous souhaitez revenir à l’utilisation de Microsoft Edge hérité en tant que navigateur web par défaut, consultez les instructions ci-dessous pour réinitialiser les [applications par défaut.](#default-app-picker)

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

Étant donné que le nouveau Microsoft Edge est une application Win32 native avec une nouvelle couche d’adaptateur UWP qui lui permet de s’exécuter sur des appareils UWP uniquement tels que HoloLens 2, certaines fonctionnalités peuvent ne pas être immédiatement disponibles. Nous allons prendre en charge de nouveaux scénarios et fonctionnalités au cours des prochains mois. Veuillez donc vérifier cet espace pour obtenir des informations à jour.

**Scénarios et fonctionnalités qui devraient fonctionner :**
- Première expérience d’application, la première expérience de synchronisation et la synchronisation
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
- Rejoindre un appel Microsoft Teams via le navigateur avec la vidéo, la capture de réalité mixte ou le partage d’écran (la prise d’appels avec l’audio fonctionne bien)

**Scénarios et fonctionnalités qui ne devraient pas fonctionner :**
- Son spatial à partir de plusieurs fenêtres avec flux audio simultanés
- « Voir, dites-le »
- Impression

**Principaux problèmes de navigateur connus :**
- La réinitialisation de votre appareil supprimera le nouveau Microsoft Edge
- L’aperçu de la loupe dans le clavier holographique affiche un contenu incorrect

#### Canaux Microsoft Edge Insider

L’équipe Microsoft Edge met trois canaux d’aperçu à la disposition de la communauté Edge Insider : Bêta, Dev et Canary. L’installation d’un canal d’aperçu ne désinstalle pas la version finale de Microsoft Edge sur votre HoloLens 2, et vous pouvez en installer plusieurs en même temps. 

Visitez la page [d’accueil du Microsoft Edge Insider](https://www.microsoftedgeinsider.com) pour en savoir plus sur la communauté Edge Insider. Pour en savoir plus sur les différents canaux Edge Insider et commencer, visitez la page de téléchargement [Edge Insider.](https://www.microsoftedgeinsider.com/download)

> [!NOTE]
> Pendant cette prévisualisation de Windows Insider pour HoloLens 2, la version de Microsoft Edge sur votre appareil peut être supérieure à celle disponible dans certains (ou tous) des canaux Microsoft Edge Insider. Cela permet de s’assurer que les nouvelles fonctionnalités et correctifs ciblant spécifiquement le navigateur web sur HoloLens 2 sont en train d’atteindre nos Windows Insiders aussi rapidement que possible. Peu de temps après la publication publique de la prochaine mise à jour Windows, les builds du canal Insider de Microsoft Edge dépasseront et resteront en avance sur la version de Microsoft Edge sur votre HoloLens 2.

### Nouvelle application Paramètres

Avec cette version, nous introduisons une nouvelle version de l’application Paramètres. La nouvelle application Paramètres inclut de nouvelles fonctionnalités et des paramètres étendus pour HoloLens 2 dans les domaines suivants : son, veille power &, réseau & Internet, applications, comptes, options d’accès faciles, etc.

> [!NOTE]
> Étant donné que la nouvelle application Paramètres est distincte de l’application Paramètres héritée, toutes les fenêtres Paramètres que vous avez précédemment placées dans votre environnement seront supprimées lors de la mise à jour.

![Page d’accueil de l’application Nouveaux paramètres](images/new-settings-app.png)

**Nouvelles fonctionnalités et nouveaux paramètres**
- Recherche de paramètres : recherchez les paramètres de la page d’accueil Paramètres à l’aide de mots clés ou du nom du paramètre
- Son système > :
  - Périphériques audio d’entrée et de sortie : choisissez indépendamment vos périphériques audio d’entrée et de sortie (par exemple, écoutez de l’audio via un casque Bluetooth ou utilisez un microphone USB-C pour l’entrée audio). Remarque : Bluetooth microphones ne sont pas pris en charge par HoloLens 2.
  - Volume d’application : ajuster indépendamment le volume de chaque application
- Système > la & veille : choisir à quel moment l’appareil doit être en veille après une période d’inactivité
- Système > batterie : activer manuellement le mode économiseur de batterie ou définir un seuil de batterie à partir duquel le mode économiseur de batterie s’active automatiquement
- Appareils > USB : vous pouvez désactiver les connexions USB par défaut
- Réseau & Internet :
  - Les adaptateurs Ethernet USB-C apparaissent désormais dans Le réseau & Internet
  - Les paramètres de l’adaptateur Ethernet USB-C sont désormais disponibles, y compris son adresse IP
  - Vous pouvez désormais activer le mode avion sur HoloLens 2
- Applications : vous pouvez réinitialiser les applications par défaut utilisées pour les types de fichiers et de liens. Pour plus [d’informations, consultez](#default-app-picker) le s sélectionneur d’application par défaut.
- Les comptes > autres utilisateurs : les propriétaires d’appareils peuvent ajouter des utilisateurs, mettre à niveau les utilisateurs standard vers les propriétaires d’appareils, rétrograder les propriétaires d’appareils en utilisateurs standard et supprimer des utilisateurs.
- Facilité d’accès : modifier la taille du texte et certains effets visuels

**Problèmes connus**
- Les fenêtres Paramètres précédemment placées seront supprimées (voir la remarque ci-dessus)
- La visite de la page Notifications peut créer un incident sur l’application Paramètres (en cours d’investigation)
- The Ethernet page currently doesn’t show up (to be fixed soon)
- L’utilisation de la batterie pour le nouveau Microsoft Edge peut ne pas être exacte, en raison de sa nature en tant qu’application de bureau Win32 prise en charge par une couche d’adaptateur UWP (aucun correctif prévu prochainement)

### S sélectionneur d’application par défaut

Lorsque vous activez un lien hypertexte ou ouvrez un type de fichier avec plusieurs applications installées qui le prend en charge, une nouvelle fenêtre s’ouvre et vous invite à sélectionner l’application installée qui doit gérer le type de fichier ou de lien. Dans cette fenêtre, vous pouvez également choisir que l’application sélectionnée gère le fichier ou le type de lien « Une seule fois » ou « Toujours ».

![Fenêtre du s picker d’application](images/default-app-picker.png)

Si vous choisissez « Toujours », mais que vous souhaitez ultérieurement modifier l’application qui gère un fichier ou un type de lien particulier, vous pouvez réinitialiser vos valeurs par défaut enregistrées dans **Paramètres > applications.** Faites défiler jusqu’au bas **** de la page et sélectionnez le bouton Effacer sous « Applications par défaut pour les types de fichiers » et/ou « Applications par défaut pour les types de liens ». Contrairement au paramètre similaire sur les PC de bureau, vous ne pouvez pas réinitialiser les valeurs par défaut des types de fichiers individuels.

### Office Web App

L’application web Office a été ajoutée à la liste « Toutes les applications » dans le menu Démarrer. Cette application web peut également être épinglée au démarrage ou désinstallée. Étant donné qu’il s’agit d’une application web, sa fonctionnalité correspond exactement à ce que vous ariez fait en visitant https://www.office.com . La fonctionnalité d’Application web Office est disponible uniquement lorsque votre HoloLens 2 dispose d’une connexion Internet active.

### Balayage pour taper

Certains clients trouvent plus rapide de « taper » sur des claviers virtuels en faisant glisser la forme du mot qu’ils ont l’intention de taper, et nous prévisualiserons cette fonctionnalité pour le clavier holographique. Vous pouvez balayer un mot à la fois en passant la pointe de votre doigt dans le plan du clavier holographique, en faisant glisser la forme du mot, puis en retirez la pointe de votre doigt du plan du clavier. Vous pouvez balayer les mots de suivi sans avoir à appuyer sur la barre d’espace en supprimant votre doigt du clavier entre les mots. Vous savez que la fonctionnalité fonctionne si vous voyez une trace de balayage après le mouvement de votre doigt sur le clavier.

Notez que cette fonctionnalité peut être difficile à utiliser et à maîtriser en raison de la nature d’un clavier holographique dans lequel vous ne vous sentez pas résistant à votre doigt (contrairement à un affichage de téléphone mobile). Nous évaluons cette fonctionnalité pour la publication publique. Vos commentaires sont donc importants . que vous trouviez la fonctionnalité utile ou que vous avez des commentaires de votre part, faites-le nous savoir via [le Hub de commentaires.](hololens-feedback.md)

### Prise en charge du microphone externe USB-C

> [!IMPORTANT]
> Le branchement **d’un micro USB ne le définira**pas automatiquement comme périphérique d’entrée. Lorsque vous branchez un ensemble de casques USB-C, les utilisateurs observent que le casque audio est automatiquement redirigé vers le casque, mais le système d’exploitation HoloLens hiérarchise le groupe de microphones interne au-dessus de tout autre périphérique d’entrée. **Pour utiliser un microphone USB-C, suivez les étapes ci-dessous.**

Les utilisateurs peuvent sélectionner des microphones externes connectés USB-C à l’aide du **panneau** Paramètres sonores. Les microphones USB-C peuvent être utilisés pour les appels, l’enregistrement, etc.

Ouvrez **l’application Paramètres** et sélectionnez **Son**  ->  **système.**

![Paramètres audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pour utiliser des microphones externes avec **Remote Assist,** les utilisateurs doivent cliquer sur le lien hypertexte « Gérer les périphériques sonores ».
>
> Ensuite, utilisez la drop-down pour définir le microphone externe sur **Default ou** **Communications Default.** Le choix **par** défaut signifie que le microphone externe sera utilisé partout.
>
> Choisir **Communications Par** défaut signifie que le microphone externe sera utilisé dans Remote Assist et d’autres applications de communication, mais que le groupe de micros HoloLens peut toujours être utilisé pour d’autres tâches.

![Gérer les périphériques sonores](images/usbc-mic-2.png)

<br>

![Définir le microphone par défaut](images/usbc-mic-3.jpg)

#### Qu’en est-il Bluetooth prise en charge du microphone ?

Malheureusement, Bluetooth microphones ne sont toujours pas pris en charge actuellement sur HoloLens 2.

#### Résolution des problèmes de microphones USB-C

N’ignorez pas que certains microphones USB-C se signalent de manière incorrecte en tant que *microphone* et haut-parleur. Il s’agit d’un problème avec le microphone et non avec HoloLens. Lorsque vous branchez l’un de ces microphones dans HoloLens, le son peut être perdu. Heureusement, il existe un correctif simple.  

Dans **settings**System Sound , définissez explicitement les haut-parleurs intégrés  ->  ****  ->  ****(pilote audio de fonctionnalité **analogique)** comme **périphérique par défaut.** HoloLens doit mémoriser ce paramètre même si le microphone est supprimé et reconnecté ultérieurement.

![Résolution des problèmes de microphones USB-C](images/usbc-mic-4.png)

### Utiliser les nouvelles applications Paramètres et Edge en mode plein affichage

Lorsque vous ajoutez des applications dans les [kiosques,](hololens-kiosk.md)un administrateur informatique ajoute souvent l’application au kiosque, mais en utilisant son ID de modèle utilisateur d’application (AUMID). Étant donné que l’application Paramètres et l’application Microsoft Edge sont considérées comme de nouvelles applications et que les anciennes applications Kiosks qui utilisent des AUMID pour ces applications devront être mises à jour pour utiliser le nouvel AUMID.

Lors de la modification d’un kiosque pour inclure les nouvelles applications, nous vous recommandons d’ajouter le nouvel AUMID et de laisser l’ancienne. Cela crée une transition facile lorsque les utilisateurs met à jour le système d’exploitation et n’ont pas besoin de recevoir de nouvelles stratégies pour continuer à utiliser le kiosque comme prévu.

| Application                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Ancienne application Paramètres       | HolographicSystemSettings_cw5n1h2txyewy ! Application            |
| Application Nouveaux paramètres       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Application |
| Ancienne application Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nouvelle application Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe ! MSEDGE    |

### Modifications du comportement du mode plein écran pour la gestion des défaillances

Dans les builds plus anciennes, si un appareil avait une configuration kiosque, qui est une combinaison d’accès affecté global et[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)d’accès affecté au membre du groupe AAD, en cas d’échec de la détermination de l’appartenance au groupe AAD, l’utilisateur ne voit « rien affiché dans le menu Démarrer ».

À partir de la version Windows Insider, l’expérience plein écran se base sur la configuration kiosque globale (si elle est présente) en cas d’échec pendant le mode plein écran du groupe AAD.

### Configuration des diagnostics de retour via l’application Paramètres

Désormais, dans l’application Paramètres, un utilisateur peut configurer le comportement des [diagnostics de base.](hololens-diagnostic-logs.md) Dans l’application Paramètres, **accédez**à la page Résolution des problèmes de confidentialité  ->  **** pour configurer ce paramètre.

> [!NOTE]
> Si une stratégie de gestion des périphériques de gestion des périphériques est configurée pour l’appareil, l’utilisateur ne peut pas remplacer ce comportement.  






## Commencer à recevoir des builds Insider

> [!NOTE]
> Si vous n’avez pas mis à jour récemment, redémarrez votre appareil pour mettre à jour l’état et obtenir la dernière build.
> - La commande vocale « Appareil de redémarrage » fonctionne bien. 
> - Vous pouvez également choisir le bouton de redémarrage dans Paramètres/Programme Windows Insider.
>
> Nous avons rencontré un bogue sur le back-end que vous avez peut-être rencontré, ce qui vous permettra de reprendre le suivi.

Sur un appareil HoloLens 2, sélectionnez Mise à jour des **paramètres**& programme Windows Insider sécurité  >  ****  >  **** et **sélectionnez Commencer.** Liez le compte que vous avez utilisé pour vous inscrire en tant que Windows Insider.

Windows Insider est désormais en train de passer aux canaux. **L’anneau** Fast deviendra le canal dev, **** l’anneau **Lent** deviendra le canal bêta **et**l’anneau Release **Preview** deviendra le canal **d’aperçu de publication.** Voici à quoi ressemble ce mappage :

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations, voir [Présentation des canaux Windows Insider sur](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) les blogs Windows.

Ensuite, sélectionnez **Développement actif de Windows,** choisissez **** si vous **** souhaitez recevoir les builds du canal de développement ou du canal bêta, puis examinez les termes du programme.

Sélectionnez **Confirmer > redémarrer maintenant** pour terminer. Une fois que votre appareil a redémarrage, rendez-vous sur **Paramètres >** Mise à jour & sécurité > recherchez les mises à jour pour obtenir la dernière build.

## Instructions de téléchargement et de flash FFU
Pour tester avec une ffu signée par une vol, vous devez d’abord déverrouiller votre appareil avant de flasher la ffu signée par la vol.
1. Sur PC :

    1. Téléchargez ffu sur votre PC à partir [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) de .
    
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store : [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. Sur HoloLens - Déverrouillage de version d’essai : ouvrez la mise à jour des **paramètres**& programme Windows Insider de sécurité, puis inscrivez-vous,  >  ****  >  **** redémarrez l’appareil.

1. Flash FFU : vous pouvez désormais flasher la FFU signée à l’aide d’ARC.

## Fournir des commentaires et signaler des problèmes

Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour fournir des commentaires et signaler des problèmes. L’utilisation du Hub de commentaires garantit que toutes les informations de diagnostic nécessaires sont incluses pour aider nos ingénieurs à déboguer et résoudre rapidement le problème.  Les problèmes avec la version chinoise et japonaise de HoloLens doivent être signalés de la même façon.

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
