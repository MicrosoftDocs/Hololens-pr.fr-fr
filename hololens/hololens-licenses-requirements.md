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
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640274"
---
# <a name="license-requirements"></a>Conditions de licence :

## <a name="hololens-2-device-managed"></a>Appareil HoloLens 2 (managé)

[Compte Azure AD](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) ne peut pas être utilisé pour gérer les appareils HoloLens.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ou un autre MDM.
- [Windows Autopilot pour HoloLens 2](hololens2-autopilot.md) : simplifie l’expérience de provisionnement pour les administrateurs informatiques et les utilisateurs finaux. Les administrateurs informatiques peuvent préconfigurer des stratégies HoloLens 2 et, lors du premier démarrage, les appareils seront déployés dans un état prêt à une utilisation professionnelle sans aucune interaction de l’utilisateur. 

  > [!NOTE]
  > Windows AutoPilot nécessite la configuration préalable d’[Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) et de l’[inscription automatique](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) pour le flux Autopilot et le déploiement des appareils avec peu d’interaction. 

### <a name="business-use-case"></a>Cas d’usage professionnel : 

- [Scénario de déploiement A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - preuve de concept ou déploiement pilote.

- [Scénario de déploiement B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - déploiement à grande échelle.

## <a name="hololens-2-device-only-non-managed"></a>Appareil HoloLens 2 uniquement (non managé)

Si vous utilisez un compte Microsoft (MSA) ou un compte local, aucune licence supplémentaire n’est nécessaire pour ces comptes.

[Compte local](/windows/security/identity-protection/access-control/local-accounts)

- Ce compte doit être préalablement [provisionné](hololens-provisioning.md#provisioning-package-hololens-wizard) avec le Concepteur de configuration Windows.

[Compte Microsoft](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Les utilisateurs multiples ne sont pas pris en charge pour un appareil utilisant un de ces comptes.

### <a name="business-use-case"></a>Cas d’usage professionnel : 

- [Scénario de déploiement C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) : déploiement hors connexion ou sécurisé.
 
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

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Connectivité réseau

Si vous prévoyez d’implémenter ce [scénario multilocataire](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), vous pouvez avoir besoin d’une licence Cloisonnement de l’information. Consultez [cet article](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) pour déterminer si une licence Cloisonnement de l’information est nécessaire.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Admin

- Compte Azure AD (nécessaire pour l’achat de l’abonnement et l’attribution de licences)
- [Abonnement ou essai gratuit Guides](/dynamics365/mixed-reality/guides/setup-step-one) pour Dynamics 365

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
