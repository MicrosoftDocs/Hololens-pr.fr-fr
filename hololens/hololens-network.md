---
title: Se connecter à un réseau
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828418"
---
# Se connecter à un réseau

Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau. Ce guide va vous aider:

- Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C
- Désactiver et réactiver le Wi-Fi

En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).

## Se connecter pour la première fois

Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi. Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif. Vérifiez que vous n’avez pas besoin d’utiliser un certificat pour vous connecter au réseau. Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.

## Connexion à un réseau Wi-Fi après l’installation

1. Sélectionnez **Démarrer** > **Paramètres**.
   - *HoloLens (1re génération) uniquement*: utilisez le pointage de votre regard pour positionner l’application Paramètres, puis faites un clic aérien pour la placer ou dire «Placer».
1. Sélectionnez **Réseau et Internet** > **Wi-Fi**. Si vous ne voyez pas votre réseau, faites défiler la liste.
1. Sélectionnez un réseau, puis **Connecter**.
1. Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.

## Connexion au Wi-Fi sur HoloLens (1re génération)

HoloLens est muni d'une option Wi-Fi 2x2, compatible 802.11ac. La connexion de HoloLens à un réseau Wi-Fi est semblable à la connexion d’un ordinateur de bureau ou d’un appareil mobile Windows10 à un réseau Wi-Fi.

![Paramètres Wi-Fi HoloLens](./images/wifi-hololens-600px.jpg)

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application Paramètres dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer** . L’application Paramètres sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet**.
1. Vérifiez que le Wi-Fi est activé.
1. Sélectionnez un réseau Wi-Fi dans la liste.
1. Le cas échéant, entrez le mot de passe du réseau Wi-Fi.

Vous pouvez également confirmer que vous êtes connecté à un réseau Wi-Fi en vérifiant l’état du Wi-Fi dans le menu **Démarrer** .

1. Ouvrez le menu **Démarrer**.
1. Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi. L’état du Wi-Fi et le SSID du réseau connecté sont affichés.

## Résolution des problèmes de connexion à la Wi-Fi

Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.

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

### À l’aide de Cortana

Dites «Hey Cortana, quelle est mon adresseIP?». Cortana afficher et lit votre adresse IP.

### À l’aide du Portail d’appareil Windows

1. Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Accédez à la section **Réseaux**.  
   Cette section contient votre adresse IP et d’autres informations sur le réseau. En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.
