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
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828095"
---
# <span data-ttu-id="c4ff2-103">Inscrire HoloLens dans un logiciel de gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="c4ff2-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="c4ff2-104">Vous pouvez gérer plusieurs appareils Microsoft HoloLens en même temps à l’aide de solutions comme [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="c4ff2-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="c4ff2-105">Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="c4ff2-106">Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="c4ff2-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="c4ff2-107">La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c4ff2-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="c4ff2-108">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="c4ff2-108">Requirements</span></span>

 <span data-ttu-id="c4ff2-109">Pour pouvoir gérer les appareils HoloLens, votre organisation doit disposer de la gestion des périphériques mobiles (GPM).</span><span class="sxs-lookup"><span data-stu-id="c4ff2-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="c4ff2-110">Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="c4ff2-111">Inscription automatique dans GPM</span><span class="sxs-lookup"><span data-stu-id="c4ff2-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="c4ff2-112">Si votre organisation utilise Azure ActiveDirectory (Azure AD) et une solution GPM qui accepte un jeton AAD pour l’authentification (uniquement pris en charge pour l’instant dans MicrosoftIntune et AirWatch), votre administrateur informatique peut configurer Azure AD de manière à autoriser automatiquement l’inscription GPM une fois que l’utilisateur s’est connecté avec son compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="c4ff2-113">Découvrez comment configurer l’inscription Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="c4ff2-114">Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="c4ff2-115">Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="c4ff2-116">Inscription via l’application Paramètres</span><span class="sxs-lookup"><span data-stu-id="c4ff2-116">Enroll through Settings app</span></span>

 <span data-ttu-id="c4ff2-117">Lorsque l’appareil n’est pas inscrit dans GPM lors de sa première utilisation, l’utilisateur peut l'inscrire manuellement avec le serveur GPM de l’entreprise via l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="c4ff2-118">Rendez-vous sur **Paramètres** > **Comptes** > **Accès professionnel**.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="c4ff2-119">Sélectionnez **Inscription GPM (gestion des périphériques mobiles)** et saisissez le compte de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="c4ff2-120">Vous serez redirigé vers la page de connexion de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="c4ff2-121">Si l’authentification aboutit sur le serveur GPM, un message de réussite s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="c4ff2-122">Votre appareil est maintenant inscrit auprès de votre serveur GPM.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="c4ff2-123">L’application Paramètres montre maintenant que le périphérique est inscrit dans la gestion des périphériques.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="c4ff2-124">Désinscrire HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="c4ff2-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="c4ff2-125">Vous ne pouvez pas [désinscrire](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) un HoloLens de Intune à distance.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="c4ff2-126">Si l’administrateur désinscrit l’appareil à l’aide de la GPM, l’appareil demeurera en dehors du tableau de bord Intune.</span><span class="sxs-lookup"><span data-stu-id="c4ff2-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
