---
title: Redémarrer, réinitialiser ou récupérer HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Comment utiliser l’Assistant Récupération avancée pour flasher une image dans HoloLens 2.
keywords: procédure de réinitialisation, de réinitialisation, de récupération, de réinitialisation matérielle, de réinitialisation à chaud, de cycle de démarrage, HoloLens, arrêt, arc, compagnon de récupération avancée
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 8c028ed39cf0925ebff18ca69889de2d87f1e7eb
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996412"
---
# <span data-ttu-id="d11fc-104">Redémarrer, réinitialiser ou récupérer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d11fc-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="d11fc-105">Recharger l’appareil</span><span class="sxs-lookup"><span data-stu-id="d11fc-105">Charge the device</span></span>

<span data-ttu-id="d11fc-106">Avant de commencer une procédure de dépannage, assurez-vous que la batterie de votre appareil est au moins entre 20 et 40%, si possible.</span><span class="sxs-lookup"><span data-stu-id="d11fc-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="d11fc-107">Utilisez le chargeur et les câbles USB de typeC fournis avec l’appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="d11fc-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="d11fc-108">Le bloc d’alimentation et le câble USB-C vers C fournis avec l’appareil constituent le meilleur moyen de charger votre HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d11fc-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="d11fc-109">Le chargeur fournit 18W d’alimentation (9V à 2A).</span><span class="sxs-lookup"><span data-stu-id="d11fc-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="d11fc-110">Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur disponible peut supporter au moins 15W de puissance.</span><span class="sxs-lookup"><span data-stu-id="d11fc-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="d11fc-111">Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB, ce serait trop lent.</span><span class="sxs-lookup"><span data-stu-id="d11fc-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="d11fc-112">Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie:</span><span class="sxs-lookup"><span data-stu-id="d11fc-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="d11fc-113">Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d11fc-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="d11fc-114">Regardez le voyant près du bouton d’alimentation (pour un débit de 40%, vous devriez voir au moins deux voyants pleins).</span><span class="sxs-lookup"><span data-stu-id="d11fc-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="d11fc-115">Lorsque l’appareil est en charge, l’indicateur de batterie s’allume pour indiquer le niveau de charge actuel.</span><span class="sxs-lookup"><span data-stu-id="d11fc-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="d11fc-116">Le dernier voyant clignote lentement pour indiquer que l’appareil est en charge.</span><span class="sxs-lookup"><span data-stu-id="d11fc-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="d11fc-117">Lorsque votre HoloLens est allumé, le témoin de la batterie affiche le niveau de la batterie par cinq incréments.</span><span class="sxs-lookup"><span data-stu-id="d11fc-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="d11fc-118">Lorsqu’un seul des cinq voyants est allumé, le niveau de batterie est inférieur à 20%.</span><span class="sxs-lookup"><span data-stu-id="d11fc-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="d11fc-119">Si le niveau de batterie est extrêmement faible et que vous essayez d’allumer l’appareil, un voyant clignote brièvement, puis s’éteint.</span><span class="sxs-lookup"><span data-stu-id="d11fc-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="d11fc-120">Sur votre ordinateur hôte, ouvrez la fenêtre de l’**Explorateur de fichiers** et recherchez votre appareil HoloLens2 sur le côté gauche sous **CePC**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="d11fc-121">Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="d11fc-122">Une boîte de dialogue indique le niveau de charge de la batterie.</span><span class="sxs-lookup"><span data-stu-id="d11fc-122">A dialog box will show the battery charge level.</span></span>

   ![Un écran Propriétés HoloLens2 affiche le niveau de charge de la batterie](images/ResetRecovery2.png)

<span data-ttu-id="d11fc-124">Si l’appareil ne parvient pas à démarrer à partir du menu Démarrer, observez l’apparence des voyants et l’énumération d’appareils sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="d11fc-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="d11fc-125">Suivez ensuite le [Guide de résolution des problèmes](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="d11fc-125">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="d11fc-126">Si l’état de l’appareil ne correspond à aucun des états indiqués dans le Guide de résolution des problèmes, démarrez une [procédure de réinitialisation matérielle](hololens-recovery.md#hard-reset-procedure) avec l’appareil connecté à l’alimentation, et non à votre PChôte.</span><span class="sxs-lookup"><span data-stu-id="d11fc-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="d11fc-127">Patientez au moins une heure pour le chargement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d11fc-127">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="d11fc-128">Réinitialisez l’appareil</span><span class="sxs-lookup"><span data-stu-id="d11fc-128">Reset the device</span></span>

