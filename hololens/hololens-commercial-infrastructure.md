---
title: Instructions d’infrastructure pour HoloLens
description: Découvrez les instructions d’infrastructure pour les appareils HoloLens, notamment la prise en charge du réseau sans fil, l’assistance à distance et la gestion des appareils mobiles.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283385"
---
# Configurer votre réseau pour HoloLens

Cette section du document nécessite l'intervention des personnes suivantes :

1. Administrateur réseau ayant les autorisations pour modifier le proxy/pare-feu
2. Administrateur Azure Active Directory
3. Administrateur du gestionnaire de périphériques mobiles

## Configuration requise pour l’infrastructure

HoloLens est le principal d’un appareil mobile Windows intégré à Azure.  Il fonctionne de façon optimale dans les environnements commerciaux avec la disponibilité du réseau sans fil (Wi-Fi) et l’accès aux services Microsoft.

Les services cloud critiques incluent :

- Azure Active Directory (Azure AD)
- Windows Update (WU)

Les clients commerciaux auront besoin d’une infrastructure de gestion de la mobilité d’entreprise (EMM) ou de gestion des appareils mobiles pour gérer les appareils HoloLens à l’échelle.  Ce guide utilise [ Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) comme exemple, même si tout fournisseur disposant d’une prise en charge complète de la stratégie Microsoft peut prendre en charge HoloLens.  Demandez à votre fournisseur de gestion des appareils mobiles s’il prend en charge HoloLens 2.

HoloLens ne prend en charge qu’un nombre limité d’expériences hors connexion dans le cloud.

### Prise en charge du protocole EAP réseau sans fil

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP.
- TTLS-TLS

### Configuration réseau spécifique à HoloLens

Vérifiez que [cette liste](hololens-offline.md) de points de terminaison est autorisée sur votre pare-feu réseau. Cela permet à HoloLens de fonctionner correctement.

### Configuration réseau spécifique à Remote Assist

