---
title: Sécurité du système d’exploitation sans administrateur
description: Découvrez les systèmes d’exploitation sans administrateur, les propriétaires d’appareils et la sécurité sur les appareils de réalité mixte HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, sans administrateur, système d’exploitation, système d’exploitation sans administrateur, système d’exploitation avec administrateur, hololens 2, sécurité hololens 2,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034450"
---
# <a name="admin-less-operating-system"></a>Système d’exploitation sans administrateur

HoloLens 2 minimise la surface d’élévation des privilèges en désactivant la prise en charge du groupe Administrateurs et en limitant le code de toutes les applications UWP tiers pour qu’elles s’exécutent seulement en tant qu’utilisateurs standard dans le bac à sable AppContainer. Ce code est autorisé à accéder seulement aux ressources protégées par des fonctionnalités explicitement présentées dans l’application pour un utilisateur de niveau non élevé, en plus des ressources accessibles à tous les AppContainers.
Ces fonctionnalités d’application continuent d’utiliser le modèle de classification à trois niveaux :
  * Général
  * Limitées
  * Windows

Les composants Windows peuvent également tirer parti du bac à sable AppContainer via les UWP système. Pour plus d’informations sur la plateforme Windows universelle (UWP, Universal Windows Platform), consultez la [documentation d’UWP](/windows/uwp/). De plus, les composants Windows nécessitant une réduction des privilèges plus importante (comme les pages de contenu des navigateurs ou les analyseurs syntaxiques) utilisent le bac à sable LPAC (Less Privileged AppContainer), qui coupe l’accès à l’ensemble des ressources accessibles à tous les AppContainers.

## <a name="device-owner"></a>Propriétaire de l’appareil

Enfin, l’exécution d’opérations spécifiques à l’échelle de l’appareil, comme l’ajout de l’appareil à un locataire ou la gestion des utilisateurs, est autorisée seulement aux « propriétaires d’appareil ». Les utilisateurs de l’appareil sont ajoutés à ce groupe via une des étapes suivantes :
  * Le premier utilisateur de l’appareil est toujours désigné comme propriétaire. 
> [!IMPORTANT]
>Pour les utilisateurs Azure AD, l’exception à cette règle est le cas où l’appareil est joint à Azure AD via Autopilot ou l’inscription en bloc à Azure AD, qui utilise un utilisateur non réel. Dans ce cas, le premier utilisateur AAD à se connecter à l’appareil peut ne pas devenir automatiquement propriétaire de l’appareil, à moins que cet utilisateur n’ait le rôle d’«administrateur global» ou d’«administrateur d’appareil» attribué dans le portail Azure. Pour plus d’informations, consultez la note ci-dessous.  

  * Quand un utilisateur est promu propriétaire à partir de l’expérience utilisateur des paramètres par un autre propriétaire de l’appareil.
  * Si le propriétaire de l’appareil n’est plus disponible (il a quitté l’entreprise) et que l’appareil est joint à Azure AD, l’administrateur du locataire peut changer le propriétaire de l’appareil pour un nouvel utilisateur dans le portail Azure. Les administrateurs généraux et les administrateurs d’appareil d’un locataire Azure AD sont implicitement connectés en tant que propriétaires sur l’appareil sans avoir devoir suivre une des étapes précédentes.  

 Les administrateurs informatiques peuvent gérer les accès des applications via des stratégies de [confidentialité](/windows/client-management/mdm/policy-csp-privacy). 

> [!NOTE]
> Si vous voulez en savoir plus sur les personnes rendues propriétaires d’un appareil sur un appareil joint à Azure AD, consultez la [documentation « Affecter un administrateur local »](/azure/active-directory/devices/assign-local-admin) (mais en gardant à l’esprit que « administrateur local » veut dire « propriétaire de l’appareil » car le rôle d’administrateur n’existe pas sur HoloLens).