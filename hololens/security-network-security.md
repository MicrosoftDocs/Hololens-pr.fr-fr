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
ms.openlocfilehash: c88a9af7369a6a9d6fb115fb820c0a4da13eafdc
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865742"
---
# <span data-ttu-id="f84cf-104">Sécurité du réseau</span><span class="sxs-lookup"><span data-stu-id="f84cf-104">Network security</span></span>

## <span data-ttu-id="f84cf-105">Protocoles réseau</span><span class="sxs-lookup"><span data-stu-id="f84cf-105">Network protocols</span></span>

<span data-ttu-id="f84cf-106">Le NetBIOS obsolète (network basic input/output system) a été largement utilisé dans les précédents scénarios dans le réseau local, souvent pour fournir une résolution de noms vers un ordinateur et des dossiers partagés.</span><span class="sxs-lookup"><span data-stu-id="f84cf-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="f84cf-107">Au fil du temps, NetBIOS a prouvé qu’il était exposé à plusieurs attaques, et sa pertinence a diminué au profit d’autres protocoles plus sécurisés.</span><span class="sxs-lookup"><span data-stu-id="f84cf-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="f84cf-108">Pour écarter ce problème de vulnérabilité, HoloLense2 a éliminé du système d’exploitation le code relatif à NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="f84cf-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="f84cf-109">Les protocolesTLS (Transport Layer Security) évoluent constamment.</span><span class="sxs-lookup"><span data-stu-id="f84cf-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="f84cf-110">Pour tenir compte des différentes attaques de sécurité qui ont été découvertes dans ce domaine, l’industrie de l’informatique a découvert des versions plus récentes et plus efficaces.</span><span class="sxs-lookup"><span data-stu-id="f84cf-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="f84cf-111">En raison du délai nécessaire à l’adoption des nouvelles versions du protocoleTLS par tous les déploiements de serveur, un mécanisme de secours peut être implémenté pour permettre au client et aux serveurs sur différentes versions de protocole par défaut de continuer à communiquer pendant la période de transition.</span><span class="sxs-lookup"><span data-stu-id="f84cf-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

<span data-ttu-id="f84cf-112">Toutefois, ces mécanismes de secours augmentent les risques de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f84cf-112">However, such fallback mechanisms increase security risks.</span></span> <span data-ttu-id="f84cf-113">En comprenant ce problème, dans HoloLens2, le basculement de TLS1,2 à TLS1,1 ou1,0 a été désactivé et aucune interface utilisateur n’est disponible pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="f84cf-113">Understanding this issue, in HoloLens 2 the fallback from TLS 1.2 to TLS 1.1 or 1.0 has been disabled, and there is no user interface to enable it.</span></span> <span data-ttu-id="f84cf-114">Par ailleurs, lors de la liaison TLS, le client demande la connexion TLS1,2 et ne permet pas au serveur d’effectuer une mise à niveau vers une version inférieure.</span><span class="sxs-lookup"><span data-stu-id="f84cf-114">Furthermore, during the TLS handshake, the client will ask for TLS 1.2, and does not allow the server to downgrade to a lower version.</span></span>

## <span data-ttu-id="f84cf-115">Une connectivité sécurisée</span><span class="sxs-lookup"><span data-stu-id="f84cf-115">Secure connectivity</span></span> 

<span data-ttu-id="f84cf-116">Le pare-feu WidowsDefender fournit une fonctionnalité capitale pour sécuriser la connectivité des appareils.</span><span class="sxs-lookup"><span data-stu-id="f84cf-116">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="f84cf-117">Avec HoloLens2, le pare-feu est toujours activé et il n’y a aucun moyen de le désactiver par programme ou par le biais de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f84cf-117">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="f84cf-118">L’accès à distance et la confidentialité de connexion pour les clients mobile est assuré par la [plateforme de plug-in VPNUWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="f84cf-118">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="f84cf-119">Les fournisseursVPN tiers peuvent créer leurs propres plug-ins à l’aide des APIWinRT qui s’exécutent dans le bac à sable d’AppContainer, ce qui élimine la complexité et les problèmes souvent associés à l’écriture de pilotes au niveau du système.</span><span class="sxs-lookup"><span data-stu-id="f84cf-119">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
