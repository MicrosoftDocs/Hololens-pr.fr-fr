---
title: Configurer HoloLens dans un environnement commercial
description: En savoir plus sur le déploiement et la gestion de HoloLens dans les environnements d’entreprise.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865563"
---
# Déploiement de HoloLens dans un environnement commercial

Vous pouvez déployer et configurer HoloLens à des fins d’évolution dans un environnement commercial. Cet article fournit des instructions pour le déploiement d’appareils HoloLens dans un environnement commercial. Ce guide suppose une connaissance de base de HoloLens. Suivez le [Guide](hololens1-setup.md) de mise en route pour configurer HoloLens pour la première fois.

Ce document part du principe que le HoloLens a été évalué par les équipes de sécurité en toute sécurité sur le réseau d’entreprise.  
> [!Tip]
> En savoir plus sur la [sécurité HoloLens](security-overview.md).
> Pour la sécurité HoloLens (1ère génération), consultez [cette FAQ](hololens1-faq-security.md).

## Vue d’ensemble des étapes de déploiement

1. [Déterminez les fonctionnalités dont vous avez besoin](hololens-requirements.md#step-1-determine-what-you-need)
1. [Déterminez les licences dont vous avez besoin](hololens-licenses-requirements.md)
1. [Configurer votre réseau pour HoloLens](hololens-commercial-infrastructure.md).
    1. Cette section inclut des exigences de bande passante, des URL et des ports qui doivent être autorisés sur votre pare-feu. Conseils d’Azure AD; Recommandations en matière de gestion des périphériques mobiles (GPM); recommandations en matière de déploiement/gestion d’applications; et recommandations en matière de certificats.
1. Facultatif [Configurer HoloLens à l’aide d’un package de mise en service](hololens-provisioning.md)
1. [Appareil d’inscription](hololens-enroll-mdm.md)
1. [Configurer des mises à jour basées sur un anneau pour HoloLens](hololens-updates.md)
1. [Activer le chiffrement d’appareil Bitlocker pour HoloLens](security-encryption-data-protection.md)

## Étape1. Déterminez ce dont vous avez besoin

Avant de déployer le HoloLens dans votre environnement, il est important de déterminer les fonctionnalités, les applications et le type d’identité nécessaires. Il est également important de veiller à ce que votre équipe de sécurité ait approuvé l’utilisation du HoloLens sur le réseau de la société. Pour plus d’informations sur la sécurité, consultez [HoloLens2 Security](security-overview.md) .

### Type d’identité

Déterminez le type d’identité qui sera utilisé pour vous connecter à l’appareil.

1. **Comptes locaux:** Ce compte est local pour l’appareil (par exemple, un compte d’administrateur local sur un PC Windows). Cela permettra à 1 utilisateur de se connecter à l’appareil.
2. **MSA:** Il s’agit d’un compte personnel (par exemple, Outlook, Hotmail, Gmail, Yahoo, etc.). Cela permettra à 1 utilisateur de se connecter à l’appareil.
3. **Comptes Azure Active Directory (Azure AD):** Il s’agit d’un compte créé dans Azure AD. Ainsi, votre entreprise peut gérer l’appareil HoloLens. Cela permettra à plusieurs utilisateurs de se connecter à la suite commerciale HoloLens de la génération de la gamme HoloLens de l’appareil HoloLens 2.

Pour plus d’informations sur les types d’identité, consultez notre article d' [identité HoloLens](hololens-identity.md) .

### Type de fonctionnalités

Votre configuration requise détermine le mode HoloLens dont vous avez besoin. L’une des fonctionnalités populaires qui s’affichent dans les environnements clients est généralement le mode plein écran. Une liste des principales fonctionnalités de HoloLens et des éditions de HoloLens qui les prennent en charge est disponible [ici](hololens-commercial-features.md).

**Qu’est-ce que le mode plein écran?**

Le mode Kiosk est un moyen de limiter les applications auxquelles un utilisateur a accès. Cela signifie que les utilisateurs sont autorisés à accéder à certaines applications uniquement.

**Quel mode Kiosk ai-je besoin?**

Il existe deux types de modes Kiosk: une application unique et plusieurs applications. Le mode Kiosk sur une seule application permet aux utilisateurs d’accéder à une seule application alors que le mode Kiosk multi-application permet aux utilisateurs d’accéder à plusieurs applications spécifiées. Pour identifier le mode Kiosk approprié pour votre entreprise, vous devez répondre aux deux questions suivantes:

1. **Les utilisateurs ont-ils besoin d’expériences/restrictions différentes?** Prenons l’exemple suivant: l’utilisateur a est un ingénieur de service pour le champ qui a uniquement besoin d’accéder à l’assistance à distance. L’utilisateur B est un stagiaire qui a uniquement besoin d’accéder aux guides.
    1. Si oui, vous devez effectuer les opérations suivantes:
        1. Comptes Azure AD comme méthode de connexion à l’appareil.
        1. Mode plein écran **à plusieurs applications** .
    1. Si non, continuez à la question 2
1. **Avez-vous besoin d’une utilisation multi-App?**
    1. Le mode kiosque **sur plusieurs applications** est requis
    1. Si la réponse à la question 1 et 2 ne vous convient pas, le mode Kiosk à **application unique** peut être utilisé

**Configuration du mode plein écran:**

Il existe deux méthodes principales de déploiement ([packages de mise en service](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) et [GPM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) pour déployer le mode kiosque pour HoloLens. Ces options seront abordées plus loin dans le document. Toutefois, vous pouvez utiliser les liens ci-dessus pour accéder aux sections correspondantes de ce document.

### Scénarios spécifiques aux applications et aux applications

La plupart des procédures décrites dans ce document s’appliquent également aux applications suivantes:

| Applications | Scénarios spécifiques à l’application |
| --- | --- |
| Assistance à distance | [Communication entre locataire](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| Guides  | *À venir* |
|Applications personnalisées | *À venir* |

### Déterminer la méthode d’inscription

1. Inscription en bloc avec un jeton de sécurité dans un package de mise en service.  
  Avantages: il s’agit de l’approche la plus automatisée.
  Cons: utilise le paramètre initial côté serveur  
1. Inscription automatique sur la connexion de l’utilisateur.  
  Avantages: approche la plus simple  
  Cons: les utilisateurs devront terminer la configuration une fois le package de mise en service appliqué.
1. _non recommandé_ -inscription manuelle après l’installation.  
  Avantages: possibilité de s’inscrire après la configuration  
  Cons: la majeure partie de l’approche et des appareils ne peuvent pas être gérés de manière centralisée tant qu’ils ne sont pas inscrits manuellement.

  Vous trouverez plus d’informations [ici](hololens-enroll-mdm.md)

### Déterminer si vous avez besoin de créer un package de mise à service

Il existe deux méthodes pour configurer un appareil HoloLens (packages de mise en service et MDMs). Nous vous suggérons d’utiliser votre appareil mobile pour configurer votre appareil HoloLens. Toutefois, dans certains cas, il est préférable d’utiliser un package de mise à niveau:

1. Vous voulez configurer le HoloLens pour ignorer l’OOBE (out-of-Box Experience)
1. Vous rencontrez des problèmes lors du déploiement d’un certificat dans un réseau complexe. La plupart du temps, vous pouvez déployer des certificats à l’aide de la gestion des périphériques mobiles (y compris dans les environnements complexes). Toutefois, certains scénarios nécessitent le déploiement de certificats via le package de mise à service.

Voici quelques configurations HoloLens que vous pouvez appliquer dans un package d’approvisionnement:

- Application de certificats à l’appareil
- Configuration d'une connexion Wi-Fi
- Pré-configurer des questions originales telles que la langue et les paramètres régionaux
- (HoloLens 2) inscrire en bloc dans la gestion des appareils mobiles
- (HoloLens v1) Appliquer la clé pour activer Windows Holographic for Business

Si vous décidez d’utiliser les packages de mise en service, suivez [ce guide](hololens-provisioning.md).

## Obtenir de l'aide

Obtenez de l’aide via le site du support Microsoft.

[Classer une demande de support](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
