---
title: Rechercher, installer et désinstaller des applications
description: Le Microsoft Store constitue votre source d’applications et de jeux compatibles avec HoloLens.  Découvrez-en plus sur la recherche, l’installation et la désinstallation d’applications holographiques.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, application, installer
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f7d4ddf41f02b083000c1e57f5140c38527826d7
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364413"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Rechercher, installer et désinstaller des applications à partir du Microsoft Store

Le Microsoft Store vous permet d'accéder aux applications et aux jeux compatibles avec l'HoloLens. Quand vous accédez au Store sur votre HoloLens, toutes les applications que vous voyez y sont exécutées.

Les applications sur HoloLens utilisent l’affichage 2D ou l’affichage holographique. Les applications qui utilisent l’affichage 2D ressemblent à des fenêtres et peuvent être positionnées partout autour de vous. Les applications qui utilisent l’affichage holographique vous entourent et deviennent la seule application que vous voyez.

HoloLens prend en charge de nombreuses applications existantes à partir du Microsoft Store ainsi que les nouvelles applications conçues spécifiquement pour HoloLens.  Cet article décrit les applications holographiques du Microsoft Store.

Pour en savoir plus sur l’installation et l’exécution d’applications personnalisées, consultez [Applications holographiques personnalisées](holographic-custom-apps.md).

## <a name="find-apps"></a>Rechercher des applications

Ouvrez le Microsoft Store à partir du menu **Démarrer**. Recherchez ensuite les applications et les jeux. Vous pouvez utiliser des [commandes vocales](hololens-cortana.md) pour effectuer des recherches en prononçant « Rechercher ». Une fois la fenêtre de recherche ouverte, dites « Démarrer la dictée », puis lorsque vous y êtes invité, commencez à énoncer vos critères de recherche.

> [!NOTE]
> La configuration requise pour les appareils HoloLens dépend de l’architecture de la build de l’application. Si une build d’application pour HoloLens (1re génération) n’a pas été mise à jour avec une nouvelle UWP dans le Windows Store afin d’inclure le package d’architecture ARM, elle ne sera pas disponible pour les appareils HoloLens 2. De même, si une application HoloLens 2 n’inclut pas le package d’architecture x86, elle ne sera pas disponible pour les appareils HoloLens (1re génération). Architectures des appareils HoloLens :
>
> - x86 = HoloLens (1re génération)
> - ARM = HoloLens 2

> [!NOTE]
> Le 12 janvier 2021, nous ne prendrons plus en charge les applications suivantes sur les appareils HoloLens. Nous vous encourageons à utiliser le lien suivant sur votre appareil pour bénéficier de la version web de l’application.

| Application        | Lien                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> Actuellement, l’application OneDrive n’est pas prise en charge pour les comptes Azure AD sur HoloLens. Nous vous recommandons de télécharger l’application PWA Microsoft OneDrive. [Suivez ces étapes pour télécharger l’application.]

## <a name="install-apps"></a>Installer des applications

Pour télécharger des applications, vous devez être connecté avec un compte Microsoft. Certaines applications sont gratuites et peuvent être téléchargées immédiatement. Pour les applications qui nécessitent un achat, vous devez être inscrit au Windows Store avec votre compte Microsoft et avoir un mode de paiement valide.

> [!NOTE]
> Il n’est pas nécessaire que le compte que vous utilisez dans le Microsoft Store soit identique au compte avec lequel vous vous êtes connecté. Si vous utilisez un compte professionnel ou scolaire sur votre HoloLens, vous devrez peut-être vous connecter à l’aide de votre compte personnel dans l’application Store pour effectuer l’achat.

