---
title: Intune et portail d’entreprise
description: Intune, gestion des applications, application, portail d’entreprise, portail
keywords: Intune, gestion des applications, application, portail d’entreprise, portail, hololens
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6a79224d02b4251a76f97f0463d4a11f6496670
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857901"
---
# Intune & portail d’entreprise

La gestion des périphériques mobiles (GPM) vous permet d’utiliser vos propres applications par le biais du [Gestionnaire de points de terminaison Microsoft](https://docs.microsoft.com/intune/windows-holographic-for-business) pour le déployer directement sur vos appareils HoloLens. Microsoft Intune est un service basé sur le Cloud qui est axé sur la gestion des périphériques mobiles (GPM) et la gestion des applications mobiles (GAM). Intune est inclus dans la[suite entreprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft, et permet aux utilisateurs d’être productifs tout en conservent la protection des données de votre organisation. Pour en savoir plus sur Intune, voir [qu’est-ce que Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Configuration

1. Téléchargez une application sur une ligne de Business ou téléchargez une application personnalisée sur votre client Intune. Voir aussi: [gestion des applications d’entreprise](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Attribuez votre application à un groupe](https://docs.microsoft.com/mem/intune/apps/apps-deploy). En fonction du type d’affectation que vous choisissez, vous pouvez faire en sorte que l’application soit remise automatiquement ou prête à être facilement récupérée si vous avez une sélection d’applications. 

> [!NOTE] 
> Lors de la création de votre ensemble d’applications AppX, assurez-vous de prendre en compte l’architecture du ou des périphériques sur lesquels vous effectuez le déploiement. HoloLens 2 est ARM64 et HoloLens (1ère génération) est x86. Vous pouvez inclure les deux dans un seul ensemble d’applications AppX si vous envisagez de disposer d’un environnement d’appareils mixtes.

## Types d’affectations

Si vous préférez que votre application soit installée automatiquement sur l’appareil après l’inscription, vous devez sélectionner **obligatoire** pour ce ou ces groupes.
Si vous préférez rendre votre application disponible en téléchargement sur les utilisateurs inscrits via le portail d’entreprise, sélectionnez **disponible pour les appareils inscrits**.


## Utilisation de l’utilisateur final

Après avoir configuré la configuration sur Intune, vous êtes prêt pour que les utilisateurs finaux puissent recevoir vos applications sélectionnées.

Pour obtenir automatiquement vos applications, procédez comme suit:
1. Inscrivez votre appareil auprès de votre client. 
2. Une fois que votre appareil a terminé l’inscription, vous devriez recevoir l’application sur votre appareil. 
3. Si vous ne voyez pas immédiatement votre application, accédez à **paramètres**de  >  **compte**  >  **travail ou établissement d’enseignement**  >  **votrecomptehttp://www.Office.com/redir/xt102780162** et faites défiler vers le bas pour consulter des informations sur l’état des applications installées.

Pour accéder aux applications via le portail d’entreprise, procédez comme suit:
1. Ouvrez le **menu Démarrer** , puis sélectionnez **Microsoft Store**. 
2. Recherchez **portail d’entreprise** et téléchargez l’application.
3. Connectez-vous à votre compte.
4. Sélectionnez l’application que vous souhaitez recevoir et télécharger.

> [!Tip]
> En savoir plus sur l' [installation automatique du portail d’entreprise et le](https://docs.microsoft.com/mem/intune/apps/company-portal-app) [déploiement et la gestion des applications dans Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
