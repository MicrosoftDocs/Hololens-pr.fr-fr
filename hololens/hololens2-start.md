---
title: Configurer votre HoloLens2
description: Découvrez comment configurer votre réseau HoloLens 2 pour la première fois sur Wi-Fi avec un compte Microsoft (MSA) ou Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 9824de1d81fd6ba9ccafc8627d660aebefeaed15
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283875"
---
# Configurer votre HoloLens2

Lorsque vous allumerez votre HoloLens pour la première fois, vous serez guidé pour la configuration de votre appareil, la connexion avec un compte d’utilisateur et l’étalonnage de HoloLens pour vos yeux.  Cette section décrit la configuration initiale de HoloLens2.

Dans la section suivante, vous découvrirez comment utiliser HoloLens et interagir avec des hologrammes. Pour passer directement à cet article, voir [Prendre en main HoloLens2](hololens2-basic-usage.md).

## Avant de commencer

Avant de commencer, assurez-vous de disposer des éléments suivants:

**Une connexion réseau**. Vous devez connecter votre HoloLens à un réseau pour le configurer. Avec HoloLens 2, vous pouvez vous connecter à un réseau Wi-Fi ou utiliser Ethernet (vous avez besoin d’un adaptateur USB-C-to-Ethernet). La première fois que vous le connectez, vous avez besoin d’un réseau ouvert ou protégé par mot de passe qui ne nécessite pas l’accès à un site Web ou l’utilisation de certificats pour se connecter. [En savoir plus sur les sites Web utilisés par HoloLens](hololens-offline.md).

**Un compte Microsoft**. Vous devez également vous connecter à HoloLens avec un compte Microsoft (ou avec votre compte professionnel, si votre organisation possède l’appareil). Si vous ne possédez pas encore de compte Microsoft, accédez à [account.microsoft.com](https://account.microsoft.com) et configurez-en un gratuitement.

**Un espace sécurisé et bien éclairé sans risques de trébucher**. [Informations relatives à la santé et à la sécurité](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Les accessoires de confort facultatifs** fournis avec votre HoloLens, pour vous aider à obtenir l’ajustement le plus confortable. [Plus d’informations sur l’ajustement et le confort](hololens2-setup.md#adjust-fit).

## Configurer Windows

La première fois que vous démarrez votre HoloLens 2, votre première tâche consiste à configurer Windows Holographique.  Lorsque vous démarrez votre HoloLens, vous entendez de la musique et le logo Windows est affiché.

![Premier écran au cours du premier démarrage](images/01-magic-moment.png)

HoloLens 2 vous guide au cours des étapes suivantes:

1. Sélectionnez votre langue.
    ![Sélectionner la langue](images/04-language.png)

1. Sélectionnez votre région.
    ![Sélectionner une région](images/05-region.png)

1. Étalonnez HoloLens pour vos yeux.  Si vous choisissez d’ignorer l’étalonnage, vous serez invité à l’effectuer lors de votre prochaine connexion.

    Pour étalonner, vous examinez un ensemble de cibles (appelées «gemme»). Vous pouvez cligner des yeux ou les fermer lors de l’étalonnage, mais vous ne pouvez pas regarder d’autres objets dans la pièce ou dans l’espace physique. HoloLens utilise ce processus pour détecter la position de vos yeux et ainsi améliorer le rendu de votre univers holographique. Après l’étalonnage, les hologrammes s’affichent correctement même lorsque la visière se déplace sur votre tête.

    Les informations d’étalonnage sont stockées localement sur l’appareil et ne sont associées à aucune information de compte. Pour plus d’informations, voir [Données d’étalonnage et sécurité](hololens-calibration.md#calibration-data-and-security).

    ![Écran de sélection de l’étalonnage](images/06-et-corners.png)

1. Connectez-vous à Internet (sélectionnez Wi-Fi ou votre connexion Ethernet).
     HoloLens définit votre fuseau horaire automatiquement en fonction des informations obtenues du réseau Wi-Fi. Une fois l’installation terminée, vous pouvez modifier le fuseau horaire à l’aide de l’application Paramètres.

    ![Se connecter au Wi-Fi](images/11-network.png)
> [!NOTE] 
> Si vous progressez au-delà de l’étape Wi-Fi et que vous devez ensuite basculer vers un autre réseau durant la configuration, vous pouvez appuyer sur les boutons de **réduction du volume** et **Démarrer** simultanément pour revenir à cette étape si vous exécutez une version du système d’exploitation datant d'octobre 2019 ou ultérieure. Pour les versions antérieures, vous devrez peut-être [réinitialiser l'appareil](hololens-recovery.md) ou le redémarrer dans un emplacement où le réseau Wi-Fi n’est pas disponible afin d'empêcher une connexion automatique.
> 
> Notez également que lors de l’installation de HoloLens, le délai d’expiration des informations d’identification est de deux minutes. Le nom d’utilisateur/mot de passe doit être entré dans les deux minutes, sans quoi le champ du nom d’utilisateur sera automatiquement effacé.

1. Connectez-vous à votre compte d’utilisateur. Vous avez le choix entre **Il appartient à mon entreprise ou à mon établissement** et **Il m’appartient**.
    - Si vous choisissez **Il appartient à mon entreprise ou à mon établissement**, vous vous connectez avec un compte Azure AD. Si votre organisation utilise Azure AD Premium et qu’elle a configuré l’inscription GPM automatique, HoloLens s’inscrit automatiquement dans GPM. Si votre organisation n’utilise pas Azure AD Premium, l’inscription GPM automatique n’est pas disponible. Dans ce cas, vous devez [inscrire HoloLens manuellement dans la gestion des périphériques](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Entrez les informations de votre compte professionnel.
        1. Acceptez la déclaration de confidentialité et le contrat de licence utilisateur final.
        1. Connectez-vous à l’aide de vos informations d’identification Azure AD. Cela pourra vous rediriger vers la page de connexion de votre entreprise.
        1. Poursuivez la configuration de l’appareil.
    - Lorsque vous choisissez **Il m’appartient**, vous vous connectez avec un compte Microsoft. Une fois l’installation terminée, vous pouvez [inscrire HoloLens manuellement dans la gestion des périphériques](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Entrez les informations de votre compte Microsoft.
        2. Saisissez votre mot de passe. Si votre compte Microsoft nécessite une [vérification en deux étapes (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), achevez le processus de vérification.

    ![Définir l’utilisateur](images/13-device-owner.png)

1. Indiquez si vous souhaitez activer la reconnaissance vocale sur HoloLens 2, et si vous souhaitez envoyer la télémétrie de diagnostic.
    ![Activer Cortana](images/22-do-more-with-voice.png)

1. Sélectionnez votre niveau de télémétrie. Si vous le pouvez, activez la télémétrie complète. Ces informations aideront réellement l’équipe d’ingénierie HoloLens.
     ![Niveau de télémétrie](images/24-telemetry.png)

1. Découvrez comment utiliser le mouvement associé au menu Démarrer sur HoloLens 2.
     ![Découvrez comment utiliser le mouvement associé au menu Démarrer, image1](images/26-01-startmenu-learning.png) ![Apprenez à utiliser le mouvement associé au menu Démarrer, image2](images/26-02-startmenu-learning.png)

Félicitations!  La configuration est terminée et vous êtes prêt à utiliser HoloLens.

## Étapes suivantes

> [!div class="nextstepaction"]
> [Prendre en main HoloLens2](hololens2-basic-usage.md)
