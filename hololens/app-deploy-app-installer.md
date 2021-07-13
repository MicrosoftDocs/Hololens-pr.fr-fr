---
title: guide pratique pour charger et installer des applications via HoloLens 2 programme d’installation de l’application
description: Apprenez à installer et à dépanner des applications avec le programme d’installation d’application et à charger et installer des applications par le biais de l’interface utilisateur.
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635583"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="34fed-104">installer des applications sur HoloLens 2 via le programme d’installation d’application</span><span class="sxs-lookup"><span data-stu-id="34fed-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="34fed-105">cette fonctionnalité a été [mise à disposition dans Windows holographique, version 20H2-mise à jour de décembre 2020](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="34fed-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="34fed-106">Assurez-vous que votre appareil est [mis à jour](hololens-update-hololens.md) pour utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="34fed-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="34fed-107">nous avons **ajouté une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications de manière plus transparente** sur vos appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="34fed-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="34fed-108">La fonctionnalité est **activée par défaut pour les appareils non gérés**.</span><span class="sxs-lookup"><span data-stu-id="34fed-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="34fed-109">Pour éviter toute interruption des entreprises, le programme d’installation de l’application ne sera **pas disponible pour les appareils gérés** à l’heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="34fed-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="34fed-110">Un appareil est considéré comme « géré » si l' **une** des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="34fed-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="34fed-111">MDM [inscrit](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="34fed-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="34fed-112">Configuré avec le [package d’approvisionnement](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="34fed-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="34fed-113">L' [identité](hololens-identity.md) de l’utilisateur est Azure ad</span><span class="sxs-lookup"><span data-stu-id="34fed-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="34fed-114">Vous êtes maintenant en mesure d’installer des applications sans avoir à activer le mode développeur ou à l’aide du portail des appareils.</span><span class="sxs-lookup"><span data-stu-id="34fed-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="34fed-115">téléchargez (sur USB ou via Microsoft Edge) le bundle appx sur votre appareil et accédez au bundle appx dans l’explorateur de fichiers pour être invité à lancer l’installation.</span><span class="sxs-lookup"><span data-stu-id="34fed-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="34fed-116">Vous pouvez également [lancer une installation à partir d’une page Web](/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="34fed-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="34fed-117">tout comme les applications que vous installez à partir de la Microsoft Store ou chargement à l’aide de la fonctionnalité de déploiement d’applications métier MDM, les applications doivent être signées numériquement avec l' [outil sign](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour la signature doit être approuvé](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens pour que l’application puisse être déployée.</span><span class="sxs-lookup"><span data-stu-id="34fed-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="34fed-118">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="34fed-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="34fed-119">Pour vos appareils :</span><span class="sxs-lookup"><span data-stu-id="34fed-119">For your devices:</span></span>

<span data-ttu-id="34fed-120">cette fonctionnalité est actuellement disponible dans Windows les builds 20H2 holographiques pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="34fed-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="34fed-121">Assurez-vous que tous les appareils qui utilisent cette méthode sont [mis à jour](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="34fed-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="34fed-122">Pour vos applications :</span><span class="sxs-lookup"><span data-stu-id="34fed-122">For your apps:</span></span>

<span data-ttu-id="34fed-123">La configuration de la solution de votre application doit être **Master** ou **Release** , car le programme d’installation de l’application utilisera les dépendances du magasin.</span><span class="sxs-lookup"><span data-stu-id="34fed-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="34fed-124">En savoir plus sur la [création de packages d’application](/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="34fed-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="34fed-125">Les applications qui sont installées par le biais de cette méthode doivent être signées numériquement.</span><span class="sxs-lookup"><span data-stu-id="34fed-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="34fed-126">Vous devez utiliser un certificat pour signer l’application.</span><span class="sxs-lookup"><span data-stu-id="34fed-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="34fed-127">Vous pouvez obtenir un certificat à partir de la [liste des autorités de certification de confiance MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). dans ce cas, vous n’aurez pas besoin d’effectuer d’action supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="34fed-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="34fed-128">Vous pouvez aussi signer votre propre certificat. Toutefois, ce certificat devra être envoyé sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="34fed-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="34fed-129">Comment signer des applications [à l’aide de l’outil Sign.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="34fed-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="34fed-130">**Options de certificat :**</span><span class="sxs-lookup"><span data-stu-id="34fed-130">**Certificate options:**</span></span>

- [<span data-ttu-id="34fed-131">Liste des autorités de certification de confiance MS</span><span class="sxs-lookup"><span data-stu-id="34fed-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="34fed-132">**Choisissez une méthode de déploiement de certificat.**</span><span class="sxs-lookup"><span data-stu-id="34fed-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="34fed-133">Les [packages d’approvisionnement](hololens-provisioning.md) peuvent être appliqués à des appareils locaux.</span><span class="sxs-lookup"><span data-stu-id="34fed-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="34fed-134">MDM peut être utilisé pour [appliquer des certificats avec des configurations d’appareil](/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="34fed-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="34fed-135">Utilisez le gestionnaire de [certificats](certificate-manager.md)de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="34fed-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="34fed-136">Méthode d’installation</span><span class="sxs-lookup"><span data-stu-id="34fed-136">Installation method</span></span>

1. <span data-ttu-id="34fed-137">Vérifiez que votre appareil n’est pas considéré comme géré.</span><span class="sxs-lookup"><span data-stu-id="34fed-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="34fed-138">vérifiez que votre appareil HoloLens 2 est sous tension et que vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="34fed-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="34fed-139">sur votre PC, accédez à votre application personnalisée et copiez votreapplication. appxbundle sur yourdevicename\Internal Stockage \Downloads.</span><span class="sxs-lookup"><span data-stu-id="34fed-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="34fed-140">Une fois que vous avez fini de copier votre fichier, vous pouvez déconnecter votre appareil et terminer l’installation ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="34fed-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="34fed-141">à partir de votre appareil HoloLens 2, ouvrez le **Menu démarrer**, sélectionnez **toutes les applications** , puis lancez l’application **explorateur de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="34fed-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="34fed-142">Accédez au dossier téléchargements.</span><span class="sxs-lookup"><span data-stu-id="34fed-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="34fed-143">Vous devrez peut-être dans le volet gauche de l’application sélectionner **cet appareil** en premier, puis accéder à téléchargements.</span><span class="sxs-lookup"><span data-stu-id="34fed-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="34fed-144">Sélectionnez le fichier VotreApplication. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="34fed-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="34fed-145">Le programme d’installation de l’application démarre.</span><span class="sxs-lookup"><span data-stu-id="34fed-145">The App Installer will launch.</span></span> <span data-ttu-id="34fed-146">Sélectionnez le bouton **installer** pour installer votre application.</span><span class="sxs-lookup"><span data-stu-id="34fed-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="34fed-147">L’application installée sera automatiquement lancée à la fin de l’installation de.</span><span class="sxs-lookup"><span data-stu-id="34fed-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Installation d’exemples MRTK via le programme d’installation d’application](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="34fed-149">Résolution des problèmes d’installation</span><span class="sxs-lookup"><span data-stu-id="34fed-149">Troubleshooting Installs</span></span>

<span data-ttu-id="34fed-150">Si votre application n’a pas pu être installée, vérifiez les éléments suivants pour résoudre les problèmes :</span><span class="sxs-lookup"><span data-stu-id="34fed-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="34fed-151">Votre application est une version principale ou une version Release.</span><span class="sxs-lookup"><span data-stu-id="34fed-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="34fed-152">Votre appareil est mis à jour vers une version sur laquelle cette fonctionnalité est disponible.</span><span class="sxs-lookup"><span data-stu-id="34fed-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="34fed-153">Vous êtes [connecté à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="34fed-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="34fed-154">vos [points de terminaison pour le Microsoft Store](hololens-offline.md) sont configurés correctement.</span><span class="sxs-lookup"><span data-stu-id="34fed-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="34fed-155">Programme d’installation web</span><span class="sxs-lookup"><span data-stu-id="34fed-155">Web Installer</span></span>

<span data-ttu-id="34fed-156">Les utilisateurs peuvent installer une application directement à partir d’un serveur Web.</span><span class="sxs-lookup"><span data-stu-id="34fed-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="34fed-157">Ce processus utilise le programme d’installation d’application associé à une méthode de distribution de téléchargement et d’installation facile.</span><span class="sxs-lookup"><span data-stu-id="34fed-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="34fed-158">Procédure de configuration de l’installation Web :</span><span class="sxs-lookup"><span data-stu-id="34fed-158">How to set up web install:</span></span>

1. <span data-ttu-id="34fed-159">Vérifiez que votre application est correctement configurée pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="34fed-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="34fed-160">[Pour activer l’installation à partir d’une page Web](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage), procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="34fed-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="34fed-161">Expérience de l’utilisateur final :</span><span class="sxs-lookup"><span data-stu-id="34fed-161">End user experience:</span></span>

1. <span data-ttu-id="34fed-162">L’utilisateur reçoit et installe le certificat sur l’appareil à l’aide d’une méthode précédemment choisie ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="34fed-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="34fed-163">L’utilisateur visite l’URL créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="34fed-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="34fed-164">L’application s’installe désormais sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="34fed-164">The app will now install to the device.</span></span> <span data-ttu-id="34fed-165">pour rechercher l’application, ouvrez le **menu Démarrer** , puis sélectionnez le bouton **toutes les applications** pour rechercher votre application.</span><span class="sxs-lookup"><span data-stu-id="34fed-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="34fed-166">Pour plus d’informations sur la résolution des problèmes liés à la méthode d’installation de l’application, consultez [résoudre les problèmes](/windows/msix/app-installer/troubleshoot-appinstaller-issues)liés au programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="34fed-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="34fed-167">L’interface utilisateur pendant le processus de mise à jour n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="34fed-167">UI during the update process is not supported.</span></span> <span data-ttu-id="34fed-168">Par conséquent, l’option ShowPrompt sur [cette page](/windows/msix/app-installer/update-settings) et les options associées ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="34fed-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="34fed-169">Exemples d’applications</span><span class="sxs-lookup"><span data-stu-id="34fed-169">Sample Apps</span></span>

<span data-ttu-id="34fed-170">Essayez le programme d’installation de l’application avec l’un de nos exemples d’applications disponibles.</span><span class="sxs-lookup"><span data-stu-id="34fed-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="34fed-171">Exemples d’application</span><span class="sxs-lookup"><span data-stu-id="34fed-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
