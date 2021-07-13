---
title: HoloLens Chiffrement BitLocker
description: découvrez comment activer le chiffrement de périphérique BitLocker pour protéger des fichiers stockés sur votre HoloLens des appareils de réalité mixte.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635243"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="b03d8-103">Chiffrement BitLocker HoloLens (1re génération)</span><span class="sxs-lookup"><span data-stu-id="b03d8-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="b03d8-104">HoloLens (1re génération) et HoloLens 2 prennent en charge le chiffrement des appareils à l’aide de bitlocker. toutefois, bitlocker est toujours activé sur HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b03d8-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="b03d8-105">cet article vous aidera à activer et à gérer BitLocker sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="b03d8-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="b03d8-106">sur HoloLens (1re génération), vous pouvez activer le chiffrement de l’appareil BitLocker manuellement ou à l’aide de la gestion des appareils mobiles (MDM).</span><span class="sxs-lookup"><span data-stu-id="b03d8-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="b03d8-107">Suivez ces instructions pour activer le [chiffrement d’appareil BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) afin de protéger les fichiers et les informations stockés sur le HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b03d8-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="b03d8-108">Le chiffrement de l’appareil vous aide à protéger vos données à l’aide de la méthode de chiffrement AES-CBC 128, qui est équivalente à la [méthode EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) dans le fournisseur de services de configuration (CSP) BitLocker.</span><span class="sxs-lookup"><span data-stu-id="b03d8-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="b03d8-109">Le personnel qui a la clé de chiffrement correcte (par exemple, un mot de passe) peut le déchiffrer ou effectuer une récupération de données.</span><span class="sxs-lookup"><span data-stu-id="b03d8-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="b03d8-110">Activer le chiffrement de l’appareil à l’aide de MDM</span><span class="sxs-lookup"><span data-stu-id="b03d8-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="b03d8-111">Vous pouvez utiliser votre fournisseur de gestion des appareils mobiles (MDM) pour appliquer une stratégie qui requiert le chiffrement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b03d8-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="b03d8-112">La stratégie à utiliser est le [paramètre Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) dans le fournisseur de services de chiffrement de stratégie.</span><span class="sxs-lookup"><span data-stu-id="b03d8-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="b03d8-113">Consultez les instructions pour activer le chiffrement de l’appareil à l’aide de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b03d8-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="b03d8-114">Pour d’autres outils MDM, consultez la documentation de votre fournisseur MDM pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="b03d8-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="b03d8-115">Si votre fournisseur MDM requiert un URI personnalisé pour le chiffrement de l’appareil, utilisez la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="b03d8-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="b03d8-116">**Nom**: nom de votre choix</span><span class="sxs-lookup"><span data-stu-id="b03d8-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="b03d8-117">**Description**: facultatif</span><span class="sxs-lookup"><span data-stu-id="b03d8-117">**Description**: optional</span></span>
- <span data-ttu-id="b03d8-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="b03d8-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="b03d8-119">**Type de données**: entier</span><span class="sxs-lookup"><span data-stu-id="b03d8-119">**Data type**: integer</span></span>
- <span data-ttu-id="b03d8-120">**Valeur** : `1`</span><span class="sxs-lookup"><span data-stu-id="b03d8-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="b03d8-121">Activer le chiffrement de l’appareil à l’aide d’un package d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="b03d8-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="b03d8-122">les packages de provisionnement sont des fichiers créés par l’outil concepteur de configuration Windows qui appliquent une Configuration spécifiée à un appareil.</span><span class="sxs-lookup"><span data-stu-id="b03d8-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="b03d8-123">créer un package de mise en service qui met à niveau le Windows édition holographique et active le chiffrement</span><span class="sxs-lookup"><span data-stu-id="b03d8-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="b03d8-124">Créez un package d’approvisionnement pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b03d8-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="b03d8-125">Accédez à **paramètres d’exécution**  >  **stratégies**  >  **sécurité**, puis sélectionnez **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Exiger le paramètre de chiffrement de l’appareil configuré sur Oui](images/device-encryption.png)

