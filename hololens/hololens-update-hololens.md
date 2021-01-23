---
title: Mettre à jour HoloLens
description: Découvrez comment vérifier votre numéro de build HoloLens, tenir à jour les mises à jour des appareils, rejoindre le programme Insiders et revenir aux mises à jour.
keywords: how-to, update, roll back, HoloLens, check build, build number
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283935"
---
# <span data-ttu-id="e99aa-104">Mettre à jour HoloLens</span><span class="sxs-lookup"><span data-stu-id="e99aa-104">Update HoloLens</span></span>

<span data-ttu-id="e99aa-105">HoloLens utilise Windows Update, comme les autres appareils Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e99aa-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="e99aa-106">Votre HoloLens télécharge et installe automatiquement les mises à jour système chaque fois qu’il est branché et connecté à Internet, même lorsqu’il est en veille.</span><span class="sxs-lookup"><span data-stu-id="e99aa-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="e99aa-107">Cet article décrit les outils HoloLens pour :</span><span class="sxs-lookup"><span data-stu-id="e99aa-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="e99aa-108">affichage de la version actuelle de votre système d’exploitation (numéro de build)</span><span class="sxs-lookup"><span data-stu-id="e99aa-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="e99aa-109">vérification des mises à jour ;</span><span class="sxs-lookup"><span data-stu-id="e99aa-109">checking for updates</span></span>
- <span data-ttu-id="e99aa-110">mise à jour manuelle de HoloLens</span><span class="sxs-lookup"><span data-stu-id="e99aa-110">manually updating HoloLens</span></span>
- <span data-ttu-id="e99aa-111">revenir à une mise à jour plus ancienne</span><span class="sxs-lookup"><span data-stu-id="e99aa-111">rolling back to an older update</span></span>

## <span data-ttu-id="e99aa-112">Vérifier la version de votre système d’exploitation (numéro de build)</span><span class="sxs-lookup"><span data-stu-id="e99aa-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="e99aa-113">Vous pouvez vérifier le numéro de version du système (numéro de build) en ouvrant l’application Paramètres et en sélectionnant **System**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="e99aa-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="e99aa-114">Vérifier les mises à jour et les mettre à jour manuellement</span><span class="sxs-lookup"><span data-stu-id="e99aa-114">Check for updates and manually update</span></span>

<span data-ttu-id="e99aa-115">Vous pouvez vérifier les mises à jour à tout moment dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="e99aa-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="e99aa-116">Pour voir les mises à jour disponibles et vérifier les nouvelles mises à jour :</span><span class="sxs-lookup"><span data-stu-id="e99aa-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="e99aa-117">Ouvrez **l’application Paramètres.**</span><span class="sxs-lookup"><span data-stu-id="e99aa-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="e99aa-118">Accédez à **Mettre à jour & sécurité**Windows  >  **Update**.</span><span class="sxs-lookup"><span data-stu-id="e99aa-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="e99aa-119">Sélectionnez **Vérifier les mises à jour.**</span><span class="sxs-lookup"><span data-stu-id="e99aa-119">Select **Check for updates**.</span></span>

