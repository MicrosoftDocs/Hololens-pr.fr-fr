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
ms.openlocfilehash: fef69ee4cd148b82721472436da8dfd627f86ff1
ms.sourcegitcommit: 708da7b390fed1fd3aea1a2b2e50461851052683
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881337"
---
# Se connecter à des appareils Bluetooth et USB-C

## Appariement des appareils Bluetooth

HoloLens 2 prend en charge les classes suivantes d’appareils Bluetooth:

- Souris
- Clavier
- Périphériques de sortie audio Bluetooth (A2DP)

> [!NOTE]
> Les microphones externes ne peuvent pas être utilisés. HoloLens 2 utilise son [réseau de microphones](hololens2-hardware.md#audio-and-speech) intégré.

HoloLens (1ère génération) prend en charge les classes suivantes d’appareils Bluetooth:

- Souris
- Clavier
- Cliquez sur HoloLens (1ère génération)

> [!NOTE]
> D’autres types d’appareils Bluetooth (haut-parleurs, casques, smartphones et tablettes de jeux, par exemple) peuvent être répertoriés comme disponibles dans les paramètres HoloLens. Toutefois, ces appareils ne sont pas pris en charge sur HoloLens (1ère génération). Pour plus d’informations, voir [Paramètres HoloLens répertorie les appareils disponibles, mais les appareils ne fonctionnent pas](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### Coupler un clavier ou une souris Bluetooth

1. Activez le clavier ou la souris, et rendez-la détectable. Pour découvrir comment rendre l’appareil détectable, recherchez des informations sur l’appareil (ou sa documentation) ou visitez le site Web du fabricant.

1. Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de départ (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.

1. Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.  

1. Lorsque vous voyez le nom de l’appareil, sélectionnez **Paire**, puis suivez les instructions.

### HoloLens (1ère génération): coupler le clic

1. Utilisez le geste «fleuri» pour accéder à **Démarrer**, puis sélectionnez **Paramètres**.

1. Sélectionnez **Appareils** et assurez-vous que le Bluetooth est activé.

1. Utilisez l’astuce d’un stylet pour appuyer sur le bouton d’appariement de la flèche et le maintenir enfoncé jusqu’à ce que le voyant de l’état du clic clignote. Veillez à maintenir le bouton enfoncé jusqu’à ce que la lumière commence à clignoter.  

   Le bouton jumelage est placé sur le côté du clic, à côté de la boucle de doigt.
   
   ![Le bouton d’appariement est en regard de la boucle de doigt.](images/use-hololens-clicker-1.png)
   
1. Sur l'écran d’appairage, sélectionnez **Appairage** > **du dispositif de clic**.

## HoloLens 2: connecter des appareils USB-C

HoloLens 2 prend en charge les classes suivantes d’appareils USB-C:

- Périphériques de stockage de grande capacité (par exemple, lecteurs miniatures)
- Cartes Ethernet (notamment la charge Ethernet plus)
- Cartes audio numériques USB-C à 3,5 mm
- Casques audio numériques USB-C (y compris les adaptateurs de casque et les débits de chargement)
- Souris filaire
- Clavier câblé
- Combinaison de la combinaison de plusieurs moyeux (USB A plus débiter)

> [!NOTE]
> Certains appareils mobiles disposant de connexions USB-C se présentent eux-mêmes au contrôle HoloLens (adaptateurs Ethernet), et peuvent être utilisés dans une configuration de connexion, à commencer par Windows holographique (version 2004). Les modems LTE USB qui requièrent un pilote distinct et/ou l’application installée pour la configuration ne sont pas pris en charge.

Suite aux commentaires des clients, nous avons activé une prise en charge limitée de la connectivité cellulaire directement dans le service HoloLens via USB-C.  La connectivité par câble ne fonctionne que pour les appareils qui prennent en charge l'implémentation générique du pilote Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) et qui ne nécessitent pas l'installation d'autres pilotes ou applications.  Cet appareil, une fois connecté, s'affiche automatiquement sous la forme d'une nouvelle connexion Ethernet dans l'interface utilisateur des paramètres réseau HoloLens 2. Pour plus d’informations sur la prise en charge du pilote Microsoft RNDIS générique, consultez le fabricant de votre appareil.

## Se connecter à Miracast

Pour utiliser Miracast, procédez comme suit:

1. Effectuez l'une des opérations suivantes:  

   - Ouvrez le menu **Démarrer**, puis sélectionnez l’icône Afficher.
   - Dites «se connecter» lorsque vous pointez le menu **Démarrer**.  

1. Dans la liste des appareils qui s’affiche, sélectionnez un appareil disponible.

1. Terminez l’appariement pour commencer la projection.

## Désactiver Bluetooth

Cette procédure désactive les composants RF de la radio Bluetooth et désactive toutes les fonctionnalités Bluetooth sur Microsoft HoloLens.

1. Utilisez le geste fleuri (HoloLens (1ère génération)) ou le geste de démarrage (HoloLens 2) pour accéder à **Démarrer**, puis sélectionnez **Paramètres** > **Appareils**.

1. Déplacez le curseur de **Bluetooth** vers la position**Désactivée**.
