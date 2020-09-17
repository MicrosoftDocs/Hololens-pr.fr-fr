---
title: Restrictions d’appareil courantes
description: Le périphérique restrctions est généralement défini sur HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016773"
---
# Restrictions d’appareil courantes 

Ce guide est destiné à aider les informaticiens à comprendre les options de gestion les plus fréquemment utilisées pour le système d’exploitation Windows 10 holographique au sein de l’entreprise. Consultez la documentation de votre système GPM pour comprendre comment ces stratégies sont activées par votre fournisseur GPM. Tous les paramètres décrits dans ce guide ne sont pas pris en charge par l’ensemble des systèmes GPM. Certains d’entre eux prennent en charge des stratégies personnalisées par le biais de fichiers XML OMA-URI. Voir [Prise en charge des stratégies personnalisées dans MicrosoftIntune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Les conventions d’affectation de noms peuvent également varier parmi les fournisseurs GPM.

## Empêcher la modification des paramètres
Les employés sont généralement autorisés à modifier certains paramètres d’appareils personnels que vous souhaiterez peut-être verrouiller sur des appareils d’entreprise. Les employés peuvent ajuster les paramètres du HoloLens par le biais de l’interface utilisateur des paramètres. À l’aide du système GPM, vous pouvez limiter les possibilités de modification des utilisateurs. Les listes suivantes répertorient les paramètres de gestion des périphériques mobiles fréquemment utilisés que Windows 10 holographique prend en charge pour configurer les restrictions de paramètres:
-   [Autoriser VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permet à l’utilisateur de modifier les paramètres de réseau privé virtuel (VPN)
-   [Autorisez la configuration WiFi manuelle:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permet aux utilisateurs de créer des connexions Wi-Fi en dehors de réseaux approvisionnés pour la gestion des périphériques mobiles.
-   [Autoriser la désinscription manuelle](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) de la gestion des périphériques mobiles Si les utilisateurs sont autorisés à supprimer le compte de l’entreprise (c’est-à-dire, à annuler l’inscription de l’appareil à partir du système GPM);

Pour plus d’informations, consultez Options de stratégie dans les [fournisseurs de stratégie](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) pris en charge HoloLens.

## Restrictions matérielles
Les appareils holographiques Windows 10 utilisent une technologie de pointe qui inclut des fonctionnalités matérielles courantes, telles que des appareils photo, des microphones, des haut-parleurs, des interfaces USB, des interfaces Bluetooth et un réseau Wi-Fi. Vous pouvez utiliser les restrictions matérielles pour contrôler la disponibilité de ces fonctionnalités.
Les listes suivantes permettent de configurer les paramètres de gestion des périphériques mobiles couramment utilisés par Windows 10 pour configurer les restrictions matérielles:

> [!NOTE]
> Certaines de ces restrictions matérielles affectent la connectivité et vous aident à protéger les données.

-   [Autorisation Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si les utilisateurs peuvent activer et utiliser la radio WiFi sur leurs appareils.
-   [Autoriser la connexion USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la connexion USB est activée (cela n’affecte pas le débit du bus USB)
-   [Autoriser Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si les utilisateurs peuvent activer et utiliser la radio Bluetooth sur leurs appareils.
-   [Restreindre la caméra:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Spécifie si les applications Windows peuvent accéder à la caméra.
-   [Restreindre les microphones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Spécifie si les applications Windows peuvent accéder au micro.
