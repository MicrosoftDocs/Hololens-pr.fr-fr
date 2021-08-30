---
title: Scénarios courants de déploiement
description: en savoir plus sur le déploiement et la gestion des HoloLens dans les environnements d’entreprise, notamment l’infrastructure, les Azure Active Directory et la gestion des appareils mobiles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189237"
---
# <a name="common-deployment-scenarios"></a>Scénarios courants de déploiement

## <a name="overview"></a>Vue d’ensemble

Il peut être difficile de savoir comment déployer un nouvel appareil lorsque vous l’essayez pour la première fois. ici, nous partageons différentes façons de déployer et de gérer des appareils Microsoft HoloLens 2 au sein de l’organisation.

Vous souhaitez déployer des solutions à grande échelle. Nous souhaitons vous y aider. Commençons par parler des étapes de déploiement des appareils, par conséquent des hologrammes, afin d’obtenir une valeur pour votre scénario de réalité mixte cible, que vous utilisiez D365 Remote Assist, guides ou une application Azure Mixed Reality Service activée que vous avez créée.

vous êtes peut-être un décideur d’entreprise, un professionnel de l’informatique ou une équipe d’innovation souhaitant adopter HoloLens au sein de votre organisation. au fur et à mesure que vous partez de la preuve de concept à un déploiement mis à l’échelle, nos guides de déploiement ont un sens de HoloLens au sein de votre infrastructure informatique, quelle que soit la taille ou la taille. Les scénarios de déploiement suivants sont les plus courants :

| Scénario |Utilisation | Points clés |
|---------|---------|---------|
| [Scénario A : appareils connectés au Cloud](hololens2-cloud-connected-overview.md) | Lorsque vous commencez votre déploiement pour la première fois, vous pouvez commencer petit et déployer un seul appareil connecté au Cloud juste pour voir le processus de base. | Les appareils sont connectés aux services Cloud et à Internet public. Cela est particulièrement adapté aux cas d’utilisation client, aux services de champ et à la preuve de concept.|
| [Scénario B : réseau de l’Organisation](hololens2-corp-connected-overview.md) | Lorsque vous déployez en production à grande échelle, vous devrez peut-être intégrer le réseau de votre propre organisation. | Les appareils sont connectés à un réseau Wi-Fi « d’entreprise ». Cela est particulièrement adapté aux utilisateurs internes, ou à l’utilisation au sein de l’environnement d’entreprise.|
| [Scénario C : environnement sécurisé hors connexion](hololens-common-scenarios-offline-secure.md) | Certains processus stratégiques ou certaines stratégies d’entreprise peuvent exiger l’utilisation d’environnements hors connexion. | Les appareils seront connectés à un réseau hautement restrictif ou seront de simples périphériques hors connexion. Cela convient particulièrement aux environnements hautement sécurisés ou aux restrictions de connectivité Internet dans les zones distantes. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scénario A : déployer sur des appareils connectés au Cloud

Ce scénario est comparable au déploiement d’appareils mobiles gérés au sein d’une entreprise. HoloLens 2 est déployée pour une utilisation principalement dans des environnements externes à un réseau d’entreprise. Les ressources d’entreprise ne sont pas accessibles ou peuvent être limitées par le biais du VPN.

