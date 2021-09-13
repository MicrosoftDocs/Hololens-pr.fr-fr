---
title: Planification du déploiement de HoloLens 2 dans un environnement commercial
description: découvrez les principaux besoins en matière de déploiement et de gestion des HoloLens dans les environnements d’entreprise, notamment l’infrastructure, azure active directory et la gestion des appareils mobiles.
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
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032443"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planification du déploiement de HoloLens 2 dans un environnement commercial

## <a name="overview"></a>Vue d’ensemble

> [!NOTE]
> cette vue d’ensemble est destinée à aider les professionnels de l’informatique à comprendre les considérations relatives au déploiement et à la gestion d’appareils Microsoft HoloLens 2 au sein d’une organisation. pour les utilisateurs finaux d’appareils, consultez [obtenir votre HoloLens 2 prêt à utiliser](hololens2-setup.md) pour commencer.

HoloLens 2 s’exécute sur Windows 10 Holographique qui fournit aux organisations des technologies de gestion des applications et des appareils mobiles robustes, flexibles et intégrées. Windows 10 Holographique prend en charge la gestion du cycle de vie des appareils de bout en bout pour permettre aux entreprises de contrôler leurs appareils, leurs données et leurs applications. les HoloLens 2 peuvent facilement être incorporées dans des pratiques de cycle de vie standard, de l’inscription des appareils, de la configuration et de la gestion des applications à la maintenance et à la retraite à l’aide d’une solution complète de gestion des appareils mobiles.

les étapes et la vidéo suivantes peuvent vous guider tout au long du processus de HoloLens 2 adoption au sein de votre organisation.

| &nbsp; | &nbsp; |
|--|--|
| ![Étape 1.](images/1green.png)| <br/> **[scénarios de déploiement courants](hololens-requirements.md)**: comprenez les scénarios de déploiement et explorez les principaux composants nécessaires au déploiement de HoloLens 2 appareils. |
| ![Étape 2.](images/2green.png)| <br/> **[Préparer](#prepare)**: Familiarisez-vous avec les principes fondamentaux de l’infrastructure nécessaires à la HoloLens 2. |
| ![Étape 3.](images/3green.png) | <br/> **[Configurer](#configure)**: Découvrez comment configurer vos composants essentiels pour un déploiement basé sur le Cloud. |
| ![Étape 4.](images/4green.png) | <br/> **[Déploiement](#deploy)**: Découvrez comment déployer vos appareils et distribuer vos applications de manière sécurisée et efficace. |
| ![Étape 5.](images/5green.png) | <br/> **[tenir à jour](#maintain)**: découvrez ce qui est nécessaire pour maintenir correctement l’état de vos appareils HoloLens 2 et garantir la conformité avec la stratégie d’entreprise. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Préparation

découvrez les services d’infrastructure essentiels requis pour prendre en charge l’ensemble complet des fonctionnalités de HoloLens 2.

| Composant | Description |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Fournit la gestion des identités et des accès pour les HoloLens 2  |
| [Gestion des appareils mobiles](hololens-mdm-configure.md)| gère HoloLens 2 appareils connectés à votre locataire  |
| [Réseau Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi est disponible et les appareils peuvent être connectés à Internet  |

## <a name="configure"></a>Configurer

utilisez Intune et autopilot comme solutions de bas niveau pour l’inscription et la configuration de HoloLens 2 au client Azure AD et au MDM de votre organisation.

| Composant | Description |
|-----------|------------|
| [Inscription automatique](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Après la connexion initiale, les appareils s’inscrivent automatiquement auprès d’Azure AD et s’inscrivent dans MDM  |
| [Licences d’application](hololens2-cloud-connected-configure.md#application-licenses)| Peut être appliqué à des utilisateurs, à des groupes d’utilisateurs ou à des groupes d’appareils  |
| [Utilisateurs et groupes Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Permet d’attribuer des configurations et des licences pour le HoloLens 2  |

## <a name="deploy"></a>Déployer

distribuez vos appareils HoloLens 2 et validez leur configuration. 

| Composant | Description |
|-----------|------------|
| [Validation de l’inscription](hololens2-corp-connected-deploy.md#enrollment-validation) | valider que l’appareil n’a Azure AD joint depuis Paramètres ou le portail Azure |
| [Validation de certificat](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Vérifier les paramètres et vérifier qu’ils ont été distribués correctement |
| [Valider les installations d’applications](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Vérifiez que l’application est présente et qu’elle fonctionne sur votre HoloLens 2 |

## <a name="maintain"></a>Maintenance

utilisez Windows Update pour l’entreprise avec votre système MDM ou le Microsoft Store pour maintenir à jour votre parc de HoloLens 2 et d’applications.

| Composant | Description |
|-----------|------------|
| [Mettre à jour HoloLens 2](hololens-updates.md) | configurer les mises à jour en fonction des besoins par le biais des mises à jour Windows pour l’entreprise |
| [Mettre à jour des applications](app-deploy-overview.md) | Configurez votre système MDM ou le Microsoft Store
