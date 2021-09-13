---
title: guide pratique pour charger et installer des applications via HoloLens 2 programme d’installation de l’application
description: Apprenez à installer et à dépanner des applications avec le programme d’installation d’application et à charger et installer des applications par le biais de l’interface utilisateur.
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032491"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>installer des applications sur HoloLens 2 via le programme d’installation d’application

> [!NOTE]
> cette fonctionnalité a été [mise à disposition dans Windows holographique, version 20H2-mise à jour de décembre 2020](hololens-release-notes.md). Assurez-vous que votre appareil est [mis à jour](hololens-update-hololens.md) pour utiliser cette fonctionnalité.

nous avons **ajouté une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications de manière plus transparente** sur vos appareils HoloLens 2. La fonctionnalité est **activée par défaut pour les appareils non gérés**. Pour éviter toute interruption des entreprises, le programme d’installation de l’application ne sera **pas disponible pour les appareils gérés** à l’heure actuelle.  

Un appareil est considéré comme « géré » si l' **une** des conditions suivantes est vraie :

- MDM [inscrit](hololens-enroll-mdm.md)
- Configuré avec le [package d’approvisionnement](hololens-provisioning.md)
- L' [identité](hololens-identity.md) de l’utilisateur est Azure ad

Vous êtes maintenant en mesure d’installer des applications sans avoir à activer le mode développeur ou à l’aide du portail des appareils.  téléchargez (sur USB ou via Microsoft Edge) le bundle appx sur votre appareil et accédez au bundle appx dans l’explorateur de fichiers pour être invité à lancer l’installation.  Vous pouvez également [lancer une installation à partir d’une page Web](/windows/msix/app-installer/installing-windows10-apps-web). tout comme les applications que vous installez à partir de la Microsoft Store ou chargement à l’aide de la fonctionnalité de déploiement d’applications métier MDM, les applications doivent être signées numériquement avec l' [outil sign](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour que l’application puisse être déployée.

## <a name="requirements"></a>Configuration requise

### <a name="for-your-devices"></a>Pour vos appareils :

cette fonctionnalité est actuellement disponible dans Windows les builds 20H2 holographiques pour les appareils HoloLens 2. Assurez-vous que tous les appareils qui utilisent cette méthode sont [mis à jour](hololens-update-hololens.md).

### <a name="for-your-apps"></a>Pour vos applications :

La configuration de la solution de votre application doit être **Master** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du magasin. En savoir plus sur la [création de packages d’application](/windows/msix/app-installer/create-appinstallerfile-vs).

Les applications qui sont installées par le biais de cette méthode doivent être signées numériquement. Vous devez utiliser un certificat pour signer l’application. Vous pouvez obtenir un certificat à partir de la [liste des autorités de certification de confiance MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). dans ce cas, vous n’aurez pas besoin d’effectuer d’action supplémentaire. Vous pouvez aussi signer votre propre certificat. Toutefois, ce certificat devra être envoyé sur l’appareil.

- Comment signer des applications [à l’aide de l’outil Sign.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Options de certificat :**

- [Liste des autorités de certification de confiance MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Choisissez une méthode de déploiement de certificat.**

- Les [packages d’approvisionnement](hololens-provisioning.md) peuvent être appliqués à des appareils locaux.
- MDM peut être utilisé pour [appliquer des certificats avec des configurations d’appareil](/mem/intune/protect/certificates-configure).
- Utilisez le gestionnaire de [certificats](certificate-manager.md)de l’appareil.

## <a name="installation-method"></a>Méthode d’installation

1. Vérifiez que votre appareil n’est pas considéré comme géré.
1. vérifiez que votre appareil HoloLens 2 est sous tension et que vous êtes connecté.
1. sur votre PC, accédez à votre application personnalisée et copiez votreapplication. appxbundle sur yourdevicename\Internal Stockage \Downloads.
    Une fois que vous avez fini de copier votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation ultérieurement.
1. à partir de votre appareil HoloLens 2, ouvrez le **Menu démarrer**, sélectionnez **toutes les applications** , puis lancez l’application **explorateur de fichiers** .
1. Accédez au dossier téléchargements. Vous devrez peut-être dans le volet gauche de l’application sélectionner **cet appareil** en premier, puis accéder à téléchargements.
1. Sélectionnez le fichier VotreApplication. appxbundle.
1. Le programme d’installation de l’application démarre. Sélectionnez le bouton **installer** pour installer votre application.

L’application installée sera automatiquement lancée à la fin de l’installation de.

![Installation d’exemples MRTK via le programme d’installation de l’application.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Résolution des problèmes d’installation

Si votre application n’a pas pu être installée, vérifiez les éléments suivants pour résoudre les problèmes :

- Votre application est une version principale ou une version Release.
- Votre appareil est mis à jour vers une version sur laquelle cette fonctionnalité est disponible.
- Vous êtes [connecté à Internet](hololens-network.md).
- vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont configurés correctement.  

## <a name="web-installer"></a>Programme d’installation web

Les utilisateurs peuvent installer une application directement à partir d’un serveur Web. Ce processus utilise le programme d’installation d’application associé à une méthode de distribution de téléchargement et d’installation facile.

### <a name="how-to-set-up-web-install"></a>Procédure de configuration de l’installation Web :

1. Vérifiez que votre application est correctement configurée pour l’installation.
1. [Pour activer l’installation à partir d’une page Web](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage), procédez comme suit.

### <a name="end-user-experience"></a>Expérience de l’utilisateur final :

1. L’utilisateur reçoit et installe le certificat sur l’appareil à l’aide d’une méthode précédemment choisie ci-dessus.
1. L’utilisateur visite l’URL créée à l’étape précédente.

L’application s’installe désormais sur l’appareil. pour rechercher l’application, ouvrez le **menu Démarrer** , puis sélectionnez le bouton **toutes les applications** pour rechercher votre application.

- Pour plus d’informations sur la résolution des problèmes liés à la méthode d’installation de l’application, consultez [résoudre les problèmes](/windows/msix/app-installer/troubleshoot-appinstaller-issues)liés au programme d’installation.

> [!NOTE]
> L’interface utilisateur pendant le processus de mise à jour n’est pas prise en charge. Par conséquent, l’option ShowPrompt sur [cette page](/windows/msix/app-installer/update-settings) et les options associées ne sont pas prises en charge.

## <a name="sample-apps"></a>Exemples d’applications

Essayez le programme d’installation de l’application avec l’un de nos exemples d’applications disponibles. 
> [!div class="nextstepaction"]
> [Exemples d’application](/windows/mixed-reality/develop/features-and-samples)
