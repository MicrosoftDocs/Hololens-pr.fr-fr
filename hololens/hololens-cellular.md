---
title: Se connecter à un réseau cellulaire et à la 5G
description: Connexion aux réseaux cellulaires à partir de vos appareils de réalité mixte HoloLens
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635838"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="f7e84-103">Se connecter à un réseau cellulaire et à la 5G</span><span class="sxs-lookup"><span data-stu-id="f7e84-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="f7e84-104">L'HoloLens 2 prend en charge deux méthodes de connexion aux réseaux cellulaires et 5G :</span><span class="sxs-lookup"><span data-stu-id="f7e84-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="f7e84-105">Un réseau Wi-Fi ad hoc fourni par l'appareil cellulaire, communément appelé « point d'accès »</span><span class="sxs-lookup"><span data-stu-id="f7e84-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="f7e84-106">Une prise en charge limitée des appareils utilisant le partage de connexion USB-C</span><span class="sxs-lookup"><span data-stu-id="f7e84-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="f7e84-107">Point d'accès (WiFi)</span><span class="sxs-lookup"><span data-stu-id="f7e84-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="f7e84-108">Un point d'accès permet de satisfaire la plupart des besoins de connectivité cellulaire.</span><span class="sxs-lookup"><span data-stu-id="f7e84-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="f7e84-109">Le Wi-Fi de l'HoloLens 2 prend en charge la norme 802.11ac, qui permet de fournir la bande passante et la latence nécessaires à la plupart des cas d'usage courants.</span><span class="sxs-lookup"><span data-stu-id="f7e84-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="f7e84-110">Le Wi-Fi est également sans câble et offre une compatibilité avec un très grand nombre d'appareils cellulaires.</span><span class="sxs-lookup"><span data-stu-id="f7e84-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="f7e84-111">Connexion à un point d'accès</span><span class="sxs-lookup"><span data-stu-id="f7e84-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="f7e84-112">Consultez le manuel de votre appareil pour savoir comment activer le mode point d'accès.</span><span class="sxs-lookup"><span data-stu-id="f7e84-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="f7e84-113">Activez le mode point d'accès, en fournissant un nom pour le réseau ainsi qu'un mot de passe connu.</span><span class="sxs-lookup"><span data-stu-id="f7e84-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="f7e84-114">Dans les paramètres réseau de l'HoloLens 2, recherchez le réseau Wi-Fi créé à l'étape 2 et rejoignez-le.</span><span class="sxs-lookup"><span data-stu-id="f7e84-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="f7e84-115">Partage de connexion USB-C</span><span class="sxs-lookup"><span data-stu-id="f7e84-115">USB-C Tethering</span></span>

<span data-ttu-id="f7e84-116">Le partage de connexion USB-C peut fournir une latence plus faible pour les charges de travail avancées qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="f7e84-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="f7e84-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), par exemple, peut en tirer parti.</span><span class="sxs-lookup"><span data-stu-id="f7e84-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="f7e84-118">Notez que le partage de connexion requiert un câble entre l'appareil cellulaire et l'HoloLens, et que seul un nombre limité d'appareils le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="f7e84-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="f7e84-119">Compatibilité USB-C</span><span class="sxs-lookup"><span data-stu-id="f7e84-119">USB-C compatibility</span></span>

<span data-ttu-id="f7e84-120">Un nombre limité d'appareils qui se présentent en tant qu'adaptateurs Ethernet peuvent être utilisés avec Windows Holographic 2004 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f7e84-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="f7e84-121">Les appareils qui ne se présentent pas en tant qu'adaptateurs Ethernet doivent prendre en charge le pilote Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) générique.</span><span class="sxs-lookup"><span data-stu-id="f7e84-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="f7e84-122">Toutefois, seul un nombre limité de ces appareils est compatible avec HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f7e84-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="f7e84-123">Veuillez contacter le fabricant de votre appareil pour savoir s'il prend en charge le pilote Microsoft RNDIS générique.</span><span class="sxs-lookup"><span data-stu-id="f7e84-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="f7e84-124">Les appareils qui ne sont pas compatibles avec RNDIS ou qui nécessitent l'installation d'un pilote ou d'une application ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f7e84-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="f7e84-125">Microsoft ne tient pas de liste des appareils compatibles, mais une discussion communautaire sur le sujet est disponible [ici](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="f7e84-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="f7e84-126">Connexion à un appareil utilisant le partage de connexion</span><span class="sxs-lookup"><span data-stu-id="f7e84-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="f7e84-127">Consultez le manuel de votre appareil pour savoir comment activer le partage de données USB.</span><span class="sxs-lookup"><span data-stu-id="f7e84-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="f7e84-128">Ce paramètre est souvent appelé « partage de connexion USB », « partage de données » ou « modem USB ».</span><span class="sxs-lookup"><span data-stu-id="f7e84-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="f7e84-129">Activez le partage de données USB.</span><span class="sxs-lookup"><span data-stu-id="f7e84-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="f7e84-130">Connectez votre appareil au port USB-C de l'HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f7e84-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="f7e84-131">Dans les paramètres réseau de l'HoloLens 2, l'appareil apparaît automatiquement comme une connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f7e84-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
