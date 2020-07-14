---
title: Questions de sécurité fréquemment posées
description: questions de sécurité fréquemment posées sur Hololens
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, sécurité
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: high
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: dc9223c2ef7e57c457f4f8a653d7fdeedbc2f2f9
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865709"
---
# Questions de sécurité fréquemment posées sur HoloLens (1ère génération)

1. **Quel niveau de protection des données offre HoloLens 1?**
    1. Voir [Chiffrement BitLocker HoloLens (1ère génération)](hololens1-encryption.md)
1. **Quel est le type de connexion sans fil utilisé?**
    1. 802.11 AC et Bluetooth 4,1 LE
1. **Quel type d’architecture est inclus?  Par exemple: point à point, maillage ou autre?**
    1. Wi-Fi peut être utilisé en mode infrastructure pour communiquer avec d’autres points d’accès sans fil.
    1. Bluetooth peut être utilisé pour parler à l’hôte entre plusieurs HoloLens si l’application cliente la prend en charge ou sur d’autres appareils Bluetooth.
1. **Qu’est-ce que la FCC ID?**
    1. C3K1688
1. **Sur quelle plage de fréquence et quels canaux l’appareil fonctionne-t-il? il peut-il être configuré?**
    1. Wi-Fi: la plage de périodicité ne peut pas être configurée par l’utilisateur et dépend du pays d’utilisation. Au Wi-Fi, Wi-Fi utilise les canaux 2,4 GHz (1-11) et 5 GHz (36-64 100-165).
    1. Bluetooth: Bluetooth utilise la plage standard 2,4-2.48 GHz.
1. **L’appareil peut-il autoriser ou bloquer des fréquences spécifiques?**
    1. Cette opération n’est pas contrôlable par l’utilisateur/l’appareil.
