---
title: Exigences relatives à la licence
description: Restez à jour avec toutes les exigences de licence et les instructions dont vous avez besoin pour la gestion des appareils mobiles, HoloLens et Remote Assist.
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
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283965"
---
# <span data-ttu-id="6a183-103">Exigences relatives à la licence</span><span class="sxs-lookup"><span data-stu-id="6a183-103">License requirements</span></span>

## <span data-ttu-id="6a183-104">Aide sur les licences de gestion des appareils mobiles (MDM)</span><span class="sxs-lookup"><span data-stu-id="6a183-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="6a183-105">Si vous prévoyez de gérer vos appareils HoloLens, vous aurez besoin d’Azure AD et d’un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="6a183-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="6a183-106">Active Director (AD) ne peut pas être utilisé pour gérer les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6a183-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="6a183-107">Si vous prévoyez l'utilisation d'une gestion des appareils mobiles autres que Intune, des licences [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) sont requises.</span><span class="sxs-lookup"><span data-stu-id="6a183-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="6a183-108">Si vous envisagez d’utiliser Intune comme MDM, consultez la [liste des suites](https://docs.microsoft.com/intune/fundamentals/licenses) qui inclut des licences Intune.</span><span class="sxs-lookup"><span data-stu-id="6a183-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="6a183-109">Notez qu’Azure Active AD est inclus dans la majorité de ces suites.</span><span class="sxs-lookup"><span data-stu-id="6a183-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="6a183-110">Identifier les licences nécessaires pour votre scénario et vos produits</span><span class="sxs-lookup"><span data-stu-id="6a183-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="6a183-111">Conditions d’acquisition de Licences de HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="6a183-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="6a183-112">Vous devez peut-être mettre à niveau votre appareil HoloLens (1ère génération) vers Windows Holographic pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="6a183-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="6a183-113">(Voir [Fonctionnalités commerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) pour déterminer si vous avez besoin d'une mise à niveau).</span><span class="sxs-lookup"><span data-stu-id="6a183-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="6a183-114">Si c’est le cas, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a183-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="6a183-115">Acquérir un fichier XML de licence HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="6a183-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="6a183-116">Appliquer le fichier XML au HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6a183-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="6a183-117">Pour ce faire, vous pouvez utiliser un [Package d’approvisionnement ](hololens-provisioning.md) ou via votre [Gestionnaire des appareils mobiles ](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="6a183-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="6a183-118">Configuration requise pour la licence Remote Assist</span><span class="sxs-lookup"><span data-stu-id="6a183-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="6a183-119">Assurez-vous que vous avez la licence et l’appareil requis, que vous pouvez consulter dans la documentation des [conditions requises](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="6a183-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="6a183-120">Licence Remote Assist</span><span class="sxs-lookup"><span data-stu-id="6a183-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="6a183-121">Ou essayer une version d’évaluation de [Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="6a183-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="6a183-122">Équipes Freemium et Teams</span><span class="sxs-lookup"><span data-stu-id="6a183-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="6a183-123">Licence Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6a183-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="6a183-124">Si vous envisagez de mettre en œuvre **[ce scénario entre tenants](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, vous aurez peut-être besoin d’une licence Cloisonnement de l’information.</span><span class="sxs-lookup"><span data-stu-id="6a183-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="6a183-125">Consultez [cet article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) pour déterminer si une licence Cloisonnement de l’information est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6a183-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="6a183-126">Guides sur les exigences relatives à la licence</span><span class="sxs-lookup"><span data-stu-id="6a183-126">Guides License Requirements</span></span>

<span data-ttu-id="6a183-127">Consultez les [licences et les appareils requis mis à jour](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="6a183-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="6a183-128">Licence Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6a183-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="6a183-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="6a183-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="6a183-130">Guides</span><span class="sxs-lookup"><span data-stu-id="6a183-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
