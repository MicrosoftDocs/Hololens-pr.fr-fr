---
title: Configurez l’aperçu des CSPs et Gestion des Périphériques
description: Comment configurer les fournisseurs de services de cryptographie, de stratégie et de gestion des appareils.
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
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252775"
---
# Configurez l’aperçu des CSPs et Gestion des Périphériques

Les administrateurs informatiques peuvent définir et implémenter des paramètres de stratégie sur HoloLens 2. Les paramètres de configuration utilisés diffèrent selon le scénario de déploiement. Ce sont les appareils mobiles qui offrent au service informatique le plus de possibilités de contrôle. Dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface pour lire, définir, modifier ou supprimer des paramètres de configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Certains fournisseurs de service de configuration prennent en charge le format WAP (WAP) support SyncML et certains prennent en charge les deux.

Pour plus d’informations sur les fournisseurs de services de gestion des périphériques holographiques de Windows 10, consultez la liste complète des [fournisseurs de services de cryptographie pris en charge sur les appareils HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Les administrateurs informatiques peuvent également gérer les fournisseurs de services cryptographiques des stratégies sur les appareils, voir la liste complète des [fournisseurs de services cryptographiques pris en charge par HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## Méthodes de configuration

### Configurer avec la gestion des périphériques mobiles

Les fournisseurs de services d’entreprise et les stratégies peuvent être gérés facilement par tout appareil personnel ou professionnel inscrit dans un système de gestion des appareils mobiles. Une fois qu’un appareil est inscrit dans votre solution de gestion des appareils mobiles, vous pouvez gérer ce périphérique ou un ensemble d’appareils à l’aide de configurations d’appareil. En savoir plus sur la [gestion de vos appareils HoloLens via le GPM](hololens-mdm-configure.md).

### Configurer avec les packages de mise en service

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations de CSP pour les appareils HoloLens 2 par le biais de packages de mise en service personnalisés. Les packages de mise en service sont généralement utilisés pour les appareils non gérés par le système de gestion de la gestion des périphériques mobiles et nécessitent d’être appliqués manuellement à chaque appareil. Découvrez des informations sur la création [de packages de mise en service personnalisés pour HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## Configurations

### Restrictions d’appareil courantes

Certaines restrictions de périphériques sont simples et la désactivation d’une fonctionnalité ou d’une connexion à l’appareil. Pour en savoir plus sur les [restrictions d’appareil communes.](hololens-common-device-restrictions.md)

### Modes Kiosk

Utiliser le mode plein écran pour contrôler les identités auxquelles vous accédez par défaut aux applications. Les Kiosk peuvent être utilisés pour une seule application ou plusieurs applications d’interface utilisateur. La plage de configurations Kiosk d’une seule application à l’aide de l’appareil, à différentes sélections d’applications pour différents groupes. Le mode Kiosk n’arrête pas les «applications autorisées» pour lancer d’autres applications et n’a pas été conçu pour le moment. Pour en savoir plus, consultez la rubrique en savoir plus [sur les modes Kiosk et son utilisation](hololens-kiosk.md).

### Visibilité de la page des paramètres

Utilisez la stratégie d’application paramètres pour contrôler les identités qui ont accès aux paramètres par défaut. À l’aide de cette stratégie, vous pouvez configurer l’application paramètres pour afficher uniquement les pages sélectionnées ou masquer toutes les pages sélectionnées. [En savoir plus sur la configuration des pages disponibles](settings-uri-list.md).

Pour l’instant, cette fonctionnalité est uniquement disponible dans les [Builds Insider](hololens-insider.md). Assurez-vous que les appareils que vous envisagez d’utiliser pour cette fonction sont disponibles sur le 19041.1349 +.

### WDAC

Utilisez la configuration WDAC pour contrôler les applications/processus qui peuvent être démarrés ou interdits, que le système soit ou non en mode plein écran.
[Consultez notre présentation du WDAC.](windows-defender-application-control-wdac.md)
