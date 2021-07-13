---
title: Vue d’ensemble-gestion des applications
description: Prise en main d’une vue d’ensemble de la gestion des applications de réalité mixte avec la gestion des appareils mobiles, le Microsoft Store pour entreprises et les packages d’approvisionnement.
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635549"
---
# <a name="app-management-overview"></a><span data-ttu-id="82d80-104">Gestion des applications : vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="82d80-104">App Management: Overview</span></span>

<span data-ttu-id="82d80-105">vous pouvez déployer des applications sur quatre chemins différents : **gestion des appareils mobiles (MDM)**, **Microsoft Store pour Entreprises**, **Microsoft Store** ou en les installant via la **configuration**.</span><span class="sxs-lookup"><span data-stu-id="82d80-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="82d80-106">Gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="82d80-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="82d80-107">Une solution de gestion des appareils mobiles permet aux décideurs informatiques et aux administrateurs d’installer automatiquement (push) leurs applications métier internes ou d’acheter des applications dans le Store pour un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="82d80-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="82d80-108">les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="82d80-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="82d80-109">Intune offre également aux utilisateurs un contrôle plus affiné sur les applications gérées par le service informatique grâce à l’expérience téléchargeable Portail d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="82d80-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="82d80-110">Les instructions suivantes sont destinées aux utilisateurs qui souhaitent gérer leurs applications avec Intune.</span><span class="sxs-lookup"><span data-stu-id="82d80-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="82d80-111">Microsoft recommande l’utilisation d’Intune pour la gestion des applications et des appareils.</span><span class="sxs-lookup"><span data-stu-id="82d80-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="82d80-112">La gestion des appareils mobiles (MDM) s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="82d80-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="82d80-113">MDM déployé + Portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="82d80-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="82d80-114">Applications métier (non publiques)</span><span class="sxs-lookup"><span data-stu-id="82d80-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="82d80-115">installation manuelle des applications disponibles via Portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="82d80-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="82d80-116">Push administrateur via la stratégie MDM</span><span class="sxs-lookup"><span data-stu-id="82d80-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="82d80-117">Mise à jour automatique via MDM</span><span class="sxs-lookup"><span data-stu-id="82d80-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="82d80-118">Microsoft Store pour Entreprises</span><span class="sxs-lookup"><span data-stu-id="82d80-118">Microsoft Store for Business</span></span>

<span data-ttu-id="82d80-119">l' [Microsoft Store pour Entreprises](app-deploy-store-business.md) fournit aux décideurs informatiques et aux administrateurs dans les entreprises la recherche, l’acquisition, la gestion et la distribution d’applications gratuites et payantes.</span><span class="sxs-lookup"><span data-stu-id="82d80-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="82d80-120">les administrateurs informatiques peuvent gérer des applications Microsoft Store et des applications métier privées dans un même inventaire, ainsi qu’attribuer et réutiliser des licences en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="82d80-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="82d80-121">pour plus d’informations, consultez [configuration requise pour l’utilisation de l’Microsoft Store pour Entreprises](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="82d80-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="82d80-122">le Microsoft Store pour Entreprises s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="82d80-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="82d80-123">Applications publiques ou métier</span><span class="sxs-lookup"><span data-stu-id="82d80-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="82d80-124">Installation automatique des applications requises par le biais de l’Association MDM</span><span class="sxs-lookup"><span data-stu-id="82d80-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="82d80-125">L’utilisateur télécharge manuellement les applications</span><span class="sxs-lookup"><span data-stu-id="82d80-125">User manually downloads apps</span></span>
* <span data-ttu-id="82d80-126">Mise à jour automatique</span><span class="sxs-lookup"><span data-stu-id="82d80-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="82d80-127">Applications du Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="82d80-127">Microsoft Store apps</span></span>

<span data-ttu-id="82d80-128">l’Microsoft Store fournit aux décideurs et aux administrateurs informatiques des entreprises pour rechercher, acquérir, gérer et distribuer des applications publiques.</span><span class="sxs-lookup"><span data-stu-id="82d80-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="82d80-129">cette Microsoft Store s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="82d80-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="82d80-130">Applications publiques uniquement</span><span class="sxs-lookup"><span data-stu-id="82d80-130">Public apps only</span></span>
* <span data-ttu-id="82d80-131">L’utilisateur télécharge manuellement les applications</span><span class="sxs-lookup"><span data-stu-id="82d80-131">User manually downloads apps</span></span>
* <span data-ttu-id="82d80-132">Mise à jour automatique en cas de connexion à Internet</span><span class="sxs-lookup"><span data-stu-id="82d80-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="82d80-133">Pour plus d’informations, consultez [applications du Store holographiques](/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="82d80-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="82d80-134">Installer via des packages d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="82d80-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="82d80-135">Les [packages de configuration](app-deploy-provisioning-package.md) vous permettent d’installer des applications personnalisées ou métier, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou plusieurs appareils locaux via USB.</span><span class="sxs-lookup"><span data-stu-id="82d80-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="82d80-136">Cette installation peut être effectuée sans connexion Internet et pour n’importe quel type d’identité.</span><span class="sxs-lookup"><span data-stu-id="82d80-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="82d80-137">L’installation via des packages de configuration s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="82d80-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="82d80-138">Applications métier/à développement automatique (non publiques)</span><span class="sxs-lookup"><span data-stu-id="82d80-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="82d80-139">Applications publiques (si le programme d’installation hors connexion est disponible)</span><span class="sxs-lookup"><span data-stu-id="82d80-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="82d80-140">Chargement côté USB uniquement</span><span class="sxs-lookup"><span data-stu-id="82d80-140">USB side-loading only</span></span>
* <span data-ttu-id="82d80-141">Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package d’approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="82d80-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="82d80-142">installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="82d80-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="82d80-143">L’utilisation des utilisateurs du [programme d’installation d’application](app-deploy-app-installer.md) peut avoir une expérience simple pour l’installation d’applications sur des appareils locaux ou le partage d’une application avec une autre personne qui ne connaît pas les autres méthodes d’installation d’applications sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="82d80-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="82d80-144">Pour ce faire, vous devez activer le mode développeur ou utiliser le portail de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="82d80-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="82d80-145">Il s’agit d’une méthode simple pour distribuer une application entièrement générée.</span><span class="sxs-lookup"><span data-stu-id="82d80-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="82d80-146">quelle que soit la façon dont vous souhaitez simplement démo votre application pour un autre utilisateur avec un HoloLens, ou vous souhaitez déployer votre application, cette méthode fonctionne facilement.</span><span class="sxs-lookup"><span data-stu-id="82d80-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="82d80-147">L’installation via le programme d’installation d’application s’applique à :</span><span class="sxs-lookup"><span data-stu-id="82d80-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="82d80-148">Applications métier/à développement automatique (non publiques)</span><span class="sxs-lookup"><span data-stu-id="82d80-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="82d80-149">Chargement indépendant uniquement</span><span class="sxs-lookup"><span data-stu-id="82d80-149">Side-load only</span></span>
* <span data-ttu-id="82d80-150">Ne nécessite pas le mode développeur ou le portail de l’appareil</span><span class="sxs-lookup"><span data-stu-id="82d80-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="82d80-151">Facile à installer par l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="82d80-151">Easy for end user to install</span></span>