<span data-ttu-id="d11fc-129">Dans certains cas, il se peut que vous deviez réinitialiser manuellement l’appareil sans utiliser l’interface utilisateurdu logiciel.</span><span class="sxs-lookup"><span data-stu-id="d11fc-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="d11fc-130">Procédure standard</span><span class="sxs-lookup"><span data-stu-id="d11fc-130">Standard procedure</span></span>
1. <span data-ttu-id="d11fc-131">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="d11fc-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="d11fc-132">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="d11fc-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="d11fc-133">Tous les voyants doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="d11fc-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="d11fc-134">Attendez 2-3secondes, puis appuyez de façon brève sur le bouton **d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="d11fc-135">Les voyants situés près du bouton d’alimentation s’allument, et l’appareil commence à démarrer.</span><span class="sxs-lookup"><span data-stu-id="d11fc-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="d11fc-136">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="d11fc-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="d11fc-137">(Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="d11fc-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="d11fc-139">Procédure de réinitialisation matérielle</span><span class="sxs-lookup"><span data-stu-id="d11fc-139">Hard-reset procedure</span></span>

<span data-ttu-id="d11fc-140">Si la procédure de réinitialisation standard ne fonctionne pas, utilisez la procédure de réinitialisation matérielle:</span><span class="sxs-lookup"><span data-stu-id="d11fc-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="d11fc-141">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="d11fc-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="d11fc-142">Maintenez enfoncées les touches **baisser le volume** +  et **alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="d11fc-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="d11fc-143">L’appareil redémarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d11fc-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="d11fc-144">Connectez l’appareil à l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="d11fc-144">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="d11fc-145">Ouvrez le gestionnaire de périphériques (pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**).</span><span class="sxs-lookup"><span data-stu-id="d11fc-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="d11fc-146">Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="d11fc-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="d11fc-148">Nettoyer l’appareil</span><span class="sxs-lookup"><span data-stu-id="d11fc-148">Clean-reflash the device</span></span>

<span data-ttu-id="d11fc-149">Dans de rares cas, il peut être nécessaire de nettoyer l’Hololens2.</span><span class="sxs-lookup"><span data-stu-id="d11fc-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="d11fc-150">Veuillez noter que la réinstallation rapide n’est pas susceptible d’affecter les problèmes suivants:</span><span class="sxs-lookup"><span data-stu-id="d11fc-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="d11fc-151">Uniformiser la couleur d’affichage</span><span class="sxs-lookup"><span data-stu-id="d11fc-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="d11fc-152">Démarrage avec un son, mais pas de sortie d’affichage</span><span class="sxs-lookup"><span data-stu-id="d11fc-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="d11fc-153">1-3-5-Modèle LED</span><span class="sxs-lookup"><span data-stu-id="d11fc-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="d11fc-154">Surchauffe</span><span class="sxs-lookup"><span data-stu-id="d11fc-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="d11fc-155">Les blocages du système d'exploitation (qui sont distincts des blocages de l’application)</span><span class="sxs-lookup"><span data-stu-id="d11fc-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="d11fc-156">Il existe deux méthodes pour nettoyer un appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="d11fc-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="d11fc-157">Pour chacune, vous devez commencer par installer [Advanced Recovery Companion à partir du WindowsStore](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="d11fc-157">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="d11fc-158">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront supprimés, y compris les informations de réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="d11fc-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="d11fc-159">Par défaut, Advanced Recovery Companion est actuellement paramétré pour télécharger le build de production de fonctionnalités pour [Windows Holographique2004](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="d11fc-159">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="d11fc-160">Si besoin, téléchargez la dernière version de la mise à jour FullFlashUpdate (FFU) d’ HoloLens2 pour réinitialiser votre appareil via Advanced Recovery Companion, [ici](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="d11fc-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="d11fc-161">Cette version est le build le plus récent disponible.</span><span class="sxs-lookup"><span data-stu-id="d11fc-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="d11fc-162">Avant de commencer la procédure de réinitialisation, assurez-vous que l’application est installée et en cours d’exécution sur votre PC Windows10 et qu’elle est prête à détecter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d11fc-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Capture d’écran de réinitialisation d’HoloLens2](images/ARC1.png)

### <span data-ttu-id="d11fc-164">Procédure normale</span><span class="sxs-lookup"><span data-stu-id="d11fc-164">Normal procedure</span></span>

1. <span data-ttu-id="d11fc-165">Lorsque l’appareil HoloLens est en marche, connectez-le au PC Windows10 sur lequel vous avez déjà ouvert l’application Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="d11fc-165">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="d11fc-166">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:</span><span class="sxs-lookup"><span data-stu-id="d11fc-166">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran initial de réinitialisation d’HoloLens2](images/ARC2.png)

3. <span data-ttu-id="d11fc-168">Sélectionnez l’appareil HoloLens2 dans l’interface utilisateur de l’application Advanced Recovery Companion et suivez les instructions pour effectuer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="d11fc-168">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="d11fc-169">Procédure manuelle</span><span class="sxs-lookup"><span data-stu-id="d11fc-169">Manual procedure</span></span>

