---
title: Insider Preview pour MicrosoftHoloLens
description: Il est facile de commencer à utiliser les builds Insider et de fournir des commentaires utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 879ff13b30fdce77d823b66035cd59fa0e217c5f
ms.sourcegitcommit: 209247c83eff5cbabbbdecb8cf6e974eabcb36ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2020
ms.locfileid: "10883369"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans la dernière build Insider Preview pour HoloLens.  Il est facile de commencer et de fournir des commentaires utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.

Windows Insider se déplace désormais vers les canaux. Le sonne **rapide** devient le **canal de développement**, la sonnerie **lente** devient le **canal bêta**et la sonnerie de la version d' **évaluation** devient le **canal de publication**. Voici à quoi ressemble le mappage:

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations: [entrée de blog Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## Commencer à recevoir les builds Insider

Sur un appareil HoloLens 2, accédez à **paramètres**  ->  **mise à jour &**  ->  **programme Windows Insider** Security et sélectionnez **commencer**. Liez le compte que vous avez utilisé pour vous inscrire au programme Windows Insider.

Ensuite, sélectionnez **développement actif de Windows**, choisissez si vous souhaitez recevoir les builds de **canaux de développement** ou de **canaux bêta** , puis passez en revue les termes du programme.

Sélectionnez **confirmer-> redémarrer maintenant** pour terminer. Après le redémarrage de votre appareil, accédez à **paramètres-> mettre à jour & sécurité-> Rechercher les mises à jour** pour obtenir la dernière version.

## Ne plus recevoir les builds Insider

Si vous ne voulez plus recevoir les builds Insider de Windows holographique, vous pouvez choisir de désactiver la version d’évaluation de votre appareil à [l’aide du](hololens-recovery.md) compagnon de récupération avancé pour récupérer votre appareil vers une version non-Insider de Windows holographique.

> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui se sont désinscrits de la version d’évaluation Insider Preview après la réinstallation manuelle d’une nouvelle version d’évaluation apparaîtraient sur un écran bleu. Par la suite, ils doivent récupérer manuellement leur appareil. Pour obtenir des informations complètes sur le [problème](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)ou non, consultez ce qui suit.

Pour vérifier que votre HoloLens exécute une build de production:

1. Accédez à **paramètres > système > à propos**de et recherchez le numéro de Build.

1. [Consultez les notes de publication pour les numéros de build de production](hololens-release-notes.md).

Pour désactiver les builds Insider:

1. Sur un HoloLens exécutant une build de production, accédez à **paramètres > mettre à jour & sécurité > programme Windows Insider**, puis sélectionnez **arrêter les builds Insider**.

1. Suivez les instructions pour choisir votre appareil.


## Faire part de vos commentaires et signaler des problèmes

Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour formuler des commentaires et signaler des problèmes. Le hub de commentaires vous permet de vous assurer que toutes les informations de diagnostic nécessaires sont incluses pour faciliter le débogage et le résolution rapide du problème.  Des problèmes liés à la version chinois et japonais de HoloLens doivent être signalés de la même manière.

> [!NOTE]
> Assurez-vous d’accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).

## Remarque pour les développeurs

