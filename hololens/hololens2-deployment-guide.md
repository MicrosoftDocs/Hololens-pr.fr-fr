---
title: Guide de déploiement des clients externes
description: guide de déploiement pour HoloLens 2 pour les Clients externes (avec l’assistance à distance à titre d’exemple)
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
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659884"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>déploiement de HoloLens 2 sur des Clients externes avec l’assistance à distance

ce guide aide les professionnels de l’informatique avec les objectifs suivants à déployer Microsoft HoloLens 2 appareils dans leur organisation :

1. appareils HoloLens 2 Cloud connect
1. appareils de HoloLens 2 d’emprunt à des clients externes pour une utilisation
1. Sécuriser les appareils prêts

ce guide fournit des [recommandations générales relatives au déploiement de HoloLens 2](#general-deployment-recommendations-and-instructions) qui s’appliquent à la plupart des HoloLens 2 scénarios de déploiement et aux [problèmes courants](#common-concerns) que les clients ont lors du déploiement de l’assistance à distance pour une utilisation externe.

## <a name="scenario-description"></a>Description du scénario

dans le cadre de ce document, Contoso Company souhaite livrer un appareil HoloLens 2 à l’usine d’un client externe à des fins d’utilisation à long terme ou à long terme. lorsque le client a besoin d’assistance pour la maintenance des machines, le client se connecte à l’appareil HoloLens 2 à l’aide des informations d’identification fournies par la société contoso et utilise l’assistance à distance pour contacter les experts de la société contoso.

En savoir plus sur l’assistance à distance [ici](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="requirements-for-this-scenario"></a>Conditions requises pour ce scénario

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Gestionnaire de périphériques mobile, par exemple [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Licence d’assistance à distance
    1. [Acheter l’assistance à distance](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistance à distance pour la version d’évaluation](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Préoccupations courantes

- [Comment s’assurer que les clients externes n’ont pas la possibilité de communiquer les uns avec les autres](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Comment s’assurer que les clients n’ont pas accès aux ressources de l’entreprise](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Comment restreindre des applications](#how-to-restrict-apps)
- [Comment gérer les mots de passe](#how-to-manage-passwords)
- [Comment s’assurer que les clients n’ont pas accès à l’historique de conversation](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Comment s’assurer que les clients externes n’ont pas la possibilité de communiquer les uns avec les autres

étant donné que l’assistance à distance HoloLens à des appels de HoloLens n’est pas prise en charge, les clients sont en mesure de rechercher, mais ne peuvent pas les communiquer les uns avec les autres. Pour limiter davantage les utilisateurs pouvant effectuer des recherches et appeler, les  [barrières d’information](/microsoft-365/compliance/information-barriers) peuvent limiter les personnes avec lesquelles un client peut communiquer. Une autre option à prendre en compte est l’utilisation de la [recherche de répertoire étendue](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Étant donné que l’authentification unique est activée, il est important de désactiver le navigateur à l’aide de [**WDac**](/hololens/windows-defender-application-control-wdac). si un client externe ouvre le navigateur et utilise la version web de Teams, le client aura accès à l’historique des appels/conversations.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Comment s’assurer que les clients n’ont pas accès aux ressources de l’entreprise

Deux options sont à prendre en compte.

La première option est une approche à plusieurs couches :

1. Attribuez uniquement les licences dont l’utilisateur a besoin. si vous n’affectez pas OneDrive, Outlook, SharePoint, Yammer, etc. à l’utilisateur, il n’aura pas accès à ces ressources. Les seules licences dont les utilisateurs ont besoin sont l’assistance à distance, Intune et les licences AAD pour commencer.
1. Bloquer les applications (telles que les courriers électroniques) auxquelles vous ne voulez pas que les clients accèdent (voir [Comment restreindre les applications](#how-to-restrict-apps)).
1. Ne partagez pas les noms d’utilisateur ni le mot de passe avec les clients. pour vous connecter au HoloLens 2, un e-mail et un code PIN numérique sont requis.

La deuxième option consiste à créer un locataire distinct qui héberge des clients (Voir l’image 1,1).

**Image 1,1**

![Image du locataire du service](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Comment restreindre des applications

le [Mode plein écran](/hololens/hololens-kiosk) et/ou [WDAC (contrôle d’Application Windows Defender)](/hololens/windows-defender-application-control-wdac) sont des options de restriction des applications.

### <a name="how-to-manage-passwords"></a>Comment gérer les mots de passe

1. Suppression de l’expiration du mot de passe. Toutefois, cela augmente la probabilité qu’un compte soit compromis. La recommandation de mot de passe NIST est de modifier les mots de passe tous les 30-90 jours.
1. étendez l’expiration du mot de passe pour les appareils HoloLens 2 pour dépasser 90 jours.
1. Les appareils doivent être retournés à contoso pour modifier les mots de passe. Toutefois, cela peut entraîner des problèmes si les appareils sont censés se trouver dans l’usine du client pendant plus de 90 jours.  
1. Pour les appareils qui sont envoyés à plusieurs clients, réinitialisez les mots de passe avant d’expédier l’appareil aux clients.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Comment s’assurer que les clients n’ont pas accès à l’historique de conversation

L’assistance à distance efface l’historique de conversation après chaque session. toutefois, l’historique de conversation sera disponible pour l’utilisateur Microsoft Teams.

> [!NOTE]
> Étant donné que l’authentification unique est activée, il est important de désactiver le navigateur à l’aide de [**WDac**](/hololens/windows-defender-application-control-wdac). si un client externe ouvre le navigateur et utilise la version web de Teams, le client aura accès à l’historique des appels/conversations.

## <a name="general-deployment-recommendations-and-instructions"></a>Recommandations et Instructions générales relatives au déploiement

pour HoloLens 2 étapes de déploiement, nous vous recommandons d’utiliser les éléments suivants :

1. utilisez la [dernière version du système d’exploitation HoloLens](https://aka.ms/hololens2download) comme build de référence.
1. Affecter des licences basées sur l’utilisateur ou l’appareil :
    1. Les licences basées sur les utilisateurs et les appareils suivent les étapes suivantes :
        1. [créez un groupe dans AAD et ajoutez des membres](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) pour les utilisateurs HoloLens/RA.
        1. [Attribuez des licences](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) basées sur l’appareil ou sur l’utilisateur à ce groupe.
        1. Facultatif Vous pouvez cibler des groupes pour les stratégies MDM.

1. Les appareils doivent être joints à AAD à votre locataire, [inscrits automatiquement](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)et configurés via le [pilote automatique](/hololens/hololens2-autopilot).
    1. Notez que le premier utilisateur sur l’appareil sera le propriétaire de l’appareil.
    1. Notez que si l’appareil est joint à AAD, l’utilisateur qui a effectué la jointure est propriétaire de l’appareil.
    1. Pour plus d’informations, consultez propriétaire de l' [appareil](/hololens/security-adminless-os#device-owner).
1. [Verrouillage](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) de l’appareil par le client pour qu’il puisse uniquement joindre votre locataire.
    1. **Lien supplémentaire :** [CSP de verrouillage de locataire](/windows/client-management/mdm/tenantlockdown-csp).
1. Configurez une [borne à l’aide de l'](/hololens/hololens-global-assigned-access-kiosk)accès global auquel vous êtes affecté.
1. Nous vous recommandons de désactiver les fonctionnalités suivantes (facultatives) :
    1. Possibilité de mettre l’appareil en mode développeur [ici](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. possibilité de connecter le HoloLens à un PC pour copier la date de [désactivation USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Si vous ne souhaitez pas désactiver USB mais souhaitez pouvoir appliquer un package d’approvisionnement à l’appareil à l’aide de l’USB, suivez les instructions indiquées [**ici**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. utilisez [WDAC](/hololens/windows-defender-application-control-wdac) pour autoriser ou bloquer des applications sur l’appareil HoloLens 2.
1. Mettez à jour l’assistance à distance vers la dernière version dans le cadre de l’installation. Pour ce faire, deux options s’imposent :
    1. pour ce faire, accédez à Windows **Microsoft Store--> Remote Assist--> et mettre à jour l’application**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -qui autorise les mises à jour automatiques de l’application : est activé par défaut. Laissez l’appareil branché pour recevoir les mises à jour.
1. [Désactivez toutes les pages de paramètres](/hololens/settings-uri-list) à l’exception des paramètres réseau pour permettre aux utilisateurs de se connecter aux réseaux invités sur les sites clients.
1. [gérer les mises à jour HoloLens](/hololens/hololens-updates)
    1. Option pour [contrôler les mises à jour du système d’exploitation](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou autoriser à circuler librement.
1. [Restrictions d’appareils courantes](/hololens/hololens-common-device-restrictions).
