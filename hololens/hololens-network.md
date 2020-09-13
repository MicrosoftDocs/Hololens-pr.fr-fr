---
title: Connecter HoloLens à un réseau
description: Instructions sur la connexion à Internet avec HoloLens et procédure d’identification de l’adresse IP de l’appareil.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, sans fil, Internet, ip, adresse ip
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009522"
---
# Connecter HoloLens à un réseau

Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau. Ce guide va vous aider:

- Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C
- Désactiver et réactiver le Wi-Fi

En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).

## Se connecter pour la première fois

Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi. Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif. Vérifiez que vous n’avez pas besoin d’utiliser un certificat pour vous connecter au réseau. Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.

Sur les appareils HoloLens 2, un utilisateur peut également [utiliser une carte USB-C vers Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pour se connecter directement au Wi-Fi afin de vous aider à configurer l’appareil. Une fois l’appareil configuré, l’utilisateur peut continuer à utiliser la carte ou il peut déconnecter l’appareil de la carte et [se connecter au Wi-Fi après avoir configuré](hololens-network.md#connecting-to-wi-fi-after-setup). 

## Connexion à un réseau Wi-Fi après l’installation

1. Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**. L’application Paramètres sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet** > **Wi-Fi**. Vérifiez que le Wi-Fi est activé. Si vous ne voyez pas votre réseau, faites défiler la liste.
1. Sélectionnez un réseau, puis **Connecter**.
1. Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.

HoloLens est muni d'une option Wi-Fi 2x2, compatible 802.11ac. La connexion de HoloLens à un réseau Wi-Fi est semblable à la connexion d’un ordinateur de bureau ou d’un appareil mobile Windows10 à un réseau Wi-Fi.

![Paramètres Wi-Fi HoloLens](./images/wifi-hololens-600px.jpg)

Vous pouvez également confirmer que vous êtes connecté à un réseau Wi-Fi en vérifiant l’état du Wi-Fi dans le menu **Démarrer** .

1. Ouvrez le menu **Démarrer**.
1. Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi. L’état du Wi-Fi et le SSID du réseau connecté sont affichés.

## Résolution des problèmes de connexion à la Wi-Fi

Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.

## VPN
Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet. HoloLens2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP). 

Protocoles VPN intégrés pris en charge:
- IKEv2
- L2TP
- PPTP

Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur. Pour déterminer si un plug-in VPN tiers prend en charge HoloLens2, accédez à Store pour trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64. HoloLens ne prend en charge que les applications de plateforme Windows universelles pour les VPN tiers.

Le VPN n’est pas activé par défaut, mais vous pouvez l’activer manuellement en ouvrant l’application **Paramètres**, puis et en accédant à **Réseau et Internet -> VPN**. Vous pouvez gérer le VPN par GPM via [Paramètres/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), puis le définir via [Vpnv2-stratégie csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).
Si vous souhaitez en savoir plus sur [la configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn), veuillez consulter [ces guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

## Désactivation de Wi-Fi sur HoloLens (1regénération)

### Utilisation de l’application Paramètres sur HoloLens

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet**.
1. Sélectionnez le curseur Wi-Fi pour le placer en position **Désactivé** . Cette opération désactive les composants RF de la radio Wi-Fi et toutes les fonctionnalités Wi-Fi sur HoloLens.

    > [!WARNING]
    > Lorsque la radio Wi-Fi est désactivée, HoloLens ne peut pas charger automatiquement vos [espaces](hololens-spaces.md).

1. Positionnez le curseur en position **Activé** pour allumer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens. L’état de l’option Wi-Fi sélectionné (**Activé** ou **Désactivé**) sera conservé en cas de redémarrage.

## Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi

### À l’aide de l’application Paramètres

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet**.
1. Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   L’adresse IP apparaît en regard de **adresse IPv4**.

### Via des commandes vocales

En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP. Sur les builds ultérieures à la [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) demandez «quelle est mon adresse IP?» Celle-ci s’affiche alors. Sur les builds antérieures ou sur HoloLens (1ère génération), dites «Hey Cortana, quelle est mon adresse IP?» Cortana afficher et lit votre adresse IP.

### À l’aide du Portail d’appareil Windows

1. Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Accédez à la section **Réseaux**.  
   Cette section contient votre adresse IP et d’autres informations sur le réseau. En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.
