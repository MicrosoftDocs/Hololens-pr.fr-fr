---
title: Insider Preview pour MicrosoftHoloLens
description: Il est facile de commencer à utiliser les builds Insider et de fournir des commentaires utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828063"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans la dernière build Insider Preview pour HoloLens.  Il est facile de commencer et de fournir des commentaires utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.

## Commencer à recevoir les builds Insider

Sur un appareil HoloLens 2, accédez à **paramètres**  ->  **mise à jour &**  ->  **programme Windows Insider** Security et sélectionnez **commencer**. Liez le compte que vous avez utilisé pour vous inscrire au programme Windows Insider.

Ensuite, sélectionnez **développement actif de Windows**, choisissez si vous souhaitez recevoir des builds **rapides** ou **lentes** , puis passez en revue les termes du programme.

Sélectionnez **confirmer-> redémarrer maintenant** pour terminer. Après le redémarrage de votre appareil, accédez à **paramètres-> mettre à jour & sécurité-> Rechercher les mises à jour** pour obtenir la dernière version.

## Ne plus recevoir les builds Insider

Si vous ne voulez plus recevoir les builds Insider de Windows holographique, vous pouvez choisir de désactiver la version d’évaluation de votre appareil à [l’aide du](hololens-recovery.md) compagnon de récupération avancé pour récupérer votre appareil vers une version non-Insider de Windows holographique.

> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui se sont désinscrits de la version d’évaluation Insider Preview après la réinstallation manuelle d’une nouvelle version d’évaluation apparaîtraient sur un écran bleu. Par la suite, ils doivent récupérer manuellement leur appareil. Pour obtenir des informations complètes sur le [problème](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)ou non, consultez ce qui suit.

Pour vérifier que votre HoloLens exécute une build de production:

1. Accédez à **paramètres > système > à propos**de et recherchez le numéro de Build.
1. [Consultez les notes de publication pour les numéros de build de production.](hololens-release-notes.md)

Pour désactiver les builds Insider:

1. Sur un HoloLens exécutant une build de production, accédez à **paramètres > mettre à jour & sécurité > programme Windows Insider**, puis sélectionnez **arrêter les builds Insider**.
1. Suivez les instructions pour choisir votre appareil.



## Faire part de vos commentaires et signaler des problèmes

Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour formuler des commentaires et signaler des problèmes. Le hub de commentaires vous permet de vous assurer que toutes les informations de diagnostic nécessaires sont incluses pour faciliter le débogage et le résolution rapide du problème.  Des problèmes liés à la version chinois et japonais de HoloLens doivent être signalés de la même manière.

> [!NOTE]
> Assurez-vous d’accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).

## Remarque pour les développeurs

Vous êtes heureux et encouragé à essayer de développer vos applications à l’aide des builds Insider de HoloLens.  Consultez la [documentation pour développeurs HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds Insider d’HoloLens.  Vous pouvez utiliser les mêmes builds Unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.


## Notes de publication de Windows Insider

Dans le cadre de notre version d’évaluation de 2020, les [mises à jour d'](hololens-release-notes.md) sont désormais les avalible Veillez à [mettre à jour votre HoloLens](hololens-update-hololens.md) pour obtenir les dernières fonctionnalités.  

Cette page sera de nouveau mise à jour avec de nouvelles fonctionnalités à mesure que nous les publions vers les builds Microsoft Insider. 

### FFU télécharger et clignoter
Pour tester la version d’évaluation d’un FFU, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU.
1. Sur un PC
    1. Téléchargez FFU sur votre PC à partir de:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 
1. Sur HoloLens-version déverrouillée **Settings**: ouvrir la  >  **mise à jour des paramètres &**  >  **programme Windows Insider** Security puis s’inscrire, redémarrer l’appareil
1. Flash FFU-désormais, vous pouvez faire clignoter le FFU signé par ARC. 
