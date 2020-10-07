---
title: Enroll HoloLens in MDM
description: Enroll HoloLens in mobile device management (MDM) for easier management of multiple devices.
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
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102323"
---
# Enroll HoloLens in MDM

You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need. Voir [Gérer les appareils qui exécutent Windows Holographic avec Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), les [Fournisseurs de services de configuration (CSP) qui sont pris en charge dans Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) et les [stratégies prises en charge par Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La Gestion des périphériques mobiles (GPM), y compris le VPN, Bitlocker et les fonctionnalités du mode plein écran, ne sont disponibles que lorsque vous effectuez la [mise à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requirements

 Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices. Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.
 
## Different ways to enroll

Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment. To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).

- If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.
    - For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.
- If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.
    - Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).
- If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.
    - Also called Add Work Account (AWA) flow.
- If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.
    - Also called pure MDM enrollment flow.

Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.

## Auto-enrollment in MDM

Si votre organisation utilise Azure ActiveDirectory (Azure AD) et une solution GPM qui accepte un jeton AAD pour l’authentification (uniquement pris en charge pour l’instant dans MicrosoftIntune et AirWatch), votre administrateur informatique peut configurer Azure AD de manière à autoriser automatiquement l’inscription GPM une fois que l’utilisateur s’est connecté avec son compte Azure AD. [Découvrez comment configurer l’inscription Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Lorsque l’inscription automatique est activée, aucune inscription manuelle supplémentaire n’est nécessaire. When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.

When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).

## Unenroll HoloLens from Intune

To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
