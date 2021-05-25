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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397880"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="30635-104">Scénarios courants – sécurité en mode hors connexion, HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="30635-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="30635-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="30635-105">Overview</span></span>

<span data-ttu-id="30635-106">Ce guide fournit des conseils pour l’application d’un exemple de package de provisionnement qui verrouille un HoloLens 2 pour une utilisation dans des environnements sécurisés avec les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="30635-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="30635-107">Désactivez le Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="30635-107">Disable WiFi.</span></span>
-   <span data-ttu-id="30635-108">Désactivez BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="30635-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="30635-109">Désactivez les microphones.</span><span class="sxs-lookup"><span data-stu-id="30635-109">Disable Microphones.</span></span>
-   <span data-ttu-id="30635-110">Empêche l’ajout ou la suppression de packages de provisionnement.</span><span class="sxs-lookup"><span data-stu-id="30635-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="30635-111">Aucun utilisateur ne peut activer les composants restreints ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="30635-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="30635-112">[![Scénario ](./images/deployment-guides-revised-scenario-c-01.png) de sécurité hors connexion](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="30635-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="30635-113">Préparation</span><span class="sxs-lookup"><span data-stu-id="30635-113">Prepare</span></span>

<span data-ttu-id="30635-114">Installation du PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="30635-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="30635-115">[Téléchargez le dernier fichier de système d’exploitation HoloLens 2](https://aka.ms/hololens2download) directement sur un PC.</span><span class="sxs-lookup"><span data-stu-id="30635-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="30635-116">La prise en charge de cette configuration est incluse dans les versions 19041,1117 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="30635-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="30635-117">Télécharger/installer l’outil de récupération avancée (ARC) [à partir du Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC</span><span class="sxs-lookup"><span data-stu-id="30635-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="30635-118">Téléchargez/installez le dernier outil [Windows configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="30635-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="30635-119">[Téléchargez le dossier OfflineSecureHL2_Sample avec les fichiers projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour générer le PPKG.</span><span class="sxs-lookup"><span data-stu-id="30635-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="30635-120">Préparez votre [application métier hors connexion pour le déploiement de PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="30635-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="30635-121">Configurer</span><span class="sxs-lookup"><span data-stu-id="30635-121">Configure</span></span>

<span data-ttu-id="30635-122">Créer un package d’approvisionnement de configuration sécurisé</span><span class="sxs-lookup"><span data-stu-id="30635-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="30635-123">Lancez l’outil WCD sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="30635-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="30635-124">Sélectionnez **fichier-> ouvrir un projet**.</span><span class="sxs-lookup"><span data-stu-id="30635-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="30635-125">Accédez à l’emplacement du dossier OfflineSecureHL2_Sample enregistré précédemment, puis sélectionnez : OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="30635-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="30635-126">Le projet doit s’ouvrir et vous devez maintenant avoir une liste des personnalisations disponibles :</span><span class="sxs-lookup"><span data-stu-id="30635-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30635-127">![Capture d’écran du package de configuration ouvert dans WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="30635-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="30635-128">Configurations définies dans ce package d’approvisionnement :</span><span class="sxs-lookup"><span data-stu-id="30635-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="30635-129">Élément</span><span class="sxs-lookup"><span data-stu-id="30635-129">Item</span></span>                                                |     <span data-ttu-id="30635-130">Paramètre</span><span class="sxs-lookup"><span data-stu-id="30635-130">Setting</span></span>                       |     <span data-ttu-id="30635-131">Description</span><span class="sxs-lookup"><span data-stu-id="30635-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="30635-132">Comptes/utilisateurs</span><span class="sxs-lookup"><span data-stu-id="30635-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="30635-133">Nom d’utilisateur local & mot de passe</span><span class="sxs-lookup"><span data-stu-id="30635-133">Local User Name & Password</span></span>    |     <span data-ttu-id="30635-134">Pour ces périphériques hors connexion, un nom d’utilisateur et un mot de passe uniques devront être définis et partagés par tous les utilisateurs de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="30635-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="30635-135">Première expérience/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="30635-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="30635-136">Vrai</span><span class="sxs-lookup"><span data-stu-id="30635-136">True</span></span>                          |     <span data-ttu-id="30635-137">Ignore l’étalonnage lors de l’installation initiale de l’appareil uniquement</span><span class="sxs-lookup"><span data-stu-id="30635-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="30635-138">Première expérience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="30635-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="30635-139">Vrai</span><span class="sxs-lookup"><span data-stu-id="30635-139">True</span></span>                          |     <span data-ttu-id="30635-140">Ignore la formation des appareils lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="30635-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="30635-141">Première expérience/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="30635-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="30635-142">Vrai</span><span class="sxs-lookup"><span data-stu-id="30635-142">True</span></span>                          |     <span data-ttu-id="30635-143">Ignore la configuration de Wi-Fi lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="30635-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="30635-144">Stratégies/connectivité/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="30635-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="30635-145">No</span><span class="sxs-lookup"><span data-stu-id="30635-145">No</span></span>                            |     <span data-ttu-id="30635-146">Désactive Bluetooth</span><span class="sxs-lookup"><span data-stu-id="30635-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="30635-147">Stratégies/expérience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="30635-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="30635-148">No</span><span class="sxs-lookup"><span data-stu-id="30635-148">No</span></span>                            |     <span data-ttu-id="30635-149">Désactive Cortana (pour éliminer les problèmes potentiels puisque les microphones sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="30635-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="30635-150">Stratégies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="30635-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="30635-151">Yes</span><span class="sxs-lookup"><span data-stu-id="30635-151">Yes</span></span>                           |     <span data-ttu-id="30635-152">Désactive le microphone</span><span class="sxs-lookup"><span data-stu-id="30635-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="30635-153">Stratégies/confidentialité/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="30635-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="30635-154">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="30635-154">Force deny</span></span>                    |     <span data-ttu-id="30635-155">Empêche les applications d’essayer d’accéder aux données d’emplacement (afin d’éliminer les problèmes potentiels puisque le suivi d’emplacement est désactivé)</span><span class="sxs-lookup"><span data-stu-id="30635-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="30635-156">Stratégies/confidentialité/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="30635-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="30635-157">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="30635-157">Force deny</span></span>                    |     <span data-ttu-id="30635-158">Empêche les applications d’essayer d’accéder aux micros (pour éliminer les problèmes potentiels puisque les microphones sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="30635-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="30635-159">Stratégies/sécurité/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="30635-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="30635-160">No</span><span class="sxs-lookup"><span data-stu-id="30635-160">No</span></span>                            |     <span data-ttu-id="30635-161">Empêche quiconque d’ajouter des packages de configuration qui peuvent tenter de remplacer les stratégies verrouillées.</span><span class="sxs-lookup"><span data-stu-id="30635-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="30635-162">Stratégies/sécurité/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="30635-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="30635-163">No</span><span class="sxs-lookup"><span data-stu-id="30635-163">No</span></span>                            |     <span data-ttu-id="30635-164">Empêche quiconque de supprimer ce package d’approvisionnement verrouillé.</span><span class="sxs-lookup"><span data-stu-id="30635-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="30635-165">Stratégies/système/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="30635-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="30635-166">No</span><span class="sxs-lookup"><span data-stu-id="30635-166">No</span></span>                            |     <span data-ttu-id="30635-167">Empêche l’appareil d’essayer d’effectuer le suivi des données d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="30635-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="30635-168">Stratégies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="30635-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="30635-169">No</span><span class="sxs-lookup"><span data-stu-id="30635-169">No</span></span>                            |     <span data-ttu-id="30635-170">Désactive Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="30635-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="30635-171">Sous paramètres d’exécution, sélectionnez **comptes/utilisateurs/nom d’utilisateur : Holo/mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="30635-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="30635-172">Notez le mot de passe et réinitialisez-le si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="30635-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="30635-173">Accédez à UniversalAppInstall/UserContextApp et [configurez l’application métier](app-deploy-provisioning-package.md) que vous allez déployer sur ces appareils.</span><span class="sxs-lookup"><span data-stu-id="30635-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30635-174">![Capture d’écran de l’emplacement d’ajout de votre application dans WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="30635-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="30635-175">Une fois l’opération terminée, sélectionnez le bouton « Exporter » et suivez toutes les invites jusqu’à ce que votre package d’approvisionnement soit créé.</span><span class="sxs-lookup"><span data-stu-id="30635-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30635-176">![Capture d’écran du bouton Exporter pour ce package dans WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="30635-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="30635-177">Déployer</span><span class="sxs-lookup"><span data-stu-id="30635-177">Deploy</span></span>

1. <span data-ttu-id="30635-178">Connectez le HL2 à votre PC Windows 10 via un câble USB.</span><span class="sxs-lookup"><span data-stu-id="30635-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="30635-179">Lancez l’outil ARC et sélectionnez **HoloLens 2** .</span><span class="sxs-lookup"><span data-stu-id="30635-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Écran de réinitialisation du nettoyage HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="30635-181">Dans l’écran suivant, sélectionnez **sélection manuelle des packages**.</span><span class="sxs-lookup"><span data-stu-id="30635-181">On the next screen select **Manual package selection**.</span></span>

   ![Écran d’informations d’ARC HoloLens 2](images/arc_device_info.png)

1. <span data-ttu-id="30635-183">Accédez au fichier. FFU téléchargé précédemment, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="30635-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="30635-184">Sur la page d’avertissement, sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="30635-184">At the Warning page select **Continue**.</span></span>

   ![Écran d’avertissement de l’ARC HoloLens 2](images/arc_warning.png)

1. <span data-ttu-id="30635-186">Attendez que l’outil ARC termine l’installation du système d’exploitation HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="30635-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="30635-187">Une fois que l’appareil a effectué l’installation et le redémarrage, à partir de votre PC, accédez à l’Explorateur de fichiers et copiez le fichier PPKG précédemment enregistré sur le dossier de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="30635-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30635-188">![Fichier PPKG sur le PC dans la fenêtre de l’Explorateur de fichiers.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="30635-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="30635-189">Sur HoloLens 2, appuyez sur la combinaison de boutons suivante pour exécuter le package d’approvisionnement : Appuyez sur le bouton de mise en **baisse du volume** et sur le **bouton d’alimentation** en même temps.</span><span class="sxs-lookup"><span data-stu-id="30635-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="30635-190">Vous serez invité à appliquer le package d’approvisionnement, à sélectionner **confirmer** .</span><span class="sxs-lookup"><span data-stu-id="30635-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="30635-191">Une fois le package d’approvisionnement terminé, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="30635-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="30635-192">Vous devez ensuite être invité à vous connecter à l’appareil avec le compte local partagé et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="30635-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="30635-193">Maintenance</span><span class="sxs-lookup"><span data-stu-id="30635-193">Maintain</span></span>

<span data-ttu-id="30635-194">Avec cette configuration, il est recommandé de redémarrer le processus ci-dessus et de relancer l’appareil avec l’outil ARC et d’appliquer un nouveau PPKG pour effectuer les mises à jour du système d’exploitation et/ou des applications.</span><span class="sxs-lookup"><span data-stu-id="30635-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
