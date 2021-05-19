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
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440335"
---
# <a name="admin-less-operating-system"></a>Système d’exploitation sans administrateur

HoloLens 2 minimise la surface d’élévation des privilèges en désactivant la prise en charge du groupe Administrateurs et en limitant les codes d'application UWP tiers pour qu'il s'exécutent uniquement en tant qu'utilisateurs standard dans le bac à sable AppContainer. Ce code est uniquement autorisé à accéder aux ressources protégées par des fonctionnalités explicitement présentées dans l’application pour un utilisateur de niveau non élevé, en plus des ressources accessibles à tous les AppContainers.
Ces fonctionnalités d’application continuent d’utiliser le modèle de classification à trois niveaux :
  * Général
  * Restricted (Restreint)
  * Windows

Les composants Windows peuvent également profiter du bac à sable AppContainer via les UWP système. Pour en savoir plus sur la plate-forme universelle Windows (UWP), consultez la [documentation UWP](https://docs.microsoft.com/windows/uwp/) . De plus, les composants Windows nécessitant une réduction des privilèges plus importante (comme les pages de contenu des navigateurs ou les analyseurs syntaxiques) utilisent le bac à sable LPAC (Less Privileged AppContainer), qui coupe l'accès à l'ensemble des ressources accessibles à tous les AppContainers.

## <a name="device-owner"></a>Propriétaire de l’appareil

Enfin, l’exécution d’opérations spécifiques à l’ensemble de l’appareil, telles que l’ajout de l’appareil à un client ou la gestion des utilisateurs, n’est autorisée que pour les « propriétaires des appareils ». Les utilisateurs de l’appareil sont ajoutés à ce groupe via l’une des étapes suivantes :
  * Le premier utilisateur de l'appareil est toujours désigné comme propriétaire. 
> [!IMPORTANT]
>Pour les utilisateurs Azure AD, l'exception à cette règle est la suivante : si le dispositif est joint à Azure AD via Autopilot ou l'inscription groupée à Azure AD, qui utilise un utilisateur non réel. Dans ce cas, le premier utilisateur de l'AAD à se connecter à l'appareil peut ne pas devenir automatiquement propriétaire de l'appareil, à moins que cet utilisateur n'ait le rôle d'«administrateur global» ou d'«administrateur d'appareil» attribué dans le portail Azure. Pour plus d'informations, voir la note ci-dessous.  

  * Lorsqu'un utilisateur est promu propriétaire à partir de l'interface utilisateur des paramètres par un autre propriétaire de l'appareil.
  * Si le propriétaire du dispositif n'est plus disponible (il quitte l'entreprise) et que le dispositif est joint à Azure AD, l'administrateur locataire peut changer le propriétaire de l'appareil en un nouvel utilisateur dans le portail Azure. Les administrateurs globaux et les administrateurs de dispositifs d'un locataire Azure AD sont implicitement connectés en tant que propriétaires sur le dispositif sans avoir à suivre l'une des étapes précédentes.  

 Les administrateurs informatiques peuvent gérer les accès des applications par le biais de politiques de [confidentialité](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 

> [!NOTE]
> Si vous souhaitez en savoir plus sur les personnes nommées propriétaire d’un appareil sur un appareil lié à Azure AD, consultez la [documentation « Attribuer un administrateur local »](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mais en gardant à l’esprit que « administrateur local » veut dire « propriétaire de l’appareil » car le rôle d’administrateur n’existe pas sur HoloLens).