---
title: Exigences relatives à la licence
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956760"
---
# <span data-ttu-id="b3371-102">Exigences relatives à la licence</span><span class="sxs-lookup"><span data-stu-id="b3371-102">License requirements</span></span>

## <span data-ttu-id="b3371-103">Aide sur les licences de gestion des appareils mobiles (MDM)</span><span class="sxs-lookup"><span data-stu-id="b3371-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="b3371-104">Si vous prévoyez de gérer vos appareils HoloLens, vous aurez besoin d’Azure AD et d’un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="b3371-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="b3371-105">Active Director (AD) ne peut pas être utilisé pour gérer les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3371-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="b3371-106">Si vous prévoyez l'utilisation d'une gestion des appareils mobiles autre que Intune, des licences [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) sont requises.</span><span class="sxs-lookup"><span data-stu-id="b3371-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="b3371-107">Si vous comptez utiliser Intune pour la gestion des appareils mobiles, [voici](https://docs.microsoft.com/intune/fundamentals/licenses) une liste de suites qui comprennent des licences Intune.</span><span class="sxs-lookup"><span data-stu-id="b3371-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="b3371-108">Notez qu’Azure Active AD est inclus dans la majorité de ces suites.</span><span class="sxs-lookup"><span data-stu-id="b3371-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="b3371-109">Identifier les licences nécessaires pour votre scénario et vos produits</span><span class="sxs-lookup"><span data-stu-id="b3371-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="b3371-110">Conditions d’acquisition de Licences de HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="b3371-110">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="b3371-111">Vous devez peut-être mettre à niveau votre appareil HoloLens (1ère génération) vers Windows Holographic pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="b3371-111">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="b3371-112">(Voir [Fonctionnalités commerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) pour déterminer si vous avez besoin d'une mise à niveau).</span><span class="sxs-lookup"><span data-stu-id="b3371-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="b3371-113">Si c’est le cas, vous devez effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="b3371-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="b3371-114">Acquérir un fichier XML de licence HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="b3371-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="b3371-115">Appliquer le fichier XML au HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3371-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="b3371-116">Pour ce faire, vous pouvez utiliser un [Package d’approvisionnement ](hololens-provisioning.md) ou via votre [Gestionnaire des appareils mobiles ](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="b3371-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="b3371-117">Configuration requise pour la licence Remote Assist</span><span class="sxs-lookup"><span data-stu-id="b3371-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="b3371-118">Assurez-vous que vous disposez des licences et des appareils requis.</span><span class="sxs-lookup"><span data-stu-id="b3371-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="b3371-119">Les mises à jour des licences et des exigences concernant les produits sont disponibles [ici](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="b3371-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="b3371-120">Licence Remote Assist</span><span class="sxs-lookup"><span data-stu-id="b3371-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="b3371-121">Ou essayer une version d’évaluation de [Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="b3371-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="b3371-122">Équipes Freemium et Teams</span><span class="sxs-lookup"><span data-stu-id="b3371-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="b3371-123">Licence Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b3371-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="b3371-124">Si vous envisagez de mettre en œuvre **[ce scénario entre tenants](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, vous aurez peut-être besoin d’une licence Cloisonnement de l’information.</span><span class="sxs-lookup"><span data-stu-id="b3371-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="b3371-125">Consultez [cet article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) pour déterminer si une licence Cloisonnement de l’information est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b3371-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="b3371-126">Guides sur les exigences relatives à la licence</span><span class="sxs-lookup"><span data-stu-id="b3371-126">Guides License Requirements</span></span>

<span data-ttu-id="b3371-127">Les mises à jour des licences et des exigences concernant les appareils sont disponibles [ici](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="b3371-127">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="b3371-128">Licence Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b3371-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="b3371-129">PowerBI</span><span class="sxs-lookup"><span data-stu-id="b3371-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="b3371-130">Guides</span><span class="sxs-lookup"><span data-stu-id="b3371-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
