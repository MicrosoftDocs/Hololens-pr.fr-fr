---
title: Scénarios courants – sécurité en mode hors connexion, HoloLens 2
description: Découvrez comment configurer un déploiement sécurisé hors connexion et un scénario de déploiement d’applications avec l’approvisionnement pour les appareils HoloLens.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308570"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="46446-104">Scénarios courants – sécurité en mode hors connexion, HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="46446-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="46446-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="46446-105">Overview</span></span>

<span data-ttu-id="46446-106">Ce guide fournit des conseils pour l’application d’un exemple de package de provisionnement qui verrouille un HoloLens 2 pour une utilisation dans des environnements sécurisés avec les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="46446-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="46446-107">Désactivez le Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="46446-107">Disable WiFi.</span></span>
-   <span data-ttu-id="46446-108">Désactivez BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="46446-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="46446-109">Désactivez les microphones.</span><span class="sxs-lookup"><span data-stu-id="46446-109">Disable Microphones.</span></span>
-   <span data-ttu-id="46446-110">Empêche l’ajout ou la suppression de packages de provisionnement.</span><span class="sxs-lookup"><span data-stu-id="46446-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="46446-111">Aucun utilisateur ne peut activer les composants restreints ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="46446-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="46446-112">Préparation</span><span class="sxs-lookup"><span data-stu-id="46446-112">Prepare</span></span>

