---
title: Se connecter à des appareils Bluetooth et USB-C
description: Prise en main de la connexion aux appareils et accessoires Bluetooth et USB-C à partir de vos appareils HoloLens de réalité mixte.
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
ms.openlocfilehash: afbcfd0762bea9e7a6bc217d5e4a2910eaab7359
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283345"
---
# <span data-ttu-id="64dca-103">Se connecter à des appareils Bluetooth et USB-C</span><span class="sxs-lookup"><span data-stu-id="64dca-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="64dca-104">Les microphones externes ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="64dca-104">External microphones cannot be used.</span></span> <span data-ttu-id="64dca-105">HoloLens 2 utilise son [réseau de microphones](hololens2-hardware.md#audio-and-speech) intégré.</span><span class="sxs-lookup"><span data-stu-id="64dca-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="64dca-106">Appariement des appareils Bluetooth</span><span class="sxs-lookup"><span data-stu-id="64dca-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="64dca-107">HoloLens 2 prend en charge les classes suivantes d’appareils Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="64dca-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="64dca-108">Souris</span><span class="sxs-lookup"><span data-stu-id="64dca-108">Mouse</span></span>
- <span data-ttu-id="64dca-109">Clavier</span><span class="sxs-lookup"><span data-stu-id="64dca-109">Keyboard</span></span>
- <span data-ttu-id="64dca-110">Périphériques de sortie audio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="64dca-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="64dca-111">HoloLens (1ère génération) prend en charge les classes suivantes d’appareils Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="64dca-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="64dca-112">Souris</span><span class="sxs-lookup"><span data-stu-id="64dca-112">Mouse</span></span>
- <span data-ttu-id="64dca-113">Clavier</span><span class="sxs-lookup"><span data-stu-id="64dca-113">Keyboard</span></span>
- <span data-ttu-id="64dca-114">Cliquez sur HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="64dca-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="64dca-115">D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens.</span><span class="sxs-lookup"><span data-stu-id="64dca-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="64dca-116">Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="64dca-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="64dca-117">Pour plus d’informations, voir [Paramètres HoloLens répertorie les appareils disponibles, mais les appareils ne fonctionnent pas](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="64dca-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="64dca-118">Coupler un clavier ou une souris Bluetooth</span><span class="sxs-lookup"><span data-stu-id="64dca-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="64dca-119">Activez le clavier ou la souris, et rendez-la détectable.</span><span class="sxs-lookup"><span data-stu-id="64dca-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="64dca-120">Pour découvrir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou visitez le site Web du fabricant.</span><span class="sxs-lookup"><span data-stu-id="64dca-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="64dca-121">Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de départ (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="64dca-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="64dca-122">Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="64dca-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="64dca-123">Lorsque vous voyez le nom de l’appareil, sélectionnez **Paire**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="64dca-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="64dca-124">HoloLens (1ère génération): coupler le clic</span><span class="sxs-lookup"><span data-stu-id="64dca-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="64dca-125">Utilisez le geste «fleuri» pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="64dca-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="64dca-126">Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="64dca-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="64dca-127">Utilisez l’astuce d’un stylet pour appuyer sur le bouton d’appariement de la flèche et le maintenir enfoncé jusqu’à ce que le voyant de l’état du clic clignote.</span><span class="sxs-lookup"><span data-stu-id="64dca-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="64dca-128">Veillez à maintenir le bouton enfoncé jusqu’à ce que la lumière commence à clignoter.</span><span class="sxs-lookup"><span data-stu-id="64dca-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="64dca-129">Le bouton jumelage est placé sur le côté du clic, à côté de la boucle de doigt.</span><span class="sxs-lookup"><span data-stu-id="64dca-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![Le bouton d’appariement est en regard de la boucle de doigt.](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="64dca-131">Sur l'écran d’appairage, sélectionnez **Appairage** > **du dispositif de clic**.</span><span class="sxs-lookup"><span data-stu-id="64dca-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="64dca-132">Désactiver Bluetooth</span><span class="sxs-lookup"><span data-stu-id="64dca-132">Disable Bluetooth</span></span>

<span data-ttu-id="64dca-133">Cette procédure désactive les composants RF de la radio Bluetooth et désactive toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="64dca-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="64dca-134">Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de démarrage (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.</span><span class="sxs-lookup"><span data-stu-id="64dca-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="64dca-135">Déplacez le curseur de **Bluetooth** vers la position**Désactivée**.</span><span class="sxs-lookup"><span data-stu-id="64dca-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="64dca-136">HoloLens 2: connecter des appareils USB-C</span><span class="sxs-lookup"><span data-stu-id="64dca-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="64dca-137">HoloLens 2 prend en charge les classes suivantes d’appareils USB-C:</span><span class="sxs-lookup"><span data-stu-id="64dca-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="64dca-138">Périphériques de stockage de grande capacité (par exemple, lecteurs miniatures)</span><span class="sxs-lookup"><span data-stu-id="64dca-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="64dca-139">Cartes Ethernet (notamment la charge Ethernet plus)</span><span class="sxs-lookup"><span data-stu-id="64dca-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="64dca-140">Cartes audio numériques USB-C à 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="64dca-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="64dca-141">Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)</span><span class="sxs-lookup"><span data-stu-id="64dca-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="64dca-142">Souris filaire</span><span class="sxs-lookup"><span data-stu-id="64dca-142">Wired mouse</span></span>
- <span data-ttu-id="64dca-143">Clavier câblé</span><span class="sxs-lookup"><span data-stu-id="64dca-143">Wired keyboard</span></span>
- <span data-ttu-id="64dca-144">Combinaison de la combinaison de plusieurs moyeux (USB A plus débiter)</span><span class="sxs-lookup"><span data-stu-id="64dca-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="64dca-145">Certains appareils mobiles disposant de connexions USB-C se présentent eux-mêmes au contrôle HoloLens (adaptateurs Ethernet), et peuvent être utilisés dans une configuration de connexion, à commencer par Windows holographique (version 2004).</span><span class="sxs-lookup"><span data-stu-id="64dca-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="64dca-146">Les modems LTE USB qui requièrent un pilote distinct et/ou l’application installée pour la configuration ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="64dca-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="64dca-147">Suite aux commentaires des clients, nous avons activé une prise en charge limitée de la connectivité cellulaire directement dans le service HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="64dca-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="64dca-148">La connectivité par câble ne fonctionne que pour les appareils qui prennent en charge l'implémentation générique du pilote Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) et qui ne nécessitent pas l'installation d'autres pilotes ou applications.</span><span class="sxs-lookup"><span data-stu-id="64dca-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="64dca-149">Cet appareil, une fois connecté, s'affiche automatiquement sous la forme d'une nouvelle connexion Ethernet dans l'interface utilisateur des paramètres réseau HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="64dca-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="64dca-150">Pour plus d’informations sur la prise en charge du pilote Microsoft RNDIS générique, consultez le fabricant de votre appareil.</span><span class="sxs-lookup"><span data-stu-id="64dca-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

## <span data-ttu-id="64dca-151">Se connecter à Miracast</span><span class="sxs-lookup"><span data-stu-id="64dca-151">Connect to Miracast</span></span>

<span data-ttu-id="64dca-152">Pour utiliser Miracast, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="64dca-152">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="64dca-153">Effectuez l'une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="64dca-153">Do one of the following:</span></span>  

   - <span data-ttu-id="64dca-154">Ouvrez le menu **Démarrer**, puis sélectionnez l’icône Afficher.</span><span class="sxs-lookup"><span data-stu-id="64dca-154">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="64dca-155">Dites «se connecter» lorsque vous pointez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="64dca-155">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="64dca-156">Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.</span><span class="sxs-lookup"><span data-stu-id="64dca-156">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="64dca-157">Terminez l’appariement pour commencer la projection.</span><span class="sxs-lookup"><span data-stu-id="64dca-157">Complete the pairing to begin projecting.</span></span>
