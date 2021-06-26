---
title: Mettre à jour HoloLens 2
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924109"
---
# <a name="update-hololens-2"></a><span data-ttu-id="76a3f-104">Mettre à jour HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="76a3f-104">Update HoloLens 2</span></span>

<span data-ttu-id="76a3f-105">HoloLens utilise Windows Update, tout comme les autres appareils Windows 10.</span><span class="sxs-lookup"><span data-stu-id="76a3f-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="76a3f-106">Votre HoloLens télécharge et installe automatiquement les mises à jour système chaque fois qu’il est connecté à Power et connecté à Internet, même lorsqu’il est en veille.</span><span class="sxs-lookup"><span data-stu-id="76a3f-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="76a3f-107">Cet article passe en revue les outils HoloLens pour :</span><span class="sxs-lookup"><span data-stu-id="76a3f-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="76a3f-108">affichage de la version actuelle du système d’exploitation (numéro de version)</span><span class="sxs-lookup"><span data-stu-id="76a3f-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="76a3f-109">recherche de mises à jour</span><span class="sxs-lookup"><span data-stu-id="76a3f-109">checking for updates</span></span>
- <span data-ttu-id="76a3f-110">mise à jour manuelle de HoloLens</span><span class="sxs-lookup"><span data-stu-id="76a3f-110">manually updating HoloLens</span></span>
- <span data-ttu-id="76a3f-111">restauration d’une mise à jour antérieure</span><span class="sxs-lookup"><span data-stu-id="76a3f-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="76a3f-112">Vérifier la version de votre système d’exploitation (numéro de version)</span><span class="sxs-lookup"><span data-stu-id="76a3f-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="76a3f-113">Vous pouvez vérifier le numéro de version du système (numéro de Build) en ouvrant l’application paramètres et en sélectionnant **système**  >  **à propos** de.</span><span class="sxs-lookup"><span data-stu-id="76a3f-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="76a3f-114">Rechercher les mises à jour et les mettre à jour manuellement</span><span class="sxs-lookup"><span data-stu-id="76a3f-114">Check for updates and manually update</span></span>

<span data-ttu-id="76a3f-115">Vous pouvez rechercher des mises à jour à tout moment dans paramètres.</span><span class="sxs-lookup"><span data-stu-id="76a3f-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="76a3f-116">Pour afficher les mises à jour disponibles et rechercher les nouvelles mises à jour :</span><span class="sxs-lookup"><span data-stu-id="76a3f-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="76a3f-117">Ouvrez l’application **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="76a3f-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="76a3f-118">Accédez à **mettre à jour &**  >  **Windows Update** de sécurité.</span><span class="sxs-lookup"><span data-stu-id="76a3f-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="76a3f-119">Sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="76a3f-119">Select **Check for updates**.</span></span>

<span data-ttu-id="76a3f-120">Si une mise à jour est disponible, le téléchargement de la nouvelle version est lancé.</span><span class="sxs-lookup"><span data-stu-id="76a3f-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="76a3f-121">Une fois le téléchargement terminé, sélectionnez le bouton **redémarrer maintenant** pour déclencher l’installation.</span><span class="sxs-lookup"><span data-stu-id="76a3f-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="76a3f-122">Si votre appareil est inférieur à 40% et qu’il n’est pas branché, le redémarrage ne démarrera pas l’installation de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="76a3f-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="76a3f-123">Pendant l’installation de la mise à jour, votre HoloLens affiche des engrenages et un indicateur de progression.</span><span class="sxs-lookup"><span data-stu-id="76a3f-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="76a3f-124">Ne désactivez pas votre HoloLens pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="76a3f-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="76a3f-125">Il redémarrera automatiquement une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="76a3f-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="76a3f-126">HoloLens applique une mise à jour à la fois.</span><span class="sxs-lookup"><span data-stu-id="76a3f-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="76a3f-127">Si votre HoloLens est plus d’une version derrière la version la plus récente, vous devrez peut-être exécuter plusieurs fois le processus de mise à jour pour le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="76a3f-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="76a3f-128">Revenir à une version précédente</span><span class="sxs-lookup"><span data-stu-id="76a3f-128">Go back to a previous version</span></span>

