---
title: Architecture de la sécurité d’HoloLens
description: Architecture de la sécurité
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, hololens 2, sécurité hololens2, vue d’ensemble de la sécurité, architecture de sécurité, architecture, architecture hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034445"
---
# <a name="security-overview-and-architecture"></a>Vue d’ensemble et architecture de la sécurité

L’architecture de la sécurité d’HoloLens 2 a été conçue et mise au point d’emblée pour être exempte des problèmes de sécurité hérités du passé, tout en créant une surface d’attaque réduite au minimum. Cette nouvelle architecture innovante offre des emplacements de stockage sécurisés et des éléments de sécurité avancés, avec des mécanismes capables de protéger les systèmes d’exploitation contre les menaces et vulnérabilités potentielles.

HoloLens 2 combine matériel, logiciels, réseaux et services pour offrir une sécurité de bout en bout, tout en offrant à l’utilisateur une expérience optimale. Avec HoloLens 2, une grande majorité des fonctionnalités de sécurité sont désormais activées automatiquement, ce qui permet de minimiser l’effort nécessaire pour installer et configurer correctement le système d’exploitation.

Windows HoloLens 2 et l’architecture du système d’exploitation proposent les fonctionnalités de sécurité innovantes suivantes :

  * **Séparation et isolation d’état** : cette nouvelle architecture protège les parties critiques du système d’exploitation HoloLens 2 contre les modifications, comme celles qui sont nécessaires pour que le système d’exploitation principal démarre dans un état approuvé. La technologie d’isolation est utilisée pour limiter les applications non fiables dans une zone de bac à sable (sandbox), afin de s’assurer qu’elles ne peuvent pas impacter la sécurité du système. Tout le système d’exploitation est segmenté en sections sécurisées, chaque section étant protégée par une combinaison de différentes technologies de sécurité.
  
  * **Protection des données** : en cas de perte ou de vol de l’appareil d’un utilisateur, HoloLens 2 empêche les applications non autorisées de lire les informations sensibles en utilisant le chiffrement de données BitLocker. 
  
  * **Système d’exploitation sans mot de passe** : les anciens systèmes d’exploitation basés sur des mots de passe pouvaient par inadvertance exposer les utilisateurs à des menaces par hameçonnage et étaient souvent responsables de comptes compromis. Windows Holographic for Business élimine l’utilisation des mots de passe pour la connexion MSA et Azure AD et renforce la protection de l’identité des utilisateurs avec la connexion Windows Hello™ et la connexion FIDO2. 
  
    > [!NOTE]
    > Pour bénéficier de la prise en charge de FIDO2, l’appareil doit utiliser la build 19041 ou ultérieure. 

  * **Sécurité réseau** : HoloLens 2 offre à l’utilisateur une sécurité réseau accrue par le biais de protocoles améliorés et de paramètres par défaut.
