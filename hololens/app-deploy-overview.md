---
title: Vue d’ensemble - Gestion des applications
description: Prise en charge d’une vue d’ensemble de la gestion des applications de réalité mixte avec la gestion des appareils mobiles, microsoft store pour entreprises et les packages d’approvisionnement.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283705"
---
# Vue d’ensemble de la gestion des applications

Vous pouvez déployer des applications sur quatre chemins différents : Gestion des périphériques mobiles **(MDM),** Microsoft Store pour **Entreprises,** **Microsoft Store**ou en les installant via **l’approvisionnement.**

## Gestion des périphériques mobiles (GPM)

Une solution MDM permet aux décideurs et administrateurs informatiques d’installer (push) en privé leurs applications métiers en interne ou d’acheter des applications via le Windows Store pour un groupe d’utilisateurs. Les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications.](app-deploy-intune.md) Intune offre également aux utilisateurs un contrôle plus fin sur les applications gérées par le service it via l’expérience téléchargeable du portail d’entreprise.

> [!NOTE]
> Les instructions suivantes sont pour les utilisateurs qui souhaitent gérer leurs applications avec Intune. Microsoft recommande d’utiliser Intune pour la gestion des applications et des appareils.

La gestion des périphériques mobiles (MDM) est applicable pour :

* GDM déployé + Portail d’entreprise
* Applications métier (non publiques)
* Installation manuelle des applications disponibles via le Portail d’entreprise
* L’administrateur fait passer par la stratégie de gestion des stratégies de gestion des stratégies de gestion
* Mise à jour automatique via la gestion des données de gestion des données

## Microsoft Store pour Entreprises

Le [Microsoft Store pour Entreprises](app-deploy-store-business.md) permet aux décideurs informatiques et aux administrateurs des entreprises de rechercher, d’acquérir, de gérer et de distribuer des applications gratuites et payantes. Les administrateurs informatiques peuvent gérer les applications du Microsoft Store et les applications métier privées dans un seul inventaire, et attribuer et réutiliser des licences selon vos besoins. Pour plus d’informations, [consultez les conditions préalables à l’utilisation du Microsoft Store pour Entreprises.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)

Le Microsoft Store pour Entreprises est applicable pour :

* Applications publiques ou métier
* Installation automatique des applications requises par le biais de l’association mdm
* L’utilisateur télécharge manuellement les applications
* Mise à jour automatique

## Applications du Microsoft Store

Le Microsoft Store permet aux décideurs informatiques et aux administrateurs des entreprises de rechercher, d’acquérir, de gérer et de distribuer des applications publiques.

Ce Microsoft Store est applicable pour :

* Applications publiques uniquement
* L’utilisateur télécharge manuellement des applications
* Mise à jour automatique en cas de connexion à Internet

Pour plus d’informations, [consultez les applications du Windows Store holographiques.](https://docs.microsoft.com/hololens/holographic-store-apps)

## Installer via des packages d’approvisionnement

[Les packages](app-deploy-provisioning-package.md) d’approvisionnement vous permettent d’installer des applications personnalisées ou métier, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou plusieurs appareils locaux via USB. Cette installation peut être effectuée sans connexion Internet et pour n’importe quel type d’identité.

L’installation via des packages d’approvisionnement s’applique pour :

* Applications métier/auto-développées (non publiques)
* Applications publiques (si le programme d’installation hors connexion est disponible)
* Chargement côté USB uniquement
* Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package d’approvisionnement)

## Installer des applications sur HoloLens 2 via le programme d’installation d’application

Les [](app-deploy-app-installer.md) utilisateurs du Programme d’installation d’application peuvent avoir une expérience simple pour installer des applications sur des appareils locaux ou partager une application avec quelqu’un d’autre qui ne connaît pas les autres méthodes d’installation d’application sur HoloLens. Pour ce faire, vous n’avez pas besoin d’activer le mode développeur ou d’utiliser Device Portal. Il s’agit d’une méthode simple de distribution d’une application entièrement intégrée. Que vous souhaitiez simplement rétrograder votre application auprès d’un autre utilisateur avec holoLens, ou que vous souhaitiez déployer votre application, cette méthode fonctionne facilement.

L’installation via le Programme d’installation d’application s’applique pour :

* Applications métier/auto-développées (non publiques)
* Chargement de version latérale uniquement
* Ne nécessite pas le mode développeur ou Device Portal
* Facile à installer pour l’utilisateur final
