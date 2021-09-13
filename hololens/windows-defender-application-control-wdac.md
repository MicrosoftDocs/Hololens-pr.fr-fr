---
title: Contrôle d’application Windows Defender (WDAC)
description: vue d’ensemble de ce que Windows Defender le contrôle d’Application et comment l’utiliser pour gérer des appareils de réalité mixte HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032925"
---
# <a name="windows-defender-application-control---wdac"></a>Contrôle d’application Windows Defender - WDAC

## <a name="overview"></a>Vue d’ensemble

WDAC vous permet de configurer HoloLens pour bloquer le lancement d’applications. Il est différent du mode plein écran, où l’interface utilisateur masque les applications, mais elles peuvent toujours être lancées. Avec WDAC, vous pouvez voir les applications, mais elles ne peuvent pas être lancées.

> [!NOTE]
> lorsque les utilisateurs finaux tentent de lancer une application qui est bloquée par WDAC sur HoloLens, ils ne sont pas avertis de l’impossibilité de lancer l’application.

Plusieurs stratégies WDAC peuvent être attribuées à un appareil. Si plusieurs stratégies WDAC sont définies sur un système, les plus restrictives prennent effet. 

voici un guide permettant aux utilisateurs d’apprendre à [utiliser WDAC et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils HoloLens 2 avec Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

lorsque les utilisateurs recherchent des applications installées sur leur ordinateur Windows 10 à l’aide du premier exemple, ils peuvent avoir besoin d’effectuer quelques tentatives pour limiter les résultats.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si vous ne connaissez pas le nom complet du package, vous devrez peut-être exécuter plusieurs fois’AppxPackage-name \* YourBestGuess \* 'pour le trouver. Ensuite, une fois que vous avez le nom « $package 1 = Get-AppxPackage-Name actual. PackageName »

par exemple, l’exécution du code suivant pour Microsoft Edge renverra plusieurs résultats, mais à partir de cette liste, vous pouvez identifier que le nom complet dont vous avez besoin est Microsoft. MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Noms des familles de packages pour les applications sur HoloLens

dans le guide lié ci-dessus, vous pouvez modifier manuellement newPolicy.xml et ajouter des règles pour les applications qui sont installées uniquement sur HoloLens avec leurs noms de famille de packages. Parfois, il existe des applications que vous pouvez utiliser et qui ne se trouvent pas sur votre PC de bureau que vous souhaitez ajouter à la stratégie.

voici une liste d’applications couramment utilisées et In-Box pour les appareils HoloLens 2.

| Nom de l’application                   | Nom de famille du package                                |
|----------------------------|----------------------------------------------------|
| Visionneuse 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Programme d’installation d’application              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendrier                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Appareil photo                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub de commentaires               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorateur de fichiers              | c5e2524a-ea46-4F67-841f-6a9465d9d515_cw5n1h2txyewy |
| Messagerie                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Films et TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Photo                     | Librairie. Windows. Photos_8wekyb3d8bbwe             |
| Paramètres                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Conseils                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-bloquer le programme d’installation de l’application bloquera uniquement l’application du programme d’installation de l’application, et non les applications installées à partir d’autres sources telles que le Microsoft Store ou de votre solution MDM.

### <a name="how-to-find-a-package-family-name"></a>Comment rechercher un nom de famille de packages

si une application ne figure pas dans cette liste, cela signifie qu’un utilisateur peut utiliser le portail de l’appareil, connecté à un HoloLens 2 sur lequel l’application a été installée pour être bloquée, afin de déterminer le PackageRelativeID et d’obtenir le PackageFamilyName.

1. installez l’application sur votre appareil HoloLens 2. 
1. ouvrez Paramètres > mises à jour & Security-> pour les développeurs et activez le **mode développeur** , puis le portail de l' **appareil**. 
    1. Pour plus d’informations, consultez la [page Configuration et utilisation du portail de l’appareil ici](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Une fois que le portail de l’appareil est connecté, accédez à **vues** , puis **applications**. 
1. Dans le panneau applications installées, utilisez la liste déroulante pour sélectionner l’application installée. 
1. Recherchez PackageRelativeID. 
1. Copier les caractères de l’application avant le `!` , ces caractères sont PackageFamilyName.

