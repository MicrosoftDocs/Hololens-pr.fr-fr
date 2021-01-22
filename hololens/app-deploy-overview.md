---
title: Vue d’ensemble - Gestion des applications
description: Prise en charge d’une vue d’ensemble de la gestion des applications de réalité mixte avec la gestion des appareils mobiles, microsoft store pour entreprises et les packages d’approvisionnement.
keywords: HoloLens, utilisateur, compte, application, gestion des applications,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283705"
---
# <span data-ttu-id="40f84-104">Vue d’ensemble de la gestion des applications</span><span class="sxs-lookup"><span data-stu-id="40f84-104">App Management: Overview</span></span>

<span data-ttu-id="40f84-105">Vous pouvez déployer des applications sur quatre chemins différents : Gestion des périphériques mobiles **(MDM),** Microsoft Store pour **Entreprises,** **Microsoft Store**ou en les installant via **l’approvisionnement.**</span><span class="sxs-lookup"><span data-stu-id="40f84-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="40f84-106">Gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="40f84-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="40f84-107">Une solution MDM permet aux décideurs et administrateurs informatiques d’installer (push) en privé leurs applications métiers en interne ou d’acheter des applications via le Windows Store pour un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="40f84-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="40f84-108">Les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="40f84-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="40f84-109">Intune offre également aux utilisateurs un contrôle plus fin sur les applications gérées par le service it via l’expérience téléchargeable du portail d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="40f84-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="40f84-110">Les instructions suivantes sont pour les utilisateurs qui souhaitent gérer leurs applications avec Intune.</span><span class="sxs-lookup"><span data-stu-id="40f84-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="40f84-111">Microsoft recommande d’utiliser Intune pour la gestion des applications et des appareils.</span><span class="sxs-lookup"><span data-stu-id="40f84-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="40f84-112">La gestion des périphériques mobiles (MDM) est applicable pour :</span><span class="sxs-lookup"><span data-stu-id="40f84-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="40f84-113">GDM déployé + Portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="40f84-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="40f84-114">Applications métier (non publiques)</span><span class="sxs-lookup"><span data-stu-id="40f84-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="40f84-115">Installation manuelle des applications disponibles via le Portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="40f84-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="40f84-116">L’administrateur fait passer par la stratégie de gestion des stratégies de gestion des stratégies de gestion</span><span class="sxs-lookup"><span data-stu-id="40f84-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="40f84-117">Mise à jour automatique via la gestion des données de gestion des données</span><span class="sxs-lookup"><span data-stu-id="40f84-117">Auto update through MDM</span></span>

## <span data-ttu-id="40f84-118">Microsoft Store pour Entreprises</span><span class="sxs-lookup"><span data-stu-id="40f84-118">Microsoft Store for Business</span></span>

