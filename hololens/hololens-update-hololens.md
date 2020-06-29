---
title: Mettre à jour HoloLens
description: Consultez le numéro de build, la mise à jour et la restauration des mises à jour de HoloLens.
keywords: procédures, mise à jour, restauration, HoloLens, vérification de la build, numéro de build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828055"
---
# <span data-ttu-id="940bf-104">Mettre à jour HoloLens</span><span class="sxs-lookup"><span data-stu-id="940bf-104">Update HoloLens</span></span>

<span data-ttu-id="940bf-105">HoloLens utilise Windows Update comme d’autres appareils Windows 10.</span><span class="sxs-lookup"><span data-stu-id="940bf-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="940bf-106">Votre HoloLens télécharge et installe automatiquement les mises à jour du système dès qu’il est connecté et qu’il est connecté à Internet, même en mode veille.</span><span class="sxs-lookup"><span data-stu-id="940bf-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="940bf-107">Cet article vous guide à travers les outils HoloLens pour:</span><span class="sxs-lookup"><span data-stu-id="940bf-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="940bf-108">affichage de votre version actuelle du système d’exploitation (numéro de Build)</span><span class="sxs-lookup"><span data-stu-id="940bf-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="940bf-109">vérification des mises à jour</span><span class="sxs-lookup"><span data-stu-id="940bf-109">checking for updates</span></span>
- <span data-ttu-id="940bf-110">mise à jour manuelle HoloLens</span><span class="sxs-lookup"><span data-stu-id="940bf-110">manually updating HoloLens</span></span>
- <span data-ttu-id="940bf-111">revenir à une ancienne mise à jour</span><span class="sxs-lookup"><span data-stu-id="940bf-111">rolling back to an older update</span></span>

## <span data-ttu-id="940bf-112">Vérifier la version de votre système d’exploitation (numéro de Build)</span><span class="sxs-lookup"><span data-stu-id="940bf-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="940bf-113">Vous pouvez vérifier le numéro de version du système (numéro de Build) en ouvrant l’application paramètres et en sélectionnant **système**  >  **à propos**de.</span><span class="sxs-lookup"><span data-stu-id="940bf-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="940bf-114">Rechercher les mises à jour et les mises à jour manuelles</span><span class="sxs-lookup"><span data-stu-id="940bf-114">Check for updates and manually update</span></span>

<span data-ttu-id="940bf-115">Vous pouvez à tout moment Rechercher les mises à jour dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="940bf-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="940bf-116">Pour afficher les mises à jour disponibles et rechercher les nouvelles mises à jour:</span><span class="sxs-lookup"><span data-stu-id="940bf-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="940bf-117">Ouvrez l’application **paramètres** .</span><span class="sxs-lookup"><span data-stu-id="940bf-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="940bf-118">Accédez à **mettre à jour & sécurité**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="940bf-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="940bf-119">Sélectionnez **Rechercher les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="940bf-119">Select **Check for updates**.</span></span>

