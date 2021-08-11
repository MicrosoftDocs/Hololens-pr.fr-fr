---
title: Guide de déploiement – entreprise connectée HoloLens 2 avec Dynamics 365 Guides-prepare
description: découvrez comment préparer l’inscription d’appareils HoloLens 2 sur un réseau connecté à l’entreprise avec Dynamics 365 Guides.
keywords: HoloLens, gestion, connecté à l’entreprise, Dynamics 365 Guides, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: 76513c2f2458119785b64d8cccac4e42c2957b5af966dfdb0c165ebeda12e069
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660082"
---
# <a name="prepare---corporate-connected-guide"></a>Préparer-Guide connecté à l’entreprise
## <a name="infrastructure-essentials"></a>Notions fondamentales de l’infrastructure
pour les scénarios de déploiement personnel et d’entreprise, un système de gestion des appareils mobiles (MDM) est l’infrastructure essentielle requise pour déployer et gérer Windows 10 appareils, en particulier les HoloLens 2. un [abonnement Azure AD Premium](/azure/active-directory/fundamentals/active-directory-get-started-premium) est recommandé en tant que fournisseur d’identité et **requis** pour prendre en charge certaines fonctionnalités.

> [!NOTE]
> bien que le HoloLens 2 soit déployé et géré comme un appareil mobile, il est généralement utilisé en tant qu’appareil partagé entre plusieurs utilisateurs.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui possède trois éditions : gratuite, Premium P1 et Premium P2 (voir les [éditions de Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). toutes les éditions prennent en charge l’inscription des appareils Azure AD, mais Premium P1 est nécessaire pour activer l’inscription automatique MDM que nous utiliserons dans ce guide plus tard.
> [!Important]
> il est essentiel de disposer d’un Azure AD, car les appareils HoloLens ne prennent pas en charge la jointure AD locale. Si vous ne disposez pas déjà d’un Azure AD, suivez les instructions pour commencer et [créer un nouveau locataire dans Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gestion des identités
Dans ce guide, l' [identité](/hololens/hololens-identity) utilisée sera Azure ad comptes. Les comptes Azure AD présentent plusieurs avantages, tels que :

- les employés utilisent leur compte Azure AD pour inscrire l’appareil dans Azure AD et peuvent l’inscrire automatiquement avec la solution mdm de l’organisation (Azure AD + mdm – nécessite un [abonnement Azure AD Premium](/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- les comptes Azure AD disposent d' [options d’authentification](/hololens/hololens-identity) supplémentaires via [Windows Hello pour l’entreprise](/windows/security/identity-protection/hello-for-business/hello-identity-verification). En plus de la connexion IRIS, les utilisateurs peuvent se connecter à partir d’un autre appareil ou utiliser des clés de sécurité Rex.

> [!WARNING] 
> Les employés peuvent utiliser un seul compte pour initialiser un appareil. **il est donc impératif que votre organisation contrôle le compte qui est activé en premier**. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion.

## <a name="mobile-device-management"></a>Gestion des appareils mobiles
Microsoft Intune, qui fait partie de Enterprise Mobility + Security, est un système MDM basé sur le cloud qui gère les appareils connectés à votre locataire. comme Office 365, Intune utilise Azure AD pour la gestion des identités, de sorte que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. Intune prend également en charge les appareils qui exécutent d’autres systèmes d’exploitation, tels que iOS et Android, pour fournir une solution MDM complète. Dans le cadre de ce guide, nous allons nous concentrer sur l’utilisation d’Intune pour l’activation d’un déploiement sur votre réseau interne avec HoloLens 2.
> [!Important] 
> Il est essentiel de disposer de la gestion des appareils mobiles. Si vous ne l’avez pas déjà fait, suivez ce guide et commencez avec Intune.

> [!Important]
> Pour pouvoir utiliser des guides, vous devez disposer d’un compte Azure AD.

> [!Note] 
> De nombreux systèmes GPM prennent en charge Windows 10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. les fournisseurs MDM qui prennent en charge Windows 10 Holographique incluent : MobileIron et autres. La plupart des fournisseurs GPM majeurs prennent déjà en charge l’intégration à Azure AD. Vous trouverez la liste la plus récente des fournisseurs MDM qui prennent en charge Azure AD dans la place de [marché Azure](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Accès réseau 
Dynamics 365 Guides est une application basée sur le cloud. Si votre administrateur réseau dispose d’une liste d’approbations, il peut être nécessaire d’ajouter des adresses IP et/ou des points de terminaison nécessaires pour se connecter aux serveurs Dynamics 365. [En savoir plus sur le déblocage des adresses IP et des URL](/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Certificats
Les certificats aident à améliorer la sécurité en fournissant l’authentification de compte, l’authentification Wi-Fi, le chiffrement VPN et le chiffrement SSL du contenu Web. Bien que les administrateurs puissent gérer les certificats sur les appareils manuellement par le biais de packages de provisionnement, il est recommandé d’utiliser votre système MDM pour gérer ces certificats tout au long de leur cycle de vie, de l’inscription au renouvellement et de la révocation. 

Votre système MDM peut déployer automatiquement ces certificats sur les magasins de certificats des appareils une fois que vous les avez inscrits (à condition que votre système MDM prenne en charge le **protocole d’Inscription de certificats simple (SCEP)** ou les **normes de chiffrement à clé publique #12 (PKCS # 12)**). [En savoir plus sur les types de certificats et les profils que vous utilisez avec Microsoft Intune](/mem/intune/protect/certificates-configure). MDM peut également interroger et supprimer des certificats clients inscrits ou déclencher une nouvelle demande d’inscription avant l’expiration du certificat actuel.

si vos systèmes MDM sont déjà configurés pour les certificats, référence [préparez les certificats et les profils réseau pour HoloLens 2](/hololens/hololens-certificates-network) pour commencer à déployer des certificats et des profils pour vos appareils HoloLens 2.

## <a name="scep"></a>SCEP

Les services suivants sont requis pour le déploiement de SCEP, à l’exception du serveur proxy d’application Web.

- [Autorité de certification](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rôle serveur NDES](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Connecteur Microsoft Intune](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Vous devez également publier votre URL NDES externe à votre réseau d’entreprise à l’aide de [Azure ad proxy d’application ou d’accès Web proxy](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application). Vous pouvez également utiliser un autre proxy inverse de votre choix.

![Workflow de données SCEP](./images/hololens2-scep-info-flow.png)

Si votre réseau ne prend pas encore en charge SCEP, ou si vous ne savez pas si votre réseau est correctement configuré pour SCEP avec Intune, référencez  [configurer l’infrastructure pour prendre en charge SCEP avec Intune](/mem/intune/protect/certificates-scep-configure).

si votre infrastructure prend déjà en charge SCEP, vous devrez [créer](/mem/intune/protect/certificates-profile-scep) un [profil](/mem/configmgr/protect/deploy-use/create-certificate-profiles) pour chaque certificat SCEP que le HoloLens 2 utilisera. Si vous rencontrez des problèmes avec SCEP, utilisez [résoudre les problèmes liés à l’utilisation des profils de certificat SCEP pour approvisionner des certificats avec Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
Intune prend également en charge l’utilisation de certificats de paire de clés publique et privée (PKCS). pour plus d’informations, consultez la référence [utiliser des certificats de clé privée et publique dans Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) .

## <a name="proxy"></a>Proxy
La plupart des réseaux intranet d’entreprise tirent parti d’un proxy pour gérer le trafic externe. avec HoloLens 2 vous pouvez configurer un serveur proxy pour les connexions ethernet, Wi-Fi et VPN.

Il existe différents types de proxy et de méthodes de configuration du proxy. Dans le cadre de ce guide, nous choisissons de choisir **un proxy Wi-Fi, de définir via une URL PAC et de les déployer via MDM**. Il s’agit des avantages du déploiement automatique via MDM, de la possibilité de mettre à jour le fichier PAC au lieu d’utiliser une configuration serveur : port, et enfin d’utiliser Wi-Fi proxy pour configurer le proxy pour qu’il s’applique uniquement à une seule Wi-Fi connexion, ce qui permet aux appareils d’être utilisés toujours s’ils sont connectés à un autre emplacement.

pour plus d’informations sur les paramètres de proxy pour Windows 10, consultez [créer un profil de Wi-Fi pour les appareils dans Microsoft Intune Azure](/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Applications métier 
si plusieurs applications peuvent être installées par le biais du Microsoft Store, il est probable que vous disposiez de votre propre application personnalisée que vous avez créée spécifiquement pour une utilisation en réalité mixte. Ces applications personnalisées distribuées au sein de votre organisation pour votre entreprise sont appelées applications métier.
  
il existe plusieurs façons de déployer des applications sur des appareils HoloLens 2. les applications peuvent être déployées directement via MDM, le Microsoft Store pour Entreprises (MSfB) ou faisant via un Package d’approvisionnement. Dans le cadre de ce guide, nous allons déployer des applications via MDM, à l’aide de l’installation d’application requise. cela permet de télécharger automatiquement vos applications métier sur vos appareils HoloLens une fois qu’ils ont terminé l’inscription.

Pour ceux d’entre vous qui n’ont pas votre propre LOB, nous vous fournissons un exemple d’application pour tester ce processus de déploiement. Cette application sera l’application [MRTK examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) , qui a déjà été prégénérée et empaquetée pour tester la preuve de concept.

Pour plus d’informations sur le déploiement d’applications, consultez [gestion des applications : vue d’ensemble](/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 prend en charge l’exécution d’applications ARM64 UWP uniquement.

## <a name="guides-playbook"></a>Manuel des guides
Repères utilise un environnement Microsoft Dataverse comme magasin de banques de vos applications guides. Il est important de comprendre la plus grande image de la manière dont votre environnement Dataverse interagit avec vos applications guides et votre locataire. nous n’aborderons pas la façon de gérer vos dataverse dans ce guide, mais nous vous invitons à consulter [les concepts de base pour le déploiement de Dynamics 365 Guides-Dynamics 365 la réalité mixte](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté d’entreprise-configurer](hololens2-corp-connected-configure.md)