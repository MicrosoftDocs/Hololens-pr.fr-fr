---
title: Configurer HoloLens dans un environnement commercial
description: En savoir plus sur le déploiement et la gestion de HoloLens dans les environnements d’entreprise, y compris l’infrastructure, Azure Active Directory et la gestion des appareils mobiles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397220"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>Gestion et déploiement de l’entreprise HoloLens 2

Cette vue d’ensemble est destinée à aider les professionnels de l’informatique à comprendre les considérations relatives au déploiement et à la gestion des appareils Microsoft HoloLens 2 au sein de l’entreprise.

HoloLens 2 s’exécute sur Windows 10 holographique, qui offre aux organisations des technologies de gestion des applications et des appareils mobiles robustes, flexibles et intégrées. Windows 10 holographique prend en charge la gestion du cycle de vie des appareils de bout en bout pour permettre aux entreprises de contrôler leurs appareils, leurs données et leurs applications. HoloLens 2 peut facilement être incorporé dans des pratiques de cycle de vie standard, de l’inscription des appareils, de la configuration et de la gestion des applications à la maintenance et à la retraite à l’aide d’une solution complète de gestion des appareils mobiles.

## <a name="prepare"></a>Préparation

Lorsque vous vous préparez à déployer HoloLens 2 dans votre environnement d’entreprise, plusieurs considérations doivent être examinées et comprises lorsque vous commencez à planifier les déploiements à l’échelle de HoloLens 2.

### <a name="infrastructure-essentials"></a>Notions fondamentales de l’infrastructure

