---
title: Améliorer la qualité visuelle et le confort
description: Apprenez à étalonner votre écart pupillaire pour améliorer la qualité de vos visuels sur les appareils HoloLens.
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
keywords: étalonnage, confort, visuels, qualité, écart pupillaire, HoloLens, Windows Mixed Reality, casques VR
ms.openlocfilehash: cdeef216cbf6d1fb165737ae194071c60b31146a
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833554"
---
# <a name="improve-visual-quality-and-comfort"></a>Améliorer la qualité visuelle et le confort

Les appareils HoloLens 2 et HoloLens (1ère génération) fonctionnent mieux lorsqu'ils sont étalonnés en fonction de vos yeux.

Ces appareils doivent tous deux être étalonnés pour offrir la meilleure qualité d'affichage des hologrammes, mais ils utilisent des technologies et techniques d'étalonnage différentes.  Accédez à [Étalonnage de l'HoloLens 2](#calibrating-your-hololens-2) ou [Étalonnage de l'HoloLens (1ère génération)](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>Étalonner votre HoloLens 2

L'HoloLens 2 utilise la technologie de suivi oculaire pour améliorer votre expérience de vision et d'interaction avec l'environnement virtuel. L'étalonnage de l'HoloLens 2 permet un suivi précis de vos yeux (et de ceux de tout autre utilisateur de l'appareil). Il contribue également au confort de l'utilisateur, à l'alignement des hologrammes et au suivi de la main. Après l'étalonnage, les hologrammes s'affichent correctement, même si la visière bouge sur votre tête.

L'utilisateur est invité à étalonner l'HoloLens 2 dans les cas suivants :

- L'utilisateur se sert de l'appareil pour la première fois.
- L'utilisateur a précédemment refusé le processus d'étalonnage.
- Le processus d'étalonnage n'a pas abouti la dernière fois que l'utilisateur s'est servi de l'appareil.
- L'utilisateur a supprimé ses profils d'étalonnage.
- L’utilisateur a éteint puis rallumé l’appareil, et l’une des circonstances ci-dessus s’applique. 

![Invite d'étalonnage pour l'adaptation aux yeux.](./images/07-et-adjust-for-your-eyes.png)

Au cours de ce processus, vous examinerez un ensemble de cibles (gemmes). Pendant l'étalonnage, vous pouvez cligner des yeux, mais essayez de rester concentré sur les gemmes plutôt que sur les autres objets présents dans la pièce.  En vous concentrant sur les gemmes, vous permettrez à l'HoloLens de mesurer la position de vos yeux pour l'affichage de votre monde holographique.

![Invite d'étalonnage indiquant à l'utilisateur de garder la tête immobile et de suivre les points avec les yeux.](./images/07-et-hold-head-still.png)

