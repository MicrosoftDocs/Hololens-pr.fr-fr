---
title: déployer un HoloLens 2 connecté au cloud à des clients externes
description: guide de déploiement pour HoloLens 2 pour les Clients externes (avec l’assistance à distance à titre d’exemple)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190325"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>déployer un HoloLens 2 connecté au cloud à des clients externes

Ce guide est un complément du [Guide de déploiement connecté au Cloud](hololens2-cloud-connected-overview.md). il est utilisé dans les situations où votre organisation souhaite livrer des HoloLens 2 des appareils à la fonctionnalité d’un client externe pour une utilisation à long terme ou à long terme. le client externe se connecte à l’appareil HoloLens 2 à l’aide des informations d’identification fournies par votre organisation et utilise l' [assistance à distance](/dynamics365/mixed-reality/remote-assist/ra-overview) pour contacter vos experts. ce guide fournit des [recommandations générales relatives au déploiement de HoloLens 2](#general-deployment-recommendations) qui s’appliquent à la plupart des scénarios de déploiement de HoloLens 2 externes et aux [problèmes courants](#common-external-client-deployment-concerns) que les clients ont lors du déploiement de l’assistance à distance pour une utilisation externe. 

## <a name="prerequisites"></a>Prérequis

l’infrastructure suivante doit être en place par le [Guide de déploiement connecté au Cloud](hololens2-cloud-connected-overview.md) pour déployer la HoloLens 2 en externe.

- Azure AD rejoindre avec l’inscription automatique MDM — gérée par MDM (Intune)
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
    - Un ou plusieurs utilisateurs par appareil sont pris en charge.

### <a name="remote-assist-licensing-and-requirements"></a>Licences et exigences de l’assistance à distance

