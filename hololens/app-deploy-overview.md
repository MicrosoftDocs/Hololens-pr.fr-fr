---
title: Vue d’ensemble-gestion des applications
description: Prise en main d’une vue d’ensemble de la gestion des applications de réalité mixte avec la gestion des appareils mobiles, le Microsoft Store pour entreprises et les packages d’approvisionnement.
keywords: HoloLens, utilisateur, compte, application, gestion des applications,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308645"
---
# <a name="app-management-overview"></a>Gestion des applications : vue d’ensemble

Vous pouvez déployer des applications sur quatre chemins différents : la **gestion des appareils mobiles (MDM)**, **Microsoft Store pour les entreprises**, les **Microsoft Store**, ou en les installant par le biais de l' **approvisionnement**.

## <a name="mobile-device-management-mdm"></a>Gestion des appareils mobiles

Une solution de gestion des appareils mobiles permet aux décideurs informatiques et aux administrateurs d’installer automatiquement (push) leurs applications métier internes ou d’acheter des applications dans le Store pour un groupe d’utilisateurs. Les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications](app-deploy-intune.md). Intune offre également aux utilisateurs un contrôle plus affiné sur les applications gérées par le service informatique grâce à l’expérience téléchargeable Portail d’entreprise.

> [!NOTE]
> Les instructions suivantes sont destinées aux utilisateurs qui souhaitent gérer leurs applications avec Intune. Microsoft recommande l’utilisation d’Intune pour la gestion des applications et des appareils.

La gestion des appareils mobiles (MDM) s’applique aux éléments suivants :

* MDM déployé + Portail d’entreprise
* Applications métier (non publiques)
* Installation manuelle des applications disponibles via Portail d’entreprise
* Push administrateur via la stratégie MDM
* Mise à jour automatique via MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store pour Entreprises

Le [Microsoft Store pour les entreprises](app-deploy-store-business.md) fournit aux décideurs et aux administrateurs informatiques des entreprises pour trouver, acquérir, gérer et distribuer des applications gratuites et payantes. Les administrateurs informatiques peuvent gérer des applications Microsoft Store et des applications métier privées dans un même inventaire, ainsi qu’attribuer et réutiliser des licences en fonction des besoins. Pour plus d’informations, consultez [Configuration requise pour l’utilisation de l’Microsoft Store pour les entreprises](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

Les Microsoft Store pour les entreprises s’appliquent aux éléments suivants :

* Applications publiques ou métier
* Installation automatique des applications requises par le biais de l’Association MDM
* L’utilisateur télécharge manuellement les applications
* Mise à jour automatique

## <a name="microsoft-store-apps"></a>Applications de Microsoft Store

L’Microsoft Store fournit aux décideurs et aux administrateurs informatiques des entreprises pour rechercher, acquérir, gérer et distribuer des applications publiques.

Cette Microsoft Store s’applique aux éléments suivants :

* Applications publiques uniquement
* L’utilisateur télécharge manuellement les applications
* Mise à jour automatique en cas de connexion à Internet

Pour plus d’informations, consultez [applications du Store holographiques](https://docs.microsoft.com/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Installer via des packages d’approvisionnement

Les [packages de configuration](app-deploy-provisioning-package.md) vous permettent d’installer des applications personnalisées ou métier, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou plusieurs appareils locaux via USB. Cette installation peut être effectuée sans connexion Internet et pour n’importe quel type d’identité.

L’installation via des packages de configuration s’applique aux éléments suivants :

* Applications métier/à développement automatique (non publiques)
* Applications publiques (si le programme d’installation hors connexion est disponible)
* Chargement côté USB uniquement
* Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package d’approvisionnement)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Installer des applications sur HoloLens 2 via le programme d’installation d’application

L’utilisation des utilisateurs du [programme d’installation d’application](app-deploy-app-installer.md) peut avoir une expérience simple pour l’installation d’applications sur des appareils locaux ou le partage d’une application avec une autre personne qui ne connaît pas les autres méthodes d’installation d’applications sur HoloLens. Pour ce faire, vous devez activer le mode développeur ou utiliser le portail de l’appareil. Il s’agit d’une méthode simple pour distribuer une application entièrement générée. Quelle que soit la façon dont vous souhaitez simplement faire une démonstration de votre application pour un autre utilisateur avec un HoloLens, ou vous souhaitez déployer votre application, cette méthode fonctionne facilement.

L’installation via le programme d’installation d’application s’applique à :

* Applications métier/à développement automatique (non publiques)
* Chargement indépendant uniquement
* Ne nécessite pas le mode développeur ou le portail de l’appareil
* Facile à installer par l’utilisateur final
