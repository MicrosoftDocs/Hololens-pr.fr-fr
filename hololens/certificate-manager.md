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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397450"
---
# <a name="certificate-manager"></a><span data-ttu-id="4681b-103">Gestionnaire de certificats</span><span class="sxs-lookup"><span data-stu-id="4681b-103">Certificate Manager</span></span>

- <span data-ttu-id="4681b-104">Amélioration de l’audit, du diagnostic et des outils de validation pour la sécurité et la conformité des appareils par le biais du nouveau gestionnaire de certificats.</span><span class="sxs-lookup"><span data-stu-id="4681b-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="4681b-105">Cette fonctionnalité vous permettra de déployer, de dépanner et de valider vos certificats à grande échelle dans les environnements commerciaux.</span><span class="sxs-lookup"><span data-stu-id="4681b-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="4681b-106">Dans Windows holographique, version 20H2, nous ajoutons un gestionnaire de certificats dans l’application paramètres HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4681b-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="4681b-107">Accédez à **paramètres > mettre à jour & sécurité > certificats**.</span><span class="sxs-lookup"><span data-stu-id="4681b-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="4681b-108">Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil.</span><span class="sxs-lookup"><span data-stu-id="4681b-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="4681b-109">Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs disposent désormais d’outils d’audit, de diagnostic et de validation améliorés pour garantir que les appareils restent sécurisés et conformes.</span><span class="sxs-lookup"><span data-stu-id="4681b-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="4681b-110">**Audit :** Possibilité de valider le déploiement correct d’un certificat ou de confirmer qu’il a été supprimé de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="4681b-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="4681b-111">**Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de faciliter la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="4681b-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="4681b-112">**Validation :** Vérifier qu’un certificat est destiné à l’usage prévu et qu’il fonctionne, peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux avant de déployer des certificats à grande échelle.</span><span class="sxs-lookup"><span data-stu-id="4681b-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="4681b-113">Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="4681b-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="4681b-114">Les utilisateurs peuvent également rechercher directement un certificat.</span><span class="sxs-lookup"><span data-stu-id="4681b-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="4681b-115">Pour afficher les propriétés d’un certificat, sélectionnez le certificat, puis cliquez sur **info**.</span><span class="sxs-lookup"><span data-stu-id="4681b-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="4681b-116">L’installation de certificat prend actuellement en charge les fichiers. cer et. CRT.</span><span class="sxs-lookup"><span data-stu-id="4681b-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="4681b-117">Les propriétaires d’appareils peuvent installer des certificats sur l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent s’installer que dans l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="4681b-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="4681b-118">Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres.</span><span class="sxs-lookup"><span data-stu-id="4681b-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="4681b-119">Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.</span><span class="sxs-lookup"><span data-stu-id="4681b-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="4681b-120">Pour installer un certificat :</span><span class="sxs-lookup"><span data-stu-id="4681b-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="4681b-121">Connectez votre HoloLens 2 à un PC.</span><span class="sxs-lookup"><span data-stu-id="4681b-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="4681b-122">Placez le fichier de certificat que vous souhaitez installer dans un emplacement sur votre HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4681b-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="4681b-123">Accédez à **paramètres application > mettre à jour & sécurité > certificats**, puis sélectionnez Installer un certificat.</span><span class="sxs-lookup"><span data-stu-id="4681b-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="4681b-124">Cliquez sur **Importer un fichier** et accédez à l’emplacement où vous avez enregistré le certificat.</span><span class="sxs-lookup"><span data-stu-id="4681b-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="4681b-125">Sélectionnez **emplacement du magasin**.</span><span class="sxs-lookup"><span data-stu-id="4681b-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="4681b-126">Sélectionnez **magasin de certificats**.</span><span class="sxs-lookup"><span data-stu-id="4681b-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="4681b-127">Cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="4681b-127">Click **Install**.</span></span>

<span data-ttu-id="4681b-128">Le certificat doit maintenant être installé sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="4681b-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="4681b-129">Pour supprimer un certificat :</span><span class="sxs-lookup"><span data-stu-id="4681b-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="4681b-130">Bien que vous puissiez afficher les certificats déployés via MDM dans le gestionnaire de certificats, vous ne pouvez pas les désinstaller dans le gestionnaire de certificats.</span><span class="sxs-lookup"><span data-stu-id="4681b-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="4681b-131">Vous devez les désinstaller via MDM.</span><span class="sxs-lookup"><span data-stu-id="4681b-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="4681b-132">Accédez à **paramètres application > mise à jour et sécurité > certificats**.</span><span class="sxs-lookup"><span data-stu-id="4681b-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="4681b-133">Recherchez le certificat par son nom dans la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="4681b-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="4681b-134">Sélectionnez le certificat.</span><span class="sxs-lookup"><span data-stu-id="4681b-134">Select the certificate.</span></span>
1. <span data-ttu-id="4681b-135">Cliquez sur **supprimer**</span><span class="sxs-lookup"><span data-stu-id="4681b-135">Click **Remove**</span></span>
1. <span data-ttu-id="4681b-136">Lorsque vous êtes invité à confirmer l’opération, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4681b-136">Select **Yes** when prompted for confirmation.</span></span>



![Visionneuse de certificats dans l’application paramètres sous certificats](images/certificate-viewer-device.jpg)

![Image illustrant l’utilisation de l’interface utilisateur de certificat pour installer un certificat dans les paramètres.](images/certificate-device-install.jpg)
