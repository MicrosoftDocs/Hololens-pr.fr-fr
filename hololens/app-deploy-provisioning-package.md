---
title: Paquet d'approvisionnement
description: déploiement d’applications, de déploiement d’applications, de déploiement d’applications d’entreprise et de mise en service
keywords: déploiement d’applications, de déploiement d’applications, de déploiement d’applications d’entreprise et de mise en service
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
ms.openlocfilehash: 11bc83be188e1b81959690efcb2bdf26d800aae3
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252675"
---
# <span data-ttu-id="ef9c4-104">Paquet d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="ef9c4-104">Provisioning Package</span></span>

<span data-ttu-id="ef9c4-105">Les packages de mise en service peuvent être utilisés pour préparer et configurer des appareils dans un environnement sans accès à la gestion des points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="ef9c4-106">Elles peuvent également être déployées sur un appareil quelle que soit l’identité de l’utilisateur, l’état de l’inscription, lors de l’utilisation de OOBE (out-of-Box Experience) ou en [appliquant un package de mise](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)à disponibilité lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="ef9c4-107">Considérations relatives aux packages de mise en service:</span><span class="sxs-lookup"><span data-stu-id="ef9c4-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="ef9c4-108">Applications non publiques</span><span class="sxs-lookup"><span data-stu-id="ef9c4-108">Non-Public apps</span></span>
* <span data-ttu-id="ef9c4-109">Télécharger uniquement le bus USB</span><span class="sxs-lookup"><span data-stu-id="ef9c4-109">USB side-load only</span></span>
* <span data-ttu-id="ef9c4-110">Aucune mise à jour automatique (nécessite des mises à jour manuelles via PPKGs)</span><span class="sxs-lookup"><span data-stu-id="ef9c4-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="ef9c4-111">Les applications installées par le biais d’un package de mise en service doivent être signées par un certificat dans le magasin de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="ef9c4-112">Les packages de mise en service peuvent uniquement installer des certificats sur le magasin de périphériques (ordinateur local), par conséquent une application et un certificat peuvent être installés par le biais du même package de mise en service.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="ef9c4-113">Si vous déployez votre certificat à partir de la gestion des périphériques mobiles ou d’une installation via le [Gestionnaire de certificats](certificate-manager.md), assurez-vous de déployer le certificat dans le magasin d’ordinateurs local pour signer les applications installées de cette manière.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="ef9c4-114">Pour découvrir les notions de base de la création d’un package de mise à service pour les appareils HoloLens, visitez [approvisionnement HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="ef9c4-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="ef9c4-115">Pour déployer une application, vous devez commencer par la mise en service avancée.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="ef9c4-116">HoloLens (1er génération) dispose d’une prise en charge limitée pour l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package de mise en service.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="ef9c4-117">Les appareils HoloLens (1ère génération) ne prennent en charge l’installation d’une application qu’avec PPKG que dans OOBE et uniquement avec les installations de contexte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="ef9c4-118">Configuration</span><span class="sxs-lookup"><span data-stu-id="ef9c4-118">Setup</span></span>

<span data-ttu-id="ef9c4-119">Dans le [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , procédez comme suit quatre étapes.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="ef9c4-120">Définissez ApplicationManagement/AllowAllTrustedApps sur «Yes».</span><span class="sxs-lookup"><span data-stu-id="ef9c4-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="ef9c4-121">Voir: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="ef9c4-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="ef9c4-122">Accédez à **UniversalAppInstall**  >  **UserContextAppLicense** entrez le **propriété packagefamilyname**.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="ef9c4-123">Voir [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="ef9c4-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="ef9c4-124">Voir aussi: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="ef9c4-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="ef9c4-125">Vous pouvez utiliser Device Portal sur un appareil sur lequel vous avez déjà installé votre application.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="ef9c4-126">Accédez à la page applications et examinez la ligne PackageRelativeID, toutes les informations précédant le «!». Est votre **propriété packagefamilyname**.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="ef9c4-127">Vous verrez alors que vous avez une nouvelle section **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="ef9c4-128">Utilisez cette zone pour télécharger votre bundle Appx.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="ef9c4-129">Selon que vous avez acheté votre application ou créé votre propre application métier, vous devrez télécharger le fichier de licence ou le certificat de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="ef9c4-130">Pour le fichier de licence: accédez à **UniversalAppInstall**  >  **UserContextAppLicence** et naviguez jusqu’à l’emplacement de votre licence et chargez-le.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="ef9c4-131">Pour le fichier de sécurité, accédez à **certificats** et sélectionnez le certificat à installer avec votre ensemble d’applications. Appx.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="ef9c4-132">Veillez à enregistrer votre projet dans un emplacement sécurisé.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="ef9c4-133">Ensuite, **exportez** -la en tant que **package de mise en service**.</span><span class="sxs-lookup"><span data-stu-id="ef9c4-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="ef9c4-134">Voir aussi: [appliquer votre package de mise en service au HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="ef9c4-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
