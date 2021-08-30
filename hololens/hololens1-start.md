---
title: configurer HoloLens (1re génération)
description: découvrez comment configurer votre HoloLens (1er génération) pour la première fois sur Wi-Fi réseau à l’aide d’un compte Microsoft (MSA) ou Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189866"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configurer votre HoloLens (1re génération)

la première fois que vous allumez votre HoloLens, vous serez guidé lors de l’étalonnage de votre appareil, de la configuration de votre appareil et de la connexion.  cet article vous guide tout au long du processus de démarrage et d’installation de HoloLens (1ère génération).

Dans la section suivante, vous découvrirez comment utiliser HoloLens et interagir avec des hologrammes. pour aller plus loin dans cet article, consultez [prise en main de HoloLens (1ère génération)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Avant de commencer

Avant de commencer, assurez-vous de disposer des éléments suivants :

**Connexion Wi-Fi**. vous devez connecter votre HoloLens à un réseau Wi-Fi pour le configurer. La première fois que vous le connectez, vous avez besoin d’un réseau ouvert ou protégé par mot de passe qui ne nécessite pas d’accès à un site web ou l’utilisation de certificats pour se connecter. [Apprenez-en davantage sur les sites web utilisés par HoloLens](hololens-offline.md).

**Un compte Microsoft ou un compte professionnel**. Vous devez également utiliser une compte Microsoft (ou un compte professionnel, si votre organisation est propriétaire de l’appareil) pour vous connecter à HoloLens. Si vous n’avez pas de compte Microsoft, accédez à [account.microsoft.com](https://account.microsoft.com) et configurez-en un gratuitement.

**Un espace sûr et bien éclairé, sans danger**. [Informations sur l’intégrité et la sécurité](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Les accessoires de confort facultatifs** fournis avec votre HoloLens, pour vous aider à obtenir l’ajustement le plus confortable. [Apprenez-en davantage sur l’ajustement et le confort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - la première fois que vous utilisez votre HoloLens, [Cortana](hololens-cortana.md) est déjà activée et prête à vous guider (bien qu’elle ne puisse pas répondre à vos questions tant que vous n’avez pas configuré votre appareil). vous pouvez désactiver l’Cortana à tout moment dans les paramètres de Cortana.
> - pour passer à la version chinoise ou japonaise de HoloLens, vous devez télécharger la version de la langue sur un PC, puis l’installer sur votre HoloLens. pour plus d’informations, consultez [installer des versions localisées de HoloLens (1re génération)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Démarrez votre Hololens et configurez Windows

la première fois que vous démarrez votre HoloLens, votre première tâche consiste à configurer Windows holographique sur votre appareil.

1. Connecter à internet (HoloLens vous guide pour sélectionner Wi-Fi réseau).

1. Connectez-vous à votre compte d’utilisateur. Choisissez entre **mon entreprise ou votre école la propriétaire** et **moi-même**.
    - Quand vous choisissez **mon entreprise ou école**, vous vous connectez à l’aide d’un compte Azure ad. Si votre organisation utilise Azure AD Premium et qu’elle a configuré l’inscription GPM automatique, HoloLens s’inscrit automatiquement dans GPM. si votre organisation n’utilise pas de Azure AD Premium, l’inscription automatique à MDM n’est pas disponible. vous devrez donc [inscrire manuellement HoloLens dans la gestion des appareils](hololens-enroll-mdm.md#different-ways-to-enroll). Pour vous connecter à votre appareil la première fois à l’aide d’un compte professionnel ou scolaire, procédez comme suit :
        1. Entrez les informations de votre compte professionnel.
        1. Acceptez la déclaration de confidentialité.
        1. Connectez-vous à l’aide de vos informations d’identification Azure AD. Cela pourra vous rediriger vers la page de connexion de votre entreprise.
        1. Poursuivez la configuration de l’appareil.
    - Lorsque vous choisissez **le propriétaire**, vous vous connectez à l’aide d’un compte Microsoft. Une fois l’installation terminée, vous pouvez [inscrire manuellement HoloLens dans la gestion des périphériques](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Entrez les informations de votre compte Microsoft.
        1. Saisissez votre mot de passe. Si votre compte Microsoft nécessite une [vérification en deux étapes (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), achevez le processus de vérification.

1. L’appareil définit votre fuseau horaire en fonction des informations qu’il obtient du réseau Wi-Fi.

## <a name="calibration"></a>Étalonnage

une fois que Cortana s’est introduit, la prochaine étape d’installation est l’étalonnage. pour une expérience de HoloLens optimale, vous devez terminer le processus d’étalonnage lors de l’installation.

HoloLens (1re génération) utilise la distance entre vos élèves (la distance IPD ou [interpupillary](https://en.wikipedia.org/wiki/Interpupillary_distance)) pour rendre les hologrammes clairs et faciles d’interaction avec. Si la IPD n’est pas correcte, les hologrammes peuvent sembler instables ou à une distance incorrecte.

pendant l’étalonnage, HoloLens vous demande d’aligner votre doigt sur une série de six cibles par œil. HoloLens utilise ce processus pour définir la bonne IPD pour vos yeux. Si l’étalonnage doit être mis à jour ou ajusté pour un nouvel utilisateur, le nouvel utilisateur peut exécuter l’application d’étalonnage en dehors du programme d’installation.

![Écran d’alignement de doigt IPD à la deuxième étape.](./images/ipd-finger-alignment-300px.jpg)

*Écran d'alignement du doigt pour définir l'écart pupillaire lors de la deuxième étape*

Félicitations ! L’installation est terminée et vous pouvez commencer à utiliser HoloLens.

## <a name="next-steps"></a>Étapes suivantes

> [!div class="nextstepaction"]
> [Bien démarrer avec HoloLens (1re génération)](hololens1-basic-usage.md)
