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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308645"
---
# <a name="app-management-overview"></a><span data-ttu-id="7ec29-104">Gestion des applications : vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="7ec29-104">App Management: Overview</span></span>

<span data-ttu-id="7ec29-105">Vous pouvez déployer des applications sur quatre chemins différents : la **gestion des appareils mobiles (MDM)**, **Microsoft Store pour les entreprises**, les **Microsoft Store**, ou en les installant par le biais de l' **approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="7ec29-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="7ec29-106">Gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="7ec29-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="7ec29-107">Une solution de gestion des appareils mobiles permet aux décideurs informatiques et aux administrateurs d’installer automatiquement (push) leurs applications métier internes ou d’acheter des applications dans le Store pour un groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7ec29-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="7ec29-108">Les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="7ec29-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="7ec29-109">Intune offre également aux utilisateurs un contrôle plus affiné sur les applications gérées par le service informatique grâce à l’expérience téléchargeable Portail d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7ec29-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="7ec29-110">Les instructions suivantes sont destinées aux utilisateurs qui souhaitent gérer leurs applications avec Intune.</span><span class="sxs-lookup"><span data-stu-id="7ec29-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="7ec29-111">Microsoft recommande l’utilisation d’Intune pour la gestion des applications et des appareils.</span><span class="sxs-lookup"><span data-stu-id="7ec29-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="7ec29-112">La gestion des appareils mobiles (MDM) s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7ec29-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="7ec29-113">MDM déployé + Portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="7ec29-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="7ec29-114">Applications métier (non publiques)</span><span class="sxs-lookup"><span data-stu-id="7ec29-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="7ec29-115">Installation manuelle des applications disponibles via Portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="7ec29-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="7ec29-116">Push administrateur via la stratégie MDM</span><span class="sxs-lookup"><span data-stu-id="7ec29-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="7ec29-117">Mise à jour automatique via MDM</span><span class="sxs-lookup"><span data-stu-id="7ec29-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="7ec29-118">Microsoft Store pour Entreprises</span><span class="sxs-lookup"><span data-stu-id="7ec29-118">Microsoft Store for Business</span></span>

<span data-ttu-id="7ec29-119">Le [Microsoft Store pour les entreprises](app-deploy-store-business.md) fournit aux décideurs et aux administrateurs informatiques des entreprises pour trouver, acquérir, gérer et distribuer des applications gratuites et payantes.</span><span class="sxs-lookup"><span data-stu-id="7ec29-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="7ec29-120">Les administrateurs informatiques peuvent gérer des applications Microsoft Store et des applications métier privées dans un même inventaire, ainsi qu’attribuer et réutiliser des licences en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="7ec29-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="7ec29-121">Pour plus d’informations, consultez [Configuration requise pour l’utilisation de l’Microsoft Store pour les entreprises](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="7ec29-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="7ec29-122">Les Microsoft Store pour les entreprises s’appliquent aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7ec29-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="7ec29-123">Applications publiques ou métier</span><span class="sxs-lookup"><span data-stu-id="7ec29-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="7ec29-124">Installation automatique des applications requises par le biais de l’Association MDM</span><span class="sxs-lookup"><span data-stu-id="7ec29-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="7ec29-125">L’utilisateur télécharge manuellement les applications</span><span class="sxs-lookup"><span data-stu-id="7ec29-125">User manually downloads apps</span></span>
* <span data-ttu-id="7ec29-126">Mise à jour automatique</span><span class="sxs-lookup"><span data-stu-id="7ec29-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="7ec29-127">Applications de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="7ec29-127">Microsoft Store apps</span></span>

<span data-ttu-id="7ec29-128">L’Microsoft Store fournit aux décideurs et aux administrateurs informatiques des entreprises pour rechercher, acquérir, gérer et distribuer des applications publiques.</span><span class="sxs-lookup"><span data-stu-id="7ec29-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="7ec29-129">Cette Microsoft Store s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7ec29-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="7ec29-130">Applications publiques uniquement</span><span class="sxs-lookup"><span data-stu-id="7ec29-130">Public apps only</span></span>
* <span data-ttu-id="7ec29-131">L’utilisateur télécharge manuellement les applications</span><span class="sxs-lookup"><span data-stu-id="7ec29-131">User manually downloads apps</span></span>
* <span data-ttu-id="7ec29-132">Mise à jour automatique en cas de connexion à Internet</span><span class="sxs-lookup"><span data-stu-id="7ec29-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="7ec29-133">Pour plus d’informations, consultez [applications du Store holographiques](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="7ec29-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="7ec29-134">Installer via des packages d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="7ec29-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="7ec29-135">Les [packages de configuration](app-deploy-provisioning-package.md) vous permettent d’installer des applications personnalisées ou métier, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou plusieurs appareils locaux via USB.</span><span class="sxs-lookup"><span data-stu-id="7ec29-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="7ec29-136">Cette installation peut être effectuée sans connexion Internet et pour n’importe quel type d’identité.</span><span class="sxs-lookup"><span data-stu-id="7ec29-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="7ec29-137">L’installation via des packages de configuration s’applique aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7ec29-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="7ec29-138">Applications métier/à développement automatique (non publiques)</span><span class="sxs-lookup"><span data-stu-id="7ec29-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="7ec29-139">Applications publiques (si le programme d’installation hors connexion est disponible)</span><span class="sxs-lookup"><span data-stu-id="7ec29-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="7ec29-140">Chargement côté USB uniquement</span><span class="sxs-lookup"><span data-stu-id="7ec29-140">USB side-loading only</span></span>
* <span data-ttu-id="7ec29-141">Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package d’approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="7ec29-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="7ec29-142">Installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="7ec29-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="7ec29-143">L’utilisation des utilisateurs du [programme d’installation d’application](app-deploy-app-installer.md) peut avoir une expérience simple pour l’installation d’applications sur des appareils locaux ou le partage d’une application avec une autre personne qui ne connaît pas les autres méthodes d’installation d’applications sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7ec29-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="7ec29-144">Pour ce faire, vous devez activer le mode développeur ou utiliser le portail de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="7ec29-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="7ec29-145">Il s’agit d’une méthode simple pour distribuer une application entièrement générée.</span><span class="sxs-lookup"><span data-stu-id="7ec29-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="7ec29-146">Quelle que soit la façon dont vous souhaitez simplement faire une démonstration de votre application pour un autre utilisateur avec un HoloLens, ou vous souhaitez déployer votre application, cette méthode fonctionne facilement.</span><span class="sxs-lookup"><span data-stu-id="7ec29-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="7ec29-147">L’installation via le programme d’installation d’application s’applique à :</span><span class="sxs-lookup"><span data-stu-id="7ec29-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="7ec29-148">Applications métier/à développement automatique (non publiques)</span><span class="sxs-lookup"><span data-stu-id="7ec29-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="7ec29-149">Chargement indépendant uniquement</span><span class="sxs-lookup"><span data-stu-id="7ec29-149">Side-load only</span></span>
* <span data-ttu-id="7ec29-150">Ne nécessite pas le mode développeur ou le portail de l’appareil</span><span class="sxs-lookup"><span data-stu-id="7ec29-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="7ec29-151">Facile à installer par l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="7ec29-151">Easy for end user to install</span></span>
