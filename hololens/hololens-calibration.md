---
title: Améliorer la qualité visuelle et le confort
description: L’étalonnage de votre écart pupillaire (IPD) peut améliorer la qualité de vos visuels. Les casques immersifs HoloLens et Windows Mixed Reality permettent de personnaliser l’IPD.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: étalonnage, confort, visuels, qualité, écart pupillaire
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f2c8afffdc24eedf9cb6b462448f5ed6ffc8d5d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828127"
---
# <span data-ttu-id="d109b-105">Améliorer la qualité visuelle et le confort</span><span class="sxs-lookup"><span data-stu-id="d109b-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="d109b-106">HoloLens 2 et HoloLens (1regénération) fonctionnent mieux lorsqu’ils sont étalonnés en fonction de vos yeux.</span><span class="sxs-lookup"><span data-stu-id="d109b-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="d109b-107">Même si ces deux appareils doivent être étalonnés pour offrir la meilleure qualité d’affichage des hologrammes, ils utilisent différentes technologies et techniques d’étalonnage.</span><span class="sxs-lookup"><span data-stu-id="d109b-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="d109b-108">Accédez à [Étalonnage HoloLens2](#calibrating-your-hololens-2) ou [Étalonnage HoloLens (1regénération)](#calibrating-your-hololens-1st-gen).</span><span class="sxs-lookup"><span data-stu-id="d109b-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="d109b-109">Étalonner votre HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d109b-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="d109b-110">HoloLens 2 utilise une technologie de suivi visuel pour améliorer votre utilisation et interagir avec l’environnement virtuel.</span><span class="sxs-lookup"><span data-stu-id="d109b-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="d109b-111">Le fait d’étalonner HoloLens 2 garantit qu’il peut effectuer un suivi précis des yeux (et des yeux d’autres personnes qui utilisent l’appareil).</span><span class="sxs-lookup"><span data-stu-id="d109b-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="d109b-112">Il vous aide également à utiliser le confort de l’utilisateur, l’alignement de l’hologramme et le suivi de main.</span><span class="sxs-lookup"><span data-stu-id="d109b-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="d109b-113">Après l’étalonnage, les hologrammes s’affichent correctement même lorsque la visière se déplace sur votre tête.</span><span class="sxs-lookup"><span data-stu-id="d109b-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="d109b-114">HoloLens 2 demande à l’utilisateur d’étalonner l’appareil dans les cas suivants:</span><span class="sxs-lookup"><span data-stu-id="d109b-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="d109b-115">L’utilisateur utilise l’appareil pour la première fois</span><span class="sxs-lookup"><span data-stu-id="d109b-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="d109b-116">L’utilisateur a précédemment désactivé le processus d’étalonnage</span><span class="sxs-lookup"><span data-stu-id="d109b-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="d109b-117">Le processus d’étalonnage n’a pas réussi lors de la dernière utilisation de l’appareil par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d109b-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="d109b-118">L’utilisateur a supprimé ses profils d’étalonnage</span><span class="sxs-lookup"><span data-stu-id="d109b-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="d109b-119">L'appareil est retiré et remis en marche et l'une des circonstances ci-dessus s'applique</span><span class="sxs-lookup"><span data-stu-id="d109b-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![Invite d’étalonnage](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="d109b-121">Au cours de ce processus, vous devez regarder un ensemble de cibles (gemmes).</span><span class="sxs-lookup"><span data-stu-id="d109b-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="d109b-122">Si vous clignotez pendant l’étalonnage, essayez de rester concentré sur les gemmes au lieu d’autres objets dans la salle.</span><span class="sxs-lookup"><span data-stu-id="d109b-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="d109b-123">Cela permet à HoloLens d’en savoir plus sur la position de votre œil pour afficher votre univers holographique.</span><span class="sxs-lookup"><span data-stu-id="d109b-123">This allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![Invite d’étalonnage](./images/07-et-hold-head-still.png)

![Invite d’étalonnage](./images/08-et-gems.png)

