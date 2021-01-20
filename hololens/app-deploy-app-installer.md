---
title: Comment charger et installer des applications de manière latérale via le programme d’installation d’application HoloLens 2
description: Chargement des diapositives et installation d’applications via l’interface utilisateur
keywords: gestion des applications, application, hololens, programme d’installation d’application
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
ms.openlocfilehash: ab0c58d5a97d5dbaf83adf321d1f9fbc01b3ad03
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280653"
---
# <span data-ttu-id="06367-104">Installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="06367-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="06367-105">Cette fonctionnalité a été mise à disposition [dans Windows Holographique, version 20H2 – Mise](hololens-release-notes.md)à jour de décembre 2020.</span><span class="sxs-lookup"><span data-stu-id="06367-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="06367-106">Assurez-vous que votre appareil [est mis à jour](hololens-update-hololens.md) pour utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="06367-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="06367-107">Nous avons ajouté une nouvelle fonctionnalité **(Programme** d’installation d’application) pour vous permettre d’installer des applications plus facilement sur vos appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="06367-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="06367-108">La fonctionnalité sera sur par défaut pour les appareils **nonmanagés.**</span><span class="sxs-lookup"><span data-stu-id="06367-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="06367-109">Pour éviter toute perturbation pour les entreprises, le programme d’installation d’application ne sera pas disponible pour les appareils **gérés** pour le moment.</span><span class="sxs-lookup"><span data-stu-id="06367-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="06367-110">Un appareil est considéré comme « géré » si **l’une** des valeurs suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="06367-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="06367-111">Inscrit à la [gestion des mdm](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="06367-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="06367-112">Configuré avec le [package d’approvisionnement](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="06367-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="06367-113">[L’identité de l’utilisateur](hololens-identity.md) est Azure AD</span><span class="sxs-lookup"><span data-stu-id="06367-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="06367-114">Vous pouvez désormais installer des applications sans avoir besoin d’activer le mode développeur ou d’utiliser Device Portal.</span><span class="sxs-lookup"><span data-stu-id="06367-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="06367-115">Téléchargez (via USB ou Microsoft Edge) l’ensemble d’applications sur votre appareil et accédez à l’ensemble d’applications dans l’Explorateur de fichiers pour être invité à lancer l’installation.</span><span class="sxs-lookup"><span data-stu-id="06367-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="06367-116">Vous pouvez également [lancer une installation à partir d’une page web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="06367-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="06367-117">Tout comme les applications que vous installez à partir du Microsoft Store ou chargez une version [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) de version [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) à l’aide de la fonctionnalité de déploiement d’applications LOB de MDM, les applications doivent être signées numériquement avec l’outil de signature et le certificat utilisé pour la signature doit être approuvé par l’appareil HoloLens avant que l’application puisse être déployée.</span><span class="sxs-lookup"><span data-stu-id="06367-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="06367-118">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="06367-118">Requirements</span></span>

