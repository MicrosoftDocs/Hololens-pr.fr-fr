---
title: Scénarios courants de déploiement d’infrastructure
description: Découvrez certains des scénarios de déploiement les plus courants basés sur différents déploiements d’infrastructure pour la réalité mixte.
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283625"
---
# Vue d’ensemble des scénarios de déploiement d’infrastructure courants

Ces informations fournissent une vue d’ensemble de l’architecture de haut niveau pour trois scénarios courants lors du déploiement et de la gestion d’appareils Microsoft HoloLens 2 au sein de l’entreprise. Souvent, la façon dont vous gérez vos appareils et comment accéder aux ressources de votre organisation est en grande partie déterminée par des facteurs déjà en place. En fonction de l’infrastructure existante, nous vous invitons à passer en revue le style de gestion des appareils commun dans les scénarios suivants et à tester nos guides de déploiement dans le scénario correspondant à vos besoins.

## Scénarios

Le diagramme ci-dessous représente trois scénarios classiques pour les déploiements HoloLens 2.
![Diagramme des scénarios](images/scenarios.jpg)

### Scénario A : Déployer sur des appareils de connexion au cloud

HoloLens 2 est déployé pour être utilisé principalement dans des environnements externes à un réseau d’entreprise. Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées via vpn. Ce déploiement est similaire aux appareils mobiles gérés au sein d’une entreprise.
 * Configurations courantes de base
   * Wi-Fi réseaux sont généralement entièrement ouverts aux services Internet et Cloud.
   * Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Prise en charge d’un ou de plusieurs utilisateurs par appareil
   * Différents niveaux de configurations de verrouillage d’appareil sont appliqués en fonction de cas d’utilisation spécifiques, de l’ouverture complète à la borne d’application unique.
   * Une ou plusieurs applications sont déployées via la gestion des applications mobiles

* Défis courants
   * Déterminer les configurations MDM à appliquer à HoloLens 2 en fonction des exigences du scénario.

Pour obtenir un guide de déploiement semblable au scénario A examinez notre guide pour [HoloLens 2](hololens2-cloud-connected-overview.md)connecté au cloud avec Remote Assist .

> [!div class="nextstepaction"]
> [Guide de déploiement – HoloLens 2 connecté au cloud avec Remote Assist](hololens2-cloud-connected-overview.md)

### Scénario B : déployer à l’intérieur du réseau de votre organisation

HoloLens 2 est déployé pour être utilisé principalement sur le réseau d’entreprise avec accès aux ressources d’entreprise internes. Les services Internet et cloud peuvent être limités. Ce déploiement est un déploiement classique pour la plupart des PC Windows 10.

 * Configurations courantes de base
   * Wi-Fi réseau est un réseau d’entreprise interne ayant accès à des ressources internes et un accès limité aux services Internet ou Cloud.
   * Azure AD Join avec inscription automatique MDM
   * Gestion de la gestion des mdm (Intune)
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Prise en charge d’un ou de plusieurs utilisateurs par appareil
   * Différents niveaux de configurations de verrouillage d’appareil sont appliqués en fonction de cas d’utilisation spécifiques, de l’ouverture complète à la borne d’application unique.
   * Une ou plusieurs applications sont déployées via la gestion des applications mobiles

 * Défis courants
   * HoloLens 2 ne prend pas en charge la jointre AD sur site ou SCCM. Seule azure AD rejoint la gestion des fonctionnalités de gestion des mdm. Aujourd’hui, de nombreuses entreprises déploient toujours des PC Windows 10 dans ce scénario, comme des appareils joints à AD sur site, gérés par System Center Configuration Manager (SCCM) et peuvent ne pas avoir déployé/configuré l’infrastructure pour la gestion des appareils Windows 10 internes via des solutions de gestion des périphériques mobiles basées sur le cloud.
   * HoloLens 2 étant un premier appareil cloud, il s’appuie largement sur les services connectés à Internet et au cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion des appareils de gestion des périphériques multifacteurs, etc. Lors de la connexion à un réseau d’entreprise, les règles de proxy/pare-feu devront probablement être ajustées pour activer l’accès pour HoloLens 2 et les applications qui s’exécutent dessus.
   * La connectivité Wi-Fi entreprise nécessite généralement des certificats pour authentifier l’appareil ou l’utilisateur sur le réseau. La configuration de l’infrastructure ou des paramètres requis pour déployer des certificats sur des appareils Windows 10 via la gestion des périphériques mobiles peut être difficile à configurer.

### Scénario C : Déployer dans un environnement hors connexion sécurisé

HoloLens 2 est déployé pour une utilisation principalement hors connexion sans accès réseau ou Internet. Il s’agit d’un déploiement classique pour les emplacements hautement sécurisés ou confidentiels.
 * Configurations courantes de base
   * Wi-Fi connectivité est désactivée. Ethernet via USB peut être activé pour la connectivité LAN si nécessaire.
   * Non géré.
   * Compte d’utilisateur local pour la connectez-vous à l’appareil.
     * HoloLens 2 prend en charge un seul compte local.
   * Différents niveaux de configurations de verrouillage d’appareil sont appliqués via des packages d’approvisionnement basés sur des cas d’utilisation spécifiques. Ces configurations sont généralement restreintes en raison des exigences d’environnement sécurisé.
   * Une ou plusieurs applications sont déployées via le package d’approvisionnement

 * Défis courants
   * Un ensemble limité de configurations est disponible via les packages d’approvisionnement
   * Les services cloud ne peuvent pas être utilisés, ce qui limite les fonctionnalités HoloLens 2.
   * Charge administrative plus élevée étant donné que ces appareils doivent être configurés, configurés et mis à jour manuellement.

Pour consulter un guide de déploiement semblable à ce scénario, examinez notre Guide de déploiement sécurisé [hors connexion.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Guide de déploiement – HoloLens 2 sécurisé hors connexion](hololens-common-scenarios-offline-secure.md)
