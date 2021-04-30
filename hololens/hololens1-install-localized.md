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
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="ec2e2-103">Installer des versions localisées de HoloLens (1re génération)</span><span class="sxs-lookup"><span data-stu-id="ec2e2-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="ec2e2-104">Pour passer à la version chinoise ou japonaise de HoloLens, vous devez utiliser l’outil de récupération d’appareils Windows (WDRT) pour télécharger la version de la langue sur un PC, puis l’installer sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec2e2-105">L’utilisation de WDRT pour installer les versions chinoises ou japonaises de HoloLens supprime les données existantes, telles que les fichiers et les paramètres personnels, de votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="ec2e2-106">Sur votre PC, téléchargez et installez [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="ec2e2-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="ec2e2-107">Téléchargez le package correspondant à la langue de votre choix sur votre ordinateur :  [chinois simplifié](https://aka.ms/hololensdownload-ch) ou [japonais](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="ec2e2-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="ec2e2-108">Une fois le téléchargement terminé, sélectionnez **Explorateur de fichiers**  >  **téléchargements**.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="ec2e2-109">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="ec2e2-110">Connectez votre HoloLens à votre PC à l’aide du câble micro-USB qu’il a fourni avec.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="ec2e2-111">(Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)</span><span class="sxs-lookup"><span data-stu-id="ec2e2-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="ec2e2-112">Une fois que l’outil a détecté automatiquement votre HoloLens, sélectionnez la vignette Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="ec2e2-113">Dans l’écran suivant, sélectionnez **sélection manuelle des packages**   et sélectionnez le fichier d’installation qui se trouve dans le dossier que vous avez décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="ec2e2-114">(Recherchez un fichier portant l’extension « . FFU ».)</span><span class="sxs-lookup"><span data-stu-id="ec2e2-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="ec2e2-115">Sélectionnez **installer le logiciel** et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="ec2e2-116">Après l’installation de la build, le programme d’installation de HoloLens démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="ec2e2-117">Placez sur l’appareil et suivez les instructions d’installation.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="ec2e2-118">Lorsque vous avez terminé l’installation, accédez à **paramètres**  >  **mettre à jour & sécurité**  >  **Windows Insider** et vérifiez que vous êtes configuré pour recevoir les dernières versions préliminaires.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="ec2e2-119">Comme les versions préliminaires en anglais, le programme Windows Insider met à jour les versions chinoises et japonaises de HoloLens avec les dernières versions préliminaires.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="ec2e2-120">Vous ne pouvez pas utiliser l’application paramètres pour modifier la langue système entre l’anglais, le japonais et le chinois.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="ec2e2-121">Le clignotement d’une nouvelle build est la seule méthode prise en charge pour modifier la langue du système de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="ec2e2-122">Bien que vous puissiez utiliser le clavier pinyin à l’écran pour entrer du texte en chinois simplifié ou en japonais, l’utilisation d’un clavier matériel Bluetooth pour taper du texte en chinois simplifié ou en japonais n’est pas prise en charge pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="ec2e2-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="ec2e2-123">Toutefois, sur le chinois ou le japonais HoloLens, vous pouvez continuer à utiliser un clavier Bluetooth pour taper en anglais (pour passer d’un clavier matériel à un type en anglais, appuyez sur la touche ~).</span><span class="sxs-lookup"><span data-stu-id="ec2e2-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
