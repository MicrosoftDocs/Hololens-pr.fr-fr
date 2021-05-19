---
title: Améliorer la qualité visuelle et le confort
description: Découvrez comment étalonner votre distance interpupillaire (DIP) pour améliorer la qualité de vos éléments visuels sur les appareils HoloLens.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: étalonnage, confort, visuels, qualité, dip, HoloLens, Windows Mixed Reality, casques VR
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283545"
---
# Améliorer la qualité visuelle et le confort

HoloLens 2 et HoloLens (1re génération) fonctionnent mieux lorsqu’ils sont étalonnés en fonction de vos yeux.

Même si ces deux appareils doivent être étalonnés pour offrir la meilleure qualité d’affichage des hologrammes, ils utilisent différentes technologies et techniques d’étalonnage.  Accédez à [Étalonnage HoloLens 2](#calibrating-your-hololens-2) ou [Étalonnage HoloLens (1re génération)](#calibrating-your-hololens-1st-gen).

## Étalonner votre HoloLens 2

HoloLens 2 utilise une technologie de suivi visuel pour améliorer votre utilisation et interagir avec l’environnement virtuel. Le fait d’étalonner HoloLens 2 garantit qu’il peut effectuer un suivi précis des yeux (et des yeux d’autres personnes qui utilisent l’appareil). Il vous aide également à utiliser le confort de l’utilisateur, l’alignement de l’hologramme et le suivi de main. Après l’étalonnage, les hologrammes s’affichent correctement même lorsque la visière se déplace sur votre tête.

HoloLens 2 demande à l’utilisateur d’étalonner l’appareil dans les cas suivants :

- L’utilisateur utilise l’appareil pour la première fois
- L’utilisateur a précédemment désactivé le processus d’étalonnage
- Le processus d’étalonnage n’a pas réussi la dernière fois que l’utilisateur a utilisé l’appareil
- L’utilisateur a supprimé ses profils d’étalonnage
- L’utilisateur éteint, puis rallume l’appareil, et les circonstances ci-dessus s’appliquent 


![Invite d’étalonnage pour l’adaptation aux yeux.](./images/07-et-adjust-for-your-eyes.png)

Au cours de ce processus, vous devez regarder un ensemble de cibles (gemmes). Si vous clignotez pendant l’étalonnage, essayez de rester concentré sur les gemmes au lieu d’autres objets dans la salle.  Le focus sur la gemme permet à HoloLens d’en apprendre davantage sur la position de votre oeil sur l’affichage de votre environnement holographique.

![Invite de calibration indiquant aux utilisateurs de garder la tête fixe et de suivre les points avec leurs yeux.](./images/07-et-hold-head-still.png)

![Invite de calibrage avec un exemple de gemme.](./images/08-et-gems.png)

![Ajustement d’une invite de calibrage.](./images/09-et-adjusting.png)

Si l’étalonnage a réussi, un écran de réussite s’affiche.  Dans le cas contraire, si vous souhaitez en savoir plus, veuillez consulter la rubrique [sur le diagnostic des échecs d’étalonnage](#troubleshooting-hololens-2-calibration).

![Réussite de l’invite d’étalonnage.](./images/10-et-success.png)

### Étalonnage lors du partage d’un appareil ou d’une session

Plusieurs utilisateurs peuvent partager un appareil HoloLens 2 sans qu’il soit nécessaire de procéder à la configuration de chaque personne. Lorsqu’un nouvel utilisateur place l’appareil sur sa tête pour la première fois, HoloLens 2 invite automatiquement l’utilisateur à étalonner les visuels. Lorsqu’un utilisateur qui a déjà calibré des visuels place l’appareil sur sa tête, l’affichage s’ajuste en toute transparence pour une qualité d’affichage confortable.  

### Démarrage manuel du processus d’étalonnage

1. Utilisez le mouvement associé au menu Démarrer pour ouvrir le [menu **Démarrer**](hololens2-basic-usage.md#start-gesture).
1. Si l’application Paramètres n’est pas épinglée au **menu Démarrer**, sélectionnez **Toutes les applications**.
1. Sélectionnez **Paramètres**, puis **Système** > **Étalonnage** > **Étalonnage des yeux** > **Exécuter l’étalonnage des yeux**.

   ![Application Paramètres présentant l’option d’étalonnage des yeux](./images/C-Settings.Calibration.png)

### Prise en charge automatique de la position des yeux

Dans HoloLens 2, les positions oculaires permettent un positionnement précis des hologrammes, une expérience d’affichage confortable et une qualité d’affichage améliorée. Les positions des yeux se calculent en interne lors du calcul du suivi oculaire. Toutefois, cela nécessite que chaque utilisateur parcourt le calibrage du suivi oculaire, même lorsque l’utilisation ne nécessite pas le pointage du regard.

La **position automatique des yeux** permet, dans ces scénarios, de calculer sans interaction la position des yeux de l’utilisateur. La position automatique des yeux commence à fonctionner automatiquement en arrière-plan dès que l’utilisateur met l’appareil sous tension. Si l’utilisateur n’a pas encore effectué de suivi oculaire, la fonctionnalité de position automatique des yeux commencera à fournir la position des yeux de l’utilisateur au système d’affichage après un temps de traitement de 20 à 30 secondes. L’appareil ne conserve pas les données utilisateur, et ce processus se répète si l’utilisateur met l’appareil hors tension, puis de nouveau sous tension ou si l’appareil redémarre ou sort du mode veille.

Il existe certaines modifications de comportement système avec la fonctionnalité de position automatique des yeux quand un utilisateur n’ayant pas effectué de calibrage utilise l’appareil. Dans ce contexte, le terme d’utilisateur non étalonné fait référence à une personne qui n’a pas déjà suivi le processus d’étalonnage du suivi oculaire sur l’appareil.

| Application active | Comportement Antérieur | Comportement de Windows Holographique, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Application non compatible avec le regard ou Holographic Shell |Affichage du dialogue de l’invite de calibrage du suivi oculaire. | Aucune invite n’est affichée. |
| Application compatible avec le regard | Affichage du dialogue de l’invite de calibrage du suivi oculaire. | L’invite de calibrage du suivi oculaire s’affiche uniquement lorsque l’application accède à un flux du regard. |

Si l’utilisateur passe d’une application non compatible avec le regard à une application qui accède aux données du regard, l’invite d’étalonnage s’affiche. 

Tout autre comportement du système est semblable à celui d’un utilisateur actuel n’ayant pas d’étalonnage du suivi oculaire actif. Par exemple, le geste de démarrage d’une seule main n’est pas activé. Les fonctionnalités Out-Of-Box-Experience de la configuration initiale ne subissent aucune modification.

Dans le cas d’expériences nécessitant des données du regard ou un positionnement d’hologramme précis, nous conseillons aux utilisateurs sans étalonnage d’exécuter l’étalonnage du suivi oculaire. Vous pouvez y accéder depuis l’invite de calibrage du suivi oculaire ou en lançant l’application Paramètres depuis le menu de démarrage, puis en sélectionnant **Système > Étalonnage > Étalonnage des yeux > Exécuter l’étalonnage des yeux**.

#### Invite d’étalonnage différé

Avec la fonction de position automatique des yeux, la boîte de dialogue d’invite d’étalonnage du suivi oculaire ne s’affiche pas jusqu’à ce qu’une application demande des données de regard. Cela garantit qu’aucune invite à l’utilisateur n’apparaît lorsque l’application active ne nécessite pas de regard. Si l’application requiert des données de regard et que l’utilisateur actuel n’a pas suivi le processus d’étalonnage, une invite d’étalonnage s’affiche sur son système. Ce comportement permet d’afficher l’invite d’étalonnage du suivi oculaire à une heure appropriée pour l’expérience. Cette méthode est recommandée pour les raisons suivantes:

1.  Le dialogue d’Invite de Calibration du Suivi Oculaire fournit à l’utilisateur des détails sur la nécessité du suivi oculaire.
2.  Offre à l’utilisateur la possibilité de décliner la calibration des yeux.

Si l’utilisateur choisit de lancer la Calibration du Suivi Oculaire, la mise au point retourne à l’application d’origine après le calibrage. 

### Résolution des problèmes de calibrage de HoloLens 2

L’étalonnage devrait fonctionner pour la plupart des personnes, mais ce n’est pas toujours le cas.
  
Voici quelques raisons potentielles d’échec de l’étalonnage :

- Si vous êtes distrait et que vous ne suivez pas les cibles d’étalonnage
- La visière est sale, rayée ou elle n’est pas positionnée correctement
- Lunettes sales ou rayées
- Certains types de lentilles de contact ou de lunettes (lentilles de contact colorées, certains lentilles de contact toriques, lunettes de blocage infrarouge, certains lunettes correctrices fortes, lunettes de soleil ou similaires)
- Maquillage plus prononcé et extensions de cils
- Cheveux ou montures de lunettes épaisses si ceux-ci empêchent l’appareil de voir vos yeux
- Certaines physiologies d’yeux, maladies ophtalmiques ou chirurgies oculaires. Exemples : yeux étroits, longs cils, amblyopie, nystagmus, certains cas de LASIK ou autres types de chirurgie oculaire

Si l’étalonnage ne fonctionne pas correctement, procédez comme suit :

- Nettoyez la visière de l’appareil
- Nettoyez les lunettes
- Rapprochez la visière de l’appareil le plus possible de vos yeux
- Retirez les objets qui pourraient se trouver dans le champ de votre visière (par exemple, vos cheveux)
- Allumez une lumière dans la pièce ou éloignez-vous de la lumière directe du soleil

Si vous avez suivi toutes les recommandations et que l’étalonnage a échoué, vous pouvez désactiver l’invite d’étalonnage dans Paramètres. N’hésitez pas à nous faire part de vos commentaires dans [Hub de commentaires](hololens-feedback.md).

Consultez également les informations relatives à la [résolution des problèmes de couleur ou de luminosité de l’image.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

La configuration de la DIP ne s’applique pas à HoloLens 2, car le système calcule les positions oculaires. 

### Données d’étalonnage et sécurité

Les informations d’étalonnage résident localement sur l’appareil et ne sont associées à aucune information de compte. Aucun enregistrement n’indique qui a utilisé l’appareil sans étalonnage. Par conséquent, les nouveaux utilisateurs doivent, sur invite, étalonner les visuels à la première utilisation de l’appareil, tout comme les utilisateurs ayant choisi de ne pas réaliser l’étalonnage auparavant ou si l’étalonnage a échoué.

L’appareil peut stocker localement jusqu’à 50 profils d’étalonnage. Une fois ce nombre atteint, l’appareil supprime automatiquement le plus ancien profil inutilisé.

Les informations d’étalonnage peuvent toujours être supprimées de l’appareil dans **Paramètres** > **Confidentialité** > **Suivi oculaire**.  

### Désactiver l’étalonnage

Vous pouvez également désactiver l’invite d’étalonnage en procédant comme suit :

1. Sélectionnez **Paramètres** > **Système** > **Étalonnage**.
1. Désactivez l’option **Quand une nouvelle personne utilise ce HoloLens, demander automatiquement un étalonnage des yeux**.

> [!IMPORTANT]
> Ce paramètre risque de nuire à la qualité et au confort du rendu des hologrammes.  Lorsque vous désactivez ce paramètre, les fonctionnalités qui dépendent du suivi oculaire (par exemple, le défilement du texte) ne fonctionnent plus dans les applications immersives.

### Technologie de suivi oculaire de HoloLens 2

L’appareil utilise sa technologie de suivi oculaire pour améliorer la qualité d’affichage et garantir que tous les hologrammes sont positionnés de manière précise et confortable pour un affichage en 3D. Étant donné qu’il utilise les yeux comme points de repère, l’appareil peut s’ajuster à chaque utilisateur et adapter ses visuels si le casque se déplace légèrement en cours d’utilisation.  Tous les ajustements sont effectués à la volée, sans nécessiter d’ajustement manuel.
> [!NOTE]
> La configuration de la DIP ne s’applique pas à Hololens 2, car le système calcule les positions oculaires.

Les applications HoloLens utilisent le suivi visuel pour suivre la direction de votre regard en temps réel. C’est la principale fonctionnalité que les développeurs peuvent utiliser pour tirer parti d’un niveau inédit de contexte, de compréhension et d’interactions humaines au sein de l’expérience holographique. Les développeurs n’ont rien à faire pour utiliser cette fonctionnalité.

## Étalonnage de votre HoloLens (1re génération)

HoloLens (1ère génération) ajuste l’affichage des hologrammes en fonction de votre [distance interpupillaire](https://en.wikipedia.org/wiki/Interpupillary_distance) (DIP) Si la DIP n’est pas précise, les hologrammes peuvent apparaître instables ou à une distance incorrecte. Vous pouvez améliorer la qualité de vos visuels en étalonnant l’appareil selon votre distance interpupillaire (DIP).

Lorsque vous définissez votre appareil HoloLens (1ère génération), il vous invite à étalonner vos visuels une fois que Cortana s’est présentée. Nous vous recommandons de réaliser la procédure d’étalonnage au cours de cette phase d’installation. Néanmoins, vous pouvez l’ignorer en attendant que Cortana vous y invite, puis en indiquant « Ignorer ».

Pendant le processus d’étalonnage, HoloLens vous demande d’aligner votre doigt avec une série de six cibles par œil. HoloLens utilise ce processus pour définir correctement l’écart pupillaire de vos yeux.

![Écran d’alignement IPD d’un doigt lors de la deuxième étape](./images/ipd-finger-alignment-300px.jpg)

### Démarrer manuellement le processus d’étalonnage

Si vous avez besoin de mettre à jour l’étalonnage ou si un nouvel utilisateur doit l’ajuster, vous pouvez exécuter l’application d’étalonnage manuellement à tout moment. L’application d’étalonnage est installée par défaut. Vous pouvez y accéder à l’aide du menu **Démarrer** ou de l’application Paramètres.

Pour exécuter l’application Étalonnage à l’aide du menu **Démarrer**, procédez comme suit :

1. Utilisez le geste [écarter les doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.
1. Pour afficher toutes les applications, sélectionnez **+**.
1. Sélectionnez **Étalonnage**.

![Accès à l’application d’étalonnage à partir de l’interpréteur de commandes](./images/calibration-shell.png)

![Application d’étalonnage affichée sous la forme d’un cube dynamique après son lancement](./images/calibration-livecube-200px.png)

Pour utiliser l’application Paramètres pour exécuter l’application Étalonnage, procédez comme suit :

1. Utilisez le geste [écartement des doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.
1. Si **Paramètres** n’est pas épinglé sur le menu **Démarrer**, sélectionnez **+** pour afficher toutes les applications.
1. Sélectionnez **Paramètres**.
1. Sélectionnez **Système** > **Utilitaires** > **Ouvrir Étalonnage**.

![Lancement de l’application Ouvrir Étalonnage à partir de l’application Paramètres](./images/calibration-settings-500px.jpg)

## Casques immersifs

Certains casques immersifs permettent de personnaliser le paramètre d’écart pupillaire. Pour modifier l’écart pupillaire de votre casque, ouvrez l’application Paramètres, sélectionnez **Réalité mixte** > **Affichage du casque**, puis déplacez le curseur. Les modifications sont apportées en temps réel dans votre casque. Si vous connaissez votre écart pupillaire, peut-être après une visite chez un opticien, vous pouvez le saisir directement.

Vous pouvez également régler ce paramètre sur votre PC en sélectionnant **Paramètres** > **Réalité mixte** > **Affichage du casque**.

Si votre casque ne prend pas en charge la personnalisation de la DIP, ce paramètre est désactivé.
