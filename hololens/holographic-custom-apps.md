---
title: Gérer les applications personnalisées pour HoloLens (1re génération)
description: Découvrez comment installer, désinstaller et charger des applications holographiques personnalisées sur des appareils HoloLens à l’aide de Device Portal et Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, chargement de version test, chargement de version test, chargement de version test, store, uwp, application, installer
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296987"
---
# <span data-ttu-id="e3660-104">Gérer les applications personnalisées pour HoloLens (1re génération)</span><span class="sxs-lookup"><span data-stu-id="e3660-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="e3660-105">HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que les nouvelles applications spécifiquement conçues pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3660-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="e3660-106">Cet article se concentre sur les applications holographiques personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e3660-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="e3660-107">Pour plus d’informations sur les applications du Store, voir [Gérer les applications avec le Windows Store.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e3660-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3660-108">Les informations suivantes ont été créées pour HoloLens (1ère génération), également appelée HoloLens Developer Edition à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="e3660-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="e3660-109">En tant que tel, le chargement d’applications de version secondaire via Device Portal et l’installation d’applications via Visual Studio ont été très fréquents à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="e3660-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="e3660-110">Pour les déploiements d’entreprise, nous vous déconseillons d’activer le mode développeur, que ces deux méthodes utilisent.</span><span class="sxs-lookup"><span data-stu-id="e3660-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="e3660-111">Si vous êtes intéressé par une méthode de déploiement d’application sécurisée, consultez notre [Gestion des applications : Vue d’ensemble.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e3660-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="e3660-112">Si vous recherchez l’une ou l’autre méthode de développeur d’installation d’application pour les appareils HoloLens 2, reportez-vous à :</span><span class="sxs-lookup"><span data-stu-id="e3660-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="e3660-113">Device Portal : installation d’une application</span><span class="sxs-lookup"><span data-stu-id="e3660-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="e3660-114">Utilisation de Visual Studio pour déployer et déboguer des applications</span><span class="sxs-lookup"><span data-stu-id="e3660-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="e3660-115">Installer des applications personnalisées</span><span class="sxs-lookup"><span data-stu-id="e3660-115">Install custom apps</span></span>

<span data-ttu-id="e3660-116">Vous pouvez installer vos propres applications sur HoloLens à l’aide de Device Portal ou en déployant les applications à partir de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e3660-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="e3660-117">Installation d’un package d’application avec Device Portal</span><span class="sxs-lookup"><span data-stu-id="e3660-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="e3660-118">Établir une connexion à [partir de Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) avec le HoloLens cible.</span><span class="sxs-lookup"><span data-stu-id="e3660-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="e3660-119">Dans le navigation de gauche, accédez à la page **Applications.**</span><span class="sxs-lookup"><span data-stu-id="e3660-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="e3660-120">Sous **Package d’application,** accédez au fichier .appx associé à votre application.</span><span class="sxs-lookup"><span data-stu-id="e3660-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e3660-121">Veillez à référencer les fichiers de dépendance et de certificat associés.</span><span class="sxs-lookup"><span data-stu-id="e3660-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="e3660-122">Sélectionnez **Go**.</span><span class="sxs-lookup"><span data-stu-id="e3660-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Formulaire d’installation de l’application dans Windows Device Portal sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="e3660-124">Déploiement à partir de Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="e3660-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="e3660-125">Ouvrez la solution de Visual Studio de votre application (fichier .sln).</span><span class="sxs-lookup"><span data-stu-id="e3660-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="e3660-126">Ouvrez les propriétés **du projet.**</span><span class="sxs-lookup"><span data-stu-id="e3660-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="e3660-127">Sélectionnez la configuration de build suivante : **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="e3660-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="e3660-128">Lorsque vous sélectionnez **Ordinateur distant**:</span><span class="sxs-lookup"><span data-stu-id="e3660-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="e3660-129">Assurez-vous que l’adresse pointe vers Wi-Fi adresse IP de votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3660-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="e3660-130">Définissez **l’authentification sur Universel (protocole non chiffré).**</span><span class="sxs-lookup"><span data-stu-id="e3660-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="e3660-131">Créez votre solution.</span><span class="sxs-lookup"><span data-stu-id="e3660-131">Build your solution.</span></span>

1. <span data-ttu-id="e3660-132">Pour déployer l’application à partir de votre PC de développement sur votre HoloLens, sélectionnez **Ordinateur distant.**</span><span class="sxs-lookup"><span data-stu-id="e3660-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="e3660-133">Si vous avez déjà une build existante sur HoloLens, sélectionnez **Oui** pour installer cette version plus récente.</span><span class="sxs-lookup"><span data-stu-id="e3660-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Déploiement d’ordinateurs distants pour les applications à Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="e3660-135">L’application s’installe et se lance automatiquement sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3660-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="e3660-136">Une fois que vous avez installé une application, vous la trouverez dans la liste **Toutes** les applications (**Démarrez**  >  **toutes les applications).**</span><span class="sxs-lookup"><span data-stu-id="e3660-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
