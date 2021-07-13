---
title: Redémarrer, réinitialiser ou récupérer HoloLens 2
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Utiliser l’Assistant Récupération avancée pour flasher une image dans HoloLens 2.
keywords: procédure de réinitialisation, de réinitialisation, de récupération, de réinitialisation matérielle, de réinitialisation à chaud, de cycle de démarrage, HoloLens, arrêt, arc, advanced recovery companion
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
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923633"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="19a99-104">Redémarrer, réinitialiser ou récupérer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="19a99-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="19a99-105">Avant de commencer une procédure de dépannage, assurez-vous que la batterie de votre appareil est au minimum entre **20 et 40 %** , si possible.</span><span class="sxs-lookup"><span data-stu-id="19a99-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="19a99-106">Les [témoins](hololens2-setup.md#lights-that-indicate-the-battery-level) situés sous le bouton d'alimentation permettent de vérifier rapidement la capacité de la batterie sans se connecter à l'appareil.</span><span class="sxs-lookup"><span data-stu-id="19a99-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="19a99-107">Utilisez le [chargeur et le câble de type USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) fournis avec l’HoloLens 2 pour charger votre appareil de manière optimale.</span><span class="sxs-lookup"><span data-stu-id="19a99-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="19a99-108">Le chargeur fournit 18 W d’alimentation (9V à 2A).</span><span class="sxs-lookup"><span data-stu-id="19a99-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="19a99-109">À l'aide du chargeur mural fourni, l'HoloLens 2 peut recharger complètement sa batterie en moins de 65 minutes lorsqu'il est en veille.</span><span class="sxs-lookup"><span data-stu-id="19a99-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="19a99-110">Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur mis à disposition peut supporter au moins 15 W de puissance.</span><span class="sxs-lookup"><span data-stu-id="19a99-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="19a99-111">Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB car ce processus est lent.</span><span class="sxs-lookup"><span data-stu-id="19a99-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="19a99-112">Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie :</span><span class="sxs-lookup"><span data-stu-id="19a99-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="19a99-113">Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="19a99-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="19a99-114">Regardez le voyant situé près du bouton d’alimentation (pour une charge de 40 %, vous devriez voir au moins deux voyants pleins).</span><span class="sxs-lookup"><span data-stu-id="19a99-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="19a99-115">Lorsque l’appareil est en charge, l’indicateur de batterie s’allume pour indiquer le niveau de charge actuel.</span><span class="sxs-lookup"><span data-stu-id="19a99-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="19a99-116">Le dernier voyant clignote lentement pour indiquer que l’appareil est en charge.</span><span class="sxs-lookup"><span data-stu-id="19a99-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="19a99-117">Lorsque votre HoloLens est allumé, le témoin de la batterie affiche le niveau de la batterie par cinq incréments.</span><span class="sxs-lookup"><span data-stu-id="19a99-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="19a99-118">Lorsqu’un seul des cinq voyants est allumé, le niveau de la batterie est inférieur à 20 %.</span><span class="sxs-lookup"><span data-stu-id="19a99-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="19a99-119">Si le niveau de la batterie est extrêmement faible et que vous essayez d’allumer l’appareil, un voyant clignote brièvement, puis s’éteint.</span><span class="sxs-lookup"><span data-stu-id="19a99-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="19a99-120">Sur votre ordinateur hôte, ouvrez l’**Explorateurs de fichiers** et recherchez votre appareil HoloLens 2 sur le côté gauche sous **Ce PC**.</span><span class="sxs-lookup"><span data-stu-id="19a99-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="19a99-121">Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="19a99-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="19a99-122">Une boîte de dialogue indique le niveau de charge de la batterie.</span><span class="sxs-lookup"><span data-stu-id="19a99-122">A dialog box will show the battery charge level.</span></span>

   ![Un écran Propriétés HoloLens 2 affiche le niveau de charge de la batterie](images/ResetRecovery2.png)

