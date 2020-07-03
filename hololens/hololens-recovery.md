---
title: Redémarrer, réinitialiser ou récupérer HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Comment utiliser l’Assistant Récupération avancée pour flasher une image dans HoloLens 2.
keywords: procédure de réinitialisation, de réinitialisation, de récupération, de réinitialisation matérielle, de réinitialisation à chaud, de cycle de démarrage, HoloLens, arrêt, arc, compagnon de récupération avancée
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828058"
---
# Réinitialiser et récupérer pour HoloLens 2

## Chargement de l’appareil

Avant de commencer une procédure de dépannage, si possible, assurez-vous que votre appareil est débité d’au moins 20% et 40%.

Vérifiez que vous utilisez le chargeur et les câbles de type C USB fournis avec l’appareil HoloLens2. Si elles ne sont pas disponibles, assurez-vous que le chargeur disponible peut prendre en charge au moins 15W de l’alimentation.

> [!NOTE]
> Dans la mesure du possible, n’utilisez pas de PC pour débiter l’appareil sur USB, car cela permet d’obtenir un coût très faible.

Si l’appareil est correctement amorcé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier les frais de votre batterie.

1. Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.
2. Utilisation du voyant près du bouton de mise sous tension (pour 40%, vous devez voir au moins deux VOYANTs pleins).
3. Sur votre ordinateur hôte, ouvrez la fenêtre de l’Explorateur de fichiers et recherchez votre appareil HoloLens 2 sur le côté gauche sous «ce PC».
    
      a. Cliquez avec le bouton droit sur le nom de l’appareil, puis sélectionnez Propriétés. Une boîte de dialogue s’affiche, indiquant le niveau de batterie de votre appareil.

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

