---
title: Redémarrer, réinitialiser ou récupérer HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915956"
---
# Redémarrer, réinitialiser ou récupérer HoloLens 2

## Recharger l’appareil

Avant de commencer une procédure de dépannage, assurez-vous que la batterie de votre appareil est au moins entre 20 et 40%, si possible. Utilisez le chargeur et les câbles USB de typeC fournis avec l’appareil HoloLens2. Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur disponible peut supporter au moins 15W de puissance.

> [!NOTE]
> Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB, ce serait trop lent.

Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie:

- Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.
- Regardez le voyant près du bouton d’alimentation (pour un débit de 40%, vous devriez voir au moins deux voyants pleins).
- Sur votre ordinateur hôte, ouvrez la fenêtre de l’Explorateur de fichiers et recherchez votre appareil HoloLens2 sur le côté gauche sous **CePC**. Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**. Une boîte de dialogue indique le niveau de charge de la batterie.

   ![Un écran Propriétés HoloLens2 affiche le niveau de charge de la batterie](images/ResetRecovery2.png)

Si l’appareil ne parvient pas à démarrer à partir du menu Démarrer, observez l’apparence des voyants et l’énumération d’appareils sur l’ordinateur hôte. Suivez ensuite le [Guide de résolution des problèmes](https://docs.microsoft.com/hololens/hololens-troubleshooting). Si l’état de l’appareil ne correspond à aucun des états indiqués dans le Guide de résolution des problèmes, démarrez une *procédure de réinitialisation matérielle* avec l’appareil connecté à l’alimentation, et non à votre PChôte. Patientez au moins une heure pour le chargement de l’appareil.

## Réinitialisez l’appareil

Dans certains cas, il se peut que vous deviez réinitialiser manuellement l’appareil sans utiliser l’interface utilisateurSW.

### Procédure standard
1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.

2. Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes. Tous les voyants doivent être désactivés.

3. Attendez 2-3secondes, puis appuyez de façon brève sur le bouton **d’alimentation**. Les voyants situés près du bouton d’alimentation s’allument, et l’appareil commence à démarrer.

4. Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques. (Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Procédure de réinitialisation matérielle

Si la procédure de réinitialisation standard ne fonctionne pas, utilisez la procédure de réinitialisation matérielle:

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.

2. Maintenez enfoncées les touches **baisser le volume** +  et **alimentation** pendant 15secondes. L’appareil redémarre automatiquement.

4. Connectez l’appareil à l’ordinateur hôte.
5. Ouvrez le gestionnaire de périphériques (pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**). Assurez-vous que l’appareil est répertorié correctement en tant que *MicrosoftHoloLens* comme illustré dans l’image suivante:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Nettoyer l’appareil

Dans de rares cas, il peut être nécessaire de nettoyer l’Hololens2. Il existe deux méthodes pour nettoyer un appareil HoloLens2. Pour chacune, vous devez commencer par installer [Advanced Recovery Companion à partir du WindowsStore](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront supprimés, y compris les informations de réinitialisation du TPM.

Par défaut, Advanced Recovery Companion est actuellement paramétré pour télécharger le build de production de fonctionnalités pour [Windows Holographique2004](hololens-release-notes.md#windows-holographic-version-2004). Si besoin, téléchargez la dernière version de la mise à jour FullFlashUpdate (FFU) d’ HoloLens2 pour réinitialiser votre appareil via Advanced Recovery Companion, [ici](https://aka.ms/hololens2download). Cette version est le build le plus récent disponible.

Avant de commencer la procédure de réinitialisation, assurez-vous que l’application est installée et en cours d’exécution sur votre PC Windows10 et qu’elle est prête à détecter l’appareil.

![Capture d’écran de réinitialisation d’HoloLens2](images/ARC1.png)

### Procédure normale

1. Lorsque l’appareil HoloLens est en marche, connectez-le au PC Windows10 sur lequel vous avez déjà ouvert l’application Advanced Recovery Companion.
 
   L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:

   ![Écran initial de réinitialisation d’HoloLens2](images/ARC2.png)

3. Sélectionnez l’appareil HoloLens2 dans l’interface utilisateur de l’application Advanced Recovery Companion et suivez les instructions pour effectuer la réinitialisation.

### Procédure manuelle

Si HoloLens2 ne démarre pas correctement, vous devrez peut-être placer l’appareil en mode de récupération:

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de typeC.

2. Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 15secondes. Tous les voyants doivent s’éteindre.

3. Tout en appuyant sur le bouton pour **augmenter le volume**, appuyez sur le bouton **d’alimentation** pour démarrer l’appareil. Patientez 15secondes avant de relâcher le bouton **d’augmentation du volume**. Parmi les cinq voyants lumineux, seul celui du milieu s’allume.

4. Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques. (Pour Windows10, appuyez sur la touche **Windows**, puis sur la touche**X**, puis sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que MicrosoftHoloLens comme illustré dans l’image suivante:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   L’appareil est détecté automatiquement, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour:

   ![Écran de réinitialisation d’HoloLens2](images/ARC2.png)

6. Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion, puis suivez les instructions pour terminer la réinitialisation.

## Télécharger ARC sans utiliser l’AppStore

Si l’environnement informatique empêche l’utilisation de l’application WindowsStore ou limite l’accès au Retail Store, l’administrateur informatique peut rendre cette application disponible via un chemin de déploiement «hors connexion».

 >[!NOTE] 
 > - Les administrateurs informatiques peuvent également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.
 > - Ce guide se concentre sur l’utilisation d’Advanced Recovery Companion, mais le processus peut également être utilisé pour d’autres applications «hors connexion».

Pour activer le chemin de déploiement, procédez comme suit:
1. Accédez à [Microsoft Store pour Entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure Active Directory.

1. Accédez à **Gérer – Paramètres**. Activez **Afficher les applications hors connexion** sous **Shopping Experience**. 
1. Accédez à **Acheter pour mon groupe** et recherchez [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1. Définissez le **type de licence** comme***Hors connexion***, puis sélectionnez **Gérer**.
1. Sous **Télécharger le package pour l’utilisation en mode hors connexion**, sélectionnez le deuxième bouton bleu **Télécharger**. Assurez-vous que l’extension de fichier est *.appxbundle*.

    - À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur le package pour installer l’application.


    - Si l’ordinateur de destination n’est pas connecté à Internet, procédez comme suit: 
       1. Sélectionnez la licence non codée, puis sélectionnez **Générer une licence**.
       2. Sous **Infrastructures requises**, sélectionnez **Télécharger**.
       3. Utilisez DISM pour appliquer le package avec la dépendance et la licence. À partir d’une invite de commandes administrateur, exécutez la commande suivante:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > Il se peut que le numéro de version dans cet exemple de code ne corresponde pas à la version actuellement disponible. Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple. Apportez les modifications nécessaires à la commande.

> [!TIP]
> Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une mise à jourFFU en mode hors connexion, il peut être utile de télécharger votre image flash. [**Télécharger l’image actuelle pour Hololens2**](https://aka.ms/hololens2download). 

Autres ressources
- [Distribuer des applications hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [Options de ligne de commande de service de package d’applicationDISM (.appx ou .appxbundle)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
