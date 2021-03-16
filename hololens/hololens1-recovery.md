---
title: Redémarrer, réinitialiser ou récupérer HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Comment utiliser l’outil récupération d’appareils Windows pour flasher une image dans HoloLens 1ère génération.
keywords: procédure de réinitialisation, de réinitialisation, de récupération, de réinitialisation matérielle, de réinitialisation à chaud, de cycle de démarrage, HoloLens, arrêt, wdrt, outil de récupération des appareils Windows
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439040"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="54c87-104">Redémarrer, réinitialiser ou récupérer HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="54c87-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="54c87-105">Si vous rencontrez des problèmes avec votre HoloLens, vous pouvez essayer d’effectuer un redémarrage ou de le réinitialiser, voire même de réinstaller le système d’exploitation à l’aide de la récupération d’appareils.</span><span class="sxs-lookup"><span data-stu-id="54c87-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="54c87-106">Cet article vous guidera à travers les étapes de récupération recommandées.</span><span class="sxs-lookup"><span data-stu-id="54c87-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="54c87-107">Si vous cherchez à récupérer votre HoloLens2, consultez[Récupération de l’HoloLens2](https://docs.microsoft.com/hololens/hololens-recovery), car ce processus est différent.</span><span class="sxs-lookup"><span data-stu-id="54c87-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="54c87-108">Cet article se concentre sur l’appareil et le logiciel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="54c87-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="54c87-109">Si le rendu de vos hologrammes est mauvais, consultez **[Considérations sur l’environnement HoloLens](hololens-environment-considerations.md)** pour obtenir des informations sur les facteurs qui améliorent la qualité de l’hologramme.</span><span class="sxs-lookup"><span data-stu-id="54c87-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="54c87-110">Redémarrer</span><span class="sxs-lookup"><span data-stu-id="54c87-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="54c87-111">Effectuer un redémarrage en toute sécurité à l’aide de Cortana</span><span class="sxs-lookup"><span data-stu-id="54c87-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="54c87-112">Le moyen le plus sûr de redémarrer votre HoloLens consiste à utiliser Cortana, qui est en règle générale la première chose à essayer lorsque vous rencontrez un problème avec HoloLens.</span><span class="sxs-lookup"><span data-stu-id="54c87-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="54c87-113">Cortana n’est pas disponible sur tous les appareils.</span><span class="sxs-lookup"><span data-stu-id="54c87-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="54c87-114">Cortana est disponible sur tous les appareils HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="54c87-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="54c87-115">Cortana est disponible sur les appareils HoloLens2 sur des builds antérieures à WindowsHolograpic, version mise à jour 2004.</span><span class="sxs-lookup"><span data-stu-id="54c87-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="54c87-116">Allumez votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="54c87-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="54c87-117">Assurez-vous qu’un utilisateur a ouvert une session et que l’appareil n’attend pas de mot de passe pour le déverrouiller.</span><span class="sxs-lookup"><span data-stu-id="54c87-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="54c87-118">Dites «Hey Cortana, redémarrez» ou «Hey Cortana, redémarrez».</span><span class="sxs-lookup"><span data-stu-id="54c87-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="54c87-119">Cortana vous répondra et vous invitera à confirmer votre choix.</span><span class="sxs-lookup"><span data-stu-id="54c87-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="54c87-120">Attendez d’entendre un son après la question, puis dites «oui».</span><span class="sxs-lookup"><span data-stu-id="54c87-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="54c87-121">L’appareil redémarrera.</span><span class="sxs-lookup"><span data-stu-id="54c87-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="54c87-122">Utiliser le bouton d’alimentation pour effectuer un redémarrage en toute sécurité</span><span class="sxs-lookup"><span data-stu-id="54c87-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="54c87-123">Si vous ne parvenez pas à redémarrer votre appareil, essayez de le redémarrer à l’aide du bouton **d’alimentation**:</span><span class="sxs-lookup"><span data-stu-id="54c87-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="54c87-124">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 5secondes.</span><span class="sxs-lookup"><span data-stu-id="54c87-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="54c87-125">Après 1seconde, les cinq voyants s’illuminent, puis s’éteignent les un après les autres, de droite à gauche.</span><span class="sxs-lookup"><span data-stu-id="54c87-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="54c87-126">Après 5secondes, tous les voyants sont éteints, ce qui indique que l’arrêt est terminé.</span><span class="sxs-lookup"><span data-stu-id="54c87-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="54c87-127">Relâchez le bouton immédiatement après que tous les voyants se sont éteints.</span><span class="sxs-lookup"><span data-stu-id="54c87-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="54c87-128">Patientez 1minute pour que l’arrêt soit complet.</span><span class="sxs-lookup"><span data-stu-id="54c87-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="54c87-129">L’arrêt peut être encore en cours, même si les affichages sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="54c87-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="54c87-130">Réactivez l’appareil en maintenant le bouton **d’alimentation** enfoncé pendant 1seconde.</span><span class="sxs-lookup"><span data-stu-id="54c87-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="54c87-131">Effectuer un redémarrage en toute sécurité à l’aide du Portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="54c87-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="54c87-132">Pour ce faire, HoloLens doit être configuré en tant qu’appareil développeur.</span><span class="sxs-lookup"><span data-stu-id="54c87-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="54c87-133">Plus d’informations sur [Portail d’appareil Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="54c87-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="54c87-134">Si la procédure précédente ne fonctionne pas, essayez de redémarrer l’appareil à l’aide de du [Portail d’appareil Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="54c87-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="54c87-135">Dans le coin supérieur droit, recherchez l’option permettant de redémarrer ou d’éteindre l’appareil.</span><span class="sxs-lookup"><span data-stu-id="54c87-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="54c87-136">Effectuer un redémarrage forcé non sécurisé</span><span class="sxs-lookup"><span data-stu-id="54c87-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="54c87-137">Si les méthodes précédentes n’ont pas redémarré votre HoloLens, forcez un redémarrage.</span><span class="sxs-lookup"><span data-stu-id="54c87-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="54c87-138">Cette méthode revient à enlever et réinstaller la batterie.</span><span class="sxs-lookup"><span data-stu-id="54c87-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="54c87-139">Cette procédure est dangereuse, car elle peut endommager votre appareil.</span><span class="sxs-lookup"><span data-stu-id="54c87-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="54c87-140">Dans ce cas, vous devez flasher votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="54c87-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="54c87-141">Il s’agit d’une méthode potentiellement nuisible qui ne doit être utilisée que si les méthodes précédemment mentionnées ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="54c87-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="54c87-142">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant au moins 10secondes.</span><span class="sxs-lookup"><span data-stu-id="54c87-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="54c87-143">Il est possible de maintenir le bouton enfoncé pendant plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="54c87-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="54c87-144">Il est possible d’ignorer toute activité LED.</span><span class="sxs-lookup"><span data-stu-id="54c87-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="54c87-145">Relâchez le bouton et attendez 2-3secondes.</span><span class="sxs-lookup"><span data-stu-id="54c87-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="54c87-146">Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 1secondes.</span><span class="sxs-lookup"><span data-stu-id="54c87-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="54c87-147">Si vous rencontrez toujours des problèmes, appuyez sur le bouton **d’alimentation** pendant 4secondes, jusqu’à ce que tous les indicateurs de batterie disparaissent et que l’écran cesse d’afficher les hologrammes.</span><span class="sxs-lookup"><span data-stu-id="54c87-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="54c87-148">Patientez 1minute, puis appuyez de nouveau sur le bouton **d’alimentation** pour allumer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="54c87-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="54c87-149">Rétablir les paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="54c87-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="54c87-150">La batterie nécessite au moins 40% de charge pour la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="54c87-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="54c87-151">Si votre HoloLens rencontre encore un problème, essayez de le réinitialiser à l’état de sortie d’usine.</span><span class="sxs-lookup"><span data-stu-id="54c87-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="54c87-152">Cette étape conserve la version du logiciel WindowsHolographique installé sur celle-ci et réinitialise tous les autres paramètres aux paramètres d’usine.</span><span class="sxs-lookup"><span data-stu-id="54c87-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="54c87-153">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels sont supprimés, y compris les informations de réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="54c87-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="54c87-154">La réinitialisation ne permet d’installer que la dernière version installée de WindowsHolographique.</span><span class="sxs-lookup"><span data-stu-id="54c87-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="54c87-155">Vous devrez rétablir toutes les étapes d’initialisation (étalonnage, connexion Wi-Fi, création d’un compte d’utilisateur, téléchargement d’applications, etc.).</span><span class="sxs-lookup"><span data-stu-id="54c87-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="54c87-156">Lancez l'application Paramètres, puis sélectionnez **Mettre à jour** > **Récupération**.</span><span class="sxs-lookup"><span data-stu-id="54c87-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="54c87-157">Sélectionnez l’option **Réinitialiser l’appareil** et lisez le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="54c87-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="54c87-158">Confirmez la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="54c87-158">Confirm the reset.</span></span> <span data-ttu-id="54c87-159">L’appareil redémarre et affiche une animation d’engrenages et une barre de progression.</span><span class="sxs-lookup"><span data-stu-id="54c87-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="54c87-160">Patientez environ 30 minutes l’exécution de ce processus.</span><span class="sxs-lookup"><span data-stu-id="54c87-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="54c87-161">Une fois l’opération terminée, l’appareil redémarre «comme neuf».</span><span class="sxs-lookup"><span data-stu-id="54c87-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="54c87-162">Réinstaller le système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="54c87-162">Reinstall the operating system</span></span>

<span data-ttu-id="54c87-163">Si le problème persiste après le redémarrage et la réinitialisation de l’appareil, vous pouvez utiliser un outil de récupération sur votre ordinateur pour réinstaller le système d’exploitation HoloLens et le microprogramme.</span><span class="sxs-lookup"><span data-stu-id="54c87-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="54c87-164">Les données requises par HoloLens pour la réinitialisation sont incluses dans une mise à jour FullFlashUpdate (FFU), ce qui est similaire à un fichier .iso, .wim ou .vhd.</span><span class="sxs-lookup"><span data-stu-id="54c87-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="54c87-165">En savoir plus sur les formats de fichier image FFU.</span><span class="sxs-lookup"><span data-stu-id="54c87-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="54c87-166">Vous pouvez installer un nouveau système d’exploitation sur votre HoloLens (1èregénération) à l’aide de l’Outil de récupération d’appareils Windows.</span><span class="sxs-lookup"><span data-stu-id="54c87-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="54c87-167">Avant d’utiliser cet outil, essayez de voir si le redémarrage ou la réinitialisation de votre HoloLens permet de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="54c87-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="54c87-168">Le processus de récupération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="54c87-168">The recovery process may take a while.</span></span> <span data-ttu-id="54c87-169">Une fois l’opération terminée, la dernière version du logiciel WindowsHolographique est installée.</span><span class="sxs-lookup"><span data-stu-id="54c87-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="54c87-170">Pour utiliser l’outil, vous avez besoin d’un ordinateur exécutant Windows10 ou une version ultérieure, avec au moins 4Go d’espace de stockage disponible.</span><span class="sxs-lookup"><span data-stu-id="54c87-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="54c87-171">Notez que vous ne pouvez pas exécuter cet outil sur une machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="54c87-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="54c87-172">Récupérer votre HoloLens</span><span class="sxs-lookup"><span data-stu-id="54c87-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="54c87-173">Téléchargez et installez [Windows Device Recovery Tool sur votre ordinateur](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).</span><span class="sxs-lookup"><span data-stu-id="54c87-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="54c87-174">Connectez l’HoloLens (1èregénération) à votre ordinateur à l’aide du câbleUSB fourni avec votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="54c87-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="54c87-175">Exécutez l’Outil de récupération d’appareils Windows et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="54c87-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="54c87-176">Si le système HoloLens (1èregénération) n’est pas détecté automatiquement, sélectionnez **Mon appareil n’a pas été détecté**.</span><span class="sxs-lookup"><span data-stu-id="54c87-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="54c87-177">Suivez ensuite les instructions pour placer l’appareil en mode de récupération.</span><span class="sxs-lookup"><span data-stu-id="54c87-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="54c87-178">Mode clignotant manuel</span><span class="sxs-lookup"><span data-stu-id="54c87-178">Manual flashing mode</span></span>

<span data-ttu-id="54c87-179">Si votre appareil n’est pas détecté, procédez comme suit pour le placer en mode clignotant:</span><span class="sxs-lookup"><span data-stu-id="54c87-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="54c87-180">Débranchez l’appareil de toute source d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="54c87-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="54c87-181">Si l’appareil est allumé, maintenez le bouton **d’alimentation** enfoncé jusqu’à ce qu’il s’éteigne complètement.</span><span class="sxs-lookup"><span data-stu-id="54c87-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="54c87-182">Maintenez le bouton **d’augmentation du volume**, puis appuyez brièvement sur le bouton **d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="54c87-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="54c87-183">L’appareil devrait démarrer et afficher uniquement le voyant du milieu.</span><span class="sxs-lookup"><span data-stu-id="54c87-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="54c87-184">Branchez l’appareil sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="54c87-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="54c87-185">Exécutez l’Outil récupération d’appareils Windows.</span><span class="sxs-lookup"><span data-stu-id="54c87-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="54c87-186">Sélectionnez **Mon appareil n’a pas été détecté** puis **Hololens**.</span><span class="sxs-lookup"><span data-stu-id="54c87-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="54c87-187">Suivez les instructions permettant de récupérer votre appareil.</span><span class="sxs-lookup"><span data-stu-id="54c87-187">Follow the instructions to recover your device.</span></span>
