---
title: Recommandations sur l’infrastructure pour HoloLens
description: Découvrez les recommandations sur l’infrastructure pour les appareils HoloLens, notamment la prise en charge du réseau sans fil, l’assistance à distance et la gestion des appareils mobiles.
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
ms.openlocfilehash: 3aa5ed676a9f8864904752da3d965cba5fab7ce98db51abb4ff9444f1a0a370b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664466"
---
# <a name="configure-your-network-for-hololens"></a>Configurer votre réseau pour HoloLens

Cette section du document nécessite l’intervention des personnes suivantes :

1. Administrateur réseau ayant les nécessaires autorisations pour modifier le proxy/pare-feu
2. Administrateur Azure Active Directory
3. Administrateur MDM

## <a name="infrastructure-requirements"></a>Spécifications pour l’infrastructure

HoloLens est en fait un appareil mobile Windows intégré à Azure.  Il fonctionne de façon optimale dans les environnements commerciaux avec la disponibilité du réseau sans fil (Wi-Fi) et l’accès aux services Microsoft.

Les services cloud critiques incluent :

- Azure Active Directory (Azure AD)
- Windows Update (WU)

Les clients commerciaux auront besoin d’une infrastructure de gestion de la mobilité d’entreprise (EMM) ou de gestion des appareils mobiles (MDM) pour gérer les appareils HoloLens à grande échelle.  Ce guide utilise [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) comme exemple, même si n’importe quel fournisseur disposant d’une prise en charge complète de la stratégie Microsoft peut prendre en charge HoloLens.  Demandez à votre fournisseur de gestion des appareils mobiles s’il prend en charge HoloLens 2.

HoloLens ne prend en charge qu’un nombre limité d’expériences déconnectées du cloud.

### <a name="wireless-network-eap-support"></a>Prise en charge du protocole EAP réseau sans fil

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP.
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>Configuration réseau spécifique à HoloLens

Vérifiez que [cette liste](hololens-offline.md) de points de terminaison est autorisée sur votre pare-feu réseau. Ceci permet à HoloLens de fonctionner correctement.

### <a name="remote-assist-specific-network-requirements"></a>Configuration réseau spécifique à Remote Assist

