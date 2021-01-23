---
title: Comment charger et installer des applications de manière latérale via le programme d’installation d’application HoloLens 2
description: Découvrez comment installer et dépanner des applications avec le programme d’installation de l’application et charger et installer des applications de manière latérale via l’interface utilisateur.
keywords: gestion des applications, application, hololens, programme d’installation d’application
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: af4e222a4f83ab82466a383099897986ddf6b8c4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297289"
---
# Installer des applications sur HoloLens 2 via le programme d’installation d’application

> [!NOTE]
> Cette fonctionnalité a été mise à disposition [dans Windows Holographique, version 20H2 – Mise](hololens-release-notes.md)à jour de décembre 2020. Assurez-vous que votre appareil [est mis à jour](hololens-update-hololens.md) pour utiliser cette fonctionnalité.

Nous avons ajouté une nouvelle fonctionnalité **(Programme** d’installation d’application) pour vous permettre d’installer des applications plus facilement sur vos appareils HoloLens 2. La fonctionnalité sera sur par défaut pour les appareils **nonmanagés.** Pour éviter toute perturbation pour les entreprises, le programme d’installation d’application ne sera pas disponible pour les appareils **gérés** pour le moment.  

Un appareil est considéré comme « géré » si **l’une** des valeurs suivantes est vraie :

- Inscrit à la [gestion des mdm](hololens-enroll-mdm.md)
- Configuré avec le [package d’approvisionnement](hololens-provisioning.md)
- [L’identité de l’utilisateur](hololens-identity.md) est Azure AD

Vous pouvez désormais installer des applications sans avoir besoin d’activer le mode développeur ou d’utiliser Device Portal.  Téléchargez (via USB ou Via Microsoft Edge) le fichier groupé Appx sur votre appareil et accédez à l’ensemble d’applications dans l’Explorateur de fichiers pour être invité à lancer l’installation.  Vous pouvez également [lancer une installation à partir d’une page web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Tout comme les applications que vous installez à partir du Microsoft Store ou chargez une version [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) de version [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) à l’aide de la fonctionnalité de déploiement d’applications LOB de MDM, les applications doivent être signées numériquement avec l’outil de signature et le certificat utilisé pour la signature doit être approuvé par l’appareil HoloLens avant que l’application puisse être déployée.

## Conditions requises

### Pour vos appareils :

Cette fonctionnalité est actuellement disponible dans les builds Windows Holographic 20H2 pour les appareils HoloLens 2. Assurez-vous que tous les appareils utilisant cette [méthode sont mis à jour.](hololens-update-hololens.md)

### Pour vos applications :

La configuration de la solution de votre application doit **être** Master ou **Release,** car le programme d’installation d’application utilisera les dépendances du Store. En savoir plus sur [la création de packages d’application.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

Les applications installées via cette méthode doivent être signées numériquement. Vous devez utiliser un certificat pour signer l’application. Vous pouvez obtenir un certificat à partir de la liste des ca de confiance [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)auquel cas vous n’aurez pas besoin d’action supplémentaire. Vous pouvez également signer votre propre certificat, mais ce certificat devra être poussée sur l’appareil.

- Comment signer des applications à [l’aide de l’outil Signer.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Options de certificat :**

- [Liste MS Trusted CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Choisissez une méthode de déploiement de certificat.**

- [Les packages d’approvisionnement](hololens-provisioning.md) peuvent être appliqués aux appareils locaux.
- La gestion des périphériques de gestion des périphériques peut être utilisée [pour appliquer des certificats avec des configurations d’appareil.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Utilisez le Gestionnaire de certificats [sur l’appareil.](certificate-manager.md)

## Méthode d’installation

1. Vérifiez que votre appareil n’est pas considéré comme géré.
1. Vérifiez que votre appareil HoloLens 2 est sous tension et que vous êtes connecté.
1. Sur votre PC, accédez à votre application personnalisée et copiez votre application.appxbundle dans votredevicename\Stockage interne\Téléchargements.
    Une fois que vous avez terminé la copie de votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation ultérieurement.
1. À partir de votre appareil HoloLens 2, ouvrez le **menu Démarrer,** sélectionnez Toutes les **applications** et lancez l’application **Explorateur de** fichiers.
1. Accédez au dossier Téléchargements. Dans le panneau gauche de l’application, sélectionnez d’abord Cet **appareil,** puis accédez à Téléchargements.
1. Sélectionnez le fichier yourapp.appxbundle.
1. Le programme d’installation d’application se lance. Sélectionnez le **bouton** Installer pour installer votre application.

L’application installée se lance automatiquement à la fin de l’installation.

![Installation d’exemples MRTK via le programme d’installation d’application](images/hololens-app-installer-picture.jpg)

### Résolution des problèmes d’installation

Si l’installation de votre application a échoué, vérifiez les problèmes suivants :

- Votre application est une build Master ou Release.
- Votre appareil est mis à jour vers une build sur laquelle cette fonctionnalité est disponible.
- Vous êtes [connecté à Internet.](hololens-network.md)
- Vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont correctement configurés.  

## Programme d’installation web

Les utilisateurs peuvent installer une application directement à partir d’un serveur web. Ce flux utilise le Programme d’installation d’application combiné à une méthode de distribution de téléchargement et d’installation simple.

### Comment configurer l’installation web :

1. Assurez-vous que votre application est correctement configurée pour l’installation.
1. Suivez ces [étapes pour activer l’installation à partir d’une page web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### Expérience utilisateur final :

1. L’utilisateur reçoit et installe le certificat sur l’appareil à l’aide d’une méthode précédemment choisie ci-dessus.
1. L’utilisateur visite l’URL créée à partir de l’étape ci-dessus.

L’application s’installe maintenant sur l’appareil. Pour trouver l’application, ouvrez **le menu Démarrer** et sélectionnez le bouton Toutes les **applications** pour trouver votre application.

- Pour plus d’informations sur la résolution des problèmes de la méthode d’installation du programme d’installation d’application, consultez [la vidéo de résolution des problèmes du programme d’installation d’application.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> L’interface utilisateur pendant le processus de mise à jour n’est pas prise en charge. Ainsi, l’option ShowPrompt sur [cette page et](https://docs.microsoft.com/windows/msix/app-installer/update-settings) les options associées ne sont pas pris en charge.

## Exemples d’applications

Pour essayer le Programme d’installation d’application avec quelques exemples d’applications, consultez certains de nos exemples disponibles :

- [Hub d’exemples MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Surfaces](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Exemples d’applications UWP qui peuvent être utilisés pour le test](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
