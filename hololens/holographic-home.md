---
title: Utiliser le menu Démarrer et l’accueil réalité mixte
description: Apprenez à utiliser le menu Démarrer, à accéder aux applications et à les gérer, et à parcourir l'accueil réalité mixte sur les appareils HoloLens.
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
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427683"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Utiliser le menu Démarrer et l’accueil réalité mixte

Tout comme l'expérience PC Windows commence avec le bureau, Windows Holographic commence avec l'accueil réalité mixte.  À l'aide du menu Démarrer, vous pouvez ouvrir et placer des fenêtres d'application, des lanceurs d'application immersive et du contenu 3D dans l'accueil réalité mixte, et leur placement dans votre espace physique sera mémorisé.

## <a name="use-the-start-menu"></a>Utiliser le menu Démarrer

Le menu Démarrer sur HoloLens vous permet d’ouvrir des applications, de voir des informations d’état importantes et d’accéder à des outils comme la caméra.

Où que vous soyez dans HoloLens, vous pouvez toujours utiliser le **mouvement associé au menu Démarrer** pour ouvrir celui-ci.  Sur l'HoloLens (1ère génération), le mouvement associé au menu Démarrer est le suivant : [écarter les doigts paume vers le haut](https://support.microsoft.com/help/12644/hololens-use-gestures). Sur l'HoloLens 2, le [mouvement associé au menu Démarrer](hololens2-basic-usage.md#start-gesture) consiste à appuyer sur l'icône de démarrage qui apparaît sur votre poignet.  Vous pouvez également ouvrir le menu Démarrer en prononçant les mots « Menu Démarrer ».

> [!TIP]
> Lorsque le menu Démarrer est ouvert, utilisez le mouvement associé au menu Démarrer pour le fermer, ou regardez le menu Démarrer et dites « Fermer ».

Une horloge et des indicateurs d'état du Wi-Fi, de la batterie et du volume apparaissent en haut du menu Démarrer. Sur l'HoloLens 2, un indicateur d'écoute indique également si l'appareil est compatible avec la reconnaissance vocale et écoute les commandes vocales. En bas, vous trouverez les boutons **Photo** et **Vidéo** qui vous permettent de prendre des photos et d'effectuer des enregistrements vidéo.  Un bouton **Connecter** vous permet également de projeter ce que vous voyez sur un autre appareil via Miracast.

### <a name="find-apps-on-start-menu"></a>Rechercher des applications dans le menu Démarrer

Le menu Démarrer comporte une liste **Applications épinglées** et une liste **Toutes les applications**.

- La liste **Applications épinglées** affiche les applications qui ont été épinglées. Vous pouvez ajouter et supprimer des applications de la liste **Applications épinglées** à l'aide du menu contextuel qui apparaît lorsque vous **sélectionnez et appuyez longuement** sur une vignette d'application.

- La liste **Toutes les applications** présente toutes les applications installées sur l'appareil.  Sélectionnez le bouton **Toutes les applications** sur le côté droit du menu **Démarrer** pour accéder à la liste.

Dans les deux listes d'applications, utilisez les boutons **Page précédente** et **Page suivante** situés sur le côté droit du menu Démarrer pour parcourir toutes les applications de la liste.  Les deux listes d'applications s'ouvrent automatiquement sur la dernière page utilisée lors d'une session de l'appareil.

> [!TIP]
> Sur l'HoloLens 2, vous pouvez faire défiler les listes d'applications à l'aide de votre index. Il vous suffit de toucher la liste du bout du doigt et de la faire glisser vers le haut ou vers le bas.

### <a name="open-apps-from-start-menu"></a>Ouvrir des applications à partir du menu Démarrer

Pour ouvrir une application à partir du menu Démarrer, il vous suffit de **sélectionner** la **vignette d'application** correspondante. Vous pouvez aussi prononcer le nom de l'application pour l'ouvrir.

Lorsque vous ouvrez une application à partir du menu Démarrer, trois scénarios sont possibles, selon la façon dont l'application est conçue :

- Une **fenêtre d'application** est placée. L'application est alors chargée dans la fenêtre et vous pouvez l'utiliser comme un écran tactile.
- Un **lanceur d'application en 3D** est placé pour une application immersive. Vous devez ensuite **sélectionner** le lanceur pour ouvrir l'application immersive.
- Une fenêtre d'application est placée. Celle-ci fait office de **lanceur** pour une application immersive. Le lancement de l'application immersive s'effectue automatiquement.

Les fenêtres d'application et les lanceurs d'application placés dans l'accueil réalité mixte y restent jusqu'à ce que vous décidiez de les supprimer.  Ils constituent un raccourci pratique pour utiliser ces fenêtres d'application ou pour lancer des applications immersives sans avoir à les rouvrir à partir du menu Démarrer. 

> [!NOTE]
>Comme sur un téléphone, les ressources système d'un HoloLens sont gérées automatiquement.  Par exemple, lorsque vous ouvrez une nouvelle application immersive, toutes les autres applications en cours d'exécution deviennent immédiatement inactives. Il n'est pas nécessaire de supprimer les fenêtres et les lanceurs d'application dans l'accueil réalité mixte pour libérer des ressources système. 

## <a name="using-apps-on-hololens"></a>Utiliser des applications sur un HoloLens

Sur un HoloLens, les applications peuvent utiliser la vue fenêtre d'application ou la vue immersive. Avec la vue fenêtre d'application, le contenu de l'application apparaît dans une fenêtre. Avec la vue immersive, une application vous éloigne de l'accueil réalité mixte pour afficher son contenu dans l'environnement physique qui vous entoure. Les applications peuvent également choisir d'utiliser les deux vues.

### <a name="use-app-windows"></a>Utiliser les fenêtres d'application

Sur l'HoloLens (1ère génération), les fenêtres d'application sont placées et utilisées dans l'accueil réalité mixte, où vous pouvez [les déplacer, les redimensionner et les faire pivoter](hololens1-basic-usage.md#move-resize-and-rotate-apps) comme vous le souhaitez. En plus du regard et du mouvement, vous pouvez également utiliser les fenêtres d'application avec une souris et un clavier Bluetooth connectés.

Sur l'HoloLens 2, vous pouvez utiliser une fenêtre d'application dans l'accueil réalité mixte ainsi qu'à l'intérieur d'une application immersive. Vous pouvez également mettre une fenêtre d'application en mode **Me suivre**. Celle-ci restera alors face à vous lorsque vous vous déplacerez. Lorsque vous ouvrez une fenêtre d'application au sein d'une application immersive, celle-ci s'ouvre automatiquement en mode **Me suivre**. Vous pouvez [déplacer, redimensionner et faire pivoter](hololens2-basic-usage.md#move-resize-and-rotate-holograms) des fenêtres d'application à l'aide de vos mains dans l'accueil réalité mixte et au sein d'une application immersive.

> [!NOTE]
>
> - Trois fenêtres d'application peuvent être simultanément actives dans l'accueil réalité mixte. Vous pouvez en ouvrir d'autres, mais seules trois d'entre elles resteront actives.
> - Lorsqu'une fenêtre d'application n'est pas active, son contenu est plus sombre que celui d'une fenêtre active.  Certaines affichent simplement l'icône de l'application à la place du contenu.  Pour activer une fenêtre inactive, il vous suffit de la **sélectionner**.
> - Chaque application ouverte ne peut disposer que d'une fenêtre active à la fois, à l'exception de Microsoft Edge, qui peut en avoir trois.

### <a name="close-apps"></a>Fermer les applications

Pour fermer une application qui utilise une fenêtre d'application, fermez cette dernière à l'aide du bouton **Fermer** de la barre de titre.  Vous pouvez également regarder la fenêtre et dire « Fermer ».

Pour quitter une application qui utilise la vue immersive, utilisez le mouvement associé **au menu Démarrer** pour afficher celui-ci, puis sélectionnez le bouton **Accueil réalité mixte**.

Si une application immersive est défectueuse et que vous devez la redémarrer, commencez par vous assurer qu'elle est complètement fermée en fermant son lanceur dans l'accueil réalité mixte, puis en la lançant à partir du menu Démarrer.

### <a name="default-app-picker"></a>Sélecteur d'application par défaut

Avec [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), lorsque vous activez un lien hypertexte ou ouvrez un type de fichier pris en charge par plusieurs applications installées, une nouvelle fenêtre s'ouvre pour vous inviter à sélectionner l'application à utiliser pour gérer le type de fichier ou de lien. Dans cette fenêtre, vous pouvez également choisir d'utiliser l'application sélectionnée « Une seule fois » ou « Toujours » afin de gérer le type de fichier ou de lien.

![Fenêtre du sélecteur d’application.](images/default-app-picker.png)

Si vous choisissez « Toujours » et que vous souhaitez ultérieurement utiliser une autre application pour gérer un type de fichier ou de lien particulier, vous pouvez réinitialiser les valeurs par défaut enregistrées en sélectionnant **Paramètres > Applications**. Faites défiler de la page vers le bas et sélectionnez le bouton **Effacer** sous « Applications par défaut pour les types de fichiers » et/ou « Applications par défaut pour les types de liens ». Contrairement au paramètre similaire des ordinateurs de bureau, vous ne pouvez pas réinitialiser les valeurs par défaut des types de fichiers individuels.

### <a name="per-app-volume-control"></a>Contrôle du volume par application

Avec [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), les utilisateurs peuvent régler manuellement le volume de chaque application. Cela permet aux utilisateurs de mieux se concentrer sur les applications dont ils ont besoin, ou de mieux entendre lorsqu'ils utilisent plusieurs applications. Par exemple, ils peuvent être amenés à baisser le volume d'une application afin d'appeler quelqu'un pour lui fournir une assistance à distance dans une autre application.

Pour régler le volume d'une application individuelle, accédez à **Paramètres** -> **Système** -> **Son**, et sous Options sonores avancées, sélectionnez **Volume de l'application et préférences de l'appareil**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Informations connexes

[Rechercher, installer et désinstaller des applications à partir du Microsoft Store](holographic-store-apps.md)
