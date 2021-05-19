---
title: Utiliser le menu Démarrer et maison virtuelle
description: Découvrez comment utiliser le menu démarrer, gérer et accéder aux applications, et parcourir la page d’accueil des réalités mixtes sur les appareils HoloLens.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 26dc73b59f569496d732bcde068b3647b3857c55
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283515"
---
# Utiliser le menu Démarrer et maison virtuelle

De la même manière que l’expérience PC Windows commence par le Bureau, Windows Holographique commence avec la maison virtuelle.  Dans le menu Démarrer, vous pouvez ouvrir et placer les fenêtres d’application, les lanceurs d’applications immersives et le contenu 3D dans la maison virtuelle et leur placement dans votre espace physique sera mémorisé.

## Utiliser le menu Démarrer

Le menu Démarrer sur HoloLens vous permet d’ouvrir des applications, d’afficher des informations d’état importantes et d’accéder à des outils tels que la caméra.

Où que vous soyez dans HoloLens, vous pouvez toujours ouvrir le menu Démarrer grâce au **mouvement associé au menu Démarrer**.  Sur HoloLens (1re génération) le mouvement associé au menu Démarrer est le geste [écarter les doigts paume vers le haut](https://support.microsoft.com/help/12644/hololens-use-gestures). Sur HoloLens 2, le [mouvement associé au menu Démarrer](hololens2-basic-usage.md#start-gesture) consiste à appuyer sur l’icône de démarrage qui apparaît sur votre poignet.  Vous pouvez également ouvrir le menu Démarrer à l’aide de votre voix en disant « Ouvrir le menu Démarrer ».

> [!TIP]
> Lorsque le menu Démarrer est ouvert, utilisez le mouvement associé au menu Démarrer pour le fermer ou regardez le menu Démarrer et dites « Fermer ».

Des indicateurs d’état du Wi-Fi, de la batterie, du volume et une horloge apparaissent en haut du menu Démarrer. Sur HoloLens 2, il existe également un indicateur d’écoute qui indique si l’appareil est compatible avec la reconnaissance vocale et qu’il écoute les commandes vocales. En bas, vous trouverez les boutons **Photo** et **Vidéo** qui vous permettent de prendre des photos et des enregistrements vidéo.  Il existe également un bouton de **connexion** qui vous permet de projeter ce que vous voyez sur un autre appareil à l’aide de Miracast.

### Rechercher des applications dans le menu Démarrer

Le menu Démarrer possède une liste d’**Applications épinglées** et une liste **Toutes les applications** .

- La liste des **Applications épinglées** affiche les applications qui ont été épinglées. Vous pouvez ajouter et supprimer des applications de la liste **Applications épinglées** à l’aide du menu contextuel qui s’affiche lorsque vous **sélectionnez et maintenez appuyé** la vignette d’une application.

- La liste **Toutes les applications** présente toutes les applications installées sur l’appareil.  Pour accéder à la liste, sélectionnez le bouton **Toutes les applications** sur le côté droit du menu **Démarrer**.

Dans les deux listes d’applications, utilisez les boutons **Page précédente** et **Page suivante** sur le côté droit du menu Démarrer pour parcourir toutes les applications de la liste.  Les deux listes d’applications s’ouvrent automatiquement à la dernière page utilisée lors d’une session d’appareil.

> [!TIP]
> Sur HoloLens 2, vous pouvez faire défiler directement les listes d’applications à l’aide de votre index. Il suffit d’appuyer sur la liste avec la pointe de votre doigt et de faire glisser vers le haut ou vers le bas.

### Ouvrir des applications à partir du menu Démarrer

Pour ouvrir une application à partir du menu Démarrer, il vous suffit de **sélectionner** une **vignette d’application**. Vous pouvez également indiquer le nom d’une application pour l’ouvrir.

Lorsque vous ouvrez une application à partir du menu Démarrer, l’une des situations suivantes se produit, selon la façon dont l’application est conçue :

- Une **fenêtre d’application** est placée. L’application est alors chargée dans la fenêtre et vous pouvez l’utiliser comme un écran tactile.
- Un **lanceur d’applications 3D** pour une application immersive est placé. Vous devez ensuite **Sélectionner** le lanceur pour ouvrir l’application immersive.
- Une fenêtre d’application est placée, qui fait office de **lanceur** pour une application immersive. Le lancement de l’application immersive s’effectue automatiquement.

Les fenêtres d’application et les lanceurs d’applications placés dans la maison virtuelle sont conservés jusqu’à ce que vous décidiez de les supprimer.  Ils constituent un raccourci pratique dans l’univers pour utiliser ces fenêtres d’application ou pour lancer des applications immersives sans avoir à les rouvrir à partir du menu Démarrer. 

> [!NOTE]
>Comme sur un téléphone, les ressources système sont gérées automatiquement sur HoloLens.  Par exemple, lorsque vous ouvrez une nouvelle application immersive, toutes les autres applications en cours d’exécution deviennent inactives immédiatement. Il n’est pas nécessaire de supprimer les fenêtres et les lanceurs d’applications dans la maison virtuelle pour libérer des ressources système. 

## Utiliser des applications sur HoloLens

Les applications sur HoloLens peuvent utiliser la vue de fenêtre d’application ou la vue d’application immersive. Avec la vue de fenêtre de l’application, l’application affiche simplement son contenu à l’intérieur d’une fenêtre. Avec la vue immersive, une application vous éloigne de la maison virtuelle, où elle peut ensuite afficher son contenu dans l’environnement physique autour de vous. Les applications peuvent également choisir d’utiliser les deux vues.

### Utiliser les fenêtres d’application

Sur HoloLens (1re génération), les fenêtres d’application sont placées et utilisées dans la maison virtuelle, où vous pouvez les [déplacer, redimensionner et faire pivoter](hololens1-basic-usage.md#move-resize-and-rotate-apps) comme vous le souhaitez. Outre le pointage du regard et le mouvement, vous pouvez également utiliser les fenêtres d’application avec une souris et un clavier Bluetooth connectés.

Sur HoloLens 2, en plus d’utiliser des fenêtres d’application dans la maison virtuelle, vous pouvez également utiliser une fenêtre d’application à la fois dans une application immersive. Vous pouvez également mettre une fenêtre d’application en mode **Me suivre**. Celle-ci restera alors face à vous lorsque vous vous déplacerez. Lorsque vous ouvrez une fenêtre d’application au sein d’une application immersive, celle-ci s’ouvre automatiquement dans le mode **Me suivre** . Vous pouvez [déplacer, redimensionner et faire pivoter](hololens2-basic-usage.md#move-resize-and-rotate-holograms) des fenêtres d’application directement avec vos mains dans la maison virtuelle et au sein d’une application immersive.

> [!NOTE]
>
> - Jusqu’à trois fenêtres d’application peuvent être actives à la fois dans la maison virtuelle. Vous pouvez en ouvrir d’autres, mais seules trois resteront actives.
> - Quand une fenêtre d’application n’est pas active, le contenu affiché s’assombrit en comparaison avec une fenêtre active.  Certaines afficheront simplement l’icône d’application, au lieu de contenu.  Pour activer une fenêtre inactive, il vous suffit de la **sélectionner**.
> - Chaque application ouverte peut avoir une fenêtre active à la fois, à l’exception de Microsoft Edge, qui peut en compter jusqu’à trois.

### Fermer des applications

Pour fermer une application qui utilise une fenêtre d’application, fermez simplement la fenêtre de l’application à l’aide du bouton **Fermer** dans la barre de titre.  Vous pouvez également regarder la fenêtre et dire « Fermer ».

Pour quitter une application qui utilise le mode immersive, utilisez le mouvement associé au menu Démarrer pour afficher le **menu Démarrer**, puis sélectionnez le bouton **Maison virtuelle** .

Si une application immersive est endommagé et que vous avez besoin de la redémarrer, vous pouvez vous assurer qu’elle est complètement arrêtée en fermant son lanceur dans la maison virtuelle, puis en la lançant à partir du menu Démarrer.

## Informations connexes

[Rechercher, installer et désinstaller des applications à partir du Microsoft Store](holographic-store-apps.md)
