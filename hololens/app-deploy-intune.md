---
title: Intune et portail d’entreprise
description: Découvrez comment configurer, affecter et créer une expérience utilisateur confortable avec Intune, la gestion des appareils mobiles et le portail d’entreprise.
keywords: intune, gestion des applications, application, portail d’entreprise, portail, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283715"
---
# Portail d'entreprise et Intune

Avec la Gestion des périphériques mobiles (MDM), vous pouvez utiliser vos propres applications personnalisées via [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) pour la déployer directement sur vos appareils HoloLens. Microsoft Intune est un service basé sur le cloud qui se concentre sur la gestion des périphériques mobiles (MDM) et la gestion des applications mobiles (MAM). Intune est inclus dans la [suite Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft et permet aux utilisateurs d’être productifs tout en protégeant les données de votre organisation. Pour en savoir plus sur Intune, lisez [Qu’est-ce qu’Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Configuration

1. Téléchargez une application vers un secteur d’activité ou téléchargez une application personnalisée vers votre client Intune. Voir aussi : [Gestion des applications d’entreprise.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [Affectez votre application à un groupe.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) En fonction du type d’affectation que vous choisissez, l’application peut être livrée automatiquement ou disponible pour être facilement tirée vers le bas si vous avez une sélection d’applications.

> [!NOTE]
> Lorsque vous construisez votre ensemble d’applications appx, veillez à inclure l’architecture des appareils sur lesquels vous déployez. HoloLens 2 est ARM64 et HoloLens (1ère génération) est x86. Vous pouvez inclure les deux dans un seul ensemble d’applications si vous envisagez d’avoir un environnement d’appareils mixtes.

## Types d’affectation

Pour que votre application soit installée automatiquement sur l’appareil après l’inscription, vous devez sélectionner **Obligatoire** pour ce ou ces groupes.
Pour rendre votre application disponible pour téléchargement sur les appareils inscrits via le portail d’entreprise, sélectionnez **Disponible pour les appareils inscrits.**

## End-User expérience utilisateur

Une fois que vous avez installé la configuration sur Intune, vous êtes prêt pour les utilisateurs finaux à recevoir vos applications sélectionnées.

Suivez ces étapes pour obtenir automatiquement vos applications :

1. Inscrivez votre appareil auprès de votre client.
2. Une fois l’inscription de votre appareil terminée, vous devez recevoir l’application sur votre appareil.
3. Si vous ne voyez pas votre application immédiatement, rendez-vous sur **Paramètres**Comptes Professionnel ou Scolaire vos informations de compte, puis faites défiler vers le bas pour voir les informations sur l’état de  >  ****  >  ****  >  ** l’application installée.

Comment obtenir des applications via le portail d’entreprise :

1. Ouvrez **le menu Démarrer** et sélectionnez Microsoft **Store.**
2. Recherchez **le portail d’entreprise** et téléchargez l’application.
3. Connectez-vous à votre compte.
4. Sélectionnez l’application que vous souhaitez recevoir et téléchargez-la.

> [!Tip]
> En savoir plus [sur l’installation automatique du portail](https://docs.microsoft.com/mem/intune/apps/company-portal-app) d’entreprise et le déploiement et la gestion des applications dans [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
