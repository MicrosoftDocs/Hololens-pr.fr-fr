---
title: Notes de publication HoloLens 2
description: En savoir plus sur les mises à jour de chaque nouvelle version de HoloLens.
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
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828251"
---
# Notes de publication HoloLens 2

Pour vous assurer que vous disposez d’une satisfaction productive sur vos appareils HoloLens, nous continuons à libérer les mises à jour de fonctionnalités, de bogues et de sécurité. Dans cette page, vous pouvez en savoir plus sur les nouveautés de HoloLens par mois. Pour télécharger la dernière version de HoloLens 2 FFU et faire clignoter votre appareil à l’aide de l' [Assistant de restauration avancée](hololens-recovery.md#clean-reflash-the-device) , vous pouvez le télécharger à partir de [cet emplacement](https://aka.ms/hololens2download). Ce dernier est tenu à jour et correspond à la dernière build disponible en général. 

Les notes de publication de l’émulateur HoloLens sont accessibles [ici](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holographique, version 2004-mise à jour de juin 2020
- Version 19041,1106

Améliorations et correctifs de la mise à jour:

- Les enregistrements MRC personnalisés possèdent de nouvelles valeurs par défaut pour certaines propriétés, si elles ne sont pas spécifiées.
  - Dans l’effet vidéo MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l’effet audio MRC:
    - LoopbackGain (valeur «augmentation audio de l’application» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
    - MicrophoneGain (valeur «MIC audio» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
- Cette mise à jour inclut un correctif qui améliore la qualité audio dans les scénarios de capture de la réalité mixte. Plus précisément, il devrait éliminer les problèmes audio dans l’enregistrement lorsque le menu Démarrer s’affiche.
- Amélioration de la stabilité de l’hologramme dans les vidéos enregistrées.
- Résout un problème dans lequel la capture de la réalité mixte n’a pas pu enregistrer la vidéo une fois que l’appareil est resté en attente pendant plusieurs jours.
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity afin d’éviter un problème qui entraîne la mise en pause de certaines applications lorsque le Visor est retourné, même si le paramètre à exécuter en arrière-plan est activé. L’API est désormais activée pour les versions Unity 2018.4.18 et supérieures, et 2019.3.4 ou version ultérieure.
- Lorsque vous accédez à Device Portal sur une connexion WiFi, un navigateur Web peut empêcher l’accès en raison d’un certificat non valide en signalant une erreur telle que «ERR_SSL_PROTOCOL_ERROR», même si le certificat d’appareil a déjà été approuvé.  Dans ce cas, vous ne pourrez pas progresser sur Device Portal en tant qu’options pour ignorer les avertissements de sécurité.  Cette mise à jour résout le problème.  Si le certificat d’appareil a été téléchargé et approuvé sur un PC pour supprimer les avertissements de sécurité du navigateur et si l’erreur SSL s’est produite, le nouveau certificat doit être téléchargé et approuvé pour répondre aux avertissements de sécurité du navigateur.
- Possibilité de créer un package de déploiement d’exécution qui peut installer une application à l’aide de packages MSIX.
- Nouveau paramètre qui permet aux utilisateurs de se retrouver sous paramètres > système > d’hologrammes, ce qui permet aux utilisateurs de les supprimer automatiquement de la maison mixte lorsque l’appareil s’arrête.
- Correction d’un problème qui entraînait des applications HoloLens qui modifiaient leur format de pixel pour afficher en noir dans l’émulateur HoloLens.
- Correction d’un bogue entraînant un blocage lors de l’ouverture de session en IRIS.
- Corrige un problème au niveau des téléchargements de magasin répétés pour des applications déjà actuelles.
- Correction d’un bogue visant à empêcher les applications immersives de démarrer à plusieurs reprises.
- Résout un problème de lancement de l’application photos au démarrage initial après la mise à jour à partir de la version 1903.
- Amélioration des performances et de la fiabilité.

## Windows holographique, version 1903-mise à jour de juin 2020
- Version 18362,1064

Améliorations et correctifs de la mise à jour:

- Les enregistrements MRC personnalisés possèdent de nouvelles valeurs par défaut pour certaines propriétés, si elles ne sont pas spécifiées.
  - Dans l’effet vidéo MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l’effet audio MRC:
    - LoopbackGain (valeur «augmentation audio de l’application» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
    - MicrophoneGain (valeur «MIC audio» actuelle sur la page de capture de la réalité mixte de Windows Device Portal)
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity afin d’éviter un problème qui entraîne la mise en pause de certaines applications lorsque le Visor est retourné, même si le paramètre à exécuter en arrière-plan est activé. L’API est désormais activée pour les versions Unity 2018.4.18 et supérieures, et 2019.3.4 ou version ultérieure.
- Correction d’un problème qui entraînait des applications HoloLens qui modifiaient leur format de pixel pour afficher en noir dans l’émulateur HoloLens.
- Résout un problème de lancement de l’application photos au démarrage initial après la mise à jour à partir de la version 1903.

## Windows holographique, version 2004  
Build-19041,1103

Nous sommes ravis de vous annoncer la mise à jour logicielle de 2020 pour HoloLens 2, **Windows holographique, version 2004**. Cette version inclut un grand nombre de nouvelles fonctionnalités passionnantes, telles que la prise en charge du pilotage automatique Windows, du mode sombre de l’application, de la prise en charge de la technologie USB pour les points d’accès 5G/LTE et bien plus encore. Pour effectuer une mise à jour vers la version la plus récente, ouvrez l' **application paramètres**, accédez à **mettre à jour & sécurité**, puis sélectionnez le bouton **Rechercher les mises à jour**   . 

|             Fonctionnalité                              |          Description                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       WindowsAutopilot                          |          Préconfiguration et configuration transparente de nouveaux appareils pour la production grâce au pilotage automatique Windows                 |
|       Support au 2-2                             |          La prise en charge des clés de sécurité FIDO2 pour activer l’authentification rapide et sécurisée pour les appareils partagés            |
|       Attribution améliorée                      |          Appliquez en toute transparence un package de mise à service d’un lecteur USB à votre HoloLens                              |
|       État de l’installation de l’application                 |          Vérifier l’état d’installation des applications ont été transmises à HoloLens 2 via la gestion des périphériques mobiles dans l’application paramètres              |
|       Fournisseurs de services de configuration (CSP)   |          Ajout de nouveaux fournisseurs de services de configuration qui améliorent les capacités de contrôle d’administration.                 |
|       Support USB 5G/LTE                       |          La prise en charge de la fonctionnalité USB USB permet une prise en charge de 5 5G/LTE.                                    |
|       Mode application sombre                              |          Mode d’application sombre pour les applications qui prennent en charge les modes sombres et clairs, améliorant ainsi l’affichage        |
|       Commandes vocales                             |          Prise en charge des commandes vocales supplémentaires pour contrôler HoloLens, mains libres                           |
|       Amélioration du suivi des mains                 |          Les améliorations apportées au suivi des mains permettent d’améliorer la précision des boutons et des interactions de ardoise 2D                        |
|       Améliorations de la qualité et correctifs                 |          Diverses améliorations apportées aux performances et à la fiabilité du système sur la plateforme                            |

### Prise en charge de Windows AutoPilot 

Windows AutoPilot pour HoloLens 2 permet au canal des ventes de l’appareil de procéder à l’inscription de HoloLens dans votre client Intune.  Lorsque les appareils arrivent, ils sont prêts à être auto-déployés en tant qu’appareils partagés sous votre client. Pour tirer parti de l’auto-déploiement, les appareils doivent se connecter à un réseau au cours du premier écran de l’installation à l’aide d’une clé USB-C à Ethernet ou d’un dongle USB-C à LTE. 

Lorsqu’un utilisateur démarre le processus Autopilot de déploiement autonome, le processus effectue les étapes suivantes: 

1. Joindre l’appareil à Azure ActiveDirectory (AzureAD). 
1. Utilisez Azure AD pour inscrire l’appareil dans Microsoft Intune (ou un autre service GPM). 
1. Téléchargez les stratégies, certificats et profils de réseau destinés aux appareils. 
1. Mettez en service l’appareil. 
1. Présentez l’écran de connexion à l’utilisateur. 

Pour plus d’informations, consultez le [Guide d’évaluation de Windows AutoPilot pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

**Contactez votre administrateur de compte pour accéder à la version d’évaluation du pilotage automatique. Les appareils AutoPilot-Ready seront bientôt disponibles pour l’expédition.**

### Prise en charge de la clé de sécurité FIDO2 

De nombreux utilisateurs partagent un appareil HoloLens doté d’un grand nombre de personnes dans un environnement professionnel ou scolaire. Que les appareils soient partagés entre étudiants au sein d’une classe ou extraits par un dispositif de protection des appareils, il est important de pouvoir modifier les utilisateurs rapidement et facilement sans taper de longs noms d’utilisateur et de mots de passe. 

Les membres de votre organisation permettent à tous les membres de votre organisation de se connecter en toute transparence à HoloLens sans entrer de nom d’utilisateur ou de mot de passe. 

FIDO2 clé de sécurité est une méthode d’authentification sans mot de passe normalisée qui peut être utilisée dans n’importe quel facteur de forme. L’identité rapide en ligne (Rex) est une norme ouverte pour l’authentification par mot de passe. Les haut-parleurs permettent aux utilisateurs et organisations de se connecter à leurs ressources sans nom d’utilisateur ou mot de passe à l’aide d’une clé de sécurité externe ou d’une clé de plateforme intégrée à un appareil. 

Lire les [documents de sécurité](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) dans un mot de passe pour commencer. 

### Inscription GPM améliorée via le package de mise en service 

Les packages de mise en service permettent de définir la configuration HoloLens par le biais d’un fichier de configuration plutôt que de passer par l’interface de déploiement hors-connexion HoloLens. Auparavant, il est possible de copier les packages de mise en service sur la mémoire interne de HoloLens, désormais sur une clé USB pour faciliter leur réutilisation sur plusieurs HoloLens et de sorte que d’autres personnes puissent approvisionner le HoloLens en parallèle.  De plus, les packages de mise en service prennent en charge un nouveau champ pour s’inscrire à la gestion des périphériques, de sorte qu’il n’y a pas de configuration manuelle après l’approvisionnement. 

1. Pour l’essayer, téléchargez la version la plus récente du concepteur de configuration Windows à partir du Windows Store sur votre PC. 
1. Sélectionnez mise en **service des appareils hololens** > sélectionnez mise en **service des appareils hololens 2** 
1. Créez votre profil de configuration et, lorsque vous avez terminé, copiez tous les fichiers créés sur un appareil de stockage USB-C. 
1. Branchez-le sur le casque HoloLens et **Mettez le volume hors tension et mettez-le en marche** pour appliquer votre package de mise en service. 

### État de l’installation de l’application sectorielle 

Le déploiement et la gestion des applications GPM pour les applications métier sont indispensables pour nos clients. Les administrateurs et les utilisateurs doivent être en mesure d’afficher l’état de l’installation de l’application, à des fins d’audit et de diagnostic. Dans cette version, nous ajoutons des informations supplémentaires sur **les paramètres > comptes > accès professionnel ou scolaire > cliquez sur le > informations de votre compte.**

### Fournisseurs et stratégies supplémentaires 

Un [fournisseur de services de configuration (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) est une interface permettant de lire, définir, modifier ou supprimer des paramètres de configuration sur un appareil. Dans cette version, nous ajoutons une prise en charge pour davantage de stratégies, ce qui accroît le nombre d’administrateurs de contrôles sur les appareils HoloLens déployés. Pour obtenir la liste des fournisseurs de services de cryptographie pris en charge par HoloLens, visitez ce [lien](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Nouveautés de cette version:

**Fournisseur de services de configuration Policy** 

Le fournisseur de services de configuration de stratégie permet à l’entreprise de configurer des stratégies sur les appareils Windows. Dans cette version, nous ajoutons de nouvelles stratégies pour HoloLens, répertoriées ci-dessous. Vous pouvez en savoir plus sur les stratégies prises en charge [ici](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**Fournisseur de services de NetworkQoSPolicy** Le fournisseur de services de configuration NetworkQoSPolicy crée des stratégies de qualité de service (QoS) réseau. Une stratégie de QoS effectue un ensemble d’actions sur le trafic réseau basé sur un ensemble de conditions de correspondance. Vous pouvez en savoir plus sur cette politique [ici](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). 

### Prise en charge Ethernet USB améliorée pour les appareils compatibles 5 5G/LTE

La prise en charge de certains appareils mobiles haut débit, tels que les téléphones 5G/LTE et le WiFi hotpots lorsque vous êtes attaché au HoloLens 2 via le bus USB est ajoutée. Ces périphériques seront affichés dans paramètres réseau comme une autre connexion Ethernet. Les appareils mobiles haut débit qui nécessitent un pilote externe ne sont pas pris en charge. Cela permet de connecter de haut débit dans les scénarios où le WiFi n’est pas disponible et la connexion WiFi n’est pas suffisante. Vous pouvez en savoir plus sur les périphériques USB pris en charge [ici](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Amélioration du suivi des mains

Le suivi des mains a reçu plusieurs améliorations dans cette version. 

- **Pointe:** Le système résiste désormais à la flexion du doigt d’index lorsqu’il devient masquée par le Palm.  Cela améliore la précision lorsque vous poussez des boutons, en tapant, en faisant défiler le contenu, etc. 
- **Réduction de l’inpression accidentelle:** Nous avons amélioré la détection du geste du AirTap.  Dans de nombreux cas, il y a moins d’activations involontaires, comme le déplacement de vos mains vers votre côté. 
- **Fiabilité du changement d’utilisateur:** Le système est désormais plus rapide et plus fiable lors de la mise à jour de la taille des mains lors du partage d’un périphérique. 
- **Réduction du vol de la mains:** Nous avons amélioré la gestion des cas où il y a plus de 2 mains en vue des capteurs.  Si plusieurs personnes travaillent de concert avec eux, il existe désormais une chance plus faible que la partie suivie passera de l’utilisateur à la partie de la scène. 
- **Fiabilité du système:** Correction d’un problème qui provoquait l’arrêt du fonctionnement du suivi du temps si l’appareil est en charge élevée. 

### Mode sombre

De nombreuses applications Windows prennent désormais en charge les modes sombre et léger, et les utilisateurs HoloLens 2 peuvent choisir le mode par défaut pour les applications qui prennent en charge les deux. Après mise à jour, le mode d’application par défaut est «sombre», mais peut être modifié facilement. Accédez à paramètres > > système de couleurs pour rechercher «choisir votre mode d’application par défaut». Voici quelques-unes des applications qui prennent en charge le mode foncé: 

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

Vous pouvez désormais accéder et utiliser rapidement des commandes avec votre voix lors de l’utilisation de n’importe quelle application sur l’appareil. Si vous utilisez une autre langue sur votre système, essayez les commandes appropriées dans cette langue. Pour plus d’informations sur les commandes et la façon de les utiliser, consultez notre documentation [ici](https://docs.microsoft.com/hololens/hololens-cortana).  

### Mises à jour de Cortana 

L’application mise à jour s’intègre à Microsoft 365, actuellement en anglais (États-Unis) uniquement, pour vous aider à accomplir vos tâches sur tous vos appareils. Sur HoloLens 2, Cortana ne prend plus en charge certaines commandes spécifiques à l’appareil, telles que le réglage du volume ou le redémarrage de l’appareil, qui sont désormais pris en charge par les nouvelles commandes vocales du système mentionnées ci-dessus. En savoir plus sur la nouvelle application Cortana et sa direction sur notre blog [ici](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

### Améliorations de la qualité et correctifs 

Améliorations et correctifs également dans la mise à jour:  
- La mise à jour introduit un système de calibration d’affichage actif. Cela permet d’améliorer la stabilité et l’alignement des hologrammes, ce qui permet aux utilisateurs de rester en place lors du déplacement de votre tête vers le côté. 
- Correction d’un bogue qui entraînait une interruption périodique du flux Wi-Fi en HoloLens. Si une application indique qu’elle a besoin d’une latence en continu faible, ce correctif peut être réalisé en appelant [cette fonction](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode). 
- Correction d’un problème de blocage de l’appareil lors de la diffusion en mode de recherche. 
- Correction d’un bogue dans certains cas où le bon utilisateur ne s’affichait pas sur l’écran de connexion lors de la reprise d’une session. 
- Correction d’un problème dans lequel les utilisateurs ne pouvaient pas exporter les journaux GPM via les paramètres. 
- Correction d’un problème lié à l’exactitude du suivi visuel qui, immédiatement après la configuration, peut être inférieur à la spécification. 
- Correction d’un problème dans lequel le sous-système de suivi des oeils ne pouvait pas être initialisé et/ou exécuter une calibration dans certaines conditions. 
- Correction d’un problème dans lequel le calibrage de l’oeil serait invité pour un utilisateur déjà calibré. 
- Correction d’un problème qui entraînait le blocage d’un pilote lors du calibrage des yeux. 
- Correction d’un problème qui entraînait la répétition d’une pression de bouton d’alimentation pouvant entraîner un blocage de 60 deuxième système et un blocage de l’environnement. 
- Amélioration de la stabilité des mémoires tampons de profondeur. 
- Le bouton «partager» a été ajouté dans le hub de commentaires pour que les utilisateurs puissent facilement partager leurs commentaires. 
- Correction d’un bogue dans lequel RoboRaid n’a pas été installé correctement. 

### Problèmes connus

- Nous travaillons à la résolution d’un problème lié à l’utilisation de la langue du système zh-CN qui empêche les commandes vocales de capturer ou d’afficher l’adresse IP de l’appareil.
- Nous cherchons un problème qui nécessite le lancement de l’application Cortana après le démarrage de l’appareil pour utiliser l’activation vocale «Hey Cortana» et si vous avez effectué une mise à jour à partir d’une build 18362, il est possible qu’une deuxième vignette d’application pour la version précédente de l’application Cortana ne fonctionne plus. 

## Windows holographique, version 1903-2020 mise à jour 
- Version 18362,1061

Cette mise à jour de la qualité mensuelle ne contient aucune modification de la remarque dans la mesure où l’équipe a été focalisée pour vous offrir la mise à jour des fonctionnalités de qualité optimale désormais disponible dans le Windows holographique, version 2004 peut être mise à jour détaillée ci-dessus. N’hésitez pas à passer à la dernière mise à jour des fonctionnalités pour avoir une formidable nouvelle modification.

## Windows holographique, version 1903-mise à jour d’avril 2020
- Version 18362,1059

**Mode sombre pour les applications prises en charge** 

De nombreuses applications Windows prennent en charge les modes sombres et clairs, et les clients HoloLens 2 peuvent choisir le mode par défaut pour les applications qui prennent en charge les deux modèles de couleurs. Sur la base de commentaires clients écrasants, nous définissons le mode d’application par défaut sur «Dark», mais vous pouvez facilement modifier ce paramètre à tout moment.
Accédez à **paramètres > > système de couleurs** pour rechercher **«choisir votre mode d’application par défaut».**

Voici quelques-unes des applications qui prennent en charge le mode foncé:
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
- Assurez-vous qu’ils sont inclus dans les captures de faits mélangées.
- Les développeurs inréalistes peuvent désormais utiliser la page d’affichage 3D dans Device Portal pour tester et déboguer leurs applications.
- Amélioration de la stabilité de l’hologramme dans la capture de la réalité mixte lors de l’utilisation de l’algorithme HolographicDepthReprojectionMethod DepthReprojection
- Correction d’une erreur de classe d’API WinRT IStreamSocketListener non enregistrée dans l’application ARM 32 bits.

## Windows holographique, version 1903-mise à jour de mars 2020 
- Version 18362,1056

Améliorations et correctifs de la mise à jour:

- Amélioration de la stabilité de l’hologramme dans la capture de la réalité mixte lors de l’utilisation de l’algorithme Autoplan HolographicDepthReprojectionMethod.
- Garantit que le système de coordonnées attaché à un échantillon de profondeur MF est cohérent avec la documentation publique.
- Amélioration de la productivité des développeurs en permettant aux clients de coller du texte important via Device Portal.

## Windows holographique, version 1903-mise à jour de février 2020 
- Version 18362,1053

Améliorations et correctifs de la mise à jour:

- Temporairement désactivé l’API HolographicSpace. UserPresence pour les applications Unity afin d’éviter un problème qui entraîne l’interruption de certaines applications lorsque le Visor est retourné, même si le paramètre à exécuter en arrière-plan est activé.
- Correction d’un blocage aléatoire du HUP en cas de suivi de l’utilisateur, dans lequel il sera remarqué qu’une interface utilisateur sera figée, puis revenir au shell après quelques secondes.
- Nous avons amélioré la prise en main du suivi pour que, lors de l’analyse de l’utilisation du doigt d’index, la partie supérieure du doigt soit moins susceptible de s’aspirer.
- Fiabilité améliorée du suivi des têtes, du mappage spatial et des autres runtimes.

## Windows holographique, version 1903-mise à jour de janvier 2020 
- Version 18362,1043

Amélioration de la mise à jour:

- Améliorations de la stabilité des applications exclusives lors de l’utilisation de l’émulateur HoloLens 2.

## Windows holographique, version 1903-mise à jour 2019 de décembre 
- Version 18362,1042

Améliorations et correctifs de la mise à jour:

- Présente les correctifs de LSR Amélioration du rendu visuel des hologrammes qui s’affichent de manière plus stable et précise en tenant compte de leur profondeur. C’est plus notable si les applications ne définissent pas correctement la profondeur des hologrammes, après cette mise à jour.
- Résout la stabilité des applications exclusives et de la navigation entre des applications exclusives.
- Résout un problème dans lequel la capture de la réalité mixte n’a pas pu enregistrer la vidéo une fois que l’appareil est resté en attente pendant plusieurs jours.
- Amélioration de la stabilité des hologrammes.

## Windows holographique, version 1903-mise à jour de novembre 2019 
- Version 18362,1039

Améliorations et correctifs de la mise à jour:

- Correctifs pour les commandes vocales **«Sélectionner»** lors de la configuration initiale de en-ca et en-au.
- Améliorations apportées à la qualité visuelle d’objets placés loin dans les dernières Unity et MRTK.
- Permet de résoudre les problèmes d’adressage avec les applications holographiques bloquées lors du lancement, tant que le panneau des broches ne s’est pas affiché et fermé de nouveau.
- OpenXRx, xxxxxxx, xxx xxxxxxxxx XXXXXXX XXXXXXX XXXXXXX xxx xxxxxxx.


