---
title: Package d’approvisionnement
description: En savoir plus sur l’empaquetage d’applications, l’approvisionnement, le déploiement et le déploiement d’applications d’entreprise pour les appareils HoloLens.
keywords: application, déploiement d’applications, déploiement d’applications d’entreprise, approvisionnement
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308733"
---
# <a name="provisioning-package"></a><span data-ttu-id="4f75f-104">Package d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="4f75f-104">Provisioning Package</span></span>

<span data-ttu-id="4f75f-105">Les packages de configuration peuvent être utilisés pour préparer et configurer des appareils dans un environnement sans accès à la gestion des points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="4f75f-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="4f75f-106">Ils peuvent également être déployés sur un appareil, quelle que soit l’identité de l’utilisateur, l’état de l’inscription, pendant l’expérience OOBE (out of Box Experience) ou l' [application d’un package de configuration pendant l’installation](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="4f75f-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="4f75f-107">Considérations sur les packages d’approvisionnement :</span><span class="sxs-lookup"><span data-stu-id="4f75f-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="4f75f-108">Applications non publiques</span><span class="sxs-lookup"><span data-stu-id="4f75f-108">Non-Public apps</span></span>
* <span data-ttu-id="4f75f-109">Chargement côté USB uniquement</span><span class="sxs-lookup"><span data-stu-id="4f75f-109">USB side-load only</span></span>
* <span data-ttu-id="4f75f-110">Aucune mise à jour automatique (nécessite des mises à jour manuelles via PPKGs)</span><span class="sxs-lookup"><span data-stu-id="4f75f-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="4f75f-111">Les applications installées à l’aide d’un package d’approvisionnement doivent être signées par un certificat dans le magasin de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="4f75f-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="4f75f-112">Les packages d’approvisionnement peuvent uniquement installer des certificats sur le magasin de l’appareil (ordinateur local). par conséquent, une application et un certificat peuvent être installés par le biais du même package de configuration.</span><span class="sxs-lookup"><span data-stu-id="4f75f-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="4f75f-113">Si vous déployez votre certificat à partir de MDM ou que vous installez via le [Gestionnaire de certificats](certificate-manager.md), veillez à déployer le certificat dans le magasin de l’ordinateur local pour signer les applications installées de cette manière.</span><span class="sxs-lookup"><span data-stu-id="4f75f-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="4f75f-114">Pour découvrir les principes de base de la création d’un package d’approvisionnement pour les appareils HoloLens, consultez [approvisionnement de hololens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="4f75f-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="4f75f-115">Pour déployer une application, vous devez commencer par l’approvisionnement avancé.</span><span class="sxs-lookup"><span data-stu-id="4f75f-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="4f75f-116">HoloLens (1ère génération) a limité la prise en charge de l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="4f75f-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="4f75f-117">Les appareils HoloLens (1er génération) prennent uniquement en charge l’installation d’une application via PPKG uniquement au cours de l’installation OOBE et uniquement avec les installations de contexte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4f75f-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="4f75f-118">Installation</span><span class="sxs-lookup"><span data-stu-id="4f75f-118">Setup</span></span>

<span data-ttu-id="4f75f-119">Dans le [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , suivez les quatre étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4f75f-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="4f75f-120">Définissez ApplicationManagement/AllowAllTrustedApps sur « Oui ».</span><span class="sxs-lookup"><span data-stu-id="4f75f-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="4f75f-121">Voir : [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="4f75f-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="4f75f-122">Accédez à **UniversalAppInstall**  >  **UserContextAppLicense** entrez le **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="4f75f-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="4f75f-123">Consultez [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="4f75f-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="4f75f-124">Voir aussi : [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="4f75f-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="4f75f-125">Vous pouvez utiliser le portail des appareils sur un appareil sur lequel vous avez déjà installé votre application.</span><span class="sxs-lookup"><span data-stu-id="4f75f-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="4f75f-126">Accédez à la page applications, puis examinez la ligne PackageRelativeID, toutes les informations avant le «  ! » Est votre **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="4f75f-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="4f75f-127">Vous verrez alors que vous avez une nouvelle section, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="4f75f-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="4f75f-128">Utilisez cette zone pour charger votre bundle Appx.</span><span class="sxs-lookup"><span data-stu-id="4f75f-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="4f75f-129">Selon que vous avez acheté votre application ou créé votre propre application métier, vous devez télécharger le fichier de licence ou le certificat de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4f75f-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="4f75f-130">Pour le fichier de licence : accédez à **UniversalAppInstall**  >  **UserContextAppLicence** et accédez à l’emplacement de votre licence et chargez-le.</span><span class="sxs-lookup"><span data-stu-id="4f75f-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="4f75f-131">Pour le fichier de sécurité, accédez à **certificats** , puis sélectionnez votre certificat à installer en même temps que votre bundle. Appx.</span><span class="sxs-lookup"><span data-stu-id="4f75f-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="4f75f-132">Veillez à enregistrer votre projet dans un emplacement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="4f75f-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="4f75f-133">Ensuite, **exportez** -le en tant que **package d’approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="4f75f-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="4f75f-134">Voir aussi : [appliquez votre package d’approvisionnement à HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="4f75f-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
