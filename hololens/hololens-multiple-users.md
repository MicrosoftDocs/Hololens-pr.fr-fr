---
title: partager votre HoloLens avec plusieurs personnes
description: vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663076"
---
# <a name="share-your-hololens-with-multiple-people"></a>partager votre HoloLens avec plusieurs personnes

il est courant de partager un HoloLens avec de nombreuses personnes ou de nombreuses personnes partagent un ensemble d’appareils HoloLens.  Cet article décrit les différentes façons dont vous pouvez partager un appareil.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Partager avec plusieurs personnes, chacune utilisant son propre compte

**condition préalable**: l’appareil HoloLens doit exécuter Windows 10, version 1803 ou ultérieure.  HoloLens (1re génération) doit également être [mis à niveau vers Windows Holographic for Business](hololens-upgrade-enterprise.md).

lorsqu’ils utilisent leurs propres comptes de Azure Active Directory (Azure AD), plusieurs utilisateurs peuvent conserver leurs propres paramètres utilisateur et données utilisateur sur l’appareil.

pour vous assurer que plusieurs personnes peuvent utiliser leurs propres comptes sur votre HoloLens, procédez comme suit pour le configurer :

1. assurez-vous que l’appareil est en cours d’exécution Windows 10, version 1803 ou ultérieure.
   > [!IMPORTANT]
   > si vous utilisez un appareil HoloLens (1er génération), [mettez à niveau l’appareil vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quand vous configurez l’appareil, sélectionnez **mon entreprise ou école en est propriétaire** et connectez-vous à l’aide d’un compte Azure ad.
1. une fois l’installation terminée, assurez-vous que lesparamètres de compte (  >  **comptes** Paramètres) incluent d' **autres utilisateurs**.

pour utiliser HoloLens, chaque utilisateur suit les étapes suivantes :

1. Si un autre utilisateur a utilisé l’appareil, effectuez l’une des opérations suivantes :
   - Appuyez une fois sur le bouton d’alimentation pour accéder à la mise en veille, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage
   - HoloLens 2 utilisateurs peuvent sélectionner la vignette de l’utilisateur dans la menu Démarrer pour déconnecter l’utilisateur actuel.

1. Utilisez les informations d’identification de votre compte Azure AD pour vous connecter à l’appareil.  
    s’il s’agit de la première fois que vous utilisez l’appareil, vous devez [étalonner](hololens-calibration.md) HoloLens à vos yeux.

pour afficher la liste des utilisateurs d’appareils ou pour supprimer un utilisateur de l’appareil, accédez à **Paramètres**  >  **comptes**  >  **autres utilisateurs**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partager avec plusieurs personnes, toutes utilisant le même compte

plusieurs utilisateurs peuvent également partager un appareil HoloLens lors de l’utilisation d’un compte d’utilisateur unique.

**sur HoloLens 2**, lorsqu’un nouvel utilisateur met l’appareil en tête pour la première fois (tout en conservant le même compte connecté), l’appareil invite le nouvel utilisateur à étalonner et à personnaliser rapidement l’expérience d’affichage. L’appareil peut stocker les informations d’étalonnage afin que, à l’avenir, l’appareil puisse optimiser automatiquement la qualité et le confort de l’expérience d’affichage de chaque utilisateur. Les utilisateurs n’ont pas besoin d’étalonner à nouveau l’appareil.

**sur HoloLens (1er génération),** les utilisateurs qui partagent un compte doivent demander à être recalibrés dans l’application Paramètres.  En savoir plus sur l' [étalonnage](hololens-calibration.md).
