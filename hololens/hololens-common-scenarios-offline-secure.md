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
# <span data-ttu-id="9609b-104">Scénarios courants: sécurité HoloLens 2 hors connexion</span><span class="sxs-lookup"><span data-stu-id="9609b-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="9609b-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="9609b-105">Overview</span></span>
<span data-ttu-id="9609b-106">Ce guide fournit des recommandations pour l’application d’un exemple de package de mise en service qui verrouille un HoloLens 2 pour une utilisation dans les environnements sécurisés avec les restrictions suivantes:</span><span class="sxs-lookup"><span data-stu-id="9609b-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="9609b-107">Désactiver le WiFi.</span><span class="sxs-lookup"><span data-stu-id="9609b-107">Disable WiFi.</span></span>
-   <span data-ttu-id="9609b-108">Désactiver BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="9609b-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="9609b-109">Désactiver les microphones.</span><span class="sxs-lookup"><span data-stu-id="9609b-109">Disable Microphones.</span></span>
-   <span data-ttu-id="9609b-110">Empêche d’ajouter ou de supprimer des packages de mise en service.</span><span class="sxs-lookup"><span data-stu-id="9609b-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="9609b-111">Aucun utilisateur ne peut activer les composants restreints mentionnés ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="9609b-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="9609b-112">Préparation</span><span class="sxs-lookup"><span data-stu-id="9609b-112">Prepare</span></span> 
<span data-ttu-id="9609b-113">Configuration d’un PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="9609b-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="9609b-114">[Télécharger le dernier fichier HoloLens 2 du système d’exploitation](https://aka.ms/hololens2download) directement sur un PC.</span><span class="sxs-lookup"><span data-stu-id="9609b-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="9609b-115">La prise en charge de cette configuration est incluse dans la version 19041,1117 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="9609b-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="9609b-116">Télécharger et installer l’outil compagnon de récupération avancée (ARC) du [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) sur votre PC</span><span class="sxs-lookup"><span data-stu-id="9609b-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="9609b-117">Téléchargez et installez la dernière version de l’outil de [configuration de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) à partir du Microsoft Store sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="9609b-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="9609b-118">[Téléchargez le dossier OfflineSecureHL2_Sample avec les fichiers de projet](https://aka.ms/HoloLensDocs-SecureOfflineSample) pour générer le PPKG.</span><span class="sxs-lookup"><span data-stu-id="9609b-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="9609b-119">Préparez votre [application métier hors ligne pour le déploiement de PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="9609b-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="9609b-120">Configurer</span><span class="sxs-lookup"><span data-stu-id="9609b-120">Configure</span></span>
<span data-ttu-id="9609b-121">Créer un package de mise en service de configuration sécurisée</span><span class="sxs-lookup"><span data-stu-id="9609b-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="9609b-122">Démarrez l’outil WCD sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="9609b-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="9609b-123">Sélectionnez **fichier-> ouvrir Project**.</span><span class="sxs-lookup"><span data-stu-id="9609b-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="9609b-124">Naviguez jusqu’à l’emplacement du dossier OfflineSecureHL2_Sample enregistré précédemment, puis sélectionnez: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="9609b-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="9609b-125">Le projet doit être ouvert et vous devez maintenant disposer d’une liste de personnalisations disponibles:</span><span class="sxs-lookup"><span data-stu-id="9609b-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du package de configuration ouvert dans le fichier WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="9609b-127">Configurations définies dans ce package de mise en service:</span><span class="sxs-lookup"><span data-stu-id="9609b-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="9609b-128">Élément</span><span class="sxs-lookup"><span data-stu-id="9609b-128">Item</span></span>                                                |     <span data-ttu-id="9609b-129">Paramètre</span><span class="sxs-lookup"><span data-stu-id="9609b-129">Setting</span></span>                       |     <span data-ttu-id="9609b-130">Description</span><span class="sxs-lookup"><span data-stu-id="9609b-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="9609b-131">Comptes/utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9609b-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="9609b-132">Nom d’utilisateur local & mot de passe</span><span class="sxs-lookup"><span data-stu-id="9609b-132">Local User Name & Password</span></span>    |     <span data-ttu-id="9609b-133">Pour ces périphériques hors connexion, un nom d’utilisateur et un mot de passe uniques doivent être définis et partagés par tous les utilisateurs de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9609b-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="9609b-134">Première expérimentation/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="9609b-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="9609b-135">Vrai</span><span class="sxs-lookup"><span data-stu-id="9609b-135">True</span></span>                          |     <span data-ttu-id="9609b-136">Ignore le calibrage lors de l’installation de l’appareil initial uniquement</span><span class="sxs-lookup"><span data-stu-id="9609b-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="9609b-137">Première expérimentation/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="9609b-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="9609b-138">Vrai</span><span class="sxs-lookup"><span data-stu-id="9609b-138">True</span></span>                          |     <span data-ttu-id="9609b-139">Ignorer la formation sur les appareils lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="9609b-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="9609b-140">Première expérimentation/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="9609b-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="9609b-141">Vrai</span><span class="sxs-lookup"><span data-stu-id="9609b-141">True</span></span>                          |     <span data-ttu-id="9609b-142">Ignore la configuration Wi-Fi lors de la configuration initiale de l’appareil</span><span class="sxs-lookup"><span data-stu-id="9609b-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="9609b-143">Politiques/connectivité/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="9609b-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="9609b-144">Non</span><span class="sxs-lookup"><span data-stu-id="9609b-144">No</span></span>                            |     <span data-ttu-id="9609b-145">Désactive Bluetooth</span><span class="sxs-lookup"><span data-stu-id="9609b-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="9609b-146">Politiques/expertise/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="9609b-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="9609b-147">Non</span><span class="sxs-lookup"><span data-stu-id="9609b-147">No</span></span>                            |     <span data-ttu-id="9609b-148">Désactive Cortana (pour éliminer les problèmes potentiels, puisque les micros sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="9609b-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="9609b-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="9609b-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="9609b-150">Oui</span><span class="sxs-lookup"><span data-stu-id="9609b-150">Yes</span></span>                           |     <span data-ttu-id="9609b-151">Désactive le microphone</span><span class="sxs-lookup"><span data-stu-id="9609b-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="9609b-152">Politiques/confidentialité/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="9609b-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="9609b-153">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="9609b-153">Force deny</span></span>                    |     <span data-ttu-id="9609b-154">Empêche les applications d’accéder aux données d’emplacement (pour éliminer les problèmes potentiels puisque le suivi d’emplacement est désactivé)</span><span class="sxs-lookup"><span data-stu-id="9609b-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="9609b-155">Politiques/confidentialité/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="9609b-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="9609b-156">Forcer le refus</span><span class="sxs-lookup"><span data-stu-id="9609b-156">Force deny</span></span>                    |     <span data-ttu-id="9609b-157">Empêche les applications d’essayer d’accéder aux microphones (pour éliminer les problèmes potentiels puisque les micros sont désactivés)</span><span class="sxs-lookup"><span data-stu-id="9609b-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="9609b-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="9609b-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="9609b-159">Non</span><span class="sxs-lookup"><span data-stu-id="9609b-159">No</span></span>                            |     <span data-ttu-id="9609b-160">Empêche tout le monde d’ajouter des packages de mise en service qui peuvent tenter de remplacer les stratégies verrouillées.</span><span class="sxs-lookup"><span data-stu-id="9609b-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="9609b-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="9609b-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="9609b-162">Non</span><span class="sxs-lookup"><span data-stu-id="9609b-162">No</span></span>                            |     <span data-ttu-id="9609b-163">Empêche tout le monde de supprimer ce package de mise en service verrouillé.</span><span class="sxs-lookup"><span data-stu-id="9609b-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="9609b-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="9609b-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="9609b-165">Non</span><span class="sxs-lookup"><span data-stu-id="9609b-165">No</span></span>                            |     <span data-ttu-id="9609b-166">Empêche l’appareil d’essayer de suivre les données de géolocalisation.</span><span class="sxs-lookup"><span data-stu-id="9609b-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="9609b-167">Politiques/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="9609b-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="9609b-168">Non</span><span class="sxs-lookup"><span data-stu-id="9609b-168">No</span></span>                            |     <span data-ttu-id="9609b-169">Désactive le Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9609b-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="9609b-170">Sous paramètres d’exécution, sélectionnez **comptes/utilisateurs/nom d’utilisateur: Holo/mot de passe**</span><span class="sxs-lookup"><span data-stu-id="9609b-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="9609b-171">Notez le mot de passe, puis réinitialisez si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9609b-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="9609b-172">Accédez à UniversalAppInstall/UserContextApp et [configurez l’application métier](app-deploy-provisioning-package.md) que vous déploierez sur ces appareils.</span><span class="sxs-lookup"><span data-stu-id="9609b-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’emplacement d’ajout de votre application dans la boîte de niveau WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="9609b-174">Lorsque vous avez terminé, sélectionnez le bouton «Exporter» et suivez les invites que vous avez apportées à la création du package de mise en service.</span><span class="sxs-lookup"><span data-stu-id="9609b-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du bouton Exporter pour ce package dans le dossier WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="9609b-176">Déployer</span><span class="sxs-lookup"><span data-stu-id="9609b-176">Deploy</span></span>
1. <span data-ttu-id="9609b-177">Branchez le HL2 sur votre PC Windows 10 à l’aide d’un câble USB.</span><span class="sxs-lookup"><span data-stu-id="9609b-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="9609b-178">Lancer l’outil ARC et sélectionner **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="9609b-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="9609b-179">Dans l’écran suivant, sélectionnez **sélection manuelle du package**.</span><span class="sxs-lookup"><span data-stu-id="9609b-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="9609b-180">Accédez au fichier téléchargé. FFU, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="9609b-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="9609b-181">Sur la page d’avertissement, sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="9609b-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="9609b-182">Attendez que l’outil ARC exécute l’installation de système d’exploitation HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9609b-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="9609b-183">Une fois l’installation terminée, redémarrez votre PC, accédez à l’Explorateur de fichiers, puis copiez le fichier PPKG enregistré précédemment sur le dossier de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9609b-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![PPKG fichier sur PC dans la fenêtre de l’Explorateur de fichiers.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="9609b-185">Sur le HoloLens 2, appuyez sur la combinaison de boutons suivante pour exécuter le package de mise en service: Appuyez sur **baisser le volume** et sur le **bouton d’alimentation** en même temps.</span><span class="sxs-lookup"><span data-stu-id="9609b-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="9609b-186">Vous êtes invité à appliquer le package de mise à service, sélectionnez **confirmer**</span><span class="sxs-lookup"><span data-stu-id="9609b-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="9609b-187">Lorsque le package de mise en service est terminé, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="9609b-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="9609b-188">Vous devez alors être invité à vous connecter à l’appareil à l’aide du compte local et du mot de passe partagés.</span><span class="sxs-lookup"><span data-stu-id="9609b-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="9609b-189">Mise à jour</span><span class="sxs-lookup"><span data-stu-id="9609b-189">Maintain</span></span>
<span data-ttu-id="9609b-190">Dans cette configuration, il est recommandé de redémarrer le processus ci-dessus et de refaire clignoter l’appareil à l’aide de l’outil ARC et d’appliquer un nouveau PPKG pour effectuer les mises à jour apportées au système d’exploitation et/ou aux applications.</span><span class="sxs-lookup"><span data-stu-id="9609b-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

