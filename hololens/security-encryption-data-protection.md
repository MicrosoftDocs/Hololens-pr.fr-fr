---
title: Chiffrement et protection des données
description: Chiffrement et protection des données
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, chiffrement, Protection des données, dispositif BitLocker, BitLocker, bitlocker, chiffrement bitlocker, intégration azur,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f67e43eaf3a20a7f6948a448af2e5efdaa83821
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009542"
---
# Chiffrement et protection des données

Le chiffrement et la protection des données protègent les données en cas de perte ou de vol de l’appareil et empêchent les applications non autorisées d’accéder aux informations sensibles.

## Chiffrement de l’appareil BitLocker

BitLocker est une fonctionnalité de chiffrement à volume complet pour la protection de l’intégrité des médias en lecture seule et la protection de la confidentialité des médias inscriptibles.  Depuis sa création, c’est un bouclier efficace contre l’accès non autorisé aux données lors d’attaques hors ligne. HoloLens2 active par défaut le chiffrement de l’appareil BitLocker (BDE, Device Encryption BitLocker) pour protéger les données contre les accès physiques non autorisés à l’appareil. Microsoft continue d’investir et d’améliorer cette technologie afin de répondre aux besoins du futur, qui évoluent en permanence.

BDE est une fonctionnalité de protection des données qui utilise le chiffrement AES-XTS-256 sur tous les volumes dans la disposition séparée par état de l’appareil. BDE fournit un chiffrement au niveau de l’appareil dans une disposition séparée par état. Le chiffrement de l’appareil BitLocker est activé automatiquement sur le système d’exploitation et les volumes de données fixes et ne peut pas être désactivé, même par les administrateurs informatiques, afin que l’appareil soit toujours protégé.

Les clés de chiffrement BDE sont ensuite utilisées pour déchiffrer de manière transparente les fichiers binaires et les données nécessaires au démarrage de l’appareil. Lorsque le volume hébergeant un système d'exploitation est déverrouillé et qu’un système démarre, les autres volumes deviennent accessibles à l’aide d’une version spécifique du volume du protecteur de déverrouillage automatique. Aucun autre protecteur n’est disponible pour préserver la confidentialité des utilisateurs et le lecteur ne peut être déverrouillé que sur le même appareil. L’application en lecture seule sur les volumes requis est appliquée et mise en place immédiatement, dès le premier démarrage.

## Intégration Azure 

HoloLens2 permet aux clients d’intégrer leurs appareils aux services Azure. Les communications entre les appareils HoloLens2 et Azure utilisent le protocole TLS (Transport Layer Security) pour protéger les données voyageant entre eux et les services cloud, ce qui offre une authentification, une confidentialité des messages et une intégrité renforcées. Tous les services Azure prennent entièrement en charge le protocole TLS1.2 et tous les services dans lesquels les clients utilisent uniquement TLS 1.2 n’acceptent que le trafic TLS 1.2. Les normes de chiffrement Azure pour les données en transit sont détaillées dans la [présentation du chiffrement Azure](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview). Consultez la documentation Azure si vous souhaitez en savoir plus sur les [meilleures pratiques de sécurité et de chiffrement des données Azure](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices). 

OneDrive, un exemple d’intégration cloud avec HoloLens2, dispose d’une fonctionnalité de téléchargement automatique grâce à laquelle vos fichiers et documents peuvent être automatiquement téléchargés sur le cloud lorsque vous êtes connecté à Internet. Suspendre la synchronisation automatique des fichiers ne peut pas être désactivée via une stratégie mais est directement configurable via l’UX. 
