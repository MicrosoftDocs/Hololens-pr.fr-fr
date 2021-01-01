---
title: Comment charger et installer des applications via le programme d’installation de l’application HoloLens 2
description: Télécharger et installer des applications par le biais de l’interface utilisateur
keywords: gestion des applications, application, hololens, programme d’installation de l’application
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253091"
---
# <span data-ttu-id="c6adf-104">Installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="c6adf-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="c6adf-105">Nous **ajoutons une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications plus en continu** sur vos appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c6adf-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="c6adf-106">Par défaut, la fonctionnalité est **activée pour les appareils non gérés**.</span><span class="sxs-lookup"><span data-stu-id="c6adf-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="c6adf-107">Pour éviter toute interruption des entreprises, le programme d’installation d’applications ne sera **pas disponible pour les appareils gérés pour** le moment.</span><span class="sxs-lookup"><span data-stu-id="c6adf-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="c6adf-108">Cette fonctionnalité a été prise en charge dans [Windows holographique, version 20H2: mise à jour 2020 de décembre](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="c6adf-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="c6adf-109">Assurez-vous que votre appareil est [mis à jour](hololens-update-hololens.md) de façon à utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="c6adf-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="c6adf-110">Nous avons **ajouté une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications plus en continu** sur vos appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c6adf-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="c6adf-111">Par défaut, la fonctionnalité est **activée pour les appareils non gérés**.</span><span class="sxs-lookup"><span data-stu-id="c6adf-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="c6adf-112">Pour éviter toute interruption des entreprises, le programme d’installation d’applications ne sera **pas disponible pour les appareils gérés pour** le moment.</span><span class="sxs-lookup"><span data-stu-id="c6adf-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="c6adf-113">Un appareil est considéré comme «géré» si l' **une** des conditions suivantes est vraie:</span><span class="sxs-lookup"><span data-stu-id="c6adf-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="c6adf-114">GPM [inscrits](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="c6adf-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="c6adf-115">Configuré avec le [package de mise en service](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="c6adf-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="c6adf-116">L' [identité](hololens-identity.md) de l’utilisateur est Azure ad</span><span class="sxs-lookup"><span data-stu-id="c6adf-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="c6adf-117">Vous pouvez maintenant installer des applications sans avoir besoin d’activer le mode développeur ou Device Portal.</span><span class="sxs-lookup"><span data-stu-id="c6adf-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="c6adf-118">Téléchargez (via USB ou Microsoft Edge) l’ensemble d’applications AppX sur votre appareil et accédez à l’ensemble d’applications AppX dans l’Explorateur de fichiers pour être invité à démarrer l’installation.</span><span class="sxs-lookup"><span data-stu-id="c6adf-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="c6adf-119">Vous pouvez également [lancer une installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="c6adf-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="c6adf-120">À l’instar des applications que vous installez à partir du Microsoft Store ou d’charger à l’aide de la fonctionnalité de déploiement d’applications métier de la gestion des applications métier, les applications doivent être signées numériquement à l’aide de l' [outil de signature](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour pouvoir déployer l’application.</span><span class="sxs-lookup"><span data-stu-id="c6adf-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="c6adf-121">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="c6adf-121">Requirements</span></span>

