---
title: Planification du déploiement de HoloLens 2 dans un environnement commercial
description: Découvrez les principaux besoins en matière de déploiement et de gestion de HoloLens dans les environnements d’entreprise, y compris l’infrastructure, Azure Active Directory et la gestion des appareils mobiles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961432"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planification du déploiement de HoloLens 2 dans un environnement commercial

## <a name="overview"></a>Vue d’ensemble
> [!NOTE]
> Cette vue d’ensemble est destinée à aider les professionnels de l’informatique à comprendre les considérations relatives au déploiement et à la gestion des appareils Microsoft HoloLens 2 au sein d’une organisation. Pour les utilisateurs finaux d’appareils, consultez [les principes de base](hololens2-setup.md) pour commencer.

HoloLens 2 s’exécute sur Windows 10 holographique, qui offre aux organisations des technologies de gestion des applications et des appareils mobiles robustes, flexibles et intégrées. Windows 10 holographique prend en charge la gestion du cycle de vie des appareils de bout en bout pour permettre aux entreprises de contrôler leurs appareils, leurs données et leurs applications. HoloLens 2 peut facilement être incorporé dans des pratiques de cycle de vie standard, de l’inscription des appareils, de la configuration et de la gestion des applications à la maintenance et à la retraite à l’aide d’une solution complète de gestion des appareils mobiles.

Les étapes suivantes peuvent vous guider tout au long du processus d’adoption de HoloLens 2 au sein de votre organisation.

| | |
|--|--|
| ![Étape 1](images/1green.png)| <br/> **[Scénarios de déploiement courants](hololens-requirements.md)**: comprenez les scénarios de déploiement et explorez les principaux composants nécessaires au déploiement d’appareils HoloLens 2. |
| ![Étape 2](images/2green.png)| <br/> **[Préparer](#prepare)**: Familiarisez-vous avec les principes fondamentaux de l’infrastructure requis pour HoloLens 2. |
| ![Étape 3 :](images/3green.png) | <br/> **[Configurer](#configure)**: Découvrez comment configurer vos composants essentiels pour un déploiement basé sur le Cloud. |
| ![Étape 4](images/4green.png) | <br/> **[Déploiement](#deploy)**: Découvrez comment déployer vos appareils et distribuer vos applications de manière sécurisée et efficace. |
| ![Étape 5](images/5green.png) | <br/> **[Tenir à jour](#maintain)**: Découvrez ce qui est nécessaire pour maintenir correctement l’état de vos appareils HoloLens 2 et garantir la conformité avec la stratégie d’entreprise. |

## <a name="prepare"></a>Préparer

Découvrez les services d’infrastructure essentiels requis pour prendre en charge l’ensemble complet des fonctionnalités HoloLens 2. 

| Composant | Description |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Fournit la gestion des identités et des accès pour HoloLens 2  |
| [Gestion des appareils mobiles](hololens-mdm-configure.md)| Gère les appareils HoloLens 2 connectés à votre locataire  |
| [Réseau Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi est disponible et les appareils peuvent être connectés à Internet  |

## <a name="configure"></a>Configurer

Utilisez Intune et AutoPilot comme des solutions à faible Touch pour l’inscription et la configuration de HoloLens 2 sur le client Azure AD de votre organisation et la gestion des appareils mobiles.

| Composant | Description |
|-----------|------------|
| [Inscription automatique](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Après la connexion initiale, les appareils s’inscrivent automatiquement auprès d’Azure AD et s’inscrivent dans MDM  |
| [Licences d’application](hololens2-cloud-connected-configure.md#application-licenses)| Peut être appliqué à des utilisateurs, à des groupes d’utilisateurs ou à des groupes d’appareils  |
| [Utilisateurs et groupes Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Permet d’attribuer des configurations et des licences pour le HoloLens 2  |

## <a name="deploy"></a>Déployer

Distribuez vos appareils HoloLens 2 et validez leur configuration. 

| Composant | Description |
|-----------|------------|
| [Validation de l’inscription](hololens2-corp-connected-deploy.md#enrollment-validation) | Valider que l’appareil n’a Azure AD joint à partir des paramètres ou du portail Azure |
| [Validation de certificat](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Vérifier les paramètres et vérifier qu’ils ont été distribués correctement |
| [Valider les installations d’applications](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Vérifiez que l’application est présente et qu’elle fonctionne sur votre HoloLens 2 |

## <a name="maintain"></a>Maintenance

Utilisez Windows Update pour l’entreprise ainsi que votre système MDM ou le Microsoft Store pour mettre à jour votre flotte de applications HoloLens 2 et.

| Composant | Description |
|-----------|------------|
| [Mettre à jour HoloLens 2](hololens-updates.md) | Configurer les mises à jour en fonction des besoins par le biais des mises à jour Windows pour les entreprises |
| [Mise à jour des applications](app-deploy-overview.md) | Configurez votre système MDM ou le Microsoft Store
