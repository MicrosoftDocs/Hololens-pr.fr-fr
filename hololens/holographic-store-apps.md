---
title: Rechercher, installer et désinstaller des applications
description: Le Microsoft Store constitue votre source d’applications et de jeux compatibles avec HoloLens.  En savoir plus sur la recherche, l’installation et la désinstallation d’applications holographiques.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, application, installer
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 44c79a41d7864cd6000ffed1bdd32dab8ffabc39
ms.sourcegitcommit: b437c738f101ac870a29bbdb7fd642eda3d67f00
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406266"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="cdf64-105">Rechercher, installer et désinstaller des applications à partir du Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cdf64-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="cdf64-106">Le Microsoft Store constitue votre source d’accès aux applications et de jeux compatibles avec HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cdf64-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="cdf64-107">Lorsque vous accédez au Store sur votre HoloLens, toutes les applications que vous voyez y sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="cdf64-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="cdf64-108">Les applications sur HoloLens utilisent l’affichage 2D ou l’affichage holographique.</span><span class="sxs-lookup"><span data-stu-id="cdf64-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="cdf64-109">Les applications qui utilisent l’affichage 2D ressemblent à des fenêtres et peuvent être positionnées partout autour de vous.</span><span class="sxs-lookup"><span data-stu-id="cdf64-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="cdf64-110">Les applications qui utilisent l’affichage holographique vous entourent et deviennent la seule application que vous voyez.</span><span class="sxs-lookup"><span data-stu-id="cdf64-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="cdf64-111">HoloLens prend en charge de nombreuses applications existantes à partir du Microsoft Store et les nouvelles applications conçues spécifiquement pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cdf64-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="cdf64-112">Cet article décrit les applications holographiques du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="cdf64-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="cdf64-113">Pour en savoir plus sur l’installation et l’exécution des applications personnalisées, consultez [Applications holographiques personnalisées](holographic-custom-apps.md).</span><span class="sxs-lookup"><span data-stu-id="cdf64-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="cdf64-114">Rechercher des applications</span><span class="sxs-lookup"><span data-stu-id="cdf64-114">Find apps</span></span>

<span data-ttu-id="cdf64-115">Ouvrez le Microsoft Store à partir du menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="cdf64-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="cdf64-116">Recherchez ensuite applications et jeux.</span><span class="sxs-lookup"><span data-stu-id="cdf64-116">Then browse for apps and games.</span></span> <span data-ttu-id="cdf64-117">Vous pouvez utiliser des [commandes vocales](hololens-cortana.md) pour effectuer des recherches en prononçant « Rechercher ». Une fois la fenêtre de recherche ouverte, dites « Démarrer la dictée », puis lorsque vous y êtes invité, commencez à énoncer vos critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="cdf64-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="cdf64-118">La configuration requise pour les appareils HoloLens dépend de l’architecture de la build de l’application.</span><span class="sxs-lookup"><span data-stu-id="cdf64-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="cdf64-119">Si une build d’application pour HoloLens (1ère génération) n’a pas été mise à jour avec une nouvelle UWP dans le Windows Store afin d’inclure le package d’architecture ARM, elle ne sera pas disponible pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cdf64-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="cdf64-120">De même, si une application HoloLens 2 n’inclut pas le package d’architecture x86, elle ne sera pas disponible pour les appareils HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="cdf64-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="cdf64-121">Architectures de périphériques HoloLens :</span><span class="sxs-lookup"><span data-stu-id="cdf64-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="cdf64-122">x86 = HoloLens (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="cdf64-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="cdf64-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="cdf64-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="cdf64-124">Le 12 janvier 2021, nous ne prendrons plus en charge les applications suivantes sur les appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cdf64-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="cdf64-125">Nous vous encourageons à utiliser le lien suivant sur votre appareil pour bénéficier de la version web de l’application.</span><span class="sxs-lookup"><span data-stu-id="cdf64-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="cdf64-126">Application</span><span class="sxs-lookup"><span data-stu-id="cdf64-126">App</span></span>        | <span data-ttu-id="cdf64-127">Link</span><span class="sxs-lookup"><span data-stu-id="cdf64-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="cdf64-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="cdf64-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="cdf64-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="cdf64-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="cdf64-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="cdf64-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="cdf64-131">Installation d’applications</span><span class="sxs-lookup"><span data-stu-id="cdf64-131">Install apps</span></span>

