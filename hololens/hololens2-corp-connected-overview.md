---
title: Guide de déploiement – connexion d’entreprise HoloLens 2 avec Dynamics 365 Guides-vue d’ensemble
description: découvrez comment inscrire des appareils HoloLens 2 avec Dynamics 365 Guides sur un réseau connecté à l’entreprise.
keywords: HoloLens, gestion, connecté à l’entreprise, Dynamics 365 Guides, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637011"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="40b75-104">Guide de déploiement-connexion d’entreprise HoloLens 2 avec Dynamics 365 Guides-vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="40b75-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="40b75-105">ce guide aide les professionnels de l’informatique à planifier et à déployer Microsoft HoloLens 2 appareils avec Dynamics 365 Guides (Guides) dans leur organisation.</span><span class="sxs-lookup"><span data-stu-id="40b75-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="40b75-106">Ce guide est parfait pour les pilotes et les déploiements de production. il est similaire au [scénario B : déployer à l’intérieur du Guide réseau de votre organisation](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) .</span><span class="sxs-lookup"><span data-stu-id="40b75-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="40b75-107">après avoir testé votre preuve de concept, utilisez ce guide pour progresser avec l’intégration d’HoloLens à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="40b75-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="40b75-108">Dans ce guide, nous allons vous montrer comment inscrire vos appareils dans la gestion des appareils existante, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser un guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la configuration des appareils.</span><span class="sxs-lookup"><span data-stu-id="40b75-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="40b75-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="40b75-109">Prerequisites</span></span>

<span data-ttu-id="40b75-110">L’infrastructure suivante doit déjà être en place :</span><span class="sxs-lookup"><span data-stu-id="40b75-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="40b75-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="40b75-111">Wi-Fi</span></span>
    - <span data-ttu-id="40b75-112">Réseau d’entreprise interne avec accès aux ressources internes et accès limité à Internet ou aux services Cloud</span><span class="sxs-lookup"><span data-stu-id="40b75-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="40b75-113">Authentification par certificat basée sur les appareils.</span><span class="sxs-lookup"><span data-stu-id="40b75-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="40b75-114">jonction de Azure Active Directory (Azure AD) avec l’inscription automatique MDM ([Azure AD abonnement P1](/azure/active-directory/fundamentals/active-directory-whatis) requis)</span><span class="sxs-lookup"><span data-stu-id="40b75-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="40b75-115">Gestion MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="40b75-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="40b75-116">Une ou plusieurs applications sont déployées via MDM.</span><span class="sxs-lookup"><span data-stu-id="40b75-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="40b75-117">Réseau</span><span class="sxs-lookup"><span data-stu-id="40b75-117">Network</span></span> 
    - <span data-ttu-id="40b75-118">Certificats (SCEP ou PKCS)</span><span class="sxs-lookup"><span data-stu-id="40b75-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="40b75-119">Configuration du proxy</span><span class="sxs-lookup"><span data-stu-id="40b75-119">Proxy configuration</span></span>
- <span data-ttu-id="40b75-120">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="40b75-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="40b75-121">Un ou plusieurs utilisateurs par appareil sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="40b75-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="40b75-122">Différents niveaux de configurations de verrouillage des appareils appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’une seule application.</span><span class="sxs-lookup"><span data-stu-id="40b75-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="40b75-123">Guides sur les licences et les exigences</span><span class="sxs-lookup"><span data-stu-id="40b75-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="40b75-124">Compte Azure AD</span><span class="sxs-lookup"><span data-stu-id="40b75-124">Azure AD account</span></span>
- <span data-ttu-id="40b75-125">Dynamics 365 Guides des applications PC et HoloLens</span><span class="sxs-lookup"><span data-stu-id="40b75-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="40b75-126">abonnement Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="40b75-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="40b75-127">Microsoft Dataverse (inclus)</span><span class="sxs-lookup"><span data-stu-id="40b75-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="40b75-128">Power Apps (inclus)</span><span class="sxs-lookup"><span data-stu-id="40b75-128">Power Apps (included)</span></span>
- <span data-ttu-id="40b75-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="40b75-129">Power BI Desktop</span></span>
- <span data-ttu-id="40b75-130">Connectivité réseau</span><span class="sxs-lookup"><span data-stu-id="40b75-130">Network Connectivity</span></span>

