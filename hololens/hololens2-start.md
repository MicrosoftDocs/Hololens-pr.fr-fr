---
title: Configurer votre HoloLens 2
description: Découvrez comment configurer votre réseau HoloLens 2 pour la première fois sur Wi-Fi avec un compte Microsoft (MSA) ou Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923715"
---
# <a name="set-up-your-hololens-2"></a>Configurer votre HoloLens 2

Lorsque vous allumez votre HoloLens pour la première fois, vous êtes guidé pour la configuration de votre appareil, la connexion avec un compte d’utilisateur et l’étalonnage de HoloLens pour vos yeux.  Cette section décrit la configuration initiale de l’appareil HoloLens 2.

Dans la section suivante, vous découvrirez comment utiliser HoloLens et interagir avec des hologrammes. Pour passer directement à cet article, consultez [Explorer HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Avant de commencer

Avant de commencer, assurez-vous de disposer des éléments suivants :

**Une connexion réseau**. Vous devez connecter votre HoloLens à un réseau pour le configurer. Avec HoloLens 2, vous pouvez vous connecter à un réseau Wi-Fi ou utiliser Ethernet (moyennant un adaptateur USB-C vers Ethernet). La première fois que vous le connectez, vous avez besoin d’un réseau ouvert ou protégé par mot de passe qui ne nécessite pas d’accès à un site web ou l’utilisation de certificats pour se connecter. [Apprenez-en davantage sur les sites web utilisés par HoloLens](hololens-offline.md).

**Un compte Microsoft**. Vous devez également vous connecter à HoloLens avec un compte Microsoft (ou avec votre compte professionnel, si l’appareil appartient à votre organisation). Si vous n’avez pas de compte Microsoft, accédez à [account.microsoft.com](https://account.microsoft.com) et configurez-en un gratuitement.

**Un espace sûr et bien éclairé, sans danger**. [Informations sur l’intégrité et la sécurité](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Les accessoires de confort facultatifs** fournis avec votre HoloLens, pour vous aider à obtenir l’ajustement le plus confortable. [Apprenez-en davantage sur l’ajustement et le confort](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Configuration de Windows

Lorsque vous démarrez votre HoloLens 2 pour la première fois, vous devez d’abord configurer Windows Holographic.  Au démarrage de votre HoloLens, vous entendez de la musique et le logo Windows s’affiche.

![Premier écran au cours du premier démarrage](images/01-magic-moment.png)

HoloLens 2 vous guide au cours des étapes suivantes :

1. Sélectionnez votre langue.

    ![Sélectionnez une langue](images/04-language.png)

1. Sélectionnez votre région.

    ![Sélectionner la région](images/05-region.png)

1. Étalonnez HoloLens pour vos yeux.  Si vous choisissez d’ignorer l’étalonnage, vous serez invité à l’effectuer lors de votre prochaine connexion. 

    1. Tout d’abord, vous allez ajuster votre visière.
    
        ![Écran de sélection de l’étalonnage](images/06-et-corners.png)

    2. Pour cet étalonnage, vous examinez un ensemble de cibles (appelées « gemmes »). Vous pouvez cligner des yeux ou les fermer lors de l’étalonnage, mais vous ne pouvez pas regarder d’autres objets de la pièce ou de l’espace physique. HoloLens utilise ce processus pour détecter la position de vos yeux et améliorer ainsi le rendu de votre univers holographique. 

        ![Ajuster à votre vue](images/07-adjust-eyes.png)

        Après l'étalonnage, les hologrammes s'affichent correctement, même si la visière bouge sur votre tête. Les informations d’étalonnage sont stockées localement sur l’appareil et ne sont associées à aucune information de compte. Pour plus d’informations, consultez [Données d’étalonnage et sécurité](hololens-calibration.md#calibration-data-and-security).

        ![L’étalonnage est terminé](images/calibration-complete.png)

1. Connectez-vous à Internet (sélectionnez Wi-Fi ou votre connexion Ethernet).

     HoloLens définit automatiquement votre fuseau horaire en fonction des informations obtenues du réseau Wi-Fi. Une fois l’installation terminée, vous pouvez modifier le fuseau horaire à l’aide de l’application Paramètres.

    ![Se connecter au Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Si vous avez terminé l’étape relative au Wi-Fi et devez ensuite basculer vers un autre réseau durant la configuration, vous pouvez appuyer simultanément sur les boutons de **Baisser le volume** and **Alimentation** pour revenir à cette étape si vous exécutez une version du système d’exploitation datant d'octobre 2019 ou ultérieure. Pour les versions antérieures, vous devrez peut-être [réinitialiser l’appareil](hololens-recovery.md) ou le redémarrer à un endroit où le réseau Wi-Fi n’est pas disponible afin d'empêcher une connexion automatique.
    > 
    > Notez également que lors de l’installation d’HoloLens, le délai d’expiration des informations d’identification est de deux minutes. Le nom d’utilisateur/mot de passe doit être entré dans les deux minutes, à défaut de quoi le champ du nom d’utilisateur sera automatiquement effacé.

1. HoloLens 2 recherchera et appliquera un profil Autopilot, le cas échéant. Aucune action n’est requise sur cet écran.
 
    ![Recherche de profil Autopilot](images/autopilot-profile-search.png) 

1. Dans l’écran de licence, cliquez sur **Accepter** .

    ![Contrat de licence Windows](images/windows-license-agreement.png)

1. Connectez-vous à votre compte d’utilisateur. Choisissez **Il appartient à mon entreprise** ou **Il m’appartient**.

    - Si vous choisissez **Il appartient à mon entreprise ou à mon établissement**, vous vous connectez avec un compte Azure AD. Si votre organisation utilise Azure AD Premium et qu’elle a configuré l’inscription GPM automatique, HoloLens s’inscrit automatiquement dans GPM. Si votre organisation n’utilise pas Azure AD Premium, l’inscription GPM automatique n’est pas disponible. Dans ce cas, vous devez [inscrire manuellement HoloLens dans la gestion des appareils](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Entrez les informations de votre compte professionnel.
        1. Acceptez la déclaration de confidentialité et le contrat de licence utilisateur final.
        1. Connectez-vous à l’aide de vos informations d’identification Azure AD. Cela pourra vous rediriger vers la page de connexion de votre entreprise.
        1. Poursuivez la configuration de l’appareil.

    - Lorsque vous choisissez **Il m'appartient**, vous vous connectez avec un compte Microsoft. Une fois l’installation terminée, vous pouvez [inscrire manuellement HoloLens dans la gestion des périphériques](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Entrez les informations de votre compte Microsoft.
        2. Saisissez votre mot de passe. Si votre compte Microsoft nécessite une [vérification en deux étapes (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), achevez le processus de vérification.

    ![Définir l’utilisateur](images/13-device-owner.png)

1. Configurez la connexion par reconnaissance de l’iris en sélectionnant **Suivant**. Vous accéderez à une expérience similaire à l’étalonnage oculaire. Sélectionnez **Terminé** une fois l’analyse terminée. Vous pouvez également sélectionner **Ignorer** pour ignorer cette étape.
    
    ![Configuration de l’iris](images/setup-iris.png) ![Fin de la configuration de l’iris](images/iris-setup-complete.png) 
     
  
1. Vous allez configurer un code PIN pour vous connecter à l’appareil. Ce code PIN est spécifique à l’appareil. 

    ![Configurer Windows Hello](images/setup-windows-hello.png)

    ![Configurer le code PIN Windows Hello](images/windows-hello-pin.png)

    ![Configuration de Windows Hello réussie](images/windows-hello-successful.png) 
    
1. Indiquez si vous souhaitez activer la reconnaissance vocale sur HoloLens 2.

    ![Activer Cortana](images/22-do-more-with-voice.png)

1. Indiquez si vous souhaitez activer la localisation sur HoloLens 2.
    
    ![Activer les services de localisation](images/setup-location-services.png)

1. Sélectionnez votre niveau de télémétrie. Si possible, activez la télémétrie facultative. Ces informations seront d’une grande aide pour l’équipe d’ingénierie HoloLens.

     ![Niveau de télémétrie](images/24-telemetry.png)

1. Découvrez comment utiliser le mouvement associé au menu Démarrer sur HoloLens 2.

     ![Découvrez comment utiliser le mouvement associé au menu Démarrer, image 1](images/26-01-startmenu-learning.png)

     ![Découvrez comment utiliser le mouvement associé au menu Démarrer, image 2](images/26-02-startmenu-learning.png)

Félicitations !  La configuration est terminée et vous êtes prêt à utiliser HoloLens.

## <a name="next-steps"></a>Étapes suivantes

1. Commencez sans plus attendre à interagir avec la réalité mixte et à naviguer dans Windows 10 sur votre HoloLens : consultez l'application **Astuces** pour accéder à des tutoriels pratiques sur les interactions avec la main. Utilisez le mouvement associé au menu Démarrer ou dites « Menu Démarrer », puis sélectionnez Astuces.

1. Cliquez sur les liens ci-dessous pour en savoir plus sur l'HoloLens 2.

> [!div class="nextstepaction"]
> [Explorer HoloLens 2](hololens2-basic-usage.md)
