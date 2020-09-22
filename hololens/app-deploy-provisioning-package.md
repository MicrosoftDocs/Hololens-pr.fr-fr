---
title: Package d’approvisionnement
description: application, déploiement de l’application, application d’entreprise demployment, approvisionnement
keywords: application, déploiement de l’application, application d’entreprise demployment, approvisionnement
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0803b5f1b77ac7f123d534d101cd24903b87094c
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052581"
---
# Package d’approvisionnement

Les packages de mise en service peuvent être utilisés pour préparer et configurer des appareils dans un environnement sans accès à la gestion des points de terminaison. Elles peuvent également être déployées sur un appareil quelle que soit l’identité de l’utilisateur, l’état de l’inscription, lors de l’utilisation de OOBE (out-of-Box Experience) ou en [appliquant un package de mise](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)à disponibilité lors de l’installation.

## Considérations relatives aux packages de mise en service:
* Applications non publiques
* Télécharger uniquement le bus USB
* Aucune mise à jour automatique (nécessite des mises à jour manuelles via PPKGs)

> [!NOTE] 
> Pour découvrir les notions de base de la création d’un package de mise à service pour les appareils HoloLens, visitez [approvisionnement HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning). Pour déployer une application, vous devez commencer par la mise en service avancée. 

> [!NOTE] 
> HoloLens (1er génération) dispose d’une prise en charge limitée pour l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package de mise en service. Les appareils HoloLens (1ère génération) ne prennent en charge l’installation d’une application qu’avec PPKG que dans OOBE et uniquement avec les installations de contexte utilisateur.

## Configuration

Dans le [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , procédez comme suit.

1. Définissez ApplicationManagement/AllowAllTrustedApps sur «Yes». Voir: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).
2. Sous **UniversalAppInstall**  >  **UserContextAppLicense** Veuillez entrer le **propriété packagefamilyname**. Voir [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Voir aussi: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Si vous ne le connaissez pas, vous pouvez utiliser Device Portal sur un appareil sur lequel vous avez déjà installé votre application. Accédez à la page applications et examinez la ligne PackageRelativeID, toutes les informations précédant le «!». Est votre **propriété packagefamilyname**.
3. Vous verrez alors que vous avez une nouvelle section **ApplicationFile**. Utilisez cette zone pour télécharger votre bundle Appx. 
4. Selon que vous avez acheté votre application ou créé votre propre application métier, vous devrez télécharger le fichier de licence ou le certificat de sécurité.
    - Pour le fichier de licence: sous **UniversalAppInstall**  >  **UserContextAppLience** et naviguez jusqu’à l’emplacement de votre licence et chargez-le. 
    - Dans le cas d’un fichier de sécurité, accédez à **certificats** et sélectionnez votre certificat à installer avec votre bundle. Appx. 

Veillez à enregistrer votre projet dans un emplacement sécurisé. Ensuite, **exportez** -la en tant que **package de mise en service**.  
    
Voir aussi: [appliquer votre package provisiong au HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
