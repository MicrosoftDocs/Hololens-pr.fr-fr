---
title: Guide de déploiement – technologie HoloLens 2 du Cloud connecté à Remote Assist-vue d’ensemble
description: Inscrire des appareils HoloLens sur un réseau connecté sur le Cloud
keywords: HoloLens, gestion, Cloud connecté, assistance à distance, AAD, Azure AD, GPM, gestion des appareils mobiles
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
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253181"
---
# Guide de déploiement – connexion HoloLens 2 du Cloud connecté à distance-vue d’ensemble

Ce guide est destiné à aider les informaticiens à planifier et à déployer des appareils Microsoft HoloLens 2 dans leur organisation en ayant la possibilité de se connecter à votre organisation à l’aide de Dynamics 365 Remote Assist. Gardez à l’esprit qu’il s’agit d’un modèle pour les déploiements de la preuve de concept au sein de votre organisation dans différentes circonstances d’utilisation HoloLens 2.

Au cours de ce guide, nous allons vous expliquer comment inscrire vos périphériques dans le cadre de la gestion de vos appareils, appliquer des licences si nécessaire et vérifier que vos utilisateurs finaux peuvent utiliser immédiatement l’assistance à distance lors de l’installation de l’appareil. Pour ce faire, nous allons examiner les éléments d’infrastructure importants nécessaires à la configuration et à l’exécution de la mise à niveau vers HoloLens 2.

## Dans ce guide

Ce guide a pour but spécifique de configurer l’assistance à distance au sein de votre organisation sur vos appareils HoloLens. Nous allons aborder les reversions nécessaires pour atteindre cet objectif. Pour pouvoir mettre le focus sur cet objectif, certaines préparations et configurations sont présélectionnées afin d’optimiser le déploiement ou de réduire les éléments nécessaires à la configuration. Vous serez averti de ces choix et pourrez personnaliser votre déploiement en fonction de vos besoins professionnels.

Il s’agit d’une configuration similaire au [scénario a: déploiement vers des appareils de connexion Cloud](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), qui est une bonne option pour de nombreux déploiements de la preuve de concept, qui incluent:

- Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services Cloud.
- Accès Azure AD à l’inscription automatique de la gestion des périphériques mobiles (GPM)
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
  - Un ou plusieurs utilisateurs par appareil pris en charge
- Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.

![Scénario connecté dans le Cloud](./images/cloud-connected-deployment-chart.png)

Il n’est pas possible d’appliquer d’autres restrictions ou configurations d’appareils à ce guide, mais nous vous encourageons à découvrir ces options après la fin.

## En savoir plus sur l’assistance à distance

L’assistance à distance permet d’apporter des opérations de maintenance et de réparation, d’inspection à distance et de partage de connaissances et de formation. En connectant des personnes dans différents rôles et emplacements, un technicien utilisant l’assistance à distance peut communiquer avec un collaborateur distant sur Microsoft Teams. Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre des problèmes en temps réel, même s’ils ne sont pas&#39;t au même endroit. Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles que le technicien&#39;de l’espace physique pour s’y référer tout en travaillant en mains libres sur HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Ce guide vous permet d’effectuer les opérations suivantes:

Prévenir

> [!div class="checklist"]
> - [Découvrez les notions fondamentales sur l’infrastructure des appareils HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [En savoir plus sur Azure AD et en configurer un si vous n’en avez pas&#39;.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Apprenez-en davantage sur la gestion des identités et la configuration optimale des comptes Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Apprenez-en davantage sur la gestion des périphériques mobiles et configurez avec Intune si vous n’avez pas encore l’un de ces&#39;.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [En savoir plus sur la configuration requise en réseau d’assistance à distance.](hololens2-cloud-connected-prepare.md#network)
> - [Si vous le souhaitez, VPN pour vous connecter aux ressources de l’Organisation](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configur

> [!div class="checklist"]
> - [Découvrez comment créer des utilisateurs et des groupes.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Comment configurer l’inscription automatique dans Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Comment affecter des licences d’application.](hololens2-cloud-connected-configure.md#application-licenses)

Deploy

> [!div class="checklist"]
> - [Configurez votre HoloLens 2 et validez l’inscription.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valider vous pouvez effectuer un appel d’assistance à distance.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Maintiendra

> [!div class="checklist"]
> - [Comment mettre à jour l’assistance à distance à l’aide de l’application Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Élaboration d’un plan de support.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de développement.](hololens2-cloud-connected-maintain.md#development-plan)

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté dans le Cloud-préparer](hololens2-cloud-connected-prepare.md)