1. **Quel est le niveau de puissance pour la transmission et la réception? Est-elle réglable? Quelle est la plage de l’opération?**
    1. Nos normes de test des émissions sont accessibles [ici](https://fccid.io/C3K1688). L’étendue de l’opération est fortement dépendante du point d’accès et de l’environnement, mais elle est à peu près équivalente à d’autres téléphones, tablettes ou PC de haute qualité.
1. **Quel est le cycle d’utilisation ou la durée de vie d’un fonctionnement normal?**
    1. 2 à 3heures d’utilisation active et jusqu’à 2 semaines de temps de veille
    1. La durée de vie de la batterie n’est pas disponible.
1. **Qu’est-ce que le comportement de transmission et de réception lorsqu’un outil n’est pas dans la plage?**
    1. La transmission/réception HoloLens suit le modèle standard Wi-Fi/Bluetooth. Au bord de la plage, vous remarquerez probablement la saisie de données hachées jusqu’à ce qu’elle se déconnecte complètement, mais une fois que vous êtes revenu dans la plage, elle devrait se reconnecter rapidement.
1. **Qu’est-ce que la densité de déploiement par mètre carré?**
    1. Cela dépend de votre infrastructure réseau.
1. **L’appareil peut-il utiliser l’infrastructure en tant que client?**
    1. Oui
1. **Quel protocole est utilisé?**
    1. HoloLens n’utilise pas de protocoles propriétaires
1. **Fréquence de mise à jour du système d’exploitation: quelle est la fréquence des mises à jour du système d’exploitation pour HL?  Y a-t-il une planification fixe?  Microsoft publie-t-il des correctifs de sécurité selon les besoins, etc.**
    1. Microsoft fournit des mises à jour de système d’exploitation à HoloLens exactement de la même façon que pour Windows 10. Il y a normalement deux mises à jour majeures par an, une au printemps, une à l'automne. Comme HoloLens est un appareil Windows, le concept de mise à jour est le même que pour tout autre appareil Windows. Microsoft publie les correctifs de sécurité selon les besoins et suit le même concept que pour tout autre appareil Windows.
1. **Renforcement des systèmes d’exploitation: Quelles sont les options disponibles pour renforcer le système d’exploitation?  Est-il possible de supprimer ou d’arrêter les applications ou services inutiles?**
    1. HoloLens se comporte comme un smartphone. Il est comparable à d’autres appareils Windows modernes. HoloLens peut être géré par Microsoft Intune ou d'autres solutions modernes de gestion des appareils, comme MobileIron, Airwatch ou Soti. Vous pouvez définir certaines stratégies dans ces systèmes de gestion afin de placer les stratégies de sécurité sur l’appareil et de renforcer l’appareil. Il existe également la possibilité de supprimer les applications inutiles si vous le souhaitez.
1. **Comment les applications logicielles seront-elles gérées et mises à jour? Quel contrôle avons-nous pour définir quelles applications sont chargées et processus de mise à jour des applications qui vivent dans la boutique Microsoft?**
    1. HoloLens obtient les applications logicielles uniquement via le Windows Store. Seuls les packages d’applications AppX peuvent être installés et développés pour l’utilisation de HoloLens. Vous pouvez le voir dans le Microsoft Store avec un petit logo à côté de l'application qui montre l'appareil HoloLens. Tout contrôle que vous avez sur les applications de gestion des magasins s’applique également à HoloLens. Vous pouvez utiliser le concept de magasin officiel ou de magasin pour les entreprises. Les applications peuvent soit être chargées en version test (processus manuel de chargement d’une application sur un appareil Windows), soit gérées via une GPM, afin que les applications soient automatiquement extraites du magasin en cas de besoin.
1. **Quelle est la fréquence des mises à jour apportées aux applications au magasin pour HoloLens?**
    1. Comme nous avons suivi le même concept du Microsoft Store et extrait les applications à partir de cet emplacement, le cycle de mise à jour est déterminé par le développeur de l’application. Toutes les options de gestion dont vous avez besoin pour contrôler le mécanisme de mise à jour au magasin s’appliquent également à HoloLens.
1. **Y a-t-il une fonctionnalité de démarrage sécurisé pour HoloLens?**
    1. Oui
1. **Y a-t-il une possibilité de désactiver ou de déconnecter la prise en charge de périphériques de l’appareil?**
    1. Oui
1. **Y a-t-il une possibilité de contrôler ou de désactiver l’utilisation des ports sur l’appareil?**
    1. Le HoloLens ne contient que 2 ports (un pour les écouteurs et un pour charger ou se connecter aux PC). Il n'est pas possible de désactiver le port pour des raisons de fonctionnalité et de récupération.
1. **Antivirus, détection de point de terminaison, IPS, liste verte de contrôle d’application: possibilité d’exécuter des antivirus, détection de point de terminaison, IPS, liste verte de contrôle d’application, etc.**
    1. Windows Holographic for Business (suite commerciale) prend en charge l’écran intelligent Windows Defender. Si un fournisseur de logiciels antivirus a créé et publié son application sur la plateforme Windows universelle, il pourrait être téléchargé sur HoloLens. Pour l’instant, aucune société n’a effectué cette opération pour HoloLens.
    1. Autoriser les applications est possible en utilisant le Microsoft Enterprise Store, où vous pouvez choisir uniquement quelles applications spécifiques peuvent être téléchargées. De plus, grâce à la GPM, vous pouvez verrouiller les applications spécifiques qui peuvent être exécutées ou même vues sur l'appareil.
1. **Pouvons-nous mettre en quarantaine l'appareil du réseau prod jusqu'à ce que nous mettions à jour l'appareil s'il a été hors ligne pendant une longue période?  P.ex. L’appareil est dans un tiroir et n’a pas été mis sous tension pendant une période (de 6 mois) et n’a pas reçu de mises à jour, de correctifs, etc.  Lorsqu’il tente de se connecter au réseau, nous pouvons le marquer et dire que vous devez effectuer une mise à jour sur un autre réseau avant d'être conforme à rejoindre le réseau.**
    1. Il s’agit d’une opération qui peut être gérée au niveau de l’infrastructure par le biais d’un serveur GPM ou local. L’appareil peut être marqué comme non conforme s’il ne remplit pas une version de mise à jour spécifiée.
1. **Est-ce que Microsoft inclut les portes dérobées ou l’accès aux services qui permet à Microsoft de se connecter à l’appareil pour le partage d’écran ou le support distantà volonté?**
    1. Non
1. **Lorsqu’un certificat PKI est généré pour la communication approuvée, nous voulons que le certificat soit généré sur l’appareil. Nous saurons ainsi qu’il est uniquement sur cet appareil, qu’il est propre à cet appareil, et qu’il ne peut être ni exporté, ni utilisé pour usurper l’identité de l’appareil. Est-ce vrai sur HoloLens? Sinon, existe-t-il une solution potentielle?**
    1. Le CSR pour SCEP est généré sur l’appareil lui-même. Intune et le connecteur SCEP local sécurisent les demandes en ajoutant et en vérifiant une chaîne de test envoyée au client.
    1. Dans la mesure où HoloLens (1ère génération et 2e génération) possèdent un module TPM, ces certificats sont stockés dans le module TPM et ne peuvent pas être extraits. De plus, même si cela peut être extrait, les chaînes de test n’ont pas pu être vérifiées sur un autre appareil, ce qui rend les certificats/clés inutilisables sur différents appareils.
