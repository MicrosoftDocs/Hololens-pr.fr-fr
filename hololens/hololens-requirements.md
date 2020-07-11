---
title: Configurer HoloLens dans un environnement commercial
description: En savoir plus sur le déploiement et la gestion de HoloLens dans les environnements d’entreprise.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865563"
---
# <span data-ttu-id="5996c-103">Déploiement de HoloLens dans un environnement commercial</span><span class="sxs-lookup"><span data-stu-id="5996c-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="5996c-104">Vous pouvez déployer et configurer HoloLens à des fins d’évolution dans un environnement commercial.</span><span class="sxs-lookup"><span data-stu-id="5996c-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="5996c-105">Cet article fournit des instructions pour le déploiement d’appareils HoloLens dans un environnement commercial.</span><span class="sxs-lookup"><span data-stu-id="5996c-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="5996c-106">Ce guide suppose une connaissance de base de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5996c-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="5996c-107">Suivez le [Guide](hololens1-setup.md) de mise en route pour configurer HoloLens pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="5996c-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="5996c-108">Ce document part du principe que le HoloLens a été évalué par les équipes de sécurité en toute sécurité sur le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5996c-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="5996c-109">En savoir plus sur la [sécurité HoloLens](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5996c-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="5996c-110">Pour la sécurité HoloLens (1ère génération), consultez [cette FAQ](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="5996c-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="5996c-111">Vue d’ensemble des étapes de déploiement</span><span class="sxs-lookup"><span data-stu-id="5996c-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="5996c-112">Déterminez les fonctionnalités dont vous avez besoin</span><span class="sxs-lookup"><span data-stu-id="5996c-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="5996c-113">Déterminez les licences dont vous avez besoin</span><span class="sxs-lookup"><span data-stu-id="5996c-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="5996c-114">[Configurer votre réseau pour HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="5996c-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="5996c-115">Cette section inclut des exigences de bande passante, des URL et des ports qui doivent être autorisés sur votre pare-feu. Conseils d’Azure AD; Recommandations en matière de gestion des périphériques mobiles (GPM); recommandations en matière de déploiement/gestion d’applications; et recommandations en matière de certificats.</span><span class="sxs-lookup"><span data-stu-id="5996c-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="5996c-116">Facultatif [Configurer HoloLens à l’aide d’un package de mise en service](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="5996c-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="5996c-117">Appareil d’inscription</span><span class="sxs-lookup"><span data-stu-id="5996c-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="5996c-118">Configurer des mises à jour basées sur un anneau pour HoloLens</span><span class="sxs-lookup"><span data-stu-id="5996c-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="5996c-119">Activer le chiffrement d’appareil Bitlocker pour HoloLens</span><span class="sxs-lookup"><span data-stu-id="5996c-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="5996c-120">Étape1.</span><span class="sxs-lookup"><span data-stu-id="5996c-120">Step 1.</span></span> <span data-ttu-id="5996c-121">Déterminez ce dont vous avez besoin</span><span class="sxs-lookup"><span data-stu-id="5996c-121">Determine what you need</span></span>

