---
title: Utilisation de Microsoft Endpoint Manager Intune pour gérer les appareils HoloLens
description: Découvrez comment utiliser la gestion des périphériques mobiles pour configurer le programme CSP, la stratégie et gérer les appareils HoloLens de réalité mixte à l’échelle à l’aide d’Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283955"
---
# Utilisation de Microsoft Endpoint Manager Intune pour gérer les appareils HoloLens

Il existe de nombreux paramètres différents que vous pouvez gérer via mdm. L’utilisation d’appareils Intune peut être regroupée et des configurations peuvent être déployées sur ces groupes d’utilisateurs ou d’appareils. Les applications peuvent également être déployées et gérées, en configurant des appareils pour se connecter à votre réseau, ainsi que des mises à jour qui se produisent au moment souhaité et sur l’anneau de mise à jour nécessaire. 

## Comment gérer via Intune

### Catégories et groupes d’appareils
À l’aide d’Intune, vous pouvez créer des catégories d’appareils pour ajouter automatiquement des appareils à des groupes en fonction des catégories que vous créez, telles que ingénierie, médical, développeurs, etc. L’idée est de faciliter la gestion de vos appareils exécutant Windows Holographic for Business.
En savoir plus : classer [les appareils en groupes](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Profils de configuration d’appareil
Intune inclut des paramètres et des fonctionnalités que vous pouvez activer ou désactiver sur différents appareils au sein de votre organisation. Ces paramètres et fonctionnalités sont gérés à l’aide de profils. Par exemple, vous pouvez créer un profil qui active Cortana ou utilise Microsoft Defender Smart Screen sur vos appareils exécutant Windows Holographic for Business.
Dans vos profils, vous pouvez utiliser OMA-URI pour personnaliser certains paramètres, créer des restrictions d’appareil et configurer un réseau privé virtuel (VPN) et le Wi-Fi.
[Commencer avec les profils de configuration](https://docs.microsoft.com/mem/intune/configuration/device-profiles)et la [vue d’ensemble des profils.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## Exemples de ce qui peut être géré et configuré

L’utilisation de la gestion des périphériques mobiles pour gérer les appareils offre un large éventail d’éléments qui peuvent être sélectionnés. 

### Wi-Fi
[Les paramètres Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) affectent les paramètres de réseau sans fil aux utilisateurs et appareils. Lorsque vous affectez un profil Wi-Fi, les utilisateurs ont accès à votre Wi-Fi d’entreprise sans avoir à le configurer eux-mêmes.
En savoir plus [sur la configuration de votre réseau pour HoloLens](hololens-commercial-infrastructure.md)

### Certificats
Les certificats contribuent à améliorer la sécurité en fournissant l’authentification de compte, Wi-Fi l’authentification, le chiffrement VPN et le chiffrement SSL du contenu web. Bien que les administrateurs peuvent gérer manuellement les certificats sur les appareils par le biais de packages d’approvisionnement, il est préférable d’utiliser votre système de gestion des périphériques mobiles pour gérer ces certificats tout au long de leur cycle de vie , de l’inscription au renouvellement et à la révocation. Votre système de gestion des périphériques mobiles peut déployer automatiquement ces certificats dans les magasins de certificats des appareils une fois que vous avez inscrit l’appareil (tant que le système de gestion des périphériques mobiles prend en charge le protocole SCEP (Simple Certificate Enrollment Protocol) ou le #12 des normes de chiffrement à clé publique (PKCS#12)). MdM peut également interroger et supprimer des certificats clients inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel. 

### Proxy
La plupart des réseaux intranet d’entreprise utilisent un proxy pour gérer le trafic interne. Avec HoloLens 2, vous pouvez configurer un serveur proxy pour ethernet et Wi-Fi connexions. Ces paramètres ne s’appliquent pas aux connexions VPN. Pour plus d’informations sur les paramètres de proxy pour Windows 10, voir [CSP NetworkProxy.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

### VPN
Les organisations font souvent appel à une connexion VPN pour contrôler l’accès aux applications et aux ressources sur l’intranet de leur société. HoloLens 2 prend en charge les connexions VPN SSL, qui nécessitent un plug-in téléchargeable à partir du Microsoft Store et sont spécifiques au fournisseur VPN de votre choix. 
- En savoir plus [sur VPN sur HoloLens.](hololens-network.md#vpn)
- Pour plus d’informations sur les profils VPN, voir le fournisseur [CSP VPNv2.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### Déployer et gérer des applications
À l’aide d’Intune, vous pouvez ajouter des applications à vos appareils exécutant Windows Holographic for Business. Une solution MDM permet aux décideurs et administrateurs informatiques d’installer (push) en privé leurs applications métiers en interne ou d’acheter des applications via le Windows Store pour un groupe d’utilisateurs. Il existe plusieurs façons de déployer des applications, notamment :
-   [Intune et portail d’entreprise]( app-deploy-intune.md)
-   [Microsoft Store pour Entreprises]( app-deploy-store-business.md)

En savoir plus sur la gestion des applications via Intune.
-   [Ajouter des applications à Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Ajouter des applications du Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Ajouter des applications que vous créez](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Affecter des applications à des groupes](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Mises à jour logicielles
Intune inclut une fonctionnalité appelée anneaux de mise à jour pour les appareils Windows 10. Ces anneaux de mise à jour incluent un groupe de paramètres qui déterminent la façon dont les mises à jour sont installées. Par exemple, vous pouvez créer une fenêtre de maintenance pour installer les mises à jour, ou choisir de redémarrer après l’installation des mises à jour. Une sonnerie de mise à jour peut être appliquée à plusieurs appareils exécutant Windows Holographic for Business.
En savoir plus sur la gestion des mises à jour [HoloLens](hololens-updates.md) et la gestion des mises à [jour logicielles via Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### Configurer le mode Kiosk
À l’aide des fonctionnalités de PC partagé ou invité disponibles dans Intune, vous pouvez configurer les appareils Windows Holographic for Business pour qu’ils s’exécutent en tant que kiosque. Ces appareils peuvent exécuter une application (mode plein écran d’application unique) ou exécuter plusieurs applications (mode plein écran multi-application). Le mode plein écran est une interface utilisateur qui permet de contrôler les identités qui ont accès aux applications par défaut.
Découvrez comment configurer [HoloLens en tant que kiosque]( hololens-kiosk.md)

