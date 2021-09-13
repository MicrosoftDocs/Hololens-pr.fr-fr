---
title: Scénarios courants – HoloLens 2 sécurisés hors connexion
description: découvrez comment configurer un déploiement sécurisé hors connexion et un scénario de déploiement d’applications avec l’approvisionnement pour des appareils HoloLens.
keywords: HoloLens, gestion, hors connexion, sécurité hors connexion
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032444"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Scénarios courants – HoloLens 2 sécurisés hors connexion

## <a name="overview"></a>Vue d’ensemble

ce guide fournit des conseils pour l’application d’un exemple de Package de provisionnement qui verrouille une HoloLens 2 pour une utilisation dans des environnements sécurisés avec les restrictions suivantes :

-   Désactivez le Wi-Fi.
-   Désactivez BlueTooth.
-   Désactivez les microphones.
-   Empêche l’ajout ou la suppression de packages de provisionnement.
-   Aucun utilisateur ne peut activer les composants restreints ci-dessus.

[![Scénario de sécurité hors connexion. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Préparation

Windows 10 Configuration du PC
1. [téléchargez le dernier fichier de système d’exploitation HoloLens 2](https://aka.ms/hololens2download) directement sur un PC. 
   1. La prise en charge de cette configuration est incluse dans les versions 19041,1117 et ultérieures.
1. télécharger/installer l’outil de récupération avancée (ARC) [à partir du Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC
1. téléchargez et installez la dernière version de l’outil [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.
1. [Téléchargez le dossier OfflineSecureHL2_Sample avec les fichiers projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour générer le PPKG.
1. Préparez votre [application métier hors connexion pour le déploiement de PPKG](app-deploy-provisioning-package.md). 


## <a name="configure"></a>Configurer

Créer un package d’approvisionnement de configuration sécurisé

1. Lancez l’outil WCD sur votre PC.
1. Sélectionnez **fichier-> ouvrir un projet**.
  1. Accédez à l’emplacement du dossier OfflineSecureHL2_Sample enregistré précédemment, puis sélectionnez : OfflineSecureHL2_Sample.icdproj.xml
1. Le projet doit s’ouvrir et vous devez maintenant avoir une liste des personnalisations disponibles :

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du package de configuration ouvert dans WCD.](images/offline-secure-sample-wcd.png)

   Configurations définies dans ce package d’approvisionnement :
   
   |     Élément                                                |     Paramètre                       |     Description                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Comptes/utilisateurs                                    |     Nom d’utilisateur local & mot de passe    |     Pour ces périphériques hors connexion, un nom d’utilisateur et un mot de passe uniques devront être définis et partagés par tous les utilisateurs de l’appareil.          |
   |     première expérience/HoloLens/SkipCalibration       |     True                          |     Ignore l’étalonnage lors de l’installation initiale de l’appareil uniquement                                                                             |
   |     première expérience/HoloLens/SkipTraining          |     True                          |     Ignore la formation des appareils lors de la configuration initiale de l’appareil                                                                              |
   |     première expérience/HoloLens/WiFi                  |     True                          |     Ignore la configuration de Wi-Fi lors de la configuration initiale de l’appareil                                                                                 |
   |     Stratégies/connectivité/AllowBluetooth                |     Non                            |     Désactive Bluetooth                                                                                                             |
   |     Stratégies/expérience/AllowCortana                    |     Non                            |     désactive Cortana (pour éliminer les problèmes potentiels, car les microphones sont désactivés)                                          |
   |     Stratégies/MixedReality/MicrophoneDisabled            |     Oui                           |     Désactive le microphone                                                                                                            |
   |     Stratégies/confidentialité/LetAppsAccessLocation              |     Forcer le refus                    |     Empêche les applications d’essayer d’accéder aux données d’emplacement (afin d’éliminer les problèmes potentiels puisque le suivi d’emplacement est désactivé)    |
   |     Stratégies/confidentialité/LetAppsAccessMicrophone            |     Forcer le refus                    |     Empêche les applications d’essayer d’accéder aux micros (pour éliminer les problèmes potentiels puisque les microphones sont désactivés)           |
   |     Stratégies/sécurité/AllowAddProvisioningPackage       |     Non                            |     Empêche quiconque d’ajouter des packages de configuration qui peuvent tenter de remplacer les stratégies verrouillées.                         |
   |     Stratégies/sécurité/AllowRemoveProvisioningPackage    |     Non                            |     Empêche quiconque de supprimer ce package d’approvisionnement verrouillé.                                                           |
   |     Stratégies/système/AllowLocation                       |     Non                            |     Empêche l’appareil d’essayer d’effectuer le suivi des données d’emplacement.                                                                        |
   |     Stratégies/WiFi/AllowWiFi                             |     Non                            |     Désactive Wi-Fi                                                                                                                 |

1. sous Paramètres d’exécution, sélectionnez **comptes/utilisateurs/nom d’utilisateur : Holo/mot de passe**.

   Notez le mot de passe et réinitialisez-le si vous le souhaitez.

1. Accédez à UniversalAppInstall/UserContextApp et [configurez l’application métier](app-deploy-provisioning-package.md) que vous allez déployer sur ces appareils.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’emplacement d’ajout de votre application dans WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Une fois l’opération terminée, sélectionnez le bouton « Exporter » et suivez toutes les invites jusqu’à ce que votre package d’approvisionnement soit créé.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du bouton Exporter pour ce package dans WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Déployer

1. Connecter le HL2 à votre Windows 10 PC via un câble USB.
1. Lancez l’outil ARC et sélectionnez **HoloLens 2**

   ![Écran initial de la réinitialisation d’HoloLens 2.](images/ARC2.png)

1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages**.

   ![HoloLens 2 Écran d’informations sur l’ARC.](images/arc_device_info.png)

1. Accédez au fichier. FFU téléchargé précédemment, puis sélectionnez **ouvrir**.
1. Sur la page d’avertissement, sélectionnez **Continuer**.

   ![HoloLens 2 Écran d’avertissement de l’ARC.](images/arc_warning.png)

1. attendez que l’outil ARC termine l’installation du système d’exploitation HoloLens 2.
1. Une fois que l’appareil a effectué l’installation et le redémarrage, à partir de votre PC, accédez à l’Explorateur de fichiers et copiez le fichier PPKG précédemment enregistré sur le dossier de l’appareil.

   > [!div class="mx-imgBorder"]
   > ![Fichier PPKG sur le PC dans la fenêtre de l’Explorateur de fichiers.](images/offline-secure-file-explorer.png)

1. sur la HoloLens 2, appuyez sur la combinaison de boutons suivante pour exécuter le Package d’approvisionnement : appuyez sur le bouton de mise en **baisse du Volume** et sur le **bouton d’alimentation** en même temps.
1. Vous serez invité à appliquer le package d’approvisionnement, à sélectionner **confirmer** .
1. Une fois le package d’approvisionnement terminé, sélectionnez **OK**.
1. Vous devez ensuite être invité à vous connecter à l’appareil avec le compte local partagé et le mot de passe.

## <a name="maintain"></a>Maintenance

Avec cette configuration, il est recommandé de redémarrer le processus ci-dessus et de relancer l’appareil avec l’outil ARC et d’appliquer un nouveau PPKG pour effectuer les mises à jour du système d’exploitation et/ou des applications.
