---
title: Scénarios courants de déploiement d’infrastructure
description: Quelques scénarios de déploiement courants basés sur différentes infrastructures communes
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253071"
---
# <span data-ttu-id="78d76-104">Présentation courante des scénarios de déploiement d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="78d76-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="78d76-105">Les informations suivantes fournissent une présentation de l’architecture de haut niveau pour trois scénarios courants lors du déploiement et de la gestion des appareils Microsoft HoloLens 2 au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="78d76-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="78d76-106">Le mode de gestion de vos appareils et l’accès aux ressources de votre organisation sont principalement déterminés en fonction de facteurs déjà en vigueur.</span><span class="sxs-lookup"><span data-stu-id="78d76-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="78d76-107">Sur la base de l’infrastructure existante, nous vous invitons à passer en revue le style de gestion commune des appareils dans les scénarios suivants et à tester nos guides de déploiement dans le scénario correspondant à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="78d76-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="78d76-108">Scénarios</span><span class="sxs-lookup"><span data-stu-id="78d76-108">Scenarios</span></span>

<span data-ttu-id="78d76-109">Le diagramme ci-dessous représente trois scénarios typiques de déploiements HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="78d76-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagramme de scénarios](images/scenarios.jpg)

### <span data-ttu-id="78d76-111">Scénario A: déploiement vers des appareils de connexion dans le Cloud</span><span class="sxs-lookup"><span data-stu-id="78d76-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="78d76-112">HoloLens 2 est déployé pour une utilisation essentiellement dans les environnements externes à un réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="78d76-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="78d76-113">Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées via un réseau VPN.</span><span class="sxs-lookup"><span data-stu-id="78d76-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="78d76-114">Ce déploiement est semblable aux appareils mobiles gérés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="78d76-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="78d76-115">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="78d76-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="78d76-116">En général, les réseaux Wi-Fi sont entièrement ouverts sur Internet et les services Cloud.</span><span class="sxs-lookup"><span data-stu-id="78d76-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="78d76-117">Accès Azure AD à l’inscription automatique de la gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="78d76-117">Azure AD Join with MDM Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="78d76-118">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="78d76-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="78d76-119">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="78d76-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="78d76-120">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="78d76-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="78d76-121">Une ou plusieurs applications sont déployées via la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="78d76-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="78d76-122">Défis courants</span><span class="sxs-lookup"><span data-stu-id="78d76-122">Common Challenges</span></span>
   * <span data-ttu-id="78d76-123">Détermination des configurations de la gestion des périphériques mobiles à appliquer à HoloLens 2 en fonction de la configuration requise pour les scénarios.</span><span class="sxs-lookup"><span data-stu-id="78d76-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="78d76-124">Pour un guide de déploiement similaire au scénario A, consultez notre guide pour le [Cloud connecté à l’assistance à distance](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78d76-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78d76-125">Guide de déploiement – technologie HoloLens 2 dans le Cloud connecté à l’assistance à distance</span><span class="sxs-lookup"><span data-stu-id="78d76-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="78d76-126">Scénario B: déploiement au sein du réseau de votre organisation</span><span class="sxs-lookup"><span data-stu-id="78d76-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="78d76-127">HoloLens 2 est déployé pour une utilisation essentiellement sur le réseau d’entreprise avec l’accès aux ressources internes de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="78d76-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="78d76-128">Les services Internet et Cloud risquent d’être limités.</span><span class="sxs-lookup"><span data-stu-id="78d76-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="78d76-129">Ce déploiement est un déploiement standard pour la plupart des PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="78d76-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="78d76-130">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="78d76-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="78d76-131">Wi-Fi réseau est un réseau d’entreprise interne avec accès à des ressources internes et accès limité aux services Internet ou Cloud.</span><span class="sxs-lookup"><span data-stu-id="78d76-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="78d76-132">Accès Azure AD avec l’inscription automatique GPM</span><span class="sxs-lookup"><span data-stu-id="78d76-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="78d76-133">Gestion de la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="78d76-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="78d76-134">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="78d76-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="78d76-135">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="78d76-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="78d76-136">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="78d76-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="78d76-137">Une ou plusieurs applications sont déployées via la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="78d76-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="78d76-138">Défis courants</span><span class="sxs-lookup"><span data-stu-id="78d76-138">Common Challenges</span></span>
   * <span data-ttu-id="78d76-139">HoloLens 2 ne prend pas en charge les jointures publicitaire locales ou SCCM.</span><span class="sxs-lookup"><span data-stu-id="78d76-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="78d76-140">Uniquement Azure AD Join avec la gestion des périphériques mobiles.</span><span class="sxs-lookup"><span data-stu-id="78d76-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="78d76-141">Dans de nombreux cas, les entreprises déploient actuellement des PC Windows 10 dans le cadre de ce scénario, en ce qui concerne les appareils joints d’annonces publicitaires, gérés par System Center Configuration Manager (SCCM) et ne disposent pas de l’infrastructure déployée/configurée pour gérer les appareils Windows 10 internes via des solutions de gestion du Cloud Computing.</span><span class="sxs-lookup"><span data-stu-id="78d76-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="78d76-142">Comme HoloLens 2 est un premier appareil Cloud, il repose fortement sur Internet et les services connectés au Cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion de la gestion des périphériques mobiles, etc. Lorsque vous vous connectez à un réseau d’entreprise, les règles de proxy et de pare-feu doivent être ajustées afin d’activer l’accès à HoloLens 2 et aux applications qui s’exécutent sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="78d76-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="78d76-143">La connectivité entreprise Wi-Fi nécessite généralement des certificats pour authentifier l’appareil ou l’utilisateur auprès du réseau.</span><span class="sxs-lookup"><span data-stu-id="78d76-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="78d76-144">L’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via la gestion des périphériques mobiles peuvent être difficiles à configurer.</span><span class="sxs-lookup"><span data-stu-id="78d76-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="78d76-145">Scénario C: déploiement dans un environnement hors connexion sécurisé</span><span class="sxs-lookup"><span data-stu-id="78d76-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="78d76-146">HoloLens 2 est déployé pour une utilisation essentiellement hors connexion sans réseau ou accès Internet.</span><span class="sxs-lookup"><span data-stu-id="78d76-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="78d76-147">Il s’agit d’un déploiement standard pour des emplacements particulièrement sécurisés ou confidentiels.</span><span class="sxs-lookup"><span data-stu-id="78d76-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="78d76-148">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="78d76-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="78d76-149">Wi-Fi connectivité est désactivée.</span><span class="sxs-lookup"><span data-stu-id="78d76-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="78d76-150">Ethernet par le biais du bus USB, si nécessaire, la connectivité LAN est activée.</span><span class="sxs-lookup"><span data-stu-id="78d76-150">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="78d76-151">Non géré.</span><span class="sxs-lookup"><span data-stu-id="78d76-151">Not Managed.</span></span>
   * <span data-ttu-id="78d76-152">Compte d’utilisateur local pour la connexion de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78d76-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="78d76-153">HoloLens 2 ne prend en charge qu’un seul compte local.</span><span class="sxs-lookup"><span data-stu-id="78d76-153">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="78d76-154">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués via des packages de mise en service en fonction de cas d’utilisation spécifiques.</span><span class="sxs-lookup"><span data-stu-id="78d76-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="78d76-155">Ces configurations sont généralement très limitées en raison de la configuration requise pour l’environnement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="78d76-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="78d76-156">Une ou plusieurs applications sont déployées via le package de mise à service</span><span class="sxs-lookup"><span data-stu-id="78d76-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="78d76-157">Défis courants</span><span class="sxs-lookup"><span data-stu-id="78d76-157">Common Challenges</span></span>
   * <span data-ttu-id="78d76-158">Un ensemble de configurations limité est disponible via les packages de mise en service</span><span class="sxs-lookup"><span data-stu-id="78d76-158">There is a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="78d76-159">Les services Cloud ne peuvent pas être utilisés, ce qui a pour effet de limiter les fonctionnalités HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="78d76-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="78d76-160">Augmentation des frais d’administration par le biais de ces périphériques, configurés et mis à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="78d76-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="78d76-161">Pour un guide de déploiement similaire à celui-ci, consultez notre [Guide de déploiement sécurisé hors connexion](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="78d76-161">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78d76-162">Guide de déploiement – sécurité HoloLens 2 hors connexion</span><span class="sxs-lookup"><span data-stu-id="78d76-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
