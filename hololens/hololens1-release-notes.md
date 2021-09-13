---
title: notes de publication de la HoloLens 1re (gen)
description: en savoir plus sur les mises à jour dans chaque nouvelle version de HoloLens.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032784"
---
# <a name="hololens-1st-gen-release-notes"></a>notes de publication de la HoloLens 1re (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1er génération) maintenance à Long terme
HoloLens (1re génération) a entré l’état de maintenance à Long terme (LTS). les futures mises à jour seront axées sur les problèmes et les correctifs de sécurité, tout en conservant la parité des fonctionnalités avec le Windows 10 Holographique version 1809 pour HoloLens (1er génération).

pour les développeurs, cela signifie que les applications HoloLens (1re génération) ne prennent pas en charge l’API OpenXR.  Ces casques restent pris en charge dans Unity 2019 LTS avec le backend de l’API WinRT pour le cycle de vie complet de Unity 2019 LTS à mi-2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographique, version 1809

> **s’applique à :** HoloLens (1re génération)

| Fonctionnalité | Détails |
|---|---|
| **Menu actions rapides** | Quand vous êtes dans une application, le geste de floraison ouvre un menu d’actions rapides pour vous permettre d’accéder rapidement aux fonctionnalités système couramment utilisées sans avoir à sortir de l’application. <br> pour plus d’informations sur le menu actions rapides en mode plein écran, consultez [configurer des HoloLens en mode plein écran](hololens-kiosk.md) .<br><br> |
| **Arrêter la capture vidéo dans le menu actions rapides ou de démarrage** | si vous démarrez la capture vidéo à partir du menu menu Démarrer ou actions rapides, vous pouvez arrêter l’enregistrement à partir du même emplacement. (N’oubliez pas que vous pouvez toujours le faire avec les commandes vocales.) |
| **Project à un appareil compatible Miracast** | Project le contenu de votre HoloLens sur un appareil ou une TV/moniteur à proximité si vous utilisez une carte d’affichage Microsoft.  dans **démarrer**, sélectionnez **Connecter**, puis sélectionnez l’appareil vers lequel vous souhaitez projeter. **Remarque :** vous pouvez déployer HoloLens pour utiliser Miracast projection sans activer le mode développeur. |
| **Nouvelles notifications** | affichez et répondez aux toasts de notification sur HoloLens, comme vous le feriez sur un PC. Pointez le regard pour y répondre ou les faire disparaître (ou, si vous êtes dans une expérience immersive, utilisez le geste de floraison). |
| **superpositions de HoloLens**<br>(sélecteur de fichiers, clavier, boîtes de dialogue, etc.) | Vous voyez maintenant des superpositions telles que le clavier, les boîtes de dialogue, le sélecteur de fichiers, etc. quand vous utilisez des applications immersifs. |
| **Interface utilisateur de superposition de commentaires visuels pour la modification du volume** | lorsque vous utilisez les boutons monter/descendre du volume sur votre HoloLens vous voyez un affichage visuel du volume. |
| **Nouvelle interface utilisateur pour le démarrage de l’appareil** | Un indicateur de chargement a été ajouté pendant le processus de démarrage pour fournir des commentaires visuels en cours de chargement par le système. redémarrez votre appareil pour voir le nouvel indicateur de chargement, c’est-à-dire entre le message « Hello » et le logo de démarrage Windows. |
| **Partage proche** | l’ajout du Windows l’expérience de partage proche, ce qui vous permet de partager une capture avec un appareil Windows proche. quand vous capturez une photo ou une vidéo sur HoloLens (ou que vous utilisez le bouton partager d’une application telle que Microsoft Edge), sélectionnez un appareil Windows proche à partager. |
| **Partager à partir de Microsoft Edge** | le bouton partager est désormais disponible sur Microsoft Edge windows sur HoloLens. dans Microsoft Edge, sélectionnez **partager**. utilisez le sélecteur de partage HoloLens pour partager du contenu web. |

#### <a name="for-international-customers"></a>Pour les clients internationaux

| Fonctionnalité | Détails |
| --- | --- |
| Versions localisées en chinois et en japonais | utilisez HoloLens avec une interface utilisateur localisée pour le chinois simplifié ou le japonais, y compris le clavier Pinyin localisé, la dictée et les commandes vocales.<br>[Découvrez comment installer les versions en chinois et en japonais de HoloLens.](hololens1-install-localized.md) |
| Synthèse vocale (TTS) | La fonctionnalité de synthèse vocale prend désormais en charge le chinois, le japonais et l’anglais. |

#### <a name="for-administrators"></a>Pour les administrateurs

