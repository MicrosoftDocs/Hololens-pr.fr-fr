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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189084"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Se connecter à des appareils Bluetooth et USB-C

## <a name="pair-bluetooth-devices"></a>Coupler des appareils Bluetooth

HoloLens 2 prend en charge les classes d’appareils Bluetooth suivantes :

- [HID](/windows-hardware/drivers/hid/) :
    - Souris
    - Clavier
- Périphériques de sortie audio (A2DP)

HoloLens 2 prend en charge les API Bluetooth suivantes :
- [Serveur](/windows/uwp/devices-sensors/gatt-server) et [Client](/windows/uwp/devices-sensors/gatt-client) GATT
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Vous devrez peut-être installer les applications compagnes correspondantes à partir du Microsoft Store pour utiliser les appareils HID et GATT.

HoloLens (1ère génération) prend en charge les classes d’appareils Bluetooth suivantes :

- Souris
- Clavier
- [Dispositif de clic HoloLens (1ère génération)](hololens1-clicker.md)

> [!NOTE]
> D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens. Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération). Pour plus d’informations, consultez [Les paramètres HoloLens répertorient des appareils disponibles, mais ceux-ci ne fonctionnent pas](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Coupler un clavier ou une souris Bluetooth

1. Activez le clavier ou la souris pour permettre sa détection. Pour savoir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou rendez-vous sur le site web du fabricant.

1. Utilisez l’écartement des doigts paume vers le haut (HoloLens (1ère génération)) ou le mouvement associé au menu Démarrer (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.

1. Sélectionnez **Appareils** et assurez-vous que Bluetooth est activé.  

1. Une fois le nom de l’appareil affiché, sélectionnez **Coupler**, puis suivez les instructions.

## <a name="disable-bluetooth"></a>Désactiver Bluetooth

Cette procédure désactive les composants RF de la radio Bluetooth, de même que toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.

1. Utilisez l’écartement des doigts paume vers le haut (HoloLens (1ère génération)) ou le mouvement associé au menu Démarrer (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.

1. Déplacez le curseur de **Bluetooth** vers la position **Off**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2 : connecter des appareils USB-C

HoloLens 2 prend en charge les classes d’appareils USB-C suivantes :

- Dispositifs de stockage de masse (lecteurs miniatures, par exemple)
- Cartes Ethernet (notamment la charge Ethernet plus)
- Cartes audio numériques USB-C à 3,5 mm
- Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)
- Microphones externes USB-C ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ou ultérieure)
- Souris filaire
- Clavier câblé
- Combinaison de hubs PD (chargement PD plus USB A)


> [!NOTE]
> En réponse aux commentaires des clients, nous avons activé une prise en charge limitée de la connectivité cellulaire directement liée à HoloLens via USB-C. Pour plus d’informations, consultez [Se connecter à un réseau cellulaire et à la 5G](hololens-cellular.md) .

### <a name="usb-c-external-microphone-support"></a>Prise en charge du microphone externe USB-C

> [!IMPORTANT]
> Le raccordement d'**un microphone USB ne le définit pas automatiquement en tant que périphérique d’entrée**. En cas de raccordement à un casque USB-C, les utilisateurs pourront constater que le son du casque est automatiquement redirigé vers le casque, mais que le système d’exploitation HoloLens priorise le réseaux de microphones internes par rapport à tout autre périphérique d’entrée. **Pour utiliser un microphone USB-C, suivez les étapes ci-dessous.**

> [!NOTE]
> Les microphones externes ne peuvent pas être utilisés dans les builds antérieures à [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ou ultérieure. 

Les utilisateurs peuvent sélectionner des microphones externes connectés par USB-C à l’aide du panneau des paramètres **Son** . Les microphones USB-C peuvent être utilisés pour appeler, enregistrer, etc.

Ouvrez l’application **Paramètres** et sélectionnez **Système** > **Son**.

![Paramètres audio.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pour utiliser des microphones externes avec **Remote Assist**, les utilisateurs doivent cliquer sur le lien hypertexte « Gérer les périphériques audio ».
>
> La liste déroulante leur permet ensuite de définir le microphone externe sur **Par défaut** ou **Communications par défaut**. **Par défaut** signifie que le microphone externe sera utilisé partout.
>
> **Communications par défaut** signifie que le microphone externe sera utilisé avec Remote Assist et autres applications de communications, mais que le réseau de microphones HoloLens restera disponible pour d’autres tâches.

![Gérer les périphériques audio.](images/usbc-mic-2.png)

<br>

![Définir le microphone par défaut.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Prise en charge des microphones Bluetooth

Malheureusement, les microphones Bluetooth ne sont pas encore pris en charge par l’HoloLens 2.

### <a name="usb-c-hubs"></a>Hubs USB-C

Certains utilisateurs peuvent avoir besoin de connecter plusieurs appareils à la fois. Les hubs USB-C peuvent répondre aux besoins des utilisateurs qui souhaitent utiliser un [microphone USB-C](#usb-c-external-microphone-support) et un autre appareil connecté. Microsoft n'a pas testé ces appareils, et nous ne pouvons recommander aucune marque spécifique.

**Exigences relatives aux hubs USB-C et appareils connectés :**

- Les appareils connectés ne doivent pas nécessiter l'installation d'un pilote.
- La puissance totale absorbée de tous les appareils connectés doit être inférieure à 4,5 watts.

## <a name="connect-to-miracast"></a>Se connecter à Miracast

Pour utiliser Miracast, procédez comme suit :

1. Effectuez l’une des opérations suivantes :  

   - Ouvrez le menu **Démarrer**, puis sélectionnez l’icône **Afficher**.
   - Dites « Se connecter » lorsque vous pointez le menu **Démarrer**.  

1. Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.

1. Terminez le couplage pour commencer la projection.
