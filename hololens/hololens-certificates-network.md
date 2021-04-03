---
title: Préparer des certificats et des profils de réseau pour l'HoloLens 2
description: Découvrez comment configurer, utiliser, déployer et dépanner des certificats pour le réseau sur des appareils de réalité mixte HoloLens 2.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de9f2c4f136a26a5956ba8a8f3b9faba1e90ea66
ms.sourcegitcommit: 86dba9e8a5e25f0bf29f4c0580970c25c44b7359
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470052"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Préparer des certificats et des profils de réseau pour l'HoloLens 2

L'authentification par certificat est une exigence courante pour les clients qui utilisent HoloLens 2. Vous pourriez avoir besoin de certificats pour accéder au Wi-Fi, pour vous connecter à des solutions VPN ou pour accéder aux ressources internes de votre organisation.

Comme les appareils HoloLens 2 sont généralement associés à Azure Active Directory (Azure AD) et gérés par Intune ou un autre fournisseur de MDM, vous devrez déployer ces certificats en utilisant une infrastructure de certificats SCEP (Simple Certificate Enrollment Protocol) ou PKCS (Public Key Cryptography Standard) intégrée à votre solution MDM. 

>[!NOTE]
> Si vous n'avez pas de fournisseur GPM, vous pouvez toujours déployer des certificats par le biais d'un [package d'approvisionnement](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) dans [Concepteur de configuration Windows](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) ou par le biais du [Gestionnaire de certificats](https://docs.microsoft.com/hololens/certificate-manager) en accédant à **Paramètres > Mise à jour et sécurité > Gestionnaire de certificats**.

## <a name="certificate-requirements"></a>Exigences de certificat
Les certificats racine sont nécessaires pour déployer les certificats à travers une infrastructure SCEP ou PKCS. D'autres applications et services de votre organisation peuvent nécessiter le déploiement de certificats racine sur vos appareils HoloLens 2 également. 

## <a name="wi-fi-connectivity-requirements"></a>Exigences en matière de connectivité Wi-Fi
Pour qu'un appareil soit automatiquement doté de la configuration Wi-Fi requise pour votre réseau d'entreprise, vous aurez besoin d'un profil de configuration Wi-Fi. Vous pouvez configurer Intune ou un autre fournisseur de MDM pour déployer ces profils sur vos appareils. Si la sécurité de votre réseau exige que les appareils fassent partie du domaine local, vous devrez peut-être aussi évaluer votre infrastructure de réseau Wi-Fi pour vous assurer qu'elle est compatible avec les appareils HoloLens 2 (les appareils HoloLens 2 sont uniquement Azure AD-joints).

## <a name="deploy-certificate-infrastructure"></a>Déployer l'infrastructure des certificats
Si aucune infrastructure SCEP ou PKCS n'existe déjà, vous devrez en préparer une. Pour permettre l'utilisation de certificats SCEP ou PKCS pour l'authentification, Intune exige l'utilisation d'un [d'un connecteur de certificat ](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Lorsque vous utilisez le SCEP avec CA Microsoft, vous devez également configurer le [service d'inscription des périphériques réseau (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Pour plus d'informations, voir [Configurer un profil de certificat pour vos appareils dans Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Déployer les certificats et le profil Wi-Fi/VPN
Pour déployer les certificats et les profils, suivez ces étapes :
1.  Créez un profil pour chacun des certificats racine et intermédiaire (voir [Créer des profils de certificats de confiance ](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Chacun de ces profils doit avoir une description qui comprend une date d'expiration au format JJ/MM/AAAA. **Les profils de certificat sans date d'expiration ne seront pas déployés.**
1.  Créer un profil pour chaque certificat SCEP ou PKCS (voir [Créer un profil de certificat SCEP ou Créer un profil de certificat PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Chacun de ces profils doit avoir une description qui comprend une date d'expiration au format JJ/MM/AAAA. **Les profils de certificat sans date d'expiration ne seront pas déployés.**

    > [!NOTE]
    > Comme l'HoloLens 2 est considéré pour beaucoup comme un appareil partagé, plusieurs utilisateurs par appareil, il est recommandé de déployer des certificats d'appareil au lieu de certificats d'utilisateur pour l'authentification Wi-Fi lorsque cela est possible

3.  Créez un profil pour chaque réseau Wi-Fi d'entreprise (voir[les paramètres Wi-Fi pour les appareils Windows 10 et ultérieurs](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Il est recommandé d'attribuer le profil Wi-Fi à [des groupes ](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) d'appareils plutôt qu'à des groupes d'utilisateurs, dans la mesure du possible. 

    > [!TIP]
    > Vous pouvez également exporter un profil Wi-Fi fonctionnel à partir d'un ordinateur Windows 10 sur votre réseau corporatif. Cette exportation crée un fichier XML avec tous les paramètres actuels. Ensuite, importez ce fichier dans Intune, et utilisez-le comme profil Wi-Fi pour vos appareils HoloLens 2. Voir [ Exporter et importer les paramètres Wi-Fi pour les appareils Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Créez un profil pour chaque VPN corporatif (voir [ les paramètres de Windows 10 et de Windows Holographic pour ajouter des connexions VPN en utilisant Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Résolution des problèmes de certificats

Si vous devez confirmer que le déploiement d’un certificat est correct, veuillez utiliser le [Gestionnaire de certificats](certificate-manager.md) de l’appareil pour vérifier que votre certificat est présent.  


