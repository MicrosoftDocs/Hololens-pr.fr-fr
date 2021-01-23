---
title: Installer des versions localisées de HoloLens
description: Découvrez comment installer les versions localisées d’HoloLens (1ère génération), y compris les versions chinoise et japonaise.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: af79e42477a3a317dde03a795c442fa31241600d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282975"
---
# Installer des versions localisées de HoloLens (1regénération)

Pour basculer vers la version chinoise ou japonaise de HoloLens, vous devez utiliser Windows Device Recovery Tool pour télécharger la version correspondant à la langue de l’ordinateur, puis l’installer sur HoloLens.

> [!IMPORTANT]
> L’utilisation de Windows Device Recovery Tool pour installer la version chinoise ou japonaise de HoloLens supprime des données existantes, telles que des fichiers personnels et des paramètres, d’HoloLens. 

1. Sur votre PC, téléchargez et installez [Windows Device Recovery Tool](https://support.microsoft.com/help/12379).
1. Téléchargez le package correspondant à la langue de votre choix pour votre PC: [chinois simplifié](https://aka.ms/hololensdownload-ch) ou [japonais](https://aka.ms/hololensdownload-jp).
1. Lorsque le téléchargement est terminé, sélectionnez **Explorateur de fichiers** > **Téléchargements**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide du câble micro-USB fourni. Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.
1. Lorsque l’outil détecte automatiquement votre HoloLens, sélectionnez la vignette Microsoft HoloLens.
1. Dans l’écran suivant, sélectionnez **Sélection manuelle du package** , puis sélectionnez le fichier d’installation qui se trouve dans le dossier que vous avez décompressé au cours de l’étape4. (Recherchez un fichier portant l’extension «. FFU».) 
1. Sélectionnez **Installer le logiciel** , puis suivez les instructions. 
1. Après l’installation de la build, le programme d’installation HoloLens démarre automatiquement. Entrez sur l’appareil et suivez les instructions d’installation. 

Lorsque vous avez terminé la configuration, accédez à **Paramètres** > **Mise à jour et sécurité** > **Programme Windows Insider** et vérifiez que vous êtes configuré pour recevoir les dernières builds d’aperçu. À l’instar des versions d’évaluation en anglais, le programme Windows Insider met à jour les versions chinoise et japonaise de HoloLens aux dernières versions d’évaluation.

> [!NOTE]
>  
> - Vous ne pouvez pas utiliser l’application Paramètres pour modifier la langue du système en anglais, japonais et chinois. Flasher une nouvelle version est le seul moyen de modifier la langue du système de l’appareil.
> - Vous pouvez utiliser le clavier Pinyin visuel pour entrer du texte en chinois ou en japonais, l’utilisation d’un clavier matériel Bluetooth pour taper du texte en chinois simplifié ou japonais n’est pas pris en charge actuellement.  Toutefois, sur les versions chinoise ou japonaises d’HoloLens, vous pouvez continuer à utiliser un clavier Bluetooth pour taper en anglais (pour activer ou désactiver le clavier matériel anglais, appuyez sur la touche ~).
