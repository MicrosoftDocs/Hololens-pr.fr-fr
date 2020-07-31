---
title: Accès global affecté
description: Guide pour l’utilisation des OMA-URI pour les Kiosques Accès affecté
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1a0a3eb8ef3d21b34e13711bcc890af57e5ae2c2
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902299"
---
# <span data-ttu-id="dd07f-104">Accès global affecté – Kiosque</span><span class="sxs-lookup"><span data-stu-id="dd07f-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="dd07f-105">Cette fonctionnalité configure l’appareil Hololens 2 pour le mode kiosque de plusieurs applications applicable au niveau du système, ne dispose d’aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se connectent à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="dd07f-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="dd07f-106">Pour l’instant, cette fonctionnalité est uniquement disponible dans les builds Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="dd07f-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="dd07f-107">Si vous souhaitez essayer cette fonctionnalité avant qu’elle ne soit généralement disponible dans les versions HoloLens, veuillez en savoir plus sur builds [Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="dd07f-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="dd07f-108">Comment l’utiliser dans Intune?</span><span class="sxs-lookup"><span data-stu-id="dd07f-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="dd07f-109">Notez les zones marquées par «<!-».</span><span class="sxs-lookup"><span data-stu-id="dd07f-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="dd07f-110">Dans ces zones, vous devez apporter des modifications en fonction de vos préférences.</span><span class="sxs-lookup"><span data-stu-id="dd07f-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="dd07f-111">Créez un profil de configuration d’appareil OMA URI personnalisé comme suit et appliquez-le au groupe de périphériques HoloLens: ![accès global affecté OMA-URI dans Intune</span><span class="sxs-lookup"><span data-stu-id="dd07f-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="dd07f-112">Pour valeur, mettre à jour et coller le contenu suivant:</span><span class="sxs-lookup"><span data-stu-id="dd07f-112">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="dd07f-113">Comment utiliser ceci dans le Concepteur de configuration Windows?</span><span class="sxs-lookup"><span data-stu-id="dd07f-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="dd07f-114">Mettez à jour et enregistrez le blob XML mentionné ci-dessus en tant que fichier XML.</span><span class="sxs-lookup"><span data-stu-id="dd07f-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="dd07f-115">Suivez les étapes décrites dans [Utiliser un package d’approvisionnement pour configurer une borne d’application ou une station multi-applications](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), notamment la section «Prov.</span><span class="sxs-lookup"><span data-stu-id="dd07f-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="dd07f-116">Pack, étape 2: ajouter le fichier XML de configuration Kiosque à un package d’approvisionnement» et faire référence au fichier XML enregistré à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="dd07f-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="dd07f-117">Puis-je créer une configuration où le groupe général s’applique à tout le monde sauf 1 compte AAD ou un groupe AAD?</span><span class="sxs-lookup"><span data-stu-id="dd07f-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="dd07f-118">Oui, consultez l’exemple d’objet blob XML ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="dd07f-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="dd07f-119">Le profil d’accès attribué global est appliqué sur Hololens lorsque celui-ci n’est pas trouvé pour l’utilisateur connecté. Par conséquent, il s’agit de la configuration par défaut en mode kiosque pour l’utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="dd07f-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="dd07f-120">Voici un exemple de blob XML à utiliser :</span><span class="sxs-lookup"><span data-stu-id="dd07f-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="dd07f-121">N’oubliez pas les zones mises en surbrillance avec <!-nécessitent des modifications de votre part en fonction de vos préférences.</span><span class="sxs-lookup"><span data-stu-id="dd07f-121">Please be aware of the highlighted areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="dd07f-122">Exclusion de DeviceOwners dans le profil d’accès attribué global</span><span class="sxs-lookup"><span data-stu-id="dd07f-122">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="dd07f-123">Cette fonctionnalité permet à un utilisateur considéré comme «[Propriétaire d’appareil](security-adminless-os.md)» sur Hololens d’être exclu de l’accès attribué global.</span><span class="sxs-lookup"><span data-stu-id="dd07f-123">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="dd07f-124">Pour tirer parti de cette fonctionnalité, dans le blob XML pour la configuration Kiosque multi-applications, vérifiez que les lignes mises en surbrillance sont ajoutées:</span><span class="sxs-lookup"><span data-stu-id="dd07f-124">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
