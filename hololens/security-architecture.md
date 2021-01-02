---
title: Architecture de sécurité HoloLens
description: Architecture de sécurité
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, hololens2, hololens2 Security, présentation de la sécurité, architecture de sécurité, architecture, architecture hololens2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253251"
---
# <span data-ttu-id="200b7-104">Vue d’ensemble et architecture de la sécurité</span><span class="sxs-lookup"><span data-stu-id="200b7-104">Security overview and architecture</span></span>

<span data-ttu-id="200b7-105">L'architecture de sécurité HoloLens 2 a été conçue et mise au point d'emblée pour être exempte des problèmes de sécurité hérités du passé, tout en créant une surface d'attaque réduite au minimum.</span><span class="sxs-lookup"><span data-stu-id="200b7-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="200b7-106">Cette nouvelle architecture innovante offre des emplacements de stockage sécurisés et des éléments de sécurité avancés, avec des mécanismes capables de protéger les systèmes d’exploitation contre les menaces et vulnérabilités potentielles.</span><span class="sxs-lookup"><span data-stu-id="200b7-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="200b7-107">HoloLens 2 combine le matériel, les logiciels, les réseaux et les services pour offrir une sécurité de bout en bout, tout en offrant à l'utilisateur une expérience optimale.</span><span class="sxs-lookup"><span data-stu-id="200b7-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="200b7-108">Avec HoloLens 2, une grande majorité des fonctionnalités de sécurité sont désormais activées automatiquement, ce qui permet de minimiser l’effort nécessaire pour installer et configurer correctement le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="200b7-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="200b7-109">Windows HoloLens 2 et l’architecture de système d’exploitation proposent les fonctionnalités de sécurité innovantes suivantes:</span><span class="sxs-lookup"><span data-stu-id="200b7-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="200b7-110">**La séparation et l’isolation d’état**:cette nouvelle architecture protège les parties critiques du système d’exploitation Hololens2 contre toutes modifications comme celles requises pour que le système d’exploitation démarre dans un état approuvé.</span><span class="sxs-lookup"><span data-stu-id="200b7-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="200b7-111">La technologie d’isolation est utilisée pour limiter les applications non fiables dans une zone de bac à sable (sandbox), afin de s’assurer qu’elles ne peuvent pas influer sur la sécurité du système.</span><span class="sxs-lookup"><span data-stu-id="200b7-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="200b7-112">Tout le système d’exploitation est segmenté en sections sécurisées, chaque section étant protégée par une combinaison de différentes technologies de sécurité.</span><span class="sxs-lookup"><span data-stu-id="200b7-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="200b7-113">**Protection des données**: en cas de perte ou de vol de l’appareil d’un utilisateur, HoloLens 2 empêche les applications non autorisées de lire les informations sensibles en utilisant le chiffrement de données BitLocker.</span><span class="sxs-lookup"><span data-stu-id="200b7-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="200b7-114">**Système d’exploitation sans mot de passe**: les anciens systèmes d'exploitation basés sur des mots de passe pouvaient par inadvertance exposer les utilisateurs à des menaces de hameçonnage et étaient souvent responsables de comptes compromis.</span><span class="sxs-lookup"><span data-stu-id="200b7-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="200b7-115">Windows holographique pour les entreprises élimine l’utilisation des mots de passe pour la connexion MSA et Azure AD et renforce la protection de l’identité des utilisateurs avec la connexion Windows Hello™ et la connexion FIDO2.</span><span class="sxs-lookup"><span data-stu-id="200b7-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="200b7-116">Pour bénéficier de la prise en charge de FIDO2, l'appareil doit être sur Build 19041 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="200b7-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="200b7-117">**Sécurité réseau**: HoloLens 2 offre à l’utilisateur une sécurité réseau accrue via des protocoles améliorés et des paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="200b7-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