[![Scénario d’un diagramme.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Quand l’utiliser

Tenez compte de ce modèle de déploiement pour :

* Déploiement de la preuve de concept, de pilotes et de services de terrain
* Déploiement de l' [assistance à distance](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Configurations courantes de base

* Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing
* Azure AD rejoindre avec l’inscription automatique de gestion des appareils mobiles (MDM)-gestion de MDM (Intune)
* Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
  * Un ou plusieurs utilisateurs par appareil pris en charge
* Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.
* Une ou plusieurs applications sont déployées via MDM

### <a name="common-challenges"></a>Défis courants

* détermination des configurations MDM à appliquer au HoloLens 2 en fonction des exigences du scénario

le guide de connexion du Cloud correspondant explique comment inscrire HoloLens 2 dans la gestion des appareils, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux peuvent utiliser immédiatement l’assistance à distance lors de la configuration de l’appareil.

> [!div class="nextstepaction"]
> [Guide de déploiement connecté au Cloud](hololens2-cloud-connected-overview.md)

Utilisez le guide clients externes pour déployer des appareils sur un site distant à des fins d’utilisation externe à long terme ou à long terme.

> [!div class="nextstepaction"]
> [Guide de déploiement du Cloud connecté (clients externes)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénario B : déployer à l’intérieur du réseau de votre organisation

ce scénario est identique à un déploiement classique pour la plupart des ordinateurs Windows 10. HoloLens 2 est déployée pour être utilisée principalement sur le réseau d’entreprise avec un accès aux ressources d’entreprise internes. Internet et les services de Cloud Computing peuvent être limités. 

[![Diagramme du scénario B1.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagramme du scénario B2.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Quand l’utiliser

Tenez compte de ce modèle de déploiement pour :

* Utilisateurs internes
* Déploiement à grande échelle (pilote et production) au sein de l’environnement d’entreprise

### <a name="basic-common-configurations"></a>Configurations courantes de base

* Wi-Fi réseau est un réseau d’entreprise interne avec accès aux ressources internes et un accès limité à Internet ou aux services Cloud.
* Joindre Azure AD avec l’inscription automatique MDM
* Gestion MDM (Intune)
* Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
  * Un ou plusieurs utilisateurs par appareil pris en charge
* Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique.
* Une ou plusieurs applications sont déployées via MDM

### <a name="common-challenges"></a>Défis courants

* HoloLens 2 ne prend pas en charge les System Center Configuration Manager ou SCCM (active directory join) locaux. Seule Azure AD rejoindre avec MDM. de nombreuses entreprises déploient toujours Windows 10 pc dans ce scénario comme des appareils joints à active directory locaux, gérés par SCCM, et peuvent ne pas disposer de l’infrastructure déployée/configurée pour la gestion des appareils Windows 10 internes via des solutions MDM basées sur le cloud.
* comme HoloLens 2 est un appareil cloud en premier, il s’appuie fortement sur internet et les services connectés au cloud pour l’authentification des utilisateurs, les mises à jour du système d’exploitation, la gestion MDM, etc. lors de la connexion à un réseau d’entreprise, il est probable que les règles de proxy/pare-feu doivent être ajustées pour permettre l’accès à HoloLens 2 et aux applications qui s’y exécutent.
* La connectivité des Wi-Fi d’entreprise requiert généralement des certificats pour authentifier l’appareil ou l’utilisateur sur le réseau. l’infrastructure ou les paramètres requis pour déployer des certificats sur des appareils Windows 10 via MDM peuvent être difficiles à configurer.

le guide connecté à l’entreprise correspondant indique comment inscrire HoloLens 2 dans la gestion des appareils existante, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser un guide Dynamics 365, ainsi que d’utiliser des applications métier personnalisées, après la configuration de l’appareil.

> [!div class="nextstepaction"]
> [Guide de déploiement de la connexion d’entreprise](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénario C : déployer dans un environnement hors connexion sécurisé

Il s’agit d’un déploiement classique pour des emplacements hautement sécurisés ou confidentiels. HoloLens 2 est déployée pour être utilisée principalement hors connexion sans réseau ou accès internet.

[![Diagramme sécurisé en mode hors connexion 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Quand l’utiliser

Tenez compte de ce modèle de déploiement pour :

* Environnements hautement sécurisés où les données doivent être conservées en interne
* « Expériences » où le public utilisera les appareils
* Problème de connectivité Internet dans la zone distante

### <a name="basic-common-configurations"></a>Configurations courantes de base

* La connectivité Wi-Fi est désactivée. Ethernet via USB peut être activé pour la connectivité LAN si nécessaire
* Non géré
* Compte d’utilisateur local pour la connexion des appareils
  * HoloLens 2 prend en charge un seul compte local
* Différents niveaux de configurations de verrouillage de périphérique sont appliqués par le biais de packages d’approvisionnement basés sur des cas d’utilisation spécifiques. Ces configurations sont généralement limitées en raison de la configuration requise de l’environnement sécurisé
* Une ou plusieurs applications sont déployées par le biais du package d’approvisionnement

### <a name="common-challenges"></a>Défis courants

* Il existe un ensemble limité de configurations disponibles par le biais de packages de provisionnement
* les services Cloud ne peuvent pas être utilisés, limitant ainsi les fonctionnalités HoloLens 2.
* Plus grande surcharge administrative, car ces appareils doivent être configurés, configurés et mis à jour manuellement.

le guide sécurisé hors connexion correspondant fournit des instructions pour l’application d’un exemple de Package de provisionnement qui verrouille une HoloLens 2 pour une utilisation dans des environnements sécurisés.

> [!div class="nextstepaction"]
> [Guide de déploiement d’un environnement sécurisé hors connexion](hololens-common-scenarios-offline-secure.md)
