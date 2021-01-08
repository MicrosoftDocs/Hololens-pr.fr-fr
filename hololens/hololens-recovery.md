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
ms.openlocfilehash: 7845a00d1141fb721683c4e3f2a884ed0c37c735
ms.sourcegitcommit: 33911e3b405732d0d31a27039c8f590d52b647c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2021
ms.locfileid: "11254831"
---
# <span data-ttu-id="be1db-104">Redémarrer, réinitialiser ou récupérer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="be1db-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="be1db-105">Recharger l’appareil</span><span class="sxs-lookup"><span data-stu-id="be1db-105">Charge the device</span></span>

<span data-ttu-id="be1db-106">Avant de commencer une procédure de dépannage, assurez-vous que la batterie de votre appareil est au moins entre 20 et 40%, si possible.</span><span class="sxs-lookup"><span data-stu-id="be1db-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="be1db-107">Utilisez le chargeur et les câbles USB de typeC fournis avec l’appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="be1db-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="be1db-108">Le bloc d’alimentation et le câble USB-C vers C fournis avec l’appareil constituent le meilleur moyen de charger votre HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="be1db-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="be1db-109">Le chargeur fournit 18W d’alimentation (9V à 2A).</span><span class="sxs-lookup"><span data-stu-id="be1db-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="be1db-110">À l’aide du chargeur mural fourni, les appareils HoloLens 2 peuvent charger la batterie à l’intégralité en moins de 65 minutes lorsque l’appareil est en veille.</span><span class="sxs-lookup"><span data-stu-id="be1db-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="be1db-111">Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur disponible peut supporter au moins 15W de puissance.</span><span class="sxs-lookup"><span data-stu-id="be1db-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="be1db-112">Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB, ce serait trop lent.</span><span class="sxs-lookup"><span data-stu-id="be1db-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="be1db-113">Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie:</span><span class="sxs-lookup"><span data-stu-id="be1db-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="be1db-114">Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="be1db-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="be1db-115">Regardez le voyant près du bouton d’alimentation (pour un débit de 40%, vous devriez voir au moins deux voyants pleins).</span><span class="sxs-lookup"><span data-stu-id="be1db-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="be1db-116">Lorsque l’appareil est en charge, l’indicateur de batterie s’allume pour indiquer le niveau de charge actuel.</span><span class="sxs-lookup"><span data-stu-id="be1db-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="be1db-117">Le dernier voyant clignote lentement pour indiquer que l’appareil est en charge.</span><span class="sxs-lookup"><span data-stu-id="be1db-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="be1db-118">Lorsque votre HoloLens est allumé, le témoin de la batterie affiche le niveau de la batterie par cinq incréments.</span><span class="sxs-lookup"><span data-stu-id="be1db-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="be1db-119">Lorsqu’un seul des cinq voyants est allumé, le niveau de batterie est inférieur à 20%.</span><span class="sxs-lookup"><span data-stu-id="be1db-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="be1db-120">Si le niveau de batterie est extrêmement faible et que vous essayez d’allumer l’appareil, un voyant clignote brièvement, puis s’éteint.</span><span class="sxs-lookup"><span data-stu-id="be1db-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="be1db-121">Sur votre ordinateur hôte, ouvrez la fenêtre de l’**Explorateur de fichiers** et recherchez votre appareil HoloLens2 sur le côté gauche sous **CePC**.</span><span class="sxs-lookup"><span data-stu-id="be1db-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="be1db-122">Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="be1db-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="be1db-123">Une boîte de dialogue indique le niveau de charge de la batterie.</span><span class="sxs-lookup"><span data-stu-id="be1db-123">A dialog box will show the battery charge level.</span></span>

   ![Un écran Propriétés HoloLens2 affiche le niveau de charge de la batterie](images/ResetRecovery2.png)

