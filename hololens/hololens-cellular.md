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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034107"
---
# <a name="connect-to-cellular-and-5g"></a>Se connecter à un réseau cellulaire et à la 5G

L'HoloLens 2 prend en charge deux méthodes de connexion aux réseaux cellulaires et 5G :

- Un réseau Wi-Fi ad hoc fourni par l'appareil cellulaire, communément appelé « point d'accès »
- Une prise en charge limitée des appareils utilisant le partage de connexion USB-C

## <a name="hotspot-wifi"></a>Point d'accès (WiFi)

Un point d'accès permet de satisfaire la plupart des besoins de connectivité cellulaire. Le Wi-Fi de l'HoloLens 2 prend en charge la norme 802.11ac, qui permet de fournir la bande passante et la latence nécessaires à la plupart des cas d'usage courants. Le Wi-Fi est également sans câble et offre une compatibilité avec un très grand nombre d'appareils cellulaires.

### <a name="connecting-to-a-hotspot"></a>Connexion à un point d'accès

1. Consultez le manuel de votre appareil pour savoir comment activer le mode point d'accès.
1. Activez le mode point d'accès, en fournissant un nom pour le réseau ainsi qu'un mot de passe connu.
1. Dans les paramètres réseau de l'HoloLens 2, recherchez le réseau Wi-Fi créé à l'étape 2 et rejoignez-le.

## <a name="usb-c-tethering"></a>Partage de connexion USB-C

Le partage de connexion USB-C peut fournir une latence plus faible pour les charges de travail avancées qui en ont besoin. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), par exemple, peut en tirer parti. Notez que le partage de connexion requiert un câble entre l'appareil cellulaire et l'HoloLens, et que seul un nombre limité d'appareils le prend en charge.

### <a name="usb-c-compatibility"></a>Compatibilité USB-C

Un nombre limité d'appareils qui se présentent en tant qu'adaptateurs Ethernet peuvent être utilisés avec Windows Holographic 2004 et versions ultérieures.

Les appareils qui ne se présentent pas en tant qu'adaptateurs Ethernet doivent prendre en charge le pilote Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) générique. Toutefois, seul un nombre limité de ces appareils est compatible avec HoloLens 2. Veuillez contacter le fabricant de votre appareil pour savoir s'il prend en charge le pilote Microsoft RNDIS générique.

Les appareils qui ne sont pas compatibles avec RNDIS ou qui nécessitent l'installation d'un pilote ou d'une application ne sont pas pris en charge.

Microsoft ne tient pas de liste des appareils compatibles, mais une discussion communautaire sur le sujet est disponible [ici](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Connexion à un appareil utilisant le partage de connexion

1. Consultez le manuel de votre appareil pour savoir comment activer le partage de données USB. Ce paramètre est souvent appelé « partage de connexion USB », « partage de données » ou « modem USB ».
1. Activez le partage de données USB.
1. Connectez votre appareil au port USB-C de l'HoloLens.
1. Dans les paramètres réseau de l'HoloLens 2, l'appareil apparaît automatiquement comme une connexion Ethernet.
