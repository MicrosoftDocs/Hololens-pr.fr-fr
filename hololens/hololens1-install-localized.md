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
# <span data-ttu-id="1a288-103">Installer des versions localisées de HoloLens (1regénération)</span><span class="sxs-lookup"><span data-stu-id="1a288-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="1a288-104">Pour basculer vers la version chinoise ou japonaise de HoloLens, vous devez utiliser Windows Device Recovery Tool pour télécharger la version correspondant à la langue de l’ordinateur, puis l’installer sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a288-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a288-105">L’utilisation de Windows Device Recovery Tool pour installer la version chinoise ou japonaise de HoloLens supprime des données existantes, telles que des fichiers personnels et des paramètres, d’HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a288-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="1a288-106">Sur votre PC, téléchargez et installez [Windows Device Recovery Tool](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="1a288-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="1a288-107">Téléchargez le package correspondant à la langue de votre choix pour votre PC: [chinois simplifié](https://aka.ms/hololensdownload-ch) ou [japonais](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="1a288-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="1a288-108">Lorsque le téléchargement est terminé, sélectionnez **Explorateur de fichiers** > **Téléchargements**.</span><span class="sxs-lookup"><span data-stu-id="1a288-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="1a288-109">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="1a288-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="1a288-110">Connectez votre HoloLens à votre PC à l’aide du câble micro-USB fourni.</span><span class="sxs-lookup"><span data-stu-id="1a288-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="1a288-111">Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.</span><span class="sxs-lookup"><span data-stu-id="1a288-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="1a288-112">Lorsque l’outil détecte automatiquement votre HoloLens, sélectionnez la vignette Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a288-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="1a288-113">Dans l’écran suivant, sélectionnez **Sélection manuelle du package** , puis sélectionnez le fichier d’installation qui se trouve dans le dossier que vous avez décompressé au cours de l’étape4.</span><span class="sxs-lookup"><span data-stu-id="1a288-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="1a288-114">(Recherchez un fichier portant l’extension «. FFU».)</span><span class="sxs-lookup"><span data-stu-id="1a288-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="1a288-115">Sélectionnez **Installer le logiciel** , puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="1a288-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="1a288-116">Après l’installation de la build, le programme d’installation HoloLens démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1a288-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="1a288-117">Entrez sur l’appareil et suivez les instructions d’installation.</span><span class="sxs-lookup"><span data-stu-id="1a288-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="1a288-118">Lorsque vous avez terminé la configuration, accédez à **Paramètres** > **Mise à jour et sécurité** > **Programme Windows Insider** et vérifiez que vous êtes configuré pour recevoir les dernières builds d’aperçu.</span><span class="sxs-lookup"><span data-stu-id="1a288-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="1a288-119">À l’instar des versions d’évaluation en anglais, le programme Windows Insider met à jour les versions chinoise et japonaise de HoloLens aux dernières versions d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="1a288-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="1a288-120">Vous ne pouvez pas utiliser l’application Paramètres pour modifier la langue du système en anglais, japonais et chinois.</span><span class="sxs-lookup"><span data-stu-id="1a288-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="1a288-121">Flasher une nouvelle version est le seul moyen de modifier la langue du système de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="1a288-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="1a288-122">Vous pouvez utiliser le clavier Pinyin visuel pour entrer du texte en chinois ou en japonais, l’utilisation d’un clavier matériel Bluetooth pour taper du texte en chinois simplifié ou japonais n’est pas pris en charge actuellement.</span><span class="sxs-lookup"><span data-stu-id="1a288-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="1a288-123">Toutefois, sur les versions chinoise ou japonaises d’HoloLens, vous pouvez continuer à utiliser un clavier Bluetooth pour taper en anglais (pour activer ou désactiver le clavier matériel anglais, appuyez sur la touche ~).</span><span class="sxs-lookup"><span data-stu-id="1a288-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
