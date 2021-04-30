---
title: Guide de déploiement – connexion d’entreprise HoloLens 2 avec Dynamics 365 guides-gérer
description: Découvrez comment gérer des appareils HoloLens 2 sur un réseau connecté à l’entreprise avec des guides Dynamics 365.
keywords: HoloLens, gestion, connecté à l’entreprise, Dynamics 365 guides, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308800"
---
# <a name="maintain---corporate-connected-guide"></a>Maintenance-Guide connecté à l’entreprise

## <a name="update-hololens"></a>Mettre à jour HoloLens

Microsoft a conçu Windows Update for Business afin d’offrir aux administrateurs informatiques des fonctionnalités de gestion supplémentaires dans Windows Update, telles que la possibilité de déployer des mises à jour sur des groupes d’appareils et de définir des fenêtres de maintenance pour l’installation des mises à jour.

Une méthode courante de gestion des mises à jour consiste à effectuer un report des fonctionnalités de 30 jours. Les administrateurs peuvent ainsi mettre à jour et prévisualiser de nouvelles fonctionnalités, obtenir de la première connaissance et informer votre support technique de toute nouvelle modification.

Découvrez comment [gérer les mises à jour HoloLens](https://docs.microsoft.com/hololens/hololens-updates), y compris les jours planifiés, l’heure planifiée et la définition des heures actives sur l’appareil, afin qu’elles soient mises à jour en dehors des heures de travail.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Comment mettre à jour les guides Dynamics 365 (et les autres applications du Windows Store)

Dynamics 365 guides est un In-Box application et peut être mis à jour via l’application Microsoft Store. Pour toutes les applications téléchargées par le biais du Microsoft Store, elles peuvent être [mises à jour manuellement via l’application Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) elle-même.

## <a name="how-to-update-lob-apps"></a>Comment mettre à jour des applications métier

Les applications métier peuvent être mises à jour de la même façon qu’elles ont été ajoutées à Intune. Les applications peuvent être mises à jour dans Intune en téléchargeant la nouvelle application avec un numéro de version supérieur à la configuration de l’application existante. Lorsque l’appareil est synchronisé avec Intune, il constate que la version de l’application est plus récente et que la nouvelle application est téléchargée et remplace l’ancienne.

1. Pour télécharger l’application la plus récente, accédez aux propriétés du [portail MEM](https://endpoint.microsoft.com/#home)  ->   -> toutes les **applications**  ->  *TheNameOfYourApp*  ->  **.**
2. En regard d’informations sur l’application, sélectionnez **modifier.**
3. Pour la valeur de &quot; Sélectionner le fichier à mettre à jour &quot; , sélectionnez votre fichier.
4. À partir de là, utilisez le menu contextuel pour ouvrir votre Explorateur de fichiers et télécharger la version la plus récente de l’application métier. Veillez à inclure les dépendances en fonction des besoins.

En savoir plus : [déploiement d’applications Intune pour HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plan de développement

Une fois votre appareil inscrit, vous êtes maintenant prêt à déployer d’autres applications métier sur vos appareils. Pour la durée de ce guide, nous utilisons un exemple d’application, mais il est plus probable que vous souhaitiez utiliser des applications personnalisées conçues pour les besoins de votre organisation.

Si vous disposez déjà d’une application métier, vous êtes prêt à [déployer votre application via MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Si vous préférez une autre méthode, consultez la [vue d’ensemble du déploiement d’applications pour HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) afin d’en savoir plus sur les méthodes de déploiement de votre application métier sur vos appareils.

Si vous n’avez pas encore créé votre propre application métier ou que vous êtes en train de créer, passez en revue nos documents de développement de réalité mixte pour [commencer à concevoir et](https://docs.microsoft.com/windows/mixed-reality/design/design) à créer des prototypes ou à apprendre les concepts fondamentaux pour commencer [à utiliser le développement de la réalité mixte.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plan de support

Un plan de support est un excellent élément à mettre en place. Avoir une personne, ou un groupe, a formé la résolution des problèmes du processus d’inscription sur les appareils HoloLens et l’utilisation générale de l’appareil HoloLens au sein de votre organisation est utile. Pour permettre aux utilisateurs de résoudre plus rapidement leurs problèmes, nous vous suggérons de traiter votre processus d’escalade de la même manière :

1. Votre support technique.
2. Votre équipe d’experts HoloLens
3. [Documents HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentation sur la résolution des problèmes HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contacter le support](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gestion des appareils

Ce guide a abordé la configuration de la gestion des appareils mobiles (MDM) et l’a utilisé pour configurer des configurations d’appareils et appliquer des paramètres pour autoriser l’accès en termes de Wi-Fi certificats et proxy. Toutefois, la gestion des appareils mobiles peut également être utilisée pour appliquer des restrictions d’appareil via des fournisseurs de services de chiffrement et des stratégies.

Dans de nombreux cas, les appareils peuvent avoir des restrictions de connectivité, telles que Bluetooth, VPN, USB ou même désactiver l’accès à l’appareil photo ou au microphone. Si l’un de ces avantages vous intéresse, nous vous invitons à lire notre [page des restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)de l’appareil.

Il existe d’autres restrictions d’appareil plus complexes que vous pouvez utiliser. Par exemple :

- Limitation des pages qui peuvent être affichées dans l’application paramètres à l’aide de [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), ce qui permet aux utilisateurs d’accéder uniquement aux paramètres qu’ils doivent ajuster, tels que la modification de leur connexion Wi-Fi.
- Utilisez le [mode plein écran](https://docs.microsoft.com/hololens/hololens-kiosk) pour limiter l’interface utilisateur présentée aux utilisateurs sur un appareil. Vous pouvez définir des bornes pour afficher une seule application ou plusieurs applications avec une page de démarrage personnalisée. Les kiosques peuvent également présenter différentes expériences à différents utilisateurs.
- [Contrôle d’application Windows (WDac)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) pour empêcher l’exécution complète d’applications ou de processus spécifiques.

Si vous souhaitez en savoir plus sur les autres méthodes de gestion des appareils ou sur les restrictions de l’appareil, effectuez l’étape suivante et lisez notre [vue d’ensemble](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)de la gestion des appareils.





