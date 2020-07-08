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
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cd2b055679f5e1a9a529ad4947773e412211f9c4
ms.sourcegitcommit: 2b1518675b9962518e08b13c12b43b6d9827fe17
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10858008"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans la dernière build Insider Preview pour HoloLens.  Il est facile de commencer et de fournir des commentaires utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.

Windows Insider se déplace désormais vers les canaux. Le sonne **rapide** devient le **canal de développement**, la sonnerie **lente** devient le **canal bêta**et la sonnerie de la version d' **évaluation** devient le **canal de publication**. Voici à quoi ressemble le mappage:

![Canaux Windows Insider explication](images/WindowsInsiderChannels.png)

Pour plus d’informations: [entrée de blog Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## Commencer à recevoir les builds Insider

Sur un appareil HoloLens 2, accédez à **paramètres**  ->  **mise à jour &**  ->  **programme Windows Insider** Security et sélectionnez **commencer**. Liez le compte que vous avez utilisé pour vous inscrire au programme Windows Insider.

Ensuite, sélectionnez **développement actif de Windows**, choisissez si vous souhaitez recevoir les builds de **canaux de développement** ou de **canaux bêta** , puis passez en revue les termes du programme.

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

Si vous recherchez une fonctionnalité qui n’est pas visible dans la liste, assurez-vous que vous ne l’avez pas fait dans les builds non-Insider, assurez-vous de lire les [notes de publication](hololens-release-notes.md) pour voir toutes les fonctionnalités disponibles en général. Veillez à [mettre à jour votre HoloLens](hololens-update-hololens.md) pour obtenir les dernières fonctionnalités.  

Cette page sera de nouveau mise à jour avec de nouvelles fonctionnalités à mesure que nous les publions vers les builds Insider pour Windows. 

### Prise en charge de la position de l’oeil automatique

Dans HoloLens 2, les positions visuelles permettent un positionnement précis des hologrammes, une confort d’affichage confortable et une meilleure qualité d’affichage. Les positions visuelles sont calculées dans le résultat du suivi visuel. Toutefois, cela nécessite que chaque utilisateur passe par le calibrage du suivi visuel, même lorsque l’utilisation ne requiert pas d’entrée en regard.

La position de l' **oeil automatique (AEP)** permet à ces scénarios d’avoir une méthode d’interaction sans interaction pour calculer la position des yeux de l’utilisateur.  La position de l’oeil automatique commence automatiquement à fonctionner en arrière-plan à partir du moment où l’utilisateur place le périphérique. Si l’utilisateur ne dispose pas d’un étalonnage de suivi d’oeil antérieur, la position d’oeil automatique commencera à fournir à l’oeil de l’utilisateur le système d’affichage après un temps de traitement faible. Ce temps de traitement est généralement compris entre 20-60 secondes. Les données de l’utilisateur ne sont pas conservées sur l’appareil et, de ce fait, le processus est répété s’il est mis en place par l’utilisateur, ou si l’appareil est redémarré ou s’arrête de sortir du mode veille.  

Il existe certaines modifications de comportement système avec la fonctionnalité de position de l’oeil automatique quand un utilisateur non calibré le place sur l’appareil. Un utilisateur sans calibrage fait référence à une personne qui n’a pas encore parcouru le processus d’étalonnage du suivi visuel sur l’appareil.

|     Application active                           |     Comportement actuel                                   |     Comportement de Windows Insider Build 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     Application et interpréteur holographique non activé    |     Invite de calibration du suivi d’oeil s’affiche.    |     Aucune invite ne s’affiche.                                                                                |
|     Application en option                             |     Invite de calibration du suivi d’oeil s’affiche.    |     L’invite de calibration du suivi d’oeil s’affiche uniquement lorsque l’application accède à un flux d’oeil.     |

 Si l’utilisateur passe d’une application à l’autre qui accède aux données de pointage, l’invite s’affiche. Il n’y a aucun changement de flux d’expérimentation hors champ. 
 
Dans le cas d’expériences nécessitant des informations visuelles ou un positionnement très précis, nous vous recommandons d’effectuer un étalonnage du suivi visuel à partir de l’invite d’étalonnage du suivi d’oeil ou en lançant l’application paramètres à partir du menu Démarrer, puis en sélectionnant **système > calibration >** d’étalonnage > d’exécution.

**Problèmes connus**
1.  Nous travaillons à la résolution d’un problème dans lequel le processus de l’hôte du pilote Le processus hôte du pilote de suivi visuel doit procéder à une récupération automatique.

## FFU télécharger et clignoter
Pour tester la version d’évaluation d’un FFU, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU.
1. Sur un PC
    1. Téléchargez FFU sur votre PC à partir de:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 
1. Sur HoloLens-version déverrouillée **Settings**: ouvrir la  >  **mise à jour des paramètres &**  >  **programme Windows Insider** Security puis s’inscrire, redémarrer l’appareil
1. Flash FFU-désormais, vous pouvez faire clignoter le FFU signé par ARC. 
