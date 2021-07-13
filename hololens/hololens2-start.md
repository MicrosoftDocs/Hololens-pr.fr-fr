---
title: Configurer votre HoloLens 2
description: Découvrez comment configurer votre réseau HoloLens 2 pour la première fois sur Wi-Fi avec un compte Microsoft (MSA) ou Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923715"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="ae59c-104">Configurer votre HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ae59c-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="ae59c-105">Lorsque vous allumez votre HoloLens pour la première fois, vous êtes guidé pour la configuration de votre appareil, la connexion avec un compte d’utilisateur et l’étalonnage de HoloLens pour vos yeux.</span><span class="sxs-lookup"><span data-stu-id="ae59c-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="ae59c-106">Cette section décrit la configuration initiale de l’appareil HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ae59c-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="ae59c-107">Dans la section suivante, vous découvrirez comment utiliser HoloLens et interagir avec des hologrammes.</span><span class="sxs-lookup"><span data-stu-id="ae59c-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="ae59c-108">Pour passer directement à cet article, consultez [Explorer HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="ae59c-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="ae59c-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ae59c-109">Before you start</span></span>

<span data-ttu-id="ae59c-110">Avant de commencer, assurez-vous de disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ae59c-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="ae59c-111">**Une connexion réseau**.</span><span class="sxs-lookup"><span data-stu-id="ae59c-111">**A network connection**.</span></span> <span data-ttu-id="ae59c-112">Vous devez connecter votre HoloLens à un réseau pour le configurer.</span><span class="sxs-lookup"><span data-stu-id="ae59c-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="ae59c-113">Avec HoloLens 2, vous pouvez vous connecter à un réseau Wi-Fi ou utiliser Ethernet (moyennant un adaptateur USB-C vers Ethernet).</span><span class="sxs-lookup"><span data-stu-id="ae59c-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="ae59c-114">La première fois que vous le connectez, vous avez besoin d’un réseau ouvert ou protégé par mot de passe qui ne nécessite pas d’accès à un site web ou l’utilisation de certificats pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="ae59c-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="ae59c-115">[Apprenez-en davantage sur les sites web utilisés par HoloLens](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="ae59c-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="ae59c-116">**Un compte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ae59c-116">**A Microsoft account**.</span></span> <span data-ttu-id="ae59c-117">Vous devez également vous connecter à HoloLens avec un compte Microsoft (ou avec votre compte professionnel, si l’appareil appartient à votre organisation).</span><span class="sxs-lookup"><span data-stu-id="ae59c-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="ae59c-118">Si vous n’avez pas de compte Microsoft, accédez à [account.microsoft.com](https://account.microsoft.com) et configurez-en un gratuitement.</span><span class="sxs-lookup"><span data-stu-id="ae59c-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="ae59c-119">**Un espace sûr et bien éclairé, sans danger**.</span><span class="sxs-lookup"><span data-stu-id="ae59c-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="ae59c-120">[Informations sur l’intégrité et la sécurité](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="ae59c-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="ae59c-121">**Les accessoires de confort facultatifs** fournis avec votre HoloLens, pour vous aider à obtenir l’ajustement le plus confortable.</span><span class="sxs-lookup"><span data-stu-id="ae59c-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="ae59c-122">[Apprenez-en davantage sur l’ajustement et le confort](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="ae59c-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="ae59c-123">Configuration de Windows</span><span class="sxs-lookup"><span data-stu-id="ae59c-123">Set up Windows</span></span>

<span data-ttu-id="ae59c-124">Lorsque vous démarrez votre HoloLens 2 pour la première fois, vous devez d’abord configurer Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="ae59c-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="ae59c-125">Au démarrage de votre HoloLens, vous entendez de la musique et le logo Windows s’affiche.</span><span class="sxs-lookup"><span data-stu-id="ae59c-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Premier écran au cours du premier démarrage](images/01-magic-moment.png)

<span data-ttu-id="ae59c-127">HoloLens 2 vous guide au cours des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ae59c-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="ae59c-128">Sélectionnez votre langue.</span><span class="sxs-lookup"><span data-stu-id="ae59c-128">Select your language.</span></span>

    ![Sélectionnez une langue](images/04-language.png)

1. <span data-ttu-id="ae59c-130">Sélectionnez votre région.</span><span class="sxs-lookup"><span data-stu-id="ae59c-130">Select your region.</span></span>

    ![Sélectionner la région](images/05-region.png)

