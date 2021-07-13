---
title: Scénarios courants de déploiement
description: en savoir plus sur le déploiement et la gestion des HoloLens dans les environnements d’entreprise, notamment l’infrastructure, les Azure Active Directory et la gestion des appareils mobiles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635464"
---
# <a name="common-deployment-scenarios"></a>Scénarios courants de déploiement

## <a name="overview"></a>Vue d’ensemble

cette page fournit une vue d’ensemble de l’architecture pour trois scénarios courants lors du déploiement et de la gestion d’appareils Microsoft HoloLens 2 au sein de l’entreprise.

Souvent, la façon dont vous gérez vos appareils et l’accès aux ressources de votre organisation est largement déterminée par les facteurs déjà en place. en fonction de votre infrastructure existante, nous vous invitons à passer en revue le style de gestion des appareils (MDM) commun dans les scénarios suivants, puis à lire [planification HoloLens 2 déploiements dans un environnement commercial](hololens-core-components.md) pour déterminer quel scénario correspond à vos besoins. Trois guides correspondants peuvent également être utilisés lors de votre déploiement.


 1. [Guide de déploiement d’un environnement connecté au cloud](hololens2-cloud-connected-overview.md)
     1. [Guide de déploiement d’un environnement (clients externes) connecté au cloud](hololens2-deployment-guide.md)
 1. [Guide de déploiement d’un réseau d’entreprise](hololens2-corp-connected-overview.md)
 1. [Guide de déploiement d’un environnement sécurisé hors connexion](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scénario A : déployer sur des appareils connectés au Cloud

Ce scénario est comparable au déploiement d’appareils mobiles gérés au sein d’une entreprise. HoloLens 2 est déployée pour une utilisation principalement dans des environnements externes à un réseau d’entreprise. Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées par le biais du VPN. 
 * Configurations courantes de base
   * Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing.
   * Azure AD rejoindre avec l’inscription automatique de gestion des appareils mobiles (MDM)-gestion de MDM (Intune)
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Un ou plusieurs utilisateurs par appareil pris en charge
   * Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.
   * Une ou plusieurs applications sont déployées via MDM

* Défis courants
   * détermination des configurations MDM à appliquer au HoloLens 2 en fonction des exigences du scénario.

[![Diagramme ](images/deployment-guides-revised-scenario-a.png) de scénario](images/deployment-guides-revised-scenario-a.png#lightbox)

le guide de connexion du Cloud correspondant explique comment inscrire HoloLens 2 dans la gestion des appareils, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux peuvent utiliser immédiatement l’assistance à distance lors de la configuration de l’appareil. Utilisez le guide clients externes pour déployer des appareils sur un site distant à des fins d’utilisation externe à long terme ou à long terme.

> [!div class="nextstepaction"]
> [Guide de déploiement d’un environnement connecté au cloud](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Guide de déploiement d’un environnement (clients externes) connecté au cloud](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénario B : déployer à l’intérieur du réseau de votre organisation

ce scénario est identique à un déploiement classique pour la plupart des ordinateurs Windows 10. HoloLens 2 est déployée pour être utilisée principalement sur le réseau d’entreprise avec un accès aux ressources d’entreprise internes. Internet et les services de Cloud Computing peuvent être limités. 

 * Configurations courantes de base
   * Wi-Fi réseau est un réseau d’entreprise interne avec accès aux ressources internes et un accès limité à Internet ou aux services Cloud.
   * Joindre Azure AD avec l’inscription automatique MDM
   * Gestion MDM (Intune)
   * Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
     * Un ou plusieurs utilisateurs par appareil pris en charge
   * Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.
   * Une ou plusieurs applications sont déployées via MDM

 * Défis courants
   * HoloLens 2 ne prend pas en charge la jointure AD locale ou SCCM. Seule Azure AD rejoindre avec MDM. de nombreuses entreprises déploient toujours Windows 10 pc dans ce scénario comme des appareils joints à active directory, gérés par System Center Configuration Manager (SCCM), et peuvent ne pas disposer de l’infrastructure déployée/configurée pour la gestion des appareils Windows 10 internes via des solutions MDM basées sur le cloud.
   * comme HoloLens 2 est un appareil cloud en premier, il s’appuie fortement sur internet et les services connectés au cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion MDM, etc. lors de la connexion à un réseau d’entreprise, il est probable que les règles de Proxy/pare-feu doivent être ajustées pour permettre l’accès à HoloLens 2 et aux applications qui s’y exécutent.
   * La connectivité des Wi-Fi d’entreprise requiert généralement des certificats pour authentifier l’appareil ou l’utilisateur sur le réseau. l’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via MDM peuvent être difficiles à configurer.

[![Diagramme ](images/deployment-guides-revised-scenario-b-01-1.png) du scénario B1](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramme ](images/deployment-guides-revised-scenario-b-02-1.png) du scénario B2](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

le guide du réseau d’entreprise correspondant explique comment inscrire HoloLens 2 dans la gestion des appareils existante, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser un guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la configuration de l’appareil.

> [!div class="nextstepaction"]
> [Guide de déploiement d’un réseau d’entreprise](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénario C : déployer dans un environnement hors connexion sécurisé

Il s’agit d’un déploiement classique pour des emplacements hautement sécurisés ou confidentiels. HoloLens 2 est déployée pour être utilisée principalement hors connexion sans réseau ou accès internet. 
 * Configurations courantes de base
   * La connectivité Wi-Fi est désactivée. Si nécessaire, Ethernet via USB peut être activé pour la connectivité LAN.
   * Non géré.
   * Compte d’utilisateur local pour la connexion de l’appareil.
     * HoloLens 2 prend en charge un seul compte local.
   * Différents niveaux de configurations de verrouillage de périphérique sont appliqués par le biais de packages d’approvisionnement basés sur des cas d’utilisation spécifiques. Ces configurations sont généralement limitées en raison de la configuration requise de l’environnement sécurisé.
   * Une ou plusieurs applications sont déployées par le biais du package d’approvisionnement

 * Défis courants
   * Il existe un ensemble limité de configurations disponibles par le biais de packages de provisionnement
   * les services Cloud ne peuvent pas être utilisés, limitant ainsi les fonctionnalités HoloLens 2.
   * Plus grande surcharge administrative, car ces appareils doivent être configurés, configurés et mis à jour manuellement.

[![Diagramme sécurisé hors connexion 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

le guide sécurisé hors connexion correspondant fournit des instructions pour l’application d’un exemple de Package de provisionnement qui verrouille une HoloLens 2 pour une utilisation dans des environnements sécurisés.

> [!div class="nextstepaction"]
> [Guide de déploiement d’un environnement sécurisé hors connexion](hololens-common-scenarios-offline-secure.md)


