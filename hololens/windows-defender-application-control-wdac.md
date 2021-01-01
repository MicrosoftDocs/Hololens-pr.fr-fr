---
title: Contrôle de l’application Windows Defender (WDAC)
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
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252645"
---
# Contrôle de l’application Windows Defender (WDAC)

Les applications WDAC permettent à un administrateur informatique de configurer leurs appareils pour bloquer le lancement d’applications sur des appareils. Cette fonction est différente de celle des méthodes de restriction de l’appareil, telles que le mode plein écran, dans laquelle l’utilisateur dispose d’une interface utilisateur qui masque les applications sur l’appareil, mais qui peut toujours être lancée. Lorsque WDAC est implémenté, les applications sont toujours visibles dans la liste toutes les applications, mais la WDAC arrête ces applications et processus de pouvoir être lancée par l’utilisateur de l’appareil.

Il est possible qu’un appareil dispose de plusieurs stratégies WDAC. S’il s’agit de stratégies WDAC multiples définies sur un système, les plus restrictives entrent en vigueur. 

> [!NOTE]
> Lorsque les utilisateurs finaux essaient de lancer une application qui est bloquée par WDAC, sur HoloLens, il ne recevra pas de notification indiquant qu’il n’est pas en mesure de lancer cette application.

Vous trouverez ci-dessous un guide permettant aux utilisateurs d’apprendre à [utiliser WDac et Windows PowerShell pour autoriser ou bloquer des applications sur les appareils HoloLens 2 avec Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Lorsque les utilisateurs recherchent des applications installées sur leur PC Windows 10 à l’aide du premier exemple de procédure, il est possible que les utilisateurs aient besoin de faire quelques tentatives pour affiner les résultats.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si vous ne connaissez pas le nom complet du package, il est possible que vous deviez exécuter’Get-AppxPackage-Name \ * YourBestGuess \ * 'quelques instants pour le trouver. Ensuite, une fois que vous avez le nom exécuter «$package 1 = Get-AppxPackage-nom réel. PackageName'

Par exemple, l’exécution de la commande suivante pour Microsoft Edge renverra plusieurs résultats, mais de cette liste, vous pouvez identifier le nom complet dont vous avez besoin pour Microsoft. MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## Noms de famille de packages pour les applications sur HoloLens

Dans le guide lié ci-dessus, vous pouvez modifier manuellement newPolicy.xml et ajouter des règles pour les applications qui sont uniquement installées sur HoloLens avec leurs noms de famille de packages. Il est parfois possible d’utiliser des applications qui ne se trouvent pas sur votre ordinateur de bureau et que vous voulez ajouter à la stratégie.

Voici une liste des applications les plus fréquemment utilisées et In-Box pour les appareils HoloLens 2.

| Nom de l’application                   | Nom de la famille de packages                                |
|----------------------------|----------------------------------------------------|
| Visionneuse3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Installateur d'applications              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendrier                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Appareil photo                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub de commentaires               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorateur de fichiers              | c5e2524a-ea46-4F67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| MicrosoftStore            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Films et TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Photos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Paramètres                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Conseils                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-le programme d’installation de l’application bloque uniquement l’application du programme d’installation de l’application, et non les applications installées à partir d’autres sources telles que le Microsoft Store ou de votre solution GPM.

### Rechercher le nom de la famille de packages

Si une application ne figure pas dans cette liste, il est possible qu’un utilisateur puisse utiliser Device Portal, connecté à un HoloLens 2 qui a installé l’application souhaitait être bloquée, afin de déterminer le PackageRelativeID et de télécharger propriété packagefamilyname.

1. Installez l’application sur votre appareil HoloLens 2. 
1. Ouvrez paramètres-> mises à jour & sécurité-> pour les développeurs, puis activez le **mode développeur** , puis **Device Portal**. 
    1. Pour plus d’informations, consultez la [rubrique Configurer et utiliser Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Une fois que Device Portal est connecté, accédez à **vues** puis **applications**. 
1. Dans le panneau des applications installées, utilisez la liste déroulante pour sélectionner l’application installée. 
1. Recherchez l’PackageRelativeID. 
1. Copiez des caractères d’application antérieurs à!, ces caractères seront votre propriété packagefamilyname.


