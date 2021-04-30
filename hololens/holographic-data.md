---
title: Rechercher et enregistrer des fichiers sur HoloLens
description: Découvrez comment utiliser l’Explorateur de fichiers sur HoloLens pour ouvrir, afficher et gérer des fichiers sur votre appareil de réalité mixte.
keywords: procédure, sélecteur de fichiers, fichiers, photos, vidéos, images, OneDrive, stockage, Explorateur de fichiers, hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308597"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="06d2d-104">Rechercher, ouvrir et enregistrer des fichiers sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="06d2d-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="06d2d-105">Les fichiers que vous créez sur HoloLens, y compris les photos et les vidéos, sont enregistrés directement sur votre appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="06d2d-106">Affichez et gérez-les de la même façon que vous gérez les fichiers sur Windows 10 :</span><span class="sxs-lookup"><span data-stu-id="06d2d-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="06d2d-107">Utilisation de l’application de l’Explorateur de fichiers pour accéder aux dossiers locaux.</span><span class="sxs-lookup"><span data-stu-id="06d2d-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="06d2d-108">Dans le stockage d’une application.</span><span class="sxs-lookup"><span data-stu-id="06d2d-108">Within an app's storage.</span></span>
- <span data-ttu-id="06d2d-109">Dans un dossier spécial (tel que la bibliothèque vidéo ou musicale).</span><span class="sxs-lookup"><span data-stu-id="06d2d-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="06d2d-110">Utilisation d’un service de stockage qui comprend un sélecteur d’application et de fichier (par exemple, OneDrive).</span><span class="sxs-lookup"><span data-stu-id="06d2d-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="06d2d-111">À l’aide d’un ordinateur de bureau connecté à votre HoloLens à l’aide d’un câble USB, en prenant en charge MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="06d2d-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="06d2d-112">Afficher les fichiers sur HoloLens à l’aide de l’Explorateur de fichiers</span><span class="sxs-lookup"><span data-stu-id="06d2d-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="06d2d-113">S’applique à tous les appareils HoloLens 2 et à HoloLens (1re génération) à partir de la [mise à jour 2018 d’avril de Windows 10 (RS4) pour HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="06d2d-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="06d2d-114">Utilisez l’Explorateur de fichiers sur HoloLens pour afficher et gérer les fichiers sur votre appareil, y compris les objets 3D, les documents et les images.</span><span class="sxs-lookup"><span data-stu-id="06d2d-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="06d2d-115">Accédez à **Démarrer** l'   >  Explorateur de fichiers de **tous les applications**   >   pour commencer.</span><span class="sxs-lookup"><span data-stu-id="06d2d-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="06d2d-116">Si aucun fichier n’est répertorié dans l’Explorateur de fichiers, sélectionnez **ce périphérique** dans le volet supérieur gauche.</span><span class="sxs-lookup"><span data-stu-id="06d2d-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="06d2d-117">Si vous ne voyez aucun fichier dans l’Explorateur de fichiers, le filtre « récent » peut être actif (l’icône d’horloge est mise en surbrillance dans le volet gauche).</span><span class="sxs-lookup"><span data-stu-id="06d2d-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="06d2d-118">Pour résoudre ce problème, sélectionnez l’icône de document de **ce périphérique** dans le volet gauche (sous l’icône d’horloge) ou ouvrez le menu et sélectionnez **cet appareil**.</span><span class="sxs-lookup"><span data-stu-id="06d2d-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="06d2d-119">Rechercher et afficher vos photos et vidéos</span><span class="sxs-lookup"><span data-stu-id="06d2d-119">Find and view your photos and videos</span></span>

<span data-ttu-id="06d2d-120">La [capture de réalité mixte](holographic-photos-and-videos.md) vous permet de prendre des photos et des vidéos de réalité mixte sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="06d2d-121">Ces photos et vidéos sont enregistrées dans le dossier pellicule de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="06d2d-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="06d2d-122">Vous pouvez accéder aux photos et vidéos prises avec HoloLens en :</span><span class="sxs-lookup"><span data-stu-id="06d2d-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="06d2d-123">accès à l’appareil photo directement par le biais de l' [application photos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="06d2d-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="06d2d-124">Téléchargement de photos et de vidéos dans le stockage cloud en synchronisant vos photos et vidéos sur OneDrive.</span><span class="sxs-lookup"><span data-stu-id="06d2d-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="06d2d-125">à l’aide de la page de capture de la réalité mixte du [portail de périphériques Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="06d2d-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="06d2d-126">Application Photos</span><span class="sxs-lookup"><span data-stu-id="06d2d-126">Photos app</span></span>

<span data-ttu-id="06d2d-127">L’application photos est l’une des applications par défaut dans le menu **Démarrer** et est intégrée avec HoloLens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="06d2d-128">En savoir plus sur [l’utilisation de l’application photos pour afficher le contenu](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="06d2d-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="06d2d-129">Vous pouvez également installer l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir de la Microsoft Store pour synchroniser des photos avec d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="06d2d-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="06d2d-130">Application OneDrive</span><span class="sxs-lookup"><span data-stu-id="06d2d-130">OneDrive app</span></span>

<span data-ttu-id="06d2d-131">[OneDrive](https://onedrive.live.com/) vous permet d’accéder, de gérer et de partager vos photos et vidéos avec n’importe quel appareil et avec n’importe quel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="06d2d-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="06d2d-132">Pour accéder aux photos et vidéos capturées sur HoloLens, téléchargez l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir du Microsoft Store sur votre hololens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="06d2d-133">Une fois le téléchargement terminé, ouvrez l’application OneDrive et sélectionnez **paramètres**  >  **appareil photo Télécharger**, puis activez l’option chargement de l' **appareil photo**.</span><span class="sxs-lookup"><span data-stu-id="06d2d-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="06d2d-134">Se connecter à un PC</span><span class="sxs-lookup"><span data-stu-id="06d2d-134">Connect to a PC</span></span>

<span data-ttu-id="06d2d-135">Si votre HoloLens exécute la [mise à jour 2018 de Windows 10 avril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou une version ultérieure, vous pouvez connecter votre hololens à un PC Windows 10 à l’aide d’un câble USB pour parcourir les photos et les vidéos sur l’appareil à l’aide du protocole MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="06d2d-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="06d2d-136">Vous devrez vous assurer que l’appareil est déverrouillé pour parcourir les fichiers si vous avez configuré un code confidentiel ou un mot de passe sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="06d2d-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="06d2d-137">Si vous avez activé le [portail de périphériques Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), vous pouvez l’utiliser pour parcourir, récupérer et gérer les photos et vidéos stockées sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="06d2d-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="06d2d-138">Accéder aux fichiers dans une application</span><span class="sxs-lookup"><span data-stu-id="06d2d-138">Access files within an app</span></span>

<span data-ttu-id="06d2d-139">Si une application enregistre des fichiers sur votre appareil, vous pouvez utiliser cette application pour y accéder.</span><span class="sxs-lookup"><span data-stu-id="06d2d-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="06d2d-140">Demande de fichiers à partir d’une autre application</span><span class="sxs-lookup"><span data-stu-id="06d2d-140">Requesting files from another app</span></span>

<span data-ttu-id="06d2d-141">Une application peut demander l’enregistrement d’un fichier ou l’ouverture d’un fichier à partir d’une autre application à l’aide de [sélecteurs de fichiers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="06d2d-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="06d2d-142">Dossiers connus</span><span class="sxs-lookup"><span data-stu-id="06d2d-142">Known folders</span></span>

<span data-ttu-id="06d2d-143">HoloLens prend en charge un certain nombre de [dossiers connus](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) auxquels les applications peuvent demander une autorisation d’accès.</span><span class="sxs-lookup"><span data-stu-id="06d2d-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="06d2d-144">Afficher des fichiers HoloLens sur votre PC</span><span class="sxs-lookup"><span data-stu-id="06d2d-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="06d2d-145">À l’instar des autres appareils mobiles, connectez HoloLens à votre ordinateur de bureau à l’aide du protocole MTP (Media Transfer Protocol) et ouvrez l’Explorateur de fichiers sur le PC pour accéder à vos bibliothèques HoloLens en vue de faciliter le transfert.</span><span class="sxs-lookup"><span data-stu-id="06d2d-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="06d2d-146">Pour afficher vos fichiers HoloLens dans l’Explorateur de fichiers sur votre ordinateur :</span><span class="sxs-lookup"><span data-stu-id="06d2d-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="06d2d-147">Connectez-vous à HoloLens, puis branchez-le sur le PC à l’aide du câble USB fourni avec le HoloLens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="06d2d-148">Sélectionnez **ouvrir l’appareil pour afficher les fichiers avec l’Explorateur de fichiers** ou ouvrez l’Explorateur de fichiers sur le PC et accédez à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="06d2d-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="06d2d-149">Pour afficher des informations sur votre HoloLens, cliquez avec le bouton droit sur le nom de l’appareil dans l’Explorateur de fichiers sur votre ordinateur, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="06d2d-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="06d2d-150">HoloLens (1re génération) ne prend pas en charge la connexion à des disques durs externes ou à des cartes SD.</span><span class="sxs-lookup"><span data-stu-id="06d2d-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="06d2d-151">Synchroniser avec le Cloud</span><span class="sxs-lookup"><span data-stu-id="06d2d-151">Sync to the cloud</span></span>

<span data-ttu-id="06d2d-152">Pour synchroniser des photos et d’autres fichiers entre votre HoloLens et le Cloud, installez et configurez OneDrive sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="06d2d-153">Pour obtenir OneDrive, recherchez-le dans le Microsoft Store sur votre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="06d2d-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="06d2d-154">HoloLens ne sauvegarde pas les fichiers et les données de l’application. il est donc judicieux d’enregistrer vos éléments importants sur OneDrive.</span><span class="sxs-lookup"><span data-stu-id="06d2d-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="06d2d-155">De cette façon, si vous réinitialisez votre appareil ou que vous désinstallez une application, vos informations seront sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="06d2d-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