<span data-ttu-id="940bf-120">Si une mise à jour est disponible, elle va commencer à télécharger la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="940bf-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="940bf-121">Une fois le téléchargement terminé, sélectionnez le bouton **redémarrer maintenant pour lancer** l’installation.</span><span class="sxs-lookup"><span data-stu-id="940bf-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="940bf-122">Si votre appareil est inférieur à 40% et qu’il n’est pas branché, le redémarrage ne démarrera pas l’installation de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="940bf-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="940bf-123">Lors de l’installation de la mise à jour, le HoloLens affiche les engrenages tournants et un indicateur de progression.</span><span class="sxs-lookup"><span data-stu-id="940bf-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="940bf-124">Ne désactivez pas votre HoloLens pendant ce temps.</span><span class="sxs-lookup"><span data-stu-id="940bf-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="940bf-125">Elle redémarrera automatiquement une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="940bf-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="940bf-126">HoloLens applique une mise à jour à la fois.</span><span class="sxs-lookup"><span data-stu-id="940bf-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="940bf-127">Si votre HoloLens est supérieur ou égal à 1, vous devrez peut-être exécuter plusieurs fois le processus de mise à jour pour le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="940bf-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="940bf-128">Revenir à une version précédente-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="940bf-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="940bf-129">Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="940bf-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="940bf-130">Pour cela, vous pouvez utiliser l’Assistant de récupération avancée pour rétablir votre HoloLens sur une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="940bf-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="940bf-131">Revenir à une version antérieure supprime vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="940bf-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="940bf-132">Pour revenir à une version antérieure de HoloLens 2, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="940bf-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="940bf-133">Assurez-vous que vous n’avez pas de téléphone ou d’appareil Windows branché sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="940bf-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="940bf-134">Sur votre PC, téléchargez l' [Assistant de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) sur le Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="940bf-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="940bf-135">Téléchargez la [version d’HoloLens 2 la plus récente](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="940bf-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="940bf-136">Lorsque vous avez terminé ces téléchargements, ouvrez l' **Explorateur de fichiers**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="940bf-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="940bf-137">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="940bf-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="940bf-138">Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C.</span><span class="sxs-lookup"><span data-stu-id="940bf-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="940bf-139">Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.</span><span class="sxs-lookup"><span data-stu-id="940bf-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="940bf-140">Le compagnon de récupération avancée détecte automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="940bf-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="940bf-141">Sélectionnez la vignette **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="940bf-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="940bf-142">Dans l’écran suivant, sélectionnez **sélection manuelle du package** , puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="940bf-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="940bf-143">(Recherchez un fichier avec l’extension. FFU.)</span><span class="sxs-lookup"><span data-stu-id="940bf-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="940bf-144">Sélectionnez **installer le logiciel**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="940bf-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="940bf-145">Revenir à une version précédente-HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="940bf-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="940bf-146">Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="940bf-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="940bf-147">Pour cela, vous pouvez utiliser l’outil de récupération d’appareils Windows pour réinitialiser votre HoloLens vers la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="940bf-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="940bf-148">Revenir à une version antérieure supprime vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="940bf-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="940bf-149">Pour revenir à une version antérieure de HoloLens 1, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="940bf-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="940bf-150">Assurez-vous que vous n’avez pas de téléphone ou d’appareil Windows branché sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="940bf-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="940bf-151">Sur votre PC, téléchargez l' [outil de récupération de périphériques Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="940bf-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="940bf-152">Téléchargez le [package de récupération des mises à jour d’anniversaire HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="940bf-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="940bf-153">À la fin des téléchargements, ouvrez le dossier téléchargements de l' **Explorateur de fichiers**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="940bf-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="940bf-154">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extract** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="940bf-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="940bf-155">Connectez votre HoloLens à votre PC à l’aide du câble micro-USB qui vous est fourni.</span><span class="sxs-lookup"><span data-stu-id="940bf-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="940bf-156">Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.</span><span class="sxs-lookup"><span data-stu-id="940bf-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="940bf-157">Le WDRT détecte automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="940bf-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="940bf-158">Sélectionnez la vignette **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="940bf-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="940bf-159">Dans l’écran suivant, sélectionnez **sélection manuelle du package** , puis choisissez le fichier d’installation contenu dans le dossier que vous avez sélectionné dans l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="940bf-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="940bf-160">(Recherchez un fichier avec l’extension. FFU.)</span><span class="sxs-lookup"><span data-stu-id="940bf-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="940bf-161">Sélectionnez **installer le logiciel**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="940bf-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="940bf-162">Si WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre PC.</span><span class="sxs-lookup"><span data-stu-id="940bf-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="940bf-163">Si cela ne fonctionne pas, sélectionnez **mon périphérique n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="940bf-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="940bf-164">Programme Windows Insider sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="940bf-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="940bf-165">Vous voulez découvrir les dernières fonctionnalités de HoloLens?</span><span class="sxs-lookup"><span data-stu-id="940bf-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="940bf-166">Si tel est le cas, rejoignez le programme Windows Insider; vous aurez accès à des versions d’évaluation des mises à jour du logiciel HoloLens avant qu’elles ne soient disponibles pour le grand public.</span><span class="sxs-lookup"><span data-stu-id="940bf-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="940bf-167">[Obtenez Windows Insider Preview pour Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="940bf-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
