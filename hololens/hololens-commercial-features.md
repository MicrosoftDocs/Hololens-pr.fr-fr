---
title: Fonctionnalités commerciales
description: Découvrez les fonctionnalités de Microsoft HoloLens Commercial Suite conçues pour faciliter la gestion des appareils HoloLens par les entreprises.
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
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397860"
---
# <a name="commercial-features"></a>Fonctionnalités commerciales

HoloLens offre des fonctionnalités qui simplifient la gestion des appareils HoloLens par les entreprises.

Chaque appareil HoloLens 2 dispose de fonctionnalités commerciales.

L'HoloLens (1ère génération) était proposé avec deux options de licence, la licence développeur et une licence commerciale. Pour déverrouiller les fonctionnalités commerciales de l'HoloLens, passez de la licence développeur à une licence commerciale. Pour acheter Microsoft HoloLens Commercial Suite, contactez votre responsable de compte Microsoft local.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Principales fonctionnalités commerciales

- **Mode plein écran.** Vous pouvez utiliser l'HoloLens en mode de démonstration ou de présentation à l'aide du mode plein écran afin de restreindre les applications qui peuvent être exécutées.

  ![En mode plein écran, l'HoloLens se lance directement dans l'application de votre choix.](images/201608-kioskmode-400px.png)

- **Gestion des périphériques mobiles (GPM) pour HoloLens.** Votre service informatique peut gérer plusieurs appareils HoloLens simultanément à l'aide de solutions telles que Microsoft Intune. Vous pouvez gérer les paramètres, sélectionner les applications à installer et définir des configurations de sécurité adaptées aux besoins de votre organisation.

  ![Sur HoloLens, la gestion des périphériques mobiles permet une gestion de niveau entreprise sur de multiples appareils.](images/201608-enterprisemanagement-400px.png)

- **Windows Update for Business.** Windows Update for Business fournit aux appareils des mises à jour contrôlées du système d'exploitation et la prise en charge du canal de maintenance à long terme.
- **Sécurité des données** Le chiffrement des données BitLocker est activé sur HoloLens pour fournir le même niveau de protection que sur n'importe quel autre appareil Windows.
- **Accès professionnel.** Tout utilisateur d'un HoloLens de votre organisation peut se connecter à distance au réseau de l'entreprise par le biais d'un réseau privé virtuel (VPN). L'HoloLens peut également accéder à des réseaux Wi-Fi qui nécessitent des informations d'identification.
- **Microsoft Store pour Entreprises.** Votre service informatique peut également configurer un magasin privé d'entreprise contenant uniquement les applications de votre entreprise qui sont utiles à votre utilisation d'HoloLens. Distribuez en toute sécurité vos logiciels d'entreprise à certains groupes d'utilisateurs.

## <a name="feature-comparison-between-editions"></a>Comparaison des fonctionnalités entre les éditions

|Fonctionnalités |HoloLens Development Edition (1ère génération) |HoloLens Commercial Suite (1ère génération) |HoloLens 2 |
|---|:---:|:---:|:---:|
|Chiffrement de l'appareil (BitLocker) | |✔️ |✔️ |
|Réseau privé virtuel (VPN) | |✔️ |✔️ |
|[Mode plein écran](hololens-kiosk.md) | |✔️ |✔️ |
|**Gestion et déploiement** | | | |
|Gestion des appareils mobiles | |✔️ |✔️ |
|Possibilité de bloquer l'annulation de l'inscription | |✔️ |✔️ |
|Accès Wi-Fi d'entreprise basé sur un certificat | |✔️ |✔️ |
|Microsoft Store (grand public) |Consommateur |Filtrer à l'aide de la gestion des périphériques mobiles |Filtrer à l'aide de la gestion des périphériques mobiles |
|[Portail Business Store](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Sécurité et identité** | | | |
|Se connecter à l'aide d'un compte Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Se connecter à l'aide d'un compte Microsoft (MSA) |✔️ |✔️ |✔️ |
|Informations d'identification nouvelle génération avec déverrouillage par code PIN |✔️ |✔️ |✔️ |
|[Démarrage sécurisé](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Maintenance et support** | | | |
|Mises à jour système automatiques à mesure qu'elles arrivent |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Canal de maintenance à long terme (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Activer les fonctionnalités commerciales

L'administrateur informatique de votre organisation peut installer des fonctionnalités commerciales telles que Microsoft Store pour Entreprises, le mode plein écran et l'accès Wi-Fi d'entreprise. La documentation [Microsoft HoloLens](index.yml) fournit des instructions détaillées pour inscrire des appareils et installer des applications à partir de Microsoft Store pour Entreprises.

## <a name="see-also"></a>Voir aussi

- [Microsoft HoloLens](index.yml)
- [Mode plein écran](hololens-kiosk.md)
- [Fournisseurs de solutions Cloud pris en charge sur les appareils HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store pour Entreprises et applications métiers](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Utilisation des applications cœur de métier](/microsoft-store/working-with-line-of-business-apps)
