---
title: utilisation de Microsoft Endpoint Manager Intune pour gérer les appareils HoloLens
description: découvrez comment utiliser la gestion des appareils mobiles pour configurer un CSP, une stratégie et gérer HoloLens des appareils de réalité mixte à grande échelle à l’aide d’Intune.
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
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640273"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>utilisation de Microsoft Endpoint Manager Intune pour gérer les appareils HoloLens

Vous pouvez gérer plusieurs paramètres à l’aide de MDM. L’utilisation d’appareils Intune peut être regroupée et les configurations peuvent être déployées sur ces groupes d’utilisateurs ou d’appareils. Vous pouvez également déployer et gérer des applications, configurer des appareils pour qu’ils se connectent à votre réseau, ainsi que configurer des mises à jour pour qu’elles se produisent à l’heure souhaitée et sur l’anneau de mise à jour nécessaire. 

## <a name="how-to-manage-via-intune"></a>Comment gérer via Intune

### <a name="device-categories-and-groups"></a>Catégories et groupes d’appareils
À l’aide d’Intune, vous pouvez créer des catégories d’appareils pour ajouter automatiquement des appareils à des groupes en fonction des catégories que vous créez, telles que l’ingénierie, la médecine, les développeurs, etc. L’idée est de faciliter la gestion de vos appareils exécutant Windows Holographic for Business.
En savoir plus : [catégorisation des appareils dans des groupes](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Profils de configuration d’appareil
Intune inclut des paramètres et des fonctionnalités que vous pouvez activer ou désactiver sur différents appareils de votre organisation. Ces paramètres et fonctionnalités sont gérés à l’aide de profils. Par exemple, vous pouvez créer un profil qui active Cortana ou Microsoft Defender SmartScreen sur vos appareils exécutant Windows Holographic for Business.
Dans vos profils, vous pouvez utiliser OMA-URI pour personnaliser certains paramètres, imposer des restrictions aux appareils et configurer un réseau VPN (réseau privé virtuel) ou Wi-Fi.
[Prise en main des profils de configuration](/mem/intune/configuration/device-profiles)et [vue d’ensemble du profil](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Exemples de ce qui peut être géré et configuré

L’utilisation de MDM pour gérer des appareils donne un grand nombre d’éléments qui peuvent être sélectionnés. 

### <a name="wi-fi"></a>Wi-Fi
Le profil [Paramètres Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) affecte les paramètres de réseau sans fil aux utilisateurs et appareils. Lorsque vous affectez un profil de Wi-Fi, les utilisateurs ont accès à votre Wi-Fi d’entreprise sans avoir à le configurer eux-mêmes.
En savoir plus sur [la configuration de votre réseau pour HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificats
Les certificats aident à améliorer la sécurité en fournissant l’authentification de compte, l’authentification Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. Bien que les administrateurs puissent gérer les certificats sur les appareils manuellement par le biais de packages de provisionnement, il est recommandé d’utiliser votre système MDM pour gérer ces certificats tout au long de leur cycle de vie, de l’inscription au renouvellement et de la révocation. Votre système MDM peut déployer automatiquement ces certificats sur les magasins de certificats des appareils après avoir inscrit l’appareil (à condition que le système MDM prenne en charge le Protocole d’inscription de certificats simple (SCEP) ou les normes de chiffrement à clé publique #12 (PKCS # 12)). MDM peut également interroger et supprimer des certificats clients inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel. 

### <a name="proxy"></a>Proxy
La plupart des réseaux intranet d’entreprise tirent parti d’un proxy pour gérer le trafic interne. avec HoloLens 2 vous pouvez configurer un serveur proxy pour les connexions ethernet et Wi-Fi. Ces paramètres ne s’appliquent pas aux connexions VPN. pour plus d’informations sur les paramètres de proxy pour Windows 10, consultez [CSP NetworkProxy](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
Les organisations font souvent appel à une connexion VPN pour contrôler l’accès aux applications et aux ressources sur l’intranet de leur société. HoloLens 2 prend en charge les connexions vpn SSL, qui nécessitent un plug-in téléchargeable à partir du Microsoft Store et sont spécifiques au fournisseur VPN de votre choix. 
- En savoir plus sur [VPN sur HoloLens](hololens-network.md#vpn).
- Pour plus d’informations sur les profils VPN, consultez le [CSP VPNv2](/windows/client-management/mdm/vpnv2-csp).

### <a name="deploy-and-manage-apps"></a>Déployer et gérer des applications
À l’aide d’Intune, vous pouvez ajouter des applications aux appareils exécutant Windows Holographic for Business. Une solution de gestion des appareils mobiles permet aux décideurs informatiques et aux administrateurs d’installer automatiquement (push) leurs applications métier internes ou d’acheter des applications dans le Store pour un groupe d’utilisateurs. Il existe plusieurs façons de déployer des applications. Par exemple, vous pouvez :
-   [Intune et Portail d’entreprise]( app-deploy-intune.md)
-   [Microsoft Store pour Entreprises]( app-deploy-store-business.md)

En savoir plus sur la gestion des applications par le biais d’Intune.
-   [Ajouter des applications à Intune](/mem/intune/apps/apps-add)
-   [Ajouter des applications Microsoft Store](/mem/intune/apps/store-apps-windows)
-   [Ajouter des applications que vous créez](/mem/intune/apps/lob-apps-windows)
- [Affecter des applications à des groupes](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Mises à jour logicielles
Intune inclut une fonctionnalité appelée anneaux de mise à jour pour les appareils Windows 10. Ces anneaux de mise à jour comportent un groupe de paramètres qui déterminent l’installation des mises à jour. Par exemple, vous pouvez créer une fenêtre de maintenance pour installer les mises à jour, ou choisir de redémarrer l’appareil après l’installation des mises à jour. Vous pouvez appliquer un anneau de mise à jour à plusieurs appareils exécutant Windows Holographic for Business.
en savoir plus sur la [gestion des mises à jour HoloLens](hololens-updates.md) et la [gestion des mises à jour logicielles via Intune](/mem/intune/protect/windows-update-for-business-configure).

### <a name="configure-kiosk-mode"></a>Configurer le mode kiosque
Avec les fonctionnalités de PC partagé ou invité qui sont disponibles dans Intune, vous pouvez configurer les appareils Windows Holographic for Business pour qu’ils s’exécutent en mode kiosque. Ces appareils peuvent exécuter une seule application (mode kiosque mono-application) ou plusieurs applications (mode kiosque multi-application). Le mode plein écran est une interface utilisateur qui permet de contrôler les identités qui ont accès aux applications par défaut.
découvrez comment [configurer HoloLens en tant que kiosque]( hololens-kiosk.md)

