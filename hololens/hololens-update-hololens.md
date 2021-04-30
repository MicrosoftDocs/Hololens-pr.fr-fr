---
title: Mettre à jour HoloLens
description: Découvrez comment vérifier votre numéro de build HoloLens, tenir à jour les mises à jour des appareils, joindre le programme Insiders et restaurer les mises à jour.
keywords: Comment, mettre à jour, restaurer, HoloLens, vérifier la build, numéro de build
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
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308811"
---
# <a name="update-hololens"></a><span data-ttu-id="2133f-104">Mettre à jour HoloLens</span><span class="sxs-lookup"><span data-stu-id="2133f-104">Update HoloLens</span></span>

<span data-ttu-id="2133f-105">HoloLens utilise Windows Update, tout comme les autres appareils Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2133f-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="2133f-106">Votre HoloLens télécharge et installe automatiquement les mises à jour système chaque fois qu’il est connecté à Power et connecté à Internet, même lorsqu’il est en veille.</span><span class="sxs-lookup"><span data-stu-id="2133f-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="2133f-107">Cet article passe en revue les outils HoloLens pour :</span><span class="sxs-lookup"><span data-stu-id="2133f-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="2133f-108">affichage de la version actuelle du système d’exploitation (numéro de version)</span><span class="sxs-lookup"><span data-stu-id="2133f-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="2133f-109">recherche de mises à jour</span><span class="sxs-lookup"><span data-stu-id="2133f-109">checking for updates</span></span>
- <span data-ttu-id="2133f-110">mise à jour manuelle de HoloLens</span><span class="sxs-lookup"><span data-stu-id="2133f-110">manually updating HoloLens</span></span>
- <span data-ttu-id="2133f-111">restauration d’une mise à jour antérieure</span><span class="sxs-lookup"><span data-stu-id="2133f-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="2133f-112">Vérifier la version de votre système d’exploitation (numéro de version)</span><span class="sxs-lookup"><span data-stu-id="2133f-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="2133f-113">Vous pouvez vérifier le numéro de version du système (numéro de Build) en ouvrant l’application paramètres et en sélectionnant **système**  >  **à propos** de.</span><span class="sxs-lookup"><span data-stu-id="2133f-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="2133f-114">Rechercher les mises à jour et les mettre à jour manuellement</span><span class="sxs-lookup"><span data-stu-id="2133f-114">Check for updates and manually update</span></span>

<span data-ttu-id="2133f-115">Vous pouvez rechercher des mises à jour à tout moment dans paramètres.</span><span class="sxs-lookup"><span data-stu-id="2133f-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="2133f-116">Pour afficher les mises à jour disponibles et rechercher les nouvelles mises à jour :</span><span class="sxs-lookup"><span data-stu-id="2133f-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="2133f-117">Ouvrez l’application **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="2133f-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="2133f-118">Accédez à **mettre à jour &**  >  **Windows Update** de sécurité.</span><span class="sxs-lookup"><span data-stu-id="2133f-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="2133f-119">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="2133f-119">Select **Check for updates**.</span></span>

