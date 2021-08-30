---
title: HoloLens Chiffrement BitLocker
description: découvrez comment activer le chiffrement de périphérique BitLocker pour protéger des fichiers stockés sur votre HoloLens des appareils de réalité mixte.
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
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: d5cf7385dd0a53c6b17f79e16364e84ab6ec867d
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189934"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>Chiffrement BitLocker HoloLens (1re génération)

HoloLens (1re génération) et HoloLens 2 prennent en charge le chiffrement des appareils à l’aide de bitlocker. toutefois, bitlocker est toujours activé sur HoloLens 2.

cet article vous aidera à activer et à gérer BitLocker sur HoloLens (1ère génération).

sur HoloLens (1re génération), vous pouvez activer le chiffrement de l’appareil BitLocker manuellement ou à l’aide de la gestion des appareils mobiles (MDM). Suivez ces instructions pour activer le [chiffrement d’appareil BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) afin de protéger les fichiers et les informations stockés sur le HoloLens. Le chiffrement de l’appareil vous aide à protéger vos données à l’aide de la méthode de chiffrement AES-CBC 128, qui est équivalente à la [méthode EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) dans le fournisseur de services de configuration (CSP) BitLocker. Le personnel qui a la clé de chiffrement correcte (par exemple, un mot de passe) peut le déchiffrer ou effectuer une récupération de données.

## <a name="enable-device-encryption-using-mdm"></a>Activer le chiffrement de l’appareil à l’aide de MDM

Vous pouvez utiliser votre fournisseur de gestion des appareils mobiles (MDM) pour appliquer une stratégie qui requiert le chiffrement de l’appareil. La stratégie à utiliser est le [paramètre Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) dans le fournisseur de services de chiffrement de stratégie.

[Consultez les instructions pour activer le chiffrement de l’appareil à l’aide de Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Pour d’autres outils MDM, consultez la documentation de votre fournisseur MDM pour obtenir des instructions. Si votre fournisseur MDM requiert un URI personnalisé pour le chiffrement de l’appareil, utilisez la configuration suivante :

- **Nom**: nom de votre choix
- **Description**: facultatif
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Type de données**: entier
- **Valeur** : `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Activer le chiffrement de l’appareil à l’aide d’un package d’approvisionnement

les packages de provisionnement sont des fichiers créés par l’outil concepteur de configuration Windows qui appliquent une Configuration spécifiée à un appareil. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>créer un package de mise en service qui met à niveau le Windows édition holographique et active le chiffrement

1. [Créez un package d’approvisionnement pour HoloLens.](hololens-provisioning.md)
1. Accédez à **paramètres d’exécution**  >  **stratégies**  >  **sécurité**, puis sélectionnez **RequireDeviceEncryption**.

    ![Exiger le paramètre de chiffrement de l’appareil configuré sur Oui.](images/device-encryption.png)

1. Recherchez le fichier de licence XML fourni lorsque vous avez acheté la suite commerciale.

1. Recherchez et sélectionnez le fichier de licence XML qui a été fourni lorsque vous avez acheté la Commercial Suite.
    > [!NOTE]
    > Vous pouvez configurer [des paramètres supplémentaires dans le package d’approvisionnement](hololens-provisioning.md).

1. Dans le menu **File** (Fichier), cliquez sur **Save** (Enregistrer). 

1. Lisez l’avertissement expliquant que les fichiers projet peuvent contenir des informations sensibles, puis cliquez sur **OK**.

    > [!IMPORTANT]
    > Quand vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et le fichier de package de configuration (. ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers projet dans un emplacement sécurisé et supprimer les fichiers projet quand vous n’en avez plus besoin.

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

### <a name="apply-the-provisioning-package-to-hololens"></a>Appliquer le package d’approvisionnement à HoloLens

1. Connecter l’appareil USB à un PC et démarrer l’appareil, mais ne continuez pas **la page de l’installation** initiale (la première page avec la boîte bleue).
1. Appuyez brièvement sur les boutons **Baisser le volume** et **Alimentation** en même temps, puis relâchez-les.
1. HoloLens s’affiche comme périphérique dans l’Explorateur de fichiers du PC.
1. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.
1. Appuyez à nouveau brièvement sur les boutons **Baisser le Volume** et **Alimentation** simultanément, puis relâchez-les, lorsque vous êtes sur la page **Ajuster**.
1. L’appareil vous demandera si vous faites confiance au package et si vous souhaitez l’appliquer. Confirmez que vous faites confiance au package.
1. Vous verrez si le package a été appliqué avec succès ou non. En cas d’échec, vous pouvez corriger votre package et essayer à nouveau. Si elle a réussi, effectuez la configuration de l’appareil.

> [!NOTE]
> Si l’appareil a été acheté avant le 2016 août, vous devez vous connecter à l’appareil avec un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser le système d’exploitation afin d’appliquer le package d’approvisionnement.

## <a name="verify-device-encryption"></a>Vérifier le chiffrement de l’appareil

Le chiffrement est en mode silencieux sur HoloLens. Pour vérifier l’état du chiffrement de l’appareil :

- sur HoloLens, accédez à **Paramètres**  >  **système**  >  **à propos** de. **BitLocker** est **activé** si l’appareil est chiffré. 

    ![À propos de l’écran indiquant que BitLocker est activé.](images/about-encryption.png)
