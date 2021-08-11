---
title: 'Conditions de licence :'
description: Restez informés de toutes les exigences de licence et des instructions dont vous avez besoin pour la gestion des appareils mobiles, d’HoloLens et de Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: aae4e1dbbf28906c1f93ac7f29620260023f596bb96fc23a3ee78442e70585fa
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663298"
---
# <a name="license-requirements"></a>Conditions de licence :

## <a name="overview"></a>Vue d’ensemble
Cette page fournit une vue d’ensemble des licences et des comptes nécessaires pour déployer des appareils HoloLens 2 gérés et non gérés dans votre organisation. Elle contient également des informations sur les licences de Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) et [Guides](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>Licences et comptes requis pour HoloLens 2

 
|       &nbsp;      | HoloLens géré | HoloLens non géré |
|-------------------|-----------------|---------------------|
| **Cas d’usage professionnel** | | |
| [Déployer sur des appareils connectés au cloud - déploiement de preuve de concept/pilote](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Déployer au sein du réseau de votre organisation - déploiement à grande échelle](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Déployer dans un environnement hors connexion sécurisé](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licences** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> ou <sup>2</sup>) | ✔️  | |
| **Comptes (Accounts)** |  | |
| Compte d’administrateur Azure AD | ✔️ |  |
| Compte d’utilisateur Azure AD | ✔️ | |
| [Compte Microsoft](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Compte local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Inscription automatique](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) pendant la configuration initiale de l’appareil, qui inscrit et joint Azure Active Directory et permet à l’appareil d’être géré par Intune.
- <sup>2</sup> [Windows Autopilot pour HoloLens 2](hololens2-autopilot.md) simplifie l’expérience de provisionnement pour les administrateurs informatiques et les utilisateurs finaux. Les administrateurs informatiques peuvent préconfigurer des stratégies HoloLens 2 et, lors du premier démarrage, les appareils seront déployés dans un état prêt à une utilisation professionnelle sans aucune interaction de l’utilisateur.
- <sup>3</sup> Ce compte doit être préalablement [provisionné](hololens-provisioning.md#provisioning-package-hololens-wizard) avec le Concepteur de configuration Windows.

> [!IMPORTANT]
> Active Directory (AD) ne peut pas être utilisé pour gérer les appareils HoloLens.
 
> [!WARNING]
> Un appareil utilisant un compte MSA ou local ne peut pas prendre en charge plusieurs utilisateurs.

## <a name="dynamics-365-licensing-and-requirements"></a>Configuration requise pour la gestion des licences Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Admin

- Compte Azure AD (nécessaire pour l’achat de l’abonnement et l’attribution de licences)
- [Abonnement Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Essai Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Utilisateur Remote Assist Dynamics 365

- Compte Azure AD

- Licence Remote Assist 

  > [!NOTE]
  > Microsoft Teams est fourni avec Remote Assist

- Connectivité réseau

#### <a name="microsoft-teams-user"></a>Utilisateur Microsoft Teams

- Compte Azure AD

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Connectivité réseau

Si vous prévoyez d’implémenter ce [scénario multilocataire](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), vous pouvez avoir besoin d’une licence Cloisonnement de l’information. Consultez [cet article](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) pour déterminer si une licence Cloisonnement de l’information est nécessaire.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Admin

1. Compte Azure AD (nécessaire pour l’achat de l’abonnement et l’attribution de licences)
2. [Abonnement ou essai gratuit Guides](/dynamics365/mixed-reality/guides/setup-step-one) pour Dynamics 365

#### <a name="guides-author"></a>Créateur Guides

1. Compte Azure AD
1. [Licence Dynamics 365 Guides](/dynamics365/mixed-reality/guides/requirements)
1. L’application Dynamics 365 Guides installée sur un PC ou sur HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (utilisé pour visualiser le tableau de bord analytique)
1. Rôle Auteur (pour la création de guides)
1. Connectivité réseau

#### <a name="guides-user"></a>Utilisateur Guides

1. Compte Azure AD
1. [Licence Dynamics 365 Guides](/dynamics365/mixed-reality/guides/requirements)
1. L’application Dynamics 365 Guides installée sur un appareil HoloLens
1. Rôle Opérateur (pour tester ou utiliser des guides)
1. Connectivité réseau
