---
title: Comment charger et installer des applications via le programme d’installation de l’application HoloLens 2
description: Télécharger et installer des applications par le biais de l’interface utilisateur
keywords: gestion des applications, application, hololens, programme d’installation de l’application
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027466"
---
# <span data-ttu-id="5d2c5-104">Installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="5d2c5-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="5d2c5-105">Les utilisateurs peuvent désormais installer des applications à l’aide de forfaits AppX dès maintenant sans avoir besoin d’activer le mode développeur ou d’utiliser Device Portal.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="5d2c5-106">Cette expérience est simple lors de l’installation d’applications sur des appareils locaux ou du partage d’une application avec une autre personne qui ne connaît pas les autres méthodes d’installation d’application sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5d2c5-107">Pour le moment, cette fonctionnalité est uniquement avalible dans les builds Insider 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="5d2c5-108">En [savoir plus sur l’inscription aux builds Insider pour Windows](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="5d2c5-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5d2c5-109">La configuration de la solution de votre application doit être **maître** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="5d2c5-110">En savoir plus sur la [création de packages d’application](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="5d2c5-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="5d2c5-111">Vérifiez que votre appareil HoloLens 2 est allumé et que vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="5d2c5-112">Sur votre PC, accédez à votre application personnalisée, puis copiez le fichier VotreApplication. appxbundle sur yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="5d2c5-113">À la fin de la copie de votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation plus tard.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="5d2c5-114">Sur votre appareil HoloLens 2, ouvrez le **menu Démarrer**, sélectionnez **toutes les applications** , puis lancez l’application **Explorateur de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="5d2c5-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="5d2c5-115">Accédez au dossier téléchargements.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="5d2c5-116">Vous pouvez être amené à vous rendre dans le volet gauche de l’application sélectionnez **ce dernier** d’abord, puis accéder à téléchargements.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="5d2c5-117">Sélectionnez le fichier VotreApplication. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="5d2c5-118">Le programme d’installation de l’application démarre.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-118">The App Installer will launch.</span></span> <span data-ttu-id="5d2c5-119">Sélectionnez le bouton **installer** pour installer votre application.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="5d2c5-120">L’application installée s’ouvre automatiquement lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![Installation des exemples MRTK via le programme d’installation de l’application](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="5d2c5-122">Si votre application n’a pas réussi à procéder à l’installation, vérifiez les points suivants:</span><span class="sxs-lookup"><span data-stu-id="5d2c5-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="5d2c5-123">Votre application est une build de type maître ou version Release.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="5d2c5-124">Vous êtes [connecté à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="5d2c5-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="5d2c5-125">Vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="5d2c5-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
