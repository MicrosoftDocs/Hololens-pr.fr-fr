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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385489"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="8b21c-103">Se connecter à des appareils Bluetooth et USB-C</span><span class="sxs-lookup"><span data-stu-id="8b21c-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="8b21c-104">Les microphones externes ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="8b21c-104">External microphones cannot be used.</span></span> <span data-ttu-id="8b21c-105">HoloLens 2 utilise son [réseau de microphones](hololens2-hardware.md#audio-and-speech) intégré.</span><span class="sxs-lookup"><span data-stu-id="8b21c-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="8b21c-106">Appariement des appareils Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8b21c-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="8b21c-107">HoloLens 2 prend en charge les classes suivantes d’appareils Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="8b21c-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="8b21c-108">Souris</span><span class="sxs-lookup"><span data-stu-id="8b21c-108">Mouse</span></span>
- <span data-ttu-id="8b21c-109">Clavier</span><span class="sxs-lookup"><span data-stu-id="8b21c-109">Keyboard</span></span>
- <span data-ttu-id="8b21c-110">Périphériques de sortie audio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="8b21c-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="8b21c-111">HoloLens (1ère génération) prend en charge les classes suivantes d’appareils Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="8b21c-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="8b21c-112">Souris</span><span class="sxs-lookup"><span data-stu-id="8b21c-112">Mouse</span></span>
- <span data-ttu-id="8b21c-113">Clavier</span><span class="sxs-lookup"><span data-stu-id="8b21c-113">Keyboard</span></span>
- [<span data-ttu-id="8b21c-114">Cliquez sur HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="8b21c-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="8b21c-115">D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8b21c-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="8b21c-116">Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="8b21c-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="8b21c-117">Pour plus d’informations, voir [Paramètres HoloLens répertorie les appareils disponibles, mais les appareils ne fonctionnent pas](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="8b21c-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="8b21c-118">Coupler un clavier ou une souris Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8b21c-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="8b21c-119">Activez le clavier ou la souris, et rendez-la détectable.</span><span class="sxs-lookup"><span data-stu-id="8b21c-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="8b21c-120">Pour découvrir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou visitez le site Web du fabricant.</span><span class="sxs-lookup"><span data-stu-id="8b21c-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="8b21c-121">Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de départ (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="8b21c-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="8b21c-122">Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="8b21c-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="8b21c-123">Lorsque vous voyez le nom de l’appareil, sélectionnez **Paire**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="8b21c-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="8b21c-124">Désactiver Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8b21c-124">Disable Bluetooth</span></span>

<span data-ttu-id="8b21c-125">Cette procédure désactive les composants RF de la radio Bluetooth et désactive toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8b21c-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="8b21c-126">Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de démarrage (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.</span><span class="sxs-lookup"><span data-stu-id="8b21c-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="8b21c-127">Déplacez le curseur de **Bluetooth** vers la position**Désactivée**.</span><span class="sxs-lookup"><span data-stu-id="8b21c-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="8b21c-128">HoloLens 2: connecter des appareils USB-C</span><span class="sxs-lookup"><span data-stu-id="8b21c-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="8b21c-129">HoloLens 2 prend en charge les classes suivantes d’appareils USB-C:</span><span class="sxs-lookup"><span data-stu-id="8b21c-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="8b21c-130">Périphériques de stockage de grande capacité (par exemple, lecteurs miniatures)</span><span class="sxs-lookup"><span data-stu-id="8b21c-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="8b21c-131">Cartes Ethernet (notamment la charge Ethernet plus)</span><span class="sxs-lookup"><span data-stu-id="8b21c-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="8b21c-132">Cartes audio numériques USB-C à 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="8b21c-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="8b21c-133">Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)</span><span class="sxs-lookup"><span data-stu-id="8b21c-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="8b21c-134">Souris filaire</span><span class="sxs-lookup"><span data-stu-id="8b21c-134">Wired mouse</span></span>
- <span data-ttu-id="8b21c-135">Clavier câblé</span><span class="sxs-lookup"><span data-stu-id="8b21c-135">Wired keyboard</span></span>
- <span data-ttu-id="8b21c-136">Combinaison de la combinaison de plusieurs moyeux (USB A plus débiter)</span><span class="sxs-lookup"><span data-stu-id="8b21c-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="8b21c-137">En réponse aux commentaires des clients, nous avons activé une prise en charge limitée de la connectivité cellulaire directement liée à HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="8b21c-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="8b21c-138">Consultez [Connexion au cellulaire et à la 5G](hololens-cellular.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="8b21c-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="8b21c-139">Hubs USB-C</span><span class="sxs-lookup"><span data-stu-id="8b21c-139">USB-C Hubs</span></span>

<span data-ttu-id="8b21c-140">Certains utilisateurs peuvent avoir besoin de connecter plusieurs appareils à la fois.</span><span class="sxs-lookup"><span data-stu-id="8b21c-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="8b21c-141">Pour les utilisateurs qui souhaitent avoir un aperçu d'une fonction Insider et[ utiliser un microphone USB-C avec ](hololens-insider.md#usb-c-external-microphone-support)un autre appareil connecté, les concentrateurs USB-C peuvent répondre au besoin du client.</span><span class="sxs-lookup"><span data-stu-id="8b21c-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="8b21c-142">Microsoft n'a pas testé ces appareils, et nous ne pouvons recommander aucune marque spécifique.</span><span class="sxs-lookup"><span data-stu-id="8b21c-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="8b21c-143">Exigences pour les concentrateurs USB-C et les appareils connectés :</span><span class="sxs-lookup"><span data-stu-id="8b21c-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="8b21c-144">Les appareils connectés ne doivent pas nécessiter l'installation d'un pilote.</span><span class="sxs-lookup"><span data-stu-id="8b21c-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="8b21c-145">La puissance totale absorbée de tous les appareils connectés doit être inférieure à 4,5 watts.</span><span class="sxs-lookup"><span data-stu-id="8b21c-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="8b21c-146">Se connecter à Miracast</span><span class="sxs-lookup"><span data-stu-id="8b21c-146">Connect to Miracast</span></span>

<span data-ttu-id="8b21c-147">Pour utiliser Miracast, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="8b21c-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="8b21c-148">Effectuez l'une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="8b21c-148">Do one of the following:</span></span>  

   - <span data-ttu-id="8b21c-149">Ouvrez le menu **Démarrer**, puis sélectionnez l’icône Afficher.</span><span class="sxs-lookup"><span data-stu-id="8b21c-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="8b21c-150">Dites «se connecter» lorsque vous pointez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="8b21c-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="8b21c-151">Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.</span><span class="sxs-lookup"><span data-stu-id="8b21c-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="8b21c-152">Terminez l’appariement pour commencer la projection.</span><span class="sxs-lookup"><span data-stu-id="8b21c-152">Complete the pairing to begin projecting.</span></span>
