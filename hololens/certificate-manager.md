---
title: Gestionnaire de certificats
description: Découvrez comment installer, gérer et supprimer manuellement des certificats sur des appareils de réalité mixte HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283685"
---
# <span data-ttu-id="3e82f-103">Gestionnaire de certificats</span><span class="sxs-lookup"><span data-stu-id="3e82f-103">Certificate Manager</span></span>

- <span data-ttu-id="3e82f-104">Amélioration des outils d’audit, de diagnostic et de validation pour la sécurité et la conformité des appareils via le nouveau Gestionnaire de certificats.</span><span class="sxs-lookup"><span data-stu-id="3e82f-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="3e82f-105">Cette fonctionnalité vous permettra de déployer, dépanner et valider vos certificats à l’échelle des environnements commerciaux.</span><span class="sxs-lookup"><span data-stu-id="3e82f-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="3e82f-106">Dans Windows Holographic, version 20H2, nous ajoutons un gestionnaire de certificats dans l’application Paramètres HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3e82f-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="3e82f-107">Go to **Settings > Update & Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="3e82f-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="3e82f-108">Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="3e82f-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="3e82f-109">Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir que les appareils restent sécurisés et conformes.</span><span class="sxs-lookup"><span data-stu-id="3e82f-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="3e82f-110">**Audit :** Possibilité de vérifier qu’un certificat est déployé correctement ou de confirmer qu’il a été supprimé correctement.</span><span class="sxs-lookup"><span data-stu-id="3e82f-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="3e82f-111">**Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="3e82f-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="3e82f-112">**Validation :** Vérifier qu’un certificat a l’objectif et qu’il est fonctionnel peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux, avant de déployer des certificats à grande échelle.</span><span class="sxs-lookup"><span data-stu-id="3e82f-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="3e82f-113">Pour trouver rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="3e82f-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="3e82f-114">Les utilisateurs peuvent également rechercher directement un certificat.</span><span class="sxs-lookup"><span data-stu-id="3e82f-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="3e82f-115">Pour afficher des propriétés de certificat individuelles, sélectionnez le certificat et cliquez sur **Info.**</span><span class="sxs-lookup"><span data-stu-id="3e82f-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="3e82f-116">L’installation de certificat prend actuellement en charge les fichiers .cer et .crt.</span><span class="sxs-lookup"><span data-stu-id="3e82f-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="3e82f-117">Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel ;  Tous les autres utilisateurs peuvent uniquement s’installer dans l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="3e82f-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="3e82f-118">Les utilisateurs peuvent uniquement supprimer les certificats installés directement à partir de l’interface utilisateur paramètres.</span><span class="sxs-lookup"><span data-stu-id="3e82f-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="3e82f-119">Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.</span><span class="sxs-lookup"><span data-stu-id="3e82f-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="3e82f-120">Pour installer un certificat :</span><span class="sxs-lookup"><span data-stu-id="3e82f-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="3e82f-121">Connectez votre HoloLens 2 à un PC.</span><span class="sxs-lookup"><span data-stu-id="3e82f-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="3e82f-122">Placez le fichier de certificat que vous souhaitez installer à un emplacement sur votre HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3e82f-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="3e82f-123">Accédez **à Paramètres App > Update & Security > Certificates**et sélectionnez Installer un certificat.</span><span class="sxs-lookup"><span data-stu-id="3e82f-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="3e82f-124">Cliquez **sur Importer un** fichier et accédez à l’emplacement où vous avez enregistré le certificat.</span><span class="sxs-lookup"><span data-stu-id="3e82f-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="3e82f-125">Sélectionnez **l’emplacement de la boutique.**</span><span class="sxs-lookup"><span data-stu-id="3e82f-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="3e82f-126">Sélectionnez **magasin de certificats.**</span><span class="sxs-lookup"><span data-stu-id="3e82f-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="3e82f-127">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="3e82f-127">Click **Install**.</span></span>

<span data-ttu-id="3e82f-128">Le certificat doit maintenant être installé sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="3e82f-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="3e82f-129">Pour supprimer un certificat :</span><span class="sxs-lookup"><span data-stu-id="3e82f-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="3e82f-130">Accédez à **Paramètres App > Update et Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="3e82f-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="3e82f-131">Recherchez le certificat par nom dans la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="3e82f-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="3e82f-132">Sélectionnez le certificat.</span><span class="sxs-lookup"><span data-stu-id="3e82f-132">Select the certificate.</span></span>
1. <span data-ttu-id="3e82f-133">Cliquez sur **Supprimer**</span><span class="sxs-lookup"><span data-stu-id="3e82f-133">Click **Remove**</span></span>
1. <span data-ttu-id="3e82f-134">Sélectionnez **Oui** lorsque vous y invitez une confirmation.</span><span class="sxs-lookup"><span data-stu-id="3e82f-134">Select **Yes** when prompted for confirmation.</span></span>


![Visionneuse de certificats dans l’application Paramètres sous Ceritifcates](images/certificate-viewer-device.jpg)

![Image montrant comment utiliser l’interface utilisateur certificat pour installer un certificat dans Paramètres.](images/certificate-device-install.jpg)
