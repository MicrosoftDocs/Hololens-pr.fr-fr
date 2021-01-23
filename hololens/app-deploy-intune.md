---
title: Intune et portail d’entreprise
description: Découvrez comment configurer, affecter et créer une expérience utilisateur confortable avec Intune, la gestion des appareils mobiles et le portail d’entreprise.
keywords: intune, gestion des applications, application, portail d’entreprise, portail, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283715"
---
# <span data-ttu-id="8c052-104">Portail d'entreprise et Intune</span><span class="sxs-lookup"><span data-stu-id="8c052-104">Intune & Company Portal</span></span>

<span data-ttu-id="8c052-105">Avec la Gestion des périphériques mobiles (MDM), vous pouvez utiliser vos propres applications personnalisées via [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) pour la déployer directement sur vos appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8c052-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="8c052-106">Microsoft Intune est un service basé sur le cloud qui se concentre sur la gestion des périphériques mobiles (MDM) et la gestion des applications mobiles (MAM).</span><span class="sxs-lookup"><span data-stu-id="8c052-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="8c052-107">Intune est inclus dans la [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft et permet aux utilisateurs d’être productifs tout en protégeant les données de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8c052-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="8c052-108">Pour en savoir plus sur Intune, lisez [Qu’est-ce qu’Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="8c052-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="8c052-109">Configuration</span><span class="sxs-lookup"><span data-stu-id="8c052-109">Setup</span></span>

1. <span data-ttu-id="8c052-110">Téléchargez une application vers un secteur d’activité ou téléchargez une application personnalisée vers votre client Intune.</span><span class="sxs-lookup"><span data-stu-id="8c052-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="8c052-111">Voir aussi : [Gestion des applications d’entreprise.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="8c052-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="8c052-112">[Affectez votre application à un groupe.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="8c052-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="8c052-113">En fonction du type d’affectation que vous choisissez, l’application peut être livrée automatiquement ou disponible pour être facilement tirée vers le bas si vous avez une sélection d’applications.</span><span class="sxs-lookup"><span data-stu-id="8c052-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="8c052-114">Lorsque vous construisez votre ensemble d’applications appx, veillez à inclure l’architecture des appareils sur lesquels vous déployez.</span><span class="sxs-lookup"><span data-stu-id="8c052-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="8c052-115">HoloLens 2 est ARM64 et HoloLens (1ère génération) est x86.</span><span class="sxs-lookup"><span data-stu-id="8c052-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="8c052-116">Vous pouvez inclure les deux dans un seul ensemble d’applications si vous envisagez d’avoir un environnement d’appareils mixtes.</span><span class="sxs-lookup"><span data-stu-id="8c052-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="8c052-117">Types d’affectation</span><span class="sxs-lookup"><span data-stu-id="8c052-117">Assignment types</span></span>

<span data-ttu-id="8c052-118">Pour que votre application soit installée automatiquement sur l’appareil après l’inscription, vous devez sélectionner **Obligatoire** pour ce ou ces groupes.</span><span class="sxs-lookup"><span data-stu-id="8c052-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="8c052-119">Pour rendre votre application disponible pour téléchargement sur les appareils inscrits via le portail d’entreprise, sélectionnez **Disponible pour les appareils inscrits.**</span><span class="sxs-lookup"><span data-stu-id="8c052-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="8c052-120">End-User expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="8c052-120">End-User Experience</span></span>

<span data-ttu-id="8c052-121">Une fois que vous avez installé la configuration sur Intune, vous êtes prêt pour les utilisateurs finaux à recevoir vos applications sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="8c052-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="8c052-122">Suivez ces étapes pour obtenir automatiquement vos applications :</span><span class="sxs-lookup"><span data-stu-id="8c052-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="8c052-123">Inscrivez votre appareil auprès de votre client.</span><span class="sxs-lookup"><span data-stu-id="8c052-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="8c052-124">Une fois l’inscription de votre appareil terminée, vous devez recevoir l’application sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="8c052-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="8c052-125">Si vous ne voyez pas votre application immédiatement, rendez-vous sur **Paramètres**Comptes Professionnel ou Scolaire vos informations de compte, puis faites défiler vers le bas pour voir les informations sur l’état de  >  \*\*\*\*  >  \*\*\*\*  >  \*\* l’application installée.</span><span class="sxs-lookup"><span data-stu-id="8c052-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="8c052-126">Comment obtenir des applications via le portail d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="8c052-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="8c052-127">Ouvrez **le menu Démarrer** et sélectionnez Microsoft **Store.**</span><span class="sxs-lookup"><span data-stu-id="8c052-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="8c052-128">Recherchez **le portail d’entreprise** et téléchargez l’application.</span><span class="sxs-lookup"><span data-stu-id="8c052-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="8c052-129">Connectez-vous à votre compte.</span><span class="sxs-lookup"><span data-stu-id="8c052-129">Sign into your account.</span></span>
4. <span data-ttu-id="8c052-130">Sélectionnez l’application que vous souhaitez recevoir et téléchargez-la.</span><span class="sxs-lookup"><span data-stu-id="8c052-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="8c052-131">En savoir plus [sur l’installation automatique du portail](https://docs.microsoft.com/mem/intune/apps/company-portal-app) d’entreprise et le déploiement et la gestion des applications dans [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="8c052-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
