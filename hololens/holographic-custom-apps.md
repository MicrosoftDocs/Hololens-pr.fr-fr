---
title: gérer les applications personnalisées pour les HoloLens (1ère génération)
description: découvrez comment installer, désinstaller et charger des applications holographiques personnalisées sur des appareils HoloLens à l’aide du portail des appareils et Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, chargement, chargement en un côté, chargement indépendant, Store, UWP, application, installer
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635906"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="a974c-104">gérer les applications personnalisées pour les HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="a974c-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="a974c-105">HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que de nouvelles applications conçues spécifiquement pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a974c-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="a974c-106">Cet article se concentre sur les applications holographiques personnalisées.</span><span class="sxs-lookup"><span data-stu-id="a974c-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="a974c-107">Pour plus d’informations sur les applications du Windows Store, consultez [gérer les applications avec le Windows Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="a974c-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a974c-108">les informations suivantes ont été créées pour la HoloLens (1re génération), également appelée édition HoloLens developer à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="a974c-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="a974c-109">en tant que telles, les applications chargement via le portail des appareils et l’installation d’applications via Visual Studio étaient courantes.</span><span class="sxs-lookup"><span data-stu-id="a974c-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="a974c-110">Pour les déploiements d’entreprise, nous vous déconseillons d’activer le mode développeur, que ces deux méthodes utilisent.</span><span class="sxs-lookup"><span data-stu-id="a974c-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="a974c-111">Si vous êtes intéressé par une méthode de déploiement d’application sécurisée, consultez la [vue d’ensemble](app-deploy-overview.md)de la gestion des applications.</span><span class="sxs-lookup"><span data-stu-id="a974c-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="a974c-112">si vous recherchez une méthode de développeur pour l’installation d’applications pour HoloLens 2 appareils, consultez :</span><span class="sxs-lookup"><span data-stu-id="a974c-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="a974c-113">Portail de l’appareil : installation d’une application</span><span class="sxs-lookup"><span data-stu-id="a974c-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="a974c-114">utilisation de Visual Studio pour déployer et déboguer des applications</span><span class="sxs-lookup"><span data-stu-id="a974c-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="a974c-115">Installer des applications personnalisées</span><span class="sxs-lookup"><span data-stu-id="a974c-115">Install custom apps</span></span>

<span data-ttu-id="a974c-116">vous pouvez installer vos propres applications sur HoloLens à l’aide du portail des appareils ou en déployant les applications à partir de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a974c-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="a974c-117">Installation d’un package d’application avec le portail de l’appareil</span><span class="sxs-lookup"><span data-stu-id="a974c-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="a974c-118">Établissez une connexion entre le portail de l' [appareil](/windows/mixed-reality/using-the-windows-device-portal) et le HoloLens cible.</span><span class="sxs-lookup"><span data-stu-id="a974c-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="a974c-119">Dans le volet de navigation de gauche, accédez à la page **applications** .</span><span class="sxs-lookup"><span data-stu-id="a974c-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="a974c-120">Sous **package d’application** , accédez au fichier. AppX associé à votre application.</span><span class="sxs-lookup"><span data-stu-id="a974c-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a974c-121">Veillez à référencer les fichiers de dépendance et de certificat associés.</span><span class="sxs-lookup"><span data-stu-id="a974c-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="a974c-122">Sélectionnez **Go**.</span><span class="sxs-lookup"><span data-stu-id="a974c-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a974c-123">![installer le formulaire d’application dans Windows portail des appareils sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="a974c-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="a974c-124">déploiement à partir de Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="a974c-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="a974c-125">ouvrez la solution Visual Studio de votre application (fichier. sln).</span><span class="sxs-lookup"><span data-stu-id="a974c-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="a974c-126">Ouvrez les **Propriétés** du projet.</span><span class="sxs-lookup"><span data-stu-id="a974c-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="a974c-127">Sélectionnez la configuration de build suivante : **maître/x86/ordinateur distant**.</span><span class="sxs-lookup"><span data-stu-id="a974c-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="a974c-128">Lorsque vous sélectionnez **ordinateur distant**:</span><span class="sxs-lookup"><span data-stu-id="a974c-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="a974c-129">Assurez-vous que l’adresse pointe vers l’adresse IP Wi-Fi de votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a974c-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="a974c-130">Définissez authentification sur **universel (protocole non chiffré)**.</span><span class="sxs-lookup"><span data-stu-id="a974c-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="a974c-131">Générez votre solution.</span><span class="sxs-lookup"><span data-stu-id="a974c-131">Build your solution.</span></span>

1. <span data-ttu-id="a974c-132">pour déployer l’application à partir de votre PC de développement vers votre HoloLens, sélectionnez **Machine distante**.</span><span class="sxs-lookup"><span data-stu-id="a974c-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="a974c-133">si vous disposez déjà d’une build dans le HoloLens, sélectionnez **oui** pour installer cette version plus récente.</span><span class="sxs-lookup"><span data-stu-id="a974c-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![déploiement d’ordinateurs distants pour les applications à Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="a974c-135">L’application s’installe et se lance automatiquement sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a974c-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="a974c-136">Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrer**  >  **toutes les applications**).</span><span class="sxs-lookup"><span data-stu-id="a974c-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
