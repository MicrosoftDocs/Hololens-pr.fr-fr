---
title: Problèmes connus avec HoloLens
description: Restez à jour avec notre liste des problèmes connus et des solutions de contournement qui peuvent affecter les clients et les développeurs HoloLens à l’aide d’Unity et de Windows Device Portal.
keywords: résolution des problèmes, problème connu, aide
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284075"
---
# <span data-ttu-id="a2fd8-104">Problèmes connus avec HoloLens</span><span class="sxs-lookup"><span data-stu-id="a2fd8-104">Known issues for HoloLens</span></span>

<span data-ttu-id="a2fd8-105">Il s’agit de la liste actuelle des problèmes connus pour les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="a2fd8-106">Vérifiez d’abord ici si vous voyez un comportement impair.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="a2fd8-107">Cette liste sera mise à jour à mesure que de nouveaux problèmes seront détectés ou signalés, ou que des problèmes seront résolus dans les futures mises à jour logicielles HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="a2fd8-108">Si vous découvrez un problème qui ne bloque pas, signalez-le sur votre appareil HoloLens via [le Hub de commentaires.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="a2fd8-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="a2fd8-109">Si le problème que vous êtes confronté vous bloque, en plus de classer les commentaires, [déposez une demande de support.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="a2fd8-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="a2fd8-110">Problèmes connus pour toutes les générations HoloLens</span><span class="sxs-lookup"><span data-stu-id="a2fd8-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="a2fd8-111">Problèmes connus pour les appareils HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a2fd8-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="a2fd8-112">Problèmes connus pour HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="a2fd8-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="a2fd8-113">Problèmes connus pour l’émulateur HoloLens</span><span class="sxs-lookup"><span data-stu-id="a2fd8-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="a2fd8-114">Problèmes connus pour toutes les générations HoloLens</span><span class="sxs-lookup"><span data-stu-id="a2fd8-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="a2fd8-115">Unity</span><span class="sxs-lookup"><span data-stu-id="a2fd8-115">Unity</span></span>

- <span data-ttu-id="a2fd8-116">Voir [Installer les outils](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pour la version la plus récente d’Unity recommandée pour le développement HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="a2fd8-117">Les problèmes connus avec unity HoloLens Technical Preview sont documentés dans les [forums HoloLens Unity](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="a2fd8-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="a2fd8-118">WindowsDevicePortal</span><span class="sxs-lookup"><span data-stu-id="a2fd8-118">Windows Device Portal</span></span>

- <span data-ttu-id="a2fd8-119">La fonctionnalité Aperçu en direct dans la capture de réalité mixte peut présenter plusieurs secondes de latence.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="a2fd8-120">Dans la page Entrée virtuelle, les contrôles Mouvement et Défilement sous la section Mouvements virtuels ne sont pas fonctionnels.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="a2fd8-121">Leur utilisation n’aura aucun effet.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-121">Using them will have no effect.</span></span> <span data-ttu-id="a2fd8-122">Le clavier virtuel sur la même page fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-122">The virtual keyboard on the same page works correctly.</span></span>

- <span data-ttu-id="a2fd8-123">Après l’activation du Mode développeur dans Paramètres, l’activation du portail d’appareil peut prendre quelques secondes avant que le commutateur soit activé.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="a2fd8-124">Chargement de l’appareil photo OneDrive</span><span class="sxs-lookup"><span data-stu-id="a2fd8-124">OneDrive camera upload</span></span>

<span data-ttu-id="a2fd8-125">L’application OneDrive pour HoloLens ne prend pas en charge le chargement automatique de l’appareil photo pour les comptes scolaires ou de travail.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="a2fd8-126">Solutions de contournement :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-126">Workarounds:</span></span>

- <span data-ttu-id="a2fd8-127">S’il est viable pour votre entreprise, le chargement automatique d’appareil photo est pris en charge sur les comptes Microsoft grand public.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="a2fd8-128">Vous pouvez vous inscrire à votre compte Microsoft en plus de votre compte scolaire ou scolaire (l’application OneDrive prend en charge la double sign-in).</span><span class="sxs-lookup"><span data-stu-id="a2fd8-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="a2fd8-129">À partir de votre profil de compte Microsoft dans OneDrive, vous pouvez activer le chargement automatique de l’appareil photo en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="a2fd8-130">Si vous ne pouvez pas utiliser en toute sécurité un compte Microsoft grand public pour télécharger automatiquement vos photos, vous pouvez charger manuellement des photos sur votre compte scolaire ou scolaire à partir de l’application OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="a2fd8-131">Pour ce faire, assurez-vous que vous êtes bien inscrit à votre compte scolaire ou scolaire dans l’application OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="a2fd8-132">Sélectionnez **+** le bouton et choisissez **Télécharger.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="a2fd8-133">Recherchez les photos ou vidéos que vous souhaitez télécharger en naviguant vers **Images > pellicule .**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="a2fd8-134">Sélectionnez les photos ou vidéos que vous souhaitez télécharger, puis sélectionnez le **bouton** Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="a2fd8-135">Problèmes connus pour les appareils HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a2fd8-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="a2fd8-136">Le lancement de Microsoft Edge échoue</span><span class="sxs-lookup"><span data-stu-id="a2fd8-136">Microsoft Edge fails to launch</span></span>

<span data-ttu-id="a2fd8-137">Quelques clients ont signalé un problème dans lequel Microsoft Edge ne parvient pas à se lancer.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-137">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="a2fd8-138">Pour ces clients, le problème persiste lors du redémarrage et n’est pas résolu avec les mises à jour windows ou d’applications.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-138">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="a2fd8-139">Si vous rencontrez ce problème et que vous avez confirmé que [Windows](hololens-updates.md#manually-check-for-updates)est à [](hololens-feedback.md) jour, veuillez déposer un bogue à partir de l’application Hub de commentaires avec la catégorie et la sous-catégorie suivantes : Installer et mettre à jour les > Téléchargement, installation et configuration de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="a2fd8-140">Il n’existe aucune solution de contournement connue, car nous n’avons pas pu à l’origine du problème jusqu’à présent.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-140">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="a2fd8-141">Le classement d’un bogue via le Hub de commentaires nous aidera à faire l’objet d’une enquête !</span><span class="sxs-lookup"><span data-stu-id="a2fd8-141">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <span data-ttu-id="a2fd8-142">Le clavier ne bascule pas vers des caractères spéciaux</span><span class="sxs-lookup"><span data-stu-id="a2fd8-142">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="a2fd8-143">Il existe un problème lors de la OOBE, où une fois que l’utilisateur a choisi un compte scolaire ou scolaire et a entré son mot de passe, en essayant de basculer vers les caractères spéciaux du clavier en appuyant sur le bouton &123 ne change pas en caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-143">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="a2fd8-144">Les contourner :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-144">Work-arounds:</span></span>
-   <span data-ttu-id="a2fd8-145">Fermez le clavier et rouvrez-le en appuyant sur le champ de texte.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-145">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="a2fd8-146">Entrez votre mot de passe de manière incorrecte.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-146">Incorrectly enter your password.</span></span> <span data-ttu-id="a2fd8-147">Lorsque le clavier est relancé la prochaine fois, il fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-147">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="a2fd8-148">Authentification web, fermez le clavier et **sélectionnez Se connectez à partir d’un autre appareil.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-148">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="a2fd8-149">Si vous entrez uniquement des nombres, un utilisateur peut appuyer et maintenir certaines touches pour ouvrir un menu développé.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-149">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="a2fd8-150">Utilisation d’un clavier USB.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-150">Using a USB keyboard.</span></span>

<span data-ttu-id="a2fd8-151">Cela n’affecte pas :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-151">This does not affect:</span></span>
- <span data-ttu-id="a2fd8-152">Utilisateurs qui choisissent d’utiliser un compte personnel.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-152">Users who choose to use a personal account.</span></span>

### <span data-ttu-id="a2fd8-153">L’écran bleu s’affiche après la désinscrire des builds Insider Preview sur un appareil réessaillé avec une build Insider</span><span class="sxs-lookup"><span data-stu-id="a2fd8-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="a2fd8-154">This is an issue affecting that affects users who are on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unnrolled from the Insider program.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-154">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="a2fd8-155">Cela n’affecte pas :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-155">This does not affect:</span></span>
- <span data-ttu-id="a2fd8-156">Utilisateurs qui ne sont pas inscrits à Windows Insider</span><span class="sxs-lookup"><span data-stu-id="a2fd8-156">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="a2fd8-157">Insiders :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-157">Insiders:</span></span>
    - <span data-ttu-id="a2fd8-158">Si un appareil a été inscrit depuis la version 18362.x des builds Insider</span><span class="sxs-lookup"><span data-stu-id="a2fd8-158">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="a2fd8-159">S’ils ont flashé une build Insider 19041.x et restent inscrits au programme Insider</span><span class="sxs-lookup"><span data-stu-id="a2fd8-159">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="a2fd8-160">Contourner :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-160">Work-around:</span></span> 
- <span data-ttu-id="a2fd8-161">Éviter le problème</span><span class="sxs-lookup"><span data-stu-id="a2fd8-161">Avoid the issue</span></span> 
    - <span data-ttu-id="a2fd8-162">Flashez une build non insider.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-162">Flash a non-insider build.</span></span> <span data-ttu-id="a2fd8-163">Une des mises à jour mensuelles régulières.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-163">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="a2fd8-164">Restez sur Insider Preview</span><span class="sxs-lookup"><span data-stu-id="a2fd8-164">Stay on Insider Preview</span></span>
- <span data-ttu-id="a2fd8-165">Barre oblique inverse de l’appareil</span><span class="sxs-lookup"><span data-stu-id="a2fd8-165">Reflash the device</span></span>

    1. <span data-ttu-id="a2fd8-166">Mettez [manuellement l’HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) en mode clignotant en l’élémentant complètement sans se connecter.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-166">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="a2fd8-167">Ensuite, tout en maintenant le volume enfoncé, appuyez sur le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-167">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="a2fd8-168">Connectez-vous au PC et ouvrez Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-168">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    
    1. <span data-ttu-id="a2fd8-169">Flashez HoloLens 2 sur la build par défaut.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-169">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="a2fd8-170">Problèmes connus pour HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="a2fd8-170">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="a2fd8-171">Impossible de se connecter à HoloLens et de le déployer via Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a2fd8-171">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="a2fd8-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="a2fd8-173">Nous vous recommandons de mettre à jour cette dernière version pour éviter cette erreur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-173">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a2fd8-174">Visual Studio a publié VS 2019 Version 16.2, qui inclut un correctif à ce problème.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-174">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="a2fd8-175">Nous vous recommandons de mettre à jour cette dernière version pour éviter cette erreur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-175">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a2fd8-176">Cause première du problème : les utilisateurs qui ont utilisé Visual Studio 2015 ou les versions antérieures d’Visual Studio 2017 pour déployer et déboguer des applications sur leur HoloLens, puis qui ont ensuite utilisé les dernières versions de Visual Studio 2017 ou Visual Studio 2019 avec le même HoloLens seront affectés.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-176">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="a2fd8-177">Les versions les plus récentes de Visual Studio déploient une nouvelle version d’un composant, mais les fichiers de l’ancienne version sont laissés sur l’appareil, entraînant l’échec de la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-177">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="a2fd8-178">Cela provoque le message d’erreur suivant : DEP0100 : Assurez-vous que le mode développeur est activé sur l’appareil cible.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-178">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="a2fd8-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="a2fd8-180">Solution de contournement</span><span class="sxs-lookup"><span data-stu-id="a2fd8-180">Workaround</span></span>

<span data-ttu-id="a2fd8-181">Notre équipe travaille actuellement sur un correctif.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-181">Our team is currently working on a fix.</span></span> <span data-ttu-id="a2fd8-182">En attendant, vous pouvez utiliser les étapes suivantes pour contourner le problème et débloquer le déploiement et le débogage :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-182">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="a2fd8-183">Ouvrez Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-183">Open Visual Studio.</span></span>

1. <span data-ttu-id="a2fd8-184">Sélectionner **un nouveau**  >  **projet**de  >  **fichier.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-184">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a2fd8-185">Sélectionnez **Visual C#**  >  **Application de console**de bureau Windows  >  **(.NET Framework).**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-185">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="a2fd8-186">Donnez un nom au projet (par exemple, « HoloLensDeploymentFix ») et assurez-vous que l’infrastructure est définie sur au moins .NET Framework 4.5, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-186">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="a2fd8-187">Cliquez avec le bouton droit sur le nœud **Références** dans l’Explorateur de solutions et ajoutez les références suivantes (sélectionnez la **section** Parcourir et sélectionnez **Parcourir)**:</span><span class="sxs-lookup"><span data-stu-id="a2fd8-187">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="a2fd8-188">Si la version 10.0.18362.0 n’est pas installée, utilisez la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-188">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="a2fd8-189">Cliquez avec le bouton droit sur le projet dans l’Explorateur de solutions et **sélectionnez Ajouter**  >  **un élément existant.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-189">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="a2fd8-190">Accédez à C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 et modifiez le filtre en **All Files (\*.\*).**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-190">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="a2fd8-191">Sélectionnez les SirepClient.dll et SshClient.dll, puis sélectionnez **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-191">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="a2fd8-192">Recherchez et sélectionnez les deux fichiers dans l’Explorateur de solutions \*\*\*\* (ils doivent se \*\*\*\* trouver en bas de la liste des fichiers) et modifiez Copier dans le répertoire de sortie dans la fenêtre Propriétés pour toujours **copier.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-192">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="a2fd8-193">En haut du fichier, ajoutez ce qui suit à la liste `using` d’instructions existante :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-193">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="a2fd8-194">À `static void Main(...)` l’intérieur de , ajoutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-194">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="a2fd8-195">Sélectionnez \*\*\*\*  >  **Build Build Solution**.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-195">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="a2fd8-196">Ouvrez une fenêtre d’invite de commandes et cd vers le dossier qui contient le fichier .exe compilé (par exemple, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="a2fd8-196">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="a2fd8-197">Exécutez l’exécutable et fournissez l’adresse IP de l’appareil en tant qu’argument de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-197">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="a2fd8-198">(Si vous êtes connecté à l’aide d’une clé USB, vous pouvez utiliser 127.0.0.1, sinon utilisez l’adresse IP Wi-Fi'appareil.)  Par exemple, « HoloLensDeploymentFix 127.0.0.1 ».</span><span class="sxs-lookup"><span data-stu-id="a2fd8-198">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="a2fd8-199">Une fois l’outil sorti sans aucun message (cela ne devrait prendre que quelques secondes), vous pourrez désormais déployer et déboguer à partir d’Visual Studio 2017 ou d’une nouvelle génération.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-199">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="a2fd8-200">L’utilisation continue de l’outil n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-200">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="a2fd8-201">Nous fournirons d’autres mises à jour dès qu’elles seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-201">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="a2fd8-202">Problèmes lors du lancement du Microsoft Store et des applications sur HoloLens</span><span class="sxs-lookup"><span data-stu-id="a2fd8-202">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="a2fd8-203">Dernière mise à jour : 02/04/2010 - Problème résolu.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="a2fd8-204">Vous pouvez être face à des problèmes lors de la tentative de lancement du Microsoft Store et des applications sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-204">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="a2fd8-205">Nous avons déterminé que le problème se produit lorsque des mises à jour d’application en arrière-plan déploient une version plus récente des packages d’infrastructure dans des séquences spécifiques pendant qu’une ou plusieurs de leurs applications dépendantes sont toujours en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-205">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="a2fd8-206">Dans ce cas, une mise à jour automatique de l’application a remis une nouvelle version de .NET Native Framework (version 10.0.25531 à 10.0.27413) a provoqué une mise à jour non correcte des applications en cours d’exécution pour toutes les applications qui utilisent la version antérieure de l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-206">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="a2fd8-207">Le flux pour la mise à jour de l’infrastructure est le suivant :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-207">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="a2fd8-208">Le nouveau package d’infrastructure est téléchargé à partir du Store et installé.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-208">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="a2fd8-209">Toutes les applications utilisant l’ancienne infrastructure sont « mises à jour » pour utiliser la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-209">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="a2fd8-210">Si l’étape 2 est interrompue avant la fin, toutes les applications pour lesquelles la nouvelle infrastructure n’a pas été inscrite ne pourront pas être lancées à partir du menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-210">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="a2fd8-211">Nous pensons que n’importe quelle application sur HoloLens pourrait être affectée par ce problème.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-211">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="a2fd8-212">Certains utilisateurs ont signalé que la fermeture d’applications suspendues et le lancement d’autres applications telles que le Hub de commentaires, la visionneuse 3D ou Photos résout le problème pour eux. Toutefois, cela ne fonctionne pas 100 % du &mdash; temps.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-212">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="a2fd8-213">Nous avons dû à la racine que ce problème n’était pas à l’origine de la mise à jour proprement dite, mais d’un bogue dans le système d’exploitation qui a entraîné une gestion incorrecte de la mise à jour de .NET Native Framework.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-213">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="a2fd8-214">Nous sommes heureux d’annoncer que nous avons identifié un correctif et publié une mise à jour (os version 17763.380) contenant le correctif.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-214">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="a2fd8-215">Pour voir si votre appareil peut prendre la mise à jour, veuillez :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-215">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="a2fd8-216">Go to the Settings app and open **Update & Security**.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-216">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="a2fd8-217">Sélectionnez **Vérifier les mises à jour.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-217">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="a2fd8-218">Si la mise à jour vers 17763.380 est disponible, mettez à jour cette build pour recevoir le correctif du bogue d’hang de l’application.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-218">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="a2fd8-219">Lors de la mise à jour vers cette version du système d’exploitation, les applications doivent fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-219">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="a2fd8-220">En outre, comme nous le faisons avec chaque version du système d’exploitation HoloLens, nous avons publié l’image FFU dans le [Centre de téléchargement Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)</span><span class="sxs-lookup"><span data-stu-id="a2fd8-220">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="a2fd8-221">Si vous ne souhaitez pas prendre la mise à jour, nous avons publié une nouvelle version de l’application UWP du Microsoft Store à partir du 29/03/2013.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-221">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="a2fd8-222">Une fois que vous avez mis à jour la version du Store :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-222">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="a2fd8-223">Ouvrez le Store et confirmez son chargement.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-223">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="a2fd8-224">Utilisez le geste d’ouverture du menu à l’appel.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-224">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="a2fd8-225">Essayez d’ouvrir des applications précédemment rompues.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-225">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="a2fd8-226">Si elle ne peut toujours pas être lancée, appuyez et maintenez l’icône de l’application rompue, puis sélectionnez Désinstaller.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-226">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="a2fd8-227">Réinstallez ces applications à partir du Store.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-227">Re-install these apps from the store.</span></span>

<span data-ttu-id="a2fd8-228">Si votre appareil ne parvient toujours pas à charger des applications, vous pouvez charger une version de .NET Native Framework et d’Runtime via le centre de téléchargement en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a2fd8-228">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="a2fd8-229">Téléchargez [ce fichier zip à partir](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) du Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-229">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="a2fd8-230">Unzipping produit deux fichiers.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-230">Unzipping will produce two files.</span></span>  <span data-ttu-id="a2fd8-231">Microsoft.NET.Native.Runtime.1.7.appx et Microsoft.NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-231">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="a2fd8-232">Vérifiez que votre appareil est déverrouillé.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-232">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="a2fd8-233">Si vous ne l’avez pas encore fait, [consultez l’outil Utilisation](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) de Windows Device Portal pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-233">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="a2fd8-234">Vous souhaitez ensuite vous rendre dans Windows Device Portal.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-234">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="a2fd8-235">Il est recommandé de le faire sur USB, en tapant dans http://127.0.0.1:10080 votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-235">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="a2fd8-236">Une fois windows Device Portal en place, nous avons besoin que vous « chargez de côté » les deux fichiers que vous avez téléchargés.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-236">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="a2fd8-237">Pour ce faire, vous devez descendre dans la barre de gauche jusqu’à ce que vous arrivez à la section **Applications** et sélectionnez **Applications.**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-237">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="a2fd8-238">Vous verrez ensuite un écran semblable à celui ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-238">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="a2fd8-239">Vous souhaitez aller à la section qui indique **Installer** l’application et accédez à l’endroit où vous avez décompressé ces deux fichiers APPX.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-239">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="a2fd8-240">Vous ne pouvez en faire qu’une seule à la fois. Ainsi, après avoir sélectionné le premier, cliquez sur « Aller » dans la section Déployer.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-240">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="a2fd8-241">Ensuite, faites-le pour le deuxième fichier APPX.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-241">Then do this for the second APPX file.</span></span>

   ![Windows Device Portal pour installer Side-Loaded application](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="a2fd8-243">À ce stade, nous pensons que vos applications doivent recommencer à fonctionner et que vous pouvez également vous rendre dans le Store.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-243">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="a2fd8-244">Dans certains cas, il est nécessaire d’exécuter l’étape supplémentaire de lancement de l’application visionneuse 3D avant que les applications concernées ne se lancent.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-244">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="a2fd8-245">Nous vous remercions de votre patience au fil du processus de résolution de ce problème, et nous attendons avec intérêt de continuer à collaborer avec notre communauté pour créer des expériences de réalité mixte réussies.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-245">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="a2fd8-246">Mise à jour de périphérique</span><span class="sxs-lookup"><span data-stu-id="a2fd8-246">Device Update</span></span>

- <span data-ttu-id="a2fd8-247">30 secondes après une nouvelle mise à jour, l’shell peut disparaître une fois.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-247">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="a2fd8-248">Effectuez le geste **d’ouverture** pour reprendre votre session.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-248">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="a2fd8-249">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a2fd8-249">Visual Studio</span></span>

- <span data-ttu-id="a2fd8-250">Voir [Installer les outils](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pour la version la plus récente de Visual Studio recommandée pour le développement HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-250">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="a2fd8-251">Lors du déploiement d’une application de Visual Studio vers votre HoloLens, vous pouvez voir l’erreur : l’opération demandée ne peut pas être effectuée sur un fichier avec une section mappée par **l’utilisateur ouverte. (Exception de HRESULT : 0x800704C8).**</span><span class="sxs-lookup"><span data-stu-id="a2fd8-251">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="a2fd8-252">Si cela se produit, essayez à nouveau et votre déploiement réussit généralement.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-252">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="a2fd8-253">API</span><span class="sxs-lookup"><span data-stu-id="a2fd8-253">API</span></span>

- <span data-ttu-id="a2fd8-254">Si l’application définit le [point de focus](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) derrière l’utilisateur ou la normale sur camera.forward, les hologrammes n’apparaissent pas dans les photos ou vidéos de capture de réalité mixte.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-254">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="a2fd8-255">Tant que ce bogue n’est pas résolu dans Windows, si les applications définissent activement le point de [focus,](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) elles doivent s’assurer que le plan normal est mis en face de la caméra (par exemple, normal = -camera.forward).</span><span class="sxs-lookup"><span data-stu-id="a2fd8-255">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="a2fd8-256">Manette sans fil Xbox</span><span class="sxs-lookup"><span data-stu-id="a2fd8-256">Xbox Wireless Controller</span></span>

- <span data-ttu-id="a2fd8-257">La manette sans fil Xbox S doit être mise à jour avant de pouvoir être utilisée avec HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-257">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="a2fd8-258">Assurez-vous que [vous êtes à jour](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) avant d’essayer de jumeler votre contrôleur avec un HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-258">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="a2fd8-259">Si vous redémarrez votre HoloLens pendant que la manette sans fil Xbox est connectée, la manette ne se reconnecte pas automatiquement à HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-259">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="a2fd8-260">La lumière du bouton Guide clignote lentement jusqu’à ce que le contrôleur s’allume après 3 minutes.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-260">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="a2fd8-261">Pour reconnecter immédiatement votre contrôleur, allumez-le en maintenant le bouton Guide enfoncé jusqu’à ce que la lumière soit éteinte.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-261">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="a2fd8-262">Lorsque vous reconnectez votre contrôleur, il se reconnecte à HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-262">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="a2fd8-263">Si votre HoloLens entre en veille pendant que la manette sans fil Xbox est connectée, toute entrée sur la manette va s’enserr le HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-263">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="a2fd8-264">Vous pouvez éviter cela en éteint votre contrôleur lorsque vous avez terminé de l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-264">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="a2fd8-265">Problèmes connus pour l’émulateur HoloLens</span><span class="sxs-lookup"><span data-stu-id="a2fd8-265">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="a2fd8-266">Toutes les applications du Microsoft Store ne sont pas compatibles avec l’émulateur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-266">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="a2fd8-267">Par exemple, Young Conker et Fragments ne sont pas lisibles sur l’émulateur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-267">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="a2fd8-268">Vous ne pouvez pas utiliser la webcam du PC dans l’émulateur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-268">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="a2fd8-269">La fonctionnalité Aperçu en direct de Windows Device Portal ne fonctionne pas avec l’émulateur.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-269">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="a2fd8-270">Vous pouvez toujours capturer des vidéos et des images de réalité mixte.</span><span class="sxs-lookup"><span data-stu-id="a2fd8-270">You can still capture Mixed Reality videos and images.</span></span>
