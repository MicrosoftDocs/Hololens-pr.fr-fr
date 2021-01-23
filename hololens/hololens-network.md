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
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283975"
---
# Connecter HoloLens à un réseau

Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau. Ce guide va vous aider:

- Se connecter à un réseau à l’aide du Wi-Fi ou (pour HoloLens 2 uniquement) Ethernet sur USB-C
- Désactiver et réactiver le Wi-Fi

En savoir plus sur l’[utilisation de HoloLens hors connexion](hololens-offline.md).

## Se connecter pour la première fois

Lors de la première utilisation de votre HoloLens, vous serez guidé pour vous connecter à un réseau Wi-Fi. Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif. Vérifiez que vous n’avez pas besoin d’utiliser un certificat pour vous connecter au réseau. Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.

Sur les appareils HoloLens 2, un utilisateur peut également [utiliser une carte USB-C vers Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pour se connecter directement au Wi-Fi afin de vous aider à configurer l’appareil. Une fois l’appareil configuré, l’utilisateur peut continuer à utiliser la carte ou il peut déconnecter l’appareil de la carte et [se connecter au Wi-Fi après avoir configuré](hololens-network.md#connecting-to-wi-fi-after-setup). 

## Connexion à un réseau Wi-Fi après l’installation

1. Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**. L’application Paramètres sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet** > **Wi-Fi**. Vérifiez que le Wi-Fi est activé. Si vous ne voyez pas votre réseau, faites défiler la liste.
1. Sélectionnez un réseau, puis **Connecter**.
1. Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.

HoloLens est muni d'une option Wi-Fi 2x2, compatible 802.11ac. La connexion de HoloLens à un réseau Wi-Fi est semblable à la connexion d’un ordinateur de bureau ou d’un appareil mobile Windows10 à un réseau Wi-Fi.

![Paramètres Wi-Fi HoloLens](./images/wifi-hololens-600px.jpg)

Vous pouvez également confirmer que vous êtes connecté à un réseau Wi-Fi en vérifiant l’état du Wi-Fi dans le menu **Démarrer** .

1. Ouvrez le menu **Démarrer**.
1. Dans l’angle supérieur gauche du menu **Démarrer** , recherchez l’état du Wi-Fi. L’état du Wi-Fi et le SSID du réseau connecté sont affichés.

## Résolution des problèmes de connexion à la Wi-Fi

Si vous rencontrez des problèmes lors de la connexion à la Wi-Fi, consultez [Je ne peux pas me connecter à la Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Lorsque vous connectez un compte d’entreprise ou organisationnel sur l’appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GDM), si la stratégie est configurée par votre administrateur informatique.

## Connecter HoloLens au réseau Wi-Fi d’entreprise

Les profils Wi-Fi d’entreprise utilisent le protocole d’authentification extensible (EAP) pour authentifier les connexions Wi-Fi. Le profil Wi-Fi d’entreprise HoloLens peut être configuré via GPM ou un package de configuration créé par le [Concepteur de configuration Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Pour l’appareil géré par MicrosoftIntune, consultez [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) pour obtenir des instructions de configuration.

Pour créer un package de configuration Wi-Fi dans le Concepteur de configuration Windows, un fichier .xml de profil Wi-Fi préconfiguré est requis. Voici un exemple de profil Wi-Fi pour WPA2-Enterprise avec authentification EAP-TLS:

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


Il se peut que le certificat d’autorité de certification racine du serveur et le certificat client doivent être configurés sur l’appareil en fonction du type d’EAP.

Ressources supplémentaires:

- Schéma WLANv1Profile: [[MS-GPWL]: Schéma du profil LAN sans fil v1 | Documents Microsoft](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schéma EAP-TLS: [[MS-GPWL]: schéma Microsoft EAP TLS | Documents Microsoft](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### Résolution des problèmes d’EAP

1. Vérifiez que les paramètres de votre profil Wi-Fi sont corrects:
   1. Le type EAP est correctement configuré. Types d’EAP communs: EAP-TLS (13), EAP-TTLS (21) et PEAP (25).
   1. Le nom SSID du Wi-Fi est correct et correspond à la chaîne HEX.
   1. Pour EAP-TLS, TrustedRootCA contient le hachage SHA-1 du certificat d’autorité de certification racine de confiance du serveur. Sur un PC Windows, la commande &quot;certutil.exe -dump cert\_file\_name&quot; affiche la chaîne de hachage SHA-1 d’un certificat.
1. Collectez la capture de paquets réseau sur les journaux du point d’accès, du contrôleur ou du serveur AAA pour savoir où la session EAP échoue.
   1. Si l’identité EAP fournie par HoloLens n’est pas attendue, vérifiez si l’identité a été correctement configurée via le profil Wi-Fi ou le certificat client.
   1. Si le serveur rejette le certificat client HoloLens, vérifiez si le certificat client requis a été configuré sur l’appareil.
   1. Si HoloLens rejette le certificat de serveur, vérifiez si le certificat d’autorité de certification racine du serveur a été configuré sur HoloLens.
1. Si le profil d’entreprise est configuré via le package de configuration Wi-Fi, envisagez d’appliquer le package de configuration sur un PC Windows10. Si le problème persiste sur les PC Windows10, suivez le [Guide de résolution des problèmes de l’authentification du client 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Donnez votre avis via le [Hub de commentaires](https://docs.microsoft.com/hololens/hololens-feedback).

### Ressources supplémentaires:
- [Exporter les paramètres Wi-Fi depuis un appareil Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## VPN
Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet. HoloLens2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP). 

Protocoles VPN intégrés pris en charge:
- IKEv2
- L2TP
- PPTP

Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur. Pour déterminer si un plug-in VPN tiers prend en charge HoloLens2, accédez à Store pour trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64. HoloLens prend uniquement en charge les applications de la plateforme Windows universelle pour les VPN tiers.

 Vous pouvez gérer les VPN avec GPM via [Paramètres/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), puis le définir via la [stratégie Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Si vous souhaitez en savoir plus sur [la configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn), veuillez consulter [ces guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

### VPN via une interface utilisateur

Le VPN n’est pas activé par défaut. Vous pouvez l’activer manuellement en ouvrant l’application **Paramètres**, puis en accédant à **Réseau et Internet -> VPN**.
1. Sélectionnez un fournisseur VPN.
1. Créez un nom de connexion. 
1. Entrez le nom ou l’adresse de votre serveur.
1. Sélectionnez le type de VPN.
1. Sélectionnez le type d’informations de connexion. 
1. Ajoutez éventuellement le nom d’utilisateur et le mot de passe.
1. Appliquez les paramètres VPN. 

![Paramètres du VPN HoloLens](./images/vpn-settings-ui.jpg)

### VPN défini via le package de configuration

> [!TIP] 
> Dans la version20H2 de Windows Holographic, nous avons résolu un problème de configuration de proxy pour la connexion VPN. Si vous envisagez d’utiliser ce flux, pensez à mettre à niveau les appareils vers cette version.

1. Lancez le Concepteur de configuration Windows.
1. Cliquez sur mise en **Configurer les appareils HoloLens**, puis sélectionnez l’appareil cible et cliquez sur **suivant**.
1. Entrez le nom et le chemin du package.
1. Cliquez sur **Basculer vers l’éditeur avancé**.
1. Ouvrez les **Paramètres d’exécution** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.
1. Configurer VPNProfileName
1. Sélectionnez le ProfileType: **Natif** ou **Tiers**.
    1. Pour le profil Natif, sélectionnez **NativeProtocolType**, puis configurez le serveur, la stratégie de routage, le type d’authentification et d’autres paramètres.
    1. Pour le profil «Tiers», configurez l’URL du serveur, le nom de la famille du package de l’application du plug-in VPN (seulement trois prédéfinis) et les configurations personnalisées.
1. Exportez votre package.
1. Connectez votre HoloLens et copiez le fichier. ppkg sur l’appareil. 
1. Sur HoloLens, appliquez le VPN .ppkg en ouvrant le menu Démarrer, puis en sélectionnant **Paramètres** -> **Compte** -> **Accès professionnel ou scolaire** -> **Ajouter ou supprimer un package de configuration** -> Sélectionnez le package de votre VPN.


### Configurer un VPN via Intune
Il suffit de suivre les documents Intune pour commencer. Lorsque vous suivez ces étapes, n’oubliez pas les protocoles VPN intégrés pris en charge par les appareils HoloLens. 

[Créer des profils VPN pour se connecter aux serveurs VPN dans Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Paramètres de l’appareil Windows10 et Windows Holographic pour ajouter des connexions VPN à l’aide d’Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).

Lorsque vous avez terminé, pensez à [affecter le profil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### VPN via des solutions GPM tierces
Exemple de connexion VPN tierce:
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

Exemple de VPN IKEv2 natif:
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
## Désactiver le Wi-Fi sur HoloLens (premièregénération)

### Utilisation de l’application Paramètres sur HoloLens

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet**.
1. Sélectionnez le curseur Wi-Fi pour le placer en position **Désactivé** . Cette opération désactive les composants RF de la radio Wi-Fi et toutes les fonctionnalités Wi-Fi sur HoloLens.

    > [!WARNING]
    > Lorsque la radio Wi-Fi est désactivée, HoloLens ne peut pas charger automatiquement vos [espaces](hololens-spaces.md).

1. Positionnez le curseur en position **Activé** pour allumer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens. L’état de l’option Wi-Fi sélectionné (**Activé** ou **Désactivé**) sera conservé en cas de redémarrage.

## Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi

### À l’aide de l’application Paramètres

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou dans la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** sera placée automatiquement en face de vous.
1. Sélectionnez **Réseau et Internet**.
1. Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.

    ![Propriétés matérielles dans les paramètres Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   L’adresse IP apparaît en regard de **adresse IPv4**.

### Via des commandes vocales

En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP. Sur les builds ultérieures à la [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) demandez «quelle est mon adresse IP?» Celle-ci s’affiche alors. Sur les builds antérieures ou sur HoloLens (1ère génération), dites «Hey Cortana, quelle est mon adresse IP?» Cortana afficher et lit votre adresse IP.

### À l’aide du Portail d’appareil Windows

1. Dans un navigateur Web sur votre PC, ouvrez le [Portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Accédez à la section **Réseaux**.  
   Cette section contient votre adresse IP et d’autres informations sur le réseau. En utilisant cette méthode, vous pouvez copier et coller l’adresse IP sur votre ordinateur de développement.
