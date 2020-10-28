---
title: Comment charger et installer des applications via le programme d’installation de l’application HoloLens 2
description: Télécharger et installer des applications par le biais de l’interface utilisateur
keywords: gestion des applications, application, hololens, programme d’installation de l’application
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135525"
---
# Installer des applications sur HoloLens 2 via le programme d’installation d’application

Dans notre version de Windows Insider, nous **ajoutons une nouvelle fonctionnalité (programme d’installation d’application) qui vous permet d’installer des applications plus en toute transparence** sur vos appareils HoloLens 2.  Vous pouvez maintenant installer des applications sans avoir besoin d’activer le mode développeur ou Device Portal.  Il vous suffit de télécharger (via câble USB ou via le système) l’ensemble d’applications AppX sur votre appareil et d’accéder à l’ensemble d’applications AppX de l’Explorateur de fichiers pour être invité à démarrer l’installation.  Vous pouvez également [lancer une installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  À l’instar des applications que vous installez à partir du Microsoft Store ou d’charger à l’aide de la fonctionnalité de déploiement d’applications métier de la gestion des applications métier, les applications doivent être signées numériquement à l’aide de l' [outil de signature](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour pouvoir déployer l’application.   

Cette mise à jour s’aligne sur le Bureau sur lequel [chargement indépendant est activé par défaut](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/) .

> [!IMPORTANT]
> Pour le moment, cette fonctionnalité est uniquement avalible dans les builds Insider 19041.1377 +. En [savoir plus sur l’inscription aux builds Insider pour Windows](hololens-insider.md).

> [!NOTE]
> Pour les administrateurs informatiques désireux de désactiver cette fonctionnalité, utilisez le nom de la famille de packages suivant dans le cadre de votre [stratégie WDac](windows-defender-application-control-wdac.md). Cela bloquera uniquement l’application du programme d’installation de l’application, et non les applications installées à partir d’autres sources telles que le Microsoft Store ou de votre solution GPM.
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> Nous vous recommandons d’utiliser la [stratégie WDac](windows-defender-application-control-wdac.md) pour contrôler les applications, mais si vous souhaitez uniquement autoriser les applications du Windows Store, les appareils configurés pour définir explicitement la stratégie [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) sur «non allowed» autorisent uniquement l’installation des applications à partir du Microsoft Store. 

## Conditions requises

### Pour vos appareils: 
> [!NOTE]
> Pour le moment, cette fonctionnalité est uniquement avalible dans les builds Insider 19041.1377 +. En [savoir plus sur l’inscription aux builds Insider pour Windows](hololens-insider.md).

### Pour vos applications: 
La configuration de la solution de votre application doit être **maître** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du Windows Store. En savoir plus sur la [création de packages d’application](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Les applications installées par le biais de cette méthode doivent être signées numériquement. Vous devez utiliser un certificat pour signer l’application. Vous pouvez obtenir un certificat de la [liste des autorités de certification MS Trusted](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), auquel cas vous n’avez pas besoin d’effectuer d’action supplémentaire. Vous pouvez également signer votre propre certificat, mais ce certificat doit être envoyé sur le périphérique. 
- Comment signer des applications [à l’aide de l’outil signature.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Options de certificat:** 
- [Liste des autorités de certification MS Trusted](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Choisissez une méthode de déploiement de certificats.** 
- Les [packages de mise en service](hololens-provisioning.md) peuvent être appliqués aux périphériques locaux.
- La gestion des périphériques mobiles peut être utilisée pour [appliquer des certificats avec des configurations d’appareil](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Utiliser le gestionnaire de [certificats](hololens-insider.md#certificate-manager)d’appareil. 

## Méthode d’installation

1.  Vérifiez que votre appareil HoloLens 2 est allumé et que vous êtes connecté.
1.  Sur votre PC, accédez à votre application personnalisée, puis copiez le fichier VotreApplication. appxbundle sur yourdevicename\Internal Storage\Downloads. 
    À la fin de la copie de votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation plus tard.
1.  Sur votre appareil HoloLens 2, ouvrez le **menu Démarrer**, sélectionnez **toutes les applications** , puis lancez l’application **Explorateur de fichiers** .
1.  Accédez au dossier téléchargements. Vous pouvez être amené à vous rendre dans le volet gauche de l’application sélectionnez **ce dernier** d’abord, puis accéder à téléchargements.
1.  Sélectionnez le fichier VotreApplication. appxbundle. 
1.  Le programme d’installation de l’application démarre. Sélectionnez le bouton **installer** pour installer votre application. 

L’application installée s’ouvre automatiquement lors de l’installation. 

![Installation des exemples MRTK via le programme d’installation de l’application](images/hololens-app-installer-picture.jpg)

### Résolution des problèmes d’installation
Si votre application n’a pas réussi à procéder à l’installation, vérifiez les points suivants:
-   Votre application est une build de type maître ou version Release.
- Votre appareil est mis à jour vers une build sur laquelle cette fonctionnalité est disponible. 
-   Vous êtes [connecté à Internet](hololens-network.md).
-   Vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont correctement configurés.  

## Programme d’installation Web

Les utilisateurs peuvent installer une application directement à partir d’un serveur Web. Cela nécessite une utilisation du programme d’installation de l’application combinée à une méthode simple de distribution et d’installation. 

### Configuration de l’installation Web:
1.  Assurez-vous que votre application est correctement configurée pour l’installation.
1.  Procédez comme [suit pour l’activer sur une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 

### Utilisation de l’utilisateur final:
1. Un utilisateur reçoit et installe un certificat sur l’appareil à l’aide de la méthode choisie précédemment. 
1. Un utilisateur visite l’URL créée à l’étape ci-dessus.

L’application sera désormais installée sur l’appareil. Pour Rechercher l’application, ouvrez le **menu Démarrer** , puis sélectionnez le bouton **toutes les applications** pour rechercher votre application. 

-   Pour obtenir de l’aide pour résoudre ce problème, consultez la rubrique [résoudre les problèmes du programme](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)d’installation de l’application. 

> [!NOTE]
> Le processus de mise à jour de l’interface utilisateur n’est pas pris en charge. Par conséquent, l’option ShowPrompt sur [cette page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) et les options associées ne sont pas prises en charge.

## Exemples d’applications

Si vous voulez faire votre choix dans quelques exemples d’applications, consultez quelques exemples disponibles:
- [MRTK-hubs](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Freins](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Exemples d’applications UWP pouvant être utilisés à des fins de test](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
