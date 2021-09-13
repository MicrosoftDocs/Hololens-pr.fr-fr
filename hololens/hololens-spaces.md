---
title: Mapper des espaces physiques avec HoloLens
description: HoloLens apprend au fil du temps à quoi ressemble un espace. Les utilisateurs peuvent faciliter ce processus en déplaçant l’HoloLens de certaines façons dans l’espace.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, conception, cartographie spatiale, HoloLens, reconstruction de surface, maille, suivi de la tête, mappage
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034367"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapper des espaces physiques avec HoloLens

HoloLens combine les hologrammes avec votre monde réel. Pour ce faire, HoloLens doit se familiariser avec le monde réel autour de vous et se souvenir de l’endroit où vous placez des hologrammes dans cet espace.

Au fil du temps, HoloLens construit une *cartographie spatiale* de l’environnement qu’il a vu.  HoloLens met à jour la cartographie en fonction de l’évolution de l’environnement. Tant que vous êtes connecté et que l’appareil est activé, HoloLens crée et met à jour vos cartographies spatiales. Si vous tenez ou que vous portez l’appareil avec les caméras pointées vers un espace, HoloLens essaie de cartographier la zone. Bien qu’HoloLens apprenne naturellement un espace au fil du temps, vous pouvez aider HoloLens à cartographier votre espace plus rapidement et plus efficacement.  

> [!NOTE]
> Si votre HoloLens ne peut pas cartographier votre espace ou n’est pas correctement calibré, il est possible qu’HoloLens passe en mode Limité. En mode Limité, vous ne pouvez pas placer des hologrammes dans votre environnement.

Cet article explique comment HoloLens cartographie les espaces, comment améliorer la cartographie spatiale et comment gérer les données spatiales recueillies par HoloLens.

## <a name="choosing-and-setting-up-and-your-space"></a>Sélection et configuration de votre espace

Les caractéristiques de votre environnement peuvent rendre difficile l’interprétation d’un espace par HoloLens. Les niveaux d’éclairage, les matériaux présents dans l’espace, la disposition des objets, etc. peuvent tous affecter la façon dont HoloLens cartographie une zone.

HoloLens fonctionne mieux dans certains types d’environnements. Pour produire la meilleure cartographie spatiale, choisissez une pièce suffisamment éclairée et spacieuse. Évitez les espaces sombres et les pièces qui présentent beaucoup de surfaces sombres, brillantes ou translucides (par exemple des miroirs ou des rideaux en gaze).

HoloLens est optimisé pour une utilisation en intérieur. La cartographie spatiale fonctionne également mieux quand le Wi-Fi est activé, bien qu’il ne soit pas nécessaire de se connecter à un réseau. HoloLens peut obtenir des points d’accès Wi-Fi même s’il n’est pas connecté ou authentifié. Les fonctionnalités d’HoloLens ne changent pas si les points d’accès sont connectés à Internet ou seulement à un Intranet/local.

