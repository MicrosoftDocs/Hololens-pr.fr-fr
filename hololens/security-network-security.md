---
title: Sécurité du réseau
description: sécurité réseau
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, réseau, sécurité réseau
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640489"
---
# <a name="network-security"></a>Sécurité du réseau

## <a name="network-protocols"></a>Protocoles réseau

Le NetBIOS (Network Basic Input/Output System) désormais obsolète a été largement utilisé dans les scénarios de réseaux locaux du passé, souvent pour fournir une résolution de noms à un ordinateur et des dossiers partagés. Au fil du temps, NetBIOS a montré qu’il était exposé à plusieurs attaques, et sa pertinence a diminué au profit d’autres protocoles plus sécurisés. Pour écarter ce problème de vulnérabilité, HoloLens 2 a éliminé du système d’exploitation le code relatif à NetBIOS.

Les protocoles TLS (Transport Layer Security) évoluent constamment. Pour tenir compte des différentes attaques de sécurité qui ont été découvertes dans ce domaine, l’industrie de l’informatique a évolué vers des versions plus récentes et plus efficaces. En raison du délai nécessaire à l’adoption des nouvelles versions du protocole TLS par tous les déploiements de serveur, un mécanisme de secours peut être implémenté pour permettre au client et aux serveurs utilisant par défaut des versions différentes du protocole de continuer à communiquer pendant la période de transition.

## <a name="secure-connectivity"></a>Connectivité sécurisée 

Le pare-feu Widows Defender fournit une fonctionnalité critique pour sécuriser la connectivité des appareils. Avec HoloLens 2, le pare-feu est toujours activé et il n’y a aucun moyen de le désactiver par programmation ou via l’interface utilisateur.

La confidentialité de l’accès à distance et la connexion pour les clients mobiles est assurée via la [plateforme du plug-in VPN UWP](/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Les fournisseurs de VPN tiers peuvent créer leurs propres plug-ins en utilisant les API WinRT qui s’exécutent dans le bac à sable d’AppContainer, ce qui élimine la complexité et les problèmes souvent associés à l’écriture de pilotes au niveau du système.
