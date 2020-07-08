---
title: Scénarios courants de déploiement d’infrastructure
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857889"
---
# <span data-ttu-id="3a543-103">Scénarios courants de déploiement d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="3a543-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="3a543-104">Les informations suivantes fournissent une présentation de l’architecture de haut niveau pour trois scénarios courants lors du déploiement et de la gestion des appareils Microsoft HoloLens 2 au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a543-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="3a543-105">Scénarios</span><span class="sxs-lookup"><span data-stu-id="3a543-105">Scenarios</span></span>

<span data-ttu-id="3a543-106">Le diagramme ci-dessous représente trois scénarios typiques de déploiements HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3a543-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![scénarios](images/scenarios.jpg)

### <span data-ttu-id="3a543-108">Scénario A</span><span class="sxs-lookup"><span data-stu-id="3a543-108">Scenario A</span></span>

<span data-ttu-id="3a543-109">HoloLens 2 est déployé pour une utilisation essentiellement dans les environnements externes à un réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a543-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="3a543-110">Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées via un réseau VPN.</span><span class="sxs-lookup"><span data-stu-id="3a543-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="3a543-111">Il s’agit d’un déploiement très similaire aux appareils mobiles gérés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a543-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="3a543-112">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="3a543-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="3a543-113">Les réseaux Wi-Fi sont généralement ouverts sur Internet et les services Cloud.</span><span class="sxs-lookup"><span data-stu-id="3a543-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="3a543-114">Accès Azure AD à l’inscription automatique de la gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="3a543-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="3a543-115">Les utilisateurs se connectent avec leur propre compte d’entreprise (AAD)</span><span class="sxs-lookup"><span data-stu-id="3a543-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="3a543-116">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="3a543-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="3a543-117">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="3a543-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="3a543-118">Une ou plusieurs applications sont déployées via la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="3a543-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="3a543-119">Défis courants</span><span class="sxs-lookup"><span data-stu-id="3a543-119">Common Challenges</span></span>
   * <span data-ttu-id="3a543-120">Détermination des configurations de la gestion des périphériques mobiles à appliquer à HoloLens 2 en fonction de la configuration requise pour les scénarios.</span><span class="sxs-lookup"><span data-stu-id="3a543-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="3a543-121">Scénario B</span><span class="sxs-lookup"><span data-stu-id="3a543-121">Scenario B</span></span>

<span data-ttu-id="3a543-122">HoloLens 2 est déployé pour une utilisation essentiellement sur le réseau d’entreprise avec l’accès aux ressources internes de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3a543-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="3a543-123">Les services Internet et Cloud risquent d’être limités.</span><span class="sxs-lookup"><span data-stu-id="3a543-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="3a543-124">Il s’agit d’un déploiement standard pour la plupart des PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3a543-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="3a543-125">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="3a543-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="3a543-126">Le réseau Wi-Fi est un réseau d’entreprise interne qui permet d’accéder à des ressources internes et un accès limité aux services Internet ou Cloud.</span><span class="sxs-lookup"><span data-stu-id="3a543-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="3a543-127">Accès Azure AD avec l’inscription automatique GPM</span><span class="sxs-lookup"><span data-stu-id="3a543-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="3a543-128">Gestion de la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="3a543-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="3a543-129">Les utilisateurs se connectent avec leur propre compte d’entreprise (AAD)</span><span class="sxs-lookup"><span data-stu-id="3a543-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="3a543-130">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="3a543-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="3a543-131">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="3a543-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="3a543-132">Une ou plusieurs applications sont déployées via la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="3a543-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="3a543-133">Défis courants</span><span class="sxs-lookup"><span data-stu-id="3a543-133">Common Challenges</span></span>
   * <span data-ttu-id="3a543-134">HoloLens 2 ne prend pas en charge les jointures publicitaire locales ou SCCM.</span><span class="sxs-lookup"><span data-stu-id="3a543-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="3a543-135">Uniquement Azure AD Join avec la gestion des périphériques mobiles.</span><span class="sxs-lookup"><span data-stu-id="3a543-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="3a543-136">Dans de nombreux cas, de nombreuses entreprises déploient actuellement des PC Windows 10 dans le cadre de ce scénario, en fonction des appareils d’annonce d’annonces sur site, gérés par System Center Configuration Manager (SCCM) et ne disposent pas de l’infrastructure déployée/configurée pour gérer les appareils Windows 10 internes via des solutions de gestion du Cloud Computing.</span><span class="sxs-lookup"><span data-stu-id="3a543-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="3a543-137">Comme HoloLens 2 est un premier appareil Cloud, il repose fortement sur Internet et les services connectés au Cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion de la gestion des périphériques mobiles, etc. Lorsque vous vous connectez à un réseau d’entreprise, les règles de proxy et de pare-feu doivent être ajustées afin d’activer l’accès à HoloLens 2 et aux applications qui s’exécutent sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="3a543-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="3a543-138">La connectivité Wi-Fi d’entreprise nécessite généralement des certificats pour authentifier l’appareil ou l’utilisateur sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="3a543-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="3a543-139">L’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via la gestion des périphériques mobiles peuvent être difficiles à configurer.</span><span class="sxs-lookup"><span data-stu-id="3a543-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="3a543-140">Scénario C</span><span class="sxs-lookup"><span data-stu-id="3a543-140">Scenario C</span></span>

<span data-ttu-id="3a543-141">HoloLens 2 est déployé pour une utilisation essentiellement hors connexion sans réseau ou accès Internet.</span><span class="sxs-lookup"><span data-stu-id="3a543-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="3a543-142">Il s’agit d’un déploiement standard pour des emplacements particulièrement sécurisés ou confidentiels.</span><span class="sxs-lookup"><span data-stu-id="3a543-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="3a543-143">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="3a543-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="3a543-144">La connectivité Wi-Fi est désactivée.</span><span class="sxs-lookup"><span data-stu-id="3a543-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="3a543-145">Ethernet par le biais du bus USB, si nécessaire, la connectivité LAN est activée.</span><span class="sxs-lookup"><span data-stu-id="3a543-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="3a543-146">Non géré.</span><span class="sxs-lookup"><span data-stu-id="3a543-146">Not Managed.</span></span>
   * <span data-ttu-id="3a543-147">Compte d’utilisateur local pour la connexion de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="3a543-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="3a543-148">HoloLens 2 ne prend en charge qu’un seul compte local.</span><span class="sxs-lookup"><span data-stu-id="3a543-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="3a543-149">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués via des packages de mise en service en fonction de cas d’utilisation spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3a543-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="3a543-150">Ces configurations sont généralement très limitées en raison de la configuration requise pour l’environnement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="3a543-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="3a543-151">Une ou plusieurs applications sont déployées via le package de mise à service</span><span class="sxs-lookup"><span data-stu-id="3a543-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="3a543-152">Défis courants</span><span class="sxs-lookup"><span data-stu-id="3a543-152">Common Challenges</span></span>
   * <span data-ttu-id="3a543-153">Un ensemble de configurations limité est disponible via les packages de mise en service</span><span class="sxs-lookup"><span data-stu-id="3a543-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="3a543-154">Les services Cloud ne peuvent pas être utilisés, ce qui a pour effet de limiter les fonctionnalités HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3a543-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="3a543-155">Augmentation des frais d’administration par le biais de ces périphériques, configurés et mis à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="3a543-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
