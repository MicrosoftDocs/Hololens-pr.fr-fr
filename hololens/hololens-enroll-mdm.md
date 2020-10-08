---
title: Inscrire HoloLens dans GPM
description: Inscrire HoloLens dans Gestion des périphériques mobiles (GPM) pour faciliter la gestion de plusieurs appareils.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102323"
---
# <span data-ttu-id="0ccd2-103">Inscrire HoloLens dans un logiciel de gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="0ccd2-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="0ccd2-104">Vous pouvez gérer plusieurs appareils Microsoft HoloLens en même temps à l’aide de solutions comme [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="0ccd2-105">Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="0ccd2-106">Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="0ccd2-107">La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="0ccd2-108">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="0ccd2-108">Requirements</span></span>

 <span data-ttu-id="0ccd2-109">Pour pouvoir gérer les appareils HoloLens, votre organisation doit disposer de la gestion des périphériques mobiles (GPM).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="0ccd2-110">Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="0ccd2-111">Différentes façons de s’inscrire</span><span class="sxs-lookup"><span data-stu-id="0ccd2-111">Different ways to enroll</span></span>

<span data-ttu-id="0ccd2-112">Selon le type d’identité choisi lors de la connexion OOBE ou après l’inscription, il existe différentes méthodes d’inscription.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="0ccd2-113">Pour en savoir plus sur chaque type d’identité sur HoloLens, consultez [cette page](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="0ccd2-114">Si Identity est AAD, vous pouvez le faire au cours de l’utilisation de l' **application**OOBE ou du  ->  bouton**School**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="0ccd2-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0ccd2-115">Pour l’inscription AAD, l’inscription de la gestion des appareils mobiles automatique se produit uniquement si AAD a été configuré avec les URL d’inscription.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="0ccd2-116">Si Identity est AAD et que l’appareil a été préconfiguré et qu’il a été enregistré avec un profil de configuration Intune et qu’il est affecté, l’inscription AAD et l’inscription se produiront automatiquement dans OOBE.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="0ccd2-117">Également appelé [flux AutoPilot](hololens2-autopilot.md) disponible dans les [Builds 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="0ccd2-118">Si Identity est MSA, utilisez le bouton d’accès à l' **application paramètres**d’utilisation  ->  **ou de School**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="0ccd2-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0ccd2-119">Également appelé flux d’ajout de compte de bureau (AWA).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="0ccd2-120">Si Identity est un utilisateur local, utilisez **Settings App**  ->  **Access Work ou School**  ->  **ENROLL only dans le lien gestion des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="0ccd2-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="0ccd2-121">Également appelé flux d’inscription pour le GPM.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="0ccd2-122">Une fois que l’appareil est inscrit auprès de votre serveur de gestion des périphériques mobiles, l’application paramètres indique désormais que l’appareil est inscrit à la gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="0ccd2-123">Inscription automatique dans GPM</span><span class="sxs-lookup"><span data-stu-id="0ccd2-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="0ccd2-124">Si votre organisation utilise Azure ActiveDirectory (Azure AD) et une solution GPM qui accepte un jeton AAD pour l’authentification (uniquement pris en charge pour l’instant dans MicrosoftIntune et AirWatch), votre administrateur informatique peut configurer Azure AD de manière à autoriser automatiquement l’inscription GPM une fois que l’utilisateur s’est connecté avec son compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="0ccd2-125">Découvrez comment configurer l’inscription Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="0ccd2-126">Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="0ccd2-127">Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.</span><span class="sxs-lookup"><span data-stu-id="0ccd2-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="0ccd2-128">Lorsqu’un appareil est rejoint AAD, il peut affecter les personnes qui ont considéré le propriétaire de l' [appareil](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="0ccd2-129">Désinscrire HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="0ccd2-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="0ccd2-130">Pour en savoir plus sur l’annulation de l’inscription d’un appareil, consultez [cette page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="0ccd2-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
