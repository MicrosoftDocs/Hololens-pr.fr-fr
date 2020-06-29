---
title: Gérer les applications personnalisées pour HoloLens
description: Applications personnalisées de chargement latéral sur HoloLens. En savoir plus sur l’installation et la désinstallation des applications holographiques.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828163"
---
# Gérer les applications personnalisées pour HoloLens

HoloLens prend en charge de nombreuses applications existantes du Microsoft Store, ainsi que les nouvelles applications spécialement conçues pour HoloLens. Cet article porte sur les applications holographiques personnalisées.  

Pour plus d’informations sur les applications du Windows Store, voir [gérer les applications avec le Windows Store](holographic-store-apps.md).

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
   - Assurez-vous que l’adresse pointe sur l’adresse IP Wi-Fi de votre HoloLens.
   - Définissez l’authentification sur le **protocole universel (protocole non chiffré)**.
1. Créez votre solution.
1. Pour déployer l’application à partir de votre ordinateur de développement vers votre HoloLens, sélectionnez **ordinateur distant**. Si vous avez déjà une build sur le HoloLens, sélectionnez **Oui** pour installer cette nouvelle version.  

   ![Déploiement d’ordinateurs distants pour les applications dans Microsoft HoloLens dans Visual Studio](images/vs2015-remotedeployment.jpg)  
1. L’application s’installe et démarre automatiquement sur votre HoloLens.

Une fois que vous avez installé une application, vous la trouverez dans la liste **toutes les applications** (**Démarrez**  >  **toutes les applications**).