| Fonctionnalité |  Détails  |
|---|----|
| [Activer l’approvisionnement après l’installation](hololens-provisioning.md) | vous pouvez maintenant appliquer un package de configuration du runtime à tout moment à l’aide de **Paramètres**. |
| Accès affecté avec les groupes de Azure AD | vous pouvez maintenant utiliser des groupes de Azure AD pour la configuration de Windows accès affecté pour configurer la configuration d’un kiosque à une ou plusieurs applications. |
| ÉPINGLer la connexion au commutateur de profil à partir de l’écran de connexion | L’authentification par code confidentiel est maintenant disponible pour un **autre utilisateur**. |
| Se connecter avec le fournisseur d’informations d’identification Web à l’aide du mot de passe | Vous pouvez maintenant sélectionner l’option de connexion au globe pour lancer la connexion Web avec votre mot de passe. Dans l’écran de connexion, sélectionnez **options de connexion** , puis sélectionnez l’option globe pour lancer la connexion Web. Entrez votre nom d’utilisateur si nécessaire, puis votre mot de passe. <br>**Remarque :** Vous pouvez choisir de contourner les options du code PIN/de la carte à puce quand vous y êtes invité pendant la connexion au Web. |
| Lire les informations matérielles de l’appareil via MDM afin que les appareils puissent être suivis par numéro de série | les administrateurs informatiques peuvent voir et suivre les HoloLens par numéro de série de l’appareil dans leur console MDM. Pour plus d’informations sur la disponibilité des fonctionnalités et obtenir des instructions, consultez la documentation MDM. |
| définir HoloLens nom de l’appareil via MDM (renommer) | les administrateurs informatiques peuvent voir et renommer HoloLens appareils dans leur console MDM. Pour plus d’informations sur la disponibilité des fonctionnalités et obtenir des instructions, consultez la documentation MDM. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, version 1803 pour Microsoft HoloLens

> **s’applique à :** HoloLens (1re génération)

Windows 10, la version 1803, est la première mise à jour des fonctionnalités de Windows Holographic for Business depuis sa publication dans Windows 10, version 1607. Cette mise à jour introduit les modifications suivantes :

- auparavant, vous pouviez uniquement vérifier que la licence de mise à niveau pour la Suite commerciale a été appliquée à votre appareil HoloLens en vérifiant si le VPN était une option disponible sur l’appareil. à présent, **Paramètres**  >  **système** affichera **Windows Holographic for Business** après l’application de la licence de mise à niveau. [découvrez comment déverrouiller les fonctionnalités de Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- vous pouvez afficher le numéro de build du système d’exploitation dans les propriétés de l’appareil dans l’application explorateur de fichiers et dans l' [outil Windows device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- l’approvisionnement d’un appareil HoloLens est désormais plus facile grâce à l’assistant nouvelle configuration des **appareils HoloLens** dans l’outil concepteur de Configuration Windows. Dans l’Assistant, vous pouvez configurer l’expérience d’installation et les connexions réseau, définir le mode développeur et obtenir des jetons de Azure AD en bloc. [Découvrez comment utiliser l’Assistant d’approvisionnement simple pour HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Lorsque vous créez un compte local dans un package d’approvisionnement, le mot de passe n’expire plus tous les 42 jours.

- vous pouvez [configurer HoloLens comme une borne d’application unique ou multi-application](hololens-kiosk.md). le mode plein écran à plusieurs applications vous permet de configurer un HoloLens pour exécuter uniquement les applications que vous spécifiez, et empêche les utilisateurs d’apporter des modifications.

- le protocole MTP (Media Transfer Protocol) est activé pour vous permettre de connecter l’appareil HoloLens à un pc par le biais d’une connexion USB et de transférer des fichiers entre HoloLens et le PC. Vous pouvez également utiliser l’application Explorateur de fichiers pour déplacer et supprimer des fichiers à partir de HoloLens.

- auparavant, une fois que vous vous êtes connecté à l’appareil avec un compte Azure Active Directory (Azure AD), vous deviez **ajouter l’accès professionnel** dans **Paramètres** pour accéder aux ressources de l’entreprise. À présent, vous vous connectez avec un compte Azure AD et l’inscription s’effectue automatiquement.

- Avant de vous connecter, vous pouvez choisir l’icône réseau sous le champ mot de passe pour choisir un autre réseau de Wi-Fi auquel vous connecter. Vous pouvez également vous connecter à un réseau invité, tel qu’un hôtel, un centre de conférence ou une entreprise.

- vous pouvez désormais facilement [partager des HoloLens avec plusieurs personnes](hololens-multiple-users.md) à l’aide de comptes de Azure AD.

- En cas d’échec de l’installation ou de la connexion, choisissez l’option **collecter les informations** pour obtenir les journaux de diagnostic à des fins de dépannage.

- Les utilisateurs individuels peuvent synchroniser leur messagerie d’entreprise sans inscrire leur appareil dans la gestion des appareils mobiles (MDM). Vous pouvez utiliser l’appareil avec un compte Microsoft, télécharger et installer l’application de messagerie et ajouter un compte de messagerie directement.

- vous pouvez vérifier l’état de synchronisation MDM d’un appareil dans **Paramètres**  >  **comptes**  >  **accès aux informations professionnelles ou scolaires**  >  . Dans la section État de la **synchronisation des appareils** , vous pouvez démarrer une synchronisation, voir zones gérées par MDM et créer et exporter un rapport de diagnostics avancés.
