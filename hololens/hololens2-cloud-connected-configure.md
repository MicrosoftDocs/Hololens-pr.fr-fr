---
title: Guide de déploiement – Cloud connecté HoloLens 2 déploiement à grande échelle avec l’assistance à distance-configurer
description: découvrez comment configurer des configurations pour inscrire des appareils HoloLens sur un réseau connecté au Cloud à grande échelle avec l’assistance à distance.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635141"
---
# <a name="configure---cloud-connected-guide"></a>Configurer-Guide connecté au Cloud

Dans cette section du guide, nous&#39;ons comment configurer l’inscription automatique pour votre locataire et comment appliquer des licences pour Intune et l’assistance à distance.

## <a name="azure-users-and-groups"></a>Utilisateurs et groupes Azure

Azure et Intune par cette extension utilisent des utilisateurs et des groupes pour vous aider à attribuer des configurations et des licences. Pour valider ce processus de déploiement et pouvoir effectuer un appel d’assistance à distance d’un utilisateur à un autre, vous&#39;aurez besoin de deux comptes d’utilisateur.

Nous pouvons créer un groupe d’utilisateurs unique dans le but d’attribuer des licences. Nous pouvons joindre les deux utilisateurs au même groupe et appliquer une licence pour Intune et Remote Assist à ce groupe.

Si vous n’avez pas&#39;avoir accès à deux comptes Azure AD dans un groupe d’utilisateurs que vous pouvez utiliser ; Voici les guides de démarrage rapide pour :

- [Comment créer un utilisateur](/mem/intune/fundamentals/quickstart-create-user)
- [Comment créer un groupe](/mem/intune/fundamentals/quickstart-create-group)
- [Ajouter des utilisateurs à un groupe](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – ajouter des utilisateurs créés à créer un groupe
- [Configurer Azure AD pour permettre à un groupe d’utilisateurs de joindre des appareils](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) : Assurez-vous que le nouveau groupe d’utilisateurs est autorisé à inscrire des appareils sur Azure ad

## <a name="auto-enrollment-on-hololens-2"></a>Inscription automatique sur HoloLens 2

pour bénéficier d’une expérience fluide et transparente, la configuration de Azure Active Directory Join (AADJ) et de l’inscription automatique à Intune pour les appareils HoloLens 2 est la méthode à suivre. Cela permet aux utilisateurs d’entrer leurs informations d’identification de connexion à l’organisation pendant l’OOBE et de s’inscrire automatiquement auprès d’Azure AD et d’inscrire l’appareil dans MDM.

en utilisant [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), vous pouvez sélectionner des services et naviguer dans quelques pages jusqu’à ce que nous puissions sélectionner obtenir une version d’évaluation Premium. vous remarquerez peut-être Azure Active Directory Premium 1 et 2, pour l’inscription automatique P1 suffit. Nous pouvons sélectionner Intune et sélectionner l’étendue de l’utilisateur pour l’inscription automatique, puis sélectionner le groupe qui a été créé précédemment.

Pour obtenir des informations détaillées et des étapes, lisez le guide sur [l’activation de l’inscription automatique pour Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="application-licenses"></a>Licences d’application

Une licence d’application permet à un utilisateur d’installer des applications achetées par l’entreprise ou de procéder à une mise à niveau d’une version d’évaluation gratuite vers la version complète d’une application. Les licences d’application peuvent être appliquées à des utilisateurs, à des groupes d’utilisateurs ou à des groupes d’appareils. Vous&#39;aurez besoin de licences d’assistance à distance pour permettre aux utilisateurs de votre organisation d’utiliser l’assistance à distance. Dans le cadre de ce guide, nous allons attribuer des licences d’assistance à distance au groupe d’utilisateurs que nous avons créé ci-dessus dans [les groupes et utilisateurs Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).

La configuration requise pour les licences peut être différente selon que l’utilisateur effectuera l’appel d’assistance à distance à partir d’un appareil ou sera un collaborateur distant de Microsoft Teams. par défaut, les cases à cocher assistance à distance et Teams sont toutes deux marquées. Dans le cadre de ce guide, nous vous suggérons de laisser les cases par défaut cochées.

1. En savoir plus sur les différentes [licences et les spécifications de produits par rôle](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Il existe plusieurs types de licences d’assistance à distance. vous devez donc veiller à obtenir les bonnes solutions pour répondre à vos besoins.
2. Vous&#39;avoir besoin d' [acquérir la licence](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Appliquez vos licences](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) au groupe.

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au Cloud-déployer](hololens2-cloud-connected-deploy.md)