---
title: Restrictions d’appareils courantes
description: restez à jour avec les paramètres et restrictions d’appareil courants pour l’appareil HoloLens de réalité mixte.
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
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639214"
---
# <a name="common-device-restrictions"></a>Restrictions d’appareils courantes 

ce guide aide les professionnels de l’informatique à comprendre les options de gestion les plus couramment utilisées pour le système d’exploitation Windows 10 Holographique dans l’entreprise. Consultez la documentation de votre système GPM pour comprendre comment ces stratégies sont activées par votre fournisseur GPM. Tous les paramètres décrits dans ce guide ne sont pas pris en charge par l’ensemble des systèmes GPM. Certains d’entre eux prennent en charge des stratégies personnalisées par le biais de fichiers XML OMA-URI. Voir [Prise en charge des stratégies personnalisées dans Microsoft Intune](/mem/intune/configuration/custom-settings-windows-10). Les conventions d’affectation de noms peuvent également varier parmi les fournisseurs GPM.

## <a name="prevent-changing-of-settings"></a>Empêcher la modification des paramètres
Les employés sont généralement autorisés à modifier certains paramètres d’appareils personnels que vous souhaiterez peut-être verrouiller sur des appareils d’entreprise. les employés peuvent ajuster de manière interactive certains paramètres du HoloLens par le biais de l’interface utilisateur des paramètres. À l’aide du système GPM, vous pouvez limiter les possibilités de modification des utilisateurs. la liste suivante répertorie les paramètres MDM couramment utilisés que Windows 10 Holographique prend en charge pour configurer des restrictions de paramètres :
-   [Autoriser le VPN :](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permet à l’utilisateur de modifier les paramètres VPN
-   [Autoriser la configuration manuelle du Wi-Fi :](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permet aux utilisateurs d’établir des connexions Wi-Fi en dehors des réseaux approvisionnés par MDM
-   [Autoriser la désinscription manuelle de MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Si les utilisateurs sont autorisés à supprimer le compte d’espace de travail (par exemple, désinscrire l’appareil du système MDM)

ajouté dans [Windows holographique, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pour les appareils HoloLens 2 :
- [Autoriser l’ajout d’un package de provisionnement :](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Basculez si les utilisateurs peuvent ajouter de nouveaux packages d’approvisionnement, en remplaçant par de nouvelles valeurs.
- [Autoriser la suppression du package d’approvisionnement :](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Bascule si les utilisateurs peuvent supprimer les packages de configuration, ce qui leur permet de basculer les paramètres précédemment verrouillés.

pour plus d’informations sur les options de stratégie, consultez la HoloLens les [fournisseurs de services de stratégie](/windows/client-management/mdm/policy-csps-supported-by-hololens2) pris en charge

## <a name="hardware-restrictions"></a>Restrictions matérielles
les appareils Windows 10 Holographique utilisent une technologie de pointe qui comprend des fonctionnalités matérielles populaires telles que des appareils photo, des microphones, des haut-parleurs, des interfaces USB, des interfaces Bluetooth et des réseaux Wi-Fi. Vous pouvez utiliser les restrictions matérielles pour contrôler la disponibilité de ces fonctionnalités.
la liste suivante répertorie les paramètres MDM couramment utilisés que Windows 10 Holographique prend en charge pour configurer des restrictions matérielles :

> [!NOTE]
> Certaines de ces restrictions matérielles affectent la connectivité et aident à la protection des données.

-   [Autoriser le Wi-Fi :](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si les utilisateurs peuvent activer et utiliser la radio WiFi sur leurs appareils.
-   [Autoriser la connexion USB :](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la connexion USB est activée (n’affecte pas la facturation USB).
-   [Autoriser Bluetooth :](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) si les utilisateurs peuvent activer et utiliser la radio Bluetooth sur leurs appareils.
-   [Restreindre l’appareil photo :](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) spécifie si les applications Windows peuvent accéder à l’appareil photo.
-   [Restreindre les microphones :](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) spécifie si les applications Windows peuvent accéder au microphone.

ajouté dans [Windows holographique, com20H2](hololens-release-notes.md#windows-holographic-version-20h2) pour les appareils HoloLens 2. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Définir la durée jusqu’à ce que l’affichage s’arrête et en désactivant l’affichage, verrouille l’appareil. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Définir la durée jusqu’à ce que l’affichage s’arrête et en désactivant l’affichage, verrouille l’appareil. 
