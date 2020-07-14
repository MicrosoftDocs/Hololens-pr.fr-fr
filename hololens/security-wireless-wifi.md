---
title: Sans fil et Wi-Fi
description: Sans fil et Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, sans fil, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865705"
---
# Sans fil et Wi-Fi

La connectivité réseau local sans fil HoloLens 2 prend en charge une gamme impressionnante de la dernière norme de sécurité Wi-Fi, telles que:
  * WPA2 (Wi-Fi Protected Access 2)  
  * TEAP (Tunnel Extensible Authentication Protocol)  
  * OWE (Opportunistic Wireless Encryption)

TEAP, la nouvelle génération d’authentification réseau d’entreprise, offre la possibilité de chaîner plusieurs informations d’identification de façon sécurisée dans une seule transaction.  Cela permet aux administrateurs d’appliquer une attitude de sécurité accrue, nécessitant une identité valide pour les ordinateurs et les utilisateurs pendant la même transaction d’authentification.

HoloLens 2 dispose de protocoles sans fil et Wi-Fi modernes qui permettent aux clients de bénéficier d’une prise en charge maximale. La radio HoloLens 2 est une solution Qualcomm WCN3990 offrant une expérience radio de qualité supérieure. La connexion Wi-Fi prise en charge est 802.11 ac/n. La plage de périodicité ne peut pas être configurée par l’utilisateur et dépend du pays d’utilisation. Aux États-Unis, le Wi-Fi utilise les canaux 2,4 GHz (1-11) et 5 GHz (36-64, 100-165) canaux. Ni l’utilisateur, ni l’appareil ne peuvent créer des listes d’autorisation/refus pour des fréquences spécifiques. Bluetooth SIC Core 5,0 possède une antenne dédiée 2,4 GHz pour Bluetooth qui n’est pas partagée avec Wi-Fi. La pile logicielle de HoloLens 2 prend en charge plusieurs protocoles et profils, notamment HID, HOGP, A2DP et GATT. 

Les administrateurs informatiques peuvent: 
  * Activer ou restreindre l’[accès Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)
  * Configurer [noms des appareils Bluetooth locaux](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)
  * Autoriser la [découverte des appareils](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)
  * Autoriser/refuser les [connexions Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 
  * Autoriser ou interdire [la connexion à un réseau Wi-Fi en dehors des réseaux installés sur le serveur](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)