### <span data-ttu-id="c6adf-122">Pour vos appareils:</span><span class="sxs-lookup"><span data-stu-id="c6adf-122">For your devices:</span></span>

 <span data-ttu-id="c6adf-123">Cette fonctionnalité est actuellement disponible dans les builds 20H2 holographiques Windows pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c6adf-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="c6adf-124">Assurez-vous que tous les appareils qui utilisent cette méthode sont [mis à jour](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="c6adf-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="c6adf-125">Pour vos applications:</span><span class="sxs-lookup"><span data-stu-id="c6adf-125">For your apps:</span></span> 
<span data-ttu-id="c6adf-126">La configuration de la solution de votre application doit être **maître** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="c6adf-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="c6adf-127">En savoir plus sur la [création de packages d’application](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="c6adf-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="c6adf-128">Les applications installées par le biais de cette méthode doivent être signées numériquement.</span><span class="sxs-lookup"><span data-stu-id="c6adf-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="c6adf-129">Vous devez utiliser un certificat pour signer l’application.</span><span class="sxs-lookup"><span data-stu-id="c6adf-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="c6adf-130">Vous pouvez obtenir un certificat de la [liste des autorités de certification MS Trusted](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), auquel cas vous n’avez pas besoin d’effectuer d’action supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c6adf-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="c6adf-131">Vous pouvez également signer votre propre certificat, mais ce certificat doit être envoyé sur le périphérique.</span><span class="sxs-lookup"><span data-stu-id="c6adf-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="c6adf-132">Comment signer des applications [à l’aide de l’outil signature.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="c6adf-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="c6adf-133">Options de certificat:</span><span class="sxs-lookup"><span data-stu-id="c6adf-133">Certificate options:</span></span>**

- [<span data-ttu-id="c6adf-134">Liste des autorités de certification MS Trusted</span><span class="sxs-lookup"><span data-stu-id="c6adf-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="c6adf-135">Choisissez une méthode de déploiement de certificats.</span><span class="sxs-lookup"><span data-stu-id="c6adf-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="c6adf-136">Les [packages de mise en service](hololens-provisioning.md) peuvent être appliqués aux périphériques locaux.</span><span class="sxs-lookup"><span data-stu-id="c6adf-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="c6adf-137">La gestion des périphériques mobiles peut être utilisée pour [appliquer des certificats avec des configurations d’appareil](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="c6adf-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="c6adf-138">Utiliser le gestionnaire de [certificats](certificate-manager.md)d’appareil.</span><span class="sxs-lookup"><span data-stu-id="c6adf-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="c6adf-139">Méthode d’installation</span><span class="sxs-lookup"><span data-stu-id="c6adf-139">Installation method</span></span>

1. <span data-ttu-id="c6adf-140">Vérifiez que votre appareil n’est pas considéré comme géré.</span><span class="sxs-lookup"><span data-stu-id="c6adf-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="c6adf-141">Vérifiez que votre appareil HoloLens 2 est allumé et que vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="c6adf-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="c6adf-142">Sur votre PC, accédez à votre application personnalisée, puis copiez le fichier VotreApplication. appxbundle sur yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="c6adf-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="c6adf-143">Lorsque vous avez terminé la copie de votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation plus tard.</span><span class="sxs-lookup"><span data-stu-id="c6adf-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="c6adf-144">Sur votre appareil HoloLens 2, ouvrez le **menu Démarrer**, sélectionnez **toutes les applications** , puis lancez l’application **Explorateur de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="c6adf-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="c6adf-145">Accédez au dossier téléchargements.</span><span class="sxs-lookup"><span data-stu-id="c6adf-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="c6adf-146">Vous pouvez être amené à vous rendre dans le volet gauche de l’application sélectionnez **ce dernier** d’abord, puis accéder à téléchargements.</span><span class="sxs-lookup"><span data-stu-id="c6adf-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="c6adf-147">Sélectionnez le fichier VotreApplication. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="c6adf-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="c6adf-148">Le programme d’installation de l’application démarre.</span><span class="sxs-lookup"><span data-stu-id="c6adf-148">The App Installer will launch.</span></span> <span data-ttu-id="c6adf-149">Sélectionnez le bouton **installer** pour installer votre application.</span><span class="sxs-lookup"><span data-stu-id="c6adf-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="c6adf-150">L’application installée s’ouvre automatiquement lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="c6adf-150">The installed app will automatically launch upon the completion of installing.</span></span>

![Installation des exemples MRTK via le programme d’installation de l’application](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="c6adf-152">Résolution des problèmes d’installation</span><span class="sxs-lookup"><span data-stu-id="c6adf-152">Troubleshooting Installs</span></span>

<span data-ttu-id="c6adf-153">Si votre application n’a pas réussi à installer, consultez les rubriques suivantes pour résoudre les problèmes:</span><span class="sxs-lookup"><span data-stu-id="c6adf-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="c6adf-154">Votre application est une build de type maître ou version Release.</span><span class="sxs-lookup"><span data-stu-id="c6adf-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="c6adf-155">Votre appareil est mis à jour vers une build sur laquelle cette fonctionnalité est disponible.</span><span class="sxs-lookup"><span data-stu-id="c6adf-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="c6adf-156">Vous êtes [connecté à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="c6adf-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="c6adf-157">Vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="c6adf-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="c6adf-158">Programme d’installation Web</span><span class="sxs-lookup"><span data-stu-id="c6adf-158">Web Installer</span></span>

<span data-ttu-id="c6adf-159">Les utilisateurs peuvent installer une application directement à partir d’un serveur Web.</span><span class="sxs-lookup"><span data-stu-id="c6adf-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="c6adf-160">Ce flux utilise le programme d’installation de l’application associé à une méthode simple de distribution et d’installation.</span><span class="sxs-lookup"><span data-stu-id="c6adf-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="c6adf-161">Configuration de l’installation Web:</span><span class="sxs-lookup"><span data-stu-id="c6adf-161">How to set up web install:</span></span>

1. <span data-ttu-id="c6adf-162">Assurez-vous que votre application est correctement configurée pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="c6adf-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="c6adf-163">Procédez comme [suit pour activer l’installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="c6adf-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="c6adf-164">Utilisation de l’utilisateur final:</span><span class="sxs-lookup"><span data-stu-id="c6adf-164">End user experience:</span></span>

1. <span data-ttu-id="c6adf-165">Un utilisateur reçoit et installe un certificat sur l’appareil à l’aide de la méthode choisie précédemment.</span><span class="sxs-lookup"><span data-stu-id="c6adf-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="c6adf-166">Un utilisateur visite l’URL créée à l’étape ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="c6adf-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="c6adf-167">L’application sera désormais installée sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c6adf-167">The app will now install to the device.</span></span> <span data-ttu-id="c6adf-168">Pour Rechercher l’application, ouvrez le **menu Démarrer** , puis sélectionnez le bouton **toutes les applications** pour rechercher votre application.</span><span class="sxs-lookup"><span data-stu-id="c6adf-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="c6adf-169">Pour obtenir de l’aide sur la résolution des problèmes d’installation de l’application, consultez [résoudre les problèmes du programme](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)d’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="c6adf-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="c6adf-170">Le processus de mise à jour de l’interface utilisateur n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c6adf-170">UI during the update process is not supported.</span></span> <span data-ttu-id="c6adf-171">Par conséquent, l’option ShowPrompt sur [cette page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) et les options associées ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="c6adf-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="c6adf-172">Exemples d’applications</span><span class="sxs-lookup"><span data-stu-id="c6adf-172">Sample Apps</span></span>

<span data-ttu-id="c6adf-173">Pour tester le programme d’installation de l’application avec quelques exemples d’applications, consultez la rubrique Voici quelques exemples disponibles:</span><span class="sxs-lookup"><span data-stu-id="c6adf-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="c6adf-174">MRTK-hubs</span><span class="sxs-lookup"><span data-stu-id="c6adf-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="c6adf-175">Freins</span><span class="sxs-lookup"><span data-stu-id="c6adf-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="c6adf-176">Exemples d’applications UWP pouvant être utilisés à des fins de test</span><span class="sxs-lookup"><span data-stu-id="c6adf-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
