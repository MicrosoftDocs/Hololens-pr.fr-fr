---
title: Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC
description: Inscription de l’adresse MAC pour le réseau sur les appareils HoloLens2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093228"
---
# <span data-ttu-id="e68b2-103">Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC</span><span class="sxs-lookup"><span data-stu-id="e68b2-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="e68b2-104">Ce document décrit un scénario courant que nous avons identifié dans les environnements clients où l’accès au Wi-Fi est restreint par adresses MAC, ou des certificats sont requis pour se connecter aux réseaux sans fil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="e68b2-105">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="e68b2-105">Example Scenario</span></span>

<span data-ttu-id="e68b2-106">Nombre de clients dans des environnements sécurisés appliquent des restrictions sur leur réseau sans fil ou câblé, ce qui permet uniquement aux appareils approuvés (basés sur des adresses MAC) de se connecter (soit avec filtrage d’adresse MAC sur un point d’accès sans fil, soit sur un serveur DHCP).</span><span class="sxs-lookup"><span data-stu-id="e68b2-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="e68b2-107">De plus, certains réseaux sans fil peuvent être protégés par PEAP, ce qui exige qu’un certificat soit appliqué sur l’appareil pour pouvoir s’authentifier sur le réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="e68b2-108">Deux problèmes clés peuvent se produire avec les appareils HoloLens, qui peuvent entraîner des délais et une intervention manuelle pour connecter les appareils HoloLens au réseau.</span><span class="sxs-lookup"><span data-stu-id="e68b2-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="e68b2-109">Le certificat PEAP sans fil doit être appliqué à l’appareil pour qu’il puisse se connecter au réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="e68b2-110">L’adresse MAC de l’adaptateur Wi-Fi HoloLens doit être inscrite.</span><span class="sxs-lookup"><span data-stu-id="e68b2-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="e68b2-111">Les principaux défis à relever sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="e68b2-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="e68b2-112">Pour l’instant, il est possible d’identifier l’adresse MAC uniquement à partir de l’application Paramètres sur l’appareil, ou à partir d’Intune suite à une inscription Intune réussie.</span><span class="sxs-lookup"><span data-stu-id="e68b2-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="e68b2-113">Sans l’adresse MAC, l’appareil ne peut pas se connecter au réseau Wi-Fi pour commencer l’inscription.</span><span class="sxs-lookup"><span data-stu-id="e68b2-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="e68b2-114">Les solutions manuelles pour résoudre ces défis nécessitent l’implication du technicien sur les appareils.</span><span class="sxs-lookup"><span data-stu-id="e68b2-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="e68b2-115">Solutions</span><span class="sxs-lookup"><span data-stu-id="e68b2-115">Solutions</span></span>

<span data-ttu-id="e68b2-116">Plusieurs méthodes s’offrent à vous pour améliorer cette situation, en fonction de l’infrastructure disponible au sein de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="e68b2-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="e68b2-117">Solution</span><span class="sxs-lookup"><span data-stu-id="e68b2-117">Solution</span></span> | <span data-ttu-id="e68b2-118">Avantages</span><span class="sxs-lookup"><span data-stu-id="e68b2-118">Benefits</span></span> | <span data-ttu-id="e68b2-119">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e68b2-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e68b2-120">Package de configuration avec adaptateur Ethernet</span><span class="sxs-lookup"><span data-stu-id="e68b2-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="e68b2-121">Améliore l’expérience OOBE et accélère l’intervention du technicien.</span><span class="sxs-lookup"><span data-stu-id="e68b2-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="e68b2-122">Concentrateur USB C compatible HoloLens. Le technicien doit continuer à interagir avec l’appareil pour la capture MAC et la finalisation de l’expérience OOBE.</span><span class="sxs-lookup"><span data-stu-id="e68b2-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="e68b2-123">Autopilot avec l’inscription Intune via Ethernet</span><span class="sxs-lookup"><span data-stu-id="e68b2-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="e68b2-124">Connexion et enregistrement de l’appareil à l’environnement client en une étape. La capture MAC peut être effectuée sans interaction avec l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="e68b2-125">Intune activé pour le client AAD du client. Adaptateur réseau compatible USB-C HoloLens</span><span class="sxs-lookup"><span data-stu-id="e68b2-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="e68b2-126">Création automatique de rapports sur les adresses MAC</span><span class="sxs-lookup"><span data-stu-id="e68b2-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="e68b2-127">Lorsque des appareils ont été enregistrés dans le client Intune, scriptez la notification de l’adresse MAC au technicien.</span><span class="sxs-lookup"><span data-stu-id="e68b2-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="e68b2-128">Commandlets PowerShell pour Intune</span><span class="sxs-lookup"><span data-stu-id="e68b2-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="e68b2-129">Package de configuration avec adaptateur Ethernet</span><span class="sxs-lookup"><span data-stu-id="e68b2-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="e68b2-130">Si le réseau câblé est également soumis aux restrictions MAC, l’adresse MAC du concentrateur/de l’adaptateur Ethernet USB-C doit être pré-approuvée.</span><span class="sxs-lookup"><span data-stu-id="e68b2-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="e68b2-131">Vous devez faire preuve de précaution avec ce concentrateur, car il permettra d’accéder au réseau à partir d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="e68b2-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="e68b2-132">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e68b2-132">Requirements</span></span>

