---
title: Guide de déploiement – Cloud connecté HoloLens 2 déploiement à grande échelle avec l’assistance à distance-maintenance
description: restez à jour grâce à nos conseils pour la maintenance et la prise en charge des appareils HoloLens sur un réseau connecté au Cloud.
keywords: HoloLens, gestion, cloud connecté, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635158"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="f5577-104">Mettre à jour-guide connecté au Cloud</span><span class="sxs-lookup"><span data-stu-id="f5577-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="f5577-105">Mises à jour</span><span class="sxs-lookup"><span data-stu-id="f5577-105">Updates</span></span>

<span data-ttu-id="f5577-106">Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans Windows Update, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="f5577-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="f5577-107">découvrez comment [gérer les mises à jour HoloLens](/hololens/hololens-updates) , y compris les jours planifiés, l’heure planifiée et la définition des heures actives sur l’appareil afin qu’il soit mis à jour en dehors des heures de travail.</span><span class="sxs-lookup"><span data-stu-id="f5577-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="f5577-108">l’assistance à distance est une application In-Box et peut être mise à jour via l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f5577-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="f5577-109">pour toutes les applications téléchargées par le biais du Microsoft Store elles peuvent être [mises à jour manuellement via l’application Microsoft Store](/hololens/holographic-store-apps#update-apps) elle-même.</span><span class="sxs-lookup"><span data-stu-id="f5577-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="f5577-110">Plan de support</span><span class="sxs-lookup"><span data-stu-id="f5577-110">Support Plan</span></span>

<span data-ttu-id="f5577-111">Un plan de support est un excellent élément à mettre en place.</span><span class="sxs-lookup"><span data-stu-id="f5577-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="f5577-112">une personne ou un groupe est formé à la résolution des problèmes du processus d’inscription sur les appareils HoloLens et l’utilisation générale de l’appareil HoloLens au sein de votre organisation est utile.</span><span class="sxs-lookup"><span data-stu-id="f5577-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="f5577-113">Pour permettre aux utilisateurs de résoudre plus rapidement leurs problèmes, nous vous suggérons de traiter votre processus d’escalade de la même manière :</span><span class="sxs-lookup"><span data-stu-id="f5577-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="f5577-114">Votre support technique.</span><span class="sxs-lookup"><span data-stu-id="f5577-114">Your Support desk.</span></span>
2. <span data-ttu-id="f5577-115">votre équipe d’experts HoloLens</span><span class="sxs-lookup"><span data-stu-id="f5577-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="f5577-116">[documentation HoloLens](/hololens/)  /  [documentation sur la résolution des problèmes HoloLens](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="f5577-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="f5577-117">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="f5577-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="f5577-118">Plan de développement</span><span class="sxs-lookup"><span data-stu-id="f5577-118">Development Plan</span></span>

<span data-ttu-id="f5577-119">Une fois votre appareil inscrit, vous êtes prêt à déployer des applications métier (applications métier) sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="f5577-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="f5577-120">Il s’agit d’applications personnalisées conçues pour votre organisation&#39;besoins.</span><span class="sxs-lookup"><span data-stu-id="f5577-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="f5577-121">Si vous disposez déjà d’une application métier, vous&#39;préparer [le déploiement de votre application via MDM](/hololens/app-deploy-intune).</span><span class="sxs-lookup"><span data-stu-id="f5577-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="f5577-122">si vous&#39;d préférer une autre méthode, consultez la [vue d’ensemble du déploiement de l’application pour HoloLens 2](/hololens/app-deploy-overview) pour en savoir plus sur les méthodes de déploiement de votre application métier sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="f5577-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="f5577-123">Si vous&#39;avez pas encore créé votre propre application métier ou que vous êtes en train de créer, passez en revue nos documents de développement de réalité mixte pour [commencer à concevoir et](/windows/mixed-reality/design/design) à créer des prototypes ou à apprendre les concepts fondamentaux pour commencer [à utiliser le développement de la réalité mixte.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="f5577-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="f5577-124">Gestion des appareils</span><span class="sxs-lookup"><span data-stu-id="f5577-124">Device Management</span></span> 

<span data-ttu-id="f5577-125">Bien que ce guide soit abordé sur la configuration de la gestion des appareils mobiles (MDM), il n’a pas été utilisé pour appliquer des restrictions d’appareil ou des stratégies ont été appliquées aux appareils.</span><span class="sxs-lookup"><span data-stu-id="f5577-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="f5577-126">La gestion des appareils peut être utilisée pour autoriser l’accès en envoyant des certificats ou limiter l’accès avec diverses restrictions d’appareil.</span><span class="sxs-lookup"><span data-stu-id="f5577-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="f5577-127">dans de nombreux cas, les appareils peuvent avoir des restrictions de connectivité, telles que Bluetooth, VPN, USB ou même désactiver l’accès à l’appareil photo ou au microphone.</span><span class="sxs-lookup"><span data-stu-id="f5577-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="f5577-128">Si l’un de ces avantages vous intéresse, nous vous invitons à lire notre [page des restrictions d’appareils courantes](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="f5577-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="f5577-129">Il existe d’autres restrictions d’appareil plus complexes que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="f5577-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="f5577-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f5577-130">Such as:</span></span>

- <span data-ttu-id="f5577-131">limitation des pages qui peuvent être affichées dans l’application Paramètres à l’aide de [SettingsPageVisibility](settings-uri-list.md), ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils ont besoin d’ajuster, par exemple la modification de leur connexion Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="f5577-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="f5577-132">Utilisez le [mode plein écran](hololens-kiosk.md) pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil.</span><span class="sxs-lookup"><span data-stu-id="f5577-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="f5577-133">Vous pouvez définir des bornes pour afficher une seule application ou plusieurs applications avec une page de démarrage personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f5577-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="f5577-134">Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5577-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="f5577-135">[le contrôle d’Application Windows (WDAC)](windows-defender-application-control-wdac.md) pour empêcher l’exécution complète d’applications ou de processus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f5577-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="f5577-136">Si vous souhaitez en savoir plus sur les différentes méthodes de gestion des appareils ou sur les restrictions de l’appareil, effectuez l’étape suivante et lisez notre vue d’ensemble de la gestion des appareils.</span><span class="sxs-lookup"><span data-stu-id="f5577-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5577-137">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="f5577-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5577-138">Lire la présentation de la gestion des fournisseurs de services et des appareils</span><span class="sxs-lookup"><span data-stu-id="f5577-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)