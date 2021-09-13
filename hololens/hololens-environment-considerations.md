---
title: Considérations liées à l’environnement HoloLens
description: Optimisez votre appareil HoloLens en fonction de vos yeux et de votre environnement pour bénéficier de la meilleure expérience possible.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: cadre holographique, champ de vision, étalonnage, espaces, environnement, procédure, HoloLens, réalité mixte, casques de réalité mixte
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034114"
---
# <a name="hololens-environment-considerations"></a>Considérations liées à l’environnement HoloLens

HoloLens associe des hologrammes au monde « réel » en les plaçant dans votre environnement. Une fenêtre d'application holographique est « accrochée » au mur, une ballerine holographique tourne sur le bureau, des oreilles de lapin viennent se poser sur la tête de votre ami qui ne se doute de rien. Lorsque vous utilisez un jeu ou une application immersive, le monde holographique s'invite dans votre environnement, mais vous voyez toujours ce qui se trouve autour de vous et pouvez vous déplacer dans l'espace.

Les hologrammes que vous placez restent là où vous les placez, même si vous éteignez votre appareil.

## <a name="setting-up-an-environment"></a>Configuration d'un environnement

Les appareils HoloLens savent placer des hologrammes stables et précis en *suivant* les utilisateurs dans un espace. Sans suivi approprié, l'appareil ne comprend pas l'environnement ou l'utilisateur qui s'y trouve. Les hologrammes peuvent apparaître aux mauvais endroits, ne pas apparaître au même endroit à chaque fois, ou ne pas apparaître du tout. Les données utilisées pour assurer le suivi des utilisateurs sont représentées sur la *carte spatiale*.  

Les performances de suivi dépendent en grande partie de l'environnement dans lequel se trouve l'utilisateur, et l'optimisation d'un environnement dans le but d'assurer un suivi stable et cohérent relève davantage de l'art que de la science. De nombreux facteurs environnementaux différents sont fusionnés pour permettre le suivi, mais en tant que développeur de réalité mixte, vous devez garder plusieurs facteurs en tête pour adapter un espace et optimiser le suivi.

### <a name="lighting"></a>Éclairage

Windows Mixed Reality utilise la lumière ambiante pour suivre l'emplacement de l'utilisateur. Lorsqu'un environnement est trop lumineux, les caméras peuvent être saturées et on ne voit rien. Et lorsque l'environnement est trop sombre, les caméras ne peuvent pas capter suffisamment d'informations et on ne voit rien non plus. L'éclairage doit être uniforme et suffisamment clair pour permettre à l'œil humain de voir sans effort, mais pas trop non plus afin de ne pas éblouir l'utilisateur.  

Les zones faiblement éclairées comportant des points de lumière vive sont également problématiques, car la caméra doit s'adapter à chaque fois qu'elle s'approche ou s'éloigne de ces points. Cela peut créer une certaine « confusion » pour l'appareil, qui peut considérer qu'un changement d'éclairage équivaut à un changement de lieu. Un éclairage uniforme garantira un meilleur suivi.  

Tout éclairage extérieur peut également provoquer une instabilité au niveau du suivi, car l'intensité de la lumière émise par le soleil peut considérablement varier d'un moment à un autre. Par exemple, le suivi dans un même espace en été et en hiver peut produire des résultats radicalement différents, car la lumière indirecte de l'extérieur peut être plus intense selon la période de l'année.  

Si vous disposez d'un luxmètre, un éclairage uniforme de 500 à 1 000 lux constitue un bon point de départ.  

#### <a name="types-of-lighting"></a>Types d'éclairage

Les différents types d'éclairage d'un espace peuvent également influencer le suivi. Les ampoules électriques émettent des impulsions en fonction du courant alternatif qui les traverse. Si la fréquence du courant alternatif est de 50 Hz, la lumière émet des impulsions à 50 Hz. L'œil humain ne détecte pas ces impulsions. La caméra 30 fps de l'HoloLens, quant à elle, perçoit ces variations : certaines images bénéficieront d'un bon éclairage tandis que d'autres non, et certaines d'entre elles seront surexposées car la caméra essaiera de compenser ces impulsions lumineuses.  

Aux États-Unis, la norme de fréquence électrique est de 60 Hz. Les impulsions des ampoules correspondent donc à la fréquence d'images de l'HoloLens : des impulsions à 60 Hz s'alignent sur la fréquence d'images de 30 FPS de l'appareil. Mais dans de nombreux autres pays, le courant alternatif 50 Hz constitue la norme, ce qui signifie que certaines images HoloLens sont prises pendant les impulsions, et d'autres non. Il est notamment reconnu qu'en Europe, l'éclairage fluorescent entraîne des problèmes.  

Vous pouvez essayer de résoudre les problèmes de scintillement de plusieurs manières. La température, l'âge des ampoules et les cycles de préchauffage sont des causes courantes de scintillement des lampes fluorescentes, et leur remplacement peut s'avérer nécessaire. Il peut également être utile de resserrer les ampoules et de s'assurer que la consommation de courant est constante.  

