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
ms.openlocfilehash: 0ca085cfcf96a07b5c022b308a513c895795e945
ms.sourcegitcommit: 81ea187bfd244fb8f489cd8b37c0cc7f6a8bc1cb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926599"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans la dernière build Insider Preview pour HoloLens.  Il est facile de commencer et de fournir des commentaires utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.

Windows Insider se déplace désormais vers les canaux. Le sonne **rapide** devient le **canal de développement**, la sonnerie **lente** devient le **canal bêta**et la sonnerie de la version d' **évaluation** devient le **canal de publication**. Voici à quoi ressemble le mappage:

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations, consultez [Présentation des canaux Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur les blogs Windows.

## Notes de publication de Windows Insider

Si vous recherchez une fonctionnalité qui n’est plus répertoriée ici, elle est désormais disponible en général. Veuillez consulter les [notes de publication](hololens-release-notes.md) pour savoir quelle Build dispose de la ou des fonctionnalités dont vous êtes ravi. Veillez à [mettre à jour votre HoloLens](hololens-update-hololens.md) pour obtenir les dernières fonctionnalités.

Nous mettrons à jour cette page avec de nouvelles fonctionnalités à mesure que nous les publions vers les builds Insider.

| Fonctionnalité                                              | Description                                                                                   | Disponible dans les builds Insider |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| Prise en charge de la position de l’oeil automatique                            | Trouve activement les positions visuelles et permet un positionnement précis des hologrammes.                       | 19041.1339 +                 |
| Afficheur de certificats                                   | Affichez les certificats d’utilisateur et d’appareil dans l’application paramètres.                                        | 19041.1346 +                 |
| Connexion Wi-Fi et utilisation du pilotage automatique                 | Utilisez AutoPilot depuis un Wi-Fi sans avoir besoin d’une carte Ethernet.                            | 19041.1364 +                 |
| Stratégies HoloLens                                    | Nouvelles stratégies pour les appareils de réalité mixte.                                                       | 19041.1349 +                 |
| Mise en cache de l’appartenance aux groupes AAD pour Kiosk hors connexion         | Politique pour le nombre de jours pendant lesquels le cache d’appartenance au groupe AAD est autorisé à utiliser le mode plein écran.     | 19041.1356 +                 |
| Nouvelles stratégies de restriction d’appareil pour HoloLens 2       | Les stratégies de gestion des appareils activées pour HoloLens 2 sont activées.                              | 19041.1349 +                 |
| Nouvelles stratégies d’alimentation pour HoloLens 2                    | Stratégies récemment prises en charge pour les paramètres de délai d’alimentation.                                          | 19041.1349 +                 |
| Stratégies de mise à jour                                      | Stratégies récemment activées permettant le contrôle des mises à jour.                                           | 19041.1352 +                 |
| Visibilité de la page de paramètres activée pour HoloLens 2      | Stratégie pour sélectionner les pages qui apparaissent dans l’application paramètres.                                          | 19041.1349 +                 |
| Accès global affecté                               | Configurer l’appareil HoloLens 2 pour le mode kiosque de plusieurs applications, applicable au niveau du système.  | 19041.1356 +                 |
| Lancement automatique d’une application dans Kiosk multi-App                | Définit une application pour qu’elle s’ouvre automatiquement lors de la connexion à un mode Kiosk à plusieurs applications. | 19041.1346 +                 |
| Modification du comportement du mode plein écran pour la gestion des échecs | Modification de la façon dont l’échec du mode plein écran est désormais géré.                                             | 19041.1356 +                 |

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

### Afficheur de certificats

Dans Windows Insider Build 19041.1346 +, nous ajoutons un afficheur de certificats à l’application paramètres HoloLens 2. Cette fonctionnalité fournit un moyen simple et convivial de vérifier les certificats sur votre appareil. Pour trouver rapidement un certificat spécifique, il est possible d’effectuer un tri sur la base d’un nom, d’un magasin ou d’une date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Avec la nouvelle visionneuse de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir la sécurité et la conformité des appareils.  Pour afficher davantage d’informations sur un certificat individuel, sélectionnez le certificat, puis cliquez sur informations.

> [!NOTE]
> Il existe une limite connue concernant la localisation des langues non américaine que nous travaillons à la résolution des versions ultérieures de Windows Insider.

-   **Audit:** Possibilité de vérifier que le déploiement d’un certificat est correct ou qu’il a été supprimé de manière appropriée. 
-   **Diagnostic:** En cas de problème, le fait de vérifier que les certificats appropriés existent sur l’appareil permet de gagner du temps et d’aider à résoudre les problèmes. 
-   **Validation:** Le fait de vérifier que le certificat a la finalité prévue et qu’il est fonctionnel, peut faire gagner du temps, en particulier dans les environnements commerciaux avant de déployer des certificats à plus grande échelle.

Pour afficher les certificats, accédez à **paramètres > mettre à jour & certificats de sécurité >**.

![Afficheur de certificats dans l’application paramètres](images/hololens-certificate-viewer.png)

### Connexion Wi-Fi et utilisation du pilotage automatique
À présent, lorsque vous connectez HoloLens 2 avec WiFi, OOBE vérifie s’il y a un profil AutoPilot pour l’appareil. S’il en existe une, il sera utilisé pour effectuer la partie restante du flux d’inscription AAD. En d’autres termes, l’utilisation d’une carte Ethernet vers une carte USB c ou WiFi vers la carte USB C n’est plus obligatoire, mais elle continue de fonctionner au début de OOBE. En savoir plus sur le [pilotage automatique pour les appareils HoloLens 2](hololens2-autopilot.md).

### Stratégies HoloLens
De nouvelles stratégies de réalité mixte ont été créées pour les appareils HoloLens 2 lors de générations 19041.1349 +. Les nouveaux paramètres contrôleurs incluent: définir la luminosité, définir le volume et désactiver l’enregistrement audio dans les captures de réalité mixte, définir quand les diagnostics peuvent être collectés et cache d’appartenance de groupe AAD.  

| Nouvelle stratégie HoloLens                                | Description                                                                               | Remarques                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permet que les boutons de luminosité soient désactivés, ce qui permet de ne pas modifier la luminosité.       | 1 Oui, 0 (par défaut)                                                |
| MixedReality\VolumeButtonDisabled                  | Autorise la désactivation des boutons de volume et la pression sur celle-ci ne modifie pas le volume.               | 1 Oui, 0 (par défaut)                                                |
| MixedReality\MicrophoneDisabled                    | Désactive le microphone de sorte qu’aucun enregistrement audio ne soit possible sur HoloLens 2.                      | 1 Oui, 0 (par défaut)                                                |
| MixedReality\FallbackDiagnostics                   | Contrôle le comportement du moment où les journaux de diagnostic peuvent être collectés.                               | 0 désactivé, 1 activé pour les propriétaires d’appareils, 2 activés pour All (par défaut) |
| MixedReality\HeadTrackingMode                      | Réservé pour une utilisation ultérieure.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Détermine le nombre de jours d’appartenance au groupe AAD pour le ciblage des kiosques pour les groupes AAD. | Voir ci-dessous.                                                           |

### Mise en cache de l’appartenance aux groupes AAD pour Kiosk hors connexion

Cette politique détermine le nombre de jours que le cache d’appartenance au groupe AAD est autorisé à utiliser pour les configurations d’accès affectées qui ciblent les groupes AAD pour l’utilisateur connecté. Lorsque la valeur de la stratégie est définie sur valeur supérieure à 0, la mise en cache est utilisée dans le cas contraire.  

Nom: valeur d’URI AADGroupMembershipCacheValidityInDays:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 jours  
Max-60 jours 

Procédure d’utilisation correcte de cette stratégie: 
1. Créez un profil de configuration d’appareil pour Kiosk ciblant des groupes AAD et attribuez-le à un ou plusieurs appareils HoloLens. 
1. Créer une configuration d’appareil basée sur un URI OMA personnalisée qui définit cette valeur de stratégie sur le nombre de jours souhaité (> 0) et de l’affecter à un ou plusieurs appareils HoloLens. 
    1. La valeur d’URI doit être entrée dans la zone de texte de l’URI OMA comme./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. La valeur peut être comprise entre min et max.
1. Inscrivez les appareils HoloLens et vérifiez que les deux configurations sont appliquées à l’appareil. 
1. Connexion de l’utilisateur AAD 1 Lorsque Internet est disponible, une fois que l’utilisateur se connecte et que l’appartenance au groupe AAD a été confirmée, le cache est créé. 
1. Désormais, l’utilisateur AAD 1 peut utiliser HoloLens hors connexion et l’utiliser pour le mode Kiosk tant que la valeur de la stratégie autorise un nombre de jours de X jours. 
1. Les étapes 4 et 5 peuvent être répétées pour tout autre utilisateur AAD N. point clé voici qu’aucun utilisateur AAD ne doit se connecter à l’appareil à l’aide d’Internet, et au moins une fois que nous pouvons déterminer qu’il est membre du groupe AAD dont la configuration Kiosk est ciblée. 
 
> [!NOTE]
> Jusqu’à ce que l’étape 4 soit effectuée pour un utilisateur AAD, il est possible de bénéficier d’un comportement d’échec indiqué ci-dessous dans les environnements «déconnecté». 

### Nouvelles stratégies de restriction d’appareil pour HoloLens 2
Stratégies récemment activées qui autorisent davantage d’options de gestion des appareils HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone) 

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