Vous êtes heureux et encouragé à essayer de développer vos applications à l’aide des builds Insider de HoloLens.  Consultez la [documentation pour développeurs HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds Insider d’HoloLens.  Vous pouvez utiliser les mêmes builds Unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.


## Notes de publication de Windows Insider

Si vous recherchez une fonctionnalité qui n’est plus répertoriée ici, elle est désormais disponible en général. Veuillez consulter les [notes de publication](hololens-release-notes.md) pour savoir quelle Build dispose de la ou des fonctionnalités dont vous êtes ravi. Veillez à [mettre à jour votre HoloLens](hololens-update-hololens.md) pour obtenir les dernières fonctionnalités.

Nous mettrons à jour cette page avec de nouvelles fonctionnalités à mesure que nous les publions vers les builds Insider.

| Fonctionnalité                               | Description                                                                                   | Disponible dans les builds Insider |
|---------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| Prise en charge de la position de l’oeil automatique             | Trouve activement les positions visuelles et permet un positionnement précis des hologrammes.                       | 19041.1339 +                 |
| Accès global affecté                | Configurer l’appareil HoloLens 2 pour le mode kiosque de plusieurs applications, applicable au niveau du système.  | 19041.1346 +                 |
| Lancement automatique d’une application dans Kiosk multi-App | Définit une application pour qu’elle s’ouvre automatiquement lors de la connexion à un mode Kiosk à plusieurs applications. | 19041.1346 +                 |
| Nouvelles stratégies d’alimentation pour Hololens 2     | Stratégies récemment prises en charge pour les paramètres de délai d’alimentation.                                          | 19041.1349 +                 |
| Afficheur de certificats                    | Affichez les certificats d’utilisateur et d’appareil dans l’application paramètres.                                        | 19041.1346 +                 |

### Prise en charge de la position de l’oeil automatique

Dans HoloLens 2, les positions visuelles permettent un positionnement précis des hologrammes, une confort d’affichage confortable et une meilleure qualité d’affichage. Les positions visuelles sont calculées dans le résultat du suivi visuel. Toutefois, cela nécessite que chaque utilisateur passe par le calibrage du suivi visuel, même lorsque l’utilisation ne requiert pas d’entrée en regard.

La position de l' **oeil automatique (AEP)** permet à ces scénarios d’avoir une méthode d’interaction sans interaction pour calculer la position des yeux de l’utilisateur.  La position de l’oeil automatique commence automatiquement à fonctionner en arrière-plan à partir du moment où l’utilisateur place le périphérique. Si l’utilisateur ne dispose pas d’un étalonnage de suivi d’oeil antérieur, la position d’oeil automatique commencera à fournir à l’oeil de l’utilisateur le système d’affichage après un temps de traitement faible. Ce temps de traitement est généralement compris entre 20-60 secondes. Les données de l’utilisateur ne sont pas conservées sur l’appareil et, de ce fait, le processus est répété s’il est mis en place par l’utilisateur, ou si l’appareil est redémarré ou s’arrête de sortir du mode veille.  

Il existe certaines modifications de comportement système avec la fonctionnalité de position de l’oeil automatique quand un utilisateur non calibré le place sur l’appareil. Un utilisateur sans calibrage fait référence à une personne qui n’a pas encore parcouru le processus d’étalonnage du suivi visuel sur l’appareil.

|     Application active                           |     Comportement actuel                                   |     Comportement de Windows Insider Build 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     Application et interpréteur holographique non activé    |     Invite de calibration du suivi d’oeil s’affiche.    |     Aucune invite ne s’affiche.                                                                                |
|     Application en option                             |     Invite de calibration du suivi d’oeil s’affiche.    |     L’invite de calibration du suivi d’oeil s’affiche uniquement lorsque l’application accède à un flux d’oeil.     |

 Si l’utilisateur passe d’une application à l’autre qui accède aux données de pointage, l’invite s’affiche. Il n’y a aucun changement de flux d’expérimentation hors champ. 
 
Dans le cas d’expériences nécessitant des informations visuelles ou un positionnement très précis, nous vous recommandons d’effectuer un étalonnage du suivi visuel à partir de l’invite d’étalonnage du suivi d’oeil ou en lançant l’application paramètres à partir du menu Démarrer, puis en sélectionnant **système > calibration >** d’étalonnage > d’exécution.

**Problèmes connus**
 - Nous travaillons à la résolution d’un problème dans lequel le processus de l’hôte du pilote Le processus hôte du pilote de suivi visuel doit procéder à une récupération automatique.

### Accès global affecté – mode plein écran
Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode kiosque de plusieurs applications, qui est applicable au niveau du système, sans affinité avec aucune identité sur le système et qui s’applique à toutes les personnes qui se connectent à l’appareil. Pour en savoir [plus, consultez](hololens-global-assigned-access-kiosk.md)cette nouvelle fonctionnalité.

### Lancement automatique d’une application dans le mode Kiosk à plusieurs applications 
S’applique uniquement au mode Kiosk multi-App et seule une application peut être désignée pour le lancement automatique à l’aide de l’attribut en surbrillance ci-dessous dans la configuration Access attribuée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Nouvelles stratégies d’alimentation pour Hololens 2
Ces stratégies récemment ajoutées permettent aux administrateurs de contrôler les États d’alimentation tels que le délai d’inactivité. Pour en savoir plus sur chaque stratégie individuelle, cliquez sur le lien correspondant à cette stratégie.

|     Lien documentation de la stratégie                |     Remarques                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Exemple de valeur à utiliser dans le concepteur de configuration Windows, c’est-à-dire 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, c’est-à-dire 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### Afficheur de certificats

Dans Windows Insider Build 19041.1346 +, nous ajoutons un afficheur de certificats à l’application paramètres HoloLens 2. Cette fonctionnalité fournit un moyen simple et convivial de vérifier les certificats sur votre appareil. Pour trouver rapidement un certificat spécifique, il est possible d’effectuer un tri sur la base d’un nom, d’un magasin ou d’une date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Avec la nouvelle visionneuse de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir la sécurité et la conformité des appareils.  Pour afficher davantage d’informations sur un certificat individuel, sélectionnez le certificat, puis cliquez sur informations.

> [!NOTE]
> Il existe une limite connue concernant la localisation des langues non américaine que nous travaillons à la résolution des versions ultérieures de Windows Insider.

-   **Audit:** Possibilité de vérifier que le déploiement d’un certificat est correct ou qu’il a été supprimé de manière appropriée. 
-   **Diagnostic:** En cas de problème, le fait de vérifier que les certificats appropriés existent sur l’appareil permet de gagner du temps et d’aider à résoudre les problèmes. 
-   **Validation:** Le fait de vérifier que le certificat a la finalité prévue et qu’il est fonctionnel, peut faire gagner du temps, en particulier dans les environnements commerciaux avant de déployer des certificats à plus grande échelle.

Pour afficher les certificats, accédez à **paramètres > mettre à jour & certificats de sécurité >**.

![Afficheur de certificats dans l’application paramètres](images/hololens-certificate-viewer.png)

## FFU télécharger et clignoter
Pour tester la version d’évaluation d’un FFU, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU.
1. Sur PC:

    1. Téléchargez FFU sur votre PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. Sur HoloLens-version de déverrouillage **Settings**: Ouvrez la  >  **mise à jour des paramètres &**  >  **programme Windows Insider** Security et inscrivez-vous, puis redémarrez l’appareil.

1. Flash FFU-désormais, vous pouvez faire clignoter le FFU signé par ARC.
