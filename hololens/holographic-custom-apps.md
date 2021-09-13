---
title: gérer les applications personnalisées pour les HoloLens (1ère génération)
description: découvrez comment installer, désinstaller et charger des applications holographiques personnalisées sur des appareils HoloLens à l’aide du portail des appareils et Visual Studio.
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032507"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>gérer les applications personnalisées pour les HoloLens (1ère génération)

HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que de nouvelles applications conçues spécifiquement pour HoloLens. Cet article se concentre sur les applications holographiques personnalisées.  

Pour plus d’informations sur les applications du Windows Store, consultez [gérer les applications avec le Windows Store](holographic-store-apps.md).

> [!IMPORTANT]
> les informations suivantes ont été créées pour la HoloLens (1re génération), également appelée édition HoloLens developer à ce moment-là. en tant que telles, les applications chargement via le portail des appareils et l’installation d’applications via Visual Studio étaient courantes. Pour les déploiements d’entreprise, nous vous déconseillons d’activer le mode développeur, que ces deux méthodes utilisent. Si vous êtes intéressé par une méthode de déploiement d’application sécurisée, consultez la [vue d’ensemble](app-deploy-overview.md)de la gestion des applications.
>
> si vous recherchez une méthode de développeur pour l’installation d’applications pour HoloLens 2 appareils, consultez :
>
> - [Portail de l’appareil : installation d’une application](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [utilisation de Visual Studio pour déployer et déboguer des applications](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Installer des applications personnalisées

vous pouvez installer vos propres applications sur HoloLens à l’aide du portail des appareils ou en déployant les applications à partir de Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Installation d’un package d’application avec le portail de l’appareil

1. Établissez une connexion entre le portail de l' [appareil](/windows/mixed-reality/using-the-windows-device-portal) et le HoloLens cible.

1. Dans le volet de navigation de gauche, accédez à la page **applications** .

1. Sous **package d’application** , accédez au fichier. AppX associé à votre application.

   > [!IMPORTANT]
   > Veillez à référencer les fichiers de dépendance et de certificat associés.

1. Sélectionnez **Go**.

   > [!div class="mx-imgBorder"]
   > ![installez le formulaire d’application dans Windows portail des appareils sur Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>déploiement à partir de Microsoft Visual Studio 2015

1. ouvrez la solution Visual Studio de votre application (fichier. sln).

1. Ouvrez les **Propriétés** du projet.

1. Sélectionnez la configuration de build suivante : **maître/x86/ordinateur distant**.

1. Lorsque vous sélectionnez **ordinateur distant**:
   - Assurez-vous que l’adresse pointe vers l’adresse IP Wi-Fi de votre HoloLens.
   - Définissez authentification sur **universel (protocole non chiffré)**.
   
1. Générez votre solution.

1. pour déployer l’application à partir de votre PC de développement vers votre HoloLens, sélectionnez **Machine distante**. si vous disposez déjà d’une build dans le HoloLens, sélectionnez **oui** pour installer cette version plus récente.  

   ![déploiement d’ordinateurs distants pour les applications à Microsoft HoloLens dans Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. L’application s’installe et se lance automatiquement sur votre HoloLens.

Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrer**  >  **toutes les applications**).
