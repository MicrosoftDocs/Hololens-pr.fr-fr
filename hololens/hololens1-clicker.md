---
title: Utiliser le dispositif de clic HoloLens
description: Cet article explique comment utiliser le dispositif de clic HoloLens, y compris l'appairage, le chargement et la récupération du dispositif de clic.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 13b86c049ba8bb6ed67be202609d27c8d47ffc53
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828510"
---
# <span data-ttu-id="81e18-104">Utiliser le dispositif de clic HoloLens (1regénération)</span><span class="sxs-lookup"><span data-stu-id="81e18-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="81e18-105">Le dispositif de clic a été conçu spécifiquement pour HoloLens (1ère génération) et vous donne un autre moyen d'interagir avec les hologrammes.</span><span class="sxs-lookup"><span data-stu-id="81e18-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="81e18-106">Il est livré avec HoloLens (1ère génération), dans une boîte séparée.</span><span class="sxs-lookup"><span data-stu-id="81e18-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="81e18-107">Utilisez-le à la place des gestes de la main pour sélectionner, faire défiler, déplacer et redimensionner les applications.</span><span class="sxs-lookup"><span data-stu-id="81e18-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <span data-ttu-id="81e18-108">Matériel et appairage du dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="81e18-109">Le dispositif de clic HoloLens (1ère génération) est doté d'une boucle de doigt pour faciliter la prise en main et d'un voyant lumineux.

</span><span class="sxs-lookup"><span data-stu-id="81e18-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![Le dispositif de clic HoloLens](images/use-hololens-clicker-1.png)

### <span data-ttu-id="81e18-111">Voyants lumineux du dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-111">Clicker indicator lights</span></span>

<span data-ttu-id="81e18-112">Voici ce que signifient les lumières sur le dispositif de clic.</span><span class="sxs-lookup"><span data-stu-id="81e18-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="81e18-113">**Blanc clignotant**.</span><span class="sxs-lookup"><span data-stu-id="81e18-113">**Blinking white**.</span></span> <span data-ttu-id="81e18-114">Le dispositif de clic est en mode d'appairage.</span><span class="sxs-lookup"><span data-stu-id="81e18-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="81e18-115">**Blanc clignotant rapide**.</span><span class="sxs-lookup"><span data-stu-id="81e18-115">**Fast-blinking white**.</span></span> <span data-ttu-id="81e18-116">L’appairage s’est effectué avec succès.</span><span class="sxs-lookup"><span data-stu-id="81e18-116">Pairing was successful.</span></span>
- <span data-ttu-id="81e18-117">**Blanc solide**.</span><span class="sxs-lookup"><span data-stu-id="81e18-117">**Solid white**.</span></span> <span data-ttu-id="81e18-118">Le dispositif de clic est en train de charger.</span><span class="sxs-lookup"><span data-stu-id="81e18-118">The clicker is charging.</span></span>
- <span data-ttu-id="81e18-119">**L'ambre clignotant**.</span><span class="sxs-lookup"><span data-stu-id="81e18-119">**Blinking amber**.</span></span> <span data-ttu-id="81e18-120">La batterie est faible.</span><span class="sxs-lookup"><span data-stu-id="81e18-120">The battery is low.</span></span>
- <span data-ttu-id="81e18-121">**Ambre solide**.</span><span class="sxs-lookup"><span data-stu-id="81e18-121">**Solid amber**.</span></span> <span data-ttu-id="81e18-122">Le dispositif de clic a rencontré une erreur et vous devrez le redémarrer.</span><span class="sxs-lookup"><span data-stu-id="81e18-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="81e18-123">Tout en appuyant sur le bouton appairage, cliquez et maintenez-le ainsi pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="81e18-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <span data-ttu-id="81e18-124">Associez le dispositif de clic à votre HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="81e18-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="81e18-125">Utilisez le mouvement « fleuri » pour aller à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils** et vérifier que le Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="81e18-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="81e18-126">Sur le dispositif de clic, appuyez et maintenez le bouton d'appairage jusqu'à ce que la lumière d'état clignote en blanc.</span><span class="sxs-lookup"><span data-stu-id="81e18-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="81e18-127">Sur l'écran d’appairage, sélectionnez **Appairage** > **du dispositif de clic**.</span><span class="sxs-lookup"><span data-stu-id="81e18-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <span data-ttu-id="81e18-128">Chargez le dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-128">Charge the clicker</span></span>

