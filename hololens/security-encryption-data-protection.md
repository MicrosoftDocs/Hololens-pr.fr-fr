---
title: Chiffrement et protection des données
description: Découvrez le chiffrement et la protection des données sur les appareils HoloLens 2, notamment l’intégration de BitLocker et d’Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, Chiffrement, Protection des données, appareil BitLocker, BitLocker, bitlocker, chiffrement bitlocker, intégration d’azure,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639367"
---
# <a name="encryption-and-data-protection"></a>Chiffrement et protection des données

Le chiffrement et la protection des données protègent les données en cas de perte ou de vol de l’appareil, et empêchent les applications non autorisées d’accéder aux informations sensibles.

## <a name="bitlocker-device-encryption"></a>Chiffrement de l’appareil BitLocker

BitLocker est une fonctionnalité de chiffrement de volume complet pour la protection de l’intégrité des médias en lecture seule et la protection de la confidentialité des médias inscriptibles.  Depuis sa création, c’est un bouclier efficace contre l’accès non autorisé aux données lors d’attaques hors connexion. HoloLens 2 active par défaut le chiffrement de l’appareil BitLocker (BDE, Device Encryption BitLocker) pour protéger les données contre les accès physiques non autorisés à l’appareil. Microsoft continue d’investir et d’améliorer cette technologie afin de répondre aux besoins du futur, qui évoluent en permanence.

BDE est une fonctionnalité de protection des données qui utilise le chiffrement AES-XTS-256 sur tous les volumes dans la disposition de l’appareil séparée par état. BDE fournit un chiffrement au niveau de l’appareil dans une disposition séparée par état. Le chiffrement de l’appareil BitLocker est activé automatiquement sur le système d’exploitation et les volumes de données fixes, et il ne peut pas être désactivé, même par les administrateurs informatiques, afin que l’appareil soit toujours protégé.

Les clés de chiffrement BDE sont ensuite utilisées pour déchiffrer de façon transparente les fichiers binaires et les données nécessaires au démarrage de l’appareil. Quand le volume hébergeant un système d’exploitation est déverrouillé et qu’un système démarre, les autres volumes deviennent accessibles avec une version spécifique du volume du protecteur de déverrouillage automatique. Aucun autre protecteur n’est disponible pour préserver la confidentialité des utilisateurs et le lecteur peut être déverrouillé seulement sur le même appareil. L’application en lecture seule sur les volumes requis est appliquée et mise en place immédiatement, dès le premier démarrage. La clé de récupération Bitlocker n’est pas nécessaire dans le cycle de vie d’HoloLens 2.

## <a name="azure-integration"></a>Intégration Azure 

HoloLens 2 permet aux clients d’intégrer leurs appareils aux services Azure. Les communications entre les appareils HoloLens 2 et Azure utilisent le protocole TLS (Transport Layer Security) pour protéger les données transitant entre ces appareils et les services cloud, ce qui offre une authentification, une confidentialité des messages et une intégrité renforcées. Tous les services Azure prennent entièrement en charge le protocole TLS 1.2 et les services où les clients utilisent seulement TLS 1.2 n’acceptent que le trafic TLS 1.2. Les standards de chiffrement d’Azure pour les données en transit sont détaillées dans [Vue d’ensemble du chiffrement Azure](/azure/security/fundamentals/encryption-overview). Consultez la documentation d’Azure pour en savoir plus sur les [bonnes pratiques en matière de chiffrement et de sécurité des données Azure](/azure/security/fundamentals/data-encryption-best-practices). 

OneDrive, un exemple d’intégration cloud à HoloLens 2, dispose d’une fonctionnalité de téléchargement automatique grâce à laquelle vos fichiers et documents peuvent être automatiquement chargés sur le cloud quand vous êtes connecté à Internet. La mise en pause de la synchronisation automatique des fichiers ne peut pas être désactivée via une stratégie mais elle est directement configurable via l’expérience utilisateur. 
