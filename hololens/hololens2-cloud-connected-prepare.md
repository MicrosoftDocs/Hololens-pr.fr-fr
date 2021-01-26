---
title: Guide de déploiement – Déploiement HoloLens 2 connecté au cloud à l’échelle avec Remote Assist - Préparer
description: Découvrez comment préparer l’inscription des appareils HoloLens sur un réseau Connecté au cloud à l’aide d’Azure Active Directory et de la gestion des identités.
keywords: HoloLens, gestion, cloud connecté, Remote Assist, AAD, Azure AD, MDM, Gestion des appareils mobiles
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283865"
---
# Préparer - Guide connecté au cloud

À la fin de cet article, vous aurez installé Azure AD, mdM et en savoir plus sur l’utilisation des comptes Azure AD et des exigences réseau. Cette section du guide vous aidera, vous et votre organisation, à vous préparer à déployer HoloLens 2 dans le cloud et à utiliser Dynamics 365 Remote Assist. Il passe en compte l’importance de chaque élément de votre infrastructure et fournit des liens vers des guides pour vous aider à configurer ces éléments selon vos besoins.

## Infrastructure Essentials

Pour les scénarios de déploiement personnel et d’entreprise, un système de gestion des périphériques mobiles est l’infrastructure essentielle requise pour déployer et gérer des appareils Windows 10 Holographiques. Un abonnement Azure AD Premium est recommandé en tant que fournisseur d’identité et requis pour la prise en charge de certaines fonctionnalités.

### Azure Active Directory

Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. Les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui possède trois éditions : Gratuite, Premium P1 et Premium P2 (voir [éditions Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Toutes les éditions prendre en charge l’inscription d’appareils Azure AD, mais Premium P1 est nécessaire pour activer l’inscription automatique mdm que nous utiliserons dans ce guide ultérieurement.

> [!IMPORTANT]
> Il est essentiel d’avoir azure Active Directory, car les appareils HoloLens ne peuvent pas prendre en charge la jointie AD sur site. Si vous n&#39;pas encore de configurer Azure Active Directory, suivez les instructions de ce lien pour commencer et créer un client dans [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## Gestion des identités

Les employés ne peuvent utiliser qu’un seul compte pour initialiser un appareil afin&#39;impératif que votre organisation contrôle d’abord quel compte est activé. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion.

Dans ce guide, nous [](https://docs.microsoft.com/hololens/hololens-identity) avons choisi d’utiliser des comptes Azure AD ou Azure Active Directory pour l’identité utilisée. Il existe plusieurs avantages pour les comptes Azure AD que nous voulons utiliser, tels que :

- Les employés utilisent leur compte Azure AD pour inscrire l’appareil dans Azure AD et l’inscrire automatiquement auprès de la solution GD de l’organisation&#39;(Azure AD+MDM – nécessite Azure AD Premium).
- Les comptes Azure AD prendre en [charge l' sign-on unique.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Lorsqu’un utilisateur se inscrit à Remote Assist, son identité de l’utilisateur Azure AD est reconnu et l’utilisateur est inscrit à l’application pour une expérience simplifiée.
- Les comptes Azure AD ont des [options d’authentification supplémentaires](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello Entreprise.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Outre l’iris, les utilisateurs peuvent se connecter à partir d’un autre appareil ou utiliser des clés de sécurité FIDO.

### Gestion des appareils mobiles

Microsoft [Intune,](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)qui fait partie de Enterprise Mobility + Security, est un système GDM basé sur le cloud qui gère les appareils connectés à votre client. Comme Office 365, Intune utilise Azure AD pour la gestion des identités, afin que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. Intune prend également en charge les appareils qui exécutent d’autres systèmes d’exploitation, tels qu’iOS et Android, pour fournir une solution MDM complète. Dans le cadre de ce guide, nous&#39;nous concentrerons sur l’utilisation d’Intune pour activer un déploiement cloud à grande échelle avec HoloLens 2.

> [!IMPORTANT]
> Il est essentiel d’avoir la gestion des appareils mobiles. Si vous n&#39;pas encore installé, suivez ce guide et commencer [avec Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> De nombreux systèmes GPM prennent en charge Windows10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. Les fournisseurs de gestion des périphériques mobiles qui supportent Actuellement Windows 10 Holographique incluent : AirWatch, MobileIron, etc. La plupart des fournisseurs GPM majeurs prennent déjà en charge l’intégration à Azure AD. Vous trouverez les fournisseurs GPM prenant en charge Azure AD dans [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Network

Dans cette configuration, nous prévoyons que les appareils HoloLens 2 se connectent à Internet à partir de n’importe quel réseau Wi-Fi ouvert disponible. Étant donné qu’un utilisateur peut avoir besoin de modifier la connexion réseau en fonction de son emplacement, il doit apprendre à connecter des appareils [HoloLens au Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Pour Dynamics 365 Remote Assist, il existe diverses conditions réseau, notamment la bande passante, la latence, la gigue et la perte de paquets, qui peuvent avoir un impact sur votre expérience d’appel vidéo. Bien que les appels audio et vidéo soient possibles dans des environnements avec une bande passante réduite, vous pouvez être en mesure de faire face à une dégradation des fonctionnalités. Lorsque vous utilisez Dynamics 365 Remote Assist sur HoloLens, voici les exigences réseau à garder à l’esprit :

**Minimum** : 1,5 Mbits/s vers le haut/bas est nécessaire pour les appels vidéo de qualité HD d’égal à égal avec une résolution HD 1080p à 30 fps.

**Optimal :** Pour les appels vidéo de qualité HD d’égal à égal avec une résolution HD 1080p, une hausse/baisse de 4 à 5 Mbits/s devrait être attendue.

Plus d’informations :

- [Configuration requise pour le réseau](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recommandations en matière d’optimisation du réseau](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Facultatif : connecter votre HoloLens à VPN

Les appareils connectés à ce guide vont se connecter au réseau via le réseau cloud externe. Il se peut que pour accéder aux ressources de l'&#39;vous devrez connecter vos appareils via VPN. Il existe plusieurs façons de connecter vos appareils à VPN, à la fois lorsque l’utilisateur final peut se connecter via l’interface utilisateur de l’appareil, ou les appareils peuvent être gérés et recevoir le profil VPN à partir d’un PPKG ou d’un GDM. La façon de configurer le VPN ne sera&#39;pas couverte dans cet article. Par exemple, si vous&#39;souhaitez en savoir plus sur les différents protocoles VPN ou sur les méthodes de gestion du VPN, consultez ces guides pour plus d’informations sur [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) et VPN.

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au cloud : configurer](hololens2-cloud-connected-configure.md)
