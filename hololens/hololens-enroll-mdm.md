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
ms.openlocfilehash: 7c17cbf88fc2e7a6dcd9aa600ad6e6910edb29a8
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253231"
---
# <span data-ttu-id="23f65-103">Inscrire HoloLens dans un logiciel de gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="23f65-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="23f65-104">Vous pouvez gérer plusieurs appareils Microsoft HoloLens en même temps à l’aide de solutions comme [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="23f65-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="23f65-105">Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="23f65-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="23f65-106">Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="23f65-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="23f65-107">La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="23f65-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="23f65-108">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="23f65-108">Requirements</span></span>

 <span data-ttu-id="23f65-109">Pour pouvoir gérer les appareils HoloLens, votre organisation doit disposer de la gestion des périphériques mobiles (GPM).</span><span class="sxs-lookup"><span data-stu-id="23f65-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="23f65-110">Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23f65-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="23f65-111">Différentes façons de s’inscrire</span><span class="sxs-lookup"><span data-stu-id="23f65-111">Different ways to enroll</span></span>

<span data-ttu-id="23f65-112">Selon le type d’identité choisi lors de la connexion OOBE ou après l’inscription, il existe différentes méthodes d’inscription.</span><span class="sxs-lookup"><span data-stu-id="23f65-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="23f65-113">Pour en savoir plus sur chaque type d’identité sur HoloLens, consultez [cette page](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="23f65-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="23f65-114">Si Identity est Azure ad, vous pouvez utiliser le bouton d’accès à l’application dans OOBE ou dans l' **application**  ->  **de bureau ou de scolaires**  ->  \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="23f65-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="23f65-115">Dans le cas d’Azure AD, l’inscription automatique de la gestion des périphériques mobiles est effectuée uniquement si Azure AD a été configuré avec les URL d’inscription.</span><span class="sxs-lookup"><span data-stu-id="23f65-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="23f65-116">S’il s’agit d’une identité Azure AD et que l’appareil a été préalablement inscrit auprès du serveur Intune GPM avec un profil de configuration spécifique qui lui est affecté, Azure AD-Join et inscription se produiront automatiquement dans OOBE.</span><span class="sxs-lookup"><span data-stu-id="23f65-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="23f65-117">Également appelé [flux AutoPilot](hololens2-autopilot.md) disponible dans les [Builds 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="23f65-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="23f65-118">Si Identity est MSA, utilisez le bouton d’accès à l' **application paramètres**d’utilisation  ->  **ou de School**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="23f65-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="23f65-119">Également appelé flux d’ajout de compte de bureau (AWA).</span><span class="sxs-lookup"><span data-stu-id="23f65-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="23f65-120">Si Identity est un utilisateur local, utilisez **Settings App**  ->  **Access Work ou School**  ->  **ENROLL only dans le lien gestion des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="23f65-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="23f65-121">Également appelé flux d’inscription pour le GPM.</span><span class="sxs-lookup"><span data-stu-id="23f65-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="23f65-122">Une fois que l’appareil est inscrit auprès de votre serveur de gestion des périphériques mobiles, l’application paramètres indique désormais que l’appareil est inscrit à la gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="23f65-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="23f65-123">Inscription automatique dans GPM</span><span class="sxs-lookup"><span data-stu-id="23f65-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="23f65-124">Si votre organisation utilise Azure Active Directory (Azure AD) et une solution GPM qui accepte un jeton Azure AD pour l’authentification (actuellement, uniquement prise en charge dans Microsoft Intune et à l’aide de la fonctionnalité d’aide à la réception), votre administrateur informatique peut configurer Azure AD de manière à ce que l’utilisateur se connecte avec son compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23f65-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="23f65-125">Découvrez comment configurer l’inscription Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23f65-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="23f65-126">Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="23f65-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="23f65-127">Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.</span><span class="sxs-lookup"><span data-stu-id="23f65-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="23f65-128">Lorsqu’un appareil est une jointure Azure AD, il peut affecter les personnes qui ont considéré le propriétaire de l' [appareil](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="23f65-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="23f65-129">Désinscrire HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="23f65-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="23f65-130">Pour en savoir plus sur l’annulation de l’inscription d’un appareil, consultez [cette page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="23f65-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
