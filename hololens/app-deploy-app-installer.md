---
title: Comment charger et installer des applications via le programme d’installation de l’application HoloLens 2
description: Télécharger et installer des applications par le biais de l’interface utilisateur
keywords: gestion des applications, application, hololens, programme d’installation de l’application
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027466"
---
# Installer des applications sur HoloLens 2 via le programme d’installation d’application

Les utilisateurs peuvent désormais installer des applications à l’aide de forfaits AppX dès maintenant sans avoir besoin d’activer le mode développeur ou d’utiliser Device Portal. Cette expérience est simple lors de l’installation d’applications sur des appareils locaux ou du partage d’une application avec une autre personne qui ne connaît pas les autres méthodes d’installation d’application sur HoloLens. 

> [!IMPORTANT]
> Pour le moment, cette fonctionnalité est uniquement avalible dans les builds Insider 19041.1377 +. En [savoir plus sur l’inscription aux builds Insider pour Windows](hololens-insider.md).

> [!NOTE]
> La configuration de la solution de votre application doit être **maître** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du Windows Store. En savoir plus sur la [création de packages d’application](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

1.  Vérifiez que votre appareil HoloLens 2 est allumé et que vous êtes connecté.
1.  Sur votre PC, accédez à votre application personnalisée, puis copiez le fichier VotreApplication. appxbundle sur yourdevicename\Internal Storage\Downloads. 
    À la fin de la copie de votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation plus tard.
1.  Sur votre appareil HoloLens 2, ouvrez le **menu Démarrer**, sélectionnez **toutes les applications** , puis lancez l’application **Explorateur de fichiers** .
1.  Accédez au dossier téléchargements. Vous pouvez être amené à vous rendre dans le volet gauche de l’application sélectionnez **ce dernier** d’abord, puis accéder à téléchargements.
1.  Sélectionnez le fichier VotreApplication. appxbundle. 
1.  Le programme d’installation de l’application démarre. Sélectionnez le bouton **installer** pour installer votre application. 

L’application installée s’ouvre automatiquement lors de l’installation. 

![Installation des exemples MRTK via le programme d’installation de l’application](images/hololens-app-installer-picture.jpg)

Si votre application n’a pas réussi à procéder à l’installation, vérifiez les points suivants:
-   Votre application est une build de type maître ou version Release.
-   Vous êtes [connecté à Internet](hololens-network.md).
-   Vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont correctement configurés.  