1. La bande passante recommandée pour des performances optimales de Remote Assist est de 1,5 Mbits/s. Si vous souhaitez en savoir plus, veuillez consulter la liste détaillée des [conditions requises pour le réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network).
**(Veuillez noter que si la vitesse de votre réseau n’est pas de 1,5 Mbits/s au minimum, Remote Assist continuera de fonctionner. La qualité peut toutefois être affectée).**
1. Vérifiez que ces ports et URL sont autorisés sur votre pare-feu réseau pour permettre le fonctionnement de Microsoft Teams. Restez à jour avec la [dernière liste de ports.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- En savoir plus sur les [exigences spécifiques du réseau pour l’assistance à distance](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- En savoir plus sur la façon de [préparer le réseau de votre organisation pour Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### Configuration requise pour le réseau

Seul un accès réseau est requis pour permettre à Guides de télécharger et utiliser l’application.

## Conseils Azure Active Directory

> [!NOTE]
> Cette étape est uniquement nécessaire si votre entreprise envisage la gestion des applications HoloLens.

1. Vérifiez que vous disposez d’une licence Azure AD.
Pour plus d’informations, voir la [ configuration requise pour les licences HoloLens](hololens-licenses-requirements.md).

1. Si vous envisagez d’utiliser l’inscription automatique, vous devez [Configurer l’inscription Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Vérifiez que les utilisateurs de votre entreprise se trouvent dans Azure Active Directory (Azure AD).
Si vous souhaitez en savoir plus sur l’ajout d’utilisateur, veuillez consulter les [instructions suivantes](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).

1. Nous vous recommandons d’ajouter les utilisateurs ayant besoin de licences similaires au même groupe.
    1. [Créer un groupe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Ajout d'utilisateurs à des groupes](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Veillez à ce que les utilisateurs (ou le groupe d’utilisateurs) de votre entreprise obtiennent les licences nécessaires.
Si vous souhaitez en savoir plus sur l’attribution de licences, veuillez suivre ces [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Ne procédez à cette étape que si les utilisateurs doivent inscrire leur appareil HoloLens/Mobile auprès de vous (trois options sont possibles). Ces étapes permettent de vérifier que les utilisateurs de votre entreprise (ou un groupe d’utilisateurs) peuvent ajouter des appareils.
    1. **Option 1 :** accordez à tous les utilisateurs l’autorisation de joindre des appareils sur Azure AD.
**Connectez-vous au Portail Microsoft Azure en tant qu’administrateur** > **Azure Active Directory** > **Appareils** > **Paramètres de l’appareil** >
**Configurer les utilisateurs pouvant joindre des appareils sur Azure AD sur *Tous***

    1. **Option 2 :** accordez aux utilisateurs ou groupes l’autorisation de joindre des appareils sur Azure AD **Se connecter au Portail Microsoft Azure en tant qu’administrateur** > **Azure Active Directory** > **Appareils** > **Paramètres de l’appareil** >
**Configurer des utilisateurs pouvant joindre des appareils à Azure AD sur* Sélectionné***
![ Image illustrant la configuration des appareils joints Azure AD.](images/azure-ad-image.png)

    1. **Option 3 :** vous pouvez empêcher tous les utilisateurs de joindre leurs appareils au domaine. Cela signifie que tous les appareils doivent être enregistrés manuellement.

## Indications sur le gestionnaire de périphériques mobiles

### Gestion continue des appareils

> [!NOTE]
> Cette étape est uniquement nécessaire si votre entreprise envisage la gestion d’HoloLens.

La gestion continue des appareils dépend de votre infrastructure de gestion des appareils mobiles.  La plupart ont les mêmes fonctionnalités générales, mais l’interface utilisateur peut varier considérablement.

1. Les fournisseurs de services de configuration [(CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) vous permet de créer et de déployer des paramètres de gestion pour les appareils de votre réseau. Si vous souhaitez en savoir plus, veuillez consulter [la liste des CSP HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).

1. Les [Stratégies de conformité](https://docs.microsoft.com/intune/device-compliance-get-started) sont des règles et des paramètres que les appareils doivent satisfaire pour être conformes à l’infrastructure de votre entreprise. Utilisez ces stratégies avec un accès conditionnel pour bloquer l’accès aux ressources de l’entreprise pour les appareils non conformes. Par exemple, vous pouvez créer une stratégie nécessitant l’activation de BitLocker.

1. [Créer une stratégie de conformité](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).

1. L’accès conditionnel permet ou empêche les appareils mobiles et les applications mobiles d’accéder aux ressources de l’entreprise. Les deux documents qui pourraient vous être utiles sont [Planifier le déploiement de votre Autorité de certification](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) et [Meilleures pratiques](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [Cet article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) parle des outils de gestion Intune pour HoloLens.

1. [Créer un profil d’appareil](https://docs.microsoft.com/intune/configuration/device-profile-create)

### Gérer les mises à jour

Intune inclut une fonctionnalité appelée sonneries de mise à jour pour les appareils Windows 10, notamment HoloLens 2 et HoloLens v1 (avec holographique pour les entreprises). Les sonneries de mise à jour incluent un groupe de paramètres qui déterminent comment et quand les mises à jour sont installées.

Par exemple, vous pouvez créer une fenêtre de maintenance pour installer les mises à jour, ou choisir de redémarrer après l’installation des mises à jour.  Vous pouvez également choisir de suspendre les mises à jour de façon indéterminée jusqu’à ce que vous soyez prêt à procéder à la mise à jour.

En savoir plus sur [la configuration des anneaux de mise à jour avec Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### Gestion des applications

Gérer les applications HoloLens via :

1. Microsoft Store  
  Microsoft Store constitue la meilleure façon de distribuer et de consommer des applications sur HoloLens.  Un ensemble d’applications HoloLens principales est déjà disponible dans le Store ou vous pouvez [publier la vôtre](https://docs.microsoft.com/windows/uwp/publish/).  
  Toutes les applications du Store sont accessibles à tous, mais si ce n’est pas le cas, rendez-vous sur Microsoft Store pour Entreprises.  

1. [Microsoft Store pour Entreprises](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store pour Entreprises et Éducation est une boutique personnalisée pour votre environnement d’entreprise.  Il vous permet d’utiliser le Microsoft Store intégré à Windows 10 et HoloLens afin de rechercher, d’acquérir, de distribuer et de gérer des applications pour votre organisation.  Il vous permet également de déployer des applications propres à votre environnement commercial, mais pas au monde.

1. Déploiement et gestion des applications via Intune ou une autre solution de gestion des appareils mobiles  
  La plupart des solutions de gestion des appareils mobiles, notamment Intune, permettent de déployer des applications métier directement dans un groupe d’appareils inscrits.  Consultez cet article pour [l’installation des applications Intune](https://docs.microsoft.com/intune/apps-deploy).

1. Portail d’appareils_non recommandé_  
  Les applications peuvent également être installées sur HoloLens directement à l’aide du portail d’appareils Windows.  Cette opération n’est pas recommandée, car le mode développeur doit être activé pour utiliser le portail d’appareils.

En savoir plus à propos de [l’installation d’applications sur HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### Certificats

Vous pouvez distribuer les certificats par le biais de votre fournisseur GPM. Si votre entreprise exige des certificats, Intune prend en charge les certificats PKCS, PFX et SCEP. Il est important de savoir quel certificat est approprié pour votre entreprise. Si vous souhaitez en savoir plus sur le certificat le plus adapté à votre cas, veuillez consulter la [documentation sur les configurations de certificats](https://docs.microsoft.com/intune/protect/certificates-configure). Si vous envisagez d’utiliser des certificats pour l’authentification HoloLens, les certificats PFX ou SCEP peuvent être appropriés.

Si vous souhaitez en savoir plus sur l’utilisation de [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep), veuillez consulter les étapes suivantes.

### Mise à niveau vers Holographics for Business Commercial Suite

> [!NOTE]
> Windows holographiques pour Entreprises (suite commerciale) est destiné uniquement aux appareils HoloLens de la première génération. Le profil ne s’appliquera pas aux appareils HoloLens 2.

Vous trouverez des instructions sur la mise à niveau vers la suite commerciale dans la documentation sur la [mise à niveau holographique](https://docs.microsoft.com/intune/configuration/holographic-upgrade).

### Comment configurer le mode plein écran à l’aide de Microsoft Intune

1. Synchroniser Microsoft Store avec Intune (consultez les [instructions suivantes](https://docs.microsoft.com/intune/apps/windows-store-for-business))

1. Vérifier les paramètres de votre application
    1. Connectez-vous à votre compte professionnel Microsoft Store
    1. **Gérer > Produits et Services > Applications et logiciels > Sélectionner l’application à synchroniser > Disponibilité du magasin privé > Sélectionner « Tous » ou « Groupes spécifiques »**
        >[!NOTE]
        >Si vous ne voyez pas l’application souhaitée, vous devez « obtenir » l’application en recherchant votre application dans le Store. **Cliquez sur la barre « Rechercher » dans le coin supérieur droit > tapez le nom de l’application > cliquez sur l’application > sélectionnez « obtenir »**.
    1. Si vos applications ne sont pas affichées dans **Intune > Applications clientes > Applications**vous devrez peut-être [ synchroniser vos applications](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) de nouveau.

1. [Créer un profil d’appareil pour mode plein écran](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Vous pouvez configurer plusieurs utilisateurs pour qu’ils aient accès à différentes expériences du mode plein écran en utilisant « Azure AD » comme « type d’ouverture de session utilisateur ». Toutefois, cette option n’est disponible qu’en mode plein écran multi-applications. Le mode multi-applications plein écran fonctionne avec une seule application aussi bien qu'avec plusieurs applications.

![Image affichant la configuration du mode plein écran dans Intune](images/aad-kioskmode.png)

Si vous souhaitez en savoir plus sur les autres services de GPM, veuillez consulter la documentation de votre fournisseur. Si vous devez utiliser un paramètre personnalisé et une configuration XML complète pour configurer une borne dans votre service de GPM, veuillez consulter les instructions de la [borne HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk).

## Certificats et authentification

Les certificats peuvent être déployés à l’aide de la gestion des appareils mobiles (voir « certificats » dans la [section GPM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Les certificats peuvent également être déployés à HoloLens au travers du positionnement de package. Pour plus d’informations, consultez le [Positionnement HoloLens](hololens-provisioning.md).

### Autres liens rapides Intune

1. [Créer des profils : ](https://docs.microsoft.com/intune/configuration/device-profile-create) les profils vous permettent d’ajouter et de configurer des paramètres qui font l'objet d'un push vers les appareils de votre organisation.

