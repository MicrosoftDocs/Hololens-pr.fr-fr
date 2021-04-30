---
title: Installer des versions localisées de HoloLens
description: Découvrez comment installer les versions localisées de HoloLens (1re génération), y compris les versions en chinois et en japonais.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309047"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Installer des versions localisées de HoloLens (1re génération)

Pour passer à la version chinoise ou japonaise de HoloLens, vous devez utiliser l’outil de récupération d’appareils Windows (WDRT) pour télécharger la version de la langue sur un PC, puis l’installer sur votre HoloLens.

> [!IMPORTANT]
> L’utilisation de WDRT pour installer les versions chinoises ou japonaises de HoloLens supprime les données existantes, telles que les fichiers et les paramètres personnels, de votre HoloLens. 

1. Sur votre PC, téléchargez et installez [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Téléchargez le package correspondant à la langue de votre choix sur votre ordinateur :  [chinois simplifié](https://aka.ms/hololensdownload-ch) ou [japonais](https://aka.ms/hololensdownload-jp).
1. Une fois le téléchargement terminé, sélectionnez **Explorateur de fichiers**  >  **téléchargements**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide du câble micro-USB qu’il a fourni avec. (Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)
1. Une fois que l’outil a détecté automatiquement votre HoloLens, sélectionnez la vignette Microsoft HoloLens.
1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages**   et sélectionnez le fichier d’installation qui se trouve dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier portant l’extension « . FFU ».) 
1. Sélectionnez **installer le logiciel** et suivez les instructions. 
1. Après l’installation de la build, le programme d’installation de HoloLens démarre automatiquement. Placez sur l’appareil et suivez les instructions d’installation. 

Lorsque vous avez terminé l’installation, accédez à **paramètres**  >  **mettre à jour & sécurité**  >  **Windows Insider** et vérifiez que vous êtes configuré pour recevoir les dernières versions préliminaires. Comme les versions préliminaires en anglais, le programme Windows Insider met à jour les versions chinoises et japonaises de HoloLens avec les dernières versions préliminaires.

> [!NOTE]
>  
> - Vous ne pouvez pas utiliser l’application paramètres pour modifier la langue système entre l’anglais, le japonais et le chinois. Le clignotement d’une nouvelle build est la seule méthode prise en charge pour modifier la langue du système de l’appareil.
> - Bien que vous puissiez utiliser le clavier pinyin à l’écran pour entrer du texte en chinois simplifié ou en japonais, l’utilisation d’un clavier matériel Bluetooth pour taper du texte en chinois simplifié ou en japonais n’est pas prise en charge pour l’instant.  Toutefois, sur le chinois ou le japonais HoloLens, vous pouvez continuer à utiliser un clavier Bluetooth pour taper en anglais (pour passer d’un clavier matériel à un type en anglais, appuyez sur la touche ~).
