---
title: Partager votre HoloLens avec plusieurs personnes
description: Vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes de Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308836"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="89139-103">Partager votre HoloLens avec plusieurs personnes</span><span class="sxs-lookup"><span data-stu-id="89139-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="89139-104">Il est courant de partager un HoloLens avec de nombreuses personnes ou de nombreuses personnes partagent un ensemble d’appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="89139-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="89139-105">Cet article décrit les différentes façons dont vous pouvez partager un appareil.</span><span class="sxs-lookup"><span data-stu-id="89139-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="89139-106">Partager avec plusieurs personnes, chacune utilisant son propre compte</span><span class="sxs-lookup"><span data-stu-id="89139-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="89139-107">**Condition préalable**: l’appareil HoloLens doit exécuter Windows 10, version 1803 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="89139-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="89139-108">HoloLens (1ère génération) doit également être [mis à niveau vers Windows holographique for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="89139-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="89139-109">Lorsqu’ils utilisent leurs propres comptes de Azure Active Directory (Azure AD), plusieurs utilisateurs peuvent conserver leurs propres paramètres utilisateur et données utilisateur sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="89139-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="89139-110">Pour vous assurer que plusieurs personnes peuvent utiliser leurs propres comptes sur votre HoloLens, procédez comme suit pour le configurer :</span><span class="sxs-lookup"><span data-stu-id="89139-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="89139-111">Assurez-vous que l’appareil exécute Windows 10, version 1803 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="89139-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="89139-112">Si vous utilisez un appareil HoloLens (1er génération), [Mettez-le à niveau vers Windows holographique pour entreprises](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="89139-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="89139-113">Quand vous configurez l’appareil, sélectionnez **mon entreprise ou école en est propriétaire** et connectez-vous à l’aide d’un compte Azure ad.</span><span class="sxs-lookup"><span data-stu-id="89139-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="89139-114">Une fois l’installation terminée, vérifiez que les paramètres de compte (comptes de **paramètres**  >  ) incluent d' **autres utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="89139-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="89139-115">Pour utiliser HoloLens, chaque utilisateur suit les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="89139-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="89139-116">Si un autre utilisateur a utilisé l’appareil, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="89139-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="89139-117">Appuyez une fois sur le bouton d’alimentation pour accéder à la mise en veille, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage</span><span class="sxs-lookup"><span data-stu-id="89139-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="89139-118">Les utilisateurs de HoloLens 2 peuvent sélectionner la vignette de l’utilisateur dans le menu Démarrer pour déconnecter l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="89139-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="89139-119">Utilisez les informations d’identification de votre compte Azure AD pour vous connecter à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="89139-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="89139-120">S’il s’agit de la première fois que vous utilisez l’appareil, vous devez [étalonner](hololens-calibration.md) HoloLens à vos propres yeux.</span><span class="sxs-lookup"><span data-stu-id="89139-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="89139-121">Pour afficher la liste des utilisateurs d’appareils ou pour supprimer un utilisateur de l’appareil, accédez à **paramètres**  >  **comptes**  >  **autres utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="89139-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="89139-122">Partager avec plusieurs personnes, toutes utilisant le même compte</span><span class="sxs-lookup"><span data-stu-id="89139-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="89139-123">Plusieurs utilisateurs peuvent également partager un appareil HoloLens en utilisant un seul compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89139-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="89139-124">**Sur HoloLens 2**, lorsqu’un nouvel utilisateur met l’appareil en tête pour la première fois (tout en conservant le même compte connecté), l’appareil invite le nouvel utilisateur à étalonner et à personnaliser rapidement l’expérience d’affichage.</span><span class="sxs-lookup"><span data-stu-id="89139-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="89139-125">L’appareil peut stocker les informations d’étalonnage afin que, à l’avenir, l’appareil puisse optimiser automatiquement la qualité et le confort de l’expérience d’affichage de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89139-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="89139-126">Les utilisateurs n’ont pas besoin d’étalonner à nouveau l’appareil.</span><span class="sxs-lookup"><span data-stu-id="89139-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="89139-127">**Sur HoloLens (1er génération),** les utilisateurs qui partagent un compte doivent demander à être recalibrés dans l’application paramètres.</span><span class="sxs-lookup"><span data-stu-id="89139-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="89139-128">En savoir plus sur l' [étalonnage](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="89139-128">Read more about [calibration](hololens-calibration.md).</span></span>