<span data-ttu-id="2133f-120">Si une mise à jour est disponible, le téléchargement de la nouvelle version est lancé.</span><span class="sxs-lookup"><span data-stu-id="2133f-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="2133f-121">Une fois le téléchargement terminé, sélectionnez le bouton **redémarrer maintenant** pour déclencher l’installation.</span><span class="sxs-lookup"><span data-stu-id="2133f-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="2133f-122">Si votre appareil est inférieur à 40% et qu’il n’est pas branché, le redémarrage ne démarrera pas l’installation de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2133f-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="2133f-123">Pendant l’installation de la mise à jour, votre HoloLens affiche des engrenages et un indicateur de progression.</span><span class="sxs-lookup"><span data-stu-id="2133f-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="2133f-124">Ne désactivez pas votre HoloLens pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="2133f-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="2133f-125">Il redémarrera automatiquement une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="2133f-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="2133f-126">HoloLens applique une mise à jour à la fois.</span><span class="sxs-lookup"><span data-stu-id="2133f-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="2133f-127">Si votre HoloLens est plus d’une version derrière la version la plus récente, vous devrez peut-être exécuter plusieurs fois le processus de mise à jour pour le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="2133f-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="2133f-128">Revenir à une version précédente-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="2133f-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="2133f-129">Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2133f-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="2133f-130">Pour ce faire, vous pouvez utiliser l’Assistant de récupération avancé pour réinitialiser votre HoloLens à la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="2133f-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="2133f-131">En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="2133f-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="2133f-132">Pour revenir à une version précédente de HoloLens 2, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2133f-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="2133f-133">Assurez-vous que vous n’avez aucun téléphone ou appareil Windows branché sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="2133f-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="2133f-134">Sur votre PC, téléchargez l' [Assistant de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) à partir du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="2133f-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="2133f-135">Téléchargez la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="2133f-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="2133f-136">Une fois ces téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  **téléchargements**.</span><span class="sxs-lookup"><span data-stu-id="2133f-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="2133f-137">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="2133f-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2133f-138">Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C.</span><span class="sxs-lookup"><span data-stu-id="2133f-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="2133f-139">(Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)</span><span class="sxs-lookup"><span data-stu-id="2133f-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2133f-140">L’Assistant de récupération avancée détecte automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2133f-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="2133f-141">Sélectionnez la vignette **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="2133f-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="2133f-142">Dans l’écran suivant, sélectionnez **sélection manuelle des packages** , puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="2133f-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="2133f-143">(Recherchez un fichier avec l’extension. FFU.)</span><span class="sxs-lookup"><span data-stu-id="2133f-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="2133f-144">Sélectionnez **installer le logiciel** et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="2133f-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="2133f-145">Revenir à une version précédente-HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="2133f-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="2133f-146">Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2133f-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="2133f-147">Pour ce faire, vous pouvez utiliser l’outil de récupération de périphérique de Windows pour réinitialiser votre HoloLens à la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="2133f-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="2133f-148">En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="2133f-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="2133f-149">Pour revenir à une version précédente de HoloLens 1, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2133f-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="2133f-150">Assurez-vous que vous n’avez aucun téléphone ou appareil Windows branché sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="2133f-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="2133f-151">Sur votre PC, téléchargez l' [outil de récupération d’appareils Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="2133f-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="2133f-152">Téléchargez le [package de récupération de la mise à jour de l’anniversaire HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="2133f-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="2133f-153">Une fois les téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  .</span><span class="sxs-lookup"><span data-stu-id="2133f-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="2133f-154">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="2133f-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2133f-155">Connectez votre HoloLens à votre PC à l’aide du câble micro-USB avec lequel il a été fourni.</span><span class="sxs-lookup"><span data-stu-id="2133f-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="2133f-156">(Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)</span><span class="sxs-lookup"><span data-stu-id="2133f-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2133f-157">Le WDRT détectera automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2133f-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="2133f-158">Sélectionnez la vignette **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="2133f-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="2133f-159">Dans l’écran suivant, sélectionnez **sélection manuelle des packages** et choisissez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="2133f-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="2133f-160">(Recherchez un fichier avec l’extension. FFU.)</span><span class="sxs-lookup"><span data-stu-id="2133f-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="2133f-161">Sélectionnez **installer le logiciel** et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="2133f-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="2133f-162">Si le WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2133f-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="2133f-163">Si cela ne fonctionne pas, sélectionnez **mon appareil n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="2133f-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="2133f-164">Programme Windows Insider sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="2133f-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="2133f-165">Vous souhaitez afficher les fonctionnalités les plus récentes dans HoloLens ?</span><span class="sxs-lookup"><span data-stu-id="2133f-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="2133f-166">Si c’est le cas, participez au programme Windows Insider. vous pouvez accéder à des versions préliminaires des mises à jour logicielles HoloLens avant qu’elles ne soient disponibles pour le grand public.</span><span class="sxs-lookup"><span data-stu-id="2133f-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="2133f-167">[Obtenir la version préliminaire de Windows Insider pour Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="2133f-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