<span data-ttu-id="40b75-131">[![Diagramme du réseau connecté à l’entreprise, étape 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="40b75-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="40b75-132">[![Diagramme du réseau connecté à l’entreprise, étape 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="40b75-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="40b75-133">Dans ce guide, vous allez :</span><span class="sxs-lookup"><span data-stu-id="40b75-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="40b75-134">Préparation</span><span class="sxs-lookup"><span data-stu-id="40b75-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="40b75-135">en savoir plus sur les notions fondamentales de l’infrastructure pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="40b75-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="40b75-136">En savoir plus sur les Azure AD et en configurer une si vous n’en avez pas.</span><span class="sxs-lookup"><span data-stu-id="40b75-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="40b75-137">En savoir plus sur la gestion des identités et sur la façon de configurer au mieux les comptes Azure AD.</span><span class="sxs-lookup"><span data-stu-id="40b75-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="40b75-138">En savoir plus sur MDM et configurer avec Intune si vous n’en avez pas déjà un.</span><span class="sxs-lookup"><span data-stu-id="40b75-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="40b75-139">Familiarisez-vous avec le Wi-Fi basé sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="40b75-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="40b75-140">Familiarisez-vous avec le proxy.</span><span class="sxs-lookup"><span data-stu-id="40b75-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="40b75-141">Découvrez comment vous pouvez utiliser des applications métier.</span><span class="sxs-lookup"><span data-stu-id="40b75-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="40b75-142">En savoir plus sur la façon dont vous pouvez utiliser les guides pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="40b75-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="40b75-143">Configurer</span><span class="sxs-lookup"><span data-stu-id="40b75-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="40b75-144">Comment créer des utilisateurs et des groupes.</span><span class="sxs-lookup"><span data-stu-id="40b75-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="40b75-145">Comment configurer l’inscription automatique.</span><span class="sxs-lookup"><span data-stu-id="40b75-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="40b75-146">Comment configurer des certificats et des profils Wi-Fi pour la connectivité des Wi-Fi d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="40b75-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="40b75-147">Télécharger et affecter des packages d’applications métier.</span><span class="sxs-lookup"><span data-stu-id="40b75-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="40b75-148">Dynamics 365 Guides d’installation.</span><span class="sxs-lookup"><span data-stu-id="40b75-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="40b75-149">Comment configurer le mode plein écran (facultatif).</span><span class="sxs-lookup"><span data-stu-id="40b75-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="40b75-150">Comment configurer WDAC (facultatif).</span><span class="sxs-lookup"><span data-stu-id="40b75-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="40b75-151">Déployer</span><span class="sxs-lookup"><span data-stu-id="40b75-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="40b75-152">Valider l’inscription via Device et MDM.</span><span class="sxs-lookup"><span data-stu-id="40b75-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="40b75-153">Validez Wi-Fi certificats.</span><span class="sxs-lookup"><span data-stu-id="40b75-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="40b75-154">Valider l’installation de l’application métier.</span><span class="sxs-lookup"><span data-stu-id="40b75-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="40b75-155">Validez les guides via la création et le fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="40b75-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="40b75-156">Maintenance</span><span class="sxs-lookup"><span data-stu-id="40b75-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="40b75-157">Mettez à jour HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="40b75-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="40b75-158">Comment mettre à jour des guides (applications du Windows Store).</span><span class="sxs-lookup"><span data-stu-id="40b75-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="40b75-159">Comment mettre à jour des applications métier.</span><span class="sxs-lookup"><span data-stu-id="40b75-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="40b75-160">Plan de développement.</span><span class="sxs-lookup"><span data-stu-id="40b75-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="40b75-161">Création d’un plan de support.</span><span class="sxs-lookup"><span data-stu-id="40b75-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="40b75-162">Options de gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="40b75-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="40b75-163">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="40b75-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="40b75-164">Déploiement connecté d’entreprise-préparer</span><span class="sxs-lookup"><span data-stu-id="40b75-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