1. La bande passante recommandée pour des performances optimales de Remote Assist est de 1,5 Mbits/s. Pour plus d’informations, consultez [Configuration réseau requise détaillée](/MicrosoftTeams/prepare-network).
**(Notez que si la vitesse de votre réseau n’est pas de 1,5 Mbits/s au minimum, Remote Assist fonctionnera néanmoins, mais la qualité peut être diminuée).**
1. Vérifiez que ces ports et ces URL sont autorisés sur votre pare-feu réseau pour permettre le fonctionnement de Microsoft Teams. Consultez la [liste de ports la plus récente](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- En savoir plus sur la [Configuration réseau requise spécifique pour Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- En savoir plus sur la [préparation du réseau de votre organisation pour Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Configuration réseau requise spécifique à Guides

Les guides nécessitent un accès réseau seulement pour télécharger et utiliser l’application.

## <a name="azure-active-directory-guidance"></a>Recommandations pour Azure Active Directory

> [!NOTE]
> Cette étape est nécessaire seulement si votre entreprise prévoit de gérer les appareils HoloLens.

1. Vérifiez que vous disposez d’une licence Azure AD.
Pour plus d’informations, consultez [Licences requises pour HoloLens](hololens-licenses-requirements.md).

1. Si vous prévoyez d’utiliser l’inscription automatique, vous devrez [Configurer l’inscription Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Vérifiez que les utilisateurs de votre entreprise se trouvent dans Azure Active Directory (Azure AD).
Consultez les [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) suivantes pour ajouter des utilisateurs.

1. Nous vous recommandons d’ajouter au même groupe les utilisateurs ayant besoin de licences similaires.
    1. [Créer un groupe](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Ajouter des utilisateurs à des groupes](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Vérifiez que les licences nécessaires sont affectées aux utilisateurs (ou aux groupes d’utilisateurs) de votre entreprise.
Si vous devez affecter des licences, suivez ces [instructions](/azure/active-directory/fundamentals/license-users-groups).

1. N’effectuez cette étape que si les utilisateurs doivent inscrire leur appareil HoloLens/Mobile auprès de vous (trois options sont possibles). Ces étapes permettent de vérifier que les utilisateurs (ou un groupe d’utilisateurs) de votre entreprise peuvent ajouter des appareils.
    1. **Option 1 :** Accordez à tous les utilisateurs l’autorisation de joindre des appareils à Azure AD.
**Connectez-vous au portail Azure en tant qu’administrateur** > **Azure Active Directory** > **Appareils** > **Paramètres d’appareil** >
**Définissez Les utilisateurs peuvent joindre des appareils à Azure AD sur *Tous***

    1. **Option 2 :** Accordez à des utilisateurs/groupes sélectionnés l’autorisation de joindre des appareils à Azure AD **Connectez-vous au portail Azure en tant qu’administrateur** > **Azure Active Directory** > **Appareils** > **Paramètres d’appareil** >
**Définissez Les utilisateurs peuvent joindre des appareils à Azure AD sur *Sélectionné***
![ Image montrant la configuration des appareils joints à Azure AD](images/azure-ad-image.png)

    1. **Option 3 :** Vous pouvez empêcher tous les utilisateurs de joindre leurs appareils au domaine. Cela signifie que tous les appareils doivent être enregistrés manuellement.

## <a name="mobile-device-manager-guidance"></a>Recommandations pour le gestionnaire d’appareils mobiles

### <a name="ongoing-device-management"></a>Gestion continue des appareils

> [!NOTE]
> Cette étape est nécessaire seulement si votre entreprise prévoit de gérer les appareils HoloLens.

La gestion continue des appareils dépend de votre infrastructure de gestion des appareils mobiles.  La plupart ont les mêmes fonctionnalités générales, mais l’interface utilisateur peut varier considérablement.

1. Les [fournisseurs de services de configuration (CSP)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) vous permettent de créer et de déployer des paramètres de gestion pour les appareils de votre réseau. Pour des informations de référence, consultez la [liste des fournisseurs de services de configuration HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).

1. Les [stratégies de conformité](/intune/device-compliance-get-started) sont des règles et des paramètres que les appareils doivent satisfaire pour être conformes à l’infrastructure de votre entreprise. Utilisez ces stratégies avec un accès conditionnel pour bloquer l’accès aux ressources de l’entreprise pour les appareils non conformes. Par exemple, vous pouvez créer une stratégie qui impose l’activation de BitLocker.

1. [Créez une stratégie de conformité](/intune/protect/compliance-policy-create-windows).

1. L’accès conditionnel permet ou empêche les appareils mobiles et les applications mobiles d’accéder aux ressources de l’entreprise. Ces deux documents peuvent vous aider : [Planifier le déploiement de votre autorité de certification](/azure/active-directory/conditional-access/plan-conditional-access) et [Bonnes pratiques](/azure/active-directory/conditional-access/best-practices).

1. [Cet article](/intune/fundamentals/windows-holographic-for-business) traite des outils de gestion Intune pour HoloLens.

1. [Créer un profil d’appareil](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Gérer les mises à jour

Intune inclut une fonctionnalité appelée Anneaux de mise à jour pour les appareils Windows 10, incluant HoloLens 2 et HoloLens v1 (avec Holographic for Business). Les anneaux de mise à jour incluent un groupe de paramètres qui déterminent comment et quand les mises à jour sont installées.

Par exemple, vous pouvez créer une fenêtre de maintenance pour installer les mises à jour, ou choisir de redémarrer l’appareil après l’installation des mises à jour.  Vous pouvez également choisir de suspendre indéfiniment les mises à jour jusqu’à ce que vous soyez prêt à procéder à la mise à jour.

En savoir plus sur la [Configuration des anneaux de mise à jour avec Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Gestion des applications

Gérer les applications HoloLens via :

1. Microsoft Store  
  Microsoft Store est la meilleure façon de distribuer et de consommer des applications sur HoloLens.  Un ensemble d’applications HoloLens est déjà disponible dans le Store et vous pouvez [publier votre propre application](/windows/uwp/publish/).  
  Toutes les applications du Store sont accessibles publiquement, mais si cela ne vous convient pas, voyez le Microsoft Store pour Entreprises.  

1. [Microsoft Store pour Entreprises](/microsoft-store/)  
  Microsoft Store pour Entreprises et Éducation est une boutique personnalisée pour votre environnement d’entreprise.  Il vous permet d’utiliser le Microsoft Store intégré à Windows 10 et HoloLens afin de rechercher, acquérir, distribuer et gérer des applications pour votre organisation.  Il vous permet également de déployer des applications propres à votre environnement commercial, mais pas au reste du monde.

1. Déploiement et gestion des applications via Intune ou une autre solution de gestion des appareils mobiles  
  La plupart des solutions de gestion des appareils mobiles, y compris Intune, permettent de déployer des applications métier directement sur un groupe d’appareils inscrits.  Consultez cet article pour l’[installation de l’application Intune](/intune/apps-deploy).

1. Portail d’appareil _non recommandé_  
  Les applications peuvent également être installées sur HoloLens directement en utilisant le portail d’appareil Windows.  Ceci n’est pas recommandé, car le mode Développeur doit être activé pour utiliser le portail d’appareil.

En savoir plus sur [l’installation d’applications sur HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certificats

Vous pouvez distribuer les certificats via votre fournisseur MDM. Si votre entreprise exige des certificats, Intune prend en charge PKCS, PFX et SCEP. Il est important de savoir quel certificat est approprié pour votre entreprise. Consultez la documentation sur les [configurations de certificats](/intune/protect/certificates-configure) pour déterminer le certificat qui vous convient le mieux. Si vous prévoyez d’utiliser des certificats pour l’authentification HoloLens, les certificats PFX ou SCEP peuvent être appropriés.

Reportez-vous aux étapes suivantes pour l’utilisation de [SCEP](/intune/protect/certificates-profile-scep).

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Comment mettre à niveau vers la suite commerciale Holographics for Business

> [!NOTE]
> Windows Holographics for Business (suite commerciale) est destiné seulement aux appareils HoloLens de première génération. Le profil ne sera pas appliqué aux appareils HoloLens 2.

Vous trouverez des instructions sur la mise à niveau vers la suite commerciale dans la documentation sur la [mise à niveau d’Holographics](/intune/configuration/holographic-upgrade).

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Comment configurer le mode Kisoque en utilisant Microsoft Intune

1. Synchronisez Microsoft Store avec Intune (consultez les [instructions](/intune/apps/windows-store-for-business) suivantes).

1. Vérifiez les paramètres de votre application
    1. Connectez-vous à votre compte professionnel Microsoft Store
    1. **Gérer > Produits et Services > Applications et logiciels > Sélectionnez l’application à synchroniser > Disponibilité du magasin privé > Sélectionnez « Tous » ou « Groupes spécifiques »**
        >[!NOTE]
        >Si vous ne voyez pas l’application souhaitée, vous devez « obtenir » l’application en la recherchant dans le Store. **Cliquez sur la barre « Rechercher » dans le coin supérieur droit > Tapez le nom de l’application > Cliquez sur l’application > Sélectionnez « Obtenir »** .
    1. Si vous ne voyez pas vos applications dans **Intune > Applications clientes > Applications**, vous devrez peut-être [resynchroniser vos applications](/intune/apps/windows-store-for-business#synchronize-apps).

1. [Créer un profil d’appareil pour le mode Kiosque](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Vous pouvez configurer les utilisateurs pour qu’ils aient accès à différentes expériences du mode Kiosque en utilisant « Azure AD » comme « Type d’ouverture de session utilisateur ». Cette option n’est cependant disponible qu’en mode Kiosque multi-application. Le mode Kiosque multi-application fonctionne avec une seule application ou avec plusieurs applications.

![Image montrant la configuration du mode Kiosque dans Intune](images/aad-kioskmode.png)

Pour d’autres services MDM, consultez la documentation de votre fournisseur pour obtenir des instructions. Si vous devez utiliser un paramètre personnalisé et une configuration XML complète pour configurer un kiosque dans votre service MDM, consultez les instructions de [Kiosque HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk).

## <a name="certificates-and-authentication"></a>Certificats et authentification

Les certificats peuvent être déployés via MDM (consultez « certificats » dans la [section MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Les certificats peuvent également être déployés sur HoloLens via le provisionnement de package. Pour plus d’informations, consultez [Provivisionnement d’HoloLens](hololens-provisioning.md).

### <a name="additional-intune-quick-links"></a>Autres liens rapides Intune

1. [Créer des profils :](/intune/configuration/device-profile-create) Les profils vous permettent d’ajouter et de configurer des paramètres qui sont envoyés (push) aux appareils de votre organisation.

