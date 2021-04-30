---
title: Vue d’ensemble de l’assistance à distance de HoloLens 2
description: Apprenez à inscrire des appareils HoloLens 2 sur un réseau connecté au Cloud avec l’assistance à distance Dynamics 365.
keywords: HoloLens, gestion, Cloud connected, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308565"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guide de déploiement – connexion Cloud HoloLens 2 avec l’assistance à distance-vue d’ensemble

Ce guide aide les professionnels de l’informatique à planifier et déployer des appareils Microsoft HoloLens 2 dans leur organisation avec l’objectif global de faire en sorte que ces appareils soient connectés à votre organisation avec Dynamics 365 Remote Assist prêt à l’emploi. Gardez à l’esprit qu’il s’agit d’un modèle pour les déploiements de preuve de concept dans votre organisation dans un large éventail de cas d’utilisation de HoloLens 2.

Au cours du guide, nous allons aborder l’inscription de vos appareils dans la gestion des appareils, appliquer des licences en fonction des besoins et vérifier que vos utilisateurs finaux sont en mesure d’utiliser immédiatement l’assistance à distance lors de la configuration de l’appareil. Pour ce faire, nous allons passer en revue les éléments importants de l’infrastructure nécessaire à la configuration et à l’exécution du déploiement à l’échelle avec HoloLens 2.

![Bannière Cloud connecté](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a>Dans ce guide

Ce guide a pour objectif de configurer l’assistance à distance au sein de votre organisation sur vos appareils HoloLens. Nous aborderons les indispensables pour atteindre cet objectif. Afin de conserver le focus sur cet objectif, certaines préparations et configurations seront présélectionnées afin d’optimiser ce déploiement ou de réduire les éléments nécessaires à la configuration. Vous êtes informé de ces choix et pouvez personnaliser votre déploiement en fonction des besoins de votre entreprise.

Il s’agit d’une configuration similaire au [scénario a : déploiement sur des appareils Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), qui est une bonne option pour de nombreux déploiements de preuve de concept, notamment :

- Les réseaux Wi-Fi sont généralement entièrement ouverts sur Internet et les services de Cloud Computing
- Azure AD rejoindre avec l’inscription automatique MDM--MDM (Intune) géré
- Les utilisateurs se connectent avec leur propre compte d’entreprise (Azure AD)
  - Un ou plusieurs utilisateurs par appareil pris en charge
- Différents niveaux de configurations de verrouillage de périphérique sont appliqués en fonction de cas d’usage spécifiques, de l’ouverture complète à la borne d’application unique

![Scénario connecté au Cloud](./images/cloud-connected-guide-diagram.png)

Aucune autre restriction ou configuration d’appareil ne sera appliquée dans ce guide. Toutefois, nous vous encourageons à explorer ces options après avoir terminé.

## <a name="learn-about-remote-assist"></a>En savoir plus sur l’assistance à distance

L’assistance à distance permet la maintenance et la réparation collaboratives, l’inspection à distance, ainsi que le partage des connaissances et la formation. En connectant des personnes dans des rôles et des emplacements différents, un technicien utilisant l’assistance à distance peut se connecter à un collaborateur distant de Microsoft Teams. Ils peuvent combiner des vidéos, des captures d’écran et des annotations pour résoudre les problèmes en temps réel, même lorsqu’ils ne sont pas&#39;t au même emplacement. Les collaborateurs distants peuvent insérer des images de référence, des schémas et d’autres informations utiles que le technicien&#39;l’espace physique pour qu’ils puissent faire référence au schéma tout en récapitulant les mains et les mains libres sur HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Dans ce guide, vous allez :

Préparation :

> [!div class="checklist"]
> - [En savoir plus sur les éléments essentiels de l’infrastructure pour les appareils HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [En savoir plus sur les Azure AD et en configurer une si vous ne l’avez pas&#39;.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [En savoir plus sur la gestion des identités et sur la façon de configurer au mieux les comptes Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Apprenez-en davantage sur MDM et configurez avec Intune si&#39;vous n’avez pas déjà un prêt.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [En savoir plus sur les exigences de mise en réseau de l’assistance à distance.](hololens2-cloud-connected-prepare.md#network)
> - [Éventuellement : VPN pour se connecter aux ressources de l’Organisation](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurer :

> [!div class="checklist"]
> - [Comment créer des utilisateurs et des groupes.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Comment configurer l’inscription automatique dans Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Comment attribuer vos licences d’application.](hololens2-cloud-connected-configure.md#application-licenses)

Deploy :

> [!div class="checklist"]
> - [Configurez votre HoloLens 2 et validez l’inscription.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valider, vous pouvez effectuer un appel d’assistance à distance.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mise à jour :

> [!div class="checklist"]
> - [Comment mettre à jour l’assistance à distance à l’aide de l’application Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Création d’un plan de support.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de développement.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au Cloud-préparer](hololens2-cloud-connected-prepare.md)

