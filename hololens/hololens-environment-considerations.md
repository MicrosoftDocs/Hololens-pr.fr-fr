---
title: Considérations en matière d’environnement pour HoloLens
description: Profitez d'une expérience idéale avec vos HoloLens lorsque vous optimisez l’appareil en fonction de vos yeux et de votre environnement.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: cadre holographique, champ de vue, fov, étalonnage, espaces, environnement, procédure, HoloLens, réalité mixte, casques de réalité mixte
ms.openlocfilehash: ae5c039387d247d1a2c795bc65d7ea56867b3843
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283135"
---
# Considérations en matière d’environnement pour HoloLens

HoloLens combine les hologrammes avec le monde «réel», en plaçant des hologrammes dans votre environnement. Une fenêtre d’application holographique se trouve sur le mur, une ballerine holographique tourne sur le bureau, des oreilles de lapin viennent se poser sur la tête de votre ami qui ne se doute de rien. Lorsque vous utilisez un jeu ou une application immersif, le monde holographique se propage pour remplir votre environnement, mais vous pouvez toujours voir et déplacer l’espace.

Les hologrammes que vous placez resteront là où vous les avez placés, même si vous éteignez votre appareil.

## Configuration d'un l’environnement

Les appareils HoloLens savent comment placer des hologrammes stables et précis en *suivant* les utilisateurs dans un espace. Sans un suivi correct, l’appareil ne comprend pas l’environnement ou l’utilisateur qui s'y trouve. Les hologrammes peuvent s’afficher aux mauvais endroits, ne pas s’afficher au même endroit à chaque fois ou ne pas s’afficher du tout. Les données utilisées pour suivre les utilisateurs sont représentées dans la *carte spatiale*.  

Le suivi des performances est largement influencé par l’environnement où se trouve l’utilisateur et le réglage d’un environnement afin d'assurer un suivi stable et cohérent est un art plus qu’une science. De nombreux facteurs environnementaux différents sont fusionnés pour activer le suivi, mais en tant que développeur de réalité mixte, il existe plusieurs facteurs que vous pouvez garder à l’esprit pour adapter un espace et ainsi optimiser le suivi.

### Éclairage

WindowsMixedReality utilise la lumière visuelle pour suivre l’emplacement de l’utilisateur. Si un environnement est trop lumineux, les caméras risquent d'être saturées et rien ne s’affichera. Si l’environnement est trop sombre, les caméras ne peuvent pas récupérer suffisamment d’informations et rien n’est visible. L’éclairage doit être même et suffisamment lumineux pour qu’un être humain puisse voir sans effort, mais pas si lumineux que la lumière est difficile à regarder.  

Les zones faiblement éclairées où il existe des points de lumière intense sont également problématiques, car la caméra doit s’ajuster chaque fois qu'elle s'approche ou s'éloigne de ces points. Cela pourrait créer une «confusion» pour l'appareil, qui peut considérer qu'un changement d'éclairage équivaut à un changement de lieu. Un éclairage uniforme garantira un meilleur suivi.  

Tout éclairage extérieur peut également provoquer une instabilité au niveau du suivi, car le soleil peut varier considérablement d'un moment à un autre. Par exemple, le suivi dans un même espace en été et en hiver peut produire des résultats sensiblement différents, car la lumière indirecte de l'extérieur peut être plus intense selon la période de l'année.  

Si vous disposez d'un luxmètre, un éclairage uniforme de 500 à 1000 lux constitue un bon point de départ.  

#### Types d'éclairage

Les différents types d'éclairage d'un espace peuvent également influencer le suivi. Ampoules alimentées par l'alimentation secteur: si la fréquence est de 50Hz, l’impulsion de la lumière est à 50Hz. Un humain ne détectera pas une telle impulsion. Toutefois, une caméra HoloLens à 30fps détecte ces variations: ainsi, certaines trames seront bien éclairées tandis que d'autres non, et certaines d'entre elles seront surexposées car la caméra tentera de compenser ces impulsions légères.  

Aux États-unis, la norme de fréquence électrique est de 60Hz, ce qui signifie que les impulsions légères des ampoules correspondent à la fréquence d’images de HoloLens: des impulsions à 60Hz s'alignent sur la fréquence d’images 30FPS de HoloLens. Toutefois dans de nombreux pays, la norme de fréquence c.a. est de 50Hz, ce qui signifie que certaines trames HoloLens seront prélevées pendant les impulsions, et d’autres non. En particulier, l’éclairage fluorescent en Europe est connu pour causer des problèmes.  

