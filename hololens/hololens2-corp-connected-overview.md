---
title: Guide de déploiement – connexion d’entreprise HoloLens 2 avec Dynamics 365 Guides-vue d’ensemble
description: découvrez comment inscrire des appareils HoloLens 2 avec Dynamics 365 Guides sur un réseau connecté à l’entreprise.
keywords: HoloLens, gestion, connecté à l’entreprise, Dynamics 365 Guides, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190172"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guide de déploiement-connexion d’entreprise HoloLens 2 avec Dynamics 365 Guides-vue d’ensemble

ce guide aide les professionnels de l’informatique à planifier et à déployer Microsoft HoloLens 2 appareils avec Dynamics 365 Guides (Guides) dans leur organisation. Ce guide est parfait pour les pilotes et les déploiements de production. il est similaire au [scénario B : déployer à l’intérieur du Guide réseau de votre organisation](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) . après avoir testé votre preuve de concept, utilisez ce guide pour progresser avec l’intégration d’HoloLens à votre organisation.

Dans ce guide, nous allons vous montrer comment inscrire vos appareils dans la gestion des appareils existante, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser un guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la configuration des appareils. 

## <a name="prerequisites"></a>Prérequis

L’infrastructure suivante doit déjà être en place :
- Wi-Fi
    - Réseau d’entreprise interne avec accès aux ressources internes et accès limité à Internet ou aux services Cloud
    - Authentification par certificat basée sur les appareils.
- jonction de Azure Active Directory (Azure AD) avec l’inscription automatique MDM ([Azure AD abonnement P1](/azure/active-directory/fundamentals/active-directory-whatis) requis)
- Gestion MDM (Intune)
    - Une ou plusieurs applications sont déployées via MDM.
- Réseau 
    - Certificats (SCEP ou PKCS)
    - Configuration du proxy
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
    - Un ou plusieurs utilisateurs par appareil sont pris en charge.
- Différents niveaux de configurations de verrouillage des appareils appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’une seule application.

## <a name="guides-licensing-and-requirements"></a>[Guides sur les licences et les exigences](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Compte Azure AD
- Dynamics 365 Guides des applications PC et HoloLens
- abonnement Dynamics 365 Guides
    - Microsoft Dataverse (inclus)
    - Power Apps (inclus)
- Power BI Desktop
- Connectivité réseau

[![Diagramme du réseau connecté à l’entreprise, étape 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramme du réseau connecté à l’entreprise, étape 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Dans ce guide, vous allez :
### <a name="prepare"></a>Préparer
> [!div class="checklist"]
>- [en savoir plus sur les notions fondamentales de l’infrastructure pour les appareils HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
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
>- [Télécharger et affecter des packages d’applications métier.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 Guides d’installation.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
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