![Invite d'étalonnage avec exemple de gemme.](./images/08-et-gems.png)

![Réglage de l'invite d'étalonnage.](./images/09-et-adjusting.png)

Si l'étalonnage a abouti, un écran s'affiche pour vous en informer.  Sinon, découvrez-en plus sur le [diagnostic des échecs d'étalonnage](hololens2-display.md#troubleshooting).

![Réussite de l'invite d'étalonnage.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Étalonnage lors du partage d'un appareil ou d'une session

Plusieurs utilisateurs peuvent partager un appareil HoloLens 2, sans que chacun ait besoin de le reconfigurer. Lorsqu'un nouvel utilisateur met l'appareil sur sa tête pour la première fois, l'HoloLens 2 l'invite automatiquement à étalonner les visuels. Lorsqu'un utilisateur qui a déjà étalonné ses visuels met l'appareil sur sa tête, l'affichage s'ajuste de manière transparente pour assurer la qualité et le confort de l'expérience visuelle.  

### <a name="manually-starting-the-calibration-process"></a>Démarrage manuel du processus d'étalonnage

1. Utilisez le geste de démarrage pour ouvrir le [**menu Démarrer**](hololens2-basic-usage.md#start-gesture).
1. Si l'application Paramètres n'est pas épinglée au menu **Démarrer**, sélectionnez **Toutes les applications**.
1. Sélectionnez **Paramètres**, puis **Système** > **Étalonnage** > **Étalonnage des yeux** > **Exécuter l'étalonnage des yeux**.

   ![Application Paramètres, avec l’option d’étalonnage oculaire.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Prise en charge de la fonctionnalité Position automatique des yeux

Dans l'HoloLens 2, la position des yeux permet un positionnement précis de l'hologramme, une expérience visuelle confortable et une meilleure qualité d'affichage. La position des yeux est calculée en interne dans le cadre du calcul du suivi oculaire. Toutefois, cela oblige chaque utilisateur à procéder à un étalonnage du suivi oculaire, même lorsque le regard n'est pas requis dans le cadre de l'expérience.

La fonctionnalité **Position automatique des yeux** permet, dans ces scénarios, de calculer la position des yeux de l'utilisateur sans interaction. La fonctionnalité Position automatique des yeux est automatiquement exécutée en arrière-plan dès que l'utilisateur allume l'appareil. Si l'utilisateur n'a pas encore effectué de suivi oculaire, la fonctionnalité Position automatique des yeux commence à fournir la position des yeux de l'utilisateur au système d'affichage après 20 à 30 secondes de traitement. Les données de l'utilisateur ne sont pas conservées sur l'appareil, et ce processus se répète si l'utilisateur éteint puis rallume l'appareil, ou si l'appareil redémarre ou sort du mode veille.

Lorsqu'un utilisateur non étalonné enfile l'appareil, la fonctionnalité Position automatique des yeux entraîne quelques modifications du comportement du système. Dans ce contexte, le terme « utilisateur non étalonné » fait référence à une personne qui n'a pas encore suivi le processus d'étalonnage du suivi oculaire sur l'appareil.

| Application active | Comportement antérieur | Comportement de Windows Holographic, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Application non compatible avec le regard ou shell holographique |La boîte de dialogue d'invite d'étalonnage du suivi oculaire s'affiche. | Aucune invite n'est affichée. |
| Application compatible avec le regard | La boîte de dialogue d'invite d'étalonnage du suivi oculaire s'affiche. | L'invite d'étalonnage du suivi oculaire s'affiche uniquement lorsque l'application accède à un flux de regard. |

Si l'utilisateur passe d'une application non compatible avec le regard à une application qui accède aux données du regard, l'invite d'étalonnage s'affiche. 

Tous les autres comportements du système seront semblables à celui qui s'applique lorsque l'utilisateur actuel ne dispose d'aucun étalonnage de suivi oculaire actif. Par exemple, le mouvement d'une main associé au menu Démarrer ne sera pas activé. Les fonctionnalités Out-Of-Box-Experience de la configuration initiale ne subissent aucune modification.

Pour les expériences qui nécessitent des données sur le regard ou un positionnement précis des hologrammes, nous recommandons aux utilisateurs non étalonnés de suivre le processus d'étalonnage du suivi oculaire. Vous pouvez y accéder depuis l'invite d'étalonnage du suivi oculaire ou en lançant l'application Paramètres à partir du menu Démarrer, puis en sélectionnant **Système > Étalonnage > Étalonnage des yeux > Exécuter l'étalonnage des yeux**.

#### <a name="deferred-calibration-prompt"></a>Invite d'étalonnage différé

Avec la fonctionnalité Position automatique des yeux, la boîte de dialogue de l'invite d'étalonnage du suivi oculaire est différée jusqu'à ce qu'une application demande des données sur le regard. Ainsi, aucune invite n'est présentée à l'utilisateur lorsque l'application active ne requiert pas de données sur le regard. Si l'application requiert des données sur le regard et que l'utilisateur actuel n'a pas suivi le processus d'étalonnage, une invite d'étalonnage s'affiche sur son système. Ce comportement peut être utilisé pour afficher une invite d’étalonnage du suivi oculaire à un moment approprié pour l’expérience. Cette méthode est recommandée pour les raisons suivantes :

1.  La boîte de dialogue de l'invite d'étalonnage du suivi oculaire explique à l'utilisateur pourquoi le suivi oculaire est nécessaire.
2.  Offre à l'utilisateur la possibilité de décliner l'étalonnage de ses yeux.

Si l’utilisateur choisit de lancer l’étalonnage du suivi oculaire, le focus doit revenir à l’application d’origine une fois l’étalonnage terminé. 

### <a name="calibration-data-and-security"></a>Données d'étalonnage et sécurité

Les informations d'étalonnage sont stockées localement sur l'appareil et ne sont associées à aucune information de compte. Aucun enregistrement n'indique qui a utilisé l'appareil sans étalonnage. Les nouveaux utilisateurs doivent donc, sur invite, étalonner les visuels à la première utilisation de l’appareil, tout comme les utilisateurs ayant précédemment choisi de ne pas réaliser l’étalonnage ou ayant rencontré un échec d’étalonnage.

L'appareil peut stocker localement jusqu'à 50 profils d'étalonnage. Une fois ce nombre atteint, l'appareil supprime automatiquement le profil inutilisé le plus ancien.

Les informations d'étalonnage peuvent toujours être supprimées de l'appareil sous **Paramètres** > **Confidentialité** > **Suivi oculaire**.  

### <a name="disable-calibration"></a>Désactiver l'étalonnage

#### <a name="eye-calibration-behavior-on-hololens-2-builds-20h2-and-newer"></a>Comportement de l’étalonnage oculaire sur HoloLens 2 build 20H2 ou ultérieure

Depuis le lancement de la [prise en charge de la position automatique des yeux](hololens-release-notes.md#auto-eye-position-support) dans Windows Holographique version 20H2, vous n’avez pas besoin de désactiver l’étalonnage. L’invite d’étalonnage n’apparaît automatiquement que si vous utilisez une application avec suivi oculaire.

#### <a name="disabling-eye-calibration-on-hololens-2-older-builds"></a>Désactivation de l’étalonnage oculaire sur les builds HoloLens 2 plus anciennes

Vous pouvez actionner un bouton Paramètres sur le casque pour désactiver l’étalonnage, mais l’état de ce bouton peut être difficile à évaluer. Il a été supprimé et remplacé par la [prise en charge de la position automatique des yeux](hololens-release-notes.md#auto-eye-position-support), qui diffère l’étalonnage tout en assurant la correction des couleurs et le positionnement des hologrammes.

#### <a name="disabling-eye-calibration-on-hololens-1st-gen"></a>Désactivation de l’étalonnage oculaire sur HoloLens (1re génération)

Pour [l’étalonnage d’HoloLens (1re génération)](#calibrating-your-hololens-1st-gen), vous pouvez désactiver l’invite d’étalonnage oculaire en effectuant les étapes suivantes :

1. Sélectionnez **Paramètres** > **Système** > **Étalonnage**.
1. Désactivez **Lorsqu'une nouvelle personne utilise cet HoloLens, lui demander automatiquement d'exécuter l'étalonnage des yeux**.

   > [!IMPORTANT]
   > Ce paramètre peut nuire à la qualité et au confort d'affichage des hologrammes.  Lorsque vous le désactivez, les fonctionnalités qui dépendent du suivi oculaire (par exemple, le défilement du texte) ne fonctionnent plus dans les applications immersives.

### <a name="hololens-2-eye-tracking-technology"></a>Technologie de suivi oculaire de l'HoloLens 2

L'appareil utilise sa technologie de suivi oculaire pour améliorer la qualité d'affichage et veiller à ce que tous les hologrammes soient positionnés de manière précise et confortable pour un affichage en 3D. Comme il utilise les yeux comme points de repère, l'appareil peut s'adapter à chaque utilisateur et ajuster ses visuels si le casque bouge légèrement en cours d'utilisation.  Tous les ajustements se font à la volée, sans qu'il soit nécessaire de procéder à un réglage manuel.
> [!NOTE]
> La configuration de l'écart pupillaire ne s'applique pas à l'Hololens 2, car la position des yeux est calculée par le système.

Les applications HoloLens utilisent le suivi oculaire pour connaître la direction de votre regard en temps réel. Il s'agit de la principale fonctionnalité que les développeurs peuvent utiliser pour tirer parti d'un niveau inédit de contexte, de compréhension humaine et d'interactions au sein de l'expérience holographique. Les développeurs n'ont rien à faire pour utiliser cette fonctionnalité.

## <a name="calibrating-your-hololens-1st-gen"></a>Étalonner votre HoloLens (1ère génération)

L'HoloLens (1ère génération) ajuste l'affichage des hologrammes en fonction de votre [écart pupillaire](https://en.wikipedia.org/wiki/Interpupillary_distance). Si l'écart pupillaire n'est pas précis, les hologrammes peuvent être instables ou apparaître à une distance incorrecte. Vous pouvez améliorer la qualité de vos visuels en étalonnant l'appareil en fonction de votre écart pupillaire.

Lorsque vous configurez votre appareil HoloLens (1ère génération), vous êtes invité à étalonner vos visuels suite à la présentation de Cortana. Nous vous recommandons de procéder à l'étalonnage au cours de cette phase de configuration. Néanmoins, vous pouvez l'ignorer en attendant que Cortana vous y invite, puis en indiquant « Ignorer ».

Pendant le processus d'étalonnage, l'HoloLens vous demande d'aligner votre doigt sur une série de six cibles par œil. L'HoloLens utilise ce processus pour définir l'écart pupillaire de vos yeux.

![Écran d’alignement du doigt pour définir l’écart pupillaire lors de la deuxième étape.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Démarrer manuellement le processus d'étalonnage

Si vous devez mettre à jour l'étalonnage ou si un nouvel utilisateur doit l'ajuster, vous pouvez à tout moment lancer manuellement l'application Étalonnage. L'application Étalonnage est installée par défaut. Vous pouvez y accéder par le biais du menu **Démarrer** ou de l'application Paramètres.

Pour exécuter l'application Étalonnage à l'aide du menu **Démarrer**, procédez comme suit :

1. Utilisez l'[écartement des doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.
1. Pour afficher toutes les applications, sélectionnez **+** .
1. Sélectionnez **Étalonnage**.

   ![Accès à l’application Étalonnage à partir du shell.](./images/calibration-shell.png)

   ![Application Étalonnage affichée sous la forme d’un cube dynamique après son lancement.](./images/calibration-livecube-200px.png)

Pour exécuter l'application Étalonnage à l'aide de l'application Paramètres, procédez comme suit :

1. Utilisez l'[écartement des doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.
1. Si l'application **Paramètres** n'est pas épinglée au menu **Démarrer**, sélectionnez **+** pour afficher toutes les applications.
1. Sélectionnez **Paramètres**.
1. Sélectionnez **Système** > **Utilitaires** > **Ouvrir l'étalonnage**.

   ![Lancement de l’application Étalonnage à partir de l’application Paramètres.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Casques immersifs

Certains casques immersifs permettent de personnaliser le paramètre d'écart pupillaire. Pour modifier l'écart pupillaire sur votre casque, ouvrez l'application Paramètres et sélectionnez **Réalité mixte** > **Affichage du casque**, puis déplacez le curseur. Les modifications sont apportées en temps réel dans votre casque. Si vous connaissez votre écart pupillaire, peut-être à la suite d'une visite chez un opticien, vous pouvez l'entrer directement.

Vous pouvez également régler ce paramètre sur votre PC en sélectionnant **Paramètres** > **Réalité mixte** > **Affichage du casque**.

Si votre casque ne prend pas en charge la personnalisation de l'écart pupillaire, ce paramètre est désactivé.
