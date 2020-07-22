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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883148"
---
# <span data-ttu-id="ced94-104">Connecter HoloLens à un réseau</span><span class="sxs-lookup"><span data-stu-id="ced94-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="ced94-105">Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau.</span><span class="sxs-lookup"><span data-stu-id="ced94-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="ced94-106">Ce guide va vous aider:</span><span class="sxs-lookup"><span data-stu-id="ced94-106">This guide will help you:</span></span>

- <span data-ttu-id="ced94-107">Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C</span><span class="sxs-lookup"><span data-stu-id="ced94-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="ced94-108">Désactiver et réactiver le Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ced94-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="ced94-109">En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="ced94-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="ced94-110">Se connecter pour la première fois</span><span class="sxs-lookup"><span data-stu-id="ced94-110">Connecting for the first time</span></span>

<span data-ttu-id="ced94-111">Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ced94-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="ced94-112">Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif.</span><span class="sxs-lookup"><span data-stu-id="ced94-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="ced94-113">Vérifiez que vous n’avez pas besoin d’utiliser un certificat pour vous connecter au réseau.</span><span class="sxs-lookup"><span data-stu-id="ced94-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="ced94-114">Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ced94-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="ced94-115">Connexion à un réseau Wi-Fi après l’installation</span><span class="sxs-lookup"><span data-stu-id="ced94-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="ced94-116">Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="ced94-116">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="ced94-117">L’application Paramètres sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="ced94-117">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ced94-118">Sélectionnez **Réseau et Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="ced94-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="ced94-119">Vérifiez que le Wi-Fi est activé.</span><span class="sxs-lookup"><span data-stu-id="ced94-119">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="ced94-120">Si vous ne voyez pas votre réseau, faites défiler la liste.</span><span class="sxs-lookup"><span data-stu-id="ced94-120">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="ced94-121">Sélectionnez un réseau, puis **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="ced94-121">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="ced94-122">Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ced94-122">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="ced94-123">HoloLens est muni d'une option Wi-Fi 2x2, compatible 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="ced94-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="ced94-124">La connexion de HoloLens à un réseau Wi-Fi est semblable à la connexion d’un ordinateur de bureau ou d’un appareil mobile Windows10 à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ced94-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Paramètres Wi-Fi HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="ced94-126">Vous pouvez également confirmer que vous êtes connecté à un réseau Wi-Fi en vérifiant l’état du Wi-Fi dans le menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="ced94-126">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="ced94-127">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="ced94-127">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ced94-128">Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ced94-128">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="ced94-129">L’état du Wi-Fi et le SSID du réseau connecté sont affichés.</span><span class="sxs-lookup"><span data-stu-id="ced94-129">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="ced94-130">Résolution des problèmes de connexion à la Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ced94-130">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="ced94-131">Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="ced94-131">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="ced94-132">Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="ced94-132">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="ced94-133">VPN</span><span class="sxs-lookup"><span data-stu-id="ced94-133">VPN</span></span>
<span data-ttu-id="ced94-134">Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet.</span><span class="sxs-lookup"><span data-stu-id="ced94-134">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="ced94-135">HoloLens2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP).</span><span class="sxs-lookup"><span data-stu-id="ced94-135">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="ced94-136">Protocoles VPN intégrés pris en charge:</span><span class="sxs-lookup"><span data-stu-id="ced94-136">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="ced94-137">IKEv2</span><span class="sxs-lookup"><span data-stu-id="ced94-137">IKEv2</span></span>
- <span data-ttu-id="ced94-138">L2TP</span><span class="sxs-lookup"><span data-stu-id="ced94-138">L2TP</span></span>
- <span data-ttu-id="ced94-139">PPTP</span><span class="sxs-lookup"><span data-stu-id="ced94-139">PPTP</span></span>

