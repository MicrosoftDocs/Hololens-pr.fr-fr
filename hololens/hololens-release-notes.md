---
title: Notes de publication de HoloLens 2
description: Restez à jour avec toutes les mises à jour de chaque nouvelle version de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 18b0d6b304e8de8c85caeec9f3e8ba190647aaec
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308944"
---
# <a name="hololens-2-release-notes"></a>Notes de publication de HoloLens 2

Pour vous assurer que vous disposez d’une expérience productive avec vos appareils HoloLens, nous continuons à publier les mises à jour des fonctionnalités, des bogues et de la sécurité. Sur cette page, vous pouvez voir les nouveautés de HoloLens chaque mois. Pour obtenir la dernière mise à jour de HoloLens 2, vous pouvez [Rechercher des mises à jour et mettre à jour manuellement](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obtenir la mise à jour Flash complète (FFU) pour [flasher votre appareil via le compagnon de récupération avancé](hololens-recovery.md#clean-reflash-the-device). Le [Téléchargement](https://aka.ms/hololens2download) est mis à jour et fournit la version la plus récente de la mise à la disposition générale.

>[!NOTE]
> Nous sommes ravis de commencer à relancer les nouvelles fonctionnalités vers Windows Insider. Nous allons nous contenter d’utiliser le canal de développement pour les dernières mises à jour. Nous continuons nos notes de la [**HoloLens Insider**](hololens-insider.md) à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider. Soyez enthousiaste et prêt à mélanger ces mises à jour dans votre réalité.

Consultez les notes de publication associées :

- [Visitez l’archive de l’émulateur HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows holographique, version 20H2-mise à jour 2021 d’avril
- Build 19041,1144

Améliorations et correctifs de la mise à jour :

- Résout un problème lié à la création de rapports d’état d’installation des applications métier.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows holographique, version 1903-mise à jour du 2021 d’avril
- Build 18362,1108

Améliorations et correctifs de la mise à jour :

- Résout un problème où l’application de paramètres se bloque lors de la tentative de modification d’un mot de passe pour un compte local.

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows holographique, version 20H2-mise à jour de mars 2021
- Build 19041,1140

Améliorations et correctifs de la mise à jour :

- Les clients qui utilisent AdvancedPhotoCapture ou LowLagPhotoCapture pour capturer des photos avec HoloLens 2 peuvent désormais récupérer la caméra jusqu’à 3 secondes après la capture de la photo.
- Résolution d’une fuite de mémoire dans le service de portail des appareils, le problème a provoqué l’augmentation de l’utilisation de la mémoire par le service qui a provoqué l’échec de l’allocation de mémoire par d’autres applications.
- Résolution d’un problème où les utilisateurs inscrits au déploiement par étapes ne sont pas en mesure de se connecter à l’appareil.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows holographique, version 1903-mise à jour du 2021 du 1er mars
- Build 18362,1102

Améliorations et correctifs de la mise à jour :

- Résolution d’une fuite de mémoire dans le service de portail des appareils, le problème a provoqué l’augmentation de l’utilisation de la mémoire par le service qui a provoqué l’échec de l’allocation de mémoire par d’autres applications.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows holographique, version 20H2-mise à jour de février 2021
- Build 19041,1136

Améliorations et correctifs de la mise à jour :

- Résout un problème lié à la configuration initiale des appareils et aux mises à jour des applications du Store.
- Résout un problème concernant les mises à niveau et les vols pour les versions de HoloLens ultérieures.
- Suppression des certificats préinstallés inutilisés du magasin racine eSIM des appareils HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows holographique, version 1903-mise à jour du 2021 du 1er février
- Build 18362,1098

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières versions de Windows holographique, version 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows holographique, version 20H2-mise à jour de janvier 2021
- Build 19041,1134

Améliorations et correctifs de la mise à jour :

- Amélioration des performances lors du démarrage, de la reprise et du changement d’utilisateur lorsqu’il y a de nombreux utilisateurs sur l’appareil.
- Ajout de la prise en charge de Arm32 pour le [mode Research](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows holographique, version 1903-mise à jour du 1er janvier 2021
- Build 18362,1091

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières versions de Windows holographique, version 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows holographique, version 20H2-mise à jour de décembre 2020
- Build 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Installer des applications sur HoloLens 2 via le programme d’installation d’application

Nous **ajoutons une nouvelle fonctionnalité (programme d’installation de l’application) pour vous permettre d’installer des applications de manière plus transparente** sur vos appareils HoloLens 2. La fonctionnalité est **activée par défaut pour les appareils non gérés**. Pour éviter toute interruption des entreprises, le programme d’installation de l’application ne sera **pas disponible pour les appareils gérés** à l’heure actuelle.  

Un appareil est considéré comme « géré » si l' **une** des conditions suivantes est vraie :
- MDM [inscrit](hololens-enroll-mdm.md)
- Configuré avec le [package d’approvisionnement](hololens-provisioning.md)
- L' [identité](hololens-identity.md) de l’utilisateur est Azure ad

Vous êtes maintenant en mesure d’installer des applications sans avoir à activer le mode développeur ou à l’aide du portail des appareils.  Téléchargez simplement (via USB ou via Edge) le bundle AppX sur votre appareil et accédez au Bundle AppX dans l’Explorateur de fichiers pour être invité à lancer l’installation.  Vous pouvez également [lancer une installation à partir d’une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Tout comme les applications que vous installez à partir de la Microsoft Store ou chargement à l’aide de la fonctionnalité de déploiement d’applications métier MDM, les applications doivent être signées numériquement avec l' [outil Sign](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) et le [certificat utilisé pour signer doit être approuvé](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) par l’appareil HoloLens avant que l’application puisse être déployée.

**Instructions d’installation de l’application.**

1.  S’assurer que votre appareil n’est pas considéré comme géré
1.  Vérifiez que votre appareil HoloLens 2 est sous tension et connecté à votre PC.
1.  Vérifiez que vous êtes connecté à l’appareil HoloLens 2
1.  Sur votre PC, accédez à votre application personnalisée et copiez VotreApplication. appxbundle dans yourdevicename\Internal Storage\Downloads.   Une fois que vous avez terminé de copier votre fichier, vous pouvez déconnecter votre appareil
1.  À partir de votre appareil HoloLens 2, ouvrez le menu Démarrer, sélectionnez toutes les applications, puis lancez l’application Explorateur de fichiers.
1.  Accédez au dossier téléchargements. Vous devrez peut-être dans le volet gauche de l’application sélectionner cet appareil en premier, puis accéder à téléchargements.
1.  Sélectionnez le fichier VotreApplication. appxbundle.
1.  Le programme d’installation de l’application démarre. Sélectionnez le bouton installer pour installer votre application.
L’application installée sera automatiquement lancée à la fin de l’installation.

Vous trouverez des exemples d’applications sur [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) pour tester ce processus.

En savoir plus sur le processus complet d' [installation d’applications sur HoloLens 2 avec le programme d’installation de l’application](app-deploy-app-installer.md).  

![Installation d’exemples MRTK via le programme d’installation d’application](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Améliorations et correctifs de la mise à jour :

- Le suivi des mains gère désormais le suivi dans de nombreux cas de figure où la main aurait été perdue précédemment.  Dans certains de ces nouveaux cas, seule la position du Palm continue à se mettre à jour en fonction de la main réelle de l’utilisateur, tandis que les autres jointures sont déduites en fonction d’une pose précédente.  Cette modification permet d’améliorer la cohérence du suivi des mouvements tels que flanque, la levée, la recherche et la applaudissements.  Elle est également utile dans les cas où la main est proche d’une surface ou maintient un objet.  Lorsque les articulations de la main sont déduites, la valeur de [précision conjointe](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) est définie sur « approximatif » au lieu de « High ».
- Correction d’un problème où la réinitialisation du code PIN pour les comptes Azure AD indique une erreur «un problème est survenu.
- Les utilisateurs doivent voir bien moins d’incidents OOBE après démarrage lors du lancement de, de l’iris à partir des paramètres application, nouvel utilisateur ou Toast de notification.
- Les utilisateurs doivent disposer d’un fuseau horaire correct sortant de OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows holographique, version 1903-mise à jour de décembre 2020
- Build 18362,1088

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester la dernière mise à jour de Windows holographique, version 20H2-décembre 2020 et la nouvelle fonctionnalité d’installation d’application ajoutée à la Build.


## <a name="windows-holographic-version-20h2"></a>Windows holographique, version 20H2
- Build 19041,1128

Windows holographique, version 20H2 est désormais disponible et apporte un ensemble de nouvelles fonctionnalités aux utilisateurs et aux professionnels de l’informatique HoloLens 2. Du positionnement de l’œil automatique au gestionnaire de certificats dans les paramètres, à la fonctionnalité de mode plein écran améliorée et aux nouvelles fonctionnalités de configuration de AutoPilot. Cette nouvelle mise à jour permet aux équipes informatiques de bénéficier d’un contrôle plus granulaire de la configuration et de la gestion des appareils HoloLens, et offre aux utilisateurs des expériences holographiques encore plus fluides. 

Cette dernière version est une mise à jour mensuelle de la version 2004, mais cette fois, nous incluons de nouvelles fonctionnalités. Le numéro de version majeure reste le même et Windows Update indique une version mensuelle de la version 2004 (Build 19041). Vous pouvez consulter votre numéro de build dans paramètres > à propos de l’écran pour confirmer que vous êtes sur la dernière version disponible 19041.1128 +. Pour effectuer une mise à jour vers la dernière version, ouvrez l’application paramètres, accédez à mettre à jour & sécurité, puis appuyez sur Rechercher les mises à jour. Pour plus d’informations sur la gestion des mises à jour HoloLens, visitez [cette page](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Nouveautés de Windows holographique, version 20H2  

| Fonctionnalité                                              | Description                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Prise en charge de la position oculaire automatique](hololens-release-notes.md#auto-eye-position-support) | Calcule activement les positions oculaires sans que les utilisateurs passent par l’étalonnage du suivi oculaire.   |
| [Gestionnaire de certificats](hololens-release-notes.md#certificate-manager)   | Permet de nouvelles méthodes plus simples pour installer et supprimer des certificats dans l’application paramètres.     |
| [Lancement automatique de l’approvisionnement à partir d’USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | L’approvisionnement de packages sur des lecteurs USB invite automatiquement la page de configuration dans OOBE.                                                         |
| [Confirmer automatiquement les packages de provisionnement dans OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Les packages d’approvisionnement sont automatiquement appliqués lors de l’OOBE à partir de la page de configuration.                                                         |
| [Approvisionnement automatique sans interface utilisateur](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Comment combiner le lancement automatique et la confirmation automatique de l’approvisionnement. |
| [Utilisation de AutoPilot avec Wi-Fi connexion](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Utilisez AutoPilot à partir de Wi-Fi d’appareil sans carte Ethernet. |
| [CSP Tenantlockdown et Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Après l’inscription du locataire et la stratégie, l’appareil peut uniquement être inscrit dans ce locataire à chaque réinitialisation ou redémarrage de l’appareil. |
| [Accès global affecté](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nouvelle méthode de configuration pour le mode plein écran d’application qui applique la borne au niveau du système, en la rendant applicable à tous.                  |
| [Lancer automatiquement une application dans une borne multi-application](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Définit une application pour qu’elle démarre automatiquement lors de la connexion à un mode plein écran à plusieurs applications.                                                        |
| [Modifications du comportement du mode plein écran pour la gestion des défaillances](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L’échec du mode plein écran présente désormais une restriction de secours.                                                                                                |
| [Stratégies HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nouvelles stratégies pour HoloLens.     |
| [Appartenance au groupe de Azure AD de cache pour une borne en mode hors connexion](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nouvelle stratégie permet aux utilisateurs d’utiliser le cache d’appartenance au groupe pour utiliser le mode plein écran pendant un nombre défini de jours.                                        |
| [Nouvelles stratégies de restriction d’appareil pour HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Les stratégies de gestion des appareils ont été activées récemment pour HoloLens 2.                                                                                |
| [Nouvelles stratégies d’alimentation pour HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Stratégies nouvellement prises en charge pour les paramètres de délai d’attente.  |
| [Mettre à jour les stratégies](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Stratégies récemment activées autorisant le contrôle des mises à jour.           |
| [Visibilité de la page des paramètres activés pour HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Stratégie pour choisir les pages qui sont affichées dans l’application paramètres.             |
| [Mode de recherche](hololens-release-notes.md#research-mode) | Utilisation du mode de recherche sur HoloLens 2. |
| [Durée d’enregistrement augmentée](hololens-release-notes.md#recording-length-increased) | Les enregistrements MRC ne sont plus limités à 5 minutes. |
| [Améliorations et correctifs de la mise à jour](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correctifs supplémentaires dans la mise à jour.   |

### <a name="auto-eye-position-support"></a>Prise en charge de la position oculaire automatique

Dans HoloLens 2, les positions oculaires permettent un positionnement d’hologramme précis, une expérience d’affichage confortable et une meilleure qualité d’affichage. Les positions oculaires sont calculées en interne dans le cadre du calcul du suivi des yeux. Toutefois, cela nécessite que chaque utilisateur passe par l’étalonnage du suivi oculaire, même si l’expérience n’a pas besoin d’une entrée de regard oculaire.

La position de l' **œil automatique (AEP)** active ces scénarios avec une méthode sans interaction pour calculer les positions oculaires de l’utilisateur. La position de l’œil automatique commence à fonctionner en arrière-plan automatiquement à partir du moment où l’utilisateur place l’appareil. Si l’utilisateur n’a pas d’étalonnage de suivi visuel précédent, la position de l’œil automatique commence à fournir aux yeux de l’utilisateur le système d’affichage après un temps de traitement de 20-30 secondes. Les données utilisateur ne sont pas conservées sur l’appareil et, par conséquent, ce processus est répété si l’utilisateur le met hors tension, ou si l’appareil redémarre ou sort du mode veille.

Il y a quelques modifications de comportement du système avec la fonctionnalité de position d’oeil automatique lorsqu’un utilisateur non étalonné place sur l’appareil. Dans ce contexte, un utilisateur non étalonné fait référence à une personne qui n’a pas encore effectué le processus d’étalonnage du suivi oculaire sur l’appareil.

| Application active | Comportement précédent | Comportement à partir de Windows holographique, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Application sans point d’accès en regard ou interface holographique |La boîte de dialogue de l’invite d’étalonnage du suivi oculaire s’affiche. | Aucune invite ne s’affiche. |
| Application avec pointage en regard | La boîte de dialogue de l’invite d’étalonnage du suivi oculaire s’affiche. | L’invite d’étalonnage du suivi oculaire s’affiche uniquement quand l’application accède à un flux de regard visuel. |

Si l’utilisateur passe d’une application qui n’est pas activée pour la première fois à une application qui accède aux données de regard, l’invite d’étalonnage s’affiche. 

Tout autre comportement système est semblable à lorsque l’utilisateur actuel ne dispose pas d’un étalonnage de suivi oculaire actif. Par exemple, le mouvement de démarrage à la main n’est pas activé. Aucune modification n’est apportée à l’expérience d’installation initiale.

Pour les expériences nécessitant des données de regard visuelles ou un positionnement d’hologramme très précis, nous recommandons aux utilisateurs déétalonnés d’exécuter un étalonnage du suivi oculaire. Elle est accessible à partir de l’invite d’étalonnage du suivi oculaire ou en lançant l’application paramètres à partir du menu Démarrer, puis en sélectionnant **système > étalonnage >** étalonnage de l’œil > exécution de l’outil.

Ces informations peuvent être recherchées ultérieurement avec d' [autres informations d’étalonnage](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gestionnaire de certificats

- Amélioration de l’audit, du diagnostic et des outils de validation pour la sécurité et la conformité des appareils par le biais du nouveau gestionnaire de certificats. Cette fonctionnalité vous permettra de déployer, de dépanner et de valider vos certificats à grande échelle dans les environnements commerciaux.

Dans Windows holographique version 20H2, nous ajoutons un gestionnaire de certificats dans l’application paramètres HoloLens 2. Accédez à **paramètres > mettre à jour & sécurité > certificats**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs disposent désormais d’outils d’audit, de diagnostic et de validation améliorés pour garantir que les appareils restent sécurisés et conformes. 

-   **Audit :** Possibilité de valider le déploiement correct d’un certificat ou de confirmer qu’il a été supprimé de manière appropriée. 
-   **Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de faciliter la résolution des problèmes. 
-   **Validation :** Vérifier qu’un certificat est destiné à l’usage prévu et qu’il fonctionne, peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux avant de déployer des certificats à grande échelle.

Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher les propriétés d’un certificat, sélectionnez le certificat, puis cliquez sur **info**. 

L’installation de certificat prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats sur l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent s’installer que dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

#### <a name="to-install-a-certificate"></a>Pour installer un certificat : 

1.  Connectez votre HoloLens 2 à un PC.
1.  Placez le fichier de certificat que vous souhaitez installer dans un emplacement sur votre HoloLens 2.
1.  Accédez à **paramètres application > mettre à jour & sécurité > certificats**, puis sélectionnez Installer un certificat.
1.  Cliquez sur **Importer un fichier** et accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **emplacement du magasin**.
1.  Sélectionnez **magasin de certificats**.
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

#### <a name="to-remove-a-certificate"></a>Pour supprimer un certificat : 
1. Accédez à **paramètres application > mise à jour et sécurité > certificats**.
1. Recherchez le certificat par son nom dans la zone de recherche.
1. Sélectionnez le certificat.
1. Cliquez sur **supprimer**
1. Lorsque vous êtes invité à confirmer l’opération, sélectionnez **Oui**.

![Visionneuse de certificats dans l’application paramètres](images/certificate-viewer-device.jpg)

![Image illustrant l’utilisation de l’interface utilisateur de certificat pour installer un certificat](images/certificate-device-install.jpg)

Ces informations peuvent être recherchées ultérieurement [dans une nouvelle page du gestionnaire de certificats](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Lancement automatique de l’approvisionnement à partir d’USB

- Processus automatisés permettant une utilisation moins importante de l’utilisateur quand des lecteurs USB avec des packages d’approvisionnement sont utilisés pendant l’OOBE.

Avant cette version, les utilisateurs devaient lancer l’écran d’approvisionnement manuellement lors de l’approvisionnement à l’aide d’une combinaison de boutons. Désormais, les utilisateurs peuvent ignorer la combinaison de boutons à l’aide d’un package d’approvisionnement sur un lecteur de stockage USB. 

1. Brancher le lecteur USB avec le package d’approvisionnement pendant la première heure d’interaction d’OOBE
1. Lorsque l’appareil est prêt à être approvisionné, il ouvre automatiquement l’invite avec la page de configuration. 

Remarque : si un lecteur USB reste branché pendant le démarrage de l’appareil, OOBE énumère les dispositifs de stockage USB existants, ainsi que des éléments supplémentaires qui sont connectés.

Pour plus d’informations sur l’application de packages de provisionnement au cours d’OOBE, consultez la documentation sur la [configuration de HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) .

Pour plus d’informations sur l' [approvisionnement automatique à partir d’un lecteur USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) , consultez la documentation relative à la configuration de HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmer automatiquement les packages de provisionnement dans OOBE
- Processus automatisé autorisant moins d’intervention de l’utilisateur, lorsque la page package d’approvisionnement s’affiche, tous les packages répertoriés sont automatiquement appliqués.

Lorsque l’écran principal de configuration s’affiche, OOBE compte 10 secondes avant de commencer à appliquer automatiquement tous les packages d’approvisionnement. Les utilisateurs peuvent toujours [confirmer ou annuler](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) pendant ces 10 secondes après avoir vérifié les packages attendus.

### <a name="automatic-provisioning-without-using-ui"></a>Approvisionnement automatique sans interface utilisateur
- Processus automatiques combinés pour réduire les interactions de l’appareil pour l’approvisionnement. 

En associant le lancement automatique de l’approvisionnement à partir des périphériques USB et la confirmation automatique des packages de provisionnement, un utilisateur peut approvisionner automatiquement des appareils HoloLens 2 sans utiliser l’interface utilisateur de l’appareil, ni même porter l’appareil. Vous pouvez continuer à utiliser le même lecteur USB et le même package de configuration pour plusieurs appareils. Cela est utile pour déployer plusieurs appareils à la fois dans la même zone. 

1. [Créez un package d’approvisionnement](hololens-provisioning.md) à l’aide du [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiez le package sur un lecteur de stockage USB.
1. [Flashez votre version de HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) à [19041,1361 ou une version plus récente](https://aka.ms/hololens2previewdownload). 
1. Lorsque l' [Assistant de récupération avancée](https://www.microsoft.com/store/productId/9P74Z35SFRS8) a terminé le clignotement de votre appareil, débranchez le câble USB-C. 
1. Branchez votre lecteur USB sur l’appareil.
1. Lorsque l’appareil HoloLens 2 démarre dans OOBE, il détecte automatiquement le package d’approvisionnement sur le lecteur USB et lance la page de configuration.
1. Après 10 secondes, l’appareil applique automatiquement le package d’approvisionnement. 

Votre appareil est maintenant configuré et [affiche l’écran de réussite de l’approvisionnement](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Utilisation de AutoPilot avec Wi-Fi connexion
- Suppression de la nécessité d’utiliser des adaptateurs USB-C pour réduire les besoins en matériel, en activant AutoPilot pour fonctionner sur Wi-Fi appareils connectés.

Désormais, lors de l’OOBE, une fois que vous avez connecté HoloLens 2 au Wi-Fi, OOBE recherche un profil AutoPilot pour l’appareil. S’il en trouve un, il sera utilisé pour terminer le reste du processus d’inscription et de jonction AAD. En d’autres termes, l’utilisation d’Ethernet vers USB-C ou Wi-Fi vers l’adaptateur USB-C n’est plus une exigence, mais elle continue de fonctionner si elle est fournie au début d’OOBE. En savoir plus sur [AutoPilot pour les appareils HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP Tenantlockdown et Autopilot
- Conserve les appareils sur le locataire de l’organisation en les verrouillant sur le locataire, même via la réinitialisation ou le redémarrage de l’appareil. Avec une sécurité accrue en désaccordant la création de comptes dans via la configuration. 

Les appareils HoloLens 2 prennent désormais en charge le CSP TenantLockdown à partir de [Windows holographique version 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) Le fournisseur CSP permet à HoloLens 2 d’être lié à l’inscription MDM à l’aide d’AutoPilot uniquement. Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur la valeur true ou false (initialement définie) sur HoloLens 2, cette valeur reste sur l’appareil malgré le réclignotement, les mises à jour du système d’exploitation, etc. 

Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown a la valeur true sur HoloLens 2, OOBE attend indéfiniment que le profil AutoPilot soit téléchargé et appliqué avec succès après une connexion réseau. 

Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown a la valeur true sur HoloLens 2, les opérations suivantes ne sont pas autorisées dans OOBE : 
- Création d’un utilisateur local à l’aide de l’approvisionnement du Runtime 
- Exécution d’une opération de jointure Azure AD via l’approvisionnement du Runtime 
- Sélection du propriétaire de l’appareil dans l’expérience OOBE 

#### <a name="how-to-set-this-using-intune"></a>Comment définir cette configuration à l’aide d’Intune ? 
1. Créez un profil de configuration d’appareil URI OMA personnalisé et spécifiez true pour le nœud RequireNetworkInOOBE comme indiqué ci-dessous.
La valeur OMA-URI doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Définition du verrouillage utilisateurs locataires via OMA-URI](images/hololens-tenant-lockdown.png)

1. Créez un groupe et affectez le profil de configuration de l’appareil à ce groupe d’appareils. 

1. Rendez le membre de l’appareil HoloLens 2 du groupe créé à l’étape précédente et déclenchez la synchronisation.  

Vérifiez dans le portail Intune que la configuration de l’appareil a été appliquée avec succès. Une fois que la configuration de l’appareil s’applique correctement sur l’appareil HoloLens 2, les effets de TenantLockdown sont actifs.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Comment faire pour annuler la RequireNetworkInOOBE de TenantLockdown sur HoloLens 2 à l’aide d’Intune ? 
1. Supprimez HoloLens 2 du groupe d’appareils sur lequel la configuration d’appareil créée ci-dessus a été précédemment affectée. 

1. Créez un profil de configuration d’appareil basé sur un URI OMA personnalisé et spécifiez false pour RequireNetworkInOOBE comme indiqué ci-dessous. La valeur OMA-URI doit être./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de la définition de RequireNetworkInOOBE sur false via un URI OMA dans Intune](images/hololens-tenant-lockdown-false.png)

1. Créez un groupe et affectez le profil de configuration de l’appareil à ce groupe d’appareils. 

1. Rendez le membre de l’appareil HoloLens 2 du groupe créé à l’étape précédente et déclenchez la synchronisation.

Vérifiez dans le portail Intune que la configuration de l’appareil a été appliquée avec succès. Une fois que la configuration de l’appareil s’applique correctement sur l’appareil HoloLens 2, les effets de TenantLockdown sont inactifs. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Que se passe-t-il lors de l’OOBE, si le profil AutoPilot n’est pas affecté sur un HoloLens après que TenantLockdown a été défini sur true ? 
OOBE attend indéfiniment que le chargement du profil AutoPilot et la boîte de dialogue suivante s’affichent. Pour supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit avec son locataire d’origine à l’aide de AutoPilot uniquement et RequireNetworkInOOBE doit être désactivé comme décrit dans l’étape précédente avant que les restrictions introduites par le CSP TenantLockdown soient supprimées. 

![Vue dans le périphérique pour lorsque la stratégie est appliquée sur l’appareil.](images/hololens-autopilot-lockdown.png)

Vous pouvez désormais trouver ces informations en même temps que le reste du pilote AutoPilot sous [TENANTLOCKDOWN CSP et AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Accès global affecté – mode plein écran
- Réduction de la gestion des identités pour les bornes, en activant la nouvelle méthode Kiosk qui applique le mode plein écran au niveau du système.

Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode plein écran de plusieurs applications, applicable au niveau du système, n’a aucune affinité avec une identité sur le système et s’applique à tous les utilisateurs qui se connectent à l’appareil. En savoir plus sur cette nouvelle fonctionnalité en détail dans la [borne d’accès assignée globale HoloLens](hololens-global-assigned-access-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Lancement automatique d’une application en mode plein écran à plusieurs applications 
- Expérience ciblée avec le lancement automatique d’applications, ce qui améliore davantage l’interface utilisateur et les sélections d’applications choisies pour les expériences en mode plein écran.

S’applique uniquement au mode plein écran à plusieurs applications et seule une application peut être désignée pour être lancée automatiquement à l’aide de l’attribut en surbrillance ci-dessous dans la configuration d’accès affectée. 

L’application est automatiquement lancée lorsque l’utilisateur se connecte. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Modifications du comportement du mode plein écran pour la gestion des défaillances
- Mode plein écran sécurisé en éliminant les applications disponibles en cas de défaillance du mode plein écran. 

Précédemment, en cas d’échec lors de l’application du mode plein écran, HoloLens était utilisé pour afficher toutes les applications dans le menu Démarrer. Désormais, dans Windows holographique version 20H2 en cas de défaillance, aucune application ne sera affichée dans le menu Démarrer comme indiqué ci-dessous : 

![Image du mode plein écran à présent en cas d’échec.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Stratégies HoloLens
- Options de gestion des appareils spécifiques à HoloLens créé pour la gestion de l’appareil. 

De nouvelles stratégies de réalité mixte ont été créées pour les appareils HoloLens 2 sur Windows holographique version 20H2. Les nouveaux paramètres contrôlables incluent : définition de la luminosité, définition du volume, désactivation de l’enregistrement audio dans les captures de réalité mixte, définition du moment où les diagnostics peuvent être collectés et mise en cache de l’appartenance au groupe AAD.  

| Nouvelle stratégie HoloLens                                | Description                                                                               | Notes                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permet de désactiver les boutons de luminosité afin que le fait de cliquer dessus ne change pas de luminosité.       | 1 Oui, 0 non (par défaut)                                                |
| MixedReality\VolumeButtonDisabled                  | Permet de désactiver les boutons de volume afin que le fait d’appuyer sur le volume ne change pas.               | 1 Oui, 0 non (par défaut)                                                |
| MixedReality\MicrophoneDisabled                    | Désactive le microphone, de sorte qu’aucun enregistrement audio n’est possible sur HoloLens 2.                      | 1 Oui, 0 non (par défaut)                                                |
| MixedReality\FallbackDiagnostics                   | Contrôle le comportement de lorsque les journaux de diagnostic peuvent être collectés.                               | 0 désactivé, 1 activé pour les propriétaires d’appareils, 2 activé pour tout (par défaut) |
| MixedReality\HeadTrackingMode                      | Réservé pour un usage futur.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Contrôle le nombre de jours pendant lesquels le cache d’appartenance au groupe Azure AD est utilisé pour les groupes de Azure AD de ciblage Kiosk. | Voir ci-dessous.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Appartenance au groupe de Azure AD de cache pour une borne en mode hors connexion
- Activez les bornes hors connexion à utiliser avec les groupes AAD pendant jusqu’à 60 jours.

Cette stratégie détermine le nombre de jours pendant lesquels le cache d’appartenance au groupe Azure AD peut être utilisé pour les configurations d’accès affectées ciblant les groupes de Azure AD pour l’utilisateur connecté. Une fois que cette valeur de stratégie est définie sur une valeur supérieure à 0, alors le cache est utilisé dans le cas contraire.  

Nom : AADGroupMembershipCacheValidityInDays URI value :./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 jours  
Max-60 jours 

Étapes pour utiliser cette stratégie correctement : 
1. Créez un profil de configuration d’appareil pour le ciblage de bornes Azure AD des groupes et affectez-le à un ou plusieurs appareils HoloLens. 
1. Créer une configuration d’appareil basée sur un URI OMA personnalisée qui définit cette valeur de stratégie sur le nombre de jours souhaité (> 0) et l’assigner au (x) appareil (s) HoloLens. 
    1. La valeur de l’URI doit être entrée dans la zone de texte OMA-URI en tant que./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. La valeur peut être comprise entre min/maximum autorisé.
1. Inscrire des appareils HoloLens et vérifier que les deux configurations sont appliquées à l’appareil. 
1. Autoriser Azure AD utilisateur 1 à se connecter quand Internet est disponible, une fois que l’utilisateur se connecte et que Azure AD appartenance au groupe est confirmée avec succès, le cache est créé. 
1. Désormais, Azure AD utilisateur 1 peut mettre HoloLens hors connexion et l’utiliser pour le mode plein écran tant que la valeur de la stratégie autorise un nombre de jours de X. 
1. Les étapes 4 et 5 peuvent être répétées pour tout autre Azure AD l’utilisateur N. point clé ici : tout utilisateur Azure AD doit se connecter à l’appareil à l’aide d’Internet, de sorte qu’au moins une fois, nous pouvons déterminer qu’ils sont membres du groupe Azure AD auquel la configuration de kiosque est destinée. 
 
> [!NOTE]
> Tant que l’étape 4 n’est pas exécutée pour un Azure AD utilisateur rencontre un comportement d’échec mentionné dans les environnements « déconnectés ». 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nouvelles stratégies de restriction d’appareil pour HoloLens 2
- Permet aux utilisateurs de gérer des stratégies de gestion d’appareils spécifiques, telles que le blocage de l’ajout ou de la suppression de packages de provisionnement.

Stratégies récemment activées qui permettent d’obtenir davantage d’options de gestion des appareils HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Ces deux nouvelles stratégies pour AllowAddProvisioningPackage et AllowRemoveProvisioningPackage sont ajoutées à nos restrictions d' [appareil courantes](hololens-common-device-restrictions.md).

> [!NOTE]
> En ce qui concerne [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), HoloLens prend uniquement en charge la configuration./Vendor/msft/RemoteLock/Lock. Les configurations associées à un code confidentiel, telles que la réinitialisation et la récupération, ne sont pas prises en charge.

### <a name="new-power-policies-for-hololens-2"></a>Nouvelles stratégies d’alimentation pour HoloLens 2
- Plus d’options pour le moment où HoloLens se met en veille ou verrouille les stratégies d’alimentation. 

Ces stratégies permettent aux administrateurs de contrôler les États d’alimentation, tels que le délai d’inactivité. Pour en savoir plus sur chaque stratégie individuelle, cliquez sur le lien correspondant à cette stratégie.

|     Lien vers la documentation sur les stratégies                |     Notes                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Exemple de valeur à utiliser dans le concepteur de configuration Windows, par exemple, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, par exemple, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Exemple de valeur à utiliser dans le concepteur de configuration Windows, c.-à-d.,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Ces deux nouvelles stratégies pour DisplayOffTimeoutOnBattery et DisplayOffTimeoutPluggedIn sont ajoutées à nos restrictions d' [appareil courantes](hololens-common-device-restrictions.md).

> [!NOTE]
> Pour une expérience cohérente sur HoloLens 2, vérifiez que les valeurs pour DisplayOffTimeoutOnBattery et StandbyTimeoutOnBattery sont définies sur la même valeur. Il en va de même pour DisplayOffTimeoutPluggedIn et StandbyTimeoutPluggedIn. Pour plus d’informations sur la mise en veille moderne, reportez-vous à l' [affichage, à la mise en veille et](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) à la mise en veille prolongée.

### <a name="newly-enabled-update-policies-for-hololens"></a>Stratégies de mise à jour récemment activées pour HoloLens
- Plus d’options pour le moment où les mises à jour sont installées ou la désactivation du bouton suspendre les mises à jour pour garantir les mises à jour.

Ces stratégies de mise à jour sont désormais activées sur les appareils HoloLens 2 :
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Mettre à jour/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Pour plus d’informations sur ces stratégies de mise à jour et leur utilisation pour les appareils HoloLens, consultez [gérer les mises à jour hololens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilité de la page des paramètres activés pour HoloLens 2
- Contrôle accru de l’interface utilisateur dans l’application paramètres, qui peut être confondu pour afficher une sélection limitée de pages.

Nous avons maintenant activé une stratégie qui permet aux administrateurs informatiques d’empêcher des pages spécifiques de l’application Paramètres système d’être visibles ou accessibles, ou de le faire pour toutes les pages, à l’exception de celles spécifiées. Pour savoir comment personnaliser entièrement cette fonctionnalité, cliquez sur le lien ci-dessous.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Pour connaître les paramètres de page que vous pouvez personnaliser sur HoloLens 2, consultez la [page Paramètres URI](settings-uri-list.md). 
 
![Capture d’écran des heures actives modifiées dans l’application paramètres](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Mode de recherche
En mode de recherche, le HoloLens 2 devient un outil puissant pour la recherche de vision par ordinateur. Par rapport aux éditions précédentes, le mode de recherche pour HoloLens 2 présente les avantages suivants :
-   Outre les capteurs exposés en mode de recherche HoloLens (1re génération), nous fournissons maintenant un accès de capteur IMU, notamment un accéléromètre, un gyroscope et un magnétomètre.
-   HoloLens 2 offre de nouvelles fonctionnalités qui peuvent être utilisées en même temps que le mode de recherche. En particulier, l’accès aux API articulées de suivi des mains et de suivi des yeux qui peuvent fournir un ensemble d’expériences plus riche.

Les chercheurs ont désormais la possibilité d’activer le mode de recherche sur leurs appareils HoloLens pour accéder à tous ces flux de capteurs d’images brutes externes. Le mode de recherche pour HoloLens 2 fournit également l’accès aux lectures accéléromètre, gyroscope et magnétomètre. Pour protéger la confidentialité des utilisateurs, les images de caméra de suivi oculaire brut ne sont pas disponibles par le biais du mode de recherche, mais la direction du point de vue des yeux est disponible via les API existantes.

Pour plus d’informations techniques, consultez la [documentation du mode de recherche](https://docs.microsoft.com/windows/mixed-reality/research-mode) .

### <a name="recording-length-increased"></a>Durée d’enregistrement augmentée
En raison des commentaires des clients, nous avons augmenté la durée d’enregistrement des [captures de réalité mixte](holographic-photos-and-videos.md). Les captures de réalité mixte ne seront plus limitées à 5 minutes par défaut, mais elles calculeront la longueur maximale d’enregistrement en fonction de l’espace disque disponible. L’appareil estime la durée maximale d’enregistrement vidéo en fonction de l’espace disque disponible, jusqu’à 80% de l’espace disque total.

> [!NOTE]
> Le HoloLens utilise la durée d’enregistrement vidéo par défaut (5 minutes) si l’un des éléments suivants se produit :
> - La durée d’enregistrement maximale estimée est inférieure à la valeur par défaut de 5 minutes.
> - L’espace disque disponible est inférieur à 20% de l’espace disque total.

Vous trouverez la configuration complète requise dans notre documentation sur les [photos et vidéos holographiques](holographic-photos-and-videos.md#maximum-recording-length) . 

### <a name="improvements-and-fixes-in-the-update"></a>Améliorations et correctifs de la mise à jour :
- D’autres écrans dans OOBE sont désormais en mode sombre.
- Pour plus d’informations, consultez la déclaration de confidentialité la plus récente en ligne.
- A résolu un problème où les utilisateurs ne pouvaient pas approvisionner des profils VPN par le biais de packages d’approvisionnement.
- Résolution d’un problème de configuration du proxy pour la connexion VPN.
- Mise à jour de la stratégie pour désactiver l’énumération des fonctions USB via MDM pour NCM pour AllowUsbConnection.
- A résolu un problème qui empêchait un appareil HoloLens de s’apparaître dans l’Explorateur de fichiers via le protocole MTP (Media Transfer Protocol) lorsque l’appareil est configuré en tant que [kiosque à une seule application](hololens-kiosk.md). Notez que le MTP (et la connexion USB en général) peuvent toujours être désactivés à l’aide de la stratégie [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- Correction d’un problème où les icônes du menu Démarrer étaient correctement mises à l’échelle en mode plein écran.
- Résolution d’un problème lié à la mise en cache HTTP interférant avec le mode plein écran ciblant les groupes de Azure AD.
- Résolution d’un problème où les utilisateurs ne pouvaient pas utiliser le bouton de paire après l’activation du mode développeur avec les packages d’approvisionnement, sauf s’ils ont désactivé et réactivé le mode développeur.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows holographique, version 1903-mise à jour du 2020 du 1er novembre
- Build 18362,1085

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à essayer notre dernière version de la version de fonctionnalité Windows holographique, version 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows holographique, version 2004-mise à jour d’octobre 2020
- Build 19041,1124
 
Améliorations et correctifs de la mise à jour :

- Suppression d’une vérification inutile qui provoquait une erreur du système d’exécution.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows holographique, version 1903-mise à jour d’octobre 2020
- Build 18362,1081

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières versions de Windows holographique, version 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows holographique, version 2004-mise à jour de septembre 2020
- Build 19041,1117

Améliorations et correctifs de la mise à jour :

- Résout un problème qui empêchait Visual Studio de déboguer une application quand SupportsMultipleInstances = "true" est présent dans appxmanifest.
- Cette version comprend le correctif de détection du proxy NCSI pour résoudre les échecs de détection Internet sur le proxy réseau. NCSI peut utiliser un proxy d’ordinateur et un proxy par profil pour la détection de la connectivité Internet. Le proxy par utilisateur sera pris en charge par NCSI dans la prochaine version.
- Sur la plupart des appareils Windows Mixed Reality, le vecteur de direction vers l’avant est parallèle au sol lorsque la tête de l’utilisateur se trouve dans une position neutre à l’avenir. Toutefois, les versions antérieures de HoloLens 2 alignent le vecteur de façon à ce qu’il soit perpendiculaire aux panneaux d’affichage, ce qui est incliné vers le bas à quelques degrés par rapport à l’orientation idéale. Les versions plus récentes de HoloLens 2 ont corrigé cela pour garantir la cohérence sémantique entre les différents facteurs de forme.
- Amélioration de la robustesse du suivi de la main qui entraîne moins de pertes de suivi dans des scénarios spécifiques.
- Cette version contient un correctif pour améliorer la qualité des horodateurs audio, qui peut avoir contribué à des problèmes de capture vidéo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows holographique, version 1903-mise à jour de septembre 2020
- Build 18362,1079

Améliorations et correctifs de la mise à jour :

- Sur la plupart des appareils Windows Mixed Reality, le vecteur de direction vers l’avant est parallèle au sol lorsque la tête de l’utilisateur se trouve dans une position neutre à l’avenir. Toutefois, les versions antérieures de HoloLens 2 alignent le vecteur de façon à ce qu’il soit perpendiculaire aux panneaux d’affichage, ce qui est incliné vers le bas à quelques degrés par rapport à l’orientation idéale. Les versions plus récentes de HoloLens 2 ont corrigé cela pour garantir la cohérence sémantique entre les différents facteurs de forme.
- Amélioration de la robustesse du suivi de la main qui entraîne moins de pertes de suivi dans des scénarios spécifiques.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows holographique, version 2004-mise à jour du 2020 août
- Build 19041,1113

Améliorations et correctifs de la mise à jour :

- L’application paramètres ne suivra plus l’utilisateur dans l’inscription par Iris ou l’étalonnage du suivi oculaire.
- Correction d’un bogue dans lequel l’application d’un package d’approvisionnement au cours d’OOBE qui renomme l’appareil et effectue d’autres actions (telles que la connexion à un réseau) ne parviendrait pas à effectuer les autres actions après le redémarrage de l’appareil en raison d’un changement de nom.
- Modèle de couleurs modifié des flux d’installation initiaux des appareils pour améliorer la qualité visuelle.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows holographique, version 1903-mise à jour du 2020 août
- Build 18362,1074

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, nous vous encourageons à tester nos dernières versions de Windows holographique, version 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows holographique, version 2004-mise à jour de juillet 2020
- Build 19041,1109

Améliorations et correctifs de la mise à jour :

- Les développeurs peuvent désormais choisir d’activer ou de désactiver le portail des appareils pour qu’ils requièrent une connexion sécurisée.
- Fiabilité améliorée pour les lancements d’applications après les mises à jour du système d’exploitation.
- Modification de la luminosité de la boîte de réception par défaut à 100 pour cent.
- Nous avons résolu un problème concernant le transfert HTTPs pour le portail de périphériques Windows sur HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows holographique, version 1903-mise à jour de juillet 2020
- Build 18362,1071

Améliorations et correctifs de la mise à jour :

- Correction d’un problème qui pouvait entraîner la disparition des hologrammes dans les applications Unity lors de la perte ou de la réobtention du suivi.
- Correction d’un problème qui provoquait le blocage des applications HoloLens exclusives sur le shell lors de l’utilisation de l’émulateur HoloLens avec l’accélération matérielle sur certains appareils.
- A résolu un problème concernant le transfert HTTPs pour le portail de périphériques Windows sur HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows holographique, version 2004-mise à jour du 2020 du 1er juin
- Build 19041,1106

Améliorations et correctifs de la mise à jour :

- Les enregistreurs MRC personnalisés ont désormais de nouvelles valeurs par défaut pour certaines propriétés s’ils ne sont pas spécifiés.
  - Sur l' *effet de la vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l' *effet audio MRC*:
    - LoopbackGain (la valeur actuelle « gain audio de l’application » sur la page de capture de la réalité mixte dans le portail d’appareils Windows)
    - MicrophoneGain (valeur actuelle « gain audio mic » sur la page de capture de la réalité mixte dans le portail d’appareils Windows)
- Correction d’un bogue pour améliorer la qualité audio dans les scénarios de capture de réalité mixte. Plus précisément, ce correctif doit éliminer les problèmes audio dans l’enregistrement lors de l’affichage du menu **Démarrer** .
- Amélioration de la stabilité des hologrammes dans les vidéos enregistrées.
- Résolution d’un problème où la capture de la réalité mixte n’a pas pu enregistrer la vidéo après que l’appareil a quitté l’état de veille pendant plusieurs jours.
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity. Ce comportement permet d’éviter un problème qui provoquait l’interruption de certaines applications lorsque le visière a été retournée, même si le paramètre « exécuter en arrière-plan » a été activé. L’API est maintenant activée pour Unity 2018.4.18 et versions ultérieures et 2019.3.4 et versions ultérieures.
- Quand vous accédez au portail des appareils via une connexion Wi-Fi, un navigateur Web peut empêcher l’accès à en raison d’un certificat non valide. Le navigateur peut signaler une erreur telle que « ERR_SSL_PROTOCOL_ERROR », même si le certificat de l’appareil a été approuvé précédemment. Dans ce cas, vous ne pouvez pas progresser vers le portail de l’appareil, car il n’est pas possible d’ignorer les avertissements de sécurité. Cette mise à jour a résolu le problème. Si le certificat de l’appareil a été précédemment téléchargé et approuvé sur un PC pour supprimer les avertissements de sécurité du navigateur et que l’erreur SSL se produit, le nouveau certificat doit être téléchargé et approuvé pour résoudre les avertissements de sécurité du navigateur.
- Activation de la possibilité de créer un package d’approvisionnement d’exécution qui peut installer une application à l’aide de packages MSIX.
- Ajout d’un paramètre dans **paramètres**  >    >  **hologrammes** système qui permet aux utilisateurs de supprimer automatiquement tous les hologrammes de la réalité mixte lorsque l’appareil s’arrête.
- Correction d’un problème qui provoquait des applications HoloLens qui modifient leur format de pixel pour restituer le noir dans l’émulateur HoloLens.
- Correction d’un bogue qui provoquait un incident lors de la connexion à iris.
- Correction d’un problème concernant les téléchargements de magasins répétés pour les applications déjà en cours.
- Correction d’un bogue pour empêcher les applications immersives d’ouvrir Microsoft Edge à plusieurs reprises.
- Correction d’un problème avec les lancements de l’application photos au démarrage initial après la mise à jour à partir de la version 1903.
- Amélioration des performances et de la fiabilité.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows holographique, version 1903-mise à jour du 2020 du 1er juin
- Build 18362,1064

Améliorations et correctifs de la mise à jour :

- Les enregistreurs MRC personnalisés ont de nouvelles valeurs par défaut pour certaines propriétés s’ils ne sont pas spécifiés.
  - Sur l' *effet de la vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (casque immersif))
  - Sur l' *effet audio MRC*:
    - LoopbackGain (la valeur actuelle « gain audio de l’application » sur la page de capture de la réalité mixte dans le portail d’appareils Windows)
    - MicrophoneGain (valeur actuelle « gain audio mic » sur la page de capture de la réalité mixte dans le portail d’appareils Windows)
- L’API HolographicSpace. UserPresence est généralement désactivée pour les applications Unity. Ce comportement évite un problème qui provoque l’interruption de certaines applications lorsque le visière est retournée, même si le paramètre à exécuter en arrière-plan est activé. L’API est maintenant activée pour Unity 2018.4.18 et versions ultérieures, et 2019.3.4 et versions ultérieures.
- Correction d’un problème qui provoquait des applications HoloLens qui modifient leur format de pixel pour restituer le noir dans l’émulateur HoloLens.
- Correction d’un problème concernant les lancements de l’application photos au démarrage initial après la mise à jour à partir de la version 1903.

## <a name="windows-holographic-version-2004"></a>Windows holographique, version 2004  
- Build-19041,1103

La mise à jour logicielle de mai 2020 pour HoloLens 2, *Windows holographique, version 2004* comprend un grand nombre de nouvelles fonctionnalités passionnantes, telles que la prise en charge de Windows AutoPilot, le mode sombre de l’application, la prise en charge USB Ethernet pour les points d’accès 5 5G/LTE, et bien plus encore. Pour effectuer une mise à jour vers la dernière version, ouvrez l’application **paramètres**   , accédez à  **mettre à jour & sécurité**, puis sélectionnez le bouton  **Rechercher les mises à jour**   . 

|             Fonctionnalité                              |          Description                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Préconfigurer et configurer en toute transparence de nouveaux appareils pour la production à l’aide de Windows AutoPilot                 |
|       Support « Rex 2 »                             |          Prise en charge des clés de sécurité FIDO2 pour activer l’authentification rapide et sécurisée pour les appareils partagés            |
|       Approvisionnement amélioré                      |          Appliquer en toute transparence un package d’approvisionnement à partir d’un lecteur USB à votre HoloLens                              |
|       État de l’installation de l’application                 |          Vérifier l’état de l’installation dans l’application paramètres pour les applications ont été transmises à HoloLens 2 via MDM               |
|       Fournisseurs de services de configuration (CSP)   |          Ajout de nouveaux fournisseurs de service de configuration pour améliorer les fonctionnalités de contrôle d’administration                 |
|       Support USB 5G/LTE                       |          La fonctionnalité Ethernet USB étendue active la prise en charge de 5G/LTE                                    |
|       Mode d’application sombre                              |          Mode d’application sombre disponible pour les applications qui prennent en charge les modes sombre et clair, améliorant ainsi l’expérience d’affichage        |
|       Commandes vocales                             |          Prise en charge d’autres commandes système vocales pour contrôler les mains libres de HoloLens                           |
|       Améliorations du suivi de la main                 |          Les améliorations du suivi de la main rendent les boutons et les interactions 2D ardoise plus précis                        |
|       Améliorations et correctifs de qualité                 |          Diverses améliorations des performances et de la fiabilité du système sur l’ensemble de la plateforme                            |

### <a name="support-for-windows-autopilot"></a>Prise en charge de Windows AutoPilot

Windows AutoPilot pour HoloLens 2 permet au canal de vente de l’appareil de préinscrire HoloLens dans votre locataire Intune. Lorsque les appareils arrivent, ils sont prêts à être déployés automatiquement en tant qu’appareils partagés sous votre locataire. Pour tirer parti du déploiement automatique, l’appareil doit se connecter à un réseau au premier écran de l’installation à l’aide d’une connexion USB-C à Ethernet.

Une fois qu’un utilisateur a démarré le processus de déploiement automatique AutoPilot, le processus effectue les étapes suivantes :

1. Joignez l’appareil à Azure Active Directory (Azure AD).
1. Utilisez Azure AD pour inscrire l’appareil dans Microsoft Intune (ou un autre service MDM).
1. Téléchargez les stratégies ciblées par l’appareil, les certificats et les profils de mise en réseau.
1. Approvisionnez l’appareil.
1. Présentez l’écran de connexion à l’utilisateur.

Pour en savoir plus, consultez le [Guide d’évaluation de Windows AutoPilot pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Contactez votre responsable de compte pour participer à la préversion de la version préliminaire AutoPilot. Les appareils AutoPilot-prêts seront bientôt expédiés.*

### <a name="fido2-security-key-support"></a>Prise en charge des clés de sécurité FIDO2

Certains utilisateurs partagent un appareil HoloLens avec d’autres personnes dans un environnement professionnel ou scolaire. Il est donc important que les utilisateurs puissent facilement sans taper des noms d’utilisateur et des mots de passe longs. L’identité rapide en ligne (Rex) permet à toute personne de votre organisation (Azure AD locataire) de se connecter en toute transparence à HoloLens sans entrer de nom d’utilisateur ou de mot de passe.

Les clés de sécurité FIDO2 sont une méthode d’authentification sans mot de passe basée sur des normes, qui peut se présenter sous n’importe quel facteur de forme. Le Rex est une norme ouverte pour l’authentification par mot de passe. Elle permet aux utilisateurs et aux organisations de se connecter à leurs ressources sans nom d’utilisateur ou mot de passe. Au lieu de cela, ils utilisent une clé de sécurité externe ou une clé de plateforme intégrée à un appareil.

Pour commencer, consultez Activer la connexion à la [clé de sécurité avec mot de passe](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Amélioration de l’inscription MDM via le package de provisionnement

Les packages de provisionnement vous permettent de définir la configuration de HoloLens via un fichier de configuration plutôt que par le biais de l’expérience out-of-Box HoloLens. Auparavant, les packages d’approvisionnement devaient être copiés dans la mémoire interne HoloLens. Désormais, ils peuvent se trouver sur un lecteur USB afin d’être plus faciles à réutiliser sur plusieurs appareils HoloLens et vous pouvez approvisionner des appareils en parallèle. Les packages d’approvisionnement prennent désormais également en charge un champ à inscrire dans la gestion des appareils. il n’y a donc pas de configuration manuelle après l’approvisionnement.

Pour essayer :

1. Téléchargez la dernière version du concepteur de configuration Windows à partir du Windows Store sur votre PC.
1. Sélectionnez **approvisionner les appareils hololens**  >  **approvisionner les appareils hololens 2**.
2. Générez votre profil de configuration. Copiez ensuite tous les fichiers qui ont été créés sur un périphérique de stockage USB-C.
3. Branchez l’appareil USB-C dans un HoloLens récemment mis à l’État. Appuyez ensuite sur les boutons de réduction de l’alimentation du **volume**  +   pour appliquer votre package d’approvisionnement.

### <a name="line-of-business-application-install-status"></a>État de l’installation des applications métier

Le déploiement et la gestion d’applications MDM pour les applications métier sont essentiels à HoloLens. Les administrateurs et les utilisateurs doivent afficher l’état d’installation des applications pour l’audit et le diagnostic. Dans cette version, nous avons ajouté plus de détails dans **paramètres**  >  **comptes**  >  **accès professionnel ou école**  >  **cliquez sur les informations de votre compte**  >  .

### <a name="additional-csps-and-policies"></a>Fournisseurs de services de chiffrement et stratégies supplémentaires

Un [fournisseur de services de configuration (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) est une interface permettant de lire, de définir, de modifier ou de supprimer des paramètres de configuration sur un appareil. Dans cette version, nous ajoutons la prise en charge d’un plus grand nombre de stratégies pour augmenter les administrateurs de contrôle sur les appareils HoloLens déployés. Pour obtenir la liste des fournisseurs de services de chiffrement pris en charge par HoloLens, consultez [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Nouveautés dans cette version :

**Fournisseur CSP Policy** 

Le fournisseur de services de configuration de stratégie permet à l’entreprise de configurer des stratégies sur les appareils Windows. Dans cette version, nous avons ajouté de nouvelles stratégies pour HoloLens, qui sont répertoriées ici. Pour plus d’informations, consultez [fournisseurs de stratégies pris en charge par HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**CSP NetworkQoSPolicy**

Le fournisseur de services de configuration NetworkQoSPolicy crée des stratégies de qualité de service (QoS) réseau. Une stratégie de QoS effectue un ensemble d’actions sur le trafic réseau en fonction d’un ensemble de conditions de correspondance. Pour plus d’informations, consultez [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Prise en charge Ethernet USB étendue pour les appareils attachés 5G/LTE

La prise en charge a été ajoutée pour permettre à certains appareils haut débit mobile, tels que les téléphones 5G/LTE et les zones réactives Wi-Fi, quand ils sont attachés à HoloLens 2 via USB. Ces appareils sont désormais affichés dans **paramètres réseau** comme une autre connexion Ethernet. (Les périphériques haut débit mobile qui requièrent un pilote externe ne sont pas pris en charge.) Cette fonctionnalité permet des connexions à bande passante élevée lorsque Wi-Fi n’est pas disponible et que Wi-Fi la connexion n’est pas suffisamment performante. Pour en savoir plus sur les périphériques USB pris en charge, consultez [se connecter à des périphériques Bluetooth et USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Améliorations du suivi de la main

Cette version comprend plusieurs améliorations de suivi de la main :

- **Point de stabilité de pose :** Le système résiste maintenant au doigt de l’index lorsqu’il est bloqués par le Palm. Cette modification améliore la précision quand vous appuyez sur les boutons, tapez, faites défiler le contenu et bien plus encore. 
- **Réduction des pressions d’air accidentelles :** Nous avons amélioré la détection du mouvement d’appui sur l’air. Il y a maintenant moins d’activations accidentelles dans plusieurs scénarios courants, par exemple lorsque vous déposez vos mains sur vos côtés.
- **Fiabilité du changement d’utilisateur :** Le système est maintenant plus rapide et plus fiable lors de la mise à jour de la taille de la main lorsque vous partagez un appareil.
- **Réduction du vol de la main :** Nous avons amélioré la gestion des cas où il y a plus de deux mains en vue des capteurs. Si plusieurs personnes travaillent à proximité, il y a maintenant une plus grande probabilité que la main « passe » de l’utilisateur à la main d’une autre personne dans la scène.
- **Fiabilité du système :** Correction d’un problème qui entraînait l’arrêt du suivi de la main lorsque l’appareil est soumis à une charge élevée.

### <a name="dark-mode"></a>Mode sombre

De nombreuses applications Windows prennent désormais en charge les modes sombre et clair. Les utilisateurs de HoloLens 2 peuvent choisir le mode par défaut pour les applications qui prennent en charge les deux. Après la mise à jour, le mode d’application par défaut est « Dark », mais vous pouvez facilement modifier ce paramètre : accédez à **paramètres**  >    >  **couleurs** système  >  **choisir votre mode d’application par défaut**. 

Ces applications « intégrées » prennent en charge le mode sombre : 

- Paramètres 
- Microsoft Store 
- Messagerie 
- Calendrier 
- Explorateur de fichiers 
- Hub de commentaires 
- OneDrive 
- Photo 
- Visionneuse 3D 
- Films et TV 

![Fenêtres en mode sombre en mosaïque](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Commandes vocales du système

Vous pouvez désormais utiliser des commandes vocales avec n’importe quelle application sur l’appareil. Pour plus d’informations, consultez [utiliser votre voix pour utiliser HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Voir également [les langues prises en charge pour HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Mises à jour Cortana

L’application mise à jour s’intègre à Microsoft 365 pour vous aider à mieux travailler sur vos appareils (actuellement en US-English uniquement). Sur HoloLens 2, Cortana ne prend plus en charge certaines commandes spécifiques à l’appareil, telles que l’ajustement du volume ou le redémarrage. Ces options sont désormais prises en charge par les nouvelles commandes du système vocal. En savoir plus sur la nouvelle application Cortana dans notre [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Améliorations et correctifs de qualité

Améliorations et correctifs également dans la mise à jour :  
- A introduit un système d’étalonnage d’affichage actif. Cette fonctionnalité améliore la stabilité et l’alignement des hologrammes. Ils restent désormais en place lorsque vous déplacez votre tête d’un côté à l’autre.
- Correction d’un bogue dans lequel la diffusion en continu de Wi-Fi vers HoloLens a été interrompue régulièrement. Si une application indique qu’elle a besoin d’une diffusion en continu à faible latence, implémentez le correctif en appelant la [fonction SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correction d’un blocage d’appareil qui s’est produit pendant le streaming en mode de recherche.
- Correction d’un bogue dans lequel, dans certains cas, l’utilisateur approprié ne s’affichait pas sur l’écran de connexion lors de la reprise d’une session.
- Résolution d’un problème où les utilisateurs ne pouvaient pas exporter les journaux MDM via les **paramètres**.
- Correction d’un problème où la précision du suivi oculaire juste après la configuration out-of-Box peut être inférieure à celle attendue.
- Correction d’un problème où le sous-système de suivi oculaire n’a pas pu initialiser ou effectuer un étalonnage dans certaines conditions.
- Correction d’un problème où l’étalonnage oculaire serait invité à fournir un utilisateur déjà étalonné.
- Résolution d’un problème qui entraînait le blocage d’un pilote pendant l’étalonnage oculaire.
- Correction d’un problème où les pressions répétées du bouton d’alimentation pouvaient entraîner un incident système et un blocage de l’interpréteur de commandes de 60 secondes.
- Stabilité améliorée pour les mémoires tampons de profondeur.
- Ajout d’un bouton de **partage** dans le hub de commentaires afin que les utilisateurs puissent partager plus facilement les commentaires.
- Correction d’un bogue où RoboRaid wan’t a été correctement installé.

### <a name="known-issues"></a>Problèmes connus

- Un problème avec la langue du système zh-CN empêche les commandes vocales d’effectuer une capture de réalité mixte ou d’afficher l’adresse IP de l’appareil.
- Un problème nécessite que vous lançiez l’application Cortana après avoir démarré l’appareil pour utiliser l’activation vocale « Hey Cortana ». Si vous avez mis à jour à partir d’une build 18362, vous pouvez également voir une deuxième vignette d’application pour la version précédente de l’application Cortana qui ne fonctionne plus dans **Start**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows holographique, version 1903-mai 2020 mise à jour 
- Build 18362,1061

Cette mise à jour de qualité mensuelle ne contient pas de modifications notables, car l’équipe travaillait sur la version 2004 de Windows holographique peut être mise à jour, comme décrit précédemment.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows holographique, version 1903-mise à jour du 2020 d’avril
- Build 18362,1059

**Mode sombre pour les applications prises en charge** 

De nombreuses applications Windows prennent en charge les modes Dark et Light. Les clients HoloLens 2 peuvent désormais choisir le mode par défaut pour les applications qui prennent en charge les deux modèles de couleurs. En fonction des commentaires des clients, nous définissons le mode d’application par défaut sur « Dark », mais vous pouvez facilement modifier ce paramètre à tout moment : accédez à **paramètres > système > couleurs** pour trouver **« Choisissez votre mode d’application par défaut ».**

Ces applications « intégrées » prennent en charge le mode sombre :
- Paramètres
- Microsoft Store
- Messagerie
- Calendrier
- Explorateur de fichiers
- Hub de commentaires
- OneDrive
- Photo
- Visionneuse 3D
- Films et TV

**Améliorations et correctifs également dans la mise à jour :** 
- Assurez-vous que les superpositions de Shell sont incluses dans les captures de réalité mixte.
- Les développeurs non réels peuvent désormais utiliser la page de vue 3D du portail de l’appareil pour tester et déboguer leurs applications.
- Stabilité améliorée des hologrammes dans la capture de réalité mixte lorsque l’algorithme *HolographicDepthReprojectionMethod DepthReprojection* est utilisé.
- Correction de l’erreur « classe d’API IStreamSocketListener WinRT non inscrite » sur les applications ARM 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows holographique, version 1903-mise à jour du 2020 du 1er mars 
- Build 18362,1056

Améliorations et correctifs de la mise à jour :

- Stabilité améliorée des hologrammes dans la capture de réalité mixte lorsque l’algorithme *Autoplanaire HolographicDepthReprojectionMethod* est utilisé.
- Assurez-vous que le système de coordonnées attaché à un échantillon Depth MF est cohérent avec la documentation publique.
- Amélioration de la productivité des développeurs en permettant aux clients de coller de grandes quantités de texte via le portail des appareils.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows holographique, version 1903-mise à jour du 2020 du 1er février 
- Build 18362,1053

Améliorations et correctifs de la mise à jour :

- Désactivation temporaire de l’API HolographicSpace. UserPresence pour les applications Unity. Cette modification permet d’éviter un problème qui provoquait l’interruption de certaines applications lorsque le visière a été retournée, même si le paramètre « exécuter en arrière-plan » a été activé.
- Correction d’un incident utilisation À domicile aléatoire provoqué par le suivi des mains, dans lequel l’utilisateur a remarqué un blocage de l’interface utilisateur, puis revient au shell après plusieurs secondes.
- Amélioration du suivi de la main. ainsi, lorsque vous surveillez votre index, la partie supérieure de ce doigt est moins susceptible de s’effectuer de façon inattendue.
- Fiabilité améliorée du suivi des têtes, du mappage spatial et d’autres runtimes.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows holographique, version 1903-mise à jour du 1er janvier 2020 
- Build 18362,1043
 
Améliorations et correctifs de la mise à jour :

- Amélioration de la stabilité des applications exclusives lors de l’utilisation de l’émulateur HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows holographique, version 1903-mise à jour de décembre 2019 
- Build 18362,1042

Améliorations et correctifs de la mise à jour :

- A introduit les correctifs de la reproduction de dernière étape (LSR). Amélioration du rendu visuel des hologrammes pour un affichage plus stable et plus clair en tenant compte plus précisément de leur profondeur. Ce symptôme sera plus perceptible après cette mise à jour si les applications ne définissent pas correctement la profondeur des hologrammes.
- Correction de la stabilité des applications exclusives et de la navigation entre les applications exclusives.
- Résolution d’un problème où la capture de la réalité mixte n’a pas pu enregistrer la vidéo une fois que l’appareil était en état de veille pendant plusieurs jours.
- Stabilité améliorée de l’hologramme.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows holographique, version 1903-mise à jour du 2019 du 1er novembre 
- Build 18362,1039

Améliorations et correctifs de la mise à jour :

- Correction des fonctionnalités des commandes vocales **Select** lors de la configuration initiale de en-ca et en-au.
- Amélioration de la qualité visuelle des objets placés loin dans les versions les plus récentes Unity et MRTK (Mixed Reality Toolkit).
- Résolution des problèmes d’adressage avec les applications holographiques bloquées dans un état suspendu au démarrage jusqu’à l’ouverture et la fermeture du menu Démarrer.
- Correctifs et améliorations de la conformité du runtime OpenXR pour HoloLens 2 et l’émulateur.
