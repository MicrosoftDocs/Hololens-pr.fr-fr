---
title: Gérer les applications personnalisées pour HoloLens (1re génération)
description: Découvrez comment installer, désinstaller et charger des applications holographiques personnalisées sur des appareils HoloLens à l’aide de Device Portal et Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, chargement de version test, chargement de version test, chargement de version test, store, uwp, application, installer
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296987"
---
# Gérer les applications personnalisées pour HoloLens (1re génération)

HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que les nouvelles applications spécifiquement conçues pour HoloLens. Cet article se concentre sur les applications holographiques personnalisées.  

Pour plus d’informations sur les applications du Store, voir [Gérer les applications avec le Windows Store.](holographic-store-apps.md)

> [!IMPORTANT]
> Les informations suivantes ont été créées pour HoloLens (1ère génération), également appelée HoloLens Developer Edition à ce moment-là. En tant que tel, le chargement d’applications de version secondaire via Device Portal et l’installation d’applications via Visual Studio ont été très fréquents à ce moment-là. Pour les déploiements d’entreprise, nous vous déconseillons d’activer le mode développeur, que ces deux méthodes utilisent. Si vous êtes intéressé par une méthode de déploiement d’application sécurisée, consultez notre [Gestion des applications : Vue d’ensemble.](app-deploy-overview.md)
>
> Si vous recherchez l’une ou l’autre méthode de développeur d’installation d’application pour les appareils HoloLens 2, reportez-vous à :
> - [Device Portal : installation d’une application](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Utilisation de Visual Studio pour déployer et déboguer des applications](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Installer des applications personnalisées

Vous pouvez installer vos propres applications sur HoloLens à l’aide de Device Portal ou en déployant les applications à partir de Visual Studio.

### Installation d’un package d’application avec Device Portal

1. Établir une connexion à [partir de Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) avec le HoloLens cible.

1. Dans le navigation de gauche, accédez à la page **Applications.**

1. Sous **Package d’application,** accédez au fichier .appx associé à votre application.

   > [!IMPORTANT]
   > Veillez à référencer les fichiers de dépendance et de certificat associés.

1. Sélectionnez **Go**.

   > [!div class="mx-imgBorder"]
   > ![Formulaire d’installation de l’application dans Windows Device Portal sur Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Déploiement à partir de Microsoft Visual Studio 2015

1. Ouvrez la solution de Visual Studio de votre application (fichier .sln).

1. Ouvrez les propriétés **du projet.**

1. Sélectionnez la configuration de build suivante : **Master/x86/Remote Machine**.

1. Lorsque vous sélectionnez **Ordinateur distant**:
   - Assurez-vous que l’adresse pointe vers Wi-Fi adresse IP de votre HoloLens.
   - Définissez **l’authentification sur Universel (protocole non chiffré).**
   
1. Créez votre solution.

1. Pour déployer l’application à partir de votre PC de développement sur votre HoloLens, sélectionnez **Ordinateur distant.** Si vous avez déjà une build existante sur HoloLens, sélectionnez **Oui** pour installer cette version plus récente.  

   ![Déploiement d’ordinateurs distants pour les applications à Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. L’application s’installe et se lance automatiquement sur votre HoloLens.

Une fois que vous avez installé une application, vous la trouverez dans la liste **Toutes** les applications (**Démarrez**  >  **toutes les applications).**