<span data-ttu-id="cdf64-132">Pour télécharger des applications, vous devez être connecté avec un compte Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cdf64-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="cdf64-133">Certaines applications sont gratuites et peuvent être téléchargées immédiatement.</span><span class="sxs-lookup"><span data-stu-id="cdf64-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="cdf64-134">Pour les applications qui nécessitent un achat, vous devez être inscrit au Windows Store avec votre compte Microsoft et avoir un mode de paiement valide.</span><span class="sxs-lookup"><span data-stu-id="cdf64-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>
> [!NOTE]
> <span data-ttu-id="cdf64-135">Il n’est pas nécessaire que le compte que vous utilisez dans le Microsoft Store soit identique au compte avec lequel vous vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="cdf64-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="cdf64-136">Si vous utilisez un compte professionnel ou scolaire sur votre HoloLens, vous devrez peut-être vous connecter à l’aide de votre compte personnel dans l’application Store pour effectuer l’achat.</span><span class="sxs-lookup"><span data-stu-id="cdf64-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="cdf64-137">Pour configurer un mode de paiement, accédez à [account.microsoft.com](https://account.microsoft.com/), puis sélectionnez **Paiement et facturation** > **Option de paiement** > **Ajouter une option de paiement**.</span><span class="sxs-lookup"><span data-stu-id="cdf64-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="cdf64-138">Pour ouvrir le [menu **Démarrer**](holographic-home.md), effectuez le [mouvement associé au menu Démarrer](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) ou un [écartement des doigts paume vers le haut](hololens1-basic-usage.md) sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="cdf64-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="cdf64-139">Sélectionnez l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="cdf64-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="cdf64-140">Après l’ouverture de l’application du Store :</span><span class="sxs-lookup"><span data-stu-id="cdf64-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="cdf64-141">Utilisez la barre de recherche pour rechercher des applications.</span><span class="sxs-lookup"><span data-stu-id="cdf64-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="cdf64-142">Sélectionnez les applications essentielles ou les applications spécialement conçues pour HoloLens dans l'une des catégories proposées.</span><span class="sxs-lookup"><span data-stu-id="cdf64-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="cdf64-143">Dans la partie supérieure droite de l’application Store, sélectionnez le bouton **« ... »**, puis sélectionnez **Ma bibliothèque** pour afficher les applications précédemment achetées.</span><span class="sxs-lookup"><span data-stu-id="cdf64-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>
1. <span data-ttu-id="cdf64-144">Sélectionnez **Télécharger** ou **Installer** sur la page de l’application (un achat peut être nécessaire).</span><span class="sxs-lookup"><span data-stu-id="cdf64-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="cdf64-145">Mettre à jour les applications</span><span class="sxs-lookup"><span data-stu-id="cdf64-145">Update Apps</span></span>
<span data-ttu-id="cdf64-146">Pour mettre à jour une application que vous avez installée à partir du Microsoft Store, vous pouvez mettre à jour l’application à partir de l’application du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="cdf64-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="cdf64-147">Pour les applications installées pour le Microsoft Store pour Entreprises, vous pouvez également les mettre à jour à partir du Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="cdf64-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 
1. <span data-ttu-id="cdf64-148">Pour ouvrir le [menu **Démarrer**](holographic-home.md), effectuez le [mouvement associé au menu Démarrer](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) ou un [écartement des doigts paume vers le haut](hololens1-basic-usage.md) sur HoloLens (1ère génération).</span><span class="sxs-lookup"><span data-stu-id="cdf64-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="cdf64-149">Sélectionnez l’application du Store.</span><span class="sxs-lookup"><span data-stu-id="cdf64-149">Select the Store app.</span></span>
1. <span data-ttu-id="cdf64-150">Regardez dans la partie supérieure droite de l’application Store.</span><span class="sxs-lookup"><span data-stu-id="cdf64-150">Look to the top right of the Store app.</span></span> 
1. <span data-ttu-id="cdf64-151">Sélectionnez le bouton **« ... »** ou « Voir plus ».</span><span class="sxs-lookup"><span data-stu-id="cdf64-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’application Microsoft Store.](images/store-update-1.png)

1. <span data-ttu-id="cdf64-153">Sélectionnez **Téléchargements et mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="cdf64-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="cdf64-154">Si votre appareil a précédemment identifié des mises à jour, il peut y avoir une flèche vers le bas et un nombre représentant les mises à jour en attente.</span><span class="sxs-lookup"><span data-stu-id="cdf64-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>
1. <span data-ttu-id="cdf64-155">Sélectionnez **Obtenir les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="cdf64-155">Select **Get updates**.</span></span> <span data-ttu-id="cdf64-156">Votre appareil va maintenant rechercher les mises à jour et les préparer au téléchargement et l’installation.</span><span class="sxs-lookup"><span data-stu-id="cdf64-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’application Microsoft Store montrant la récupération de mises à jour.](images/store-update-2.png.jpg)

> [!NOTE]
> <span data-ttu-id="cdf64-158">Si les applications sur votre appareil ont été distribuées par votre organisation, elles peuvent être mises à jour via les mêmes méthodes de gestion des applications commerciales.</span><span class="sxs-lookup"><span data-stu-id="cdf64-158">If the apps on your device were distrubted by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="cdf64-159">Si cela s’applique à votre situation, consultez pour plus d’informations notre [vue d’ensemble du déploiement d’applications commerciales.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cdf64-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="cdf64-160">Si vous voulez mettre à jour une application personnalisée en version test ou déployée, vous devez utiliser la même méthode avec la version mise à jour de votre application.</span><span class="sxs-lookup"><span data-stu-id="cdf64-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="cdf64-161">Pour en savoir plus sur l’installation et l’exécution des applications personnalisées, consultez la rubrique [Applications holographiques personnalisées](holographic-custom-apps.md).</span><span class="sxs-lookup"><span data-stu-id="cdf64-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="cdf64-162">Désinstaller les applications</span><span class="sxs-lookup"><span data-stu-id="cdf64-162">Uninstall apps</span></span>

<span data-ttu-id="cdf64-163">Vous pouvez désinstaller les applications de deux manières.</span><span class="sxs-lookup"><span data-stu-id="cdf64-163">There are two ways to uninstall applications.</span></span>  <span data-ttu-id="cdf64-164">Vous pouvez désinstaller les applications par le biais du Microsoft Store ou du menu Démarrer.</span><span class="sxs-lookup"><span data-stu-id="cdf64-164">You can uninstall applications through the Microsoft Store or Start menu.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="cdf64-165">Désinstaller à partir du menu Démarrer</span><span class="sxs-lookup"><span data-stu-id="cdf64-165">Uninstall from the Start menu</span></span>

<span data-ttu-id="cdf64-166">Dans le menu **Démarrer** ou dans la liste **Toutes les applications**, accédez à l’application.</span><span class="sxs-lookup"><span data-stu-id="cdf64-166">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="cdf64-167">Sélectionnez et maintenez jusqu'à ce que le menu apparaisse, puis sélectionnez **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="cdf64-167">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="cdf64-168">Désinstaller à partir du Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cdf64-168">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="cdf64-169">Ouvrez le Microsoft Store à partir du menu **Démarrer,** puis recherchez l’application que vous souhaitez désinstaller.</span><span class="sxs-lookup"><span data-stu-id="cdf64-169">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="cdf64-170">Dans la page Store, chaque application installée dispose d’un bouton **Désinstaller.**</span><span class="sxs-lookup"><span data-stu-id="cdf64-170">On the Store page, each installed application has an **Uninstall** button.</span></span>
