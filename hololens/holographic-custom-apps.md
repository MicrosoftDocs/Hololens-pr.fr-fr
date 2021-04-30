---
title: Gérer des applications personnalisées pour HoloLens (1ère génération)
description: Découvrez comment installer, désinstaller et charger des applications holographiques personnalisées sur des appareils HoloLens à l’aide du portail des appareils et de Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, chargement, chargement en un côté, chargement indépendant, Store, UWP, application, installer
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308658"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gérer des applications personnalisées pour HoloLens (1ère génération)

HoloLens prend en charge de nombreuses applications existantes à partir du Microsoft Store, ainsi que de nouvelles applications spécifiquement conçues pour HoloLens. Cet article se concentre sur les applications holographiques personnalisées.  

Pour plus d’informations sur les applications du Windows Store, consultez [gérer les applications avec le Windows Store](holographic-store-apps.md).

> [!IMPORTANT]
> Les informations suivantes ont été créées pour le HoloLens (1re génération), également appelé l’édition de développement HoloLens à ce moment-là. En tant que telles, les applications chargement via le portail des appareils et l’installation d’applications via Visual Studio étaient courantes. Pour les déploiements d’entreprise, nous vous déconseillons d’activer le mode développeur, que ces deux méthodes utilisent. Si vous êtes intéressé par une méthode de déploiement d’application sécurisée, consultez la [vue d’ensemble](app-deploy-overview.md)de la gestion des applications.
>
> Si vous recherchez une méthode de développeur pour l’installation d’applications pour les appareils HoloLens 2, reportez-vous à :
> - [Portail de l’appareil : installation d’une application](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Utilisation de Visual Studio pour déployer et déboguer des applications](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installer des applications personnalisées

Vous pouvez installer vos propres applications sur HoloLens soit à l’aide du portail de l’appareil, soit en déployant les applications à partir de Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installation d’un package d’application avec le portail de l’appareil

1. Établissez une connexion entre le portail de l' [appareil](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) et le HoloLens cible.

1. Dans le volet de navigation de gauche, accédez à la page **applications** .

1. Sous **package d’application** , accédez au fichier. AppX associé à votre application.

   > [!IMPORTANT]
   > Veillez à référencer les fichiers de dépendance et de certificat associés.

1. Sélectionnez **Go**.

   > [!div class="mx-imgBorder"]
   > ![Installer le formulaire d’application dans le portail de périphériques Windows sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Déploiement à partir de Microsoft Visual Studio 2015

1. Ouvrez la solution Visual Studio de votre application (fichier. sln).

1. Ouvrez les **Propriétés** du projet.

1. Sélectionnez la configuration de build suivante : **maître/x86/ordinateur distant**.

1. Lorsque vous sélectionnez **ordinateur distant**:
   - Assurez-vous que l’adresse pointe vers l’adresse IP Wi-Fi de votre HoloLens.
   - Définissez authentification sur **universel (protocole non chiffré)**.
   
1. Générez votre solution.

1. Pour déployer l’application à partir de votre PC de développement vers votre HoloLens, sélectionnez **machine distante**. Si vous avez déjà une build existante sur HoloLens, sélectionnez **Oui** pour installer cette version plus récente.  

   ![Déploiement d’ordinateurs distants pour des applications dans Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. L’application s’installe et se lance automatiquement sur votre HoloLens.

Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrer**  >  **toutes les applications**).
