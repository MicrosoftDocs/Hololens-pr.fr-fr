---
title: Inscrire HoloLens dans GPM
description: Inscrire HoloLens dans Gestion des périphériques mobiles (GPM) pour faciliter la gestion de plusieurs appareils.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903220"
---
# Inscrire HoloLens dans un logiciel de gestion des périphériques mobiles (GPM)

Vous pouvez gérer plusieurs appareils Microsoft HoloLens en même temps à l’aide de solutions comme [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise. Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Conditions requises

 Pour pouvoir gérer les appareils HoloLens, votre organisation doit disposer de la gestion des périphériques mobiles (GPM). Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.
 
## Différentes façons de s’inscrire

Selon le type d’identité choisi lors de la connexion OOBE ou après l’inscription, il existe différentes méthodes d’inscription. Pour en savoir plus sur chaque type d’identité sur HoloLens, consultez [cette page](hololens-identity.md).

- Si Identity est AAD, vous pouvez le faire au cours de l’utilisation de l' **application**OOBE ou du  ->  bouton**School**  ->  **Connect** .
    - Pour l’inscription AAD, l’inscription de la gestion des appareils mobiles automatique se produit uniquement si AAD a été configuré avec les URL d’inscription.
- Si Identity est AAD et que l’appareil a été préconfiguré et qu’il a été enregistré avec un profil de configuration Intune et qu’il est affecté, l’inscription AAD et l’inscription se produiront automatiquement dans OOBE.
    - Également appelé [flux AutoPilot](hololens2-autopilot.md) disponible dans les [Builds 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).
- Si Identity est MSA, utilisez le bouton d’accès à l' **application paramètres**d’utilisation  ->  **ou de School**  ->  **Connect** .
    - Également appelé flux d’ajout de compte de bureau (AWA).
- Si Identity est un utilisateur local, utilisez **Settings App**  ->  **Access Work ou School**  ->  **ENROLL only dans le lien gestion des périphériques** .
    - Également appelé flux d’inscription pour le GPM.

Une fois que l’appareil est inscrit auprès de votre serveur de gestion des périphériques mobiles, l’application paramètres indique désormais que l’appareil est inscrit à la gestion des appareils.

## Inscription automatique dans GPM

Si votre organisation utilise Azure ActiveDirectory (Azure AD) et une solution GPM qui accepte un jeton AAD pour l’authentification (uniquement pris en charge pour l’instant dans MicrosoftIntune et AirWatch), votre administrateur informatique peut configurer Azure AD de manière à autoriser automatiquement l’inscription GPM une fois que l’utilisateur s’est connecté avec son compte Azure AD. [Découvrez comment configurer l’inscription Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire. Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.

## Désinscrire HoloLens de Intune

Pour en savoir plus sur l’annulation de l’inscription d’un appareil, consultez [cette page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