### <a name="items-in-a-space"></a>Éléments présents dans un espace

HoloLens utilise des repères environnementaux uniques, également appelés *caractéristiques* afin de se repérer dans un espace.  

Un appareil ne peut pratiquement jamais effectuer de suivi dans une zone pauvre en caractéristiques, car il n'a alors aucun moyen de se repérer dans l'espace. L'ajout de caractéristiques sur les murs d'un espace permet généralement d'améliorer le suivi. Les affiches et symboles figurant sur un mur, les plantes, les objets particuliers ou autres éléments similaires sont tous utiles. Un bureau en désordre est un bon exemple d'environnement favorisant un bon suivi grâce à la présence d'un grand nombre de caractéristiques différentes au sein de la même zone.  

Utilisez également les caractéristiques particulières d'un espace. Par exemple, la présence d'une même affiche à différents endroits sur un mur sera source de confusion pour l'appareil, car l'HoloLens ne saura pas laquelle il regarde. Pour ajouter des caractéristiques uniques, vous pouvez utiliser des lignes de ruban de masquage afin de créer des modèles uniques et non répétitifs le long des murs et du sol d'un espace.  

Posez-vous la question suivante : si vous ne voyiez qu'une petite partie de la scène, seriez-vous en mesure de vous repérer avec précision dans cet espace ? Si ce n'est pas le cas, l'appareil aura probablement le même problème.

#### <a name="wormholes"></a>Trous de ver

Si deux zones ou régions se ressemblent, le dispositif de suivi peut considérer qu'elles sont identiques. Par conséquent, l'appareil risque de croire qu'il se trouve à un autre endroit. Nous appelons ces types de zones répétitives des *trous de ver*.  

Pour éviter ces trous de ver, essayez d'éviter les zones identiques dans un même espace. Parmi ces zones identiques figurent parfois les stations d'une usine, les fenêtres d'un bâtiment, les racks des serveurs ou les stations de travail. L'étiquetage de ces zones ou l'ajout de caractéristiques uniques dans chacune d'elles peut contribuer à atténuer les trous de ver.

### <a name="movement-in-a-space"></a>Mouvement dans un espace

Si votre environnement évolue et change constamment, l'appareil ne dispose d'aucune caractéristique stable pour se repérer.  

Plus il y a d'objets mobiles dans un espace, y compris des personnes, plus le suivi est difficile. Les tapis roulants, les éléments en cours de production et les nombreuses personnes présentes dans un espace sont autant d'éléments problématiques pour le suivi.

L'HoloLens peut rapidement s'adapter à ces changements, à condition que la zone soit clairement visible par l'appareil. L'appareil peut accuser un retard par rapport à la réalité dans les zones qu'il ne « voit » pas fréquemment, ce qui peut provoquer des erreurs au niveau de la carte spatiale. Par exemple, un utilisateur scanne un ami, puis se retourne tandis que l'ami quitte la pièce. Une représentation « fantôme » de l'ami persistera dans les données de cartographie spatiale jusqu'à ce que l'utilisateur scanne à nouveau l'espace devenu vide.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Proximité de l'utilisateur par rapport aux éléments présents dans l'espace

Comme l'œil humain, les caméras de l'HoloLens ont du mal à discerner les objets trop proches. Si un objet est trop proche pour être visible par les deux caméras, ou s'il bloque une caméra, l'appareil aura du mal à le suivre.  

Les caméras ne peuvent distinguer un objet que si celui-ci se trouve à une distance minimum de 15 cm.

### <a name="surfaces-in-a-space"></a>Surfaces dans un espace

Les surfaces fortement réfléchissantes peuvent avoir un aspect différent selon l'angle, ce qui a un impact sur le suivi. Pensez à une voiture neuve : lorsque vous vous déplacez autour d'elle, la lumière s'y reflète et différents objets se réfléchissent à sa surface à mesure que vous bougez. Pour le dispositif de suivi, les différents objets reflétés à la surface représentent un environnement changeant, ce qui empêche le suivi.

Le suivi des objets moins brillants est plus facile.

### <a name="wi-fi-fingerprint-considerations"></a>Considérations relatives à l'empreinte Wi-Fi

Tant que le Wi-Fi est activé, les données cartographiques sont corrélées avec une empreinte Wi-Fi, même sans connexion à un réseau/routeur Wi-Fi réel. Sans les informations du Wi-Fi, l'appareil peut mettre un peu plus de temps à détecter l'espace et les hologrammes. Si les signaux Wi-Fi changent de manière significative, l'appareil peut penser qu'il se trouve dans un autre espace.

Les données d'identification réseau (par exemple, SSID ou adresse MAC) ne sont pas envoyées à Microsoft et toutes les références Wi-Fi sont conservées localement sur l'HoloLens.

## <a name="mapping-new-spaces"></a>Cartographie de nouveaux espaces

