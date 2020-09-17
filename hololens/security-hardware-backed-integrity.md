---
title: Attestation d'intégrité et de runtime soutenue par le matériel
description: Attestation d'intégrité et de runtime soutenue par le matériel
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: sécurité, hololens, intégrité soutenue par le matériel, attestation runtime, UEFI, démarrage sécurisé UEFI, démarrage sécurisé, TPM, protection contre les menaces, assurance anti-persistance Windows, intégrité du code, protection du code,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: befd2d892403b7b6c7050f48ba9beffb45b241fe
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016678"
---
# Attestation d'intégrité et de runtime soutenue par le matériel

L'intégrité soutenue par le matériel et l'attestation runtime protège contre les menaces qui proviennent avant le démarrage d'un système d'exploitation, pendant l'exécution, lorsque le dispositif utilise du matériel, et les services d'attestation à distance pour garantir le maintien de l'intégrité au démarrage et pendant toute la durée d'exécution.

## Démarrage sécurisé UEFI

HoloLens 2 applique le démarrage sécurisé UEFI (Unified Extensible Firmware Interface) à tout moment, et UEFI démarre uniquement Windows holographique pour les entreprises.
Le démarrage sécurisé permet de vérifier que toute la chaîne de démarrage est vérifiée et que Windows démarre toujours avec les stratégies de sécurité appropriées qui lui sont appliquées. Pour en savoir plus sur le démarrage sécurisé, cliquez ici.

## TPM

Le module de plateforme sécurisée (TPM) est une puce spécialisée sur un appareil de point de terminaison. HoloLens 2 utilise une puce TPM 2.0 qui fournit une isolation des clés appliquée par le matériel.

## Accès à la persistance protection contre les menaces

L'objectif de la plupart des cyberattaques est de maintenir un accès persistant à un appareil. Pour la cybercriminalité, maintenir cette persistance permet à un appareil Windows compromis de rejoindre un botnet, de vendre l’accès à l’appareil ou à d’autres utilisateurs de malveillants, ou d’autoriser un vol de données répété. Dans le monde des attaques ciblées, la persistance est essentielle à la réussite d'une cyberattaque, que ce soit sur un appareil ou (plus communément) sur un réseau entier.  

En fait, des attaques ciblées sont considérées comme une «menace persistante avancée», en raison de leur besoin stratégique de maintenir l’accès à un appareil ou à un réseau cible. Pour cette raison, Windows holographique pour les entreprises considère la défense contre la persistance absolument cruciale et utilise la technologie anti-persistance pour faire une promesse de sécurité à toute épreuve aux clients.

### Démarrage sécurisé 

HoloLens 2 applique le démarrage sécurisé de l’interface UEFI (Unified Extensible Firmware Interface) sur l’état de tous les systèmes d’exploitation centraux. UEFI ne démarre que les plateformes de confiance de Microsoft, ce permet de vérifier que toute la chaîne de démarrage est vérifiée et que Windows démarre toujours avec les stratégies de sécurité appropriées qui lui sont appliquées. Le démarrage de l’application HoloLens 2 ne permet pas de désactiver le démarrage, ni d’autoriser les chargeurs de démarrage tiers.

> [!Tip]
> En savoir plus sur [Démarrage sécurisée](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Assurance contre la persistance de Windows

La fonctionnalité d'anti-persistance de l'HoloLens 2 garantit à ses utilisateurs que même dans la rare situation où un compromis d'exécution du système devait se produire (par exemple, un exploitation à distance), un tel événement serait atténué par le retrait de tout code malveillant du système simplement en éteignant l'appareil. Afin de renforcer son anti-persistance, HoloLens 2 a ajouté une protection d'intégrité puissante, et a mis en place des protections en lecture seule.

La persistance aux données de système d’exploitation sous forme de données est encore possible, sauf si l’utilisateur effectue une réinitialisation de bouton-poussoir (PBR) de l’appareil qui efface toutes les partitions mutables. Bien que la persistance de partitions immuables soit rendue plus difficile, l'utilisateur a besoin de PBR le Hololens 2 pour supprimer toute menace-persistance possible des parties mutables.

## Protection de l’intégrité du code 

L’intégrité du code (IC) est une propriété de sécurité essentielle d’un système d’exploitation moderne. L'application de l'IC permet de prendre des décisions de sécurité judicieuses, car elle garantit que la provenance du code est transparente tant pour l'utilisateur que pour le système d'exploitation. L’intégrité complète du code doit s'étendre au-delà de la signature d’image binaire précédente et inclure l’application Runtime, comme l’intégrité du flux de contrôle et les restrictions relatives au code dynamique. L'intégrité du code est essentielle pour prévenir de multiples classes d'attaques, y compris les logiciels malveillants d'ingénierie sociale, tels que les rançonlogiciels, les exploitations d'exécution de code à distance et diverses autres classes d'attaques.
