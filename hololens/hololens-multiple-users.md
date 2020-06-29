---
title: Partager votre HoloLens avec plusieurs personnes
description: Vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828419"
---
# Partager votre HoloLens avec plusieurs personnes

Le partage d’un HoloLens avec de nombreuses personnes ou de nombreux utilisateurs peut partager un ensemble d’appareils HoloLens.  Cet article décrit les différentes façons dont vous pouvez partager un appareil.

## Partager avec plusieurs personnes en utilisant leur propre compte

**Configuration requise**: l’appareil HoloLens doit exécuter Windows 10, version 1803 ou ultérieure.  HoloLens (1ère génération) doit également être [mis à niveau vers Windows holographique pour les entreprises](hololens-upgrade-enterprise.md).

Lorsqu’ils utilisent leur propre compte Azure Active Directory (Azure AD), plusieurs utilisateurs peuvent conserver leurs propres paramètres utilisateur et données utilisateur sur l’appareil.

Pour vous assurer que plusieurs personnes peuvent utiliser leur propre compte sur votre HoloLens, procédez comme suit pour les configurer:

1. Vérifiez que l’appareil exécute Windows 10, version 1803 ou ultérieure.
   > [!IMPORTANT]
   > Si vous utilisez un appareil HoloLens (1ère génération), [effectuez la mise à niveau de votre appareil vers Windows holographique pour les entreprises](hololens1-upgrade-enterprise.md).
1. Lorsque vous configurez l’appareil, sélectionnez **mon entreprise ou votre établissement scolaire propriétaire** , puis connectez-vous à l’aide d’un compte Azure ad.
1. Une fois l’installation terminée, assurez-vous que les paramètres du compte (comptes de**paramètres**  >  **Accounts**) incluent d' **autres utilisateurs**.

Pour utiliser HoloLens, chaque utilisateur doit suivre les étapes suivantes:

1. Si un autre utilisateur a utilisé l’appareil, effectuez l’une des opérations suivantes:
   - Appuyez une fois sur le bouton d’alimentation pour accéder à l’option Standby, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage.
   - Les utilisateurs HoloLens 2 peuvent sélectionner la vignette utilisateur dans le menu Démarrer pour se déconnecter de l’utilisateur actuel.

1. Utilisez vos informations d’identification de compte Azure AD pour vous connecter à l’appareil.  
    S’il s’agit de la première fois que vous utilisez l’appareil, vous devez [étalonner](hololens-calibration.md) HoloLens à vos propres yeux.

Pour afficher une liste des utilisateurs de l’appareil ou pour supprimer un utilisateur de l’appareil, accédez à **paramètres**de  >  **comptes**  >  **autres utilisateurs**.

## Partager avec plusieurs personnes en utilisant le même compte

Plusieurs utilisateurs peuvent également partager un appareil HoloLens lors de l’utilisation d’un seul compte d’utilisateur.

**Sur HoloLens 2**, lorsqu’un utilisateur place le périphérique sur son tête pour la première fois (tout en conservant la connexion de votre compte), l’appareil demande au nouvel utilisateur d’étalonner et de personnaliser rapidement l’interface d’affichage. L’appareil peut stocker les informations d’étalonnage de sorte à ce qu’à l’avenir, l’appareil puisse automatiquement optimiser la qualité et le confort de l’affichage de chaque utilisateur. Les utilisateurs n’ont pas besoin de calibrer l’appareil.

**Sur les utilisateurs HoloLens (1er génération),** le partage d’un compte nécessite une demande de calibrage dans l’application paramètres.  En savoir plus sur le [calibrage](hololens-calibration.md).