<span data-ttu-id="be1db-125">Si l’appareil ne parvient pas à démarrer à partir du menu Démarrer, observez l’apparence des voyants et l’énumération d’appareils sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="be1db-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="be1db-126">Suivez ensuite le [Guide de résolution des problèmes](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="be1db-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="be1db-127">Si l’état de l’appareil ne correspond à aucun des états indiqués dans le Guide de résolution des problèmes, démarrez une [procédure de réinitialisation matérielle](hololens-recovery.md#hard-reset-procedure) avec l’appareil connecté à l’alimentation, et non à votre PChôte.</span><span class="sxs-lookup"><span data-stu-id="be1db-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="be1db-128">Patientez au moins une heure pour le chargement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="be1db-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="be1db-129">Réinitialisez l’appareil</span><span class="sxs-lookup"><span data-stu-id="be1db-129">Reset the device</span></span>

<span data-ttu-id="be1db-130">Dans certains cas, il se peut que vous deviez réinitialiser manuellement l’appareil sans utiliser l’interface utilisateurdu logiciel.</span><span class="sxs-lookup"><span data-stu-id="be1db-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="be1db-131">Procédure standard</span><span class="sxs-lookup"><span data-stu-id="be1db-131">Standard procedure</span></span>

1. <span data-ttu-id="be1db-132">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="be1db-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="be1db-133">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="be1db-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="be1db-134">Tous les voyants doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="be1db-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="be1db-135">Attendez 2-3secondes, puis appuyez de façon brève sur le bouton **d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="be1db-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="be1db-136">Les voyants situés près du bouton d’alimentation s’allument, et l’appareil commence à démarrer.</span><span class="sxs-lookup"><span data-stu-id="be1db-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="be1db-137">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="be1db-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="be1db-138">(Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="be1db-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gestionnaire de périphériques HoloLens2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="be1db-140">Procédure de réinitialisation matérielle</span><span class="sxs-lookup"><span data-stu-id="be1db-140">Hard-reset procedure</span></span>

<span data-ttu-id="be1db-141">Si la procédure de réinitialisation standard ne fonctionne pas, utilisez la procédure de réinitialisation matérielle:</span><span class="sxs-lookup"><span data-stu-id="be1db-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="be1db-142">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="be1db-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="be1db-143">Maintenez enfoncées les touches **baisser le volume** +  et **alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="be1db-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="be1db-144">L’appareil redémarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="be1db-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="be1db-145">Connectez l’appareil à l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="be1db-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="be1db-146">Ouvrez le gestionnaire de périphériques (pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**).</span><span class="sxs-lookup"><span data-stu-id="be1db-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="be1db-147">Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="be1db-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gestionnaire de périphériques HoloLens2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="be1db-149">Nettoyer l’appareil</span><span class="sxs-lookup"><span data-stu-id="be1db-149">Clean-reflash the device</span></span>

<span data-ttu-id="be1db-150">Dans de rares cas, il peut être nécessaire de nettoyer l’Hololens2.</span><span class="sxs-lookup"><span data-stu-id="be1db-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="be1db-151">Veuillez noter que la réinstallation rapide n’est pas susceptible d’affecter les problèmes suivants:</span><span class="sxs-lookup"><span data-stu-id="be1db-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="be1db-152">Uniformiser la couleur d’affichage</span><span class="sxs-lookup"><span data-stu-id="be1db-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="be1db-153">Démarrage avec un son, mais pas de sortie d’affichage</span><span class="sxs-lookup"><span data-stu-id="be1db-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="be1db-154">1-3-5-Modèle LED</span><span class="sxs-lookup"><span data-stu-id="be1db-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="be1db-155">Surchauffe</span><span class="sxs-lookup"><span data-stu-id="be1db-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="be1db-156">Les blocages du système d'exploitation (qui sont distincts des blocages de l’application)</span><span class="sxs-lookup"><span data-stu-id="be1db-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="be1db-157">Il existe deux méthodes pour nettoyer un appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="be1db-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="be1db-158">Pour les deux, vous devez d’abord [installer le Compagnon de récupération avancée à partir du Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="be1db-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="be1db-159">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront supprimés, y compris les informations de réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="be1db-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="be1db-160">Par défaut, le Compagnon de récupération avancé est configuré pour télécharger la version la plus récente de publication de la fonctionnalité, consultez cette page pour découvrir nos [Notes de publication](hololens-release-notes.md#) relative à la dernière publication de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="be1db-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="be1db-161">Pour télécharger la dernière version de package de mise à jour FFU HoloLens2 pour refaire clignoter votre périphérique via le Compagnon de récupération avancé, [cliquez ici pour télécharger la dernière image de Hololens2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="be1db-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="be1db-162">Cette version est le build le plus récent disponible.</span><span class="sxs-lookup"><span data-stu-id="be1db-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="be1db-163">Avant de commencer la procédure de réinitialisation, assurez-vous que l’application est installée et en cours d’exécution sur votre PC Windows10 et qu’elle est prête à détecter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="be1db-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="be1db-164">Assurez-vous également que votre HoloLens est chargé à un minimum de 40 %.</span><span class="sxs-lookup"><span data-stu-id="be1db-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Capture d’écran de réinitialisation d’HoloLens2](images/ARC1.png)

### <span data-ttu-id="be1db-166">Procédure normale</span><span class="sxs-lookup"><span data-stu-id="be1db-166">Normal procedure</span></span>

1. <span data-ttu-id="be1db-167">Lorsque l’appareil HoloLens est en marche, connectez-le au PC Windows10 sur lequel vous avez déjà ouvert l’application Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="be1db-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="be1db-168">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:</span><span class="sxs-lookup"><span data-stu-id="be1db-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran initial de réinitialisation d’HoloLens2](images/ARC2.png)

3. <span data-ttu-id="be1db-170">Sélectionnez l’appareil HoloLens2 dans l’interface utilisateur de l’application Advanced Recovery Companion et suivez les instructions pour effectuer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="be1db-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="be1db-171">Procédure manuelle</span><span class="sxs-lookup"><span data-stu-id="be1db-171">Manual procedure</span></span>

<span data-ttu-id="be1db-172">Si HoloLens2 ne démarre pas correctement, vous devrez peut-être placer l’appareil en mode de récupération:</span><span class="sxs-lookup"><span data-stu-id="be1db-172">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="be1db-173">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="be1db-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="be1db-174">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="be1db-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="be1db-175">Tous les voyants doivent s’éteindre.</span><span class="sxs-lookup"><span data-stu-id="be1db-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="be1db-176">Tout en appuyant sur le bouton pour **augmenter le volume**, appuyez sur le bouton **d’alimentation** pour démarrer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="be1db-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="be1db-177">Patientez 15secondes avant de relâcher le bouton **d’augmentation du volume**.</span><span class="sxs-lookup"><span data-stu-id="be1db-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="be1db-178">Parmi les cinq voyants lumineux, seul celui du milieu s’allume.</span><span class="sxs-lookup"><span data-stu-id="be1db-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="be1db-179">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="be1db-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="be1db-180">(Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que MicrosoftHoloLens comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="be1db-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="be1db-182">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:</span><span class="sxs-lookup"><span data-stu-id="be1db-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran de réinitialisation d’HoloLens2](images/ARC2.png)

6. <span data-ttu-id="be1db-184">Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion, puis suivez les instructions pour terminer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="be1db-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="be1db-185">Télécharger ARC sans utiliser l’AppStore</span><span class="sxs-lookup"><span data-stu-id="be1db-185">Download ARC without using the app store</span></span>

<span data-ttu-id="be1db-186">Si l’environnement informatique empêche l’utilisation de l’application WindowsStore ou limite l’accès au Retail Store, l’administrateur informatique peut rendre cette application disponible via un chemin de déploiement «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="be1db-186">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="be1db-187">Les administrateurs informatiques peuvent également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.</span><span class="sxs-lookup"><span data-stu-id="be1db-187">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="be1db-188">Ce guide se concentre sur l’utilisation d’Advanced Recovery Companion, mais le processus peut également être utilisé pour d’autres applications «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="be1db-188">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="be1db-189">Pour activer le chemin de déploiement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="be1db-189">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="be1db-190">Accédez à [Microsoft Store pour Entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be1db-190">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="be1db-191">Accédez à **Gérer – Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="be1db-191">Go to **Manage – Settings**.</span></span> <span data-ttu-id="be1db-192">Activez **Afficher les applications hors connexion** sous **Shopping Experience**.</span><span class="sxs-lookup"><span data-stu-id="be1db-192">Turn on **Show offline apps** under **Shopping experience**.</span></span>
1. <span data-ttu-id="be1db-193">Accédez à la **section acheter pour mon groupe**et recherchez l' [\**_Assistant de récupération avancée_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="be1db-193">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="be1db-194">Changez le _*Type de licence*\* en \**_mode hors connexion_*_, puis sélectionnez _\*Manage\*\*.</span><span class="sxs-lookup"><span data-stu-id="be1db-194">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="be1db-195">Sous **Télécharger le package pour l’utilisation en mode hors connexion**, sélectionnez le deuxième bouton bleu **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="be1db-195">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="be1db-196">Assurez-vous que l’extension de fichier est *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="be1db-196">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="be1db-197">À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur le package pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="be1db-197">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="be1db-198">Si l’ordinateur de destination ne dispose pas d’une connexion Internet, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="be1db-198">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="be1db-199">Sélectionnez la licence non codée, puis sélectionnez **Générer une licence**.</span><span class="sxs-lookup"><span data-stu-id="be1db-199">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="be1db-200">Sous **Infrastructures requises**, sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="be1db-200">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="be1db-201">Utilisez DISM pour appliquer le package avec la dépendance et la licence.</span><span class="sxs-lookup"><span data-stu-id="be1db-201">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="be1db-202">À partir d’une invite de commandes administrateur, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="be1db-202">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="be1db-203">Il se peut que le numéro de version dans cet exemple de code ne corresponde pas à la version actuellement disponible.</span><span class="sxs-lookup"><span data-stu-id="be1db-203">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="be1db-204">Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="be1db-204">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="be1db-205">Apportez les modifications nécessaires à la commande.</span><span class="sxs-lookup"><span data-stu-id="be1db-205">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="be1db-206">Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une mise à jourFFU en mode hors connexion, il peut être utile de télécharger votre image flash.</span><span class="sxs-lookup"><span data-stu-id="be1db-206">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="be1db-207">[**Télécharger l’image actuelle pour Hololens2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="be1db-207">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>

<span data-ttu-id="be1db-208">Autres ressources</span><span class="sxs-lookup"><span data-stu-id="be1db-208">Other resources:</span></span>
- [<span data-ttu-id="be1db-209">Distribuer des applications hors connexion</span><span class="sxs-lookup"><span data-stu-id="be1db-209">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="be1db-210">Options de ligne de commande de service de package d’applicationDISM (.appx ou .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="be1db-210">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
