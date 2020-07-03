---
title: Redémarrer, réinitialiser ou récupérer HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828058"
---
# <span data-ttu-id="f0a8d-104">Réinitialiser et récupérer pour HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f0a8d-104">Reset and Recovery for HoloLens 2</span></span>

## <span data-ttu-id="f0a8d-105">Chargement de l’appareil</span><span class="sxs-lookup"><span data-stu-id="f0a8d-105">Charging the device</span></span>

<span data-ttu-id="f0a8d-106">Avant de commencer une procédure de dépannage, si possible, assurez-vous que votre appareil est débité d’au moins 20% et 40%.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="f0a8d-107">Vérifiez que vous utilisez le chargeur et les câbles de type C USB fournis avec l’appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="f0a8d-108">Si elles ne sont pas disponibles, assurez-vous que le chargeur disponible peut prendre en charge au moins 15W de l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a8d-109">Dans la mesure du possible, n’utilisez pas de PC pour débiter l’appareil sur USB, car cela permet d’obtenir un coût très faible.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="f0a8d-110">Si l’appareil est correctement amorcé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier les frais de votre batterie.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="f0a8d-111">Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="f0a8d-112">Utilisation du voyant près du bouton de mise sous tension (pour 40%, vous devez voir au moins deux VOYANTs pleins).</span><span class="sxs-lookup"><span data-stu-id="f0a8d-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="f0a8d-113">Sur votre ordinateur hôte, ouvrez la fenêtre de l’Explorateur de fichiers et recherchez votre appareil HoloLens 2 sur le côté gauche sous «ce PC».</span><span class="sxs-lookup"><span data-stu-id="f0a8d-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="f0a8d-114">a.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-114">a.</span></span> <span data-ttu-id="f0a8d-115">Cliquez avec le bouton droit sur le nom de l’appareil, puis sélectionnez Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="f0a8d-116">Une boîte de dialogue s’affiche, indiquant le niveau de batterie de votre appareil.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

