---
title: Affichages HoloLens 2
description: Attentes pour les affichages HoloLens 2. Conseils pour la configuration des affichages pour optimiser la qualité de l’image.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: affichage, étalonnage, confort, visuels, qualité, écart pupillaire
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 0001ff627b150a9ba79e76f8d995231186c46917
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163016"
---
# Affichage HoloLens 2

L’affichage HoloLens 2 est une combinaison de guides d’onde et de projecteurs de lumière. Les utilisateurs examinent les guides d’onde à l’intérieur du visière lorsque vous portez le casque. Les projecteurs de lumière se trouvent à l’intérieur du boîtier au-dessus du navigateur. HoloLens 2 utilise la lumière laser pour illuminer l’affichage.

## Résolution des problèmes

Pour HoloLens 2, procédez comme suit pour garantir une qualité visuelle optimale des hologrammes présentés dans les affichages:

* **Augmentez la luminosité de l’affichage.** Les hologrammes s’affichent mieux lorsque l’écran est à son niveau le plus lumineux.
* **Rapprochez la visière de vos yeux.** Faites basculer la visière vers la position la plus proche de vos yeux.
* **Décaler la visière vers le bas.** Essayez de déplacer le pavé de navigation de votre front vers le bas, ce qui rapprochera la visière de votre nez.
* **Exécutez l’étalonnage des yeux.** L’affichage utilise votre distance interpupillaire (IPD) et le pointage de votre regard pour optimiser les images sur l’écran. Si vous n’effectuez pas l’étalonnage de l’œil, la qualité de l’image peut être pire. Pour effectuer l’étalonnage de l’œil, accédez à **Paramètres** > **Système** > **Étalonnage** > **Étalonnage de l’œil**.

## Forum Aux Questions

### Quels sont les modèles qui clignotent occasionnellement dans les coins inférieurs de l’écran?

Il peut arriver que votre moniteur HoloLens 2 affiche des motifs différents dans les coins inférieur gauche et droit de l’écran. Les exemples ci-dessous (gif animé) sont illustrés ci-dessous. Ce modèle fait partie du fonctionnement normal de votre appareil HoloLens 2 afin d’étalonner l’affichage pour une expérience optimale.

![Modèle biphase](./images/DAT-Biphase-Fiducial.gif) ![Modèle GEO](./images/DAT-GEO-Fiducial.gif)

### Pourquoi ne puis-je pas prendre une photo précise de mon affichage HoloLens2?

L’affichage HoloLens 2 est conçu pour être consulté par l’œil humain. Un système de correction de couleur actif s’adapte aux yeux des utilisateurs sur l’appareil. Par rapport à l'œil humain, les appareils photo voient les environnements différemment et voici quelques facteurs qui peuvent avoir une incidence sur toute incohérence entre ce qu'un appareil photo capture et ce qu'un utilisateur voit.

