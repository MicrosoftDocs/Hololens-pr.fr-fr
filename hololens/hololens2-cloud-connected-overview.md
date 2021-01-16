---
title: Guide de déploiement – HoloLens 2 connecté au cloud avec Remote Assist - Vue d’ensemble
description: Inscrire des appareils HoloLens sur un réseau connecté au cloud
keywords: HoloLens, gestion, cloud connecté, Remote Assist, AAD, Azure AD, MDM, Gestion des appareils mobiles
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
ms.openlocfilehash: fe83333c99f8dbf23b211c9b5155db256dcd20b3
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271671"
---
# <span data-ttu-id="3dcc6-104">Guide de déploiement – HoloLens 2 connecté au cloud avec Remote Assist – Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="3dcc6-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="3dcc6-105">Ce guide aide les professionnels de l’informatique à planifier et à déployer des appareils Microsoft HoloLens 2 dans leur organisation avec l’objectif global d’avoir ces appareils connectés à votre organisation avec Dynamics 365 Remote Assist prêt à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="3dcc6-106">N’oubliez pas que cela servira de modèle pour les déploiements de preuve de concept dans votre organisation dans divers cas d’utilisation de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="3dcc6-107">Au cours du guide, nous allons apprendre à inscrire vos appareils dans la gestion de vos appareils, à appliquer des licences selon vos besoins et à vérifier que vos utilisateurs finaux peuvent immédiatement utiliser Remote Assist lors de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="3dcc6-108">Pour ce faire, nous allons passer en détail les éléments d’infrastructure importants nécessaires à la mise en place et à l’exécution , en obtenant un déploiement à grande échelle avec HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="3dcc6-109">Dans ce guide</span><span class="sxs-lookup"><span data-stu-id="3dcc6-109">In this Guide</span></span>

<span data-ttu-id="3dcc6-110">Ce guide a pour objectif spécifique de définir Remote Assist au sein de votre organisation sur vos appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="3dcc6-111">Nous allons couvrir les nécessités nécessaires pour atteindre cet objectif.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="3dcc6-112">Afin de maintenir le focus sur cet objectif, certaines préparations et configurations seront préalablement sélectionnées afin d’optimiser ce déploiement ou de réduire les éléments nécessaires à la configuration.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="3dcc6-113">Vous serez informé de ces choix et pourrez personnaliser votre déploiement en fonction des besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="3dcc6-114">Il s’agit d’une installation similaire au scénario A : déployer sur des appareils [de connexion au cloud,](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)ce qui est une bonne option pour de nombreux déploiements de preuve de concept, qui incluront :</span><span class="sxs-lookup"><span data-stu-id="3dcc6-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="3dcc6-115">Wi-Fi réseaux sont généralement entièrement ouverts aux services Internet et Cloud</span><span class="sxs-lookup"><span data-stu-id="3dcc6-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="3dcc6-116">Azure AD Join avec inscription automatique MDM - Gestion de la gestion des fonctionnalités de gestion des plateformes (Intune)</span><span class="sxs-lookup"><span data-stu-id="3dcc6-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="3dcc6-117">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3dcc6-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="3dcc6-118">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="3dcc6-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="3dcc6-119">Différents niveaux de configurations de verrouillage d’appareil sont appliqués en fonction de cas d’utilisation spécifiques, de l’ouverture complète à la borne d’application unique</span><span class="sxs-lookup"><span data-stu-id="3dcc6-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Scénario connecté au cloud](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="3dcc6-121">Aucune autre restriction ou configuration d’appareil ne sera appliquée dans ce guide, mais nous vous encourageons à explorer ces options après avoir terminé.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="3dcc6-122">En savoir plus sur Remote Assist</span><span class="sxs-lookup"><span data-stu-id="3dcc6-122">Learn about Remote Assist</span></span>

<span data-ttu-id="3dcc6-123">Remote Assist permet la maintenance et la réparation collaboratives, l’inspection à distance, ainsi que le partage de connaissances et la formation.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="3dcc6-124">En connectant des personnes dans différents rôles et emplacements, un technicien utilisant Remote Assist peut se connecter à un collaborateur distant sur Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="3dcc6-125">Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre les problèmes en temps réel,&#39;ne se trouve pas au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="3dcc6-126">Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles sur l’espace physique du technicien&#39;afin qu’ils peuvent faire référence au schéma tout en travaillant à tête haute et mains libres sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="3dcc6-127">Dans ce guide, vous allez :</span><span class="sxs-lookup"><span data-stu-id="3dcc6-127">In this guide you will:</span></span>

<span data-ttu-id="3dcc6-128">Préparez :</span><span class="sxs-lookup"><span data-stu-id="3dcc6-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="3dcc6-129">Découvrez les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="3dcc6-130">En savoir plus sur Azure AD et en configurer un si vous ne l&#39;pas.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="3dcc6-131">Découvrez la gestion des identités et la meilleure façon de configurer les comptes Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="3dcc6-132">En savoir plus sur la gestion des mdm et configurer avec Intune si vous n'&#39;pas déjà en avoir un.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="3dcc6-133">Découvrez les exigences de mise en réseau de Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="3dcc6-134">Facultatif : VPN pour se connecter aux ressources organisationnelles</span><span class="sxs-lookup"><span data-stu-id="3dcc6-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="3dcc6-135">Configurez :</span><span class="sxs-lookup"><span data-stu-id="3dcc6-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="3dcc6-136">Comment créer des utilisateurs et des groupes.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="3dcc6-137">Comment configurer l’inscription automatique dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="3dcc6-138">Comment attribuer vos licences d’application.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="3dcc6-139">Déployez :</span><span class="sxs-lookup"><span data-stu-id="3dcc6-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="3dcc6-140">Configurer votre HoloLens 2 et valider l’inscription.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="3dcc6-141">Validez que vous pouvez effectuer un appel d’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="3dcc6-142">Maintenez à jour :</span><span class="sxs-lookup"><span data-stu-id="3dcc6-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="3dcc6-143">Comment mettre à jour Remote Assist à l’aide de l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="3dcc6-144">La réalisation d’un plan de support.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="3dcc6-145">Plan de développement.</span><span class="sxs-lookup"><span data-stu-id="3dcc6-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="3dcc6-146">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="3dcc6-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3dcc6-147">Déploiement connecté au cloud : préparer</span><span class="sxs-lookup"><span data-stu-id="3dcc6-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