<span data-ttu-id="f0a8d-118">Si l’appareil ne peut pas être amorcé dans le menu de démarrage, notez les voyants et l’énumération sur l’ordinateur hôte et suivez le Guide de résolution des problèmes (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="f0a8d-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="f0a8d-119">Si l’état de l’appareil n’est pas inclus dans l’un des États indiqués dans le Guide de résolution des problèmes, exécutez le **procédure de réinitialisation matérielle** sans rebrancher l’appareil sur votre PC hôte, mais Connectez-le à la place de l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="f0a8d-120">Patientez au moins une heure pour le chargement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="f0a8d-121">Réinitialisez l’appareil</span><span class="sxs-lookup"><span data-stu-id="f0a8d-121">Reset the device</span></span>

<span data-ttu-id="f0a8d-122">Dans certains cas, il est possible que le client soit obligé de réinitialiser manuellement l’appareil sans utiliser l’interface utilisateur SW.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="f0a8d-123">Procédure standard</span><span class="sxs-lookup"><span data-stu-id="f0a8d-123">Standard procedure</span></span>
1. <span data-ttu-id="f0a8d-124">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="f0a8d-125">Appuyez de façon prolongée sur le bouton **Alimentation** pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="f0a8d-126">Tous les voyants doivent être désactivés.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="f0a8d-127">Patientez 2-3 secondes, puis appuyez sur le **bouton Alimentation**, les voyants situés près du bouton d’alimentation s’allument et l’appareil commence à démarrer.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="f0a8d-128">Connectez l’appareil à l’ordinateur hôte, ouvrez le gestionnaire d’appareils (pour Windows 10, appuyez sur la **touche «Windows»** puis sur la **touche «x»** et cliquez sur «Gestionnaire de périphériques») et vérifiez que l’appareil est correctement répertorié en tant que Microsoft HoloLens, comme illustré dans les images ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="f0a8d-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

### <span data-ttu-id="f0a8d-130">Procédure de réinitialisation matérielle</span><span class="sxs-lookup"><span data-stu-id="f0a8d-130">Hard-reset procedure</span></span>

<span data-ttu-id="f0a8d-131">Si la procédure de réinitialisation standard ne fonctionne pas, vous pouvez utiliser la procédure de réinitialisation matérielle.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="f0a8d-132">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="f0a8d-133">Maintenez enfoncée le bouton **baisser le volume + alimentation** pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="f0a8d-134">L’appareil redémarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="f0a8d-135">Connectez l’appareil à l’ordinateur hôte, ouvrez le gestionnaire d’appareils (pour Windows 10, appuyez sur la touche **«Windows»** puis sur la **touche «x»** et cliquez sur «gestionnaire de périphériques») et vérifiez que l’appareil est correctement répertorié en tant que Microsoft HoloLens, comme illustré dans les images ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="f0a8d-137">Nettoyer l’appareil</span><span class="sxs-lookup"><span data-stu-id="f0a8d-137">Clean reflash the device</span></span>

<span data-ttu-id="f0a8d-138">Dans certains cas, il peut être nécessaire de nettoyer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="f0a8d-139">Il existe deux méthodes pour refaire clignoter un appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="f0a8d-140">Pour toutes les procédures de reflashage, vous devez [installer l’application Assistant Récupération avancée à partir du Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="f0a8d-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="f0a8d-141">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels sont supprimés, y compris la réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="f0a8d-142">L’Assistant Récupération avancée est actuellement paramétré pour télécharger la build de la fonctionnalité version pour [Windows holographique 2004](hololens-release-notes.md#windows-holographic-version-2004), si vous voulez télécharger la dernière version de HoloLens 2 FFU pour flasher votre appareil via Advanced Recovery Companion, vous pouvez le télécharger à partir [ici](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="f0a8d-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="f0a8d-143">Ces informations sont mises à jour et correspondent à la dernière build généralement disponible.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="f0a8d-144">Avant de commencer la procédure de clignotement, assurez-vous que l’application est installée et en cours d’exécution sur votre PC Windows 10 et que vous êtes prêt à détecter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Réinstallation rapide de HoloLens 2](images/ARC1.png)

### <span data-ttu-id="f0a8d-146">Procédure normale</span><span class="sxs-lookup"><span data-stu-id="f0a8d-146">Normal procedure</span></span>

1. <span data-ttu-id="f0a8d-147">Pendant l’exécution de l’appareil HoloLens, connectez-le à votre PC Windows 10 sur lequel vous avez précédemment lancé l’application compagnon de récupération avancée.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="f0a8d-148">L’appareil est automatiquement détecté et l’interface utilisateur de l’application compagnon récupération avancée se met à jour comme suit:</span><span class="sxs-lookup"><span data-stu-id="f0a8d-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![Réinstallation rapide de HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="f0a8d-150">Sélectionnez l’appareil HoloLens2 dans l’interface utilisateur de l’application Assistant Récupération avancée et suivez les instructions pour terminer le clignotement.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="f0a8d-151">Procédure manuelle</span><span class="sxs-lookup"><span data-stu-id="f0a8d-151">Manual procedure</span></span>

<span data-ttu-id="f0a8d-152">Si l’appareil ne démarre pas correctement, il se peut que vous deviez placer l’appareil HoloLens 2 en mode de récupération.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="f0a8d-153">Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="f0a8d-154">Appuyez de façon prolongée sur le bouton **Alimentation** pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="f0a8d-155">Tous les voyants doivent s’éteindre.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="f0a8d-156">Tout en appuyant sur le **bouton monter le volume**, appuyez sur le **bouton d’alimentation** pour démarrer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="f0a8d-157">Patientez 15 secondes avant de relâcher le bouton monter le volume.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="f0a8d-158">À partir des 5 LED de l’appareil, seul le LED central s’illumine.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="f0a8d-159">Connectez l’appareil à l’ordinateur hôte, ouvrez le gestionnaire d’appareils (pour Windows 10, appuyez sur la **touche «Windows»** puis sur la **touche «x»** et cliquez sur «Gestionnaire de périphériques») et vérifiez que l’appareil est correctement répertorié en tant que Microsoft HoloLens, comme illustré dans l’image ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="f0a8d-161">L’appareil est détecté automatiquement, et l’interface utilisateur de l’application compagnon de récupération avancée se met à jour comme suit:</span><span class="sxs-lookup"><span data-stu-id="f0a8d-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![Réinstallation rapide de HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="f0a8d-163">Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Assistant Récupération avancée et suivez les instructions pour terminer le clignotement.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="f0a8d-164">Téléchargement d’un ARC sans utiliser l’App Store</span><span class="sxs-lookup"><span data-stu-id="f0a8d-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="f0a8d-165">Si un environnement informatique empêche l’utilisation de l’application Windows Store ou limite l’accès au magasin, les administrateurs informatiques peuvent rendre cette application disponible via d’autres chemins de déploiement «hors connexion».</span><span class="sxs-lookup"><span data-stu-id="f0a8d-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="f0a8d-166">Ce processus peut également être utilisé pour d’autres applications, comme illustré à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="f0a8d-167">Ce guide se concentre sur l’Assistant récupération avancé, mais mon compte est modifié pour les autres applications hors connexion.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="f0a8d-168">Ce chemin de déploiement peut être activé en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="f0a8d-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="f0a8d-169">Accédez au [site web Magasin pour les entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="f0a8d-170">Accédez à **Gérer – Paramètres**, puis activez **Afficher les applications en mode hors connexion** sous **Expérience de commerce**, comme décrit dans https://businessstore.microsoft.com/manage/settings/shop</span><span class="sxs-lookup"><span data-stu-id="f0a8d-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="f0a8d-171">Accédez à **magasiner pour mon groupe** et recherchez l’application [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="f0a8d-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="f0a8d-172">Modifiez la zone **Type de licence** en mode hors connexion, puis cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="f0a8d-173">Sous Télécharger le package pour une utilisation en mode hors connexion, cliquez sur le deuxième bouton bleu **«Télécharger»**.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="f0a8d-174">Assurez-vous que l’extension de fichier est .appxbundle.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="f0a8d-175">À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur et installez.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="f0a8d-176">L’administrateur informatique peut également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="f0a8d-177">Si l’ordinateur cible ne dispose d’aucune connectivité Internet, des étapes supplémentaires sont nécessaires:</span><span class="sxs-lookup"><span data-stu-id="f0a8d-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="f0a8d-178">Sélectionnez la licence non codée, puis cliquez sur **«Générer une licence»** puis sous **«Cadre nécessaire»** cliquez sur **«Télécharger».**</span><span class="sxs-lookup"><span data-stu-id="f0a8d-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="f0a8d-179">Les PC disposant d’un accès à Internet devront utiliser DISM pour appliquer le package avec la dépendance et la licence.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="f0a8d-180">Dans une invite de commandes administrateur, tapez:</span><span class="sxs-lookup"><span data-stu-id="f0a8d-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="f0a8d-181">Il se peut que le numéro de version dans cet exemple de code ne corresponde pas à la version actuellement disponible.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="f0a8d-182">Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple fourni.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="f0a8d-183">Assurez-vous d’apporter les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="f0a8d-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="f0a8d-184">Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une FFU en mode hors connexion, il peut être utile de télécharger votre image clignotante sur disponible. Voici [l’image actuelle pour HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="f0a8d-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="f0a8d-185">Autres ressources</span><span class="sxs-lookup"><span data-stu-id="f0a8d-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


