---
title: Guide de déploiement – HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Gérer
description: Découvrez comment gérer des appareils HoloLens 2 sur un réseau connecté d’entreprise à l’aide des guides Dynamics 365.
keywords: HoloLens, gestion, connecté à l’entreprise, guides Dynamics 365, AAD, Azure AD, GESTION DES PÉRIPHÉRIQUES MOBILES, Gestion des appareils mobiles
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448542"
---
# <a name="maintain---corporate-connected-guide"></a>Maintenance - Guide connecté à l’entreprise

## <a name="update-hololens"></a>Mettre à jour HoloLens

Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans WindowsUpdate, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.

Une méthode populaire de gestion des mises à jour consiste à reporter les fonctionnalités de 30 jours. Cela permet aux administrateurs de mettre à jour et d’afficher un aperçu des nouvelles fonctionnalités, en leur permettant d’acquérir des connaissances et d’informer votre support technique de toute nouvelle modification.

Découvrez comment gérer les mises à jour [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates)y compris les jours programmés, l’heure prévue et la définition des heures d’activité sur l’appareil, afin qu’elle soit mise à jour en dehors des heures de travail.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Comment mettre à jour les guides Dynamics 365 (et d’autres applications du Store)

Dynamics 365 Guides est une application In-Box et peut être mise à jour via l’application Microsoft Store. Pour toutes les applications téléchargées via le Microsoft Store, elles peuvent être mises à jour manuellement via l’application [du Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) elle-même.

## <a name="how-to-update-lob-apps"></a>Comment mettre à jour des applications LOB

Les applications LOB peuvent être mises à jour de la même façon qu’elles ont été ajoutées à Intune. Les applications peuvent être mises à jour dans Intune en téléchargeant la nouvelle application avec un numéro de version supérieur vers la configuration d’application existante. Lorsque l’appareil est synchronisé avec Intune, il observe qu’il existe une version d’application plus récente et que l’application la plus récente est téléchargée et remplace l’ancienne application.

1. Pour télécharger la nouvelle application, accédez au portail [MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> All **apps**  ->  *TheNameOfYourApp*  ->  **Properties.**
2. En plus des informations sur l’application, sélectionnez **Modifier.**
3. Pour la valeur du &quot; fichier Select à mettre à &quot; jour, sélectionnez votre fichier.
4. À partir de là, utilisez le menu contexto pour ouvrir votre explorateur de fichiers et télécharger la version la plus récente de l’application LOB. Veillez à inclure les dépendances selon les besoins.

En savoir plus : [Déploiement d’applications Intune pour HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plan de développement

Une fois votre appareil correctement inscrit, vous êtes maintenant prêt à déployer davantage d’applications LOB sur vos appareils. Pendant la durée de ce Guide, nous utilisons un exemple d’application, mais il est plus probable que vous vouliez utiliser des applications personnalisées conçues pour les besoins de votre organisation.

Si vous avez déjà une application LOB, vous êtes prêt à [déployer votre application via mdM.](https://docs.microsoft.com/hololens/app-deploy-intune) Si vous préférez une autre méthode, examinez la vue d’ensemble du déploiement d’applications pour [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) pour en savoir plus sur les méthodes de déploiement de votre application LOB sur vos appareils.

Si vous n’avez pas encore créé votre propre application métier ou que vous êtes encore en cours de création, examinez nos documents de développement de réalité mixte pour commencer la conception et le [prototypage,](https://docs.microsoft.com/windows/mixed-reality/design/design) ou découvrez les concepts de base pour commencer avec le développement de réalité [mixte.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plan de support

Un plan de support est une excellente chose à mettre en place. Une personne, ou un groupe, formé à la résolution des problèmes du processus d’inscription sur les appareils HoloLens et à l’utilisation générale de l’appareil HoloLens au sein de votre organisation est utile. Pour permettre à vos utilisateurs de résoudre plus rapidement leurs problèmes, nous vous suggérons de gérer votre processus d’escalade de la même manière que dans cet ordre :

1. Votre support technique.
2. Votre équipe HoloLens Expert
3. [Documentation HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentation de dépannage HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contacter le support](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gestion des périphériques

Ce guide a abordé la configuration de la gestion des périphériques mobiles (MDM) et l’a utilisé pour configurer certaines configurations d’appareils et appliquer des paramètres pour autoriser l’accès en termes de certificats Wi-Fi et de proxy. Toutefois, la gestion des périphériques de gestion des périphériques peut également être utilisée pour appliquer des restrictions d’appareil via des stratégies et des CSP.

Dans de nombreux cas, les appareils peuvent avoir des restrictions de connectivité, telles que les Bluetooth, VPN, USB ou même la restriction d’accès à la caméra ou au microphone. Si l’un de ces intérêts vous intéresse, nous vous encourageons à lire notre [page commune de restrictions d’appareil](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).

Il existe d’autres restrictions d’appareil plus complexes que vous pouvez utiliser. Par exemple :

- Limiter les pages qui peuvent être vues dans l’application Paramètres à l’aide de [SettingsPageVisibility,](https://docs.microsoft.com/hololens/settings-uri-list)ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils doivent ajuster, tels que la modification de leur connexion Wi-Fi données.
- Utilisez [le mode plein](https://docs.microsoft.com/hololens/hololens-kiosk) écran pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil. Vous pouvez définir des kiosques pour afficher une seule application ou plusieurs applications avec une page de démarrage personnalisée. Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.
- [Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) pour empêcher le lancement complet d’applications ou de processus spécifiques.

Si vous souhaitez en savoir plus sur les méthodes supplémentaires de gestion des appareils ou les restrictions d’appareil, faites l’étape suivante et lisez notre vue d’ensemble de la [gestion des périphériques.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





