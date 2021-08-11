---
title: Séparation et isolation d’état
description: Découvrez la séparation d’état, l’isolation, la signature de code et les applications Defender sur votre appareil de réalité mixte HoloLens 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, Séparation d’état, Séparation et isolation d’état, hololens 2, sécurité hololens 2, vue d’ensemble de la sécurité, architecture de sécurité, architecture, architecture hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 18c30b4edd649c088f71e479a401c8b286ddfd592f57a5659c3c15b3ec9c854f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665367"
---
# <a name="state-separation-and-isolation"></a>Séparation et isolation d’état

La séparation et l’isolation d’état protègent les parties critiques du système d’exploitation Hololens 2 contre les modifications, comme celles qui sont nécessaires pour que le système d’exploitation démarre dans un état approuvé. Avec la technologie d’isolation, les applications non approuvées sont déplacées vers un environnement de bac à sable isolé, pour garantir qu’elles n’affectent pas la sécurité du système.

## <a name="state-separation"></a>Séparation d’état

La séparation d’état sur HoloLens 2 améliore considérablement la sécurité et la facilité de maintenance (les mises à jour), et vous aide à protéger les données de votre application.  Voici comment la séparation d’état fonctionne :
  * Le système d’exploitation principal est stocké dans le volume de système d’exploitation principal (système d’exploitation Microsoft OS approuvé ou vérifié mettant à jour le système d’exploitation).
  * Les parties du système d’exploitation qui peuvent être modifiées au moment de l’exécution (comme les pilotes et les configurations téléchargeables) utilisent la séparation d’état pour partitionner les données et les stocker dans des emplacements de stockage distincts et sécurisés.
  * Chaque emplacement de stockage sécurisé a des stratégies de sécurité distinctes, offrant différents avantages en matière de sécurité, comme décrit dans la section suivante.

## <a name="state-separation-benefits"></a>Avantages de la séparation d’état

  * Sécurité : la séparation d’état proposée dans HoloLens 2 améliore considérablement l’intégrité des plateformes, la résistance aux programmes malveillants et la protection des données utilisateur. En séparant la partie inaltérable du système d’exploitation, et en la rendant en lecture seule ou avec protection de l’intégrité, la séparation d’état diminue énormément les chances des programmes malveillants de survivre à un redémarrage à froid. 
  * Mises à jour : avec HoloLens 2, une fois que le système d’exploitation principal est non modifiable et est proprement séparé du reste des données de l’appareil, les mises à jour deviennent simples et fiables.  De plus, la séparation d’état constitue le point de départ essentiel pour des mises à jour considérablement plus rapides, ce qui permet de remplacer le système d’exploitation en une seule étape (une unité atomique).
  * Réinitialisation de l’appareil : la réinitialisation HoloLens 2 efface les données générées par l’utilisateur et les données d’application utilisateur sur l’appareil, y compris les emplacements de stockage internes et externes. Elle préserve les applications actuelles du système d’exploitation et les applications critiques de sécurité, ainsi que les applications personnalisées Microsoft et OEM (préinstallées). Ces applications préinstallées peuvent être réactivées sur l’appareil une fois la réinitialisation terminée.

### <a name="state-separation-states"></a>États de la séparation d’état

La séparation d’état garantit que le système d’exploitation ne peut être modifié que par des composants d’appareils approuvés par Microsoft et que seul un état de valeur élevée est autorisé à être conservé au fil des redémarrages. les autres états du système n’existent que pendant la durée de la session de démarrage et sont éliminés après un redémarrage. La séparation d’état rétablit rapidement l’état d’origine de l’appareil. Les états de Windows Holographic for Business peuvent être répartis selon ces catégories distinctes :
  * Système d’exploitation principal - État inaltérable
  * Données du système d’exploitation - État altérable 
  * Données utilisateur - État altérable

Chacun de ces états d’exploitation d’HoloLens 2 est décrit dans la section suivante.

#### <a name="core-operating-system"></a>Système d’exploitation principal

État immuable composé de fichiers exécutables et de données qui sont inaltérables et qui ne peuvent être changés que par Microsoft lors de l’installation des mises à jour. Au cours de ces mises-à-jour du système d’exploitation principal, une nouvelle image contenant le dernier état de fonctionnement souhaité est activée.
L’état inaltérable est marqué en lecture seule (ou est protégé en intégrité), empêchant la persistance des programmes malveillants avec des privilèges élevés. Voici les fichiers et données exécutables protégés dans l’état immuable :
  * Pilotes natifs de Windows Holographique
  * Fichiers binaires du système d’exploitation
  * Pilotes natifs de Windows
  * Paramètres Windows Holographique statiques stockés dans la ruche du Registre Windows (HKLM)
    * Par exemple : HKLM stocke les informations de configuration des applications installées sur une machine. Il stocke également des informations pour détecter le matériel et les pilotes correspondants.
