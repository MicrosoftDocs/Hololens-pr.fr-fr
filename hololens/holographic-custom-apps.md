---
title: Gérer les applications personnalisées pour HoloLens
description: Applications personnalisées de chargement latéral sur HoloLens. En savoir plus sur l’installation et la désinstallation des applications holographiques.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, charger, charge latérale, Windows Store, Windows Store, UWP, application, installer
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218631"
---
# <span data-ttu-id="52be1-105">Gérer les applications personnalisées pour HoloLens</span><span class="sxs-lookup"><span data-stu-id="52be1-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="52be1-106">HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que les nouvelles applications spécifiquement conçues pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="52be1-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="52be1-107">Cet article porte sur les applications holographiques personnalisées.</span><span class="sxs-lookup"><span data-stu-id="52be1-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="52be1-108">Pour plus d’informations sur les applications du Windows Store, voir [gérer les applications avec le Windows Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="52be1-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52be1-109">Les informations suivantes ont été créées pour le HoloLens (1er génération), également appelé HoloLens (édition de développement HoloLens).</span><span class="sxs-lookup"><span data-stu-id="52be1-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="52be1-110">Comme ces applications chargement indépendant via Device Portal et l’installation d’applications par Visual Studio étaient banales.</span><span class="sxs-lookup"><span data-stu-id="52be1-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="52be1-111">Pour les déploiements d’entreprise, nous vous recommandons de ne pas activer le mode développeur, qui est utilisé par les deux méthodes.</span><span class="sxs-lookup"><span data-stu-id="52be1-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="52be1-112">Si vous êtes intéressé par la méthode de déploiement d’applications sécurisées, consultez notre [rubrique gestion des applications: vue d’ensemble](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="52be1-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="52be1-113">Si vous recherchez une méthode de développement pour l’installation des applications pour les appareils HoloLens 2, reportez-vous aux rubriques suivantes:</span><span class="sxs-lookup"><span data-stu-id="52be1-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="52be1-114">Device Portal: installation d’une application</span><span class="sxs-lookup"><span data-stu-id="52be1-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="52be1-115">Utilisation de Visual Studio pour déployer et déboguer des applications</span><span class="sxs-lookup"><span data-stu-id="52be1-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="52be1-116">Installer des applications personnalisées</span><span class="sxs-lookup"><span data-stu-id="52be1-116">Install custom apps</span></span>

<span data-ttu-id="52be1-117">Vous pouvez installer vos propres applications sur HoloLens en utilisant Device Portal ou en déployant les applications à partir de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52be1-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="52be1-118">Installation d’un package d’application avec Device Portal</span><span class="sxs-lookup"><span data-stu-id="52be1-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="52be1-119">Etablissez une connexion à partir de [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) vers le HoloLens cible.</span><span class="sxs-lookup"><span data-stu-id="52be1-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="52be1-120">Dans le volet de navigation gauche, accédez à la page **applications** .</span><span class="sxs-lookup"><span data-stu-id="52be1-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="52be1-121">Sous le package de l' **application** , recherchez le fichier. AppX associé à votre application.</span><span class="sxs-lookup"><span data-stu-id="52be1-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="52be1-122">Veillez à référencer tout fichier de dépendance et de certificat associé.</span><span class="sxs-lookup"><span data-stu-id="52be1-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="52be1-123">Sélectionnez **Go (atteindre**).</span><span class="sxs-lookup"><span data-stu-id="52be1-123">Select **Go**.</span></span>
   ![Installer le formulaire d’application dans Windows Device Portal sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="52be1-125">Déploiement à partir de Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="52be1-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="52be1-126">Ouvrez la solution Visual Studio de votre application (fichier. sln).</span><span class="sxs-lookup"><span data-stu-id="52be1-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="52be1-127">Ouvrez les **Propriétés**du projet.</span><span class="sxs-lookup"><span data-stu-id="52be1-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="52be1-128">Sélectionnez la configuration de build suivante: **maître/x86/ordinateur distant**.</span><span class="sxs-lookup"><span data-stu-id="52be1-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="52be1-129">Lorsque vous sélectionnez **ordinateur distant**:</span><span class="sxs-lookup"><span data-stu-id="52be1-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="52be1-130">Assurez-vous que l’adresse pointe vers l’adresse IP Wi-Fi de votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="52be1-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="52be1-131">Définissez l’authentification sur le **protocole universel (protocole non chiffré)**.</span><span class="sxs-lookup"><span data-stu-id="52be1-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="52be1-132">Créez votre solution.</span><span class="sxs-lookup"><span data-stu-id="52be1-132">Build your solution.</span></span>
1. <span data-ttu-id="52be1-133">Pour déployer l’application à partir de votre ordinateur de développement vers votre HoloLens, sélectionnez **ordinateur distant**.</span><span class="sxs-lookup"><span data-stu-id="52be1-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="52be1-134">Si vous avez déjà une build sur le HoloLens, sélectionnez **Oui** pour installer cette nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="52be1-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Déploiement d’ordinateurs distants pour les applications dans Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="52be1-136">L’application s’installe et démarre automatiquement sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="52be1-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="52be1-137">Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrez**  >  **toutes les applications**).</span><span class="sxs-lookup"><span data-stu-id="52be1-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
