---
title: Connecter HoloLens à un réseau
description: Découvrez comment configurer et connecter HoloLens à Internet et identifier l’adresse IP de l’appareil.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, sans fil, internet, ip, adresse ip
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923599"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="81027-104">Connecter HoloLens à un réseau</span><span class="sxs-lookup"><span data-stu-id="81027-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="81027-105">Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau.</span><span class="sxs-lookup"><span data-stu-id="81027-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="81027-106">HoloLens contient une radio Wi-Fi 2x2 802.11ac et permet de la connecter à un réseau de manière similaire à la connexion d’un ordinateur de bureau Windows 10 ou d’un appareil mobile à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="81027-107">Ce guide peut vous aider à :</span><span class="sxs-lookup"><span data-stu-id="81027-107">This guide will help you:</span></span>

- <span data-ttu-id="81027-108">Vous connecter à un réseau à l’aide du Wi-Fi ou, pour HoloLens 2 uniquement, Wi-Fi Direct ou Ethernet sur USB-C</span><span class="sxs-lookup"><span data-stu-id="81027-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="81027-109">Désactiver et réactiver le Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="81027-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="81027-110">En savoir plus sur [l’utilisation de l’HoloLens hors connexion](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="81027-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="81027-111">Vous connecter pour la première fois</span><span class="sxs-lookup"><span data-stu-id="81027-111">Connecting for the first time</span></span>

<span data-ttu-id="81027-112">La première fois que vous utilisez votre HoloLens, vous êtes guidé en vous connectant à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="81027-113">Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif.</span><span class="sxs-lookup"><span data-stu-id="81027-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="81027-114">De plus, vérifiez que la connexion au réseau n’implique pas de certificat.</span><span class="sxs-lookup"><span data-stu-id="81027-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="81027-115">Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="81027-116">Sur les appareils HoloLens 2, un utilisateur peut également [utiliser un adaptateur USB-C vers Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pour se connecter directement au Wi-Fi afin de faciliter la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="81027-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="81027-117">Une fois l’appareil configuré, un utilisateur peut continuer à utiliser l’adaptateur ou déconnecter l’appareil de l’adaptateur et [se connecter à un réseau Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="81027-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="81027-118">Connexion à un réseau Wi-Fi après la configuration</span><span class="sxs-lookup"><span data-stu-id="81027-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="81027-119">Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="81027-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="81027-120">L’application Paramètres s’affiche automatiquement devant vous.</span><span class="sxs-lookup"><span data-stu-id="81027-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="81027-121">Sélectionnez **Réseau et Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="81027-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="81027-122">Vérifiez que le Wi-Fi est activé.</span><span class="sxs-lookup"><span data-stu-id="81027-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="81027-123">Si votre réseau ne s’affiche pas, faites défiler la liste.</span><span class="sxs-lookup"><span data-stu-id="81027-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="81027-124">Sélectionnez un réseau, puis **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="81027-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="81027-125">Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81027-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Paramètres Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="81027-127">Pour vérifier que vous êtes connecté à un réseau Wi-Fi, consultez l’état Wi-Fi dans le menu **Démarrer** :</span><span class="sxs-lookup"><span data-stu-id="81027-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="81027-128">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="81027-129">Dans l’angle supérieur gauche du menu **Démarrer**, recherchez l’état du Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="81027-130">L’état du Wi-Fi et le SSID du réseau connecté sont affichés.</span><span class="sxs-lookup"><span data-stu-id="81027-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="81027-131">Si le Wi-Fi n’est pas disponible, vous pouvez également vous [connecter à des réseaux cellulaires et 5G](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="81027-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81027-132">Pour des raisons de conception, les utilisateurs ne peuvent pas affiner le comportement d’itinérance Wi-Fi de l’HoloLens 2 ; **l’unique moyen d’actualiser la liste Wi-Fi consiste à activer et désactiver le Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="81027-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="81027-133">Cela permet d’éviter de nombreux problèmes, comme lorsqu’un appareil reste bloqué sur un point d’accès hors de portée.</span><span class="sxs-lookup"><span data-stu-id="81027-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="81027-134">Connecter l’HoloLens à un réseau Wi-Fi d’entreprise</span><span class="sxs-lookup"><span data-stu-id="81027-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="81027-135">Les profils Wi-Fi d’entreprise utilisent le protocole d’authentification extensible (EAP) pour authentifier les connexions Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="81027-136">Le profil Wi-Fi d’entreprise HoloLens peut être configuré via GPM ou un package de configuration créé par le [Concepteur de configuration Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="81027-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="81027-137">Pour l’appareil géré par Microsoft Intune, consultez [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) afin d’obtenir des instructions de configuration.</span><span class="sxs-lookup"><span data-stu-id="81027-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="81027-138">Pour créer un package de configuration Wi-Fi dans le Concepteur de configuration Windows, un fichier .xml de profil Wi-Fi préconfiguré est requis.</span><span class="sxs-lookup"><span data-stu-id="81027-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="81027-139">Voici un exemple de profil Wi-Fi pour WPA2-Enterprise avec authentification EAP-TLS :</span><span class="sxs-lookup"><span data-stu-id="81027-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="81027-140">Le certificat d’autorité de certification racine du serveur et le certificat client devront peut-être être configurés sur l’appareil en fonction du type d’EAP.</span><span class="sxs-lookup"><span data-stu-id="81027-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="81027-141">Ressources supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="81027-141">Additional resources:</span></span>

- <span data-ttu-id="81027-142">Schéma WLANv1Profile : [[MS-GPWL] : schéma v1 de profil de réseau local sans fil | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="81027-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="81027-143">Schéma EAP-TLS : [[MS-GPWL] : schéma Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="81027-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="81027-144">Consultez notre page [Résolution des problèmes](hololens2-enterprise-troubleshooting.md#) si vous rencontrez des problèmes de connexion à votre Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="81027-145">Configurer le proxy réseau</span><span class="sxs-lookup"><span data-stu-id="81027-145">Configure Network Proxy</span></span>

<span data-ttu-id="81027-146">Cette section traite du proxy réseau pour le système d’exploitation HoloLens et les applications de plateforme Windows universelle (UWP) utilisant la pile HTTP Windows.</span><span class="sxs-lookup"><span data-stu-id="81027-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="81027-147">Les applications utilisant une pile HTTP non Windows peuvent présenter une configuration et une gestion du proxy qui leur sont propres.</span><span class="sxs-lookup"><span data-stu-id="81027-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="81027-148">Configurations du proxy</span><span class="sxs-lookup"><span data-stu-id="81027-148">Proxy Configurations</span></span> 

- <span data-ttu-id="81027-149">Script de configuration automatique du proxy (PAC) : un [fichier PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (ouvre un site non-Microsoft) contient une fonction JavaScript FindProxyForURL (URL, hôte).</span><span class="sxs-lookup"><span data-stu-id="81027-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="81027-150">Proxy statique : sous la forme Server:Port.</span><span class="sxs-lookup"><span data-stu-id="81027-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="81027-151">Protocole de découverte automatique de proxy web (WPAD) : indiquez l’URL du fichier de configuration du proxy via DHCP ou DNS.</span><span class="sxs-lookup"><span data-stu-id="81027-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="81027-152">Méthodes d’approvisionnement du proxy</span><span class="sxs-lookup"><span data-stu-id="81027-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="81027-153">Il existe trois façons d’approvisionner des proxies :</span><span class="sxs-lookup"><span data-stu-id="81027-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="81027-154">**IU Paramètres :**</span><span class="sxs-lookup"><span data-stu-id="81027-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="81027-155">Proxy par utilisateur (version 20H2 ou antérieure) :</span><span class="sxs-lookup"><span data-stu-id="81027-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="81027-156">Ouvrez le menu Démarrer et sélectionnez Paramètres.</span><span class="sxs-lookup"><span data-stu-id="81027-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="81027-157">Sélectionnez Réseau et Internet, puis Proxy dans le menu de gauche.</span><span class="sxs-lookup"><span data-stu-id="81027-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="81027-158">Faites défiler jusqu’à Configuration manuelle du proxy et activez Utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="81027-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="81027-159">Entrez l'adresse IP du serveur proxy</span><span class="sxs-lookup"><span data-stu-id="81027-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="81027-160">Entrez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="81027-160">Enter the port number.</span></span>
        6. <span data-ttu-id="81027-161">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="81027-161">Click Save.</span></span>
      1. <span data-ttu-id="81027-162">Proxy Wi-Fi (version 21H1 ou ultérieure) :</span><span class="sxs-lookup"><span data-stu-id="81027-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="81027-163">Ouvrez la menu Démarrer et accédez à la page Propriétés de votre réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="81027-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="81027-164">Faites défiler jusqu'à Proxy.</span><span class="sxs-lookup"><span data-stu-id="81027-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="81027-165">Basculez vers Configuration manuelle.</span><span class="sxs-lookup"><span data-stu-id="81027-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="81027-166">Entrez l'adresse IP du serveur proxy</span><span class="sxs-lookup"><span data-stu-id="81027-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="81027-167">Entrez le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="81027-167">Enter the port number.</span></span>
          1. <span data-ttu-id="81027-168">Cliquez sur Appliquer.</span><span class="sxs-lookup"><span data-stu-id="81027-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="81027-169">**Gestion des appareils mobiles**</span><span class="sxs-lookup"><span data-stu-id="81027-169">**MDM**</span></span> 
     1. <span data-ttu-id="81027-170">Intune : suivez les [étapes](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) ci-dessous pour configurer le proxy dans Intune.</span><span class="sxs-lookup"><span data-stu-id="81027-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="81027-171">Vous devez faire défiler jusqu’en bas de la section.</span><span class="sxs-lookup"><span data-stu-id="81027-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="81027-172">Autres solutions GPM tierces : utilisez un [fournisseur CSP Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="81027-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="81027-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="81027-173">**PPKG**</span></span> 
    1. <span data-ttu-id="81027-174">Ouvrez le Concepteur de configuration Windows.</span><span class="sxs-lookup"><span data-stu-id="81027-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="81027-175">Cliquez sur Approvisionnement avancé, entrez le nom de votre nouveau projet, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="81027-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="81027-176">Sélectionnez Windows Holographic (HoloLens 2), puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="81027-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="81027-177">Importez votre PPKG (facultatif), puis cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="81027-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="81027-178">Développez Paramètres d’exécution -> Profils de connectivité -> WLAN -> Proxy WLAN.</span><span class="sxs-lookup"><span data-stu-id="81027-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="81027-179">Entrez le SSID de votre réseau Wi-Fi, puis cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="81027-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="81027-180">Sélectionnez votre réseau Wi-Fi dans la fenêtre de gauche et entrez les personnalisations souhaitées.</span><span class="sxs-lookup"><span data-stu-id="81027-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="81027-181">Les personnalisations activées s’affichent en gras dans le menu de gauche.</span><span class="sxs-lookup"><span data-stu-id="81027-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="81027-182">Cliquez sur Enregistrer, puis Quitter.</span><span class="sxs-lookup"><span data-stu-id="81027-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="81027-183">[Appliquez](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) le package d’approvisionnement à HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81027-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="81027-184">Les [fournisseurs de solutions Cloud](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) sont à l’origine de nombreuses tâches et stratégies de gestion de Windows 10 dans Microsoft Intune et dans les fournisseurs de services GPM autres que Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81027-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="81027-185">Vous pouvez également utiliser le [Concepteur de configuration Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) pour créer un [package de configuration](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) et l’appliquer à l’HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="81027-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="81027-186">Les fournisseurs de solutions Cloud qui seront appliqués à votre HoloLens 2 peuvent être :</span><span class="sxs-lookup"><span data-stu-id="81027-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="81027-187">[CSP Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): Wi-Fi proxy par profil</span><span class="sxs-lookup"><span data-stu-id="81027-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="81027-188">Autres fournisseurs de solutions Cloud pris en charge sur les appareils HoloLens</span><span class="sxs-lookup"><span data-stu-id="81027-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="81027-189">VPN</span><span class="sxs-lookup"><span data-stu-id="81027-189">VPN</span></span>
<span data-ttu-id="81027-190">Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet.</span><span class="sxs-lookup"><span data-stu-id="81027-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="81027-191">HoloLens 2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP).</span><span class="sxs-lookup"><span data-stu-id="81027-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="81027-192">Protocoles VPN intégrés pris en charge :</span><span class="sxs-lookup"><span data-stu-id="81027-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="81027-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="81027-193">IKEv2</span></span>
- <span data-ttu-id="81027-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="81027-194">L2TP</span></span>
- <span data-ttu-id="81027-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="81027-195">PPTP</span></span>

<span data-ttu-id="81027-196">Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81027-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="81027-197">Pour déterminer si un plug-in VPN tiers prend en charge HoloLens 2, accédez au Store afin de trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="81027-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="81027-198">HoloLens prend uniquement en charge les applications de la plateforme Windows universelle pour les VPN tiers.</span><span class="sxs-lookup"><span data-stu-id="81027-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="81027-199">Le VPN peut être géré par GPM via [Paramètres/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) et défini via la [stratégie Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="81027-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="81027-200">Apprenez-en davantage sur la [configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) en consultant [ces guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="81027-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="81027-201">VPN via une interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="81027-201">VPN via UI</span></span>

<span data-ttu-id="81027-202">Le VPN n’est pas activé par défaut. Vous pouvez l’activer manuellement en ouvrant **Paramètres**, puis en accédant à **Réseau et Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="81027-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="81027-203">Sélectionnez un fournisseur VPN.</span><span class="sxs-lookup"><span data-stu-id="81027-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="81027-204">Créez un nom de connexion.</span><span class="sxs-lookup"><span data-stu-id="81027-204">Create a connection name.</span></span> 
1. <span data-ttu-id="81027-205">Entrez le nom ou l’adresse de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="81027-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="81027-206">Sélectionnez le type de VPN.</span><span class="sxs-lookup"><span data-stu-id="81027-206">Select the VPN type.</span></span>
1. <span data-ttu-id="81027-207">Sélectionnez le type d’informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="81027-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="81027-208">Ajoutez éventuellement le nom d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="81027-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="81027-209">Appliquez les paramètres VPN.</span><span class="sxs-lookup"><span data-stu-id="81027-209">Apply the VPN settings.</span></span> 

![Paramètres du VPN HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="81027-211">VPN défini via le package de configuration</span><span class="sxs-lookup"><span data-stu-id="81027-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="81027-212">Dans la version 20H2 de Windows Holographic, nous avons résolu un problème de configuration de proxy pour la connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="81027-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="81027-213">Si vous envisagez d’utiliser ce flux, pensez à mettre à niveau les appareils vers cette version.</span><span class="sxs-lookup"><span data-stu-id="81027-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="81027-214">Lancez le Concepteur de configuration Windows.</span><span class="sxs-lookup"><span data-stu-id="81027-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="81027-215">Cliquez sur **Approvisionner les appareils HoloLens**, puis sélectionnez l’appareil cible et **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81027-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="81027-216">Entrez le nom et le chemin du package.</span><span class="sxs-lookup"><span data-stu-id="81027-216">Enter package name and path.</span></span>
1. <span data-ttu-id="81027-217">Cliquez sur **Basculer vers l'éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="81027-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="81027-218">Ouvrez **Paramètres d’exécution** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="81027-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="81027-219">Configurer VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="81027-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="81027-220">Sélectionnez ProfileType : **Natif** ou **Tiers**.</span><span class="sxs-lookup"><span data-stu-id="81027-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="81027-221">Pour le profil Natif, sélectionnez **NativeProtocolType**, puis configurez le serveur, la stratégie de routage, le type d’authentification et d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="81027-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="81027-222">Pour le profil « Tiers », configurez l’URL du serveur, le nom de la famille du package de l’application du plug-in VPN (seulement trois prédéfinis) et les configurations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="81027-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="81027-223">Exportez votre package.</span><span class="sxs-lookup"><span data-stu-id="81027-223">Export your package.</span></span>
1. <span data-ttu-id="81027-224">Connectez votre HoloLens et copiez le fichier. ppkg sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="81027-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="81027-225">Sur HoloLens, appliquez le fichier .ppkg du VPN en ouvrant le menu Démarrer, puis en sélectionnant **Paramètres** -> **Compte** -> **Accéder à un compte professionnel ou scolaire** -> **Ajouter ou supprimer un package de configuration** -> Sélectionnez le package de votre VPN.</span><span class="sxs-lookup"><span data-stu-id="81027-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="81027-226">Configurer un VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="81027-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="81027-227">Pour ce faire, suivez la documentation Intune.</span><span class="sxs-lookup"><span data-stu-id="81027-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="81027-228">Lorsque vous suivez ces étapes, n’oubliez pas les protocoles VPN intégrés pris en charge par les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81027-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="81027-229">[Créer des profils VPN pour se connecter à des serveurs VPN dans Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="81027-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="81027-230">[Paramètres des appareils Windows 10 et Windows Holographic permettant d’ajouter des connexions VPN en utilisant Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="81027-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="81027-231">Lorsque vous avez terminé, pensez à [attribuer le profil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="81027-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="81027-232">VPN via des solutions GPM tierces</span><span class="sxs-lookup"><span data-stu-id="81027-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="81027-233">Exemple de connexion VPN tierce :</span><span class="sxs-lookup"><span data-stu-id="81027-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="81027-234">Exemple de VPN IKEv2 natif :</span><span class="sxs-lookup"><span data-stu-id="81027-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="81027-235">Désactiver le Wi-Fi sur HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="81027-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="81027-236">Utilisation de l’application Paramètres sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="81027-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="81027-237">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="81027-238">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="81027-239">L’application **Paramètres** s’affiche automatiquement devant vous.</span><span class="sxs-lookup"><span data-stu-id="81027-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="81027-240">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="81027-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="81027-241">Sélectionnez le curseur Wi-Fi pour le déplacer sur **Off**.</span><span class="sxs-lookup"><span data-stu-id="81027-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="81027-242">Cette opération désactive les composants RF de la radio Wi-Fi, de même que toutes les fonctionnalités Wi-Fi sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81027-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="81027-243">Lorsque la radio Wi-Fi est désactivée, HoloLens n’est pas en mesure de charger automatiquement vos [espaces](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="81027-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="81027-244">Déplacez le curseur sur **On** pour activer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81027-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="81027-245">L’état radio Wi-Fi sélectionné (**On** ou **Off**) est conservé en cas de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="81027-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="81027-246">Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="81027-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="81027-247">À l’aide de l’application Paramètres</span><span class="sxs-lookup"><span data-stu-id="81027-247">By using the Settings app</span></span>

1. <span data-ttu-id="81027-248">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="81027-249">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="81027-250">L’application **Paramètres** s’affiche automatiquement devant vous.</span><span class="sxs-lookup"><span data-stu-id="81027-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="81027-251">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="81027-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="81027-252">Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.</span><span class="sxs-lookup"><span data-stu-id="81027-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="81027-254">L’adresse IP apparaît en regard de **Adresse IPv4**.</span><span class="sxs-lookup"><span data-stu-id="81027-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="81027-255">À l’aide de commandes vocales</span><span class="sxs-lookup"><span data-stu-id="81027-255">By using voice commands</span></span>

<span data-ttu-id="81027-256">En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="81027-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="81027-257">Sur les builds ultérieures à [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), dites « Quelle est mon adresse IP ? »</span><span class="sxs-lookup"><span data-stu-id="81027-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="81027-258">Celle-ci s’affiche alors.</span><span class="sxs-lookup"><span data-stu-id="81027-258">and it will be displayed.</span></span> <span data-ttu-id="81027-259">Sur les builds antérieures ou sur HoloLens (1ère génération), dites « Hey Cortana, quelle est mon adresse IP ? »</span><span class="sxs-lookup"><span data-stu-id="81027-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="81027-260">Cortana affiche et lit votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="81027-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="81027-261">À l’aide du portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="81027-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="81027-262">Sur votre PC, à l’aide d’un navigateur web, ouvrez le [portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="81027-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="81027-263">Accédez à la section **Réseaux**.</span><span class="sxs-lookup"><span data-stu-id="81027-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="81027-264">Cette section affiche votre adresse IP entre autres informations relatives au réseau.</span><span class="sxs-lookup"><span data-stu-id="81027-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="81027-265">Cette méthode vous permet de copier et coller l’adresse IP sur votre ordinateur de développement.</span><span class="sxs-lookup"><span data-stu-id="81027-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="81027-266">Changer une adresse IP en adresse statique</span><span class="sxs-lookup"><span data-stu-id="81027-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="81027-267">En utilisant Paramètres</span><span class="sxs-lookup"><span data-stu-id="81027-267">By using Settings</span></span>
 
1. <span data-ttu-id="81027-268">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="81027-269">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="81027-270">L’application **Paramètres** s’affiche automatiquement devant vous.</span><span class="sxs-lookup"><span data-stu-id="81027-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="81027-271">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="81027-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="81027-272">Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.</span><span class="sxs-lookup"><span data-stu-id="81027-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="81027-273">Dans la fenêtre **Modifier les paramètres IP** , définissez le premier champ sur **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="81027-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="81027-274">Entrez la configuration IP souhaitée dans les champs restants, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="81027-275">À l’aide du portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="81027-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="81027-276">Sur votre PC, à l’aide d’un navigateur web, ouvrez le [portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="81027-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="81027-277">Accédez à la section **Réseaux**.</span><span class="sxs-lookup"><span data-stu-id="81027-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="81027-278">Sélectionnez le bouton **Configuration IPv4** .</span><span class="sxs-lookup"><span data-stu-id="81027-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="81027-279">Sélectionnez **Utiliser l’adresse IP suivante** et entrez la configuration TCP/IP souhaitée.</span><span class="sxs-lookup"><span data-stu-id="81027-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="81027-280">Sélectionnez **Utiliser les adresses de serveur DNS suivantes** et entrez les adresses de serveur DNS préférées et secondaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="81027-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="81027-281">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="81027-281">Click **Save**.</span></span> 