Pour HoloLens 2 dans un scénario de déploiement d’entreprise, certains services d’infrastructure essentiels sont requis pour prendre en charge l’ensemble complet des fonctionnalités. HoloLens 2 a été créé avec une [gestion des appareils mobiles moderne](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) à l’esprit pour le déploiement et la gestion. Avec Azure AD Join + MDM comme moyen principal d’atteindre cela dans un personnel mobile en constante évolution. Les rubriques ci-dessous fournissent une brève présentation de chaque composant d’infrastructure qui doit être pris en compte dans la planification de votre déploiement pour HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. Vous pouvez l’intégrer à des annuaires sur site existants pour créer une solution de gestion des identités hybride. Les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui possède trois éditions : gratuite, Premium P1 et Premium P2 (voir [éditions Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Toutes les éditions prennent en charge l’inscription des appareils Azure AD, mais la version Premium P1 est nécessaire pour activer l’inscription automatique MDM. HoloLens 2 requiert Azure Active Directory join pour activer la plupart des fonctionnalités de niveau entreprise.

> [!NOTE]
> Localement Active Directory Join n’est pas pris en charge sur HoloLens 2.

### <a name="mobile-device-management"></a>Gestion des appareils mobiles
HoloLens 2 est conçu spécifiquement pour être géré par les systèmes de gestion des appareils mobiles (MDM) dans un environnement d’entreprise. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), qui fait partie du Enterprise Mobility + Security, est un système MDM basé sur le Cloud qui gère les appareils dans l’entreprise. Comme Office 365, Intune utilise Azure AD pour la gestion des identités, les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. De nombreux systèmes GPM prennent en charge Windows 10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. Les systèmes MDM peuvent également gérer les déploiements d’applications et les mises à jour pour HoloLens 2. Les autres fournisseurs MDM qui prennent en charge HoloLens 2 incluent actuellement : MobileIron, etc. Tous les fournisseurs de systèmes MDM ont un accès égal aux fournisseurs de services de configuration de la gestion des appareils Windows 10, ce qui permet aux organisations informatiques de sélectionner le système le mieux adapté à leurs besoins en termes de gestion, qu’il s’agisse Microsoft Intune ou d’un produit MDM tiers.

> [!NOTE]
> Les systèmes de gestion de PC traditionnels sur site tels que les System Center Configuration Manager ne sont pas pris en charge sur HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update for Business
Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans Windows Update, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour. Pour plus d’informations sur la gestion des mises à jour HoloLens 2, consultez la documentation sur les [mises à jour hololens](https://docs.microsoft.com/hololens/hololens-updates) .

### <a name="certificates"></a>Certificats
HoloLens 2 prend en charge le déploiement de certificats via MDM si votre environnement requiert des certificats pour l’authentification réseau Corp Wi-Fi ou l’accès à d’autres ressources. Certaines configurations de l’infrastructure MDM peuvent être nécessaires pour activer les déploiements de certificats sur HoloLens 2. En savoir plus sur la [préparation des certificats et des profils réseau pour HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Si vous utilisez Intune, consultez les détails de la configuration de la [certification](https://docs.microsoft.com/mem/intune/protect/certificates-configure) .

## <a name="configure"></a>Configurer

Les administrateurs MDM peuvent définir et implémenter des paramètres de stratégie sur n’importe quel appareil d’entreprise inscrit dans un système MDM. Les paramètres de configuration que vous utilisez varient en fonction du scénario de déploiement. Dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface permettant de lire, de définir, de modifier ou de supprimer des paramètres de configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Pour plus d’informations sur les fournisseurs de services de gestion d’appareils Windows 10 pour HoloLens 2, voir la liste complète des [fournisseurs de services de chiffrement pris en charge dans les appareils hololens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations CSP par le biais de packages d’approvisionnement personnalisés. Les packages d’approvisionnement sont généralement exploités pour les appareils non gérés par MDM et nécessitent une application manuelle sur chaque appareil. Pour plus d’informations sur la création de packages d’approvisionnement personnalisés, consultez la documentation sur la [configuration de HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) .

> [!NOTE]
> HoloLens 2 prend en charge [Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), fournissant un processus simple et facile pour la gestion des configurations d’appareils Windows 10 de votre entreprise.

### <a name="identity-management"></a>Gestion des identités

Les employés peuvent utiliser un seul compte pour initialiser un appareil afin qu’il&#39;s impératifs que votre organisation contrôle le compte qui est activé en premier. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion. HoloLens 2 prend en charge 3 types de comptes : compte d’utilisateur local, compte Microsoft personnel et comptes de Azure Active Directory. Nous vous recommandons vivement de tirer parti de Azure Active Directory pour votre solution de gestion des identités d’entreprise, car elle activera toutes les fonctionnalités sur vos appareils HoloLens 2. Pour plus d’informations sur les identités pour HoloLens 2, consultez [identité hololens](https://docs.microsoft.com/hololens/hololens-identity) .

### <a name="network-and-connectivity"></a>Réseau et connectivité

Étant donné que HoloLens 2 est un appareil Cloud en premier, l’accès réseau aux ressources en ligne est requis pour la mise à disposition de toutes les fonctionnalités et fonctionnalités. Si vous déployez des appareils HoloLens 2 avec une connectivité à votre réseau intranet d’entreprise, vous devrez peut-être mettre à jour vos règles de proxy/pare-feu pour autoriser l’accès aux services Cloud HoloLens 2. Pour plus d’informations, consultez la liste des points de [terminaison courants pour le système d’exploitation HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline). L’accès à des points de terminaison supplémentaires peut être nécessaire pour que les applications ou d’autres services Cloud s’exécutent correctement sur HoloLens 2.

Voici quelques-uns des services HoloLens 2 courants nécessitant un accès au point de terminaison supplémentaire :

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guides D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Assistance à distance D365 (infrastructure des équipes O365)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Déploiement de certificats

Si des certificats sont requis pour l’accès aux réseaux d' Wi-Fi d’entreprise ou à d’autres services au sein de votre organisation, HoloLens 2 prend en charge le déploiement de certificats d’utilisateur et de périphérique via MDM. Remarque : votre solution MDM peut nécessiter une configuration d’infrastructure supplémentaire pour déployer des certificats sur des appareils Windows 10.

### <a name="security-review"></a>Revue de sécurité

La plupart des services informatiques d’entreprise nécessitent l’évaluation et l’examen des nouveaux appareils déployés sur un réseau d’entreprise. Si votre organisation a besoin d’une révision de sécurité de HoloLens 2, vous trouverez plus de détails pour vous aider à [obtenir des approbations de sécurité](https://docs.microsoft.com/hololens/security-overview).

### <a name="common-hololens-2-device-settings"></a>Paramètres courants de l’appareil HoloLens 2

Lors du déploiement d’appareils HoloLens 2 dans un environnement d’entreprise, il existe plusieurs configurations d’appareil courantes qui peuvent être prises en compte lors de la planification de votre déploiement de HoloLens 2. Cette liste met en évidence les configurations et les paramètres qui sont assez courants et ne comprend pas une liste complète des options disponibles :

| Paramètre de l’appareil | Brève description.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrictions matérielles](hololens-requirements.md#hardware-restrictions)               | Les restrictions matérielles réduisent la connectivité et aident à la protection des données.                        |
| [Profils Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurez Wi-Fi profils sans intervention de l’utilisateur ou interaction.                              |
| [Certificates](hololens-requirements.md#certificates-1)               | Fournir l’authentification de compte et/ou de Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gérer le trafic interne.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Contrôler l’accès aux applications et aux ressources sur l’intranet de l’entreprise.                               |
| [Mode plein écran](hololens-requirements.md#kiosk-mode) | Limite les applications présentées aux utilisateurs par le biais de l’interface utilisateur. |

#### <a name="hardware-restrictions"></a>Restrictions matérielles

HoloLens 2 utilise la technologie de pointe qui comprend des fonctionnalités matérielles populaires telles que les appareils photo, les microphones, les intervenants, les interfaces USB, les interfaces Bluetooth et le Wi-Fi. Vous pouvez utiliser les restrictions matérielles pour contrôler la disponibilité de ces fonctionnalités.

La liste suivante répertorie les paramètres MDM les plus couramment utilisés que HoloLens 2 prend en charge pour configurer des restrictions matérielles. Certaines de ces restrictions matérielles assurent la connectivité et contribuent à protéger les données.

- [**Autoriser le Wi-Fi :**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si les utilisateurs peuvent activer et utiliser la radio Wi-Fi sur leurs appareils
- [**Autoriser la connexion USB :**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la connexion USB est activée (&#39;t affecte le chargement USB)
- [**Autoriser Bluetooth :**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si les utilisateurs peuvent activer et utiliser la radio Bluetooth sur leurs appareils

En savoir plus sur les autres [restrictions d’appareils courantes.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Profils Wi-Fi

La plupart des réseaux Wi-Fi nécessitent des certificats et d’autres informations complexes pour visant à limiter et à sécuriser l’accès des utilisateurs. Ces informations de Wi-Fi avancées sont difficiles à configurer par les utilisateurs standard, mais les systèmes MDM peuvent entièrement configurer ces profils Wi-Fi sans intervention de l’utilisateur. Vous pouvez créer plusieurs profils Wi-Fi dans votre système GPM.

Pour plus d’informations sur les paramètres de Wi-Fi pour Windows 10, consultez [paramètres Enterprise Profil WiFi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### <a name="certificates"></a>Certificats

Les certificats aident à améliorer la sécurité en fournissant l’authentification de compte, l’authentification Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. Bien que les administrateurs puissent gérer les certificats sur les appareils manuellement par le biais de packages de provisionnement, il&#39;recommandé d’utiliser votre système MDM pour gérer ces certificats tout au long de leur cycle de vie, de l’inscription à la révocation et du renouvellement. Votre système MDM peut déployer automatiquement ces certificats sur les périphériques&#39; les magasins de certificats après l’inscription de l’appareil (à condition que le système MDM prenne en charge le Protocole d’inscription de certificats simple (SCEP) ou les normes de chiffrement à clé publique #12 (PKCS # 12)). MDM peut également interroger et supprimer des certificats clients inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel.

En savoir plus sur la [préparation des certificats et des profils réseau pour HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

La plupart des réseaux intranet d’entreprise tirent parti d’un proxy pour gérer le trafic interne. Avec HoloLens 2, vous pouvez configurer un serveur proxy pour les connexions Ethernet et Wi-Fi. Ces paramètres ne s’appliquent pas aux connexions VPN.

Pour plus d’informations sur les paramètres de proxy pour Windows 10, consultez [CSP NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>VPN

Les organisations utilisent souvent un VPN pour contrôler l’accès aux applications et aux ressources sur l’intranet de leur entreprise&#39;s. HoloLens 2 prend en charge les connexions VPN SSL, qui nécessitent un plug-in téléchargeable à partir de la Microsoft Store et sont spécifiques au fournisseur VPN de votre choix.

Pour plus d’informations sur les profils VPN, voir [Fournisseur CSP VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

#### <a name="kiosk-mode"></a>Mode plein écran

Vous pouvez configurer un appareil HoloLens 2 pour qu’il fonctionne comme un appareil à usage fixe, également appelé kiosque, en configurant l’appareil pour qu’il s’exécute en mode plein écran. Le mode plein écran limite les applications (ou utilisateurs) qui sont disponibles sur l’appareil. Le mode plein écran est une fonctionnalité pratique que vous pouvez utiliser pour dédier un appareil HoloLens 2 à des applications d’entreprise, ou pour utiliser l’appareil HoloLens 2 dans une démonstration d’application.

Pour plus d’informations sur la configuration d’un HoloLens 2 en mode plein écran, consultez [configurer hololens en tant que kiosque](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Déployer

### <a name="mdm-device-enrollment"></a>Inscription des appareils MDM

Pour les déploiements d’entreprise, il est recommandé d' [inscrire des appareils](https://docs.microsoft.com/hololens/hololens-enroll-mdm) dans MDM comme appareils d’entreprise uniquement avec l’inscription de Azure ad et la gestion automatique des appareils mobiles (Azure ad + MDM). Cela nécessite Azure AD Premium et prend en charge l’inscription automatique à plusieurs fournisseurs MDM, y compris Intune.

En savoir plus sur le [AutoPilot](https://docs.microsoft.com/hololens/hololens2-autopilot)de la méthode d’inscription en libre-déploiement.

### <a name="application-deployment"></a>Déploiement d’application

La productivité de l’utilisateur sur les appareils mobiles dépend souvent des applications.

Windows 10 permet de développer des applications qui fonctionnent en toute transparence sur plusieurs appareils à l’aide de la plateforme Windows universelle (UWP) pour les applications Windows.

Il existe plusieurs façons de déployer des applications sur des appareils HoloLens 2. Les applications peuvent être déployées directement via MDM, le Microsoft Store pour entreprises ou faisant via un package d’approvisionnement. Pour plus d’informations, consultez la documentation relative au [déploiement d’applications](https://docs.microsoft.com/hololens/app-deploy-overview) .

> [!NOTE]
> HoloLens 2 prend en charge l’exécution d’applications ARM64 UWP uniquement.

## <a name="maintain"></a>Maintenance

Dans les environnements informatiques d’entreprise, le besoin de sécurité et de contrôle des coûts doit être mis en balance avec le désir de fournir aux utilisateurs les technologies les plus récentes. Étant donné que les cyberattaques sont devenus une occurrence quotidienne, il est important de conserver correctement l’état de vos appareils Windows 10. Le service informatique doit contrôler les paramètres de configuration, en veillant bien à leur conformité, et déterminer quels appareils peuvent accéder aux applications internes. HoloLens 2 fournit les fonctionnalités de gestion des opérations mobiles nécessaires pour s’assurer que les appareils sont conformes à la stratégie d’entreprise.

### <a name="os-servicing-options"></a>Options de maintenance du système d’exploitation

**Un processus de mise à jour simplifié**

Microsoft simplifié l’ingénierie et le cycle de lancement des produits Windows afin de pouvoir fournir les nouvelles fonctions, expériences et fonctionnalités exigées par le marché plus rapidement que jamais. Microsoft prévoit de mettre à disposition deux mises à jour de fonctionnalité par an (période de 12 mois). Les **mises à jour de fonctionnalités** établissent un Current Branch ou un CB, et ont une version associée.

Microsoft fournira et installera également des mises à jour pour la sécurité et la stabilité directement sur les appareils HoloLens 2. Ces **mises à jour qualité** , publiées sous le contrôle Microsoft via Windows Update, sont disponibles tous les mois. HoloLens 2 consomme des mises à jour de fonctionnalités et des mises à jour qualité dans le cadre du même processus de mise à jour standard.

Les clients d’entreprise peuvent gérer l’expérience et le processus de mise à jour sur HoloLens 2S à l’aide d’un système MDM. Dans la plupart des cas, les stratégies de gestion du processus de mise à jour s’appliquent aux mises à jour de fonctionnalités et qualité. Plus d’informations sur la [configuration de MDM pour les mises à jour HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="managing-applications"></a>Gestion des applications

Les administrateurs informatiques peuvent contrôler les applications qui sont autorisées à être installées sur HoloLens 2 et comment elles doivent être tenues à jour.

HoloLens 2 prend en charge [Windows Defender application Control (WDac)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), qui permet aux administrateurs de créer, d’autoriser ou d’interdire des listes d’applications à partir de la Microsoft Store. Cette fonctionnalité s’étend également aux applications intégrées. La possibilité d’autoriser ou de refuser des applications permet de s’assurer que les utilisateurs utilisent leurs appareils à des fins prévues. Cependant, il n’est pas toujours simple de répondre à la fois aux besoins ou aux demandes des employés et aux préoccupations en matière de sécurité. La création de listes d’autorisation ou d’interdiction nécessite également de suivre le paysage de l’application en cours de Microsoft Store.

Pour plus d’informations, consultez [application Control CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Mettre hors service

La mise hors service de l’appareil est la dernière phase du cycle de vie de l’appareil. Il&#39;s important que les appareils remplacés par des modèles plus récents soient mis hors service en toute sécurité, car&#39;vous ne souhaitez pas que les données de l’entreprise restent sur des appareils ignorés qui pourraient compromettre la confidentialité de vos données. Le service informatique a également besoin d’un moyen de prendre en charge de manière appropriée les utilisateurs qui ont besoin d’effacer des appareils perdus ou volés.

HoloLens 2 prend en charge trois méthodes de nettoyage de l’appareil

**Réinitialisation de la fabrique MDM :** Rétablit HoloLens 2 sur l’image de fabrique par le biais de la commande MDM initiée par l’administrateur. Efface toutes les données stockées sur l’appareil.

**Réinitialisation de l’appareil dans les paramètres :** Les utilisateurs finaux peuvent réinitialiser manuellement le HoloLens 2 dans l’application paramètres sur l’appareil. Efface toutes les données stockées sur l’appareil.

**Complément de récupération avancé (ARC) :** À partir d’un PC exécutant l’outil ARC, un utilisateur ou un administrateur peut flasher un HoloLens 2 connecté au PC via un câble USB. Efface toutes les données stockées sur l’appareil.

> [!div class="nextstepaction"]
> [Scénarios de déploiement courants](common-scenarios.md)
