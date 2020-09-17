---
title: Vue d’ensemble-gestion d’applications
description: application, gestion, gestion des applications
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
ms.openlocfilehash: b0b7609f1caac20ff0c47251b1f85a26d7fe1de8
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016648"
---
# Vue d’ensemble de la gestion des applications

Vous pouvez déployer des applications sur quatre chemins différents: **gestion des périphériques mobiles (GPM)**, **Microsoft Store entreprise**, **Microsoft Store**ou en les installant via la fonction de **mise en service**. 

## Gestion des périphériques mobiles (GPM)

Une solution de gestion des appareils mobiles permet aux utilisateurs de décideurs de décision et aux administrateurs d’installer en privé une installation automatique de leurs applications métier internes ou d’acheter des applications dans le Windows Store pour un groupe d’utilisateurs. Les appareils HoloLens fonctionnent mieux avec Microsoft Endpoint Manager (Intune) pour la [gestion des applications](app-deploy-intune.md). Intune offre aux utilisateurs un contrôle plus précis sur les applications gérées par le biais de l’interface du portail d’entreprise.

> [!NOTE] 
> Les instructions suivantes s’appliquent aux utilisateurs qui souhaitent gérer leurs applications avec Intune. Microsoft recommande l’utilisation de Intune pour la gestion des applications et des appareils.
    
La gestion des périphériques mobiles (GPM) s’applique aux éléments suivants: 
* Déploiement d’une entreprise via la gestion des périphériques mobiles 
* Lignes d’applications entreprise (non publiques)
* Installation manuelle des applications disponibles via le portail d’entreprise
* Stratégie d’administration Poussée via le GPM
* Mise à jour automatique via le GPM

## Microsoft Store pour Entreprises

Le [Microsoft Store pour les entreprises](app-deploy-store-business.md) fournit aux décisionnaires de décision et aux administrateurs des entreprises la recherche, l’acquisition, la gestion et la distribution des applications gratuites et payantes. Les administrateurs informatiques peuvent gérer les applications du MicrosoftStore et les applications cœur de métier privées dans un inventaire unique, et attribuer et réutiliser les licences selon leurs besoins. Pour plus d’informations, consultez [la configuration requise pour utiliser le Microsoft Store pour les entreprises](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).
    
Le Microsoft Store pour entreprises s’applique aux éléments suivants: 
* Applications publiques ou métier
* Installation automatique d’applications requises par le biais de l’Association GPM
* L’utilisateur télécharge manuellement des applications
* Mise à jour automatique

## Applications du Microsoft Store

Le Microsoft Store fournit aux décideurs de décision et aux administrateurs des entreprises la recherche, l’acquisition, la gestion et la distribution d’applications publiques.
    
Ce Microsoft Store est applicable pour: 
* Applications publiques uniquement
* L’utilisateur télécharge manuellement des applications
* Mise à jour automatique s’il est connecté à Internet

Pour plus d’informations, consultez applications du Windows [Store holographique](https://docs.microsoft.com/hololens/holographic-store-apps).

## Installation via les packages de mise en service

Les [packages de mise en service](app-deploy-provisioning-package.md) vous permettent d’installer des applications personnalisées ou d’une entreprise, ce qui permet aux professionnels de l’informatique et aux administrateurs d’installer rapidement des applications sur un ou des appareils locaux via USB. Cette opération peut être réalisée sans connexion Internet et pour tout type d’identité.
    
L’installation via les packages de mise en service est applicable pour: 
* Lignes d’applications entreprise (non publiques)
* Applications publiques (si le programme d’installation hors connexion est disponible)
* Télécharger uniquement le bus USB
* Aucune mise à jour automatique (nécessite des mises à jour manuelles via le package de mise en service)