<span data-ttu-id="19a99-124">Si l’appareil ne parvient pas à démarrer à partir du menu Démarrer, observez l’apparence des voyants et l’énumération d’appareils sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="19a99-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="19a99-125">Suivez ensuite le [Guide de résolution des problèmes](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="19a99-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="19a99-126">Si l’état de l’appareil ne correspond à aucun des états indiqués dans le Guide de résolution des problèmes, démarrez une [procédure de réinitialisation matérielle](hololens-recovery.md#hard-reset-procedure) avec l’appareil connecté à l’alimentation, et non à votre PC hôte.</span><span class="sxs-lookup"><span data-stu-id="19a99-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="19a99-127">Patientez au moins une heure pour le chargement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="19a99-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="19a99-128">Réinitialisation de l’appareil</span><span class="sxs-lookup"><span data-stu-id="19a99-128">Reset the device</span></span>

<span data-ttu-id="19a99-129">Vous pouvez être amené à réinitialiser manuellement l’appareil sans utiliser l’interface utilisateur du logiciel.</span><span class="sxs-lookup"><span data-stu-id="19a99-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="19a99-130">Procédure standard</span><span class="sxs-lookup"><span data-stu-id="19a99-130">Standard procedure</span></span>

1. <span data-ttu-id="19a99-131">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.</span><span class="sxs-lookup"><span data-stu-id="19a99-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="19a99-132">Appuyez de façon prolongée sur le bouton d’**alimentation** pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="19a99-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="19a99-133">Tous les voyants doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="19a99-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="19a99-134">Attendez 2 à 3 secondes, puis appuyez brièvement sur le bouton d’**alimentation**.</span><span class="sxs-lookup"><span data-stu-id="19a99-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="19a99-135">Les voyants situés près du bouton d’alimentation s’allument, et l’appareil commence à démarrer.</span><span class="sxs-lookup"><span data-stu-id="19a99-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="19a99-136">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="19a99-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="19a99-137">(Pour Windows 10, appuyez sur la touche **Windows**, puis sur la touche **X** et sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que *Microsoft HoloLens* comme le montre l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="19a99-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gestionnaire de périphériques HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="19a99-139">Procédure de réinitialisation matérielle</span><span class="sxs-lookup"><span data-stu-id="19a99-139">Hard-reset procedure</span></span>

<span data-ttu-id="19a99-140">Si la procédure de réinitialisation standard ne fonctionne pas, utilisez la procédure de réinitialisation matérielle :</span><span class="sxs-lookup"><span data-stu-id="19a99-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="19a99-141">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.</span><span class="sxs-lookup"><span data-stu-id="19a99-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="19a99-142">Maintenez les boutons **baisser le volume** + **alimentation** enfoncés pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="19a99-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="19a99-143">L’appareil redémarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="19a99-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="19a99-144">Connectez l’appareil à l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="19a99-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="19a99-145">Ouvrez le Gestionnaire de périphériques (pour Windows 10, appuyez sur la touche **Windows**, puis sur la touche **X** et sélectionnez , puis sélectionnez **Gestionnaire de périphériques**).</span><span class="sxs-lookup"><span data-stu-id="19a99-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="19a99-146">Assurez-vous que l’appareil est répertorié correctement en tant que *Microsoft HoloLens* comme le montre l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="19a99-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gestionnaire de périphériques HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="19a99-148">Réinitialiser l’appareil</span><span class="sxs-lookup"><span data-stu-id="19a99-148">Clean-reflash the device</span></span>

<span data-ttu-id="19a99-149">Dans de rares cas, il peut être nécessaire de réinitialiser l’Hololens 2.</span><span class="sxs-lookup"><span data-stu-id="19a99-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="19a99-150">Notez qu’une telle opération n’a pas d’incidence sur les problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="19a99-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="19a99-151">Uniformiser la couleur d’affichage</span><span class="sxs-lookup"><span data-stu-id="19a99-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="19a99-152">Démarrage avec un son, mais pas de sortie d’affichage</span><span class="sxs-lookup"><span data-stu-id="19a99-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="19a99-153">Modèle LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="19a99-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="19a99-154">Surchauffe</span><span class="sxs-lookup"><span data-stu-id="19a99-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="19a99-155">Blocages du système d'exploitation (différents des blocages d’application)</span><span class="sxs-lookup"><span data-stu-id="19a99-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="19a99-156">Il existe deux méthodes pour réinitialiser un appareil HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="19a99-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="19a99-157">Pour ces deux méthodes, vous devez d’abord [installer Advanced Recovery Companion à partir du Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="19a99-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="19a99-158">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront supprimés, y compris les informations de réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="19a99-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="19a99-159">Par défaut, Advanced Recovery Companion est configuré pour télécharger la version la plus récente de publication de la fonctionnalité, consultez cette page pour accéder à nos [Notes de publication](hololens-release-notes.md#) relative à la dernière publication de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="19a99-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="19a99-160">Pour télécharger la dernière version de package de mise à jour FFU (Full Flash Update) HoloLens 2 afin de réinitialiser votre appareil via Advanced Recovery Companion, [cliquez ici et téléchargez la dernière image mensuelle HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="19a99-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="19a99-161">Cette version correspond à la build le plus récente disponible.</span><span class="sxs-lookup"><span data-stu-id="19a99-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="19a99-162">Avant de commencer la procédure de réinitialisation, assurez-vous que l’application est installée, en cours d’exécution sur votre PC Windows 10 et prête à détecter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="19a99-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="19a99-163">Assurez-vous également que votre HoloLens est chargé à un minimum de 40 %.</span><span class="sxs-lookup"><span data-stu-id="19a99-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Capture d’écran de réinitialisation d’HoloLens 2](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="19a99-165">Procédure normale</span><span class="sxs-lookup"><span data-stu-id="19a99-165">Normal procedure</span></span>

1. <span data-ttu-id="19a99-166">Lorsque l’appareil HoloLens est en marche, connectez-le au PC Windows 10 sur lequel vous avez déjà ouvert l’application Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="19a99-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="19a99-167">L’appareil est automatiquement détecté, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour :</span><span class="sxs-lookup"><span data-stu-id="19a99-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran initial de réinitialisation d’HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="19a99-169">Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion et suivez les instructions pour effectuer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="19a99-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="19a99-170">Procédure manuelle</span><span class="sxs-lookup"><span data-stu-id="19a99-170">Manual procedure</span></span>

<span data-ttu-id="19a99-171">Si HoloLens 2 ne démarre pas correctement ou si Advanced Recovery Companion ne parvient pas à détecter l’appareil, vous devrez peut-être placer l’appareil en mode de récupération :</span><span class="sxs-lookup"><span data-stu-id="19a99-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="19a99-172">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.</span><span class="sxs-lookup"><span data-stu-id="19a99-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="19a99-173">Appuyez de façon prolongée sur le bouton d’**alimentation** pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="19a99-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="19a99-174">Tous les voyants doivent s’éteindre.</span><span class="sxs-lookup"><span data-stu-id="19a99-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="19a99-175">Tout en appuyant sur le bouton pour **monter le volume**, appuyez sur le bouton d’**alimentation** pour démarrer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="19a99-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="19a99-176">Patientez 15 secondes avant de relâcher le bouton pour **monter le volume**.</span><span class="sxs-lookup"><span data-stu-id="19a99-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="19a99-177">Parmi les cinq voyants lumineux, seul celui du milieu s’allume.</span><span class="sxs-lookup"><span data-stu-id="19a99-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="19a99-178">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="19a99-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="19a99-179">(Pour Windows 10, appuyez sur la touche **Windows**, puis sur la touche **X** et sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que Microsoft HoloLens comme le montre l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="19a99-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="19a99-181">L’appareil est automatiquement détecté, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour :</span><span class="sxs-lookup"><span data-stu-id="19a99-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran de réinitialisation HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="19a99-183">Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion, puis suivez les instructions pour terminer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="19a99-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="19a99-184">Résoudre les problèmes liés à l’application Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="19a99-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="19a99-185">Assurez-vous que votre appareil est chargé à un minimum de 40 % avant de tenter une réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="19a99-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="19a99-186">Vérifiez que votre appareil est déverrouillé.</span><span class="sxs-lookup"><span data-stu-id="19a99-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="19a99-187">Si Advanced Recovery Companion ne détecte pas votre appareil, assurez-vous que vous pouvez vous connecter à celui-ci via l’Explorateur de fichiers sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="19a99-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="19a99-188">Dans le cas contraire,</span><span class="sxs-lookup"><span data-stu-id="19a99-188">If you cannot;</span></span>

    1.  <span data-ttu-id="19a99-189">Il est possible que votre appareil présente des stratégies USB qui désactivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="19a99-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="19a99-190">Si tel est le cas, essayez le [mode de réinitialisation manuelle](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="19a99-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="19a99-191">En l’absence de stratégies, essayez un autre câble USB.</span><span class="sxs-lookup"><span data-stu-id="19a99-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="19a99-192">Vérifiez que votre appareil n’affiche pas un [modèle LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).</span><span class="sxs-lookup"><span data-stu-id="19a99-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="19a99-193">Télécharger Advanced Recovery Companion sans utiliser l’App Store</span><span class="sxs-lookup"><span data-stu-id="19a99-193">Download ARC without using the app store</span></span>

<span data-ttu-id="19a99-194">Si l’environnement informatique empêche l’utilisation de l’application Windows Store ou limite l’accès au Retail Store, l’administrateur informatique peut rendre cette application disponible via un chemin de déploiement « hors connexion ».</span><span class="sxs-lookup"><span data-stu-id="19a99-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="19a99-195">Les administrateurs informatiques peuvent également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.</span><span class="sxs-lookup"><span data-stu-id="19a99-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="19a99-196">Ce guide se concentre sur l’utilisation d’Advanced Recovery Companion, mais le processus peut également être utilisé pour d’autres applications « hors connexion ».</span><span class="sxs-lookup"><span data-stu-id="19a99-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="19a99-197">Pour activer le chemin de déploiement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="19a99-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="19a99-198">Accédez à [Microsoft Store pour Entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19a99-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="19a99-199">Accédez à **Gérer - Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="19a99-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="19a99-200">Activez **Afficher les applications hors connexion** sous **Expérience d’achat**.</span><span class="sxs-lookup"><span data-stu-id="19a99-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="19a99-201">Accédez à **Acheter pour mon groupe** et recherchez [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="19a99-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="19a99-202">Remplacez le **type de licence** par **_hors connexion_ *_, puis sélectionnez _* Gérer**.</span><span class="sxs-lookup"><span data-stu-id="19a99-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="19a99-203">Sous **Télécharger le package pour une utilisation hors connexion**, sélectionnez le deuxième bouton bleu **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="19a99-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="19a99-204">Assurez-vous que le fichier porte l’extension *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="19a99-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="19a99-205">À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur le package pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="19a99-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="19a99-206">Si l’ordinateur de destination ne dispose pas d’une connexion Internet, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="19a99-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="19a99-207">Sélectionnez la licence non codée, puis **Générer une licence**.</span><span class="sxs-lookup"><span data-stu-id="19a99-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="19a99-208">Sous **Frameworks requis**, sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="19a99-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="19a99-209">Utilisez DISM pour appliquer le package avec la dépendance et la licence.</span><span class="sxs-lookup"><span data-stu-id="19a99-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="19a99-210">À partir d’une invite de commandes administrateur, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="19a99-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="19a99-211">Le numéro de version de cet exemple de code peut ne pas correspondre à la version actuellement disponible.</span><span class="sxs-lookup"><span data-stu-id="19a99-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="19a99-212">Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="19a99-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="19a99-213">Apportez les modifications nécessaires à la commande.</span><span class="sxs-lookup"><span data-stu-id="19a99-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="19a99-214">Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une mise à jour FFU en mode hors connexion, il peut s’avérer utile de télécharger votre image flash.</span><span class="sxs-lookup"><span data-stu-id="19a99-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="19a99-215">[**Téléchargez l’image actuelle pour HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="19a99-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="19a99-216">Autres ressources :</span><span class="sxs-lookup"><span data-stu-id="19a99-216">Other resources:</span></span>
- [<span data-ttu-id="19a99-217">Distribuer des applications hors connexion</span><span class="sxs-lookup"><span data-stu-id="19a99-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="19a99-218">Options de ligne de commande de service de package d’application DISM (.appx ou .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="19a99-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