Si l’appareil ne peut pas être amorcé dans le menu de démarrage, notez les voyants et l’énumération sur l’ordinateur hôte et suivez le Guide de résolution des problèmes (https://docs.microsoft.com/hololens/hololens-troubleshooting). Si l’état de l’appareil n’est pas inclus dans l’un des États indiqués dans le Guide de résolution des problèmes, exécutez le **procédure de réinitialisation matérielle** sans rebrancher l’appareil sur votre PC hôte, mais Connectez-le à la place de l’alimentation. Patientez au moins une heure pour le chargement de l’appareil.

## Réinitialisez l’appareil

Dans certains cas, il est possible que le client soit obligé de réinitialiser manuellement l’appareil sans utiliser l’interface utilisateur SW. 

### Procédure standard
1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.

2. Appuyez de façon prolongée sur le bouton **Alimentation** pendant 15 secondes. Tous les voyants doivent être désactivés.

3. Patientez 2-3 secondes, puis appuyez sur le **bouton Alimentation**, les voyants situés près du bouton d’alimentation s’allument et l’appareil commence à démarrer. 

4. Connectez l’appareil à l’ordinateur hôte, ouvrez le gestionnaire d’appareils (pour Windows 10, appuyez sur la **touche «Windows»** puis sur la **touche «x»** et cliquez sur «Gestionnaire de périphériques») et vérifiez que l’appareil est correctement répertorié en tant que Microsoft HoloLens, comme illustré dans les images ci-dessous:

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

### Procédure de réinitialisation matérielle

Si la procédure de réinitialisation standard ne fonctionne pas, vous pouvez utiliser la procédure de réinitialisation matérielle.

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.

2. Maintenez enfoncée le bouton **baisser le volume + alimentation** pendant 15 secondes.

3. L’appareil redémarre automatiquement. 

4. Connectez l’appareil à l’ordinateur hôte, ouvrez le gestionnaire d’appareils (pour Windows 10, appuyez sur la touche **«Windows»** puis sur la **touche «x»** et cliquez sur «gestionnaire de périphériques») et vérifiez que l’appareil est correctement répertorié en tant que Microsoft HoloLens, comme illustré dans les images ci-dessous.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Nettoyer l’appareil

Dans certains cas, il peut être nécessaire de nettoyer l’appareil. Il existe deux méthodes pour refaire clignoter un appareil HoloLens2. Pour toutes les procédures de reflashage, vous devez [installer l’application Assistant Récupération avancée à partir du Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8). Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels sont supprimés, y compris la réinitialisation du TPM.

L’Assistant Récupération avancée est actuellement paramétré pour télécharger la build de la fonctionnalité version pour [Windows holographique 2004](hololens-release-notes.md#windows-holographic-version-2004), si vous voulez télécharger la dernière version de HoloLens 2 FFU pour flasher votre appareil via Advanced Recovery Companion, vous pouvez le télécharger à partir [ici](https://aka.ms/hololens2download). Ces informations sont mises à jour et correspondent à la dernière build généralement disponible. 

Avant de commencer la procédure de clignotement, assurez-vous que l’application est installée et en cours d’exécution sur votre PC Windows 10 et que vous êtes prêt à détecter l’appareil.

![Réinstallation rapide de HoloLens 2](images/ARC1.png)

### Procédure normale

1. Pendant l’exécution de l’appareil HoloLens, connectez-le à votre PC Windows 10 sur lequel vous avez précédemment lancé l’application compagnon de récupération avancée.

2. L’appareil est automatiquement détecté et l’interface utilisateur de l’application compagnon récupération avancée se met à jour comme suit:

![Réinstallation rapide de HoloLens 2](images/ARC2.png)

3. Sélectionnez l’appareil HoloLens2 dans l’interface utilisateur de l’application Assistant Récupération avancée et suivez les instructions pour terminer le clignotement.

### Procédure manuelle

Si l’appareil ne démarre pas correctement, il se peut que vous deviez placer l’appareil HoloLens 2 en mode de récupération.

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C. 

2. Appuyez de façon prolongée sur le bouton **Alimentation** pendant 15 secondes. Tous les voyants doivent s’éteindre. 

3. Tout en appuyant sur le **bouton monter le volume**, appuyez sur le **bouton d’alimentation** pour démarrer l’appareil. Patientez 15 secondes avant de relâcher le bouton monter le volume. À partir des 5 LED de l’appareil, seul le LED central s’illumine.

4. Connectez l’appareil à l’ordinateur hôte, ouvrez le gestionnaire d’appareils (pour Windows 10, appuyez sur la **touche «Windows»** puis sur la **touche «x»** et cliquez sur «Gestionnaire de périphériques») et vérifiez que l’appareil est correctement répertorié en tant que Microsoft HoloLens, comme illustré dans l’image ci-dessous.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. L’appareil est détecté automatiquement, et l’interface utilisateur de l’application compagnon de récupération avancée se met à jour comme suit:

![Réinstallation rapide de HoloLens 2](images/ARC2.png)

6. Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Assistant Récupération avancée et suivez les instructions pour terminer le clignotement.

## Téléchargement d’un ARC sans utiliser l’App Store

Si un environnement informatique empêche l’utilisation de l’application Windows Store ou limite l’accès au magasin, les administrateurs informatiques peuvent rendre cette application disponible via d’autres chemins de déploiement «hors connexion». 

- Ce processus peut également être utilisé pour d’autres applications, comme illustré à l’étape 2. Ce guide se concentre sur l’Assistant récupération avancé, mais mon compte est modifié pour les autres applications hors connexion.  

Ce chemin de déploiement peut être activé en procédant comme suit:
1.  Accédez au [site web Magasin pour les entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure AD.
1.  Accédez à **Gérer – Paramètres**, puis activez **Afficher les applications en mode hors connexion** sous **Expérience de commerce**, comme décrit dans https://businessstore.microsoft.com/manage/settings/shop 
1.  Accédez à **magasiner pour mon groupe** et recherchez l’application [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1.  Modifiez la zone **Type de licence** en mode hors connexion, puis cliquez sur **Gérer**.
1.  Sous Télécharger le package pour une utilisation en mode hors connexion, cliquez sur le deuxième bouton bleu **«Télécharger»**. Assurez-vous que l’extension de fichier est .appxbundle.
1.  À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur et installez. 
1.  L’administrateur informatique peut également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.
1.  Si l’ordinateur cible ne dispose d’aucune connectivité Internet, des étapes supplémentaires sont nécessaires: 
    1.  Sélectionnez la licence non codée, puis cliquez sur **«Générer une licence»** puis sous **«Cadre nécessaire»** cliquez sur **«Télécharger».** 
    1.  Les PC disposant d’un accès à Internet devront utiliser DISM pour appliquer le package avec la dépendance et la licence. Dans une invite de commandes administrateur, tapez:

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> Il se peut que le numéro de version dans cet exemple de code ne corresponde pas à la version actuellement disponible. Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple fourni. Assurez-vous d’apporter les modifications nécessaires.

> [!TIP]
> Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une FFU en mode hors connexion, il peut être utile de télécharger votre image clignotante sur disponible. Voici [l’image actuelle pour HoloLens 2](https://aka.ms/hololens2download). 

Autres ressources
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