<span data-ttu-id="e99aa-120">Si une mise à jour est disponible, elle commence à télécharger la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="e99aa-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="e99aa-121">Une fois le téléchargement terminé, sélectionnez le bouton **Redémarrer maintenant** pour déclencher l’installation.</span><span class="sxs-lookup"><span data-stu-id="e99aa-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="e99aa-122">Si votre appareil est inférieur à 40 % et qu’il n’est pas branché, le redémarrage ne démarre pas l’installation de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e99aa-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="e99aa-123">Pendant que votre HoloLens installe la mise à jour, il affiche des engrenages de rotation et un indicateur de progression.</span><span class="sxs-lookup"><span data-stu-id="e99aa-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="e99aa-124">Ne pas désactiver votre HoloLens pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="e99aa-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="e99aa-125">Il redémarre automatiquement une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="e99aa-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="e99aa-126">HoloLens applique une mise à jour à la fois.</span><span class="sxs-lookup"><span data-stu-id="e99aa-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="e99aa-127">Si votre HoloLens est plus d’une version derrière la dernière version, vous devrez peut-être exécuter le processus de mise à jour plusieurs fois pour le mettre entièrement à jour.</span><span class="sxs-lookup"><span data-stu-id="e99aa-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="e99aa-128">Revenir à une version précédente - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e99aa-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="e99aa-129">Dans certains cas, vous souhaiterez peut-être revenir à une version antérieure du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e99aa-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e99aa-130">Pour ce faire, utilisez l’Outil de récupération avancée (Advanced Recovery Companion) pour réinitialiser votre HoloLens à la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="e99aa-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e99aa-131">En revenir à une version antérieure, vous supprimez vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="e99aa-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e99aa-132">Pour revenir à une version antérieure de HoloLens 2, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="e99aa-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="e99aa-133">Assurez-vous que vous n’avez pas de téléphones ou d’appareils Windows branchés sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="e99aa-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e99aa-134">Sur votre PC, téléchargez [l’Outil](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) de récupération avancée à partir du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e99aa-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="e99aa-135">Téléchargez la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="e99aa-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="e99aa-136">Une fois ces téléchargements terminés, ouvrez **l’Explorateur**  >  **de fichiers.**</span><span class="sxs-lookup"><span data-stu-id="e99aa-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e99aa-137">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="e99aa-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e99aa-138">Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C.</span><span class="sxs-lookup"><span data-stu-id="e99aa-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="e99aa-139">Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.</span><span class="sxs-lookup"><span data-stu-id="e99aa-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e99aa-140">Advanced Recovery Companion détecte automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e99aa-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="e99aa-141">Sélectionnez la vignette **Microsoft HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="e99aa-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e99aa-142">Dans l’écran suivant, sélectionnez Sélection manuelle du **package,** puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="e99aa-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="e99aa-143">(Recherchez un fichier avec l’extension .ffu.)</span><span class="sxs-lookup"><span data-stu-id="e99aa-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e99aa-144">Sélectionnez **Installer le**logiciel et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="e99aa-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="e99aa-145">Revenir à une version précédente : HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="e99aa-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="e99aa-146">Dans certains cas, vous souhaiterez peut-être revenir à une version antérieure du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e99aa-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e99aa-147">Vous pouvez le faire à l’aide de l’outil de récupération d’appareil Windows pour réinitialiser votre HoloLens à la version antérieure.</span><span class="sxs-lookup"><span data-stu-id="e99aa-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e99aa-148">En revenir à une version antérieure, vous supprimez vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="e99aa-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e99aa-149">Pour revenir à une version précédente de HoloLens 1, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e99aa-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="e99aa-150">Assurez-vous que vous n’avez pas de téléphones ou d’appareils Windows branchés sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="e99aa-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e99aa-151">Sur votre PC, téléchargez [l’outil de récupération d’appareil Windows (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="e99aa-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="e99aa-152">Téléchargez le [package de récupération de mise à jour anniversaire HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="e99aa-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="e99aa-153">Une fois les téléchargements terminés, ouvrez **l’Explorateur**  >  **de fichiers.**</span><span class="sxs-lookup"><span data-stu-id="e99aa-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e99aa-154">Cliquez avec le bouton droit sur le dossier compressé que vous avez téléchargé, puis sélectionnez **Extraire tout**  >  **l’extraction** pour le déziper.</span><span class="sxs-lookup"><span data-stu-id="e99aa-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e99aa-155">Connectez votre HoloLens à votre PC à l’aide du câble micro-USB qu’il a utilisé.</span><span class="sxs-lookup"><span data-stu-id="e99aa-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="e99aa-156">Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.</span><span class="sxs-lookup"><span data-stu-id="e99aa-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e99aa-157">Le WDRT détecte automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e99aa-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="e99aa-158">Sélectionnez la vignette **Microsoft HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="e99aa-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e99aa-159">Dans l’écran suivant, sélectionnez Sélection manuelle du **package** et choisissez le fichier d’installation contenu dans le dossier décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="e99aa-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="e99aa-160">(Recherchez un fichier avec l’extension .ffu.)</span><span class="sxs-lookup"><span data-stu-id="e99aa-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e99aa-161">Sélectionnez **Installer le**logiciel et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="e99aa-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e99aa-162">Si le WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre PC.</span><span class="sxs-lookup"><span data-stu-id="e99aa-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="e99aa-163">Si cela ne fonctionne pas, sélectionnez **Mon appareil n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="e99aa-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="e99aa-164">Programme Windows Insider sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="e99aa-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="e99aa-165">Vous souhaitez voir les dernières fonctionnalités de HoloLens ?</span><span class="sxs-lookup"><span data-stu-id="e99aa-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="e99aa-166">Si c’est le cas, rejoignez le programme Windows Insider ; Vous aurez accès aux builds d’aperçu des mises à jour logicielles HoloLens avant qu’elles ne soit disponibles pour le grand public.</span><span class="sxs-lookup"><span data-stu-id="e99aa-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="e99aa-167">[Obtenir la prévisualisation de Windows Insider pour Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="e99aa-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
