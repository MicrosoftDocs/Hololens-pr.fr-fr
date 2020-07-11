---
title: Chiffrement BitLocker HoloLens
description: Activer le chiffrement de l’appareil Bitlocker pour protéger les fichiers stockés sur le casque HoloLens
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
ms.openlocfilehash: 5ab35f0804c6a906cb0bb262211e8ae5ab017459
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865706"
---
# <span data-ttu-id="8d309-103">HoloLens (1ère génération) chiffrement BitLocker</span><span class="sxs-lookup"><span data-stu-id="8d309-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="8d309-104">HoloLens (1er génération) et HoloLens 2 prennent en charge le chiffrement de l’appareil à l’aide de BitLocker, mais BitLocker est toujours activé sur HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8d309-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="8d309-105">Cet article va vous aider à activer et à gérer BitLocker sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="8d309-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="8d309-106">Sur HoloLens (1ère génération), vous pouvez activer le chiffrement de périphériques BitLocker manuellement ou à l’aide de la gestion des périphériques mobiles (GPM).</span><span class="sxs-lookup"><span data-stu-id="8d309-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="8d309-107">Suivez ces instructions pour activer le [chiffrement de l’appareil BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) afin de protéger les fichiers et les informations stockés sur le HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8d309-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="8d309-108">Le chiffrement de l’appareil permet de protéger vos données à l’aide de la méthode de chiffrement AES-CBC 128, qui équivaut à la [méthode EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) du fournisseur de services de configuration (CSP).</span><span class="sxs-lookup"><span data-stu-id="8d309-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="8d309-109">Le personnel qui dispose de la clé de cryptage correcte (par exemple, un mot de passe) peut le déchiffrer ou effectuer une récupération des données.</span><span class="sxs-lookup"><span data-stu-id="8d309-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <span data-ttu-id="8d309-110">Activer le chiffrement de l’appareil à l’aide de GPM</span><span class="sxs-lookup"><span data-stu-id="8d309-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="8d309-111">Vous pouvez utiliser votre fournisseur de gestion des périphériques mobiles (GPM) pour appliquer une stratégie qui nécessite le chiffrement de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8d309-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="8d309-112">La stratégie à utiliser est le [paramètre Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) du CSP de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="8d309-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="8d309-113">Voir instructions relatives à l’activation du chiffrement d’appareil à l’aide de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8d309-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="8d309-114">Pour d’autres outils de GPM, consultez la documentation de votre fournisseur GPM pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="8d309-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="8d309-115">Si votre fournisseur de gestion des appareils mobiles nécessite un URI personnalisé pour le chiffrement de l’appareil, utilisez la configuration suivante:</span><span class="sxs-lookup"><span data-stu-id="8d309-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="8d309-116">**Nom**: un nom de votre choix</span><span class="sxs-lookup"><span data-stu-id="8d309-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="8d309-117">**Description**: facultatif</span><span class="sxs-lookup"><span data-stu-id="8d309-117">**Description**: optional</span></span>
- <span data-ttu-id="8d309-118">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="8d309-118">**OMA-URI**:</span></span> `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- <span data-ttu-id="8d309-119">**Type de données**: entier</span><span class="sxs-lookup"><span data-stu-id="8d309-119">**Data type**: integer</span></span>
- <span data-ttu-id="8d309-120">**Valeur**:</span><span class="sxs-lookup"><span data-stu-id="8d309-120">**Value**:</span></span> `1`

## <span data-ttu-id="8d309-121">Activer le chiffrement de l’appareil à l’aide d’un package de configuration</span><span class="sxs-lookup"><span data-stu-id="8d309-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="8d309-122">Les packages de configuration sont des fichiers créés par l’outil Concepteur de configuration Windows qui appliquent une configuration spécifiée à un appareil.</span><span class="sxs-lookup"><span data-stu-id="8d309-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <span data-ttu-id="8d309-123">Créer un package de mise à niveau qui met à jour Windows holographique Edition et active le chiffrement</span><span class="sxs-lookup"><span data-stu-id="8d309-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="8d309-124">Créez un package de configuration pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8d309-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="8d309-125">Accédez à **Paramètres d'exécution** > **Stratégies** > **Sécurité**, puis sélectionnez **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="8d309-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Exiger que le paramètre de chiffrement d’appareil soit configuré sur oui](images/device-encryption.png)

1. <span data-ttu-id="8d309-127">Recherchez le fichier de licence XML fourni lors de l’achat de la suite commerciale.</span><span class="sxs-lookup"><span data-stu-id="8d309-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="8d309-128">Recherchez et sélectionnez le fichier de licence XML qui a été fourni lorsque vous avez acheté la Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="8d309-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="8d309-129">Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="8d309-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="8d309-130">Dans le menu **Fichier**, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8d309-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="8d309-131">Lisez le message d’avertissement expliquant que les fichiers de projet risquent de contenir des informations sensibles, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d309-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8d309-132">Lorsque vous créez un package de mise en service, vous pouvez inclure des informations sensibles dans le fichier de projet et le package de mise en service (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="8d309-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="8d309-133">Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés.</span><span class="sxs-lookup"><span data-stu-id="8d309-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="8d309-134">Lorsque vous n’en avez plus besoin, vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers de projet.</span><span class="sxs-lookup"><span data-stu-id="8d309-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="8d309-135">Dans le menu **Exporter**, cliquez sur **Package d’approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="8d309-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="8d309-136">Remplacez **Propriétaire** par **Administrateur informatique**, ce qui indique que la priorité de ce package d’approvisionnement est supérieure à celle des packages d’approvisionnement appliqués à cet appareil provenant d’autres sources, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8d309-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="8d309-137">Définissez une valeur pour **Package Version**.</span><span class="sxs-lookup"><span data-stu-id="8d309-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8d309-138">Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.</span><span class="sxs-lookup"><span data-stu-id="8d309-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="8d309-139">Sur **Sélectionner les données de sécurité du package de mise en service**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8d309-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="8d309-140">Cliquez sur **Suivant** pour spécifier l’emplacement de sortie où vous souhaitez diriger le package d’approvisionnement une fois ce dernier généré.</span><span class="sxs-lookup"><span data-stu-id="8d309-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="8d309-141">Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="8d309-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="8d309-142">Le cas échéant, cliquez sur Parcourir pour modifier l’emplacement de sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d309-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="8d309-143">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8d309-143">Click **Next**.</span></span>
1. <span data-ttu-id="8d309-144">Cliquez sur **Build** pour commencer à générer le package.</span><span class="sxs-lookup"><span data-stu-id="8d309-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="8d309-145">Les informations du projet s'affichent sur la page de génération, et la barre de progression indique l'état de la génération.</span><span class="sxs-lookup"><span data-stu-id="8d309-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="8d309-146">Lorsque la génération est achevée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8d309-146">When the build completes, click **Finish**.</span></span>

### <span data-ttu-id="8d309-147">Appliquer le package d’approvisionnement à HoloLens</span><span class="sxs-lookup"><span data-stu-id="8d309-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="8d309-148">Connectez l’appareil à un PC via USB et démarrez l’appareil, mais ne dépassez pas la page **ajuster** de l'expérience de configuration initiale (la première page affichant le rectangle bleu).</span><span class="sxs-lookup"><span data-stu-id="8d309-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="8d309-149">Appuyez brièvement sur les boutons **Baisser le volume** et **Marche/Arrêt** en même temps, puis relâchez-les.</span><span class="sxs-lookup"><span data-stu-id="8d309-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="8d309-150">HoloLens s’affiche comme périphérique dans l’Explorateur de fichiers du PC.</span><span class="sxs-lookup"><span data-stu-id="8d309-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="8d309-151">Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="8d309-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="8d309-152">Appuyez à nouveau brièvement sur les boutons **Baisser le Volume** et **Alimentation** simultanément, puis relâchez-les, lorsque vous êtes sur la page **Ajuster**.</span><span class="sxs-lookup"><span data-stu-id="8d309-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="8d309-153">L’appareil vous demandera si vous faites confiance au package et si vous souhaitez l’appliquer.</span><span class="sxs-lookup"><span data-stu-id="8d309-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="8d309-154">Confirmez que vous faites confiance au package.</span><span class="sxs-lookup"><span data-stu-id="8d309-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="8d309-155">Vous verrez si le package a été appliqué avec succès ou non.</span><span class="sxs-lookup"><span data-stu-id="8d309-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="8d309-156">En cas d’échec, vous pouvez corriger votre package et essayer à nouveau.</span><span class="sxs-lookup"><span data-stu-id="8d309-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="8d309-157">Si l'opération a réussi, passez à la configuration de l'appareil.</span><span class="sxs-lookup"><span data-stu-id="8d309-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="8d309-158">Si l’appareil a été acheté avant août2016, vous devrez vous y connecter avec un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser celui-ci pour pouvoir appliquer le package de configuration.</span><span class="sxs-lookup"><span data-stu-id="8d309-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <span data-ttu-id="8d309-159">Vérifier le chiffrement de l’appareil</span><span class="sxs-lookup"><span data-stu-id="8d309-159">Verify device encryption</span></span>

<span data-ttu-id="8d309-160">Le chiffrement est en mode silencieux sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8d309-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="8d309-161">Pour vérifier l’état de chiffrement de l'appareil:</span><span class="sxs-lookup"><span data-stu-id="8d309-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="8d309-162">Sur HoloLens, accédez à **Paramètres** > **Système** > **À propos de**.</span><span class="sxs-lookup"><span data-stu-id="8d309-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="8d309-163">**BitLocker** est **activé** si l’appareil est chiffré.</span><span class="sxs-lookup"><span data-stu-id="8d309-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![À propos de l’affichage de BitLocker activé](images/about-encryption.png)
