---
title: Déverrouiller les fonctionnalités de Windows Holographic for Business
description: lorsque vous effectuez une mise à niveau vers Windows Holographic for Business, HoloLens fournit des fonctionnalités supplémentaires conçues pour l’entreprise.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189186"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Déverrouiller les fonctionnalités de Windows Holographic for Business

> [!IMPORTANT]
> cette page s’applique uniquement à HoloLens 1re génération.

Microsoft HoloLens est disponible dans l' *édition Development*, qui s’exécute Windows holographique (une édition de Windows 10 conçue pour HoloLens) et dans la [Suite commerciale](hololens-commercial-features.md), qui offre des fonctionnalités supplémentaires conçues pour les entreprises.

lorsque vous achetez la Suite commerciale, vous recevez une licence qui met à niveau Windows holographique vers Windows Holographic for Business. Vous pouvez appliquer cette licence à l’appareil soit à l’aide du [fournisseur de gestion des appareils mobiles (MDM)](#edition-upgrade-by-using-mdm) de l’organisation, soit à l’aide d’un [package de configuration](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> dans Windows 10, la version 1803, vous pouvez vérifier que le HoloLens a été mis à niveau vers l’édition business en sélectionnant **Paramètres**  >  **système**.

## <a name="edition-upgrade-by-using-mdm"></a>Mise à niveau d’édition à l’aide de MDM

La licence d’entreprise peut être appliquée par n’importe quel fournisseur GPM qui prend en charge le [fournisseur de services de configuration (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). La dernière version de l’API Microsoft GPM prendra en charge le CSP WindowsLicensing.

pour obtenir des instructions pas à pas sur la mise à niveau de HoloLens à l’aide de Microsoft Intune, consultez [mettre à niveau des appareils exécutant Windows holographique vers Windows Holographic for Business](/intune/holographic-upgrade).

 Sur les autres fournisseurs GPM, les étapes de configuration et de déploiement de la stratégie spécifiques peuvent varier.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Mise à niveau d’édition à l’aide d’un package d’approvisionnement

les packages de provisionnement sont des fichiers créés par l’outil concepteur de configuration Windows qui appliquent une Configuration spécifiée à un appareil.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Créer un package d’approvisionnement qui met à niveau l’édition Windows Holographique

1. [Créez un package d’approvisionnement pour HoloLens.](hololens-provisioning.md)
1. Accédez à **paramètres d’exécution**  >  **EditionUpgrade**, puis sélectionnez **EditionUpgradeWithLicense**.

    ![Version de mise à niveau avec le paramètre de licence sélectionné.](images/icd1.png)

1. Recherchez le fichier de licence XML fourni lorsque vous avez acheté la suite commerciale.

    > [!NOTE]
    > Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).

1. Dans le menu **Fichier**, sélectionnez **Enregistrer**. 

1. Lisez l’avertissement indiquant que les fichiers projet peuvent contenir des informations sensibles, puis cliquez sur **OK**.

    > [!IMPORTANT]
    > Quand vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et le fichier de package de configuration (. ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers projet dans un emplacement sécurisé et supprimer les fichiers projet quand vous n’en avez plus besoin.

1. Dans le menu **Export**, sélectionnez **Provisioning package**.

1. Remplacez **propriétaire** par **administrateur informatique**, qui définit la priorité de ce package d’approvisionnement sur une valeur supérieure à celle appliquée à cet appareil à partir de différentes sources, puis sélectionnez **suivant**.

1. Définissez une valeur pour **Package Version**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

1. Dans **Sélectionner les détails de sécurité pour le package d’approvisionnement**, sélectionnez **suivant**.

1. Sélectionnez **suivant** pour spécifier l’emplacement de sortie où vous souhaitez que le package de configuration se trouve une fois qu’il a été créé. Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.

    Si vous le souhaitez, vous pouvez sélectionner **Parcourir** pour modifier l’emplacement de sortie par défaut.

1. Sélectionnez **Suivant**.

1. Sélectionnez **Build** pour commencer à générer le package. La page générer affiche les informations du projet et la barre de progression indique l’état de la Build.

1. Une fois la génération terminée, sélectionnez **Terminer**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Appliquer le package d’approvisionnement à HoloLens

1. À l’aide du câble USB, connectez l’appareil à un PC. Démarrez l’appareil, mais ne passez pas à la page **ajuster** de l’expérience d’installation initiale (première page avec la zone bleue). sur le PC, HoloLens apparaît en tant qu’appareil dans l’explorateur de fichiers.

    > [!NOTE]
    > si le HoloLens appareil exécute Windows 10, version 1607 ou antérieure, ouvrez l’explorateur de fichiers en appuyant sur la touche et en relâchant les boutons de réduction et **d’alimentation** du **Volume** simultanément sur l’appareil.

1. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.

1. bien que HoloLens soit toujours sur la page **ajuster** , appuyez brièvement sur les boutons arrêter et **redémarrer du** **Volume** et relâchez-les simultanément.

1. HoloLens vous demande si vous faites confiance au package et que vous souhaitez l’appliquer. Confirmez que vous faites confiance au package.

1. Vous verrez si le package a été appliqué avec succès ou non. S’il n’a pas été appliqué, vous pouvez corriger votre package et réessayer. En cas de réussite, effectuez la configuration de l’appareil.
