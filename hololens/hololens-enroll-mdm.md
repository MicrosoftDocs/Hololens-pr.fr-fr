---
title: Inscrire HoloLens dans GPM
description: découvrez comment inscrire HoloLens dans la gestion des appareils mobiles (MDM) pour faciliter la gestion de plusieurs appareils.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979353"
---
# <a name="enroll-hololens-in-mdm"></a>Inscrire HoloLens dans GPM

vous pouvez gérer plusieurs appareils Microsoft HoloLens simultanément à l’aide de solutions comme [Microsoft Intune](/intune/windows-holographic-for-business). Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise. consultez [gérer les appareils exécutant Windows holographique avec Microsoft Intune](/intune/windows-holographic-for-business), les [fournisseurs de services de configuration pris en charge dans Windows holographique](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La gestion des appareils mobiles (MDM), y compris les fonctionnalités VPN, BitLocker et en mode plein écran, est disponible uniquement lorsque vous [effectuez une mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Configuration requise

 votre organisation doit configurer la gestion des appareils mobiles (MDM) pour gérer les appareils HoloLens. Votre fournisseur GPM peut être Microsoft Intune ou un fournisseur tiers qui utilise les API GPM de Microsoft.

## <a name="different-ways-to-enroll"></a>Différentes façons d’inscrire

Selon le type d' [identité](hololens-identity.md) choisi pendant l’OOBE ou la publication, il existe différentes méthodes d’inscription.

- si l’identité est Azure AD, alors lors de l’utilisation d’OOBE ou **Paramètres**  ->  Connecter bouton d'**accès professionnel ou scolaire**  ->   .
    - Par Azure AD, l' [inscription automatique à MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se produit uniquement si Azure ad a été configuré avec des URL d’inscription.

- Si l’identité est Azure AD et que l’appareil a été préalablement inscrit auprès du serveur MDM Intune avec un profil de configuration spécifique affecté, le AD-Join Azure et l' [inscription automatique à MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se produiront au cours d’OOBE.
    - Également appelé le [déroulement AutoPilot](hololens2-autopilot.md) disponible dans [19041.1103 + builds](hololens-release-notes.md#windows-holographic-version-2004).


- si l’identité est MSA, utilisez **Paramètres** bouton Connecter d’accès à l’application ou à l'  ->  **école**  ->   .
    - Également appelé Flow AWA (ajouter un compte professionnel).
- si l’identité est utilisateur Local, utilisez **Paramètres** accès à l’application ou à l'  ->    ->  **inscription scolaire uniquement dans le lien de gestion des périphériques** .
    - Également appelé un workflow d’inscription MDM pur.

une fois que l’appareil est inscrit auprès de votre serveur MDM, l’application Paramètres reflète à présent que l’appareil est inscrit dans la gestion des appareils.

## <a name="auto-enrollment-in-mdm"></a>Inscription automatique dans GPM

si votre organisation dispose d’un [abonnement Azure Premium](https://azure.microsoft.com/overview/), utilise Azure Active Directory (Azure AD) et une solution de gestion des appareils mobiles qui accepte un jeton Azure AD pour l’authentification (actuellement pris en charge uniquement dans Microsoft Intune et la surveillance), votre administrateur informatique peut configurer Azure AD pour autoriser automatiquement l’inscription MDM une fois que l’utilisateur se connecte avec son compte Azure AD. [Découvrez comment configurer l’inscription Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire. Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.

Quand un appareil est Azure AD joint, il peut affecter les personnes qui ont considéré le propriétaire de l' [appareil](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>désinscrire HoloLens d’Intune

Selon la méthode d’inscription, l’annulation de l’inscription de votre appareil peut ne pas être disponible.

Si votre appareil a été inscrit avec un compte Azure AD ou AutoPilot, il ne peut pas être désinscrit d’Intune. si vous souhaitez annuler la jointure HoloLens de Azure AD ou le rejoindre à un locataire différent pour Azure AD, vous devez [réinitialiser/](hololens-recovery.md#reset-the-device) recommencer l’appareil.

Si votre appareil a été inscrit auprès d’un compte MSA qui a ajouté un compte professionnel ou à partir d’un compte local inscrit uniquement dans la gestion des appareils, vous pouvez annuler l’inscription de l’appareil. ouvrez le menu Démarrer, puis sélectionnez **Paramètres**  ->  bouton de déconnexion YourAccount d'**accès à l’application ou scolaire**  ->    ->   .

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>s’assurer que l’inscription MDM n’est pas bloquée pour les appareils Windows

pour que l’inscription aboutisse, vous devez vous assurer que vos appareils HoloLens peuvent s’inscrire. étant donné que HoloLens est considéré comme un appareil Windows, aucune restriction d’inscription ne peut bloquer votre déploiement. [Passez en revue cette liste de restrictions](/mem/intune/enrollment/enrollment-restrictions-set) et assurez-vous de pouvoir inscrire vos appareils.