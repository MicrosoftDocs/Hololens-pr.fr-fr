---
title: Inscrire HoloLens dans GPM
description: Découvrez comment inscrire HoloLens dans la gestion des périphériques mobiles (MDM) pour faciliter la gestion de plusieurs appareils.
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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400674"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="0e21c-103">Inscrire HoloLens dans GPM</span><span class="sxs-lookup"><span data-stu-id="0e21c-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="0e21c-104">Vous pouvez gérer plusieurs appareils Microsoft HoloLens simultanément à l’aide de solutions [telles que Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="0e21c-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="0e21c-105">Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="0e21c-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="0e21c-106">Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="0e21c-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="0e21c-107">La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0e21c-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="0e21c-108">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="0e21c-108">Requirements</span></span>

 <span data-ttu-id="0e21c-109">Votre organisation devra configurer la gestion des périphériques mobiles (MDM) pour gérer les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0e21c-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="0e21c-110">Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e21c-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="0e21c-111">Différentes façons de s’inscrire</span><span class="sxs-lookup"><span data-stu-id="0e21c-111">Different ways to enroll</span></span>

<span data-ttu-id="0e21c-112">Selon le type d’identité [choisi lors](hololens-identity.md) de la OOBE ou de la post-inscription, il existe différentes méthodes d’inscription.</span><span class="sxs-lookup"><span data-stu-id="0e21c-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="0e21c-113">Si l’identité est Azure AD, pendant la OOBE ou le bouton **Paramètres d’accès**à l’application  ->  **Travail ou Connexion**  ->  **scolaire.**</span><span class="sxs-lookup"><span data-stu-id="0e21c-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0e21c-114">Pour Azure AD, l’inscription [mdm](hololens-enroll-mdm.md#auto-enrollment-in-mdm) automatique se produit uniquement si Azure AD a été configuré avec des URL d’inscription.</span><span class="sxs-lookup"><span data-stu-id="0e21c-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span> 
     
- <span data-ttu-id="0e21c-115">Si l’identité est Azure AD et que l’appareil a été pré-inscrit auprès du serveur MDM Intune avec un profil de configuration spécifique qui lui est affecté, Azure AD-Join et l’inscription [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) automatique se produisent pendant la phase OOBE.</span><span class="sxs-lookup"><span data-stu-id="0e21c-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="0e21c-116">Également appelé [flux Autopilot](hololens2-autopilot.md) disponible [dans les builds 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="0e21c-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="0e21c-117">Si l’identité est MSA, utilisez le bouton **Paramètres App**  ->  **Access Work ou School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="0e21c-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0e21c-118">Également appelé flux Ajouter un compte de travail (AWA).</span><span class="sxs-lookup"><span data-stu-id="0e21c-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="0e21c-119">Si l’identité est Utilisateur local, utilisez **Paramètres App**  ->  **Access Work ou School**  ->  **Enroll uniquement dans** le lien gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="0e21c-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="0e21c-120">Également appelé flux d’inscription MDM pur.</span><span class="sxs-lookup"><span data-stu-id="0e21c-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="0e21c-121">Une fois que l’appareil est inscrit auprès de votre serveur MDM, l’application Paramètres reflète désormais que l’appareil est inscrit dans la gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="0e21c-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="0e21c-122">Inscription automatique dans GPM</span><span class="sxs-lookup"><span data-stu-id="0e21c-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="0e21c-123">Si votre organisation dispose d’un abonnement [Azure Premium](https://azure.microsoft.com/overview/), utilise Azure Active Directory (Azure AD) et une solution MDM qui accepte un jeton Azure AD pour l’authentification (actuellement uniquement pris en charge dans Microsoft Intune et AirWatch), votre administrateur informatique peut configurer Azure AD pour autoriser automatiquement l’inscription MDM une fois que l’utilisateur s’est inscrit avec son compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0e21c-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="0e21c-124">Découvrez comment configurer l’inscription Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0e21c-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="0e21c-125">Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0e21c-125">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="0e21c-126">Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.</span><span class="sxs-lookup"><span data-stu-id="0e21c-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="0e21c-127">Lorsqu’un appareil est joint à Azure AD, cela peut affecter les personnes considérées comme [propriétaires de l’appareil.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="0e21c-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="0e21c-128">Désinscrire HoloLens d’Intune</span><span class="sxs-lookup"><span data-stu-id="0e21c-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="0e21c-129">Bien que HoloLens 2 soit un appareil Windows 10, il ne peut pas être simplement désinsaiscé d’Intune.</span><span class="sxs-lookup"><span data-stu-id="0e21c-129">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="0e21c-130">Si vous souhaitez déjoindralisez HoloLens d’Azure AD ou rejoignez-le à un autre client Azure AD, vous devez réinitialiser/réinitialiser l’appareil. [](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device)</span><span class="sxs-lookup"><span data-stu-id="0e21c-130">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>