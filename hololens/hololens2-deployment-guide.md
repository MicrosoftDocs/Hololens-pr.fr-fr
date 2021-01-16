---
title: Guide de déploiement des clients externes
description: Guide de déploiement pour HoloLens 2 pour les clients externes (avec l’assistance à distance comme exemple)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 7658ace4879fef401accabb95ca22e307e5f80a8
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271658"
---
# Déploiement de l'HoloLens 2 auprès de clients externes avec assistance à distance

Ce guide aide les professionnels de l’informatique avec les objectifs suivants à déployer des appareils Microsoft HoloLens 2 dans leur organisation :

1. Connecter des appareils HoloLens 2 dans le cloud
1. Prêt d’appareils HoloLens 2 à des clients externes pour une utilisation
1. Sécuriser les appareils prêts

Ce guide fournit des recommandations générales sur le déploiement de [HoloLens 2](#general-deployment-recommendations-and-instructions) qui s’appliquent à la plupart des scénarios de déploiement HoloLens 2 et aux [préoccupations courantes](#common-concerns) des clients lors du déploiement de Remote Assist pour une utilisation externe.

## Description du scénario

Dans le cadre de ce document, la société Contoso souhaite expédier un appareil HoloLens 2 à l’usine d’un client externe pour une utilisation à court ou à long terme. Lorsque le client a besoin d’assistance pour la maintenance, il se connecte à l’appareil HoloLens 2 à l’aide des informations d’identification fournies par la société Contoso et utilise Remote Assist pour contacter les experts de contoso Company.

En savoir plus sur Remote Assist [ici.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### Conditions requises pour ce scénario

1. [AzureAD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestionnaire de périphériques mobiles , tel [qu’Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licence Remote Assist
    1. [Acheter Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistance à distance de la version d’essai](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## Préoccupations courantes

- [Comment s’assurer que les clients externes n’ont pas la possibilité de communiquer les uns avec les autres](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Comment s’assurer que les clients n’ont pas accès aux ressources de l’entreprise](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Comment limiter les applications](#how-to-restrict-apps)
- [Comment gérer les mots de passe](#how-to-manage-passwords)
- [Comment s’assurer que les clients n’ont pas accès à l’historique des conversation](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### Comment s’assurer que les clients externes n’ont pas la possibilité de communiquer les uns avec les autres

Étant donné que les appels HoloLens à HoloLens Remote Assist ne sont pas pris en charge, les clients peuvent rechercher, mais ne peuvent pas communiquer entre eux. Pour limiter davantage les personnes avec qui les clients peuvent rechercher et appeler, les  [obstacles](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) à l’information peuvent restreindre les personnes avec qui un client peut communiquer. Une autre option à envisager consiste à utiliser [la recherche dans l’annuaire dans l’étendue](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Étant donné que l’activation unique est activée, il est important de désactiver le navigateur à l’aide [**de WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Si un client externe ouvre le navigateur et utilise la version web de Teams, le client aura accès à l’historique des appels/conversation.

### Comment s’assurer que les clients n’ont pas accès aux ressources de l’entreprise

Deux options sont à envisager.

La première option est une approche multicqueque :

1. Attribuez uniquement les licences dont l’utilisateur a besoin. Si vous n’affectez pas OneDrive, Outlook, SharePoint, Yammer, etc. à l’utilisateur, il n’aura pas accès à ces ressources. Les seules licences dont les utilisateurs auront besoin sont Remote Assist, Intune et AAD pour commencer.
1. Bloquez les applications (telles que la messagerie électronique) que vous ne souhaitez pas que les clients accèdent (voir [Comment restreindre les applications).](#how-to-restrict-apps)
1. Ne partagez pas les noms d’utilisateur ni le mot de passe avec les clients. Pour vous connecter à HoloLens 2, un e-mail et un code confidentiel numérique sont requis.

La deuxième option consiste à créer un client distinct qui héberge des clients (voir Image 1.1).

**Image 1.1**

![Image du client de service](./images/hololens-service-tenant-image.png)

### Comment limiter les applications

[Le mode](https://docs.microsoft.com/hololens/hololens-kiosk) plein écran et/ou [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) sont des options pour restreindre les applications.

### Comment gérer les mots de passe

1. Supprimer l’expiration du mot de passe. Toutefois, cela augmente le risque qu’un compte soit compromis. La recommandation de mot de passe NIST consiste à modifier les mots de passe tous les 30 à 90 jours.
1. Prolonger l’expiration du mot de passe pour les appareils HoloLens 2 pour qu’il dépasse 90 jours.
1. Les appareils doivent être renvoyés à Contoso pour modifier les mots de passe. Toutefois, cela peut entraîner des problèmes si les appareils sont censés se trouver dans l’usine du client pendant plus de 90 jours.  
1. Pour les appareils envoyés à plusieurs clients, réinitialisez les mots de passe avant d’envoyer l’appareil aux clients.

### Comment s’assurer que les clients n’ont pas accès à l’historique des conversation

Remote Assist permet d’effacer l’historique des conversation après chaque session. Toutefois, l’historique de conversation sera disponible pour l’utilisateur de Microsoft Teams.

> [!NOTE]
> Étant donné que l’activation unique est activée, il est important de désactiver le navigateur à l’aide [**de WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Si un client externe ouvre le navigateur et utilise la version web de Teams, le client aura accès à l’historique des appels/conversation.

## Recommandations et instructions générales sur le déploiement

Nous vous recommandons les étapes suivantes pour le déploiement de HoloLens 2 :

1. Utilisez la [dernière version du système d’exploitation HoloLens](https://aka.ms/hololens2download) comme build de référence.
1. Attribuez des licences basées sur l’utilisateur ou l’appareil :
    1. Les licences basées sur l’utilisateur et les appareils suivent les étapes suivantes :
        1. [Créez un groupe dans AAD et ajoutez des membres](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) pour les utilisateurs HoloLens/RA.
        1. [Attribuez des licences basées sur l’appareil ou basées](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) sur l’utilisateur à ce groupe.
        1. (Facultatif) Vous pouvez cibler des groupes pour les stratégies de gestion des stratégies de gestion

1. Les appareils doivent être joints à votre [client,](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)inscrits automatiquement et configurés par le biais du pilote [automatique.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Notez que le premier utilisateur de l’appareil sera le propriétaire de l’appareil.
    1. Notez que si l’appareil est joint à AAD, l’utilisateur qui a effectué la jointeur est rendu propriétaire de l’appareil.
    1. Pour plus d’informations, voir [Propriétaire de l’appareil.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [Le client verrouille](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) l’appareil afin qu’il puisse uniquement rejoindre votre client.
    1. **Lien supplémentaire :** [CSP verrouillage du client.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Configurez kiosk à l’aide de l’accès affecté global [à cette zone.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. Nous vous recommandons de désactiver les fonctionnalités de suivi (facultatives) :
    1. Possibilité de placer l’appareil en mode [développeur ici.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Possibilité de connecter holoLens à un PC pour copier la date [désactiver USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Si vous ne souhaitez pas désactiver usb, mais que vous souhaitez pouvoir appliquer un package d’approvisionnement à l’appareil à l’aide de la clé USB, suivez les instructions répertoriées [**ici.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Utilisez [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) pour autoriser ou noir les applications sur l’appareil HoloLens 2.
1. Mettez à jour Remote Assist vers la dernière version dans le cadre de l’installation. Deux options s’offrent à vous :
    1. Pour ce faire, vous pouvez passer à Windows **Microsoft Store --> Remote Assist --> et mettre à jour l’application**.
    1. Activez les mises à jour automatiques à l’aide du CSP [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) et maintenez l’appareil branché pour recevoir les mises à jour.
1. [Désactivez toutes les pages de paramètres](https://docs.microsoft.com/hololens/settings-uri-list) à l’exception des paramètres réseau pour permettre aux utilisateurs de se connecter aux réseaux invités sur les sites clients.
1. [Gérer les mises à jour de HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Option permettant de [contrôler les mises à jour du système](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) d’exploitation ou d’autoriser le flux librement.
1. [Restrictions d’appareil courantes](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
