---
title: Configurer HoloLens dans un environnement commercial
description: En savoir plus sur le déploiement et la gestion de HoloLens dans les environnements d’entreprise.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/30/2020
ms.openlocfilehash: b7523b8ab38cfc37795ea6c99f9b22953baffe47
ms.sourcegitcommit: 30e910348f5d5b68e914219c8eadb34d93770eab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "11099803"
---
# HoloLens 2-déploiement et gestion d’entreprise

Cette vue d’ensemble est destinée à aider les informaticiens à comprendre les considérations en matière de déploiement et de gestion des appareils Microsoft HoloLens 2 au sein de l’entreprise.

HoloLens 2 s’exécute sur Windows 10 holographique qui fournit aux organisations des technologies de gestion des applications et périphériques mobiles robustes, flexibles et intégrés. Holographique Windows 10 prend en charge la gestion du cycle de vie des appareils de bout en bout pour permettre aux entreprises de contrôler leurs appareils, données et applications. Le HoloLens 2 peut facilement être intégré aux pratiques de cycle de vie standard, à l’inscription de l’appareil, à la configuration et à la gestion des applications, au maintien et à la mise hors service au moyen d’une solution de gestion des appareils mobiles complète.

## Préparation

Lorsque vous préparez le déploiement de HoloLens 2 vers votre environnement d’entreprise, il existe plusieurs éléments à prendre en compte lorsque vous commencez à planifier des déploiements d’échelle de HoloLens 2.

### Notions fondamentales sur l’infrastructure

Pour HoloLens 2 dans le scénario de déploiement d’entreprise entreprise, certains services d’infrastructure essentiels sont requis pour prendre en charge l’ensemble complet de fonctionnalités. HoloLens 2 a été créé avec une [gestion de périphériques mobiles modernes](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) à l’esprit pour le déploiement et la gestion. Avec Azure AD Join + MDM, c’est le principal moyen d’y parvenir dans une mobilité sans précédent. Les rubriques suivantes fournissent un bref aperçu de chaque composant d’infrastructure qui doit être pris en compte dans la planification du déploiement pour HoloLens 2.