1. <span data-ttu-id="b03d8-127">Recherchez le fichier de licence XML fourni lorsque vous avez acheté la suite commerciale.</span><span class="sxs-lookup"><span data-stu-id="b03d8-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="b03d8-128">Recherchez et sélectionnez le fichier de licence XML qui a été fourni lorsque vous avez acheté la Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="b03d8-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b03d8-129">Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="b03d8-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="b03d8-130">Dans le menu **File** (Fichier), cliquez sur **Save** (Enregistrer).</span><span class="sxs-lookup"><span data-stu-id="b03d8-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="b03d8-131">Lisez l’avertissement expliquant que les fichiers projet peuvent contenir des informations sensibles, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b03d8-132">Quand vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et le fichier de package de configuration (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="b03d8-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="b03d8-133">Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés.</span><span class="sxs-lookup"><span data-stu-id="b03d8-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="b03d8-134">Vous devez stocker les fichiers projet dans un emplacement sécurisé et supprimer les fichiers projet quand vous n’en avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="b03d8-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="b03d8-135">Dans le menu **Exporter**, cliquez sur **Package d’approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="b03d8-136">Remplacez **Propriétaire** par **Administrateur informatique**, ce qui indique que la priorité de ce package d’approvisionnement est supérieure à celle des packages d’approvisionnement appliqués à cet appareil provenant d’autres sources, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="b03d8-137">Définissez une valeur pour **Package Version**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="b03d8-138">Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.</span><span class="sxs-lookup"><span data-stu-id="b03d8-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="b03d8-139">Sur **Sélectionner les données de sécurité du package de mise en service**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="b03d8-140">Cliquez sur **Suivant** pour spécifier l’emplacement de sortie où vous souhaitez diriger le package d’approvisionnement une fois ce dernier généré.</span><span class="sxs-lookup"><span data-stu-id="b03d8-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="b03d8-141">Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="b03d8-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="b03d8-142">Le cas échéant, cliquez sur Parcourir pour modifier l’emplacement de sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="b03d8-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="b03d8-143">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-143">Click **Next**.</span></span>
1. <span data-ttu-id="b03d8-144">Cliquez sur **Build** pour commencer à générer le package.</span><span class="sxs-lookup"><span data-stu-id="b03d8-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="b03d8-145">Les informations du projet s'affichent sur la page de génération, et la barre de progression indique l'état de la génération.</span><span class="sxs-lookup"><span data-stu-id="b03d8-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="b03d8-146">Lorsque la génération est achevée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="b03d8-147">Appliquer le package d’approvisionnement à HoloLens</span><span class="sxs-lookup"><span data-stu-id="b03d8-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="b03d8-148">Connecter l’appareil USB à un PC et démarrer l’appareil, mais ne continuez pas **la page de l’installation** initiale (la première page avec la boîte bleue).</span><span class="sxs-lookup"><span data-stu-id="b03d8-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="b03d8-149">Appuyez brièvement sur les boutons **Baisser le volume** et **Alimentation** en même temps, puis relâchez-les.</span><span class="sxs-lookup"><span data-stu-id="b03d8-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="b03d8-150">HoloLens s’affiche comme périphérique dans l’Explorateur de fichiers du PC.</span><span class="sxs-lookup"><span data-stu-id="b03d8-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="b03d8-151">Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b03d8-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="b03d8-152">Appuyez à nouveau brièvement sur les boutons **Baisser le Volume** et **Alimentation** simultanément, puis relâchez-les, lorsque vous êtes sur la page **Ajuster**.</span><span class="sxs-lookup"><span data-stu-id="b03d8-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="b03d8-153">L’appareil vous demandera si vous faites confiance au package et si vous souhaitez l’appliquer.</span><span class="sxs-lookup"><span data-stu-id="b03d8-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="b03d8-154">Confirmez que vous faites confiance au package.</span><span class="sxs-lookup"><span data-stu-id="b03d8-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="b03d8-155">Vous verrez si le package a été appliqué avec succès ou non.</span><span class="sxs-lookup"><span data-stu-id="b03d8-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="b03d8-156">En cas d’échec, vous pouvez corriger votre package et essayer à nouveau.</span><span class="sxs-lookup"><span data-stu-id="b03d8-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="b03d8-157">Si elle a réussi, effectuez la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b03d8-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="b03d8-158">Si l’appareil a été acheté avant le 2016 août, vous devez vous connecter à l’appareil avec un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser le système d’exploitation afin d’appliquer le package d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="b03d8-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="b03d8-159">Vérifier le chiffrement de l’appareil</span><span class="sxs-lookup"><span data-stu-id="b03d8-159">Verify device encryption</span></span>

<span data-ttu-id="b03d8-160">Le chiffrement est en mode silencieux sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b03d8-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="b03d8-161">Pour vérifier l’état du chiffrement de l’appareil :</span><span class="sxs-lookup"><span data-stu-id="b03d8-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="b03d8-162">sur HoloLens, accédez à **Paramètres**  >  **système**  >  **à propos** de.</span><span class="sxs-lookup"><span data-stu-id="b03d8-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="b03d8-163">**BitLocker** est **activé** si l’appareil est chiffré.</span><span class="sxs-lookup"><span data-stu-id="b03d8-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![À propos de l’écran indiquant que BitLocker est activé](images/about-encryption.png)