Lorsque vous entrez dans un nouvel espace (ou que vous chargez un espace existant), un maillage apparaît sur l'espace. Cela signifie que votre appareil est en train de cartographier votre environnement. Bien qu'un appareil HoloLens apprenne à reconnaître un espace au fil du temps, il existe des trucs et astuces pour cartographier les espaces.

## <a name="environment-management"></a>Gestion de l’environnement

Deux paramètres permettent aux utilisateurs de « nettoyer » les hologrammes et d'amener leur appareil HoloLens à « oublier » un espace. Ceux-ci se trouvent sous **Hologrammes et environnements** dans l'application Paramètres ; le deuxième paramètre est également accessible sous **Confidentialité** dans l'application Paramètres.  

1. **Supprimer les hologrammes proches**. Lorsque vous sélectionnez ce paramètre, HoloLens efface tous les hologrammes ancrés et toutes les données cartographiques stockées pour l'espace où se trouve l'appareil. Une nouvelle section de carte est créée et stockée dans la base de données pour cet emplacement une fois les hologrammes replacés dans le même espace.

1. **Supprimer tous les hologrammes**. Si vous sélectionnez ce paramètre, HoloLens efface TOUTES les données cartographiques et TOUS les hologrammes ancrés dans l'ensemble des bases de données d'espaces. Aucun hologramme n'est redécouvert et tous les hologrammes doivent être replacés pour que des sections de carte soient à nouveau enregistrées dans la base de données.

## <a name="hologram-quality"></a>Qualité des hologrammes

Les hologrammes peuvent être placés partout dans votre environnement (en haut, en bas et tout autour de vous), mais vous les verrez à travers un [cadre holographique](/windows/mixed-reality/holographic-frame) positionné devant vos yeux. Pour bénéficier d'une vue optimale, veillez à régler votre appareil de manière à pouvoir voir l'intégralité du cadre. Et n'hésitez pas à vous promener dans votre environnement et à l'explorer !

Pour que vos [hologrammes](/windows/mixed-reality/hologram) soient clairs, nets et stables, votre HoloLens doit être étalonné en fonction de vos besoins. Lors de la configuration initiale de votre HoloLens, vous serez guidé tout au long de ce processus. Par la suite, si les hologrammes ne s'affichent pas correctement ou si vous rencontrez de nombreuses erreurs, vous pourrez effectuer des ajustements.

Si vous avez du mal à cartographier des espaces, essayez de supprimer les hologrammes les plus proches et de recartographier l'espace.

### <a name="calibration"></a>Étalonnage

Si vos hologrammes sont instables ou tremblants, ou si vous avez du mal à les placer, la première chose à faire est d'essayer l'[application Étalonnage](hololens-calibration.md). Cette application peut également vous être utile en cas de difficultés à utiliser votre HoloLens.

Pour ouvrir l'application Étalonnage, accédez à **Paramètres** > **Système** > **Utilitaires**. Sélectionnez **Ouvrir Étalonnage** et suivez les instructions.

Si une autre personne doit utiliser votre HoloLens, celle-ci doit d'abord exécuter l'application Étalonnage afin que l'appareil soit correctement configuré pour elle.

## <a name="temperature-and-regulatory-information"></a>Informations sur la réglementation et la température

[Informations réglementaires sur HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information) : comprend des informations sur la température, l'élimination, les interférences radio et TV, etc.

Voir les détails pour « HoloLens » dans [Matériaux et substances](https://www.microsoft.com/legal/compliance/materials-substances) > Article 33, Divulgation sur la conformité environnementale (PDF).

Recommandations à suivre lors de l'utilisation de votre appareil :

1. Stockez l'appareil (en mode veille ou éteint) dans un environnement dont la température se situe dans la plage indiquée pendant une heure avant de l'utiliser.
1. Utilisez l'appareil dans un environnement dont la température se situe dans la plage indiquée.
1. Utilisez l'appareil à l'intérieur.
1. Utilisez l'appareil à l'ombre ; même à l'intérieur, évitez la lumière directe du soleil à travers les fenêtres ou les verrières.
1. Si vous suivez les instructions précédentes mais que vous rencontrez des problèmes de surchauffe inattendus, suivez les étapes ci-dessous pour nous envoyer vos [commentaires](hololens-feedback.md). 
    1. Vérifiez que la télémétrie **Complète** ou **Facultative** est activée sur votre appareil. Si ce n'est pas le cas, activez-la. 
    >[!CAUTION]
    > La télémétrie n'est pas rétroactive pour les événements thermiques. Elle doit être activée pendant la surchauffe ou les données requises ne seront pas capturées.
    
    2. Reproduisez le problème de surchauffe.
    3. Incluez la date et l'heure de la surchauffe.
    4. Envoyez vos [commentaires](hololens-feedback.md).

## <a name="see-also"></a>Voir aussi

- [Conception du mappage spatial](/windows/mixed-reality/spatial-mapping)
- [Hologrammes](/windows/mixed-reality/hologram)
