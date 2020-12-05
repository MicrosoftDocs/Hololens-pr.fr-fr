---
title: Guide de déploiement-déploiement d’HoloLens 2 connecté dans le Cloud à l’échelle de l’assistance à distance-préparer
description: Préparation à l’inscription des appareils HoloLens via un réseau connecté sur le Cloud
keywords: HoloLens, gestion, Cloud connecté, assistance à distance, AAD, Azure AD, GPM, gestion des appareils mobiles
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
ms.openlocfilehash: 0e9222df2c387fab8f61a585d3a7f3966b9ecd31
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196298"
---
# Préparer-Guide lié au Cloud

À la fin de cet article, vous allez configurer AAD, le GPM et en savoir plus sur l’utilisation des comptes AAD et des exigences réseau. Cette section du guide permettra à vous et à votre organisation de se préparer au déploiement de HoloLens 2 dans le Cloud et à l’aide de Dynamics 365 Remote Assist. L’importance de chaque partie de votre infrastructure ainsi que des liens vers des repères vous aideront à configurer ces pièces selon vos besoins.

## Notions fondamentales sur l’infrastructure

Dans le cadre de scénarios de déploiement d’entreprise ou personnels, un système GPM est l’infrastructure essentielle requise pour le déploiement et la gestion des appareils holographiques Windows 10. Un abonnement Azure AD Premium est recommandé en tant que fournisseur d’identité et requis pour la prise en charge de certaines fonctionnalités.

### Azure Active Directory

Azure AD est un service d’annuaire basé sur le cloud qui offre des fonctionnalités de gestion des accès et de l’identité. Les organisations qui utilisent Microsoft Office 365 ou Intune utilisent déjà Azure AD, qui comporte trois éditions: gratuit, Premium P1 et Premium P2 (voir [éditions Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Toutes les éditions prennent en charge l’inscription de l’appareil Azure AD, mais Premium P1 est requis pour activer l’inscription automatique de la gestion des périphériques mobiles que nous utiliserons plus tard.

> [!IMPORTANT]
> Il est essentiel de disposer d’Azure Active Directory en tant que périphériques HoloLens ne prenant pas en charge la jointure publicitaire locale. Si&#39;vous ne disposez pas encore d’une connexion Azure Active Directory, suivez les instructions fournies dans le lien ci-dessous pour commencer et [créer un nouveau client dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## Gestion des identités

Les employés ne peuvent utiliser qu’un seul compte pour initialiser un appareil de sorte qu’il&#39;est impératif que votre organisation contrôle quel compte est activé pour la première fois. Le compte choisi déterminera qui contrôle l’appareil et aura une influence sur vos capacités de gestion.

Dans ce guide, nous avons choisi d’utiliser les comptes AAD ou les comptes Azure Active Directory pour l' [identité](https://docs.microsoft.com/hololens/hololens-identity) utilisée. Il existe plusieurs avantages pour les comptes AAD que nous voulons utiliser, par exemple:

- Les employés utilisent leur compte Azure AD pour inscrire l’appareil dans Azure AD et l’inscrire automatiquement avec la solution de gestion des périphériques mobiles (AAD + GPM) de l’organisation&#39;.
- Les comptes AAD prennent en charge l' [authentification unique](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Lorsqu’un utilisateur se connecte à l’assistance à distance, son identité de l’utilisateur connecté dans AAD est reconnue et l’utilisateur est connecté à l’application pour une utilisation rationalisée.
- Les comptes AAD disposent d' [options d’authentification](https://docs.microsoft.com/hololens/hololens-identity) supplémentaires par le biais [de Windows Hello entreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Outre les utilisateurs de l’ouverture de session de l’iris, vous pouvez vous connecter à partir d’un autre appareil ou utiliser des clés de sécurité de l’appareil.

### Gestion des appareils mobiles

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), qui fait partie de l’entreprise Mobility + Security, est un système de gestion des appareils mobiles fonctionnant sous le Cloud qui gère les appareils connectés à votre client. Comme Office 365, Intune utilise Azure AD pour la gestion des identités, de sorte que les employés utilisent les mêmes informations d’identification pour inscrire des appareils dans Intune qu’ils utilisent pour se connecter à Office 365. Intune prend également en charge les appareils exécutant d’autres systèmes d’exploitation tels qu’iOS et Android, afin de fournir une solution MDM complète. Dans le cadre de ce guide, nous allons&#39;se concentrer sur l’utilisation de Intune pour permettre un déploiement Cloud à l’échelle avec HoloLens 2.

> [!IMPORTANT]
> Il est essentiel de disposer de la gestion des périphériques mobiles. Si vous n’avez pas encore configuré ce service, vous&#39;pouvez utiliser [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> De nombreux systèmes GPM prennent en charge Windows10. La plupart prennent en charge les scénarios de déploiement d’appareils personnels et d’entreprise. Les fournisseurs GPM qui prennent en charge Windows 10 holographique incluent actuellement: MobileIron, etc. La plupart des fournisseurs GPM majeurs prennent déjà en charge l’intégration à Azure AD. Vous trouverez les fournisseurs GPM prenant en charge Azure AD dans [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Network

Dans cette configuration, nous pensons que les appareils HoloLens 2 se connectent à Internet depuis n’importe quel réseau ouvert Wi-Fi disponible. Dans la mesure où un utilisateur peut avoir besoin de modifier la connexion réseau en fonction de l’emplacement, il doit apprendre à [connecter les appareils HoloLens au Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Pour Dynamics 365 Remote Assist, il existe diverses conditions réseau, notamment la bande passante, la latence, l’instabilité et la perte de paquets, qui peuvent avoir un impact sur votre expérience d’appel vidéo. Bien que les appels audio et vidéo puissent être possibles dans les environnements à faible bande passante, il est possible que vous rencontriez une dégradation des fonctionnalités. Lorsque vous utilisez Dynamics 365 Remote Assist sur HoloLens, vous devez tenir compte des éléments suivants:

**Minimum** : 1,5 Mbps vers le haut/bas est requis pour les appels vidéo d’égal à égal en HD grâce à la résolution de 1080 1080p à 30 ips.

**Optimale:** Pour les appels vidéo d’égal à égal en HD grâce à la résolution de 1080 1080p, 4-5 Mbps.

Informations supplémentaires:

- [Configuration requise pour le réseau](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recommandations en matière d’optimisation réseau](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Facultatif: connecter votre HoloLens à un VPN

Les appareils qui sont connectés à ce guide sont connectés au réseau par le biais du réseau Cloud externe. Il est possible que vous deviez accéder aux ressources de l’entreprise dont vous avez besoin pour vous&#39;que vous voulez connecter vos périphériques via un réseau VPN. Il existe plusieurs façons de connecter vos périphériques à un réseau privé virtuel (VPN), dans lesquels l’utilisateur final peut se connecter à l’aide de l’interface utilisateur de l’appareil, ou bien les appareils peuvent être gérés et recevoir le profil de VPN à partir d’un PPKG ou d’un appareil mobile. Pour plus d’informations sur les différents protocoles VPN et sur la façon de gérer le réseau VPN, reportez-&#39;vous à la rubrique Configuration de l’utilisation d'&#39;un réseau VPN pour plus d' [informations sur HoloLens et VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté dans le Cloud-configuration](hololens2-cloud-connected-configure.md)
