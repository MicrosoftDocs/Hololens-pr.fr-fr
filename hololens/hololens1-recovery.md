---
title: Redémarrer, réinitialiser ou récupérer HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 36192315e234db16c7747457e69d6d6281c31bfe
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857732"
---
# <span data-ttu-id="0974e-104">Redémarrer, réinitialiser ou récupérer HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="0974e-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="0974e-105">Si vous rencontrez des problèmes avec votre HoloLens, vous souhaiterez peut-être essayer d’effectuer un redémarrage, de réinitialiser ou même de relancer la récupération des appareils.</span><span class="sxs-lookup"><span data-stu-id="0974e-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="0974e-106">Voici quelques solutions à essayer si votre service HoloLens ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="0974e-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="0974e-107">Cet article vous guide dans les étapes de récupération recommandées successivement.</span><span class="sxs-lookup"><span data-stu-id="0974e-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="0974e-108">Si vous cherchez à récupérer un contrôle HoloLens 2, consultez la page de [Récupération d’unHoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), car les processus présentent des différences.</span><span class="sxs-lookup"><span data-stu-id="0974e-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="0974e-109">Cet article se concentre sur l’appareil et les logiciels HoloLens, si vos hologrammes ne s’affichent pas correctement, [cet article](hololens-environment-considerations.md) parle de facteurs environnementaux qui améliorent la qualité de l’hologramme.</span><span class="sxs-lookup"><span data-stu-id="0974e-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="0974e-110">Redémarrer</span><span class="sxs-lookup"><span data-stu-id="0974e-110">Restart</span></span>

### <span data-ttu-id="0974e-111">Effectuer un redémarrage en toute sécurité à l’aide de Cortana</span><span class="sxs-lookup"><span data-stu-id="0974e-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="0974e-112">Le moyen le plus sûr de redémarrer le HoloLens consiste à utiliser Cortana.</span><span class="sxs-lookup"><span data-stu-id="0974e-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="0974e-113">Il s’agit généralement d’une première étape facile pour rencontrer un problème avec HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0974e-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="0974e-114">Cortana n’est pas disponible sur tous les appareils.</span><span class="sxs-lookup"><span data-stu-id="0974e-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="0974e-115">Cortana est disponible à tous les appareils HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="0974e-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="0974e-116">Cortana est disponible sur les appareils HoloLens 2 sur une version antérieure à la mise à jour de la version 2004 de Windows.</span><span class="sxs-lookup"><span data-stu-id="0974e-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="0974e-117">Placer sur votre appareil</span><span class="sxs-lookup"><span data-stu-id="0974e-117">Put on your device</span></span>
1. <span data-ttu-id="0974e-118">Assurez-vous qu’il est alimenté, qu’un utilisateur est connecté et que l’appareil n’attend pas de mot de passe pour le déverrouiller.</span><span class="sxs-lookup"><span data-stu-id="0974e-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="0974e-119">Dites «Hey Cortana, redémarrez» ou «Hey Cortana, redémarrez».</span><span class="sxs-lookup"><span data-stu-id="0974e-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="0974e-120">Lorsqu’elle reconnaît, elle vous demandera de confirmer votre choix.</span><span class="sxs-lookup"><span data-stu-id="0974e-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="0974e-121">Patientez pendant la lecture d’un signal sonore une fois qu’il a terminé sa question, indiquant qu’il vous écoute et dites «oui».</span><span class="sxs-lookup"><span data-stu-id="0974e-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="0974e-122">L’appareil redémarre maintenant.</span><span class="sxs-lookup"><span data-stu-id="0974e-122">The device will now restart.</span></span>

