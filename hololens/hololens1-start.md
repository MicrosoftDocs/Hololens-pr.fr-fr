---
title: Installer HoloLens (1re génération)
description: Ce guide décrit la configuration initiale.  Vous avez besoin d’un réseau Wi-Fi et d’un compte Microsoft (MSA) ou Azure Active Directory (Azure AD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 042856de2b89395fa0168d90515a7700298087f1
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828507"
---
# Installer votre HoloLens (1re génération)

Lorsque vous allumez votre HoloLens pour la première fois, vous serez guidé lors de l’étalonnage de votre appareil, sa configuration et la connexion.  Cet article décrit le premier démarrage de HoloLens (1re génération) et la configuration.

Dans la section suivante, vous découvrirez comment utiliser HoloLens et interagir avec des hologrammes. Pour passer directement à cet article, consultez [Prendre en main HoloLens (1re génération)](hololens1-basic-usage.md).

## Avant de commencer

Avant de commencer, assurez-vous de disposer des éléments suivants:

**Une connexion Wi-Fi**. Vous devez connecter votre HoloLens à un réseau Wi-Fi pour le configurer. La première fois que vous le connectez, vous avez besoin d’un réseau ouvert ou protégé par mot de passe qui ne nécessite pas l’accès à un site Web ou l’utilisation de certificats pour se connecter. [En savoir plus sur les sites Web utilisés par HoloLens](hololens-offline.md).

**Un compte Microsoft ou un compte professionnel**. Vous devez également utiliser un compte Microsoft (ou un compte professionnel, si votre organisation est propriétaire de l’appareil) pour vous connecter à HoloLens. Si vous ne possédez pas encore de compte Microsoft, accédez à [account.microsoft.com](https://account.microsoft.com) et configurez-en un gratuitement.

**Un espace sécurisé et bien éclairé sans risques de trébucher**. [Informations relatives à la santé et à la sécurité](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Les accessoires de confort facultatifs** fournis avec votre HoloLens, pour vous aider à obtenir l’ajustement le plus confortable. [Plus d’informations sur l’ajustement et le confort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - La première fois que vous utilisez votre HoloLens, [Cortana](hololens-cortana.md) est déjà en cours d’exécution et prêt à vous guider (même si elle ne peut pas répondre à vos questions tant que vous n’avez pas configuré votre appareil). Vous pouvez désactiver Cortana à tout moment dans les paramètres de Cortana.
> - Pour basculer vers la version chinois ou japonais de HoloLens, vous devez télécharger la version correspondant à la langue sur un PC, puis l’installer sur votre HoloLens. Pour plus d’informations, consultez [Installer des versions localisées de HoloLens (1regénération)](hololens1-install-localized.md).

## Démarrer votre HoloLens et configurer Windows

Lorsque vous démarrez votre HoloLens pour la première fois, la première chose à faire est configurer Windows Holographique sur votre appareil.

1. Connectez-vous à Internet (HoloLens vous guide pour sélectionner le réseau Wi-Fi).

1. Connectez-vous à votre compte d’utilisateur. Choisissez **Il appartient à mon entreprise ou à mon établissement** ou **Il m’appartient**.
    - Si vous sélectionnez **Il appartient à mon entreprise ou à mon établissement**, vous vous connectez avec un compte AzureAD. Si votre organisation utilise Azure AD Premium et qu’elle a configuré l’inscription GPM automatique, HoloLens s’inscrit automatiquement dans GPM. Si votre organisation n’utilise pas Azure AD Premium, l’inscription GPM automatique n’est pas disponible, vous devrez donc procéder [manuellement à l’inscription HoloLens dans gestion des périphériques](hololens-enroll-mdm.md#enroll-through-settings-app). Pour vous connecter à votre appareil pour la première fois à l’aide d’un compte professionnel ou scolaire, procédez comme suit:
        1. Entrez les informations de votre compte professionnel.
        1. Acceptez la déclaration sur le respect de la vie privée.
        1. Connectez-vous à l’aide de vos informations d’identification Azure AD. Cela pourra vous rediriger vers la page de connexion de votre entreprise.
        1. Poursuivez la configuration de l’appareil.
    - Si vous choisissez **Il m’appartient**, vous vous connectez avec un compte Microsoft. Une fois l’installation terminée, vous pouvez [inscrire HoloLens manuellement dans la gestion des périphériques](hololens-enroll-mdm.md#enroll-through-settings-app).
        1. Entrez les informations de votre compte Microsoft.
        1. Saisissez votre mot de passe. Si votre compte Microsoft nécessite une [vérification en deux étapes (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), achevez le processus de vérification.

1. L’appareil définit votre fuseau horaire en fonction des informations obtenues par le réseau Wi-Fi.

## Étalonnage

Dès que Cortana se présente, l’étape de configuration suivante est l’étalonnage. Pour optimiser l’utilisation de HoloLens, vous devez terminer le processus d’étalonnage lors de l’installation.

HoloLens (1re génération) utilise l’écart entre vos pupilles (IPD ou [écart pupillaire](https://en.wikipedia.org/wiki/Interpupillary_distance)) pour rendre les hologrammes clairs et faciliter l’interaction avec eux. Si l’écart pupillaire n’est pas correct, les hologrammes peuvent sembler instables ou se trouver à une distance incorrecte.

Lors de l’étalonnage, HoloLens vous demande d’aligner votre doigt sur une série de six cibles par œil. HoloLens utilise ce processus pour définir l’écart pupillaire adapté à vos yeux. Si l’étalonnage doit être mis à jour ou ajusté pour un nouvel utilisateur, le nouvel utilisateur peut exécuter l’application Étalonnage en dehors du programme d’installation.

![Écran d’alignement IPD d’un doigt lors de la deuxième étape](./images/ipd-finger-alignment-300px.jpg)

*Écran d’alignement IPD d’un doigt lors de la deuxième étape*

Félicitations! La configuration est terminée, et vous pouvez commencer à utiliser HoloLens.

## Étapes suivantes

> [!div class="nextstepaction"]
> [Prise en main de HoloLens (1regénération)](hololens1-basic-usage.md)
