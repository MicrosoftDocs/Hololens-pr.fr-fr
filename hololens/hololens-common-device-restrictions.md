---
title: Limites des PériphériquesCommunes
description: Restez à jour avec les restrictions et paramètres d’appareil courants pour l’appareil HoloLens de réalité mixte.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283355"
---
# Limites des PériphériquesCommunes 

Ce guide aide les professionnels de l’informatique à comprendre les options de gestion les plus couramment utilisées disponibles pour le système d’exploitation holographique Windows 10 dans l’entreprise. Consultez la documentation de votre système GPM pour comprendre comment ces stratégies sont activées par votre fournisseur GPM. Tous les paramètres décrits dans ce guide ne sont pas pris en charge par l’ensemble des systèmes GPM. Certains d’entre eux prennent en charge des stratégies personnalisées par le biais de fichiers XML OMA-URI. Voir [Prise en charge des stratégies personnalisées dans MicrosoftIntune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Les conventions d’affectation de noms peuvent également varier parmi les fournisseurs GPM.

## Empêcher la modification des paramètres
Les employés sont généralement autorisés à modifier certains paramètres d’appareils personnels que vous souhaiterez peut-être verrouiller sur des appareils d’entreprise. Les employés peuvent ajuster de manière interactive certains paramètres de l’HoloLens via l’interface utilisateur des paramètres. À l’aide du système GPM, vous pouvez limiter les possibilités de modification des utilisateurs. Les listes suivantes répertorient les paramètres de gestion des appareils de gestion des appareils (MDM) couramment utilisés par Windows 10 Holographique pour configurer les restrictions de paramètres :
-   [Autoriser le VPN :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permet à l’utilisateur de modifier les paramètres VPN
-   [Autoriser la configuration WiFi manuelle :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permet aux utilisateurs d’établir Wi-Fi connexions en dehors des réseaux de gestion des données mobiles (MDM)
-   [Autoriser la désinscrire manuellement mdm](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Si les utilisateurs sont autorisés à supprimer le compte de l’espace de travail (c’est-à-dire, désinscrire l’appareil du système de gestion des périphériques mobiles)

Ajouté dans [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pour les appareils HoloLens 2 :
- [Autoriser l’ajout d’un package d’approvisionnement :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Bascule si les utilisateurs peuvent ajouter de nouveaux packages d’approvisionnement, en cas de basculement avec de nouvelles valeurs.
- [Autoriser la suppression du package d’approvisionnement :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Bascule si les utilisateurs peuvent supprimer des packages d’approvisionnement, ce qui leur permet de faire bascule les paramètres précédemment verrouillés.

Pour plus d’informations sur les options de stratégie, voir les [CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) de stratégie pris en charge par HoloLens

## Restrictions matérielles
Les appareils Holographiques Windows 10 utilisent une technologie de pointe qui inclut des fonctionnalités matérielles populaires telles que les caméras, les microphones, les haut-parleurs, les interfaces USB, les interfaces Bluetooth et le Wi-Fi. Vous pouvez utiliser les restrictions matérielles pour contrôler la disponibilité de ces fonctionnalités.
Les listes suivantes répertorient les paramètres de gestion des périphériques multigéographiques couramment utilisés par Windows 10 Holographique pour configurer les restrictions matérielles :

> [!NOTE]
> Certaines de ces restrictions matérielles affectent la connectivité et aident à la protection des données.

-   [Autoriser le Wi-Fi :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si les utilisateurs peuvent activer et utiliser la radio WiFi sur leurs appareils.
-   [Autoriser la connexion USB :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la connexion USB est activée (n’affecte pas la charge USB.)
-   [Autorisez Bluetooth :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si les utilisateurs peuvent activer et utiliser la radio Bluetooth sur leurs appareils.
-   [Restreindre l’appareil photo :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Spécifie si les applications Windows peuvent accéder à l’appareil photo.
-   [Restreindre les microphones :](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Spécifie si les applications Windows peuvent accéder au microphone.

Ajouté dans [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pour les appareils HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Définissez la durée jusqu’à ce que l’affichage soit éteint et que l’affichage soit éteint, verrouille l’appareil. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Définissez la durée jusqu’à ce que l’affichage soit éteint et, en le faisant, verrouille l’appareil. 