<span data-ttu-id="81e18-129">Lorsque la pile du dispositif de clic est faible, le voyant de la pile clignote en ambre.</span><span class="sxs-lookup"><span data-stu-id="81e18-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="81e18-130">Branchez le câble Micro USB à une alimentation USB pour charger l'appareil.</span><span class="sxs-lookup"><span data-stu-id="81e18-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <span data-ttu-id="81e18-131">Utiliser le dispositif de clic avec HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="81e18-131">Use the clicker with HoloLens (1st gen)</span></span>

### <span data-ttu-id="81e18-132">Maintenir le dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-132">Hold the clicker</span></span>

<span data-ttu-id="81e18-133">Pour mettre le dispositif de clic, faites glisser la boucle sur votre bague ou votre majeur de façon à ce que le port Micro USB soit orienté vers votre poignet.</span><span class="sxs-lookup"><span data-stu-id="81e18-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="81e18-134">Reposez votre pouce dans le renfoncement.</span><span class="sxs-lookup"><span data-stu-id="81e18-134">Rest your thumb in the indentation.</span></span>

![Comment tenir le dispositif de clic](images/use-hololens-clicker-2.png)

### <span data-ttu-id="81e18-136">Mouvements du dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-136">Clicker gestures</span></span>

<span data-ttu-id="81e18-137">Les mouvements du dispositif de clic sont de petites rotations du poignet, et non les grands mouvements utilisés pour les mouvements de la main de l'HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81e18-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="81e18-138">Et HoloLens reconnaît vos mouvements et clics, même si celui-ci se trouve en dehors du [cadre de mouvement](hololens1-basic-usage.md), afin que vous puissiez maintenir le clic dans la position qui vous convient le mieux.</span><span class="sxs-lookup"><span data-stu-id="81e18-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="81e18-139">**Sélectionnez**.</span><span class="sxs-lookup"><span data-stu-id="81e18-139">**Select**.</span></span> <span data-ttu-id="81e18-140">Pour sélectionner un hologramme, un bouton ou un autre élément, fixez-le, puis cliquez.</span><span class="sxs-lookup"><span data-stu-id="81e18-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="81e18-141">**Cliquer et maintenir**.</span><span class="sxs-lookup"><span data-stu-id="81e18-141">**Click and hold**.</span></span> <span data-ttu-id="81e18-142">Cliquez et maintenez votre pouce sur le bouton pour faire certaines des mêmes choses que vous feriez en le maintenant appuyé, comme déplacer ou redimensionner un hologramme.</span><span class="sxs-lookup"><span data-stu-id="81e18-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="81e18-143">**Faire défiler**.</span><span class="sxs-lookup"><span data-stu-id="81e18-143">**Scroll**.</span></span> <span data-ttu-id="81e18-144">Sur la barre d'application, sélectionnez **Outil de défilement**.</span><span class="sxs-lookup"><span data-stu-id="81e18-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="81e18-145">Cliquez et maintenez appuyé, puis faites pivoter le dispositif de clic vers le haut, le bas, la gauche ou la droite.</span><span class="sxs-lookup"><span data-stu-id="81e18-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="81e18-146">Pour faire défiler plus rapidement, éloignez votre main du centre de l'outil de défilement.</span><span class="sxs-lookup"><span data-stu-id="81e18-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="81e18-147">**Zoom**.</span><span class="sxs-lookup"><span data-stu-id="81e18-147">**Zoom**.</span></span> <span data-ttu-id="81e18-148">Sur la barre d'application, sélectionnez **Outil de zoom**.</span><span class="sxs-lookup"><span data-stu-id="81e18-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="81e18-149">Cliquez et maintenez le bouton appuyé, puis faites pivoter le dispositif de clic vers le haut pour effectuer un zoom avant, ou vers le bas pour effectuer un zoom arrière.</span><span class="sxs-lookup"><span data-stu-id="81e18-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="81e18-150">Pour effectuer un zoom avant ou arrière lorsque vous utilisez Microsoft Edge, regardez une page et double-cliquez.</span><span class="sxs-lookup"><span data-stu-id="81e18-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <span data-ttu-id="81e18-151">Redémarrer ou récupérer le dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-151">Restart or recover the clicker</span></span>

