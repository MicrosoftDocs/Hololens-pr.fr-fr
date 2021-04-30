---
title: Présentation de la configuration des CSP et de la gestion des appareils
description: Découvrez comment configurer les fournisseurs de services de chiffrement, de stratégie et de gestion des appareils à l’aide de packages de configuration et de gestion des appareils mobiles.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308911"
---
# <a name="configure-csps-and-device-management-overview"></a>Présentation de la configuration des CSP et de la gestion des appareils

Les administrateurs informatiques peuvent définir et implémenter des paramètres de stratégie sur HoloLens 2. Les paramètres de configuration utilisés diffèrent selon le scénario de déploiement. Ce sont les appareils mobiles qui offrent au service informatique le plus de possibilités de contrôle. Dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface permettant de lire, de définir, de modifier ou de supprimer des paramètres de configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Certains fournisseurs de services de configuration prennent en charge le format WAP, certains SyncML de prise en charge et certains prennent en charge.

Pour plus d’informations sur les fournisseurs de services de gestion de périphériques holographiques Windows 10, consultez la liste complète des [fournisseurs de services de chiffrement pris en charge dans les appareils HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Les administrateurs informatiques peuvent également gérer les CSP de stratégie sur les appareils, voir la liste complète des [fournisseurs de services de stratégie pris en charge par HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Méthodes de configuration

### <a name="configure-with-mdm"></a>Configurer avec MDM

Les fournisseurs de services de chiffrement et les stratégies peuvent être gérés facilement sur n’importe quel appareil personnel ou d’entreprise inscrit dans un système MDM. Une fois qu’un appareil est inscrit dans votre solution MDM, vous pouvez gérer cet appareil ou un ensemble d’appareils à l’aide des configurations de l’appareil. En savoir plus sur la [gestion de vos appareils HoloLens via MDM](hololens-mdm-configure.md).

### <a name="configure-with-provisioning-packages"></a>Configurer avec des packages d’approvisionnement

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations CSP pour les appareils HoloLens 2 par le biais de packages de configuration personnalisés. Les packages d’approvisionnement sont généralement exploités pour les appareils non gérés par MDM et nécessitent une application manuelle sur chaque appareil. Lisez des informations sur la création de [packages d’approvisionnement personnalisés pour HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## <a name="configurations"></a>Configurations

### <a name="common-device-restrictions"></a>Restrictions d’appareils courantes

Certaines restrictions d’appareil sont aussi simples et désactivent une fonctionnalité ou une connexion à l’appareil. Pour en savoir plus sur ces informations, consultez la en savoir plus sur les [restrictions d’appareils courantes.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Modes plein écran

Utilisez le mode plein écran pour contrôler les identités qui ont accès aux applications par défaut. Les kiosques peuvent être utilisés pour une seule application ou pour une expérience d’interface utilisateur de plusieurs applications. Les configurations de kiosque vont d’une seule application pour toute personne utilisant l’appareil, à différentes sélections d’applications pour différents groupes. Le mode plein écran n’empêche pas les « applications autorisées » de lancer d’autres applications et n’a pas été conçu pour le moment. Pour en savoir plus, consultez la rubrique à [propos des modes kiosque et comment les utiliser](hololens-kiosk.md).

### <a name="settings-page-visibility"></a>Visibilité de la page des paramètres

Utilisez paramètres Stratégie d’application pour contrôler les identités qui ont accès aux paramètres par défaut. À l’aide de cette stratégie, l’application paramètres peut être configurée pour afficher uniquement les pages sélectionnées ou masquer toutes les pages sélectionnées. [En savoir plus sur la configuration des pages disponibles](settings-uri-list.md).

Cette fonctionnalité est actuellement disponible uniquement dans les [versions de Windows Insider](hololens-insider.md). Assurez-vous que les appareils pour lesquels vous avez l’intention d’utiliser cette fonctionnalité sont sur Build 19041.1349 +.

### <a name="wdac"></a>WDAC

Utilisez la configuration WDAC pour contrôler les applications/processus qui sont autorisés/interdits pour être lancés, que le système soit en mode plein écran ou non.
[Consultez notre présentation de WDAC.](windows-defender-application-control-wdac.md)