Vous pouvez essayer de résoudre ces problèmes de scintillement de plusieurs manières. La température, l’ancienneté des ampoules et les cycles de préchauffage sont des causes courantes de scintillement et de remplacement des ampoules. Il peut être également utile de vérifier le serrage des ampoules ainsi que la constance du courant.  

### Éléments dans un espace

HoloLens utilise des repères environnementaux uniques, également appelés *fonctionnalités* afin de se repérer dans un espace.  

Un appareil ne peut pratiquement jamais effectuer de suivi dans une zone comptant peu de fonctionnalités, car l’appareil n’a alors aucun moyen de se repérer dans l'espace. L’ajout de fonctionnalités aux murs d’un espace permet généralement d'améliorer le suivi. Les affiches et les symboles sur un mur, des plantes, des objets uniques ou d’autres éléments similaires sont également utiles en ce sens. Un bureau désordonné est un bon exemple d’environnement assurant un bon suivi: il existe un grand nombre de fonctionnalités différentes dans une seule et même zone.  

En outre, utilisez des fonctionnalités uniques dans un même espace. Par exemple, une même affiche figurant plusieurs fois sur un mur entraînera une confusion de l'appareil, car le HoloLens ne saura pas laquelle il regarde. Pour ajouter des fonctionnalités uniques, vous pouvez utiliser des lignes de ruban de masquage afin de créer des modèles uniques et non répétitifs le long des murs et du plancher d’un espace.  

Il sera utile de vous poser la question suivante: si vous pouviez voir seulement une partie de cette scène, pourriez-vous vous localiser avec précision dans cet espace? Si ce n’est pas le cas, il est probable que l’appareil rencontrera également des problèmes de suivi.

#### Trous de ver

Si deux zones ou régions sont similaires, le dispositif de suivi peut les considérer identiques. En conséquence, l'appareil risque de croire qu'il se trouve à un autre endroit. Nous appelons ces types de zones répétitives des *trous de ver*.  

Pour éviter ces trous de ver, essayez d'éviter les zones identiques dans un même espace. Ces zones identiques peuvent parfois comprendre des stations d’usine, des fenêtres sur un bâtiment, des racks de serveurs ou des stations de travail. Pour minimiser ces trous de ver, il peut être utile de labelliser ces zones ou d'ajouter des fonctionnalités uniques dans chacune d'elles.

### Mouvement dans un espace

Si votre environnement évolue et change constamment, l’appareil ne dispose d'aucune fonctionnalité stable pour se repérer.  

Plus il y a d’objets mobiles dans un espace, notamment des personnes, plus le suivi est difficile. Les courroies transporteuses, les éléments dans différents états de production ou un grand nombre de personnes dans un espace sont tout autant d'éléments problématiques pour le suivi.

Les HoloLens peuvent rapidement s’adapter à ces modifications, mais uniquement lorsque cette zone est clairement visible par l’appareil. L'appareil peut accuser un retard par rapport à la réalité dans des zones qu'il ne «voit» pas fréquemment, ce qui peut provoquer des erreurs au niveau de la carte spatiale. Par exemple, un utilisateur scanne un ami, puis se retourne tandis que l’ami quitte la pièce. Une représentation «fantôme» de l’ami est conservée dans les données de mappage spatial jusqu’à ce que l’utilisateur réanalyse l’espace vide.

### Proximité de l’utilisateur aux éléments de l’espace

De même que les humains ont du mal à voir un objet si celui-ci est trop proche des yeux, HoloLens a du mal à discerner les objets trop proches de ses caméras. Si un objet est trop proche pour être visible par les deux caméras, ou si un objet bloque une caméra, l’appareil aura beaucoup plus de mal à suivre l'objet.  

Les caméras peuvent voir un objet si celui-ci est à une distance de 15cm minimum.

### Surfaces d'un espace

Les surfaces fortement réfléchissantes auront probablement un aspect différent selon divers angles, ce qui a un impact sur le suivi. Imaginez un nouveau véhicule: lorsque vous vous déplacez autour de lui, la lumière se reflète dessus et vous voyez différents objets réfléchis sur la surface à mesure que vous bougez. Pour le dispositif de suivi, les différents objets reflétés sur la surface représentent un environnement en évolution, ce qui empêche le suivi.

Il est plus facile de suivre des objets moins brillants.

### Considérations relatives à l'empreinte Wi-Fi

Tant que le Wi-Fi est activé, les données cartographiques sont corrélées avec une empreinte Wi-Fi, même sans connexion à un réseau/routeur WiFi réel. Sans les informations du Wi-Fi, l’appareil peut mettre un peu plus de temps à détecter l'espace et les hologrammes. Si les signaux Wi-Fi changent de manière significative, l’appareil peut penser qu’il se trouve dans un autre espace.