Utilisez HoloLens seulement dans les endroits sûrs et sans dangers. [En savoir plus sur la sécurité](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Cartographie de votre espace

Vous êtes maintenant prêt à commencer à cartographier votre espace.  Quand HoloLens commence à cartographier votre environnement, vous voyez un graphique de mailles se développer dans l’espace.  Dans la page d’accueil de Mixed Reality, vous pouvez déclencher l’affichage de la cartographie en sélectionnant une surface cartographiée.

Voici des recommandations pour créer une bonne cartographie spatiale.

### <a name="understand-the-scenarios-for-the-area"></a>Comprendre les scénarios pour la zone

Il est important de consacrer le plus de temps là où vous allez utiliser HoloLens, de sorte que la cartographie soit pertinente et complète. Par exemple, si un scénario d’utilisation d’HoloLens implique de se déplacer du point A au point B, parcourez ce chemin deux ou trois fois, en regardant dans toutes les directions pendant que vous vous déplacez.  

### <a name="walk-slowly-around-the-space"></a>Parcourez lentement l’espace.

Si vous vous déplacez trop rapidement dans la zone, il est probable qu’HoloLens ne parvienne pas à cartographier des zones. Parcourez lentement l’espace, en vous arrêtant tous les 2 à 3 mètres pour regarder votre environnement.  

Des mouvements calmes aident également à améliorer l’efficacité de la cartographie par HoloLens.

### <a name="look-in-all-directions"></a>Regardez dans toutes les directions

Le fait de regarder autour de vous quand vous cartographiez l’espace donne davantage de données à HoloLens sur la position des points les uns par rapport aux autres.  

Par exemple, si vous ne regardez pas en haut, HoloLens ne peut pas savoir où se trouve le plafond d’une pièce.  

N’oubliez pas de regarder le sol quand vous cartographiez l’espace.

### <a name="cover-key-areas-multiple-times"></a>Couvrez les zones importantes plusieurs fois

Parcourir une zone plusieurs fois permet de collecter des caractéristiques que vous avez peut-être manquées lors du premier parcours. Pour créer une cartographie idéale, essayez de parcourir une zone deux à trois fois.

Si possible, en répétant ces mouvements, consacrez du temps à parcourir une zone dans une direction, puis faites demi-tour et revenez par le même chemin.

### <a name="take-your-time-mapping-the-area"></a>Prenez le temps de bien cartographier la zone

Il faut entre 15 et 20 minutes pour qu’HoloLens cartographie entièrement son environnement et s’y adapte. Si vous disposez d’un espace où vous envisagez d’utiliser un appareil HoloLens fréquemment, prendre ce temps préalablement pour cartographier l’espace peut éviter de rencontrer des problèmes ultérieurement.  

## <a name="possible-errors-in-the-spatial-map"></a>Erreurs possibles dans la cartographie spatiale

Les erreurs dans les données de cartographie spatiale sont classées en plusieurs catégories :

- *Trous* : des surfaces du monde réel sont absentes des données de la cartographie spatiale.
- *Hallucinations* : des surfaces existent dans les données cartographiques spatiales alors qu’elles n’existent pas dans le monde réel.
- *Trous de vers* : HoloLens « perd » une partie de la cartographie spatiale en pensant qu’elle se trouve dans une partie de la cartographie différente de celle où elle se trouve en réalité.
- *Biais* : des surfaces dans les données de la cartographie spatiale sont imparfaitement alignées avec les surfaces du monde réel, en décalage vers l’avant ou l’arrière.

Si vous rencontrez une de ces erreurs, utilisez le [hub de feedback](hololens-feedback.md) pour envoyer votre feedback.

## <a name="security-and-storage-for-spatial-data"></a>Sécurité et stockage des données spatiales

La mise à jour de Windows 10 version 1803 et ultérieur pour Microsoft HoloLens stocke les données de cartographie dans une base de données locale (sur l’appareil).

Les utilisateurs d’HoloLens ne peuvent pas accéder directement à la base de données cartographique, même quand l’appareil est connecté à un PC ou en utilisant l’application Explorateur de fichiers. Quand BitLocker est activé sur HoloLens, les données cartographiques stockées sont également cryptées ainsi que l’ensemble du volume.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Supprimer des données cartographiques et des espaces connus de HoloLens

Il existe deux options pour supprimer des données cartographiques dans **Settings > System > Holograms** (Paramètres -> Système -> Hologrammes) :

- Pour supprimer les hologrammes à proximité, sélectionnez **Remove nearby holograms** (Supprimer les hologrammes à proximité). Cette commande efface les données cartographiques et les hologrammes ancrés pour l’espace actif. Si vous continuez à utiliser l’appareil dans le même espace, il crée et stocke une toute nouvelle section de cartographie pour remplacer les informations supprimées.

   > [!NOTE]
   > Les hologrammes « à proximité » sont des hologrammes ancrés dans la même section de cartographie de l’espace actif.

   Par exemple, vous pouvez utiliser cette option pour effacer les données cartographiques professionnelles sans affecter les données cartographiques privées.

- Pour supprimer tous les hologrammes, sélectionnez **Remove all holograms** (Supprimer tous les hologrammes). Cette commande efface toutes les données cartographiques stockées sur l’appareil ainsi que tous les hologrammes ancrés. Vous devrez placer les hologrammes explicitement. Vous ne pourrez pas redécouvrir les hologrammes précédemment placés.

> [!NOTE]
> Une fois que vous avez supprimé les hologrammes à proximité ou tous les hologrammes, HoloLens commence immédiatement l’analyse et la cartographie de l’espace actif.

### <a name="wi-fi-data-in-spatial-maps"></a>Données Wi-Fi dans les cartographies spatiales

HoloLens stocke les caractéristiques Wi-Fi afin de vous aider à corréler les emplacements des hologrammes et les sections de cartographie stockées dans la base de données HoloLens des espaces connus. Les informations sur les caractéristiques Wi-Fi ne sont pas accessibles aux utilisateurs et elles ne sont pas envoyées à Microsoft en utilisant le cloud ou la télémétrie.

Tant que le Wi-Fi est activé, HoloLens met en corrélation les données cartographiques avec les points d’accès Wi-Fi à proximité. Il n’y a pas de différence de comportement selon qu’un réseau est connecté ou simplement détecté à proximité. Si le Wi-Fi est désactivé, l’HoloLens continue de le rechercher dans l’espace. Cependant, HoloLens doit rechercher dans davantage de données cartographiques de la base de données spatiale et peut avoir besoin de plus de temps pour trouver des hologrammes. Sans les informations Wi-Fi, HoloLens doit comparer les analyses actives à toutes les ancres d’hologramme et aux sections de cartographie qui sont stockées sur l’appareil afin de localiser la partie correcte de la cartographie.

## <a name="related-topics"></a>Rubriques connexes

- [Conception du mappage spatial](/windows/mixed-reality/spatial-mapping)
