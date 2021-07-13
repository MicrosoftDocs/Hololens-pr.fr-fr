---
title: Se connecter à des appareils Bluetooth et USB-C
description: Familiarisez-vous avec la connexion aux appareils et accessoires Bluetooth et USB-C à partir de vos appareils HoloLens de réalité mixte.
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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924177"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="479fe-103">Se connecter à des appareils Bluetooth et USB-C</span><span class="sxs-lookup"><span data-stu-id="479fe-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="479fe-104">Coupler des appareils Bluetooth</span><span class="sxs-lookup"><span data-stu-id="479fe-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="479fe-105">HoloLens 2 prend en charge les classes d’appareils Bluetooth suivantes :</span><span class="sxs-lookup"><span data-stu-id="479fe-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="479fe-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/) :</span><span class="sxs-lookup"><span data-stu-id="479fe-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="479fe-107">Souris</span><span class="sxs-lookup"><span data-stu-id="479fe-107">Mouse</span></span>
    - <span data-ttu-id="479fe-108">Clavier</span><span class="sxs-lookup"><span data-stu-id="479fe-108">Keyboard</span></span>
- <span data-ttu-id="479fe-109">Périphériques de sortie audio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="479fe-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="479fe-110">HoloLens 2 prend en charge les API Bluetooth suivantes :</span><span class="sxs-lookup"><span data-stu-id="479fe-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="479fe-111">[Serveur](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) et [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) GATT</span><span class="sxs-lookup"><span data-stu-id="479fe-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="479fe-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="479fe-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="479fe-113">Vous devrez peut-être installer les applications compagnes correspondantes à partir du Microsoft Store pour utiliser les appareils HID et GATT.</span><span class="sxs-lookup"><span data-stu-id="479fe-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="479fe-114">HoloLens (1ère génération) prend en charge les classes d’appareils Bluetooth suivantes :</span><span class="sxs-lookup"><span data-stu-id="479fe-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="479fe-115">Souris</span><span class="sxs-lookup"><span data-stu-id="479fe-115">Mouse</span></span>
- <span data-ttu-id="479fe-116">Clavier</span><span class="sxs-lookup"><span data-stu-id="479fe-116">Keyboard</span></span>
- [<span data-ttu-id="479fe-117">Dispositif de clic HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="479fe-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="479fe-118">D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens.</span><span class="sxs-lookup"><span data-stu-id="479fe-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="479fe-119">Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="479fe-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="479fe-120">Pour plus d’informations, consultez [Les paramètres HoloLens répertorient des appareils disponibles, mais ceux-ci ne fonctionnent pas](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span><span class="sxs-lookup"><span data-stu-id="479fe-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="479fe-121">Coupler un clavier ou une souris Bluetooth</span><span class="sxs-lookup"><span data-stu-id="479fe-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="479fe-122">Activez le clavier ou la souris pour permettre sa détection.</span><span class="sxs-lookup"><span data-stu-id="479fe-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="479fe-123">Pour savoir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou rendez-vous sur le site web du fabricant.</span><span class="sxs-lookup"><span data-stu-id="479fe-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="479fe-124">Utilisez l’écartement des doigts paume vers le haut (HoloLens (1ère génération)) ou le mouvement associé au menu Démarrer (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="479fe-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="479fe-125">Sélectionnez **Appareils** et assurez-vous que Bluetooth est activé.</span><span class="sxs-lookup"><span data-stu-id="479fe-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="479fe-126">Une fois le nom de l’appareil affiché, sélectionnez **Coupler**, puis suivez les instructions.</span><span class="sxs-lookup"><span data-stu-id="479fe-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="479fe-127">Désactiver Bluetooth</span><span class="sxs-lookup"><span data-stu-id="479fe-127">Disable Bluetooth</span></span>

<span data-ttu-id="479fe-128">Cette procédure désactive les composants RF de la radio Bluetooth, de même que toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="479fe-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="479fe-129">Utilisez l’écartement des doigts paume vers le haut (HoloLens (1ère génération)) ou le mouvement associé au menu Démarrer (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.</span><span class="sxs-lookup"><span data-stu-id="479fe-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="479fe-130">Déplacez le curseur de **Bluetooth** vers la position **Off**.</span><span class="sxs-lookup"><span data-stu-id="479fe-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="479fe-131">HoloLens 2 : connecter des appareils USB-C</span><span class="sxs-lookup"><span data-stu-id="479fe-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="479fe-132">HoloLens 2 prend en charge les classes d’appareils USB-C suivantes :</span><span class="sxs-lookup"><span data-stu-id="479fe-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="479fe-133">Dispositifs de stockage de masse (lecteurs miniatures, par exemple)</span><span class="sxs-lookup"><span data-stu-id="479fe-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="479fe-134">Cartes Ethernet (notamment la charge Ethernet plus)</span><span class="sxs-lookup"><span data-stu-id="479fe-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="479fe-135">Cartes audio numériques USB-C à 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="479fe-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="479fe-136">Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)</span><span class="sxs-lookup"><span data-stu-id="479fe-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="479fe-137">Microphones externes USB-C ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ou ultérieure)</span><span class="sxs-lookup"><span data-stu-id="479fe-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="479fe-138">Souris filaire</span><span class="sxs-lookup"><span data-stu-id="479fe-138">Wired mouse</span></span>
- <span data-ttu-id="479fe-139">Clavier câblé</span><span class="sxs-lookup"><span data-stu-id="479fe-139">Wired keyboard</span></span>
- <span data-ttu-id="479fe-140">Combinaison de hubs PD (chargement PD plus USB A)</span><span class="sxs-lookup"><span data-stu-id="479fe-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="479fe-141">En réponse aux commentaires des clients, nous avons activé une prise en charge limitée de la connectivité cellulaire directement liée à HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="479fe-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="479fe-142">Pour plus d’informations, consultez [Se connecter à un réseau cellulaire et à la 5G](hololens-cellular.md) .</span><span class="sxs-lookup"><span data-stu-id="479fe-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="479fe-143">Prise en charge du microphone externe USB-C</span><span class="sxs-lookup"><span data-stu-id="479fe-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="479fe-144">Le raccordement d'**un microphone USB ne le définit pas automatiquement en tant que périphérique d’entrée**.</span><span class="sxs-lookup"><span data-stu-id="479fe-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="479fe-145">En cas de raccordement à un casque USB-C, les utilisateurs pourront constater que le son du casque est automatiquement redirigé vers le casque, mais que le système d’exploitation HoloLens priorise le réseaux de microphones internes par rapport à tout autre périphérique d’entrée.</span><span class="sxs-lookup"><span data-stu-id="479fe-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="479fe-146">**Pour utiliser un microphone USB-C, suivez les étapes ci-dessous.**</span><span class="sxs-lookup"><span data-stu-id="479fe-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="479fe-147">Les microphones externes ne peuvent pas être utilisés dans les builds antérieures à [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="479fe-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="479fe-148">Les utilisateurs peuvent sélectionner des microphones externes connectés par USB-C à l’aide du panneau des paramètres **Son** .</span><span class="sxs-lookup"><span data-stu-id="479fe-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="479fe-149">Les microphones USB-C peuvent être utilisés pour appeler, enregistrer, etc.</span><span class="sxs-lookup"><span data-stu-id="479fe-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="479fe-150">Ouvrez l’application **Paramètres** et sélectionnez **Système** > **Son**.</span><span class="sxs-lookup"><span data-stu-id="479fe-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Paramètres audio](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="479fe-152">Pour utiliser des microphones externes avec **Remote Assist**, les utilisateurs doivent cliquer sur le lien hypertexte « Gérer les périphériques audio ».</span><span class="sxs-lookup"><span data-stu-id="479fe-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="479fe-153">La liste déroulante leur permet ensuite de définir le microphone externe sur **Par défaut** ou **Communications par défaut**.</span><span class="sxs-lookup"><span data-stu-id="479fe-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="479fe-154">**Par défaut** signifie que le microphone externe sera utilisé partout.</span><span class="sxs-lookup"><span data-stu-id="479fe-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="479fe-155">**Communications par défaut** signifie que le microphone externe sera utilisé avec Remote Assist et autres applications de communications, mais que le réseau de microphones HoloLens restera disponible pour d’autres tâches.</span><span class="sxs-lookup"><span data-stu-id="479fe-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Gérer les périphériques audio](images/usbc-mic-2.png)

