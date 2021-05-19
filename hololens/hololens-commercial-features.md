---
title: Fonctionnalités commerciales
description: Découvrez les fonctionnalités de Microsoft HoloLens Commercial Suite qui facilitent la gestion des appareils HoloLens par les entreprises.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, commercial, fonctionnalités, gpm, gestion des périphériques mobiles, mode plein écran
ms.openlocfilehash: 5aef764b1d7937832e162ab219131d8c3d768e68
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283445"
---
# Fonctionnalités commerciales

HoloLens offre des fonctionnalités qui simplifient la gestion des appareils HoloLens pour les entreprises.

Chaque appareil HoloLens 2 dispose de fonctionnalités commerciales.

HoloLens (1re génération) est doté de deux options de gestion des licences, la licence développeur et une licence commerciale. Pour déverrouiller les fonctionnalités commerciales de HoloLens, mettez à niveau la licence développeur à une licence commerciale. Pour acheter Microsoft HoloLens Commercial Suite, contactez votre gestionnaire de comptes Microsoft local.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## Principales fonctionnalités commerciales

- **Mode plein écran.** Vous pouvez utiliser HoloLens en mode de démonstration ou de présentation à l’aide du mode plein écran afin de restreindre les applications pouvant être exécutées.

  ![À l’aide du mode plein écran, HoloLens est lancé directement dans l’application de votre choix.](images/201608-kioskmode-400px.png)

- **Gestion des périphériques mobiles (GPM) pour HoloLens.** Votre service informatique peut gérer plusieurs appareils HoloLens en même temps à l’aide de solutions telles que Microsoft Intune. Vous pouvez gérer les paramètres, sélectionner les applications à installer et définir des configurations de sécurité adaptées aux besoins de votre organisation.

  ![La gestion des périphériques mobiles sur HoloLens fournit une gestion des périphériques de niveau entreprise sur plusieurs appareils.](images/201608-enterprisemanagement-400px.png)

- **Windows Update pour Entreprise.** Windows Update pour Entreprise fournit des mises à jour de système d’exploitation contrôlées sur les appareils et la prise en charge du canal de maintenance à long terme.
- **Protection des données.** Le chiffrement de données BitLocker est activé sur HoloLens pour fournir le même niveau de protection de la sécurité qu’un autre appareil Windows.
- **Accès au bureau.** Toutes les personnes de votre organisation peuvent se connecter à distance au réseau d’entreprise via un réseau privé virtuel (VPN) sur un HoloLens. HoloLens peut également accéder aux réseaux Wi-Fi qui nécessitent des informations d’identification.
- **Microsoft Store pour Entreprises.** Votre service informatique peut également configurer un magasin privé d’entreprise contenant uniquement les applications de votre entreprise utiles à votre utilisation de HoloLens. Distribuez en toute sécurité votre logiciel d’entreprise à certains groupes d’utilisateurs d’entreprise.

## Comparaison des fonctionnalités entre les éditions

|Fonctionnalités |HoloLens Development Edition |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Chiffrement de l’appareil (BitLocker) | |✔️ |✔️ |
|Réseau privé virtuel (VPN) | |✔️ |✔️ |
|[Mode plein écran](hololens-kiosk.md) | |✔️ |✔️ |
|**Gestion et déploiement** | | | |
|Gestion des périphériques mobiles (GPM) | |✔️ |✔️ |
|Possibilité de bloquer l’annulation de l’inscription | |✔️ |✔️ |
|Accès Wi-Fi d’entreprise basé sur un certificat | |✔️ |✔️ |
|Microsoft Store (grand public) |Grand public |Filtrer à l’aide de la gestion des périphériques mobiles |Filtrer à l’aide de la gestion des périphériques mobiles |
|[Portail Business Store](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Sécurité et identité** | | | |
|Se connecter à l’aide d’Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Se connecter à l’aide d’un compte Microsoft (MSA) |✔️ |✔️ |✔️ |
|Informations d’identification nouvelle génération avec déverrouillage par code confidentiel |✔️ |✔️ |✔️ |
|[Démarrage sécurisé](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Maintenance et support** | | | |
|Mises à jour système automatiques à mesure qu’elles arrivent |✔️ |✔️ |✔️ |
|[Windows Update pour Entreprise](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Canal de maintenance à long terme (LTSC) | |✔️ |✔️ |

## Activation des fonctionnalités commerciales

L’administrateur informatique de votre organisation peut installer des fonctionnalités commerciales telles que Microsoft Store pour Entreprises, le mode plein écran et l’accès Wi-Fi d’entreprise. La documentation [Microsoft HoloLens](index.yml) fournit des instructions détaillées pour inscrire des appareils et installer des applications à partir de Microsoft Store pour Entreprises.

## Articles associés

- [Microsoft HoloLens](index.yml)
- [Mode plein écran](hololens-kiosk.md)
- [Fournisseurs de solutions Cloud pris en charge sur les appareils HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store pour Entreprises et applications cœur de métier](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Utilisation des applications cœur de métier](/microsoft-store/working-with-line-of-business-apps)
