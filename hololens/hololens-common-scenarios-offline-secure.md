---
title: 'Scénarios courants: sécurité HoloLens 2 hors connexion'
description: Déploiement de l’application et du déploiement sécurisé hors ligne via la mise en service.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080484"
---
# Scénarios courants: sécurité HoloLens 2 hors connexion

## Présentation
Ce guide fournit des recommandations pour l’application d’un exemple de package de mise en service qui verrouille un HoloLens 2 pour une utilisation dans les environnements sécurisés avec les restrictions suivantes:
-   Désactiver le WiFi.
-   Désactiver BlueTooth.
-   Désactiver les microphones.
-   Empêche d’ajouter ou de supprimer des packages de mise en service.
-   Aucun utilisateur ne peut activer les composants restreints mentionnés ci-dessus.

## Préparation 
Configuration d’un PC Windows 10
1. [Télécharger le dernier fichier HoloLens 2 du système d’exploitation](https://aka.ms/hololens2download) directement sur un PC. 
   1. La prise en charge de cette configuration est incluse dans la version 19041,1117 et les versions ultérieures.
1. Télécharger et installer l’outil compagnon de récupération avancée (ARC) du [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC
1. Téléchargez et installez la dernière version de l’outil de [configuration de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.
1. [Téléchargez le dossier OfflineSecureHL2_Sample avec les fichiers de projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour générer le PPKG.
1. Préparez votre [application métier hors ligne pour le déploiement de PPKG](app-deploy-provisioning-package.md). 


## Configurer
Créer un package de mise en service de configuration sécurisée

1. Démarrez l’outil WCD sur votre PC.
1. Sélectionnez **fichier-> ouvrir Project**.
  1. Naviguez jusqu’à l’emplacement du dossier OfflineSecureHL2_Sample enregistré précédemment, puis sélectionnez: OfflineSecureHL2_Sample.icdproj.xml
1. Le projet doit être ouvert et vous devez maintenant disposer d’une liste de personnalisations disponibles: 

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du package de configuration ouvert dans le fichier WCD](images/offline-secure-sample-wcd.png)

Configurations définies dans ce package de mise en service:

|     Élément                                                |     Paramètre                       |     Description                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Comptes/utilisateurs                                    |     Nom d’utilisateur local & mot de passe    |     Pour ces périphériques hors connexion, un nom d’utilisateur et un mot de passe uniques doivent être définis et partagés par tous les utilisateurs de l’appareil.          |
|     Première expérimentation/HoloLens/SkipCalibration       |     Vrai                          |     Ignore le calibrage lors de l’installation de l’appareil initial uniquement                                                                             |
|     Première expérimentation/HoloLens/SkipTraining          |     Vrai                          |     Ignorer la formation sur les appareils lors de la configuration initiale de l’appareil                                                                              |
|     Première expérimentation/HoloLens/WiFi                  |     Vrai                          |     Ignore la configuration Wi-Fi lors de la configuration initiale de l’appareil                                                                                 |
|     Politiques/connectivité/AllowBluetooth                |     Non                            |     Désactive Bluetooth                                                                                                             |
|     Politiques/expertise/AllowCortana                    |     Non                            |     Désactive Cortana (pour éliminer les problèmes potentiels, puisque les micros sont désactivés)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     Oui                           |     Désactive le microphone                                                                                                            |
|     Politiques/confidentialité/LetAppsAccessLocation              |     Forcer le refus                    |     Empêche les applications d’accéder aux données d’emplacement (pour éliminer les problèmes potentiels puisque le suivi d’emplacement est désactivé)    |
|     Politiques/confidentialité/LetAppsAccessMicrophone            |     Forcer le refus                    |     Empêche les applications d’essayer d’accéder aux microphones (pour éliminer les problèmes potentiels puisque les micros sont désactivés)           |
|     Policies/Security/AllowAddProvisioningPackage       |     Non                            |     Empêche tout le monde d’ajouter des packages de mise en service qui peuvent tenter de remplacer les stratégies verrouillées.                         |
|     Policies/Security/AllowRemoveProvisioningPackage    |     Non                            |     Empêche tout le monde de supprimer ce package de mise en service verrouillé.                                                           |
|     Policies/System/AllowLocation                       |     Non                            |     Empêche l’appareil d’essayer de suivre les données de géolocalisation.                                                                        |
|     Politiques/WiFi/AllowWiFi                             |     Non                            |     Désactive le Wi-Fi                                                                                                                 |

4. Sous paramètres d’exécution, sélectionnez **comptes/utilisateurs/nom d’utilisateur: Holo/mot de passe** 
    - Notez le mot de passe, puis réinitialisez si vous le souhaitez.
5. Accédez à UniversalAppInstall/UserContextApp et [configurez l’application métier](app-deploy-provisioning-package.md) que vous déploierez sur ces appareils.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’emplacement d’ajout de votre application dans la boîte de niveau WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Lorsque vous avez terminé, sélectionnez le bouton «Exporter» et suivez les invites que vous avez apportées à la création du package de mise en service.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du bouton Exporter pour ce package dans le dossier WCD.](images/offline-secure-sample-wcd-export.png)


## Déployer
1. Branchez le HL2 sur votre PC Windows 10 à l’aide d’un câble USB.
1. Lancer l’outil ARC et sélectionner **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Dans l’écran suivant, sélectionnez **sélection manuelle du package**.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Accédez au fichier téléchargé. FFU, puis sélectionnez **ouvrir**.
1. Sur la page d’avertissement, sélectionnez **Continuer**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Attendez que l’outil ARC exécute l’installation de système d’exploitation HoloLens 2.
1. Une fois l’installation terminée, redémarrez votre PC, accédez à l’Explorateur de fichiers, puis copiez le fichier PPKG enregistré précédemment sur le dossier de l’appareil.

   > [!div class="mx-imgBorder"]
   > ![PPKG fichier sur PC dans la fenêtre de l’Explorateur de fichiers.](images/offline-secure-file-explorer.png)

1. Sur le HoloLens 2, appuyez sur la combinaison de boutons suivante pour exécuter le package de mise en service: Appuyez sur **baisser le volume** et sur le **bouton d’alimentation** en même temps.
1. Vous êtes invité à appliquer le package de mise à service, sélectionnez **confirmer**
1. Lorsque le package de mise en service est terminé, sélectionnez **OK**.
1. Vous devez alors être invité à vous connecter à l’appareil à l’aide du compte local et du mot de passe partagés.

## Mise à jour
Dans cette configuration, il est recommandé de redémarrer le processus ci-dessus et de refaire clignoter l’appareil à l’aide de l’outil ARC et d’appliquer un nouveau PPKG pour effectuer les mises à jour apportées au système d’exploitation et/ou aux applications. 

