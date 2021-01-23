---
title: Contrôle de l’application Windows Defender (WDAC)
description: Vue d’ensemble Windows Defender contrôle d’application et comment l’utiliser pour gérer les appareils HoloLens de réalité mixte.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284135"
---
# Contrôle de l’application Windows Defender (WDAC)

WDAC permet à un administrateur informatique de configurer ses appareils pour bloquer le lancement des applications sur les appareils. Ceci est différent des méthodes de restriction d’appareil telles que le mode plein écran, où l’utilisateur se présente avec une interface utilisateur qui masque les applications sur l’appareil, mais qui peuvent toujours être lancées. Lorsque WDAC est implémenté, les applications sont toujours visibles dans la liste Toutes les applications, mais WDAC empêche le lancement de ces applications et processus par l’utilisateur de l’appareil.

Plusieurs stratégies WDAC peuvent être affectées à un appareil. Si plusieurs stratégies WDAC sont définies sur un système, la plupart des stratégies restrictives prennent effet. 

> [!NOTE]
> Lorsque les utilisateurs finaux tentent de lancer une application bloquée par WDAC, sur HoloLens, ils ne reçoivent pas de notification de ne pas pouvoir lancer cette application.

Voici un guide permettant aux utilisateurs d’apprendre à utiliser WDAC et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils [HoloLens 2 avec Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Lorsque les utilisateurs recherchent des applications installées sur leur PC Windows 10 à l’aide de la première étape, ils devront peut-être tenter de réduire les résultats.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si vous ne connaissez pas le nom complet du package, vous devrez peut-être exécuter « Get-AppxPackage -name \*YourBestGuess\* » plusieurs fois pour le trouver. Une fois que vous avez le nom, exécutez « $package 1 = Get-AppxPackage -name Actual.PackageName »

Par exemple, l’exécution de ce qui suit pour Microsoft Edge retourne plusieurs résultats, mais à partir de cette liste, vous pouvez identifier que le nom complet dont vous avez besoin est Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## Noms de famille de packages pour les applications sur HoloLens

Dans le guide lié ci-dessus, vous pouvez modifier manuellement newPolicy.xml et ajouter des règles pour les applications installées uniquement sur HoloLens avec leurs noms de famille de packages. Parfois, il existe des applications que vous pouvez utiliser et qui ne sont pas sur votre PC de bureau que vous souhaitez ajouter à la stratégie.

Voici une liste des applications fréquemment utilisées et In-Box pour les appareils HoloLens 2.

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
| Explorateur de fichiers              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| MicrosoftStore            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Films et TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Photos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Paramètres                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Conseils                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 : le blocage du programme d’installation d’application bloque uniquement l’application Programme d’installation d’application, et non les applications installées à partir d’autres sources telles que le Microsoft Store ou votre solution MDM.

### Comment trouver un nom de famille de packages

Si une application ne figure pas dans cette liste, un utilisateur peut utiliser Device Portal, connecté à un HoloLens 2 qui a installé l’application qui a souhaité être bloqué, pour déterminer le PackageRelativeID et à partir de là obtenir packageFamilyName.

1. Installez l’application sur votre appareil HoloLens 2. 
1. Ouvrez Paramètres -> mises à jour & sécurité -> pour les développeurs, puis activez le **mode** développeur, puis **Device Portal**. 
    1. Pour plus d’informations, voir plus d’instructions sur la configuration et [l’utilisation de Device Portal ici.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Une fois Device Portal connecté, accédez à **Affichages** puis **Applications**. 
1. Dans le volet Applications installées, utilisez la dropdown pour sélectionner l’application installée. 
1. Recherchez PackageRelativeID. 
1. Copiez les caractères d’application avant !, ces caractères seront votre PackageFamilyName.