### Stratégies de mise à jour récemment activées HoloLens
Ces stratégies de mise à jour sont désormais activées sur les appareils HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### Visibilité de la page de paramètres activée pour HoloLens 2
Nous avons à présent activé une stratégie qui permet aux administrateurs informatiques d’empêcher les pages spécifiques de l’application Paramètres système d’être visibles ou accessibles, ou de le faire pour toutes les pages à l’exception de celles spécifiées. Pour savoir comment personnaliser entièrement cette fonctionnalité, cliquez sur le lien ci-dessous.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![Capture d’heures d’activité modifiées dans l’application paramètres](images/hololens-page-visibility-list.jpg)

### Accès global affecté – mode plein écran
Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode kiosque de plusieurs applications, qui est applicable au niveau du système, sans affinité avec aucune identité sur le système et qui s’applique à toutes les personnes qui se connectent à l’appareil. Pour en savoir [plus, consultez](hololens-global-assigned-access-kiosk.md)cette nouvelle fonctionnalité.

### Lancement automatique d’une application dans le mode Kiosk à plusieurs applications 
S’applique uniquement au mode Kiosk multi-App et seule une application peut être désignée pour le lancement automatique à l’aide de l’attribut en surbrillance ci-dessous dans la configuration Access attribuée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Modification du comportement du mode plein écran pour la gestion des échecs

