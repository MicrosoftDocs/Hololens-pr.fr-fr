---
title: Guide de déploiement – Cloud connecté HoloLens 2 déploiement à grande échelle avec l’assistance à distance-préparer
description: découvrez comment préparer l’inscription de HoloLens appareils sur un réseau connecté au Cloud à l’aide d’azure active directory et de la gestion des identités.
keywords: HoloLens, gestion, cloud connecté, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f747a2893ed3551e91a81bdbf5971deefbf6ce46
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637130"
---
# <a name="prepare---cloud-connected-guide"></a>Préparer-Guide connecté au Cloud

À la fin de cet article, vous aurez configuré Azure AD, MDM et en savoir plus sur l’utilisation des comptes Azure AD et des exigences réseau. cette section du guide vous aidera, vous et votre organisation, à déployer HoloLens 2 dans le cloud et à utiliser Dynamics 365 Remote Assist. Il détaillera l’importance de chaque partie de votre infrastructure et fournira des liens vers des guides qui vous aideront à configurer ces éléments en fonction des besoins.

## <a name="infrastructure-essentials"></a>Notions fondamentales de l’infrastructure

pour les scénarios de déploiement personnel et d’entreprise, un système MDM est l’infrastructure essentielle requise pour déployer et gérer des appareils Windows 10 Holographique. Un abonnement Azure AD Premium est recommandé en tant que fournisseur d’identité et requis pour la prise en charge de certaines fonctionnalités.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui dispose de trois éditions : gratuite, Premium P1 et Premium P2 (voir les [éditions de Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). toutes les éditions prennent en charge l’inscription des appareils Azure AD, mais Premium P1 est nécessaire pour activer l’inscription automatique MDM que nous utiliserons dans ce guide plus tard.

> [!IMPORTANT]
> il est essentiel de disposer d’un Azure Active Directory, car les appareils HoloLens ne prennent pas en charge la jointure AD locale. si vous n’avez pas déjà Azure Active Directory configuration de l'&#39;, accédez à [créer un nouveau locataire dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gestion des identités

Les employés peuvent utiliser un seul compte pour initialiser un appareil afin qu’il&#39;s impératifs que votre organisation contrôle le compte qui est activé en premier. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion.

dans ce guide, nous avons choisi que pour l' [identité](/hololens/hololens-identity) utilisée, nous allons utiliser des comptes de Azure AD ou des comptes Azure Active Directory. Il existe plusieurs avantages pour Azure AD les comptes que nous souhaitons utiliser, par exemple :

- Les employés utilisent leur compte Azure AD pour inscrire l’appareil dans Azure AD et l’inscrire automatiquement auprès de la solution MDM de l’organisation&#39;s (Azure AD + MDM – requiert Azure AD Premium).
- Les comptes de Azure AD prennent en charge l' [authentification unique](/azure/active-directory/manage-apps/what-is-single-sign-on). Lorsqu’un utilisateur se connecte à l’assistance à distance, son identité de l’utilisateur connecté Azure AD est reconnue et l’utilisateur est connecté à l’application pour une expérience rationalisée.
- les comptes Azure AD disposent d' [options d’authentification](/hololens/hololens-identity) supplémentaires via [Windows Hello pour l’entreprise](/windows/security/identity-protection/hello-for-business/hello-identity-verification). En plus des utilisateurs de l’ouverture de session IRIS, les utilisateurs peuvent se connecter à partir d’un autre appareil ou utiliser des clés de sécurité Rex.

### <a name="mobile-device-management"></a>Gestion des appareils mobiles

Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), qui fait partie du Enterprise Mobility + Security, est un système MDM basé sur le cloud qui gère les appareils connectés à votre locataire. comme Office 365, Intune utilise Azure AD pour la gestion des identités, de sorte que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. Intune prend également en charge les appareils qui exécutent d’autres systèmes d’exploitation, tels que iOS et Android, pour fournir une solution MDM complète. Dans le cadre de ce guide, nous allons&#39;se concentrer sur l’utilisation d’Intune pour l’activation d’un déploiement Cloud à grande échelle avec HoloLens 2.

> [!IMPORTANT]
> Il est essentiel de disposer de la gestion des appareils mobiles. Si&#39;vous n’avez pas déjà configuré le service informatique, suivez ce guide et [commencez avec Intune](/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> De nombreux systèmes GPM prennent en charge Windows 10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. les fournisseurs MDM qui prennent en charge Windows 10 Holographique incluent actuellement : MobileIron, etc. La plupart des fournisseurs GPM majeurs prennent déjà en charge l’intégration à Azure AD. Vous trouverez les fournisseurs GPM prenant en charge Azure AD dans [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Réseau

dans cette configuration, nous prévoyons HoloLens 2 appareils qui se connectent à Internet à partir de tout réseau ouvert Wi-Fi disponible. étant donné qu’un utilisateur peut avoir besoin de modifier la connexion réseau en fonction de son emplacement, il doit apprendre à [connecter HoloLens appareils au Wi-Fi.](/hololens/hololens-network)

par Dynamics 365 Remote Assist il existe diverses conditions réseau, notamment la bande passante, la latence, l’instabilité et la perte de paquets, qui peuvent avoir un impact sur votre expérience d’appel vidéo. Bien que les appels audio et vidéo puissent être possibles dans les environnements avec une bande passante réduite, vous pouvez rencontrer une dégradation des fonctionnalités. lorsque vous utilisez Dynamics 365 Remote Assist sur HoloLens voici la configuration réseau à garder à l’esprit :

**Minimum** : 1,5 Mbits/s vers le haut/vers le haut est requis pour l’appel vidéo de qualité HD d’égal à égal avec résolution de HD 1080p à 30 i/s.

**Optimal :** Pour une vidéo de qualité HD d’égal à égal, l’appel avec une résolution de HD 1080p, 4-5 Mbits/s est attendu.

Plus d’informations :

- [Configuration requise pour le réseau](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recommandations relatives à l’optimisation du réseau](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>facultatif : Connecter votre HoloLens au VPN

Les appareils connectés à ce guide vont se connecter au réseau via et le réseau Cloud externe. Il se peut que pour accéder aux ressources de l’entreprise, vous&#39;devez connecter vos appareils via VPN. Il existe plusieurs façons de connecter vos appareils à un VPN, à la fois où l’utilisateur final peut se connecter via l’interface utilisateur de l’appareil, ou bien les appareils peuvent être gérés et recevoir le profil VPN à partir d’un PPKG ou d’un MDM. la configuration du réseau privé virtuel gagné&#39;t est traitée dans cet article. donc, si vous&#39;d, pour en savoir plus sur les différents protocoles vpn ou sur les différentes façons de gérer les réseaux vpn, consultez [ces guides pour plus d’informations sur HoloLens et vpn.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au Cloud-configurer](hololens2-cloud-connected-configure.md)
