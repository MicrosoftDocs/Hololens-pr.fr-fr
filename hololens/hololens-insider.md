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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162954"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans la dernière build Insider Preview pour HoloLens. Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.

## Notes de publication de Windows Insider

### Installer des applications sur HoloLens 2 via le programme d’installation d’application
Nous vous enverrons la fonctionnalité du programme d’installation de l’application bientôt disponible suite à la mise à jour de Windows holographique, version 20H2. Nous **ajoutons une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications plus en continu** sur vos appareils HoloLens 2. Par défaut, la fonctionnalité est **activée pour les appareils non gérés**. Pour éviter toute interruption des entreprises, le programme d’installation d’applications ne sera **pas disponible pour les appareils gérés pour** le moment.  

Un appareil est considéré comme «géré» si l' **une** des conditions suivantes est vraie:
- GPM [inscrits](hololens-enroll-mdm.md)
- Configuré avec le [package de mise en service](hololens-provisioning.md)
- L' [identité](hololens-identity.md) de l’utilisateur est AAD

Vous pouvez maintenant installer des applications sans avoir besoin d’activer le mode développeur ou Device Portal.  Il vous suffit de télécharger (via câble USB ou via le système) l’ensemble d’applications AppX sur votre appareil et d’accéder à l’ensemble d’applications AppX de l’Explorateur de fichiers pour être invité à démarrer l’installation.  Vous pouvez également [lancer une installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  À l’instar des applications que vous installez à partir du Microsoft Store ou d’charger à l’aide de la fonctionnalité de déploiement d’applications métier de la gestion des applications métier, les applications doivent être signées numériquement à l’aide de l' [outil de signature](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour pouvoir déployer l’application.

**Instructions d’installation de l’application.**

1.  Vérifiez que votre appareil n’est pas considéré comme géré.
1.  Vérifiez que votre appareil HoloLens 2 est allumé et connecté à votre PC.
1.  Vérifiez que vous êtes connecté à l’appareil HoloLens 2
1.  Sur votre PC, accédez à votre application personnalisée, puis copiez le fichier VotreApplication. appxbundle sur yourdevicename\Internal Storage\Downloads.   Lorsque vous avez terminé de copier votre fichier, vous pouvez le déconnecter de votre appareil.
1.  Sur votre appareil HoloLens 2, ouvrez le menu Démarrer, sélectionnez toutes les applications, puis lancez l’application Explorateur de fichiers.
1.  Accédez au dossier téléchargements. Vous pouvez être amené à vous rendre dans le volet gauche de l’application sélectionnez ce dernier d’abord, puis accéder à téléchargements.
1.  Sélectionnez le fichier VotreApplication. appxbundle.
1.  Le programme d’installation de l’application démarre. Sélectionnez le bouton installer pour installer votre application.
L’application installée s’ouvre automatiquement lors de l’installation.

Vous trouverez des exemples d’applications sur [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) pour tester ce flux.

Apprenez-en davantage sur l' [installation complète des applications sur HoloLens 2 avec le programme d’installation de l’application](app-deploy-app-installer.md).  

![Installation des exemples MRTK via le programme d’installation de l’application](images/hololens-app-installer-picture.jpg)

## Commencer à recevoir les builds Insider

> [!NOTE]
> Si vous n’avez pas effectué de mise à jour récemment, redémarrez votre appareil pour mettre à jour l’État et obtenir la dernière version.
> - La commande vocale «redémarrage de l’appareil» fonctionne bien. 
> - Vous pouvez également choisir le bouton redémarrer dans paramètres/programme Windows Insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez rencontré et c’est en retour.

Sur un appareil HoloLens 2, accédez à **paramètres**  >  **mise à jour &**  >  **programme Windows Insider** Security et sélectionnez **commencer**. Liez le compte que vous avez utilisé pour vous inscrire au programme Windows Insider.

Windows Insider se déplace désormais vers les canaux. Le sonne **rapide** devient le **canal de développement**, la sonnerie **lente** devient le **canal bêta**et la sonnerie de la version d' **évaluation** devient le **canal de publication**. Voici à quoi ressemble le mappage:

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations, consultez [Présentation des canaux Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur les blogs Windows.

Ensuite, sélectionnez **développement actif de Windows**, choisissez si vous souhaitez recevoir les builds de **canaux de développement** ou de **canaux bêta** , puis passez en revue les termes du programme.

Sélectionnez **confirmer > redémarrer maintenant** pour terminer. Après le redémarrage de votre appareil, accédez à **paramètres > mettre à jour & sécurité > Rechercher les mises à jour** pour obtenir la dernière version.

## FFU télécharger et clignoter
Pour tester la version d’évaluation d’un FFU, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU.
1. Sur PC:

    1. Téléchargez FFU sur votre PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. Sur HoloLens-version de déverrouillage **Settings**: Ouvrez la  >  **mise à jour des paramètres &**  >  **programme Windows Insider** Security et inscrivez-vous, puis redémarrez l’appareil.

1. Flash FFU-désormais, vous pouvez faire clignoter le FFU signé par ARC.

## Faire part de vos commentaires et signaler des problèmes

Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour formuler des commentaires et signaler des problèmes. Le hub de commentaires vous permet de vous assurer que toutes les informations de diagnostic nécessaires sont incluses pour faciliter le débogage et le résolution rapide du problème.  Des problèmes liés à la version chinois et japonais de HoloLens doivent être signalés de la même manière.

> [!NOTE]
> Assurez-vous d’accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).

## Remarque pour les développeurs

Vous êtes heureux et encouragé à essayer de développer vos applications à l’aide des builds Insider de HoloLens.  Consultez la [documentation pour développeurs HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds Insider d’HoloLens.  Vous pouvez utiliser les mêmes builds Unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.

## Ne plus recevoir les builds Insider

Si vous ne voulez plus recevoir les builds Insider de Windows holographique, vous pouvez choisir de désactiver la version d’évaluation de votre appareil à [l’aide du](hololens-recovery.md) compagnon de récupération avancé pour récupérer votre appareil vers une version non-Insider de Windows holographique.

> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui se sont désinscrits de la version d’évaluation Insider Preview après la réinstallation manuelle d’une nouvelle version d’évaluation apparaîtraient sur un écran bleu. Par la suite, ils doivent récupérer manuellement leur appareil. Pour obtenir des informations complètes sur le [problème](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)ou non, consultez ce qui suit.

Pour vérifier que votre HoloLens exécute une build de production:

1. Accédez à **paramètres > système > à propos**de et recherchez le numéro de Build.

1. [Consultez les notes de publication pour les numéros de build de production](hololens-release-notes.md).

Pour désactiver les builds Insider:

1. Sur un HoloLens exécutant une build de production, accédez à **paramètres > mettre à jour & sécurité > programme Windows Insider**, puis sélectionnez **arrêter les builds Insider**.

1. Suivez les instructions pour choisir votre appareil.
