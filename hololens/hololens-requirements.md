---
title: Configurer HoloLens dans un environnement commercial
description: En savoir plus sur le déploiement et la gestion de HoloLens dans les environnements d’entreprise, notamment l’infrastructure, Azure Active Directory et la gestion des appareils mobiles.
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
ms.openlocfilehash: 9458a6fd02cf96dd265580cb099e39fa221d4206
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284045"
---
# Gestion et déploiement d’entreprise HoloLens 2

Cette vue d’ensemble est destinée à aider les professionnels de l’informatique à comprendre les considérations à prendre en compte pour le déploiement et la gestion d’appareils Microsoft HoloLens 2 au sein de l’entreprise.

HoloLens 2 s’exécute sur Windows 10 Holographique, qui fournit aux organisations des technologies de gestion des applications et des appareils mobiles robustes, flexibles et intégrées. Windows 10 Holographic prend en charge la gestion du cycle de vie des appareils de bout en bout pour donner aux entreprises le contrôle sur leurs appareils, données et applications. HoloLens 2 peut facilement être intégré aux pratiques de cycle de vie standard, de l’inscription des appareils, de la configuration et de la gestion des applications à la maintenance et à la mise en retrait à l’aide d’une solution complète de gestion des appareils mobiles.

## Préparation

Lorsque vous vous préparez à déployer HoloLens 2 dans votre environnement d’entreprise, plusieurs considérations doivent être examinées et comprises lorsque vous commencez à planifier des déploiements à grande échelle de HoloLens 2.

### Infrastructure Essentials

Pour HoloLens 2 dans un scénario de déploiement d’entreprise, certains services d’infrastructure essentiels sont requis pour prendre en charge l’ensemble complet des fonctionnalités. HoloLens 2 a été conçu avec [la gestion des](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) appareils mobiles modernes à l’esprit pour le déploiement et la gestion. Avec Azure AD Join + GD comme principal moyen d’atteindre ce niveau dans un personnel mobile en constante augmentation. Les rubriques ci-dessous fournissent une brève vue d’ensemble de chaque composant d’infrastructure à prendre en compte dans votre planification de déploiement pour HoloLens 2.

