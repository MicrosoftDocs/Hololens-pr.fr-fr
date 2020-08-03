---
title: Sécurité du réseau
description: sécurité du réseau
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, réseau, sécurité du réseau
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 147401331cb6da732a6fe37e57964d61a10dce99
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883138"
---
# <span data-ttu-id="2af29-104">Sécurité du réseau</span><span class="sxs-lookup"><span data-stu-id="2af29-104">Network security</span></span>

## <span data-ttu-id="2af29-105">Protocoles réseau</span><span class="sxs-lookup"><span data-stu-id="2af29-105">Network protocols</span></span>

<span data-ttu-id="2af29-106">Le NetBIOS obsolète (network basic input/output system) a été largement utilisé dans les précédents scénarios dans le réseau local, souvent pour fournir une résolution de noms vers un ordinateur et des dossiers partagés.</span><span class="sxs-lookup"><span data-stu-id="2af29-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="2af29-107">Au fil du temps, NetBIOS a prouvé qu’il était exposé à plusieurs attaques, et sa pertinence a diminué au profit d’autres protocoles plus sécurisés.</span><span class="sxs-lookup"><span data-stu-id="2af29-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="2af29-108">Pour écarter ce problème de vulnérabilité, HoloLens2 a éliminé du système d’exploitation le code relatif à NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="2af29-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="2af29-109">Les protocolesTLS (Transport Layer Security) évoluent constamment.</span><span class="sxs-lookup"><span data-stu-id="2af29-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="2af29-110">Pour tenir compte des différentes attaques de sécurité qui ont été découvertes dans ce domaine, l’industrie de l’informatique a découvert des versions plus récentes et plus efficaces.</span><span class="sxs-lookup"><span data-stu-id="2af29-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="2af29-111">En raison du délai nécessaire à l’adoption des nouvelles versions du protocoleTLS par tous les déploiements de serveur, un mécanisme de secours peut être implémenté pour permettre au client et aux serveurs sur différentes versions de protocole par défaut de continuer à communiquer pendant la période de transition.</span><span class="sxs-lookup"><span data-stu-id="2af29-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="2af29-112">Une connectivité sécurisée</span><span class="sxs-lookup"><span data-stu-id="2af29-112">Secure connectivity</span></span> 

<span data-ttu-id="2af29-113">Le pare-feu WidowsDefender fournit une fonctionnalité capitale pour sécuriser la connectivité des appareils.</span><span class="sxs-lookup"><span data-stu-id="2af29-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="2af29-114">Avec HoloLens2, le pare-feu est toujours activé et il n’y a aucun moyen de le désactiver par programme ou par le biais de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2af29-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="2af29-115">L’accès à distance et la confidentialité de connexion pour les clients mobile est assuré par la [plateforme de plug-in VPNUWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="2af29-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="2af29-116">Les fournisseursVPN tiers peuvent créer leurs propres plug-ins à l’aide des APIWinRT qui s’exécutent dans le bac à sable d’AppContainer, ce qui élimine la complexité et les problèmes souvent associés à l’écriture de pilotes au niveau du système.</span><span class="sxs-lookup"><span data-stu-id="2af29-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
