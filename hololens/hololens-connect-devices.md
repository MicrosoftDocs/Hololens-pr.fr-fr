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
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Se connecter à des appareils Bluetooth et USB-C

> [!NOTE]
> Les microphones externes ne peuvent pas être utilisés. HoloLens 2 utilise son [réseau de microphones](hololens2-hardware.md#audio-and-speech) intégré.

## <a name="pair-bluetooth-devices"></a>Appariement des appareils Bluetooth

HoloLens 2 prend en charge les classes suivantes d’appareils Bluetooth:

- Souris
- Clavier
- Périphériques de sortie audio Bluetooth (A2DP)

HoloLens (1ère génération) prend en charge les classes suivantes d’appareils Bluetooth:

- Souris
- Clavier
- [Cliquez sur HoloLens (1ère génération)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens. Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération). Pour plus d’informations, voir [Paramètres HoloLens répertorie les appareils disponibles, mais les appareils ne fonctionnent pas](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Coupler un clavier ou une souris Bluetooth

1. Activez le clavier ou la souris, et rendez-la détectable. Pour découvrir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou visitez le site Web du fabricant.

1. Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de départ (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.

1. Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.  

1. Lorsque vous voyez le nom de l’appareil, sélectionnez **Paire**, puis suivez les instructions.

## <a name="disable-bluetooth"></a>Désactiver Bluetooth

Cette procédure désactive les composants RF de la radio Bluetooth et désactive toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.

1. Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de démarrage (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.

1. Déplacez le curseur de **Bluetooth** vers la position**Désactivée**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: connecter des appareils USB-C

HoloLens 2 prend en charge les classes suivantes d’appareils USB-C:

- Périphériques de stockage de grande capacité (par exemple, lecteurs miniatures)
- Cartes Ethernet (notamment la charge Ethernet plus)
- Cartes audio numériques USB-C à 3,5 mm
- Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)
- Souris filaire
- Clavier câblé
- Combinaison de la combinaison de plusieurs moyeux (USB A plus débiter)

> [!NOTE]
> En réponse aux commentaires des clients, nous avons activé une prise en charge limitée de la connectivité cellulaire directement liée à HoloLens via USB-C. Consultez [Connexion au cellulaire et à la 5G](hololens-cellular.md) pour plus d’informations.

### <a name="usb-c-hubs"></a>Hubs USB-C

Certains utilisateurs peuvent avoir besoin de connecter plusieurs appareils à la fois. Pour les utilisateurs qui souhaitent avoir un aperçu d'une fonction Insider et[ utiliser un microphone USB-C avec ](hololens-insider.md#usb-c-external-microphone-support)un autre appareil connecté, les concentrateurs USB-C peuvent répondre au besoin du client. Microsoft n'a pas testé ces appareils, et nous ne pouvons recommander aucune marque spécifique.

**Exigences pour les concentrateurs USB-C et les appareils connectés :**

- Les appareils connectés ne doivent pas nécessiter l'installation d'un pilote.
- La puissance totale absorbée de tous les appareils connectés doit être inférieure à 4,5 watts.

## <a name="connect-to-miracast"></a>Se connecter à Miracast

Pour utiliser Miracast, procédez comme suit:

1. Effectuez l'une des opérations suivantes:  

   - Ouvrez le menu **Démarrer**, puis sélectionnez l’icône Afficher.
   - Dites «se connecter» lorsque vous pointez le menu **Démarrer**.  

1. Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.

1. Terminez l’appariement pour commencer la projection.
