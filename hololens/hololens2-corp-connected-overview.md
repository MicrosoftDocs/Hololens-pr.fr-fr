---
title: Guide de déploiement – connexion d’entreprise HoloLens 2 avec Dynamics 365 guides-vue d’ensemble
description: Découvrez comment inscrire des appareils HoloLens 2 avec des guides Dynamics 365 sur un réseau connecté à l’entreprise.
keywords: HoloLens, gestion, connecté à l’entreprise, Dynamics 365 guides, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: ee6c24f65e5990f1e84a71d86b24dd782cf9f4cc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397196"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guide de déploiement-connexion d’entreprise HoloLens 2 avec Dynamics 365 guides-vue d’ensemble

Ce guide aidera les professionnels de l’informatique à planifier et déployer des appareils Microsoft HoloLens 2 avec Dynamics 365 guides (guides) à leur organisation. Ce guide est parfait pour les pilotes et les déploiements de production. il est similaire au [scénario B : déployer à l’intérieur du Guide réseau de votre organisation](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) . Après avoir testé votre preuve de concept, utilisez ce guide pour progresser dans l’intégration de HoloLens à votre organisation.

Dans ce guide, nous allons vous montrer comment inscrire vos appareils dans la gestion des appareils existante, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser un guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la configuration des appareils. 

## <a name="prerequisites"></a>Prérequis

L’infrastructure suivante doit déjà être en place :
- Wi-Fi
    - Réseau d’entreprise interne avec accès aux ressources internes et accès limité à Internet ou aux services Cloud
    - Authentification par certificat basée sur les appareils.
- Jonction de Azure Active Directory (Azure AD) avec l’inscription automatique MDM ([Azure ad abonnement P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) requis)
- Gestion MDM (Intune)
    - Une ou plusieurs applications sont déployées via MDM.
- Réseau 
    - Certificats (SCEP ou PKCS)
    - Configuration du proxy
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
    - Un ou plusieurs utilisateurs par appareil sont pris en charge.
- Différents niveaux de configurations de verrouillage des appareils appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’une seule application.

## <a name="guides-licensing-and-requirements"></a>[Guides sur les licences et les exigences](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Compte Azure AD
- Dynamics 365 guides applications PC et HoloLens
- Abonnement à Dynamics 365 guides
    - Microsoft Dataverse (inclus)
    - Power Apps (inclus)
- Power BI Desktop
- Connectivité réseau

[![Diagramme du réseau connecté à l’entreprise, étape 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramme du réseau connecté à l’entreprise, étape 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Dans ce guide, vous allez :
### <a name="prepare"></a>Préparation
> [!div class="checklist"]
>- [En savoir plus sur les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [En savoir plus sur les Azure AD et en configurer une si vous n’en avez pas.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [En savoir plus sur la gestion des identités et sur la façon de configurer au mieux les comptes Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [En savoir plus sur MDM et configurer avec Intune si vous n’en avez pas déjà un.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarisez-vous avec le Wi-Fi basé sur les certificats.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarisez-vous avec le proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Découvrez comment vous pouvez utiliser des applications métier.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [En savoir plus sur la façon dont vous pouvez utiliser les guides pour votre organisation.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurer
> [!div class="checklist"]
>- [Comment créer des utilisateurs et des groupes.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Comment configurer l’inscription automatique.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Comment configurer des certificats et des profils Wi-Fi pour la connectivité des Wi-Fi d’entreprise.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Téléchargez et attribuez des packages d’application métier.](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurez les guides Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Comment configurer le mode plein écran (facultatif).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Comment configurer WDAC (facultatif).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Déployer
> [!div class="checklist"]
>-  [Valider l’inscription via Device et MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Validez Wi-Fi certificats.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Valider l’installation de l’application métier.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Validez les guides via la création et le fonctionnement.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Maintenance
> [!div class="checklist"]
>- [Mettez à jour HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Comment mettre à jour des guides (applications du Windows Store).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Comment mettre à jour des applications métier.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plan de développement.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Création d’un plan de support.](hololens2-corp-connected-maintain.md#support-plan)
>- [Options de gestion des appareils.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté d’entreprise-préparer](hololens2-corp-connected-prepare.md)
