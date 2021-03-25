---
title: Guide de déploiement – HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Vue d’ensemble
description: Découvrez comment inscrire des appareils HoloLens 2 à l’aide de guides Dynamics 365 sur un réseau connecté d’entreprise.
keywords: HoloLens, gestion, connecté à l’entreprise, guides Dynamics 365, AAD, Azure AD, GESTION DES PÉRIPHÉRIQUES MOBILES, Gestion des appareils mobiles
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448543"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="62d28-104">Guide de déploiement - HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="62d28-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="62d28-105">Ce guide aidera les professionnels de l’informatique à planifier et déployer des appareils Microsoft HoloLens 2 à l’aide de guides (Guides) Dynamics 365 dans leur organisation.</span><span class="sxs-lookup"><span data-stu-id="62d28-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="62d28-106">Ce guide est idéal pour les déploiements pilotes et de production et est semblable au scénario B : Déployer à [l’intérieur](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) du guide réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="62d28-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="62d28-107">Après avoir testé votre preuve de concept, utilisez ce guide pour aller de l’avant avec l’intégration de HoloLens dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="62d28-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="62d28-108">Dans ce guide, nous allons apprendre à inscrire vos appareils dans votre gestion d’appareils existante, à appliquer des licences selon vos besoins et à vérifier que vos utilisateurs finaux sont en mesure d’utiliser un Guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la mise en place de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="62d28-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="62d28-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="62d28-109">Prerequisites</span></span>

<span data-ttu-id="62d28-110">L’infrastructure suivante doit déjà être en place :</span><span class="sxs-lookup"><span data-stu-id="62d28-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="62d28-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="62d28-111">Wi-Fi</span></span>
    - <span data-ttu-id="62d28-112">Réseau d’entreprise interne avec accès aux ressources internes et accès limité aux services Internet ou Cloud</span><span class="sxs-lookup"><span data-stu-id="62d28-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="62d28-113">Authentification de certificat basée sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="62d28-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="62d28-114">Joindre Azure Active Directory (Azure AD) avec inscription automatique MDM[(abonnement Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) requis)</span><span class="sxs-lookup"><span data-stu-id="62d28-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="62d28-115">Gestion de la gestion des mdm (Intune)</span><span class="sxs-lookup"><span data-stu-id="62d28-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="62d28-116">Une ou plusieurs applications sont déployées via la gestion des applications mobiles.</span><span class="sxs-lookup"><span data-stu-id="62d28-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="62d28-117">Network</span><span class="sxs-lookup"><span data-stu-id="62d28-117">Network</span></span> 
    - <span data-ttu-id="62d28-118">Certificats (SCEP ou PKCS)</span><span class="sxs-lookup"><span data-stu-id="62d28-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="62d28-119">Configuration du proxy</span><span class="sxs-lookup"><span data-stu-id="62d28-119">Proxy configuration</span></span>
- <span data-ttu-id="62d28-120">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="62d28-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="62d28-121">Un ou plusieurs utilisateurs par appareil sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="62d28-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="62d28-122">Différents niveaux de configurations de verrouillage d’appareil appliqués en fonction de cas d’utilisation spécifiques, de l’ouverture complète à la borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="62d28-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="62d28-123">Guide des licences et des conditions requises</span><span class="sxs-lookup"><span data-stu-id="62d28-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="62d28-124">Compte Azure AD</span><span class="sxs-lookup"><span data-stu-id="62d28-124">Azure AD account</span></span>
- <span data-ttu-id="62d28-125">Dynamics 365 Guides applications PC and HoloLens</span><span class="sxs-lookup"><span data-stu-id="62d28-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="62d28-126">Abonnement aux guides Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="62d28-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="62d28-127">Microsoft Dataverse (inclus)</span><span class="sxs-lookup"><span data-stu-id="62d28-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="62d28-128">Power Apps (inclus)</span><span class="sxs-lookup"><span data-stu-id="62d28-128">Power Apps (included)</span></span>
- <span data-ttu-id="62d28-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="62d28-129">Power BI Desktop</span></span>
- <span data-ttu-id="62d28-130">Connectivité réseau</span><span class="sxs-lookup"><span data-stu-id="62d28-130">Network Connectivity</span></span>