### <span data-ttu-id="0974e-123">Effectuer un redémarrage en toute sécurité à l’aide du bouton arrêter l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="0974e-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="0974e-124">Si vous ne parvenez pas à redémarrer votre appareil, vous pouvez essayer de le redémarrer à l’aide du bouton arrêter l’ordinateur:</span><span class="sxs-lookup"><span data-stu-id="0974e-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="0974e-125">Appuyez de façon prolongée sur le bouton de mise sous tension pendant cinq secondes.</span><span class="sxs-lookup"><span data-stu-id="0974e-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="0974e-126">Après une seconde, les cinq voyants s’allument, puis s’éteignent lentement de droite à gauche.</span><span class="sxs-lookup"><span data-stu-id="0974e-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="0974e-127">Après cinq secondes, tous les voyants sont désactivés, indiquant que la commande d’arrêt a été correctement émise.</span><span class="sxs-lookup"><span data-stu-id="0974e-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="0974e-128">Notez qu’il est important de ne pas appuyer sur le bouton immédiatement après que tous les voyants ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="0974e-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="0974e-129">Patientez une minute pour que l’arrêt aboutisse correctement.</span><span class="sxs-lookup"><span data-stu-id="0974e-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="0974e-130">Notez que l’arrêt peut être encore en cours, même si les affichages sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="0974e-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="0974e-131">Rallumez l’appareil en appuyant sur le bouton de mise sous tension pendant une seconde.</span><span class="sxs-lookup"><span data-stu-id="0974e-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="0974e-132">Effectuer un redémarrage en toute sécurité à l’aide du portail d’appareils Windows</span><span class="sxs-lookup"><span data-stu-id="0974e-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="0974e-133">Pour ce faire, HoloLens doit être configuré en tant qu’appareil développeur.</span><span class="sxs-lookup"><span data-stu-id="0974e-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="0974e-134">En savoir plus sur le [Portail d’appareils de Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="0974e-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="0974e-135">Si la procédure précédente ne fonctionne pas, vous pouvez essayer de redémarrer l’appareil à l’aide du [Portail d’appareils de Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="0974e-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="0974e-136">Dans le coin supérieur droit, vous pouvez redémarrer ou arrêter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="0974e-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="0974e-137">Effectuer un redémarrage forcé non sécurisé</span><span class="sxs-lookup"><span data-stu-id="0974e-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="0974e-138">Si aucune des méthodes précédentes ne peut redémarrer votre appareil, vous pouvez forcer un redémarrage.</span><span class="sxs-lookup"><span data-stu-id="0974e-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="0974e-139">Cette méthode revient à tirer la batterie de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0974e-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="0974e-140">Il s’agit d’une opération dangereuse qui peut rendre votre appareil endommagé.</span><span class="sxs-lookup"><span data-stu-id="0974e-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="0974e-141">Dans ce cas, vous devez flasher votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0974e-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="0974e-142">Il s’agit d’une méthode potentiellement nuisible qui ne doit être utilisée que dans le cas où aucune des méthodes ci-dessus ne fonctionne.</span><span class="sxs-lookup"><span data-stu-id="0974e-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="0974e-143">Appuyez de façon prolongée sur le bouton de mise sous tension pendant au moins 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="0974e-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="0974e-144">Il est possible de maintenir le bouton enfoncé pendant plus de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="0974e-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="0974e-145">Il est possible d’ignorer toute activité LED.</span><span class="sxs-lookup"><span data-stu-id="0974e-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="0974e-146">Relâchez le bouton et attendez deux ou trois secondes.</span><span class="sxs-lookup"><span data-stu-id="0974e-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="0974e-147">Rallumez l’appareil en appuyant sur le bouton de mise sous tension pendant une seconde.</span><span class="sxs-lookup"><span data-stu-id="0974e-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="0974e-148">Si vous rencontrez toujours des problèmes, appuyez sur le bouton de mise sous tension pendant 4 secondes, jusqu’à ce que tous les indicateurs de batterie disparaisse et que l’écran cesse d’afficher les hologrammes.</span><span class="sxs-lookup"><span data-stu-id="0974e-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="0974e-149">Patientez 1 minute, puis appuyez de nouveau sur le bouton Power pour allumer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="0974e-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="0974e-150">Rétablir les paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="0974e-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="0974e-151">La batterie nécessite au moins 40% de charge pour la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="0974e-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="0974e-152">Si vous rencontrez encore des problèmes après avoir redémarré votre HoloLens, essayez de le réinitialiser à l’état d’origine.</span><span class="sxs-lookup"><span data-stu-id="0974e-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="0974e-153">La réinitialisation de votre contrôle HoloLens conserve la version du logiciel Windows holographique qui est installé dessus et renvoie tous les autres paramètres aux paramètres d’usine.</span><span class="sxs-lookup"><span data-stu-id="0974e-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="0974e-154">Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels sont supprimés, y compris la réinitialisation du TPM.</span><span class="sxs-lookup"><span data-stu-id="0974e-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="0974e-155">La réinitialisation de n’installera que la dernière version de Windows holographique. vous devrez rétablir toutes les étapes d’initialisation (étalonner, connecter à Wi-Fi, créer un compte d’utilisateur, télécharger des applications, etc.).</span><span class="sxs-lookup"><span data-stu-id="0974e-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="0974e-156">Lancez l’application paramètres, puis sélectionnez **Mise à jour** > **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="0974e-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="0974e-157">Sélectionnez l’option **Réinitialiser l’appareil** et lisez le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="0974e-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="0974e-158">Si vous acceptez de réinitialiser votre appareil, l’appareil redémarre et affiche un série de rapports tournants avec une barre de progression.</span><span class="sxs-lookup"><span data-stu-id="0974e-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="0974e-159">Patientez environ 30 minutes l’exécution de ce processus.</span><span class="sxs-lookup"><span data-stu-id="0974e-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="0974e-160">La réinitialisation se termine et l’appareil redémarre dans le cadre de l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="0974e-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="0974e-161">Réinstaller le système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="0974e-161">Re-install the operating system</span></span>

