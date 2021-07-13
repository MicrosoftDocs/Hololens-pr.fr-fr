---
title: Guide de déploiement – Cloud connecté HoloLens 2 déploiement à grande échelle avec l’assistance à distance-maintenance
description: restez à jour grâce à nos conseils pour la maintenance et la prise en charge des appareils HoloLens sur un réseau connecté au Cloud.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635158"
---
# <a name="maintain---cloud-connected-guide"></a>Mettre à jour-guide connecté au Cloud

## <a name="updates"></a>Mises à jour

Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans Windows Update, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.

découvrez comment [gérer les mises à jour HoloLens](/hololens/hololens-updates) , y compris les jours planifiés, l’heure planifiée et la définition des heures actives sur l’appareil afin qu’il soit mis à jour en dehors des heures de travail.

l’assistance à distance est une application In-Box et peut être mise à jour via l’application Microsoft Store. pour toutes les applications téléchargées par le biais du Microsoft Store elles peuvent être [mises à jour manuellement via l’application Microsoft Store](/hololens/holographic-store-apps#update-apps) elle-même.

## <a name="support-plan"></a>Plan de support

Un plan de support est un excellent élément à mettre en place. une personne ou un groupe est formé à la résolution des problèmes du processus d’inscription sur les appareils HoloLens et l’utilisation générale de l’appareil HoloLens au sein de votre organisation est utile. Pour permettre aux utilisateurs de résoudre plus rapidement leurs problèmes, nous vous suggérons de traiter votre processus d’escalade de la même manière :

1. Votre support technique.
2. votre équipe d’experts HoloLens
3. [documentation HoloLens](/hololens/)  /  [documentation sur la résolution des problèmes HoloLens](/hololens/hololens-troubleshooting)
4. [Contacter le support](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plan de développement

Une fois votre appareil inscrit, vous êtes prêt à déployer des applications métier (applications métier) sur vos appareils. Il s’agit d’applications personnalisées conçues pour votre organisation&#39;besoins.

Si vous disposez déjà d’une application métier, vous&#39;préparer [le déploiement de votre application via MDM](/hololens/app-deploy-intune). si vous&#39;d préférer une autre méthode, consultez la [vue d’ensemble du déploiement de l’application pour HoloLens 2](/hololens/app-deploy-overview) pour en savoir plus sur les méthodes de déploiement de votre application métier sur vos appareils.

Si vous&#39;avez pas encore créé votre propre application métier ou que vous êtes en train de créer, passez en revue nos documents de développement de réalité mixte pour [commencer à concevoir et](/windows/mixed-reality/design/design) à créer des prototypes ou à apprendre les concepts fondamentaux pour commencer [à utiliser le développement de la réalité mixte.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Gestion des appareils 

Bien que ce guide soit abordé sur la configuration de la gestion des appareils mobiles (MDM), il n’a pas été utilisé pour appliquer des restrictions d’appareil ou des stratégies ont été appliquées aux appareils. La gestion des appareils peut être utilisée pour autoriser l’accès en envoyant des certificats ou limiter l’accès avec diverses restrictions d’appareil. 

dans de nombreux cas, les appareils peuvent avoir des restrictions de connectivité, telles que Bluetooth, VPN, USB ou même désactiver l’accès à l’appareil photo ou au microphone. Si l’un de ces avantages vous intéresse, nous vous invitons à lire notre [page des restrictions d’appareils courantes](hololens-common-device-restrictions.md).

Il existe d’autres restrictions d’appareil plus complexes que vous pouvez utiliser. Par exemple :

- limitation des pages qui peuvent être affichées dans l’application Paramètres à l’aide de [SettingsPageVisibility](settings-uri-list.md), ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils ont besoin d’ajuster, par exemple la modification de leur connexion Wi-Fi.
- Utilisez le [mode plein écran](hololens-kiosk.md) pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil. Vous pouvez définir des bornes pour afficher une seule application ou plusieurs applications avec une page de démarrage personnalisée. Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.  
- [le contrôle d’Application Windows (WDAC)](windows-defender-application-control-wdac.md) pour empêcher l’exécution complète d’applications ou de processus spécifiques.

Si vous souhaitez en savoir plus sur les différentes méthodes de gestion des appareils ou sur les restrictions de l’appareil, effectuez l’étape suivante et lisez notre vue d’ensemble de la gestion des appareils.

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Lire la présentation de la gestion des fournisseurs de services et des appareils](hololens-csp-policy-overview.md)