### Azure Active Directory
Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. Vous pouvez l’intégrer à des annuaires sur site existants pour créer une solution de gestion des identités hybride. Les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui comporte trois éditions: gratuit, Premium P1 et Premium P2 (voir [éditions d’Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Toutes les éditions prennent en charge l’inscription de l’appareil Azure AD, mais Premium P1 est requis pour activer la fonction d’inscription automatique de GPM. HoloLens 2 nécessite Azure Active Directory join pour activer la plupart des fonctionnalités et fonctionnalités au niveau de l’entreprise.

> [!NOTE]
> La jointure Active Directory locale n’est pas prise en charge sur HoloLens 2.

### Gestion des appareils mobiles
HoloLens 2 a été conçu spécifiquement pour être géré par des systèmes de gestion des périphériques mobiles (GPM) dans un environnement d’entreprise. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), qui fait partie de l’entreprise mobilité + sécurité, est un système de gestion de la gestion des appareils dans l’entreprise. Comme Office 365, Intune utilise Azure AD pour la gestion des identités, de sorte que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. De nombreux systèmes GPM prennent en charge Windows10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. Les systèmes GPM peuvent également gérer également les déploiements d’application et les mises à jour pour le HoloLens 2. D’autres fournisseurs GPM qui prennent en charge HoloLens 2 incluent actuellement: MobileIron, etc. Tous les fournisseurs de systèmes de gestion des appareils mobiles ont le même accès aux fournisseurs de services de configuration de la gestion des appareils Windows 10, ce qui leur permet de sélectionner le système le mieux adapté à leurs besoins en matière de gestion, qu’il s’agisse de Microsoft Intune ou d’un produit de type GPM tiers.

> [!NOTE]
> Les systèmes de gestion traditionnels de PC sur site comme System Center Configuration Manager ne sont pas pris en charge sur HoloLens 2.

### WindowsUpdate for Business
Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour. Pour plus d’informations sur la gestion des mises à jour de HoloLens 2, consultez la [page suivante](https://docs.microsoft.com/hololens/hololens-updates).

### Certificats
HoloLens 2 prend en charge le déploiement de certificats via la gestion des périphériques mobiles si votre environnement nécessite des certificats pour l’authentification du réseau Wi-Fi d’entreprise ou l’accès à d’autres ressources. Certaines configurations d’infrastructure de la gestion des périphériques mobiles doivent être requises pour activer le déploiement de certificats vers HoloLens 2. Découvrez comment [préparer des certificats et des profils réseau pour HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Les informations sur Intune sont accessibles [ici](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## Configurer

Les administrateurs de la gestion des périphériques mobiles peuvent définir et implémenter des paramètres de stratégie sur n’importe quel appareil d’entreprise inscrit dans un système GPM. Quels sont les paramètres de configuration que vous utilisez varient en fonction du scénario de déploiement. Dans Windows 10, les fournisseurs de services de configuration (CSP) sont une interface pour lire, définir, modifier ou supprimer des paramètres de configuration sur l’appareil. Ces paramètres sont mappés à des clés de registre ou des fichiers. Pour plus d’informations sur les fournisseurs de services de gestion des appareils Windows 10 pour HoloLens 2, voir la liste complète des [fournisseurs de services de cryptographie pris en charge sur les appareils hololens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

HoloLens 2 prend également en charge la définition d’un ensemble limité de configurations CSP par le biais de packages de mise en service personnalisés. Les packages de mise en service sont généralement utilisés pour les appareils non gérés par le système de gestion de la gestion des périphériques mobiles et nécessitent d’être appliqués manuellement à chaque appareil. Pour plus d’informations [, consultez Création](https://docs.microsoft.com/hololens/hololens-provisioning)de packages d’approvisionnement personnalisés.

> [!NOTE]
> HoloLens 2 prend en charge [Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), qui fournit un processus simple et simple de gestion de vos configurations d’appareils Windows 10.

### Gestion des identités

Les employés ne peuvent utiliser qu’un seul compte pour initialiser un appareil de sorte qu’il&#39;est impératif que votre organisation contrôle quel compte est activé pour la première fois. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion. HoloLens 2 prend en charge 3 types de comptes: compte d’utilisateur local, compte Microsoft personnel et comptes Azure Active Directory. Il est vivement recommandé d’utiliser Azure Active Directory pour votre solution de gestion des identités d’entreprise, car elle permettra d’utiliser toutes les fonctionnalités sur vos appareils HoloLens 2. Vous trouverez des informations supplémentaires sur les identités sur HoloLens 2 [ici](https://docs.microsoft.com/hololens/hololens-identity).

### Réseau et connectivité

Comme HoloLens 2 est un premier appareil Cloud, l’accès réseau à des ressources en ligne est requis pour rendre les fonctionnalités complètes disponibles. Si vous déployez des appareils HoloLens 2 avec une connectivité à votre réseau intranet d’entreprise, vous devrez peut-être mettre à jour vos règles de proxy et de pare-feu pour autoriser l’accès aux services Cloud HoloLens 2. La liste des points de terminaison courants nécessaires pour le système d’exploitation HoloLens 2 est disponible [ici](https://docs.microsoft.com/hololens/hololens-offline). L’accès à des points de terminaison supplémentaires est susceptible d’être requis pour l’exécution correcte des applications ou autres services Cloud sur HoloLens 2.

Certains services HoloLens 2 courants nécessitant un accès au point de terminaison supplémentaire sont les suivants:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guides de D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (infrastructure des équipes O365)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Déploiement de certificats

Si des certificats sont requis pour accéder à des réseaux Wi-Fi d’entreprise ou à d’autres services au sein de votre organisation, HoloLens 2 prend en charge le déploiement des certificats d’utilisateur et d’appareil via la gestion des périphériques mobiles. Remarque: votre solution de gestion des périphériques mobiles (GPM) risque de nécessiter une configuration d’infrastructure supplémentaire pour déployer des certificats sur des appareils Windows 10.

### Examen de la sécurité

La plupart des services informatiques d’entreprise doivent procéder à une analyse et à un examen des nouveaux appareils déployés sur un réseau d’entreprise. Si votre organisation nécessite un examen de sécurité de HoloLens 2, vous pouvez [en savoir plus sur cette page pour obtenir des autorisations de sécurité](https://docs.microsoft.com/hololens/security-overview).

### Paramètres d’appareil HoloLens 2 communs

Lors du déploiement de périphériques HoloLens 2 vers un environnement d’entreprise d’entreprise, il existe un certain nombre de configurations d’appareils courantes qui peuvent être envisagées lors de la planification de votre déploiement de HoloLens 2. Cette liste met en évidence les configurations et les paramètres qui ne sont pas connus et qui ne comprend pas la liste complète des options disponibles:

| Paramètre d’appareil | Brève description.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrictions matérielles](hololens-requirements.md#hardware-restrictions)               | Restrictions matérielles réduction de la connectivité et assistance en matière de protection des données.                        |
| [Profils Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurer des profils Wi-Fi sans aucune intervention ou action de l’utilisateur.                              |
| [Certificats](hololens-requirements.md#certificates-1)               | Fournissez l’authentification par compte et/ou Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gérer le trafic interne.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Contrôle de l’accès aux applications et aux ressources sur l’intranet de leur entreprise.                               |
| [Mode plein écran](hololens-requirements.md#kiosk-mode) | Limite les applications présentées aux utilisateurs par le biais de l’interface utilisateur. |

#### Restrictions matérielles

HoloLens 2 utilise une technologie de pointe qui inclut des fonctionnalités matérielles courantes, telles que des appareils photo, des microphones, des haut-parleurs, des interfaces USB, des interfaces Bluetooth et un réseau Wi-Fi. Vous pouvez utiliser les restrictions matérielles pour contrôler la disponibilité de ces fonctionnalités.

La liste suivante répertorie les paramètres de gestion des périphériques mobiles les plus fréquemment utilisés qui sont pris en charge par HoloLens 2 pour configurer les restrictions matérielles. Certaines de ces restrictions matérielles assurent la connectivité et permettent de protéger les données.

- [**Autoriser le Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si les utilisateurs peuvent activer et utiliser la radio Wi-Fi sur leurs appareils
- [**Autoriser la connexion USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la connexion USB est activée (n’est pas&#39;t d’affecter la charge USB)
- [**Autoriser Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si les utilisateurs peuvent activer et utiliser la radio Bluetooth sur leurs appareils

En savoir plus sur les autres [restrictions d’appareil courantes.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Profils Wi-Fi

La plupart des réseaux Wi-Fi nécessitent des certificats et d’autres informations complexes pour visant à limiter et à sécuriser l’accès des utilisateurs. Ce type d’informations Wi-Fi est difficile à configurer pour les utilisateurs typiques, mais les systèmes de gestion des appareils mobiles peuvent configurer entièrement ces profils Wi-Fi sans l’intervention de l’utilisateur. Vous pouvez créer plusieurs profils Wi-Fi dans votre système GPM.

Pour plus d’informations sur les paramètres Wi-Fi pour Windows 10, voir [paramètres WiFi de profil d’entreprise](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### Certificats

Les certificats permettent d’améliorer la sécurité en fournissant l’authentification de compte, l’authentification Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. Bien que les administrateurs puissent gérer les certificats sur les appareils manuellement par le biais de la mise en service des packages, il&#39;est préférable d’utiliser votre système de gestion des applications mobiles pour gérer ces certificats tout au long de leur cycle de vie, de l’inscription au renouvellement et de la révocation. Votre système de gestion des périphériques mobiles peut déployer automatiquement ces certificats sur les appareils&#39; les magasins de certificats après l’inscription de l’appareil (à condition que le système GPM prenne en charge les normes de cryptographie par le biais du protocole SCEP ou de clé publique #12 (PKCS # 12). Le GPM peut également rechercher et supprimer des certificats client inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel.

En savoir plus sur la [préparation des certificats et des profils réseau pour HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

La plupart des réseaux intranet d’entreprise tirent parti d’un proxy pour gérer le trafic interne. Avec HoloLens 2, vous pouvez configurer un serveur proxy pour les connexions Ethernet et Wi-Fi. Ces paramètres ne s’appliquent pas aux connexions VPN.

Pour plus d’informations sur les paramètres de proxy pour Windows 10, consultez [fournisseur de services de NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

Les organisations utilisent souvent un réseau privé virtuel (VPN) pour contrôler l’accès aux applications et aux ressources sur leur réseau d’entreprise&#39;s. HoloLens 2 prend en charge les connexions VPN SSL qui nécessitent un plug-in téléchargeable auprès du Microsoft Store et qui sont propres à l’éditeur de votre choix.

Pour plus d’informations sur les profils VPN, voir [Fournisseur CSP VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

#### Mode plein écran

Vous pouvez configurer un appareil HoloLens 2 pour qu’il fonctionne en tant qu’appareil à usage fixe, également appelé borne, en configurant l’appareil pour qu’il s’exécute en mode plein écran. Le mode plein écran limite les applications (ou utilisateurs) qui sont disponibles sur l’appareil. Le mode Kiosk est une fonctionnalité pratique qui vous permet de dédier un périphérique HoloLens 2 aux applications métier ou d’utiliser l’appareil HoloLens 2 dans une démonstration d’application.

Pour plus d’informations sur la configuration d’un HoloLens 2 en mode plein écran, voir [configurer hololens en tant que borne](https://docs.microsoft.com/hololens/hololens-kiosk)

## Déployer

### Inscription de périphériques GPM

Pour les déploiements d’entreprise, il est recommandé d' [inscrire des appareils](https://docs.microsoft.com/hololens/hololens-enroll-mdm) dans la gestion des périphériques mobiles en tant qu’appareils d’entreprise uniquement avec la fonction d’inscription d’Azure ad et l’inscription à la gestion des périphériques mobiles automatiques. Pour cela, vous devez disposer d’Azure AD Premium et prendre en charge l’inscription automatique à plusieurs fournisseurs GPM, y compris Intune.

En savoir plus sur le [pilotage](https://docs.microsoft.com/hololens/hololens2-autopilot)automatique de la méthode d’inscription.

### Déploiement d’applications

La productivité de l’utilisateur sur les appareils mobiles dépend souvent des applications.

Windows10 permet de développer des applications qui fonctionnent en toute transparence sur plusieurs appareils à l’aide de la plateforme Windows universelle (UWP) pour les applications Windows.

Il existe plusieurs façons de déployer des applications sur des appareils HoloLens 2. Les applications peuvent être déployées directement via la gestion des périphériques mobiles, le Microsoft Store pour les entreprises ou chargée par le biais d’un package de mise à service. Vous trouverez des informations supplémentaires sur le déploiement de l' [application ici](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 prend en charge l’exécution d’applications ARM64 UWP uniquement.

## Mise à jour

Dans les environnements informatiques d’entreprise, le besoin de sécurité et de contrôle des coûts doit être mis en balance avec le désir de fournir aux utilisateurs les technologies les plus récentes. Dans la mesure où cyberattacks est devenu une occurrence quotidienne, il est important de conserver correctement l’état de vos appareils Windows 10. Le service informatique doit contrôler les paramètres de configuration, en veillant bien à leur conformité, et déterminer quels appareils peuvent accéder aux applications internes. HoloLens 2 fournit les fonctionnalités de gestion des opérations mobiles nécessaires pour s’assurer que les appareils sont conformes à la stratégie d’entreprise.

### Options de maintenance du système d’exploitation

**Un processus de mise à jour simplifié**

Microsoft simplifié l’ingénierie et le cycle de lancement des produits Windows afin de pouvoir fournir les nouvelles fonctions, expériences et fonctionnalités exigées par le marché plus rapidement que jamais. Microsoft prévoit de mettre à disposition deux mises à jour de fonctionnalité par an (période de 12mois). Les **mises à jour de fonctionnalités** établissent une branche actuelle ou un CB et possèdent une version associée.

Microsoft fournira et installera également des mises à jour de sécurité et de stabilité directement sur les appareils HoloLens 2. Les **mises à jour** de la qualité, publiée sous le contrôle Microsoft par le biais de Windows Update, sont disponibles par mois. HoloLens 2 utilise les mises à jour de fonctionnalités et les mises à jour de qualité dans le cadre du même processus de mise à jour standard.

Les clients d’entreprise peuvent gérer l’utilisation et le processus de mise à jour sur HoloLens 2S à l’aide d’un système de gestion des périphériques mobiles. Dans la plupart des cas, les stratégies de gestion du processus de mise à jour s’appliquent aux mises à jour de fonctionnalités et qualité. En savoir plus sur la configuration de la gestion des périphériques mobiles [pour les mises à jour HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### Gestion des applications 

Les administrateurs informatiques peuvent contrôler les applications qui peuvent être installées sur le HoloLens 2 et la manière dont elles doivent être mises à jour.

HoloLens 2 prend en charge le [contrôle de Windows Defender application Control (WDac)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), qui permet aux administrateurs de créer, autoriser ou interdire des listes d’applications à partir du Microsoft Store. Cette fonctionnalité s’étend également aux applications intégrées. La possibilité d’autoriser ou de refuser des applications permet de s’assurer que les personnes utilisent leurs appareils dans leurs buts prévus. Cependant, il n’est pas toujours simple de répondre à la fois aux besoins ou aux demandes des employés et aux préoccupations en matière de sécurité. Par ailleurs, la création de listes d’applications autorisées ou interdites nécessite de suivre de près l’évolution du catalogue du MicrosoftStore.

Pour plus d’informations, consultez [fournisseur de services de gestion des applications](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### Mise hors service

La mise hors service de l’appareil est la dernière phase du cycle de vie de l’appareil. Il&#39;est important que les appareils qui ont été remplacés par des modèles plus récents soient en sécurité dans la mesure où vous ne&#39;pas que les données d’une entreprise continuent d’avoir besoin de la confidentialité de vos données. Le service informatique a également besoin d’un moyen de prendre en charge de manière appropriée les utilisateurs qui ont besoin d’effacer des appareils perdus ou volés.

HoloLens 2 prend en charge 3 méthodes d’effacement du périphérique

**Effacement de fabrique GPM:** Réinitialisation du HoloLens 2 à l’image de fabrique via la commande GPM initialisée par l’administrateur. Efface toutes les données stockées sur l’appareil.

**Réinitialisation de l’appareil à partir de paramètres:** Les utilisateurs finaux peuvent réinitialiser manuellement le HoloLens 2 dans l’application paramètres de l’appareil. Efface toutes les données stockées sur l’appareil.

**Compagnon de récupération avancée (ARC):** À partir d’un PC exécutant l’outil ARC, un utilisateur ou un administrateur peut faire clignoter un HoloLens 2 connecté au PC via un câble USB. Efface toutes les données stockées sur l’appareil.
