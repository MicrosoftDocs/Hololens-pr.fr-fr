---
title: Intune et portail d’entreprise
description: Intune, gestion des applications, application, portail d’entreprise, portail
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
ms.openlocfilehash: 7fcd65d5e49fa9cdd771828401749a0a41e50238
ms.sourcegitcommit: d319ac257b9ace484acf5dcfb16c9d4e19ea50a9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247216"
---
# <span data-ttu-id="4a1f5-104">Portail d'entreprise et Intune</span><span class="sxs-lookup"><span data-stu-id="4a1f5-104">Intune & Company Portal</span></span>

<span data-ttu-id="4a1f5-105">La gestion des périphériques mobiles (GPM) vous permet d’utiliser vos propres applications par le biais du [Gestionnaire de points de terminaison Microsoft](https://docs.microsoft.com/intune/windows-holographic-for-business) pour le déployer directement sur vos appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="4a1f5-106">Microsoft Intune est un service basé sur le Cloud qui est axé sur la gestion des périphériques mobiles (GPM) et la gestion des applications mobiles (GAM).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="4a1f5-107">Intune est inclus dans la [suite entreprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft, et permet aux utilisateurs d’être productifs tout en conservent la protection des données de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="4a1f5-108">Pour en savoir plus sur Intune, voir [qu’est-ce que Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="4a1f5-109">Configuration</span><span class="sxs-lookup"><span data-stu-id="4a1f5-109">Setup</span></span>

1. <span data-ttu-id="4a1f5-110">Téléchargez une application sur une ligne de Business ou téléchargez une application personnalisée sur votre client Intune.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="4a1f5-111">Voir aussi: [gestion des applications d’entreprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="4a1f5-112">[Attribuez votre application à un groupe](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="4a1f5-113">En fonction du type d’affectation que vous choisissez, vous pouvez faire en sorte que l’application soit remise automatiquement ou prête à être facilement récupérée si vous avez une sélection d’applications.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="4a1f5-114">Lors de la création de votre ensemble d’applications AppX, assurez-vous de prendre en compte l’architecture du ou des périphériques sur lesquels vous effectuez le déploiement.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="4a1f5-115">HoloLens 2 est ARM64 et HoloLens (1ère génération) est x86.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="4a1f5-116">Vous pouvez inclure les deux dans un seul ensemble d’applications AppX si vous envisagez de disposer d’un environnement d’appareils mixtes.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="4a1f5-117">Types d’affectations</span><span class="sxs-lookup"><span data-stu-id="4a1f5-117">Assignment types</span></span>

<span data-ttu-id="4a1f5-118">Si vous préférez que votre application soit installée automatiquement sur l’appareil après l’inscription, vous devez sélectionner **obligatoire** pour ce ou ces groupes.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="4a1f5-119">Si vous préférez rendre votre application disponible en téléchargement sur les utilisateurs inscrits via le portail d’entreprise, sélectionnez **disponible pour les appareils inscrits**.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="4a1f5-120">Utilisation de l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="4a1f5-120">End User Experience</span></span>

<span data-ttu-id="4a1f5-121">Après avoir configuré la configuration sur Intune, vous êtes prêt pour que les utilisateurs finaux puissent recevoir vos applications sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="4a1f5-122">Pour obtenir automatiquement vos applications, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="4a1f5-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="4a1f5-123">Inscrivez votre appareil auprès de votre client.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="4a1f5-124">Une fois que votre appareil a terminé l’inscription, vous devriez recevoir l’application sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="4a1f5-125">Si vous ne voyez pas immédiatement votre application, accédez à **paramètres**de  >  **compte**  >  **travail ou établissement d’enseignement**  >  **votrecomptehttp://www.Office.com/redir/xt102780162** et faites défiler vers le bas pour consulter des informations sur l’état des applications installées.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="4a1f5-126">Pour accéder aux applications via le portail d’entreprise, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="4a1f5-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="4a1f5-127">Ouvrez le **menu Démarrer** , puis sélectionnez **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="4a1f5-128">Recherchez **portail d’entreprise** et téléchargez l’application.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="4a1f5-129">Connectez-vous à votre compte.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-129">Sign into your account.</span></span>
4. <span data-ttu-id="4a1f5-130">Sélectionnez l’application que vous souhaitez recevoir et télécharger.</span><span class="sxs-lookup"><span data-stu-id="4a1f5-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="4a1f5-131">En savoir plus sur l' [installation automatique du portail d’entreprise et le](https://docs.microsoft.com/mem/intune/apps/company-portal-app) [déploiement et la gestion des applications dans Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="4a1f5-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
