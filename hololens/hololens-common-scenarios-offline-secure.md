---
title: 'Scénarios courants: HoloLens 2 sécurisé hors connexion'
description: Découvrez comment configurer un déploiement sécurisé hors connexion et un scénario de déploiement d’application avec la mise en service pour les appareils HoloLens.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407578"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Scénarios courants: HoloLens 2 sécurisé hors connexion

## <a name="overview"></a>Vue d’ensemble

Ce guide fournit des conseils pour l’application d’un exemple de package d’approvisionnement qui verrouillera un HoloLens 2 pour une utilisation dans des environnements sécurisés avec les restrictions suivantes :

-   Désactivez le WiFi.
-   Désactivez BlueTooth.
-   Désactivez les microphones.
-   Empêche l’ajout ou la suppression de packages d’approvisionnement.
-   Aucun utilisateur ne peut activer l’un des composants restreints ci-dessus.

## <a name="prepare"></a>Préparation

Installation de PC Windows 10
1. [Téléchargez le dernier fichier de système d’exploitation HoloLens 2](https://aka.ms/hololens2download) directement sur un PC. 
   1. La prise en charge de cette configuration est incluse dans la build 19041.1117 et les builds supérieures.
1. Télécharger/installer l’outil Advanced Recovery Companion(ARC) à partir [du Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC
1. Téléchargez/installez le dernier outil Concepteur de [configuration Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.
1. [Téléchargez le OfflineSecureHL2_Sample avec les fichiers de projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour créer le PPKG.
1. Préparez votre [application métier hors connexion pour le déploiement PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configurer

Créer un package d’approvisionnement de configuration sécurisée

1. Lancez l’outil WCD sur votre PC.
1. Select **File -> Open project**.
  1. Accédez à l’emplacement du dossier de OfflineSecureHL2_Sample précédemment enregistré, puis sélectionnez : OfflineSecureHL2_Sample.icdproj.xml
1. Le projet doit s’ouvrir et vous devez maintenant avoir une liste des personnalisations disponibles :

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du package de configuration ouvert dans WCD](images/offline-secure-sample-wcd.png)

   Configurations définies dans ce package d’approvisionnement :
   
   |     Élément                                                |     Paramètre                       |     Description                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Comptes/Utilisateurs                                    |     Nom d’utilisateur local & mot de passe    |     Pour ces appareils hors connexion, un seul nom d’utilisateur et mot de passe doivent être définies et partagées par tous les utilisateurs de l’appareil.          |
   |     Première expérience / HoloLens / SkipCalibration       |     Vrai                          |     Ignore l’étalonnage lors de la configuration initiale de l’appareil uniquement                                                                             |
   |     Première expérience / HoloLens /SkipTraining          |     Vrai                          |     Ignore la formation sur les appareils lors de la configuration initiale de l’appareil                                                                              |
   |     Première expérience / HoloLens /WiFi                  |     Vrai                          |     Ignore la configuration Wi-Fi lors de la configuration initiale de l’appareil                                                                                 |
   |     Stratégies/Connectivité/AllowBluetooth                |     Non                            |     Désactive la Bluetooth                                                                                                             |
   |     Stratégies/Expérience/AllowCortana                    |     Non                            |     Désactive Cortana (pour éliminer les problèmes potentiels car les microphones sont désactivés)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Oui                           |     Désactive le microphone                                                                                                            |
   |     Stratégies/Confidentialité/LetAppsAccessLocation              |     Forcer le refus                    |     Empêche les applications d’essayer d’accéder aux données de géolocalisation (pour éliminer les problèmes potentiels depuis la désactivation du suivi de l’emplacement)    |
   |     Stratégies/Confidentialité/LetAppsAccessMicrophone            |     Forcer le refus                    |     Empêche les applications d’essayer d’accéder aux microphones (pour éliminer les problèmes potentiels car les microphones sont désactivés)           |
   |     Stratégies/Sécurité/AllowAddProvisioningPackage       |     Non                            |     Empêche toute personne d’ajouter des packages d’approvisionnement qui peuvent tenter de remplacer les stratégies verrouillées.                         |
   |     Stratégies/Sécurité/AllowRemoveProvisioningPackage    |     Non                            |     Empêche tout le monde de supprimer ce package d’approvisionnement verrouillé.                                                           |
   |     Stratégies/Système/AllowLocation                       |     Non                            |     Empêche l’appareil d’essayer de suivre les données d’emplacement.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     Non                            |     Désactive la Wi-Fi                                                                                                                 |

1. Sous Paramètres d’runtime, **sélectionnez Comptes/ Utilisateurs / Nom d’utilisateur : Holo / Mot de passe**.

   Notez le mot de passe et réinitialisez si vous le souhaitez.

1. Accédez à UniversalAppInstall/UserContextApp et configurez l’application [LOB](app-deploy-provisioning-package.md) que vous allez déployer sur ces appareils.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’endroit où ajouter votre application dans WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Une fois terminé, sélectionnez le bouton « Exporter » et suivez toutes les invites jusqu’à ce que votre package d’approvisionnement soit créé.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du bouton Exporter pour ce package dans WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Déployer

1. Connectez HL2 à votre PC Windows 10 via un câble USB.
1. Lancer l’outil ARC et sélectionner **HoloLens 2**

   ![Écran initial de réinitialisation d’HoloLens2](images/ARC2.png)

1. Dans l’écran suivant, sélectionnez **Sélection manuelle du package.**

   ![Écran d’informations sur l’ARC HoloLens 2](images/arc_device_info.png)

1. Accédez au fichier .ffu précédemment téléchargé, puis sélectionnez **Ouvrir.**
1. Dans la page Avertissement, sélectionnez **Continuer.**

   ![Écran d’avertissement holoLens 2 ARC](images/arc_warning.png)

1. Attendez que l’outil ARC termine l’installation du système d’exploitation HoloLens 2.
1. Une fois que l’appareil a terminé l’installation et a été sauvegardé, à partir de votre PC, accédez à l’Explorateur de fichiers et copiez le fichier PPKG précédemment enregistré dans le dossier de l’appareil.

   > [!div class="mx-imgBorder"]
   > ![Fichier PPKG sur PC dans la fenêtre Explorateur de fichiers.](images/offline-secure-file-explorer.png)

1. Sur HoloLens 2, appuyez sur la liste déroulante de **** boutons suivante pour exécuter le package d’approvisionnement : Appuyez sur **Le volume** et sur le bouton d’alimentation en même temps.
1. Vous serez invité à appliquer le package d’approvisionnement, sélectionnez **Confirmer**
1. Une fois le package d’approvisionnement terminé, sélectionnez **OK.**
1. Vous devez ensuite être invité à vous inscrire à l’appareil avec le compte local partagé et le mot de passe.

## <a name="maintain"></a>Maintenir

Avec cette configuration, il est recommandé de redémarrer le processus ci-dessus, de réessiller l’appareil avec l’outil ARC et d’appliquer un nouveau PPKG pour effectuer des mises à jour du système d’exploitation et/ou des applications.
