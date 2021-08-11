---
title: Attestation d’intégrité et de runtime assurée par le matériel
description: Attestation d’intégrité et de runtime assurée par le matériel
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: sécurité, hololens, intégrité assurée par le matériel, attestation de runtime, UEFI, démarrage sécurisé UEFI, démarrage sécurisé, TPM, protection contre les menaces, assurance anti-persistance de Windows, intégrité du code, protection du code,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de12231b87c028ed9d8ca785a5b351fc4cb1c6fd8dbe304e4baaccd6803c5f6a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665401"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Attestation d’intégrité et de runtime assurée par le matériel

L’attestation d’intégrité et de runtime assurée par le matériel protège contre les menaces qui proviennent d’avant le démarrage d’un système d’exploitation, pendant l’exécution, quand le dispositif utilise du matériel, et des services d’attestation à distance pour garantir le maintien de l’intégrité au démarrage et pendant toute la durée de l’exécution.

## <a name="uefi-secure-boot"></a>Démarrage sécurisé UEFI

HoloLens 2 applique toujours le démarrage sécurisé UEFI (Unified Extensible Firmware Interface) et UEFI démarre seulement Windows Holographic for Business.
Le démarrage sécurisé garantit que l’intégrité de toute la chaîne de démarrage est vérifiée et que Windows démarre toujours avec les stratégies de sécurité appropriées appliquées. En savoir plus sur le [démarrage sécurisé](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>Module de plateforme sécurisée

Le module de plateforme sécurisée (TPM) est une puce spécialisée sur un appareil de point de terminaison. HoloLens 2 utilise un TPM 2.0, qui fournit une isolation de clé appliquée par le matériel. En savoir plus sur les [concepts de base de TPM](/windows/security/information-protection/tpm/tpm-fundamentals).

## <a name="persistence-access-threat-protection"></a>Protection contre les menaces d’accès persistant

L’objectif de la plupart des cyberattaques est de maintenir un accès persistant à un appareil. Pour la cybercriminalité, maintenir cette persistance permet à un appareil Windows compromis de rejoindre un botnet, de vendre l’accès à l’appareil ou à d’autres utilisateurs malveillants, ou d’autoriser le vol de données répété. Dans le monde des attaques ciblées, la persistance est essentielle à la réussite d’une cyberattaque, que ce soit sur un appareil ou (plus communément) sur tout un réseau.  

En fait, les attaques ciblées sont considérées comme une « menace persistante avancée », en raison de leur besoin stratégique de maintenir l’accès à un appareil ou à un réseau cible. Pour cette raison, Windows Holographic for Business considère comme absolument cruciale la défense contre la persistance et utilise une technologie anti-persistance pour faire une promesse de sécurité à toute épreuve aux clients.

### <a name="secure-boot"></a>Démarrage sécurisé

HoloLens 2 applique le démarrage sécurisé de l’interface UEFI (Unified Extensible Firmware Interface) sur l’état de tous les systèmes d’exploitation principaux. UEFI démarre seulement les plateformes de confiance Microsoft, ce qui garantit que l’intégrité de toute la chaîne de démarrage est vérifiée et que Windows démarre toujours avec les stratégies de sécurité appliquées. HoloLens 2 ne permet pas de désactiver le démarrage sécurisé et n’autorise pas les chargeurs de démarrage tiers.

> [!Tip]
> En savoir plus sur le [démarrage sécurisé](/windows-hardware/design/device-experiences/oem-secure-boot).

### <a name="windows-anti-persistence-assurance"></a>Assurance anti-persistance de Windows

La fonctionnalité d’anti-persistance d’HoloLens 2 garantit à ses utilisateurs que même dans la rare situation où un compromis d’exécution du système devait se produire (par exemple un exploit à distance), un tel événement serait atténué via la suppression de tout le code malveillant du système simplement en éteignant l’appareil. Afin de renforcer son anti-persistance, HoloLens 2 a ajouté une protection d’intégrité puissante et a mis en place des protections en lecture seule.

La persistance des données du système d’exploitation sous forme de données est encore possible, sauf si l’utilisateur effectue une réinitialisation rapide de l’appareil qui efface toutes les partitions mutables. Alors que la persistance des partitions immuables est rendue beaucoup plus difficile, l’utilisateur doit effectuer une réinitialisation rapide d’HoloLens 2 pour supprimer toute persistance des menaces possibles des parties mutables.

## <a name="code-integrity-protection"></a>Protection de l’intégrité du code

L’intégrité du code est une propriété de sécurité essentielle d’un système d’exploitation moderne. L’application de l’intégrité du code permet de prendre des décisions de sécurité judicieuses, car elle garantit que la provenance du code est transparente tant pour l’utilisateur que pour le système d’exploitation. L’intégrité complète du code doit s’étendre au-delà de la signature d’image binaire déjà existante et inclure l’application du runtime, comme l’intégrité du flux de contrôle et les restrictions relatives au code dynamique. L’intégrité du code est essentielle pour prévenir de multiples classes d’attaques, notamment les logiciels malveillants de l’ingénierie sociale, comme les rançonlogiciels, les exploits d’exécution de code à distance et différentes autres classes d’attaques.
