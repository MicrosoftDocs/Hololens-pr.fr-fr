---
title: Guide de déploiement – Déploiement HoloLens 2 connecté au cloud à l’échelle avec Remote Assist - Configurer
description: Découvrez comment configurer des configurations pour inscrire des appareils HoloLens sur un réseau Connecté au cloud à l’échelle avec Remote Assist.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283885"
---
# Configurer - Guide connecté au cloud

Dans cette section du guide, nous allons&#39;comment configurer l’inscription automatique pour votre client et comment appliquer des licences pour Intune et Remote Assist.

## Utilisateurs et groupes Azure

Azure et Intune par cette extension utilisent des utilisateurs et des groupes pour vous aider à attribuer des configurations et des licences. Pour valider ce flux de déploiement et être en mesure d’effectuer un appel d’assistance à distance d’un utilisateur à un autre, vous&#39;besoin de deux comptes d’utilisateur.

Nous pouvons faire un groupe d’utilisateurs unique dans le but d’attribuer des licences. Nous pouvons joindre les deux utilisateurs au même groupe et appliquer une licence pour Intune et Remote Assist à ce groupe.

Si vous n'&#39;pas déjà accès à deux comptes Azure AD dans un groupe d’utilisateurs, vous pouvez utiliser ; voici les guides de démarrage rapide pour :

- [Comment créer un utilisateur](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Comment créer un groupe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Ajouter des utilisateurs à un groupe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Ajouter des utilisateurs créés pour créer un groupe
- [Configurer Azure AD pour autoriser](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) un groupe d’utilisateurs à joindre des appareils : assurez-vous que le nouveau groupe d’utilisateurs est autorisé à inscrire des appareils dans Azure AD

## Inscription automatique sur HoloLens 2

Pour que l’expérience soit fluide et transparente, la configuration d’Azure Active Directory Join (AADJ) et de l’inscription automatique à Intune pour les appareils HoloLens 2 est la solution. Cela permettra aux utilisateurs d’entrer les informations d’identification de connexion de leur organisation pendant la OOBE, de s’inscrire automatiquement auprès d’Azure AD et d’inscrire l’appareil dans la gestion des périphériques mobiles.

À [l’aide de Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)nous pouvons sélectionner des services et parcourir quelques pages jusqu’à ce que nous sélectionnions Obtenir une version d’évaluation Premium. Vous remarquerez peut-être qu’Azure Active Directory Premium 1 et 2 sont suffisants pour l’inscription automatique P1. Nous pouvons sélectionner Intune et l’étendue utilisateur pour l’inscription automatique, puis sélectionner le groupe précédemment créé.

Pour obtenir des détails complets et des étapes, lisez le guide sur la façon d’activer l’inscription [automatique pour Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## Licences d’application

Une licence d’application permet à un utilisateur d’installer les applications achetées par l’entreprise ou de passer d’une version d’essai gratuite à la version complète d’une application. Les licences d’application peuvent être appliquées à des utilisateurs, des groupes d’utilisateurs ou des groupes d’appareils. Vous&#39;des licences Remote Assist pour que les utilisateurs de votre organisation utilisent Remote Assist. Dans le but de ce guide, nous allons attribuer des licences Remote Assist au groupe d’utilisateurs que nous avons créé ci-dessus dans [Utilisateurs et groupes Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Les conditions requises pour les licences peuvent être différentes selon que l’utilisateur effectuera l’appel d’assistance à distance à partir d’un appareil ou s’il sera un collaborateur distant de Microsoft Teams. Par défaut, les cases à cocher Assistance à distance et Teams sont toutes deux marquées. Pour les besoins de ce guide, nous vous suggérons de laisser les cases par défaut cochées.

1. En savoir plus sur les différentes exigences en matière de [licences et de produits par rôle.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Il existe différents types de licences Remote Assist. Assurez-vous donc d’en obtenir les bonnes pour vos besoins.
2. Vous&#39;devez acquérir [la licence.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Appliquez vos licences](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) au groupe.

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au cloud : déployer](hololens2-cloud-connected-deploy.md)