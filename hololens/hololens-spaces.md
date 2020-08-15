---
title: Mapper des espaces physiques avec HoloLens
description: HoloLens apprend à quoi ressemble un espace dans le temps. Les utilisateurs peuvent faciliter ce processus en déplaçant l'HoloLens de certaines manières dans l'espace.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, conception, cartographie spatiale, HoloLens, reconstruction de surface, maillage, suivi de tête, mappage
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: 6f2ec9ced776166f96eddcd601bef5de715703a5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931836"
---
# Mapper des espaces physiques avec HoloLens

HoloLens combine les hologrammes avec votre monde réel. Pour ce faire, HoloLens doit se familiariser avec le monde réel autour de vous et vous souvenir où vous placez des hologrammes dans cet espace.

Au fil du temps, l’HoloLens génère une *carte spatiale* de l’environnement qu’elle a vu.  HoloLens met à jour la carte en fonction de l'évolution de l'environnement. Tant que vous êtes connecté et que l’appareil est activé, HoloLens crée et met à jour vos cartes spatiales. Si vous tenez ou portez l'appareil avec les caméras pointées vers un espace, l'HoloLens essaie de mapper la zone. Bien que la carte HoloLens ait une grande efficacité dans le temps, vous pouvez aider HoloLens à mapper votre espace plus rapidement et plus efficacement.  

> [!NOTE]
> Si votre HoloLens ne peut pas mapper votre espace ou n’est pas disponible, il est possible que HoloLens passe en mode limité. En mode limité, vous ne pouvez pas placer des hologrammes dans votre environnement.

Cet article explique comment HoloLens mappe les espaces, comment améliorer la cartographie spatiale et comment gérer les données spatiales recueillies par HoloLens.

## Sélection et configuration de votre espace

Les caractéristiques de votre environnement peuvent rendre difficile l'interprétation d'un espace par l'HoloLens. Les niveaux d’éclairage, les matériaux présents dans l’espace, la disposition des objets, etc., peuvent tous affecter la façon dont HoloLens mappe une zone.

L'HoloLens fonctionne mieux dans certains types d'environnements. Pour produire la meilleure carte spatiale, choisissez une pièce suffisamment éclairée et spacieuse. Évitez les espaces sombres et les pièces qui présentent beaucoup de surfaces sombres, brillantes ou translucides (par exemple, des miroirs ou des rideaux en gaze).

L'HoloLens est optimisé pour une utilisation en intérieur. La cartographie spatiale fonctionne également mieux lorsque le Wi-Fi est activé, bien qu'il ne soit pas nécessaire de se connecter à un réseau. HoloLens peut obtenir des points d'accès Wi-Fi même s'il n'est pas connecté ou authentifié. La fonctionnalité HoloLens ne change pas si les points d’accès sont connectés à Internet ou Intranet/local uniquement.

