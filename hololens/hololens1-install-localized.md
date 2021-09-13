---
title: Installer des versions localisées de HoloLens
description: découvrez comment installer les versions localisées de HoloLens (1re génération), y compris les versions en chinois et en japonais.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032800"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>installer des versions localisées de HoloLens (1re génération)

pour passer à la version chinoise ou japonaise de HoloLens, vous devez utiliser l’outil Windows Device Recovery Tool (WDRT) pour télécharger la version de la langue sur un PC, puis l’installer sur votre HoloLens.

> [!IMPORTANT]
> l’utilisation de WDRT pour installer les versions chinoises ou japonaises de HoloLens supprime les données existantes, telles que les fichiers et les paramètres personnels, de votre HoloLens. 

1. sur votre PC, téléchargez et installez [l’outil Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Téléchargez le package correspondant à la langue de votre choix sur votre ordinateur :  [chinois simplifié](https://aka.ms/hololensdownload-ch) ou [japonais](https://aka.ms/hololensdownload-jp).
1. Une fois le téléchargement terminé, sélectionnez **Explorateur de fichiers**  >  **téléchargements**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.
1. Connecter votre HoloLens sur votre ordinateur à l’aide du câble micro-USB livré avec. (même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)
1. une fois que l’outil a détecté automatiquement votre HoloLens, sélectionnez la vignette Microsoft HoloLens.
1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages**   et sélectionnez le fichier d’installation qui se trouve dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier portant l’extension « . FFU ».) 
1. Sélectionnez **installer le logiciel** et suivez les instructions. 
1. après l’installation de la build, HoloLens installation démarre automatiquement. Placez sur l’appareil et suivez les instructions d’installation. 

lorsque vous avez terminé l’installation, accédez à **Paramètres**  >  **mettre à jour & Security**  >  **Windows programme insider** et vérifiez que vous êtes configuré pour recevoir les dernières versions préliminaires. à l’instar des builds en version préliminaire anglaise, le programme Windows insider conserve les versions chinoises et japonaises de HoloLens à jour avec les dernières versions préliminaires.

> [!NOTE]
>  
> - vous ne pouvez pas utiliser l’application Paramètres pour modifier la langue du système entre l’anglais, le japonais et le chinois. Le clignotement d’une nouvelle build est la seule méthode prise en charge pour modifier la langue du système de l’appareil.
> - bien que vous puissiez utiliser le clavier Pinyin à l’écran pour entrer du texte en chinois simplifié ou en japonais, l’utilisation d’un clavier Bluetooth pour taper du texte en chinois simplifié ou en japonais n’est pas prise en charge pour l’instant.  toutefois, sur le chinois ou le japonais HoloLens, vous pouvez continuer à utiliser un clavier Bluetooth pour taper en anglais (pour basculer un clavier matériel vers le type en anglais, appuyez sur la touche ~).
