---
title: Inscrire HoloLens dans GPM
description: Découvrez comment inscrire HoloLens dans la gestion des périphériques mobiles (MDM) pour faciliter la gestion de plusieurs appareils.
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
ms.openlocfilehash: 5613c69bda8bbf70722a050ac5ce4ebeab95d332
ms.sourcegitcommit: 771e53feefbcc6bce18577515ad7d3f6a7f33840
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399382"
---
# <a name="enroll-hololens-in-mdm"></a>Inscrire HoloLens dans GPM

Vous pouvez gérer plusieurs appareils Microsoft HoloLens simultanément à l’aide de solutions [telles que Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise. Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Conditions requises

 Votre organisation devra configurer la gestion des périphériques mobiles (MDM) pour gérer les appareils HoloLens. Votre fournisseur GPM peut être MicrosoftIntune ou un fournisseur tiers qui utilise les API GPM de Microsoft.
 
## <a name="different-ways-to-enroll"></a>Différentes façons de s’inscrire

Selon le type d’identité choisi lors de la OOBE ou de la post-connect, il existe différentes méthodes d’inscription. Pour en savoir plus sur chaque type d’identité sur HoloLens, visitez [cette page.](hololens-identity.md)

- Si l’identité est Azure AD, pendant la OOBE ou le bouton **Paramètres d’accès**à l’application  ->  **Travail ou Connexion**  ->  **scolaire.**
    - Pour Azure AD, l’inscription mdm automatique se produit uniquement si Azure AD a été configuré avec des URL d’inscription.
- Si l’identité est Azure AD et que l’appareil a été pré-inscrit auprès du serveur MDM Intune avec un profil de configuration spécifique qui lui est affecté, Azure AD-Join et l’inscription se produisent automatiquement pendant la phase OOBE.
    - Également appelé [flux Autopilot](hololens2-autopilot.md) disponible [dans les builds 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).
- Si l’identité est MSA, utilisez le bouton **Paramètres App**  ->  **Access Work ou School**  ->  **Connect.**
    - Également appelé flux Ajouter un compte de travail (AWA).
- Si l’identité est Utilisateur local, utilisez **Paramètres Application**Accès Travail ou Inscription  ->  ****  ->  **scolaire uniquement dans le lien gestion des** appareils.
    - Également appelé flux d’inscription MDM pur.

Une fois que l’appareil est inscrit auprès de votre serveur MDM, l’application Paramètres reflète désormais que l’appareil est inscrit dans la gestion des appareils.

## <a name="auto-enrollment-in-mdm"></a>Inscription automatique dans GPM

Si votre organisation utilise Azure Active Directory (Azure AD) et une solution MDM qui accepte un jeton Azure AD pour l’authentification (actuellement uniquement pris en charge dans Microsoft Intune et AirWatch), votre administrateur informatique peut configurer Azure AD pour autoriser automatiquement l’inscription MDM une fois que l’utilisateur s’est inscrit avec son compte Azure AD. [Découvrez comment configurer l’inscription Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire. Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.

Lorsqu’un appareil est joint à Azure AD, cela peut affecter les personnes considérées comme [propriétaires de l’appareil.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Désinscrire HoloLens d’Intune

Bien que HoloLens 2 soit un appareil Windows 10, il ne peut pas être simplement désinsaiscé d’Intune. Si vous souhaitez déjoindralisez HoloLens d’Azure AD ou rejoignez-le à un autre client Azure AD, vous devez réinitialiser/réinitialiser l’appareil. [](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device)