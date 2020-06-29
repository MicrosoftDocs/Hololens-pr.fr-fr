---
title: Gérer les applications personnalisées pour HoloLens
description: Applications personnalisées de chargement latéral sur HoloLens. En savoir plus sur l’installation et la désinstallation des applications holographiques.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828163"
---
# <span data-ttu-id="71935-105">Gérer les applications personnalisées pour HoloLens</span><span class="sxs-lookup"><span data-stu-id="71935-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="71935-106">HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que les nouvelles applications spécialement conçues pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="71935-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="71935-107">Cet article porte sur les applications holographiques personnalisées.</span><span class="sxs-lookup"><span data-stu-id="71935-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="71935-108">Pour plus d’informations sur les applications du Windows Store, voir [gérer les applications avec le Windows Store](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="71935-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="71935-109">Installer des applications personnalisées</span><span class="sxs-lookup"><span data-stu-id="71935-109">Install custom apps</span></span>

<span data-ttu-id="71935-110">Vous pouvez installer vos propres applications sur HoloLens en utilisant Device Portal ou en déployant les applications à partir de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="71935-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="71935-111">Installation d’un package d’application avec Device Portal</span><span class="sxs-lookup"><span data-stu-id="71935-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="71935-112">Etablissez une connexion à partir de [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) vers le HoloLens cible.</span><span class="sxs-lookup"><span data-stu-id="71935-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="71935-113">Dans le volet de navigation gauche, accédez à la page **applications** .</span><span class="sxs-lookup"><span data-stu-id="71935-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="71935-114">Sous le package de l' **application** , recherchez le fichier. AppX associé à votre application.</span><span class="sxs-lookup"><span data-stu-id="71935-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="71935-115">Veillez à référencer tout fichier de dépendance et de certificat associé.</span><span class="sxs-lookup"><span data-stu-id="71935-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="71935-116">Sélectionnez **Go (atteindre**).</span><span class="sxs-lookup"><span data-stu-id="71935-116">Select **Go**.</span></span>
   ![Installer le formulaire d’application dans Windows Device Portal sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="71935-118">Déploiement à partir de Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="71935-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="71935-119">Ouvrez la solution Visual Studio de votre application (fichier. sln).</span><span class="sxs-lookup"><span data-stu-id="71935-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="71935-120">Ouvrez les **Propriétés**du projet.</span><span class="sxs-lookup"><span data-stu-id="71935-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="71935-121">Sélectionnez la configuration de build suivante: **maître/x86/ordinateur distant**.</span><span class="sxs-lookup"><span data-stu-id="71935-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="71935-122">Lorsque vous sélectionnez **ordinateur distant**:</span><span class="sxs-lookup"><span data-stu-id="71935-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="71935-123">Assurez-vous que l’adresse pointe sur l’adresse IP Wi-Fi de votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="71935-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="71935-124">Définissez l’authentification sur le **protocole universel (protocole non chiffré)**.</span><span class="sxs-lookup"><span data-stu-id="71935-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="71935-125">Créez votre solution.</span><span class="sxs-lookup"><span data-stu-id="71935-125">Build your solution.</span></span>
1. <span data-ttu-id="71935-126">Pour déployer l’application à partir de votre ordinateur de développement vers votre HoloLens, sélectionnez **ordinateur distant**.</span><span class="sxs-lookup"><span data-stu-id="71935-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="71935-127">Si vous avez déjà une build sur le HoloLens, sélectionnez **Oui** pour installer cette nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="71935-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Déploiement d’ordinateurs distants pour les applications dans Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="71935-129">L’application s’installe et démarre automatiquement sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="71935-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="71935-130">Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrez**  >  **toutes les applications**).</span><span class="sxs-lookup"><span data-stu-id="71935-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
