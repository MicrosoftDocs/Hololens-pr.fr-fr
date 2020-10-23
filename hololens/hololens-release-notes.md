---
title: Notes de publication HoloLens 2
description: En savoir plus sur les mises à jour de chaque nouvelle version de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 85bba3c955c26bcfdb7e80a24be0befa1e06289e
ms.sourcegitcommit: 8fb914cf6512c67444e0ead2050cf1c82bd5decc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134423"
---
# Notes de publication HoloLens 2

Pour vous assurer que vous disposez d’une satisfaction productive sur vos appareils HoloLens, nous continuons à libérer les mises à jour de fonctionnalités, de bogues et de sécurité. Sur cette page, vous pouvez voir les nouveautés du HoloLens par mois. Pour obtenir la dernière mise à jour du flash HoloLens 2 (FFU [), vous pouvez la](hololens-recovery.md#clean-reflash-the-device) [Télécharger ici](https://aka.ms/hololens2download). Le téléchargement est mis à jour et fournit la version la plus récente disponible en général.

>[!NOTE]
> Pour lire les notes de publication de HoloLens Emulator, [consultez l’archive](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holographique, version 2004-mise à jour d’octobre 2020
- Version 19041,1124
 
Améliorations et correctifs de la mise à jour:

- Suppression d’une vérification inutile qui entraînait une erreur du système d’exécution.

## Windows holographique, version 1903-mise à jour d’octobre 2020
- Version 18362,1081

Cette mise à jour de qualité mensuelle ne contient pas de modifications remarquables, nous vous encourageons à essayer les dernières builds pour Windows holographique, version 2004.

## Windows holographique, version 2004-mise à jour de septembre 2020
- Version 19041,1117

Améliorations et correctifs de la mise à jour:

- Résout un problème qui empêchait Visual Studio de déboguer une application lorsque SupportsMultipleInstances = «true» est présent dans appxmanifest.
- Cette version inclut le correctif de détection de proxy NCSI permettant d’adresser une détection Internet ayant échoué sur un proxy réseau. NCSI peut utiliser proxy d’ordinateur et proxy par profil pour la détection de connectivité Internet. Le proxy par utilisateur sera pris en charge par NCSI dans la prochaine version.
- Sur la plupart des appareils Windows Mixed Reality, le vecteur de direction vers le haut est parallèle au sol lorsque la tête de l’utilisateur se trouve à la position neutre en avance. Toutefois, les versions antérieures de HoloLens 2 alignent le vecteur pour être perpendiculaire aux panneaux d’affichage à la place, qui est inclinée de quelques degrés par rapport à l’orientation idéale. Les versions plus récentes de HoloLens 2 ont corrigé le problème afin de garantir la cohérence de la sémantique entre les différents facteurs de forme.
- Amélioration de la robustesse de suivi des mains entraînant moins de pertes de suivi dans des scénarios spécifiques.
- Cette version contient un correctif permettant d’améliorer la qualité de l’estampille audio, qui pourrait avoir contribué aux problèmes de capture vidéo.

## Windows holographique, version 1903-mise à jour de septembre 2020
- Version 18362,1079

Améliorations et correctifs de la mise à jour:

- Sur la plupart des appareils Windows Mixed Reality, le vecteur de direction vers le haut est parallèle au sol lorsque la tête de l’utilisateur se trouve à la position neutre en avance. Toutefois, les versions antérieures de HoloLens 2 alignent le vecteur pour être perpendiculaire aux panneaux d’affichage à la place, qui est inclinée de quelques degrés par rapport à l’orientation idéale. Les versions plus récentes de HoloLens 2 ont corrigé le problème afin de garantir la cohérence de la sémantique entre les différents facteurs de forme.
- Amélioration de la robustesse de suivi des mains entraînant moins de pertes de suivi dans des scénarios spécifiques.

## Windows holographique, version 2004-mise à jour d’août 2020
- Version 19041,1113

Améliorations et correctifs de la mise à jour:

- L’application paramètres ne sera plus suivie de l’utilisateur dans les expériences d’étalonnage d’iris ou de suivi oculaire.
- Correction d’un bogue lors de l’application d’un package de mise en service au cours de l’utilisation de la version OOBE pour renommer l’appareil et effectuer d’autres actions (par exemple, la connexion à un réseau) n’a pas pu effectuer les autres actions après le redémarrage de l’appareil en raison d’un changement de nom.
- Le modèle de couleurs modifié des flux d’installation initial de l’appareil pour améliorer la qualité visuelle.

## Windows holographique, version 1903-mise à jour d’août 2020
- Version 18362,1074

Cette mise à jour de qualité mensuelle ne contient pas de modifications remarquables, nous vous encourageons à essayer les dernières builds pour Windows holographique, version 2004.

## Windows holographique, version 2004-mise à jour de juillet 2020
- Version 19041,1109

Améliorations et correctifs de la mise à jour:

- Les développeurs peuvent désormais choisir entre l’activation et la désactivation de Device Portal pour lesquelles Device Portal nécessite une connexion sécurisée.
- Fiabilité améliorée pour les lancements d’applications après les mises à jour du système d’exploitation.
- Modification de la luminosité par défaut de la boîte de réception à 100%.
- A résolu un problème lié au transfert de HTTPs pour Windows Device Portal sur HoloLens 2.

## Windows holographique, version 1903-mise à jour de juillet 2020
- Version 18362,1071

Améliorations et correctifs de la mise à jour:

- Correction d’un problème qui pouvait entraîner la disparition d’hologrammes dans les applications Unity lors de la perte ou de la réobtention du suivi.
- Correction d’un problème qui entraînait le blocage d’applications HoloLens exclusives sur le shell lors de l’utilisation de l’émulateur HoloLens avec l’accélération matérielle sur certains appareils.
- A résolu un problème lié au transfert de HTTPs pour Windows Device Portal sur HoloLens 2.

## Windows holographique, version 2004-mise à jour de juin 2020
- Version 19041,1106

Améliorations et correctifs de la mise à jour:

- Les enregistrements MRC personnalisés possèdent désormais de nouvelles valeurs par défaut pour certaines propriétés qui ne sont pas spécifiées.
  - Dans l' *effet vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l' *effet audio MRC*:
    - LoopbackGain (valeur «augmentation audio de l’application» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
    - MicrophoneGain (valeur «MIC audio» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
- Correction d’un bogue pour améliorer la qualité audio dans les scénarios de capture de la réalité mixte. En particulier, ce correctif doit éliminer les problèmes audio dans l’enregistrement lorsque le menu **Démarrer** s’affiche.
- Amélioration de la stabilité de l’hologramme dans les vidéos enregistrées.
- Résolution d’un problème de capture de la réalité mixte impossible d’enregistrer la vidéo une fois que l’appareil a quitté l’état d’attente pendant plusieurs jours.
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity. Ce comportement évite un problème qui entraînait le arrêt de certaines applications lorsque le Visor était retourné, même si le paramètre «exécuter en arrière-plan» a été activé. L’API est désormais activée pour les versions Unity 2018.4.18 et les versions ultérieures et 2019.3.4 et les versions ultérieures.
- Lorsque vous accédez à Device Portal sur une connexion Wi-Fi, un navigateur Web peut empêcher l’accès en raison d’un certificat non valide. Le navigateur peut signaler une erreur telle que «ERR_SSL_PROTOCOL_ERROR», même si le certificat d’appareil a été précédemment approuvé. Dans ce cas, vous ne pouvez pas progresser sur Device Portal, car il n’est pas possible d’ignorer les avertissements de sécurité. Cette mise à jour a résolu le problème. Si le certificat d’appareil a déjà été téléchargé et approuvé sur un PC pour supprimer les avertissements de sécurité du navigateur et si l’erreur SSL se produit, le nouveau certificat doit être téléchargé et approuvé pour répondre aux avertissements de sécurité du navigateur.
- A activé la possibilité de créer un package de déploiement d’exécution qui peut installer une application à l’aide de packages MSIX.
- Un paramètre a été ajouté dans les **paramètres**d'  >  **System**  >  **hologrammes** système qui permettent aux utilisateurs de supprimer automatiquement tous les hologrammes de la page d’accueil mixte lorsque l’appareil s’arrête.
- Correction d’un problème qui entraînait des applications HoloLens qui modifiaient leur format de pixel pour afficher en noir dans l’émulateur HoloLens.
- Correction d’un bogue entraînant un blocage lors de l’ouverture de session en IRIS.
- Correction d’un problème de téléchargement de magasin répété pour les applications déjà actuelles.
- Correction d’un bogue visant à empêcher les applications immersives d’ouvrir Microsoft Edge à plusieurs reprises.
- Correction d’un problème avec le lancement de l’application photos lors des démarrages initiaux après la mise à jour à partir de la version 1903.
- Amélioration des performances et de la fiabilité.

## Windows holographique, version 1903-mise à jour de juin 2020
- Version 18362,1064

Améliorations et correctifs de la mise à jour:

- Les enregistrements MRC personnalisés possèdent de nouvelles valeurs par défaut pour certaines propriétés, si elles ne sont pas spécifiées.
  - Dans l' *effet vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l' *effet audio MRC*:
    - LoopbackGain (valeur «augmentation audio de l’application» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
    - MicrophoneGain (valeur «MIC audio» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity. Ce comportement permet d’éviter un problème qui entraîne l’interruption de certaines applications lorsque le Visor est retourné, même si le paramètre à exécuter en arrière-plan est activé. L’API est désormais activée pour les versions Unity 2018.4.18 et les versions ultérieures, et 2019.3.4 et les versions ultérieures.
- Correction d’un problème qui entraînait des applications HoloLens qui modifiaient leur format de pixel pour afficher en noir dans l’émulateur HoloLens.
- Correction d’un problème concernant les lancements de l’application photos lors des démarrages initiaux après la mise à jour à partir de la version 1903.

## Windows holographique, version 2004  
- Build-19041,1103

La mise à jour logicielle majeure de 2020 pour HoloLens 2, *Windows holographique, version 2004* inclut un hôte de nouvelles fonctionnalités passionnantes, telles que la prise en charge de Windows AutoPilot, le mode sombre de l’application, la prise en charge de la technologie USB Ethernet pour les points d’accès 5 5G/LTE et bien plus encore. Pour effectuer une mise à jour vers la version la plus récente, ouvrez l’application **paramètres**   , accédez à **mettre à jour & sécurité**, puis sélectionnez le bouton **Rechercher les mises à jour**   . 

|             Fonctionnalité                              |          Description                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Préconfigurer et configurer en toute transparence de nouveaux appareils pour la production à l’aide de Windows AutoPilot                 |
|       Support au 2-2                             |          La prise en charge des clés de sécurité FIDO2 pour activer l’authentification rapide et sécurisée pour les appareils partagés            |
|       Attribution améliorée                      |          Appliquez en toute transparence un package de mise à service d’un lecteur USB à votre HoloLens                              |
|       État de l’installation de l’application                 |          Vérifier l’état d’installation dans l’application paramètres pour les applications qui ont été transmises à HoloLens 2 via la gestion des périphériques mobiles               |
|       Fournisseurs de services de configuration (CSP)   |          Ajout de nouveaux fournisseurs de service de configuration pour améliorer les fonctionnalités de contrôle d’administration                 |
|       Support USB 5G/LTE                       |          La prise en charge de la fonctionnalité USB USB permet une prise en charge de 5 5G/LTE.                                    |
|       Mode application sombre                              |          Mode application sombre disponible pour les applications qui prennent en charge les modes sombres et clairs, améliorant ainsi l’affichage        |
|       Commandes vocales                             |          Prise en charge des commandes vocales supplémentaires pour contrôler les mains libres de HoloLens                           |
|       Amélioration du suivi des mains                 |          Les améliorations apportées au suivi des mains permettent d’améliorer la précision des boutons et des interactions de ardoise 2D                        |
|       Améliorations de la qualité et correctifs                 |          Diverses améliorations apportées aux performances et à la fiabilité du système sur la plateforme                            |

### Prise en charge de Windows AutoPilot

Windows AutoPilot pour HoloLens 2 permet au canal des ventes de l’appareil de procéder à l’inscription de HoloLens dans votre client Intune. Lorsque les appareils arrivent, ils sont prêts à être auto-déployés en tant qu’appareils partagés sous votre client. Pour tirer parti de l’auto-déploiement, l’appareil doit se connecter à un réseau au cours du premier écran du programme d’installation en utilisant une connexion USB-C-to-Ethernet.

Après le démarrage du processus de déploiement automatique du pilotage automatique par un utilisateur, le processus effectue les étapes suivantes:

1. Joindre l’appareil à Azure ActiveDirectory (AzureAD).
1. Utilisez Azure AD pour inscrire l’appareil dans Microsoft Intune (ou un autre service GPM).
1. Téléchargez les stratégies, certificats et profils de réseau destinés aux appareils.
1. Mettez en service l’appareil.
1. Présentez l’écran de connexion à l’utilisateur.

Pour plus d’informations, consultez le [Guide d’évaluation de Windows AutoPilot pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Contactez votre administrateur de compte pour accéder à la version d’évaluation du pilotage automatique. Les appareils AutoPilot-Ready seront bientôt disponibles pour l’expédition.*

### Prise en charge de la clé de sécurité FIDO2

Certains utilisateurs partagent un appareil HoloLens avec d’autres personnes dans un environnement professionnel ou scolaire. C’est pourquoi il est important que les utilisateurs puissent facilement taper des noms d’utilisateur et des mots de passe longs. Identité rapide en ligne (Rex) permet à tous les membres de votre organisation de se connecter sans problème à HoloLens sans entrer de nom d’utilisateur ou de mot de passe.

Les clés de sécurité FIDO2 sont une méthode d’authentification par mot de passe standard «sans hameçonnage», qui peut être basée sur tout facteur de forme. Le Rex est une norme ouverte pour l’authentification par mot de passe. Il permet aux utilisateurs et aux organisations de se connecter à leurs ressources sans nom d’utilisateur ou mot de passe. Au lieu de cela, ils utilisent une clé de sécurité externe ou une clé de plateforme intégrée à un appareil.

Pour commencer, voir connexion à la [clé de sécurité en](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)tant que mot de passe.

### Inscription GPM améliorée via le package de mise en service

Les packages de mise en service permettent de définir la configuration HoloLens par le biais d’un fichier de configuration plutôt que par le biais de l’interface HoloLens de la boîte de l’utilisateur. Auparavant, les packages de mise en service devaient être copiés sur la mémoire interne du HoloLens. Ils peuvent désormais se trouver sur un lecteur USB de sorte qu’ils soient plus faciles à réutiliser sur plusieurs appareils HoloLens et que vous pouvez fournir des périphériques en parallèle. Les packages de mise en service prennent désormais en charge un champ pour s’inscrire à la gestion des périphériques, de sorte qu’il n’y a pas de configuration manuelle après approvisionnement.

Pour l’essayer:

1. Téléchargez la version la plus récente du concepteur de configuration Windows à partir du Windows Store sur votre PC.
1. Sélectionnez mise en **service de périphériques hololens**pour les  >  **appareils hololens 2**.
2. Créez votre profil de configuration. Ensuite, copiez tous les fichiers qui ont été créés sur un appareil de stockage USB-C.
3. Connectez l’appareil USB-C à un casque HoloLens fraîche. Ensuite, appuyez **volume down**sur les  +  boutons**d’alimentation** du volume.

### État d’installation d’une application métier

Le déploiement et la gestion des applications GPM pour les applications métier sont essentiels au HoloLens. Les administrateurs et les utilisateurs doivent afficher l’état de l’installation de l’application à des fins d’audit et de diagnostic. Dans cette version, nous avons ajouté des informations supplémentaires dans la **section paramètres**d'  >  **Accounts**  >  **accès aux comptes, professionnel ou scolaire**,  >  cliquez sur les informations de**votre compte**  >  **Info**.

### Fournisseurs et stratégies supplémentaires

Un [fournisseur de services de configuration (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) est une interface permettant de lire, définir, modifier ou supprimer des paramètres de configuration sur un appareil. Dans cette version, nous ajoutons une prise en charge pour davantage de stratégies afin d’augmenter les administrateurs de contrôles sur les appareils HoloLens déployés. Pour obtenir la liste des fournisseurs de services de cryptographie pris en charge par HoloLens, consultez [fournisseur de services de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Nouveautés de cette version:

**Fournisseur de services de configuration Policy** 

Le fournisseur de services de configuration de stratégie permet à l’entreprise de configurer des stratégies sur les appareils Windows. Dans cette version, nous avons ajouté de nouvelles stratégies pour HoloLens, qui sont répertoriées ici. Pour plus d’informations, voir [FSC de stratégie pris en charge par HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**Fournisseur de services de configuration NetworkQoSPolicy**

Le fournisseur de services de configuration NetworkQoSPolicy crée des stratégies de qualité de service (QoS) réseau. Une stratégie de QoS effectue un ensemble d’actions sur le trafic réseau basé sur un ensemble de conditions de correspondance. Pour en savoir plus, consultez [fournisseur de services de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Prise en charge Ethernet USB améliorée pour les appareils compatibles 5 5G/LTE

La prise en charge des appareils mobiles haut débit (par exemple, les téléphones 5G/LTE et Wi-Fi hotpots, lorsqu’elles sont attachées au HoloLens 2 via USB) a été ajoutée. Ces périphériques apparaissent désormais dans les **paramètres réseau** comme une autre connexion Ethernet. (Les appareils mobiles haut débit qui nécessitent un pilote externe ne sont pas pris en charge.) Cette fonctionnalité permet une connexion haut débit lorsque le Wi-Fi n’est pas disponible et que la connexion Wi-Fi n’est pas suffisamment performante. Pour en savoir plus sur les périphériques USB pris en charge, voir [se connecter à des appareils Bluetooth et USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Amélioration du suivi des mains

Cette version inclut plusieurs améliorations de suivi manuel:

- **Pointe:** Le système résiste désormais au doigt de l’index lorsqu’il obtient masquée par le Palm. Ce changement améliore la précision lorsque vous appuyez sur les boutons, tapez, faites défiler le contenu, etc. 
- **Diminution de la pression accidentelle d’air:** Nous avons amélioré la détection du geste d’appui ambiant. Il existe désormais moins d’activations involontaires dans plusieurs scénarios courants, par exemple lorsque vous déposez vos mains sur les côtés.
- **Fiabilité du changement d’utilisateur:** Le système est désormais plus rapide et plus fiable lors de la mise à jour de la taille de la mains lors du partage d’un appareil.
- **Réduction du vol de la mains:** Nous avons amélioré la gestion des cas où il y a plus de deux mains en vue des capteurs. S’il existe plusieurs personnes proches, il y a maintenant une chance de reculer que la partie suivie va de la part de l’utilisateur à la partie de la scène.
- **Fiabilité du système:** Correction d’un problème qui provoquait l’arrêt du fonctionnement du suivi de l’appareil lorsque celui-ci est en charge élevée.

### Mode sombre

De nombreuses applications Windows prennent désormais en charge les modes sombres et clairs. Les utilisateurs HoloLens 2 peuvent choisir le mode par défaut pour les applications qui prennent en charge les deux. Après la mise à jour, le mode d’application par défaut est «sombre», mais vous pouvez facilement modifier ce paramètre: accédez à **paramètres**  >  **System**  >  **couleurs**système  >  **Choisissez votre mode d’application par défaut**. 

Les applications «intégrées» prennent en charge le mode foncé: 

- Paramètres 
- MicrosoftStore 
- Mail 
- Calendrier 
- Explorateur de fichiers 
- Hub de commentaires 
- OneDrive 
- Photos 
- Visionneuse3D 
- Films et TV 

![Fenêtre affichée en mode foncé](images/DarkMode.jpg)

### Commandes vocales du système

Vous pouvez désormais utiliser les commandes vocales avec n’importe quelle application sur l’appareil. Pour plus d’informations, reportez-vous [à utilisation de votre voix pour utiliser HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Voir également [langues prises en charge pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Mises à jour de Cortana

L’application mise à jour s’intègre à Microsoft 365 pour vous permettre d’être plus productif sur vos appareils (actuellement US-English uniquement). Sur HoloLens 2, Cortana ne prend plus en charge certaines commandes spécifiques à des appareils, comme le réglage du volume ou le redémarrage. Ces options sont désormais prises en charge par les nouvelles commandes vocales du système. En savoir plus sur la nouvelle application Cortana dans notre [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Améliorations de la qualité et correctifs

Améliorations et correctifs également dans la mise à jour:  
- Introduction d’un système de calibration d’affichage actif. Cette fonctionnalité permet d’améliorer la stabilité et l’alignement des hologrammes. Ils restent en place lorsque vous déplacez votre tête d’un côté à l’autre.
- Correction d’un bogue qui entraînait une interruption périodique de Wi-Fi la diffusion en continu vers HoloLens. Si une application indique qu’elle a besoin d’une latence en flux faible, mettez-la en service en appelant la [fonction SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correction d’un blocage de périphérique qui se produisait lors de la diffusion en mode de recherche.
- Correction d’un bogue où, dans certains cas, l’utilisateur approprié ne s’affichait pas sur l’écran de connexion lors de la reprise d’une session.
- Correction d’un problème dans lequel les utilisateurs ne pouvaient pas exporter les journaux GPM via les **paramètres**.
- Correction d’un problème qui empêchait la précision du suivi visuel immédiatement après la configuration de la version prédéfinie.
- Correction d’un problème pour lequel le sous-système de suivi d’oeil n’a pas pu initialiser ou exécuter un étalonnage dans certaines conditions.
- Correction d’un problème dans lequel un étalonnage d’oeil serait invité pour un utilisateur déjà calibré.
- Correction d’un problème qui entraînait le blocage d’un pilote lors du calibrage des yeux.
- Correction d’un problème qui entraînait la répétition d’une pression de bouton d’alimentation pouvant entraîner un blocage du système d’attente de 60 secondes et un blocage de l’environnement.
- Amélioration de la stabilité des mémoires tampons de profondeur.
- Ajout d’un bouton **partager** dans le hub de commentaires pour permettre aux utilisateurs de partager plus facilement leurs commentaires.
- Correction d’un bogue dans lequel RoboRaid wan’t a été correctement installé.

### Problèmes connus

- Un problème lié à la langue du système zh-CN empêche les commandes vocales de prendre une réalité mixte ou d’afficher l’adresse IP de l’appareil.
- Un problème nécessite le lancement de l’application Cortana après le démarrage de l’appareil pour utiliser l’activation vocale «Hey Cortana». Si vous avez mis à jour à partir d’une build 18362, vous pouvez également voir une deuxième vignette d’application pour la version précédente de l’application Cortana qui ne fonctionne plus dans le **menu Démarrer**.

## Windows holographique, version 1903-2020 mise à jour 
- Version 18362,1061

Cette mise à jour de qualité mensuelle ne contient aucune modification remarquable, car l’équipe a travaillé sur la version 2004 de Windows holographique, comme décrit précédemment.

## Windows holographique, version 1903-mise à jour d’avril 2020
- Version 18362,1059

**Mode sombre pour les applications prises en charge** 

De nombreuses applications Windows prennent en charge les modes sombre et clair. Les clients HoloLens 2 peuvent désormais choisir le mode par défaut pour les applications qui prennent en charge les deux modèles de couleurs. Sur la base des commentaires des clients, nous définissons le mode d’application par défaut sur «Dark», mais vous pouvez facilement modifier ce paramètre à tout moment: accédez à **paramètres > système > couleurs** pour rechercher **«choisir votre mode d’application par défaut».**

Les applications «intégrées» prennent en charge le mode foncé:
- Paramètres
- MicrosoftStore
- Mail
- Calendrier
- Explorateur de fichiers
- Hub de commentaires
- OneDrive
- Photos
- Visionneuse3D
- Films et TV

**Améliorations et correctifs également dans la mise à jour:** 
- Assurez-vous que les façades de l’interpréteur de Shell sont incluses dans les captures de réalité mixte.
- Les développeurs inconcrets peuvent désormais utiliser la page d’affichage 3D dans Device Portal pour tester et déboguer leurs applications.
- Amélioration de la stabilité de l’hologramme lors de la capture de la réalité mixte lors de l’utilisation de l’algorithme *DepthReprojection HolographicDepthReprojectionMethod* .
- Correction du message d’erreur «Impossible d’inscrire la classe de l’API IStreamSocketListener WinRT» dans les applications ARM 32 bits.

## Windows holographique, version 1903-mise à jour de mars 2020 
- Version 18362,1056

Améliorations et correctifs de la mise à jour:

- Amélioration de la stabilité de l’hologramme lors de la capture de la réalité mixte lors de l’utilisation de l’algorithme *Autoplan HolographicDepthReprojectionMethod*
- Vérifiez que le système de coordonnées attaché à un échantillon de profondeur MF est cohérent avec la documentation publique.
- Amélioration de la productivité des développeurs en permettant aux clients de coller de grandes quantités de texte par le biais de Device Portal.

## Windows holographique, version 1903-mise à jour de février 2020 
- Version 18362,1053

Améliorations et correctifs de la mise à jour:

- Temporairement désactivé l’API HolographicSpace. UserPresence pour les applications Unity. Cette modification évite un problème qui entraînait le suspension de certaines applications lorsque le Visor avait été retourné, même si le paramètre «exécuter en arrière-plan» a été activé.
- Correction d’un blocage HUP aléatoire causé par un suivi de la mains, dans lequel l’utilisateur a remarqué qu’une interface utilisateur est figée, puis revenez à l’interpréteur de secondes.
- Amélioration du suivi de la main de façon à ce que lors de l’utilisation du doigt indexé, la partie supérieure du doigt ne devrait pas être bouclée.
- Fiabilité améliorée du suivi des têtes, du mappage spatial et des autres runtimes.

## Windows holographique, version 1903-mise à jour de janvier 2020 
- Version 18362,1043
 
Améliorations et correctifs de la mise à jour:

- Amélioration de la stabilité des applications exclusives lors de l’utilisation de l’émulateur HoloLens 2.

## Windows holographique, version 1903-mise à jour 2019 de décembre 
- Version 18362,1042

Améliorations et correctifs de la mise à jour:

- Introduction de la reproduction de la dernière étape (LSR). Amélioration du rendu visuel des hologrammes qui s’affichent de manière plus stable et précise en tenant compte de leur profondeur. Ce symptôme sera plus remarqué après cette mise à jour si les applications ne définissent pas correctement la profondeur des hologrammes.
- Fiabilité incorrecte des applications exclusives et de la navigation entre des applications exclusives.
- Résolution d’un problème pour lequel la capture de la réalité mixte n’a pas pu enregistrer la vidéo une fois que l’appareil a été en état d’attente pendant plusieurs jours.
- Amélioration de la stabilité des hologrammes.

## Windows holographique, version 1903-mise à jour de novembre 2019 
- Version 18362,1039

Améliorations et correctifs de la mise à jour:

- Fonctionnalités corrigées du bouton **Sélectionner** les commandes vocales lors de la configuration initiale de en-ca et en-au.
- Amélioration de la qualité visuelle des objets placés loin dans les versions les plus récentes des Unitments et des outils de MRTK
- Correction des problèmes d’adressage liés aux applications holographiques bloqués dans un état suspendu au démarrage jusqu’à ce que le menu Démarrer soit ouvert, puis fermé.
- OpenXRx, xxxxxxx, xxx xxxxxxxxx XXXXXXX XXXXXXX XXXXXXX xxx xxxxxxx.
