---
title: Contrôle d’application Windows Defender-WDAC
description: Vue d’ensemble du contrôle d’application Windows Defender et de son utilisation pour gérer les appareils de réalité mixte HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308728"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="6622a-103">Contrôle d’application Windows Defender-WDAC</span><span class="sxs-lookup"><span data-stu-id="6622a-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="6622a-104">WDAC permet à un administrateur informatique de configurer ses appareils pour bloquer le lancement d’applications sur les appareils.</span><span class="sxs-lookup"><span data-stu-id="6622a-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="6622a-105">Cela diffère des méthodes de restriction de l’appareil, telles que le mode plein écran, où l’utilisateur voit une interface utilisateur qui masque les applications sur l’appareil, mais qui peut toujours être lancée.</span><span class="sxs-lookup"><span data-stu-id="6622a-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="6622a-106">Si WDAC est implémenté, les applications sont toujours visibles dans la liste toutes les applications, mais WDAC arrête l’exécution de ces applications et processus par l’utilisateur de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6622a-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="6622a-107">Plusieurs stratégies WDAC peuvent être attribuées à un appareil.</span><span class="sxs-lookup"><span data-stu-id="6622a-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="6622a-108">Si plusieurs stratégies WDAC sont définies sur un système, les plus restrictives prennent effet.</span><span class="sxs-lookup"><span data-stu-id="6622a-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="6622a-109">Lorsque les utilisateurs finaux tentent de lancer une application qui est bloquée par WDAC, sur HoloLens, ils ne reçoivent pas de notification sur l’impossibilité de lancer cette application.</span><span class="sxs-lookup"><span data-stu-id="6622a-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="6622a-110">Voici un guide permettant aux utilisateurs d’apprendre à [utiliser WDac et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils HoloLens 2 avec Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="6622a-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="6622a-111">Lorsque les utilisateurs recherchent des applications installées sur leur PC Windows 10 à l’aide du premier exemple, ils peuvent avoir besoin d’effectuer quelques tentatives pour limiter les résultats.</span><span class="sxs-lookup"><span data-stu-id="6622a-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="6622a-112">Si vous ne connaissez pas le nom complet du package, vous devrez peut-être exécuter plusieurs fois’AppxPackage-name \* YourBestGuess \* 'pour le trouver.</span><span class="sxs-lookup"><span data-stu-id="6622a-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="6622a-113">Ensuite, une fois que vous avez le nom « $package 1 = Get-AppxPackage-Name actual. PackageName »</span><span class="sxs-lookup"><span data-stu-id="6622a-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="6622a-114">Par exemple, l’exécution de la commande suivante pour Microsoft Edge renverra plusieurs résultats, mais à partir de cette liste, vous pouvez identifier que le nom complet dont vous avez besoin est Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="6622a-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="6622a-115">Noms des familles de packages pour les applications sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="6622a-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="6622a-116">Dans le guide lié ci-dessus, vous pouvez modifier manuellement newPolicy.xml et ajouter des règles pour les applications qui sont installées uniquement sur HoloLens avec leurs noms de famille de packages.</span><span class="sxs-lookup"><span data-stu-id="6622a-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="6622a-117">Parfois, il existe des applications que vous pouvez utiliser et qui ne se trouvent pas sur votre PC de bureau que vous souhaitez ajouter à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="6622a-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="6622a-118">Voici une liste des applications couramment utilisées et In-Box pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6622a-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="6622a-119">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="6622a-119">App Name</span></span>                   | <span data-ttu-id="6622a-120">Nom de famille du package</span><span class="sxs-lookup"><span data-stu-id="6622a-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="6622a-121">Visionneuse 3D</span><span class="sxs-lookup"><span data-stu-id="6622a-121">3D Viewer</span></span>                  | <span data-ttu-id="6622a-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="6622a-123">Programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="6622a-123">App Installer</span></span>              | <span data-ttu-id="6622a-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6622a-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="6622a-125">Calendrier</span><span class="sxs-lookup"><span data-stu-id="6622a-125">Calendar</span></span>                   | <span data-ttu-id="6622a-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="6622a-127">Appareil photo</span><span class="sxs-lookup"><span data-stu-id="6622a-127">Camera</span></span>                     | <span data-ttu-id="6622a-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="6622a-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="6622a-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="6622a-129">Cortana</span></span>                    | <span data-ttu-id="6622a-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="6622a-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="6622a-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="6622a-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="6622a-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="6622a-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="6622a-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="6622a-135">Hub de commentaires</span><span class="sxs-lookup"><span data-stu-id="6622a-135">Feedback Hub</span></span>               | <span data-ttu-id="6622a-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="6622a-137">Explorateur de fichiers</span><span class="sxs-lookup"><span data-stu-id="6622a-137">File Explorer</span></span>              | <span data-ttu-id="6622a-138">c5e2524a-ea46-4F67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="6622a-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="6622a-139">Messagerie</span><span class="sxs-lookup"><span data-stu-id="6622a-139">Mail</span></span>                       | <span data-ttu-id="6622a-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="6622a-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6622a-141">Microsoft Store</span></span>            | <span data-ttu-id="6622a-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="6622a-143">Films et TV</span><span class="sxs-lookup"><span data-stu-id="6622a-143">Movies & TV</span></span>                | <span data-ttu-id="6622a-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="6622a-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6622a-145">OneDrive</span></span>                   | <span data-ttu-id="6622a-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="6622a-147">Photo</span><span class="sxs-lookup"><span data-stu-id="6622a-147">Photos</span></span>                     | <span data-ttu-id="6622a-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="6622a-149">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6622a-149">Settings</span></span>                   | <span data-ttu-id="6622a-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="6622a-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="6622a-151">Conseils</span><span class="sxs-lookup"><span data-stu-id="6622a-151">Tips</span></span>                       | <span data-ttu-id="6622a-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6622a-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="6622a-153">1-bloquer le programme d’installation de l’application bloquera uniquement l’application du programme d’installation de l’application, et non les applications installées à partir d’autres sources telles que le Microsoft Store ou de votre solution MDM.</span><span class="sxs-lookup"><span data-stu-id="6622a-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="6622a-154">Comment rechercher un nom de famille de packages</span><span class="sxs-lookup"><span data-stu-id="6622a-154">How to find a Package Family Name</span></span>

<span data-ttu-id="6622a-155">Si une application ne figure pas dans cette liste, cela signifie qu’un utilisateur peut utiliser le portail de l’appareil, connecté à un HoloLens 2 sur lequel l’application a été installée, pour déterminer le PackageRelativeID et, à partir de là, obtenir le PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="6622a-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="6622a-156">Installez l’application sur votre appareil HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6622a-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="6622a-157">Ouvrez paramètres-> mises à jour & Security-> pour les développeurs, puis activez le **mode développeur** , puis le portail de l' **appareil**.</span><span class="sxs-lookup"><span data-stu-id="6622a-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="6622a-158">Pour plus d’informations, consultez la [page Configuration et utilisation du portail de l’appareil ici](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="6622a-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="6622a-159">Une fois que le portail de l’appareil est connecté, accédez à **vues** , puis **applications**.</span><span class="sxs-lookup"><span data-stu-id="6622a-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="6622a-160">Dans le panneau applications installées, utilisez la liste déroulante pour sélectionner l’application installée.</span><span class="sxs-lookup"><span data-stu-id="6622a-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="6622a-161">Recherchez PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="6622a-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="6622a-162">Copier les caractères de l’application avant le !, ces caractères sont PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="6622a-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


