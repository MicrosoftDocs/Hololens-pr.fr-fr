---
title: Guide de déploiement – Déploiement HoloLens 2 connecté au cloud à l’échelle avec Remote Assist - Maintenir
description: Restez à jour avec nos conseils pour la maintenance et la prise en charge des appareils HoloLens sur un réseau connecté au cloud.
keywords: HoloLens, gestion, cloud connecté, Remote Assist, AAD, Azure AD, MDM, Gestion des appareils mobiles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283895"
---
# <span data-ttu-id="94ddc-104">Maintain - Guide connecté au cloud</span><span class="sxs-lookup"><span data-stu-id="94ddc-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="94ddc-105">Mises à jour</span><span class="sxs-lookup"><span data-stu-id="94ddc-105">Updates</span></span>

<span data-ttu-id="94ddc-106">Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="94ddc-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="94ddc-107">Découvrez comment gérer les mises à jour [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) y compris les jours prévus, l’heure prévue et la définition des heures d’activité sur l’appareil afin qu’elle soit mise à jour en dehors des heures de travail.</span><span class="sxs-lookup"><span data-stu-id="94ddc-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="94ddc-108">Remote Assist est une application In-Box et peut être mise à jour via l’application du Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="94ddc-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="94ddc-109">Pour toutes les applications téléchargées via le Microsoft Store, elles peuvent être mises à jour manuellement via [l’application du Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) elle-même.</span><span class="sxs-lookup"><span data-stu-id="94ddc-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="94ddc-110">Plan de support</span><span class="sxs-lookup"><span data-stu-id="94ddc-110">Support Plan</span></span>

<span data-ttu-id="94ddc-111">Un plan de support est une excellente chose à mettre en place.</span><span class="sxs-lookup"><span data-stu-id="94ddc-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="94ddc-112">Il est utile de disposer d’une personne ou d’un groupe formé à la résolution des problèmes de processus d’inscription sur les appareils HoloLens, ainsi qu’à l’utilisation générale de l’appareil HoloLens au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="94ddc-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="94ddc-113">Pour permettre à vos utilisateurs de résoudre plus rapidement leurs problèmes, nous vous suggérons de gérer votre processus d’escalade de la même manière que dans cet ordre :</span><span class="sxs-lookup"><span data-stu-id="94ddc-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="94ddc-114">Votre support technique.</span><span class="sxs-lookup"><span data-stu-id="94ddc-114">Your Support desk.</span></span>
2. <span data-ttu-id="94ddc-115">Votre équipe HoloLens Expert</span><span class="sxs-lookup"><span data-stu-id="94ddc-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="94ddc-116">[Documentation HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentation de dépannage HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="94ddc-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="94ddc-117">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="94ddc-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="94ddc-118">Plan de développement</span><span class="sxs-lookup"><span data-stu-id="94ddc-118">Development Plan</span></span>

<span data-ttu-id="94ddc-119">Une fois votre appareil correctement inscrit, vous êtes prêt à déployer des applications métier sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="94ddc-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="94ddc-120">Il s’agit d’applications personnalisées conçues pour votre&#39;besoins.</span><span class="sxs-lookup"><span data-stu-id="94ddc-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="94ddc-121">Si vous avez déjà une application métier,&#39;êtes prêt à déployer votre [application via la gestion des](https://docs.microsoft.com/hololens/app-deploy-intune)applications de gestion des&#39;.</span><span class="sxs-lookup"><span data-stu-id="94ddc-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="94ddc-122">Si vous&#39;préférez une autre méthode, examinez la vue d’ensemble du déploiement d’application pour [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) pour en savoir plus sur les méthodes de déploiement de votre application LOB sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="94ddc-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="94ddc-123">Si vous n&#39;avez pas encore créé votre propre application métier ou que vous êtes encore en cours de création, examinez nos documents de développement de réalité mixte pour commencer à concevoir et créer un [prototype](https://docs.microsoft.com/windows/mixed-reality/design/design) ou découvrez les concepts de base pour commencer avec le développement de réalité [mixte.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="94ddc-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="94ddc-124">Gestion des périphériques</span><span class="sxs-lookup"><span data-stu-id="94ddc-124">Device Management</span></span> 

<span data-ttu-id="94ddc-125">Bien que ce guide a abordé la configuration de la gestion des périphériques mobiles (MDM), il n’a pas été utilisé pour appliquer des restrictions d’appareil ou des stratégies ont été appliquées aux appareils.</span><span class="sxs-lookup"><span data-stu-id="94ddc-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="94ddc-126">La gestion des appareils peut être utilisée à la fois pour autoriser l’accès en pushant des certificats ou pour restreindre l’accès avec une variété de restrictions d’appareil.</span><span class="sxs-lookup"><span data-stu-id="94ddc-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="94ddc-127">Dans de nombreux cas, les appareils peuvent avoir des restrictions de connectivité telles que Bluetooth, VPN, USB ou même la connexion à l’appareil photo ou au microphone.</span><span class="sxs-lookup"><span data-stu-id="94ddc-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="94ddc-128">Si l’un de ces intérêts vous intéresse, nous vous encourageons à lire notre [page commune de restrictions d’appareil](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="94ddc-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="94ddc-129">Il existe d’autres restrictions d’appareil plus complexes que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="94ddc-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="94ddc-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="94ddc-130">Such as:</span></span>

- <span data-ttu-id="94ddc-131">Limiter les pages qui peuvent être vues dans l’application Paramètres à l’aide de [SettingsPageVisibility,](settings-uri-list.md)ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils doivent ajuster, par exemple en modifiant leur connexion Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="94ddc-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="94ddc-132">Utilisez [le mode plein](hololens-kiosk.md) écran pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil.</span><span class="sxs-lookup"><span data-stu-id="94ddc-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="94ddc-133">Vous pouvez définir des kiosques pour afficher une seule application ou plusieurs applications avec une page de démarrage personnalisée.</span><span class="sxs-lookup"><span data-stu-id="94ddc-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="94ddc-134">Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="94ddc-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="94ddc-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) pour empêcher le lancement complet d’applications ou de processus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="94ddc-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="94ddc-136">Si vous souhaitez en savoir plus sur les différentes méthodes de gestion des appareils ou les restrictions d’appareil, prenez l’étape suivante et lisez notre vue d’ensemble de la gestion des périphériques.</span><span class="sxs-lookup"><span data-stu-id="94ddc-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="94ddc-137">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="94ddc-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94ddc-138">Lire la vue d’ensemble des CSP et de la gestion des périphériques</span><span class="sxs-lookup"><span data-stu-id="94ddc-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)