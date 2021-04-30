---
title: Partager votre HoloLens avec plusieurs personnes
description: Vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes de Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308836"
---
# <a name="share-your-hololens-with-multiple-people"></a>Partager votre HoloLens avec plusieurs personnes

Il est courant de partager un HoloLens avec de nombreuses personnes ou de nombreuses personnes partagent un ensemble d’appareils HoloLens.  Cet article décrit les différentes façons dont vous pouvez partager un appareil.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Partager avec plusieurs personnes, chacune utilisant son propre compte

**Condition préalable**: l’appareil HoloLens doit exécuter Windows 10, version 1803 ou ultérieure.  HoloLens (1ère génération) doit également être [mis à niveau vers Windows holographique for Business](hololens-upgrade-enterprise.md).

Lorsqu’ils utilisent leurs propres comptes de Azure Active Directory (Azure AD), plusieurs utilisateurs peuvent conserver leurs propres paramètres utilisateur et données utilisateur sur l’appareil.

Pour vous assurer que plusieurs personnes peuvent utiliser leurs propres comptes sur votre HoloLens, procédez comme suit pour le configurer :

1. Assurez-vous que l’appareil exécute Windows 10, version 1803 ou ultérieure.
   > [!IMPORTANT]
   > Si vous utilisez un appareil HoloLens (1er génération), [Mettez-le à niveau vers Windows holographique pour entreprises](hololens1-upgrade-enterprise.md).
1. Quand vous configurez l’appareil, sélectionnez **mon entreprise ou école en est propriétaire** et connectez-vous à l’aide d’un compte Azure ad.
1. Une fois l’installation terminée, vérifiez que les paramètres de compte (comptes de **paramètres**  >  ) incluent d' **autres utilisateurs**.

Pour utiliser HoloLens, chaque utilisateur suit les étapes suivantes :

1. Si un autre utilisateur a utilisé l’appareil, effectuez l’une des opérations suivantes :
   - Appuyez une fois sur le bouton d’alimentation pour accéder à la mise en veille, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage
   - Les utilisateurs de HoloLens 2 peuvent sélectionner la vignette de l’utilisateur dans le menu Démarrer pour déconnecter l’utilisateur actuel.

1. Utilisez les informations d’identification de votre compte Azure AD pour vous connecter à l’appareil.  
    S’il s’agit de la première fois que vous utilisez l’appareil, vous devez [étalonner](hololens-calibration.md) HoloLens à vos propres yeux.

Pour afficher la liste des utilisateurs d’appareils ou pour supprimer un utilisateur de l’appareil, accédez à **paramètres**  >  **comptes**  >  **autres utilisateurs**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partager avec plusieurs personnes, toutes utilisant le même compte

Plusieurs utilisateurs peuvent également partager un appareil HoloLens en utilisant un seul compte d’utilisateur.

**Sur HoloLens 2**, lorsqu’un nouvel utilisateur met l’appareil en tête pour la première fois (tout en conservant le même compte connecté), l’appareil invite le nouvel utilisateur à étalonner et à personnaliser rapidement l’expérience d’affichage. L’appareil peut stocker les informations d’étalonnage afin que, à l’avenir, l’appareil puisse optimiser automatiquement la qualité et le confort de l’expérience d’affichage de chaque utilisateur. Les utilisateurs n’ont pas besoin d’étalonner à nouveau l’appareil.

**Sur HoloLens (1er génération),** les utilisateurs qui partagent un compte doivent demander à être recalibrés dans l’application paramètres.  En savoir plus sur l' [étalonnage](hololens-calibration.md).