<span data-ttu-id="40f84-119">Le [Microsoft Store pour Entreprises](app-deploy-store-business.md) permet aux décideurs informatiques et aux administrateurs des entreprises de rechercher, d’acquérir, de gérer et de distribuer des applications gratuites et payantes.</span><span class="sxs-lookup"><span data-stu-id="40f84-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="40f84-120">Les administrateurs informatiques peuvent gérer les applications du Microsoft Store et les applications métier privées dans un seul inventaire, et attribuer et réutiliser des licences selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="40f84-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="40f84-121">Pour plus d’informations, [consultez les conditions préalables à l’utilisation du Microsoft Store pour Entreprises.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="40f84-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="40f84-122">Le Microsoft Store pour Entreprises est applicable pour :</span><span class="sxs-lookup"><span data-stu-id="40f84-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="40f84-123">Applications publiques ou métier</span><span class="sxs-lookup"><span data-stu-id="40f84-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="40f84-124">Installation automatique des applications requises par le biais de l’association mdm</span><span class="sxs-lookup"><span data-stu-id="40f84-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="40f84-125">L’utilisateur télécharge manuellement les applications</span><span class="sxs-lookup"><span data-stu-id="40f84-125">User manually downloads apps</span></span>
* <span data-ttu-id="40f84-126">Mise à jour automatique</span><span class="sxs-lookup"><span data-stu-id="40f84-126">Auto Update</span></span>

## <span data-ttu-id="40f84-127">Applications du Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="40f84-127">Microsoft Store apps</span></span>

<span data-ttu-id="40f84-128">Le Microsoft Store permet aux décideurs informatiques et aux administrateurs des entreprises de rechercher, d’acquérir, de gérer et de distribuer des applications publiques.</span><span class="sxs-lookup"><span data-stu-id="40f84-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="40f84-129">Ce Microsoft Store est applicable pour :</span><span class="sxs-lookup"><span data-stu-id="40f84-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="40f84-130">Applications publiques uniquement</span><span class="sxs-lookup"><span data-stu-id="40f84-130">Public apps only</span></span>
* <span data-ttu-id="40f84-131">L’utilisateur télécharge manuellement des applications</span><span class="sxs-lookup"><span data-stu-id="40f84-131">User manually downloads apps</span></span>
* <span data-ttu-id="40f84-132">Mise à jour automatique en cas de connexion à Internet</span><span class="sxs-lookup"><span data-stu-id="40f84-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="40f84-133">Pour plus d’informations, [consultez les applications du Windows Store holographiques.](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="40f84-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="40f84-134">Installer via des packages d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="40f84-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="40f84-135">[Les packages](app-deploy-provisioning-package.md) d’approvisionnement vous permettent d’installer des applications personnalisées ou métier, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou plusieurs appareils locaux via USB.</span><span class="sxs-lookup"><span data-stu-id="40f84-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="40f84-136">Cette installation peut être effectuée sans connexion Internet et pour n’importe quel type d’identité.</span><span class="sxs-lookup"><span data-stu-id="40f84-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="40f84-137">L’installation via des packages d’approvisionnement s’applique pour :</span><span class="sxs-lookup"><span data-stu-id="40f84-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="40f84-138">Applications métier/auto-développées (non publiques)</span><span class="sxs-lookup"><span data-stu-id="40f84-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="40f84-139">Applications publiques (si le programme d’installation hors connexion est disponible)</span><span class="sxs-lookup"><span data-stu-id="40f84-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="40f84-140">Chargement côté USB uniquement</span><span class="sxs-lookup"><span data-stu-id="40f84-140">USB side-loading only</span></span>
* <span data-ttu-id="40f84-141">Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package d’approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="40f84-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="40f84-142">Installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="40f84-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="40f84-143">Les [](app-deploy-app-installer.md) utilisateurs du Programme d’installation d’application peuvent avoir une expérience simple pour installer des applications sur des appareils locaux ou partager une application avec quelqu’un d’autre qui ne connaît pas les autres méthodes d’installation d’application sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="40f84-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="40f84-144">Pour ce faire, vous n’avez pas besoin d’activer le mode développeur ou d’utiliser Device Portal.</span><span class="sxs-lookup"><span data-stu-id="40f84-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="40f84-145">Il s’agit d’une méthode simple de distribution d’une application entièrement intégrée.</span><span class="sxs-lookup"><span data-stu-id="40f84-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="40f84-146">Que vous souhaitiez simplement rétrograder votre application auprès d’un autre utilisateur avec holoLens, ou que vous souhaitiez déployer votre application, cette méthode fonctionne facilement.</span><span class="sxs-lookup"><span data-stu-id="40f84-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="40f84-147">L’installation via le Programme d’installation d’application s’applique pour :</span><span class="sxs-lookup"><span data-stu-id="40f84-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="40f84-148">Applications métier/auto-développées (non publiques)</span><span class="sxs-lookup"><span data-stu-id="40f84-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="40f84-149">Chargement de version latérale uniquement</span><span class="sxs-lookup"><span data-stu-id="40f84-149">Side-load only</span></span>
* <span data-ttu-id="40f84-150">Ne nécessite pas le mode développeur ou Device Portal</span><span class="sxs-lookup"><span data-stu-id="40f84-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="40f84-151">Facile à installer pour l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="40f84-151">Easy for end user to install</span></span>
