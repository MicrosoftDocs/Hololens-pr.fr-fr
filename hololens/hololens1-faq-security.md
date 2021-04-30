---
title: Questions fréquentes sur la sécurité
description: Restez à jour avec les questions et réponses de sécurité les plus fréquentes sur les appareils de réalité mixte HoloLens.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, sécurité
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309012"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Questions fréquentes sur la sécurité HoloLens (1re génération)

1. **Quel est le niveau de protection des données qu’offre HoloLens 1 ?**
    1. Voir [HoloLens (1re génération) chiffrement BitLocker](hololens1-encryption.md)
1. **Quel type de réseau sans fil est utilisé ?**
    1. 802.11 AC et Bluetooth 4,1
1. **Quel type d’architecture est incorporé ?  Par exemple : point à point, maillage ou autre chose ?**
    1. Wi-Fi peut être utilisé en mode infrastructure pour communiquer avec d’autres points d’accès sans fil.
    1. Bluetooth peut être utilisé pour communiquer de pair à pair entre plusieurs HoloLens si l’application du client la prend en charge ou d’autres périphériques Bluetooth.
1. **Qu’est-ce que l’ID FCC ?**
    1. C3K1688
1. **Sur quelle plage de fréquence et quels canaux l’appareil fonctionne-t-il et peut-il être configuré ?**
    1. Wi-Fi : la plage de fréquences n’est pas configurable par l’utilisateur et dépend du pays d’utilisation. Aux États-Unis Wi-Fi utilise des canaux 2,4 GHz (1-11) et 5 GHz (36-64 100-165).
    1. Bluetooth : Bluetooth utilise la plage standard de 2,4-2.48 GHz.
1. **L’appareil peut-il autoriser ou bloquer des fréquences spécifiques ?**
    1. Cela n’est pas contrôlable par l’utilisateur/appareil.