<span data-ttu-id="76a3f-129">Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="76a3f-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="76a3f-130">Les étapes recommandées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="76a3f-130">The recommended steps are:</span></span>

1. <span data-ttu-id="76a3f-131">Contactez le support technique pour voir s’ils peuvent résoudre votre problème.</span><span class="sxs-lookup"><span data-stu-id="76a3f-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="76a3f-132">Assurez-vous que les données de télémétrie **facultatives** ou **complètes** sont activées. cela rend votre bogue plus exploitable et plus facile pour les ingénieurs à diagnostiquer.</span><span class="sxs-lookup"><span data-stu-id="76a3f-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="76a3f-133">[Commentaires de fichier](hololens-feedback.md) aussi descriptifs que possible.</span><span class="sxs-lookup"><span data-stu-id="76a3f-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="76a3f-134">Prenez note du titre ou utilisez la fonctionnalité partager pour pouvoir partager votre bogue avec la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="76a3f-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="76a3f-135">Contactez le [support technique](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="76a3f-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="76a3f-136">S’il s’agit d’un problème qui doit être résolu en revenant à une version antérieure, il peut vous fournir le FFU pour flasher votre appareil.</span><span class="sxs-lookup"><span data-stu-id="76a3f-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="76a3f-137">Si cela ne fonctionne pas, [réinitialisez ou redémarrez votre HoloLens 2 avec le compagnon de récupération avancé](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="76a3f-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="76a3f-138">Sur votre PC, téléchargez l' [Assistant de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) à partir du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="76a3f-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="76a3f-139">Assurez-vous que vous n’avez aucun téléphone ou appareil Windows branché sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="76a3f-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="76a3f-140">Choisissez la version à utiliser pour le flash :</span><span class="sxs-lookup"><span data-stu-id="76a3f-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="76a3f-141">Vous pouvez télécharger la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="76a3f-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="76a3f-142">Vous pouvez utiliser la build par défaut qu’ARC héberge.</span><span class="sxs-lookup"><span data-stu-id="76a3f-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="76a3f-143">(Si vous choisissez cette option, ignorez l’étape suivante.)</span><span class="sxs-lookup"><span data-stu-id="76a3f-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="76a3f-144">Vous pouvez utiliser une prise en charge de build fournie avec.</span><span class="sxs-lookup"><span data-stu-id="76a3f-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="76a3f-145">Une fois ces téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  **téléchargements**.</span><span class="sxs-lookup"><span data-stu-id="76a3f-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="76a3f-146">Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.</span><span class="sxs-lookup"><span data-stu-id="76a3f-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="76a3f-147">Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C.</span><span class="sxs-lookup"><span data-stu-id="76a3f-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="76a3f-148">(Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)</span><span class="sxs-lookup"><span data-stu-id="76a3f-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="76a3f-149">L’Assistant de récupération avancée détecte automatiquement votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="76a3f-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="76a3f-150">Sélectionnez la vignette **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="76a3f-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="76a3f-151">Dans l’écran suivant, sélectionnez **sélection manuelle des packages** , puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="76a3f-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="76a3f-152">(Recherchez un fichier avec l’extension. FFU.)</span><span class="sxs-lookup"><span data-stu-id="76a3f-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="76a3f-153">Sélectionnez **installer le logiciel** et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="76a3f-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="76a3f-154">En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.</span><span class="sxs-lookup"><span data-stu-id="76a3f-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="76a3f-155">En outre, si vous souhaitez rester sur la version actuellement installée, vous pouvez également suspendre manuellement les [mises à jour](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="76a3f-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="76a3f-156">Cela permet à l’équipe d’ingénierie de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="76a3f-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="76a3f-157">Programme Windows Insider sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="76a3f-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="76a3f-158">Vous souhaitez afficher les fonctionnalités les plus récentes dans HoloLens ?</span><span class="sxs-lookup"><span data-stu-id="76a3f-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="76a3f-159">Si c’est le cas, participez au programme Windows Insider. vous pouvez accéder à des versions préliminaires des mises à jour logicielles HoloLens avant qu’elles ne soient disponibles pour le grand public.</span><span class="sxs-lookup"><span data-stu-id="76a3f-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="76a3f-160">[Obtenir la version préliminaire de Windows Insider pour Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="76a3f-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
