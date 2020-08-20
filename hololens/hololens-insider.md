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
ms.openlocfilehash: 1e6b8fcfad1dab49823f38c722de33654b361f58
ms.sourcegitcommit: 16d61083a1da8007278aed7e11eb6d44f7a90952
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941686"
---
# Insider Preview pour MicrosoftHoloLens

Bienvenue dans la dernière build Insider Preview pour HoloLens. Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) utiles pour notre prochaine mise à jour du système d’exploitation pour HoloLens.

## Notes de publication de Windows Insider

Vous trouverez ci-dessous la liste des fonctionnalités à venir que vous pouvez tester dès aujourd’hui dans la version Windows Insider.

| Fonctionnalité                                                | Description                                                                                    | Disponible dans les builds Insider |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [Prise en charge de la position de l’oeil automatique](hololens-insider.md#auto-eye-position-support)                              | Trouve activement les positions visuelles et permet un positionnement précis des hologrammes.                        | 19041.1339 +                 |
| [Afficheur de certificats](hololens-insider.md#certificate-viewer)                                     | Affichez les certificats d’utilisateur et d’appareil dans l’application paramètres.                                         | 19041.1346 +                 |
| [Installation et suppression de certificats](hololens-insider.md#install-and-remove-certificates)                        | Les utilisateurs peuvent installer et supprimer des certificats à l’aide de l’observateur de certificats.                        | 19041.1361 +                 |
| [Mise en service du lancement automatique à partir d’USB](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE détecte automatiquement les packages de mise en service sur les lecteurs USB.                                | 19041.1361 +                 |
| [Vérifier automatiquement les packages de mise en service dans OOBE](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | Appliquer automatiquement les packages de mise en service dans OOBE.                                             | 19041.1361 +                 |
| [Utilisation du pilotage automatique avec la connexion Wi-Fi](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | Utilisez AutoPilot depuis un Wi-Fi sans avoir besoin d’une carte Ethernet.                             | 19041.1364 +                 |
|[FSC Tenantlockdown et Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | Après l’inscription au client et si le Policiy est appliqué, l’appareil ne peut être inscrit à ce client qu’à chaque réinitialisation ou réactivation de l’appareil. | 19041.1366 +|
| [Accès global affecté](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | Configurer l’appareil HoloLens 2 pour le mode kiosque de plusieurs applications, applicable au niveau du système. | 19041.1356 +                 |
| [Lancement automatique d’une application dans Kiosk multi-App](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | Définit une application pour qu’elle s’ouvre automatiquement lors de la connexion au mode plein écran à plusieurs applications.     | 19041.1346 +                 |
| [Connexion automatique de visiteur pour les bornes](hololens-insider.md#visitor-auto-logon-for-kiosks)                          | Autorise l’utilisation de la connexion automatique sur les comptes de visiteur pour les modes Kiosk.                         | 19041.1361 +                 |
| [Modification du comportement du mode plein écran pour la gestion des échecs](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Modification de la façon dont l’échec du mode plein écran est désormais géré.                                              | 19041.1356 +                 |
| [Stratégies HoloLens](hololens-insider.md#hololens-policies)                                      | Nouvelles stratégies pour les appareils de réalité mixte.                                                        | 19041.1349 +                 |
| [Mise en cache de l’appartenance aux groupes AAD pour Kiosk hors connexion](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | Politique pour le nombre de jours pendant lesquels le cache d’appartenance au groupe AAD est autorisé à utiliser le mode plein écran.    | 19041.1356 +                 |
| [Nouvelles stratégies de restriction d’appareil pour HoloLens 2](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | Les stratégies de gestion des appareils activées pour HoloLens 2 sont activées.                               | 19041.1349 +                 |
| [Nouvelles stratégies d’alimentation pour HoloLens 2](hololens-insider.md#new-power-policies-for-hololens-2)                      | Stratégies récemment prises en charge pour les paramètres de délai d’alimentation.                                           | 19041.1349 +                 |
| [Stratégies de mise à jour](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | Stratégies récemment activées permettant le contrôle des mises à jour.                                            | 19041.1352 +                 |
| [Visibilité de la page de paramètres activée pour HoloLens 2](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | Stratégie pour sélectionner les pages qui apparaissent dans l’application paramètres.                                           | 19041.1349 +                 |
| [Améliorations et correctifs de la mise à jour](hololens-insider.md#improvements-and-fixes-in-the-update)                   | Autres correctifs de la mise à jour.                                                                | 19041.1361 +                 |

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

Dans Windows Insider Build 19041.1346 +, nous ajoutons un afficheur de certificats à l’application paramètres HoloLens 2. Le certificat installation prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent être installés que dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

-   **Audit:** Possibilité de vérifier que le déploiement d’un certificat est correct ou qu’il a été supprimé de manière appropriée. 
-   **Diagnostic:** En cas de problème, le fait de vérifier que les certificats appropriés existent sur l’appareil permet de gagner du temps et d’aider à résoudre les problèmes. 
-   **Validation:** Le fait de vérifier que le certificat a la finalité prévue et qu’il est fonctionnel, peut faire gagner du temps, en particulier dans les environnements commerciaux avant de déployer des certificats à plus grande échelle.

Pour afficher les certificats, accédez à **paramètres > mettre à jour & certificats de sécurité >**.

![Afficheur de certificats dans l’application paramètres](images/certificate-viewer-device.jpg)

### Installation et suppression de certificats
À partir de Windows Insider version 19041.1361 +, vous pouvez installer et supprimer des certificats directement sur HoloLens 2 via l’application paramètres. Le certificat installation prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent être installés que dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

#### Pour installer un certificat à l’aide de l’observateur de certificats: 
1. Accédez à **paramètres**de  ->  **mise à jour de l’application et**  ->  **certificats**de sécurité, puis sélectionnez **installer un certificat**. 
1. Sélectionnez un fichier. cer dans l’interface du sélecteur de fichiers.
1. Sélectionnez ordinateur local (ou votre certificat).
1. Sélectionnez **racine** en tant que magasin de certificats (ou quel magasin vous voulez placer votre certificat). 
1. Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

#### Pour supprimer un certificat à l’aide de l’observateur de certificats: 
1. Accédez à **paramètres**de  ->  **mise à jour de l’application et**  ->  **certificats**de sécurité.
1. Recherchez le certificat par nom dans la zone de recherche.
1. Cliquez sur le certificat.
1. Cliquez sur **supprimer** .
1. Sélectionnez Oui lorsque vous y êtes invité, puis, lorsque vous êtes invité à confirmer.

![Image illustrant l’utilisation de l’interface utilisateur de certificats pour l’installation d’un certificat](images/certificate-device-install.jpg)

#### Problèmes connus 
Dans le cadre de la sélection d’un certificat dans le sélecteur de fichiers, l’interface utilisateur de la boîte de dialogue d’installation ne montre pas le fichier de certificat sélectionné, même si elle a été sélectionnée. Après avoir sélectionné le fichier, vous pouvez poursuivre l’installation même si le fichier n’apparaît pas dans la boîte de dialogue. 

### Mise en service du lancement automatique à partir d’USB
Avant cela, les utilisateurs devaient lancer l’écran de mise en service manuellement lors de la mise en service à l’aide d’une combinaison de boutons. Les utilisateurs peuvent désormais ignorer la combinaison de boutons à l’aide d’un package de mise en service sur un lecteur de stockage USB. 

1. Brancher le lecteur USB avec le package de mise en service lors du premier moment de l’interaction de OOBE
1. Lorsque l’appareil est prêt à être approvisionné, il ouvre automatiquement l’invite à l’aide de la page de configuration. 

Remarque: Si vous laissez un lecteur USB branché dans le cadre du démarrage de l’appareil, l’interface OOBE recense le périphérique de stockage USB existant, ainsi que les éléments supplémentaires connectés.

Pour plus d’informations sur l’application des packages de mise en service lors de la configuration de OOBE, continuez à lire [ici](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Vérifier automatiquement les packages de mise en service dans OOBE
Lorsque l’écran principal de mise en service s’affiche, OOBE compte 10 secondes avant de commencer à appliquer automatiquement tous les packages de mise en service. Les utilisateurs peuvent toujours confirmer ou annuler dans les 10 secondes qui suivent la vérification des packages attendus.

### Configuration automatique sans utiliser d’interface utilisateur
En associant le lancement automatique de la mise en service à partir d’appareils USB et la confirmation automatique des packages de mise en service, un utilisateur peut configurer automatiquement les appareils HoloLens 2 sans utiliser l’interface utilisateur de l’appareil, ni ne porter le périphérique. Vous pouvez continuer à utiliser le même pilote USB et le même package de mise en service pour plusieurs appareils. Cela s’avère utile pour le déploiement de plusieurs appareils à la fois dans la même zone. 

1. [Créer un package de mise à service](hololens-provisioning.md) à l’aide du [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiez le package sur un lecteur de stockage USB.
1. [Flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) vers [19041,1361 ou version ultérieure](https://aka.ms/hololens2previewdownload). 
1. Lorsque le [compagnon de récupération avancée](https://www.microsoft.com/store/productId/9P74Z35SFRS8) clignote sur votre appareil, débranchez votre câble USB-C. 
1. Branchez votre lecteur USB sur le périphérique.
1. Lors du démarrage de l’appareil HoloLens 2 dans OOBE, le package de mise en service sera automatiquement détecté sur le lecteur USB et lancera la page de configuration.
1. Après 10 secondes, l’appareil applique automatiquement le package de mise en service. 

Votre appareil est désormais configuré et affiche l’écran de mise en service réussi.

### Utilisation du pilotage automatique avec la connexion Wi-Fi
À présent, lorsque vous connectez HoloLens 2 avec WiFi, OOBE vérifie s’il y a un profil AutoPilot pour l’appareil. S’il en existe une, il sera utilisé pour effectuer la partie restante du flux d’inscription AAD. En d’autres termes, l’utilisation d’une carte Ethernet vers une carte USB c ou WiFi vers la carte USB C n’est plus obligatoire, mais elle continue de fonctionner au début de OOBE. En savoir plus sur le [pilotage automatique pour les appareils HoloLens 2](hololens2-autopilot.md).

### FSC Tenantlockdown et Autopilot
Les appareils HoloLens 2 prennent désormais en charge le fournisseur de services de TenantLockdown à partir de Windows Insider Build 19041.1366 +. 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) Le fournisseur de services cryptographiques permet à HoloLens 2 d’être lié à l’inscription de la gestion des périphériques mobiles à l’aide du pilotage automatique uniquement. Lorsque le nœud RequireNetworkInOOBE du fournisseur de services de TenantLockdown est défini sur true ou false (défini initialement) sur HoloLens 2, cette valeur reste sur l’appareil malgré le réclignotement, les mises à jour du système d’exploitation, etc. 

Lorsque le nœud RequireNetworkInOOBE des fournisseurs de services de TenantLockdown est défini sur true sur HoloLens 2, OOBE attend indéfiniment pour le téléchargement et l’application du profil AutoPilot après une connectivité réseau. 

Lorsque le nœud RequireNetworkInOOBE des fournisseurs de services de TenantLockdown est défini sur true sur HoloLens 2, les opérations suivantes ne sont pas autorisées dans OOBE: 
- Création d’un utilisateur local à l’aide de la configuration du Runtime 
- Exécution d’une opération de jointure AAD via la mise en service de l’exécution 
- Sélectionner le propriétaire de l’appareil dans l’interface OOBE 

#### Comment définir cette configuration à l’aide de Intune? 
1. Créez un profil personnalisé de configuration de l’appareil d’URI OMA et spécifiez true pour le nœud RequireNetworkInOOBE, comme illustré ci-dessous.
La valeur d’URI OMA doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE ![ paramètre du client Lockdown via OMA-URI](images/hololens-tenant-lockdown.png)
1. Créez un groupe et attribuez-lui le profil de configuration de l’appareil. 
1. Définissez le membre du périphérique HoloLens 2 du groupe créé lors de l’étape précédente et déclenchez la synchronisation.  

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois que la configuration de l’appareil Hololens 2 s’applique correctement, les effets de TenantLockdown seront actifs.

#### Comment inverser les RequireNetworkInOOBE de TenantLockdown sur HoloLens 2 avec Intune? 
1. Supprimez le HoloLens 2 du groupe de périphériques sur lequel est précédemment attribuée la configuration de l’appareil créée ci-dessus. 
1. Créez un profil personnalisé de configuration d’appareil d’URI OMA et spécifiez la valeur false pour RequireNetworkInOOBE, comme illustré ci-dessous. La valeur de l’URI-URL devrait être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE ![ capture d’écran de la définition de RequireNetworkInOOBE sur false via un URI OMA dans Intune](images/hololens-tenant-lockdown-false.png)
1. Créez un groupe et attribuez-lui le profil de configuration de l’appareil. 
1. Définissez le membre du périphérique HoloLens 2 du groupe créé lors de l’étape précédente et déclenchez la synchronisation.

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois la configuration de l’appareil Hololens 2 appliquée, les effets de TenantLockdown seront désactivés. 

#### Que se passe-t-il lors de l’installation de OOBE, si le profil de pilote automatique n’est pas affecté sur un HoloLens après la définition de TenantLockdown. 
OOBE attend indéfiniment du profil AutoPilot pour le téléchargement et la présentation de la boîte de dialogue qui s’affiche. Pour supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit au client d’origine à l’aide du pilotage automatique uniquement et RequireNetworkInOOBE doit être désactivé comme décrit dans l’étape précédente avant la suppression des restrictions introduites par le fournisseur de services de TenantLockdown. 

![Dans l’affichage du périphérique, lorsque la stratégie est appliquée à l’appareil.](images/hololens-autopilot-lockdown.png)

### Accès global affecté – mode plein écran
Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode kiosque de plusieurs applications, qui est applicable au niveau du système, sans affinité avec aucune identité sur le système et qui s’applique à toutes les personnes qui se connectent à l’appareil. Pour en savoir [plus, consultez](hololens-global-assigned-access-kiosk.md)cette nouvelle fonctionnalité.

### Lancement automatique d’une application dans le mode Kiosk à plusieurs applications 
S’applique uniquement au mode Kiosk multi-App et seule une application peut être désignée pour le lancement automatique à l’aide de l’attribut en surbrillance ci-dessous dans la configuration Access attribuée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Connexion automatique de visiteur pour les bornes
Cette nouvelle fonctionnalité permet d’utiliser l’ouverture de session automatique sur les comptes de visiteur pour les modes Kiosk. 

Pour une configuration non-AAD, pour configurer un appareil pour le logo automatique de visiteur:
1.  Créez un package de mise à service qui:
    1.  Configure les **paramètres d’exécution/AssignedAccess** pour autoriser les comptes de visiteur.
    1.  Si vous le souhaitez, vous pouvez inscrire l’appareil dans la gestion des périphériques mobiles **(paramètres d’exécution/lieu de travail/inscriptions)** afin qu’il puisse être géré par la suite.
    1.  Ne pas créer de compte local
1.  [Appliquez le package de mise en service](hololens-provisioning.md).

Dans le cas d’une configuration AAD, les utilisateurs peuvent obtenir un aspect similaire à celui-ci aujourd’hui sans cette modification. Les appareils joints AAD configurés pour le mode kiosque peuvent se connecter à un compte visiteur avec un seul bouton à partir de l’écran de connexion. Lorsque vous êtes connecté au compte du visiteur, l’appareil ne demande pas de connexion tant qu’il n’a pas été explicitement déconnecté du menu Démarrer ou que l’appareil est redémarré.

### Modification du comportement du mode plein écran pour la gestion des échecs

Auparavant lors de la mise en application du mode plein écran, HoloLens est utilisé pour afficher toutes les applications dans le menu Démarrer. À partir de cette version de Windows Insider, en cas d’échecs, aucune application ne s’affichera dans le menu Démarrer comme suit: 

![Image illustrant l’affichage du mode plein écran lors d’une panne.](images/hololens-kiosk-failure-behavior.png )

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
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

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

### Améliorations et correctifs de la mise à jour:
- Stratégie mise à jour pour désactiver l’énumération des fonctions USB via la gestion des périphériques mobiles (GPM) pour NCM pour AllowUsbConnection.
- D’autres écrans dans OOBE sont désormais en mode sombre.
- En savoir plus sur le contenu doit pointer vers la dernière déclaration de confidentialité en ligne.
- Résolu et problème dans lequel les utilisateurs ne pouvaient pas approvisionner des profils VPN via les packages de mise en service.

## Commencer à recevoir les builds Insider

> [!NOTE]
> Si vous n’avez pas effectué de mise à jour récemment, redémarrez votre appareil pour mettre à jour l’État et obtenir la dernière version.
> - La commande vocale «redémarrage de l’appareil» fonctionne bien. 
> - Vous pouvez également choisir le bouton redémarrer dans paramètres/programme Windows Insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez rencontré et c’est en retour.

Sur un appareil HoloLens 2, accédez à **paramètres**  >  **mise à jour &**  >  **programme Windows Insider** Security et sélectionnez **commencer**. Liez le compte que vous avez utilisé pour vous inscrire au programme Windows Insider.

Windows Insider se déplace désormais vers les canaux. Le sonne **rapide** devient le **canal de développement**, la sonnerie **lente** devient le **canal bêta**et la sonnerie de la version d' **évaluation** devient le **canal de publication**. Voici à quoi ressemble le mappage:

![Explication des canaux Windows Insider](images/WindowsInsiderChannels.png)

Pour plus d’informations, consultez [Présentation des canaux Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur les blogs Windows.

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