![Diagramme réseau connecté à l’entreprise](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="62d28-132">Étapes de déploiement</span><span class="sxs-lookup"><span data-stu-id="62d28-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="62d28-133">Préparation</span><span class="sxs-lookup"><span data-stu-id="62d28-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="62d28-134">Découvrez les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="62d28-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="62d28-135">En savoir plus sur Azure AD et en configurer un si vous ne l’avez pas.</span><span class="sxs-lookup"><span data-stu-id="62d28-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="62d28-136">Découvrez la gestion des identités et la meilleure façon de configurer les comptes Azure AD.</span><span class="sxs-lookup"><span data-stu-id="62d28-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="62d28-137">En savoir plus sur la gestion des mdm et la configurer avec Intune si vous n’en avez pas déjà un.</span><span class="sxs-lookup"><span data-stu-id="62d28-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="62d28-138">Familiarisez-vous avec le Wi-Fi basé sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="62d28-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="62d28-139">Familiarisez-vous avec le proxy.</span><span class="sxs-lookup"><span data-stu-id="62d28-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="62d28-140">Comprendre comment vous pouvez utiliser les applications métier.</span><span class="sxs-lookup"><span data-stu-id="62d28-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="62d28-141">En savoir plus sur la façon dont vous pouvez utiliser les Guides pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="62d28-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="62d28-142">Configurer</span><span class="sxs-lookup"><span data-stu-id="62d28-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="62d28-143">Comment créer des utilisateurs et des groupes.</span><span class="sxs-lookup"><span data-stu-id="62d28-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="62d28-144">Comment configurer l’inscription automatique.</span><span class="sxs-lookup"><span data-stu-id="62d28-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="62d28-145">Comment configurer des certificats Wi-Fi et des profils pour la connectivité Wi-Fi entreprise.</span><span class="sxs-lookup"><span data-stu-id="62d28-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="62d28-146">Charger et affecter des packages d’application métier.</span><span class="sxs-lookup"><span data-stu-id="62d28-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="62d28-147">Configurer les guides Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="62d28-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="62d28-148">Comment configurer le mode plein écran (facultatif).</span><span class="sxs-lookup"><span data-stu-id="62d28-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="62d28-149">Comment configurer WDAC (facultatif).</span><span class="sxs-lookup"><span data-stu-id="62d28-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="62d28-150">Déployer</span><span class="sxs-lookup"><span data-stu-id="62d28-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="62d28-151">Valider l’inscription via l’appareil et la gestion des périphériques de gestion des périphériques.</span><span class="sxs-lookup"><span data-stu-id="62d28-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="62d28-152">Validez Wi-Fi certificats.</span><span class="sxs-lookup"><span data-stu-id="62d28-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="62d28-153">Valider l’installation de l’application LOB.</span><span class="sxs-lookup"><span data-stu-id="62d28-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="62d28-154">Valider les guides via la authoring et le fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="62d28-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="62d28-155">Maintenir</span><span class="sxs-lookup"><span data-stu-id="62d28-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="62d28-156">Mettez à jour HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="62d28-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="62d28-157">Comment mettre à jour les guides (stocker des applications).</span><span class="sxs-lookup"><span data-stu-id="62d28-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="62d28-158">Comment mettre à jour les applications LOB.</span><span class="sxs-lookup"><span data-stu-id="62d28-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="62d28-159">Plan de développement.</span><span class="sxs-lookup"><span data-stu-id="62d28-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="62d28-160">La réalisation d’un plan de support.</span><span class="sxs-lookup"><span data-stu-id="62d28-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="62d28-161">Options de gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="62d28-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="62d28-162">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="62d28-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="62d28-163">Déploiement connecté à l’entreprise : préparer</span><span class="sxs-lookup"><span data-stu-id="62d28-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
