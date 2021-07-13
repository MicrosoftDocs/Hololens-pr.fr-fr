---
title: Déverrouiller les fonctionnalités de Windows Holographic for Business
description: lorsque vous effectuez une mise à niveau vers Windows Holographic for Business, HoloLens fournit des fonctionnalités supplémentaires conçues pour l’entreprise.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635192"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="177c8-103">Déverrouiller les fonctionnalités de Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="177c8-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="177c8-104">cette page s’applique uniquement à HoloLens 1re génération.</span><span class="sxs-lookup"><span data-stu-id="177c8-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="177c8-105">Microsoft HoloLens est disponible dans l' *édition Development*, qui s’exécute Windows holographique (une édition de Windows 10 conçue pour HoloLens) et dans la [Suite commerciale](hololens-commercial-features.md), qui offre des fonctionnalités supplémentaires conçues pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="177c8-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="177c8-106">lorsque vous achetez la Suite commerciale, vous recevez une licence qui met à niveau Windows holographique vers Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="177c8-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="177c8-107">Vous pouvez appliquer cette licence à l’appareil soit à l’aide du [fournisseur de gestion des appareils mobiles (MDM)](#edition-upgrade-by-using-mdm) de l’organisation, soit à l’aide d’un [package de configuration](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="177c8-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="177c8-108">dans Windows 10, la version 1803, vous pouvez vérifier que le HoloLens a été mis à niveau vers l’édition business en sélectionnant **Paramètres**  >  **système**.</span><span class="sxs-lookup"><span data-stu-id="177c8-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="177c8-109">Mise à niveau d’édition à l’aide de MDM</span><span class="sxs-lookup"><span data-stu-id="177c8-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="177c8-110">La licence d’entreprise peut être appliquée par n’importe quel fournisseur GPM qui prend en charge le [fournisseur de services de configuration (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="177c8-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="177c8-111">La dernière version de l’API Microsoft GPM prendra en charge le CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="177c8-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="177c8-112">pour obtenir des instructions pas à pas sur la mise à niveau de HoloLens à l’aide de Microsoft Intune, consultez [mettre à niveau des appareils exécutant Windows holographique vers Windows Holographic for Business](/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="177c8-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="177c8-113">Sur les autres fournisseurs GPM, les étapes de configuration et de déploiement de la stratégie spécifiques peuvent varier.</span><span class="sxs-lookup"><span data-stu-id="177c8-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="177c8-114">Mise à niveau d’édition à l’aide d’un package d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="177c8-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="177c8-115">les packages de provisionnement sont des fichiers créés par l’outil concepteur de configuration Windows qui appliquent une Configuration spécifiée à un appareil.</span><span class="sxs-lookup"><span data-stu-id="177c8-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="177c8-116">Créer un package d’approvisionnement qui met à niveau l’édition Windows Holographique</span><span class="sxs-lookup"><span data-stu-id="177c8-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="177c8-117">Créez un package d’approvisionnement pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="177c8-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="177c8-118">Accédez à **paramètres d’exécution**  >  **EditionUpgrade**, puis sélectionnez **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="177c8-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Mettez à jour l'édition avec le paramètre de licence sélectionné](images/icd1.png)

1. <span data-ttu-id="177c8-120">Recherchez le fichier de licence XML fourni lorsque vous avez acheté la suite commerciale.</span><span class="sxs-lookup"><span data-stu-id="177c8-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="177c8-121">Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="177c8-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="177c8-122">Dans le menu **File** (Fichier), sélectionnez **Save** (Enregistrer).</span><span class="sxs-lookup"><span data-stu-id="177c8-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="177c8-123">Lisez l’avertissement indiquant que les fichiers projet peuvent contenir des informations sensibles, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="177c8-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="177c8-124">Quand vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et le fichier de package de configuration (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="177c8-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="177c8-125">Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés.</span><span class="sxs-lookup"><span data-stu-id="177c8-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="177c8-126">Vous devez stocker les fichiers projet dans un emplacement sécurisé et supprimer les fichiers projet quand vous n’en avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="177c8-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="177c8-127">Dans le menu **Export**, sélectionnez **Provisioning package**.</span><span class="sxs-lookup"><span data-stu-id="177c8-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="177c8-128">Remplacez **propriétaire** par **administrateur informatique**, qui définit la priorité de ce package d’approvisionnement sur une valeur supérieure à celle appliquée à cet appareil à partir de différentes sources, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="177c8-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="177c8-129">Définissez une valeur pour **Package Version**.</span><span class="sxs-lookup"><span data-stu-id="177c8-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="177c8-130">Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.</span><span class="sxs-lookup"><span data-stu-id="177c8-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="177c8-131">Dans **Sélectionner les détails de sécurité pour le package d’approvisionnement**, sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="177c8-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="177c8-132">Sélectionnez **suivant** pour spécifier l’emplacement de sortie où vous souhaitez que le package de configuration se trouve une fois qu’il a été créé.</span><span class="sxs-lookup"><span data-stu-id="177c8-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="177c8-133">Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="177c8-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="177c8-134">Si vous le souhaitez, vous pouvez sélectionner **Parcourir** pour modifier l’emplacement de sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="177c8-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="177c8-135">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="177c8-135">Select **Next**.</span></span>

1. <span data-ttu-id="177c8-136">Sélectionnez **Build** pour commencer à générer le package.</span><span class="sxs-lookup"><span data-stu-id="177c8-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="177c8-137">La page générer affiche les informations du projet et la barre de progression indique l’état de la Build.</span><span class="sxs-lookup"><span data-stu-id="177c8-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="177c8-138">Une fois la génération terminée, sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="177c8-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="177c8-139">Appliquer le package d’approvisionnement à HoloLens</span><span class="sxs-lookup"><span data-stu-id="177c8-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="177c8-140">À l’aide du câble USB, connectez l’appareil à un PC.</span><span class="sxs-lookup"><span data-stu-id="177c8-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="177c8-141">Démarrez l’appareil, mais ne passez pas à la page **ajuster** de l’expérience d’installation initiale (première page avec la zone bleue).</span><span class="sxs-lookup"><span data-stu-id="177c8-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="177c8-142">sur le PC, HoloLens apparaît en tant qu’appareil dans l’explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="177c8-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="177c8-143">si le HoloLens appareil exécute Windows 10, version 1607 ou antérieure, ouvrez l’explorateur de fichiers en appuyant sur la touche et en relâchant les boutons de réduction et **d’alimentation** du **Volume** simultanément sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="177c8-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="177c8-144">Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="177c8-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="177c8-145">bien que HoloLens soit toujours sur la page **ajuster** , appuyez brièvement sur les boutons arrêter et **redémarrer du** **Volume** et relâchez-les simultanément.</span><span class="sxs-lookup"><span data-stu-id="177c8-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="177c8-146">HoloLens vous demande si vous faites confiance au package et que vous souhaitez l’appliquer.</span><span class="sxs-lookup"><span data-stu-id="177c8-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="177c8-147">Confirmez que vous faites confiance au package.</span><span class="sxs-lookup"><span data-stu-id="177c8-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="177c8-148">Vous verrez si le package a été appliqué avec succès ou non.</span><span class="sxs-lookup"><span data-stu-id="177c8-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="177c8-149">S’il n’a pas été appliqué, vous pouvez corriger votre package et réessayer.</span><span class="sxs-lookup"><span data-stu-id="177c8-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="177c8-150">En cas de réussite, effectuez la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="177c8-150">If successful, proceed with device setup.</span></span>