> [!TIP]
> Pour configurer un mode de paiement, accédez à [account.microsoft.com](https://account.microsoft.com/) et sélectionnez **Paiement et facturation** > **Options de paiement** > **Ajouter une option de paiement**.

1. Pour ouvrir le [menu **Démarrer**](holographic-home.md), effectuez un [mouvement associé au menu Démarrer](/hololens/hololens2-basic-usage#start-gesture) ou un [écartement des doigts paume vers le haut](hololens1-basic-usage.md) sur HoloLens (1re génération).

1. Sélectionnez l’application Microsoft Store. Après l’ouverture de l’application du Store :
   1. Utilisez la barre de recherche pour rechercher des applications.
   1. Sélectionnez les applications essentielles ou les applications spécialement conçues pour HoloLens dans l’une des catégories proposées.
   1. Dans la partie supérieure droite de l’application Store, sélectionnez le bouton **« ... »** , puis sélectionnez **Ma bibliothèque** pour afficher les applications précédemment achetées.

1. Sélectionnez **Obtenir** ou **Installer** dans la page de l’application (un achat peut être nécessaire).

### <a name="install-microsoft-onedrive-pwa-app"></a>Installer l’application PWA Microsoft OneDrive

Prérequis : l’utilisateur a déjà joint l’appareil HoloLens 2 à son locataire de travail.

1. Ouvrez le menu Démarrer et lancez le navigateur Edge.

    ![Menu Démarrer](images/office-pwa-1.jpg)

1. Sur votre HoloLens, accédez à [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) et entrez les informations d’identification de votre compte professionnel.

    ![Connexion avec un compte professionnel](images/office-pwa-2.jpg)

1. Une fois connecté à votre portail web OneDrive, attendez 30 à 60 secondes. Vous devriez alors voir le bouton de téléchargement de l’application PWA.

    ![Bouton d’installation de l’application PWA](images/office-pwa-3.jpg)

1. Sélectionnez le bouton de téléchargement de l’application PWA et effectuez l’installation.

    ![Invite d’installation](images/office-pwa-4.jpg)

1. Fermez le navigateur Edge. Ensuite, à partir du menu Démarrer, sélectionnez le bouton **Toutes les applications** et lancez l’application PWA OneDrive nommée **Microsoft OneDrive**.

    ![« Toutes les applications » avec les deux applications.](images/office-pwa-5.jpg)

    > [!NOTE]
    > « Microsoft OneDrive » est l’application PWA, tandis que « OneDrive » est l’ancienne application UWP.

1. Vous pouvez alors voir vos fichiers OneDrive.

    ![Application PWA OneDrive](images/office-pwa-6.jpg)

Voir aussi : [Activation des chargements automatiques pour OneDrive Entreprise](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Mettre à jour des applications

### <a name="manual-updates"></a>Mises à jour manuelles

Pour mettre à jour une application que vous avez installée à partir du Microsoft Store, vous pouvez mettre à jour l’application à partir de l’application du Microsoft Store. Pour les applications installées pour le Microsoft Store pour Entreprises, vous pouvez également les mettre à jour à partir du Microsoft Store pour Entreprises.

1. Pour ouvrir le [menu **Démarrer**](holographic-home.md), effectuez un [mouvement associé au menu Démarrer](/hololens/hololens2-basic-usage#start-gesture) ou un [écartement des doigts paume vers le haut](hololens1-basic-usage.md) sur HoloLens (1re génération).

1. Sélectionnez l’application du Store.

1. Regardez dans la partie supérieure droite de l’application Store.

1. Sélectionnez le bouton **« ... »** ou « Voir plus ».

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’application Microsoft Store.](images/store-update-1.png)

1. Sélectionnez **Téléchargements et mises à jour**.
    1. Si votre appareil a précédemment identifié des mises à jour, il peut y avoir une flèche vers le bas et un nombre représentant les mises à jour en attente.

1. Sélectionnez **Obtenir les mises à jour**. Votre appareil va maintenant rechercher les mises à jour et les préparer au téléchargement et l’installation.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de l’application Microsoft Store montrant la récupération de mises à jour.](images/store-update-2.png.jpg)

> [!NOTE]
> Si les applications sur votre appareil ont été distribuées par votre organisation, elles peuvent être mises à jour au moyen des mêmes méthodes de gestion des applications commerciales. Si cela s’applique à votre situation, consultez notre [vue d’ensemble du déploiement d’applications commerciales](app-deploy-overview.md).
>
> Si vous voulez mettre à jour une application personnalisée en version test ou déployée, vous devez utiliser la même méthode avec la version mise à jour de votre application. Pour en savoir plus sur l’installation et l’exécution d’applications personnalisées, consultez [Applications holographiques personnalisées](holographic-custom-apps.md).

### <a name="automatic-app-updates"></a>Mises à jour automatiques des applications

Les mises à jour automatiques s’appliquent uniquement aux applications qui ont été installées directement à partir du Microsoft Store ou du Microsoft Store pour Entreprises. En cas d’installation à partir d’Intune, le service informatique peut envoyer (push) les mises à jour à partir de MDM en activant la synchronisation avec le Microsoft Store pour Entreprises afin d’obtenir la dernière version disponible des applications.

> [!NOTE]
> Pour les applications provenant du Microsoft Store pour Entreprises, vous devez être connecté au Store et authentifié avec le même locataire que celui associé au catalogue Microsoft Store pour Entreprises utilisé sur l’appareil.

#### <a name="how-automatic-updates-work"></a>Fonctionnement des mises à jour automatiques

Les mises à jour automatiques des applications sont planifiées quotidiennement (environ toutes les 24 heures), selon la disponibilité du réseau. Gardez votre appareil actif ou branché sur le secteur pour recevoir les mises à jour. Même si une mise à jour est téléchargée durant la phase d’utilisation quotidienne active, elle n’est appliquée que lorsque l’application à mettre à jour n’est plus utilisée.

> [!TIP]
> Si possible, chargez votre appareil quand il est connecté au réseau d’entreprise. Si vous pouvez télécharger et installer les mises à jour pendant la nuit, l’utilisation active de l’appareil est moins susceptible d’être interrompue.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Comment les administrateurs informatiques peuvent contrôler les mises à jour automatiques

Les administrateurs informatiques peuvent contrôler les mises à jour automatiques des applications par le biais de la stratégie [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate). Cette stratégie permet d’activer ou de désactiver complètement les mises à jour automatiques des applications, mais elle ne contrôle pas quand les mises à jour ont lieu.

À partir de [21H2](hololens-release-notes.md#windows-holographic-version-21h1), les administrateurs informatiques peuvent également utiliser la stratégie [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) pour contrôler à quel moment procéder au redémarrage de force des applications qui étaient en cours d’utilisation et qui n’ont pas pu être mises à jour lors des tentatives précédentes.

## <a name="uninstall-apps"></a>Désinstallation d’applications

Vous pouvez désinstaller les applications de trois manières. Vous pouvez désinstaller les applications par le biais du Microsoft Store, du menu Démarrer ou des Paramètres.

> [!WARNING]
> Vous ne pouvez pas désinstaller une application système ou le Microsoft Store.

> [!IMPORTANT]
> Si votre HoloLens 2 est partagé par plusieurs utilisateurs, l’utilisateur qui a installé l’application doit se connecter pour la désinstaller.

### <a name="uninstall-from-the-microsoft-store"></a>Désinstaller à partir du Microsoft Store

Ouvrez le Microsoft Store à partir du menu **Démarrer**, puis recherchez l’application que vous souhaitez désinstaller.  Dans la page Store, chaque application installée a un bouton **Désinstaller**.

### <a name="uninstall-from-the-start-menu"></a>Désinstaller à partir du menu Démarrer

Dans le menu **Démarrer** ou dans la liste **Toutes les applications**, accédez à l’application. Sélectionnez-la en maintenant l’appui jusqu’à ce que le menu s’affiche, puis sélectionnez **Désinstaller**.

### <a name="uninstall-from-settings"></a>Désinstaller à partir des paramètres

Dans le menu **Démarrer**, sélectionnez **Paramètres > Applications**. Recherchez l’application dans la liste, sélectionnez-la et cliquez sur **Désinstaller**.

Si vous ne parvenez pas à désinstaller une application, veuillez [envoyer un commentaire](/hololens/hololens-feedback) à l’aide du Hub de commentaires.
