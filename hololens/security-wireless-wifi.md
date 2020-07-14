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
# <span data-ttu-id="88f32-104">Sans fil et Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="88f32-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="88f32-105">La connectivité réseau local sans fil HoloLens 2 prend en charge une gamme impressionnante de la dernière norme de sécurité Wi-Fi, telles que:</span><span class="sxs-lookup"><span data-stu-id="88f32-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="88f32-106">WPA2 (Wi-Fi Protected Access 2)</span><span class="sxs-lookup"><span data-stu-id="88f32-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="88f32-107">TEAP (Tunnel Extensible Authentication Protocol)</span><span class="sxs-lookup"><span data-stu-id="88f32-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="88f32-108">OWE (Opportunistic Wireless Encryption)</span><span class="sxs-lookup"><span data-stu-id="88f32-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="88f32-109">TEAP, la nouvelle génération d’authentification réseau d’entreprise, offre la possibilité de chaîner plusieurs informations d’identification de façon sécurisée dans une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="88f32-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="88f32-110">Cela permet aux administrateurs d’appliquer une attitude de sécurité accrue, nécessitant une identité valide pour les ordinateurs et les utilisateurs pendant la même transaction d’authentification.</span><span class="sxs-lookup"><span data-stu-id="88f32-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="88f32-111">HoloLens 2 dispose de protocoles sans fil et Wi-Fi modernes qui permettent aux clients de bénéficier d’une prise en charge maximale.</span><span class="sxs-lookup"><span data-stu-id="88f32-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="88f32-112">La radio HoloLens 2 est une solution Qualcomm WCN3990 offrant une expérience radio de qualité supérieure.</span><span class="sxs-lookup"><span data-stu-id="88f32-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="88f32-113">La connexion Wi-Fi prise en charge est 802.11 ac/n.</span><span class="sxs-lookup"><span data-stu-id="88f32-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="88f32-114">La plage de périodicité ne peut pas être configurée par l’utilisateur et dépend du pays d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="88f32-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="88f32-115">Aux États-Unis, le Wi-Fi utilise les canaux 2,4 GHz (1-11) et 5 GHz (36-64, 100-165) canaux.</span><span class="sxs-lookup"><span data-stu-id="88f32-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="88f32-116">Ni l’utilisateur, ni l’appareil ne peuvent créer des listes d’autorisation/refus pour des fréquences spécifiques.</span><span class="sxs-lookup"><span data-stu-id="88f32-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="88f32-117">Bluetooth SIC Core 5,0 possède une antenne dédiée 2,4 GHz pour Bluetooth qui n’est pas partagée avec Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="88f32-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="88f32-118">La pile logicielle de HoloLens 2 prend en charge plusieurs protocoles et profils, notamment HID, HOGP, A2DP et GATT.</span><span class="sxs-lookup"><span data-stu-id="88f32-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="88f32-119">Les administrateurs informatiques peuvent:</span><span class="sxs-lookup"><span data-stu-id="88f32-119">IT admins can:</span></span> 
  * <span data-ttu-id="88f32-120">Activer ou restreindre l’[accès Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span><span class="sxs-lookup"><span data-stu-id="88f32-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="88f32-121">Configurer [noms des appareils Bluetooth locaux](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span><span class="sxs-lookup"><span data-stu-id="88f32-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="88f32-122">Autoriser la [découverte des appareils](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span><span class="sxs-lookup"><span data-stu-id="88f32-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="88f32-123">Autoriser/refuser les [connexions Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span><span class="sxs-lookup"><span data-stu-id="88f32-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="88f32-124">Autoriser ou interdire [la connexion à un réseau Wi-Fi en dehors des réseaux installés sur le serveur](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span><span class="sxs-lookup"><span data-stu-id="88f32-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
