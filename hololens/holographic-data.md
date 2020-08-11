---
title: Rechercher et enregistrer des fichiers sur HoloLens
description: Utiliser l’Explorateur de fichiers sur HoloLens pour afficher et gérer des fichiers sur votre appareil
keywords: procédures, sélecteur de fichiers, fichiers, photos, vidéos, images, OneDrive, stockage, Explorateur de fichiers, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fb3287f0a074eddeac0c7ee2871e289b93eafcac
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919121"
---
# <span data-ttu-id="4f0e7-104">Rechercher, ouvrir et enregistrer des fichiers sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="4f0e7-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="4f0e7-105">Les fichiers que vous créez sur HoloLens, y compris les photos et vidéos, sont enregistrés directement sur votre appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="4f0e7-106">Vous pouvez les afficher et les gérer de la même manière que pour gérer les fichiers sur Windows 10:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="4f0e7-107">Utilisation de l’application Explorateur de fichiers pour accéder aux dossiers locaux.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="4f0e7-108">Dans le stockage d’une application.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-108">Within an app's storage.</span></span>
- <span data-ttu-id="4f0e7-109">Dans un dossier spécial (par exemple, la bibliothèque de vidéos ou de musique).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="4f0e7-110">À l’aide d’un service de stockage incluant une application et un sélecteur de fichiers (par exemple, OneDrive).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="4f0e7-111">À l’aide d’un PC de bureau connecté à votre HoloLens à l’aide d’un câble USB, avec une prise en charge de MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="4f0e7-112">Afficher des fichiers sur HoloLens à l’aide de l’Explorateur de fichiers</span><span class="sxs-lookup"><span data-stu-id="4f0e7-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="4f0e7-113">S’applique à tous les appareils HoloLens 2 et HoloLens (1er génération) en vertu de la [mise à jour 2018 de Windows 10 d’avril (RS4) pour HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="4f0e7-114">Utilisez l’Explorateur de fichiers sur HoloLens pour afficher et gérer des fichiers sur votre appareil, dont des objets, des documents et des images 3D.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="4f0e7-115">Accédez à **l'**   >  Explorateur de fichiers de**tous les applications**   >  **File Explorer** pour commencer.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="4f0e7-116">Si aucun fichier n’est répertorié dans l’Explorateur de fichiers, sélectionnez **ce périphérique** dans le volet supérieur gauche.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="4f0e7-117">Si aucun fichier n’apparaît dans l’Explorateur de fichiers, il est possible que le filtre «récent» soit actif (l’icône d’horloge soit mise en évidence dans le volet de gauche).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="4f0e7-118">Pour résoudre ce problème, sélectionnez l’icône de document de **ce périphérique** dans le volet gauche, sous l’icône d’horloge, ou ouvrez le menu et sélectionnez **cet appareil**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="4f0e7-119">Rechercher et afficher vos photos et vidéos</span><span class="sxs-lookup"><span data-stu-id="4f0e7-119">Find and view your photos and videos</span></span>

<span data-ttu-id="4f0e7-120">Le mode de capture de la [réalité combinée](holographic-photos-and-videos.md) vous permet de prendre des photos et vidéos de réalité mélangées sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="4f0e7-121">Ces photos et vidéos sont enregistrées dans le dossier pellicule de votre appareil.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="4f0e7-122">Vous pouvez accéder aux photos et vidéos prises avec HoloLens par:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="4f0e7-123">accès à la pellicule directement par le biais de l' [application photos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="4f0e7-124">Téléchargez des photos et des vidéos dans le stockage cloud en synchronisant vos photos et vidéos sur OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="4f0e7-125">à l’aide de la page de capture de la réalité mixte de [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="4f0e7-126">Application Photos</span><span class="sxs-lookup"><span data-stu-id="4f0e7-126">Photos app</span></span>

