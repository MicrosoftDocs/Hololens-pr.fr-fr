---
title: Redémarrer, réinitialiser ou récupérer HoloLens 2
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Utiliser l’Assistant Récupération avancée pour flasher une image dans HoloLens 2.
keywords: procédure de réinitialisation, de réinitialisation, de récupération, de réinitialisation matérielle, de réinitialisation à chaud, de cycle de démarrage, HoloLens, arrêt, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: e9aad32891bb093cbce18671b76549788b19afcb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428603"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Redémarrer, réinitialiser ou récupérer HoloLens 2

>[!IMPORTANT]
> Avant de commencer une procédure de dépannage, assurez-vous que la batterie de votre appareil est au minimum entre **20 et 40 %** , si possible. Les [témoins](hololens2-setup.md#lights-that-indicate-the-battery-level) situés sous le bouton d'alimentation permettent de vérifier rapidement la capacité de la batterie sans se connecter à l'appareil.

Utilisez le [chargeur et le câble de type USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) fournis avec l’HoloLens 2 pour charger votre appareil de manière optimale. Le chargeur fournit 18 W d’alimentation (9V à 2A). À l'aide du chargeur mural fourni, l'HoloLens 2 peut recharger complètement sa batterie en moins de 65 minutes lorsqu'il est en veille. Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur mis à disposition peut supporter au moins 15 W de puissance.

> [!NOTE]
> Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB car ce processus est lent.

Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie :

- Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.
- Regardez le voyant situé près du bouton d’alimentation (pour une charge de 40 %, vous devriez voir au moins deux voyants pleins).
    - Lorsque l’appareil est en charge, l’indicateur de batterie s’allume pour indiquer le niveau de charge actuel.  Le dernier voyant clignote lentement pour indiquer que l’appareil est en charge.
    - Lorsque votre HoloLens est allumé, le témoin de la batterie affiche le niveau de la batterie par cinq incréments.
    - Lorsqu’un seul des cinq voyants est allumé, le niveau de la batterie est inférieur à 20 %.
    - Si le niveau de la batterie est extrêmement faible et que vous essayez d’allumer l’appareil, un voyant clignote brièvement, puis s’éteint.
- Sur votre ordinateur hôte, ouvrez l’**Explorateurs de fichiers** et recherchez votre appareil HoloLens 2 sur le côté gauche sous **Ce PC**. Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**. Une boîte de dialogue indique le niveau de charge de la batterie.

   ![Un écran Propriétés HoloLens 2 affiche le niveau de charge de la batterie.](images/ResetRecovery2.png)

Si l’appareil ne parvient pas à démarrer à partir du menu Démarrer, observez l’apparence des voyants et l’énumération d’appareils sur l’ordinateur hôte. Suivez ensuite le [Guide de résolution des problèmes](hololens-troubleshooting.md). Si l’état de l’appareil ne correspond à aucun des états indiqués dans le Guide de résolution des problèmes, démarrez une [procédure de réinitialisation matérielle](hololens-recovery.md#hard-reset-procedure) avec l’appareil connecté à l’alimentation, et non à votre PC hôte. Patientez au moins une heure pour le chargement de l’appareil.

## <a name="reset-the-device"></a>Réinitialisation de l’appareil

Vous pouvez être amené à réinitialiser manuellement l’appareil sans utiliser l’interface utilisateur du logiciel.

### <a name="standard-procedure"></a>Procédure standard

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.

2. Appuyez de façon prolongée sur le bouton d’**alimentation** pendant 15 secondes. Tous les voyants doivent être désactivés.

3. Attendez 2 à 3 secondes, puis appuyez brièvement sur le bouton d’**alimentation**. Les voyants situés près du bouton d’alimentation s’allument, et l’appareil commence à démarrer.

4. Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques. (Pour Windows 10, appuyez sur la touche **Windows**, puis sur la touche **X** et sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que *Microsoft HoloLens* comme le montre l’image suivante :

   ![Gestionnaire des appareils HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procédure de réinitialisation matérielle

Si la procédure de réinitialisation standard ne fonctionne pas, utilisez la procédure de réinitialisation matérielle :

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.

1. Maintenez les boutons **baisser le volume** + **alimentation** enfoncés pendant 15 secondes. L’appareil redémarre automatiquement.

1. Connectez l’appareil à l’ordinateur hôte.

1. Ouvrez le Gestionnaire de périphériques (pour Windows 10, appuyez sur la touche **Windows**, puis sur la touche **X** et sélectionnez , puis sélectionnez **Gestionnaire de périphériques**). Assurez-vous que l’appareil est répertorié correctement en tant que *Microsoft HoloLens* comme le montre l’image suivante :

   ![Gestionnaire des appareils HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Réinitialiser l’appareil

Dans de rares cas, il peut être nécessaire de réinitialiser l’Hololens 2. Notez qu’une telle opération n’a pas d’incidence sur les problèmes suivants :

- [Uniformiser la couleur d’affichage](hololens2-display.md)
- Démarrage avec un son, mais pas de sortie d’affichage
- [Modèle LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems)
- [Surchauffe](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Blocages du système d'exploitation (différents des blocages d’application)

Il existe deux méthodes pour réinitialiser un appareil HoloLens 2. Pour ces deux méthodes, vous devez d’abord [installer Advanced Recovery Companion à partir du Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront supprimés, y compris les informations de réinitialisation du TPM.

Par défaut, Advanced Recovery Companion est configuré pour télécharger la version la plus récente des fonctionnalités. Pour plus d’informations sur les dernières fonctionnalités publiées, consultez [Notes de publication HoloLens 2](hololens-release-notes.md). Pour obtenir la dernière version du package de mise à jour FFU HoloLens 2 dans le but de réinitialiser votre appareil via Advanced Recovery Companion, téléchargez la dernière image mensuelle HoloLens 2 : [https://aka.ms/hololens2download](https://aka.ms/hololens2download). Cette version correspond à la build le plus récente disponible.

Avant de commencer la procédure de réinitialisation, assurez-vous que l’application est installée, en cours d’exécution sur votre PC Windows 10 et prête à détecter l’appareil. Assurez-vous également que votre HoloLens est chargé à un minimum de 40 %.

![Capture d’écran de la réinitialisation d’HoloLens 2.](images/ARC1.png)

### <a name="normal-procedure"></a>Procédure normale

1. Lorsque l’appareil HoloLens est en marche, connectez-le au PC Windows 10 sur lequel vous avez déjà ouvert l’application Advanced Recovery Companion.

   L’appareil est automatiquement détecté, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour :

   ![Écran initial de la réinitialisation d’HoloLens 2.](images/ARC2.png)

1. Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion et suivez les instructions pour effectuer la réinitialisation.

### <a name="manual-procedure"></a>Procédure manuelle

Vous devrez peut-être mettre l’appareil en mode de récupération si :

- HoloLens 2 ne démarre pas correctement
- Advanced Recovery Companion ne détecte pas l’appareil
- Vous ne connaissez plus le mot de passe ou le code confidentiel d’un appareil qui n’a qu’un seul utilisateur

1. Déconnectez l’appareil de l’alimentation ou de l’ordinateur hôte en débranchant le câble de type C.

2. Appuyez de façon prolongée sur le bouton d’**alimentation** pendant 15 secondes. Tous les voyants doivent s’éteindre.

3. Tout en appuyant sur le bouton pour **monter le volume**, appuyez sur le bouton d’**alimentation** pour démarrer l’appareil. Patientez 15 secondes avant de relâcher le bouton pour **monter le volume**. Parmi les cinq voyants lumineux, seul celui du milieu s’allume.

4. Connectez l’appareil à l’ordinateur hôte, puis ouvrez le Gestionnaire de périphériques. (Pour Windows 10, appuyez sur la touche **Windows**, puis sur la touche **X** et sélectionnez **Gestionnaire de périphériques**.) Assurez-vous que l’appareil est répertorié correctement en tant que Microsoft HoloLens comme le montre l’image suivante :

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   L’appareil est automatiquement détecté, et l’interface utilisateur de l’application Advanced Recovery Companion démarre le processus de mise à jour :

   ![Écran de réinitialisation HoloLens 2.](images/ARC2.png)

6. Sélectionnez l’appareil HoloLens 2 dans l’interface utilisateur de l’application Advanced Recovery Companion, puis suivez les instructions pour terminer la réinitialisation.

## <a name="troubleshoot-advanced-recovery-companion"></a>Résoudre les problèmes liés à l’application Advanced Recovery Companion

1. Assurez-vous que votre appareil est chargé à un minimum de 40 % avant de tenter une réinitialisation.

1. Vérifiez que votre appareil est déverrouillé.

1. Vérifiez que votre appareil est relié directement au PC hôte, et non à un concentrateur.

1. Si votre appareil n’apparaît pas dans la liste des appareils HoloLens/HoloLens Recovery sous Pilotes USB, vérifiez s’il figure sous :
    1. **Ports**, en tant qu’appareil Qualcomm HS-USB
    1. **Autres appareils**, en tant qu’appareil QUSB_BULK. Votre PC hôte ne dispose pas des pilotes nécessaires pour détecter votre HoloLens. Cliquez avec le bouton droit, sélectionnez Mettre à jour le pilote, puis recherchez les pilotes en ligne ou [activez les mises à jour facultatives dans vos paramètres Windows Update](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Une fois le pilote téléchargé, ARC doit pouvoir le détecter.

1. Si Advanced Recovery Companion ne détecte pas votre appareil, assurez-vous que vous pouvez vous connecter à celui-ci via l’Explorateur de fichiers sur votre ordinateur. Dans le cas contraire,

    1. Il est possible que votre appareil présente des stratégies USB qui désactivent cette connexion. Si tel est le cas, essayez le [mode de réinitialisation manuelle](hololens-recovery.md#manual-procedure).
    2. En l’absence de stratégies, essayez un autre câble USB.

1. Vérifiez que votre appareil n’affiche pas un [modèle LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).

## <a name="download-arc-without-using-the-app-store"></a>Télécharger Advanced Recovery Companion sans utiliser l’App Store

Si l’environnement informatique empêche l’utilisation de l’application Windows Store ou limite l’accès au Retail Store, l’administrateur informatique peut rendre cette application disponible via un chemin de déploiement « hors connexion ».

 >[!NOTE]
 > - Les administrateurs informatiques peuvent également distribuer cette application via System Center Configuration Manager (SCCM) ou Intune.
 > - Ce guide se concentre sur l’utilisation d’Advanced Recovery Companion, mais le processus peut également être utilisé pour d’autres applications « hors connexion ».

Pour activer le chemin de déploiement, procédez comme suit :

1. Accédez à [Microsoft Store pour Entreprises](https://businessstore.microsoft.com) et connectez-vous à l’aide d’une identité Azure Active Directory.

1. Accédez à **Gérer - Paramètres**. Activez **Afficher les applications hors connexion** sous **Expérience d’achat**.

1. Accédez à **Acheter pour mon groupe** et recherchez [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Remplacez le **type de licence** par **_hors connexion_ *_, puis sélectionnez _* Gérer**.

1. Sous **Télécharger le package pour une utilisation hors connexion**, sélectionnez le deuxième bouton bleu **Télécharger**. Assurez-vous que le fichier porte l’extension *.appxbundle*.

    - À ce stade, si le PC de bureau dispose d’un accès à Internet, double-cliquez sur le package pour installer l’application.

    - Si l’ordinateur de destination ne dispose pas d’une connexion Internet, procédez comme suit :
       1. Sélectionnez la licence non codée, puis **Générer une licence**.
       2. Sous **Frameworks requis**, sélectionnez **Télécharger**.
       3. Utilisez DISM pour appliquer le package avec la dépendance et la licence. À partir d’une invite de commandes administrateur, exécutez la commande suivante :

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Le numéro de version de cet exemple de code peut ne pas correspondre à la version actuellement disponible. Vous avez peut-être également choisi un autre emplacement de téléchargement que dans l’exemple. Apportez les modifications nécessaires à la commande.

> [!TIP]
> Lorsque vous envisagez d’utiliser Advanced Recovery Companion pour installer une mise à jour FFU en mode hors connexion, il peut s’avérer utile de télécharger votre image flash. [**Téléchargez l’image actuelle pour HoloLens 2**](https://aka.ms/hololens2download).

Autres ressources :

- [Distribuer des applications hors connexion](/microsoft-store/distribute-offline-apps) 
- [Options de ligne de commande de service de package d’application DISM (.appx ou .appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
