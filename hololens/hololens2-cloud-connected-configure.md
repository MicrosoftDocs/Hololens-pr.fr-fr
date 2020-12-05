---
title: Guide de déploiement-déploiement d’HoloLens 2 connecté dans le Cloud à l’échelle de l’assistance à distance-Configuration
description: Comment configurer des configurations pour inscrire des appareils HoloLens sur un réseau connecté sur le Cloud
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196295"
---
# Configurer-Guide connecté dans le Cloud

Dans cette section du guide, nous&#39;allons passer en revue la configuration de l’inscription automatique pour votre client et la manière d’appliquer des licences pour les éléments Intune et Remote Assist.

## Utilisateurs et groupes Azure

Azure et Intune par cette extension utilisent des utilisateurs et des groupes pour vous permettre d’affecter des configurations et des licences. Pour pouvoir valider ce flux de déploiement et être en mesure de passer un appel d’assistance à distance d’un utilisateur à un autre, vous&#39;avoir 2 comptes d’utilisateurs.

Il est possible de créer un groupe d’utilisateurs unique pour pouvoir affecter des licences. Nous pouvons rejoindre les deux utilisateurs dans le même groupe et appliquer une licence pour Intune et l’assistance à distance à ce groupe.

Si vous n’avez pas&#39;avez déjà accès à deux comptes AAD dans un groupe d’utilisateurs, vous pouvez le faire. Voici les guides de démarrage rapide pour:

- [Comment créer un utilisateur](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Créer un groupe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Ajouter des utilisateurs à un groupe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : ajouter des utilisateurs créés pour créer un groupe
- [Configurer AAD pour permettre à un groupe d’utilisateurs de joindre des appareils](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) : s’assurer que le nouveau groupe d’utilisateurs est autorisé à inscrire des appareils à AAD

## Inscription automatique sur HoloLens 2

Pour disposer d’une connaissance fluide et transparente, la configuration d’Azure Active Directory Join (AADJ) et de l’inscription automatique sur Intune pour les appareils HoloLens 2 vous permet d’effectuer des opérations. Cela permettra aux utilisateurs d’entrer simplement les informations d’identification de votre organisation au cours de l’OOBE et de s’inscrire automatiquement auprès de AAD et de l’inscrire dans la gestion des périphériques mobiles.

Le [Gestionnaire de points de terminaison Microsoft](https://endpoint.microsoft.com/#home) vous permet de sélectionner des services et de naviguer dans quelques pages jusqu’à ce que nous puissions sélectionner obtenir une version d’évaluation Premium. Vous remarquerez que l’inscription automatique P1 est suffisante pour Azure Active Directory Premium 1 et 2. Nous pouvons sélectionner Intune et sélectionner la portée utilisateur pour l’inscription automatique, puis sélectionner le groupe créé précédemment.

Pour obtenir des informations et des étapes complets, consultez le guide sur [l’activation de l’inscription automatique pour Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## Licences d’application

Une licence d’application permet à un utilisateur d’installer des applications achetées d’entreprise ou de procéder à la mise à niveau d’une version d’évaluation gratuite vers la version complète d’une application. Les licences d’application peuvent être appliquées à des utilisateurs, des groupes d’utilisateurs ou des groupes d’appareils. Vous avez&#39;besoin de licences à distance pour permettre aux utilisateurs de votre organisation d’utiliser l’assistance à distance. Dans le cadre de ce guide, nous allons affecter des licences d’assistance à distance au groupe d’utilisateurs que nous avons créé au-dessus des [utilisateurs et groupes Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).

La configuration requise pour les licences peut différer selon que l’utilisateur effectue l’appel d’assistance à distance à partir d’un appareil ou qu’il s’agit d’un collaborateur distant de Microsoft Teams. Par défaut, les cases à cocher assistance à distance et équipes sont marquées. Dans le cadre de ce guide, nous vous suggérons de ne pas activer les cases à cocher par défaut.

1. En savoir plus sur les différentes [licences et les spécifications de produit par rôle](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Il existe plusieurs types de licences Remote Assist pour vous permettre d’obtenir les bons éléments appropriés en fonction de vos besoins.
2. Vous&#39;avoir besoin d' [acquérir la licence](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Appliquez vos licences](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) au groupe.

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement de connexion Cloud-déploiement](hololens2-cloud-connected-deploy.md)