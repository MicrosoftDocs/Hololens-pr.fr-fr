---
title: Guide de déploiement – Déploiement HoloLens 2 connecté au cloud à l’échelle avec Remote Assist - Maintenir
description: Restez à jour avec nos conseils pour la maintenance et la prise en charge des appareils HoloLens sur un réseau connecté au cloud.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283895"
---
# Maintain - Guide connecté au cloud

## Mises à jour

Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.

Découvrez comment gérer les mises à jour [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) y compris les jours prévus, l’heure prévue et la définition des heures d’activité sur l’appareil afin qu’elle soit mise à jour en dehors des heures de travail.

Remote Assist est une application In-Box et peut être mise à jour via l’application du Microsoft Store. Pour toutes les applications téléchargées via le Microsoft Store, elles peuvent être mises à jour manuellement via [l’application du Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) elle-même.

## Plan de support

Un plan de support est une excellente chose à mettre en place. Il est utile de disposer d’une personne ou d’un groupe formé à la résolution des problèmes de processus d’inscription sur les appareils HoloLens, ainsi qu’à l’utilisation générale de l’appareil HoloLens au sein de votre organisation. Pour permettre à vos utilisateurs de résoudre plus rapidement leurs problèmes, nous vous suggérons de gérer votre processus d’escalade de la même manière que dans cet ordre :

1. Votre support technique.
2. Votre équipe HoloLens Expert
3. [Documentation HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentation de dépannage HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contacter le support](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Plan de développement

Une fois votre appareil correctement inscrit, vous êtes prêt à déployer des applications métier sur vos appareils. Il s’agit d’applications personnalisées conçues pour votre&#39;besoins.

Si vous avez déjà une application métier,&#39;êtes prêt à déployer votre [application via la gestion des](https://docs.microsoft.com/hololens/app-deploy-intune)applications de gestion des&#39;. Si vous&#39;préférez une autre méthode, examinez la vue d’ensemble du déploiement d’application pour [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) pour en savoir plus sur les méthodes de déploiement de votre application LOB sur vos appareils.

Si vous n&#39;avez pas encore créé votre propre application métier ou que vous êtes encore en cours de création, examinez nos documents de développement de réalité mixte pour commencer à concevoir et créer un [prototype](https://docs.microsoft.com/windows/mixed-reality/design/design) ou découvrez les concepts de base pour commencer avec le développement de réalité [mixte.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Gestion des périphériques 

Bien que ce guide a abordé la configuration de la gestion des périphériques mobiles (MDM), il n’a pas été utilisé pour appliquer des restrictions d’appareil ou des stratégies ont été appliquées aux appareils. La gestion des appareils peut être utilisée à la fois pour autoriser l’accès en pushant des certificats ou pour restreindre l’accès avec une variété de restrictions d’appareil. 

Dans de nombreux cas, les appareils peuvent avoir des restrictions de connectivité telles que Bluetooth, VPN, USB ou même la connexion à l’appareil photo ou au microphone. Si l’un de ces intérêts vous intéresse, nous vous encourageons à lire notre [page commune de restrictions d’appareil](hololens-common-device-restrictions.md).

Il existe d’autres restrictions d’appareil plus complexes que vous pouvez utiliser. Par exemple :

- Limiter les pages qui peuvent être vues dans l’application Paramètres à l’aide de [SettingsPageVisibility,](settings-uri-list.md)ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils doivent ajuster, par exemple en modifiant leur connexion Wi-Fi.
- Utilisez [le mode plein](hololens-kiosk.md) écran pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil. Vous pouvez définir des kiosques pour afficher une seule application ou plusieurs applications avec une page de démarrage personnalisée. Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.  
- [Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) pour empêcher le lancement complet d’applications ou de processus spécifiques.

Si vous souhaitez en savoir plus sur les différentes méthodes de gestion des appareils ou les restrictions d’appareil, prenez l’étape suivante et lisez notre vue d’ensemble de la gestion des périphériques.

## Étape suivante

> [!div class="nextstepaction"]
> [Lire la vue d’ensemble des CSP et de la gestion des périphériques](hololens-csp-policy-overview.md)