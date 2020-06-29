---
title: Déverrouiller les fonctionnalités de Windows Holographic for Business
description: Lorsque vous effectuez une mise à niveau vers Windows holographique entreprise, HoloLens fournit des fonctionnalités supplémentaires conçues pour les entreprises.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828455"
---
# <span data-ttu-id="dba03-103">Déverrouiller les fonctionnalités de Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="dba03-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dba03-104">Cette page s’applique uniquement à HoloLens 1ère génération.</span><span class="sxs-lookup"><span data-stu-id="dba03-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="dba03-105">Microsoft HoloLens est disponible dans l' *édition Development*qui exécute Windows holographique (édition de Windows 10 conçue pour HoloLens), et dans la [suite commerciale](hololens-commercial-features.md), qui fournit des fonctionnalités supplémentaires conçues pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="dba03-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="dba03-106">Lorsque vous achetez la Commercial Suite, vous recevez une licence qui met à niveau WindowsHolographique vers WindowsHolographic for Business.</span><span class="sxs-lookup"><span data-stu-id="dba03-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="dba03-107">Vous pouvez l’appliquer à l’appareil à l’aide du [fournisseur de gestion des périphériques mobiles (GPM)](#edition-upgrade-by-using-mdm) de l’organisation ou d’un [package de mise à service](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="dba03-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="dba03-108">Dans Windows 10, version 1803, vous pouvez vérifier que le HoloLens a été mis à niveau vers l’édition commerciale en sélectionnant l’option système de **paramètres**  >  **System**.</span><span class="sxs-lookup"><span data-stu-id="dba03-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="dba03-109">Mise à niveau d’une édition à l’aide de la GPM</span><span class="sxs-lookup"><span data-stu-id="dba03-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="dba03-110">La licence d’entreprise peut être appliquée par n’importe quel fournisseur GPM qui prend en charge le [fournisseur de services de configuration (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="dba03-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="dba03-111">La dernière version de l’API Microsoft GPM prendra en charge le CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="dba03-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="dba03-112">Pour obtenir des instructions détaillées pour la mise à niveau de HoloLens à l’aide de Microsoft Intune, voir [mise à niveau de périphériques exécutant Windows holographique vers Windows holographique pour les entreprises](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="dba03-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="dba03-113">Sur les autres fournisseurs GPM, les étapes de configuration et de déploiement de la stratégie spécifiques peuvent varier.</span><span class="sxs-lookup"><span data-stu-id="dba03-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="dba03-114">Mise à niveau d’une édition à l’aide d’un package de mise en service</span><span class="sxs-lookup"><span data-stu-id="dba03-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="dba03-115">Les packages de configuration sont des fichiers créés par l’outil Concepteur de configuration Windows qui appliquent une configuration spécifiée à un appareil.</span><span class="sxs-lookup"><span data-stu-id="dba03-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="dba03-116">Créer un package de configuration qui met à niveau l’édition Windows Holographique</span><span class="sxs-lookup"><span data-stu-id="dba03-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="dba03-117">Créez un package d’approvisionnement pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dba03-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="dba03-118">Accédez à **Paramètres d’exécution** > **EditionUpgrade**, puis sélectionnez **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="dba03-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Mettez à jour l'édition avec le paramètre de licence sélectionné](images/icd1.png)

1. <span data-ttu-id="dba03-120">Recherchez le fichier de licence XML fourni lors de l’achat de la suite commerciale.</span><span class="sxs-lookup"><span data-stu-id="dba03-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dba03-121">Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="dba03-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="dba03-122">Dans le menu **fichier** , sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dba03-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="dba03-123">Lisez le message d’avertissement indiquant que les fichiers de projet contiennent des informations sensibles, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dba03-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dba03-124">Lorsque vous créez un package de mise en service, vous pouvez inclure des informations sensibles dans le fichier de projet et le package de mise en service (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="dba03-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="dba03-125">Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés.</span><span class="sxs-lookup"><span data-stu-id="dba03-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="dba03-126">Lorsque vous n’en avez plus besoin, vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers de projet.</span><span class="sxs-lookup"><span data-stu-id="dba03-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="dba03-127">Dans le menu **Export**, sélectionnez **Provisioning package**.</span><span class="sxs-lookup"><span data-stu-id="dba03-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="dba03-128">Remplacez le **propriétaire** par l' **administrateur informatique**, qui définit le niveau de priorité de ce package de mise à niveau de sorte qu’il soit plus élevé que d’autres utilisateurs appliqués à cet appareil à partir de sources différentes, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dba03-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="dba03-129">Définissez une valeur pour **Package Version**.</span><span class="sxs-lookup"><span data-stu-id="dba03-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="dba03-130">Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.</span><span class="sxs-lookup"><span data-stu-id="dba03-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="dba03-131">Dans **Sélectionner les détails de sécurité du package de mise en service**, sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="dba03-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="dba03-132">Sélectionnez **suivant** pour spécifier l’emplacement de sortie dans lequel vous souhaitez que le package de mise en service soit placé une fois qu’il est intégré.</span><span class="sxs-lookup"><span data-stu-id="dba03-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="dba03-133">Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="dba03-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="dba03-134">Vous pouvez également sélectionner **Parcourir** pour changer l’emplacement de sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="dba03-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="dba03-135">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="dba03-135">Select **Next**.</span></span>

1. <span data-ttu-id="dba03-136">Pour commencer à générer le package, sélectionnez **Build** .</span><span class="sxs-lookup"><span data-stu-id="dba03-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="dba03-137">La page de génération affiche les informations du projet et la barre de progression indique l’état de la Build.</span><span class="sxs-lookup"><span data-stu-id="dba03-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="dba03-138">À la fin de la build, sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="dba03-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="dba03-139">Appliquer le package d’approvisionnement à HoloLens</span><span class="sxs-lookup"><span data-stu-id="dba03-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="dba03-140">À l’aide du câble USB, connectez l’appareil à un PC.</span><span class="sxs-lookup"><span data-stu-id="dba03-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="dba03-141">Démarrez l’appareil, mais ne poursuivez pas la **page d’accueil de l’expérience** de configuration initiale (première page avec le cadre bleu).</span><span class="sxs-lookup"><span data-stu-id="dba03-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="dba03-142">Sur PC, HoloLens est affiché en tant qu’appareil dans l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="dba03-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dba03-143">Si le périphérique HoloLens exécute Windows 10, version 1607 ou antérieure, ouvrez l’Explorateur de fichiers en appuyant brièvement sur le **volume** et sur les boutons **d’alimentation** situés en même temps que l’appareil.</span><span class="sxs-lookup"><span data-stu-id="dba03-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="dba03-144">Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="dba03-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="dba03-145">Lorsque HoloLens est toujours dans la page **ajuster** , appuyez brièvement sur le **volume** , puis relâchez le bouton **d’alimentation** .</span><span class="sxs-lookup"><span data-stu-id="dba03-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="dba03-146">HoloLens vous demande si vous faites confiance au package et si vous voulez l’appliquer.</span><span class="sxs-lookup"><span data-stu-id="dba03-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="dba03-147">Confirmez que vous faites confiance au package.</span><span class="sxs-lookup"><span data-stu-id="dba03-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="dba03-148">Vous verrez si le package a été appliqué avec succès ou non.</span><span class="sxs-lookup"><span data-stu-id="dba03-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="dba03-149">S’il n’a pas été correctement appliqué, vous pouvez résoudre votre problème, puis réessayer.</span><span class="sxs-lookup"><span data-stu-id="dba03-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="dba03-150">En cas de succès, continuez avec la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="dba03-150">If successful, proceed with device setup.</span></span>