![Invite d’étalonnage](./images/09-et-adjusting.png)

<span data-ttu-id="d109b-127">Si l’étalonnage a réussi, un écran de réussite s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d109b-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="d109b-128">Si ce n’est pas le cas, découvrez la façon de diagnostiquer les échecs d’étalonnage [ici](#troubleshooting-hololens-2-calibration).</span><span class="sxs-lookup"><span data-stu-id="d109b-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![Invite d’étalonnage](./images/10-et-success.png)

### <span data-ttu-id="d109b-130">Étalonnage lors du partage d’un appareil ou d’une session</span><span class="sxs-lookup"><span data-stu-id="d109b-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="d109b-131">Plusieurs utilisateurs peuvent partager un appareil HoloLens 2 sans qu’il soit nécessaire de procéder à la configuration de chaque personne.</span><span class="sxs-lookup"><span data-stu-id="d109b-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="d109b-132">Lorsqu’un nouvel utilisateur place l’appareil sur sa tête pour la première fois, HoloLens 2 invite automatiquement l’utilisateur à étalonner les visuels.</span><span class="sxs-lookup"><span data-stu-id="d109b-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="d109b-133">Lorsqu’un utilisateur qui a déjà calibré des visuels place l’appareil sur sa tête, l’affichage s’ajuste en toute transparence pour une qualité d’affichage confortable.</span><span class="sxs-lookup"><span data-stu-id="d109b-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="d109b-134">Démarrage manuel du processus d’étalonnage</span><span class="sxs-lookup"><span data-stu-id="d109b-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="d109b-135">Utilisez le mouvement associé au menu Démarrer pour ouvrir le [menu **Démarrer**](hololens2-basic-usage.md#start-gesture).</span><span class="sxs-lookup"><span data-stu-id="d109b-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="d109b-136">Si l’application Paramètres n’est pas épinglée au **menu Démarrer**, sélectionnez **Toutes les applications**.</span><span class="sxs-lookup"><span data-stu-id="d109b-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="d109b-137">Sélectionnez **Paramètres**, puis **Système** > **Étalonnage** > **Étalonnage des yeux** > **Exécuter l’étalonnage des yeux**.</span><span class="sxs-lookup"><span data-stu-id="d109b-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![Application Paramètres présentant l’option d’étalonnage des yeux](./images/C-Settings.Calibration.png)

### <span data-ttu-id="d109b-139">Résolution des problèmes d’étalonnage d’HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d109b-139">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="d109b-140">L’étalonnage devrait fonctionner pour la plupart des personnes, mais ce n’est pas toujours le cas.</span><span class="sxs-lookup"><span data-stu-id="d109b-140">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="d109b-141">Voici quelques raisons potentielles d’échec de l’étalonnage:</span><span class="sxs-lookup"><span data-stu-id="d109b-141">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="d109b-142">Si vous êtes distrait et que vous ne suivez pas les cibles d’étalonnage</span><span class="sxs-lookup"><span data-stu-id="d109b-142">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="d109b-143">La visière est sale, rayée ou elle n’est pas positionnée correctement</span><span class="sxs-lookup"><span data-stu-id="d109b-143">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="d109b-144">Lunettes sales ou rayées</span><span class="sxs-lookup"><span data-stu-id="d109b-144">Dirty or scratched glasses</span></span>
- <span data-ttu-id="d109b-145">Certains types de lentilles de contact ou de lunettes (lentilles de contact colorées, certains lentilles de contact toriques, lunettes de blocage infrarouge, certains lunettes correctrices fortes, lunettes de soleil ou similaires)</span><span class="sxs-lookup"><span data-stu-id="d109b-145">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="d109b-146">Maquillage plus prononcé et certaines extensions de cils</span><span class="sxs-lookup"><span data-stu-id="d109b-146">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="d109b-147">Les cheveux ou des montures de lunettes épaisses si ceux-ci empêchent l’appareil de voir vos yeux</span><span class="sxs-lookup"><span data-stu-id="d109b-147">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="d109b-148">Certaines physiologies d’yeux, maladies ophtalmiques ou chirurgies oculaires, comme les yeux étroits, les longs cils, l’amblyopie, les nystagmus, certains cas de LASIK ou autres types de chirurgie oculaire</span><span class="sxs-lookup"><span data-stu-id="d109b-148">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="d109b-149">Si l’étalonnage ne fonctionne pas correctement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="d109b-149">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="d109b-150">Nettoyez la visière de l’appareil</span><span class="sxs-lookup"><span data-stu-id="d109b-150">Cleaning your device visor</span></span>
- <span data-ttu-id="d109b-151">Nettoyez les lunettes</span><span class="sxs-lookup"><span data-stu-id="d109b-151">Cleaning your glasses</span></span>
- <span data-ttu-id="d109b-152">Rapprochez la visière de l’appareil le plus possible de vos yeux</span><span class="sxs-lookup"><span data-stu-id="d109b-152">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="d109b-153">Retirez les objets qui pourraient se trouver dans le champ de votre visière (par exemple, vos cheveux)</span><span class="sxs-lookup"><span data-stu-id="d109b-153">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="d109b-154">Allumez une lumière dans la pièce ou éloignez-vous de la lumière directe du soleil</span><span class="sxs-lookup"><span data-stu-id="d109b-154">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="d109b-155">Si vous avez suivi toutes les recommandations et que l’étalonnage a échoué, vous pouvez désactiver l’invite d’étalonnage dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="d109b-155">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="d109b-156">N’hésitez pas à nous faire part de vos commentaires dans [Hub de commentaires](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="d109b-156">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="d109b-157">Notez que la configuration de IPD ne s’applique pas à HoloLens 2, car les positions oculaires sont calculées par le système.</span><span class="sxs-lookup"><span data-stu-id="d109b-157">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="d109b-158">Données d’étalonnage et sécurité</span><span class="sxs-lookup"><span data-stu-id="d109b-158">Calibration data and security</span></span>

<span data-ttu-id="d109b-159">Les informations d’étalonnage sont stockées localement sur l’appareil et ne sont associées à aucune information de compte.</span><span class="sxs-lookup"><span data-stu-id="d109b-159">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="d109b-160">Il n’existe aucun enregistrement de qui a utilisé l’appareil sans étalonnage.</span><span class="sxs-lookup"><span data-stu-id="d109b-160">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="d109b-161">Cela signifie que chaque nouvel utilisateur est invité à étalonner les visuels à la première utilisation de l’appareil, tout comme les utilisateurs ayant choisi de ne pas réaliser l’étalonnage auparavant ou si l’étalonnage a échoué.</span><span class="sxs-lookup"><span data-stu-id="d109b-161">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="d109b-162">L’appareil peut stocker localement jusqu’à 50 profils d’étalonnage.</span><span class="sxs-lookup"><span data-stu-id="d109b-162">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="d109b-163">Une fois ce nombre atteint, l’appareil supprime automatiquement le plus ancien profil inutilisé.</span><span class="sxs-lookup"><span data-stu-id="d109b-163">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="d109b-164">Les informations d’étalonnage peuvent toujours être supprimées de l’appareil dans **Paramètres** > **Confidentialité** > **Suivi oculaire**.</span><span class="sxs-lookup"><span data-stu-id="d109b-164">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="d109b-165">Désactiver l’étalonnage</span><span class="sxs-lookup"><span data-stu-id="d109b-165">Disable calibration</span></span>

<span data-ttu-id="d109b-166">Vous pouvez également désactiver l’invite d’étalonnage en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="d109b-166">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="d109b-167">Sélectionnez **Paramètres** > **Système** > **Étalonnage**.</span><span class="sxs-lookup"><span data-stu-id="d109b-167">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="d109b-168">Désactivez l’option **Quand une nouvelle personne utilise ce HoloLens, demander automatiquement un étalonnage des yeux**.</span><span class="sxs-lookup"><span data-stu-id="d109b-168">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d109b-169">Ce paramètre risque de nuire à la qualité et au confort du rendu des hologrammes.</span><span class="sxs-lookup"><span data-stu-id="d109b-169">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="d109b-170">Lorsque vous désactivez ce paramètre, les fonctionnalités qui dépendent du suivi oculaire (par exemple, le défilement du texte) ne fonctionnent plus dans les applications immersives.</span><span class="sxs-lookup"><span data-stu-id="d109b-170">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="d109b-171">Technologie de suivi oculaire de HoloLens2</span><span class="sxs-lookup"><span data-stu-id="d109b-171">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="d109b-172">L’appareil utilise sa technologie de suivi oculaire pour améliorer la qualité d’affichage et garantir que tous les hologrammes sont positionnés de manière précise et confortable pour un affichage en 3D.</span><span class="sxs-lookup"><span data-stu-id="d109b-172">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="d109b-173">Étant donné qu’il utilise les yeux comme points de repère, l’appareil peut s’ajuster à chaque utilisateur et adapter ses visuels si le casque se déplace légèrement en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="d109b-173">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="d109b-174">Tous les ajustements sont effectués à la volée, sans nécessiter d’ajustement manuel.</span><span class="sxs-lookup"><span data-stu-id="d109b-174">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="d109b-175">La configuration de IPD ne s’applique pas à HoloLens 2, car les positions oculaires sont calculées par le système.</span><span class="sxs-lookup"><span data-stu-id="d109b-175">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="d109b-176">Les applications HoloLens utilisent le suivi visuel pour suivre l’endroit où vous regardez en temps réel.</span><span class="sxs-lookup"><span data-stu-id="d109b-176">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="d109b-177">C’est la principale fonctionnalité que les développeurs peuvent utiliser pour tirer parti d’un nouveau niveau de contexte, compréhension et interactions humaines au sein de l’expérience holographique.</span><span class="sxs-lookup"><span data-stu-id="d109b-177">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="d109b-178">Les développeurs n’ont rien à faire pour tirer parti de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d109b-178">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="d109b-179">Étalonnage de votre HoloLens (1re génération)</span><span class="sxs-lookup"><span data-stu-id="d109b-179">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="d109b-180">HoloLens (1re génération) ajuste l’affichage des hologrammes en fonction de votre [écart pupillaire](https://en.wikipedia.org/wiki/Interpupillary_distance).</span><span class="sxs-lookup"><span data-stu-id="d109b-180">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="d109b-181">Si l’écart pupillaire n’est pas précis, les hologrammes pourraient paraître instables ou à une distance incorrecte.</span><span class="sxs-lookup"><span data-stu-id="d109b-181">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="d109b-182">Vous pouvez améliorer la qualité de vos visuels en étalonnant l’appareil selon votre écart pupillaire.</span><span class="sxs-lookup"><span data-stu-id="d109b-182">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="d109b-183">Lorsque vous configurez votre appareil HoloLens (1re génération), celui-ci vous invite à étalonner vos visuels une fois que Cortana s’est présentée.</span><span class="sxs-lookup"><span data-stu-id="d109b-183">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="d109b-184">Nous vous conseillons de réaliser la procédure d’étalonnage au cours de cette phase d’installation.</span><span class="sxs-lookup"><span data-stu-id="d109b-184">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="d109b-185">Néanmoins, vous pouvez l’ignorer en attendant que Cortana vous y invite, puis en indiquant «Ignorer».</span><span class="sxs-lookup"><span data-stu-id="d109b-185">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="d109b-186">Pendant le processus d’étalonnage, HoloLens vous demande d’aligner votre doigt avec une série de six cibles par œil.</span><span class="sxs-lookup"><span data-stu-id="d109b-186">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="d109b-187">HoloLens utilise ce processus pour définir correctement l’écart pupillaire de vos yeux.</span><span class="sxs-lookup"><span data-stu-id="d109b-187">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![Écran d’alignement IPD d’un doigt lors de la deuxième étape](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="d109b-189">Démarrer manuellement le processus d’étalonnage</span><span class="sxs-lookup"><span data-stu-id="d109b-189">Manually start the calibration process</span></span>

<span data-ttu-id="d109b-190">Si vous avez besoin de mettre à jour l’étalonnage ou si un nouvel utilisateur doit l’ajuster, vous pouvez exécuter l’application d’étalonnage manuellement à tout moment.</span><span class="sxs-lookup"><span data-stu-id="d109b-190">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="d109b-191">L’application d’étalonnage est installée par défaut.</span><span class="sxs-lookup"><span data-stu-id="d109b-191">The Calibration app is installed by default.</span></span> <span data-ttu-id="d109b-192">Vous pouvez y accéder à l’aide du menu **Démarrer** ou de l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="d109b-192">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="d109b-193">Pour exécuter l’application Étalonnage à l’aide du menu **Démarrer**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="d109b-193">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="d109b-194">Utilisez le geste [écarter les doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="d109b-194">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="d109b-195">Pour afficher toutes les applications, sélectionnez **+**.</span><span class="sxs-lookup"><span data-stu-id="d109b-195">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="d109b-196">Sélectionnez **Étalonnage**.</span><span class="sxs-lookup"><span data-stu-id="d109b-196">Select **Calibration**.</span></span>

![Accès à l’application d’étalonnage à partir de l’interpréteur de commandes](./images/calibration-shell.png)

![Application d’étalonnage affichée sous la forme d’un cube dynamique après son lancement](./images/calibration-livecube-200px.png)

<span data-ttu-id="d109b-199">Pour utiliser l’application Paramètres pour exécuter l’application Étalonnage, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="d109b-199">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="d109b-200">Utilisez le geste [écartement des doigts paume vers le haut](hololens1-basic-usage.md) pour ouvrir le menu **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="d109b-200">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="d109b-201">Si **Paramètres** n’est pas épinglé sur le menu **Démarrer**, sélectionnez **+** pour afficher toutes les applications.</span><span class="sxs-lookup"><span data-stu-id="d109b-201">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="d109b-202">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="d109b-202">Select **Settings**.</span></span>
1. <span data-ttu-id="d109b-203">Sélectionnez **Système** > **Utilitaires** > **Ouvrir Étalonnage**.</span><span class="sxs-lookup"><span data-stu-id="d109b-203">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![Lancement de l’application Ouvrir Étalonnage à partir de l’application Paramètres](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="d109b-205">Casques immersifs</span><span class="sxs-lookup"><span data-stu-id="d109b-205">Immersive headsets</span></span>

<span data-ttu-id="d109b-206">Certains casques immersifs permettent de personnaliser le paramètre d’écart pupillaire.</span><span class="sxs-lookup"><span data-stu-id="d109b-206">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="d109b-207">Pour modifier l’écart pupillaire de votre casque, ouvrez l’application Paramètres, sélectionnez **Réalité mixte** > **Affichage du casque**, puis déplacez le curseur.</span><span class="sxs-lookup"><span data-stu-id="d109b-207">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="d109b-208">Les modifications sont apportées en temps réel dans votre casque.</span><span class="sxs-lookup"><span data-stu-id="d109b-208">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="d109b-209">Si vous connaissez votre écart pupillaire, peut-être après une visite chez un opticien, vous pouvez le saisir directement.</span><span class="sxs-lookup"><span data-stu-id="d109b-209">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="d109b-210">Vous pouvez également régler ce paramètre sur votre PC en sélectionnant **Paramètres** > **Réalité mixte** > **Affichage du casque**.</span><span class="sxs-lookup"><span data-stu-id="d109b-210">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="d109b-211">Si votre casque ne prend pas en charge la personnalisation de l’écart pupillaire, ce paramètre est désactivé.</span><span class="sxs-lookup"><span data-stu-id="d109b-211">If your headset does not support IPD customization, this setting will be disabled.</span></span>
