---
title: Résolution des problèmes liés à l'implémentation et à la gestion des appareils HoloLens 2
description: Résolution des problèmes liés aux appareils HoloLens 2 dans un environnement d'entreprise
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Résolution de problèmes
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428166"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Résolution des problèmes liés à l'implémentation et à la gestion des appareils 

Cet article explique comment résoudre différents problèmes ou répondre à des questions concernant l'implémentation et la gestion des appareils HoloLens 2.

>[!IMPORTANT]
> Avant d'entamer une procédure de résolution des problèmes, assurez-vous que la batterie de votre appareil est, si possible, chargée à **20 ou 40 %** de sa capacité. Les [témoins](hololens2-setup.md#lights-that-indicate-the-battery-level) situés sous le bouton d'alimentation permettent de vérifier rapidement la capacité de la batterie sans se connecter à l'appareil.


<a id="list"></a>
- [Résolution des problèmes EAP](#eap-troubleshooting)
- [Résolution des problèmes liés au Wi-Fi](#wi-fi-troubleshooting)
- [Résolution des problèmes de réseau](#network-troubleshooting)
- [Impossible de se connecter à un appareil HoloLens déjà configuré](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Impossible de se connecter après la mise à jour vers Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Résolution des problèmes liés à Autopilot](#autopilot-troubleshooting)
- [Questions fréquentes (FAQ) sur les appareils HoloLens gérés](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Résolution des problèmes liés au protocole EAP
1. Vérifiez que les paramètres de votre profil Wi-Fi sont corrects :
    - Le type EAP est correctement configuré. Types EAP courants : EAP-TLS (13), EAP-TTLS (21) et PEAP (25).
    - Le nom SSID du Wi-Fi est correct et correspond à la chaîne HEX.
    - Pour EAP-TLS, TrustedRootCA contient le hachage SHA-1 du certificat d'autorité de certification racine de confiance du serveur. Sur un Windows PC, la commande « certutil.exe -dump cert_file_name » affiche la chaîne de hachage SHA-1 d'un certificat.
2. Collectez la capture des paquets réseau dans les journaux du point d'accès, du contrôleur ou du serveur AAA pour déterminer où la session EAP échoue.
    - Si l'identité EAP fournie par l'HoloLens n'est pas attendue, vérifiez que l'identité a été correctement configurée via le profil Wi-Fi ou le certificat client.
    - Si le serveur rejette le certificat client de l'HoloLens, vérifiez que le certificat client requis a été configuré sur l'appareil.
    - Si l'HoloLens rejette le certificat du serveur, vérifiez que le certificat d'autorité de certification racine du serveur a été configuré sur l'HoloLens.
3. Si le profil d'entreprise est configuré via le package de configuration Wi-Fi, pensez à appliquer ce package sur un PC Windows 10. S'il échoue également sur un PC Windows 10, suivez le guide de résolution des problèmes d'authentification du client Windows 802.1X.
4. Faites-nous part de vos commentaires via le Hub de commentaires.

[Retour à la liste](#list)

## <a name="wi-fi-troubleshooting"></a>Résolution des problèmes liés au Wi-Fi

Si vous ne parvenez pas à connecter votre HoloLens à un réseau Wi-Fi, vous pouvez essayer ce qui suit :

1. Vérifiez que le Wi-Fi est activé. Pour ce faire, utilisez le mouvement associé au menu Démarrer, puis sélectionnez Paramètres > Réseau et Internet > Wi-Fi. Si le Wi-Fi est activé, essayez de le désactiver puis de le réactiver.
2. Rapprochez-vous du routeur ou du point d'accès.
3. Redémarrez votre routeur Wi-Fi, puis redémarrez l'HoloLens. Réessayez de vous connecter.
4. Si le problème persiste, vérifiez que votre routeur utilise le microprogramme le plus récent. Cette information est disponible sur le site web du fabricant.

Lorsque vous vous connectez à un compte d'entreprise ou d'organisation sur l'appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GPM), si votre administrateur informatique en a configuré une.

[Retour à la liste](#list)

## <a name="network-troubleshooting"></a>Résolution des problèmes de réseau
Si les problèmes de réseau sont un obstacle à la réussite du déploiement et de l’utilisation d’HoloLens 2 dans votre organisation, configurez Fiddler et/ou Wireshark pour capturer et analyser le trafic HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Configurer Fiddler pour capturer le trafic HTTP
Fiddler est un proxy de débogage web qui est utilisé pour résoudre les problèmes HTTP(S). Il capture chaque requête HTTP que l’ordinateur effectue et enregistre tout ce qui y est associé. La découverte des problèmes d’authentification des utilisateurs finaux pour vos applications HTTPS améliore la productivité et l’efficacité de vos cas d’utilisation HoloLens 2 cibles. 

#### <a name="prerequisites"></a>Prérequis
 
- Les appareils HoloLens 2 et votre ordinateur doivent se trouver sur le même réseau.
- Notez l’adresse IP de votre PC.

#### <a name="install-and-configure-fiddler"></a>Installer et configurer Fiddler

1. Sur votre PC, [installez](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) et démarrez Fiddler.  
1. Sur votre PC, configurez Fiddler pour autoriser les ordinateurs distants à se connecter.
    1. Accédez à Fiddler Settings -> Connections (Paramètres Fiddler -> Connexions)
    1. Notez le port d’écoute pour Fiddler (la valeur par défaut est 8866)
    1. Cochez Allow remote computers to connect (Autoriser les ordinateurs distants à se connecter)
    1. Cliquez sur Enregistrer.
3. Sur votre HoloLens 2, configurez Fiddler comme serveur proxy<sup>1</sup> :
    1. Ouvrez le menu Start (Démarrer) et sélectionnez Settings (Paramètres).
    1. Sélectionnez Network & Internet (Réseau et Internet), puis Proxy dans le menu de gauche.
    1. Faites défiler jusqu’à Manual proxy setup (Configuration manuelle du proxy) et définissez Use a proxy server (Utiliser un serveur proxy) sur On (Activé).
    1. Entrez l’adresse IP du PC où Fiddler est installé
    1. Entrez le numéro de port que vous avez noté ci-dessus (la valeur par défaut est 8866)
    1. Cliquez sur Enregistrer.

<sup>1</sup> Pour les builds 20279.1006+ (Insiders et la version à venir), utilisez les étapes suivantes pour configurer le proxy :
1. Ouvrez le menu Start et accédez à la page des propriétés de votre réseau Wi-Fi. 
1. Faites défiler jusqu'à Proxy.
1. Basculez vers Configuration manuelle.
1. Entrez l’adresse IP du PC où Fiddler est installé
1. Entrez le numéro de port que vous avez noté ci-dessus (la valeur par défaut est 8866)
1. Cliquer sur Apply
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Déchiffrer le trafic HTTPS provenant d’HoloLens 2

1. Sur votre PC, exportez le certificat Fiddler.
    1. Accédez Fiddler Settings -> HTTPS (Paramètres Fiddler -> HTTPS) et développez Advanced Settings (Paramètres avancés)
    2. Cliquez sur Export Fiddler certificate (Exporter le certificat Fiddler). Il va être enregistré sur votre ordinateur.
    3. Déplacez le certificat vers le dossier Downloads (Téléchargements) de votre HoloLens 2

2.  Sur votre HoloLens 2, importez le certificat Fiddler.
    1. Accédez à Settings -> Update and Security -> Certificates (Paramètres -> Mise à jour et sécurité -> Certificats)
    2. Cliquez sur Install Certificate (Installer un certificat), accédez au dossier Downloads (Téléchargements) et sélectionnez le certificat Fiddler.
    3. Changer l’emplacement de stockage sur la machine locale
    4. Changer le magasin de certificats en magasin racine
    5. Sélectionnez Install (Installer).
    6. Vérifiez que le certificat apparaît dans la liste des certificats. Si ce n’est pas le cas, répétez les étapes ci-dessus.

#### <a name="inspect-https-sessions"></a>Inspecter les sessions HTTP(S)

Sur votre PC, Fiddler va montrer les sessions HTTP(S) en direct d’HoloLens 2. Le panneau Inspectors de Fiddler peut montrer la requête/réponse HTTP(S) dans différentes vues : par exemple, la vue « Raw » montre la requête ou la réponse en texte brut. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Configurer Wireshark pour capturer le trafic réseau
Wireshark est un analyseur de protocole réseau qui est utilisé pour inspecter le trafic TCP/UDP depuis et vers vos appareils HoloLens 2. Ceci permet d’identifier facilement le trafic qui traverse votre réseau vers votre HoloLens 2, sa quantité, sa fréquence, le temps de latence entre certains tronçons, etc.

#### <a name="prerequisites"></a>Prérequis :
- Le PC doit avoir accès à Internet et prendre en charge le partage Internet sur Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Installer et configurer Wireshark
1. Sur votre PC, installez [Wireshark](https://www.wireshark.org/#download) 
1. Sur votre PC, activez le point d’accès mobile pour partager votre connexion Internet à partir du Wi-Fi.
1. Sur votre PC, démarrez Wireshark et capturez le trafic à partir de l’interface du point d’accès mobile. 
1. Sur votre HoloLens 2, remplacez son réseau Wi-Fi par le point d’accès Mobile du PC. Le trafic IP d’HoloLens 2 apparaît dans Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analyser les journaux Wireshark
Les filtres Wireshark peuvent vous aider à filtrer les paquets qui vous intéressent. 

Consultez le [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) d’origine.

[Retour à la liste](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Impossible de se connecter à un appareil HoloLens déjà configuré

Si votre appareil a déjà été configuré pour un autre utilisateur, comme un client ou un ancien employé, et que vous ne disposez pas de son mot de passe pour déverrouiller l'appareil, vous pouvez utiliser Intune pour [réinitialiser](/intune/remote-actions/devices-wipe) l'appareil à distance. L'appareil se réinitialise alors.  
> [!IMPORTANT]
> Lorsque vous réinitialisez l'appareil, décochez **Conserver l'état d'inscription et le compte d'utilisateur**.

[Retour à la liste](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Impossible de se connecter après la mise à jour vers Windows Holographic 21H1

### <a name="symptoms"></a>Symptômes
- La connexion à l'aide du code PIN échoue alors que le bon code PIN a été utilisé.
- L'utilisation de la méthode de connexion web échoue après la connexion à la page web.
- L'appareil n'est pas répertorié comme « joint à Azure AD » sous [Portail Azure](https://portal.azure.com/) -> Azure Active Directory -> Appareils.

### <a name="cause"></a>Cause
L'appareil concerné a peut-être été supprimé du locataire Azure AD. Cela peut par exemple se produire pour les raisons suivantes :

- Un administrateur ou un utilisateur a supprimé l'appareil sur le portail Azure ou à l'aide de PowerShell.
- L'appareil a été supprimé du locataire Azure AD pour cause d'inactivité. Pour une gestion efficace de l'environnement, nous recommandons généralement aux administrateurs informatiques de [supprimer les appareils obsolètes et inactifs de leur locataire Azure AD](/azure/active-directory/devices/manage-stale-devices).

Lorsqu'un appareil concerné tente à nouveau de contacter le locataire Azure AD après sa suppression, il ne parvient pas à s'authentifier auprès d'Azure AD. Cet effet est souvent invisible pour l'utilisateur de l'appareil, car la connexion en cache via le code PIN continue à permettre à l'utilisateur de se connecter.

### <a name="mitigation"></a>Limitation des risques
Il n'existe actuellement aucun moyen de rajouter un appareil HoloLens supprimé dans Azure AD. Les appareils concernés doivent être réinitialisés en suivant les instructions de [réinitialisation](hololens-recovery.md#clean-reflash-the-device).

[Retour à la liste](#list)

## <a name="autopilot-troubleshooting"></a>Résolution des problèmes liés à Autopilot

Les articles suivants vous permettront d'en savoir plus et de résoudre les problèmes liés à Autopilot. Sachez toutefois que ces articles sont basés sur la version bureau de Windows 10 et que certaines informations ne s'appliquent pas à l'HoloLens :

- [Windows AutoPilot : problèmes connus](/mem/autopilot/known-issues)
- [Résolution des problèmes d’inscription d’appareils Windows dans Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot : conflits de stratégie](/mem/autopilot/policy-conflicts)

[Retour à la liste](#list)

## <a name="managed-hololens-devices-faqs"></a>Questions fréquentes (FAQ) sur les appareils HoloLens gérés

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Puis-je utiliser System Center Configuration Manager (SCCM) pour gérer les appareils HoloLens ?

Non. Pour gérer les appareils HoloLens, vous devez utiliser un système GPM.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Puis-je utiliser les services de domaine Active Directory (AD DS) pour gérer les comptes d'utilisateur HoloLens ?

Non. Pour gérer les comptes d'utilisateur des appareils HoloLens, vous devez utiliser Azure Active Directory (Azure AD).

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>L'HoloLens est-il capable d'enregistrer automatiquement les systèmes de capture automatique de données (ADCS) ?

Non.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>L'HoloLens peut-il participer à l'authentification Windows intégrée ?

Non.

### <a name="does-hololens-support-branding"></a>L'HoloLens prend-il en charge la personnalisation ?

Non. Cependant, vous pouvez contourner ce problème en utilisant l'une des approches suivantes :

- Créez une application personnalisée, puis [activez le mode plein écran](hololens-kiosk.md). L'application personnalisée peut intégrer une personnalisation et lancer d'autres applications (comme Remote Assist).  
- Dans Azure AD, remplacez toutes les photos de profil des utilisateurs par le logo de votre entreprise. Ceci n'est toutefois pas souhaitable pour certains scénarios.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Quelles capacités de journalisation l'HoloLens 2 offre-t-il ?

La journalisation est limitée aux suivis qui peuvent être capturés dans certains scénarios de développement ou de résolution des problèmes, ou aux données de télémétrie que les appareils envoient aux serveurs Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Questions relatives à la sécurisation des appareils HoloLens

Consultez les [informations sur la sécurité de l'HoloLens 2](security-overview.md).
Pour les appareils HoloLens de 1ère génération, consultez [ces questions fréquentes (FAQ)](hololens1-faq-security.yml).

[Retour à la liste](#list)
