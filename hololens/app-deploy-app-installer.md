---
title: Comment charger et installer des applications via le programme d’installation de l’application HoloLens 2
description: Télécharger et installer des applications par le biais de l’interface utilisateur
keywords: gestion des applications, application, hololens, programme d’installation de l’application
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 53937881d6569e6aaa17d7e60083381b13502b87
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201368"
---
# Installer des applications sur HoloLens 2 via le programme d’installation d’application


Nous **ajoutons une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications plus en continu** sur vos appareils HoloLens 2. Par défaut, la fonctionnalité est **activée pour les appareils non gérés**. Pour éviter toute interruption des entreprises, le programme d’installation d’applications ne sera **pas disponible pour les appareils gérés pour** le moment.  

> [!NOTE]
> Cette fonctionnalité a été prise en charge dans [Windows holographique, version 20H2: mise à jour 2020 de décembre](hololens-release-notes.md). Assurez-vous que votre appareil est [mis à jour](hololens-update-hololens.md) de façon à utiliser cette fonctionnalité.

Nous avons **ajouté une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications plus en continu** sur vos appareils HoloLens 2. Par défaut, la fonctionnalité est **activée pour les appareils non gérés**. Pour éviter toute interruption des entreprises, le programme d’installation d’applications ne sera **pas disponible pour les appareils gérés pour** le moment.  

Un appareil est considéré comme «géré» si l' **une** des conditions suivantes est vraie:
- GPM [inscrits](hololens-enroll-mdm.md)
- Configuré avec le [package de mise en service](hololens-provisioning.md)
- L' [identité](hololens-identity.md) de l’utilisateur est AAD

Vous pouvez maintenant installer des applications sans avoir besoin d’activer le mode développeur ou Device Portal.  Il vous suffit de télécharger (via câble USB ou via le système) l’ensemble d’applications AppX sur votre appareil et d’accéder à l’ensemble d’applications AppX de l’Explorateur de fichiers pour être invité à démarrer l’installation.  Vous pouvez également [lancer une installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  À l’instar des applications que vous installez à partir du Microsoft Store ou d’charger à l’aide de la fonctionnalité de déploiement d’applications métier de la gestion des applications métier, les applications doivent être signées numériquement à l’aide de l' [outil de signature](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour pouvoir déployer l’application.   

## Conditions requises

### Pour vos appareils: 
Ce n’est actuellement avalible que dans les [versions de Windows Insider](hololens-insider.md) pour les appareils HoloLens 2. Vérifiez que tous les appareils qui utilisent cette méthode sont [mis à jour](hololens-update-hololens.md). 

### Pour vos applications: 
La configuration de la solution de votre application doit être **maître** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du Windows Store. En savoir plus sur la [création de packages d’application](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Les applications installées par le biais de cette méthode doivent être signées numériquement. Vous devez utiliser un certificat pour signer l’application. Vous pouvez obtenir un certificat de la [liste des autorités de certification MS Trusted](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), auquel cas vous n’avez pas besoin d’effectuer d’action supplémentaire. Vous pouvez également signer votre propre certificat, mais ce certificat doit être envoyé sur le périphérique. 
- Comment signer des applications [à l’aide de l’outil signature.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Options de certificat:** 
- [Liste des autorités de certification MS Trusted](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Choisissez une méthode de déploiement de certificats.** 
- Les [packages de mise en service](hololens-provisioning.md) peuvent être appliqués aux périphériques locaux.
- La gestion des périphériques mobiles peut être utilisée pour [appliquer des certificats avec des configurations d’appareil](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Utiliser le gestionnaire de [certificats](certificate-manager.md)d’appareil. 

## Méthode d’installation

1.  Assurez-vous que votre appareil n’est pas considéré comme géré.
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
