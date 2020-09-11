---
title: Séparation et isolation d’état
description: Séparation et isolation d’état
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, séparation d’état, séparation et isolation d’état, hololens2, hololens2 Security, présentation de la sécurité, architecture de sécurité, architecture, architecture hololens2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 702b713b7a930a2e4909dffaa895856d918d11c9
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009412"
---
# Séparation et isolation d’état

La séparation et l’isolation d’état protègent les parties critiques du système d’exploitation Hololens2 contre toutes modifications comme celles requises pour que le système d’exploitation démarre dans un état approuvé. Avec la technologie d’isolation, les applications non approuvées sont déplacées vers un environnement bac à sable isolé, afin de s’assurer qu’elles n’affectent pas la sécurité du système.

## Séparation d’état

La séparation d’état sur HoloLens2 améliore considérablement la sécurité et la facilité de maintenance (les mises à jour) et vous aide à protéger les données de votre application.  Voici comment la séparation d’état fonctionne :
  * Le système d’exploitation principal est stocké dans le volume de système d’exploitation principal (système d’exploitation MicrosoftOS de mise à jour approuvé ou vérifié).
  * Les différentes parties du système d’exploitation qui peuvent être modifiées au moment de l’exécution (par exemple, les pilotes et les configurations pouvant être téléchargés) utilisent la séparation d’état pour partitionner les données et les stocker dans des emplacements de stockage distincts et sécurisés.
  * Chaque emplacement de stockage sécurisé dispose de stratégies de sécurité distinctes, offrant divers avantages en matière de sécurité, comme décrit dans la section suivante.

## Avantages d’une séparation d’état

  * Sécurité: la séparation d’état proposée dans HoloLens2 améliore considérablement l’intégrité des plateformes, la résistance aux programmes malveillants et la protection des données utilisateur. En séparant la partie inaltérable du système d’exploitation et en la dotant d’une protection en intégrité ou grâce à la lecture seule, la séparation d’état diminue énormément les chances des programmes malveillants de survivre à un redémarrage à froid. 
  * Mises à jour: avec HoloLens2, une fois que le système d’exploitation principal n’est plus modifiable et est proprement séparé du reste des données de l’appareil, les mises à jour deviennent simples et fiables.  De plus, la séparation d’état constitue le point de départ essentiel pour les mises à jour considérablement plus rapides, ce qui permet de remplacer le système d’exploitation en une seule étape (une unité atomique).
  * Réinitialisation de l’appareil: la réinitialisation HoloLens2 efface les données générées par l’utilisateur et les données d’application utilisateur sur l’appareil, y compris les emplacements de stockage internes et externes. Elle préserve les applications actuelles du système d’exploitation et les applications principales de sécurité, ainsi que les applications personnalisées Microsoft et OEM (préinstallées). Ces applications préinstallées peuvent être réactivées sur l’appareil une fois la réinitialisation terminée.

### États de séparation d’état

La séparation d’état garantit que le système d’exploitation ne peut être modifié que par les composants d’appareils approuvés par Microsoft et que seul l’état de valeur élevée est autorisé à être conservé au fil des redémarrages. D’autres états du système n’existent que pendant la durée de la session de démarrage et sont éliminés après un redémarrage. La séparation d’état rétablit rapidement l’état d’origine de l’appareil. Les états Windows Holographique Entreprise peuvent être divisés en catégories distinctes:
  * Système d’exploitation principal (état inaltérable)
  * Données de système d’exploitation (état modifiable) 
  * Données utilisateur (état modifiable)

Chacun de ces états d’exploitation HoloLens2 est décrit dans la section suivante.

#### Système d’exploitation principal

État immuable composé de fichiers exécutables et de données qui ne sont pas modifiables et qui ne peuvent être changées que par Microsoft pendant l’installation des mises à jour. Au cours de ces mises-à-jour du système d’exploitation principal, une nouvelle image contenant le dernier état de fonctionnement souhaité est activée.
L’état inaltérable est souligné par une lecture seule (ou protégé en intégrité), empêchant la survie de tout programme malveillant avec des privilèges élevés. Voici les fichiers et données exécutables protégés dans l’état immuable:
  * Pilotes de la boîte de réception WindowsHolographique
  * Fichiers binaires du système d'exploitation
  * Pilotes de la boîte de réception Windows
  * Paramètres Windows Holographique statiques stockés dans la ruche du registre Windows (HKLM)
    * Par exemple: HKLM stocke les informations de configuration des applications installées sur un ordinateur. Il stocke également les informations pour détecter le matériel et les pilotes correspondants.
