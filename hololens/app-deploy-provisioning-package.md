---
title: Package d’approvisionnement
description: En savoir plus sur l’empaquetage d’applications, l’approvisionnement, le déploiement et le déploiement d’applications d’entreprise pour les appareils HoloLens.
keywords: application, déploiement d’applications, déploiement d’applications d’entreprise, approvisionnement
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308733"
---
# <a name="provisioning-package"></a>Package d’approvisionnement

Les packages de configuration peuvent être utilisés pour préparer et configurer des appareils dans un environnement sans accès à la gestion des points de terminaison. Ils peuvent également être déployés sur un appareil, quelle que soit l’identité de l’utilisateur, l’état de l’inscription, pendant l’expérience OOBE (out of Box Experience) ou l' [application d’un package de configuration pendant l’installation](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Considérations sur les packages d’approvisionnement :

* Applications non publiques
* Chargement côté USB uniquement
* Aucune mise à jour automatique (nécessite des mises à jour manuelles via PPKGs)

Les applications installées à l’aide d’un package d’approvisionnement doivent être signées par un certificat dans le magasin de l’ordinateur local. Les packages d’approvisionnement peuvent uniquement installer des certificats sur le magasin de l’appareil (ordinateur local). par conséquent, une application et un certificat peuvent être installés par le biais du même package de configuration. Si vous déployez votre certificat à partir de MDM ou que vous installez via le [Gestionnaire de certificats](certificate-manager.md), veillez à déployer le certificat dans le magasin de l’ordinateur local pour signer les applications installées de cette manière.

Pour découvrir les principes de base de la création d’un package d’approvisionnement pour les appareils HoloLens, consultez [approvisionnement de hololens](https://docs.microsoft.com/hololens/hololens-provisioning). Pour déployer une application, vous devez commencer par l’approvisionnement avancé.

> [!NOTE]
> HoloLens (1ère génération) a limité la prise en charge de l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package d’approvisionnement. Les appareils HoloLens (1er génération) prennent uniquement en charge l’installation d’une application via PPKG uniquement au cours de l’installation OOBE et uniquement avec les installations de contexte utilisateur.

## <a name="setup"></a>Installation

Dans le [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , suivez les quatre étapes ci-dessous.

1. Définissez ApplicationManagement/AllowAllTrustedApps sur « Oui ». Voir : [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Accédez à **UniversalAppInstall**  >  **UserContextAppLicense** entrez le **PackageFamilyName**. Consultez [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Voir aussi : [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Vous pouvez utiliser le portail des appareils sur un appareil sur lequel vous avez déjà installé votre application. Accédez à la page applications, puis examinez la ligne PackageRelativeID, toutes les informations avant le «  ! » Est votre **PackageFamilyName**.

3. Vous verrez alors que vous avez une nouvelle section, **ApplicationFile**. Utilisez cette zone pour charger votre bundle Appx.

4. Selon que vous avez acheté votre application ou créé votre propre application métier, vous devez télécharger le fichier de licence ou le certificat de sécurité.

    - Pour le fichier de licence : accédez à **UniversalAppInstall**  >  **UserContextAppLicence** et accédez à l’emplacement de votre licence et chargez-le.
    - Pour le fichier de sécurité, accédez à **certificats** , puis sélectionnez votre certificat à installer en même temps que votre bundle. Appx.

Veillez à enregistrer votre projet dans un emplacement sécurisé. Ensuite, **exportez** -le en tant que **package d’approvisionnement**.  

Voir aussi : [appliquez votre package d’approvisionnement à HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