<span data-ttu-id="81e18-152">Voici quelques éléments à essayer si le dispositif de clic HoloLens ne répond pas ou ne fonctionne pas bien.</span><span class="sxs-lookup"><span data-stu-id="81e18-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <span data-ttu-id="81e18-153">Redémarrer le dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-153">Restart the clicker</span></span>

<span data-ttu-id="81e18-154">Utilisez la pointe d'un stylo pour appuyer et maintenir le bouton d'appairage.</span><span class="sxs-lookup"><span data-stu-id="81e18-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="81e18-155">Dans le même temps, cliquez et maintenez le dispositif de clic pendant 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="81e18-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="81e18-156">Si le dispositif de clic était déjà connecté à votre HoloLens, il le restera après son redémarrage.</span><span class="sxs-lookup"><span data-stu-id="81e18-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="81e18-157">Si le dispositif de clic ne s'allume pas ou ne redémarre pas, essayez de le recharger en utilisant le chargeur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81e18-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="81e18-158">Si la batterie est très faible, l’activation du voyant lumineux blanc peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="81e18-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <span data-ttu-id="81e18-159">Repairer le dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-159">Re-pair the clicker</span></span>

<span data-ttu-id="81e18-160">Sélectionnez **Paramètres** > **Appareils**, puis sélectionnez le dispositif de clic.</span><span class="sxs-lookup"><span data-stu-id="81e18-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="81e18-161">Sélectionnez **Supprimer**, patientez quelques secondes, puis repairez le dispositif ce clic.</span><span class="sxs-lookup"><span data-stu-id="81e18-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <span data-ttu-id="81e18-162">Récupérer le dispositif de clic</span><span class="sxs-lookup"><span data-stu-id="81e18-162">Recover the clicker</span></span>

<span data-ttu-id="81e18-163">Si le redémarrage et la ré-appairage du dispositif de clic ne résolvent pas le problème, l’outil de récupération des périphériques Windows peut vous aider à le récupérer.</span><span class="sxs-lookup"><span data-stu-id="81e18-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="81e18-164">Le processus de récupération peut prendre un certain temps et il installera la dernière version du logiciel du dispositif de clic.</span><span class="sxs-lookup"><span data-stu-id="81e18-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="81e18-165">Pour utiliser l’outil, vous avez besoin d'un ordinateur équipé de Windows 10 ou d'une version ultérieure et disposant d'au moins 4 Go d’espace de stockage disponible.</span><span class="sxs-lookup"><span data-stu-id="81e18-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="81e18-166">Pour récupérer le dispositif de clic :</span><span class="sxs-lookup"><span data-stu-id="81e18-166">To recover the clicker:</span></span>

1. <span data-ttu-id="81e18-167">Téléchargez et installez [Outil de récupération des périphériques Windows](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="81e18-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="81e18-168">Connectez le dispositif de clic à votre ordinateur en utilisant le câble Micro USB fourni avec votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81e18-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="81e18-169">Exécutez l’outil de récupération des périphériques Windows et suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="81e18-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="81e18-170">Si le dispositif de clic n’est pas détecté automatiquement, sélectionnez **Mon appareil n’a pas été détecté** et suivez les instructions pour passer en mode de récupération.</span><span class="sxs-lookup"><span data-stu-id="81e18-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
