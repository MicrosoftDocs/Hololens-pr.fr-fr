---
title: Configurez l’aperçu des CSPs et Gestion des Périphériques
description: Découvrez comment configurer les CSP, les stratégies et la gestion des appareils à l’aide de la gestion des périphériques mobiles et des packages d’approvisionnement.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283245"
---
# Configurez l’aperçu des CSPs et Gestion des Périphériques

Les administrateurs informatiques peuvent définir et implémenter des paramètres de stratégie sur HoloLens 2. Les paramètres de configuration utilisés diffèrent selon le scénario de déploiement. Ce sont les appareils mobiles qui offrent au service informatique le plus de possibilités de contrôle. Dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface pour lire, définir, modifier ou supprimer des paramètres de configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Certains fournisseurs de services de configuration prise en charge le format WAP, d’autres la prise en charge de SyncML et d’autres les deux.

Pour plus d’informations sur les CSP de gestion des appareils Windows 10 Holographique, consultez la liste complète des CSP pris en charge sur les [appareils HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
Les administrateurs informatiques peuvent également gérer le programme CSP de stratégie sur les appareils. Consultez la liste complète des CSP de stratégie pris en charge [par HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## Méthodes de configuration

### Configurer avec la gestion des mdm

Les stratégies et les CSP peuvent être facilement gérés sur n’importe quel appareil personnel ou d’entreprise inscrit dans un système de gestion des périphériques de gestion des périphériques. Une fois qu’un appareil est inscrit dans votre solution de gestion des périphériques mobiles, vous pouvez gérer cet appareil ou un ensemble d’appareils à l’aide de configurations d’appareil. En savoir plus sur la gestion [de vos appareils HoloLens via la gestion des](hololens-mdm-configure.md)périphériques mobiles .

### Configurer avec des packages d’approvisionnement

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations CSP pour les appareils HoloLens 2 via des packages d’approvisionnement personnalisés. Les packages d’approvisionnement sont généralement utilisés pour les appareils non gérés par la gestion des périphériques mobiles et doivent être appliqués manuellement à chaque appareil. Lisez les informations sur la création de [packages d’approvisionnement personnalisés pour HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Configurations

### Restrictions d’appareil courantes

Certaines restrictions d’appareil sont aussi simples et désactivent une fonctionnalité ou une connexion à l’appareil. Pour en savoir plus sur ces restrictions [d’appareil courantes.](hololens-common-device-restrictions.md)

### Modes plein affichage

Utilisez le mode plein écran pour contrôler les identités qui ont accès aux applications par défaut. Les kiosques peuvent être utilisés pour une seule application ou plusieurs expériences d’interface utilisateur d’application. Les configurations kiosk vont d’une application unique pour toute personne utilisant l’appareil à différentes sélections d’applications pour différents groupes. Le mode plein écran n’empêche pas les « applications autorisées » de lancer d’autres applications et n’a jamais été conçu. Pour en savoir [plus, lisez les modes Kiosk et leur utilisation.](hololens-kiosk.md)

### Visibilité de la page Paramètres

Utilisez la stratégie d’application Paramètres pour contrôler les identités qui ont accès aux paramètres par défaut. À l’aide de cette stratégie, l’application Paramètres peut être configurée pour afficher uniquement les pages sélectionnées ou masquer toutes les pages sélectionnées. [Découvrez comment configurer les pages disponibles.](settings-uri-list.md)

Cette fonctionnalité est actuellement disponible uniquement dans les [builds Windows Insider.](hololens-insider.md) Assurez-vous que les appareils pour qui vous avez l’intention d’utiliser cette fonctionnalité sont sur la build 19041.1349+.

### WDAC

Utilisez la configuration WDAC pour contrôler les applications/processus autorisés/non autorisés à être lancés, que le système soit en mode plein écran ou non.
[Consultez notre vue d’ensemble pour WDAC.](windows-defender-application-control-wdac.md)
