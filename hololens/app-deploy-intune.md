---
title: Intune et Portail d’entreprise
description: Découvrez comment configurer, attribuer et créer une expérience utilisateur confortable avec Intune, la gestion des appareils mobiles et le portail d’entreprise.
keywords: Intune, gestion des applications, application, portail d’entreprise, portail, hololens
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308915"
---
# <a name="intune--company-portal"></a><span data-ttu-id="9ec9f-104">Portail d’entreprise & Intune</span><span class="sxs-lookup"><span data-stu-id="9ec9f-104">Intune & Company Portal</span></span>

<span data-ttu-id="9ec9f-105">Avec la gestion des appareils mobiles (MDM), vous pouvez utiliser vos propres applications personnalisées via [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) pour les déployer directement sur vos appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="9ec9f-106">Microsoft Intune est un service cloud qui se concentre sur la gestion des appareils mobiles (MDM) et la gestion des applications mobiles (GAM).</span><span class="sxs-lookup"><span data-stu-id="9ec9f-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="9ec9f-107">Intune est inclus dans la suite [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) de Microsoft, et permet aux utilisateurs d’être productifs tout en protégeant les données de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="9ec9f-108">Pour en savoir plus sur Intune, consultez [qu’est-ce qu’Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="9ec9f-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="9ec9f-109">Installation</span><span class="sxs-lookup"><span data-stu-id="9ec9f-109">Setup</span></span>

1. <span data-ttu-id="9ec9f-110">Téléchargez une application sur une activité ou téléchargez une application personnalisée sur votre locataire Intune.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="9ec9f-111">Voir aussi : [gestion des applications d’entreprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="9ec9f-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="9ec9f-112">[Affectez votre application à un groupe](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="9ec9f-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="9ec9f-113">Selon le type d’affectation que vous choisissez, l’application peut être remise automatiquement ou disponible pour être extraite facilement si vous avez sélectionné des applications.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="9ec9f-114">Lors de la création de votre bundle AppX, veillez à tenir compte de l’architecture des appareils sur lesquels vous effectuez le déploiement.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="9ec9f-115">HoloLens 2 est ARM64 et HoloLens (1re génération) est x86.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="9ec9f-116">Vous pouvez inclure les deux dans un même Bundle AppX si vous prévoyez d’avoir un environnement mixte d’appareils.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="9ec9f-117">Types d’attributions</span><span class="sxs-lookup"><span data-stu-id="9ec9f-117">Assignment types</span></span>

<span data-ttu-id="9ec9f-118">Pour que votre application soit automatiquement installée sur l’appareil après l’inscription, vous devez sélectionner **obligatoire** pour ce (s) groupe (s).</span><span class="sxs-lookup"><span data-stu-id="9ec9f-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="9ec9f-119">Pour que votre application soit disponible en téléchargement sur des appareils inscrits via le portail d’entreprise, sélectionnez **disponible pour les appareils inscrits**.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="9ec9f-120">Expérience de l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="9ec9f-120">End-User Experience</span></span>

<span data-ttu-id="9ec9f-121">Une fois que vous avez configuré la configuration sur Intune, vous êtes prêt pour que les utilisateurs finaux puissent recevoir vos applications sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="9ec9f-122">Procédez comme suit pour récupérer automatiquement vos applications :</span><span class="sxs-lookup"><span data-stu-id="9ec9f-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="9ec9f-123">Inscrivez votre appareil auprès de votre locataire.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="9ec9f-124">Une fois l’inscription de votre appareil terminée, vous devez recevoir l’application sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="9ec9f-125">Si vous ne voyez pas immédiatement l’application, accédez à **paramètres**  >  **comptes**  >  **professionnel ou école**  >  informations de *votre compte* , puis faites défiler la page pour afficher les informations sur l’état de l’application installée.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="9ec9f-126">Comment accéder aux applications via l’Portail d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="9ec9f-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="9ec9f-127">Ouvrez le **menu Démarrer** et sélectionnez **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="9ec9f-128">Recherchez **portail d’entreprise** et téléchargez l’application.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="9ec9f-129">Connectez-vous à votre compte.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-129">Sign into your account.</span></span>
4. <span data-ttu-id="9ec9f-130">Sélectionnez l’application que vous souhaitez recevoir et téléchargez-la.</span><span class="sxs-lookup"><span data-stu-id="9ec9f-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="9ec9f-131">En savoir plus sur [l’installation automatique du portail d’entreprise et le](https://docs.microsoft.com/mem/intune/apps/company-portal-app) [déploiement et la gestion d’applications dans Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="9ec9f-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
