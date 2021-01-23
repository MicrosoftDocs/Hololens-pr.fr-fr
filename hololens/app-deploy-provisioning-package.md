---
title: Package d’approvisionnement
description: Découvrez l’empaquetage, l’approvisionnement, le déploiement et le déploiement d’applications d’entreprise pour les appareils HoloLens.
keywords: application, déploiement d’application, déploiement d’applications d’entreprise, approvisionnement
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283695"
---
# Package d’approvisionnement

Les packages d’approvisionnement peuvent être utilisés pour préparer et configurer des appareils dans un environnement sans accès à la gestion des points de terminaison. Ils peuvent également être déployés sur un appareil quelle que soit l’identité de l’utilisateur, l’état d’inscription, pendant la OOBE (Out of Box Experience) ou en appliquant un package d’approvisionnement lors de [l’installation.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## Considérations sur les packages d’approvisionnement :

* Applications non publiques
* Chargement côté USB uniquement
* Aucune mise à jour automatique (nécessite des mises à jour manuelles via les ppkgs)

Les applications installées via un package d’approvisionnement doivent être signées par un certificat dans le magasin d’ordinateurs local. Les packages d’approvisionnement peuvent uniquement installer des certificats dans le magasin d’appareils (ordinateur local), par conséquent une application et un certificat peuvent être installés via le même package d’approvisionnement. Si vous déployez votre certificat à partir [](certificate-manager.md)de la gestion des applications mobiles ou que vous effectuez l’installation via le Gestionnaire de certificats, veillez à déployer le certificat sur le magasin d’ordinateurs local pour signer les applications installées de cette façon.

Pour découvrir les principes de base de la création d’un package d’approvisionnement pour les appareils HoloLens, visitez [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning). Pour déployer une application, vous devez commencer par l’approvisionnement avancé.

> [!NOTE]
> HoloLens (1ère génération) offre une prise en charge limitée de l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package d’approvisionnement. Les appareils HoloLens (1ère génération) ne peuvent installer une application via PPKG qu’en OOBE et uniquement avec les installations de contexte utilisateur.

## Configuration

Dans le [Concepteur de configuration Windows,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) quatre étapes sont nécessaires.

1. Définissez ApplicationManagement/AllowAllTrustedApps sur « Oui ». Voir : [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Accédez **à UniversalAppInstall**  >  **UserContextAppLicense** et entrez **PackageFamilyName**. Voir [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Voir aussi : [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Vous pouvez utiliser Device Portal sur un appareil sur qui vous avez déjà installé votre application. Visitez la page Applications et regardez la ligne PackageRelativeID, toutes les informations avant le « ! » Est votre **PackageFamilyName**.

3. Vous verrez ensuite que vous avez une nouvelle section, **ApplicationFile**. Utilisez cette zone pour télécharger votre offre groupée appx.

4. Selon que vous avez acheté votre application ou créé votre propre application LOB, vous devez télécharger le fichier de licence ou le certificat de sécurité.

    - Pour le fichier de licence : accédez à **UniversalAppInstall**  >  **UserContextAppLicence** et accédez à l’emplacement de votre licence et téléchargez-la.
    - Pour le fichier de sécurité, accédez à **Certificats** et sélectionnez votre certificat à installer en même temps que votre fichier groupé .appx.

Veillez à enregistrer votre projet dans un emplacement sécurisé. Ensuite, **exporte-le** en tant que package **d’approvisionnement.**  

Voir aussi : [Appliquez votre package d’approvisionnement à HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
