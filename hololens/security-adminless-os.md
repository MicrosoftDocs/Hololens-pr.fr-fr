---
title: Sécurité du système d’exploitation sans administrateur
description: Découvrez les systèmes d’exploitation sans administrateur, les propriétaires d’appareils et la sécurité sur les appareils HoloLens mixed reality.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, sans administrateur, système d’exploitation, système d’exploitation sans administrateur, système d’exploitation avec administrateur, hololens 2, sécurité hololens2,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a5c86a5420f3a9b0705667161e6b9440134731d7
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284125"
---
# Système d’exploitation sans administrateur

HoloLens2 minimise la surface d’élévation des privilèges en désactivant la prise en charge du groupe Administrateurs et en limitant les codes d'application UWP tiers pour qu'il s'exécutent uniquement en tant qu'utilisateurs standard dans le bac à sable AppContainer. Ce code est uniquement autorisé à accéder aux ressources protégées par des fonctionnalités explicitement présentées dans l’application pour un utilisateur de niveau non élevé, en plus des ressources accessibles à tous les AppContainers.
Ces fonctionnalités d’application continuent d’utiliser le modèle de classification à trois niveaux:
  * Général
  * Restricted (Restreint)
  * Windows

Les composants Windows peuvent également profiter du bac à sable AppContainer via les UWP système. Si vous souhaitez en savoir plus sur la plateforme Windows universelle (UWP), consultez la [documentation UWP](https://docs.microsoft.com/windows/uwp/). De plus, les composants Windows ayant besoin d’une meilleure réduction des privilèges (par exemple, les pages de contenu du navigateur, les analyseurs) utilisent le bac à sable à faible privilège AppContainer (LPAC) qui coupe l’accès à l’ensemble des ressources accessibles à tous les AppContainers.

## Propriétaire de l’appareil

Enfin, l’exécution d’opérations spécifiques à l’ensemble de l’appareil, telles que l’ajout de l’appareil à un client ou la gestion des utilisateurs, n’est autorisée que pour les «propriétaires des appareils». Les utilisateurs de l’appareil sont ajoutés à ce groupe via l’une des étapes suivantes:
  * Le premier utilisateur de l’appareil est toujours désigné comme étant le Propriétaire. 
    * Il existe une exception à cette règle: si l’appareil est associé à Azure AD, l’utilisateur ayant effectué cette opération devient le propriétaire de l’appareil. Par exemple, cela s’applique si un appareil est lié à Azure AD via Autopilot. Dans ce cas, le premier utilisateur à se connecter à l’appareil n’est pas la personne qui a effectué cette association et ne deviendra donc pas propriétaire de l’appareil. Si vous souhaitez en savoir plus sur les personnes nommées propriétaire d’un appareil sur un appareil lié à Azure AD, consultez la [documentation «Attribuer un administrateur local»](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mais en gardant à l’esprit que «administrateur local» veut dire «propriétaire de l’appareil» car le rôle d’administrateur n’existe pas sur HoloLens).
  * Lorsqu’un utilisateur est promu Propriétaire, à partir des paramètres UX, par un autre propriétaire sur l’appareil.
  * Si le propriétaire de l’appareil n’est plus disponible (s’il quitte l’entreprise par exemple) et que l’appareil est joint à Azure AD, l’administrateur du client peut remplacer le propriétaire de l’appareil par un nouvel utilisateur dans le portail Azure.
Les administrateurs généraux d’un client Azure AD sont implicitement connectés en tant que propriétaires sur l’appareil et n’ont pas besoin d’effectuer les étapes précédentes. 

Les administrateurs informatiques peuvent gérer les autorisations d’accès des applications via les stratégies de [Confidentialité](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 
