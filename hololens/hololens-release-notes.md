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
ms.date: 10/13/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 0825e3fd2d0a4e6328eaa617e4233639f481e8cb
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163152"
---
# Notes de publication HoloLens 2

Pour vous assurer que vous disposez d’une satisfaction productive sur vos appareils HoloLens, nous continuons à libérer les mises à jour de fonctionnalités, de bogues et de sécurité. Sur cette page, vous pouvez voir les nouveautés du HoloLens par mois. Pour obtenir la dernière mise à jour du flash HoloLens 2 (FFU [), vous pouvez la](hololens-recovery.md#clean-reflash-the-device) [Télécharger ici](https://aka.ms/hololens2download). Le téléchargement est mis à jour et fournit la version la plus récente disponible en général.

>[!NOTE]
> Pour lire les notes de publication de HoloLens Emulator, [consultez l’archive](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holographique, version 20H2
- Version 19041,1128

Windows holographique, version 20H2 est désormais disponible et propose un ensemble de nouvelles fonctionnalités aux utilisateurs de HoloLens 2 et aux professionnels de l’informatique. Du positionnement de l’œil automatique, au gestionnaire de certificats dans les paramètres, à la fonctionnalité de mode plein écran et aux nouvelles fonctionnalités de configuration du pilotage automatique. Cette nouvelle mise à jour permet aux équipes informatiques de disposer d’un contrôle plus précis sur la configuration et la gestion des appareils HoloLens et offre aux utilisateurs une expérience holographique plus transparente. 

Cette dernière version est une mise à jour mensuelle de la version 2004, mais cette fois-ci, nous avons inclus de nouvelles fonctionnalités. Le numéro principal de la version reste le même et Windows Update indique une version mensuelle de la version 2004 (Build 19041). Pour vérifier que vous disposez de la dernière version disponible, vous pouvez examiner le numéro de build que vous avez > écran pour vérifier que vous disposez de la dernière version 19041.1128 +. Pour effectuer une mise à jour vers la dernière version, ouvrez l’application paramètres, accédez à mettre à jour & sécurité, puis appuyez sur Rechercher les mises à jour. Pour plus d’informations sur la gestion des mises à jour de HoloLens, consultez [cette page](https://docs.microsoft.com/hololens/hololens-updates).

### Nouveautés de Windows holographique, version 20H2  

| Fonctionnalité                                              | Description                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Prise en charge de la position de l’oeil automatique](hololens-release-notes.md#auto-eye-position-support) | Calcule activement les positions visuelles sans qu’ils passent par le calibrage actif.   |
| [Gestionnaire de certificats](hololens-release-notes.md#certificate-manager)   | Permet aux nouvelles méthodes simples d’installer et de supprimer des certificats de l’application paramètres.     |
| [Mise en service du lancement automatique à partir d’USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Les packages de mise en service sur les lecteurs USB invitent automatiquement la page de configuration dans OOBE.                                                         |
| [Vérifier automatiquement les packages de mise en service dans OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Les packages de mise en service sont automatiquement appliqués lors de la création de la page de configuration.                                                         |
| [Configuration automatique sans utiliser d’interface utilisateur](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Comment combiner le lancement automatique de la mise en service et la vérification automatique. |
| [Utilisation du pilotage automatique avec la connexion Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Utiliser AutoPilot à partir d’un Wi-Fi d’appareil sans avoir besoin d’une carte Ethernet. |
| [FSC Tenantlockdown et Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Après l’inscription du client et la stratégie appliquée, l’appareil ne peut être inscrit qu’à ce client à chaque réinitialisation ou réactivation de l’appareil. |
| [Accès global affecté](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nouvelle méthode de configuration pour le mode kiosque de plusieurs applications qui applique la Kiosk au niveau du système, et le rend applicable partout.                  |
| [Lancement automatique d’une application dans Kiosk multi-App](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Définit une application pour qu’elle s’ouvre automatiquement lors de la connexion au mode plein écran à plusieurs applications.                                                        |
| [Modification du comportement du mode plein écran pour la gestion des échecs](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L’échec du mode plein écran comporte désormais une restriction de secours.                                                                                                |
| [Stratégies HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nouvelles stratégies pour HoloLens.     |
| [Mise en cache de l’appartenance aux groupes AAD pour Kiosk hors connexion](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | Une nouvelle stratégie permet aux utilisateurs d’utiliser le cache d’appartenance de groupe pour utiliser le mode plein écran pendant un nombre de jours défini.                                        |
| [Nouvelles stratégies de restriction d’appareil pour HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Les stratégies de gestion des appareils activées pour HoloLens 2 sont activées.                                                                                |
| [Nouvelles stratégies d’alimentation pour HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Stratégies récemment prises en charge pour les paramètres de délai d’alimentation.  |
| [Stratégies de mise à jour](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Stratégies récemment activées permettant le contrôle des mises à jour.           |
| [Visibilité de la page de paramètres activée pour HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Stratégie pour sélectionner les pages qui apparaissent dans l’application paramètres.             |
| [Mode recherche](hololens-release-notes.md#research-mode) | Utiliser le mode recherche sur HoloLens 2. |
| [Durée d’enregistrement accrue](hololens-release-notes.md#recording-length-increased) | Les enregistrements MRC n’ont plus de 5 minutes. |
| [Améliorations et correctifs de la mise à jour](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Autres correctifs de la mise à jour.   |

### Prise en charge de la position de l’oeil automatique

- Nous fournissons désormais une précision supérieure pour le positionnement des hologrammes grâce à la prise en charge automatique de la position des yeux pour une qualité d’affichage élevée et une meilleure qualité d’affichage. 

Dans HoloLens 2, les positions visuelles permettent un positionnement précis des hologrammes, une confort d’affichage confortable et une meilleure qualité d’affichage. Les positions visuelles sont calculées dans le résultat du suivi visuel. Toutefois, cela nécessite que chaque utilisateur passe par le calibrage du suivi visuel, même lorsque l’utilisation ne requiert pas d’entrée en regard.

La position de l' **oeil automatique (AEP)** permet à ces scénarios d’avoir une méthode d’interaction sans interaction pour calculer la position des yeux de l’utilisateur.  La position de l’oeil automatique commence automatiquement à fonctionner en arrière-plan à partir du moment où l’utilisateur place le périphérique. Si l’utilisateur ne dispose pas d’un étalonnage de suivi d’oeil antérieur, la position d’oeil automatique commencera à fournir à l’oeil de l’utilisateur le système d’affichage après un temps de traitement faible. Ce temps de traitement est généralement compris entre 20-60 secondes. Les données de l’utilisateur ne sont pas conservées sur l’appareil et, de ce fait, le processus est répété s’il est mis en place par l’utilisateur, ou si l’appareil est redémarré ou s’arrête de sortir du mode veille.  

Il existe certaines modifications de comportement système avec la fonctionnalité de position de l’oeil automatique quand un utilisateur non calibré le place sur l’appareil. Un utilisateur sans calibrage fait référence à une personne qui n’a pas encore parcouru le processus d’étalonnage du suivi visuel sur l’appareil.

|     Application active                           |     Ancien comportement                                   |     Comportement de la version holographique Windows 20H2                                                     |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     Application et interpréteur holographique non activé    |     Invite de calibration du suivi d’oeil s’affiche.    |     Aucune invite ne s’affiche.                                                                                |
|     Application en option                             |     Invite de calibration du suivi d’oeil s’affiche.    |     L’invite de calibration du suivi d’oeil s’affiche uniquement lorsque l’application accède à un flux d’oeil.     |

 Si l’utilisateur passe d’une application à l’autre qui accède aux données de pointage, l’invite s’affiche. Il n’y a aucun changement de flux d’expérimentation hors champ. 
 
Dans le cas d’expériences nécessitant des informations visuelles ou un positionnement très précis, nous vous recommandons d’effectuer un étalonnage du suivi visuel à partir de l’invite d’étalonnage du suivi d’oeil ou en lançant l’application paramètres à partir du menu Démarrer, puis en sélectionnant **système > calibration >** d’étalonnage > d’exécution.

Pour plus d' [informations](hololens-calibration.md#auto-eye-position-support), consultez les informations suivantes. 

### Gestionnaire de certificats

- Amélioration de l’audit, du diagnostic et de l’outil de validation pour la sécurité et la conformité des périphériques via le nouveau gestionnaire de certificats. Cette fonctionnalité vous permet de déployer, de résoudre les problèmes et de valider vos certificats à des fins d’évolution en environnement commercial.

Dans Windows holographique version 20H2, nous ajoutons un gestionnaire de certificats à l’application paramètres HoloLens 2. Accédez à **paramètres > mettre à jour & certificats de sécurité >**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir la sécurité et la conformité des appareils. 

-   **Audit:** Possibilité de vérifier que le déploiement d’un certificat est correct ou qu’il a été supprimé de manière appropriée. 
-   **Diagnostic:** En cas de problème, le fait de vérifier que les certificats appropriés existent sur l’appareil permet de gagner du temps et d’aider à résoudre les problèmes. 
-   **Validation:** Le fait de vérifier qu’un certificat répond à la finalité prévue et est opérationnel, peut faire gagner du temps, en particulier dans les environnements commerciaux avant de déployer des certificats à des fins d’évolution plus importantes.

Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher les propriétés de chaque certificat, sélectionnez le certificat, puis cliquez sur **informations**. 

Le certificat installation prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent être installés que dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

#### Pour installer un certificat: 

1.  Connectez votre HoloLens 2 à un PC.
1.  Sur votre HoloLens 2, placez le fichier de certificat que vous voulez installer.
1.  Accédez à **paramètres de l’application > mettre à jour & sécurité > certificats**et sélectionnez Installer un certificat.
1.  Cliquez sur **importer le fichier** , puis accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **emplacement du magasin**.
1.  Sélectionnez **magasin de certificats**.
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

#### Pour supprimer un certificat: 
1. Accédez à **paramètres d’application de paramètres > de mise à jour et de sécurité > certificats**.
1. Recherchez le certificat par nom dans la zone de recherche.
1. Cliquez sur le certificat.
1. Cliquez sur **supprimer** .
1. Sélectionnez **Oui** lorsque vous êtes invité à confirmer.

![Afficheur de certificats dans l’application paramètres](images/certificate-viewer-device.jpg)

![Image illustrant l’utilisation de l’interface utilisateur de certificats pour l’installation d’un certificat](images/certificate-device-install.jpg)

Pour plus d’informations, reportez-vous [à la page de gestion des certificats](certificate-manager.md).

### Mise en service du lancement automatique à partir d’USB

- Processus automatisés autorisant moins d’interactions utilisateur, lorsque les lecteurs USB avec des packages de mise en service sont utilisés au cours de l’utilisation de la fonction OOBE.

Pour pouvoir lancer l’affichage de l’écran de mise en service manuellement lors de la mise en service de l’utilisation d’une combinaison de boutons Les utilisateurs peuvent désormais ignorer la combinaison de boutons à l’aide d’un package de mise en service sur un lecteur de stockage USB. 

1. Brancher le lecteur USB avec le package de mise en service lors du premier moment de l’interaction de OOBE
1. Lorsque l’appareil est prêt à être approvisionné, il ouvre automatiquement l’invite à l’aide de la page de configuration. 

Remarque: Si vous laissez un lecteur USB branché dans le cadre du démarrage de l’appareil, l’interface OOBE recense le périphérique de stockage USB existant, ainsi que les éléments supplémentaires connectés.

Pour plus d’informations sur l’application des packages de mise en service lors de la configuration de OOBE, continuez à lire [ici](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

Pour plus d’informations, consultez cette [page.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### Vérifier automatiquement les packages de mise en service dans OOBE
- Processus automatisé permettant d’avoir moins d’interactions avec l’utilisateur, lorsque la page package de mise en service s’affiche, il applique automatiquement tous les packages répertoriés.

Lorsque l’écran principal de mise en service s’affiche, OOBE compte 10 secondes avant de commencer à appliquer automatiquement tous les packages de mise en service. Les utilisateurs peuvent toujours confirmer ou annuler dans les 10 secondes qui suivent la vérification des packages attendus.

Pour plus d’informations, consultez cette [page.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### Configuration automatique sans utiliser d’interface utilisateur
- Processus automatiques combinés pour réduire les interactions d’appareil pour la mise en service. 

En associant le lancement automatique de la mise en service à partir d’appareils USB et la confirmation automatique des packages de mise en service, un utilisateur peut configurer automatiquement les appareils HoloLens 2 sans utiliser l’interface utilisateur de l’appareil, ni ne porter le périphérique. Vous pouvez continuer à utiliser le même pilote USB et le même package de mise en service pour plusieurs appareils. Cela s’avère utile pour le déploiement de plusieurs appareils à la fois dans la même zone. 

1. [Créer un package de mise à service](hololens-provisioning.md) à l’aide du [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiez le package sur un lecteur de stockage USB.
1. [Flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) vers [19041,1361 ou version ultérieure](https://aka.ms/hololens2previewdownload). 
1. Lorsque le [compagnon de récupération avancée](https://www.microsoft.com/store/productId/9P74Z35SFRS8) clignote sur votre appareil, débranchez votre câble USB-C. 
1. Branchez votre lecteur USB sur le périphérique.
1. Lors du démarrage de l’appareil HoloLens 2 dans OOBE, le package de mise en service sera automatiquement détecté sur le lecteur USB et lancera la page de configuration.
1. Après 10 secondes, l’appareil applique automatiquement le package de mise en service. 

Votre appareil est désormais configuré et affiche l’écran de mise en service réussi.

Pour plus d’informations, consultez cette [page.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Utilisation du pilotage automatique avec la connexion Wi-Fi
- Suppression requise pour les adaptateurs USB-C vers Ethernet qui allège les besoins en matériel, en permettant le fonctionnement automatique du pilotage sur Wi-Fi les appareils connectés.

À présent, lorsque vous connectez HoloLens 2 avec WiFi, OOBE vérifie s’il y a un profil AutoPilot pour l’appareil. S’il en existe une, il sera utilisé pour effectuer la partie restante du flux d’inscription AAD. En d’autres termes, l’utilisation d’une carte Ethernet vers une carte USB-C ou Wi-Fi vers la carte USB-C n’est plus nécessaire, mais elle continue de fonctionner si elle est fournie au début de OOBE. En savoir plus sur le [pilotage automatique pour les appareils HoloLens 2](hololens2-autopilot.md).

### FSC Tenantlockdown et Autopilot
- Conserve les appareils sur le client de l’organisation en les verrouillant vers le client même via la réinitialisation ou le redémarrage de l’appareil. Renforcez la sécurité en autorisant la création de comptes via la mise en service. 

Les appareils HoloLens 2 prennent désormais en charge le fournisseur de services de TenantLockdown à partir de la [version holographique de Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) Le fournisseur de services cryptographiques permet à HoloLens 2 d’être lié à l’inscription de la gestion des périphériques mobiles à l’aide du pilotage automatique uniquement. Lorsque le nœud RequireNetworkInOOBE du fournisseur de services de TenantLockdown est défini sur true ou false (défini initialement) sur HoloLens 2, cette valeur reste sur l’appareil malgré le réclignotement, les mises à jour du système d’exploitation, etc. 

Lorsque le nœud RequireNetworkInOOBE des fournisseurs de services de TenantLockdown est défini sur true sur HoloLens 2, OOBE attend indéfiniment pour le téléchargement et l’application du profil AutoPilot après une connectivité réseau. 

Lorsque le nœud RequireNetworkInOOBE des fournisseurs de services de TenantLockdown est défini sur true sur HoloLens 2, les opérations suivantes ne sont pas autorisées dans OOBE: 
- Création d’un utilisateur local à l’aide de la configuration du Runtime 
- Exécution d’une opération de jointure AAD via la mise en service de l’exécution 
- Sélectionner le propriétaire de l’appareil dans l’interface OOBE 

#### Comment définir cette configuration à l’aide de Intune? 
1. Créez un profil personnalisé de configuration de l’appareil d’URI OMA et spécifiez true pour le nœud RequireNetworkInOOBE, comme illustré ci-dessous.
La valeur d’URI OMA doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuration de du client Lockdown via OMA-URI](images/hololens-tenant-lockdown.png)

1. Créez un groupe et attribuez-lui le profil de configuration de l’appareil. 

1. Définissez le membre du périphérique HoloLens 2 du groupe créé lors de l’étape précédente et déclenchez la synchronisation.  

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois que la configuration de l’appareil Hololens 2 s’applique correctement, les effets de TenantLockdown seront actifs.

#### Comment inverser les RequireNetworkInOOBE de TenantLockdown sur HoloLens 2 avec Intune? 
1. Supprimez le HoloLens 2 du groupe de périphériques sur lequel est précédemment attribuée la configuration de l’appareil créée ci-dessus. 

1. Créez un profil personnalisé de configuration d’appareil d’URI OMA et spécifiez la valeur false pour RequireNetworkInOOBE, comme illustré ci-dessous. La valeur d’URI OMA doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de la définition de RequireNetworkInOOBE sur false via un URI OMA dans Intune](images/hololens-tenant-lockdown-false.png)

1. Créez un groupe et attribuez-lui le profil de configuration de l’appareil. 

1. Définissez le membre du périphérique HoloLens 2 du groupe créé lors de l’étape précédente et déclenchez la synchronisation.

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois la configuration de l’appareil Hololens 2 appliquée, les effets de TenantLockdown seront désactivés. 

#### Que se passe-t-il lors de l’installation de OOBE, si le profil de pilote automatique n’est pas affecté sur un HoloLens après la définition de TenantLockdown. 
OOBE attend indéfiniment du profil AutoPilot pour le téléchargement et la présentation de la boîte de dialogue qui s’affiche. Pour supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit au client d’origine à l’aide du pilotage automatique uniquement et RequireNetworkInOOBE doit être désactivé comme décrit dans l’étape précédente avant la suppression des restrictions introduites par le fournisseur de services de TenantLockdown. 

![Dans l’affichage du périphérique, lorsque la stratégie est appliquée à l’appareil.](images/hololens-autopilot-lockdown.png)

Ces informations sont désormais disponibles en même temps que le reste du pilotage automatique sous [TENANTLOCKDOWN CSP et AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### Accès global affecté – mode plein écran
- Réduction de la gestion des identités pour Kiosk, en permettant la nouvelle méthode Kiosk qui applique le mode Kiosk au niveau du système.

Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode kiosque de plusieurs applications, qui est applicable au niveau du système, sans affinité avec aucune identité sur le système et qui s’applique à toutes les personnes qui se connectent à l’appareil. Pour en savoir [plus, consultez](hololens-global-assigned-access-kiosk.md)cette nouvelle fonctionnalité.

### Lancement automatique d’une application dans le mode Kiosk à plusieurs applications 
- Expérience prioritaire grâce au lancement automatique d’une application, ce qui a pour but d’améliorer les sélections de l’interface utilisateur et de l’application choisies en mode plein

S’applique uniquement au mode Kiosk multi-App et seule une application peut être désignée pour le lancement automatique à l’aide de l’attribut en surbrillance ci-dessous dans la configuration Access attribuée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Modification du comportement du mode plein écran pour la gestion des échecs
- Mode plein écran plus sécurisé en éliminant les problèmes d’application disponibles en mode plein écran. 

Auparavant lors de la mise en application du mode plein écran, HoloLens est utilisé pour afficher toutes les applications dans le menu Démarrer. À présent dans la version holographique de Windows 20H2 en cas d’échecs, aucune application ne s’affichera dans le menu Démarrer comme suit: 

![Image illustrant l’affichage du mode plein écran lors d’une panne.](images/hololens-kiosk-failure-behavior.png )

### Stratégies HoloLens
- Options de gestion des périphériques spécifiques pour HoloLens créées pour la gestion de l’appareil. 

De nouvelles stratégies de réalité mixte ont été créées pour les appareils HoloLens 2 sur Windows holographique version 20H2. Les nouveaux paramètres contrôleurs incluent: définir la luminosité, définir le volume et désactiver l’enregistrement audio dans les captures de réalité mixte, définir quand les diagnostics peuvent être collectés et cache d’appartenance de groupe AAD.  

| Nouvelle stratégie HoloLens                                | Description                                                                               | Remarques                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permet que les boutons de luminosité soient désactivés, ce qui permet de ne pas modifier la luminosité.       | 1 Oui, 0 (par défaut)                                                |
| MixedReality\VolumeButtonDisabled                  | Autorise la désactivation des boutons de volume et la pression sur celle-ci ne modifie pas le volume.               | 1 Oui, 0 (par défaut)                                                |
| MixedReality\MicrophoneDisabled                    | Désactive le microphone de sorte qu’aucun enregistrement audio ne soit possible sur HoloLens 2.                      | 1 Oui, 0 (par défaut)                                                |
| MixedReality\FallbackDiagnostics                   | Contrôle le comportement du moment où les journaux de diagnostic peuvent être collectés.                               | 0 désactivé, 1 activé pour les propriétaires d’appareils, 2 activés pour All (par défaut) |
| MixedReality\HeadTrackingMode                      | Réservé pour une utilisation ultérieure.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Détermine le nombre de jours d’appartenance au groupe AAD pour le ciblage des kiosques pour les groupes AAD. | Voir ci-dessous.                                                           |

### Mise en cache de l’appartenance aux groupes AAD pour Kiosk hors connexion
- Vous pouvez utiliser des bornes hors ligne pour un maximum de 60 jours.

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
> Jusqu’à ce que l’étape 4 soit exécutée pour un utilisateur AAD, il est possible de bénéficier du comportement d’échec mentionné dans les environnements «déconnectés». 

### Nouvelles stratégies de restriction d’appareil pour HoloLens 2
- Permet aux utilisateurs de gérer des stratégies de gestion des appareils spécifiques, telles que le blocage de l’ajout ou de la suppression des packages de mise en service.

Stratégies récemment activées qui autorisent davantage d’options de gestion des appareils HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Ces deux nouvelles politiques pour AllowAddProvisioningPackage et AllowRemoveProvisioningPackage sont ajoutées à nos restrictions d' [appareil courantes](hololens-common-device-restrictions.md).

### Nouvelles stratégies d’alimentation pour Hololens 2
- Plus d’options pour la mise en veille de l’HoloLens ou son verrouillage via une stratégie d’alimentation. 

Ces stratégies récemment ajoutées permettent aux administrateurs de contrôler les États d’alimentation tels que le délai d’inactivité. Pour en savoir plus sur chaque stratégie individuelle, cliquez sur le lien correspondant à cette stratégie.

|     Lien documentation de la stratégie                |     Remarques                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Exemple de valeur à utiliser dans le concepteur de configuration Windows, c’est-à-dire 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, c’est-à-dire 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Par exemple, la valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Ces deux nouvelles politiques pour DisplayOffTimeoutOnBattery et DisplayOffTimeoutPluggedIn sont ajoutées à nos restrictions d' [appareil courantes](hololens-common-device-restrictions.md).

> [!NOTE]
> Pour une interface cohérente sur HoloLens 2, assurez-vous que les valeurs pour DisplayOffTimeoutOnBattery et StandbyTimeoutOnBattery sont définies sur la même valeur. Il en va de même pour DisplayOffTimeoutPluggedIn et StandbyTimeoutPluggedIn. Pour plus d’informations sur l’utilisation du mode moderne, voir les [minuteurs d’affichage, de mise en veille et de mise en veille prolongée](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### Stratégies de mise à jour récemment activées HoloLens
- Autres options de lors de l’installation des mises à jour ou de désactivation du bouton suspendre les mises à jour pour garantir les mises à jour.

Ces stratégies de mise à jour sont désormais activées sur les appareils HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Pour plus d’informations sur ces stratégies de mise à jour et sur leur utilisation pour les appareils HoloLens, voir [gérer les mises à jour de hololens](hololens-updates.md).

### Visibilité de la page de paramètres activée pour HoloLens 2
- Amélioration du contrôle de l’interface utilisateur dans l’application paramètres, susceptible de ne pas afficher une sélection limitée de pages.

Nous avons à présent activé une stratégie qui permet aux administrateurs informatiques d’empêcher les pages spécifiques de l’application Paramètres système d’être visibles ou accessibles, ou de le faire pour toutes les pages à l’exception de celles spécifiées. Pour savoir comment personnaliser entièrement cette fonctionnalité, cliquez sur le lien ci-dessous.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Pour en savoir plus sur les paramètres de page que vous pouvez personnaliser sur HoloLens 2, consultez notre [page des URI de paramètres](settings-uri-list.md). 
 
![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

### Mode recherche
Dans le mode recherche, le HoloLens 2 devient un outil puissant pour la recherche de vision informatisée. Comparé aux éditions précédentes, le mode recherche pour HoloLens 2 offre les avantages suivants:
-   Outre les capteurs exposés au mode de recherche HoloLens (1ère génération), nous fournissons désormais un accès au capteur IMU, y compris un accéléromètre, un gyroscope et un magnétomètre.
-   HoloLens 2 fournit de nouvelles fonctionnalités qui peuvent être utilisées avec le mode recherche. Il s’agit plus précisément d’un accès aux API articulées en matière de suivi manuel et de suivi oculaire qui peuvent apporter un ensemble d’expériences plus riches.

Les chercheurs ont désormais la possibilité d’activer le mode de recherche sur leurs périphériques HoloLens pour accéder à l’ensemble des flux de capteurs d’images brutes externes. Le mode de recherche pour HoloLens 2 donne également accès aux lectures d’accéléromètre, de gyroscope et de magnétomètre. Pour protéger la confidentialité des utilisateurs, vous ne pouvez pas utiliser le mode recherche pour les images de l’appareil photo pour le suivi des yeux

Pour plus d’informations techniques, consultez la [documentation du mode de recherche](https://docs.microsoft.com/windows/mixed-reality/research-mode) .

### Durée d’enregistrement accrue
En raison des commentaires des clients, nous avons augmenté la durée d’enregistrement des [captures de réalité mélangées](holographic-photos-and-videos.md). Par défaut, les captures de réalité mixte ne seront plus limitées à 5 minutes, mais au lieu de calculer la longueur d’enregistrement maximale en fonction de l’espace disque disponible. L’appareil évalue la durée d’enregistrement vidéo maximale en fonction de l’espace disque disponible jusqu’à 80% du total de l’espace disque.

> [!NOTE]
> Le HoloLens utilisera une durée d’enregistrement vidéo par défaut (5 minutes) dans l’un des cas suivants:
> - La durée d’enregistrement maximale estimée est inférieure à la valeur par défaut de 5 minutes.
> - L’espace disque disponible est inférieur à 20% du total de l’espace disque.

Ces informations sont à nouveau accessibles [ici](holographic-photos-and-videos.md#maximum-recording-length). 

### Améliorations et correctifs de la mise à jour:
- D’autres écrans dans OOBE sont désormais en mode sombre.
- En savoir plus sur le contenu doit pointer vers la dernière déclaration de confidentialité en ligne.
- Nous avons résolu un problème dans lequel les utilisateurs ne pouvaient pas approvisionner des profils VPN via les packages de mise en service.
- Correction d’un problème de configuration de proxy pour une connexion VPN.
- Stratégie mise à jour pour désactiver l’énumération des fonctions USB via la gestion des périphériques mobiles (GPM) pour NCM pour AllowUsbConnection.
- Nous avons résolu un problème qui empêchait un appareil de HoloLens d’apparaître dans l’Explorateur de fichiers sur le protocole MTP (Media Transfer Protocol) quand l’appareil est configuré en tant que [borne d’application unique](hololens-kiosk.md). Notez que le MTP (et la connexion USB en général) peut toujours être désactivé à l’aide de la stratégie [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- Correction d’un problème de mise à l’échelle des icônes dans le menu Démarrer avec le mode plein écran.
- Correction d’un problème en raison de la mise en cache HTTP interférant avec le mode plein écran ciblé par les groupes AAD.
- Correction d’un problème qui empêchait les utilisateurs d’utiliser le bouton paire après l’activation du mode développeur avec les packages de mise en service, sauf s’ils ont désactivé et réactivé le mode développeur.

## Windows holographique, version 1903-mise à jour de novembre 2020
- Version 18362,1085

Cette mise à jour de la qualité mensuelle ne contient pas de modifications remarquables, nous vous encourageons à tester notre dernière version de Windows holographique, version 20H2.

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
