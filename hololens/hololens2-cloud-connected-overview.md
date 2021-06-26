---
title: Vue d’ensemble de l’assistance à distance de HoloLens 2
description: Apprenez à inscrire des appareils HoloLens 2 sur un réseau connecté au Cloud avec l’assistance à distance Dynamics 365.
keywords: HoloLens, gestion, Cloud connected, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923531"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="f12c7-104">Guide de déploiement – connexion Cloud HoloLens 2 avec l’assistance à distance-vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="f12c7-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="f12c7-105">Ce guide aidera les professionnels de l’informatique à planifier et déployer des appareils Microsoft HoloLens 2 avec l’assistance à distance pour leur organisation.</span><span class="sxs-lookup"><span data-stu-id="f12c7-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="f12c7-106">Cela servira de modèle pour les déploiements de preuve de concept dans votre organisation, dans différents cas d’utilisation de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f12c7-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="f12c7-107">Le programme d’installation est similaire au [scénario A : déployer sur des appareils Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span><span class="sxs-lookup"><span data-stu-id="f12c7-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="f12c7-108">Dans le cadre de ce guide, nous allons aborder l’inscription de vos appareils dans la gestion des appareils, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser immédiatement l’assistance à distance lors de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f12c7-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="f12c7-109">Pour ce faire, nous allons passer en revue les éléments importants de l’infrastructure nécessaire à la configuration et à l’exécution, ce qui permet un déploiement à l’échelle avec HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f12c7-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="f12c7-110">Aucune autre restriction ou configuration d’appareil ne sera appliquée dans ce guide. Toutefois, nous vous encourageons à explorer ces options après avoir terminé.</span><span class="sxs-lookup"><span data-stu-id="f12c7-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f12c7-111">Prérequis</span><span class="sxs-lookup"><span data-stu-id="f12c7-111">Prerequisites</span></span>

<span data-ttu-id="f12c7-112">L’infrastructure suivante doit être en place pour déployer le HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f12c7-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="f12c7-113">Si ce n’est pas le cas, la configuration d’Azure et d’Intune est incluse dans ce guide :</span><span class="sxs-lookup"><span data-stu-id="f12c7-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="f12c7-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f12c7-114">Wi-Fi</span></span>
    - <span data-ttu-id="f12c7-115">Les réseaux sont généralement ouverts sur Internet et les services de Cloud Computing</span><span class="sxs-lookup"><span data-stu-id="f12c7-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="f12c7-116">Jonction de Azure Active Directory (Azure AD) avec l’inscription automatique MDM ([Azure ad abonnement P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) requis)</span><span class="sxs-lookup"><span data-stu-id="f12c7-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="f12c7-117">Gestion MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="f12c7-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="f12c7-118">Une ou plusieurs applications sont déployées via MDM.</span><span class="sxs-lookup"><span data-stu-id="f12c7-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="f12c7-119">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="f12c7-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="f12c7-120">Un ou plusieurs utilisateurs par appareil sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f12c7-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Scénario connecté au Cloud" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="f12c7-122">En savoir plus sur l’assistance à distance</span><span class="sxs-lookup"><span data-stu-id="f12c7-122">Learn about Remote Assist</span></span>