<span data-ttu-id="46446-113">Installation du PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="46446-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="46446-114">[Téléchargez le dernier fichier de système d’exploitation HoloLens 2](https://aka.ms/hololens2download) directement sur un PC.</span><span class="sxs-lookup"><span data-stu-id="46446-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="46446-115">La prise en charge de cette configuration est incluse dans les versions 19041,1117 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="46446-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="46446-116">Télécharger/installer l’outil de récupération avancée (ARC) [à partir du Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC</span><span class="sxs-lookup"><span data-stu-id="46446-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="46446-117">Téléchargez/installez le dernier outil [Windows configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="46446-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="46446-118">[Téléchargez le dossier OfflineSecureHL2_Sample avec les fichiers projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour générer le PPKG.</span><span class="sxs-lookup"><span data-stu-id="46446-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="46446-119">Préparez votre [application métier hors connexion pour le déploiement de PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="46446-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="46446-120">Configurer</span><span class="sxs-lookup"><span data-stu-id="46446-120">Configure</span></span>

<span data-ttu-id="46446-121">Créer un package d’approvisionnement de configuration sécurisé</span><span class="sxs-lookup"><span data-stu-id="46446-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="46446-122">Lancez l’outil WCD sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="46446-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="46446-123">Sélectionnez **fichier-> ouvrir un projet**.</span><span class="sxs-lookup"><span data-stu-id="46446-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="46446-124">Accédez à l’emplacement du dossier OfflineSecureHL2_Sample enregistré précédemment, puis sélectionnez : OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="46446-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="46446-125">Le projet doit s’ouvrir et vous devez maintenant avoir une liste des personnalisations disponibles :</span><span class="sxs-lookup"><span data-stu-id="46446-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46446-126">![Capture d’écran du package de configuration ouvert dans WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="46446-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="46446-127">Configurations définies dans ce package d’approvisionnement :</span><span class="sxs-lookup"><span data-stu-id="46446-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="46446-128">Élément</span><span class="sxs-lookup"><span data-stu-id="46446-128">Item</span></span>                                                |     <span data-ttu-id="46446-129">Paramètre</span><span class="sxs-lookup"><span data-stu-id="46446-129">Setting</span></span>                       |     <span data-ttu-id="46446-130">Description</span><span class="sxs-lookup"><span data-stu-id="46446-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="46446-131">Comptes/utilisateurs</span><span class="sxs-lookup"><span data-stu-id="46446-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="46446-132">Nom d’utilisateur local & mot de passe</span><span class="sxs-lookup"><span data-stu-id="46446-132">Local User Name & Password</span></span>    |     <span data-ttu-id="46446-133">Pour ces périphériques hors connexion, un nom d’utilisateur et un mot de passe uniques devront être définis et partagés par tous les utilisateurs de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="46446-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="46446-134">Première expérience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="46446-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="46446-135">Vrai</span><span class="sxs-lookup"><span data-stu-id="46446-135">True</span></span>                          |     <span data-ttu-id="46446-136">Ignore l’étalonnage lors de l’installation initiale de l’appareil uniquement</span><span class="sxs-lookup"><span data-stu-id="46446-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="46446-137">Première expérience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="46446-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="46446-138">Vrai</span><span class="sxs-lookup"><span data-stu-id="46446-138">True</span></span>                          |     <span data-ttu-id="46446-139">Ignore la formation des appareils lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="46446-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="46446-140">Première expérience/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="46446-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="46446-141">Vrai</span><span class="sxs-lookup"><span data-stu-id="46446-141">True</span></span>                          |     <span data-ttu-id="46446-142">Ignore la configuration de Wi-Fi lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="46446-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="46446-143">Stratégies/connectivité/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="46446-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="46446-144">Non</span><span class="sxs-lookup"><span data-stu-id="46446-144">No</span></span>                            |     <span data-ttu-id="46446-145">Désactive Bluetooth</span><span class="sxs-lookup"><span data-stu-id="46446-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="46446-146">Stratégies/expérience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="46446-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="46446-147">Non</span><span class="sxs-lookup"><span data-stu-id="46446-147">No</span></span>                            |     <span data-ttu-id="46446-148">Désactive Cortana (pour éliminer les problèmes potentiels puisque les microphones sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="46446-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="46446-149">Stratégies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="46446-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="46446-150">Oui</span><span class="sxs-lookup"><span data-stu-id="46446-150">Yes</span></span>                           |     <span data-ttu-id="46446-151">Désactive le microphone</span><span class="sxs-lookup"><span data-stu-id="46446-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="46446-152">Stratégies/confidentialité/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="46446-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="46446-153">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="46446-153">Force deny</span></span>                    |     <span data-ttu-id="46446-154">Empêche les applications d’essayer d’accéder aux données d’emplacement (afin d’éliminer les problèmes potentiels puisque le suivi d’emplacement est désactivé)</span><span class="sxs-lookup"><span data-stu-id="46446-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="46446-155">Stratégies/confidentialité/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="46446-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="46446-156">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="46446-156">Force deny</span></span>                    |     <span data-ttu-id="46446-157">Empêche les applications d’essayer d’accéder aux micros (pour éliminer les problèmes potentiels puisque les microphones sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="46446-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="46446-158">Stratégies/sécurité/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="46446-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="46446-159">Non</span><span class="sxs-lookup"><span data-stu-id="46446-159">No</span></span>                            |     <span data-ttu-id="46446-160">Empêche quiconque d’ajouter des packages de configuration qui peuvent tenter de remplacer les stratégies verrouillées.</span><span class="sxs-lookup"><span data-stu-id="46446-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="46446-161">Stratégies/sécurité/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="46446-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="46446-162">Non</span><span class="sxs-lookup"><span data-stu-id="46446-162">No</span></span>                            |     <span data-ttu-id="46446-163">Empêche quiconque de supprimer ce package d’approvisionnement verrouillé.</span><span class="sxs-lookup"><span data-stu-id="46446-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="46446-164">Stratégies/système/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="46446-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="46446-165">Non</span><span class="sxs-lookup"><span data-stu-id="46446-165">No</span></span>                            |     <span data-ttu-id="46446-166">Empêche l’appareil d’essayer d’effectuer le suivi des données d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="46446-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="46446-167">Stratégies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="46446-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="46446-168">Non</span><span class="sxs-lookup"><span data-stu-id="46446-168">No</span></span>                            |     <span data-ttu-id="46446-169">Désactive Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="46446-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="46446-170">Sous paramètres d’exécution, sélectionnez **comptes/utilisateurs/nom d’utilisateur : Holo/mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="46446-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="46446-171">Notez le mot de passe et réinitialisez-le si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="46446-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="46446-172">Accédez à UniversalAppInstall/UserContextApp et [configurez l’application métier](app-deploy-provisioning-package.md) que vous allez déployer sur ces appareils.</span><span class="sxs-lookup"><span data-stu-id="46446-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46446-173">![Capture d’écran de l’emplacement d’ajout de votre application dans WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="46446-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="46446-174">Une fois l’opération terminée, sélectionnez le bouton « Exporter » et suivez toutes les invites jusqu’à ce que votre package d’approvisionnement soit créé.</span><span class="sxs-lookup"><span data-stu-id="46446-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46446-175">![Capture d’écran du bouton Exporter pour ce package dans WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="46446-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="46446-176">Déployer</span><span class="sxs-lookup"><span data-stu-id="46446-176">Deploy</span></span>

1. <span data-ttu-id="46446-177">Connectez le HL2 à votre PC Windows 10 via un câble USB.</span><span class="sxs-lookup"><span data-stu-id="46446-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="46446-178">Lancez l’outil ARC et sélectionnez **HoloLens 2** .</span><span class="sxs-lookup"><span data-stu-id="46446-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Écran de réinitialisation du nettoyage HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="46446-180">Dans l’écran suivant, sélectionnez **sélection manuelle des packages**.</span><span class="sxs-lookup"><span data-stu-id="46446-180">On the next screen select **Manual package selection**.</span></span>

   ![Écran d’informations d’ARC HoloLens 2](images/arc_device_info.png)

1. <span data-ttu-id="46446-182">Accédez au fichier. FFU téléchargé précédemment, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="46446-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="46446-183">Sur la page d’avertissement, sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="46446-183">At the Warning page select **Continue**.</span></span>

   ![Écran d’avertissement de l’ARC HoloLens 2](images/arc_warning.png)

1. <span data-ttu-id="46446-185">Attendez que l’outil ARC termine l’installation du système d’exploitation HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="46446-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="46446-186">Une fois que l’appareil a effectué l’installation et le redémarrage, à partir de votre PC, accédez à l’Explorateur de fichiers et copiez le fichier PPKG précédemment enregistré sur le dossier de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="46446-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="46446-187">![Fichier PPKG sur le PC dans la fenêtre de l’Explorateur de fichiers.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="46446-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="46446-188">Sur HoloLens 2, appuyez sur la combinaison de boutons suivante pour exécuter le package d’approvisionnement : Appuyez sur le bouton de mise en **baisse du volume** et sur le **bouton d’alimentation** en même temps.</span><span class="sxs-lookup"><span data-stu-id="46446-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="46446-189">Vous serez invité à appliquer le package d’approvisionnement, à sélectionner **confirmer** .</span><span class="sxs-lookup"><span data-stu-id="46446-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="46446-190">Une fois le package d’approvisionnement terminé, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="46446-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="46446-191">Vous devez ensuite être invité à vous connecter à l’appareil avec le compte local partagé et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="46446-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="46446-192">Maintenance</span><span class="sxs-lookup"><span data-stu-id="46446-192">Maintain</span></span>

<span data-ttu-id="46446-193">Avec cette configuration, il est recommandé de redémarrer le processus ci-dessus et de relancer l’appareil avec l’outil ARC et d’appliquer un nouveau PPKG pour effectuer les mises à jour du système d’exploitation et/ou des applications.</span><span class="sxs-lookup"><span data-stu-id="46446-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