Utilisez HoloLens uniquement dans les endroits sûrs, sans danger. [En savoir plus sur la sécurité](https://support.microsoft.com/help/4023454/safety-information).

## Mappage de votre espace

Vous êtes maintenant prêt à commencer à mapper votre carte de réserve.  Lorsque HoloLens commence à mapper votre environnement, un maillage graphique va se répandre sur l'espace.  Dans la page d’accueil de Mixed Reality, vous pouvez déclencher l’affichage de la carte en sélectionnant sur une surface mappée.

Voici des recommandations pour créer une excellente carte spatiale.

### Comprendre les scénarios de la zone

Il est important de consacrer le plus de temps à l’utilisation de la carte HoloLens, de sorte que la carte soit pertinente et complète. Par exemple, si un scénario d'utilisation de l'HoloLens implique de se déplacer du point A au point B, parcourez ce chemin deux à trois fois, en regardant dans toutes les directions pendant que vous vous déplacez.  

### Parcourez lentement l'espace

Si vous parcourez la zone trop rapidement, il est probable que l'HoloLens n’arrive pas à identifier certaines zones. Parcourez lentement l’espace, en vous arrêtant tous les 2 à 3 mètres pour observer votre environnement.  

Des mouvements précis aident également à améliorer l'efficacité de la carte HoloLens.

### Examiner toutes les directions

La recherche dans le cadre du mappage de l’espace donne davantage de données à l’HoloLens sur les points les uns par rapport aux autres.  

Si vous ne regardez pas en haut, par exemple, l'HoloLens peut ne pas savoir où se trouve le plafond d'une pièce.  

N'oubliez pas de regarder le sol au fur et à mesure que vous mappez l’espace.

### Couvrir les zones clés plusieurs fois

Parcourir une zone plusieurs fois permet de récupérer les fonctionnalités que vous avez peut-être manquées lors de la première procédure. Pour créer une carte idéale, essayez de parcourir une zone deux à trois fois.

Si possible, tandis que vous répétez ces mouvements, consacrez du temps à parcourir une zone dans une direction, puis faites demi-tour et reprenez le même parcours.

### Prenez le temps de mapper la zone

Il faut entre 15 et 20 minutes pour que l'HoloLens puisse être entièrement mappé et s'adapter à son environnement. Si vous disposez d’un espace dans lequel vous envisagez d’utiliser un HoloLens fréquemment, l’utilisation à l’avance du mappage de l’espace peut empêcher les problèmes plus tard.  

## Erreurs possibles dans la carte spatiale

Les erreurs dans les données de cartographie spatiale sont classées en plusieurs catégories:

- *des trous*: les surfaces réelles sont absentes des données de cartographie spatiale.
- *Allusions*: Les surfaces existent dans les données cartographiques spatiales qui n'existent pas dans le monde réel.
- *Repaires*: HoloLens « perd » une partie de la carte spatiale en pensant qu'elle se trouve dans une partie différente de la carte qu'elle ne l'est en réalité.
- *Bias*: Les surfaces des données cartographiques spatiales sont imparfaitement alignées avec les surfaces du monde réel, qu'elles soient appuyées ou déplacées.

Si vous rencontrez l’une de ces erreurs, utilisez la [FeedbackHub](hololens-feedback.md) pour envoyer des commentaires.

## Sécurité et stockage des données spatiales

La mise à jour de Windows 10 version 1803 pour Microsoft HoloLens et les versions ultérieures stocke les données de mappage dans une base de données locale (sur un appareil).

Les utilisateurs de HoloLens ne peuvent pas accéder directement à la base de données cartographiques, même lorsque l’appareil est connecté à un PC ou à l’aide de l’application Explorateur de fichiers. Lorsque BitLocker est activé sur HoloLens, les données cartographiques stockées sont également cryptées, ainsi que l'ensemble du volume.

### Supprimer les données cartographiques et les espaces connus de HoloLens

Il existe deux options pour supprimer des données cartographiques dans **Paramètres > Système > Hologrammes**:

- Pour supprimer les hologrammes proches, sélectionnez **Supprimer les hologrammes proches**. Cette commande efface les données cartographiques et les hologrammes ancrées pour l’espace actuel. Si vous continuez à utiliser l’appareil dans le même espace, il crée et stocke une toute nouvelle section de carte pour remplacer les informations supprimées.

   > [!NOTE]
   > Les hologrammes «proches» sont des hologrammes ancrées dans la même section de carte de l’espace actuel.

   Par exemple, vous pouvez utiliser cette option pour effacer les données cartographiques liées au travail sans affecter les données cartographiques liées au domicile.

- Pour supprimer tous les hologrammes, sélectionnez **Supprimer tous les hologrammes**. Cette commande efface toutes les données de carte stockées sur l’appareil, ainsi que tous les hologrammes ancrés. Vous devrez placer les hologrammes de manière explicite. Vous ne pourrez pas redécouvrir les hologrammes précédemment placés.

> [!NOTE]
> Une fois que vous avez supprimé les hologrammes à proximité ou tous les hologrammes, HoloLens commence immédiatement l’analyse et le mappage de l’espace actuel.

### Données Wi-Fi dans les cartes spatiales

HoloLens stocke les caractéristiques Wi-Fi afin de vous aider à corréler les emplacements d’hologrammes et les sections de carte stockées dans la base de données HoloLens des espaces connus. Les informations sur les caractéristiques du Wi-Fi ne sont pas accessibles aux utilisateurs, et ne sont pas envoyées à Microsoft en utilisant le nuage ou la télémétrie.

Tant que le Wi-Fi est activé, HoloLens met en corrélation les données cartographiques avec les points d’accès Wi-Fi à proximité. Il n'y a pas de différence de comportement selon qu'un réseau est connecté ou simplement détecté à proximité. Si le Wi-Fi est désactivé, l'HoloLens continue à rechercher l'espace. Cependant, HoloLens doit rechercher davantage de données cartographiques dans la base de données spatiales et peut avoir besoin de plus de temps pour trouver des hologrammes. Sans les informations Wi-Fi, l’HoloLens doit comparer les analyses actives à toutes les ancres holographiques et aux sections de carte qui sont stockées sur l'appareil afin de localiser la partie correcte de la carte.

## Rubriques connexes

- [Conception de cartographie spatiale](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
