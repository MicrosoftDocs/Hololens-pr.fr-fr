---
title: Gérer des applications personnalisées pour HoloLens (1ère génération)
description: Découvrez comment installer, désinstaller et charger des applications holographiques personnalisées sur des appareils HoloLens à l’aide du portail des appareils et de Visual Studio.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308658"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="f1a9d-104">Gérer des applications personnalisées pour HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="f1a9d-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="f1a9d-105">HoloLens prend en charge de nombreuses applications existantes à partir du Microsoft Store, ainsi que de nouvelles applications spécifiquement conçues pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="f1a9d-106">Cet article se concentre sur les applications holographiques personnalisées.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="f1a9d-107">Pour plus d’informations sur les applications du Windows Store, consultez [gérer les applications avec le Windows Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="f1a9d-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1a9d-108">Les informations suivantes ont été créées pour le HoloLens (1re génération), également appelé l’édition de développement HoloLens à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="f1a9d-109">En tant que telles, les applications chargement via le portail des appareils et l’installation d’applications via Visual Studio étaient courantes.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="f1a9d-110">Pour les déploiements d’entreprise, nous vous déconseillons d’activer le mode développeur, que ces deux méthodes utilisent.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="f1a9d-111">Si vous êtes intéressé par une méthode de déploiement d’application sécurisée, consultez la [vue d’ensemble](app-deploy-overview.md)de la gestion des applications.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="f1a9d-112">Si vous recherchez une méthode de développeur pour l’installation d’applications pour les appareils HoloLens 2, reportez-vous à :</span><span class="sxs-lookup"><span data-stu-id="f1a9d-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="f1a9d-113">Portail de l’appareil : installation d’une application</span><span class="sxs-lookup"><span data-stu-id="f1a9d-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="f1a9d-114">Utilisation de Visual Studio pour déployer et déboguer des applications</span><span class="sxs-lookup"><span data-stu-id="f1a9d-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="f1a9d-115">Installer des applications personnalisées</span><span class="sxs-lookup"><span data-stu-id="f1a9d-115">Install custom apps</span></span>

<span data-ttu-id="f1a9d-116">Vous pouvez installer vos propres applications sur HoloLens soit à l’aide du portail de l’appareil, soit en déployant les applications à partir de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="f1a9d-117">Installation d’un package d’application avec le portail de l’appareil</span><span class="sxs-lookup"><span data-stu-id="f1a9d-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="f1a9d-118">Établissez une connexion entre le portail de l' [appareil](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) et le HoloLens cible.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="f1a9d-119">Dans le volet de navigation de gauche, accédez à la page **applications** .</span><span class="sxs-lookup"><span data-stu-id="f1a9d-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="f1a9d-120">Sous **package d’application** , accédez au fichier. AppX associé à votre application.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f1a9d-121">Veillez à référencer les fichiers de dépendance et de certificat associés.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="f1a9d-122">Sélectionnez **Go**.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1a9d-123">![Installer le formulaire d’application dans le portail de périphériques Windows sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="f1a9d-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="f1a9d-124">Déploiement à partir de Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="f1a9d-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="f1a9d-125">Ouvrez la solution Visual Studio de votre application (fichier. sln).</span><span class="sxs-lookup"><span data-stu-id="f1a9d-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="f1a9d-126">Ouvrez les **Propriétés** du projet.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="f1a9d-127">Sélectionnez la configuration de build suivante : **maître/x86/ordinateur distant**.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="f1a9d-128">Lorsque vous sélectionnez **ordinateur distant**:</span><span class="sxs-lookup"><span data-stu-id="f1a9d-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="f1a9d-129">Assurez-vous que l’adresse pointe vers l’adresse IP Wi-Fi de votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="f1a9d-130">Définissez authentification sur **universel (protocole non chiffré)**.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="f1a9d-131">Générez votre solution.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-131">Build your solution.</span></span>

1. <span data-ttu-id="f1a9d-132">Pour déployer l’application à partir de votre PC de développement vers votre HoloLens, sélectionnez **machine distante**.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="f1a9d-133">Si vous avez déjà une build existante sur HoloLens, sélectionnez **Oui** pour installer cette version plus récente.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Déploiement d’ordinateurs distants pour des applications dans Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="f1a9d-135">L’application s’installe et se lance automatiquement sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="f1a9d-136">Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrer**  >  **toutes les applications**).</span><span class="sxs-lookup"><span data-stu-id="f1a9d-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