- Compte Azure AD (nécessaire pour l’achat de l’abonnement et l’attribution de licences)
- [Abonnement Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Essai Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Consultez [en savoir plus sur l’assistance à distance](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Utilisateur Remote Assist Dynamics 365

- Licence Remote Assist
- Connectivité réseau

### <a name="microsoft-teams-user"></a>Utilisateur Microsoft Teams

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Connectivité réseau

## <a name="general-deployment-recommendations"></a>Recommandations générales relatives au déploiement

nous vous recommandons d’utiliser les étapes suivantes pour le déploiement de HoloLens 2 externe :

1. utilisez la [dernière version du système d’exploitation HoloLens](https://aka.ms/hololens2download) comme build de référence.
1. Affectez des licences basées sur l’utilisateur ou l’appareil en suivant les étapes ci-dessous :
    1. [créez un groupe dans AAD et ajoutez des membres](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) pour les utilisateurs HoloLens/RA.
    1. [Attribuez des licences](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) basées sur l’appareil ou sur l’utilisateur à ce groupe.
    1. Facultatif Groupes cibles pour les stratégies de [gestion des appareils mobiles (MDM)](hololens-enroll-mdm.md) .

1. Joindre des appareils AAD à votre locataire, l' [inscrire automatiquement](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)et le configurer via [AutoPilot](/hololens/hololens2-autopilot). Pour plus d’informations, consultez propriétaire de l' [appareil](/hololens/security-adminless-os#device-owner).
    1. Le premier utilisateur sur l’appareil sera le propriétaire de l’appareil.
    1. Si l’appareil est joint à AAD, l’utilisateur qui a effectué la jonction est devenu propriétaire de l’appareil.
    
1. Le [client verrouille](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) l’appareil pour qu’il puisse être joint uniquement par votre locataire.
    1. Voir aussi [CSP de verrouillage de locataire](/windows/client-management/mdm/tenantlockdown-csp).

1. [Configurer le mode plein écran à l’aide de l’accès global assigné](/hololens/hololens-global-assigned-access-kiosk).

1. Désactivez les fonctionnalités suivantes (facultatives) :
    1. Possibilité de mettre l’appareil en mode développeur [ici](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. possibilité de connecter le HoloLens à un PC pour copier la date de [désactivation USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Si vous ne souhaitez pas désactiver USB mais souhaitez pouvoir appliquer un package d’approvisionnement à l’appareil à l’aide de l’USB, suivez les [instructions pour autoriser l’installation du package d’approvisionnement](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. utilisez le [contrôle WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) pour autoriser ou bloquer des applications sur l’appareil HoloLens 2.
1. Mettez à jour l’assistance à distance vers la dernière version dans le cadre de l’installation. Tenez compte des deux options suivantes :
    1. accédez à Windows **Microsoft Store--> Remote Assist--> et mettre à jour l’application**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -qui autorise les mises à jour automatiques de l’application : est activé par défaut. Laissez l’appareil branché pour recevoir les mises à jour.
1. [Désactivez toutes les pages de paramètres](/hololens/settings-uri-list) à l’exception des paramètres réseau pour permettre aux utilisateurs de se connecter aux réseaux invités sur les sites clients.
1. [Gérer les mises à jour de HoloLens](/hololens/hololens-updates)
    1. Option pour [contrôler les mises à jour du système d’exploitation](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou autoriser à circuler librement.
1. Définir des [restrictions d’appareil courantes](/hololens/hololens-common-device-restrictions).

Maintenant, vos clients externes sont prêts à utiliser leur HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Problèmes courants liés au déploiement de clients externes

- [S’assurer que les clients ne peuvent pas communiquer les uns avec les autres](#ensure-that-external-clients-cant-communicate-with-one-another)
- [S’assurer que les clients ne peuvent pas accéder aux ressources de l’entreprise](#ensure-that-clients-wont-have-access-to-company-resources)
- [Masquage ou restriction des applications](#hidden-or-restricted-apps)
- [Gestion des mots de passe pour vos clients](#password-management-for-your-clients) 
- [S’assurer que les clients ne peuvent pas accéder à l’historique de conversation](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>S’assurer que les clients externes ne peuvent pas communiquer les uns avec les autres

l’assistance à distance HoloLens à des appels de HoloLens n’est pas prise en charge. Les clients peuvent rechercher, mais ne peuvent pas communiquer entre eux. les [barrières en matière d’informations dans Microsoft 365](/microsoft-365/compliance/information-barriers) peuvent limiter davantage les personnes pouvant faire l’objet d’une recherche et d’un appel à un client. une autre option consiste à utiliser [Microsoft Teams recherche](/MicrosoftTeams/teams-scoped-directory-search)dans l’étendue de l’annuaire.

 > [!NOTE]
> étant donné que l’authentification unique est activée, il est important de désactiver le navigateur à l’aide de [Windows Defender contrôle d’Application (WDAC)](/hololens/windows-defender-application-control-wdac). si un client externe ouvre le navigateur et utilise la version web de Teams, le client aura accès à votre historique de conversation.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>S’assurer que les clients n’ont pas accès aux ressources de l’entreprise

Deux options sont à prendre en compte.

La première option est une approche à plusieurs couches :

1. Attribuez uniquement les licences dont l’utilisateur a besoin. si vous n’affectez pas OneDrive, Outlook, SharePoint, Yammer, etc., l’utilisateur n’aura pas accès à ces ressources. Les seules licences dont les utilisateurs ont besoin sont l’assistance à distance, Intune et les licences AAD pour commencer.
1. Bloquer les applications (telles que les courriers électroniques) auxquelles vous ne voulez pas que les clients accèdent (voir les [applications sont masquées ou restreintes](#apps are hidden or restricted)).
1. Ne partagez pas les noms d’utilisateur ni le mot de passe avec les clients. pour vous connecter au HoloLens 2, un e-mail et un code PIN numérique sont requis.

La deuxième option consiste à créer un locataire distinct qui héberge des clients (Voir l’image 1,1).

**Image 1,1**

![Image du locataire du service.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Applications masquées ou restreintes

le [mode plein écran](/hololens/hololens-kiosk) et/ou [le contrôle d’Application Windows Defender (WDAC)](/hololens/windows-efender-application-control-wdac) sont des options de masquage et/ou de restriction des applications.

### <a name="password-management-for-your-clients"></a>Gestion des mots de passe pour vos clients

1. Suppression de l’expiration du mot de passe. Toutefois, cette option peut augmenter le risque de compromission d’un compte. La recommandation de mot de passe NIST est de modifier les mots de passe tous les 30-90 jours.
1. étendez l’expiration du mot de passe pour les appareils HoloLens 2 pour dépasser 90 jours.
1. Les appareils doivent être renvoyés à votre organisation pour modifier les mots de passe. Toutefois, cette option peut provoquer des problèmes si les appareils sont censés se trouver dans l’usine du client pendant plus de 90 jours.  
1. Pour les appareils qui sont envoyés à plusieurs clients, réinitialisez les mots de passe avant d’expédier l’appareil aux clients.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>S’assurer que les clients n’ont pas accès à l’historique de conversation

L’assistance à distance efface l’historique de conversation après chaque session. toutefois, l’historique de conversation sera disponible pour les utilisateurs de Microsoft Teams.

> [!NOTE]
> étant donné que l’authentification unique est activée, il est important de désactiver le navigateur à l’aide de [Windows Defender contrôle d’Application (WDAC)](/hololens/windows-defender-application-control-wdac).  si un client externe ouvre le navigateur et utilise la version web de Teams, le client aura accès à l’historique des appels/conversations.
