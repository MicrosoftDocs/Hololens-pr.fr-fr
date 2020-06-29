---
title: Déverrouiller les fonctionnalités de Windows Holographic for Business
description: Lorsque vous effectuez une mise à niveau vers Windows holographique entreprise, HoloLens fournit des fonctionnalités supplémentaires conçues pour les entreprises.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828455"
---
# Déverrouiller les fonctionnalités de Windows Holographic for Business

> [!IMPORTANT]
> Cette page s’applique uniquement à HoloLens 1ère génération.

Microsoft HoloLens est disponible dans l' *édition Development*qui exécute Windows holographique (édition de Windows 10 conçue pour HoloLens), et dans la [suite commerciale](hololens-commercial-features.md), qui fournit des fonctionnalités supplémentaires conçues pour les entreprises.

Lorsque vous achetez la Commercial Suite, vous recevez une licence qui met à niveau WindowsHolographique vers WindowsHolographic for Business. Vous pouvez l’appliquer à l’appareil à l’aide du [fournisseur de gestion des périphériques mobiles (GPM)](#edition-upgrade-by-using-mdm) de l’organisation ou d’un [package de mise à service](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> Dans Windows 10, version 1803, vous pouvez vérifier que le HoloLens a été mis à niveau vers l’édition commerciale en sélectionnant l’option système de **paramètres**  >  **System**.

## Mise à niveau d’une édition à l’aide de la GPM

La licence d’entreprise peut être appliquée par n’importe quel fournisseur GPM qui prend en charge le [fournisseur de services de configuration (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). La dernière version de l’API Microsoft GPM prendra en charge le CSP WindowsLicensing.

Pour obtenir des instructions détaillées pour la mise à niveau de HoloLens à l’aide de Microsoft Intune, voir [mise à niveau de périphériques exécutant Windows holographique vers Windows holographique pour les entreprises](https://docs.microsoft.com/intune/holographic-upgrade).

 Sur les autres fournisseurs GPM, les étapes de configuration et de déploiement de la stratégie spécifiques peuvent varier.

## Mise à niveau d’une édition à l’aide d’un package de mise en service

Les packages de configuration sont des fichiers créés par l’outil Concepteur de configuration Windows qui appliquent une configuration spécifiée à un appareil.

### Créer un package de configuration qui met à niveau l’édition Windows Holographique

1. [Créez un package d’approvisionnement pour HoloLens.](hololens-provisioning.md)
1. Accédez à **Paramètres d’exécution** > **EditionUpgrade**, puis sélectionnez **EditionUpgradeWithLicense**.

    ![Mettez à jour l'édition avec le paramètre de licence sélectionné](images/icd1.png)

1. Recherchez le fichier de licence XML fourni lors de l’achat de la suite commerciale.

    > [!NOTE]
    > Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).

1. Dans le menu **fichier** , sélectionnez **Enregistrer**. 

1. Lisez le message d’avertissement indiquant que les fichiers de projet contiennent des informations sensibles, puis cliquez sur **OK**.

    > [!IMPORTANT]
    > Lorsque vous créez un package de mise en service, vous pouvez inclure des informations sensibles dans le fichier de projet et le package de mise en service (. ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Lorsque vous n’en avez plus besoin, vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers de projet.

1. Dans le menu **Export**, sélectionnez **Provisioning package**.

1. Remplacez le **propriétaire** par l' **administrateur informatique**, qui définit le niveau de priorité de ce package de mise à niveau de sorte qu’il soit plus élevé que d’autres utilisateurs appliqués à cet appareil à partir de sources différentes, puis sélectionnez **suivant**.

1. Définissez une valeur pour **Package Version**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

1. Dans **Sélectionner les détails de sécurité du package de mise en service**, sélectionnez **suivant**.

1. Sélectionnez **suivant** pour spécifier l’emplacement de sortie dans lequel vous souhaitez que le package de mise en service soit placé une fois qu’il est intégré. Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.

    Vous pouvez également sélectionner **Parcourir** pour changer l’emplacement de sortie par défaut.

1. Sélectionnez **Suivant**.

1. Pour commencer à générer le package, sélectionnez **Build** . La page de génération affiche les informations du projet et la barre de progression indique l’état de la Build.

1. À la fin de la build, sélectionnez **Terminer**.

### Appliquer le package d’approvisionnement à HoloLens

1. À l’aide du câble USB, connectez l’appareil à un PC. Démarrez l’appareil, mais ne poursuivez pas la **page d’accueil de l’expérience** de configuration initiale (première page avec le cadre bleu). Sur PC, HoloLens est affiché en tant qu’appareil dans l’Explorateur de fichiers.

    > [!NOTE]
    > Si le périphérique HoloLens exécute Windows 10, version 1607 ou antérieure, ouvrez l’Explorateur de fichiers en appuyant brièvement sur le **volume** et sur les boutons **d’alimentation** situés en même temps que l’appareil.

1. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.

1. Lorsque HoloLens est toujours dans la page **ajuster** , appuyez brièvement sur le **volume** , puis relâchez le bouton **d’alimentation** .

1. HoloLens vous demande si vous faites confiance au package et si vous voulez l’appliquer. Confirmez que vous faites confiance au package.

1. Vous verrez si le package a été appliqué avec succès ou non. S’il n’a pas été correctement appliqué, vous pouvez résoudre votre problème, puis réessayer. En cas de succès, continuez avec la configuration de l’appareil.