<span data-ttu-id="d11fc-170">Si HoloLens2 ne démarre pas correctement, vous devrez peut-être placer l’appareil en mode de récupération:</span><span class="sxs-lookup"><span data-stu-id="d11fc-170">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="d11fc-171">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="d11fc-171">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="d11fc-172">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="d11fc-172">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="d11fc-173">Tous les voyants doivent s’éteindre.</span><span class="sxs-lookup"><span data-stu-id="d11fc-173">All LEDs should turn off.</span></span>

3. <span data-ttu-id="d11fc-174">Tout en appuyant sur le bouton pour **augmenter le volume**, appuyez sur le bouton **d’alimentation** pour démarrer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d11fc-174">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="d11fc-175">Patientez 15secondes avant de relâcher le bouton **d’augmentation du volume**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-175">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="d11fc-176">Parmi les cinq voyants lumineux, seul celui du milieu s’allume.</span><span class="sxs-lookup"><span data-stu-id="d11fc-176">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="d11fc-177">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="d11fc-177">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="d11fc-178">(Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que MicrosoftHoloLens comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="d11fc-178">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="d11fc-180">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:</span><span class="sxs-lookup"><span data-stu-id="d11fc-180">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran de réinitialisation d’HoloLens2](images/ARC2.png)

6. <span data-ttu-id="d11fc-182">Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion, puis suivez les instructions pour terminer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="d11fc-182">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="d11fc-183">Télécharger ARC sans utiliser l’AppStore</span><span class="sxs-lookup"><span data-stu-id="d11fc-183">Download ARC without using the app store</span></span>

<span data-ttu-id="d11fc-184">Si l’environnement informatique empêche l’utilisation de l’application WindowsStore ou limite l’accès au Retail Store, l’administrateur informatique peut rendre cette application disponible via un chemin de déploiement «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="d11fc-184">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="d11fc-185">Les administrateurs informatiques peuvent également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.</span><span class="sxs-lookup"><span data-stu-id="d11fc-185">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="d11fc-186">Ce guide se concentre sur l’utilisation d’Advanced Recovery Companion, mais le processus peut également être utilisé pour d’autres applications «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="d11fc-186">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="d11fc-187">Pour activer le chemin de déploiement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="d11fc-187">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="d11fc-188">Accédez à [Microsoft Store pour Entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d11fc-188">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="d11fc-189">Accédez à **Gérer – Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-189">Go to **Manage – Settings**.</span></span> <span data-ttu-id="d11fc-190">Activez **Afficher les applications hors connexion** sous **Shopping Experience**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-190">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="d11fc-191">Accédez à **Acheter pour mon groupe** et recherchez [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="d11fc-191">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="d11fc-192">Définissez le **type de licence** comme***Hors connexion***, puis sélectionnez **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-192">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="d11fc-193">Sous **Télécharger le package pour l’utilisation en mode hors connexion**, sélectionnez le deuxième bouton bleu **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-193">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="d11fc-194">Assurez-vous que l’extension de fichier est *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="d11fc-194">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="d11fc-195">À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur le package pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="d11fc-195">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="d11fc-196">Si l’ordinateur de destination n’est pas connecté à Internet, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="d11fc-196">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="d11fc-197">Sélectionnez la licence non codée, puis sélectionnez **Générer une licence**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-197">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="d11fc-198">Sous **Infrastructures requises**, sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="d11fc-198">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="d11fc-199">Utilisez DISM pour appliquer le package avec la dépendance et la licence.</span><span class="sxs-lookup"><span data-stu-id="d11fc-199">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="d11fc-200">À partir d’une invite de commandes administrateur, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="d11fc-200">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="d11fc-201">Il se peut que le numéro de version dans cet exemple de code ne corresponde pas à la version actuellement disponible.</span><span class="sxs-lookup"><span data-stu-id="d11fc-201">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="d11fc-202">Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="d11fc-202">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="d11fc-203">Apportez les modifications nécessaires à la commande.</span><span class="sxs-lookup"><span data-stu-id="d11fc-203">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="d11fc-204">Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une mise à jourFFU en mode hors connexion, il peut être utile de télécharger votre image flash.</span><span class="sxs-lookup"><span data-stu-id="d11fc-204">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="d11fc-205">[**Télécharger l’image actuelle pour Hololens2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="d11fc-205">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="d11fc-206">Autres ressources</span><span class="sxs-lookup"><span data-stu-id="d11fc-206">Other resources:</span></span>
- [<span data-ttu-id="d11fc-207">Distribuer des applications hors connexion</span><span class="sxs-lookup"><span data-stu-id="d11fc-207">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="d11fc-208">Options de ligne de commande de service de package d’applicationDISM (.appx ou .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="d11fc-208">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
