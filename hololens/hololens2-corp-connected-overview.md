---
title: Guide de déploiement – HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Vue d’ensemble
description: Découvrez comment inscrire des appareils HoloLens 2 à l’aide de guides Dynamics 365 sur un réseau connecté d’entreprise.
keywords: HoloLens, gestion, connecté à l’entreprise, guides Dynamics 365, AAD, Azure AD, GESTION DES PÉRIPHÉRIQUES MOBILES, Gestion des appareils mobiles
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448543"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guide de déploiement - HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Vue d’ensemble

Ce guide aidera les professionnels de l’informatique à planifier et déployer des appareils Microsoft HoloLens 2 à l’aide de guides (Guides) Dynamics 365 dans leur organisation. Ce guide est idéal pour les déploiements pilotes et de production et est semblable au scénario B : Déployer à [l’intérieur](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) du guide réseau de votre organisation. Après avoir testé votre preuve de concept, utilisez ce guide pour aller de l’avant avec l’intégration de HoloLens dans votre organisation.

Dans ce guide, nous allons apprendre à inscrire vos appareils dans votre gestion d’appareils existante, à appliquer des licences selon vos besoins et à vérifier que vos utilisateurs finaux sont en mesure d’utiliser un Guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la mise en place de l’appareil. 

## <a name="prerequisites"></a>Prérequis

L’infrastructure suivante doit déjà être en place :
- Wi-Fi
    - Réseau d’entreprise interne avec accès aux ressources internes et accès limité aux services Internet ou Cloud
    - Authentification de certificat basée sur l’appareil.
- Joindre Azure Active Directory (Azure AD) avec inscription automatique MDM[(abonnement Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) requis)
- Gestion de la gestion des mdm (Intune)
    - Une ou plusieurs applications sont déployées via la gestion des applications mobiles.
- Network 
    - Certificats (SCEP ou PKCS)
    - Configuration du proxy
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
    - Un ou plusieurs utilisateurs par appareil sont pris en charge.
- Différents niveaux de configurations de verrouillage d’appareil appliqués en fonction de cas d’utilisation spécifiques, de l’ouverture complète à la borne d’application unique.

## [<a name="guides-licensing-and-requirements"></a>Guide des licences et des conditions requises](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Compte Azure AD
- Dynamics 365 Guides applications PC and HoloLens
- Abonnement aux guides Dynamics 365
    - Microsoft Dataverse (inclus)
    - Power Apps (inclus)
- Power BI Desktop
- Connectivité réseau

![Diagramme réseau connecté à l’entreprise](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Étapes de déploiement
### <a name="prepare"></a>Préparation
> [!div class="checklist"]
>- [Découvrez les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [En savoir plus sur Azure AD et en configurer un si vous ne l’avez pas.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Découvrez la gestion des identités et la meilleure façon de configurer les comptes Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [En savoir plus sur la gestion des mdm et la configurer avec Intune si vous n’en avez pas déjà un.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarisez-vous avec le Wi-Fi basé sur les certificats.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarisez-vous avec le proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Comprendre comment vous pouvez utiliser les applications métier.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [En savoir plus sur la façon dont vous pouvez utiliser les Guides pour votre organisation.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurer
> [!div class="checklist"]
>- [Comment créer des utilisateurs et des groupes.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Comment configurer l’inscription automatique.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Comment configurer des certificats Wi-Fi et des profils pour la connectivité Wi-Fi entreprise.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Charger et affecter des packages d’application métier.](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurer les guides Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Comment configurer le mode plein écran (facultatif).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Comment configurer WDAC (facultatif).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Déployer
> [!div class="checklist"]
>-  [Valider l’inscription via l’appareil et la gestion des périphériques de gestion des périphériques.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Validez Wi-Fi certificats.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Valider l’installation de l’application LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Valider les guides via la authoring et le fonctionnement.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Maintenir
> [!div class="checklist"]
>- [Mettez à jour HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Comment mettre à jour les guides (stocker des applications).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Comment mettre à jour les applications LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plan de développement.](hololens2-corp-connected-maintain.md#development-plan) 
>- [La réalisation d’un plan de support.](hololens2-corp-connected-maintain.md#support-plan)
>- [Options de gestion des appareils.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté à l’entreprise : préparer](hololens2-corp-connected-prepare.md)