<span data-ttu-id="f12c7-123">L’assistance à distance permet la maintenance et la réparation collaboratives, l’inspection à distance, ainsi que le partage des connaissances et la formation.</span><span class="sxs-lookup"><span data-stu-id="f12c7-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="f12c7-124">En connectant des personnes dans des rôles et des emplacements différents, un technicien utilisant l’assistance à distance peut se connecter à un collaborateur distant de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f12c7-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="f12c7-125">Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre les problèmes en temps réel, même lorsqu’ils ne sont pas&#39;t au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="f12c7-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="f12c7-126">Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles que le technicien&#39;l’espace physique pour qu’ils puissent faire référence au schéma tout en récapitulant les mains et les mains libres sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f12c7-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="f12c7-127">Licences et exigences de l’assistance à distance</span><span class="sxs-lookup"><span data-stu-id="f12c7-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="f12c7-128">Compte Azure AD (requis pour l’achat de l’abonnement et l’attribution de licences)</span><span class="sxs-lookup"><span data-stu-id="f12c7-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="f12c7-129">[Abonnement à distance Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [essai d’assistance à distance](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="f12c7-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="f12c7-130">Utilisateur de l’assistance à distance Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f12c7-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="f12c7-131">Licence d’assistance à distance</span><span class="sxs-lookup"><span data-stu-id="f12c7-131">Remote Assist license</span></span>
- <span data-ttu-id="f12c7-132">Connectivité réseau</span><span class="sxs-lookup"><span data-stu-id="f12c7-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="f12c7-133">Utilisateur Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f12c7-133">Microsoft Teams user</span></span>

- <span data-ttu-id="f12c7-134">Équipes Microsoft teams ou [Team freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="f12c7-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="f12c7-135">Connectivité réseau</span><span class="sxs-lookup"><span data-stu-id="f12c7-135">Network connectivity</span></span>

<span data-ttu-id="f12c7-136">Si vous envisagez d’implémenter ce [scénario inter-clients](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), vous aurez peut-être besoin d’une licence de barrières d’information.</span><span class="sxs-lookup"><span data-stu-id="f12c7-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="f12c7-137">Consultez [cet article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) pour déterminer si une licence de cloisonnement des informations est requise.</span><span class="sxs-lookup"><span data-stu-id="f12c7-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="f12c7-138">Dans ce guide, vous allez :</span><span class="sxs-lookup"><span data-stu-id="f12c7-138">In this guide you will:</span></span>

<span data-ttu-id="f12c7-139">Préparation :</span><span class="sxs-lookup"><span data-stu-id="f12c7-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f12c7-140">En savoir plus sur les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f12c7-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="f12c7-141">En savoir plus sur les Azure AD et en configurer une si vous ne l’avez pas&#39;.</span><span class="sxs-lookup"><span data-stu-id="f12c7-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="f12c7-142">En savoir plus sur la gestion des identités et sur la façon de configurer au mieux les comptes Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f12c7-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="f12c7-143">Apprenez-en davantage sur MDM et configurez avec Intune si&#39;vous n’avez pas déjà un prêt.</span><span class="sxs-lookup"><span data-stu-id="f12c7-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="f12c7-144">En savoir plus sur les exigences de mise en réseau de l’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="f12c7-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="f12c7-145">Éventuellement : VPN pour se connecter aux ressources de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="f12c7-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="f12c7-146">Configurer :</span><span class="sxs-lookup"><span data-stu-id="f12c7-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f12c7-147">Comment créer des utilisateurs et des groupes.</span><span class="sxs-lookup"><span data-stu-id="f12c7-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="f12c7-148">Comment configurer l’inscription automatique dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f12c7-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="f12c7-149">Comment attribuer vos licences d’application.</span><span class="sxs-lookup"><span data-stu-id="f12c7-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="f12c7-150">Deploy :</span><span class="sxs-lookup"><span data-stu-id="f12c7-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f12c7-151">Configurez votre HoloLens 2 et validez l’inscription.</span><span class="sxs-lookup"><span data-stu-id="f12c7-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="f12c7-152">Valider, vous pouvez effectuer un appel d’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="f12c7-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="f12c7-153">Mise à jour :</span><span class="sxs-lookup"><span data-stu-id="f12c7-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f12c7-154">Comment mettre à jour l’assistance à distance à l’aide de l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f12c7-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="f12c7-155">Création d’un plan de support.</span><span class="sxs-lookup"><span data-stu-id="f12c7-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="f12c7-156">Plan de développement.</span><span class="sxs-lookup"><span data-stu-id="f12c7-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="f12c7-157">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="f12c7-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f12c7-158">Déploiement connecté au Cloud-préparer</span><span class="sxs-lookup"><span data-stu-id="f12c7-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

