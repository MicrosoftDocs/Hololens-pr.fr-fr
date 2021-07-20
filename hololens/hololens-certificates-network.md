---
title: Préparer des certificats et des profils réseau pour HoloLens 2
description: Apprenez à configurer, utiliser, déployer et dépanner des certificats pour le réseau sur des appareils de réalité mixte HoloLens 2.
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
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639265"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Préparer des certificats et des profils réseau pour HoloLens 2

L'authentification basée sur les certificats est une exigence courante pour les clients qui utilisent l'HoloLens 2. Des certificats peuvent être requis pour accéder au Wi-Fi, pour vous connecter à des solutions VPN ou pour accéder aux ressources internes de votre organisation.

Comme les appareils HoloLens 2 sont généralement joints à Azure Active Directory (Azure AD) et gérés par Intune ou un autre fournisseur GPM, vous devrez déployer ces certificats via une infrastructure de certificats SCEP (Simple Certificate Enrollment Protocol) ou PKCS (Public Key Cryptography Standard) intégrée à votre solution GPM. 

>[!NOTE]
> Si vous n'avez pas de fournisseur GPM, vous pouvez toujours déployer des certificats via un [package de configuration](hololens-provisioning.md#steps-for-creating-provisioning-packages) dans le [Concepteur de configuration Windows](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab), ou via le [Gestionnaire de certificats](certificate-manager.md) en accédant à **Paramètres > Mise à jour et sécurité > Gestionnaire de certificats**.

## <a name="certificate-requirements"></a>Configuration requise des certificats
Les certificats racine sont nécessaires pour déployer des certificats via une infrastructure SCEP ou PKCS. Les certificats racine peuvent également être exigés pour déployer d'autres applications et services de votre organisation sur vos appareils HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Exigences en matière de connectivité Wi-Fi
Pour qu'un appareil reçoive automatiquement la configuration Wi-Fi requise pour votre réseau d'entreprise, un profil de configuration Wi-Fi est nécessaire. Vous pouvez configurer Intune ou un autre fournisseur GPM pour qu'il déploie ces profils sur vos appareils. Si la sécurité de votre réseau exige que les appareils fassent partie du domaine local, vous serez peut-être amené à évaluer votre infrastructure de réseau Wi-Fi pour vous assurer qu'elle est compatible avec les appareils HoloLens 2 (les appareils HoloLens 2 sont uniquement joints à Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Déployer l'infrastructure de certificats
En l'absence d'infrastructure SCEP ou PKCS, vous devrez en préparer une. Pour utiliser des certificats SCEP ou PKCS dans le cadre de l'authentification, Intune exige l'utilisation d'un [connecteur de certificats](/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Lorsque vous utilisez SCEP avec une autorité de certification Microsoft, vous devez également configurer le [service d'inscription de périphérique réseau (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes).

Pour plus d'informations, consultez [Configurer un profil de certificat pour vos appareils dans Microsoft Intune](/intune/certificates-configure).

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Déployer les certificats et le profil Wi-Fi/VPN
Pour déployer les certificats et les profils, procédez comme suit :
1.  Créez un profil pour chacun des certificats racine et intermédiaire (voir [Créer des profils de certificats de confiance](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Chacun de ces profils doit comporter une description qui inclut une date d'expiration au format AAAA/MM/JJ. **Les profils de certificat sans date d'expiration ne seront pas déployés.**
1.  Créez un profil pour chaque certificat SCEP ou PKCS (voir [Créer un profil de certificat SCEP ou Créer un profil de certificat PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Chacun de ces profils doit comporter une description qui inclut une date d'expiration au format AAAA/MM/JJ. **Les profils de certificat sans date d'expiration ne seront pas déployés.**

    > [!NOTE]
    > Comme l'HoloLens 2 est souvent considéré comme un appareil partagé, avec plusieurs utilisateurs par appareil, nous vous recommandons, si possible, de déployer des certificats d'appareil plutôt que des certificats d'utilisateur pour l'authentification Wi-Fi.

3.  Créez un profil pour chaque réseau Wi-Fi d'entreprise (voir [Paramètres Wi-Fi pour les appareils Windows 10 et ultérieurs](/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Dans la mesure du possible, nous vous recommandons d'[attribuer](/mem/intune/configuration/device-profile-assign) le profil Wi-Fi à des groupes d'appareils plutôt qu'à des groupes d'utilisateurs. 

    > [!TIP]
    > Vous pouvez également exporter un profil Wi-Fi fonctionnel à partir d'un PC Windows 10 sur votre réseau d'entreprise. Cette exportation crée un fichier XML contenant tous les paramètres actuels. Importez ensuite ce fichier dans Intune et utilisez-le comme profil Wi-Fi pour vos appareils HoloLens 2. Consultez [Exporter et importer les paramètres Wi-Fi pour des appareils Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

4.  Créez un profil pour chaque VPN d'entreprise (voir [Paramètres des appareils Windows 10 et Windows Holographic pour ajouter des connexions VPN à l'aide d'Intune](/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Résolution des problèmes de certificats

Si vous devez confirmer qu'un certificat a été correctement déployé, utilisez le [Gestionnaire de certificats](certificate-manager.md) de l'appareil pour vérifier qu'il est bien présent.  

>[!WARNING]
> Le Gestionnaire de certificats vous permet de visualiser les certificats déployés via GPM, mais pas de les désinstaller. Pour les désinstaller, vous devez utiliser GPM.


