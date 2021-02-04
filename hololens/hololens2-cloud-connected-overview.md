---
title: Vue d’ensemble de HoloLens 2 connecté au cloud avec Remote Assist
description: Découvrez comment inscrire des appareils HoloLens 2 sur un réseau connecté au cloud à l’aide de Dynamics 365 Remote Assist.
keywords: HoloLens, gestion, cloud connecté, Remote Assist, AAD, Azure AD, MDM, Gestion des appareils mobiles
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: 39424078a75feaf6a1e9b0547cb7d5de9847faf3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312632"
---
# Guide de déploiement du HoloLens2 connecté au cloud avec Remote Assist: vue d’ensemble

Ce guide aide les professionnels de l’informatique à planifier et à déployer des appareils Microsoft HoloLens 2 dans leur organisation avec l’objectif global d’avoir ces appareils connectés à votre organisation avec Dynamics 365 Remote Assist prêt à l’emploi. N’oubliez pas que cela servira de modèle pour les déploiements de preuve de concept dans votre organisation dans divers cas d’utilisation de HoloLens 2.

Au cours du guide, nous allons apprendre à inscrire vos appareils dans votre gestion des appareils, à appliquer des licences selon vos besoins et à vérifier que vos utilisateurs finaux peuvent immédiatement utiliser Remote Assist lors de la configuration de l’appareil. Pour ce faire, nous allons passer en détail les éléments d’infrastructure importants nécessaires à la mise en place et à l’exécution , en obtenant un déploiement à grande échelle avec HoloLens 2.

![Bannière connectée au cloud](./images/cloud-connected-hololens-large.png)

## Dans ce guide

Ce guide a pour objectif spécifique de définir l’assistance à distance au sein de votre organisation sur vos appareils HoloLens. Nous allons couvrir les nécessités nécessaires pour atteindre cet objectif. Afin de maintenir le focus sur cet objectif, certaines préparations et configurations seront préalablement sélectionnées afin d’optimiser ce déploiement ou de réduire les éléments nécessaires à la configuration. Vous serez informé de ces choix et pourrez personnaliser votre déploiement en fonction des besoins de votre entreprise.

Il s’agit d’une installation similaire au scénario A : déployer sur des appareils [de connexion au cloud,](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)ce qui est une bonne option pour de nombreux déploiements de preuve de concept, qui incluront :

- Wi-Fi réseaux sont généralement entièrement ouverts aux services Internet et Cloud
- Azure AD Join avec inscription automatique MDM - Gestion de la gestion des fonctionnalités de gestion des plateformes (Intune)
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
  - Un ou plusieurs utilisateurs par appareil pris en charge
- Différents niveaux de configurations de verrouillage d’appareil sont appliqués en fonction de cas d’utilisation spécifiques, de l’ouverture complète à la borne d’application unique

![Scénario connecté au cloud](./images/cloud-connected-guide-diagram.png)

Aucune autre restriction ou configuration d’appareil ne sera appliquée dans ce guide, mais nous vous encourageons à explorer ces options après avoir terminé.

## En savoir plus sur Remote Assist

Remote Assist permet la maintenance et la réparation collaboratives, l’inspection à distance, ainsi que le partage de connaissances et la formation. En connectant des personnes dans différents rôles et emplacements, un technicien utilisant Remote Assist peut se connecter à un collaborateur distant sur Microsoft Teams. Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre les problèmes en temps réel,&#39;ne se trouve pas au même emplacement. Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles sur l’espace physique du technicien&#39;afin qu’ils peuvent faire référence au schéma tout en travaillant à tête haute et mains libres sur HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Dans ce guide, vous allez :

Préparez :

> [!div class="checklist"]
> - [Découvrez les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [En savoir plus sur Azure AD et en configurer un si vous ne l&#39;pas.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Découvrez la gestion des identités et la meilleure façon de configurer les comptes Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [En savoir plus sur la gestion des mdm et configurer avec Intune si vous n'&#39;pas déjà en avoir un.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Découvrez les exigences de mise en réseau de Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Facultatif : VPN pour se connecter aux ressources organisationnelles](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurez :

> [!div class="checklist"]
> - [Comment créer des utilisateurs et des groupes.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Comment configurer l’inscription automatique dans Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Comment attribuer vos licences d’application.](hololens2-cloud-connected-configure.md#application-licenses)

Déployez :

> [!div class="checklist"]
> - [Configurer votre HoloLens 2 et valider l’inscription.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Validez que vous pouvez effectuer un appel d’assistance à distance.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Maintenez :

> [!div class="checklist"]
> - [Comment mettre à jour Remote Assist à l’aide de l’application Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [La réalisation d’un plan de support.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de développement.](hololens2-cloud-connected-maintain.md#development-plan)

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au cloud : préparer](hololens2-cloud-connected-prepare.md)

