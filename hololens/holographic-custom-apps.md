---
title: Gérer les applications personnalisées pour HoloLens
description: Applications personnalisées de chargement latéral sur HoloLens. En savoir plus sur l’installation et la désinstallation des applications holographiques.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, charger, charge latérale, Windows Store, Windows Store, UWP, application, installer
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218631"
---
# Gérer les applications personnalisées pour HoloLens

HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que les nouvelles applications spécifiquement conçues pour HoloLens. Cet article porte sur les applications holographiques personnalisées.  

Pour plus d’informations sur les applications du Windows Store, voir [gérer les applications avec le Windows Store](holographic-store-apps.md).

> [!IMPORTANT]
> Les informations suivantes ont été créées pour le HoloLens (1er génération), également appelé HoloLens (édition de développement HoloLens). Comme ces applications chargement indépendant via Device Portal et l’installation d’applications par Visual Studio étaient banales. Pour les déploiements d’entreprise, nous vous recommandons de ne pas activer le mode développeur, qui est utilisé par les deux méthodes. Si vous êtes intéressé par la méthode de déploiement d’applications sécurisées, consultez notre [rubrique gestion des applications: vue d’ensemble](app-deploy-overview.md).
>
> Si vous recherchez une méthode de développement pour l’installation des applications pour les appareils HoloLens 2, reportez-vous aux rubriques suivantes:
> - [Device Portal: installation d’une application](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Utilisation de Visual Studio pour déployer et déboguer des applications](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Installer des applications personnalisées

Vous pouvez installer vos propres applications sur HoloLens en utilisant Device Portal ou en déployant les applications à partir de Visual Studio.

### Installation d’un package d’application avec Device Portal

1. Etablissez une connexion à partir de [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) vers le HoloLens cible.
1. Dans le volet de navigation gauche, accédez à la page **applications** .
1. Sous le package de l' **application** , recherchez le fichier. AppX associé à votre application.
   > [!IMPORTANT]
   > Veillez à référencer tout fichier de dépendance et de certificat associé.

1. Sélectionnez **Go (atteindre**).
   ![Installer le formulaire d’application dans Windows Device Portal sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Déploiement à partir de Microsoft Visual Studio 2015

1. Ouvrez la solution Visual Studio de votre application (fichier. sln).
1. Ouvrez les **Propriétés**du projet.
1. Sélectionnez la configuration de build suivante: **maître/x86/ordinateur distant**.
1. Lorsque vous sélectionnez **ordinateur distant**:
   - Assurez-vous que l’adresse pointe vers l’adresse IP Wi-Fi de votre HoloLens.
   - Définissez l’authentification sur le **protocole universel (protocole non chiffré)**.
1. Créez votre solution.
1. Pour déployer l’application à partir de votre ordinateur de développement vers votre HoloLens, sélectionnez **ordinateur distant**. Si vous avez déjà une build sur le HoloLens, sélectionnez **Oui** pour installer cette nouvelle version.  

   ![Déploiement d’ordinateurs distants pour les applications dans Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
1. L’application s’installe et démarre automatiquement sur votre HoloLens.

Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrez**  >  **toutes les applications**).
