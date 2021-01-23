---
title: Chiffrement HoloLens BitLocker
description: Découvrez comment activer le chiffrement d’appareil Bitlocker pour protéger les fichiers stockés sur vos appareils HoloLens de réalité mixte.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284025"
---
# Chiffrement BitLocker HoloLens (1ère génération)

HoloLens (1ère génération) et HoloLens 2 permettent tous deux le chiffrement de l’appareil à l’aide de BitLocker. Toutefois, BitLocker est toujours activé sur HoloLens 2.

Cet article vous aidera à activer et à gérer BitLocker sur HoloLens (1ère génération).

Sur HoloLens (1ère génération), vous pouvez activer le chiffrement d’appareil BitLocker manuellement ou à l’aide de la gestion des périphériques mobiles (GDM). Suivez ces instructions pour activer le chiffrement [de l’appareil BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) afin de protéger les fichiers et les informations stockés sur HoloLens. Le chiffrement de l’appareil permet de protéger vos données à l’aide de la méthode de chiffrement AES-CBC 128, qui équivaut à la méthode [EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) dans le fournisseur de services de configuration BitLocker. Le personnel qui a la clé de chiffrement correcte (par exemple, un mot de passe) peut la déchiffrer ou effectuer une récupération de données.

## Activer le chiffrement de l’appareil à l’aide de GPM

Vous pouvez utiliser votre fournisseur de gestion des périphériques mobiles (MDM) pour appliquer une stratégie qui nécessite le chiffrement de l’appareil. La stratégie à utiliser est le [paramètre Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) dans le programme CSP Policy.

[Consultez les instructions pour activer le chiffrement de l’appareil à l’aide de Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Pour d’autres outils de GPM, consultez la documentation de votre fournisseur GPM pour obtenir des instructions. Si votre fournisseur de gestion des périphériques de gestion des périphériques nécessite un URI personnalisé pour le chiffrement de l’appareil, utilisez la configuration suivante :

- **Nom**: un nom de votre choix
- **Description**: facultatif
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Type de données**: entier
- **Valeur**: `1`

## Activer le chiffrement de l’appareil à l’aide d’un package de configuration

Les packages de configuration sont des fichiers créés par l’outil Concepteur de configuration Windows qui appliquent une configuration spécifiée à un appareil. 

### Créer un package d’approvisionnement qui permet de mettre à niveau l’édition Windows Holographique et d’activer le chiffrement

1. [Créez un package de configuration pour HoloLens.](hololens-provisioning.md)
1. Accédez à **Paramètres d'exécution** > **Stratégies** > **Sécurité**, puis sélectionnez **RequireDeviceEncryption**.

    ![Exiger que le paramètre de chiffrement d’appareil soit configuré sur oui](images/device-encryption.png)

1. Recherchez le fichier de licence XML fourni lors de l’achat de commercial Suite.

1. Recherchez et sélectionnez le fichier de licence XML qui a été fourni lorsque vous avez acheté la Commercial Suite.
    > [!NOTE]
    > Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).

1. Dans le menu **Fichier**, cliquez sur **Enregistrer**. 

1. Lisez l’avertissement expliquant que les fichiers de projet peuvent contenir des informations sensibles et cliquez sur **OK.**

    > [!IMPORTANT]
    > Lorsque vous créez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers de projet et le fichier de package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers de projet lorsque cela n’est plus nécessaire.

1. Dans le menu **Exporter**, cliquez sur **Package d’approvisionnement**.
1. Remplacez **Propriétaire** par **Administrateur informatique**, ce qui indique que la priorité de ce package d’approvisionnement est supérieure à celle des packages d’approvisionnement appliqués à cet appareil provenant d’autres sources, puis sélectionnez **Suivant**.
1. Définissez une valeur pour **Package Version**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

1. Sur **Sélectionner les données de sécurité du package de mise en service**, cliquez sur **Suivant**.
1. Cliquez sur **Suivant** pour spécifier l’emplacement de sortie où vous souhaitez diriger le package d’approvisionnement une fois ce dernier généré. Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.

    Le cas échéant, cliquez sur Parcourir pour modifier l’emplacement de sortie par défaut.

1. Cliquez sur **Suivant**.
1. Cliquez sur **Build** pour commencer à générer le package. Les informations du projet s'affichent sur la page de génération, et la barre de progression indique l'état de la génération.
1. Lorsque la génération est achevée, cliquez sur **Terminer**.

### Appliquer le package d’approvisionnement à HoloLens

1. Connectez l’appareil à un PC via USB et démarrez l’appareil, mais ne dépassez pas la page **ajuster** de l'expérience de configuration initiale (la première page affichant le rectangle bleu).
1. Appuyez brièvement sur les boutons **Baisser le volume** et **Marche/Arrêt** en même temps, puis relâchez-les.
1. HoloLens s’affiche comme périphérique dans l’Explorateur de fichiers du PC.
1. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.
1. Appuyez à nouveau brièvement sur les boutons **Baisser le Volume** et **Alimentation** simultanément, puis relâchez-les, lorsque vous êtes sur la page **Ajuster**.
1. L’appareil vous demandera si vous faites confiance au package et si vous souhaitez l’appliquer. Confirmez que vous faites confiance au package.
1. Vous verrez si le package a été appliqué avec succès ou non. En cas d’échec, vous pouvez corriger votre package et essayer à nouveau. Si l'opération a réussi, passez à la configuration de l'appareil.

> [!NOTE]
> Si l’appareil a été acheté avant août2016, vous devrez vous y connecter avec un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser celui-ci pour pouvoir appliquer le package de configuration.

## Vérifier le chiffrement de l’appareil

Le chiffrement est en mode silencieux sur HoloLens. Pour vérifier l’état de chiffrement de l'appareil:

- Sur HoloLens, accédez à **Paramètres** > **Système** > **À propos de**. **BitLocker est** **activé si** l’appareil est chiffré. 

    ![À propos de l’écran montrant BitLocker activé](images/about-encryption.png)
