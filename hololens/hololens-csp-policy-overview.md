---
title: Vue d’ensemble de la configuration des fournisseurs CSP et de la gestion des appareils
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032427"
---
# <a name="configure-csps-and-device-management-overview"></a>Vue d’ensemble de la configuration des fournisseurs CSP et de la gestion des appareils

Les administrateurs informatiques peuvent définir et implémenter des paramètres de stratégie sur HoloLens 2. Les paramètres de configuration utilisés diffèrent selon le scénario de déploiement. Ce sont les appareils mobiles qui offrent au service informatique le plus de possibilités de contrôle. dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface permettant de lire, de définir, de modifier ou de supprimer des paramètres de Configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Certains fournisseurs de services de configuration prennent en charge le format WAP, certains SyncML de prise en charge et certains prennent en charge.

pour plus d’informations sur Windows 10 Holographique csp de gestion des appareils, consultez la liste complète des [fournisseurs de services de chiffrement pris en charge dans les appareils HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Les administrateurs informatiques peuvent également gérer les CSP de stratégie sur les appareils, voir la liste complète des fournisseurs de services de stratégie de groupe [pris en charge par HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Méthodes de configuration

### <a name="configure-with-mdm"></a>Configurer avec MDM

Les fournisseurs de services de chiffrement et les stratégies peuvent être gérés facilement sur n’importe quel appareil personnel ou d’entreprise inscrit dans un système MDM. Une fois qu’un appareil est inscrit dans votre solution MDM, vous pouvez gérer cet appareil ou un ensemble d’appareils à l’aide des configurations de l’appareil. en savoir plus sur la [gestion de vos appareils HoloLens via MDM](hololens-mdm-configure.md).

### <a name="configure-with-provisioning-packages"></a>Configurer avec des packages d’approvisionnement

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations CSP pour les appareils HoloLens 2 par le biais de Packages d’approvisionnement personnalisés. Les packages d’approvisionnement sont généralement exploités pour les appareils non gérés par MDM et nécessitent une application manuelle sur chaque appareil. Lisez des informations sur la création [de packages d’approvisionnement personnalisés pour HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Configurations

### <a name="common-device-restrictions"></a>Restrictions d’appareil courantes

Certaines restrictions d’appareil sont aussi simples et désactivent une fonctionnalité ou une connexion à l’appareil. Pour en savoir plus sur ces informations, consultez la en savoir plus sur les [restrictions d’appareils courantes.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Modes plein écran

Utilisez le mode plein écran pour contrôler les identités qui ont accès aux applications par défaut. Les kiosques peuvent être utilisés pour une seule application ou pour une expérience d’interface utilisateur de plusieurs applications. Les configurations de kiosque vont d’une seule application pour toute personne utilisant l’appareil, à différentes sélections d’applications pour différents groupes. Le mode plein écran n’empêche pas les « applications autorisées » de lancer d’autres applications et n’a pas été conçu pour le moment. Pour en savoir plus, consultez la rubrique à [propos des modes kiosque et comment les utiliser](hololens-kiosk.md).

### <a name="settings-page-visibility"></a>Paramètres Visibilité de page

utilisez Paramètres stratégie d’application pour contrôler les identités qui ont accès aux paramètres par défaut. à l’aide de cette stratégie, l’application Paramètres peut être configurée pour afficher uniquement les pages sélectionnées ou masquer toutes les pages sélectionnées. [En savoir plus sur la configuration des pages disponibles](settings-uri-list.md).

cette fonctionnalité est actuellement disponible uniquement dans [Windows les builds insider](hololens-insider.md). Assurez-vous que les appareils pour lesquels vous avez l’intention d’utiliser cette fonctionnalité sont sur Build 19041.1349 +.

### <a name="wdac"></a>WDAC

Utilisez la configuration WDAC pour contrôler les applications/processus qui sont autorisés/interdits pour être lancés, que le système soit en mode plein écran ou non.
[Consultez notre présentation de WDAC.](windows-defender-application-control-wdac.md)
