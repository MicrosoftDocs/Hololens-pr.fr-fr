---
title: Planification du déploiement de HoloLens 2 dans un environnement commercial
description: découvrez les principaux besoins en matière de déploiement et de gestion des HoloLens dans les environnements d’entreprise, notamment l’infrastructure, azure active directory et la gestion des appareils mobiles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639078"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="c1048-103">Planification du déploiement de HoloLens 2 dans un environnement commercial</span><span class="sxs-lookup"><span data-stu-id="c1048-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="c1048-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="c1048-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="c1048-105">cette vue d’ensemble est destinée à aider les professionnels de l’informatique à comprendre les considérations relatives au déploiement et à la gestion d’appareils Microsoft HoloLens 2 au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="c1048-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="c1048-106">pour les utilisateurs finaux d’appareils, consultez [obtenir votre HoloLens 2 prêt à utiliser](hololens2-setup.md) pour commencer.</span><span class="sxs-lookup"><span data-stu-id="c1048-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="c1048-107">HoloLens 2 s’exécute sur Windows 10 Holographique qui fournit aux organisations des technologies de gestion des applications et des appareils mobiles robustes, flexibles et intégrées.</span><span class="sxs-lookup"><span data-stu-id="c1048-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="c1048-108">Windows 10 Holographique prend en charge la gestion du cycle de vie des appareils de bout en bout pour permettre aux entreprises de contrôler leurs appareils, leurs données et leurs applications.</span><span class="sxs-lookup"><span data-stu-id="c1048-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="c1048-109">les HoloLens 2 peuvent facilement être incorporées dans des pratiques de cycle de vie standard, de l’inscription des appareils, de la configuration et de la gestion des applications à la maintenance et à la retraite à l’aide d’une solution complète de gestion des appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="c1048-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="c1048-110">les étapes et la vidéo suivantes peuvent vous guider tout au long du processus de HoloLens 2 adoption au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c1048-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![Étape 1](images/1green.png)| <br/> <span data-ttu-id="c1048-112">**[scénarios de déploiement courants](hololens-requirements.md)**: comprenez les scénarios de déploiement et explorez les principaux composants nécessaires au déploiement de HoloLens 2 appareils.</span><span class="sxs-lookup"><span data-stu-id="c1048-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Étape 2](images/2green.png)| <br/> <span data-ttu-id="c1048-114">**[Préparer](#prepare)**: Familiarisez-vous avec les principes fondamentaux de l’infrastructure nécessaires à la HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c1048-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Étape 3](images/3green.png) | <br/> <span data-ttu-id="c1048-116">**[Configurer](#configure)**: Découvrez comment configurer vos composants essentiels pour un déploiement basé sur le Cloud.</span><span class="sxs-lookup"><span data-stu-id="c1048-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Étape 4](images/4green.png) | <br/> <span data-ttu-id="c1048-118">**[Déploiement](#deploy)**: Découvrez comment déployer vos appareils et distribuer vos applications de manière sécurisée et efficace.</span><span class="sxs-lookup"><span data-stu-id="c1048-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Étape 5](images/5green.png) | <br/> <span data-ttu-id="c1048-120">**[tenir à jour](#maintain)**: découvrez ce qui est nécessaire pour maintenir correctement l’état de vos appareils HoloLens 2 et garantir la conformité avec la stratégie d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c1048-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="c1048-121">Préparation</span><span class="sxs-lookup"><span data-stu-id="c1048-121">Prepare</span></span>

<span data-ttu-id="c1048-122">découvrez les services d’infrastructure essentiels requis pour prendre en charge l’ensemble complet des fonctionnalités de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c1048-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="c1048-123">Composant</span><span class="sxs-lookup"><span data-stu-id="c1048-123">Component</span></span> | <span data-ttu-id="c1048-124">Description</span><span class="sxs-lookup"><span data-stu-id="c1048-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c1048-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="c1048-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="c1048-126">Fournit la gestion des identités et des accès pour les HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c1048-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="c1048-127">Gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="c1048-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="c1048-128">gère HoloLens 2 appareils connectés à votre locataire</span><span class="sxs-lookup"><span data-stu-id="c1048-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="c1048-129">Réseau Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c1048-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="c1048-130">Wi-Fi est disponible et les appareils peuvent être connectés à Internet</span><span class="sxs-lookup"><span data-stu-id="c1048-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="c1048-131">Configurer</span><span class="sxs-lookup"><span data-stu-id="c1048-131">Configure</span></span>

<span data-ttu-id="c1048-132">utilisez Intune et autopilot comme solutions de bas niveau pour l’inscription et la configuration de HoloLens 2 au client Azure AD et au MDM de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c1048-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="c1048-133">Composant</span><span class="sxs-lookup"><span data-stu-id="c1048-133">Component</span></span> | <span data-ttu-id="c1048-134">Description</span><span class="sxs-lookup"><span data-stu-id="c1048-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c1048-135">Inscription automatique</span><span class="sxs-lookup"><span data-stu-id="c1048-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="c1048-136">Après la connexion initiale, les appareils s’inscrivent automatiquement auprès d’Azure AD et s’inscrivent dans MDM</span><span class="sxs-lookup"><span data-stu-id="c1048-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="c1048-137">Licences d’application</span><span class="sxs-lookup"><span data-stu-id="c1048-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="c1048-138">Peut être appliqué à des utilisateurs, à des groupes d’utilisateurs ou à des groupes d’appareils</span><span class="sxs-lookup"><span data-stu-id="c1048-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="c1048-139">Utilisateurs et groupes Azure</span><span class="sxs-lookup"><span data-stu-id="c1048-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="c1048-140">Permet d’attribuer des configurations et des licences pour le HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c1048-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="c1048-141">Déployer</span><span class="sxs-lookup"><span data-stu-id="c1048-141">Deploy</span></span>

<span data-ttu-id="c1048-142">distribuez vos appareils HoloLens 2 et validez leur configuration.</span><span class="sxs-lookup"><span data-stu-id="c1048-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="c1048-143">Composant</span><span class="sxs-lookup"><span data-stu-id="c1048-143">Component</span></span> | <span data-ttu-id="c1048-144">Description</span><span class="sxs-lookup"><span data-stu-id="c1048-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c1048-145">Validation de l’inscription</span><span class="sxs-lookup"><span data-stu-id="c1048-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="c1048-146">valider que l’appareil n’a Azure AD joint depuis Paramètres ou le portail Azure</span><span class="sxs-lookup"><span data-stu-id="c1048-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="c1048-147">Validation de certificat</span><span class="sxs-lookup"><span data-stu-id="c1048-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="c1048-148">Vérifier les paramètres et vérifier qu’ils ont été distribués correctement</span><span class="sxs-lookup"><span data-stu-id="c1048-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="c1048-149">Valider les installations d’applications</span><span class="sxs-lookup"><span data-stu-id="c1048-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="c1048-150">Vérifiez que l’application est présente et qu’elle fonctionne sur votre HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c1048-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="c1048-151">Maintenance</span><span class="sxs-lookup"><span data-stu-id="c1048-151">Maintain</span></span>

<span data-ttu-id="c1048-152">utilisez Windows Update pour l’entreprise avec votre système MDM ou le Microsoft Store pour maintenir à jour votre parc de HoloLens 2 et d’applications.</span><span class="sxs-lookup"><span data-stu-id="c1048-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="c1048-153">Composant</span><span class="sxs-lookup"><span data-stu-id="c1048-153">Component</span></span> | <span data-ttu-id="c1048-154">Description</span><span class="sxs-lookup"><span data-stu-id="c1048-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c1048-155">Mettre à jour HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c1048-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="c1048-156">configurer les mises à jour en fonction des besoins par le biais des mises à jour Windows pour l’entreprise</span><span class="sxs-lookup"><span data-stu-id="c1048-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="c1048-157">Mise à jour des applications</span><span class="sxs-lookup"><span data-stu-id="c1048-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="c1048-158">Configurez votre système MDM ou le Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c1048-158">Configure through your MDM system or the Microsoft Store</span></span>
