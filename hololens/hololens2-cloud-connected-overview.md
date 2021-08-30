---
title: vue d’ensemble de la connexion Cloud HoloLens 2 avec l’assistance à distance
description: découvrez comment inscrire des appareils HoloLens 2 sur un réseau connecté au Cloud à l’aide de Dynamics 365 Remote Assist.
keywords: HoloLens, gestion, cloud connecté, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189645"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guide de déploiement – Cloud connected HoloLens 2 avec l’assistance à distance – vue d’ensemble

ce guide aide les professionnels de l’informatique à planifier et à déployer des appareils Microsoft HoloLens 2 avec l’assistance à distance pour leur organisation. cela servira de modèle pour les déploiements de preuve de concept dans votre organisation dans plusieurs cas d’utilisation HoloLens 2. Le programme d’installation est similaire au [scénario A : déployer sur des appareils Cloud Connect](common-scenarios.md#scenario-a). 

Dans le cadre de ce guide, nous allons aborder l’inscription de vos appareils dans la gestion des appareils, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser immédiatement l’assistance à distance lors de la configuration de l’appareil. Pour ce faire, nous allons passer en revue les éléments importants de l’infrastructure nécessaire à la configuration et à l’exécution, ce qui permet un déploiement à grande échelle avec HoloLens 2. Aucune autre restriction ou configuration d’appareil ne sera appliquée dans ce guide. Toutefois, nous vous encourageons à explorer ces options après avoir terminé.

## <a name="prerequisites"></a>Prérequis

L’infrastructure suivante doit être en place pour déployer le HoloLens 2. Si ce n’est pas le cas, la configuration d’Azure et d’Intune est incluse dans ce guide :

Il s’agit d’une configuration similaire au [scénario a : déploiement sur des appareils Cloud Connect](/hololens/common-scenarios#scenario-a), qui est une bonne option pour de nombreux déploiements de preuve de concept, à savoir :

- Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing
- Azure AD rejoindre avec l’inscription automatique MDM — gérée par MDM (Intune)
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
    - Un ou plusieurs utilisateurs par appareil sont pris en charge.

:::image type="content" alt-text="Scénario connecté au Cloud." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>En savoir plus sur l’assistance à distance

L’assistance à distance permet la maintenance et la réparation collaboratives, l’inspection à distance, ainsi que le partage des connaissances et la formation. En connectant des personnes à des rôles et des emplacements différents, un technicien qui utilise l’assistance à distance peut se connecter à un collaborateur distant sur Microsoft Teams. Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre les problèmes en temps réel, même lorsqu’ils ne se trouvent pas au même emplacement. Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles à l’espace physique du technicien, afin qu’ils puissent faire référence au schéma tout en récapitulant les mains et les mains sur HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licences et exigences de l’assistance à distance

- Compte Azure AD (nécessaire pour l’achat de l’abonnement et l’attribution de licences)
- [Abonnement Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Essai Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Utilisateur Remote Assist Dynamics 365

- Licence Remote Assist
- Connectivité réseau

#### <a name="microsoft-teams-user"></a>Utilisateur Microsoft Teams

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Connectivité réseau

Si vous prévoyez d’implémenter ce [scénario multilocataire](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), vous pouvez avoir besoin d’une licence Cloisonnement de l’information. pour déterminer si une licence de barrière des informations est requise, consultez [fournisseurs et clients utiliser les fonctionnalités de Dynamics 365 Remote Assist complètes](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).

## <a name="in-this-guide-you-will"></a>Dans ce guide, vous allez :

Préparation :

> [!div class="checklist"]
> - [en savoir plus sur les notions fondamentales de l’infrastructure pour les appareils HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [En savoir plus sur les Azure AD et en configurer une si vous ne l’avez pas&#39;.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [En savoir plus sur la gestion des identités et sur la façon de configurer au mieux les comptes Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Apprenez-en davantage sur MDM et configurez avec Intune si&#39;vous n’avez pas déjà un prêt.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [En savoir plus sur les exigences de mise en réseau de l’assistance à distance.](hololens2-cloud-connected-prepare.md#network)
> - [Éventuellement : VPN pour se connecter aux ressources de l’Organisation](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurer :

> [!div class="checklist"]
> - [Comment créer des utilisateurs et des groupes.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Comment configurer l’inscription automatique dans Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Comment attribuer vos licences d’application.](hololens2-cloud-connected-configure.md#application-licenses)

Deploy :

> [!div class="checklist"]
> - [configurez votre HoloLens 2 et validez l’inscription.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valider, vous pouvez effectuer un appel d’assistance à distance.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mise à jour :

> [!div class="checklist"]
> - [comment mettre à jour l’assistance à distance à l’aide de l’application Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Création d’un plan de support.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de développement.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au Cloud-préparer](hololens2-cloud-connected-prepare.md)

