---
title: partager votre HoloLens avec plusieurs personnes
description: vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032911"
---
# <a name="share-your-hololens-with-multiple-people"></a>partager votre HoloLens avec plusieurs personnes

## <a name="overview"></a>Vue d’ensemble
les entreprises investissent souvent dans de nombreux appareils HoloLens partagés. la façon dont vous utilisez HoloLens est flexible dans le tableau, en fonction de vos besoins spécifiques. Voici un exemple d’expériences multi-utilisateurs : 

- les appareils qui sont facturés et qui ont Dynamics 365 Guides et permettent à vos employés d’ouvrir l’application Paramètres pour apporter des ajustements aux Wi-Fi nécessaires, mais la stratégie de visibilité des Paramètres de Page est activée pour limiter la quantité de pages disponibles dans l’application Paramètres.
- Appareils destinés à l’assistance à distance et à votre application métier qui sont loués à d’autres sociétés. Ces appareils ont des bornes qui incluent uniquement votre application et l’assistance à distance. WDAC est utilisé pour empêcher le lancement de l’application Paramètres et Microsoft Edge. La location est un pack de batterie USB-C qui permet de maintenir les appareils à pleine charge sur plusieurs équipes.
- Tous vos appareils sont configurés pour AutoPilot et téléchargent toutes les applications de votre entreprise. Vous avez configuré plusieurs profils kiosque, ciblant différents groupes de Azure AD. chaque utilisateur se connecte au HoloLens à l’aide de clés FIDO2 et se connecte à son propre compte Azure AD, et est présenté avec une expérience personnalisée.



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

1. Si un autre utilisateur utilise l’appareil, choisissez l’une des options suivantes :
   - Appuyez une fois sur le bouton d’alimentation pour accéder à la mise en veille, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage
   - HoloLens 2 utilisateurs peuvent sélectionner la vignette de l’utilisateur dans la menu Démarrer pour déconnecter l’utilisateur actuel.

1. Utilisez les informations d’identification de votre compte Azure AD pour vous connecter à l’appareil.  
    s’il s’agit de la première fois que vous utilisez l’appareil, vous devez [étalonner](hololens-calibration.md) HoloLens à vos yeux.

pour afficher la liste des utilisateurs d’appareils ou pour supprimer un utilisateur de l’appareil, accédez à **Paramètres**  >  **comptes**  >  **autres utilisateurs**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partager avec plusieurs personnes, toutes utilisant le même compte

plusieurs utilisateurs peuvent également partager un appareil HoloLens lors de l’utilisation d’un compte d’utilisateur unique.

**sur HoloLens 2**, lorsqu’un nouvel utilisateur met l’appareil en tête pour la première fois (tout en conservant le même compte connecté), l’appareil invite le nouvel utilisateur à étalonner et à personnaliser rapidement l’expérience d’affichage. L’appareil peut stocker les informations d’étalonnage afin que, à l’avenir, l’appareil puisse optimiser automatiquement la qualité et le confort de l’expérience d’affichage de chaque utilisateur. Les utilisateurs n’ont pas besoin d’étalonner à nouveau l’appareil.

**sur HoloLens (1er génération),** les utilisateurs qui partagent un compte doivent demander à être recalibrés dans l’application Paramètres.  En savoir plus sur l' [étalonnage](hololens-calibration.md).