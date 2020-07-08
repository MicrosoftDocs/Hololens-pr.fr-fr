---
title: Vue d’ensemble-gestion d’applications
description: application, gestion, gestion des applications
keywords: HoloLens, utilisateur, compte, application, gestion des applications,
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857912"
---
# <span data-ttu-id="b90f6-104">Gestion des applications: vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="b90f6-104">App Management: Overview</span></span>

<span data-ttu-id="b90f6-105">Vous pouvez déployer des applications sur quatre chemins différents: **gestion des périphériques mobiles (GPM)**, **Microsoft Store entreprise**, **Microsoft Store**ou en les installant via la fonction de **mise en service**.</span><span class="sxs-lookup"><span data-stu-id="b90f6-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="b90f6-106">Gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="b90f6-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="b90f6-107">Une solution de gestion des appareils mobiles permet aux utilisateurs de décideurs de décision et aux administrateurs d’installer en privé une installation automatique de leurs applications métier internes ou d’acheter des applications dans le Windows Store pour un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b90f6-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="b90f6-108">Les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="b90f6-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="b90f6-109">Intune offre aux utilisateurs un contrôle plus précis sur les applications gérées par le biais de l’interface du portail d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b90f6-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="b90f6-110">Les instructions suivantes s’appliquent aux utilisateurs qui souhaitent gérer leurs applications avec Intune.</span><span class="sxs-lookup"><span data-stu-id="b90f6-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="b90f6-111">Microsoft recommande l’utilisation de Intune pour la gestion des applications et des appareils.</span><span class="sxs-lookup"><span data-stu-id="b90f6-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="b90f6-112">La gestion des périphériques mobiles (GPM) s’applique aux éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="b90f6-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="b90f6-113">Déploiement d’une entreprise via la gestion des périphériques mobiles</span><span class="sxs-lookup"><span data-stu-id="b90f6-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="b90f6-114">Lignes d’applications entreprise (non publiques)</span><span class="sxs-lookup"><span data-stu-id="b90f6-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="b90f6-115">Installation manuelle des applications disponibles via le portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="b90f6-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="b90f6-116">Stratégie d’administration Poussée via le GPM</span><span class="sxs-lookup"><span data-stu-id="b90f6-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="b90f6-117">Mise à jour automatique via le GPM</span><span class="sxs-lookup"><span data-stu-id="b90f6-117">Auto update through MDM</span></span>

## <span data-ttu-id="b90f6-118">Microsoft Store pour Entreprises</span><span class="sxs-lookup"><span data-stu-id="b90f6-118">Microsoft Store for Business</span></span>

<span data-ttu-id="b90f6-119">Le [Microsoft Store pour les entreprises](app-deploy-store-business.md) fournit aux décisionnaires de décision et aux administrateurs des entreprises la recherche, l’acquisition, la gestion et la distribution des applications gratuites et payantes.</span><span class="sxs-lookup"><span data-stu-id="b90f6-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="b90f6-120">Les administrateurs informatiques peuvent gérer les applications du MicrosoftStore et les applications cœur de métier privées dans un inventaire unique, et attribuer et réutiliser les licences selon leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="b90f6-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="b90f6-121">Pour plus d’informations, consultez [la configuration requise pour utiliser le Microsoft Store pour les entreprises](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="b90f6-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="b90f6-122">Le Microsoft Store pour entreprises s’applique aux éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="b90f6-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="b90f6-123">Applications publiques ou métier</span><span class="sxs-lookup"><span data-stu-id="b90f6-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="b90f6-124">Installation automatique d’applications requises par le biais de l’Association GPM</span><span class="sxs-lookup"><span data-stu-id="b90f6-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="b90f6-125">L’utilisateur télécharge manuellement des applications</span><span class="sxs-lookup"><span data-stu-id="b90f6-125">User manually downloads apps</span></span>
* <span data-ttu-id="b90f6-126">Mise à jour automatique</span><span class="sxs-lookup"><span data-stu-id="b90f6-126">Auto Update</span></span>

## <span data-ttu-id="b90f6-127">Applications du Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b90f6-127">Microsoft Store apps</span></span>

<span data-ttu-id="b90f6-128">Le Microsoft Store fournit aux décideurs de décision et aux administrateurs des entreprises la recherche, l’acquisition, la gestion et la distribution d’applications publiques.</span><span class="sxs-lookup"><span data-stu-id="b90f6-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="b90f6-129">Ce Microsoft Store est applicable pour:</span><span class="sxs-lookup"><span data-stu-id="b90f6-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="b90f6-130">Applications publiques uniquement</span><span class="sxs-lookup"><span data-stu-id="b90f6-130">Public apps only</span></span>
* <span data-ttu-id="b90f6-131">L’utilisateur télécharge manuellement des applications</span><span class="sxs-lookup"><span data-stu-id="b90f6-131">User manually downloads apps</span></span>
* <span data-ttu-id="b90f6-132">Mise à jour automatique s’il est connecté à Internet</span><span class="sxs-lookup"><span data-stu-id="b90f6-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="b90f6-133">Pour plus d’informations, consultez applications du Windows [Store holographique](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="b90f6-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="b90f6-134">Installation via les packages de mise en service</span><span class="sxs-lookup"><span data-stu-id="b90f6-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="b90f6-135">Les [packages de mise en service](app-deploy-provisioning-package.md) vous permettent d’installer des applications personnalisées ou d’une entreprise, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou des appareils locaux via USB.</span><span class="sxs-lookup"><span data-stu-id="b90f6-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="b90f6-136">Cette opération peut être réalisée sans connexion Internet et pour tout type d’identité.</span><span class="sxs-lookup"><span data-stu-id="b90f6-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="b90f6-137">L’installation via les packages de mise en service est applicable pour:</span><span class="sxs-lookup"><span data-stu-id="b90f6-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="b90f6-138">Lignes d’applications entreprise (non publiques)</span><span class="sxs-lookup"><span data-stu-id="b90f6-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="b90f6-139">Applications publiques (si le programme d’installation hors connexion est disponible)</span><span class="sxs-lookup"><span data-stu-id="b90f6-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="b90f6-140">Télécharger uniquement le bus USB</span><span class="sxs-lookup"><span data-stu-id="b90f6-140">USB side-load only</span></span>
* <span data-ttu-id="b90f6-141">Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package de mise en service)</span><span class="sxs-lookup"><span data-stu-id="b90f6-141">No auto update (requires manual updates via Provisioning Package)</span></span>
