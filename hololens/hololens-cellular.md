---
title: Connexion au cellulaire et à la 5G
description: Connexion aux réseaux cellulaires à partir de vos appareils HoloLens de réalité mixte.
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
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385639"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="3064f-103">Connexion au cellulaire et à la 5G</span><span class="sxs-lookup"><span data-stu-id="3064f-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="3064f-104">HoloLens 2 prend en charge deux méthodes de connexion aux réseaux cellulaires et 5G :</span><span class="sxs-lookup"><span data-stu-id="3064f-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="3064f-105">Un réseau WiFi ad hoc fourni par le périphérique cellulaire, communément appelé « point d’accès »</span><span class="sxs-lookup"><span data-stu-id="3064f-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="3064f-106">Prise en charge limitée des appareils connectés à l’USB-C</span><span class="sxs-lookup"><span data-stu-id="3064f-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="3064f-107">Point d’accès (WiFi)</span><span class="sxs-lookup"><span data-stu-id="3064f-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="3064f-108">La plupart des besoins de connectivité cellulaire peuvent être satisfaits avec un point d’accès.</span><span class="sxs-lookup"><span data-stu-id="3064f-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="3064f-109">Le WiFi HoloLens 2 prend en charge 802.11ac, qui peut fournir les besoins en bande passante et en latence nécessaires pour les cas d’utilisation les plus courants.</span><span class="sxs-lookup"><span data-stu-id="3064f-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="3064f-110">Le WiFi est également sans câble et offre une compatibilité avec le plus grand nombre d’appareils cellulaires.</span><span class="sxs-lookup"><span data-stu-id="3064f-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="3064f-111">Connexion à un point d’accès</span><span class="sxs-lookup"><span data-stu-id="3064f-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="3064f-112">Consultez le manuel de votre appareil pour savoir comment activer le mode point d’accès.</span><span class="sxs-lookup"><span data-stu-id="3064f-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="3064f-113">Activez le mode point d’accès, en fournissant un nom pour le réseau ainsi qu’un mot de passe connu.</span><span class="sxs-lookup"><span data-stu-id="3064f-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="3064f-114">Dans les paramètres réseau HoloLens 2, recherchez le réseau WiFi créé à l’étape 2 et connectez-vous.</span><span class="sxs-lookup"><span data-stu-id="3064f-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="3064f-115">Connexion USB-C</span><span class="sxs-lookup"><span data-stu-id="3064f-115">USB-C Tethering</span></span>

<span data-ttu-id="3064f-116">La connexion USB-C peut fournir une latence moindre pour les charges de travail avancées qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="3064f-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="3064f-117">Le [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), par exemple, peut bénéficier de la connexion.</span><span class="sxs-lookup"><span data-stu-id="3064f-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="3064f-118">Notez que la connexion nécessite un câble entre le périphérique cellulaire et HoloLens, et la connexion est prise en charge par un nombre limité d’appareils.</span><span class="sxs-lookup"><span data-stu-id="3064f-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="3064f-119">Compatibilité USB-C</span><span class="sxs-lookup"><span data-stu-id="3064f-119">USB-C compatibility</span></span>

<span data-ttu-id="3064f-120">Les appareils qui se présentent en tant qu’adaptateur ethernet peuvent être utilisés avec Windows Holographic version 2004 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="3064f-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="3064f-121">Les appareils qui ne se présentent pas en tant qu’adaptateur ethernet doivent prendre en charge le pilote [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft générique.</span><span class="sxs-lookup"><span data-stu-id="3064f-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="3064f-122">Veuillez consulter le fabricant de votre appareil pour plus d’informations sur la capacité de l’appareil à prendre en charge le pilote RNDIS Microsoft générique.</span><span class="sxs-lookup"><span data-stu-id="3064f-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="3064f-123">Les appareils qui ne sont pas compatibles au RNDIS ou qui nécessitent l’installation d’un pilote ou d’une application ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="3064f-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="3064f-124">Bien que Microsoft ne conserve pas la liste des appareils compatibles, il existe une discussion de la communauté sur la rubrique [ici](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="3064f-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="3064f-125">Connexion à un appareil connecté</span><span class="sxs-lookup"><span data-stu-id="3064f-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="3064f-126">Consultez le manuel de votre appareil pour l’activation du partage de données sur USB.</span><span class="sxs-lookup"><span data-stu-id="3064f-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="3064f-127">Ce paramètre est souvent appelé « connexion USB », « Partage de données » ou « Modem USB ».</span><span class="sxs-lookup"><span data-stu-id="3064f-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="3064f-128">Activer le partage de données sur USB.</span><span class="sxs-lookup"><span data-stu-id="3064f-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="3064f-129">Connectez votre appareil au port USB-C HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3064f-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="3064f-130">Dans les paramètres réseau HoloLens 2, l’appareil s’affiche automatiquement en tant que connexion Ethernet.</span><span class="sxs-lookup"><span data-stu-id="3064f-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
