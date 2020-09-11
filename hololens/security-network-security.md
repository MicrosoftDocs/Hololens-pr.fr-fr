---
title: Sécurité du réseau
description: sécurité du réseau
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, réseau, sécurité du réseau
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009422"
---
# Sécurité du réseau

## Protocoles réseau

Le NetBIOS obsolète (network basic input/output system) a été largement utilisé dans les précédents scénarios dans le réseau local, souvent pour fournir une résolution de noms vers un ordinateur et des dossiers partagés. Au fil du temps, NetBIOS a prouvé qu’il était exposé à plusieurs attaques, et sa pertinence a diminué au profit d’autres protocoles plus sécurisés. Pour écarter ce problème de vulnérabilité, HoloLens2 a éliminé du système d’exploitation le code relatif à NetBIOS.

Les protocolesTLS (Transport Layer Security) évoluent constamment. Pour tenir compte des différentes attaques de sécurité qui ont été découvertes dans ce domaine, l’industrie de l’informatique a découvert des versions plus récentes et plus efficaces. En raison du délai nécessaire à l’adoption des nouvelles versions du protocoleTLS par tous les déploiements de serveur, un mécanisme de secours peut être implémenté pour permettre au client et aux serveurs sur différentes versions de protocole par défaut de continuer à communiquer pendant la période de transition.

## Une connectivité sécurisée 

Le pare-feu WidowsDefender fournit une fonctionnalité capitale pour sécuriser la connectivité des appareils. Avec HoloLens2, le pare-feu est toujours activé et il n’y a aucun moyen de le désactiver par programme ou par le biais de l’interface utilisateur.

L’accès à distance et la confidentialité de connexion pour les clients mobile est assuré par la [plateforme de plug-in VPNUWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Les fournisseursVPN tiers peuvent créer leurs propres plug-ins à l’aide des APIWinRT qui s’exécutent dans le bac à sable d’AppContainer, ce qui élimine la complexité et les problèmes souvent associés à l’écriture de pilotes au niveau du système.
