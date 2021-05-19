---
title: Connecter HoloLens à un réseau
description: Découvrez comment configurer et connecter HoloLens à internet et comment identifier l’adresse IP de l’appareil.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, sans fil, Internet, ip, adresse ip
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442589"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="a6ffd-104">Connecter HoloLens à un réseau</span><span class="sxs-lookup"><span data-stu-id="a6ffd-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="a6ffd-105">Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="a6ffd-106">HoloLens contient une radio Wi-Fi 2x2 802.11ac et permet de la connecter à un réseau de manière similaire à la connexion d’un ordinateur de bureau Windows 10 ou d’un appareil mobile à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="a6ffd-107">Ce guide peut vous aider :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-107">This guide will help you:</span></span>

- <span data-ttu-id="a6ffd-108">Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C</span><span class="sxs-lookup"><span data-stu-id="a6ffd-108">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="a6ffd-109">Désactiver et réactiver le Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a6ffd-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="a6ffd-110">En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="a6ffd-111">Se connecter pour la première fois</span><span class="sxs-lookup"><span data-stu-id="a6ffd-111">Connecting for the first time</span></span>

<span data-ttu-id="a6ffd-112">Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="a6ffd-113">Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="a6ffd-114">De plus, confirmez que le réseau ne nécessite pas de certificat pour s’y connecter.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="a6ffd-115">Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="a6ffd-116">Sur les appareils HoloLens 2, un utilisateur peut également utiliser un adaptateur [USB-C vers Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pour se connecter directement au Wi-Fi afin d’aider à la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="a6ffd-117">Une fois que l’appareil a été installé, un utilisateur peut continuer à utiliser l’adaptateur ou déconnecter l’appareil de l’adaptateur et [se connecter au Wi-Fi après avoir été installé](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="a6ffd-118">Connexion à un réseau Wi-Fi après l’installation</span><span class="sxs-lookup"><span data-stu-id="a6ffd-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="a6ffd-119">Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="a6ffd-120">L’application Paramètres sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a6ffd-121">Sélectionnez **Réseau et Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="a6ffd-122">Vérifiez que le Wi-Fi est activé.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="a6ffd-123">Si vous ne voyez pas votre réseau, faites défiler la liste.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="a6ffd-124">Sélectionnez un réseau, puis **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="a6ffd-125">Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Paramètres Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="a6ffd-127">Pour vérifier que vous êtes connecté à un réseau Wi-Fi, vérifiez l’état Wi-Fi dans le menu **Démarrage** :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="a6ffd-128">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a6ffd-129">Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="a6ffd-130">L’état du Wi-Fi et le SSID du réseau connecté sont affichés.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="a6ffd-131">Si aucun Wi-Fi n’est disponible, vous pouvez également vous [connecter aux réseaux cellulaires et 5G](https://docs.microsoft.com/hololens/hololens-cellular).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6ffd-132">Pour des raisons de conception, les utilisateurs ne peuvent pas affiner le comportement d’itinérance Wi-Fi de l’HoloLens 2. **La seule façon d’actualiser la liste Wi-Fi consiste à activer et désactiver le Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="a6ffd-133">Cela permet d’éviter de nombreux problèmes, comme lorsqu’un appareil reste bloqué sur un point d’accès hors de portée.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="a6ffd-134">Résolution des problèmes de connexion au Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a6ffd-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="a6ffd-135">Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="a6ffd-136">Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="a6ffd-137">Connecter HoloLens au réseau Wi-Fi d’entreprise</span><span class="sxs-lookup"><span data-stu-id="a6ffd-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="a6ffd-138">Les profils Wi-Fi d’entreprise utilisent le protocole d’authentification extensible (EAP) pour authentifier les connexions Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="a6ffd-139">Le profil Wi-Fi d’entreprise HoloLens peut être configuré via GPM ou un package de configuration créé par le [Concepteur de configuration Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="a6ffd-140">Pour l’appareil géré par Microsoft Intune, consultez [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) pour obtenir des instructions de configuration.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="a6ffd-141">Pour créer un package de configuration Wi-Fi dans le Concepteur de configuration Windows, un fichier .xml de profil Wi-Fi préconfiguré est requis.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="a6ffd-142">Voici un exemple de profil Wi-Fi pour WPA2-Enterprise avec authentification EAP-TLS :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="a6ffd-143">Il se peut que le certificat d’autorité de certification racine du serveur et le certificat client doivent être configurés sur l’appareil en fonction du type d’EAP.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="a6ffd-144">Ressources supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-144">Additional resources:</span></span>

- <span data-ttu-id="a6ffd-145">Schéma WLANv1Profile : [[MS-GPWL] : Schéma du profil LAN sans fil v1 | Documents Microsoft](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="a6ffd-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="a6ffd-146">Schéma EAP-TLS : [[MS-GPWL] : schéma Microsoft EAP TLS | Documents Microsoft](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="a6ffd-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <a name="eap-troubleshooting"></a><span data-ttu-id="a6ffd-147">Résolution des problèmes d’EAP</span><span class="sxs-lookup"><span data-stu-id="a6ffd-147">EAP Troubleshooting</span></span>

1. <span data-ttu-id="a6ffd-148">Vérifiez que les paramètres de votre profil Wi-Fi sont corrects :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-148">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="a6ffd-149">Le type EAP est correctement configuré. Types d’EAP communs : EAP-TLS (13), EAP-TTLS (21) et PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-149">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="a6ffd-150">Le nom SSID du Wi-Fi est correct et correspond à la chaîne HEX.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-150">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="a6ffd-151">Pour EAP-TLS, TrustedRootCA contient le hachage SHA-1 du certificat d’autorité de certification racine de confiance du serveur.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-151">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="a6ffd-152">Sur un PC Windows, la commande &quot;certutil.exe -dump cert\_file\_name&quot; affiche la chaîne de hachage SHA-1 d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-152">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="a6ffd-153">Collectez la capture de paquets réseau sur les journaux du point d’accès, du contrôleur ou du serveur AAA pour savoir où la session EAP échoue.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-153">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="a6ffd-154">Si l’identité EAP fournie par HoloLens n’est pas attendue, vérifiez si l’identité a été correctement configurée via le profil Wi-Fi ou le certificat client.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-154">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="a6ffd-155">Si le serveur rejette le certificat client HoloLens, vérifiez si le certificat client requis a été configuré sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-155">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="a6ffd-156">Si HoloLens rejette le certificat de serveur, vérifiez si le certificat d’autorité de certification racine du serveur a été configuré sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-156">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="a6ffd-157">Si le profil d’entreprise est configuré via le package de configuration Wi-Fi, envisagez d’appliquer le package de configuration sur un PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-157">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="a6ffd-158">Si le problème persiste sur les PC Windows 10, suivez le [Guide de résolution des problèmes de l’authentification du client 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-158">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="a6ffd-159">Donnez votre avis via le [Hub de commentaires](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-159">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a6ffd-160">Ressources supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-160">Additional resources:</span></span>
- [<span data-ttu-id="a6ffd-161">Exporter les paramètres Wi-Fi depuis un appareil Windows</span><span class="sxs-lookup"><span data-stu-id="a6ffd-161">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a><span data-ttu-id="a6ffd-162">VPN</span><span class="sxs-lookup"><span data-stu-id="a6ffd-162">VPN</span></span>
<span data-ttu-id="a6ffd-163">Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-163">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="a6ffd-164">HoloLens 2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-164">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="a6ffd-165">Protocoles VPN intégrés pris en charge :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-165">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="a6ffd-166">IKEv2</span><span class="sxs-lookup"><span data-stu-id="a6ffd-166">IKEv2</span></span>
- <span data-ttu-id="a6ffd-167">L2TP</span><span class="sxs-lookup"><span data-stu-id="a6ffd-167">L2TP</span></span>
- <span data-ttu-id="a6ffd-168">PPTP</span><span class="sxs-lookup"><span data-stu-id="a6ffd-168">PPTP</span></span>

<span data-ttu-id="a6ffd-169">Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-169">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="a6ffd-170">Pour déterminer si un plug-in VPN tiers prend en charge HoloLens 2, accédez à Store pour trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-170">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="a6ffd-171">HoloLens prend uniquement en charge les applications de la plateforme Windows universelle pour les VPN tiers.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-171">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="a6ffd-172">Vous pouvez gérer les VPN avec GPM via [Paramètres/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), puis le définir via la [stratégie Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-172">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="a6ffd-173">Si vous souhaitez en savoir plus sur [la configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn), veuillez consulter [ces guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-173">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="a6ffd-174">VPN via une interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="a6ffd-174">VPN via UI</span></span>

<span data-ttu-id="a6ffd-175">Le VPN n’est pas activé par défaut. Vous pouvez l’activer manuellement en ouvrant l’application **Paramètres**, puis en accédant à **Réseau et Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-175">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="a6ffd-176">Sélectionnez un fournisseur VPN.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-176">Select a VPN provider.</span></span>
1. <span data-ttu-id="a6ffd-177">Créez un nom de connexion.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-177">Create a connection name.</span></span> 
1. <span data-ttu-id="a6ffd-178">Entrez le nom ou l’adresse de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-178">Enter your server name or address.</span></span>
1. <span data-ttu-id="a6ffd-179">Sélectionnez le type de VPN.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-179">Select the VPN type.</span></span>
1. <span data-ttu-id="a6ffd-180">Sélectionnez le type d’informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-180">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="a6ffd-181">Ajoutez éventuellement le nom d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-181">Optionally add user name and password.</span></span>
1. <span data-ttu-id="a6ffd-182">Appliquez les paramètres VPN.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-182">Apply the VPN settings.</span></span> 

![Paramètres du VPN HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="a6ffd-184">VPN défini via le package de configuration</span><span class="sxs-lookup"><span data-stu-id="a6ffd-184">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="a6ffd-185">Dans la version 20H2 de Windows Holographic, nous avons résolu un problème de configuration de proxy pour la connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-185">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="a6ffd-186">Si vous envisagez d’utiliser ce flux, pensez à mettre à niveau les appareils vers cette version.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-186">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="a6ffd-187">Lancez le Concepteur de configuration Windows.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-187">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="a6ffd-188">Cliquez sur mise en **Configurer les appareils HoloLens**, puis sélectionnez l’appareil cible et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-188">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="a6ffd-189">Entrez le nom et le chemin du package.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-189">Enter package name and path.</span></span>
1. <span data-ttu-id="a6ffd-190">Cliquez sur **Basculer vers l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-190">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="a6ffd-191">Ouvrez les **Paramètres d’exécution** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-191">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="a6ffd-192">Configurer VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="a6ffd-192">Configure VPNProfileName</span></span>
1. <span data-ttu-id="a6ffd-193">Sélectionnez le ProfileType : **Natif** ou **Tiers**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-193">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="a6ffd-194">Pour le profil Natif, sélectionnez **NativeProtocolType**, puis configurez le serveur, la stratégie de routage, le type d’authentification et d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-194">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="a6ffd-195">Pour le profil « Tiers », configurez l’URL du serveur, le nom de la famille du package de l’application du plug-in VPN (seulement trois prédéfinis) et les configurations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-195">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="a6ffd-196">Exportez votre package.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-196">Export your package.</span></span>
1. <span data-ttu-id="a6ffd-197">Connectez votre HoloLens et copiez le fichier. ppkg sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-197">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="a6ffd-198">Sur HoloLens, appliquez le VPN .ppkg en ouvrant le menu Démarrer, puis en sélectionnant **Paramètres** -> **Compte** -> **Accès professionnel ou scolaire** -> **Ajouter ou supprimer un package de configuration** -> Sélectionnez le package de votre VPN.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-198">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="a6ffd-199">Configurer un VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="a6ffd-199">Setting up VPN via Intune</span></span>
<span data-ttu-id="a6ffd-200">Il suffit de suivre les documents Intune pour commencer.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-200">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="a6ffd-201">Lorsque vous suivez ces étapes, n’oubliez pas les protocoles VPN intégrés pris en charge par les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-201">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="a6ffd-202">[Créer des profils VPN pour se connecter aux serveurs VPN dans Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-202">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="a6ffd-203">[Paramètres de l’appareil Windows 10 et Windows Holographic pour ajouter des connexions VPN à l’aide d’Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-203">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="a6ffd-204">Lorsque vous avez terminé, pensez à [affecter le profil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-204">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="a6ffd-205">VPN via des solutions GPM tierces</span><span class="sxs-lookup"><span data-stu-id="a6ffd-205">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="a6ffd-206">Exemple de connexion VPN tierce :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-206">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="a6ffd-207">Exemple de VPN IKEv2 natif :</span><span class="sxs-lookup"><span data-stu-id="a6ffd-207">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="a6ffd-208">Désactiver le Wi-Fi sur HoloLens (première génération)</span><span class="sxs-lookup"><span data-stu-id="a6ffd-208">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="a6ffd-209">Utilisation de l’application Paramètres sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="a6ffd-209">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="a6ffd-210">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-210">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a6ffd-211">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-211">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a6ffd-212">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-212">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a6ffd-213">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-213">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a6ffd-214">Sélectionnez le curseur Wi-Fi pour le placer en position **Désactivé** .</span><span class="sxs-lookup"><span data-stu-id="a6ffd-214">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="a6ffd-215">Cette opération désactive les composants RF de la radio Wi-Fi et toutes les fonctionnalités Wi-Fi sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-215">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="a6ffd-216">Lorsque la radio Wi-Fi est désactivée, HoloLens ne peut pas charger automatiquement vos [espaces](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-216">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="a6ffd-217">Positionnez le curseur en position **Activé** pour allumer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-217">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="a6ffd-218">L’état de l’option Wi-Fi sélectionné (**Activé** ou **Désactivé**) sera conservé en cas de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-218">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="a6ffd-219">Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a6ffd-219">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="a6ffd-220">À l’aide de l’application Paramètres</span><span class="sxs-lookup"><span data-stu-id="a6ffd-220">By using the Settings app</span></span>

1. <span data-ttu-id="a6ffd-221">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-221">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a6ffd-222">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-222">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a6ffd-223">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-223">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a6ffd-224">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-224">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a6ffd-225">Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-225">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="a6ffd-227">L’adresse IP apparaît en regard de **adresse IPv4**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-227">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="a6ffd-228">Via des commandes vocales</span><span class="sxs-lookup"><span data-stu-id="a6ffd-228">By using voice commands</span></span>

<span data-ttu-id="a6ffd-229">En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-229">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="a6ffd-230">Sur les builds ultérieures à la [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) demandez « quelle est mon adresse IP ? »</span><span class="sxs-lookup"><span data-stu-id="a6ffd-230">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="a6ffd-231">Celle-ci s’affiche alors.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-231">and it will be displayed.</span></span> <span data-ttu-id="a6ffd-232">Sur les builds antérieures ou sur HoloLens (1ère génération), dites « Hey Cortana, quelle est mon adresse IP ? »</span><span class="sxs-lookup"><span data-stu-id="a6ffd-232">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="a6ffd-233">Cortana afficher et lit votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-233">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="a6ffd-234">À l’aide du Portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="a6ffd-234">By using Windows Device Portal</span></span>

1. <span data-ttu-id="a6ffd-235">Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="a6ffd-235">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="a6ffd-236">Accédez à la section **Réseaux**.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-236">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="a6ffd-237">Cette section contient votre adresse IP et d’autres informations sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-237">This section displays your IP address and other network information.</span></span> <span data-ttu-id="a6ffd-238">En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.</span><span class="sxs-lookup"><span data-stu-id="a6ffd-238">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
