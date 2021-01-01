---
title: Guide de déploiement-déploiement d’HoloLens 2 connecté dans le Cloud à l’échelle de l’assistance à distance-maintenance
description: Conseils pour la mise à jour des appareils HoloLens via un réseau connecté au Cloud
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252695"
---
# Maintenance-Guide connecté dans le Cloud

## Mises à jour

Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.

Découvrez comment [gérer les mises à jour de HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , y compris les jours prévus, les heures prévues et définir les heures d’activité sur l’appareil pour qu’elle soit mise à jour en dehors des heures de travail.

L’assistance à distance est une application In-Box, qui peut être mise à jour par le biais de l’application Microsoft Store. Pour toutes les applications téléchargées via le Microsoft Store, celles-ci peuvent être [mises à jour manuellement par le biais de l’application Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .

## Plan de support

Un plan d’assistance est un excellent point de départ. Une personne ou un groupe est formé à la résolution des problèmes liés au processus d’inscription sur les appareils HoloLens et à l’utilisation générale du périphérique HoloLens au sein de votre organisation. Pour permettre à vos utilisateurs d’avoir une résolution plus rapide de leurs problèmes, nous vous suggérons de traiter le processus de remontée comme suit:

1. Votre support technique.
2. Votre équipe HoloLens expert
3. [Documents HoloLens](https://docs.microsoft.com/hololens/)  /  [Documents de dépannage HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contacter le support](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Plan de développement

À l’inscription de votre appareil, vous êtes maintenant prêt à déployer des applications métier (LOB) sur vos appareils. Il s’agit d’applications personnalisées conçues pour le&#39;de votre organisation.

Si vous disposez déjà d’une application métier, vous&#39;de nouveau à [déployer votre application via la gestion des](https://docs.microsoft.com/hololens/app-deploy-intune)périphériques mobiles. Si vous&#39;d préfère une méthode différente, passez en revue la [vue d’ensemble du déploiement d’applications pour HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) pour découvrir d’autres méthodes de déploiement de votre application métier sur vos appareils.

Si vous&#39;que vous avez déjà créé votre propre application métier ou si vous êtes en train de créer votre propre application métier, passez en revue nos documents de développement de réalité mixte pour [commencer à concevoir et créer un prototype](https://docs.microsoft.com/windows/mixed-reality/design/design) ou découvrir les principaux concepts de mise en route du développement d’une [réalité mixte.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Gestion des périphériques 

Ce guide propos de la configuration de la gestion des périphériques mobiles (GPM), il n’a pas été utilisé pour appliquer des restrictions à des appareils ou des stratégies. La gestion des appareils peut être utilisée pour autoriser l’accès par le biais de certificats ou limiter l’accès avec diverses restrictions d’appareil. 

Dans de nombreux cas, les appareils peuvent être dotés de restrictions de connectivité, tels que Bluetooth, VPN, USB ou même la désactivation de l’accès à l’appareil photo ou au microphone. Si l’un de ces éléments vous intéresse, nous vous encourageons à lire notre [page de restrictions d’appareil commune](hololens-common-device-restrictions.md).

Vous pouvez utiliser d’autres restrictions d’appareils plus complexes. Par exemple:

- Limiter les pages qui peuvent être affichées dans l’application paramètres en utilisant [SettingsPageVisibility](settings-uri-list.md), ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils ont besoin d’ajuster, par exemple de modifier leur connexion Wi-Fi.
- Utiliser le [mode plein écran](hololens-kiosk.md) pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil. Vous pouvez définir des bornes pour afficher une application unique ou plusieurs applications avec une page de démarrage personnalisée. Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.  
- [Contrôle d’application Windows (WDac)](windows-defender-application-control-wdac.md) pour assurer la totalité du lancement d’applications ou de processus spécifiques.

Si vous souhaitez en savoir plus sur les différentes méthodes de gestion des appareils ou de restrictions d’appareil, passez à l’étape suivante et consultez notre présentation de la gestion des périphériques.

## Étape suivante

> [!div class="nextstepaction"]
> [Lire l’aperçu des fournisseurs de services de cryptographie et de gestion des appareils](hololens-csp-policy-overview.md)