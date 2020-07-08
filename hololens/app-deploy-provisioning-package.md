---
title: Package de mise à service
description: application, déploiement de l’application, application d’entreprise demployment, approvisionnement
keywords: application, déploiement de l’application, application d’entreprise demployment, approvisionnement
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857911"
---
# <span data-ttu-id="b96f8-104">Package de mise à service</span><span class="sxs-lookup"><span data-stu-id="b96f8-104">Provisioning Package</span></span>

<span data-ttu-id="b96f8-105">Les packages de mise en service peuvent être utilisés pour préparer et configurer des appareils dans un environnement sans accès à la gestion des points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="b96f8-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="b96f8-106">Elles peuvent également être déployées sur un appareil quelle que soit l’identité de l’utilisateur, l’état de l’inscription, lors de l’utilisation de OOBE (out-of-Box Experience) ou en [appliquant un package de mise](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)à disponibilité lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="b96f8-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="b96f8-107">Considérations relatives aux packages de mise en service:</span><span class="sxs-lookup"><span data-stu-id="b96f8-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="b96f8-108">Applications non publiques</span><span class="sxs-lookup"><span data-stu-id="b96f8-108">Non-Public apps</span></span>
* <span data-ttu-id="b96f8-109">Télécharger uniquement le bus USB</span><span class="sxs-lookup"><span data-stu-id="b96f8-109">USB side-load only</span></span>
* <span data-ttu-id="b96f8-110">Aucune mise à jour automatique (nécessite des mises à jour manuelles via PPKGs)</span><span class="sxs-lookup"><span data-stu-id="b96f8-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="b96f8-111">Pour découvrir les notions de base de la création d’un package de mise à service pour les appareils HoloLens, visitez [approvisionnement HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="b96f8-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="b96f8-112">Pour déployer une application, vous devez commencer par la mise en service avancée.</span><span class="sxs-lookup"><span data-stu-id="b96f8-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="b96f8-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="b96f8-113">Setup</span></span>

<span data-ttu-id="b96f8-114">Dans le [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b96f8-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="b96f8-115">Définissez ApplicationManagement/AllowAllTrustedApps sur «Yes».</span><span class="sxs-lookup"><span data-stu-id="b96f8-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="b96f8-116">Voir: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="b96f8-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="b96f8-117">Sous **UniversalAppInstall**  >  **UserContextAppLicense** Veuillez entrer le **propriété packagefamilyname**.</span><span class="sxs-lookup"><span data-stu-id="b96f8-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="b96f8-118">Voir [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="b96f8-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="b96f8-119">Voir aussi: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="b96f8-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="b96f8-120">Si vous ne le connaissez pas, vous pouvez utiliser Device Portal sur un appareil sur lequel vous avez déjà installé votre application.</span><span class="sxs-lookup"><span data-stu-id="b96f8-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="b96f8-121">Accédez à la page applications et examinez la ligne PackageRelativeID, toutes les informations précédant le «!». Est votre **propriété packagefamilyname**.</span><span class="sxs-lookup"><span data-stu-id="b96f8-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="b96f8-122">Vous verrez alors que vous avez une nouvelle section **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="b96f8-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="b96f8-123">Utilisez cette zone pour télécharger votre bundle Appx.</span><span class="sxs-lookup"><span data-stu-id="b96f8-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="b96f8-124">Selon que vous avez acheté votre application ou créé votre propre application métier, vous devrez télécharger le fichier de licence ou le certificat de sécurité.</span><span class="sxs-lookup"><span data-stu-id="b96f8-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="b96f8-125">Pour le fichier de licence: sous **UniversalAppInstall**  >  **UserContextAppLience** et naviguez jusqu’à l’emplacement de votre licence et chargez-le.</span><span class="sxs-lookup"><span data-stu-id="b96f8-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="b96f8-126">Dans le cas d’un fichier de sécurité, accédez à **certificats** et sélectionnez votre certificat à installer avec votre bundle. Appx.</span><span class="sxs-lookup"><span data-stu-id="b96f8-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="b96f8-127">Veillez à enregistrer votre projet dans un emplacement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="b96f8-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="b96f8-128">Ensuite, **exportez** -la en tant que **package de mise en service**.</span><span class="sxs-lookup"><span data-stu-id="b96f8-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="b96f8-129">Voir aussi: [appliquer votre package provisiong au HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="b96f8-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
