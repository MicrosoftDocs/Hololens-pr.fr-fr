---
title: Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC
description: Inscription de l’adresse MAC pour le réseau sur les appareils HoloLens 2
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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407619"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="96734-103">Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC</span><span class="sxs-lookup"><span data-stu-id="96734-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="96734-104">Ce document décrit un scénario courant que nous avons identifié dans les environnements clients où l’accès au Wi-Fi est restreint par adresses MAC, ou des certificats sont requis pour se connecter aux réseaux sans fil.</span><span class="sxs-lookup"><span data-stu-id="96734-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="96734-105">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="96734-105">Example Scenario</span></span>

<span data-ttu-id="96734-106">De nombreux clients en environnement sécurisé sont soumis à des restrictions sur leurs réseaux sans fil ou câblés, ce qui permet uniquement aux périphériques approuvés (en fonction de leur adresse MAC) de se connecter correctement.</span><span class="sxs-lookup"><span data-stu-id="96734-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="96734-107">Cela peut être appliqué par le biais du filtrage des adresses MAC sur un point d’accès sans fil ou via un serveur DHCP.</span><span class="sxs-lookup"><span data-stu-id="96734-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="96734-108">De plus, certains réseaux sans fil peuvent être protégés par PEAP, ce qui exige qu’un certificat soit appliqué sur l’appareil avant l’authentification sur le réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="96734-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="96734-109">Dans ce scénario, deux exigences clés peuvent introduire des retards ou nécessiter une intervention manuelle lors de la connexion des appareils HoloLens au réseau :</span><span class="sxs-lookup"><span data-stu-id="96734-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="96734-110">Le certificat PEAP sans fil doit être appliqué à l’appareil pour qu’il puisse se connecter au réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="96734-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="96734-111">L’adresse MAC de l’adaptateur Wi-Fi HoloLens doit être inscrite.</span><span class="sxs-lookup"><span data-stu-id="96734-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="96734-112">Les principaux défis liés aux exigences ci-dessus sont les éléments ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="96734-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="96734-113">L’adresse MAC ne peut actuellement être identifiée qu’à partir de l’application Paramètres sur l’appareil ou à partir d’Intune après une inscription réussie.</span><span class="sxs-lookup"><span data-stu-id="96734-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="96734-114">Sans l’adresse MAC, l’appareil ne peut pas se connecter au réseau Wi-Fi pour commencer l’inscription.</span><span class="sxs-lookup"><span data-stu-id="96734-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="96734-115">Pour contourner manuellement ces problèmes, un technicien doit interagir avec l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="96734-116">Solutions</span><span class="sxs-lookup"><span data-stu-id="96734-116">Solutions</span></span>

<span data-ttu-id="96734-117">Il existe de nombreuses façons d’améliorer cette situation, en fonction de l’infrastructure disponible au sein de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="96734-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="96734-118">Solution</span><span class="sxs-lookup"><span data-stu-id="96734-118">Solution</span></span> | <span data-ttu-id="96734-119">Avantages</span><span class="sxs-lookup"><span data-stu-id="96734-119">Benefits</span></span> | <span data-ttu-id="96734-120">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="96734-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96734-121">Package de configuration avec adaptateur Ethernet</span><span class="sxs-lookup"><span data-stu-id="96734-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="96734-122">Améliore l’expérience OOBE et accélère l’intervention du technicien.</span><span class="sxs-lookup"><span data-stu-id="96734-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="96734-123">Concentrateur USB C compatible HoloLens + adaptateur Ethernet et le technicien doit continuer à interagir avec l’appareil pour la capture MAC et la finalisation de l’expérience OOBE.</span><span class="sxs-lookup"><span data-stu-id="96734-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="96734-124">Autopilot avec l’inscription Intune via Ethernet</span><span class="sxs-lookup"><span data-stu-id="96734-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="96734-125">Il s’agit d’une connexion à une étape et d’une inscription de l’appareil à l’environnement du client.</span><span class="sxs-lookup"><span data-stu-id="96734-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="96734-126">La capture MAC peut être effectuée sans avoir à interagir avec l’appareil</span><span class="sxs-lookup"><span data-stu-id="96734-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="96734-127">Intune activé pour le client client AAD et un adaptateur Ethernet USB-C compatible HoloLens</span><span class="sxs-lookup"><span data-stu-id="96734-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="96734-128">Création automatique de rapports sur les adresses MAC</span><span class="sxs-lookup"><span data-stu-id="96734-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="96734-129">Lorsque des appareils sont enregistrés auprès du client Intune, un script peut signaler l’adresse MAC au technicien.</span><span class="sxs-lookup"><span data-stu-id="96734-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="96734-130">Cmdlets Intune PowerShell</span><span class="sxs-lookup"><span data-stu-id="96734-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="96734-131">Package de configuration avec adaptateur Ethernet</span><span class="sxs-lookup"><span data-stu-id="96734-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="96734-132">Si le réseau câblé est également soumis à des restrictions mac, l’adresse Mac du concentrateur USB-C + adapteur Ethernet doit également être pré-approuvée.</span><span class="sxs-lookup"><span data-stu-id="96734-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="96734-133">Il convient de prendre soin de cet adaptateur, car elle permet d’accéder au réseau à partir d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="96734-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="96734-134">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="96734-134">Requirements</span></span>

