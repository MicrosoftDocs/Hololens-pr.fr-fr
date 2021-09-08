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
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189101"
---
# <a name="connect-hololens-to-a-network"></a>Connecter HoloLens à un réseau

Pour réaliser la plupart des opérations sur votre HoloLens, vous devez être connecté à un réseau. HoloLens contient une radio Wi-Fi 2x2 802.11ac et permet de la connecter à un réseau de manière similaire à la connexion d’un ordinateur de bureau Windows 10 ou d’un appareil mobile à un réseau Wi-Fi. Ce guide peut vous aider à :

- Vous connecter à un réseau à l’aide du Wi-Fi ou, pour HoloLens 2 uniquement, Wi-Fi Direct ou Ethernet sur USB-C
- Désactiver et réactiver le Wi-Fi

En savoir plus sur [l’utilisation de l’HoloLens hors connexion](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Vous connecter pour la première fois

La première fois que vous utilisez votre HoloLens, vous êtes guidé en vous connectant à un réseau Wi-Fi. Si vous rencontrez des problèmes de connexion à un réseau Wi-Fi lors de l’installation, assurez-vous que votre réseau est un réseau ouvert, protégé par mot de passe ou un réseau de portail captif. De plus, vérifiez que la connexion au réseau n’implique pas de certificat. Après la configuration, vous pouvez vous connecter à d’autres types de réseaux Wi-Fi.

Sur les appareils HoloLens 2, un utilisateur peut également [utiliser un adaptateur USB-C vers Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pour se connecter directement au Wi-Fi afin de faciliter la configuration de l’appareil. Une fois l’appareil configuré, un utilisateur peut continuer à utiliser l’adaptateur ou déconnecter l’appareil de l’adaptateur et [se connecter à un réseau Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Connexion à un réseau Wi-Fi après la configuration

1. Effectuez le **mouvement associé au menu Démarrer**, puis sélectionnez **Paramètres**. L’application Paramètres s’affiche automatiquement devant vous.
1. Sélectionnez **Réseau et Internet** > **Wi-Fi**. Vérifiez que le Wi-Fi est activé. Si votre réseau ne s’affiche pas, faites défiler la liste.
1. Sélectionnez un réseau, puis **Se connecter**.
1. Si vous êtes invité à entrer un mot de passe réseau, tapez-le, puis sélectionnez **Suivant**.

![Paramètres Wi-Fi HoloLens.](./images/hololens-2-wifi-settings.jpg)

Pour vérifier que vous êtes connecté à un réseau Wi-Fi, consultez l’état Wi-Fi dans le menu **Démarrer** :

1. Ouvrez le menu **Démarrer**.
1. Dans l’angle supérieur gauche du menu **Démarrer**, recherchez l’état du Wi-Fi. L’état du Wi-Fi et le SSID du réseau connecté sont affichés.

> [!TIP]
> Si le Wi-Fi n’est pas disponible, vous pouvez également vous [connecter à des réseaux cellulaires et 5G](hololens-cellular.md).

> [!IMPORTANT]
> Pour des raisons de conception, les utilisateurs ne peuvent pas affiner le comportement d’itinérance Wi-Fi de l’HoloLens 2 ; **l’unique moyen d’actualiser la liste Wi-Fi consiste à activer et désactiver le Wi-Fi**. Cela permet d’éviter de nombreux problèmes, comme lorsqu’un appareil reste bloqué sur un point d’accès hors de portée.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Connecter l’HoloLens à un réseau Wi-Fi d’entreprise

Les profils Wi-Fi d’entreprise utilisent le protocole d’authentification extensible (EAP) pour authentifier les connexions Wi-Fi. Le profil Wi-Fi d’entreprise HoloLens peut être configuré via GPM ou un package de configuration créé par le [Concepteur de configuration Windows](/windows/configuration/provisioning-packages/provisioning-packages).

Pour l’appareil géré par Microsoft Intune, consultez [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) afin d’obtenir des instructions de configuration.

Pour créer un package de configuration Wi-Fi dans le Concepteur de configuration Windows, un fichier .xml de profil Wi-Fi préconfiguré est requis. Voici un exemple de profil Wi-Fi pour WPA2-Enterprise avec authentification EAP-TLS :

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


Le certificat d’autorité de certification racine du serveur et le certificat client devront peut-être être configurés sur l’appareil en fonction du type d’EAP.

Ressources supplémentaires :

- Schéma WLANv1Profile : [[MS-GPWL] : schéma v1 de profil de réseau local sans fil | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schéma EAP-TLS : [[MS-GPWL] : schéma Microsoft EAP TLS | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Consultez notre page [Résolution des problèmes](hololens2-enterprise-troubleshooting.md#) si vous rencontrez des problèmes de connexion à votre Wi-Fi.

## <a name="configure-network-proxy"></a>Configurer le proxy réseau

Cette section traite du proxy réseau pour le système d’exploitation HoloLens et les applications de plateforme Windows universelle (UWP) utilisant la pile HTTP Windows. Les applications utilisant une pile HTTP non Windows peuvent présenter une configuration et une gestion du proxy qui leur sont propres. 

### <a name="proxy-configurations"></a>Configurations du proxy 

- Script de configuration automatique du proxy (PAC) : un [fichier PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (ouvre un site non-Microsoft) contient une fonction JavaScript FindProxyForURL (URL, hôte). 
- Proxy statique : sous la forme Server:Port.  
- Protocole de découverte automatique de proxy web (WPAD) : indiquez l’URL du fichier de configuration du proxy via DHCP ou DNS. 

### <a name="proxy-provisioning-methods"></a>Méthodes d’approvisionnement du proxy 
Il existe trois façons d’approvisionner des proxies :

 

1.  **IU Paramètres :** 
    1. Proxy par utilisateur (version 20H2 ou antérieure) :
        1. Ouvrez le menu Démarrer et sélectionnez Paramètres.
        2. Sélectionnez Réseau et Internet, puis Proxy dans le menu de gauche.
        3. Faites défiler jusqu’à Configuration manuelle du proxy et activez Utiliser un serveur proxy.
        4. Entrez l'adresse IP du serveur proxy
        5. Entrez le numéro de port.
        6. Cliquez sur Enregistrer.
      1. Proxy Wi-Fi (version 21H1 ou ultérieure) :
          1. Ouvrez la menu Démarrer et accédez à la page Propriétés de votre réseau Wi-Fi.
          1. Faites défiler jusqu'à Proxy.
          1. Basculez vers Configuration manuelle.
          1. Entrez l'adresse IP du serveur proxy
          1. Entrez le numéro de port.
          1. Cliquez sur Appliquer.
        
 2. **Gestion des appareils mobiles** 
     1. Intune : suivez les [étapes](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) ci-dessous pour configurer le proxy dans Intune. Vous devez faire défiler jusqu’en bas de la section.
     1. Autres solutions GPM tierces : utilisez un [fournisseur CSP Wi-Fi](/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Ouvrez le Concepteur de configuration Windows.
    1. Cliquez sur Approvisionnement avancé, entrez le nom de votre nouveau projet, puis cliquez sur Suivant.
    1. Sélectionnez Windows Holographic (HoloLens 2), puis cliquez sur Suivant.
    1. Importez votre PPKG (facultatif), puis cliquez sur Terminer.
    1. Développez Paramètres d’exécution -> Profils de connectivité -> WLAN -> Proxy WLAN.
    1. Entrez le SSID de votre réseau Wi-Fi, puis cliquez sur Ajouter.
    1. Sélectionnez votre réseau Wi-Fi dans la fenêtre de gauche et entrez les personnalisations souhaitées. Les personnalisations activées s’affichent en gras dans le menu de gauche.
    1. Cliquez sur Enregistrer, puis Quitter.
    1. [Appliquez](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) le package d’approvisionnement à HoloLens.

Les [fournisseurs de solutions Cloud](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) sont à l’origine de nombreuses tâches et stratégies de gestion de Windows 10 dans Microsoft Intune et dans les fournisseurs de services GPM autres que Microsoft. Vous pouvez également utiliser le [Concepteur de configuration Windows](/windows/configuration/provisioning-packages/provisioning-install-icd) pour créer un [package de configuration](/windows/configuration/provisioning-packages/provisioning-packages) et l’appliquer à l’HoloLens 2.
Les fournisseurs de solutions Cloud qui seront appliqués à votre HoloLens 2 peuvent être :

- [CSP Wi-Fi](/windows/client-management/mdm/wifi-csp): Wi-Fi proxy par profil 

[Autres fournisseurs de solutions Cloud pris en charge sur les appareils HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Le VPN offre une connexion et un accès plus sécurisés au réseau de votre entreprise et à Internet. HoloLens 2 prend en charge le client VPN intégré et le plug-in VPN de la plateforme Windows universelle (UWP). 

Protocoles VPN intégrés pris en charge :
- IKEv2
- L2TP
- PPTP

Si l’authentification pour le client VPN intégré fait appel à un certificat, vous devez ajouter le certificat client nécessaire au magasin de certificats de l’utilisateur. Pour déterminer si un plug-in VPN tiers prend en charge HoloLens 2, accédez au Store afin de trouver l’application VPN. Ensuite, vérifiez si HoloLens est répertorié comme appareil pris en charge, puis, dans la page Configuration requise, si l’application prend en charge l’architecture ARM ou ARM64. HoloLens prend uniquement en charge les applications de la plateforme Windows universelle pour les VPN tiers.

 Le VPN peut être géré par GPM via [Paramètres/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) et défini via la [stratégie Vpnv2-csp](/windows/client-management/mdm/vpnv2-csp).

Apprenez-en davantage sur la [configuration du VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) en consultant [ces guides](/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN via une interface utilisateur

Le VPN n’est pas activé par défaut. Vous pouvez l’activer manuellement en ouvrant **Paramètres**, puis en accédant à **Réseau et Internet -> VPN**.
1. Sélectionnez un fournisseur VPN.
1. Créez un nom de connexion. 
1. Entrez le nom ou l’adresse de votre serveur.
1. Sélectionnez le type de VPN.
1. Sélectionnez le type d’informations de connexion. 
1. Ajoutez éventuellement le nom d’utilisateur et le mot de passe.
1. Appliquez les paramètres VPN. 

![Paramètres VPN HoloLens.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN défini via le package de configuration

> [!TIP] 
> Dans la version 20H2 de Windows Holographic, nous avons résolu un problème de configuration de proxy pour la connexion VPN. Si vous envisagez d’utiliser ce flux, pensez à mettre à niveau les appareils vers cette version.

1. Lancez le Concepteur de configuration Windows.
1. Cliquez sur **Approvisionner les appareils HoloLens**, puis sélectionnez l’appareil cible et **Suivant**.
1. Entrez le nom et le chemin du package.
1. Cliquez sur **Basculer vers l'éditeur avancé**.
1. Ouvrez **Paramètres d’exécution** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.
1. Configurer VPNProfileName
1. Sélectionnez ProfileType : **Natif** ou **Tiers**.
    1. Pour le profil Natif, sélectionnez **NativeProtocolType**, puis configurez le serveur, la stratégie de routage, le type d’authentification et d’autres paramètres.
    1. Pour le profil « Tiers », configurez l’URL du serveur, le nom de la famille du package de l’application du plug-in VPN (seulement trois prédéfinis) et les configurations personnalisées.
1. Exportez votre package.
1. Connectez votre HoloLens et copiez le fichier. ppkg sur l’appareil. 
1. Sur HoloLens, appliquez le fichier .ppkg du VPN en ouvrant le menu Démarrer, puis en sélectionnant **Paramètres** -> **Compte** -> **Accéder à un compte professionnel ou scolaire** -> **Ajouter ou supprimer un package de configuration** -> Sélectionnez le package de votre VPN.


### <a name="setting-up-vpn-via-intune"></a>Configurer un VPN via Intune
Pour ce faire, suivez la documentation Intune. Lorsque vous suivez ces étapes, n’oubliez pas les protocoles VPN intégrés pris en charge par les appareils HoloLens. 

[Créer des profils VPN pour se connecter à des serveurs VPN dans Intune](/mem/intune/configuration/vpn-settings-configure).

[Paramètres des appareils Windows 10 et Windows Holographic permettant d’ajouter des connexions VPN en utilisant Intune](/mem/intune/configuration/vpn-settings-windows-10).

Lorsque vous avez terminé, pensez à [attribuer le profil](/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN via des solutions GPM tierces
Exemple de connexion VPN tierce :
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

Exemple de VPN IKEv2 natif :
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Désactiver le Wi-Fi sur HoloLens (1ère génération)

### <a name="using-the-settings-app-on-hololens"></a>Utilisation de l’application Paramètres sur HoloLens

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** s’affiche automatiquement devant vous.
1. Sélectionnez **Réseau et Internet**.
1. Sélectionnez le curseur Wi-Fi pour le déplacer sur **Off**. Cette opération désactive les composants RF de la radio Wi-Fi, de même que toutes les fonctionnalités Wi-Fi sur HoloLens.

    > [!WARNING]
    > Lorsque la radio Wi-Fi est désactivée, HoloLens n’est pas en mesure de charger automatiquement vos [espaces](hololens-spaces.md).

1. Déplacez le curseur sur **On** pour activer la radio Wi-Fi et restaurer les fonctionnalités Wi-Fi sur Microsoft HoloLens. L’état radio Wi-Fi sélectionné (**On** ou **Off**) est conservé en cas de redémarrage.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identification de l’adresse IP de votre HoloLens sur le réseau Wi-Fi

### <a name="by-using-the-settings-app"></a>À l’aide de l’application Paramètres

1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** s’affiche automatiquement devant vous.
1. Sélectionnez **Réseau et Internet**.
1. Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.

    ![Propriétés matérielles dans les paramètres Wi-Fi.](./images/wifi-hololens-hwdetails.jpg)

   L’adresse IP apparaît en regard de **Adresse IPv4**.

### <a name="by-using-voice-commands"></a>À l’aide de commandes vocales

En fonction de la build de votre appareil, vous pouvez utiliser les commandes vocales intégrées ou Cortana pour afficher votre adresse IP. Sur les builds ultérieures à [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), dites « Quelle est mon adresse IP ? » Celle-ci s’affiche alors. Sur les builds antérieures ou sur HoloLens (1ère génération), dites « Hey Cortana, quelle est mon adresse IP ? » Cortana affiche et lit votre adresse IP.

### <a name="by-using-windows-device-portal"></a>À l’aide du portail d’appareil Windows

1. Sur votre PC, à l’aide d’un navigateur web, ouvrez le [portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Accédez à la section **Réseaux**.  
   Cette section affiche votre adresse IP entre autres informations relatives au réseau. Cette méthode vous permet de copier et coller l’adresse IP sur votre ordinateur de développement.

## <a name="change-ip-address-to-static-address"></a>Changer une adresse IP en adresse statique
### <a name="by-using-settings"></a>En utilisant Paramètres
 
1. Ouvrez le menu **Démarrer**.
1. Sélectionnez l’application **Paramètres** dans le menu **Démarrer** ou la liste **Toutes les applications** à droite du menu **Démarrer**. L’application **Paramètres** s’affiche automatiquement devant vous.
1. Sélectionnez **Réseau et Internet**.
1. Faites défiler vers le bas jusqu’à la liste de réseaux Wi-Fi disponibles et sélectionnez **Propriétés matérielles**.
1. Dans la fenêtre **Modifier les paramètres IP** , définissez le premier champ sur **Manuel**.
1. Entrez la configuration IP souhaitée dans les champs restants, puis cliquez sur **Enregistrer**.

### <a name="by-using-windows-device-portal"></a>À l’aide du portail d’appareil Windows

1. Sur votre PC, à l’aide d’un navigateur web, ouvrez le [portail d’appareil](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Accédez à la section **Réseaux**.
1. Sélectionnez le bouton **Configuration IPv4** .
1. Sélectionnez **Utiliser l’adresse IP suivante** et entrez la configuration TCP/IP souhaitée.
1. Sélectionnez **Utiliser les adresses de serveur DNS suivantes** et entrez les adresses de serveur DNS préférées et secondaires, si nécessaire.
1. Cliquez sur **Enregistrer**. 
