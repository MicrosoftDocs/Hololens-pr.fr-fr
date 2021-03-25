---
title: Guide de déploiement – HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Préparer
description: Découvrez comment préparer l’inscription d’appareils HoloLens 2 sur un réseau connecté à l’entreprise à l’aide des guides Dynamics 365.
keywords: HoloLens, gestion, connexion d’entreprise, guides Dynamics 365, AAD, Azure AD, GESTION DES PÉRIPHÉRIQUES MOBILES, Gestion des appareils mobiles
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448541"
---
# <a name="prepare---corporate-connected-guide"></a>Préparer - Guide connecté à l’entreprise
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Pour les scénarios de déploiement personnel et d’entreprise, un système de gestion des périphériques mobiles (MDM) est l’infrastructure essentielle requise pour déployer et gérer des appareils Windows 10, en particulier HoloLens 2. Un [abonnement Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) est recommandé en tant que fournisseur d’identité et **requis** pour prendre en charge certaines fonctionnalités.

> [!NOTE]
> Bien que HoloLens 2 soit déployé et géré comme un appareil mobile, il est généralement utilisé comme appareil partagé entre de nombreux utilisateurs.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. Les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui possède trois éditions : Gratuite, Premium P1 et Premium P2 (voir [éditions Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Toutes les éditions prendre en charge l’inscription d’appareils Azure AD, mais Premium P1 est nécessaire pour activer l’inscription automatique mdm que nous utiliserons dans ce guide ultérieurement.
> [!Important]
> Il est essentiel d’avoir un Azure AD, car les appareils HoloLens ne peuvent pas prendre en charge la jointeurs AD en local. Si vous n’avez pas encore installé Azure AD, suivez les instructions pour commencer et créer un client [dans Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Gestion des identités
Dans ce guide, [l’identité](https://docs.microsoft.com/hololens/hololens-identity) utilisée sera les comptes Azure AD. Les comptes Azure AD offrent plusieurs avantages, tels que :
- Les employés utilisent leur compte Azure AD pour inscrire l’appareil dans Azure AD et peuvent l’inscrire automatiquement à la solution GD de l’organisation (Azure AD+MDM – nécessite un abonnement [Azure AD Premium).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Les comptes Azure AD offrent des [options d’authentification supplémentaires](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello Entreprise.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Outre la connexion à l’iris, les utilisateurs peuvent se connecter à partir d’un autre appareil ou utiliser des clés de sécurité FIDO.

> [!WARNING] 
> Les employés ne peuvent utiliser qu’un seul compte pour initialiser un appareil. Il est donc impératif que votre organisation contrôle **d’abord**quel compte est activé. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion.

## <a name="mobile-device-management"></a>Gestion des appareils mobiles
Microsoft Intune, qui fait partie d’Enterprise Mobility + Security, est un système GDM basé sur le cloud qui gère les appareils connectés à votre client. Comme Office 365, Intune utilise Azure AD pour la gestion des identités, afin que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. Intune prend également en charge les appareils qui exécutent d’autres systèmes d’exploitation, tels qu’iOS et Android, pour fournir une solution MDM complète. Dans le cadre de ce guide, nous allons nous concentrer sur l’utilisation d’Intune pour permettre un déploiement sur votre réseau interne avec HoloLens 2.
> [!Important] 
> Il est essentiel d’avoir la gestion des périphériques mobiles. Si ce n’est pas déjà fait, suivez ce guide et commencer avec Intune.

> [!Important]
> Pour utiliser les guides, un compte Azure AD est requis.

> [!Note] 
> De nombreux systèmes GPM prennent en charge Windows10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. Les fournisseurs de gestion des périphériques mobiles qui supportent Windows 10 Holographique sont notamment : AirWatch, MobileIron, etc. La plupart des fournisseurs GPM majeurs prennent déjà en charge l’intégration à Azure AD. Vous trouverez la liste la plus à jour des fournisseurs de gestion des services de gestion des biens et des services de gestion des logiciels (MDM) qui prendre en charge Azure AD [dans Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Accès réseau 
Dynamics 365 Guides est une application basée sur le cloud. Si votre administrateur réseau dispose d’une liste d’approbation, il peut être nécessaire d’ajouter des adresses IP et/ou des points de terminaison nécessaires pour se connecter aux serveurs Dynamics 365. [En savoir plus sur le déblocage d’adresses IP et d’URL.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificats
Les certificats contribuent à améliorer la sécurité en fournissant l’authentification de compte, Wi-Fi l’authentification, le chiffrement VPN et le chiffrement SSL du contenu web. Bien que les administrateurs peuvent gérer manuellement les certificats sur les appareils par le biais de packages d’approvisionnement, il est préférable d’utiliser votre système de gestion des périphériques mobiles pour gérer ces certificats tout au long de leur cycle de vie , de l’inscription au renouvellement et à la révocation. 

Votre système de gestion des périphériques mobiles peut déployer automatiquement ces certificats dans les magasins de certificats des appareils après les avoir inscrits (tant que votre système de gestion des périphériques mobiles prend en charge le protocole **SCEP (Simple Certificate Enrollment Protocol)** ou le #12 des normes de chiffrement à clé publique **(PKCS#12)**). [Découvrez les types de certificats et les profils que vous utilisez avec Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-configure) MdM peut également interroger et supprimer des certificats clients inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel.
 
Si vos systèmes de gestion des périphériques mobiles sont déjà configurés pour les certificats, référencez préparer les certificats et les profils réseau pour [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) afin de commencer à déployer des certificats et des profils pour vos appareils HoloLens 2.

## <a name="scep"></a>SCEP

Les services suivants sont requis pour le déploiement SCEP, à l’exception du serveur proxy d’application web.
- [Autorité de certification](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rôle serveur NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Connecteur Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Vous devez également publier votre URL NDES externe à votre réseau d’entreprise à l’aide du proxy d’application Azure AD ou du [proxy d’accès web.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Vous pouvez également utiliser un autre proxy inverse de votre choix.

![Flux de données SCEP](./images/hololens2-scep-info-flow.png)

Si votre réseau ne prend pas déjà en charge SCEP, ou si vous ne savez pas si votre réseau est correctement configuré pour SCEP avec Intune, référencez Configurer l’infrastructure pour prendre en charge SCEP avec [Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

Si votre infrastructure prend déjà en [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) charge [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) scEP, vous devez créer un profil pour chaque certificat SCEP que HoloLens 2 utilisera. Si vous avez des problèmes avec SCEP, utilisez la résolution des problèmes d’utilisation des profils de certificat SCEP pour mettre en service des [certificats avec Microsoft Intune.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Intune prend également en charge l’utilisation de certificats PKCS (private and public key pair). Référence [Utiliser des certificats de clé privée et publique dans Microsoft Intune pour](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) plus d’informations.

## <a name="proxy"></a>Proxy
La plupart des réseaux intranet d’entreprise utilisent un proxy pour gérer le trafic externe. Avec HoloLens 2, vous pouvez configurer un serveur proxy pour les connexions ethernet, Wi-Fi et VPN.

Il existe différents types de proxy et méthodes de configuration du proxy. Dans le cadre de ce guide, nous choisissons de choisir un **proxy Wi-Fi,** de le définir via l’URL PAC et de le déployer via la gestion des données de gestion des données . Cela présente les avantages d’être déployé automatiquement via la gestion des périphériques mobiles, de pouvoir mettre à jour le fichier PAC au lieu d’utiliser une configuration server:port, et enfin d’utiliser un proxy Wi-Fi pour configurer le proxy de manière à ce qu’il s’applique uniquement à une seule connexion Wi-Fi, ce qui permet aux appareils d’être toujours utilisés s’ils sont connectés à un autre emplacement. 


Pour plus d’informations sur les paramètres de proxy pour Windows 10, voir Créer un profil Wi-Fi pour les appareils dans [Microsoft Intune - Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Applications métier 
Bien que plusieurs applications soient installées via le Microsoft Store, il est probable que vous possédiez votre propre application personnalisée que vous avez créée spécifiquement pour une utilisation en réalité mixte. Ces applications personnalisées distribuées dans toute votre organisation pour votre entreprise sont appelées applications métier.
  
Il existe plusieurs façons de déployer des applications sur des appareils HoloLens 2. Les applications peuvent être déployées directement par le biais de la gestion des applications mobiles, du Microsoft Store pour Entreprises (MSfB) ou d’un package d’approvisionnement. Dans le cadre de ce guide, nous allons déployer des applications via la gestion des applications mobiles, à l’aide de l’installation requise de l’application. Cela permet à vos applications LOB d’être automatiquement téléchargées sur vos appareils HoloLens une fois qu’elles ont terminé leur inscription.

Pour ceux d’entre vous qui ne possèdent pas votre propre LOB, nous fournirons un exemple d’application pour tester ce flux de déploiement. Cette application, qui sera l’application [MRTK Examples,](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) a déjà été pré-préodée et empaqueté pour tester la preuve de concept.
 
Pour plus d’informations sur le déploiement d’applications, voir Gestion des [applications : Vue d’ensemble.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 prend uniquement en charge l’exécution d’applications ARM64 UWP.

## <a name="guides-playbook"></a>Guides Playbook
Les guides utilisent un environnement Microsoft Dataverse comme magasin de données pour vos applications guides. Il est important de comprendre la façon dont votre environnement Dataverse interagit avec vos applications guides et votre client. Nous n’allons pas vous parler de la gestion de votre dataverse dans ce guide, mais consultez les concepts de base pour le déploiement des [guides Dynamics 365 - Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté à l’entreprise : configurer](hololens2-corp-connected-configure.md)