<span data-ttu-id="5996c-122">Avant de déployer le HoloLens dans votre environnement, il est important de déterminer les fonctionnalités, les applications et le type d’identité nécessaires.</span><span class="sxs-lookup"><span data-stu-id="5996c-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="5996c-123">Il est également important de veiller à ce que votre équipe de sécurité ait approuvé l’utilisation du HoloLens sur le réseau de la société.</span><span class="sxs-lookup"><span data-stu-id="5996c-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="5996c-124">Pour plus d’informations sur la sécurité, consultez [HoloLens2 Security](security-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="5996c-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="5996c-125">Type d’identité</span><span class="sxs-lookup"><span data-stu-id="5996c-125">Type of Identity</span></span>

<span data-ttu-id="5996c-126">Déterminez le type d’identité qui sera utilisé pour vous connecter à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="5996c-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="5996c-127">**Comptes locaux:** Ce compte est local pour l’appareil (par exemple, un compte d’administrateur local sur un PC Windows).</span><span class="sxs-lookup"><span data-stu-id="5996c-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="5996c-128">Cela permettra à 1 utilisateur de se connecter à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="5996c-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="5996c-129">**MSA:** Il s’agit d’un compte personnel (par exemple, Outlook, Hotmail, Gmail, Yahoo, etc.). Cela permettra à 1 utilisateur de se connecter à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="5996c-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="5996c-130">**Comptes Azure Active Directory (Azure AD):** Il s’agit d’un compte créé dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5996c-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="5996c-131">Ainsi, votre entreprise peut gérer l’appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5996c-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="5996c-132">Cela permettra à plusieurs utilisateurs de se connecter à la suite commerciale HoloLens de la génération de la gamme HoloLens de l’appareil HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5996c-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="5996c-133">Pour plus d’informations sur les types d’identité, consultez notre article d' [identité HoloLens](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="5996c-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="5996c-134">Type de fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="5996c-134">Type of Features</span></span>

<span data-ttu-id="5996c-135">Votre configuration requise détermine le mode HoloLens dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="5996c-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="5996c-136">L’une des fonctionnalités populaires qui s’affichent dans les environnements clients est généralement le mode plein écran.</span><span class="sxs-lookup"><span data-stu-id="5996c-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="5996c-137">Une liste des principales fonctionnalités de HoloLens et des éditions de HoloLens qui les prennent en charge est disponible [ici](hololens-commercial-features.md).</span><span class="sxs-lookup"><span data-stu-id="5996c-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="5996c-138">Qu’est-ce que le mode plein écran?</span><span class="sxs-lookup"><span data-stu-id="5996c-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="5996c-139">Le mode Kiosk est un moyen de limiter les applications auxquelles un utilisateur a accès.</span><span class="sxs-lookup"><span data-stu-id="5996c-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="5996c-140">Cela signifie que les utilisateurs sont autorisés à accéder à certaines applications uniquement.</span><span class="sxs-lookup"><span data-stu-id="5996c-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="5996c-141">Quel mode Kiosk ai-je besoin?</span><span class="sxs-lookup"><span data-stu-id="5996c-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="5996c-142">Il existe deux types de modes Kiosk: une application unique et plusieurs applications.</span><span class="sxs-lookup"><span data-stu-id="5996c-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="5996c-143">Le mode Kiosk sur une seule application permet aux utilisateurs d’accéder à une seule application alors que le mode Kiosk multi-application permet aux utilisateurs d’accéder à plusieurs applications spécifiées.</span><span class="sxs-lookup"><span data-stu-id="5996c-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="5996c-144">Pour identifier le mode Kiosk approprié pour votre entreprise, vous devez répondre aux deux questions suivantes:</span><span class="sxs-lookup"><span data-stu-id="5996c-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="5996c-145">Les utilisateurs ont-ils besoin d’expériences/restrictions différentes?</span><span class="sxs-lookup"><span data-stu-id="5996c-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="5996c-146">Prenons l’exemple suivant: l’utilisateur a est un ingénieur de service pour le champ qui a uniquement besoin d’accéder à l’assistance à distance.</span><span class="sxs-lookup"><span data-stu-id="5996c-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="5996c-147">L’utilisateur B est un stagiaire qui a uniquement besoin d’accéder aux guides.</span><span class="sxs-lookup"><span data-stu-id="5996c-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="5996c-148">Si oui, vous devez effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="5996c-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="5996c-149">Comptes Azure AD comme méthode de connexion à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="5996c-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="5996c-150">Mode plein écran **à plusieurs applications** .</span><span class="sxs-lookup"><span data-stu-id="5996c-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="5996c-151">Si non, continuez à la question 2</span><span class="sxs-lookup"><span data-stu-id="5996c-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="5996c-152">Avez-vous besoin d’une utilisation multi-App?</span><span class="sxs-lookup"><span data-stu-id="5996c-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="5996c-153">Le mode kiosque **sur plusieurs applications** est requis</span><span class="sxs-lookup"><span data-stu-id="5996c-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="5996c-154">Si la réponse à la question 1 et 2 ne vous convient pas, le mode Kiosk à **application unique** peut être utilisé</span><span class="sxs-lookup"><span data-stu-id="5996c-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="5996c-155">Configuration du mode plein écran:</span><span class="sxs-lookup"><span data-stu-id="5996c-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="5996c-156">Il existe deux méthodes principales de déploiement ([packages de mise en service](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) et [GPM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) pour déployer le mode kiosque pour HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5996c-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="5996c-157">Ces options seront abordées plus loin dans le document. Toutefois, vous pouvez utiliser les liens ci-dessus pour accéder aux sections correspondantes de ce document.</span><span class="sxs-lookup"><span data-stu-id="5996c-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="5996c-158">Scénarios spécifiques aux applications et aux applications</span><span class="sxs-lookup"><span data-stu-id="5996c-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="5996c-159">La plupart des procédures décrites dans ce document s’appliquent également aux applications suivantes:</span><span class="sxs-lookup"><span data-stu-id="5996c-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="5996c-160">Applications</span><span class="sxs-lookup"><span data-stu-id="5996c-160">App</span></span> | <span data-ttu-id="5996c-161">Scénarios spécifiques à l’application</span><span class="sxs-lookup"><span data-stu-id="5996c-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="5996c-162">Assistance à distance</span><span class="sxs-lookup"><span data-stu-id="5996c-162">Remote Assist</span></span> | [<span data-ttu-id="5996c-163">Communication entre locataire</span><span class="sxs-lookup"><span data-stu-id="5996c-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="5996c-164">Guides</span><span class="sxs-lookup"><span data-stu-id="5996c-164">Guides</span></span>  | *<span data-ttu-id="5996c-165">À venir</span><span class="sxs-lookup"><span data-stu-id="5996c-165">Coming Soon</span></span>* |
|<span data-ttu-id="5996c-166">Applications personnalisées</span><span class="sxs-lookup"><span data-stu-id="5996c-166">Custom Apps</span></span> | *<span data-ttu-id="5996c-167">À venir</span><span class="sxs-lookup"><span data-stu-id="5996c-167">Coming Soon</span></span>* |

### <span data-ttu-id="5996c-168">Déterminer la méthode d’inscription</span><span class="sxs-lookup"><span data-stu-id="5996c-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="5996c-169">Inscription en bloc avec un jeton de sécurité dans un package de mise en service.</span><span class="sxs-lookup"><span data-stu-id="5996c-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="5996c-170">Avantages: il s’agit de l’approche la plus automatisée.</span><span class="sxs-lookup"><span data-stu-id="5996c-170">Pros: this is the most automated approach\</span></span>
  <span data-ttu-id="5996c-171">Cons: utilise le paramètre initial côté serveur</span><span class="sxs-lookup"><span data-stu-id="5996c-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="5996c-172">Inscription automatique sur la connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5996c-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="5996c-173">Avantages: approche la plus simple</span><span class="sxs-lookup"><span data-stu-id="5996c-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="5996c-174">Cons: les utilisateurs devront terminer la configuration une fois le package de mise en service appliqué.</span><span class="sxs-lookup"><span data-stu-id="5996c-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="5996c-175">_non recommandé_ -inscription manuelle après l’installation.</span><span class="sxs-lookup"><span data-stu-id="5996c-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="5996c-176">Avantages: possibilité de s’inscrire après la configuration</span><span class="sxs-lookup"><span data-stu-id="5996c-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="5996c-177">Cons: la majeure partie de l’approche et des appareils ne peuvent pas être gérés de manière centralisée tant qu’ils ne sont pas inscrits manuellement.</span><span class="sxs-lookup"><span data-stu-id="5996c-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="5996c-178">Vous trouverez plus d’informations [ici](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="5996c-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="5996c-179">Déterminer si vous avez besoin de créer un package de mise à service</span><span class="sxs-lookup"><span data-stu-id="5996c-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="5996c-180">Il existe deux méthodes pour configurer un appareil HoloLens (packages de mise en service et MDMs).</span><span class="sxs-lookup"><span data-stu-id="5996c-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="5996c-181">Nous vous suggérons d’utiliser votre appareil mobile pour configurer votre appareil HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5996c-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="5996c-182">Toutefois, dans certains cas, il est préférable d’utiliser un package de mise à niveau:</span><span class="sxs-lookup"><span data-stu-id="5996c-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="5996c-183">Vous voulez configurer le HoloLens pour ignorer l’OOBE (out-of-Box Experience)</span><span class="sxs-lookup"><span data-stu-id="5996c-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="5996c-184">Vous rencontrez des problèmes lors du déploiement d’un certificat dans un réseau complexe.</span><span class="sxs-lookup"><span data-stu-id="5996c-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="5996c-185">La plupart du temps, vous pouvez déployer des certificats à l’aide de la gestion des périphériques mobiles (y compris dans les environnements complexes).</span><span class="sxs-lookup"><span data-stu-id="5996c-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="5996c-186">Toutefois, certains scénarios nécessitent le déploiement de certificats via le package de mise à service.</span><span class="sxs-lookup"><span data-stu-id="5996c-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="5996c-187">Voici quelques configurations HoloLens que vous pouvez appliquer dans un package d’approvisionnement:</span><span class="sxs-lookup"><span data-stu-id="5996c-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="5996c-188">Application de certificats à l’appareil</span><span class="sxs-lookup"><span data-stu-id="5996c-188">Apply certificates to the device</span></span>
- <span data-ttu-id="5996c-189">Configuration d'une connexion Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5996c-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="5996c-190">Pré-configurer des questions originales telles que la langue et les paramètres régionaux</span><span class="sxs-lookup"><span data-stu-id="5996c-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="5996c-191">(HoloLens 2) inscrire en bloc dans la gestion des appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="5996c-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="5996c-192">(HoloLens v1) Appliquer la clé pour activer Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="5996c-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="5996c-193">Si vous décidez d’utiliser les packages de mise en service, suivez [ce guide](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="5996c-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="5996c-194">Obtenir de l'aide</span><span class="sxs-lookup"><span data-stu-id="5996c-194">Get support</span></span>

<span data-ttu-id="5996c-195">Obtenez de l’aide via le site du support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5996c-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="5996c-196">Classer une demande de support</span><span class="sxs-lookup"><span data-stu-id="5996c-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
