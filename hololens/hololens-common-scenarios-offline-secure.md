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
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="9ff6b-104">Scénarios courants: HoloLens 2 sécurisé hors connexion</span><span class="sxs-lookup"><span data-stu-id="9ff6b-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="9ff6b-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="9ff6b-105">Overview</span></span>

<span data-ttu-id="9ff6b-106">Ce guide fournit des conseils pour l’application d’un exemple de package d’approvisionnement qui verrouillera un HoloLens 2 pour une utilisation dans des environnements sécurisés avec les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ff6b-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="9ff6b-107">Désactivez le WiFi.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-107">Disable WiFi.</span></span>
-   <span data-ttu-id="9ff6b-108">Désactivez BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="9ff6b-109">Désactivez les microphones.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-109">Disable Microphones.</span></span>
-   <span data-ttu-id="9ff6b-110">Empêche l’ajout ou la suppression de packages d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="9ff6b-111">Aucun utilisateur ne peut activer l’un des composants restreints ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="9ff6b-112">Préparation</span><span class="sxs-lookup"><span data-stu-id="9ff6b-112">Prepare</span></span>

<span data-ttu-id="9ff6b-113">Installation de PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ff6b-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="9ff6b-114">[Téléchargez le dernier fichier de système d’exploitation HoloLens 2](https://aka.ms/hololens2download) directement sur un PC.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="9ff6b-115">La prise en charge de cette configuration est incluse dans la build 19041.1117 et les builds supérieures.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="9ff6b-116">Télécharger/installer l’outil Advanced Recovery Companion(ARC) à partir [du Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC</span><span class="sxs-lookup"><span data-stu-id="9ff6b-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="9ff6b-117">Téléchargez/installez le dernier outil Concepteur de [configuration Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="9ff6b-118">[Téléchargez le OfflineSecureHL2_Sample avec les fichiers de projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour créer le PPKG.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="9ff6b-119">Préparez votre [application métier hors connexion pour le déploiement PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="9ff6b-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="9ff6b-120">Configurer</span><span class="sxs-lookup"><span data-stu-id="9ff6b-120">Configure</span></span>

<span data-ttu-id="9ff6b-121">Créer un package d’approvisionnement de configuration sécurisée</span><span class="sxs-lookup"><span data-stu-id="9ff6b-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="9ff6b-122">Lancez l’outil WCD sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="9ff6b-123">Select **File -> Open project**.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="9ff6b-124">Accédez à l’emplacement du dossier de OfflineSecureHL2_Sample précédemment enregistré, puis sélectionnez : OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="9ff6b-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="9ff6b-125">Le projet doit s’ouvrir et vous devez maintenant avoir une liste des personnalisations disponibles :</span><span class="sxs-lookup"><span data-stu-id="9ff6b-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du package de configuration ouvert dans WCD](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="9ff6b-127">Configurations définies dans ce package d’approvisionnement :</span><span class="sxs-lookup"><span data-stu-id="9ff6b-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="9ff6b-128">Élément</span><span class="sxs-lookup"><span data-stu-id="9ff6b-128">Item</span></span>                                                |     <span data-ttu-id="9ff6b-129">Paramètre</span><span class="sxs-lookup"><span data-stu-id="9ff6b-129">Setting</span></span>                       |     <span data-ttu-id="9ff6b-130">Description</span><span class="sxs-lookup"><span data-stu-id="9ff6b-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="9ff6b-131">Comptes/Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9ff6b-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="9ff6b-132">Nom d’utilisateur local & mot de passe</span><span class="sxs-lookup"><span data-stu-id="9ff6b-132">Local User Name & Password</span></span>    |     <span data-ttu-id="9ff6b-133">Pour ces appareils hors connexion, un seul nom d’utilisateur et mot de passe doivent être définies et partagées par tous les utilisateurs de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="9ff6b-134">Première expérience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="9ff6b-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="9ff6b-135">Vrai</span><span class="sxs-lookup"><span data-stu-id="9ff6b-135">True</span></span>                          |     <span data-ttu-id="9ff6b-136">Ignore l’étalonnage lors de la configuration initiale de l’appareil uniquement</span><span class="sxs-lookup"><span data-stu-id="9ff6b-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="9ff6b-137">Première expérience / HoloLens /SkipTraining</span><span class="sxs-lookup"><span data-stu-id="9ff6b-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="9ff6b-138">Vrai</span><span class="sxs-lookup"><span data-stu-id="9ff6b-138">True</span></span>                          |     <span data-ttu-id="9ff6b-139">Ignore la formation sur les appareils lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="9ff6b-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="9ff6b-140">Première expérience / HoloLens /WiFi</span><span class="sxs-lookup"><span data-stu-id="9ff6b-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="9ff6b-141">Vrai</span><span class="sxs-lookup"><span data-stu-id="9ff6b-141">True</span></span>                          |     <span data-ttu-id="9ff6b-142">Ignore la configuration Wi-Fi lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="9ff6b-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="9ff6b-143">Stratégies/Connectivité/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="9ff6b-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="9ff6b-144">Non</span><span class="sxs-lookup"><span data-stu-id="9ff6b-144">No</span></span>                            |     <span data-ttu-id="9ff6b-145">Désactive la Bluetooth</span><span class="sxs-lookup"><span data-stu-id="9ff6b-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="9ff6b-146">Stratégies/Expérience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="9ff6b-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="9ff6b-147">Non</span><span class="sxs-lookup"><span data-stu-id="9ff6b-147">No</span></span>                            |     <span data-ttu-id="9ff6b-148">Désactive Cortana (pour éliminer les problèmes potentiels car les microphones sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="9ff6b-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="9ff6b-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="9ff6b-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="9ff6b-150">Oui</span><span class="sxs-lookup"><span data-stu-id="9ff6b-150">Yes</span></span>                           |     <span data-ttu-id="9ff6b-151">Désactive le microphone</span><span class="sxs-lookup"><span data-stu-id="9ff6b-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="9ff6b-152">Stratégies/Confidentialité/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="9ff6b-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="9ff6b-153">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="9ff6b-153">Force deny</span></span>                    |     <span data-ttu-id="9ff6b-154">Empêche les applications d’essayer d’accéder aux données de géolocalisation (pour éliminer les problèmes potentiels depuis la désactivation du suivi de l’emplacement)</span><span class="sxs-lookup"><span data-stu-id="9ff6b-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="9ff6b-155">Stratégies/Confidentialité/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="9ff6b-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="9ff6b-156">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="9ff6b-156">Force deny</span></span>                    |     <span data-ttu-id="9ff6b-157">Empêche les applications d’essayer d’accéder aux microphones (pour éliminer les problèmes potentiels car les microphones sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="9ff6b-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="9ff6b-158">Stratégies/Sécurité/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="9ff6b-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="9ff6b-159">Non</span><span class="sxs-lookup"><span data-stu-id="9ff6b-159">No</span></span>                            |     <span data-ttu-id="9ff6b-160">Empêche toute personne d’ajouter des packages d’approvisionnement qui peuvent tenter de remplacer les stratégies verrouillées.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="9ff6b-161">Stratégies/Sécurité/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="9ff6b-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="9ff6b-162">Non</span><span class="sxs-lookup"><span data-stu-id="9ff6b-162">No</span></span>                            |     <span data-ttu-id="9ff6b-163">Empêche tout le monde de supprimer ce package d’approvisionnement verrouillé.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="9ff6b-164">Stratégies/Système/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="9ff6b-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="9ff6b-165">Non</span><span class="sxs-lookup"><span data-stu-id="9ff6b-165">No</span></span>                            |     <span data-ttu-id="9ff6b-166">Empêche l’appareil d’essayer de suivre les données d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="9ff6b-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="9ff6b-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="9ff6b-168">Non</span><span class="sxs-lookup"><span data-stu-id="9ff6b-168">No</span></span>                            |     <span data-ttu-id="9ff6b-169">Désactive la Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9ff6b-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="9ff6b-170">Sous Paramètres d’runtime, **sélectionnez Comptes/ Utilisateurs / Nom d’utilisateur : Holo / Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="9ff6b-171">Notez le mot de passe et réinitialisez si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="9ff6b-172">Accédez à UniversalAppInstall/UserContextApp et configurez l’application [LOB](app-deploy-provisioning-package.md) que vous allez déployer sur ces appareils.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’endroit où ajouter votre application dans WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="9ff6b-174">Une fois terminé, sélectionnez le bouton « Exporter » et suivez toutes les invites jusqu’à ce que votre package d’approvisionnement soit créé.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du bouton Exporter pour ce package dans WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="9ff6b-176">Déployer</span><span class="sxs-lookup"><span data-stu-id="9ff6b-176">Deploy</span></span>

1. <span data-ttu-id="9ff6b-177">Connectez HL2 à votre PC Windows 10 via un câble USB.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="9ff6b-178">Lancer l’outil ARC et sélectionner **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="9ff6b-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Écran initial de réinitialisation d’HoloLens2](images/ARC2.png)

1. <span data-ttu-id="9ff6b-180">Dans l’écran suivant, sélectionnez **Sélection manuelle du package.**</span><span class="sxs-lookup"><span data-stu-id="9ff6b-180">On the next screen select **Manual package selection**.</span></span>

   ![Écran d’informations sur l’ARC HoloLens 2](images/arc_device_info.png)

1. <span data-ttu-id="9ff6b-182">Accédez au fichier .ffu précédemment téléchargé, puis sélectionnez **Ouvrir.**</span><span class="sxs-lookup"><span data-stu-id="9ff6b-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="9ff6b-183">Dans la page Avertissement, sélectionnez **Continuer.**</span><span class="sxs-lookup"><span data-stu-id="9ff6b-183">At the Warning page select **Continue**.</span></span>

   ![Écran d’avertissement holoLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="9ff6b-185">Attendez que l’outil ARC termine l’installation du système d’exploitation HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="9ff6b-186">Une fois que l’appareil a terminé l’installation et a été sauvegardé, à partir de votre PC, accédez à l’Explorateur de fichiers et copiez le fichier PPKG précédemment enregistré dans le dossier de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Fichier PPKG sur PC dans la fenêtre Explorateur de fichiers.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="9ff6b-188">Sur HoloLens 2, appuyez sur la liste déroulante de \*\*\*\* boutons suivante pour exécuter le package d’approvisionnement : Appuyez sur **Le volume** et sur le bouton d’alimentation en même temps.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="9ff6b-189">Vous serez invité à appliquer le package d’approvisionnement, sélectionnez **Confirmer**</span><span class="sxs-lookup"><span data-stu-id="9ff6b-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="9ff6b-190">Une fois le package d’approvisionnement terminé, sélectionnez **OK.**</span><span class="sxs-lookup"><span data-stu-id="9ff6b-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="9ff6b-191">Vous devez ensuite être invité à vous inscrire à l’appareil avec le compte local partagé et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="9ff6b-192">Maintenir</span><span class="sxs-lookup"><span data-stu-id="9ff6b-192">Maintain</span></span>

<span data-ttu-id="9ff6b-193">Avec cette configuration, il est recommandé de redémarrer le processus ci-dessus, de réessiller l’appareil avec l’outil ARC et d’appliquer un nouveau PPKG pour effectuer des mises à jour du système d’exploitation et/ou des applications.</span><span class="sxs-lookup"><span data-stu-id="9ff6b-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
