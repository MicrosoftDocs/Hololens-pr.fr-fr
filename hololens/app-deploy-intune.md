---
title: Intune et Portail d’entreprise
description: Découvrez comment configurer, attribuer et créer une expérience utilisateur confortable avec Intune, la gestion des appareils mobiles et le portail d’entreprise.
keywords: Intune, gestion des applications, application, portail d’entreprise, portail, hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635498"
---
# <a name="intune--company-portal"></a>Intune et le portail d’entreprise

avec la gestion des appareils mobiles (MDM), vous pouvez utiliser vos propres applications personnalisées par le biais de [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) pour les déployer directement sur vos appareils HoloLens. Microsoft Intune est un service cloud qui se concentre sur la gestion des appareils mobiles (MDM) et la gestion des applications mobiles (GAM). Intune est inclus dans la suite [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) de Microsoft, et permet aux utilisateurs d’être productifs tout en protégeant les données de votre organisation. Pour en savoir plus sur Intune, consultez [qu’est-ce qu’Intune](/mem/intune/fundamentals/what-is-intune).

## <a name="setup"></a>Programme d’installation

1. Télécharger une application à une activité ou téléchargez une application personnalisée sur votre locataire Intune. voir aussi : [Enterprise la gestion des applications](/windows/client-management/mdm/enterprise-app-management).

2. [Affectez votre application à un groupe](/mem/intune/apps/apps-deploy). Selon le type d’affectation que vous choisissez, l’application peut être remise automatiquement ou disponible pour être extraite facilement si vous avez sélectionné des applications.

> [!NOTE]
> Lors de la création de votre bundle AppX, veillez à tenir compte de l’architecture des appareils sur lesquels vous effectuez le déploiement. HoloLens 2 est ARM64 et HoloLens (1re génération) est x86. Vous pouvez inclure les deux dans un même Bundle AppX si vous prévoyez d’avoir un environnement mixte d’appareils.

## <a name="assignment-types"></a>Types d’attributions

Pour que votre application soit automatiquement installée sur l’appareil après l’inscription, vous devez sélectionner **obligatoire** pour ce (s) groupe (s).
Pour que votre application soit disponible en téléchargement sur des appareils inscrits via le portail d’entreprise, sélectionnez **disponible pour les appareils inscrits**.

## <a name="end-user-experience"></a>Expérience de l’utilisateur final

Une fois que vous avez configuré la configuration sur Intune, vous êtes prêt pour que les utilisateurs finaux puissent recevoir vos applications sélectionnées.

Procédez comme suit pour récupérer automatiquement vos applications :

1. Inscrivez votre appareil auprès de votre locataire.
2. Une fois l’inscription de votre appareil terminée, vous devez recevoir l’application sur votre appareil.
3. si vous ne voyez pas immédiatement l’application, accédez à **Paramètres**  >  **comptes**  >  **professionnels ou scolaires**  >  informations de *votre compte* , puis faites défiler la page pour afficher les informations sur l’état de l’application installée.

comment accéder aux applications via l’Portail d’entreprise :

1. Ouvrez le **menu Démarrer** et sélectionnez **Microsoft Store**.
2. recherchez **Portail d’entreprise** et téléchargez l’application.
3. Connectez-vous à votre compte.
4. Sélectionnez l’application que vous souhaitez recevoir et téléchargez-la.

> [!Tip]
> en savoir plus sur [l’installation automatique du Portail d’entreprise et le](/mem/intune/apps/company-portal-app) [déploiement et la gestion d’applications dans Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
