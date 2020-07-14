---
title: Architecture de sécurité HoloLens
description: Architecture de sécurité
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, hololens2, hololens2 Security, présentation de la sécurité, architecture de sécurité, architecture, architecture hololens2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8045f534926e0719bd2f8e448809b5a2965346c4
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865714"
---
# Vue d’ensemble et architecture de la sécurité

L'architecture de sécurité HoloLens 2 a été conçue et mise au point d'emblée pour être exempte des problèmes de sécurité hérités du passé, tout en créant une surface d'attaque réduite au minimum. Cette nouvelle architecture innovante offre des emplacements de stockage sécurisés et des éléments de sécurité avancés, avec des mécanismes capables de protéger les systèmes d’exploitation contre les menaces et vulnérabilités potentielles.

HoloLens 2 combine le matériel, les logiciels, les réseaux et les services pour offrir une sécurité de bout en bout, tout en offrant à l'utilisateur une expérience optimale. Avec HoloLens 2, une grande majorité des fonctionnalités de sécurité sont désormais activées automatiquement, ce qui permet de minimiser l’effort nécessaire pour installer et configurer correctement le système d’exploitation.

Windows HoloLens 2 et l’architecture de système d’exploitation proposent les fonctionnalités de sécurité innovantes suivantes:

  * **La séparation et l’isolation d’état**:cette nouvelle architecture protège les parties critiques du système d’exploitation Hololens2 contre toutes modifications comme celles requises pour que le système d’exploitation démarre dans un état approuvé. La technologie d’isolation est utilisée pour limiter les applications non fiables dans une zone de bac à sable (sandbox), afin de s’assurer qu’elles ne peuvent pas influer sur la sécurité du système. Tout le système d’exploitation est segmenté en sections sécurisées, chaque section étant protégée par une combinaison de différentes technologies de sécurité.
  
  * **Protection des données**: en cas de perte ou de vol de l’appareil d’un utilisateur, HoloLens 2 empêche les applications non autorisées de lire les informations sensibles en utilisant le chiffrement de données BitLocker. 
  
  * **Système d’exploitation sans mot de passe**: les anciens systèmes d'exploitation basés sur des mots de passe pouvaient par inadvertance exposer les utilisateurs à des menaces de hameçonnage et étaient souvent responsables de comptes compromis. Windows holographique pour les entreprises élimine l’utilisation des mots de passe pour la connexion MSA et AAD et renforce la protection de l’identité des utilisateurs avec la connexion Windows Hello™ et la connexion FIDO2. 
  
    > [!NOTE]
    > Pour bénéficier de la prise en charge de FIDO2, l'appareil doit être sur Build 19041 ou une version ultérieure. 

  * **Sécurité réseau**: HoloLens 2 offre à l’utilisateur une sécurité réseau accrue via des protocoles améliorés et des paramètres par défaut.
