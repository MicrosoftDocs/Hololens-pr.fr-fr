---
title: Inscrire HoloLens dans GPM
description: Découvrez comment inscrire HoloLens dans la gestion des appareils mobiles (MDM) pour faciliter la gestion de plusieurs appareils.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308908"
---
# <a name="enroll-hololens-in-mdm"></a>Inscrire HoloLens dans GPM

Vous pouvez gérer plusieurs appareils Microsoft HoloLens simultanément à l’aide de solutions telles que [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Vous serez en mesure de gérer les paramètres, de sélectionner les applications à installer et de définir les configurations de sécurité adaptées aux besoins de votre entreprise. Consultez [gérer les appareils exécutant Windows holographique avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [fournisseurs de services de configuration (CSP) pris en charge dans Windows holographique](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)et les [stratégies prises en charge par Windows holographique for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La gestion des appareils mobiles (MDM), y compris les fonctionnalités VPN, BitLocker et en mode plein écran, est disponible uniquement lorsque vous [effectuez une mise à niveau vers Windows holographique for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Configuration requise

 Votre organisation doit configurer la gestion des appareils mobiles (MDM) pour gérer les appareils HoloLens. Votre fournisseur GPM peut être Microsoft Intune ou un fournisseur tiers qui utilise les API GPM de Microsoft.
 
## <a name="different-ways-to-enroll"></a>Différentes façons d’inscrire

Selon le type d' [identité](hololens-identity.md) choisi pendant l’OOBE ou la publication, il existe différentes méthodes d’inscription.

- Si l’identité est Azure ad, alors lors de l'   ->  utilisation du bouton d'**accès professionnel ou scolaire de l'** application paramètres  ->   .
    - Par Azure AD, l' [inscription automatique à MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se produit uniquement si Azure ad a été configuré avec des URL d’inscription.
     
- Si l’identité est Azure AD et que l’appareil a été préalablement inscrit auprès du serveur MDM Intune avec un profil de configuration spécifique affecté, le AD-Join Azure et l' [inscription automatique à MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se produiront au cours d’OOBE.
    - Également appelé le [déroulement AutoPilot](hololens2-autopilot.md) disponible dans [19041.1103 + builds](hololens-release-notes.md#windows-holographic-version-2004).
    

- Si l’identité est MSA, utilisez les paramètres accéder à l' **application** ou à l'  ->  **établissement scolaire**  ->   .
    - Également appelé Flow AWA (ajouter un compte professionnel).
- Si l’identité est utilisateur local, utilisez **paramètres** accéder à l’application ou à l'  ->    ->  **inscription scolaire uniquement dans le lien de gestion des périphériques** .
    - Également appelé un workflow d’inscription MDM pur.

Une fois que l’appareil est inscrit auprès de votre serveur MDM, l’application paramètres indique à présent que l’appareil est inscrit dans la gestion des appareils.

## <a name="auto-enrollment-in-mdm"></a>Inscription automatique dans GPM

Si votre organisation dispose d’un [abonnement Azure Premium](https://azure.microsoft.com/overview/), utilise Azure Active Directory (Azure AD) et une solution de gestion des appareils mobiles qui accepte un jeton Azure AD pour l’authentification (actuellement pris en charge uniquement dans Microsoft Intune et la surveillance), votre administrateur informatique peut configurer Azure AD pour autoriser automatiquement l’inscription MDM une fois que l’utilisateur se connecte avec son compte Azure ad. [Découvrez comment configurer l’inscription Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire. Lorsque l’utilisateur se connecte avec un compte Azure AD, l’appareil est inscrit dans GPM lors de sa première utilisation.

Quand un appareil est Azure AD joint, il peut affecter les personnes qui ont considéré le propriétaire de l' [appareil](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Désinscrire HoloLens d’Intune

Selon la méthode d’inscription, l’annulation de l’inscription de votre appareil peut ne pas être disponible.

Si votre appareil a été inscrit avec un compte Azure AD ou AutoPilot, il ne peut pas être désinscrit d’Intune. Si vous souhaitez annuler la jointure de la Azure AD ou la rejoindre à une autre Azure AD locataire, vous devez [Réinitialiser/](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) recommencer l’appareil.

Si votre appareil a été inscrit auprès d’un compte MSA qui a ajouté un compte professionnel ou à partir d’un compte local inscrit uniquement dans la gestion des appareils, vous pouvez annuler l’inscription de l’appareil. Ouvrez le menu Démarrer, puis sélectionnez **paramètres App**  ->  **Access Work ou School**  ->  *YourAccount*  ->  **Disconnect** Button.