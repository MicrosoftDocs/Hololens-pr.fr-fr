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
ms.openlocfilehash: 734176dcf8a789f130aa8b010f5f3c9ec1d22c72
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857792"
---
# <span data-ttu-id="30037-104">Connecter HoloLens à un réseau</span><span class="sxs-lookup"><span data-stu-id="30037-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="30037-105">Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau.</span><span class="sxs-lookup"><span data-stu-id="30037-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="30037-106">Ce guide va vous aider:</span><span class="sxs-lookup"><span data-stu-id="30037-106">This guide will help you:</span></span>

- <span data-ttu-id="30037-107">Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C</span><span class="sxs-lookup"><span data-stu-id="30037-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="30037-108">Désactiver et réactiver le Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="30037-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="30037-109">En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="30037-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="30037-110">Se connecter pour la première fois</span><span class="sxs-lookup"><span data-stu-id="30037-110">Connecting for the first time</span></span>

<span data-ttu-id="30037-111">Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="30037-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="30037-112">Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif.</span><span class="sxs-lookup"><span data-stu-id="30037-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="30037-113">Vérifiez que vous n’avez pas besoin d’utiliser un certificat pour vous connecter au réseau.</span><span class="sxs-lookup"><span data-stu-id="30037-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="30037-114">Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="30037-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="30037-115">Connexion à un réseau Wi-Fi après l’installation</span><span class="sxs-lookup"><span data-stu-id="30037-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="30037-116">Sélectionnez **Démarrer** > **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="30037-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="30037-117">*HoloLens (1re génération) uniquement*: utilisez le pointage de votre regard pour positionner l’application Paramètres, puis faites un clic aérien pour la placer ou dire «Placer».</span><span class="sxs-lookup"><span data-stu-id="30037-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="30037-118">Sélectionnez **Réseau et Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="30037-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="30037-119">Si vous ne voyez pas votre réseau, faites défiler la liste.</span><span class="sxs-lookup"><span data-stu-id="30037-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="30037-120">Sélectionnez un réseau, puis **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="30037-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="30037-121">Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30037-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="30037-122">Connexion au Wi-Fi sur HoloLens (1re génération)</span><span class="sxs-lookup"><span data-stu-id="30037-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="30037-123">HoloLens est muni d'une option Wi-Fi 2x2, compatible 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="30037-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="30037-124">La connexion de HoloLens à un réseau Wi-Fi est semblable à la connexion d’un ordinateur de bureau ou d’un appareil mobile Windows10 à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="30037-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Paramètres Wi-Fi HoloLens](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="30037-126">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="30037-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="30037-127">Sélectionnez l’application Paramètres dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="30037-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="30037-128">L’application Paramètres sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="30037-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="30037-129">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="30037-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="30037-130">Vérifiez que le Wi-Fi est activé.</span><span class="sxs-lookup"><span data-stu-id="30037-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="30037-131">Sélectionnez un réseau Wi-Fi dans la liste.</span><span class="sxs-lookup"><span data-stu-id="30037-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="30037-132">Le cas échéant, entrez le mot de passe du réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="30037-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="30037-133">Vous pouvez également confirmer que vous êtes connecté à un réseau Wi-Fi en vérifiant l’état du Wi-Fi dans le menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="30037-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="30037-134">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="30037-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="30037-135">Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="30037-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="30037-136">L’état du Wi-Fi et le SSID du réseau connecté sont affichés.</span><span class="sxs-lookup"><span data-stu-id="30037-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="30037-137">Résolution des problèmes de connexion à la Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="30037-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="30037-138">Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="30037-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="30037-139">Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="30037-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="30037-140">Désactivation de Wi-Fi sur HoloLens (1regénération)</span><span class="sxs-lookup"><span data-stu-id="30037-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="30037-141">Utilisation de l’application Paramètres sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="30037-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="30037-142">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="30037-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="30037-143">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="30037-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="30037-144">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="30037-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="30037-145">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="30037-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="30037-146">Sélectionnez le curseur Wi-Fi pour le placer en position **Désactivé** .</span><span class="sxs-lookup"><span data-stu-id="30037-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="30037-147">Cette opération désactive les composants RF de la radio Wi-Fi et toutes les fonctionnalités Wi-Fi sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="30037-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="30037-148">Lorsque la radio Wi-Fi est désactivée, HoloLens ne peut pas charger automatiquement vos [espaces](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="30037-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="30037-149">Positionnez le curseur en position **Activé** pour allumer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="30037-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="30037-150">L’état de l’option Wi-Fi sélectionné (**Activé** ou **Désactivé**) sera conservé en cas de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="30037-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="30037-151">Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="30037-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="30037-152">À l’aide de l’application Paramètres</span><span class="sxs-lookup"><span data-stu-id="30037-152">By using the Settings app</span></span>

1. <span data-ttu-id="30037-153">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="30037-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="30037-154">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="30037-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="30037-155">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="30037-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="30037-156">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="30037-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="30037-157">Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.</span><span class="sxs-lookup"><span data-stu-id="30037-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="30037-159">L’adresse IP apparaît en regard de **adresse IPv4**.</span><span class="sxs-lookup"><span data-stu-id="30037-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="30037-160">À l’aide de Cortana</span><span class="sxs-lookup"><span data-stu-id="30037-160">By using Cortana</span></span>

<span data-ttu-id="30037-161">Dites «Hey Cortana, quelle est mon adresseIP?».</span><span class="sxs-lookup"><span data-stu-id="30037-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="30037-162">Cortana afficher et lit votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="30037-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="30037-163">À l’aide du Portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="30037-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="30037-164">Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="30037-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="30037-165">Accédez à la section **Réseaux**.</span><span class="sxs-lookup"><span data-stu-id="30037-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="30037-166">Cette section contient votre adresse IP et d’autres informations sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="30037-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="30037-167">En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.</span><span class="sxs-lookup"><span data-stu-id="30037-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