### Azure Active Directory
Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. Vous pouvez l’intégrer à des annuaires sur site existants pour créer une solution de gestion des identités hybride. Les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui possède trois éditions : Gratuite, Premium P1 et Premium P2 (voir [éditions Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Toutes les éditions prendre en charge l’inscription d’appareils Azure AD, mais Premium P1 est nécessaire pour activer l’inscription automatique mdm. HoloLens 2 nécessite Azure Active Directory Join pour activer la plupart des fonctionnalités et fonctionnalités au niveau de l’entreprise.

> [!NOTE]
> Active Directory Join local n’est pas pris en charge sur HoloLens 2.

### Gestion des appareils mobiles
HoloLens 2 est conçu spécifiquement pour être géré par les systèmes de gestion des périphériques mobiles (MDM) dans un environnement d’entreprise. Microsoft [Intune, qui](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)fait partie de Enterprise Mobility + Security, est un système GDM basé sur le cloud qui gère les appareils dans l’entreprise. Comme Office 365, Intune utilise Azure AD pour la gestion des identités, afin que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. De nombreux systèmes GPM prennent en charge Windows10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. Les systèmes de gestion des applications de gestion des applications peuvent également gérer les déploiements d’applications et les mises à jour pour HoloLens 2. Les autres fournisseurs de gestion des périphériques mobiles qui supportent HoloLens 2 incluent actuellement : AirWatch, MobileIron, etc. Tous les fournisseurs de systèmes mdm ont un accès égal aux fournisseurs de services de configuration de gestion des appareils Windows 10, ce qui donne aux organisations informatiques la liberté de sélectionner le système le mieux adapté à leurs besoins de gestion, que Microsoft Intune ou un produit MDM tiers.

> [!NOTE]
> Les systèmes de gestion de PC locaux traditionnels tels que System Center Configuration Manager ne sont pas pris en charge sur HoloLens 2.

### WindowsUpdate for Business
Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour. Pour plus [d’informations](https://docs.microsoft.com/hololens/hololens-updates) sur la gestion des mises à jour HoloLens 2, voir la documentation des mises à jour HoloLens.

### Certificats
HoloLens 2 prend en charge le déploiement de certificats via la gestion des applications de gestion des applications (MDM) si votre environnement nécessite des certificats pour l’authentification réseau Wi-Fi Corp ou l’accès à d’autres ressources. Certaines configurations d’infrastructure MDM peuvent être nécessaires pour activer les déploiements de certificats sur HoloLens 2. Découvrez comment préparer [les certificats et les profils réseau pour HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Si vous utilisez Intune, consultez les détails de [la configuration de certification.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## Configurer

Les administrateurs mdm peuvent définir et implémenter des paramètres de stratégie sur n’importe quel appareil d’entreprise inscrit dans un système DE GESTION. Les paramètres de configuration que vous utilisez diffèrent en fonction du scénario de déploiement. Dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface pour lire, définir, modifier ou supprimer des paramètres de configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Pour plus d’informations sur les CSP de gestion des appareils Windows 10 pour HoloLens 2, consultez la liste complète des CSP pris en charge dans les [appareils HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations CSP via des packages d’approvisionnement personnalisés. Les packages d’approvisionnement sont généralement utilisés pour les appareils non gérés par la gestion des périphériques mobiles et doivent être appliqués manuellement à chaque appareil. Pour plus [d’informations sur](https://docs.microsoft.com/hololens/hololens-provisioning) la création de packages d’approvisionnement personnalisés, voir la documentation d’approvisionnement HoloLens.

> [!NOTE]
> HoloLens 2 prend en charge [Windows Autopilot,](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)offrant un processus simple et simple de gestion des configurations de votre appareil Windows 10 d’entreprise.

### Gestion des identités

Les employés ne peuvent utiliser qu’un seul compte pour initialiser un appareil afin&#39;impératif que votre organisation contrôle d’abord quel compte est activé. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion. HoloLens 2 prend en charge 3 types de comptes : compte d’utilisateur local, compte Microsoft personnel et comptes Azure Active Directory. Il est vivement recommandé de tirer parti d’Azure Active Directory pour votre solution de gestion des identités d’entreprise, car elle activera toutes les fonctionnalités sur vos appareils HoloLens 2. Consultez [l’identité HoloLens](https://docs.microsoft.com/hololens/hololens-identity) pour plus d’informations sur les identités pour HoloLens 2.

### Réseau et connectivité

Comme HoloLens 2 est un premier appareil cloud, l’accès réseau aux ressources en ligne est nécessaire pour que toutes les fonctionnalités et fonctionnalités soient disponibles. Si vous déployez des appareils HoloLens 2 avec une connectivité à votre réseau intranet d’entreprise, vous de devez peut-être mettre à jour vos règles de proxy/pare-feu pour autoriser l’accès aux services cloud HoloLens 2. Pour plus d’informations, voir la liste des points de terminaison courants pour le système [d’exploitation HoloLens 2.](https://docs.microsoft.com/hololens/hololens-offline) L’accès à des points de terminaison supplémentaires peut être nécessaire pour que les applications ou d’autres services cloud s’exécutent correctement sur HoloLens 2.

Voici quelques services HoloLens 2 courants nécessitant un accès supplémentaire aux points de terminaison :

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 Guides](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (infrastructure O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Déploiement de certificats

Si des certificats sont requis pour l’accès aux réseaux Wi-Fi d’entreprise ou à d’autres services au sein de votre organisation, HoloLens 2 prend en charge le déploiement de certificats d’utilisateur et d’appareil via la gestion des périphériques mobiles. Remarque : votre solution MDM peut nécessiter une configuration d’infrastructure supplémentaire pour déployer des certificats sur des appareils Windows 10.

### Examen de la sécurité

La plupart des services informatiques d’entreprise nécessitent une évaluation et un examen des nouveaux appareils déployés sur un réseau d’entreprise. Si votre organisation a besoin d’une révision de sécurité de HoloLens 2, vous trouverez plus de détails pour vous aider à obtenir des [approbations de sécurité.](https://docs.microsoft.com/hololens/security-overview)

### Paramètres courants de l’appareil HoloLens 2

Lorsque vous déployez des appareils HoloLens 2 dans un environnement d’entreprise, plusieurs configurations d’appareils courantes peuvent être envisagées lors de la planification de votre déploiement de HoloLens 2. Cette liste met en évidence les configurations et les paramètres qui sont jugés assez courants et ne comprend pas une liste complète des options disponibles :

| Paramètre de l’appareil | Brève description.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrictions matérielles](hololens-requirements.md#hardware-restrictions)               | Les restrictions matérielles réduisent la connectivité et aident à la protection des données.                        |
| [Profils Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurez Wi-Fi profils sans intervention ni interaction de l’utilisateur.                              |
| [Certificats](hololens-requirements.md#certificates-1)               | Fournir un compte et/ou une authentification Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu web. |
| [Proxy](hololens-requirements.md#proxy)              | Gérer le trafic interne.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Contrôler l’accès aux applications et aux ressources sur l’intranet de leur entreprise.                               |
| [Mode plein écran](hololens-requirements.md#kiosk-mode) | Limite les applications présentées aux utilisateurs via l’interface utilisateur. |

#### Restrictions matérielles

HoloLens 2 utilise une technologie de pointe qui inclut des fonctionnalités matérielles populaires telles que des caméras, des microphones, des haut-parleurs, des interfaces USB, des interfaces Bluetooth et le Wi-Fi. Vous pouvez utiliser les restrictions matérielles pour contrôler la disponibilité de ces fonctionnalités.

L’exemple suivant répertorie les paramètres de gestion des appareils de gestion des appareils les plus couramment utilisés par HoloLens 2 pour configurer les restrictions matérielles. Certaines de ces restrictions matérielles assurent la connectivité et permettent de protéger les données.

- [**Autoriser le WiFi :**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si les utilisateurs peuvent activer et utiliser la radio Wi-Fi sur leurs appareils
- [**Autoriser la connexion USB :**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la connexion USB est activée (n’affecte&#39;charge USB)
- [**Autorisez Bluetooth :**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si les utilisateurs peuvent activer et utiliser la radio Bluetooth sur leurs appareils

En savoir plus sur les [autres restrictions d’appareil courantes.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Profils Wi-Fi

La plupart des réseaux Wi-Fi nécessitent des certificats et d’autres informations complexes pour visant à limiter et à sécuriser l’accès des utilisateurs. Ces informations de Wi-Fi avancées sont difficiles à configurer pour les utilisateurs classiques, mais les systèmes de gestion des données mobiles peuvent entièrement configurer ces profils Wi-Fi sans intervention de l’utilisateur. Vous pouvez créer plusieurs profils Wi-Fi dans votre système GPM.

Pour plus d’informations sur Wi-Fi paramètres de windows 10, voir [Paramètres WiFi de profil d’entreprise.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### Certificats

Les certificats contribuent à améliorer la sécurité en fournissant l’authentification de compte, Wi-Fi l’authentification, le chiffrement VPN et le chiffrement SSL du contenu web. Bien que les administrateurs peuvent gérer manuellement les certificats sur les appareils par le biais de packages d’approvisionnement, il est&#39;d’utiliser votre système de gestion des périphériques mobiles pour gérer ces certificats tout au long de leur cycle de vie , de l’inscription au renouvellement et à la révocation. Votre système de gestion des périphériques mobiles peut déployer automatiquement ces certificats sur les appareils&#39; magasins de certificats une fois que vous avez inscrit l’appareil (tant que le système de gestion des périphériques mobiles prend en charge le protocole SCEP (Simple Certificate Enrollment Protocol) ou le #12 de chiffrement à clé publique (PKCS#12)). MdM peut également interroger et supprimer des certificats clients inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel.

En savoir plus sur la préparation [des certificats et des profils réseau pour HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

La plupart des réseaux intranet d’entreprise utilisent un proxy pour gérer le trafic interne. Avec HoloLens 2, vous pouvez configurer un serveur proxy pour ethernet et Wi-Fi connexions. Ces paramètres ne s’appliquent pas aux connexions VPN.

Pour plus d’informations sur les paramètres de proxy pour Windows 10, voir [CSP NetworkProxy.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### VPN

Les organisations utilisent souvent un VPN pour contrôler l’accès aux applications et aux ressources sur leur&#39;intranet. HoloLens 2 prend en charge les connexions VPN SSL, qui nécessitent un plug-in téléchargeable à partir du Microsoft Store et sont spécifiques au fournisseur VPN de votre choix.

Pour plus d’informations sur les profils VPN, voir [Fournisseur CSP VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

#### Mode plein écran

Vous pouvez configurer un appareil HoloLens 2 pour qu’il fonctionne comme un appareil à usage fixe, également appelé kiosque, en configurant l’appareil pour qu’il s’exécute en mode plein écran. Le mode plein écran limite les applications (ou utilisateurs) disponibles sur l’appareil. Le mode plein écran est une fonctionnalité pratique que vous pouvez utiliser pour dédier un appareil HoloLens 2 aux applications d’entreprise ou pour utiliser l’appareil HoloLens 2 dans une démonstration d’application.

Pour plus d’informations sur la configuration d’un HoloLens 2 en mode plein écran, voir Configuration de [HoloLens en tant que kiosque](https://docs.microsoft.com/hololens/hololens-kiosk)

## Déployer

### Inscription d’appareils MDM

Pour les déploiements d’entreprise, il est recommandé d’inscrire des appareils dans la gestion des périphériques mobiles en tant qu’appareils d’entreprise uniquement avec la participation à Azure AD et l’inscription G MDM automatique (Azure AD+MDM). [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) Cela nécessite Azure AD Premium et prend en charge l’inscription automatique à plusieurs fournisseurs de gestion des données, y compris Intune.

En savoir plus sur la méthode d’inscription à déploiement automatique [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### Déploiement d’applications

La productivité de l’utilisateur sur les appareils mobiles dépend souvent des applications.

Windows10 permet de développer des applications qui fonctionnent en toute transparence sur plusieurs appareils à l’aide de la plateforme Windows universelle (UWP) pour les applications Windows.

Il existe plusieurs façons de déployer des applications sur des appareils HoloLens 2. Les applications peuvent être déployées directement via la gestion des applications mobiles, le Microsoft Store pour Entreprises ou une version de chargement secondaire via un package d’approvisionnement. Pour plus [](https://docs.microsoft.com/hololens/app-deploy-overview) d’informations, consultez la documentation de déploiement d’application.

> [!NOTE]
> HoloLens 2 prend uniquement en charge l’exécution d’applications ARM64 UWP.

## Maintenir

Dans les environnements informatiques d’entreprise, le besoin de sécurité et de contrôle des coûts doit être mis en balance avec le désir de fournir aux utilisateurs les technologies les plus récentes. Étant donné que les cyberattaques sont devenues une occurrence quotidienne, il est important de maintenir correctement l’état de vos appareils Windows 10. Le service informatique doit contrôler les paramètres de configuration, en veillant bien à leur conformité, et déterminer quels appareils peuvent accéder aux applications internes. HoloLens 2 offre les fonctionnalités de gestion des opérations mobiles nécessaires pour s’assurer que les appareils sont conformes à la stratégie d’entreprise.

### Options de maintenance du système d’exploitation

**Un processus de mise à jour simplifié**

Microsoft simplifié l’ingénierie et le cycle de lancement des produits Windows afin de pouvoir fournir les nouvelles fonctions, expériences et fonctionnalités exigées par le marché plus rapidement que jamais. Microsoft prévoit de mettre à disposition deux mises à jour de fonctionnalité par an (période de 12mois). **Les mises à jour de** fonctionnalités établissent une branche actuelle ou cb et ont une version associée.

Microsoft fournit et installe également des mises à jour pour la sécurité et la stabilité directement sur les appareils HoloLens 2. Ces **mises à jour qualité, publiées** sous le contrôle de Microsoft via Windows Update, sont disponibles tous les mois. HoloLens 2 utilise les mises à jour de fonctionnalités et les mises à jour qualité dans le cadre du même processus de mise à jour standard.

Les clients d’entreprise peuvent gérer l’expérience de mise à jour et le processus sur HoloLens 2s à l’aide d’un système mdm. Dans la plupart des cas, les stratégies de gestion du processus de mise à jour s’appliquent aux mises à jour de fonctionnalités et qualité. Plus d’informations sur la configuration de la gestion des données de gestion des données pour [les mises à jour HoloLens.](https://docs.microsoft.com/hololens/hololens-updates)

### Gestion des applications

Les administrateurs informatiques peuvent contrôler les applications qui sont autorisées à être installées sur HoloLens 2 et la façon dont elles doivent être tenues à jour.

HoloLens 2 prend en [charge Windows Defender Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)qui permet aux administrateurs de créer, d’autoriser ou d’autoriser des listes d’applications à partir du Microsoft Store. Cette fonctionnalité s’étend également aux applications intégrées. La possibilité d’autoriser ou de refuser des applications permet de s’assurer que les utilisateurs utilisent leurs appareils à leurs fins. Cependant, il n’est pas toujours simple de répondre à la fois aux besoins ou aux demandes des employés et aux préoccupations en matière de sécurité. Par ailleurs, la création de listes d’applications autorisées ou interdites nécessite de suivre de près l’évolution du catalogue du MicrosoftStore.

Pour plus d’informations, voir [CSP Contrôle d’application.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### Mise hors service

Le retrait de l’appareil est la dernière phase du cycle de vie de l’appareil. Il est&#39;important que les appareils remplacés par des modèles plus anciens soient retirés en toute sécurité, car vous ne souhaitez&#39;pas que les données d’entreprise restent sur les appareils ignorés, ce qui peut compromettre la confidentialité de vos données. Le service informatique a également besoin d’un moyen de prendre en charge de manière appropriée les utilisateurs qui ont besoin d’effacer des appareils perdus ou volés.

HoloLens 2 prend en charge 3 méthodes de wiping de l’appareil

**Effacement d’usine MDM :** Réinitialise HoloLens 2 à l’image d’usine via la commande MDM initiée par l’administrateur. Efface toutes les données stockées sur l’appareil.

**Réinitialisation de l’appareil à partir des paramètres :** Les utilisateurs finaux peuvent réinitialiser manuellement l’HoloLens 2 dans l’application Paramètres sur l’appareil. Efface toutes les données stockées sur l’appareil.

**Advanced Recovery Companion (ARC) :** À partir d’un PC exécutant l’outil ARC, un utilisateur ou un administrateur peut flasher un HoloLens 2 connecté au PC via un câble USB. Efface toutes les données stockées sur l’appareil.

> [!div class="nextstepaction"]
> [Scénarios courants de déploiement](common-scenarios.md)
