---
title: Améliorer la qualité visuelle et le confort
description: L’étalonnage de votre écart pupillaire (IPD) peut améliorer la qualité de vos visuels. Les casques immersifs HoloLens et Windows Mixed Reality permettent de personnaliser l’IPD.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: étalonnage, confort, visuels, qualité, écart pupillaire
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a4a5478f396dff9eef84540286e0fa9672172076
ms.sourcegitcommit: 9197b9d507d8b9b195bdf512d1b832888b53162d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899096"
---
# Améliorer la qualité visuelle et le confort

HoloLens 2 et HoloLens (1regénération) fonctionnent mieux lorsqu’ils sont étalonnés en fonction de vos yeux.

Même si ces deux appareils doivent être étalonnés pour offrir la meilleure qualité d’affichage des hologrammes, ils utilisent différentes technologies et techniques d’étalonnage.  Accédez à [Étalonnage HoloLens2](#calibrating-your-hololens-2) ou [Étalonnage HoloLens (1regénération)](#calibrating-your-hololens-1st-gen).

## Étalonner votre HoloLens 2

HoloLens 2 utilise une technologie de suivi visuel pour améliorer votre utilisation et interagir avec l’environnement virtuel. Le fait d’étalonner HoloLens 2 garantit qu’il peut effectuer un suivi précis des yeux (et des yeux d’autres personnes qui utilisent l’appareil). Il vous aide également à utiliser le confort de l’utilisateur, l’alignement de l’hologramme et le suivi de main. Après l’étalonnage, les hologrammes s’affichent correctement même lorsque la visière se déplace sur votre tête.

HoloLens 2 demande à l’utilisateur d’étalonner l’appareil dans les cas suivants:

- L’utilisateur utilise l’appareil pour la première fois
- L’utilisateur a précédemment désactivé le processus d’étalonnage
- Le processus d’étalonnage n’a pas réussi lors de la dernière utilisation de l’appareil par l’utilisateur.
- L’utilisateur a supprimé ses profils d’étalonnage
- L'appareil est retiré et remis en marche et l'une des circonstances ci-dessus s'applique 


![Invite d’étalonnage](./images/07-et-adjust-for-your-eyes.png)

Au cours de ce processus, vous devez regarder un ensemble de cibles (gemmes). Si vous clignotez pendant l’étalonnage, essayez de rester concentré sur les gemmes au lieu d’autres objets dans la salle.  Cela permet à HoloLens d’en savoir plus sur la position de votre œil pour afficher votre univers holographique.

![Invite d’étalonnage](./images/07-et-hold-head-still.png)

![Invite d’étalonnage](./images/08-et-gems.png)

![Invite d’étalonnage](./images/09-et-adjusting.png)

Si l’étalonnage a réussi, un écran de réussite s’affiche.  Si ce n’est pas le cas, découvrez la façon de diagnostiquer les échecs d’étalonnage [ici](#troubleshooting-hololens-2-calibration).

![Invite d’étalonnage](./images/10-et-success.png)

### Étalonnage lors du partage d’un appareil ou d’une session

Plusieurs utilisateurs peuvent partager un appareil HoloLens 2 sans qu’il soit nécessaire de procéder à la configuration de chaque personne. Lorsqu’un nouvel utilisateur place l’appareil sur sa tête pour la première fois, HoloLens 2 invite automatiquement l’utilisateur à étalonner les visuels. Lorsqu’un utilisateur qui a déjà calibré des visuels place l’appareil sur sa tête, l’affichage s’ajuste en toute transparence pour une qualité d’affichage confortable.  

### Démarrage manuel du processus d’étalonnage

1. Utilisez le mouvement associé au menu Démarrer pour ouvrir le [menu **Démarrer**](hololens2-basic-usage.md#start-gesture).
1. Si l’application Paramètres n’est pas épinglée au **menu Démarrer**, sélectionnez **Toutes les applications**.
1. Sélectionnez **Paramètres**, puis **Système** > **Étalonnage** > **Étalonnage des yeux** > **Exécuter l’étalonnage des yeux**.

   ![Application Paramètres présentant l’option d’étalonnage des yeux](./images/C-Settings.Calibration.png)

### Résolution des problèmes d’étalonnage d’HoloLens 2

L’étalonnage devrait fonctionner pour la plupart des personnes, mais ce n’est pas toujours le cas.
  
Voici quelques raisons potentielles d’échec de l’étalonnage:

- Si vous êtes distrait et que vous ne suivez pas les cibles d’étalonnage
- La visière est sale, rayée ou elle n’est pas positionnée correctement
- Lunettes sales ou rayées
- Certains types de lentilles de contact ou de lunettes (lentilles de contact colorées, certains lentilles de contact toriques, lunettes de blocage infrarouge, certains lunettes correctrices fortes, lunettes de soleil ou similaires)
- Maquillage plus prononcé et certaines extensions de cils
- Les cheveux ou des montures de lunettes épaisses si ceux-ci empêchent l’appareil de voir vos yeux
- Certaines physiologies d’yeux, maladies ophtalmiques ou chirurgies oculaires, comme les yeux étroits, les longs cils, l’amblyopie, les nystagmus, certains cas de LASIK ou autres types de chirurgie oculaire

Si l’étalonnage ne fonctionne pas correctement, procédez comme suit:

- Nettoyez la visière de l’appareil
- Nettoyez les lunettes
- Rapprochez la visière de l’appareil le plus possible de vos yeux
- Retirez les objets qui pourraient se trouver dans le champ de votre visière (par exemple, vos cheveux)
- Allumez une lumière dans la pièce ou éloignez-vous de la lumière directe du soleil

Si vous avez suivi toutes les recommandations et que l’étalonnage a échoué, vous pouvez désactiver l’invite d’étalonnage dans les paramètres. N’hésitez pas à nous faire part de vos commentaires dans [Hub de commentaires](hololens-feedback.md).

Consultez également les informations relatives à la [résolution des problèmes de couleur ou de luminosité de l’image.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Notez que la configuration de IPD ne s’applique pas à HoloLens 2, car les positions oculaires sont calculées par le système. 

### Données d’étalonnage et sécurité

Les informations d’étalonnage sont stockées localement sur l’appareil et ne sont associées à aucune information de compte. Il n’existe aucun enregistrement de qui a utilisé l’appareil sans étalonnage. Cela signifie que chaque nouvel utilisateur est invité à étalonner les visuels à la première utilisation de l’appareil, tout comme les utilisateurs ayant choisi de ne pas réaliser l’étalonnage auparavant ou si l’étalonnage a échoué.

L’appareil peut stocker localement jusqu’à 50 profils d’étalonnage. Une fois ce nombre atteint, l’appareil supprime automatiquement le plus ancien profil inutilisé.

Les informations d’étalonnage peuvent toujours être supprimées de l’appareil dans **Paramètres** > **Confidentialité** > **Suivi oculaire**.  

### Désactiver l’étalonnage

Vous pouvez également désactiver l’invite d’étalonnage en procédant comme suit:

1. Sélectionnez **Paramètres** > **Système** > **Étalonnage**.
1. Désactivez l’option **Quand une nouvelle personne utilise ce HoloLens, demander automatiquement un étalonnage des yeux**.

> [!IMPORTANT]
> Ce paramètre risque de nuire à la qualité et au confort du rendu des hologrammes.  Lorsque vous désactivez ce paramètre, les fonctionnalités qui dépendent du suivi oculaire (par exemple, le défilement du texte) ne fonctionnent plus dans les applications immersives.

### Technologie de suivi oculaire de HoloLens2

L’appareil utilise sa technologie de suivi oculaire pour améliorer la qualité d’affichage et garantir que tous les hologrammes sont positionnés de manière précise et confortable pour un affichage en 3D. Étant donné qu’il utilise les yeux comme points de repère, l’appareil peut s’ajuster à chaque utilisateur et adapter ses visuels si le casque se déplace légèrement en cours d’utilisation.  Tous les ajustements sont effectués à la volée, sans nécessiter d’ajustement manuel.
> [!NOTE]
> La configuration de IPD ne s’applique pas à HoloLens 2, car les positions oculaires sont calculées par le système.

Les applications HoloLens utilisent le suivi visuel pour suivre l’endroit où vous regardez en temps réel. C’est la principale fonctionnalité que les développeurs peuvent utiliser pour tirer parti d’un nouveau niveau de contexte, compréhension et interactions humaines au sein de l’expérience holographique. Les développeurs n’ont rien à faire pour tirer parti de cette fonctionnalité.

## Étalonnage de votre HoloLens (1re génération)

HoloLens (1re génération) ajuste l’affichage des hologrammes en fonction de votre [écart pupillaire](https://en.wikipedia.org/wiki/Interpupillary_distance). Si l’écart pupillaire n’est pas précis, les hologrammes pourraient paraître instables ou à une distance incorrecte. Vous pouvez améliorer la qualité de vos visuels en étalonnant l’appareil selon votre écart pupillaire.

Lorsque vous configurez votre appareil HoloLens (1re génération), celui-ci vous invite à étalonner vos visuels une fois que Cortana s’est présentée. Nous vous conseillons de réaliser la procédure d’étalonnage au cours de cette phase d’installation. Néanmoins, vous pouvez l’ignorer en attendant que Cortana vous y invite, puis en indiquant «Ignorer».

Pendant le processus d’étalonnage, HoloLens vous demande d’aligner votre doigt avec une série de six cibles par œil. HoloLens utilise ce processus pour définir correctement l’écart pupillaire de vos yeux.

![Écran d’alignement IPD d’un doigt lors de la deuxième étape](./images/ipd-finger-alignment-300px.jpg)

### Démarrer manuellement le processus d’étalonnage

Si vous avez besoin de mettre à jour l’étalonnage ou si un nouvel utilisateur doit l’ajuster, vous pouvez exécuter l’application d’étalonnage manuellement à tout moment. L’application d’étalonnage est installée par défaut. Vous pouvez y accéder à l’aide du menu **Démarrer** ou de l’application Paramètres.

Pour exécuter l’application Étalonnage à l’aide du menu **Démarrer**, procédez comme suit:

1. Utilisez le geste [écarter les doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.
1. Pour afficher toutes les applications, sélectionnez **+**.
1. Sélectionnez **Étalonnage**.

![Accès à l’application d’étalonnage à partir de l’interpréteur de commandes](./images/calibration-shell.png)

![Application d’étalonnage affichée sous la forme d’un cube dynamique après son lancement](./images/calibration-livecube-200px.png)

Pour utiliser l’application Paramètres pour exécuter l’application Étalonnage, procédez comme suit:

1. Utilisez le geste [écartement des doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.
1. Si **Paramètres** n’est pas épinglé sur le menu **Démarrer**, sélectionnez **+** pour afficher toutes les applications.
1. Sélectionnez **Paramètres**.
1. Sélectionnez **Système** > **Utilitaires** > **Ouvrir Étalonnage**.

![Lancement de l’application Ouvrir Étalonnage à partir de l’application Paramètres](./images/calibration-settings-500px.jpg)

## Casques immersifs

Certains casques immersifs permettent de personnaliser le paramètre d’écart pupillaire. Pour modifier l’écart pupillaire de votre casque, ouvrez l’application Paramètres, sélectionnez **Réalité mixte** > **Affichage du casque**, puis déplacez le curseur. Les modifications sont apportées en temps réel dans votre casque. Si vous connaissez votre écart pupillaire, peut-être après une visite chez un opticien, vous pouvez le saisir directement.

Vous pouvez également régler ce paramètre sur votre PC en sélectionnant **Paramètres** > **Réalité mixte** > **Affichage du casque**.

Si votre casque ne prend pas en charge la personnalisation de l’écart pupillaire, ce paramètre est désactivé.
