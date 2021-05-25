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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397650"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="45e63-104">Guide de déploiement – connexion Cloud HoloLens 2 avec l’assistance à distance-vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="45e63-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="45e63-105">Ce guide aide les professionnels de l’informatique à planifier et déployer des appareils Microsoft HoloLens 2 dans leur organisation avec l’objectif global de faire en sorte que ces appareils soient connectés à votre organisation avec Dynamics 365 Remote Assist prêt à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="45e63-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="45e63-106">Gardez à l’esprit qu’il s’agit d’un modèle pour les déploiements de preuve de concept dans votre organisation dans un large éventail de cas d’utilisation de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="45e63-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="45e63-107">Au cours du guide, nous allons aborder l’inscription de vos appareils dans la gestion des appareils, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser immédiatement l’assistance à distance lors de la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="45e63-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="45e63-108">Pour ce faire, nous allons passer en revue les éléments importants de l’infrastructure nécessaire à la configuration et à l’exécution du déploiement à l’échelle avec HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="45e63-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="45e63-109">[![Scénario ](./images/deployment-guides-revised-scenario-a.png) connecté au Cloud](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="45e63-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="45e63-110">Dans ce guide</span><span class="sxs-lookup"><span data-stu-id="45e63-110">In this Guide</span></span>

<span data-ttu-id="45e63-111">Ce guide a pour objectif de configurer l’assistance à distance au sein de votre organisation sur vos appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="45e63-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="45e63-112">Nous aborderons les indispensables pour atteindre cet objectif.</span><span class="sxs-lookup"><span data-stu-id="45e63-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="45e63-113">Afin de conserver le focus sur cet objectif, certaines préparations et configurations seront présélectionnées afin d’optimiser ce déploiement ou de réduire les éléments nécessaires à la configuration.</span><span class="sxs-lookup"><span data-stu-id="45e63-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="45e63-114">Vous êtes informé de ces choix et pouvez personnaliser votre déploiement en fonction des besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="45e63-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="45e63-115">Il s’agit d’une configuration similaire au [scénario a : déploiement sur des appareils Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), qui est une bonne option pour de nombreux déploiements de preuve de concept, notamment :</span><span class="sxs-lookup"><span data-stu-id="45e63-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="45e63-116">Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing</span><span class="sxs-lookup"><span data-stu-id="45e63-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="45e63-117">Azure AD rejoindre avec l’inscription automatique MDM--MDM (Intune) géré</span><span class="sxs-lookup"><span data-stu-id="45e63-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="45e63-118">Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="45e63-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="45e63-119">Un ou plusieurs utilisateurs par appareil pris en charge</span><span class="sxs-lookup"><span data-stu-id="45e63-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="45e63-120">Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique</span><span class="sxs-lookup"><span data-stu-id="45e63-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="45e63-121">Aucune autre restriction ou configuration d’appareil ne sera appliquée dans ce guide. Toutefois, nous vous encourageons à explorer ces options après avoir terminé.</span><span class="sxs-lookup"><span data-stu-id="45e63-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="45e63-122">En savoir plus sur l’assistance à distance</span><span class="sxs-lookup"><span data-stu-id="45e63-122">Learn about Remote Assist</span></span>

<span data-ttu-id="45e63-123">L’assistance à distance permet la maintenance et la réparation collaboratives, l’inspection à distance, ainsi que le partage des connaissances et la formation.</span><span class="sxs-lookup"><span data-stu-id="45e63-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="45e63-124">En connectant des personnes dans des rôles et des emplacements différents, un technicien utilisant l’assistance à distance peut se connecter à un collaborateur distant de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="45e63-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="45e63-125">Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre les problèmes en temps réel, même lorsqu’ils ne sont pas&#39;t au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="45e63-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="45e63-126">Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles que le technicien&#39;l’espace physique pour qu’ils puissent faire référence au schéma tout en récapitulant les mains et les mains libres sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="45e63-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="45e63-127">Dans ce guide, vous allez :</span><span class="sxs-lookup"><span data-stu-id="45e63-127">In this guide you will:</span></span>

<span data-ttu-id="45e63-128">Préparation :</span><span class="sxs-lookup"><span data-stu-id="45e63-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="45e63-129">En savoir plus sur les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="45e63-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="45e63-130">En savoir plus sur les Azure AD et en configurer une si vous ne l’avez pas&#39;.</span><span class="sxs-lookup"><span data-stu-id="45e63-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="45e63-131">En savoir plus sur la gestion des identités et sur la façon de configurer au mieux les comptes Azure AD.</span><span class="sxs-lookup"><span data-stu-id="45e63-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="45e63-132">Apprenez-en davantage sur MDM et configurez avec Intune si&#39;vous n’avez pas déjà un prêt.</span><span class="sxs-lookup"><span data-stu-id="45e63-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="45e63-133">En savoir plus sur les exigences de mise en réseau de l’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="45e63-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="45e63-134">Éventuellement : VPN pour se connecter aux ressources de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="45e63-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="45e63-135">Configurer :</span><span class="sxs-lookup"><span data-stu-id="45e63-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="45e63-136">Comment créer des utilisateurs et des groupes.</span><span class="sxs-lookup"><span data-stu-id="45e63-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="45e63-137">Comment configurer l’inscription automatique dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="45e63-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="45e63-138">Comment attribuer vos licences d’application.</span><span class="sxs-lookup"><span data-stu-id="45e63-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="45e63-139">Deploy :</span><span class="sxs-lookup"><span data-stu-id="45e63-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="45e63-140">Configurez votre HoloLens 2 et validez l’inscription.</span><span class="sxs-lookup"><span data-stu-id="45e63-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="45e63-141">Valider, vous pouvez effectuer un appel d’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="45e63-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="45e63-142">Mise à jour :</span><span class="sxs-lookup"><span data-stu-id="45e63-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="45e63-143">Comment mettre à jour l’assistance à distance à l’aide de l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="45e63-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="45e63-144">Création d’un plan de support.</span><span class="sxs-lookup"><span data-stu-id="45e63-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="45e63-145">Plan de développement.</span><span class="sxs-lookup"><span data-stu-id="45e63-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="45e63-146">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="45e63-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="45e63-147">Déploiement connecté au Cloud-préparer</span><span class="sxs-lookup"><span data-stu-id="45e63-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

