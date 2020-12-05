---
title: Guide de déploiement – technologie HoloLens 2 du Cloud connecté à Remote Assist-vue d’ensemble
description: Inscrire des appareils HoloLens sur un réseau connecté sur le Cloud
keywords: HoloLens, gestion, Cloud connecté, assistance à distance, AAD, Azure AD, GPM, gestion des appareils mobiles
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196300"
---
# <span data-ttu-id="f43f2-104">Guide de déploiement – connexion HoloLens 2 du Cloud connecté à distance-vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="f43f2-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="f43f2-105">Ce guide est destiné à aider les informaticiens à planifier et à déployer des appareils Microsoft HoloLens 2 dans leur organisation en ayant la possibilité de se connecter à votre organisation à l’aide de Dynamics 365 Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="f43f2-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="f43f2-106">Gardez à l’esprit qu’il s’agit d’un modèle pour les déploiements de la preuve de concept au sein de votre organisation dans différentes circonstances d’utilisation HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f43f2-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="f43f2-107">Au cours de ce guide, nous allons vous expliquer comment inscrire vos appareils dans le cadre de la gestion des appareils, appliquer des licences si nécessaire et vérifier que vos utilisateurs finaux peuvent utiliser immédiatement l’assistance à distance lors de la configuration de périphériques.</span><span class="sxs-lookup"><span data-stu-id="f43f2-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device set up.</span></span> <span data-ttu-id="f43f2-108">Pour ce faire, nous allons examiner les éléments d’infrastructure importants nécessaires à la configuration et à l’exécution de la mise à niveau vers HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f43f2-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="f43f2-109">Dans ce guide</span><span class="sxs-lookup"><span data-stu-id="f43f2-109">In this Guide</span></span>

<span data-ttu-id="f43f2-110">Ce guide a pour but spécifique de configurer l’assistance à distance au sein de votre organisation sur vos appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f43f2-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="f43f2-111">Nous allons aborder les reversions nécessaires pour atteindre cet objectif.</span><span class="sxs-lookup"><span data-stu-id="f43f2-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="f43f2-112">Pour pouvoir mettre le focus sur cet objectif, certaines préparations et configurations sont présélectionnées afin d’optimiser le déploiement ou de réduire les éléments nécessaires à la configuration.</span><span class="sxs-lookup"><span data-stu-id="f43f2-112">In order to maintain focus on this goal certain preparations and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="f43f2-113">Vous serez averti de ces choix et pourrez personnaliser votre déploiement en fonction de vos besoins professionnels.</span><span class="sxs-lookup"><span data-stu-id="f43f2-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="f43f2-114">Il s’agit d’une configuration similaire au [scénario a: déploiement vers des appareils de connexion Cloud](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), qui est une bonne option pour de nombreux déploiements de la preuve de concept qui incluent:</span><span class="sxs-lookup"><span data-stu-id="f43f2-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments which will include:</span></span>

- <span data-ttu-id="f43f2-115">Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services Cloud.</span><span class="sxs-lookup"><span data-stu-id="f43f2-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="f43f2-116">Accès Azure AD à l’inscription automatique de la gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="f43f2-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="f43f2-117">Les utilisateurs se connectent avec leur propre compte d’entreprise (AAD)</span><span class="sxs-lookup"><span data-stu-id="f43f2-117">Users sign in with their own corporate account (AAD)</span></span>
  - <span data-ttu-id="f43f2-118">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="f43f2-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="f43f2-119">Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.</span><span class="sxs-lookup"><span data-stu-id="f43f2-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Scénario connecté dans le Cloud](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="f43f2-121">Il n’est pas possible d’appliquer des restrictions ou configurations de périphériques supplémentaires dans ce guide, mais nous vous encourageons à découvrir ces options après la fin.</span><span class="sxs-lookup"><span data-stu-id="f43f2-121">No additional device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="f43f2-122">En savoir plus sur l’assistance à distance</span><span class="sxs-lookup"><span data-stu-id="f43f2-122">Learn about Remote Assist</span></span>

<span data-ttu-id="f43f2-123">L’assistance à distance permet d’apporter des opérations de maintenance et de réparation, d’inspection à distance et de partage de connaissances et de formation.</span><span class="sxs-lookup"><span data-stu-id="f43f2-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="f43f2-124">En connectant des personnes dans différents rôles et emplacements, un technicien utilisant l’assistance à distance peut communiquer avec un collaborateur distant sur Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f43f2-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="f43f2-125">Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre des problèmes en temps réel, même s’ils ne sont pas&#39;t au même endroit.</span><span class="sxs-lookup"><span data-stu-id="f43f2-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="f43f2-126">Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles que le technicien&#39;de l’espace physique pour s’y référer tout en travaillant en mains libres sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f43f2-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="f43f2-127">Ce guide vous permet d’effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="f43f2-127">In this guide you will:</span></span>

<span data-ttu-id="f43f2-128">Prévenir</span><span class="sxs-lookup"><span data-stu-id="f43f2-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f43f2-129">Découvrez les notions fondamentales sur l’infrastructure des appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f43f2-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="f43f2-130">En savoir plus sur AAD et en configurer un si vous n’en avez pas&#39;.</span><span class="sxs-lookup"><span data-stu-id="f43f2-130">Learn more about AAD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="f43f2-131">Apprenez-en davantage sur la gestion des identités et la configuration des comptes AAD.</span><span class="sxs-lookup"><span data-stu-id="f43f2-131">Learn about Identity management and how to best set up AAD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="f43f2-132">Apprenez-en davantage sur la gestion des périphériques mobiles et configurez avec Intune si vous n’avez pas encore l’un de ces&#39;.</span><span class="sxs-lookup"><span data-stu-id="f43f2-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="f43f2-133">En savoir plus sur la configuration requise en réseau d’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="f43f2-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="f43f2-134">Si vous le souhaitez, VPN pour vous connecter aux ressources de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="f43f2-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="f43f2-135">Configur</span><span class="sxs-lookup"><span data-stu-id="f43f2-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f43f2-136">Découvrez comment créer des utilisateurs et des groupes.</span><span class="sxs-lookup"><span data-stu-id="f43f2-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="f43f2-137">Comment configurer l’inscription automatique dans AAD.</span><span class="sxs-lookup"><span data-stu-id="f43f2-137">How to set up Auto-enrollment within AAD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="f43f2-138">Comment affecter des licences d’application.</span><span class="sxs-lookup"><span data-stu-id="f43f2-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="f43f2-139">Deploy</span><span class="sxs-lookup"><span data-stu-id="f43f2-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f43f2-140">Configurez votre HoloLens 2 et validez l’inscription.</span><span class="sxs-lookup"><span data-stu-id="f43f2-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="f43f2-141">Valider vous pouvez effectuer un appel d’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="f43f2-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="f43f2-142">Maintiendra</span><span class="sxs-lookup"><span data-stu-id="f43f2-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="f43f2-143">Comment mettre à jour l’assistance à distance à l’aide de l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f43f2-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="f43f2-144">Élaboration d’un plan de support.</span><span class="sxs-lookup"><span data-stu-id="f43f2-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="f43f2-145">Plan de développement.</span><span class="sxs-lookup"><span data-stu-id="f43f2-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="f43f2-146">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="f43f2-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f43f2-147">Déploiement connecté dans le Cloud-préparer</span><span class="sxs-lookup"><span data-stu-id="f43f2-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

