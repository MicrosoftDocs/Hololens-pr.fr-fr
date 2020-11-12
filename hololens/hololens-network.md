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
ms.openlocfilehash: 7932ba493f8434c0fa5fc7a0efdd4d43eedd51bd
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163047"
---
# <span data-ttu-id="c3d16-104">Connecter HoloLens à un réseau</span><span class="sxs-lookup"><span data-stu-id="c3d16-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="c3d16-105">Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau.</span><span class="sxs-lookup"><span data-stu-id="c3d16-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="c3d16-106">Ce guide va vous aider:</span><span class="sxs-lookup"><span data-stu-id="c3d16-106">This guide will help you:</span></span>

- <span data-ttu-id="c3d16-107">Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C</span><span class="sxs-lookup"><span data-stu-id="c3d16-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="c3d16-108">Désactiver et réactiver le Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c3d16-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="c3d16-109">En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="c3d16-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="c3d16-110">Se connecter pour la première fois</span><span class="sxs-lookup"><span data-stu-id="c3d16-110">Connecting for the first time</span></span>

<span data-ttu-id="c3d16-111">Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c3d16-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="c3d16-112">Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif.</span><span class="sxs-lookup"><span data-stu-id="c3d16-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="c3d16-113">Vérifiez que vous n’avez pas besoin d’utiliser un certificat pour vous connecter au réseau.</span><span class="sxs-lookup"><span data-stu-id="c3d16-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="c3d16-114">Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c3d16-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="c3d16-115">Sur les appareils HoloLens 2, un utilisateur peut également [utiliser une carte USB-C vers Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pour se connecter directement au Wi-Fi afin de vous aider à configurer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c3d16-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="c3d16-116">Une fois l’appareil configuré, l’utilisateur peut continuer à utiliser la carte ou il peut déconnecter l’appareil de la carte et [se connecter au Wi-Fi après avoir configuré](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="c3d16-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="c3d16-117">Connexion à un réseau Wi-Fi après l’installation</span><span class="sxs-lookup"><span data-stu-id="c3d16-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="c3d16-118">Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="c3d16-119">L’application Paramètres sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="c3d16-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="c3d16-120">Sélectionnez **Réseau et Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="c3d16-121">Vérifiez que le Wi-Fi est activé.</span><span class="sxs-lookup"><span data-stu-id="c3d16-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="c3d16-122">Si vous ne voyez pas votre réseau, faites défiler la liste.</span><span class="sxs-lookup"><span data-stu-id="c3d16-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="c3d16-123">Sélectionnez un réseau, puis **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="c3d16-124">Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="c3d16-125">HoloLens est muni d'une option Wi-Fi 2x2, compatible 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="c3d16-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="c3d16-126">La connexion de HoloLens à un réseau Wi-Fi est semblable à la connexion d’un ordinateur de bureau ou d’un appareil mobile Windows10 à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c3d16-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Paramètres Wi-Fi HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="c3d16-128">Vous pouvez également confirmer que vous êtes connecté à un réseau Wi-Fi en vérifiant l’état du Wi-Fi dans le menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="c3d16-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="c3d16-129">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c3d16-130">Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c3d16-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="c3d16-131">L’état du Wi-Fi et le SSID du réseau connecté sont affichés.</span><span class="sxs-lookup"><span data-stu-id="c3d16-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="c3d16-132">Résolution des problèmes de connexion à la Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c3d16-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="c3d16-133">Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="c3d16-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="c3d16-134">Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="c3d16-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="c3d16-135">Connecter HoloLens au réseau Wi-Fi d’entreprise</span><span class="sxs-lookup"><span data-stu-id="c3d16-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="c3d16-136">Les profils Wi-Fi d’entreprise utilisent le protocole d’authentification extensible (EAP) pour authentifier les connexions Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c3d16-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="c3d16-137">Le profil Wi-Fi d’entreprise HoloLens peut être configuré via GPM ou un package de configuration créé par le [Concepteur de configuration Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="c3d16-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="c3d16-138">Pour l’appareil géré par MicrosoftIntune, consultez [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) pour obtenir des instructions de configuration.</span><span class="sxs-lookup"><span data-stu-id="c3d16-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="c3d16-139">Pour créer un package de configuration Wi-Fi dans le Concepteur de configuration Windows, un fichier .xml de profil Wi-Fi préconfiguré est requis.</span><span class="sxs-lookup"><span data-stu-id="c3d16-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="c3d16-140">Voici un exemple de profil Wi-Fi pour WPA2-Enterprise avec authentification EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="c3d16-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="c3d16-141">Il se peut que le certificat d’autorité de certification racine du serveur et le certificat client doivent être configurés sur l’appareil en fonction du type d’EAP.</span><span class="sxs-lookup"><span data-stu-id="c3d16-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="c3d16-142">Ressources supplémentaires:</span><span class="sxs-lookup"><span data-stu-id="c3d16-142">Additional resources:</span></span>

- <span data-ttu-id="c3d16-143">Schéma WLANv1Profile: [[MS-GPWL]: Schéma du profil LAN sans fil v1 | Documents Microsoft](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="c3d16-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="c3d16-144">Schéma EAP-TLS: [[MS-GPWL]: schéma Microsoft EAP TLS | Documents Microsoft](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="c3d16-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="c3d16-145">Résolution des problèmes d’EAP</span><span class="sxs-lookup"><span data-stu-id="c3d16-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="c3d16-146">Vérifiez que les paramètres de votre profil Wi-Fi sont corrects:</span><span class="sxs-lookup"><span data-stu-id="c3d16-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="c3d16-147">Le type EAP est correctement configuré. Types d’EAP communs: EAP-TLS (13), EAP-TTLS (21) et PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="c3d16-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="c3d16-148">Le nom SSID du Wi-Fi est correct et correspond à la chaîne HEX.</span><span class="sxs-lookup"><span data-stu-id="c3d16-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="c3d16-149">Pour EAP-TLS, TrustedRootCA contient le hachage SHA-1 du certificat d’autorité de certification racine de confiance du serveur.</span><span class="sxs-lookup"><span data-stu-id="c3d16-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="c3d16-150">Sur un PC Windows, la commande &quot;certutil.exe -dump cert\_file\_name&quot; affiche la chaîne de hachage SHA-1 d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="c3d16-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="c3d16-151">Collectez la capture de paquets réseau sur les journaux du point d’accès, du contrôleur ou du serveur AAA pour savoir où la session EAP échoue.</span><span class="sxs-lookup"><span data-stu-id="c3d16-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="c3d16-152">Si l’identité EAP fournie par HoloLens n’est pas attendue, vérifiez si l’identité a été correctement configurée via le profil Wi-Fi ou le certificat client.</span><span class="sxs-lookup"><span data-stu-id="c3d16-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="c3d16-153">Si le serveur rejette le certificat client HoloLens, vérifiez si le certificat client requis a été configuré sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c3d16-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="c3d16-154">Si HoloLens rejette le certificat de serveur, vérifiez si le certificat d’autorité de certification racine du serveur a été configuré sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c3d16-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="c3d16-155">Si le profil d’entreprise est configuré via le package de configuration Wi-Fi, envisagez d’appliquer le package de configuration sur un PC Windows10.</span><span class="sxs-lookup"><span data-stu-id="c3d16-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="c3d16-156">Si le problème persiste sur les PC Windows10, suivez le [Guide de résolution des problèmes de l’authentification du client 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="c3d16-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="c3d16-157">Donnez votre avis via le [Hub de commentaires](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="c3d16-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="c3d16-158">Ressources supplémentaires:</span><span class="sxs-lookup"><span data-stu-id="c3d16-158">Additional resources:</span></span>
- [<span data-ttu-id="c3d16-159">Exporter les paramètres Wi-Fi depuis un appareil Windows</span><span class="sxs-lookup"><span data-stu-id="c3d16-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="c3d16-160">VPN</span><span class="sxs-lookup"><span data-stu-id="c3d16-160">VPN</span></span>
<span data-ttu-id="c3d16-161">Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet.</span><span class="sxs-lookup"><span data-stu-id="c3d16-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="c3d16-162">HoloLens2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP).</span><span class="sxs-lookup"><span data-stu-id="c3d16-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="c3d16-163">Protocoles VPN intégrés pris en charge:</span><span class="sxs-lookup"><span data-stu-id="c3d16-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="c3d16-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="c3d16-164">IKEv2</span></span>
- <span data-ttu-id="c3d16-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="c3d16-165">L2TP</span></span>
- <span data-ttu-id="c3d16-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="c3d16-166">PPTP</span></span>

<span data-ttu-id="c3d16-167">Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3d16-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="c3d16-168">Pour déterminer si un plug-in VPN tiers prend en charge HoloLens2, accédez à Store pour trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="c3d16-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="c3d16-169">HoloLens prend uniquement en charge les applications de la plateforme Windows universelle pour les VPN tiers.</span><span class="sxs-lookup"><span data-stu-id="c3d16-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="c3d16-170">Vous pouvez gérer les VPN avec GPM via [Paramètres/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), puis le définir via la [stratégie Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="c3d16-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="c3d16-171">Si vous souhaitez en savoir plus sur [la configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn), veuillez consulter [ces guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="c3d16-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="c3d16-172">VPN via une interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="c3d16-172">VPN via UI</span></span>

<span data-ttu-id="c3d16-173">Le VPN n’est pas activé par défaut. Vous pouvez l’activer manuellement en ouvrant l’application **Paramètres**, puis en accédant à **Réseau et Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="c3d16-174">Sélectionnez un fournisseur VPN.</span><span class="sxs-lookup"><span data-stu-id="c3d16-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="c3d16-175">Créez un nom de connexion.</span><span class="sxs-lookup"><span data-stu-id="c3d16-175">Create a connection name.</span></span> 
1. <span data-ttu-id="c3d16-176">Entrez le nom ou l’adresse de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="c3d16-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="c3d16-177">Sélectionnez le type de VPN.</span><span class="sxs-lookup"><span data-stu-id="c3d16-177">Select the VPN type.</span></span>
1. <span data-ttu-id="c3d16-178">Sélectionnez le type d’informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="c3d16-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="c3d16-179">Ajoutez éventuellement le nom d’utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c3d16-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="c3d16-180">Appliquez les paramètres VPN.</span><span class="sxs-lookup"><span data-stu-id="c3d16-180">Apply the VPN settings.</span></span> 

![Paramètres du VPN HoloLens](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="c3d16-182">VPN défini via le package de configuration</span><span class="sxs-lookup"><span data-stu-id="c3d16-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="c3d16-183">Dans la version20H2 de Windows Holographic, nous avons résolu un problème de configuration de proxy pour la connexion VPN.</span><span class="sxs-lookup"><span data-stu-id="c3d16-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="c3d16-184">Si vous envisagez d’utiliser ce flux, pensez à mettre à niveau les appareils vers cette version.</span><span class="sxs-lookup"><span data-stu-id="c3d16-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="c3d16-185">Lancez le Concepteur de configuration Windows.</span><span class="sxs-lookup"><span data-stu-id="c3d16-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="c3d16-186">Cliquez sur mise en **Configurer les appareils HoloLens**, puis sélectionnez l’appareil cible et cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="c3d16-187">Entrez le nom et le chemin du package.</span><span class="sxs-lookup"><span data-stu-id="c3d16-187">Enter package name and path.</span></span>
1. <span data-ttu-id="c3d16-188">Cliquez sur **Basculer vers l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="c3d16-189">Ouvrez les **Paramètres d’exécution** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="c3d16-190">Configurer VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="c3d16-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="c3d16-191">Sélectionnez le ProfileType: **Natif** ou **Tiers**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="c3d16-192">Pour le profil Natif, sélectionnez **NativeProtocolType**, puis configurez le serveur, la stratégie de routage, le type d’authentification et d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="c3d16-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="c3d16-193">Pour le profil «Tiers», configurez l’URL du serveur, le nom de la famille du package de l’application du plug-in VPN (seulement trois prédéfinis) et les configurations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="c3d16-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="c3d16-194">Exportez votre package.</span><span class="sxs-lookup"><span data-stu-id="c3d16-194">Export your package.</span></span>
1. <span data-ttu-id="c3d16-195">Connectez votre HoloLens et copiez le fichier. ppkg sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c3d16-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="c3d16-196">Sur HoloLens, appliquez le VPN .ppkg en ouvrant le menu Démarrer, puis en sélectionnant **Paramètres** -> **Compte** -> **Accès professionnel ou scolaire** -> **Ajouter ou supprimer un package de configuration** -> Sélectionnez le package de votre VPN.</span><span class="sxs-lookup"><span data-stu-id="c3d16-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="c3d16-197">Configurer un VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="c3d16-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="c3d16-198">Il suffit de suivre les documents Intune pour commencer.</span><span class="sxs-lookup"><span data-stu-id="c3d16-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="c3d16-199">Lorsque vous suivez ces étapes, n’oubliez pas les protocoles VPN intégrés pris en charge par les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c3d16-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="c3d16-200">[Créer des profils VPN pour se connecter aux serveurs VPN dans Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="c3d16-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="c3d16-201">[Paramètres de l’appareil Windows10 et Windows Holographic pour ajouter des connexions VPN à l’aide d’Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="c3d16-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="c3d16-202">Lorsque vous avez terminé, pensez à [affecter le profil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="c3d16-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="c3d16-203">VPN via des solutions GPM tierces</span><span class="sxs-lookup"><span data-stu-id="c3d16-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="c3d16-204">Exemple de connexion VPN tierce:</span><span class="sxs-lookup"><span data-stu-id="c3d16-204">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="c3d16-205">Exemple de VPN IKEv2 natif:</span><span class="sxs-lookup"><span data-stu-id="c3d16-205">Native IKEv2 VPN example:</span></span>
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
## <span data-ttu-id="c3d16-206">Désactiver le Wi-Fi sur HoloLens (premièregénération)</span><span class="sxs-lookup"><span data-stu-id="c3d16-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="c3d16-207">Utilisation de l’application Paramètres sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="c3d16-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="c3d16-208">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c3d16-209">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="c3d16-210">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="c3d16-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="c3d16-211">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="c3d16-212">Sélectionnez le curseur Wi-Fi pour le placer en position **Désactivé** .</span><span class="sxs-lookup"><span data-stu-id="c3d16-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="c3d16-213">Cette opération désactive les composants RF de la radio Wi-Fi et toutes les fonctionnalités Wi-Fi sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c3d16-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="c3d16-214">Lorsque la radio Wi-Fi est désactivée, HoloLens ne peut pas charger automatiquement vos [espaces](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="c3d16-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="c3d16-215">Positionnez le curseur en position **Activé** pour allumer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c3d16-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="c3d16-216">L’état de l’option Wi-Fi sélectionné (**Activé** ou **Désactivé**) sera conservé en cas de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="c3d16-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="c3d16-217">Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c3d16-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="c3d16-218">À l’aide de l’application Paramètres</span><span class="sxs-lookup"><span data-stu-id="c3d16-218">By using the Settings app</span></span>

1. <span data-ttu-id="c3d16-219">Ouvrez le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c3d16-220">Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="c3d16-221">L’application **Paramètres** sera placée automatiquement en face de vous.</span><span class="sxs-lookup"><span data-stu-id="c3d16-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="c3d16-222">Sélectionnez **Réseau et Internet**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="c3d16-223">Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="c3d16-225">L’adresse IP apparaît en regard de **adresse IPv4**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="c3d16-226">Via des commandes vocales</span><span class="sxs-lookup"><span data-stu-id="c3d16-226">By using voice commands</span></span>

<span data-ttu-id="c3d16-227">En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="c3d16-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="c3d16-228">Sur les builds ultérieures à la [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) demandez «quelle est mon adresse IP?»</span><span class="sxs-lookup"><span data-stu-id="c3d16-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="c3d16-229">Celle-ci s’affiche alors.</span><span class="sxs-lookup"><span data-stu-id="c3d16-229">and it will be displayed.</span></span> <span data-ttu-id="c3d16-230">Sur les builds antérieures ou sur HoloLens (1ère génération), dites «Hey Cortana, quelle est mon adresse IP?»</span><span class="sxs-lookup"><span data-stu-id="c3d16-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="c3d16-231">Cortana afficher et lit votre adresse IP.</span><span class="sxs-lookup"><span data-stu-id="c3d16-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="c3d16-232">À l’aide du Portail d’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="c3d16-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="c3d16-233">Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="c3d16-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="c3d16-234">Accédez à la section **Réseaux**.</span><span class="sxs-lookup"><span data-stu-id="c3d16-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="c3d16-235">Cette section contient votre adresse IP et d’autres informations sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c3d16-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="c3d16-236">En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.</span><span class="sxs-lookup"><span data-stu-id="c3d16-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