1. **Quel est le niveau de puissance pour la transmission et la réception ? Est-il réglable ? Quelle est la plage d’opérations ?**
    1. Nos normes de test des émissions se trouvent [ici](https://fccid.io/C3K1688). La plage d’opérations dépend fortement du point d’accès et de l’environnement, mais elle est à peu près équivalente à d’autres téléphones, tablettes ou PC de grande qualité.
1. **Quel est le cycle/la durée de vie d’un fonctionnement normal ?**
    1. 2-3 heures d’utilisation active et jusqu’à deux semaines de temps d’attente
    1. La durée de vie de la batterie n’est pas disponible.
1. **Qu’est-ce que le comportement de transmission et de réception lorsqu’un outil n’est pas à portée ?**
    1. La transmission/réception HoloLens suit le modèle Wi-Fi/Bluetooth standard. Au bord de sa plage, vous remarquerez probablement que l’entrée est hachée jusqu’à ce qu’elle se déconnecte complètement, mais une fois que vous êtes revenu à l’échelle, elle doit se reconnecter rapidement.
1. **Qu’est-ce que la densité de déploiement par mètre carré ?**
    1. Cela dépend de votre infrastructure réseau.
1. **L’appareil peut-il utiliser l’infrastructure en tant que client ?**
    1. Oui
1. **Quel protocole est utilisé ?**
    1. HoloLens n’utilise aucun protocole propriétaire
1. **Fréquence des mises à jour du système d’exploitation : quelle est la fréquence des mises à jour du système d’exploitation pour le niveau HL ?  Existe-t-il une planification définie ?  Les mises à jour de sécurité de Microsoft sont-elles nécessaires, etc.**
    1. Microsoft fournit des mises à jour du système d’exploitation à HoloLens exactement de la même façon que pour Windows 10. Il y a généralement deux mises à jour majeures par an, une seule dans le printemps, une en automne. Comme HoloLens est un appareil Windows, le concept de mise à jour est identique à celui d’un autre appareil Windows. Microsoft publie les correctifs de sécurité nécessaires et suit le même concept que sur n’importe quel autre appareil Windows.
1. **Renforcement du système d’exploitation : quelles options sont disponibles pour renforcer le système d’exploitation ?  Pouvez-vous supprimer ou arrêter les applications ou services inutiles ?**
    1. HoloLens se comporte comme un smartphone. Il est comparable à d’autres appareils Windows modernes. HoloLens peut être géré par Microsoft Intune ou d’autres solutions modernes de gestion des appareils, telles que MobileIron,, ou SOTI. Il existe des stratégies que vous pouvez définir dans ces systèmes de gestion pour mettre en place des stratégies de sécurité sur l’appareil et pour renforcer la sécurité de l’appareil. Vous pouvez également supprimer toutes les applications inutiles, le cas échéant.
1. **Comment les applications logicielles seront-elles gérées et mises à jour ? Quel contrôle devons-nous définir quelles sont les applications chargées et le processus de mise à jour des applications qui résident dans le Microsoft Store ?**
    1. HoloLens obtient des applications logicielles uniquement par le biais du Windows Store. Seuls les packages d’application AppX peuvent être installés, qui sont développés pour l’utilisation de HoloLens. Vous pouvez le voir dans le Microsoft Store avec un petit logo en regard de l’application qui affiche l’appareil HoloLens. Tout contrôle dont vous disposez sur la gestion des applications du Store s’applique également à HoloLens. Vous pouvez utiliser le concept du magasin officiel ou du magasin pour l’entreprise. Les applications peuvent être chargées (processus manuel pour charger une application sur un appareil Windows) ou être gérées par le biais d’un MDM afin que les applications soient automatiquement extraites du magasin en cas de besoin.
1. **Quelle est la fréquence des mises à jour des applications dans le magasin pour HoloLens ?**
    1. Au fur et à mesure que nous suivons le même concept de Microsoft Store et de l’extraction d’applications à partir de là, le cycle de mise à jour est déterminé par le développeur de l’application. Toutes les options de gestion dont vous avez besoin pour contrôler le mécanisme de mise à jour dans le magasin s’appliquent également à HoloLens.
1. **Existe-t-il une fonctionnalité de démarrage sécurisé pour HoloLens ?**
    1. Oui
1. **Est-il possible de désactiver ou de déconnecter la prise en charge des périphériques de l’appareil ?**
    1. Oui
1. **Existe-t-il une capacité de contrôle ou de désactivation de l’utilisation de ports sur l’appareil ?**
    1. Le HoloLens contient uniquement deux ports (un pour casque et un pour le chargement ou la connexion aux PC). Il n’est pas possible de désactiver le port pour des raisons de fonctionnalité et de récupération.
1. **Antivirus, détection de point de terminaison, IP, liste verte de contrôle d’application : toute possibilité d’exécuter l’antivirus, la détection de point de terminaison, les adresses IP, la liste verte d’application Control, etc.**
    1. Windows holographique for Business (suite commerciale) prend en charge l’écran Windows Defender intelligent. Si une société d’antivirus devait créer et publier son application sur le plateforme Windows universelle, elle peut être téléchargée sur HoloLens. À l’heure actuelle, aucune entreprise n’a effectué cette opération pour HoloLens.
    1. Il est possible d’autoriser les applications à l’aide de Microsoft Enterprise Store, où vous pouvez choisir uniquement les applications spécifiques qui peuvent être téléchargées. En outre, grâce à MDM, vous pouvez verrouiller les applications spécifiques qui peuvent être exécutées ou même affichées sur l’appareil.
1. **Pouvons-nous mettre l’appareil en quarantaine à partir du réseau de production jusqu’à ce que nous ayons mis à jour l’appareil s’il est hors connexion pendant une période prolongée ?  Par exemple, l’appareil est assis dans un tiroir qui n’a pas été mis sous tension pendant une période (six mois) et n’a reçu aucune mise à jour, aucun correctif, etc.  En cas de tentative de mise sur le réseau, pouvons-nous le marquer et indiquer que vous devez mettre à jour sur un autre réseau avant d’être interrogé pour rejoindre le réseau.**
    1. Il s’agit d’une opération qui peut être gérée au niveau de l’infrastructure par le biais d’un serveur MDM ou local. L’appareil peut être marqué comme non conforme s’il ne correspond pas à une version de mise à jour spécifiée.
1. **Microsoft inclut-il des portes back ou un accès à des services qui permet à Microsoft de se connecter à l’appareil pour le partage d’écran ou le support à distance ?**
    1. Non
1. **Quand un certificat d’infrastructure à clé publique est généré pour la communication approuvée, nous voulons que le certificat soit généré sur l’appareil afin que nous sachions qu’il se trouve uniquement sur cet appareil, propre à cet appareil, et qu’il ne peut pas être exporté ou utilisé pour emprunter l’identité de l’appareil. Cette valeur est-elle vraie sur HoloLens ? Si ce n’est pas le cas, existe-t-il une atténuation potentielle ?**
    1. Le CSR pour SCEP est généré sur l’appareil lui-même. Intune et le connecteur SCEP sur site permettent de sécuriser les requêtes elles-mêmes en ajoutant et en vérifiant une chaîne de stimulation envoyée au client.
    1. Dans la mesure où HoloLens (1er génération et 2e génération) possèdent un module TPM, ces certificats sont stockés dans le module TPM et ne peuvent pas être extraits. En outre, même s’il peut être extrait, les chaînes de stimulation n’ont pas pu être vérifiées sur un autre appareil, ce qui rend inutilisables les certificats/la clé sur des appareils différents.