* **Position des yeux.** L’affichage HoloLens 2 est conçu spécifiquement pour la position oculaire de l’utilisateur. Le HoloLens 2 utilise la technologie de suivi oculaire pour s’adapter à la position oculaire de l’utilisateur. Un appareil photo mal positionné de quelques millimètres peut entraîner une distorsion de l'image. Le positionnement précis avec un appareil photo est difficile et doit correspondre à la position exacte et au relief oculaire pour lesquels l'appareil effectue la correction des couleurs.
* **Mouvement des yeux.** L’affichage s’adapte au mouvement de l’œil d’un utilisateur pour ajuster les couleurs. Les éléments affichés sur l’écran peuvent différer selon que l’utilisateur observe le centre, le bord ou le coin de l’écran. La capture d’une seule image peut au mieux afficher l’apparence de l’écran pour l’axe qui correspond à une direction de regard.
* **Affichage binoculaire.** L’affichage HoloLens 2 est conçu pour être affiché avec les deux yeux. Le cerveau s’adapte à la visualisation de deux images et les fusibles ensemble. Les images d’un seul affichage ignorent les informations de l’autre affichage.
* **Vitesse d'obturation de l'appareil photo.** La vitesse d'obturation de l'appareil photo doit être un multiple exact de 1/120e de seconde. La fréquence d'images affichée par HoloLens est de 120 Hz. En raison de la manière dont le service HoloLens 2 dessine des images, la capture d’un seul cadre suffit également pour reproduire l’expérience visuelle d’un humain. En même temps, si l'appareil se déplace, même par micro-mouvements, le système reprojette l'image sur l'écran pour stabiliser les hologrammes. La capture de plusieurs images tout en conservant la mise en place de la fonctionnalité HoloLens nécessite généralement la configuration d’un laboratoire.
* **Taille de l’ouverture de l’appareil photo.** La taille de l’ouverture de l’appareil photo doit être d’au moins 3 mm pour capturer une image précise. Les appareils photo de téléphone portable équipés de petites ouvertures intègrent la lumière d’une zone plus petite que l’œil humain. L’appareil applique la correction des couleurs pour les modèles observés dans des ouvertures plus grandes. Avec de petites ouvertures, les modèles d’uniformité sont plus nets et restent visibles, même en dépit de corrections de couleur appliquées par le système.
* **Pupille d'entrée de l'appareil photo.** La pupille d’entrée de l'appareil photo doit être d’au moins 3 mm de diamètre pour capturer une image précise. Dans le cas contraire, l’appareil photo capture certains modèles de haute fréquence qui ne sont pas visibles à l’œil. La position des pupilles d’entrée doit se trouver devant l’appareil photo et être positionnée sur la distance de la détente de l’œil pour éviter d’introduire des aberrations et d’autres variantes sur l’image acquise.
* **Position de l'appareil photo.** Les appareils photo qui remplissent les conditions requises pour afficher l’affichage HoloLens2 sont plus grands et il est difficile de positionner l’appareil photo suffisamment près de l’affichage HoloLens 2 pour observer l’image corrigée de couleur. Si l’appareil photo se trouve au mauvais endroit, la correction de couleur peut avoir un impact négatif sur la capture de l’affichage HoloLens 2.
* **Correction d’image.** Les appareils photo numériques et les appareils photo pour smartphones typiques appliquent une courbe de reproduction des tons (TRC) qui augmente le contraste et la couleur pour donner un résultat plus net. Lorsqu'elle est appliquée à un affichage HoloLens2, cette courbe de tons amplifie les non-uniformités.

Il reste néanmoins possible pour les appareils photo industriels spécialisés de capturer des images représentatives à partir de l’affichage HoloLens2. Malheureusement, les appareils photo des smartphones, des consommateurs et des professionnels ne capturent pas des images qui correspondent à ce qu'un utilisateur voit sur HoloLens 2.

### Qu’est-ce que l’étalonnage de l’œil pour afficher la qualité de l’image?

L’affichage HoloLens2 affiche une couleur active pour corriger les images en fonction de la position des yeux de l’utilisateur. [L’étalonnage de l’œil](hololens-calibration.md) fournit deux entrées importantes: (1) la distance interpupillaire (IPD) de l’utilisateur et (2) la direction de chaque œil. Sans étalonnage de l’œil, le système par défaut est une position oculaire sans mouvement oculaire. La différence entre la correction de couleur active et la non-correction dépend de la physiologie de l’utilisateur proprement dit. Par exemple, les utilisateurs qui ont la même IPD que le système par défaut voient moins d’améliorations de la correction de couleur. Bien que les utilisateurs disposant d’une IPD plus étroite ou plus large que le système par défaut, voient plus de modifications apportées à l’image d’affichage.