- <span data-ttu-id="e68b2-133">Port réseau câblé avec accès au réseau du client</span><span class="sxs-lookup"><span data-stu-id="e68b2-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="e68b2-134">Concentrateur USB-C compatible HoloLens contenant un adaptateur Ethernet: tout concentrateur qui ne nécessite pas de pilotes ni d’installations d’applications supplémentaires convient.</span><span class="sxs-lookup"><span data-stu-id="e68b2-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="e68b2-135">Contenu du package de configuration:</span><span class="sxs-lookup"><span data-stu-id="e68b2-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="e68b2-136">Certificat et informations sur le réseau sans fil</span><span class="sxs-lookup"><span data-stu-id="e68b2-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="e68b2-137">Informations d’inscription pour l’AzureAD de l’organisation (facultatif)</span><span class="sxs-lookup"><span data-stu-id="e68b2-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="e68b2-138">Tout autre paramètre de configuration requis</span><span class="sxs-lookup"><span data-stu-id="e68b2-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="e68b2-139">Process</span><span class="sxs-lookup"><span data-stu-id="e68b2-139">Process</span></span>

<span data-ttu-id="e68b2-140">Le processus peut varier en fonction du niveau du logiciel de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="e68b2-141">Si l’appareil présente la [mise à jour2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e68b2-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="e68b2-142">Placez le package de configuration sur la racine d’une clé USB et branchez-la sur le concentrateur.</span><span class="sxs-lookup"><span data-stu-id="e68b2-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="e68b2-143">Connectez le câble Ethernet au concentrateur.</span><span class="sxs-lookup"><span data-stu-id="e68b2-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="e68b2-144">Connectez le concentrateur USB-C à l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e68b2-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="e68b2-145">Activez l’appareil HoloLens et portez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="e68b2-146">Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="e68b2-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="e68b2-147">Le technicien peut désormais suivre l’expérience OOBE et, une fois terminé, ouvrir l’application Paramètres et récupérer l’adresse MAC de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="e68b2-148">Si la build du système d'exploitation de l’appareil est antérieure à la [mise à jour2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e68b2-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="e68b2-149">Activez l’appareil HoloLens et branchez l’appareil sur un PC.</span><span class="sxs-lookup"><span data-stu-id="e68b2-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="e68b2-150">L’appareil doit apparaître sur le PC en tant que dispositif de stockage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e68b2-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="e68b2-151">Copiez le package de configuration sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="e68b2-152">Connectez le câble Ethernet au concentrateur.</span><span class="sxs-lookup"><span data-stu-id="e68b2-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="e68b2-153">Connectez le concentrateur USB-C à l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e68b2-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="e68b2-154">Portez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-154">Wear the device.</span></span>
7. <span data-ttu-id="e68b2-155">Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="e68b2-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="e68b2-156">Le technicien peut désormais suivre l’expérience OOBE et, une fois terminé, ouvrir l’application Paramètres et récupérer l’adresse MAC de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="e68b2-157">Avantages</span><span class="sxs-lookup"><span data-stu-id="e68b2-157">Benefits</span></span>

<span data-ttu-id="e68b2-158">Cela permettra, en &quot;une seule pression&quot; sur l’appareil, d’appliquer le package de configuration correct et d’obtenir l’adresse MAC de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e68b2-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="e68b2-159">Vous pouvez créer les packages de configuration à l’aide des instructions fournies ici.</span><span class="sxs-lookup"><span data-stu-id="e68b2-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="e68b2-160">Autopilot avec l’inscription Intune</span><span class="sxs-lookup"><span data-stu-id="e68b2-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="e68b2-161">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e68b2-161">Requirements</span></span>

- <span data-ttu-id="e68b2-162">Port réseau câblé avec accès au réseau du client</span><span class="sxs-lookup"><span data-stu-id="e68b2-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="e68b2-163">Appareils HoloLens exécutant Windows Holographic2004</span><span class="sxs-lookup"><span data-stu-id="e68b2-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="e68b2-164">Concentrateur USB-C compatible HoloLens</span><span class="sxs-lookup"><span data-stu-id="e68b2-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="e68b2-165">Intune configuré et activé pour le client du client</span><span class="sxs-lookup"><span data-stu-id="e68b2-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="e68b2-166">Appareil inscrit pour Autopilot et importé dans le client du client</span><span class="sxs-lookup"><span data-stu-id="e68b2-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="e68b2-167">Stratégies Intune définies pour l’appareil:</span><span class="sxs-lookup"><span data-stu-id="e68b2-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="e68b2-168">Certificat et informations sur le réseau sans fil</span><span class="sxs-lookup"><span data-stu-id="e68b2-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="e68b2-169">Tout autre paramètre de configuration requis</span><span class="sxs-lookup"><span data-stu-id="e68b2-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="e68b2-170">Cela permet à un client ayant besoin d’une configuration réseau avancée d’inscrire les appareils en utilisant une approche pratique et évolutive.</span><span class="sxs-lookup"><span data-stu-id="e68b2-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="e68b2-171">Des conditions préalables supplémentaires sont requises comme suit:</span><span class="sxs-lookup"><span data-stu-id="e68b2-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="e68b2-172">Activez le client pour l’aperçu Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e68b2-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="e68b2-173">Créez les stratégies HoloLens pour remplacer le package de configuration dans Intune.</span><span class="sxs-lookup"><span data-stu-id="e68b2-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="e68b2-174">Créez les stratégies Intune HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e68b2-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="e68b2-175">Attribuez les appareils au groupe approprié.</span><span class="sxs-lookup"><span data-stu-id="e68b2-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="e68b2-176">Process</span><span class="sxs-lookup"><span data-stu-id="e68b2-176">Process</span></span>

1. <span data-ttu-id="e68b2-177">Branchez le concentrateur USB-C et le câble Ethernet sur l’appareil HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="e68b2-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="e68b2-178">Activez HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="e68b2-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="e68b2-179">L’appareil doit se connecter automatiquement à Internet à l’aide de l’expérience OOBE via l’adaptateur Ethernet, détecter la configuration Autopilot et s’inscrire automatiquement auprès d’Azure AD et d’Intune.</span><span class="sxs-lookup"><span data-stu-id="e68b2-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="e68b2-180">L’appareil applique les certificats Wi-Fi requis et d’autres configurations si nécessaire via Intune.</span><span class="sxs-lookup"><span data-stu-id="e68b2-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="e68b2-181">Une fois l’opération terminée, le technicien pourra charger le portail Intune (Endpoint Manager), puis explorer la page des propriétés de l’appareil en accédant à **Accueil-> Appareils-> NomDeL’Appareil-> Matériel**.</span><span class="sxs-lookup"><span data-stu-id="e68b2-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="e68b2-182">L’adresse MAC Wi-Fi sera visible dans le portail Intune.</span><span class="sxs-lookup"><span data-stu-id="e68b2-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Adresse MAC via Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="e68b2-184">Le technicien ajoutera cette adresse MAC en tant qu’appareil autorisé.</span><span class="sxs-lookup"><span data-stu-id="e68b2-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="e68b2-185">Avantages</span><span class="sxs-lookup"><span data-stu-id="e68b2-185">Benefits</span></span>

<span data-ttu-id="e68b2-186">Cela permet une expérience de déploiement &quot;sans port sur la tête&quot; pour le technicien. Il peut en effet inscrire l’appareil sur AAD et Intune sans avoir à le porter ni à interagir manuellement avec l’environnement HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e68b2-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="e68b2-187">Notification des adresses MAC au technicien</span><span class="sxs-lookup"><span data-stu-id="e68b2-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="e68b2-188">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e68b2-188">Requirements</span></span>

- <span data-ttu-id="e68b2-189">Autorisation du &quot;PowerShell Graph Intune&quot; sur le client du client</span><span class="sxs-lookup"><span data-stu-id="e68b2-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="e68b2-190">Installation du PowerShell Graph Intune sur l’ordinateur du technicien.</span><span class="sxs-lookup"><span data-stu-id="e68b2-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="e68b2-191">Accès en lecture sur les éléments &quot;Appareils gérés&quot; d’Intune.</span><span class="sxs-lookup"><span data-stu-id="e68b2-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="e68b2-192">(Opérateur de support technique ou supérieur, ou rôle personnalisé)</span><span class="sxs-lookup"><span data-stu-id="e68b2-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="e68b2-193">Pour l’instant, il n’existe aucun moyen &quot;simple&quot; de déclencher une commande d’automatisation basée sur l’inscription d’un nouvel appareil dans Intune.</span><span class="sxs-lookup"><span data-stu-id="e68b2-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="e68b2-194">Par conséquent, cette commande offre au technicien une méthode simple pour récupérer l’adresse MAC sans avoir à se connecter au portail et récupérer celle-ci manuellement.</span><span class="sxs-lookup"><span data-stu-id="e68b2-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="e68b2-195">Cette opération renvoie le nom et l’adresse MAC de tous les appareils HoloLens inscrits au cours des 30derniers jours.</span><span class="sxs-lookup"><span data-stu-id="e68b2-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Adresse MAC via PowerShell](images/mac-address-powershell.jpg)

### <span data-ttu-id="e68b2-197">Process</span><span class="sxs-lookup"><span data-stu-id="e68b2-197">Process</span></span>

<span data-ttu-id="e68b2-198">Une fois l’inscription à Intune terminée, le technicien exécutait le script ci-dessus pour récupérer l’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="e68b2-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
