---
title: Partager votre HoloLens avec plusieurs personnes
description: Vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828419"
---
# <span data-ttu-id="e26e1-103">Partager votre HoloLens avec plusieurs personnes</span><span class="sxs-lookup"><span data-stu-id="e26e1-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="e26e1-104">Le partage d’un HoloLens avec de nombreuses personnes ou de nombreux utilisateurs peut partager un ensemble d’appareils HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e26e1-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="e26e1-105">Cet article décrit les différentes façons dont vous pouvez partager un appareil.</span><span class="sxs-lookup"><span data-stu-id="e26e1-105">This article describes the different ways in which you can share a device.</span></span>

## <span data-ttu-id="e26e1-106">Partager avec plusieurs personnes en utilisant leur propre compte</span><span class="sxs-lookup"><span data-stu-id="e26e1-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="e26e1-107">**Configuration requise**: l’appareil HoloLens doit exécuter Windows 10, version 1803 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e26e1-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="e26e1-108">HoloLens (1ère génération) doit également être [mis à niveau vers Windows holographique pour les entreprises](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e26e1-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="e26e1-109">Lorsqu’ils utilisent leur propre compte Azure Active Directory (Azure AD), plusieurs utilisateurs peuvent conserver leurs propres paramètres utilisateur et données utilisateur sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e26e1-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="e26e1-110">Pour vous assurer que plusieurs personnes peuvent utiliser leur propre compte sur votre HoloLens, procédez comme suit pour les configurer:</span><span class="sxs-lookup"><span data-stu-id="e26e1-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="e26e1-111">Vérifiez que l’appareil exécute Windows 10, version 1803 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e26e1-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="e26e1-112">Si vous utilisez un appareil HoloLens (1ère génération), [effectuez la mise à niveau de votre appareil vers Windows holographique pour les entreprises](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e26e1-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="e26e1-113">Lorsque vous configurez l’appareil, sélectionnez **mon entreprise ou votre établissement scolaire propriétaire** , puis connectez-vous à l’aide d’un compte Azure ad.</span><span class="sxs-lookup"><span data-stu-id="e26e1-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="e26e1-114">Une fois l’installation terminée, assurez-vous que les paramètres du compte (comptes de**paramètres**  >  **Accounts**) incluent d' **autres utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e26e1-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="e26e1-115">Pour utiliser HoloLens, chaque utilisateur doit suivre les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="e26e1-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="e26e1-116">Si un autre utilisateur a utilisé l’appareil, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="e26e1-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="e26e1-117">Appuyez une fois sur le bouton d’alimentation pour accéder à l’option Standby, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage.</span><span class="sxs-lookup"><span data-stu-id="e26e1-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="e26e1-118">Les utilisateurs HoloLens 2 peuvent sélectionner la vignette utilisateur dans le menu Démarrer pour se déconnecter de l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="e26e1-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="e26e1-119">Utilisez vos informations d’identification de compte Azure AD pour vous connecter à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e26e1-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="e26e1-120">S’il s’agit de la première fois que vous utilisez l’appareil, vous devez [étalonner](hololens-calibration.md) HoloLens à vos propres yeux.</span><span class="sxs-lookup"><span data-stu-id="e26e1-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="e26e1-121">Pour afficher une liste des utilisateurs de l’appareil ou pour supprimer un utilisateur de l’appareil, accédez à **paramètres**de  >  **comptes**  >  **autres utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e26e1-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <span data-ttu-id="e26e1-122">Partager avec plusieurs personnes en utilisant le même compte</span><span class="sxs-lookup"><span data-stu-id="e26e1-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="e26e1-123">Plusieurs utilisateurs peuvent également partager un appareil HoloLens lors de l’utilisation d’un seul compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e26e1-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="e26e1-124">**Sur HoloLens 2**, lorsqu’un utilisateur place le périphérique sur son tête pour la première fois (tout en conservant la connexion de votre compte), l’appareil demande au nouvel utilisateur d’étalonner et de personnaliser rapidement l’interface d’affichage.</span><span class="sxs-lookup"><span data-stu-id="e26e1-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="e26e1-125">L’appareil peut stocker les informations d’étalonnage de sorte à ce qu’à l’avenir, l’appareil puisse automatiquement optimiser la qualité et le confort de l’affichage de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e26e1-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="e26e1-126">Les utilisateurs n’ont pas besoin de calibrer l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e26e1-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="e26e1-127">**Sur les utilisateurs HoloLens (1er génération),** le partage d’un compte nécessite une demande de calibrage dans l’application paramètres.</span><span class="sxs-lookup"><span data-stu-id="e26e1-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="e26e1-128">En savoir plus sur le [calibrage](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="e26e1-128">Read more about [calibration](hololens-calibration.md).</span></span>
