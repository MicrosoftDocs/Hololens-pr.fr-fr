---
title: Utilisation du gestionnaire de points de terminaison Microsoft pour gérer les appareils HoloLens
description: L’utilisation de la gestion des appareils mobiles et de la stratégie et de la gestion de HoloLens à l’échelle.
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009635"
---
# Utilisation du gestionnaire de points de terminaison Microsoft pour gérer les appareils HoloLens

Vous pouvez gérer différents paramètres via le GPM. L’utilisation de périphériques Intune peut être regroupée et les configurations peuvent être déployées vers ces groupes d’utilisateurs ou d’appareils. Il est également possible de déployer et de gérer des applications, de configurer des appareils pour vous connecter à votre réseau et de configurer les mises à jour pour qu’elles se produisent au moment souhaité et sur l’anneau de mise à jour nécessaire. 

## Gestion via Intune

### Catégories et groupes de périphériques
À l’aide de Intune, vous pouvez créer des catégories d’appareils pour ajouter automatiquement des appareils aux groupes en fonction de catégories que vous créez, telles que l’ingénierie, la médecine, les développeurs, etc. L’idée consiste à faciliter la gestion de vos appareils exécutant Windows holographique pour les entreprises.
En savoir plus: [classer des appareils en groupes](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Profils de configuration d’appareil
Intune inclut des paramètres et fonctionnalités que vous pouvez activer ou désactiver sur différents appareils au sein de votre organisation. Ces paramètres et fonctionnalités sont gérés à l’aide de profils. Par exemple, vous pouvez créer un profil qui autorise Cortana, ou utiliser l’écran intelligent de Microsoft Defender sur vos appareils exécutant Windows holographique pour les entreprises.
Dans vos profils, vous pouvez utiliser un URI OMA pour personnaliser certains paramètres, créer des restrictions d’appareil et configurer un réseau privé virtuel (VPN) et un réseau Wi-Fi.
[Familiarisez-vous avec les profils de configuration](https://docs.microsoft.com/mem/intune/configuration/device-profiles)et la [vue d’ensemble du profil](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).

## Exemples de gestion et de configuration

L’utilisation de la gestion des périphériques mobiles pour gérer les appareils donne accès à un large éventail d’éléments pouvant être sélectionnés. 

### Wi-Fi
Les [paramètres Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) attribuent des paramètres réseau sans fil aux utilisateurs et aux appareils. Lorsque vous attribuez un profil Wi-Fi, les utilisateurs accèdent à votre Wi-Fi d’entreprise sans avoir à le configurer.
En savoir plus sur [la configuration de votre réseau pour HoloLens](hololens-commercial-infrastructure.md)

### Certificats
Les certificats permettent d’améliorer la sécurité en fournissant l’authentification de compte, l’authentification Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. Bien que les administrateurs puissent gérer les certificats sur les appareils manuellement par le biais de la mise en service des packages, il est recommandé d’utiliser votre système de gestion des appareils mobiles pour gérer ces certificats tout au long de leur cycle de vie, de l’inscription au renouvellement et de la révocation. Votre système de gestion des périphériques mobiles peut déployer automatiquement ces certificats sur les magasins de certificats de périphériques après l’inscription de l’appareil (tant que le système de gestion des appareils mobiles prend en charge les normes de cryptographie par le biais du protocole SCEP) ou du chiffrement à clé publique #12 (PKCS # 12)). Le GPM peut également rechercher et supprimer des certificats client inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel. 

### Proxy
La plupart des réseaux intranet d’entreprise tirent parti d’un proxy pour gérer le trafic interne. Avec HoloLens 2, vous pouvez configurer un serveur proxy pour les connexions Ethernet et Wi-Fi. Ces paramètres ne s’appliquent pas aux connexions VPN. Pour plus d’informations sur les paramètres de proxy pour Windows 10, consultez [fournisseur de services de NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
Les organisations font souvent appel à une connexion VPN pour contrôler l’accès aux applications et aux ressources sur l’intranet de leur société. HoloLens 2 prend en charge les connexions VPN SSL qui nécessitent un plug-in téléchargeable auprès du Microsoft Store et qui sont propres à l’éditeur de votre choix. 
- En savoir plus sur [VPN sur HoloLens](hololens-network.md#vpn).
- Pour plus d’informations sur les profils VPN, voir le [fournisseur de services de VPNv2](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

### Déployer et gérer des applications
À l’aide de Intune, vous pouvez ajouter des applications sur vos appareils exécutant Windows holographique pour les entreprises. Une solution de gestion des appareils mobiles permet aux utilisateurs de décideurs de décision et aux administrateurs d’installer en privé une installation automatique de leurs applications métier internes ou d’acheter des applications dans le Windows Store pour un groupe d’utilisateurs. Il existe de nombreuses façons de déployer des applications, notamment:
-   [Intune et portail d’entreprise]( app-deploy-intune.md)
-   [Microsoft Store pour Entreprises]( app-deploy-store-business.md)

En savoir plus sur la gestion des applications via Intune.
-   [Ajouter des applications à Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Ajouter des applications du Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Ajouter des applications que vous créez](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Affecter des applications à des groupes](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Mises à jour logicielles
Intune inclut une fonctionnalité appelée anneaux de mise à jour pour les appareils Windows 10. Ces anneaux de mise à jour incluent un groupe de paramètres qui déterminent le mode d’installation des mises à jour. Par exemple, vous pouvez créer une fenêtre de maintenance pour installer les mises à jour, ou choisir de redémarrer après l’installation des mises à jour. Un anneau de mise à jour peut être appliqué à plusieurs appareils exécutant Windows holographique pour les entreprises.
En savoir plus sur la [gestion des mises à jour de HoloLens](hololens-updates.md) et la [gestion des mises à jour logicielles via Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

### Configurer le mode Kiosk
À l’aide des fonctionnalités des PC partagés ou invités disponibles dans Intune, vous pouvez configurer les appareils Windows holographique pour les entreprises pour qu’ils s’exécutent en tant que kiosque. Ces appareils peuvent exécuter une seule application (en mode kiosque d’application unique) ou exécuter plusieurs applications (mode Kiosk multi-App). Le mode Kiosk est une interface utilisateur qui vous permet de contrôler les identités auxquelles vous accédez par défaut aux applications.
Découvrir comment [configurer HoloLens en tant que borne]( hololens-kiosk.md)