<span data-ttu-id="0974e-162">Si le problème persiste après le redémarrage et la réinitialisation de l’appareil, vous pouvez utiliser un outil de récupération sur votre ordinateur pour réinstaller le système d’exploitation et le microprogramme HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0974e-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="0974e-163">La réinitialisation de tous les données de HoloLens est incluse dans une mise à jour Flash complète (FFU).</span><span class="sxs-lookup"><span data-stu-id="0974e-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="0974e-164">Il s’agit du même type que les normes ISO, Wim et VHD.</span><span class="sxs-lookup"><span data-stu-id="0974e-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="0974e-165">En savoir plus sur les formats de fichier image FFU.</span><span class="sxs-lookup"><span data-stu-id="0974e-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="0974e-166">Si nécessaire, vous pouvez installer un système d’exploitation totalement nouveau sur votre HoloLens (1ère génération) à l’aide de l’outil de récupération d’appareils Windows.</span><span class="sxs-lookup"><span data-stu-id="0974e-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="0974e-167">Avant d’utiliser cet outil, déterminez si le redémarrage ou la réinitialisation de votre outil HoloLens permet de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="0974e-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="0974e-168">Le processus de récupération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="0974e-168">The recovery process may take some time.</span></span>  <span data-ttu-id="0974e-169">Lorsque vous avez terminé, la dernière version du logiciel Windows holographique approuvée pour votre HoloLens sera installée.</span><span class="sxs-lookup"><span data-stu-id="0974e-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="0974e-170">Pour utiliser l’outil, vous avez besoin d’un ordinateur exécutant Windows 10 ou version ultérieure, avec au moins 4 Go d’espace de stockage disponible.</span><span class="sxs-lookup"><span data-stu-id="0974e-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="0974e-171">Notez que vous ne pouvez pas exécuter cet outil sur une machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="0974e-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="0974e-172">Récupérer votre HoloLens:</span><span class="sxs-lookup"><span data-stu-id="0974e-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="0974e-173">Téléchargez et installez [Windows Device Recovery Tool sur votre ordinateur](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).</span><span class="sxs-lookup"><span data-stu-id="0974e-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="0974e-174">Connectez HoloLens (1ère génération) à votre ordinateur à l’aide du câble USB fourni avec votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0974e-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="0974e-175">Exécutez l’outil récupération d’appareils Windows et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="0974e-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="0974e-176">Si le système HoloLens (1ère génération) n’est pas détecté automatiquement, sélectionnez **Mon appareil n’a pas été détecté** et suivez les instructions pour passer en mode de récupération.</span><span class="sxs-lookup"><span data-stu-id="0974e-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="0974e-177">Mode clignotant manuel:</span><span class="sxs-lookup"><span data-stu-id="0974e-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="0974e-178">Dans le cas où votre appareil n’est pas détecté, veuillez utiliser la méthode suivante pour le placer manuellement en mode clignotant.</span><span class="sxs-lookup"><span data-stu-id="0974e-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="0974e-179">Débranchez l’appareil de toutes les sources d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="0974e-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="0974e-180">Si l’appareil est allumé, maintenez le bouton Power enfoncé jusqu’à ce qu’il soit complètement désactivé.</span><span class="sxs-lookup"><span data-stu-id="0974e-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="0974e-181">Maintenez le bouton **Monter le volume**, puis appuyez sur le **bouton Alimentation**.</span><span class="sxs-lookup"><span data-stu-id="0974e-181">Hold the **Volume Up** button, and breifly tap the **Power button**.</span></span> 
1. <span data-ttu-id="0974e-182">L’appareil doit être amorcé et afficher uniquement le voyant du milieu.</span><span class="sxs-lookup"><span data-stu-id="0974e-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="0974e-183">Branchez l’appareil sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="0974e-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="0974e-184">Lancez l’outil récupération des appareils Windows.</span><span class="sxs-lookup"><span data-stu-id="0974e-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="0974e-185">Vous devrez sélectionner \* mon appareil n’a pas été détecté \* \*, puis sélectionner **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="0974e-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="0974e-186">Suivez les instructions permettant de récupérer votre appareil.</span><span class="sxs-lookup"><span data-stu-id="0974e-186">Follow the instructions to recover your device.</span></span>