1. <span data-ttu-id="ae59c-132">Étalonnez HoloLens pour vos yeux.</span><span class="sxs-lookup"><span data-stu-id="ae59c-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="ae59c-133">Si vous choisissez d’ignorer l’étalonnage, vous serez invité à l’effectuer lors de votre prochaine connexion.</span><span class="sxs-lookup"><span data-stu-id="ae59c-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="ae59c-134">Tout d’abord, vous allez ajuster votre visière.</span><span class="sxs-lookup"><span data-stu-id="ae59c-134">First, you'll adjust your visor.</span></span>
    
        ![Écran de sélection de l’étalonnage](images/06-et-corners.png)

    2. <span data-ttu-id="ae59c-136">Pour cet étalonnage, vous examinez un ensemble de cibles (appelées « gemmes »).</span><span class="sxs-lookup"><span data-stu-id="ae59c-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="ae59c-137">Vous pouvez cligner des yeux ou les fermer lors de l’étalonnage, mais vous ne pouvez pas regarder d’autres objets de la pièce ou de l’espace physique.</span><span class="sxs-lookup"><span data-stu-id="ae59c-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="ae59c-138">HoloLens utilise ce processus pour détecter la position de vos yeux et améliorer ainsi le rendu de votre univers holographique.</span><span class="sxs-lookup"><span data-stu-id="ae59c-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Ajuster à votre vue](images/07-adjust-eyes.png)

        <span data-ttu-id="ae59c-140">Après l'étalonnage, les hologrammes s'affichent correctement, même si la visière bouge sur votre tête.</span><span class="sxs-lookup"><span data-stu-id="ae59c-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="ae59c-141">Les informations d’étalonnage sont stockées localement sur l’appareil et ne sont associées à aucune information de compte.</span><span class="sxs-lookup"><span data-stu-id="ae59c-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="ae59c-142">Pour plus d’informations, consultez [Données d’étalonnage et sécurité](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="ae59c-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![L’étalonnage est terminé](images/calibration-complete.png)

1. <span data-ttu-id="ae59c-144">Connectez-vous à Internet (sélectionnez Wi-Fi ou votre connexion Ethernet).</span><span class="sxs-lookup"><span data-stu-id="ae59c-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="ae59c-145">HoloLens définit automatiquement votre fuseau horaire en fonction des informations obtenues du réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ae59c-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="ae59c-146">Une fois l’installation terminée, vous pouvez modifier le fuseau horaire à l’aide de l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="ae59c-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Se connecter au Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="ae59c-148">Si vous avez terminé l’étape relative au Wi-Fi et devez ensuite basculer vers un autre réseau durant la configuration, vous pouvez appuyer simultanément sur les boutons de **Baisser le volume** and **Alimentation** pour revenir à cette étape si vous exécutez une version du système d’exploitation datant d'octobre 2019 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ae59c-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="ae59c-149">Pour les versions antérieures, vous devrez peut-être [réinitialiser l’appareil](hololens-recovery.md) ou le redémarrer à un endroit où le réseau Wi-Fi n’est pas disponible afin d'empêcher une connexion automatique.</span><span class="sxs-lookup"><span data-stu-id="ae59c-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="ae59c-150">Notez également que lors de l’installation d’HoloLens, le délai d’expiration des informations d’identification est de deux minutes.</span><span class="sxs-lookup"><span data-stu-id="ae59c-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="ae59c-151">Le nom d’utilisateur/mot de passe doit être entré dans les deux minutes, à défaut de quoi le champ du nom d’utilisateur sera automatiquement effacé.</span><span class="sxs-lookup"><span data-stu-id="ae59c-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="ae59c-152">HoloLens 2 recherchera et appliquera un profil Autopilot, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ae59c-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="ae59c-153">Aucune action n’est requise sur cet écran.</span><span class="sxs-lookup"><span data-stu-id="ae59c-153">No action is needed on this screen.</span></span>
 
    ![Recherche de profil Autopilot](images/autopilot-profile-search.png) 

1. <span data-ttu-id="ae59c-155">Dans l’écran de licence, cliquez sur **Accepter** .</span><span class="sxs-lookup"><span data-stu-id="ae59c-155">Click **Accept** on the licensing screen.</span></span>

    ![Contrat de licence Windows](images/windows-license-agreement.png)

1. <span data-ttu-id="ae59c-157">Connectez-vous à votre compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ae59c-157">Sign in to your user account.</span></span> <span data-ttu-id="ae59c-158">Choisissez **Il appartient à mon entreprise** ou **Il m’appartient**.</span><span class="sxs-lookup"><span data-stu-id="ae59c-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="ae59c-159">Si vous choisissez **Il appartient à mon entreprise ou à mon établissement**, vous vous connectez avec un compte Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ae59c-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="ae59c-160">Si votre organisation utilise Azure AD Premium et qu’elle a configuré l’inscription GPM automatique, HoloLens s’inscrit automatiquement dans GPM.</span><span class="sxs-lookup"><span data-stu-id="ae59c-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="ae59c-161">Si votre organisation n’utilise pas Azure AD Premium, l’inscription GPM automatique n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="ae59c-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="ae59c-162">Dans ce cas, vous devez [inscrire manuellement HoloLens dans la gestion des appareils](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="ae59c-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="ae59c-163">Entrez les informations de votre compte professionnel.</span><span class="sxs-lookup"><span data-stu-id="ae59c-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="ae59c-164">Acceptez la déclaration de confidentialité et le contrat de licence utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="ae59c-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="ae59c-165">Connectez-vous à l’aide de vos informations d’identification Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ae59c-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="ae59c-166">Cela pourra vous rediriger vers la page de connexion de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ae59c-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="ae59c-167">Poursuivez la configuration de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ae59c-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="ae59c-168">Lorsque vous choisissez **Il m'appartient**, vous vous connectez avec un compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae59c-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="ae59c-169">Une fois l’installation terminée, vous pouvez [inscrire manuellement HoloLens dans la gestion des périphériques](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="ae59c-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="ae59c-170">Entrez les informations de votre compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae59c-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="ae59c-171">Saisissez votre mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ae59c-171">Enter your password.</span></span> <span data-ttu-id="ae59c-172">Si votre compte Microsoft nécessite une [vérification en deux étapes (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), achevez le processus de vérification.</span><span class="sxs-lookup"><span data-stu-id="ae59c-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Définir l’utilisateur](images/13-device-owner.png)

1. <span data-ttu-id="ae59c-174">Configurez la connexion par reconnaissance de l’iris en sélectionnant **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ae59c-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="ae59c-175">Vous accéderez à une expérience similaire à l’étalonnage oculaire.</span><span class="sxs-lookup"><span data-stu-id="ae59c-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="ae59c-176">Sélectionnez **Terminé** une fois l’analyse terminée.</span><span class="sxs-lookup"><span data-stu-id="ae59c-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="ae59c-177">Vous pouvez également sélectionner **Ignorer** pour ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="ae59c-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="ae59c-178">![Configuration de l’iris](images/setup-iris.png) ![Fin de la configuration de l’iris](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="ae59c-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="ae59c-179">Vous allez configurer un code PIN pour vous connecter à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ae59c-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="ae59c-180">Ce code PIN est spécifique à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ae59c-180">This PIN is device specific.</span></span> 

    ![Configurer Windows Hello](images/setup-windows-hello.png)

    ![Configurer le code PIN Windows Hello](images/windows-hello-pin.png)

    ![Configuration de Windows Hello réussie](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="ae59c-184">Indiquez si vous souhaitez activer la reconnaissance vocale sur HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ae59c-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Activer Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="ae59c-186">Indiquez si vous souhaitez activer la localisation sur HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ae59c-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Activer les services de localisation](images/setup-location-services.png)

1. <span data-ttu-id="ae59c-188">Sélectionnez votre niveau de télémétrie.</span><span class="sxs-lookup"><span data-stu-id="ae59c-188">Select your telemetry level.</span></span> <span data-ttu-id="ae59c-189">Si possible, activez la télémétrie facultative.</span><span class="sxs-lookup"><span data-stu-id="ae59c-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="ae59c-190">Ces informations seront d’une grande aide pour l’équipe d’ingénierie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ae59c-190">This information really helps the HoloLens engineering team.</span></span>

     ![Niveau de télémétrie](images/24-telemetry.png)

1. <span data-ttu-id="ae59c-192">Découvrez comment utiliser le mouvement associé au menu Démarrer sur HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ae59c-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Découvrez comment utiliser le mouvement associé au menu Démarrer, image 1](images/26-01-startmenu-learning.png)

     ![Découvrez comment utiliser le mouvement associé au menu Démarrer, image 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="ae59c-195">Félicitations !</span><span class="sxs-lookup"><span data-stu-id="ae59c-195">Congratulations!</span></span>  <span data-ttu-id="ae59c-196">La configuration est terminée et vous êtes prêt à utiliser HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ae59c-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae59c-197">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ae59c-197">Next steps</span></span>

1. <span data-ttu-id="ae59c-198">Commencez sans plus attendre à interagir avec la réalité mixte et à naviguer dans Windows 10 sur votre HoloLens : consultez l'application **Astuces** pour accéder à des tutoriels pratiques sur les interactions avec la main.</span><span class="sxs-lookup"><span data-stu-id="ae59c-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="ae59c-199">Utilisez le mouvement associé au menu Démarrer ou dites « Menu Démarrer », puis sélectionnez Astuces.</span><span class="sxs-lookup"><span data-stu-id="ae59c-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="ae59c-200">Cliquez sur les liens ci-dessous pour en savoir plus sur l'HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ae59c-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ae59c-201">Explorer HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ae59c-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
