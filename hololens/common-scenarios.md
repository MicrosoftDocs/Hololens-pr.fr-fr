---
title: Scénarios courants de déploiement d’infrastructure
description: Découvrez quelques-uns des scénarios de déploiement les plus courants en fonction de différents déploiements d’infrastructure pour la réalité mixte.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308787"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Vue d’ensemble des scénarios courants de déploiement d’infrastructure

Les informations suivantes fournissent une vue d’ensemble de l’architecture de haut niveau pour trois scénarios courants lors du déploiement et de la gestion d’appareils Microsoft HoloLens 2 au sein de l’entreprise. Souvent, la façon dont vous gérez vos appareils et comment accéder aux ressources de votre organisation est largement déterminée par les facteurs déjà en place. Sur la base de l’infrastructure existante, nous vous invitons à passer en revue le style de gestion des appareils communs dans les scénarios suivants et à essayer nos guides de déploiement dans le scénario correspondant à vos besoins.

## <a name="scenarios"></a>Scénarios

Le diagramme ci-dessous représente trois scénarios typiques pour les déploiements HoloLens 2.
![Diagramme de scénarios](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Scénario A : déployer sur des appareils Cloud Connect

HoloLens 2 est déployé pour une utilisation principalement dans des environnements externes à un réseau d’entreprise. Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées par le biais du VPN. Ce déploiement est similaire à celui des appareils mobiles gérés au sein d’une entreprise.
 * Configurations courantes de base
   * Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing.
   * Azure AD rejoindre avec l’inscription automatique de gestion des appareils mobiles (MDM)-gestion de MDM (Intune)
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Un ou plusieurs utilisateurs par appareil pris en charge
   * Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.
   * Une ou plusieurs applications sont déployées via MDM

* Défis courants
   * Détermination des configurations MDM à appliquer à HoloLens 2 en fonction des spécifications du scénario.

Pour obtenir un guide de déploiement similaire au scénario A, consultez notre guide pour le [Cloud Connected HoloLens 2 avec l’assistance à distance](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guide de déploiement – connexion Cloud HoloLens 2 avec assistance à distance](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénario B : déployer à l’intérieur du réseau de votre organisation

HoloLens 2 est déployé pour être principalement utilisé sur le réseau d’entreprise avec un accès aux ressources d’entreprise internes. Internet et les services de Cloud Computing peuvent être limités. Ce déploiement est un déploiement classique pour la plupart des PC Windows 10.

 * Configurations courantes de base
   * Wi-Fi réseau est un réseau d’entreprise interne avec accès aux ressources internes et un accès limité à Internet ou aux services Cloud.
   * Joindre Azure AD avec l’inscription automatique MDM
   * Gestion MDM (Intune)
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Un ou plusieurs utilisateurs par appareil pris en charge
   * Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.
   * Une ou plusieurs applications sont déployées via MDM

 * Défis courants
   * HoloLens 2 ne prend pas en charge la jointure AD locale ou SCCM. Seule Azure AD rejoindre avec MDM. De nombreuses entreprises déploient toujours des PC Windows 10 dans ce scénario en tant qu’appareils intégrés à Active Directory, gérés par System Center Configuration Manager (SCCM) et peuvent ne pas avoir l’infrastructure déployée/configurée pour la gestion des appareils Windows 10 internes via des solutions MDM basées sur le Cloud.
   * Étant donné que HoloLens 2 est un premier appareil Cloud, il s’appuie fortement sur Internet et les services connectés au Cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion MDM, etc. Lors de la connexion à un réseau d’entreprise, il est probable que les règles de proxy/pare-feu doivent être ajustées pour permettre l’accès à HoloLens 2 et aux applications qui s’y exécutent.
   * La connectivité des Wi-Fi d’entreprise requiert généralement des certificats pour authentifier l’appareil ou l’utilisateur sur le réseau. L’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via MDM peuvent être difficiles à configurer.

> [!div class="nextstepaction"]
> [Guide de déploiement – connexion d’entreprise HoloLens 2 avec Dynamics 365 guides](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénario C : déployer dans un environnement hors connexion sécurisé

HoloLens 2 est déployé pour une utilisation hors connexion principale sans accès réseau ou Internet. Il s’agit d’un déploiement classique pour des emplacements hautement sécurisés ou confidentiels.
 * Configurations courantes de base
   * La connectivité Wi-Fi est désactivée. Si nécessaire, Ethernet via USB peut être activé pour la connectivité LAN.
   * Non géré.
   * Compte d’utilisateur local pour la connexion de l’appareil.
     * HoloLens 2 ne prend en charge qu’un seul compte local.
   * Différents niveaux de configurations de verrouillage de périphérique sont appliqués par le biais de packages d’approvisionnement basés sur des cas d’utilisation spécifiques. Ces configurations sont généralement limitées en raison de la configuration requise de l’environnement sécurisé.
   * Une ou plusieurs applications sont déployées par le biais du package d’approvisionnement

 * Défis courants
   * Il existe un ensemble limité de configurations disponibles par le biais de packages de provisionnement
   * Les services Cloud ne peuvent pas être utilisés, limitant ainsi les fonctionnalités HoloLens 2.
   * Plus grande surcharge administrative, car ces appareils doivent être configurés, configurés et mis à jour manuellement.

Pour obtenir un guide de déploiement similaire à ce scénario, consultez notre [Guide de déploiement sécurisé en mode hors connexion](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guide de déploiement-sécurité HoloLens 2 en mode hors connexion](hololens-common-scenarios-offline-secure.md)