Auparavant lors de la mise en application du mode plein écran, HoloLens est utilisé pour afficher toutes les applications dans le menu Démarrer. À partir de cette version de Windows Insider, en cas d’échecs, aucune application ne s’affichera dans le menu Démarrer comme suit: 

![Image illustrant l’affichage du mode plein écran lors d’une panne.](images/hololens-kiosk-failure-behavior.png )

## Commencer à recevoir les builds Insider

> [!NOTE]
> Si vous n’avez pas effectué de mise à jour récemment, redémarrez votre appareil pour mettre à jour l’État et obtenir la dernière version.
> - La commande vocale «redémarrage de l’appareil» fonctionne bien. 
> - Vous pouvez également choisir le bouton redémarrer dans paramètres/programme Windows Insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez rencontré et c’est en retour.

Sur un appareil HoloLens 2, accédez à **paramètres**  >  **mise à jour &**  >  **programme Windows Insider** Security et sélectionnez **commencer**. Liez le compte que vous avez utilisé pour vous inscrire au programme Windows Insider.

Ensuite, sélectionnez **développement actif de Windows**, choisissez si vous souhaitez recevoir les builds de **canaux de développement** ou de **canaux bêta** , puis passez en revue les termes du programme.

Sélectionnez **confirmer > redémarrer maintenant** pour terminer. Après le redémarrage de votre appareil, accédez à **paramètres > mettre à jour & sécurité > Rechercher les mises à jour** pour obtenir la dernière version.

## FFU télécharger et clignoter
Pour tester la version d’évaluation d’un FFU, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU.
1. Sur PC:

    1. Téléchargez FFU sur votre PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installez ARC (Advanced Recovery Companion) à partir du Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. Sur HoloLens-version de déverrouillage **Settings**: Ouvrez la  >  **mise à jour des paramètres &**  >  **programme Windows Insider** Security et inscrivez-vous, puis redémarrez l’appareil.

1. Flash FFU-désormais, vous pouvez faire clignoter le FFU signé par ARC.

## Faire part de vos commentaires et signaler des problèmes

Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour formuler des commentaires et signaler des problèmes. Le hub de commentaires vous permet de vous assurer que toutes les informations de diagnostic nécessaires sont incluses pour faciliter le débogage et le résolution rapide du problème.  Des problèmes liés à la version chinois et japonais de HoloLens doivent être signalés de la même manière.

> [!NOTE]
> Assurez-vous d’accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).

## Remarque pour les développeurs

Vous êtes heureux et encouragé à essayer de développer vos applications à l’aide des builds Insider de HoloLens.  Consultez la [documentation pour développeurs HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds Insider d’HoloLens.  Vous pouvez utiliser les mêmes builds Unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.

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
