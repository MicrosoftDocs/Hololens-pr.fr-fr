---
title: Scénarios courants de déploiement d’infrastructure
description: Découvrez quelques-uns des scénarios de déploiement les plus courants en fonction de différents déploiements d’infrastructure pour la réalité mixte.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397416"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="d118b-104">Vue d’ensemble des scénarios courants de déploiement d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="d118b-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="d118b-105">Les informations suivantes fournissent une vue d’ensemble de l’architecture de haut niveau pour trois scénarios courants lors du déploiement et de la gestion d’appareils Microsoft HoloLens 2 au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d118b-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="d118b-106">Souvent, la façon dont vous gérez vos appareils et comment accéder aux ressources de votre organisation est largement déterminée par les facteurs déjà en place.</span><span class="sxs-lookup"><span data-stu-id="d118b-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="d118b-107">Sur la base de l’infrastructure existante, nous vous invitons à passer en revue le style de gestion des appareils communs dans les scénarios suivants et à essayer nos guides de déploiement dans le scénario correspondant à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="d118b-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d118b-108">Scénarios</span><span class="sxs-lookup"><span data-stu-id="d118b-108">Scenarios</span></span>

<span data-ttu-id="d118b-109">Le diagramme ci-dessous représente deux scénarios managés typiques pour les déploiements HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d118b-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="d118b-110">Il existe également un troisième scénario qui permet des déploiements sécurisés hors connexion.</span><span class="sxs-lookup"><span data-stu-id="d118b-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="d118b-111">Scénario A : déployer sur des appareils connectés au Cloud</span><span class="sxs-lookup"><span data-stu-id="d118b-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="d118b-112">HoloLens 2 est déployé pour une utilisation principalement dans des environnements externes à un réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d118b-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="d118b-113">Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées par le biais du VPN.</span><span class="sxs-lookup"><span data-stu-id="d118b-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="d118b-114">Ce déploiement est similaire à celui des appareils mobiles gérés au sein d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="d118b-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="d118b-115">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="d118b-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="d118b-116">Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing.</span><span class="sxs-lookup"><span data-stu-id="d118b-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="d118b-117">Azure AD rejoindre avec l’inscription automatique de gestion des appareils mobiles (MDM)-gestion de MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="d118b-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d118b-118">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d118b-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d118b-119">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="d118b-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d118b-120">Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="d118b-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d118b-121">Une ou plusieurs applications sont déployées via MDM</span><span class="sxs-lookup"><span data-stu-id="d118b-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="d118b-122">Défis courants</span><span class="sxs-lookup"><span data-stu-id="d118b-122">Common Challenges</span></span>
   * <span data-ttu-id="d118b-123">Détermination des configurations MDM à appliquer à HoloLens 2 en fonction des spécifications du scénario.</span><span class="sxs-lookup"><span data-stu-id="d118b-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="d118b-124">[![Diagramme ](images/deployment-guides-revised-scenario-a.png) de scénario](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d118b-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="d118b-125">Pour obtenir un guide de déploiement similaire à ce scénario, consultez notre guide du Guide de déploiement d’un [environnement connecté au Cloud](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d118b-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d118b-126">Guide de déploiement de l’environnement connecté au Cloud</span><span class="sxs-lookup"><span data-stu-id="d118b-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="d118b-127">Guide de déploiement de l’environnement connecté au Cloud (clients externes)</span><span class="sxs-lookup"><span data-stu-id="d118b-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="d118b-128">Scénario B : déployer à l’intérieur du réseau de votre organisation</span><span class="sxs-lookup"><span data-stu-id="d118b-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="d118b-129">HoloLens 2 est déployé pour être principalement utilisé sur le réseau d’entreprise avec un accès aux ressources d’entreprise internes.</span><span class="sxs-lookup"><span data-stu-id="d118b-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="d118b-130">Internet et les services de Cloud Computing peuvent être limités.</span><span class="sxs-lookup"><span data-stu-id="d118b-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="d118b-131">Ce déploiement est un déploiement classique pour la plupart des PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d118b-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="d118b-132">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="d118b-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="d118b-133">Wi-Fi réseau est un réseau d’entreprise interne avec accès aux ressources internes et un accès limité à Internet ou aux services Cloud.</span><span class="sxs-lookup"><span data-stu-id="d118b-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="d118b-134">Joindre Azure AD avec l’inscription automatique MDM</span><span class="sxs-lookup"><span data-stu-id="d118b-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="d118b-135">Gestion MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="d118b-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d118b-136">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d118b-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d118b-137">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="d118b-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d118b-138">Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="d118b-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d118b-139">Une ou plusieurs applications sont déployées via MDM</span><span class="sxs-lookup"><span data-stu-id="d118b-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="d118b-140">Défis courants</span><span class="sxs-lookup"><span data-stu-id="d118b-140">Common Challenges</span></span>
   * <span data-ttu-id="d118b-141">HoloLens 2 ne prend pas en charge la jointure AD locale ou SCCM.</span><span class="sxs-lookup"><span data-stu-id="d118b-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="d118b-142">Seule Azure AD rejoindre avec MDM.</span><span class="sxs-lookup"><span data-stu-id="d118b-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="d118b-143">De nombreuses entreprises déploient toujours des PC Windows 10 dans ce scénario en tant qu’appareils intégrés à Active Directory, gérés par System Center Configuration Manager (SCCM) et peuvent ne pas avoir l’infrastructure déployée/configurée pour la gestion des appareils Windows 10 internes via des solutions MDM basées sur le Cloud.</span><span class="sxs-lookup"><span data-stu-id="d118b-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="d118b-144">Étant donné que HoloLens 2 est un premier appareil Cloud, il s’appuie fortement sur Internet et les services connectés au Cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion MDM, etc.</span><span class="sxs-lookup"><span data-stu-id="d118b-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="d118b-145">Lors de la connexion à un réseau d’entreprise, il est probable que les règles de proxy/pare-feu doivent être ajustées pour permettre l’accès à HoloLens 2 et aux applications qui s’y exécutent.</span><span class="sxs-lookup"><span data-stu-id="d118b-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="d118b-146">La connectivité des Wi-Fi d’entreprise requiert généralement des certificats pour authentifier l’appareil ou l’utilisateur sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="d118b-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="d118b-147">L’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via MDM peuvent être difficiles à configurer.</span><span class="sxs-lookup"><span data-stu-id="d118b-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="d118b-148">[![Diagramme ](images/deployment-guides-revised-scenario-b-01-1.png) du scénario B1](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d118b-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="d118b-149">[![Diagramme ](images/deployment-guides-revised-scenario-b-02-1.png) du scénario B2](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d118b-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="d118b-150">Pour obtenir un guide de déploiement similaire à ce scénario, consultez notre guide du Guide de déploiement d’un [réseau d’entreprise](hololens2-corp-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d118b-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d118b-151">Guide de déploiement du réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d118b-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="d118b-152">Scénario C : déployer dans un environnement hors connexion sécurisé</span><span class="sxs-lookup"><span data-stu-id="d118b-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="d118b-153">HoloLens 2 est déployé pour une utilisation hors connexion principale sans accès réseau ou Internet.</span><span class="sxs-lookup"><span data-stu-id="d118b-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="d118b-154">Il s’agit d’un déploiement classique pour des emplacements hautement sécurisés ou confidentiels.</span><span class="sxs-lookup"><span data-stu-id="d118b-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="d118b-155">Configurations courantes de base</span><span class="sxs-lookup"><span data-stu-id="d118b-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="d118b-156">La connectivité Wi-Fi est désactivée.</span><span class="sxs-lookup"><span data-stu-id="d118b-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="d118b-157">Si nécessaire, Ethernet via USB peut être activé pour la connectivité LAN.</span><span class="sxs-lookup"><span data-stu-id="d118b-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="d118b-158">Non géré.</span><span class="sxs-lookup"><span data-stu-id="d118b-158">Not Managed.</span></span>
   * <span data-ttu-id="d118b-159">Compte d’utilisateur local pour la connexion de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="d118b-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="d118b-160">HoloLens 2 ne prend en charge qu’un seul compte local.</span><span class="sxs-lookup"><span data-stu-id="d118b-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="d118b-161">Différents niveaux de configurations de verrouillage de périphérique sont appliqués par le biais de packages d’approvisionnement basés sur des cas d’utilisation spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d118b-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="d118b-162">Ces configurations sont généralement limitées en raison de la configuration requise de l’environnement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="d118b-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="d118b-163">Une ou plusieurs applications sont déployées par le biais du package d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="d118b-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="d118b-164">Défis courants</span><span class="sxs-lookup"><span data-stu-id="d118b-164">Common Challenges</span></span>
   * <span data-ttu-id="d118b-165">Il existe un ensemble limité de configurations disponibles par le biais de packages de provisionnement</span><span class="sxs-lookup"><span data-stu-id="d118b-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="d118b-166">Les services Cloud ne peuvent pas être utilisés, limitant ainsi les fonctionnalités HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d118b-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="d118b-167">Plus grande surcharge administrative, car ces appareils doivent être configurés, configurés et mis à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="d118b-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="d118b-168">[![Diagramme sécurisé hors connexion 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d118b-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="d118b-169">Pour obtenir un guide de déploiement similaire à ce scénario, consultez notre guide de déploiement de l' [environnement sécurisé en mode hors connexion](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="d118b-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d118b-170">Guide de déploiement de l’environnement sécurisé hors connexion</span><span class="sxs-lookup"><span data-stu-id="d118b-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