### <span data-ttu-id="06367-119">Pour vos appareils :</span><span class="sxs-lookup"><span data-stu-id="06367-119">For your devices:</span></span>

 <span data-ttu-id="06367-120">est actuellement disponible dans les builds Windows Holographic 20H2 pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="06367-120">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="06367-121">Assurez-vous que tous les appareils utilisant cette [méthode sont mis à jour.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="06367-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="06367-122">Pour vos applications :</span><span class="sxs-lookup"><span data-stu-id="06367-122">For your apps:</span></span> 
<span data-ttu-id="06367-123">La configuration de la solution de votre application doit **être** Master ou **Release,** car le programme d’installation d’application utilisera les dépendances du Store.</span><span class="sxs-lookup"><span data-stu-id="06367-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="06367-124">En savoir plus sur [la création de packages d’application.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="06367-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="06367-125">Les applications installées via cette méthode doivent être signées numériquement.</span><span class="sxs-lookup"><span data-stu-id="06367-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="06367-126">Vous devez utiliser un certificat pour signer l’application.</span><span class="sxs-lookup"><span data-stu-id="06367-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="06367-127">Vous pouvez obtenir un certificat à partir de la liste des ca de confiance [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)auquel cas vous n’aurez pas besoin d’action supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="06367-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="06367-128">Vous pouvez également signer votre propre certificat, mais ce certificat devra être poussée sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="06367-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="06367-129">Comment signer des applications à [l’aide de l’outil De signature.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="06367-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="06367-130">Options de certificat :</span><span class="sxs-lookup"><span data-stu-id="06367-130">Certificate options:</span></span>**

- [<span data-ttu-id="06367-131">Liste MS Trusted CA</span><span class="sxs-lookup"><span data-stu-id="06367-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="06367-132">Choisissez une méthode de déploiement de certificat.</span><span class="sxs-lookup"><span data-stu-id="06367-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="06367-133">[Les packages d’approvisionnement](hololens-provisioning.md) peuvent être appliqués aux appareils locaux.</span><span class="sxs-lookup"><span data-stu-id="06367-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="06367-134">La gestion des périphériques de gestion des périphériques peut être utilisée [pour appliquer des certificats avec des configurations d’appareil.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="06367-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="06367-135">Utilisez le Gestionnaire de certificats [sur l’appareil.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="06367-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="06367-136">Méthode d’installation</span><span class="sxs-lookup"><span data-stu-id="06367-136">Installation method</span></span>

1. <span data-ttu-id="06367-137">Vérifiez que votre appareil n’est pas considéré comme géré.</span><span class="sxs-lookup"><span data-stu-id="06367-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="06367-138">Vérifiez que votre appareil HoloLens 2 est sous tension et que vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="06367-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="06367-139">Sur votre PC, accédez à votre application personnalisée et copiez votre application.appxbundle dans votredevicename\Stockage interne\Téléchargements.</span><span class="sxs-lookup"><span data-stu-id="06367-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="06367-140">Une fois que vous avez terminé la copie de votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="06367-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="06367-141">À partir de votre appareil HoloLens 2, ouvrez le **menu Démarrer,** sélectionnez Toutes les **applications** et lancez l’application **Explorateur de** fichiers.</span><span class="sxs-lookup"><span data-stu-id="06367-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="06367-142">Accédez au dossier Téléchargements.</span><span class="sxs-lookup"><span data-stu-id="06367-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="06367-143">Dans le panneau gauche de l’application, sélectionnez d’abord Cet **appareil,** puis accédez à Téléchargements.</span><span class="sxs-lookup"><span data-stu-id="06367-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="06367-144">Sélectionnez le fichier yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="06367-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="06367-145">Le programme d’installation d’application se lance.</span><span class="sxs-lookup"><span data-stu-id="06367-145">The App Installer will launch.</span></span> <span data-ttu-id="06367-146">Sélectionnez le **bouton** Installer pour installer votre application.</span><span class="sxs-lookup"><span data-stu-id="06367-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="06367-147">L’application installée se lance automatiquement à la fin de l’installation.</span><span class="sxs-lookup"><span data-stu-id="06367-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installation d’exemples MRTK via le programme d’installation d’application](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="06367-149">Résolution des problèmes d’installation</span><span class="sxs-lookup"><span data-stu-id="06367-149">Troubleshooting Installs</span></span>

<span data-ttu-id="06367-150">Si l’installation de votre application a échoué, vérifiez les problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="06367-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="06367-151">Votre application est une build Master ou Release.</span><span class="sxs-lookup"><span data-stu-id="06367-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="06367-152">Votre appareil est mis à jour vers une build sur laquelle cette fonctionnalité est disponible.</span><span class="sxs-lookup"><span data-stu-id="06367-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="06367-153">Vous êtes [connecté à Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="06367-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="06367-154">Vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="06367-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="06367-155">Programme d’installation web</span><span class="sxs-lookup"><span data-stu-id="06367-155">Web Installer</span></span>

<span data-ttu-id="06367-156">Les utilisateurs peuvent installer une application directement à partir d’un serveur web.</span><span class="sxs-lookup"><span data-stu-id="06367-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="06367-157">Ce flux utilise le Programme d’installation d’application combiné à une méthode de distribution de téléchargement et d’installation simple.</span><span class="sxs-lookup"><span data-stu-id="06367-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="06367-158">Comment configurer l’installation web :</span><span class="sxs-lookup"><span data-stu-id="06367-158">How to set up web install:</span></span>

1. <span data-ttu-id="06367-159">Assurez-vous que votre application est correctement configurée pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="06367-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="06367-160">Suivez ces [étapes pour activer l’installation à partir d’une page web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="06367-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="06367-161">Expérience utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="06367-161">End user experience:</span></span>

1. <span data-ttu-id="06367-162">L’utilisateur reçoit et installe le certificat sur l’appareil à l’aide d’une méthode précédemment choisie ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="06367-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="06367-163">L’utilisateur visite l’URL créée à partir de l’étape ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="06367-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="06367-164">L’application s’installe maintenant sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="06367-164">The app will now install to the device.</span></span> <span data-ttu-id="06367-165">Pour trouver l’application, ouvrez **le menu Démarrer** et sélectionnez le bouton Toutes les **applications** pour trouver votre application.</span><span class="sxs-lookup"><span data-stu-id="06367-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="06367-166">Pour plus d’informations sur la résolution des problèmes de la méthode d’installation du programme d’installation d’application, consultez [la vidéo de résolution des problèmes du programme d’installation d’application.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="06367-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="06367-167">L’interface utilisateur pendant le processus de mise à jour n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="06367-167">UI during the update process is not supported.</span></span> <span data-ttu-id="06367-168">Ainsi, l’option ShowPrompt sur [cette page et](https://docs.microsoft.com/windows/msix/app-installer/update-settings) les options associées ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="06367-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="06367-169">Exemples d’applications</span><span class="sxs-lookup"><span data-stu-id="06367-169">Sample Apps</span></span>

<span data-ttu-id="06367-170">Pour essayer le Programme d’installation d’application avec quelques exemples d’applications, consultez certains de nos exemples disponibles :</span><span class="sxs-lookup"><span data-stu-id="06367-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="06367-171">Hub d’exemples MRTK</span><span class="sxs-lookup"><span data-stu-id="06367-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="06367-172">Surfaces</span><span class="sxs-lookup"><span data-stu-id="06367-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="06367-173">Exemples d’applications UWP qui peuvent être utilisés pour le test</span><span class="sxs-lookup"><span data-stu-id="06367-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