<span data-ttu-id="ced94-140">Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ced94-140">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="ced94-141">Pour déterminer si un plug-in VPN tiers prend en charge HoloLens2, accédez à Store pour trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="ced94-141">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="ced94-142">HoloLens ne prend en charge que les applications de plateforme Windows universelles pour les VPN tiers.</span><span class="sxs-lookup"><span data-stu-id="ced94-142">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="ced94-143">Le VPN n’est pas activé par défaut, mais vous pouvez l’activer manuellement en ouvrant l’application **Paramètres**, puis et en accédant à **Réseau et Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="ced94-143">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="ced94-144">Vous pouvez gérer le VPN par GPM via [Paramètres/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), puis le définir via [Vpnv2-stratégie csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="ced94-144">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="ced94-145">Si vous souhaitez en savoir plus sur [la configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn), veuillez consulter [ces guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="ced94-145">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="ced94-146">Désactivation de Wi-Fi sur HoloLens (1regénération)</span><span class="sxs-lookup"><span data-stu-id="ced94-146">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="ced94-147">Utilisation de l’application Paramètres sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="ced94-147">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="ced94-148">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="ced94-148">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ced94-149">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="ced94-149">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="ced94-150">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="ced94-150">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ced94-151">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="ced94-151">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="ced94-152">Sélectionnez le curseur Wi-Fi pour le placer en position **Désactivé** .</span><span class="sxs-lookup"><span data-stu-id="ced94-152">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="ced94-153">Cette opération désactive les composants RF de la radio Wi-Fi et toutes les fonctionnalités Wi-Fi sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ced94-153">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="ced94-154">Lorsque la radio Wi-Fi est désactivée, HoloLens ne peut pas charger automatiquement vos [espaces](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="ced94-154">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="ced94-155">Positionnez le curseur en position **Activé** pour allumer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ced94-155">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="ced94-156">L’état de l’option Wi-Fi sélectionné (**Activé** ou **Désactivé**) sera conservé en cas de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="ced94-156">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="ced94-157">Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ced94-157">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="ced94-158">À l’aide de l’application Paramètres</span><span class="sxs-lookup"><span data-stu-id="ced94-158">By using the Settings app</span></span>

1. <span data-ttu-id="ced94-159">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="ced94-159">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ced94-160">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="ced94-160">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="ced94-161">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="ced94-161">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ced94-162">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="ced94-162">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="ced94-163">Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.</span><span class="sxs-lookup"><span data-stu-id="ced94-163">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="ced94-165">L’adresse IP apparaît en regard de **adresse IPv4**.</span><span class="sxs-lookup"><span data-stu-id="ced94-165">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="ced94-166">Via des commandes vocales</span><span class="sxs-lookup"><span data-stu-id="ced94-166">By using voice commands</span></span>

<span data-ttu-id="ced94-167">En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="ced94-167">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="ced94-168">Sur les builds ultérieures à la [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) demandez «quelle est mon adresse IP?»</span><span class="sxs-lookup"><span data-stu-id="ced94-168">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="ced94-169">Celle-ci s’affiche alors.</span><span class="sxs-lookup"><span data-stu-id="ced94-169">and it will be displayed.</span></span> <span data-ttu-id="ced94-170">Sur les builds antérieures ou sur HoloLens (1ère génération), dites «Hey Cortana, quelle est mon adresse IP?»</span><span class="sxs-lookup"><span data-stu-id="ced94-170">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="ced94-171">Cortana afficher et lit votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="ced94-171">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="ced94-172">À l’aide du Portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="ced94-172">By using Windows Device Portal</span></span>

1. <span data-ttu-id="ced94-173">Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="ced94-173">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="ced94-174">Accédez à la section **Réseaux**.</span><span class="sxs-lookup"><span data-stu-id="ced94-174">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="ced94-175">Cette section contient votre adresse IP et d’autres informations sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="ced94-175">This section displays your IP address and other network information.</span></span> <span data-ttu-id="ced94-176">En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.</span><span class="sxs-lookup"><span data-stu-id="ced94-176">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
