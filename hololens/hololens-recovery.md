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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915956"
---
# <span data-ttu-id="f9d3d-104">Redémarrer, réinitialiser ou récupérer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f9d3d-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="f9d3d-105">Recharger l’appareil</span><span class="sxs-lookup"><span data-stu-id="f9d3d-105">Charge the device</span></span>

<span data-ttu-id="f9d3d-106">Avant de commencer une procédure de dépannage, assurez-vous que la batterie de votre appareil est au moins entre 20 et 40%, si possible.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="f9d3d-107">Utilisez le chargeur et les câbles USB de typeC fournis avec l’appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-107">Use the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="f9d3d-108">Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur disponible peut supporter au moins 15W de puissance.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-108">If those accessories aren't available, make sure the charger that's available can support at least 15 W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="f9d3d-109">Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB, ce serait trop lent.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-109">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="f9d3d-110">Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-110">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="f9d3d-111">Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-111">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="f9d3d-112">Regardez le voyant près du bouton d’alimentation (pour un débit de 40%, vous devriez voir au moins deux voyants pleins).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-112">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
- <span data-ttu-id="f9d3d-113">Sur votre ordinateur hôte, ouvrez la fenêtre de l’Explorateur de fichiers et recherchez votre appareil HoloLens2 sur le côté gauche sous **CePC**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-113">On your host PC, open File Explorer and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="f9d3d-114">Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-114">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="f9d3d-115">Une boîte de dialogue indique le niveau de charge de la batterie.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-115">A dialog box will show the battery charge level.</span></span>

   ![Un écran Propriétés HoloLens2 affiche le niveau de charge de la batterie](images/ResetRecovery2.png)

<span data-ttu-id="f9d3d-117">Si l’appareil ne parvient pas à démarrer à partir du menu Démarrer, observez l’apparence des voyants et l’énumération d’appareils sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-117">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="f9d3d-118">Suivez ensuite le [Guide de résolution des problèmes](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-118">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="f9d3d-119">Si l’état de l’appareil ne correspond à aucun des états indiqués dans le Guide de résolution des problèmes, démarrez une *procédure de réinitialisation matérielle* avec l’appareil connecté à l’alimentation, et non à votre PChôte.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-119">If the state of the device doesn't match any of the states listed in the troubleshooting guide, do the *hard reset procedure* with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="f9d3d-120">Patientez au moins une heure pour le chargement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-120">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="f9d3d-121">Réinitialisez l’appareil</span><span class="sxs-lookup"><span data-stu-id="f9d3d-121">Reset the device</span></span>

<span data-ttu-id="f9d3d-122">Dans certains cas, il se peut que vous deviez réinitialiser manuellement l’appareil sans utiliser l’interface utilisateurSW.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-122">Under certain circumstances, you may have to manually reset the device without using the SW UI.</span></span>

### <span data-ttu-id="f9d3d-123">Procédure standard</span><span class="sxs-lookup"><span data-stu-id="f9d3d-123">Standard procedure</span></span>
1. <span data-ttu-id="f9d3d-124">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-124">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="f9d3d-125">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-125">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="f9d3d-126">Tous les voyants doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="f9d3d-127">Attendez 2-3secondes, puis appuyez de façon brève sur le bouton **d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-127">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="f9d3d-128">Les voyants situés près du bouton d’alimentation s’allument, et l’appareil commence à démarrer.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-128">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="f9d3d-129">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-129">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="f9d3d-130">(Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-130">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="f9d3d-132">Procédure de réinitialisation matérielle</span><span class="sxs-lookup"><span data-stu-id="f9d3d-132">Hard-reset procedure</span></span>

<span data-ttu-id="f9d3d-133">Si la procédure de réinitialisation standard ne fonctionne pas, utilisez la procédure de réinitialisation matérielle:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-133">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="f9d3d-134">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-134">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="f9d3d-135">Maintenez enfoncées les touches **baisser le volume** +  et **alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-135">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="f9d3d-136">L’appareil redémarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-136">The device will automatically restart.</span></span>

4. <span data-ttu-id="f9d3d-137">Connectez l’appareil à l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-137">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="f9d3d-138">Ouvrez le gestionnaire de périphériques (pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-138">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="f9d3d-139">Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-139">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="f9d3d-141">Nettoyer l’appareil</span><span class="sxs-lookup"><span data-stu-id="f9d3d-141">Clean-reflash the device</span></span>

