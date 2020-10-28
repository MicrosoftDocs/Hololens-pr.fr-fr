---
title: Comment installer des applications via le programme d’installation Web
description: Installer des applications via le programme d’installation Web du programme d’installation d’applications
keywords: gestion des applications, application, hololens, programme d’installation de l’application, installation Web
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135441"
---
# <span data-ttu-id="4169d-104">Installation d’applications à partir d’une page Web</span><span class="sxs-lookup"><span data-stu-id="4169d-104">Installing apps from a web page</span></span>

<span data-ttu-id="4169d-105">Les utilisateurs peuvent installer une application directement à partir d’un serveur Web.</span><span class="sxs-lookup"><span data-stu-id="4169d-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="4169d-106">Cela nécessite une utilisation du programme d’installation de l’application combinée à une méthode simple de distribution et d’installation.</span><span class="sxs-lookup"><span data-stu-id="4169d-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4169d-107">Pour le moment, cette fonctionnalité est uniquement avalible dans les builds Insider 19041.1366 +.</span><span class="sxs-lookup"><span data-stu-id="4169d-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="4169d-108">En [savoir plus sur l’inscription aux builds Insider pour Windows](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="4169d-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="4169d-109">Configuration:</span><span class="sxs-lookup"><span data-stu-id="4169d-109">How to set this up:</span></span>
1.  <span data-ttu-id="4169d-110">Assurez-vous que votre application est correctement configurée pour l’installation.</span><span class="sxs-lookup"><span data-stu-id="4169d-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="4169d-111">Procédez comme [suit pour l’activer sur une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="4169d-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="4169d-112">Choisissez une méthode de déploiement de certificats.</span><span class="sxs-lookup"><span data-stu-id="4169d-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="4169d-113">Les [packages de mise en service](hololens-provisioning.md) peuvent être appliqués aux périphériques locaux.</span><span class="sxs-lookup"><span data-stu-id="4169d-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="4169d-114">La gestion des périphériques mobiles peut être utilisée pour [appliquer des certificats avec des configurations d’appareil](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="4169d-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="4169d-115">Utiliser le gestionnaire de [certificats](hololens-insider.md#certificate-manager)d’appareil.</span><span class="sxs-lookup"><span data-stu-id="4169d-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="4169d-116">Utilisation de l’utilisateur final:</span><span class="sxs-lookup"><span data-stu-id="4169d-116">End User Experience:</span></span>
1.  <span data-ttu-id="4169d-117">Un utilisateur reçoit et installe un certificat sur l’appareil à l’aide de la méthode choisie précédemment.</span><span class="sxs-lookup"><span data-stu-id="4169d-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="4169d-118">Un utilisateur visite l’URL créée à l’étape ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4169d-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="4169d-119">L’application sera désormais installée sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="4169d-119">The app will now install to the device.</span></span> <span data-ttu-id="4169d-120">Pour Rechercher l’application, ouvrez le **menu Démarrer** , puis sélectionnez le bouton **toutes les applications** pour rechercher votre application.</span><span class="sxs-lookup"><span data-stu-id="4169d-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="4169d-121">Pour obtenir de l’aide pour résoudre ce problème, consultez la rubrique [résoudre les problèmes du programme](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)d’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="4169d-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="4169d-122">Le processus de mise à jour de l’interface utilisateur n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4169d-122">UI during the update process is not supported.</span></span> <span data-ttu-id="4169d-123">Par conséquent, l’option ShowPrompt sur [cette page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) et les options associées ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4169d-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
