---
title: Contrôle de l’Application Windows Defender
description: Vue d’ensemble sur le mode WDAC et sur l’utilisation de la gestion des appareils HoloLens.
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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163120"
---
# <span data-ttu-id="a8dc2-103">Contrôle de l’Application Windows Defender</span><span class="sxs-lookup"><span data-stu-id="a8dc2-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="a8dc2-104">Les applications WDAC permettent à un administrateur informatique de configurer leurs appareils pour bloquer le lancement d’applications sur des appareils.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="a8dc2-105">Cette fonction est différente de celle des méthodes de restriction de l’appareil, telles que le mode plein écran, dans laquelle l’utilisateur dispose d’une interface utilisateur qui masque les applications sur l’appareil, mais qui peut toujours être lancée.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="a8dc2-106">Lorsque WDAC est implémenté, les applications sont toujours visibles dans la liste toutes les applications, mais la WDAC arrête ces applications et processus de pouvoir être lancée par l’utilisateur de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="a8dc2-107">Il est possible qu’un appareil dispose de plusieurs stratégies WDAC.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="a8dc2-108">S’il s’agit de stratégies WDAC multiples définies sur un système, les plus restrictives entrent en vigueur.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8dc2-109">Lorsque les utilisateurs finaux essaient de lancer une application qui est bloquée par WDAC, sur HoloLens, il ne recevra pas de notification indiquant qu’il n’est pas en mesure de lancer cette application.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="a8dc2-110">Vous trouverez ci-dessous un guide permettant aux utilisateurs d’apprendre à [utiliser WDac et Windows PowerShell pour autoriser ou bloquer des applications sur les appareils HoloLens 2 avec Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="a8dc2-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="a8dc2-111">Lorsque les utilisateurs recherchent des applications installées sur leur PC Windows 10 à l’aide du premier exemple de procédure, il est possible que vous deviez apporter quelques tentatives pour affiner les résultats.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-111">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="a8dc2-112">Si vous ne connaissez pas le nom complet du package, il est possible que vous deviez exécuter’Get-AppxPackage-Name \ \* YourBestGuess \ \* 'quelques instants pour le trouver.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="a8dc2-113">Ensuite, une fois que vous avez le nom exécuter «$package 1 = Get-AppxPackage-nom réel. PackageName'</span><span class="sxs-lookup"><span data-stu-id="a8dc2-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="a8dc2-114">Par exemple, l’exécution de la commande suivante pour Edge renverra plusieurs résultats, mais de cette liste, vous pouvez identifier le nom complet dont vous avez besoin pour Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-114">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="a8dc2-115">Noms de famille de packages pour les applications sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="a8dc2-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="a8dc2-116">Dans le guide lié ci-dessus, vous pouvez modifier manuellement newPolicy.xml et ajouter des règles pour les applications qui sont uniquement installées sur HoloLens avec leurs noms de famille de packages.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="a8dc2-117">Il est parfois possible d’utiliser des applications qui ne se trouvent pas sur votre ordinateur de bureau et que vous voulez ajouter à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="a8dc2-118">Voici une liste des applications les plus fréquemment utilisées et In-Box pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="a8dc2-119">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="a8dc2-119">App Name</span></span>                   | <span data-ttu-id="a8dc2-120">Nom de la famille de packages</span><span class="sxs-lookup"><span data-stu-id="a8dc2-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="a8dc2-121">Visionneuse3D</span><span class="sxs-lookup"><span data-stu-id="a8dc2-121">3D Viewer</span></span>                  | <span data-ttu-id="a8dc2-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="a8dc2-123">Installateur de l'application</span><span class="sxs-lookup"><span data-stu-id="a8dc2-123">App Installer</span></span>              | <span data-ttu-id="a8dc2-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="a8dc2-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="a8dc2-125">Calendrier</span><span class="sxs-lookup"><span data-stu-id="a8dc2-125">Calendar</span></span>                   | <span data-ttu-id="a8dc2-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="a8dc2-127">Appareil photo</span><span class="sxs-lookup"><span data-stu-id="a8dc2-127">Camera</span></span>                     | <span data-ttu-id="a8dc2-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="a8dc2-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="a8dc2-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="a8dc2-129">Cortana</span></span>                    | <span data-ttu-id="a8dc2-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="a8dc2-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="a8dc2-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="a8dc2-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="a8dc2-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="a8dc2-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="a8dc2-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="a8dc2-135">Hub de commentaires</span><span class="sxs-lookup"><span data-stu-id="a8dc2-135">Feedback Hub</span></span>               | <span data-ttu-id="a8dc2-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="a8dc2-137">Explorateur de fichiers</span><span class="sxs-lookup"><span data-stu-id="a8dc2-137">File Explorer</span></span>              | <span data-ttu-id="a8dc2-138">c5e2524a-ea46-4F67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="a8dc2-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="a8dc2-139">Mail</span><span class="sxs-lookup"><span data-stu-id="a8dc2-139">Mail</span></span>                       | <span data-ttu-id="a8dc2-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="a8dc2-141">MicrosoftStore</span><span class="sxs-lookup"><span data-stu-id="a8dc2-141">Microsoft Store</span></span>            | <span data-ttu-id="a8dc2-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="a8dc2-143">Films et TV</span><span class="sxs-lookup"><span data-stu-id="a8dc2-143">Movies & TV</span></span>                | <span data-ttu-id="a8dc2-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="a8dc2-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a8dc2-145">OneDrive</span></span>                   | <span data-ttu-id="a8dc2-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="a8dc2-147">Photos</span><span class="sxs-lookup"><span data-stu-id="a8dc2-147">Photos</span></span>                     | <span data-ttu-id="a8dc2-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="a8dc2-149">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a8dc2-149">Settings</span></span>                   | <span data-ttu-id="a8dc2-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="a8dc2-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="a8dc2-151">Conseils</span><span class="sxs-lookup"><span data-stu-id="a8dc2-151">Tips</span></span>                       | <span data-ttu-id="a8dc2-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="a8dc2-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="a8dc2-153">1-le programme d’installation de l’application bloque uniquement l’application du programme d’installation de l’application, et non les applications installées à partir d’autres sources telles que le Microsoft Store ou de votre solution GPM.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="a8dc2-154">Rechercher le nom de la famille de packages</span><span class="sxs-lookup"><span data-stu-id="a8dc2-154">How to find a Package Family Name</span></span>

<span data-ttu-id="a8dc2-155">Si une application ne figure pas dans cette liste, il est possible qu’un utilisateur puisse utiliser Device Portal, connecté à un HoloLens 2 qui a installé l’application souhaitait être bloquée, afin de déterminer le PackageRelativeID et de télécharger propriété packagefamilyname.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-155">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="a8dc2-156">Installez l’application sur votre appareil HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="a8dc2-157">Ouvrez paramètres-> mises à jour & sécurité-> pour les développeurs, puis activez le **mode développeur** , puis **Device Portal**.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="a8dc2-158">Pour plus d’informations, consultez la [rubrique Configurer et utiliser Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="a8dc2-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="a8dc2-159">Une fois que Device Portal est connecté, accédez à **vues** puis **applications**.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="a8dc2-160">Dans le volet applications installées, utilisez la liste déroulante pour sélectionner l’application installée.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-160">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="a8dc2-161">Recherchez l’PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="a8dc2-162">Copiez des caractères d’application avant!, il s’agira de votre propriété packagefamilyname.</span><span class="sxs-lookup"><span data-stu-id="a8dc2-162">Copy app characters before the !, this will be your PackageFamilyName.</span></span>