Les données d’identification réseau (par exemple, SSID ou adresse MAC) ne sont pas envoyées à Microsoft et toutes les références Wi-Fi sont conservées localement sur le HoloLens.

## Mappage de nouveaux espaces

Lorsque vous entrez dans un nouvel espace (ou en chargez un existant), vous voyez un graphique de maillage qui se propage sur l’espace. Cela signifie que votre appareil est en train de mapper votre environnement. Bien qu’un HoloLens apprenne à reconnaître un espace au fil du temps, il existe des conseils et des astuces pour mapper les espaces.

## Gestion de l'environnement

Il existe deux paramètres qui permettent aux utilisateurs de «nettoyer» les hologrammes et d’amener HoloLens à «oublier» un espace. Ceux-ci se trouvent dans **Hologrammes et environnements** de l’application Paramètres; le deuxième paramètre est également accessible via **Confidentialité** dans l’application Paramètres.  

1. **Supprimer les hologrammes à proximité**. Lorsque vous sélectionnez ce paramètre, HoloLens efface tous les hologrammes ancrés et toutes les données cartographiques stockées pour l'espace où se trouve actuellement l’appareil. Une nouvelle section de mappage est créée et stockée dans la base de données pour cet emplacement une fois que les hologrammes sont à nouveau placés dans le même espace.

1. **Supprimer tous les hologrammes.** Si vous sélectionnez ce paramètre, HoloLens efface toutes les données cartographiques et tous les hologrammes ancrés dans l’ensemble des bases de données des espaces. Aucun hologramme ne sera redécouvert et tous les hologrammes devront être replacés pour stocker à nouveau le mappage dans la base de données.

## Qualité d’hologramme

Les hologrammes peuvent être placés partout dans votre environnement (en haut, en bas et partout autour de vous), mais vous les verrez par le biais d'une [image holographique](https://docs.microsoft.com/windows/mixed-reality/holographic-frame) qui se trouvera devant vos yeux. Pour obtenir la meilleure vue, veillez à régler votre appareil afin de pouvoir voir l’image entière. Et n’hésitez pas à naviguer dans votre environnement et à explorer!

Pour que [vos hologrammes](https://docs.microsoft.com/windows/mixed-reality/hologram) s’affichent de façon claire, précise et stable, votre HoloLens doit être étalonné en fonction de vos propres besoins. Lors de la configuration initiale de votre HoloLens, vous serez guidé à travers ce processus. Si par la suite, les hologrammes ne s’affichent pas correctement ou si vous rencontrez de nombreuses erreurs, vous pourrez effectuer des ajustements.

Si vous avez des difficultés à mapper les espaces, essayez de supprimer des hologrammes à proximité et de remapper l’espace.

### Étalonnage

Si vos hologrammes sont instables ou tremblants, ou si vous avez des difficultés à les placer, la première chose à faire consiste à utiliser [l’application d’étalonnage](hololens-calibration.md). Cette application peut également vous être utile en cas de difficultés à utiliser votre HoloLens.

Pour accéder à l’application d’étalonnage, accédez à **Paramètres** > **Système** > **Utilitaire**. Sélectionnez **Ouvrir l'étalonnage** et suivez les instructions.

Si une autre personne utilisera votre HoloLens, elle doit d’abord exécuter l’application d’étalonnage pour que l’appareil soit correctement configuré en fonction de ses propres besoins.

## Informations sur la réglementation et la température

[Réglementation HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): comprend des informations sur la température, l’élimination, les interférences radio et Télé, et bien plus encore.

Voici quelques recommandations à suivre lorsque vous utilisez votre appareil:

1. Stockez l’appareil dans un environnement compris dans la plage de températures (en veille ou éteint) pendant une heure avant de l’utiliser.
1. Utilisez l’appareil dans un environnement compris dans la plage de températures.
1. Utilisez l’appareil à l’intérieur .
1. Utilisez l’appareil à l’ombre; même à l’intérieur évitez le contact direct de la lumière solaire à travers les fenêtres ou les verrières.
1. Si vous suivez les recommandations ci-dessus, mais que vous rencontrez des problèmes de surchauffe inattendus, assurez-vous que la fonctionnalité de télémétrie complète est activée avant de soumettre [les commentaires](hololens-feedback.md).

## Voir également

- [Conception de cartographie spatiale](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [Hologrammes](https://docs.microsoft.com/windows/mixed-reality/hologram)
