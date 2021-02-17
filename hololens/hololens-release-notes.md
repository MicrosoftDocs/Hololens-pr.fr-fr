---
title: Notes de publication HoloLens 2
description: Restez à jour avec toutes les mises à jour de chaque nouvelle version holoLens 2.
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
ms.openlocfilehash: 7ab8eede6e48ed1a6cb4584188a80adbd832c169
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340553"
---
# Notes de publication HoloLens 2

Pour vous assurer que vous disposez d’une expérience productive avec vos appareils HoloLens, nous continuons à publier des mises à jour de fonctionnalités, de bogues et de sécurité. Sur cette page, vous pouvez voir les nouveautés de HoloLens chaque mois. Pour obtenir la dernière mise à jour [](hololens-update-hololens.md#check-for-updates-and-manually-update) HoloLens 2, vous pouvez soit vérifier les mises à jour et les mettre à jour manuellement, soit obtenir la mise à jour flash complète (FFU) pour flasher votre appareil [via Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). Le [téléchargement](https://aka.ms/hololens2download) est tenu à jour et fournit la dernière version généralement disponible.

>[!NOTE]
> Nous sommes ravis de commencer à lancer à nouveau la mise en flight de nouvelles fonctionnalités pour les Windows Insiders. Nous allons mettre en version d’essai le canal de développement pour les dernières mises à jour. Nous continuerons à lire nos [**notes HoloLens Insider**](hololens-insider.md) à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider. Soyez ravis et prêt à combiner ces mises à jour dans votre réalité.

Consultez les notes de publication associées :

- [Visiter l’archive de l’émulateur HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## Windows Holographic, version 20H2 - Mise à jour de février 2021
- Build 19041.1136

Améliorations et correctifs de la mise à jour :

- Résout un problème autour de la configuration initiale de l’appareil et du stockage des mises à jour d’application.
- Résout un problème autour des mises à niveau et des vols pour les mises à jour holoLens ultérieures.
- Suppression des certificats préinstallés inutilisés du magasin racine eSIM des appareils HoloLens.

## Windows Holographic, version 1903 - Mise à jour de février 2021
- Build 18362.1098

Cette mise à jour de qualité mensuelle ne contient aucune modification notable. Nous vous encourageons à tester nos dernières versions pour Windows Holographic, version 2004.

## Windows Holographic, version 20H2 - Mise à jour de janvier 2021
- Build 19041.1134

Améliorations et correctifs de la mise à jour :

- Performances améliorées lors du démarrage, de la reprise et du changement d’utilisateur lorsqu’il y a de nombreux utilisateurs sur l’appareil.
- Ajout de la prise en charge d’Arm32 [pour le mode Recherche.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## Windows Holographic, version 1903 - Mise à jour de janvier 2021
- Build 18362.1091

Cette mise à jour de qualité mensuelle ne contient aucune modification notable. Nous vous encourageons à tester nos dernières versions pour Windows Holographic, version 2004.

## Windows Holographic, version 20H2 – Mise à jour de décembre 2020
- Build 19041.1131

### Installer des applications sur HoloLens 2 via le programme d’installation d’application

Nous **ajoutons une nouvelle fonctionnalité (Programme** d’installation d’application) pour vous permettre d’installer des applications de façon plus transparente sur vos appareils HoloLens 2. La fonctionnalité sera sur par défaut pour les appareils **nonmanagés.** Pour éviter toute perturbation pour les entreprises, le programme d’installation d’application ne sera pas disponible pour les appareils **gérés** pour le moment.  

Un appareil est considéré comme « géré » si **l’une** des valeurs suivantes est vraie :
- Inscrit à la [gestion des mdm](hololens-enroll-mdm.md)
- Configuré avec le [package d’approvisionnement](hololens-provisioning.md)
- [L’identité de l’utilisateur](hololens-identity.md) est Azure AD

Vous pouvez désormais installer des applications sans avoir à activer le mode développeur ou à utiliser Device Portal.  Téléchargez simplement (via USB ou Via Edge) le fichier groupé Appx sur votre appareil et accédez à l’ensemble d’applications dans l’Explorateur de fichiers pour être invité à lancer l’installation.  Vous pouvez également [lancer une installation à partir d’une page web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Tout comme les applications que vous installez à partir du Microsoft Store ou chargez une version [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) de version [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) à l’aide de la fonctionnalité de déploiement d’applications LOB de MDM, les applications doivent être signées numériquement avec l’outil de signature et le certificat utilisé pour la signature doit être approuvé par l’appareil HoloLens avant que l’application puisse être déployée.

**Instructions d’installation de l’application.**

1.  S’assurer que votre appareil n’est pas considéré comme géré
1.  Assurez-vous que votre appareil HoloLens 2 est alimenté et connecté à votre PC
1.  Assurez-vous que vous êtes connecté à l’appareil HoloLens 2
1.  Sur votre PC, accédez à votre application personnalisée et copiez votre application.appxbundle dans votredevicename\Stockage interne\Téléchargements.   Une fois que vous avez terminé la copie de votre fichier, vous pouvez déconnecter votre appareil
1.  À partir de votre appareil HoloLens 2, ouvrez le menu Démarrer, sélectionnez Toutes les applications et lancez l’application Explorateur de fichiers.
1.  Accédez au dossier Téléchargements. Dans le panneau gauche de l’application, sélectionnez d’abord Cet appareil, puis accédez à Téléchargements.
1.  Sélectionnez le fichier yourapp.appxbundle.
1.  Le programme d’installation d’application se lance. Sélectionnez le bouton Installer pour installer votre application.
L’application installée se lance automatiquement à la fin de l’installation.

Vous trouverez des exemples d’applications [sur Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) pour tester ce flux.

Découvrez le processus complet [d’installation des applications sur HoloLens 2 avec le programme d’installation d’application.](app-deploy-app-installer.md)  

![Installation d’exemples MRTK via le programme d’installation d’application](images/hololens-app-installer-picture.jpg)

### Améliorations et correctifs de la mise à jour :

- Le suivi des mains conserve désormais le suivi dans de nombreux nouveaux cas où la main aurait été perdue précédemment.  Dans certains de ces nouveaux cas, seule la position de la paume continue de se mettre à jour en fonction de la main réelle de l’utilisateur, tandis que les autres joints sont déduites en fonction d’une pose précédente.  Cette modification permet d’améliorer la cohérence du suivi dans les mouvements tels que les mouvements de frappe, de projection, de frappe et de frappe.  Cela aide également dans les cas où la main est proche d’une surface ou lorsqu’elle maintient un objet.  Lorsque les joints de main sont déduits, la valeur de précision par [joint](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) est définie sur « Approximate » au lieu de « High ».
- Nous avons résolu un problème dans lequel la réinitialisation du code confidentiel pour les comptes Azure AD afficherait une erreur « Un problème s’est produit.
- Les utilisateurs doivent voir beaucoup moins d’incidents OOBE après le démarrage lors du lancement d’ET, d’Iris à partir de l’application paramètres, d’un nouvel utilisateur ou d’un toast de notification.
- Les utilisateurs doivent avoir un fuseau horaire correct sortant de la zone OOBE.

## Windows Holographic, version 1903 – Mise à jour de décembre 2020
- Build 18362.1088

Cette mise à jour qualité mensuelle ne contient pas de modifications notables. Nous vous encourageons à tester notre dernière version de Windows Holographique, version 20H2 – Mise à jour de décembre 2020 et la nouvelle fonctionnalité du programme d’installation d’application ajoutée dans la build.


## Windows Holographic, version 20H2
- Build 19041.1128

Windows Holographic, version 20H2 est désormais disponible et offre un grand nombre de nouvelles fonctionnalités aux utilisateurs et aux professionnels de l’informatique HoloLens 2. Du positionnement de l’œil automatique au Gestionnaire de certificats dans les paramètres, en aux fonctionnalités améliorées du mode plein écran et aux nouvelles fonctionnalités d’installation d’Autopilot. Cette nouvelle mise à jour permet aux équipes techniques de prendre un contrôle plus granulaire sur la configuration et la gestion des appareils HoloLens, et offre aux utilisateurs des expériences holographiques encore plus transparentes. 

Cette dernière version est une mise à jour mensuelle vers la version 2004, mais cette fois, nous inséons de nouvelles fonctionnalités. Le numéro de build principal reste le même et Windows Update indique une version mensuelle vers la version 2004 (build 19041). Vous pouvez examiner votre numéro de build dans votre écran Paramètres > À propos de l’écran pour confirmer que vous êtes sur la dernière version disponible 19041.1128+. Pour mettre à jour la dernière version, ouvrez l’application Paramètres, & Sécurité des mises à jour, puis appuyez sur Vérifier les mises à jour. Pour plus d’informations sur la gestion des mises à jour HoloLens, visitez [cette page.](https://docs.microsoft.com/hololens/hololens-updates)

### Nouveautés de Windows Holographic, version 20H2  

| Fonctionnalité                                              | Description                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Prise en charge automatique de la position des yeux](hololens-release-notes.md#auto-eye-position-support) | Calcule activement les positions oculaires sans que les utilisateurs ne traversent l’étalonnage du suivi oculaire.   |
| [Gestionnaire de certificats](hololens-release-notes.md#certificate-manager)   | Permet aux nouvelles méthodes plus simples d’installer et de supprimer des certificats de l’application Paramètres.     |
| [Mise en service de lancement automatique à partir du port USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Les packages d’approvisionnement sur les lecteurs USB invitent automatiquement la page d’approvisionnement en OOBE.                                                         |
| [Confirmer automatiquement les packages d’approvisionnement en mode OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Les packages d’approvisionnement sont automatiquement appliqués lors de la OOBE à partir de la page d’approvisionnement.                                                         |
| [Approvisionnement automatique sans utilisation de l’interface utilisateur](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Comment combiner le lancement automatique de l’approvisionnement et la confirmation automatique. |
| [Utilisation d’Autopilot avec Wi-Fi connexion](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Utilisez autopilot à partir de l'Wi-Fi sans avoir besoin d’adaptateur ethernet. |
| [CSP Tenantlockdown et Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Après l’inscription du client et l’application de la stratégie, l’appareil ne peut être inscrit dans ce client que chaque fois que l’appareil est réinitialisé ou flashé à nouveau. |
| [Accès global affecté](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nouvelle méthode de configuration pour le mode plein écran de plusieurs applications qui applique la borne au niveau du système, ce qui le rend applicable à tous.                  |
| [Lancer automatiquement une application dans une borne multi-applications](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Définit une application à lancer automatiquement lors de la signature en mode plein écran multi-application.                                                        |
| [Modifications du comportement du mode plein écran pour la gestion des défaillances](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | L’échec du mode plein écran a désormais un retour restrictif.                                                                                                |
| [Stratégies HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nouvelles stratégies pour HoloLens.     |
| [Mettre en cache l’appartenance au groupe Azure AD pour kiosque hors connexion](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nouvelle stratégie permet aux utilisateurs d’utiliser le cache d’appartenance à un groupe pour utiliser le mode plein écran hors connexion pendant un nombre de jours donné.                                        |
| [Nouvelles stratégies de restriction d’appareil pour HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Stratégies de gestion des appareils récemment activées pour HoloLens 2.                                                                                |
| [Nouvelles stratégies d’alimentation pour HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Stratégies nouvellement prise en charge pour les paramètres de délai d’alimentation.  |
| [Mettre à jour des stratégies](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Stratégies nouvellement activées permettant de contrôler les mises à jour.           |
| [Visibilité de la page Paramètres activés pour HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Stratégie de sélection des pages visibles dans l’application Paramètres.             |
| [Mode Recherche](hololens-release-notes.md#research-mode) | Utilisation du mode Recherche sur HoloLens 2. |
| [Augmentation de la longueur de l’enregistrement](hololens-release-notes.md#recording-length-increased) | Les enregistrements MRC ne sont plus limité à 5 minutes. |
| [Améliorations et correctifs de la mise à jour](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correctifs supplémentaires dans la mise à jour.   |

### Prise en charge Automatique de la Position des Yeux

Dans HoloLens 2, les positions des yeux permettent un positionnement précis des hologrammes, un affichage confortable et une meilleure qualité d’affichage. Les positions des yeux sont calculées en interne dans le cadre du calcul du suivi oculaire. Toutefois, cela nécessite que chaque utilisateur parcourt le calibrage du suivi oculaire, même lorsque l’utilisation ne nécessite pas le pointage du regard.

La **Position Automatique des Yeux** permet à ces scénarios sans interaction de calculer la position des yeux de l’utilisateur. La Position automatique des yeux commence à fonctionner automatiquement en arrière-plan dès que l’utilisateur allume l’appareil. Si l’utilisateur n’a pas encore effectué de suivi oculaire, la Position Automatique des Yeux commencera à fournir la position des yeux de l’utilisateur au système d’affichage après un temps de traitement de 20 à 30 secondes. Les données utilisateur ne sont pas conservées sur l’appareil et, par conséquent, ce processus est répété si l’utilisateur éteint l’appareil puis le rallume ou si l’appareil redémarre ou sort du mode veille.

Il existe certaines modifications de comportement système avec la fonctionnalité de position automatique des yeux quand un utilisateur n’ayant pas effectué de calibrage utilise l’appareil. Dans ce contexte, un utilisateur non calibré fait référence à une personne qui n’a pas encore parcouru le processus de calibrage du suivi oculaire sur l’appareil.

| Application active | Comportement Antérieur | Comportement de Windows Holographique, version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Application non compatible avec le regard ou Holographic Shell |Affichage du dialogue de l’invite de calibrage du suivi oculaire. | Aucune invite n’est affichée. |
| Application compatible avec le regard | Affichage du dialogue de l’invite de calibrage du suivi oculaire. | L’invite de calibrage du suivi oculaire s’affiche uniquement lorsque l’application accède à un flux du regard. |

Si l’utilisateur passe d’une application non compatible avec le regard à une application qui accède aux données du regard, l’invite de calibrage s’affiche. 

Tout autre comportement du système est semblable à celui d’un utilisateur actuel n’ayant pas de calibrage du suivi oculaire actif. Par exemple, le geste de démarrage à une main ne sera pas activé. Aucune modification n’est apportée aux fonctionnalités Out-Of-Box-Experience de la configuration initiale.

Dans le cas d’expériences nécessitant des données du regard ou un positionnement d’hologramme très précis, nous conseillons aux utilisateurs sans calibrage d’exécuter le calibrage du suivi oculaire. Vous pouvez y accéder à partir de l’invite de calibrage du suivi oculaire ou en lançant l’application des Paramètres à partir du menu de démarrage, puis en sélectionnant **Système > Calibration > Exécuter la calibration des yeux**.

Ces informations sont disponibles ultérieurement avec [d’autres informations d’étalonnage.](hololens-calibration.md#auto-eye-position-support) 

### Gestionnaire de certificats

- Amélioration des outils d’audit, de diagnostic et de validation pour la sécurité et la conformité des appareils via le nouveau Gestionnaire de certificats. Cette fonctionnalité vous permettra de déployer, dépanner et valider vos certificats à l’échelle des environnements commerciaux.

Dans Windows Holographic version 20H2, nous ajoutons un gestionnaire de certificats dans l’application Paramètres HoloLens 2. Go to **Settings > Update & Security > Certificates**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir que les appareils restent sécurisés et conformes. 

-   **Audit :** Possibilité de vérifier qu’un certificat est déployé correctement ou de confirmer qu’il a été supprimé correctement. 
-   **Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de résoudre les problèmes. 
-   **Validation :** Vérifier qu’un certificat a l’objectif et qu’il est fonctionnel peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux, avant de déployer des certificats à grande échelle.

Pour trouver rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher les propriétés de certificat individuelles, sélectionnez le certificat et cliquez sur **Informations.** 

L’installation de certificat prend actuellement en charge les fichiers .cer et .crt. Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel ;  Tous les autres utilisateurs peuvent uniquement s’installer dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer les certificats installés directement à partir de l’interface utilisateur paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

#### Pour installer un certificat : 

1.  Connectez votre HoloLens 2 à un PC.
1.  Placez le fichier de certificat que vous souhaitez installer à un emplacement sur votre HoloLens 2.
1.  Accédez **à Paramètres App > Update & Security > Certificates**et sélectionnez Installer un certificat.
1.  Cliquez **sur Importer un** fichier et accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **l’emplacement de la boutique.**
1.  Sélectionnez **magasin de certificats.**
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

#### Pour supprimer un certificat : 
1. Accédez à **Paramètres App > Update et Security > Certificates**.
1. Recherchez le certificat par nom dans la zone de recherche.
1. Sélectionnez le certificat.
1. Cliquez sur **Supprimer**
1. Sélectionnez **Oui** lorsque vous y invitez une confirmation.

![Visionneuse de certificats dans l’application Paramètres](images/certificate-viewer-device.jpg)

![Image montrant comment utiliser l’interface utilisateur certificat pour installer un certificat](images/certificate-device-install.jpg)

Ces informations sont disponibles plus loin [dans une nouvelle page gestionnaire de certificats.](certificate-manager.md)

### Mise en service de lancement automatique à partir du port USB

- Processus automatisés permettant de réduire l’interaction utilisateur, lorsque des lecteurs USB avec packages d’approvisionnement sont utilisés pendant la OOBE.

Avant cette version, les utilisateurs deviez lancer l’écran d’approvisionnement manuellement pendant la OOBE pour le mettre en service à l’aide d’une combinaison de boutons. Les utilisateurs peuvent maintenant ignorer la combinaison de boutons à l’aide d’un package d’approvisionnement sur un lecteur de stockage USB. 

1. Branchez le lecteur USB avec le package d’approvisionnement lors du premier moment interagi de la première OOBE
1. Lorsque l’appareil est prêt à être mis en service, il ouvre automatiquement l’invite avec la page d’approvisionnement. 

Remarque : si un lecteur USB est laissé branché pendant le démarrage de l’appareil, la OOBE édifiera le périphérique de stockage USB existant et observera les autres disques branchés.

Pour plus d’informations sur l’application de packages d’approvisionnement pendant la OOBE, consultez la documentation [d’approvisionnement HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Pour plus d’informations sur l’approvisionnement de lancement automatique à partir [d’un port USB,](hololens-provisioning.md#auto-launch-provisioning-from-usb) voir la documentation d’approvisionnement HoloLens.

### Confirmer automatiquement les packages d’approvisionnement en mode OOBE
- Processus automatisé permettant de réduire l’interaction utilisateur, lorsque la page Package d’approvisionnement s’affiche, elle applique automatiquement tous les packages répertoriés.

Lorsque l’écran principal d’approvisionnement se présente, la OOBE compte moins 10 secondes avant de commencer automatiquement à appliquer tous les packages d’approvisionnement. Les utilisateurs [peuvent toujours confirmer ou annuler](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) au cours de cette période de 10 secondes après avoir vérifié les packages attendus.

### Approvisionnement automatique sans utilisation de l’interface utilisateur
- Processus automatiques combinés pour réduire les interactions d’appareil pour l’approvisionnement. 

En combinant le lancement automatique de l’approvisionnement à partir de périphériques USB et la confirmation automatique des packages d’approvisionnement, un utilisateur peut mettre en service les appareils HoloLens 2 automatiquement sans utiliser l’interface utilisateur de l’appareil, ni même porter l’appareil. Vous pouvez continuer à utiliser le même lecteur USB et le même package d’approvisionnement pour plusieurs appareils. Cela est utile pour déployer plusieurs appareils à la fois dans la même zone. 

1. [Créez un package d’approvisionnement à l’aide](hololens-provisioning.md) [du Concepteur de configuration Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copiez le package sur un lecteur de stockage USB.
1. [Flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) vers [la build 19041.1361](https://aka.ms/hololens2previewdownload)ou une build plus nouvelle. 
1. Lorsque [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) a terminé de faire clignoter votre appareil pour débrancher votre câble USB-C. 
1. Branchez votre lecteur USB à l’appareil.
1. Lorsque l’appareil HoloLens 2 démarre en OOBE, il détecte automatiquement le package d’approvisionnement sur le lecteur USB et lance la page d’approvisionnement.
1. Au bout de 10 secondes, l’appareil applique automatiquement le package d’approvisionnement. 

Votre appareil est maintenant configuré et affiche [l’écran](hololens-provisioning.md#automatic-provisioning-without-using-ui)Configuration réussie.

### Utilisation d’Autopilot avec Wi-Fi connexion
- Suppression du besoin d’adaptateurs USB-C pour ethernet réduisant les besoins matériels, en permettant à Autopilot de fonctionner sur Wi-Fi appareils connectés.

Maintenant, pendant la OOBE, une fois que vous connectez HoloLens 2 au Wi-Fi, OOBE recherche un profil Autopilot pour l’appareil. S’il en trouve un, il sera utilisé pour terminer le reste du flux de participation et d’inscription AAD. En d’autres termes, l’utilisation d’ethernet en USB-C ou de Wi-Fi en adaptateur USB-C n’est plus obligatoire, mais elles continuent de fonctionner si elles sont fournies au début de la OOBE. En savoir plus [sur Autopilot pour les appareils HoloLens 2.](hololens2-autopilot.md)

### CSP Tenantlockdown et Autopilot
- Conserve les appareils sur le client de l’organisation en les verrouillant vers le client via la réinitialisation ou le redémarrage de l’appareil. Avec plus de sécurité en interdisant la création de compte via la configuration. 

Les appareils HoloLens 2 supportent désormais le programme CSP TenantLockdown à partir de [Windows Holographic version 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

Le CSP [TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) permet à HoloLens2 d’être lié à l’inscription de la gestion des périphériques mobiles à l’aide de Autpilot uniquement. Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur la valeur true ou false (initialement définie) sur HoloLens2, cette valeur reste sur l’appareil malgré le redémarrage, les mises à jour du système d’exploitation, etc. 

Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur true sur HoloLens2, l’application OOBE attend indéfiniment que le profil Autopilot soit téléchargé et appliqué avec succès, après la connectivité réseau. 

Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur true sur HoloLens2, les opérations suivantes ne sont pas autorisées dans l’application OOBE: 
- Créer un utilisateur local à l’aide de la configuration de l’exécution 
- Exécuter une opération de jointure Azure AD via la configuration de l’exécution 
- Sélectionner le propriétaire de l’appareil dans l’application OOBE 

#### Comment définir cette configuration à l’aide de Intune? 
1. Créez un profil de configuration de périphérique URI OMA personnalisé et spécifiez true pour le nœud RequireNetworkInOOBE comme indiqué ci-dessous.
La valeur OMA-URI doit être ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Définition du verrouillage du client via OMA-URI](images/hololens-tenant-lockdown.png)

1. Créez un groupe et attribuez le profil de configuration de périphérique à ce groupe d’appareils. 

1. Faites de l’appareil HoloLens2 un membre du groupe créé à l’étape précédente et déclenchez la synchronisation.  

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois que la configuration de l’appareil HoloLens 2 s’applique correctement, les effets de TenantLockdown seront actifs.

#### Comment annuler la configuration de RequireNetworkInOOBE de TenantLockdown sur HoloLens2 avec Intune? 
1. Supprimez HoloLens2 du groupe d’appareils auquel la configuration d’appareil créée ci-dessus a été précédemment affectée. 

1. Créez un profil de configuration de périphérique basé sur OMA URI personnalisé et spécifiez false pour RequireNetworkInOOBE comme indiqué ci-dessous. La valeur OMA-URI doit être ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de la définition de RequireNetworkInOOBE sur false via un URI OMA dans Intune](images/hololens-tenant-lockdown-false.png)

1. Créez un groupe et attribuez le profil de configuration de périphérique à ce groupe d’appareils. 

1. Faites de l’appareil HoloLens2 un membre du groupe créé à l’étape précédente et déclenchez la synchronisation.

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois la configuration de l’appareil HoloLens 2 appliquée, les effets de TenantLockdown seront désactivés. 

#### Que se passe-t-il pendant le processus OOBE, si le profil Autopilot n’est pas affecté sur un HoloLens après la définition de TenantLockdown sur true. 
L’application OOBE attend indéfiniment le téléchargement du profil AutoPilot et la boîte de dialogue suivante s’affichera. Afin de supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit auprès de son client d’origine à l’aide de Autopilot uniquement et RequireNetworkInOOBE doit être annulé comme décrit à l’étape précédente avant que les restrictions introduites par le CSP TenantLockdown ne soient supprimées. 

![Vue de l’appareil lorsque la stratégie est appliquée à l’appareil.](images/hololens-autopilot-lockdown.png)

Ces informations sont désormais disponibles avec le reste de Autopilot sous [CSP Tenantlockdown et Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### Accès affecté global – Mode plein écran
- Gestion réduite des identités pour Kiosk, en activant une nouvelle méthode Kiosk qui applique le mode plein écran au niveau du système.

Cette nouvelle fonctionnalité permet à un administrateur informatique de configurer un appareil HoloLens 2 pour le mode plein écran de plusieurs applications, qui s’applique au niveau du système, n’a aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se sont connectés à l’appareil. Découvrez cette nouvelle fonctionnalité en détail dans la borne [d’accès affecté globale HoloLens.](hololens-global-assigned-access-kiosk.md)

### Lancement automatique d’une application en mode plein écran multi-application 
- Expérience axée sur le lancement automatique d’application, ce qui augmente davantage l’interface utilisateur et les sélections d’applications choisies pour les expériences en mode plein écran.

S’applique uniquement au mode plein écran de plusieurs applications et une seule application peut être désignée pour le lancement automatique à l’aide de l’attribut en surbrillation ci-dessous dans la configuration Accès affecté. 

L’application est lancée automatiquement lorsque l’utilisateur se ouvre. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Modifications du comportement du mode plein écran pour la gestion des défaillances
- Mode plein écran plus sécurisé en éliminant les applications disponibles en cas de défaillance du mode plein écran. 

Précédemment, lors de la rencontre d’échecs lors de l’application du mode plein écran, HoloLens était utilisé pour afficher toutes les applications dans le menu Démarrer. Désormais, dans Windows Holographique version 20H2 en cas d’échec, aucune application ne s’affiche dans le menu Démarrer comme ci-dessous : 

![Image de l’apparence du mode plein écran en cas d’échec.](images/hololens-kiosk-failure-behavior.png )

### Stratégies HoloLens
- Options de gestion des appareils spécifiquement pour HoloLens créées pour la gestion de l’appareil. 

De nouvelles stratégies de réalité mixte ont été créées pour les appareils HoloLens 2 sur Windows Holographique version 20H2. Les nouveaux paramètres contrôlables incluent : la définition de la luminosité, la définition du volume, la désactivation de l’enregistrement audio dans les captures de réalité mixte, la définition du moment où les diagnostics peuvent être collectés et le cache d’appartenance au groupe AAD.  

| Nouvelle stratégie HoloLens                                | Description                                                                               | Remarques                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permet de désactiver les boutons de luminosité afin que le fait d’appuyer dessus ne modifie pas la luminosité.       | 1 Oui, 0 Non (par défaut)                                                |
| MixedReality\VolumeButtonDisabled                  | Permet de désactiver les boutons de volume afin que le fait d’appuyer dessus ne modifie pas le volume.               | 1 Oui, 0 Non (par défaut)                                                |
| MixedReality\MicrophoneDisabled                    | Désactive le microphone afin qu’aucun enregistrement audio ne soit possible sur HoloLens 2.                      | 1 Oui, 0 Non (par défaut)                                                |
| MixedReality\FallbackDiagnostics                   | Contrôle le comportement de collecte des journaux de diagnostic.                               | 0 Désactivé, 1 Activé pour les propriétaires d’appareils, 2 Activé pour tous (par défaut) |
| MixedReality\HeadTrackingMode                      | Réservé à une utilisation ultérieure.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Contrôle le nombre de jours d’utilisation du cache d’appartenance à un groupe Azure AD pour le ciblage de groupes Azure AD par kiosque. | Voir ci-dessous.                                                           |

### Mettre en cache l’appartenance au groupe Azure AD pour kiosque hors connexion
- Activé l’utilisation des kiosques hors connexion avec des groupes AAD pendant 60 jours.

Cette stratégie contrôle le nombre de jours pendant combien de jours, le cache d’appartenance aux groupes Azure AD est autorisé à être utilisé pour les configurations d’accès affecté ciblant des groupes Azure AD pour l’utilisateur. Une fois que cette valeur de stratégie est définie sur une valeur supérieure à 0 uniquement, le cache n’est pas utilisé dans le cas contraire.  

Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 jour  
Max - 60 jours 

Étapes pour utiliser cette stratégie correctement : 
1. Créez un profil de configuration d’appareil pour un kiosque ciblant des groupes Azure AD et affectez-le à des appareils HoloLens. 
1. Créez une configuration d’appareil OMA URI personnalisée qui définit cette valeur de stratégie sur le nombre de jours souhaité (> 0) et affectez-la à des appareils HoloLens. 
    1. La valeur d’URI doit être entrée dans la zone de texte OMA-URI en tant que ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. La valeur peut être entre min /max autorisée.
1. Inscrivez les appareils HoloLens et vérifiez que les deux configurations sont appliquées à l’appareil. 
1. Laissez l’utilisateur Azure AD 1 se connecter lorsqu’Internet est disponible, une fois que l’utilisateur s’est connecté et que l’appartenance au groupe Azure AD a été confirmée, le cache est créé. 
1. Désormais, l’utilisateur Azure AD 1 peut déconnecter HoloLens et l’utiliser en mode plein écran tant que la valeur de stratégie autorise X nombre de jours. 
1. Les étapes 4 et 5 peuvent être répétées pour n’importe quel autre utilisateur Azure AD N. Ici, tout utilisateur Azure AD doit se connecter à l’appareil à l’aide d’Internet. Nous pouvons donc déterminer au moins une fois qu’ils sont membres du groupe Azure AD sur lequel la configuration Kiosk est ciblée. 
 
> [!NOTE]
> Jusqu’à ce que l’étape 4 soit effectuée pour un utilisateur Azure AD, le comportement d’échec mentionné dans les environnements « déconnectés » se produit. 

### Nouvelles stratégies de restriction d’appareil pour HoloLens 2
- Permet aux utilisateurs de gérer des stratégies de gestion des appareils spécifiques, telles que le blocage de l’ajout ou de la suppression de packages d’approvisionnement.

Stratégies nouvellement activées qui autorisent davantage d’options de gestion des appareils HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Ces deux nouvelles polices pour AllowAddProvisioningPackage et AllowRemoveProvisioningPackage sont ajoutées à nos [restrictions d’appareil communes.](hololens-common-device-restrictions.md)

> [!NOTE]
> En ce [qui concerne RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), HoloLens ne prendra en charge que la configuration ./Vendor/MSFT/RemoteLock/Lock. Les configurations traitant du code confidentiel, telles que la réinitialisation et la récupération, ne sont pas prises en charge.

### Nouvelles stratégies d’alimentation pour HoloLens 2
- Plus d’options pour le moment où HoloLens est en veille ou se verrouille via des stratégies d’alimentation. 

Ces stratégies récemment ajoutées permettent aux administrateurs de contrôler les états d’alimentation, tels que le délai d’inactivité. Pour en savoir plus sur chaque stratégie individuelle, cliquez sur le lien de cette stratégie.

|     Lien de documentation sur la stratégie                |     Remarques                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Exemple de valeur à utiliser dans le Concepteur de configuration Windows, c’est-à-dire,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Exemple de valeur à utiliser dans le Concepteur de configuration Windows, c’est-à-dire,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Exemple de valeur à utiliser dans le Concepteur de configuration Windows, c’est-à-dire, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Exemple de valeur à utiliser dans le Concepteur de configuration Windows, c’est-à-dire, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Exemple de valeur à utiliser dans le Concepteur de configuration Windows, c’est-à-dire,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Exemple de valeur à utiliser dans le Concepteur de configuration Windows, c’est-à-dire,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Ces deux nouvelles stratégies pour DisplayOffTimeoutOnBattery et DisplayOffTimeoutPluggedIn sont ajoutées à nos [restrictions d’appareil communes.](hololens-common-device-restrictions.md)

> [!NOTE]
> Pour une expérience cohérente sur HoloLens 2, assurez-vous que les valeurs pour DisplayOffTimeoutOnBattery et StandbyTimeoutOnBattery sont définies comme valeur identique. Il en va de même pour DisplayOffTimeoutPluggedIn et StandbyTimeoutPluggedIn. [Reportez-vous aux périodes d’inactivité](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) d’affichage, de veille et de mise en veille prolongée pour plus d’informations sur la veille moderne.

### Stratégies de mise à jour nouvellement activées pour HoloLens
- Plus d’options pour l’installation des mises à jour ou la désactivation du bouton Suspendre les mises à jour pour garantir les mises à jour.

Ces stratégies de mise à jour sont désormais activées sur les appareils HoloLens 2 :
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Les détails complets sur ces stratégies de mise à jour et leur utilisation pour les appareils HoloLens sont consultables ici dans Gérer les mises à jour [HoloLens.](hololens-updates.md)

### Visibilité de la page Paramètres activés pour HoloLens 2
- Contrôle accru de l’interface utilisateur dans l’application Paramètres, qui peut être confondu pour afficher une sélection limitée de pages.

Nous avons maintenant activé une stratégie qui permet aux administrateurs informatiques d’empêcher que des pages spécifiques de l’application Paramètres système soient visibles ou accessibles, ou de le faire pour toutes les pages à l’exception de celles spécifiées. Pour découvrir comment personnaliser entièrement cette fonctionnalité, cliquez sur le lien ci-dessous.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Pour découvrir les paramètres de page que vous pouvez personnaliser sur HoloLens 2, visitez notre page [URL paramètres.](settings-uri-list.md) 
 
![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

### Mode Recherche
En mode Recherche, HoloLens 2 devient un outil de recherche de vision de l’ordinateur. Par rapport aux éditions précédentes, le mode recherche pour HoloLens 2 présente les avantages suivants :
-   En plus des capteurs exposés en mode recherche HoloLens (1ère génération), nous fournissons désormais un accès au capteur IMU, y compris un accéléromètre, un gyroscope et un magnétomètre.
-   HoloLens 2 offre de nouvelles fonctionnalités qui peuvent être utilisées avec le mode recherche. Plus précisément, l’accès à des API de suivi de la main et de suivi oculaire qui peuvent fournir un ensemble plus riche d’expériences.

Les chercheurs ont désormais la possibilité d’activer le mode Recherche sur leurs appareils HoloLens pour accéder à tous ces flux de capteurs d’image bruts externes. Le mode recherche pour HoloLens 2 permet également d’accéder aux lectures de l’accéléromètre, du gyroscope et du magnétomètre. Pour protéger la confidentialité des utilisateurs, les images brutes de l’appareil photo de suivi oculaire ne sont pas disponibles via le mode Recherche, mais la direction du regard est disponible via les API existantes.

Pour plus [d’informations techniques, consultez](https://docs.microsoft.com/windows/mixed-reality/research-mode) la documentation du mode Recherche.

### Augmentation de la longueur de l’enregistrement
En raison des commentaires des clients, nous avons augmenté la longueur d’enregistrement des [captures de réalité mixte.](holographic-photos-and-videos.md) Les captures de réalité mixte ne sont plus limitées à 5 minutes par défaut, mais calculent à la place la longueur d’enregistrement maximale en fonction de l’espace disque disponible. L’appareil estimera la durée maximale d’enregistrement vidéo en fonction de l’espace disque disponible jusqu’à 80 % de l’espace disque total.

> [!NOTE]
> HoloLens utilise la longueur d’enregistrement vidéo par défaut (5 minutes) si l’une des raisons suivantes se produit :
> - La durée d’enregistrement maximale estimée est plus petite que la durée par défaut de 5 minutes.
> - L’espace disque disponible est inférieur à 20 % de l’espace disque total.

Vous trouverez toutes les conditions requises dans notre documentation sur les [photos et vidéos holographiques.](holographic-photos-and-videos.md#maximum-recording-length) 

### Améliorations et correctifs de la mise à jour :
- D’autres écrans en mode OOBE sont désormais en mode sombre.
- En savoir plus sur le contenu doit pointer vers la dernière déclaration de confidentialité en ligne.
- Nous avons résolu un problème dans lequel les utilisateurs ne pouvaient pas mettre en service les profils VPN via des packages d’approvisionnement.
- Problème de configuration du proxy résolu pour la connexion VPN.
- Stratégie mise à jour pour désactiver l’éumération des fonctions USB via GDM pour NCM pour AllowUsbConnection.
- Nous avons résolu un problème qui empêchait un appareil HoloLens de s’afficher dans l’Explorateur de fichiers sur MTP (Media Transfer Protocol) lorsque l’appareil est installé en tant que borne à [application unique.](hololens-kiosk.md) Notez que le MTP (et la connexion USB en général) peuvent toujours être désactivés à l’aide de la stratégie [AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Nous avons résolu un problème dans lequel les icônes du menu Démarrer ont été correctement retentée en mode plein écran.
- Nous avons résolu un problème en raison de la mise en cache HTTP interférant avec le mode plein écran ciblé pour les groupes Azure AD.
- Nous avons résolu un problème dans lequel les utilisateurs ne pouvaient pas utiliser le bouton Coupler après l’activation du mode développeur avec des packages d’approvisionnement, sauf s’ils désactivaient et réactivaient le mode développeur.

## Windows Holographic, version 1903 - Mise à jour de novembre 2020
- Build 18362.1085

Cette mise à jour de qualité mensuelle ne contient aucune modification notable. Nous vous encourageons à essayer notre dernière version de la fonctionnalité Windows Holographic, version 20H2.

## Windows Holographic, version 2004 - Mise à jour d’octobre 2020
- Build 19041.1124
 
Améliorations et correctifs de la mise à jour :

- Suppression d’une vérification inutile à l’origine d’une erreur d’utilisation du système.

## Windows Holographic, version 1903 - Mise à jour d’octobre 2020
- Build 18362.1081

Cette mise à jour de qualité mensuelle ne contient aucune modification notable. Nous vous encourageons à tester nos dernières versions pour Windows Holographic, version 2004.

## Windows Holographic, version 2004 - Mise à jour de septembre 2020
- Build 19041.1117

Améliorations et correctifs de la mise à jour :

- Résout un problème qui empêchait Visual Studio débogage d’une application lorsque SupportsMultipleInstances="true» était présent dans appxmanifest.
- Cette version inclut le correctif de détection de proxy NCSI pour résoudre les problèmes de détection Internet sur le proxy réseau. NCSI peut utiliser le proxy de l’ordinateur et le proxy par profil pour la détection de connectivité Internet. Le proxy par utilisateur sera pris en charge par NCSI dans la prochaine version.
- Sur la plupart des appareils Windows Mixed Reality, le vecteur de direction avant est parallèle au sol lorsque la tête de l’utilisateur est dans une position neutre en regardant vers l’avant. Toutefois, les versions antérieures de HoloLens 2 alignaient le vecteur pour qu’il soit perpendiculaire aux panneaux d’affichage à la place, ce qui est incliné vers le bas de quelques degrés par rapport à l’orientation idéale. Les versions plus récentes de HoloLens 2 ont corrigé ce problème pour garantir la cohérence sémantique entre les facteurs de forme.
- Amélioration de la robustesse du suivi des mains, ce qui entraîne moins de pertes de suivi dans des scénarios spécifiques.
- Cette version contient un correctif pour améliorer la qualité de l’timestamp audio, ce qui peut avoir contribué à des problèmes de capture vidéo.

## Windows Holographic, version 1903 - Mise à jour de septembre 2020
- Build 18362.1079

Améliorations et correctifs de la mise à jour :

- Sur la plupart des appareils Windows Mixed Reality, le vecteur de direction avant est parallèle au sol lorsque la tête de l’utilisateur est dans une position neutre en regardant vers l’avant. Toutefois, les versions antérieures de HoloLens 2 alignaient le vecteur pour qu’il soit perpendiculaire aux panneaux d’affichage à la place, ce qui est incliné vers le bas de quelques degrés par rapport à l’orientation idéale. Les versions plus récentes de HoloLens 2 ont corrigé ce problème pour garantir la cohérence sémantique entre les facteurs de forme.
- Amélioration de la robustesse du suivi des mains, ce qui entraîne moins de pertes de suivi dans des scénarios spécifiques.

## Windows Holographic, version 2004 - Mise à jour d’août 2020
- Build 19041.1113

Améliorations et correctifs de la mise à jour :

- L’application Paramètres ne suit plus l’utilisateur dans les expériences d’inscription de l’iris ou d’étalonnage du suivi oculaire.
- Correction d’un bogue dans lequel l’application d’un package d’approvisionnement lors de la OOBE qui renomme l’appareil et effectue d’autres actions (telles que la connexion à un réseau) ne peut pas effectuer les autres actions après le redémarrage de l’appareil en raison du changement de nom.
- Modification du jeu de couleurs des flux de configuration initiaux de l’appareil pour améliorer la qualité visuelle.

## Windows Holographic, version 1903 - Mise à jour d’août 2020
- Build 18362.1074

Cette mise à jour de qualité mensuelle ne contient aucune modification notable. Nous vous encourageons à tester nos dernières versions pour Windows Holographic, version 2004.

## Windows Holographic, version 2004 - Mise à jour de juillet 2020
- Build 19041.1109

Améliorations et correctifs de la mise à jour :

- Les développeurs peuvent désormais choisir entre l’activation et la désactivation d’une connexion sécurisée à Device Portal.
- Fiabilité améliorée pour les lancements d’applications après les mises à jour du système d’exploitation.
- La luminosité de la boîte de réception par défaut a été modifiée à 100 %.
- Nous avons résolu un problème concernant le forwarding HTTPS pour Windows Device Portal sur HoloLens 2.

## Windows Holographic, version 1903 - Mise à jour de juillet 2020
- Build 18362.1071

Améliorations et correctifs de la mise à jour :

- Correction d’un problème qui pouvait faire disparaître les hologrammes dans les applications Unity lors de la perte ou de la reprise du suivi.
- Nous avons résolu un problème qui provoquait le retour d’applications HoloLens exclusives sur l’environnement de ligne de base lors de l’utilisation de l’émulateur HoloLens avec accélération matérielle sur certains appareils.
- Nous avons résolu un problème concernant le forwarding HTTPS pour Windows Device Portal sur HoloLens 2.

## Windows Holographic, version 2004 - Mise à jour de juin 2020
- Build 19041.1106

Améliorations et correctifs de la mise à jour :

- Les enregistreurs MRC personnalisés ont désormais de nouvelles valeurs par défaut pour certaines propriétés si elles ne sont pas spécifiées.
  - Sur *l’effet vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casque immersif))
  - Sur *l’effet audio MRC*:
    - LoopbackGain (valeur actuelle « Gain audio de l’application » sur la page De capture de réalité mixte dans Windows Device Portal)
    - MicrophoneGain (valeur actuelle « Gain audio micro » sur la page De capture de réalité mixte dans Windows Device Portal)
- Correction d’un bogue pour améliorer la qualité audio dans les scénarios de capture de réalité mixte. Plus précisément, ce correctif doit éliminer les problèmes audio dans l’enregistrement lorsque **le** menu Démarrer s’affiche.
- Stabilité améliorée de l’hologramme dans les vidéos enregistrées.
- Résolution d’un problème dans lequel la capture de réalité mixte ne pouvait pas enregistrer la vidéo après que l’appareil a été laissé en état de veille pendant plusieurs jours.
- L’API HolographicSpace.UserPresence est généralement désactivée pour les applications Unity. Ce comportement évite un problème qui a entraîné l’interruption de certaines applications lorsque la visière a été retournée, même si le paramètre « Exécuter en arrière-plan » a été activé. L’API est désormais activée pour unity versions 2018.4.18 et ultérieures et 2019.3.4 et versions ultérieures.
- Lorsque vous accédez à Device Portal sur Wi-Fi connexion, un navigateur web peut en empêcher l’accès en raison d’un certificat non valide. Le navigateur peut signaler une erreur telle que « ERR_SSL_PROTOCOL_ERROR », même si le certificat d’appareil était précédemment approuvé. Dans ce cas, vous ne pouvez pas passer à Device Portal, car il n’existe aucune option pour ignorer les avertissements de sécurité. Cette mise à jour a résolu le problème. Si le certificat d’appareil a été précédemment téléchargé et approuvé sur un PC pour supprimer les avertissements de sécurité du navigateur et que l’erreur SSL se produit, le nouveau certificat doit être téléchargé et approuvé pour résoudre les avertissements de sécurité du navigateur.
- Possibilité de créer un package d’approvisionnement d’runtime qui peut installer une application à l’aide de packages MSIX.
- Ajout d’un paramètre dans les hologrammes système des **paramètres**qui permet aux utilisateurs de supprimer automatiquement tous les hologrammes de la maison virtuelle lorsque l’appareil  >  ****  >  **** s’arrête.
- Résolution d’un problème : les applications HoloLens qui changent leur format de pixel restitulaient le noir dans l’émulateur HoloLens.
- Correction d’un bogue à l’origine d’un incident lors de la connexion à l’iris.
- Correction d’un problème de téléchargements répétés dans le Store pour les applications déjà en cours.
- Correction d’un bogue pour empêcher les applications immersives d’ouvrir Microsoft Edge à plusieurs reprises.
- Nous avons résolu un problème lors du lancement de l’application Photos initiale après la mise à jour à partir de la version 1903.
- Performances et fiabilité améliorées.

## Windows Holographic, version 1903 - Mise à jour de juin 2020
- Build 18362.1064

Améliorations et correctifs de la mise à jour :

- Les enregistreurs MRC personnalisés ont de nouvelles valeurs par défaut pour certaines propriétés si elles ne sont pas spécifiées.
  - Sur *l’effet vidéo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casque immersif))
  - Sur *l’effet audio MRC*:
    - LoopbackGain (valeur actuelle « Gain audio de l’application » sur la page De capture de réalité mixte dans Windows Device Portal)
    - MicrophoneGain (valeur actuelle « Gain audio micro » sur la page De capture de réalité mixte dans Windows Device Portal)
- L’API HolographicSpace.UserPresence est généralement désactivée pour les applications Unity. Ce comportement évite un problème qui entraîne l’interruption de certaines applications lorsque la visière est retournée, même si le paramètre à exécuter en arrière-plan est activé. L’API est désormais activée pour unity versions 2018.4.18 et ultérieures, et 2019.3.4 et versions ultérieures.
- Résolution d’un problème qui avait pour effet que les applications HoloLens qui changent leur format de pixel restitulaient le noir dans l’émulateur HoloLens.
- Nous avons résolu un problème concernant les lancements de l’application Photos lancement initial après la mise à jour à partir de la version 1903.

## Windows Holographic, version 2004  
- Build - 19041.1103

La mise à jour logicielle majeure de mai 2020 pour HoloLens 2, *Windows Holographic, version 2004* inclut une multitude de nouvelles fonctionnalités intéressantes, telles que la prise en charge de Windows Autopilot, le mode sombre de l’application, la prise en charge d’Ethernet USB pour les points d’accès 5G/LTE, et bien plus encore. Pour mettre à jour la dernière version, ouvrez l’application **Paramètres,** sélectionnez Mettre à jour & sécurité et sélectionnez le bouton Vérifier les    **** mises **à**   jour. 

|             Fonctionnalité                              |          Description                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurer et configurer en toute transparence de nouveaux appareils pour la production à l’aide de Windows AutoPilot                 |
|       Prise en charge de FIDO 2                             |          Prise en charge des clés de sécurité FIDO2 pour activer l’authentification rapide et sécurisée pour les appareils partagés            |
|       Approvisionnement amélioré                      |          Appliquer en toute transparence un package d’approvisionnement d’un lecteur USB à votre HoloLens                              |
|       État d’installation de l’application                 |          Vérifier l’état d’installation dans l’application Paramètres pour les applications ont été poussées vers HoloLens 2 via la gestion des applications mobiles               |
|       Fournisseurs de services de configuration (CSP)   |          Ajout de nouveaux fournisseurs de services de configuration pour améliorer les fonctionnalités de contrôle d’administration                 |
|       Prise en charge USB 5G/LTE                       |          La fonctionnalité Ethernet USB étendue permet la prise en charge de la 5G/LTE                                    |
|       Mode d’application sombre                              |          Mode d’application sombre disponible pour les applications qui utilisent les modes sombre et clair, améliorant ainsi l’expérience d’affichage        |
|       Commandes vocales                             |          Prise en charge de commandes vocales système supplémentaires pour contrôler HoloLens mains libres                           |
|       Améliorations apportées au suivi des mains                 |          Les améliorations apportées au suivi des mains améliorent la précision des interactions entre les boutons et les tablettes 2D                        |
|       Améliorations et correctifs de qualité                 |          Diverses améliorations en matière de performances et de fiabilité du système sur la plateforme                            |

### Prise en charge de Windows Autopilot

Windows Autopilot pour HoloLens 2 permet au canal des ventes d’appareils de pré-inscrire HoloLens dans votre client Intune. Lorsque les appareils arrivent, ils sont prêts à se déployer eux-mêmes en tant qu’appareils partagés sous votre client. Pour tirer parti de l’auto-déploiement, l’appareil doit se connecter à un réseau lors du premier écran de configuration à l’aide d’un port USB-C-to-Ethernet.

Une fois qu’un utilisateur démarre le processus de déploiement automatique Autopilot, le processus suit les étapes suivantes :

1. Joindre l’appareil à AzureActiveDirectory (AzureAD).
1. Utilisez Azure AD pour inscrire l’appareil dans Microsoft Intune (ou un autre service GPM).
1. Téléchargez les stratégies, certificats et profils de réseau destinés aux appareils.
1. Mettez en service l’appareil.
1. Présenter l’écran de connexion à l’utilisateur.

En savoir plus à partir du guide d’évaluation [de Windows Autopilot pour HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Contactez votre gestionnaire de comptes pour rejoindre l’aperçu AutoPilot maintenant. Les appareils prêts pour Autopilot commenceront bientôt la livraison.*

### Prise en charge des clés de sécurité FIDO2

Certains utilisateurs partagent un appareil HoloLens avec d’autres personnes dans un environnement professionnel ou scolaire. Il est donc important que les utilisateurs ne tapent pas facilement des mots de passe et des noms d’utilisateur longs. Fast Identity Online (FIDO) permet à tous les membres de votre organisation (client Azure AD) de se connecter en toute transparence à HoloLens sans entrer de nom d’utilisateur ou de mot de passe.

Les clés de sécurité FIDO2 sont une méthode d’authentification sans mot de passe basée sur des normes et qui peut être utilisée dans n’importe quel facteur de forme. FIDO est une norme ouverte pour l’authentification sans mot de passe. Il permet aux utilisateurs et aux organisations de se connectent à leurs ressources sans nom d’utilisateur ou mot de passe. Au lieu de cela, ils utilisent une clé de sécurité externe ou une clé de plateforme intégrée à un appareil.

To get started, see [Enable passwordless security key sign-in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Amélioration de l’inscription mdm via le package d’approvisionnement

Les packages d’approvisionnement vous permet de définir la configuration HoloLens via un fichier de configuration plutôt que par le biais de l’expérience HoloLens out-of-box. Auparavant, les packages d’approvisionnement devait être copiés sur la mémoire interne HoloLens. Désormais, ils peuvent être sur un lecteur USB afin qu’ils soient plus faciles à réutiliser sur plusieurs appareils HoloLens et que vous pouvez les mettre en service en parallèle. Les packages d’approvisionnement désormais également prendre en charge un champ pour s’inscrire à la gestion des appareils afin qu’il n’y a pas de configuration manuelle après la mise en service.

Pour l’essayer:

1. Téléchargez la dernière version du Concepteur de configuration Windows à partir du Windows Store sur votre PC.
1. Sélectionnez **Provision HoloLens Devices**  >  **Provision HoloLens 2 devices**.
2. Créez votre profil de configuration. Copiez ensuite tous les fichiers créés sur un périphérique de stockage USB-C.
3. Branchez l’appareil USB-C dans n’importe quel HoloLens flashé. Appuyez ensuite sur **les boutons d’alimentation**de baisse du volume pour appliquer votre package  +  **** d’approvisionnement.

### État d’installation des applications métiers

Le déploiement et la gestion des applications MDM pour les applications métier sont essentiels pour HoloLens. Les administrateurs et les utilisateurs doivent afficher l’état d’installation de l’application pour l’audit et le diagnostic. Dans cette version, nous avons ajouté plus de détails dans **Paramètres**Comptes Accès travail ou Scolaire  >  ****  >  ****  >  **Cliquez sur les informations de votre**  >  **compte.**

### Stratégies et CSP supplémentaires

Un fournisseur de services de [configuration (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) est une interface qui permet de lire, définir, modifier ou supprimer des paramètres de configuration sur un appareil. Dans cette version, nous ajoutons la prise en charge d’autres stratégies pour augmenter le nombre d’administrateurs de contrôle sur les appareils HoloLens déployés. Pour obtenir la liste des CSP pris en charge par HoloLens, voir [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Nouveautés de cette version :

**Fournisseur de services de configuration Policy** 

Le fournisseur de services de configuration de stratégie permet à l’entreprise de configurer des stratégies sur les appareils Windows. Dans cette version, nous avons ajouté de nouvelles stratégies pour HoloLens, qui sont répertoriées ici. Pour plus d’informations, voir [Les CSP de stratégie pris en charge par HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

Le fournisseur de services de configuration NetworkQoSPolicy crée des stratégies de qualité de service (QoS) réseau. Une stratégie de QoS effectue un ensemble d’actions sur le trafic réseau basé sur un ensemble de conditions de correspondance. Pour en savoir plus, consultez le programme [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### Prise en charge étendue d’Ethernet USB pour les appareils connectés 5G/LTE

La prise en charge a été ajoutée pour activer certains appareils haut débit mobiles, tels que les téléphones 5G/LTE et les points d’accès Wi-Fi, lorsqu’ils sont connectés à HoloLens 2 via USB. Ces appareils sont désormais affichés dans les **paramètres réseau** en tant qu’une autre connexion Ethernet. (Les appareils mobiles haut débit qui nécessitent un pilote externe ne sont pas pris en charge.) Cette fonctionnalité permet des connexions à bande passante élevée lorsque Wi-Fi n’est pas disponible et Wi-Fi connexion n’est pas suffisamment performante. Pour en savoir plus sur les périphériques USB pris en charge, consultez la [Bluetooth et les périphériques USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### Améliorations apportées au suivi des mains

Cette version inclut plusieurs améliorations du suivi des mains :

- **Le pointage pose une stabilité :** Le système résistait désormais à l’insération de l’index lorsqu’il est mascité par la paume. Cette modification améliore la précision lorsque vous appuyez sur les boutons, tapez, faites défiler le contenu, et bien plus encore ! 
- **Réduction des pressions accidentelles :** Nous avons amélioré la détection du mouvement d’pression d’air. Il existe désormais moins d’activations accidentelles dans plusieurs scénarios courants, par exemple lorsque vous déposez vos mains sur vos côtés.
- **Fiabilité du commutateur utilisateur :** Le système est désormais plus rapide et plus fiable lors de la mise à jour de la taille de la main lorsque vous partagez un appareil.
- **Vol de main réduite :** Nous avons amélioré la gestion des cas où il y a plus de deux mains en vue des capteurs. Si plusieurs personnes travaillent en étroite collaboration, il est désormais beaucoup moins possible que la main de suivi « passe » de l’utilisateur à la main d’une autre personne sur la scène.
- **Fiabilité du système :** Nous avons résolu un problème qui provoquait l’arrêt du suivi des mains lorsque l’appareil est en charge élevée.

### Mode sombre

De nombreuses applications Windows utilisent désormais les modes sombre et clair. Les utilisateurs HoloLens 2 peuvent choisir le mode par défaut pour les applications qui les prendre en charge. Après la mise à jour, le mode d’application par défaut est « sombre », mais vous pouvez facilement modifier ce paramètre : accédez aux **paramètres Couleurs**système Choisissez votre  >  ****  >  ****  >  **mode d’application par défaut.** 

Ces applications « in-box » permettent la prise en charge du mode sombre : 

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

![Fenêtres en mode sombre en mosaïque](images/DarkMode.jpg)

### Commandes vocales système

Vous pouvez désormais utiliser des commandes vocales avec n’importe quelle application sur l’appareil. Pour plus d’informations, [voir Utiliser votre voix pour utiliser HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Voir également [les langues pris en charge pour HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### Mises à jour de Cortana

L’application mise à jour s’intègre à Microsoft 365 pour vous aider à mieux faire sur vos appareils (actuellement en US-English uniquement). Sur HoloLens 2, Cortana ne prend plus en charge certaines commandes spécifiques à l’appareil, telles que l’ajustement du volume ou le redémarrage. Ces options sont désormais pris en charge par les nouvelles commandes vocales système. En savoir plus sur la nouvelle application Cortana dans notre [blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### Améliorations et correctifs de qualité

Améliorations et correctifs également dans la mise à jour :  
- Introduction d’un système d’étalonnage d’affichage actif. Cette fonctionnalité améliore la stabilité et l’alignement des hologrammes. Ils restent maintenant en place lorsque vous déplacez votre tête d’un côté à l’autre.
- Correction d’un bogue Wi-Fi diffusion en continu vers HoloLens était régulièrement interrompue. Si une application indique qu’elle a besoin d’une diffusion en continu à faible latence, implémentez le correctif en appelant la fonction [SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correction d’un incident d’appareil qui s’est produit lors de la diffusion en continu en mode recherche.
- Correction d’un bogue qui, dans certains cas, ne s’affichait pas sur l’écran de la session lors de la reprise d’une session.
- Nous avons résolu un problème dans lequel les utilisateurs ne pouvaient pas exporter les journaux de gestion des données mobiles via **les paramètres.**
- Nous avons résolu un problème dans lequel la précision du suivi oculaire immédiatement après la configuration d’out-of-box pouvait être inférieure à celle attendue.
- Nous avons résolu un problème dans lequel le sous-système de suivi oculaire n’a pas réussi à initialiser ou à effectuer l’étalonnage dans certaines conditions.
- Nous avons résolu un problème dans lequel l’étalonnage de l’œil était demandé pour un utilisateur déjà étalonné.
- Nous avons résolu un problème dans lequel un pilote se crashait lors de l’étalonnage de l’œil.
- Nous avons résolu un problème dans lequel des pressions répétées sur les boutons d’alimentation pouvaient provoquer un délai d’arrêt du système de 60 secondes et un arrêt de l’environnement de shell.
- Stabilité améliorée des tampons de profondeur.
- Ajout **d’un bouton Partager** dans le Hub de commentaires pour que les utilisateurs partagent plus facilement leurs commentaires.
- Correction d’un bogue dans lequel le wan RoboRaid n’était pas installé correctement.

### Problèmes connus

- Un problème avec le langage système zh-CN empêche les commandes vocales de prendre une capture de réalité mixte ou d’afficher l’adresse IP de l’appareil.
- Un problème vous oblige à lancer l’application Cortana après avoir lancé l’appareil pour utiliser l’activation vocale « Hey Cortana ». Si vous avez mis à jour à partir d’une build 18362, vous pouvez également voir une deuxième vignette d’application pour la version précédente de l’application Cortana qui ne fonctionne plus dans **l’démarrer.**

## Windows Holographic, version 1903 - Mise à jour de mai 2020 
- Build 18362.1061

Cette mise à jour qualité mensuelle ne contient pas de modifications notables, car l’équipe travaillait sur windows Holographic version 2004 May Update, comme décrit précédemment.

## Windows Holographic, version 1903 - Mise à jour d’avril 2020
- Build 18362.1059

**Mode sombre pour les applications pris en charge** 

De nombreuses applications Windows sont en charge à la fois en mode sombre et clair. Les clients HoloLens 2 peuvent désormais choisir le mode par défaut pour les applications qui prendre en charge les deux jeux de couleurs. En fonction des commentaires des clients, nous avons choisi le mode d’application par défaut sur « sombre », mais vous pouvez facilement modifier ce paramètre à tout moment : accédez à **Paramètres > Couleurs** système > pour rechercher « Choisir votre mode d’application par défaut **».**

Ces applications « in-box » permettent la prise en charge du mode sombre :
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

**Améliorations et correctifs également dans la mise à jour :** 
- Garantit que les superpositions d’shells sont incluses dans les captures de réalité mixte.
- Les développeurs Unreal peuvent désormais utiliser la page Vue 3D dans Device Portal pour tester et déboguer leurs applications.
- Stabilité améliorée de l’hologramme dans la capture de réalité mixte lorsque l’algorithme *HolographicDepthReprojectionMethod DepthReprojection* est utilisé.
- Correction de l’erreur « Classe API WinRT IStreamSocketListener non enregistrée » sur les applications ARM 32 bits.

## Windows Holographic, version 1903 - Mise à jour de mars 2020 
- Build 18362.1056

Améliorations et correctifs de la mise à jour :

- Amélioration de la stabilité de l’hologramme dans la capture de réalité mixte lorsque l’algorithme *HolographicDepthReprojectionMethod AutoPlanar* est utilisé.
- Garantit que le système de coordonnées attaché à un échantillon MF de profondeur est cohérent avec la documentation publique.
- Amélioration de la productivité des développeurs en permettant aux clients de coller de grandes quantités de texte via le portail d’appareil.

## Windows Holographic, version 1903 - Mise à jour de février 2020 
- Build 18362.1053

Améliorations et correctifs de la mise à jour :

- Désactivation temporaire de l’API HolographicSpace.UserPresence pour les applications Unity. Cette modification évite un problème qui a entraîné l’interruption de certaines applications lorsque la visière a été retournée, même si le paramètre « Exécuter en arrière-plan » a été activé.
- Correction d’un blocage aléatoire du HUP provoqué par le suivi de la main, dans lequel l’utilisateur a remarqué un blocage de l’interface utilisateur, puis de nouveau dans l’interface utilisateur après plusieurs secondes.
- Amélioration du suivi de la main de sorte que lorsque vous entrecroisez avec votre index, la partie supérieure de ce doigt est moins susceptible d’être inattendue.
- Fiabilité améliorée du suivi de la tête, du mappage spatial et d’autres runtimes.

## Windows Holographic, version 1903 - Mise à jour de janvier 2020 
- Build 18362.1043
 
Améliorations et correctifs de la mise à jour :

- Stabilité améliorée pour les applications exclusives lorsque vous travaillez avec l’émulateur HoloLens 2.

## Windows Holographic, version 1903 - Mise à jour de décembre 2019 
- Build 18362.1042

Améliorations et correctifs de la mise à jour :

- Introduction des correctifs de reproduction de dernière étape (LSR). Amélioration du rendu visuel des hologrammes pour qu’ils apparaissent plus stables et plus nettes en rendant compte plus précisément de leur profondeur. Ce symptôme sera plus perceptible après cette mise à jour si les applications ne définissent pas correctement la profondeur des hologrammes.
- Stabilité fixe des applications exclusives et navigation entre les applications exclusives.
- Résolution d’un problème dans lequel la capture de réalité mixte ne pouvait pas enregistrer la vidéo après que l’appareil était en état de veille pendant plusieurs jours.
- Stabilité améliorée de l’hologramme.

## Windows Holographic, version 1903 - Mise à jour de novembre 2019 
- Build 18362.1039

Améliorations et correctifs de la mise à jour :

- Fonctionnalité fixe de sélection **des** commandes vocales lors de la configuration initiale pour en-CA et en-AU.
- Amélioration de la qualité visuelle des objets placés loin dans les dernières versions de Shared Computer Toolkit réalité mixte (MRTK).
- Correction des problèmes de correction avec des applications holographiques bloquées dans un état suspendu au démarrage jusqu’à ce que le menu Démarrer soit ouvert, puis fermé.
- Correctifs et améliorations de conformité du runtime OpenXR pour HoloLens 2 et l’émulateur.
