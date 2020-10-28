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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135568"
---
# Contrôle de l’Application Windows Defender

Les applications WDAC permettent à un administrateur informatique de configurer leurs appareils pour bloquer le lancement d’applications sur des appareils. Cette fonction est différente de celle des méthodes de restriction de l’appareil, telles que le mode plein écran, dans laquelle l’utilisateur dispose d’une interface utilisateur qui masque les applications sur l’appareil, mais qui peut toujours être lancée. Lorsque WDAC est implémenté, les applications sont toujours visibles dans la liste toutes les applications, mais la WDAC arrête ces applications et processus de pouvoir être lancée par l’utilisateur de l’appareil.

> [!NOTE]
> Lorsque les utilisateurs finaux essaient de lancer une application qui est bloquée par WDAC, sur HoloLens, il ne recevra pas de notification indiquant qu’il n’est pas en mesure de lancer cette application.

Vous trouverez ci-dessous un guide permettant aux utilisateurs d’apprendre à [utiliser WDac et Windows PowerShell pour autoriser ou bloquer des applications sur les appareils HoloLens 2 avec Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Lorsque les utilisateurs recherchent des applications installées sur leur PC Windows 10 à l’aide du premier exemple de procédure, il est possible que vous deviez apporter quelques tentatives pour affiner les résultats.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si vous ne connaissez pas le nom complet du package, il est possible que vous deviez exécuter’Get-AppxPackage-Name \ * YourBestGuess \ * 'quelques instants pour le trouver. Ensuite, une fois que vous avez le nom exécuter «$package 1 = Get-AppxPackage-nom réel. PackageName'

Par exemple, l’exécution de la commande suivante pour Edge renverra plusieurs résultats, mais de cette liste, vous pouvez identifier le nom complet dont vous avez besoin pour Microsoft. MicrosoftEdge. 

```powershell
Get-AppxPackage -name *edge*
``` 

## Noms de famille de packages pour les applications sur HoloLens

Dans le guide lié ci-dessus, vous pouvez modifier manuellement newPolicy.xml et ajouter des règles pour les applications qui sont uniquement installées sur HoloLens avec leurs noms de famille de packages. Il est parfois possible d’utiliser des applications qui ne se trouvent pas sur votre ordinateur de bureau et que vous voulez ajouter à la stratégie. 

Voici une liste des applications les plus fréquemment utilisées et In-Box pour les appareils HoloLens 2.

| Nom de l’application                   | Nom de la famille de packages                                |
|----------------------------|----------------------------------------------------|
| Visionneuse3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Programme d'installation d'application              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
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
1. Ouvrez paramètres-> mises à jour & allier-> pour les développeurs, puis activez le **mode développeur** et **Device Portal**. 
    1. Pour plus d’informations, consultez la [rubrique Configurer et utiliser Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Une fois que Device Portal est connecté, accédez à **vues** puis **applications**. 
1. Dans le volet applications installées, utilisez la liste déroulante pour sélectionner l’application installée. 
1. Recherchez l’PackageRelativeID. 
1. Copiez des caractères d’application avant!, il s’agira de votre propriété packagefamilyname.

## Exemple de programme d’installation de blocage d’application

Par exemple, vous pourriez vouloir bloquer l’application du [programme d’installation](app-deploy-app-installer.md) de l’application. Dans cet exemple, nous avons inclus des exemples de code. [Pour cet exemple, téléchargez ces exemples de code](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer). Dans le fichier zip, vous trouverez les éléments suivants:

| Fichier | Utiliser |
|-|-|
| compiledPolicy. bin | [Créé à l’étape 9, utilisé dans la dernière étape 10.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| mergedPolicy.xml | [Créé à l’étape 6.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| WDAC_Set. SyncML | Non utilisé dans WDAC mais peut être utilisé pour les [fournisseurs de services de EnterpriseModernAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) |

Si vous souhaitez utiliser le blocage immédiat d’une application, dans ce cas, l’application du programme d’installation de l’application, utilisez le fichier compiledPolicy. bin et passez directement à l’étape 10 du lien ci-dessus. Cela vous permet d’effectuer le test de la stratégie personnalisée et de vérifier l’exactitude des affectations de groupe et de la configuration de la stratégie. 

Si vous voulez combiner la stratégie WDAC de blocage du programme d’installation d’application avec d’autres applications de la liste ci-dessus ou d’une autre application, vous pouvez utiliser le fichier mergedPolicy.xml et continuer à fusionner les nouvelles stratégies. Comme indiqué ci-dessus, les stratégies WDAC sont additives, ce qui n’est pas obligatoire. 

Dans la mesure où l’application du programme d’installation de l’application est lancée lors d’une tentative d’ouverture d’un fichier, une invite s’affiche. Comme indiqué ci-dessus, les applications bloquées par la fonction WDAC n’affichent pas de message d’invite, car l’utilisateur tente d’ouvrir un fichier sur son appareil en raison d’une erreur d’ouverture du fichier. 

![Installation de l’application bloquée par WDAC](images\wdac-app-installer-no-launch.jpg)

Si vous ne souhaitez pas utiliser WDAC, vous pouvez également utiliser le fournisseur de [services de EnterpriseModernAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) pour supprimer l’expérience du programme d’installation de l’application, qui est une application après tout. C’est la raison pour laquelle l’application du programme d’installation de l’application est désinstallée de l’appareil. les extensions de fichier. AppX,. msix,. msixbundle, ainsi que les autres extensions de fichier ainsi que le lancement de l’application Web à l’application ne seront plus gérées par l’application du programme d’installation de l’application. L’utilisateur reçoit une invite pour rechercher un gestionnaire pour l’extension/protocole de fichier dans le Windows Store et ne trouvera pas l’application, car elle n’est pas répertoriée.