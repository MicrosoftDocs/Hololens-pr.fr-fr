---
title: Guide de déploiement-déploiement d’HoloLens 2 connecté dans le Cloud à l’échelle de l’assistance à distance-maintenance
description: Conseils pour la mise à jour des appareils HoloLens via un réseau connecté au Cloud
keywords: HoloLens, gestion, Cloud connecté, assistance à distance, AAD, Azure AD, GPM, gestion des appareils mobiles
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252695"
---
# <span data-ttu-id="c8a45-104">Maintenance-Guide connecté dans le Cloud</span><span class="sxs-lookup"><span data-stu-id="c8a45-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="c8a45-105">Mises à jour</span><span class="sxs-lookup"><span data-stu-id="c8a45-105">Updates</span></span>

<span data-ttu-id="c8a45-106">Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="c8a45-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="c8a45-107">Découvrez comment [gérer les mises à jour de HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , y compris les jours prévus, les heures prévues et définir les heures d’activité sur l’appareil pour qu’elle soit mise à jour en dehors des heures de travail.</span><span class="sxs-lookup"><span data-stu-id="c8a45-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="c8a45-108">L’assistance à distance est une application In-Box, qui peut être mise à jour par le biais de l’application Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="c8a45-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="c8a45-109">Pour toutes les applications téléchargées via le Microsoft Store, celles-ci peuvent être [mises à jour manuellement par le biais de l’application Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .</span><span class="sxs-lookup"><span data-stu-id="c8a45-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="c8a45-110">Plan de support</span><span class="sxs-lookup"><span data-stu-id="c8a45-110">Support Plan</span></span>

<span data-ttu-id="c8a45-111">Un plan d’assistance est un excellent point de départ.</span><span class="sxs-lookup"><span data-stu-id="c8a45-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="c8a45-112">Une personne ou un groupe est formé à la résolution des problèmes liés au processus d’inscription sur les appareils HoloLens et à l’utilisation générale du périphérique HoloLens au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c8a45-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="c8a45-113">Pour permettre à vos utilisateurs d’avoir une résolution plus rapide de leurs problèmes, nous vous suggérons de traiter le processus de remontée comme suit:</span><span class="sxs-lookup"><span data-stu-id="c8a45-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="c8a45-114">Votre support technique.</span><span class="sxs-lookup"><span data-stu-id="c8a45-114">Your Support desk.</span></span>
2. <span data-ttu-id="c8a45-115">Votre équipe HoloLens expert</span><span class="sxs-lookup"><span data-stu-id="c8a45-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="c8a45-116">[Documents HoloLens](https://docs.microsoft.com/hololens/)  /  [Documents de dépannage HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="c8a45-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="c8a45-117">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="c8a45-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="c8a45-118">Plan de développement</span><span class="sxs-lookup"><span data-stu-id="c8a45-118">Development Plan</span></span>

<span data-ttu-id="c8a45-119">À l’inscription de votre appareil, vous êtes maintenant prêt à déployer des applications métier (LOB) sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="c8a45-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="c8a45-120">Il s’agit d’applications personnalisées conçues pour le&#39;de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c8a45-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="c8a45-121">Si vous disposez déjà d’une application métier, vous&#39;de nouveau à [déployer votre application via la gestion des](https://docs.microsoft.com/hololens/app-deploy-intune)périphériques mobiles.</span><span class="sxs-lookup"><span data-stu-id="c8a45-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="c8a45-122">Si vous&#39;d préfère une méthode différente, passez en revue la [vue d’ensemble du déploiement d’applications pour HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) pour découvrir d’autres méthodes de déploiement de votre application métier sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="c8a45-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="c8a45-123">Si vous&#39;que vous avez déjà créé votre propre application métier ou si vous êtes en train de créer votre propre application métier, passez en revue nos documents de développement de réalité mixte pour [commencer à concevoir et créer un prototype](https://docs.microsoft.com/windows/mixed-reality/design/design) ou découvrir les principaux concepts de mise en route du développement d’une [réalité mixte.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="c8a45-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="c8a45-124">Gestion des périphériques</span><span class="sxs-lookup"><span data-stu-id="c8a45-124">Device Management</span></span> 

<span data-ttu-id="c8a45-125">Ce guide propos de la configuration de la gestion des périphériques mobiles (GPM), il n’a pas été utilisé pour appliquer des restrictions à des appareils ou des stratégies.</span><span class="sxs-lookup"><span data-stu-id="c8a45-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="c8a45-126">La gestion des appareils peut être utilisée pour autoriser l’accès par le biais de certificats ou limiter l’accès avec diverses restrictions d’appareil.</span><span class="sxs-lookup"><span data-stu-id="c8a45-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="c8a45-127">Dans de nombreux cas, les appareils peuvent être dotés de restrictions de connectivité, tels que Bluetooth, VPN, USB ou même la désactivation de l’accès à l’appareil photo ou au microphone.</span><span class="sxs-lookup"><span data-stu-id="c8a45-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="c8a45-128">Si l’un de ces éléments vous intéresse, nous vous encourageons à lire notre [page de restrictions d’appareil commune](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="c8a45-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="c8a45-129">Vous pouvez utiliser d’autres restrictions d’appareils plus complexes.</span><span class="sxs-lookup"><span data-stu-id="c8a45-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="c8a45-130">Par exemple:</span><span class="sxs-lookup"><span data-stu-id="c8a45-130">Such as:</span></span>

- <span data-ttu-id="c8a45-131">Limiter les pages qui peuvent être affichées dans l’application paramètres en utilisant [SettingsPageVisibility](settings-uri-list.md), ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils ont besoin d’ajuster, par exemple de modifier leur connexion Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c8a45-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="c8a45-132">Utiliser le [mode plein écran](hololens-kiosk.md) pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil.</span><span class="sxs-lookup"><span data-stu-id="c8a45-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="c8a45-133">Vous pouvez définir des bornes pour afficher une application unique ou plusieurs applications avec une page de démarrage personnalisée.</span><span class="sxs-lookup"><span data-stu-id="c8a45-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="c8a45-134">Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c8a45-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="c8a45-135">[Contrôle d’application Windows (WDac)](windows-defender-application-control-wdac.md) pour assurer la totalité du lancement d’applications ou de processus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c8a45-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="c8a45-136">Si vous souhaitez en savoir plus sur les différentes méthodes de gestion des appareils ou de restrictions d’appareil, passez à l’étape suivante et consultez notre présentation de la gestion des périphériques.</span><span class="sxs-lookup"><span data-stu-id="c8a45-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="c8a45-137">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="c8a45-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8a45-138">Lire l’aperçu des fournisseurs de services de cryptographie et de gestion des appareils</span><span class="sxs-lookup"><span data-stu-id="c8a45-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)