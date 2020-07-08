---
title: Exigences relatives à la licence
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18a583f407b19c5b86870a49b8182d45f46a45f5
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857802"
---
# Exigences relatives à la licence

## Aide sur les licences de gestion des appareils mobiles (MDM)

Si vous prévoyez de gérer vos appareils HoloLens, vous aurez besoin d’Azure AD et d’un appareil mobile. Active Director (AD) ne peut pas être utilisé pour gérer les appareils HoloLens.
Si vous prévoyez l'utilisation d'une gestion des appareils mobiles autre que Intune, des licences [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) sont requises.
Si vous comptez utiliser Intune pour la gestion des appareils mobiles, [voici](https://docs.microsoft.com/intune/fundamentals/licenses) une liste de suites qui comprennent des licences Intune. **Notez qu’Azure Active AD est inclus dans la majorité de ces suites.**

## Identifier les licences nécessaires pour votre scénario et vos produits

### Conditions préalables pour les licences HoloLens

Vous devez peut-être mettre à niveau votre appareil HoloLens de la première génération vers Windows Holographic for Business. (Voir [Fonctionnalités commerciales de HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) pour déterminer si vous avez besoin d'une mise à niveau).

 Si c’est le cas, vous devez effectuer les opérations suivantes:

- Acquérir un fichier XML de licence HoloLens Enterprise
- Appliquer le fichier XML au HoloLens. Pour ce faire, vous pouvez utiliser un [Package d’approvisionnement ](hololens-provisioning.md) ou via votre [Gestionnaire des appareils mobiles ](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### Configuration requise pour la licence Remote Assist

Assurez-vous que vous disposez des licences et des appareils requis. Les mises à jour des licences et des exigences concernant les produits sont disponibles [ici](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).

1. [Licence Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [Équipes Freemium et Teams](https://products.office.com/microsoft-teams/free)
1. [Licence Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Si vous envisagez de mettre en œuvre **[ce scénario entre tenants](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, vous aurez peut-être besoin d’une licence Cloisonnement de l’information. Consultez [cet article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) pour déterminer si une licence Cloisonnement de l’information est nécessaire.

### Guides sur les exigences relatives à la licence

Les mises à jour des licences et des exigences concernant les appareils sont disponibles [ici](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).

1. [Licence Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [PowerBI](https://powerbi.microsoft.com/desktop/)
1. [Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