<span data-ttu-id="f9d3d-142">Dans de rares cas, il peut être nécessaire de nettoyer l’Hololens2.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-142">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="f9d3d-143">Il existe deux méthodes pour nettoyer un appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-143">There are two ways to reflash the device.</span></span> <span data-ttu-id="f9d3d-144">Pour chacune, vous devez commencer par installer [Advanced Recovery Companion à partir du WindowsStore](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-144">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="f9d3d-145">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront supprimés, y compris les informations de réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-145">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="f9d3d-146">Par défaut, Advanced Recovery Companion est actuellement paramétré pour télécharger le build de production de fonctionnalités pour [Windows Holographique2004](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-146">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="f9d3d-147">Si besoin, téléchargez la dernière version de la mise à jour FullFlashUpdate (FFU) d’ HoloLens2 pour réinitialiser votre appareil via Advanced Recovery Companion, [ici](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-147">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="f9d3d-148">Cette version est le build le plus récent disponible.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-148">This version is the latest generally available build.</span></span>

<span data-ttu-id="f9d3d-149">Avant de commencer la procédure de réinitialisation, assurez-vous que l’application est installée et en cours d’exécution sur votre PC Windows10 et qu’elle est prête à détecter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-149">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Capture d’écran de réinitialisation d’HoloLens2](images/ARC1.png)

### <span data-ttu-id="f9d3d-151">Procédure normale</span><span class="sxs-lookup"><span data-stu-id="f9d3d-151">Normal procedure</span></span>

1. <span data-ttu-id="f9d3d-152">Lorsque l’appareil HoloLens est en marche, connectez-le au PC Windows10 sur lequel vous avez déjà ouvert l’application Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-152">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="f9d3d-153">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-153">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran initial de réinitialisation d’HoloLens2](images/ARC2.png)

3. <span data-ttu-id="f9d3d-155">Sélectionnez l’appareil HoloLens2 dans l’interface utilisateur de l’application Advanced Recovery Companion et suivez les instructions pour effectuer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-155">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="f9d3d-156">Procédure manuelle</span><span class="sxs-lookup"><span data-stu-id="f9d3d-156">Manual procedure</span></span>

<span data-ttu-id="f9d3d-157">Si HoloLens2 ne démarre pas correctement, vous devrez peut-être placer l’appareil en mode de récupération:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-157">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="f9d3d-158">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-158">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="f9d3d-159">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-159">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="f9d3d-160">Tous les voyants doivent s’éteindre.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-160">All LEDs should turn off.</span></span>

3. <span data-ttu-id="f9d3d-161">Tout en appuyant sur le bouton pour **augmenter le volume**, appuyez sur le bouton **d’alimentation** pour démarrer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-161">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="f9d3d-162">Patientez 15secondes avant de relâcher le bouton **d’augmentation du volume**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-162">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="f9d3d-163">Parmi les cinq voyants lumineux, seul celui du milieu s’allume.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-163">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="f9d3d-164">Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-164">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="f9d3d-165">(Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que MicrosoftHoloLens comme illustré dans l’image suivante:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-165">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="f9d3d-167">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Écran de réinitialisation d’HoloLens2](images/ARC2.png)

6. <span data-ttu-id="f9d3d-169">Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion, puis suivez les instructions pour terminer la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="f9d3d-170">Télécharger ARC sans utiliser l’AppStore</span><span class="sxs-lookup"><span data-stu-id="f9d3d-170">Download ARC without using the app store</span></span>

<span data-ttu-id="f9d3d-171">Si l’environnement informatique empêche l’utilisation de l’application WindowsStore ou limite l’accès au Retail Store, l’administrateur informatique peut rendre cette application disponible via un chemin de déploiement «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="f9d3d-171">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="f9d3d-172">Les administrateurs informatiques peuvent également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-172">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="f9d3d-173">Ce guide se concentre sur l’utilisation d’Advanced Recovery Companion, mais le processus peut également être utilisé pour d’autres applications «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="f9d3d-173">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="f9d3d-174">Pour activer le chemin de déploiement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-174">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="f9d3d-175">Accédez à [Microsoft Store pour Entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-175">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="f9d3d-176">Accédez à **Gérer – Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-176">Go to **Manage – Settings**.</span></span> <span data-ttu-id="f9d3d-177">Activez **Afficher les applications hors connexion** sous **Shopping Experience**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-177">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="f9d3d-178">Accédez à **Acheter pour mon groupe** et recherchez [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-178">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="f9d3d-179">Définissez le **type de licence** comme***Hors connexion***, puis sélectionnez **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-179">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="f9d3d-180">Sous **Télécharger le package pour l’utilisation en mode hors connexion**, sélectionnez le deuxième bouton bleu **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-180">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="f9d3d-181">Assurez-vous que l’extension de fichier est *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-181">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="f9d3d-182">À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur le package pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-182">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="f9d3d-183">Si l’ordinateur de destination n’est pas connecté à Internet, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-183">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="f9d3d-184">Sélectionnez la licence non codée, puis sélectionnez **Générer une licence**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-184">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="f9d3d-185">Sous **Infrastructures requises**, sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-185">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="f9d3d-186">Utilisez DISM pour appliquer le package avec la dépendance et la licence.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-186">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="f9d3d-187">À partir d’une invite de commandes administrateur, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f9d3d-187">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="f9d3d-188">Il se peut que le numéro de version dans cet exemple de code ne corresponde pas à la version actuellement disponible.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-188">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="f9d3d-189">Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-189">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="f9d3d-190">Apportez les modifications nécessaires à la commande.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-190">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="f9d3d-191">Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une mise à jourFFU en mode hors connexion, il peut être utile de télécharger votre image flash.</span><span class="sxs-lookup"><span data-stu-id="f9d3d-191">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="f9d3d-192">[**Télécharger l’image actuelle pour Hololens2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="f9d3d-192">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="f9d3d-193">Autres ressources</span><span class="sxs-lookup"><span data-stu-id="f9d3d-193">Other resources:</span></span>
- [<span data-ttu-id="f9d3d-194">Distribuer des applications hors connexion</span><span class="sxs-lookup"><span data-stu-id="f9d3d-194">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="f9d3d-195">Options de ligne de commande de service de package d’applicationDISM (.appx ou .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="f9d3d-195">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
