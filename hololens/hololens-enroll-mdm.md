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
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828095"
---
# Inscrire HoloLens dans un logiciel de gestion des périphériques mobiles (GPM)

Vous pouvez gérer plusieurs appareils Microsoft HoloLens en même temps à l’aide de solutions comme [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise. Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Conditions requises

 Pour pouvoir gérer les appareils HoloLens, votre organisation doit disposer de la gestion des périphériques mobiles (GPM). Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.

## Inscription automatique dans GPM

Si votre organisation utilise Azure ActiveDirectory (Azure AD) et une solution GPM qui accepte un jeton AAD pour l’authentification (uniquement pris en charge pour l’instant dans MicrosoftIntune et AirWatch), votre administrateur informatique peut configurer Azure AD de manière à autoriser automatiquement l’inscription GPM une fois que l’utilisateur s’est connecté avec son compte Azure AD. [Découvrez comment configurer l’inscription Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire. Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.

## Inscription via l’application Paramètres

 Lorsque l’appareil n’est pas inscrit dans GPM lors de sa première utilisation, l’utilisateur peut l'inscrire manuellement avec le serveur GPM de l’entreprise via l’application Paramètres.

1. Rendez-vous sur **Paramètres** > **Comptes** > **Accès professionnel**.
1. Sélectionnez **Inscription GPM (gestion des périphériques mobiles)** et saisissez le compte de votre entreprise. Vous serez redirigé vers la page de connexion de votre entreprise.
1. Si l’authentification aboutit sur le serveur GPM, un message de réussite s’affiche.

Votre appareil est maintenant inscrit auprès de votre serveur GPM. L’application Paramètres montre maintenant que le périphérique est inscrit dans la gestion des périphériques.

## Désinscrire HoloLens de Intune

Vous ne pouvez pas [désinscrire](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) un HoloLens de Intune à distance. Si l’administrateur désinscrit l’appareil à l’aide de la GPM, l’appareil demeurera en dehors du tableau de bord Intune.