<span data-ttu-id="4f0e7-127">L’application photos est l’une des applications par défaut du menu **Démarrer** et est intégrée avec HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="4f0e7-128">En savoir plus sur [l’utilisation de l’application photos pour afficher du contenu](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="4f0e7-129">Vous pouvez également installer l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir de la boutique Microsoft pour synchroniser des photos avec d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="4f0e7-130">Application OneDrive</span><span class="sxs-lookup"><span data-stu-id="4f0e7-130">OneDrive app</span></span>

<span data-ttu-id="4f0e7-131">[OneDrive](https://onedrive.live.com/) vous permet d’accéder à vos photos et vidéos et de les partager avec n’importe quel appareil et avec n’importe quel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="4f0e7-132">Pour accéder aux photos et vidéos capturées sur HoloLens, téléchargez l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir de la boutique Microsoft sur votre hololens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="4f0e7-133">Une fois le téléchargement terminé, ouvrez l’application OneDrive, sélectionnez **paramètres**de chargement de l'  >  **appareil photo**, puis activez l’option chargement de l' **appareil photo**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="4f0e7-134">Se connecter à un PC</span><span class="sxs-lookup"><span data-stu-id="4f0e7-134">Connect to a PC</span></span>

<span data-ttu-id="4f0e7-135">Si votre HoloLens exécute la [mise à jour 2018 de Windows 10 d’avril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou version ultérieure, vous pouvez connecter votre hololens à un PC Windows 10 à l’aide d’un câble USB pour parcourir les photos et vidéos de l’appareil à l’aide du protocole MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="4f0e7-136">Vous devez vous assurer que l’appareil est déverrouillé pour parcourir les fichiers si un code confidentiel ou un mot de passe est configuré sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="4f0e7-137">Si vous avez activé [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), vous pouvez l’utiliser pour rechercher, récupérer et gérer les photos et vidéos stockées sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="4f0e7-138">Accéder à des fichiers dans une application</span><span class="sxs-lookup"><span data-stu-id="4f0e7-138">Access files within an app</span></span>

<span data-ttu-id="4f0e7-139">Si une application enregistre des fichiers sur votre appareil, vous pouvez utiliser cette application pour y accéder.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="4f0e7-140">Demande de fichiers à partir d’une autre application</span><span class="sxs-lookup"><span data-stu-id="4f0e7-140">Requesting files from another app</span></span>

<span data-ttu-id="4f0e7-141">Une application peut demander d’enregistrer un fichier ou d’ouvrir un fichier à partir d’une autre application à l’aide de [sélecteurs de fichiers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="4f0e7-142">Dossiers connus</span><span class="sxs-lookup"><span data-stu-id="4f0e7-142">Known folders</span></span>

<span data-ttu-id="4f0e7-143">HoloLens prend en charge un certain nombre de [dossiers connus](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) auxquels les applications peuvent demander des autorisations d’accès.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="4f0e7-144">Afficher des fichiers HoloLens sur votre PC</span><span class="sxs-lookup"><span data-stu-id="4f0e7-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="4f0e7-145">À l’instar des autres appareils mobiles, connectez HoloLens à votre ordinateur de bureau à l’aide du protocole MTP (Media Transfer Protocol), puis ouvrez l’Explorateur de fichiers sur le PC pour accéder à vos bibliothèques HoloLens en vue d’un transfert aisé.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="4f0e7-146">Pour afficher vos fichiers HoloLens dans l’Explorateur de fichiers sur votre PC, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="4f0e7-147">Connectez-vous à HoloLens, puis branchez-le sur le PC à l’aide du câble USB fourni avec le HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="4f0e7-148">Sélectionnez **ouvrir l’appareil pour afficher les fichiers**dans l’Explorateur de fichiers ou ouvrir l’Explorateur de fichiers sur le PC, puis accédez à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="4f0e7-149">Pour afficher des informations sur votre HoloLens, cliquez avec le bouton droit sur le nom de l’appareil dans l’Explorateur de fichiers sur votre PC, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="4f0e7-150">HoloLens (1ère génération) ne prend pas en charge la connexion à des disques durs externes ou des cartes SD.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="4f0e7-151">Synchroniser avec le Cloud</span><span class="sxs-lookup"><span data-stu-id="4f0e7-151">Sync to the cloud</span></span>

<span data-ttu-id="4f0e7-152">Pour synchroniser des photos et d’autres fichiers à partir de votre HoloLens dans le Cloud, installez et configurez OneDrive sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="4f0e7-153">Pour utiliser OneDrive, recherchez-le dans le Microsoft Store sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="4f0e7-154">HoloLens n’enregistre pas les fichiers et les données de l’application, il est donc judicieux d’enregistrer vos éléments importants sur OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="4f0e7-155">Ainsi, si vous réinitialisez votre appareil ou que vous désinstallez une application, vos informations sont sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
