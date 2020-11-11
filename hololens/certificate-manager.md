---
title: Gestionnaire de certificats
description: Apprenez-en davantage sur la gestion manuelle des certificats sur HoloLens 2.
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163218"
---
# <span data-ttu-id="3ec2f-103">Gestionnaire de certificats</span><span class="sxs-lookup"><span data-stu-id="3ec2f-103">Certificate Manager</span></span>

- <span data-ttu-id="3ec2f-104">Amélioration de l’audit, du diagnostic et de l’outil de validation pour la sécurité et la conformité des périphériques via le nouveau gestionnaire de certificats.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="3ec2f-105">Cette fonctionnalité vous permet de déployer, de résoudre les problèmes et de valider vos certificats à des fins d’évolution en environnement commercial.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="3ec2f-106">Dans Windows holographique, version 20H2, nous ajoutons un gestionnaire de certificats à l’application paramètres HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="3ec2f-107">Accédez à **paramètres > mettre à jour & certificats de sécurité >**.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="3ec2f-108">Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="3ec2f-109">Le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir la sécurité et la conformité des appareils.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="3ec2f-110">**Audit:** Possibilité de vérifier que le déploiement d’un certificat est correct ou qu’il a été supprimé de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="3ec2f-111">**Diagnostic:** En cas de problème, le fait de vérifier que les certificats appropriés existent sur l’appareil permet de gagner du temps et d’aider à résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="3ec2f-112">**Validation:** Le fait de vérifier qu’un certificat répond à la finalité prévue et est opérationnel, peut faire gagner du temps, en particulier dans les environnements commerciaux avant de déployer des certificats à des fins d’évolution plus importantes.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="3ec2f-113">Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="3ec2f-114">Les utilisateurs peuvent également rechercher directement un certificat.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="3ec2f-115">Pour afficher les propriétés de chaque certificat, sélectionnez le certificat, puis cliquez sur **informations**.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="3ec2f-116">Le certificat installation prend actuellement en charge les fichiers. cer et. CRT.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="3ec2f-117">Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent être installés que dans l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="3ec2f-118">Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="3ec2f-119">Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="3ec2f-120">Pour installer un certificat:</span><span class="sxs-lookup"><span data-stu-id="3ec2f-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="3ec2f-121">Connectez votre HoloLens 2 à un PC.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="3ec2f-122">Sur votre HoloLens 2, placez le fichier de certificat que vous voulez installer.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="3ec2f-123">Accédez à **paramètres de l’application > mettre à jour & sécurité > certificats**et sélectionnez Installer un certificat.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="3ec2f-124">Cliquez sur **importer le fichier** , puis accédez à l’emplacement où vous avez enregistré le certificat.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="3ec2f-125">Sélectionnez **emplacement du magasin**.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="3ec2f-126">Sélectionnez **magasin de certificats**.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="3ec2f-127">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-127">Click **Install**.</span></span>

<span data-ttu-id="3ec2f-128">Le certificat doit maintenant être installé sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="3ec2f-129">Pour supprimer un certificat:</span><span class="sxs-lookup"><span data-stu-id="3ec2f-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="3ec2f-130">Accédez à **paramètres d’application de paramètres > de mise à jour et de sécurité > certificats**.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="3ec2f-131">Recherchez le certificat par nom dans la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="3ec2f-132">Cliquez sur le certificat.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-132">Select the certificate.</span></span>
1. <span data-ttu-id="3ec2f-133">Cliquez sur **supprimer** .</span><span class="sxs-lookup"><span data-stu-id="3ec2f-133">Click **Remove**</span></span>
1. <span data-ttu-id="3ec2f-134">Sélectionnez **Oui** lorsque vous êtes invité à confirmer.</span><span class="sxs-lookup"><span data-stu-id="3ec2f-134">Select **Yes** when prompted for confirmation.</span></span>


![Visionneuse de certificats dans l’application paramètres sous Ceritifcates](images/certificate-viewer-device.jpg)

![Image illustrant l’utilisation de l’interface utilisateur de certificats pour l’installation d’un certificat dans les paramètres.](images/certificate-device-install.jpg)
