---
title: Résolution des problèmes liés à l'affichage de l'HoloLens 2
description: Attentes relatives aux affichages de l'HoloLens 2. Conseils relatifs à la configuration des affichages pour optimiser la qualité de l'image.
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
ms.openlocfilehash: 96bacd79d559bc0adcd42665c4a8b4af856b58b0
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923616"
---
# <a name="hololens-2-display-troubleshooting"></a>Résolution des problèmes liés à l'affichage de l'HoloLens 2

## <a name="overview"></a>Vue d’ensemble
L'affichage de l'HoloLens 2 est une combinaison de guides d'ondes et de projecteurs de lumière. Lorsqu'ils portent le casque, les utilisateurs regardent à travers les guides d'ondes (lentilles situées à l'intérieur de la visière). Les projecteurs de lumière se trouvent à l'intérieur du boîtier, au-dessus du front. L'HoloLens 2 utilise un éclairage laser pour illuminer l'affichage.

## <a name="troubleshooting"></a>Résolution des problèmes

Procédez comme suit pour garantir une qualité visuelle optimale des hologrammes affichés :

* **Augmentez la luminosité de l'affichage.** L'affichage des hologrammes est meilleur lorsque la luminosité est maximale. Lorsque vous portez le casque HoloLens, les boutons de luminosité se trouvent sur le côté gauche de la visière, près de votre tempe.
* **Rapprochez la visière de vos yeux.** Abaissez la visière jusqu'à la position la plus proche de vos yeux.
* **Abaissez la visière.** Essayez de déplacer la protection pour le front vers le bas, ce qui rapprochera la visière de votre nez.
* **[Exécutez l'étalonnage des yeux.](hololens-calibration.md#calibrating-your-hololens-2)** Le système d'affichage utilise votre écart pupillaire et votre regard pour optimiser les images affichées. Si cet étalonnage n'est pas effectué, la qualité de l'image risque d'en pâtir. Pour effectuer l'étalonnage des yeux, accédez à **Paramètres** > **Système** > **Étalonnage** > **Exécuter l'étalonnage des yeux**.
* **Exécutez l'étalonnage des couleurs d'affichage**. Sous [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) et versions ultérieures, vous pouvez **sélectionner un autre profil de couleurs** pour l'affichage de votre HoloLens 2. Cela peut permettre d'obtenir des couleurs plus justes, avec notamment des niveaux de luminosité inférieurs. La fonctionnalité d'étalonnage des couleurs d'affichage se trouve dans l'application **Paramètres**, sur la page **Système > Étalonnage**.

    > [!NOTE]
    > Étant donné que ce paramètre enregistre un nouveau profil de couleurs dans votre microprogramme d'affichage, il s'applique à chaque appareil (et non à chaque compte d'utilisateur).

### <a name="how-to-use-display-color-calibration"></a>Utiliser l'étalonnage des couleurs d'affichage
1. Lancez l'application **Paramètres** et accédez à **Système > Étalonnage**.
1. Sous **Étalonnage des couleurs d'affichage**, sélectionnez le bouton **Exécuter l'étalonnage des couleurs d'affichage**.
1. L'expérience d'étalonnage des couleurs d'affichage se lance et vous invite à vous assurer que votre visière est bien positionnée.
1. Une fois que vous aurez parcouru les boîtes de dialogue d'instructions, la luminosité de l'affichage sera automatiquement réduite à 30 %.
    > [!TIP]
    > Si nécessaire, vous pouvez ajuster manuellement le niveau de luminosité de l'HoloLens 2 à l'aide des boutons de réglage de la luminosité situés sur le côté gauche de l'appareil.
1. Sélectionnez les boutons 1 à 6 pour essayer instantanément chaque profil de couleurs et trouver celui qui vous convient le mieux (il s'agit généralement du profil qui propose la scène la plus neutre, avec la gamme de gris et les tons chair attendus).

    ![Étalonnage des couleurs d'affichage](images/color-cal-ui.png)
    
6. Lorsque le profil sélectionné vous convient, cliquez sur le bouton **Enregistrer et quitter**.
1. Si vous préférez n'apporter aucune modification, cliquez sur le bouton **Annuler et quitter** et vos modifications seront annulées.

> [!TIP]
> Voici quelques conseils utiles à garder à l'esprit lors de l'utilisation du paramètre d'étalonnage des couleurs d'affichage :
> - Vous pouvez à tout moment procéder à un nouvel étalonnage des couleurs d'affichage à partir de Paramètres.
> - Si un utilisateur de l'appareil a déjà utilisé le paramètre pour modifier les profils de couleurs, la date et l'heure de la modification la plus récente apparaissent sur la page Paramètres.
> - Lorsque vous procédez à un nouvel étalonnage des couleurs d'affichage, le profil de couleurs précédemment enregistré est mis en surbrillance et le Profil 0 n'apparaît pas (car le Profil 0 représente le profil de couleurs d'origine).
> - Si vous le souhaitez, vous pouvez revenir au profil de couleurs d'origine à partir de la page Paramètres (voir [Réinitialiser le profil de couleurs](#how-to-reset-color-profile)).

### <a name="how-to-reset-color-profile"></a>Réinitialiser le profil de couleurs

Si le profil de couleurs personnalisé enregistré sur votre HoloLens 2 ne vous convient pas, vous pouvez rétablir le profil de couleurs d'origine de l'appareil :
1. Lancez l'application **Paramètres** et accédez à **Système > Étalonnage**.
1. Sous **Étalonnage des couleurs d'affichage**, sélectionnez le bouton **Rétablir le profil de couleurs par défaut**.
1. Lorsque la boîte de dialogue s'ouvre, sélectionnez **Redémarrer** si vous êtes prêt à redémarrer HoloLens 2 et à appliquer vos modifications.

### <a name="top-display-color-calibration-known-issues"></a>Principaux problèmes signalés lors de l'étalonnage des couleurs d'affichage

- Sur la page Paramètres, la chaîne d'état qui indique la date de la dernière modification du profil de couleurs sera obsolète tant que vous n'aurez pas rechargé cette page. 
    - **Solution de contournement** : sélectionnez une autre page Paramètres, puis sélectionnez à nouveau la page Étalonnage.
- Si votre HoloLens 2 se met en veille pendant l'étalonnage des couleurs d'affichage, il reprendra plus tard dans l'accueil réalité mixte et le niveau de luminosité reste réduit.
- Vous devrez peut-être appuyer plusieurs fois sur les boutons de réglage de la luminosité situés sur le côté gauche de votre appareil pour qu'ils fonctionnent comme prévu.
- La localisation n'est pas encore terminée pour certains marchés.

## <a name="faq"></a>Questions fréquentes (FAQ)

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>À quoi correspondent les motifs qui apparaissent occasionnellement sous forme de flashs dans les coins inférieurs de l'affichage ?

De temps en temps, votre HoloLens 2 affichera différents motifs dans les coins inférieurs gauche et droit de l'affichage. Des exemples sont présentés ci-dessous (GIF animés). Ceci fait partie du fonctionnement normal de votre appareil HoloLens 2 afin d'étalonner l'affichage pour une expérience optimale.

![Motif biphase](./images/DAT-Biphase-Fiducial.gif) ![Motif GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Pourquoi est-ce que je ne parviens pas à prendre une photo correcte de l'affichage de mon HoloLens 2 ?

L'affichage de l'HoloLens 2 est conçu pour être vu par l'œil humain. L'appareil dispose d'un système de correction active des couleurs qui s'adapte aux yeux de l'utilisateur. Les appareils photo ne voient pas les environnements comme l'œil humain. Vous trouverez ci-dessous quelques facteurs qui peuvent avoir un impact sur les incohérences entre ce qu'un appareil photo capture et ce que voit un utilisateur.

* **Position des yeux.** L'affichage de l'HoloLens 2 est conçu pour la position des yeux de l'utilisateur. L'HoloLens 2 utilise la technologie de suivi oculaire pour s'adapter à la position des yeux de l'utilisateur. Un appareil photo mal positionné de quelques millimètres peut entraîner une distorsion de l'image. Il est difficile d'effectuer un positionnement précis avec un appareil photo, car ce positionnement doit correspondre à la position exacte et au dégagement oculaire pour lesquels l'HoloLens 2 effectue la correction des couleurs.
* **Mouvement des yeux.** L'affichage s'adapte au mouvement des yeux de l'utilisateur pour ajuster les couleurs. Le contenu visible peut être différent selon que l'utilisateur regarde le centre, le bord ou le coin de l'affichage. La capture d'une seule image peut au mieux afficher ce qui correspond à l'axe de la direction du regard.
* **Vision binoculaire.** L'affichage de l'HoloLens 2 est conçu pour être regardé avec les deux yeux. Le cerveau s'adapte à la vision de deux images et les fusionne. Les images d'un seul affichage ignorent les informations de l'autre affichage.
* **Temps d'exposition de l'appareil photo.** Le temps d'exposition de l'appareil photo doit être un multiple exact de 1/120e de seconde. La fréquence d'images de l'affichage de l'HoloLens est de 120 Hz. En raison de la façon dont l'HoloLens 2 dessine les images, la capture d'une seule image n'est pas non plus suffisante pour reproduire l'expérience de l'œil humain. Dans le même temps, si l'appareil bouge, même s'il s'agit de microdéplacements, le système reprojette l'image sur l'affichage pour stabiliser les hologrammes. La capture de plusieurs images tout en empêchant l'HoloLens de bouger nécessite généralement une configuration en laboratoire.
* **Ouverture de l'appareil photo.** L'ouverture de l'appareil photo doit être d'au moins 3 mm pour capturer une image précise. Les appareils photo à petite ouverture des téléphones portables intègrent la lumière à partir d'une zone plus petite que l'œil humain. L'appareil applique une correction des couleurs pour les motifs observés par des ouvertures plus grandes. Avec de petites ouvertures, les motifs uniformité sont plus nets et restent visibles malgré les corrections de couleurs appliquées par le système.
* **Pupille d'entrée de l'appareil photo.** La pupille d'entrée de l'appareil photo doit être d'au moins 3 mm de diamètre pour capturer une image précise. Sinon, l'appareil photo capture des motifs à haute fréquence non visibles à l'œil nu. La pupille d'entrée doit être positionnée à la fois en face de l'appareil photo et à la distance du dégagement oculaire pour éviter d'introduire des aberrations et d'autres variations sur l'image capturée.
* **Position de l'appareil photo.** Les appareils photo qui remplissent les conditions requises pour capturer l'affichage de l'HoloLens 2 sont plus grands, et il est difficile de positionner l'appareil photo suffisamment près de l'affichage de l'HoloLens 2 pour observer l'image corrigée en couleur. Si l'appareil photo est mal placé, la correction des couleurs peut avoir un impact négatif sur la capture de l'affichage de l'HoloLens 2.
* **Correction de l'image.** Les appareils photo numériques et les appareils photo des smartphones classiques appliquent une courbe de reproduction des tons (TRC) qui intensifie le contraste et les couleurs pour obtenir un résultat plus net. Lorsqu'elle est appliquée à l'affichage d'un HoloLens 2, cette courbe de reproduction des tons amplifie les non-uniformités.

Il reste néanmoins possible pour les appareils photo industriels spécialisés de capturer des images représentatives de l'affichage de l'HoloLens 2. Malheureusement, les appareils photo pour smartphones, grand public et professionnels ne sont pas en mesure de capturer des images correspondant à ce qu'un utilisateur voit sur l'HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Quel est l'effet de l'étalonnage des yeux sur la qualité de l'image affichée ?

L'affichage de l'HoloLens 2 corrige activement les couleurs des images en fonction de la position des yeux de l'utilisateur. L'[étalonnage des yeux](hololens-calibration.md) fournit deux entrées importantes : (1) l'écart pupillaire de l'utilisateur et (2) la direction dans laquelle chaque œil regarde. Sans étalonnage, le système utilise par défaut une position nominale des yeux sans mouvement oculaire. La différence entre une correction active des couleurs et l'absence de correction dépend de la physiologie de l'utilisateur. Par exemple, les utilisateurs qui ont un écart pupillaire proche de la valeur par défaut du système verront moins d'améliorations de la correction des couleurs. En revanche, les utilisateurs qui ont un écart pupillaire beaucoup plus étroit ou plus large que la valeur par défaut du système verront plus de changements dans l'image affichée.

Notez qu'une nouvelle fonctionnalité de [Windows Holographic version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) permettra de [détecter automatiquement la position des yeux](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Quelles sont les différences d'affichage entre l'HoloLens (1ère génération) et l'HoloLens 2 ?

Parmi les principales demandes adressées à Microsoft par les utilisateurs de l'HoloLens 1 figuraient (1) l'augmentation du champ de vision et (2) l'augmentation de la luminosité. Des avancées technologiques ont permis à Microsoft de produire des guides d'ondes qui ont doublé la surface du champ de vision et de produire des projecteurs de lumière offrant un affichage jusqu'à trois fois plus lumineux. Le matériel pose les bases de trois compromis à prendre en compte pour la qualité de l'image affichée : (1) le champ de vision, (2) la luminosité et (3) l'uniformité des couleurs. Les progrès technologiques permettent d'améliorer tous ces aspects sans sacrifier les autres. Entre-temps, la technologie existante fixe les limites disponibles pour ces compromis.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Quelles sont les prochaines modifications qui permettront d'améliorer la qualité de l'image de l'HoloLens 2 ?

De nombreuses recherches sont encore cours pour améliorer la qualité de l'image, mais les améliorations suivantes devraient être disponibles dans les prochaines mises à jour :

* **Position automatique des yeux.** Cette fonctionnalité permettra d'effectuer l'étalonnage des yeux en arrière-plan. Les utilisateurs n'auront plus besoin de procéder à l'étalonnage des yeux pour que la correction active des couleurs fonctionne. Elle fonctionnera automatiquement.
* **Améliorations de l'étalonnage des couleurs.** Cette mise à jour se concentre sur les valeurs chromatiques des couleurs les plus sombres (comme le gris foncé). Actuellement, les couleurs sombres prennent un ton rouge. Ce problème survient également lorsque la luminosité de l'affichage est réduite ; l'intégralité de l'affichage prend alors des teintes rouges. Ce problème est dû à une trop grande activité dans le canal de couleur rouge pour ces couleurs sombres. Nous avons caractérisé les courbes d'éclairage laser sur ces couleurs plus sombres et nous espérons proposer une procédure d'étalonnage de l'utilisateur. La précision des couleurs seront ainsi accrue dans le spectre de luminosité. Et cela ne changera pas l'apparence des arrière-plans blancs à pleine luminosité. Nous continuons à conseiller l'utilisation de modèles de conception en mode sombre dans les applications.
* **Mode Lecture.** Les développeurs d'applications ont la possibilité de sacrifier le champ de vision de l'affichage pour accroître la résolution angulaire. Ils peuvent remplacer la matrice de projection afin d'afficher le contenu selon la résolution de dessin de l'affichage. Cette fonctionnalité entraîne une réduction de 30 % du champ de vision et une augmentation correspondante de la résolution angulaire. Nous préparons actuellement l'introduction de cette fonctionnalité dans le kit de ressources [Mixed Reality Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). Lorsqu'il sera disponible, le mode Lecture fonctionnera sur n'importe quel système d'exploitation HoloLens 2 (puisqu'il ne dépend pas d'une mise à jour du système d'exploitation).

Les mises à jour du système d'exploitation sont fournies automatiquement. Vous pouvez également tester les premières versions des améliorations logicielles via le programme Insider Preview.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Quels conseils les développeurs doivent-ils suivre pour appliquer les principes de conception en mode sombre ?

Les utilisateurs bénéficieront d'une expérience optimale s'ils évitent les arrière-plans blancs. Le mode sombre est un principe de conception utilisé par les applications pour les arrière-plans noirs ou de couleur sombre. Par défaut, les paramètres système sont en mode sombre et peuvent être ajustés en accédant à **Paramètres** > **Système** > **Couleur**.

Il est recommandé aux développeurs de suivre les conseils de conception en mode sombre :

* [Conseils de conception à l'intention des développeurs pour les affichages HoloLens](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Tailles de police recommandées](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Lorsqu'un hologramme nécessite un arrière-plan blanc, sa taille doit être inférieure au champ de vision complet de l'affichage. Cette taille permet aux utilisateurs de placer l'hologramme au centre de l'affichage.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Comment nettoyer l'affichage d'un HoloLens 2 ?

Utilisez un chiffon en microfibres pour essuyer délicatement la visière. Pour désinfecter la visière, essuyez-la à l'aide d'un chiffon préalablement humidifié avec de l'alcool isopropylique à 70 %. Consultez les conseils complets fournis dans le document [FAQ sur le nettoyage de l'HoloLens 2](hololens2-maintenance.md).