Notez qu’une nouvelle fonctionnalité de la [Windows Holographic version20H2](hololens-release-notes.md#windows-holographic-version-20h2) commencera à [détecter automatiquement la position des yeux](hololens-calibration.md#auto-eye-position-support). 

### Quelles sont les différences d’affichage entre HoloLens (1ère génération) et HoloLens2?

Parmi les principales demandes que les clients ont adressées à Microsoft après avoir fait l'expérience de l'HoloLens 1, il y avait (1) l'augmentation du champ de vision et (2) l'augmentation de la luminosité. Les développements technologiques ont permis à Microsoft de produire des guides d’onde qui ont doublé la zone de la vue et qui produisent des projecteurs d’éclairage avec un affichage de trois fois plus clair. Le matériel définit la ligne de base pour un trio de compromis pour la qualité de l’image d’affichage: (1) champ-de-vue, (2) luminosité et (3) uniformité des couleurs. L’évolution continue des technologies permet d’améliorer toutes les fonctionnalités sans sacrifier à une autre zone. Au intérimaire, la technologie existante définit les limites disponibles pour ces compromis.

### Quelles améliorations vont améliorer la qualité de l’image HoloLens2?

Bien que de nombreuses investigations aient commencé à améliorer la qualité de l’image, les éléments suivants sont supposés arriver dans les mises à jour à venir:

* **Position automatique des yeux.** Cette fonctionnalité permet d’effectuer les procédures d’étalonnage de l’œil à l’arrière-plan. Les utilisateurs n’auront plus besoin d’utiliser l’étalonnage de l’œil pour que la correction des couleurs soit active. Au lieu de cela, elle fonctionnera tout simplement.
* **Améliorations de l’étalonnage des couleurs.** Cette mise à jour se concentre sur les valeurs de couleur des couleurs plus foncées (par exemple, gris foncé). Pour l’instant, les couleurs de l’estompage prennent un ton rouge. Ce problème se produit également lorsque l’affichage est grisé, l’intégralité de l’écran reprend les couleurs rouge. Ce problème est dû à une activité trop importante dans le canal de couleur rouge pour ces couleurs plus foncées. Nous avons caractérisé les courbes d’éclairage laser à ces couleurs de luminosité et nous travaillons à offrir une procédure d’étalonnage de l’utilisateur. Le résultat présente une plus grande précision de couleur au-delà du spectre de luminosité. Il ne modifie pas l’apparence des arrière-plans blancs à la luminosité entière. Nous continuons à conseiller l’utilisation des modèles de conception en mode foncé dans les applications.
* **Mode Lecture.** Il est possible pour les développeurs d’applications de contourner le champ d’affichage pour obtenir une résolution d’angle supérieure. Les développeurs d’applications peuvent remplacer la matrice de projection de façon à ce que le contenu soit rendu dans la résolution de dessin de l’écran. Cette fonctionnalité entraîne une réduction de 30% de la vue du champ et une augmentation correspondante de la résolution angulaire. Nous avons commencé à présenter cette fonctionnalité au kit de ressources de réalité mixte. Lorsqu’il est disponible, le mode lecture fonctionne sur un système d’exploitation HoloLens 2, car il n’est pas dépendant de la mise à jour du système d’exploitation.

Les mises à jour de système d’exploitation sont automatiquement remises. Vous pouvez également tester les versions antérieures de l’amélioration des logiciels via le programme Insider preview.

### Quelles instructions sont disponibles pour que les développeurs appliquent des principes de conception en mode sombre?

Les utilisateurs bénéficieront d’une expérience optimale pour éviter les arrière-plans. Le mode sombre est un principe de conception utilisé par les applications pour utiliser des arrière-plans de couleur noire ou sombre. Les paramètres système sont définis par défaut sur le mode sombre. Vous pouvez les ajuster en accédant à **Paramètres** > **Système** > **Couleur**.

Il est recommandé aux développeurs de suivre les conseils de conception en mode sombre:

* [Instructions de conception pour les développeurs pour HoloLens](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Tailles de police recommandées](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Lorsqu’un hologramme nécessite un arrière-plan blanc, conserver la taille de l’hologramme plus petit que le champ complet de l’affichage. Cette taille permet aux utilisateurs de placer l’hologramme au centre de l’écran.

### Comment nettoyer un affichage HoloLens2?

Utilisez un chiffon en microfibre pour essuyer doucement la visière. Pour désinfecter la visière, utilisez de l'alcool isopropylique à 70 % pour humidifier légèrement un chiffon puis essuyez la visière. Consultez les instructions complètes dans le [Nettoyage HoloLens2: FAQ](hololens2-maintenance.md).
