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
# <a name="connect-to-cellular-and-5g"></a>Connexion au cellulaire et à la 5G

HoloLens 2 prend en charge deux méthodes de connexion aux réseaux cellulaires et 5G :

- Un réseau WiFi ad hoc fourni par le périphérique cellulaire, communément appelé « point d’accès »
- Prise en charge limitée des appareils connectés à l’USB-C

## <a name="hotspot-wifi"></a>Point d’accès (WiFi)

La plupart des besoins de connectivité cellulaire peuvent être satisfaits avec un point d’accès. Le WiFi HoloLens 2 prend en charge 802.11ac, qui peut fournir les besoins en bande passante et en latence nécessaires pour les cas d’utilisation les plus courants. Le WiFi est également sans câble et offre une compatibilité avec le plus grand nombre d’appareils cellulaires.

### <a name="connecting-to-a-hotspot"></a>Connexion à un point d’accès

1. Consultez le manuel de votre appareil pour savoir comment activer le mode point d’accès.
1. Activez le mode point d’accès, en fournissant un nom pour le réseau ainsi qu’un mot de passe connu.
1. Dans les paramètres réseau HoloLens 2, recherchez le réseau WiFi créé à l’étape 2 et connectez-vous.

## <a name="usb-c-tethering"></a>Connexion USB-C

La connexion USB-C peut fournir une latence moindre pour les charges de travail avancées qui en ont besoin. Le [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), par exemple, peut bénéficier de la connexion. Notez que la connexion nécessite un câble entre le périphérique cellulaire et HoloLens, et la connexion est prise en charge par un nombre limité d’appareils.

### <a name="usb-c-compatibility"></a>Compatibilité USB-C

Les appareils qui se présentent en tant qu’adaptateur ethernet peuvent être utilisés avec Windows Holographic version 2004 et ultérieures.

Les appareils qui ne se présentent pas en tant qu’adaptateur ethernet doivent prendre en charge le pilote [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft générique. Veuillez consulter le fabricant de votre appareil pour plus d’informations sur la capacité de l’appareil à prendre en charge le pilote RNDIS Microsoft générique.

Les appareils qui ne sont pas compatibles au RNDIS ou qui nécessitent l’installation d’un pilote ou d’une application ne sont pas pris en charge.

Bien que Microsoft ne conserve pas la liste des appareils compatibles, il existe une discussion de la communauté sur la rubrique [ici](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Connexion à un appareil connecté

1. Consultez le manuel de votre appareil pour l’activation du partage de données sur USB. Ce paramètre est souvent appelé « connexion USB », « Partage de données » ou « Modem USB ».
1. Activer le partage de données sur USB.
1. Connectez votre appareil au port USB-C HoloLens.
1. Dans les paramètres réseau HoloLens 2, l’appareil s’affiche automatiquement en tant que connexion Ethernet.
