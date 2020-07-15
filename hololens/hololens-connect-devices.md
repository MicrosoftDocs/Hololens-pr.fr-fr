---
title: Se connecter à des appareils Bluetooth et USB-C
description: Ce guide vous guide dans la connexion à des appareils Bluetooth et périphériques USB-C.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881244"
---
# <span data-ttu-id="bbcce-103">Se connecter à des appareils Bluetooth et USB-C</span><span class="sxs-lookup"><span data-stu-id="bbcce-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="bbcce-104">Appariement des appareils Bluetooth</span><span class="sxs-lookup"><span data-stu-id="bbcce-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="bbcce-105">HoloLens 2 prend en charge les classes suivantes d’appareils Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="bbcce-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="bbcce-106">Souris</span><span class="sxs-lookup"><span data-stu-id="bbcce-106">Mouse</span></span>
- <span data-ttu-id="bbcce-107">Clavier</span><span class="sxs-lookup"><span data-stu-id="bbcce-107">Keyboard</span></span>
- <span data-ttu-id="bbcce-108">Périphériques de sortie audio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="bbcce-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="bbcce-109">Les microphones externes ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="bbcce-109">External microphones cannot be used.</span></span> <span data-ttu-id="bbcce-110">HoloLens 2 utilise son [réseau de microphones](hololens2-hardware.md#audio-and-speech) intégré.</span><span class="sxs-lookup"><span data-stu-id="bbcce-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="bbcce-111">HoloLens (1ère génération) prend en charge les classes suivantes d’appareils Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="bbcce-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="bbcce-112">Souris</span><span class="sxs-lookup"><span data-stu-id="bbcce-112">Mouse</span></span>
- <span data-ttu-id="bbcce-113">Clavier</span><span class="sxs-lookup"><span data-stu-id="bbcce-113">Keyboard</span></span>
- <span data-ttu-id="bbcce-114">Cliquez sur HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="bbcce-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="bbcce-115">D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bbcce-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="bbcce-116">Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="bbcce-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="bbcce-117">Pour plus d’informations, voir [Paramètres HoloLens répertorie les appareils disponibles, mais les appareils ne fonctionnent pas](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="bbcce-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="bbcce-118">Coupler un clavier ou une souris Bluetooth</span><span class="sxs-lookup"><span data-stu-id="bbcce-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="bbcce-119">Activez le clavier ou la souris, et rendez-la détectable.</span><span class="sxs-lookup"><span data-stu-id="bbcce-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="bbcce-120">Pour découvrir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou visitez le site Web du fabricant.</span><span class="sxs-lookup"><span data-stu-id="bbcce-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="bbcce-121">Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de départ (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="bbcce-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="bbcce-122">Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="bbcce-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="bbcce-123">Lorsque vous voyez le nom de l’appareil, sélectionnez **Paire**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="bbcce-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="bbcce-124">HoloLens (1ère génération): coupler le clic</span><span class="sxs-lookup"><span data-stu-id="bbcce-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="bbcce-125">Utilisez le geste «fleuri» pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="bbcce-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="bbcce-126">Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="bbcce-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="bbcce-127">Utilisez l’astuce d’un stylet pour appuyer sur le bouton d’appariement de la flèche et le maintenir enfoncé jusqu’à ce que le voyant de l’état du clic clignote.</span><span class="sxs-lookup"><span data-stu-id="bbcce-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="bbcce-128">Veillez à maintenir le bouton enfoncé jusqu’à ce que la lumière commence à clignoter.</span><span class="sxs-lookup"><span data-stu-id="bbcce-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="bbcce-129">Le bouton jumelage est placé sur le côté du clic, à côté de la boucle de doigt.</span><span class="sxs-lookup"><span data-stu-id="bbcce-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![Le bouton d’appariement est en regard de la boucle de doigt.](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="bbcce-131">Sur l'écran d’appairage, sélectionnez **Appairage** > **du dispositif de clic**.</span><span class="sxs-lookup"><span data-stu-id="bbcce-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="bbcce-132">HoloLens 2: connecter des appareils USB-C</span><span class="sxs-lookup"><span data-stu-id="bbcce-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="bbcce-133">HoloLens 2 prend en charge les classes suivantes d’appareils USB-C:</span><span class="sxs-lookup"><span data-stu-id="bbcce-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="bbcce-134">Périphériques de stockage de grande capacité (par exemple, lecteurs miniatures)</span><span class="sxs-lookup"><span data-stu-id="bbcce-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="bbcce-135">Cartes Ethernet (notamment la charge Ethernet plus)</span><span class="sxs-lookup"><span data-stu-id="bbcce-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="bbcce-136">Cartes audio numériques USB-C à 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="bbcce-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="bbcce-137">Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)</span><span class="sxs-lookup"><span data-stu-id="bbcce-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="bbcce-138">Souris filaire</span><span class="sxs-lookup"><span data-stu-id="bbcce-138">Wired mouse</span></span>
- <span data-ttu-id="bbcce-139">Clavier câblé</span><span class="sxs-lookup"><span data-stu-id="bbcce-139">Wired keyboard</span></span>
- <span data-ttu-id="bbcce-140">Combinaison de la combinaison de plusieurs moyeux (USB A plus débiter)</span><span class="sxs-lookup"><span data-stu-id="bbcce-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="bbcce-141">Certains appareils mobiles disposant de connexions USB-C se présentent eux-mêmes au contrôle HoloLens (adaptateurs Ethernet), et peuvent être utilisés dans une configuration de connexion, à commencer par Windows holographique (version 2004).</span><span class="sxs-lookup"><span data-stu-id="bbcce-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="bbcce-142">Les modems LTE USB qui requièrent un pilote distinct et/ou l’application installée pour la configuration ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bbcce-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="bbcce-143">Se connecter à Miracast</span><span class="sxs-lookup"><span data-stu-id="bbcce-143">Connect to Miracast</span></span>

<span data-ttu-id="bbcce-144">Pour utiliser Miracast, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="bbcce-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="bbcce-145">Effectuez l'une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="bbcce-145">Do one of the following:</span></span>  

   - <span data-ttu-id="bbcce-146">Ouvrez le menu **Démarrer**, puis sélectionnez l’icône Afficher.</span><span class="sxs-lookup"><span data-stu-id="bbcce-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="bbcce-147">Dites «se connecter» lorsque vous pointez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="bbcce-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="bbcce-148">Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.</span><span class="sxs-lookup"><span data-stu-id="bbcce-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="bbcce-149">Terminez l’appariement pour commencer la projection.</span><span class="sxs-lookup"><span data-stu-id="bbcce-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="bbcce-150">Désactiver Bluetooth</span><span class="sxs-lookup"><span data-stu-id="bbcce-150">Disable Bluetooth</span></span>

<span data-ttu-id="bbcce-151">Cette procédure désactive les composants RF de la radio Bluetooth et désactive toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bbcce-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="bbcce-152">Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de démarrage (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.</span><span class="sxs-lookup"><span data-stu-id="bbcce-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="bbcce-153">Déplacez le curseur de **Bluetooth** vers la position**Désactivée**.</span><span class="sxs-lookup"><span data-stu-id="bbcce-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
