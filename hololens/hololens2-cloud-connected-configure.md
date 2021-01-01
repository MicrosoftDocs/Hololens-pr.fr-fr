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
ms.openlocfilehash: 042a29fe436b21ca37a2fcd7921fc53d6a9686d5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253041"
---
# Configurer-Guide connecté dans le Cloud

Dans cette section du guide, nous&#39;découvrir comment configurer l’inscription automatique pour votre client, et comment appliquer des licences pour Intune et l’assistance à distance.

## Utilisateurs et groupes Azure

Azure et Intune par cette extension utilisent des utilisateurs et des groupes pour vous permettre d’affecter des configurations et des licences. Pour pouvoir valider ce flux de déploiement et être en mesure de passer un appel d’assistance à distance d’un utilisateur à un autre, vous&#39;avoir deux comptes d’utilisateurs.

Il est possible de créer un groupe d’utilisateurs unique pour pouvoir affecter des licences. Nous pouvons rejoindre les deux utilisateurs dans le même groupe et appliquer une licence pour Intune et l’assistance à distance à ce groupe.

Si vous n’avez pas&#39;avez déjà accès à deux comptes Azure AD dans un groupe d’utilisateurs que vous pouvez utiliser; Voici les guides de démarrage rapide pour:

- [Comment créer un utilisateur](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Créer un groupe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Ajouter des utilisateurs à un groupe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : ajouter des utilisateurs créés pour créer un groupe
- [Configuration d’Azure AD pour permettre à un groupe d’utilisateurs de joindre des appareils](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) : s’assurer que le nouveau groupe d’utilisateurs est autorisé à inscrire des appareils sur Azure ad

## Inscription automatique sur HoloLens 2

Pour disposer d’une connaissance fluide et transparente, la configuration d’Azure Active Directory Join (AADJ) et de l’inscription automatique sur Intune pour les appareils HoloLens 2 vous permet d’effectuer des opérations. Cela permettra aux utilisateurs d’entrer les informations d’identification de votre organisation dans OOBE et de s’inscrire automatiquement auprès d’Azure AD et de l’inscrire dans la gestion des périphériques mobiles.

Le [Gestionnaire de points de terminaison Microsoft](https://endpoint.microsoft.com/#home)vous permet de sélectionner des services et de naviguer dans quelques pages jusqu’à ce que nous puissions sélectionner obtenir une version d’évaluation Premium. Vous remarquerez peut-être qu’Azure Active Directory Premium 1 et 2 pour l’inscription automatique P1 est suffisant. Nous pouvons sélectionner Intune et sélectionner la portée utilisateur pour l’inscription automatique, puis sélectionner le groupe créé précédemment.

Pour obtenir des informations et des étapes complets, consultez le Guide d’activation de l' [inscription automatique pour Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## Licences d’application

Une licence d’application permet à un utilisateur d’installer des applications achetées d’entreprise ou de procéder à la mise à niveau d’une version d’évaluation gratuite vers la version complète d’une application. Les licences d’application peuvent être appliquées à des utilisateurs, des groupes d’utilisateurs ou des groupes d’appareils. Vous avez&#39;besoin de licences à distance pour permettre aux utilisateurs de votre organisation d’utiliser l’assistance à distance. Dans le cadre de ce guide, nous allons affecter des licences d’assistance à distance au groupe d’utilisateurs que nous avons créé au-dessus des [utilisateurs et groupes Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).

La configuration requise pour les licences peut différer selon que l’utilisateur effectue l’appel d’assistance à distance à partir d’un appareil ou qu’il s’agit d’un collaborateur distant de Microsoft Teams. Par défaut, les cases à cocher assistance à distance et équipes sont marquées. Dans le cadre de ce guide, nous vous suggérons de laisser activé les cases par défaut.

1. En savoir plus sur les différentes [licences et les spécifications de produit par rôle](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Il existe plusieurs types de licences Remote Assist pour vous permettre d’obtenir les bons éléments appropriés en fonction de vos besoins.
2. Vous&#39;avoir besoin d' [acquérir la licence](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Appliquez vos licences](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) au groupe.

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement de connexion Cloud-déploiement](hololens2-cloud-connected-deploy.md)