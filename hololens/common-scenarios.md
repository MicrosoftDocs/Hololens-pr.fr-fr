---
title: Scénarios courants de déploiement d’infrastructure
description: Quelques scénarios de déploiement courants basés sur différentes infrastructures communes
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253071"
---
# Présentation courante des scénarios de déploiement d’infrastructure

Les informations suivantes fournissent une présentation de l’architecture de haut niveau pour trois scénarios courants lors du déploiement et de la gestion des appareils Microsoft HoloLens 2 au sein de l’entreprise. Le mode de gestion de vos appareils et l’accès aux ressources de votre organisation sont principalement déterminés en fonction de facteurs déjà en vigueur. Sur la base de l’infrastructure existante, nous vous invitons à passer en revue le style de gestion commune des appareils dans les scénarios suivants et à tester nos guides de déploiement dans le scénario correspondant à vos besoins.

## Scénarios

Le diagramme ci-dessous représente trois scénarios typiques de déploiements HoloLens 2.
![Diagramme de scénarios](images/scenarios.jpg)

### Scénario A: déploiement vers des appareils de connexion dans le Cloud

HoloLens 2 est déployé pour une utilisation essentiellement dans les environnements externes à un réseau d’entreprise. Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées via un réseau VPN. Ce déploiement est semblable aux appareils mobiles gérés au sein d’une entreprise.
 * Configurations courantes de base
   * En général, les réseaux Wi-Fi sont entièrement ouverts sur Internet et les services Cloud.
   * Accès Azure AD à l’inscription automatique de la gestion des périphériques mobiles (GPM)
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Un ou plusieurs utilisateurs par appareil pris en charge
   * Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.
   * Une ou plusieurs applications sont déployées via la gestion des périphériques mobiles

* Défis courants
   * Détermination des configurations de la gestion des périphériques mobiles à appliquer à HoloLens 2 en fonction de la configuration requise pour les scénarios.

Pour un guide de déploiement similaire au scénario A, consultez notre guide pour le [Cloud connecté à l’assistance à distance](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guide de déploiement – technologie HoloLens 2 dans le Cloud connecté à l’assistance à distance](hololens2-cloud-connected-overview.md)

### Scénario B: déploiement au sein du réseau de votre organisation

HoloLens 2 est déployé pour une utilisation essentiellement sur le réseau d’entreprise avec l’accès aux ressources internes de l’entreprise. Les services Internet et Cloud risquent d’être limités. Ce déploiement est un déploiement standard pour la plupart des PC Windows 10.

 * Configurations courantes de base
   * Wi-Fi réseau est un réseau d’entreprise interne avec accès à des ressources internes et accès limité aux services Internet ou Cloud.
   * Accès Azure AD avec l’inscription automatique GPM
   * Gestion de la gestion des périphériques mobiles
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Un ou plusieurs utilisateurs par appareil pris en charge
   * Différents niveaux de configuration de verrouillage de l’appareil sont appliqués en fonction de cas d’utilisation spécifiques, d’une ouverture complète à une borne d’application unique.
   * Une ou plusieurs applications sont déployées via la gestion des périphériques mobiles

 * Défis courants
   * HoloLens 2 ne prend pas en charge les jointures publicitaire locales ou SCCM. Uniquement Azure AD Join avec la gestion des périphériques mobiles. Dans de nombreux cas, les entreprises déploient actuellement des PC Windows 10 dans le cadre de ce scénario, en ce qui concerne les appareils joints d’annonces publicitaires, gérés par System Center Configuration Manager (SCCM) et ne disposent pas de l’infrastructure déployée/configurée pour gérer les appareils Windows 10 internes via des solutions de gestion du Cloud Computing.
   * Comme HoloLens 2 est un premier appareil Cloud, il repose fortement sur Internet et les services connectés au Cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion de la gestion des périphériques mobiles, etc. Lorsque vous vous connectez à un réseau d’entreprise, les règles de proxy et de pare-feu doivent être ajustées afin d’activer l’accès à HoloLens 2 et aux applications qui s’exécutent sur celle-ci.
   * La connectivité entreprise Wi-Fi nécessite généralement des certificats pour authentifier l’appareil ou l’utilisateur auprès du réseau. L’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via la gestion des périphériques mobiles peuvent être difficiles à configurer.

### Scénario C: déploiement dans un environnement hors connexion sécurisé

HoloLens 2 est déployé pour une utilisation essentiellement hors connexion sans réseau ou accès Internet. Il s’agit d’un déploiement standard pour des emplacements particulièrement sécurisés ou confidentiels.
 * Configurations courantes de base
   * Wi-Fi connectivité est désactivée. Ethernet par le biais du bus USB, si nécessaire, la connectivité LAN est activée.
   * Non géré.
   * Compte d’utilisateur local pour la connexion de l’appareil.
     * HoloLens 2 ne prend en charge qu’un seul compte local.
   * Différents niveaux de configuration de verrouillage de l’appareil sont appliqués via des packages de mise en service en fonction de cas d’utilisation spécifiques. Ces configurations sont généralement très limitées en raison de la configuration requise pour l’environnement sécurisé.
   * Une ou plusieurs applications sont déployées via le package de mise à service

 * Défis courants
   * Un ensemble de configurations limité est disponible via les packages de mise en service
   * Les services Cloud ne peuvent pas être utilisés, ce qui a pour effet de limiter les fonctionnalités HoloLens 2.
   * Augmentation des frais d’administration par le biais de ces périphériques, configurés et mis à jour manuellement.

Pour un guide de déploiement similaire à celui-ci, consultez notre [Guide de déploiement sécurisé hors connexion](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guide de déploiement – sécurité HoloLens 2 hors connexion](hololens-common-scenarios-offline-secure.md)
