---
title: Inscrire HoloLens dans GPM
description: découvrez comment inscrire HoloLens dans la gestion des appareils mobiles (MDM) pour faciliter la gestion de plusieurs appareils.
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
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640404"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="b31b1-103">Inscrire HoloLens dans GPM</span><span class="sxs-lookup"><span data-stu-id="b31b1-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="b31b1-104">vous pouvez gérer plusieurs appareils Microsoft HoloLens simultanément à l’aide de solutions comme [Microsoft Intune](/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="b31b1-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="b31b1-105">Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="b31b1-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="b31b1-106">consultez [gérer les appareils exécutant Windows holographique avec Microsoft Intune](/intune/windows-holographic-for-business), les [fournisseurs de services de configuration pris en charge dans Windows holographique](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="b31b1-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="b31b1-107">La gestion des appareils mobiles (MDM), y compris les fonctionnalités VPN, BitLocker et en mode plein écran, est disponible uniquement lorsque vous [effectuez une mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b31b1-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="b31b1-108">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b31b1-108">Requirements</span></span>

 <span data-ttu-id="b31b1-109">votre organisation doit configurer la gestion des appareils mobiles (MDM) pour gérer les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b31b1-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="b31b1-110">Votre fournisseur GPM peut être Microsoft Intune ou un fournisseur tiers qui utilise les API GPM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b31b1-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="b31b1-111">Différentes façons d’inscrire</span><span class="sxs-lookup"><span data-stu-id="b31b1-111">Different ways to enroll</span></span>

<span data-ttu-id="b31b1-112">Selon le type d' [identité](hololens-identity.md) choisi pendant l’OOBE ou la publication, il existe différentes méthodes d’inscription.</span><span class="sxs-lookup"><span data-stu-id="b31b1-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="b31b1-113">si l’identité est Azure AD, alors lors de l’utilisation d’OOBE ou **Paramètres**  ->  Connecter bouton d'**accès professionnel ou scolaire**  ->   .</span><span class="sxs-lookup"><span data-stu-id="b31b1-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="b31b1-114">Par Azure AD, l' [inscription automatique à MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se produit uniquement si Azure ad a été configuré avec des URL d’inscription.</span><span class="sxs-lookup"><span data-stu-id="b31b1-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="b31b1-115">Si l’identité est Azure AD et que l’appareil a été préalablement inscrit auprès du serveur MDM Intune avec un profil de configuration spécifique affecté, le AD-Join Azure et l' [inscription automatique à MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se produiront au cours d’OOBE.</span><span class="sxs-lookup"><span data-stu-id="b31b1-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="b31b1-116">Également appelé le [déroulement AutoPilot](hololens2-autopilot.md) disponible dans [19041.1103 + builds](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="b31b1-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="b31b1-117">si l’identité est MSA, utilisez **Paramètres** bouton Connecter d’accès à l’application ou à l'  ->  **école**  ->   .</span><span class="sxs-lookup"><span data-stu-id="b31b1-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="b31b1-118">Également appelé Flow AWA (ajouter un compte professionnel).</span><span class="sxs-lookup"><span data-stu-id="b31b1-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="b31b1-119">si l’identité est utilisateur Local, utilisez **Paramètres** accès à l’application ou à l'  ->    ->  **inscription scolaire uniquement dans le lien de gestion des périphériques** .</span><span class="sxs-lookup"><span data-stu-id="b31b1-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="b31b1-120">Également appelé un workflow d’inscription MDM pur.</span><span class="sxs-lookup"><span data-stu-id="b31b1-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="b31b1-121">une fois que l’appareil est inscrit auprès de votre serveur MDM, l’application Paramètres reflète à présent que l’appareil est inscrit dans la gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="b31b1-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="b31b1-122">Inscription automatique dans GPM</span><span class="sxs-lookup"><span data-stu-id="b31b1-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="b31b1-123">si votre organisation dispose d’un [abonnement Azure Premium](https://azure.microsoft.com/overview/), utilise Azure Active Directory (Azure AD) et une solution de gestion des appareils mobiles qui accepte un jeton Azure AD pour l’authentification (actuellement pris en charge uniquement dans Microsoft Intune et la surveillance), votre administrateur informatique peut configurer Azure AD pour autoriser automatiquement l’inscription MDM une fois que l’utilisateur se connecte avec son compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b31b1-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="b31b1-124">Découvrez comment configurer l’inscription Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b31b1-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="b31b1-125">Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b31b1-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="b31b1-126">Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.</span><span class="sxs-lookup"><span data-stu-id="b31b1-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="b31b1-127">Quand un appareil est Azure AD joint, il peut affecter les personnes qui ont considéré le propriétaire de l' [appareil](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="b31b1-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="b31b1-128">désinscrire HoloLens d’Intune</span><span class="sxs-lookup"><span data-stu-id="b31b1-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="b31b1-129">Selon la méthode d’inscription, l’annulation de l’inscription de votre appareil peut ne pas être disponible.</span><span class="sxs-lookup"><span data-stu-id="b31b1-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="b31b1-130">Si votre appareil a été inscrit avec un compte Azure AD ou AutoPilot, il ne peut pas être désinscrit d’Intune.</span><span class="sxs-lookup"><span data-stu-id="b31b1-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="b31b1-131">si vous souhaitez annuler la jointure HoloLens de Azure AD ou le rejoindre à un locataire différent pour Azure AD, vous devez [réinitialiser/](hololens-recovery.md#reset-the-device) recommencer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b31b1-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="b31b1-132">Si votre appareil a été inscrit auprès d’un compte MSA qui a ajouté un compte professionnel ou à partir d’un compte local inscrit uniquement dans la gestion des appareils, vous pouvez annuler l’inscription de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b31b1-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="b31b1-133">ouvrez le menu Démarrer, puis sélectionnez **Paramètres**  ->  bouton de déconnexion YourAccount d'**accès à l’application ou scolaire**  ->    ->   .</span><span class="sxs-lookup"><span data-stu-id="b31b1-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>