<br>

![Définir le microphone par défaut](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="479fe-158">Prise en charge des microphones Bluetooth</span><span class="sxs-lookup"><span data-stu-id="479fe-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="479fe-159">Malheureusement, les microphones Bluetooth ne sont pas encore pris en charge par l’HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="479fe-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="479fe-160">Hubs USB-C</span><span class="sxs-lookup"><span data-stu-id="479fe-160">USB-C Hubs</span></span>

<span data-ttu-id="479fe-161">Certains utilisateurs peuvent avoir besoin de connecter plusieurs appareils à la fois.</span><span class="sxs-lookup"><span data-stu-id="479fe-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="479fe-162">Les hubs USB-C peuvent répondre aux besoins des utilisateurs qui souhaitent utiliser un [microphone USB-C](#usb-c-external-microphone-support) et un autre appareil connecté.</span><span class="sxs-lookup"><span data-stu-id="479fe-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="479fe-163">Microsoft n'a pas testé ces appareils, et nous ne pouvons recommander aucune marque spécifique.</span><span class="sxs-lookup"><span data-stu-id="479fe-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="479fe-164">**Exigences relatives aux hubs USB-C et appareils connectés :**</span><span class="sxs-lookup"><span data-stu-id="479fe-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="479fe-165">Les appareils connectés ne doivent pas nécessiter l'installation d'un pilote.</span><span class="sxs-lookup"><span data-stu-id="479fe-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="479fe-166">La puissance totale absorbée de tous les appareils connectés doit être inférieure à 4,5 watts.</span><span class="sxs-lookup"><span data-stu-id="479fe-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="479fe-167">Se connecter à Miracast</span><span class="sxs-lookup"><span data-stu-id="479fe-167">Connect to Miracast</span></span>

<span data-ttu-id="479fe-168">Pour utiliser Miracast, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="479fe-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="479fe-169">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="479fe-169">Do one of the following:</span></span>  

   - <span data-ttu-id="479fe-170">Ouvrez le menu **Démarrer**, puis sélectionnez l’icône **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="479fe-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="479fe-171">Dites « Se connecter » lorsque vous pointez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="479fe-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="479fe-172">Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.</span><span class="sxs-lookup"><span data-stu-id="479fe-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="479fe-173">Terminez le couplage pour commencer la projection.</span><span class="sxs-lookup"><span data-stu-id="479fe-173">Complete the pairing to begin projecting.</span></span>