En les protégeant dans l’état immuable (par une protection en lecture seule et en intégrité), nous garantissons que le système d’exploitation principal démarre toujours dans un état approuvé. De plus, lors de la réinitialisation d’un appareil, nous sommes sûrs que l’appareil démarre seulement dans les composants qui se trouvent sur cette section immuable. 

#### <a name="operating-system-data"></a>Données du système d’exploitation 

Il est important de noter que les fichiers exécutables et les données qui sont modifiables au moment de l’exécution (et qui ne sont pas critiques pour le fonctionnement du système d’exploitation) peuvent être supprimés et recréés quand les données sont endommagées ou compromises. Un état modifiable de valeur élevée doit être rendu persistant fonctionnellement par le système d’exploitation, ou considéré comme persistant à travers l’arrêt et/ou les redémarrages du système d’exploitation par les scénarios de système d’exploitation et d’appareils Windows pris en charge. Voici des exemples d’états modifiables de valeur élevée :
  * Paramètres d’appareil général configuré par l’administrateur informatique, comme la désactivation de l’emplacement pour tous les utilisateurs.
  * Réseaux mémorisés par les appareils avec les données d’accès à une connexion réseau Wi-Fi et les mots de passe associés.
  * Images mémoire sur incident, y compris les paramètres et les journaux.
  * Pilotes téléchargés à la demande pour les appareils nouvellement découverts.
Un état altérable de valeur élevée sur HoloLens 2 se trouve à l’emplacement de sécurité des données du système d’exploitation, sous la forme d’un fichier enregistré sur le disque ou dans une ruche de Registre persistant.

#### <a name="user-data"></a>Données utilisateur

La dernière catégorie d’état représente les données utilisateur produites ou conservées par les applications UWP ou le système d’exploitation. Tous les dossiers utilisateur connus, comme Téléchargements, Documents, Vidéos, Profils utilisateur et la ruche HKEY_CURRENT_USER, sont également stockés à cet emplacement. Ces données ne peuvent pas être extraites sans informations d’identification appropriées. Pour plus d’informations sur la protection des données, consultez [Chiffrement et protection des données](security-encryption-data-protection.md).

##  <a name="isolation"></a>Isolation

Pour atteindre cet équilibre, HoloLens 2 a un système d’exploitation central utilisé pour les fonctions principales comme le démarrage, le contrôle du matériel, la connexion, etc. Seules deux ensembles d’applications s’exécutent sur le système d’exploitation central : les applications préinstallées et les applications UWP.

## <a name="code-signing"></a>Signature de code

Le code de signature numérique permet de faire la preuve que les fichiers exécutables et les scripts n’ont pas été modifiés depuis leur signature par une source approuvée, offrant ainsi l’authenticité et l’intégrité. Par défaut, les autorités approuvées par HoloLens 2 sont Microsoft et Microsoft Store. Les administrateurs informatiques peuvent ajouter de nouveaux certificats à l’appareil via les fournisseurs de service de configuration [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) et [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp). Ils peuvent également utiliser la [stratégie AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) pour approuver des [applications métier](/intune/apps/lob-apps-windows) supplémentaires chargées indépendamment. Les certificats se trouvent dans le magasin de certificats de la machine locale stockée dans HKLM/Root si vous utilisez « Appareil », ou dans HKCU si vous utilisez « Utilisateur ».

## <a name="defender-protections"></a>Protections Defender
HoloLens 2 utilise les services Microsoft pour offrir aux utilisateurs un niveau de sécurité avancé :

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) est automatiquement activé sur Windows Holographique par le système d’exploitation, et protège contre le hameçonnage et les programmes malveillants ainsi que contre le téléchargement de fichiers potentiellement malveillants sur Edge. Il ne peut pas être désactivé par l’utilisateur, mais il peut l’être via une stratégie.

* Le [Pare-feu Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) empêche le trafic réseau non autorisé de circuler vers et depuis votre appareil. Il est activé par défaut, et n’est pas configurable par le client via des actions locales ou une stratégie. 

* [Contrôle d’application Windows Defender (WDAC)](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview) : HoloLens 2 prend en charge WDAC, qui permet à l’administrateur informatique d’envoyer (Push) des stratégies de contrôle d’application sur l’appareil. Vous pouvez trouver plus d’informations dans [Utiliser WDAC sur des appareils HoloLens 2 avec Microsoft Intune](/mem/intune/configuration/custom-profile-hololens). 

Les administrateurs informatiques peuvent gérer le comportement de SmartScreen via [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) et le comportement du navigateur via [ces stratégies](/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