- <span data-ttu-id="96734-135">Port réseau câblé avec accès au réseau du client</span><span class="sxs-lookup"><span data-stu-id="96734-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="96734-136">Concentrateur USB-C compatible HoloLens avec adaptateur Ethernet : tout adaptateur qui ne nécessite pas de pilotes ni d’installations d’applications supplémentaires convient.</span><span class="sxs-lookup"><span data-stu-id="96734-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="96734-137">Contenu du package de configuration :</span><span class="sxs-lookup"><span data-stu-id="96734-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="96734-138">Certificat et informations sur le réseau sans fil</span><span class="sxs-lookup"><span data-stu-id="96734-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="96734-139">Informations d’inscription pour l’Azure AD de l’organisation (facultatif)</span><span class="sxs-lookup"><span data-stu-id="96734-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="96734-140">Tout autre paramètre de configuration requis</span><span class="sxs-lookup"><span data-stu-id="96734-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="96734-141">Process</span><span class="sxs-lookup"><span data-stu-id="96734-141">Process</span></span>

<span data-ttu-id="96734-142">Le processus peut varier en fonction du niveau du logiciel de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="96734-143">Si l’appareil présente la [mise à jour 2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="96734-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="96734-144">Placez le package de configuration sur la racine d’une clé USB et branchez-la sur le concentrateur.</span><span class="sxs-lookup"><span data-stu-id="96734-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="96734-145">Connectez le câble Ethernet à l’adaptateur Hub + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="96734-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="96734-146">Connectez le Hub USB-C à l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96734-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="96734-147">Activer HoloLens et activer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="96734-148">Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="96734-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="96734-149">Le technicien peut désormais suivre la OOBE et, une fois terminé, ouvrez l’application Paramètres pour récupérer l’adresse MAC de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="96734-150">Si la build du système d'exploitation de l’appareil est antérieure à la [mise à jour 2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="96734-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="96734-151">Activez HoloLens et brancher l’appareil sur un PC.</span><span class="sxs-lookup"><span data-stu-id="96734-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="96734-152">L’appareil doit apparaître sur le PC en tant que dispositif de stockage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="96734-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="96734-153">Copiez le package de configuration sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="96734-154">Connectez le câble Ethernet au concentrateur.</span><span class="sxs-lookup"><span data-stu-id="96734-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="96734-155">Connectez le Hub USB-C à l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96734-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="96734-156">Mettez l'HoloLens en marche</span><span class="sxs-lookup"><span data-stu-id="96734-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="96734-157">Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.</span><span class="sxs-lookup"><span data-stu-id="96734-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="96734-158">Le technicien peut désormais suivre la OOBE et, une fois terminé, ouvrez l’application Paramètres pour récupérer l’adresse MAC de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="96734-159">Avantages</span><span class="sxs-lookup"><span data-stu-id="96734-159">Benefits</span></span>

<span data-ttu-id="96734-160">Cela permettra, en une « Seule pression » sur l’appareil, d’appliquer le package de configuration correct et d’obtenir l’adresse MAC de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="96734-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="96734-161">Vous pouvez créer les packages de configuration à l’aide des instructions fournies ici.</span><span class="sxs-lookup"><span data-stu-id="96734-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="96734-162">Autopilot avec l’inscription Intune</span><span class="sxs-lookup"><span data-stu-id="96734-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="96734-163">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="96734-163">Requirements</span></span>

- <span data-ttu-id="96734-164">Port réseau câblé avec accès au réseau du client</span><span class="sxs-lookup"><span data-stu-id="96734-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="96734-165">Appareils HoloLens exécutant Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="96734-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="96734-166">Adaptateur Ethernet USB-C compatible HoloLens</span><span class="sxs-lookup"><span data-stu-id="96734-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="96734-167">Intune configuré et activé pour le client du client</span><span class="sxs-lookup"><span data-stu-id="96734-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="96734-168">Appareil inscrit pour Autopilot et importé dans le client du client</span><span class="sxs-lookup"><span data-stu-id="96734-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="96734-169">Stratégies Intune définies pour l’appareil :</span><span class="sxs-lookup"><span data-stu-id="96734-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="96734-170">Certificat et informations sur le réseau sans fil</span><span class="sxs-lookup"><span data-stu-id="96734-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="96734-171">Tout autre paramètre de configuration requis</span><span class="sxs-lookup"><span data-stu-id="96734-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="96734-172">Cela permet à un client ayant besoin d’une configuration réseau avancée d’inscrire les appareils en utilisant une approche pratique et évolutive.</span><span class="sxs-lookup"><span data-stu-id="96734-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="96734-173">Des conditions préalables supplémentaires sont requises comme suit :</span><span class="sxs-lookup"><span data-stu-id="96734-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="96734-174">[Activez le client pour l’aperçu Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span><span class="sxs-lookup"><span data-stu-id="96734-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="96734-175">Créez les stratégies HoloLens pour remplacer le package de configuration dans Intune.</span><span class="sxs-lookup"><span data-stu-id="96734-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="96734-176">Créez les stratégies Intune HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96734-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="96734-177">Attribuez les appareils au groupe approprié.</span><span class="sxs-lookup"><span data-stu-id="96734-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="96734-178">Processus</span><span class="sxs-lookup"><span data-stu-id="96734-178">Process</span></span>

1. <span data-ttu-id="96734-179">Connectez le câble Ethernet à l’adaptateur et branchez-le au port USB-C sur l’appareil HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="96734-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="96734-180">Activer l’HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96734-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="96734-181">L’appareil doit se connecter automatiquement à Internet pendant l’utilisation de la connexion Internet via l’adaptateur Ethernet.</span><span class="sxs-lookup"><span data-stu-id="96734-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="96734-182">Il doit détecter la configuration Autopilot et s’inscrire automatiquement auprès d’Azure AD et d’Intune.</span><span class="sxs-lookup"><span data-stu-id="96734-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="96734-183">L’appareil applique les certificats Wi-Fi requis et d’autres configurations si nécessaire via Intune.</span><span class="sxs-lookup"><span data-stu-id="96734-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="96734-184">Une fois terminé, le technicien peut charger le portail Intune (Gestionnaire de point de terminaison) et effectuer une recherche dans la page des propriétés de l’appareil sur home **-> Devices -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="96734-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="96734-185">L’adresse MAC Wi-Fi sera visible dans le portail Intune.</span><span class="sxs-lookup"><span data-stu-id="96734-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Adresse MAC via Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="96734-187">Le technicien ajoutera cette adresse MAC en tant qu’appareil autorisé.</span><span class="sxs-lookup"><span data-stu-id="96734-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="96734-188">Avantages</span><span class="sxs-lookup"><span data-stu-id="96734-188">Benefits</span></span>

<span data-ttu-id="96734-189">Cela permet une expérience de déploiement « Sans port sur la tête » pour le technicien. Il peut en effet inscrire l’appareil sur Azure AD et Intune sans avoir à le porter ni à interagir manuellement avec l’environnement HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96734-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="96734-190">Notification des adresses MAC au technicien</span><span class="sxs-lookup"><span data-stu-id="96734-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="96734-191">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="96734-191">Requirements</span></span>

- <span data-ttu-id="96734-192">Autorisation de « Intune Graph PowerShell » sur le client</span><span class="sxs-lookup"><span data-stu-id="96734-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="96734-193">Installation du PowerShell Graph Intune sur l’ordinateur du technicien.</span><span class="sxs-lookup"><span data-stu-id="96734-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="96734-194">Accès en lecture aux éléments « Appareils gérés » d’Intune.</span><span class="sxs-lookup"><span data-stu-id="96734-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="96734-195">(Opérateur de support technique ou supérieur, ou rôle personnalisé)</span><span class="sxs-lookup"><span data-stu-id="96734-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="96734-196">Pour l’instant, il n’existe aucun moyen « simple » de déclencher une commande d’automatisation basée sur l’inscription d’un nouvel appareil dans Intune.</span><span class="sxs-lookup"><span data-stu-id="96734-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="96734-197">Par conséquent, cette commande offre au technicien une méthode simple pour récupérer l’adresse MAC sans avoir à se connecter au portail et récupérer celle-ci manuellement.</span><span class="sxs-lookup"><span data-stu-id="96734-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="96734-198">Cette opération renvoie le nom et l’adresse MAC de tous les appareils HoloLens inscrits au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="96734-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Adresse MAC via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="96734-200">Processus</span><span class="sxs-lookup"><span data-stu-id="96734-200">Process</span></span>

<span data-ttu-id="96734-201">Une fois l’inscription à Intune terminée, le technicien exécutait le script ci-dessus pour récupérer l’adresse MAC.</span><span class="sxs-lookup"><span data-stu-id="96734-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