En les protégeant au sein de l’état immuable (par une protection en lecture seule et en intégrité), nous nous assurons que le système d’exploitation principal démarre toujours dans un état approuvé. De plus, lors de la réinitialisation d’un appareil, nous sommes sûrs que l’appareil démarre uniquement dans les composants qui figurent sur cette section immuable. 

#### Données de système d’exploitation 

Notez que les fichiers exécutables et les données qui sont modifiables au moment de l’exécution (et qui ne sont pas cruciales au fonctionnement du système d’exploitation) peuvent être rejetés et recréés lorsque les données sont endommagées ou compromises. Un état modifiable de valeur élevée est soit requis pour être conservé par le système d’exploitation, soit conservé à l’arrêt du système d’exploitation, et/ou lors des redémarrages des scénarios de système d’exploitation et d’appareils Windows pris en charge. Voici quelques exemples d’états modifiables de valeur élevée:
  * Paramètres de l’appareil général configuré par l’administrateur informatique, tels que la désactivation de l’emplacement pour tous les utilisateurs.
  * Mots de passe associés à la connexion et données d’accès à la connexion au réseau Wi-Fi des appareils mémorisés.
  * Vidages sur incident, y compris les paramètres et les journaux.
  * Pilotes téléchargés à la demande pour les nouveaux appareils détectés.
Un état modifiable de valeur élevée sur HoloLens2 réside sur l’emplacement de sécurité des données du système d’exploitation, soit sous la forme d’un fichier enregistré sur le disque, soit dans une ruche de registre persistant.

#### Données utilisateur

La dernière catégorie de l’état représente les données utilisateur produites ou conservées par les applicationsUWP ou le système d’exploitation. Tous les dossiers utilisateur connus tels que Téléchargements, Documents, Vidéos, Profils utilisateur et HKEY_CURRENT_USER ruche sont également stockés dans cet emplacement. Ces données ne peuvent pas être extraites sans informations d’identification appropriées. Pour en savoir plus sur la protection des données, voir [Chiffrement et protection des données](security-encryption-data-protection.md).

##  Isolation

Pour atteindre cet équilibre, HoloLens2 dispose d’un système d’exploitation central utilisé pour les fonctions principales telles que le démarrage, le contrôle matériel, la connexion, etc. Seules deux séries d’applications s’exécutent sur le système d’exploitation central (les applications préinstallées et les applicationsUWP).

## Code de signature

Le code de signature numérique permet de faire en sorte que les fichiers exécutables et les scripts n’ont pas été modifiés depuis leur signature par une source approuvée, offrant ainsi une authenticité et une intégrité. Par défaut, les autorités que HoloLens2 approuvent sont Microsoft et MicrosoftStore. Les administrateurs informatiques peuvent ajouter de nouveaux certificats à l’appareil via les CSP [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) et [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp). Ils peuvent également utiliser la stratégie [AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) pour faire confiance à d’autres applications [cœur de métier](https://docs.microsoft.com/intune/apps/lob-apps-windows) ou dont la version test a été chargée. Les certificats se situent dans le magasin de certificats de l’ordinateur local stocké dans HKLM/Root si vous utilisez «Appareil», ou dans HKCU si vous utilisez «Utilisateur».

## Protections Defender
HoloLens2 utilise les services Microsoft pour offrir aux utilisateurs un niveau de sécurité avancé:

* [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) est automatiquement activé sur WindowsHolographique par le système d’exploitation et protège contre le hameçonnage et les programmes malveillants, ainsi que le téléchargement de fichiers potentiellement malveillants sur Edge. Il ne peut pas être désactivé par l’utilisateur, mais peut être désactivé par le biais de la stratégie mentionnée.

* Le [Pare-feu Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) empêche le trafic réseau non autorisé de circuler vers et à partir de votre appareil. Celui-ci est activée par défaut et ne peut pas être configurée par le client via des actions ou une stratégie locale. 

* Le [Contrôle d’application WindowsDefender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens2 prend en charge WDAC qui permet aux administrateurs informatiques de distribuer les stratégies de contrôle des applications sur l’appareil. Pour plus d’informations, consultez [Utiliser WDAC sur les appareils HoloLens2 avec MSFTIntune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens). 

Les administrateurs informatiques peuvent gérer le comportement de SmartScreen par le biais de [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen), et celui d’un navigateur avec [ces stratégies](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

