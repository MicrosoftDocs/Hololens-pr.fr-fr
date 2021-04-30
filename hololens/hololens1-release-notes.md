---
title: Notes de publication de la mise à jour HoloLens 1re (Gen)
description: En savoir plus sur les mises à jour dans chaque nouvelle version de HoloLens.
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
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "108309051"
---
# <a name="hololens-1st-gen-release-notes"></a>Notes de publication de la mise à jour HoloLens 1re (Gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1ère génération) maintenance à long terme
HoloLens (1re génération) est passé à l’état de maintenance à long terme (LTS). Les futures mises à jour seront axées sur le problème et les correctifs de sécurité, tout en conservant la parité des fonctionnalités avec la version 1809 de Windows 10 holographique, version pour HoloLens (1re génération).

Pour les développeurs, cela signifie que les applications HoloLens (1re génération) ne prennent pas en charge l’API OpenXR.  Ces casques restent pris en charge dans Unity 2019 LTS avec le backend de l’API WinRT pour le cycle de vie complet de Unity 2019 LTS à mi-2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 holographique, version 1809

> **S’applique à :** HoloLens (1ère génération)

| Fonctionnalité | Détails |
|---|---|
| **Menu actions rapides** | Quand vous êtes dans une application, le geste de floraison ouvre un menu d’actions rapides pour vous permettre d’accéder rapidement aux fonctionnalités système couramment utilisées sans avoir à sortir de l’application. <br> Consultez [configurer HoloLens en mode plein écran](hololens-kiosk.md) pour obtenir des informations sur le menu actions rapides en mode plein écran.<br><br> |
| **Arrêter la capture vidéo dans le menu actions rapides ou de démarrage** | Si vous démarrez la capture vidéo à partir du menu Démarrer ou du menu actions rapides, vous pouvez arrêter l’enregistrement à partir du même emplacement. (N’oubliez pas que vous pouvez toujours le faire avec les commandes vocales.) |
| **Projet sur un appareil compatible Miracast** | Projetez votre contenu HoloLens sur un appareil à surface proche ou une TV/moniteur si vous utilisez l’adaptateur d’affichage Microsoft.  Dans **Démarrer**, sélectionnez **se connecter**, puis sélectionnez l’appareil sur lequel vous souhaitez projeter. **Remarque :** Vous pouvez déployer HoloLens pour utiliser la projection Miracast sans activer le mode développeur. |
| **Nouvelles notifications** | Affichez et répondez aux toasts de notification sur HoloLens, comme vous le feriez sur un PC. Pointez le regard pour y répondre ou les faire disparaître (ou, si vous êtes dans une expérience immersive, utilisez le geste de floraison). |
| **Superpositions HoloLens**<br>(sélecteur de fichiers, clavier, boîtes de dialogue, etc.) | Vous voyez maintenant des superpositions telles que le clavier, les boîtes de dialogue, le sélecteur de fichiers, etc. quand vous utilisez des applications immersifs. |
| **Interface utilisateur de superposition de commentaires visuels pour la modification du volume** | Lorsque vous utilisez les boutons monter/descendre du volume sur votre HoloLens, vous verrez un affichage du niveau du volume. |
| **Nouvelle interface utilisateur pour le démarrage de l’appareil** | Un indicateur de chargement a été ajouté pendant le processus de démarrage pour fournir des commentaires visuels en cours de chargement par le système. Redémarrez votre appareil pour voir le nouvel indicateur de chargement, c’est-à-dire entre le message « Hello » et le logo de démarrage Windows. |
| **Partage proche** | Ajout de l’expérience de partage Windows à proximité, qui vous permet de partager une capture avec un appareil Windows proche. Quand vous capturez une photo ou une vidéo sur HoloLens (ou que vous utilisez le bouton partager d’une application telle que Microsoft Edge), sélectionnez un appareil Windows proche avec lequel partager. |
| **Partager à partir de Microsoft Edge** | Le bouton partager est désormais disponible sur les fenêtres Microsoft Edge sur HoloLens. Dans Microsoft Edge, sélectionnez **partager**. Utilisez le sélecteur de partage HoloLens pour partager du contenu Web. |

#### <a name="for-international-customers"></a>Pour les clients internationaux

| Fonctionnalité | Détails |
| --- | --- |
| Versions localisées en chinois et en japonais | Utilisez HoloLens avec une interface utilisateur localisée pour le chinois simplifié ou le japonais, y compris le clavier, la dictée et les commandes vocales pinyin localisés.<br>[Découvrez comment installer les versions en chinois et en japonais de HoloLens.](hololens1-install-localized.md) |
| Synthèse vocale (TTS) | La fonctionnalité de synthèse vocale prend désormais en charge le chinois, le japonais et l’anglais. |

#### <a name="for-administrators"></a>Pour les administrateurs

| Fonctionnalité |  Détails  |
|---|----|
| [Activer l’approvisionnement après l’installation](hololens-provisioning.md) | Vous pouvez maintenant appliquer un package de configuration du runtime à tout moment à l’aide des **paramètres**. |
| Accès affecté avec les groupes de Azure AD | Vous pouvez maintenant utiliser des groupes de Azure AD pour la configuration de l’accès affecté à Windows pour configurer la configuration d’un kiosque à une ou plusieurs applications. |
| ÉPINGLer la connexion au commutateur de profil à partir de l’écran de connexion | L’authentification par code confidentiel est maintenant disponible pour un **autre utilisateur**. |
| Se connecter avec le fournisseur d’informations d’identification Web à l’aide du mot de passe | Vous pouvez maintenant sélectionner l’option de connexion au globe pour lancer la connexion Web avec votre mot de passe. Dans l’écran de connexion, sélectionnez **options de connexion** , puis sélectionnez l’option globe pour lancer la connexion Web. Entrez votre nom d’utilisateur si nécessaire, puis votre mot de passe. <br>**Remarque :** Vous pouvez choisir de contourner les options du code PIN/de la carte à puce quand vous y êtes invité pendant la connexion au Web. |
| Lire les informations matérielles de l’appareil via MDM afin que les appareils puissent être suivis par numéro de série | Les administrateurs informatiques peuvent voir et suivre HoloLens par numéro de série d’appareil dans leur console MDM. Pour plus d’informations sur la disponibilité des fonctionnalités et obtenir des instructions, consultez la documentation MDM. |
| Définir le nom de l’appareil HoloLens via MDM (renommer) | Les administrateurs informatiques peuvent voir et renommer des appareils HoloLens dans leur console MDM. Pour plus d’informations sur la disponibilité des fonctionnalités et obtenir des instructions, consultez la documentation MDM. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, version 1803 pour Microsoft HoloLens

> **S’applique à :** HoloLens (1ère génération)

Windows 10, version 1803, est la première fonctionnalité mise à jour vers Windows holographique for Business depuis sa publication dans Windows 10, version 1607. Cette mise à jour introduit les modifications suivantes :

- Auparavant, vous pouviez uniquement vérifier que la licence de mise à niveau pour la suite commerciale a été appliquée à votre appareil HoloLens en vérifiant si le VPN était une option disponible sur l’appareil. Désormais,   >  le **système** de paramètres affiche **Windows holographique for Business** après l’application de la licence de mise à niveau. [Découvrez comment déverrouiller les fonctionnalités Windows holographique for Business](hololens1-upgrade-enterprise.md).

- Vous pouvez afficher le numéro de build du système d’exploitation dans les propriétés de l’appareil dans l’application Explorateur de fichiers et dans l' [outil de récupération des appareils Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- L’approvisionnement d’un appareil HoloLens est désormais plus facile grâce au nouvel Assistant **approvisionner les appareils hololens** dans l’outil concepteur de configuration Windows. Dans l’Assistant, vous pouvez configurer l’expérience d’installation et les connexions réseau, définir le mode développeur et obtenir des jetons de Azure AD en bloc. [Découvrez comment utiliser l’Assistant d’approvisionnement simple pour HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Lorsque vous créez un compte local dans un package d’approvisionnement, le mot de passe n’expire plus tous les 42 jours.

- Vous pouvez [configurer HoloLens en tant que kiosque à une ou plusieurs applications](hololens-kiosk.md). Le mode plein écran à plusieurs applications vous permet de configurer un HoloLens pour exécuter uniquement les applications que vous spécifiez et empêche les utilisateurs d’apporter des modifications.

- Le protocole MTP (Media Transfer Protocol) est activé pour vous permettre de connecter l’appareil HoloLens à un PC par le biais d’une connexion USB et de transférer des fichiers entre HoloLens et le PC. Vous pouvez également utiliser l’application Explorateur de fichiers pour déplacer et supprimer des fichiers à partir de HoloLens.

- Auparavant, une fois que vous vous êtes connecté à l’appareil avec un compte Azure Active Directory (Azure AD), vous deviez **Ajouter l’accès professionnel** dans **paramètres** pour accéder aux ressources de l’entreprise. À présent, vous vous connectez avec un compte Azure AD et l’inscription s’effectue automatiquement.

- Avant de vous connecter, vous pouvez choisir l’icône réseau sous le champ mot de passe pour choisir un autre réseau de Wi-Fi auquel vous connecter. Vous pouvez également vous connecter à un réseau invité, tel qu’un hôtel, un centre de conférence ou une entreprise.

- Vous pouvez désormais facilement [partager HoloLens avec plusieurs personnes](hololens-multiple-users.md) à l’aide de comptes de Azure ad.

- En cas d’échec de l’installation ou de la connexion, choisissez l’option **collecter les informations** pour obtenir les journaux de diagnostic à des fins de dépannage.

- Les utilisateurs individuels peuvent synchroniser leur messagerie d’entreprise sans inscrire leur appareil dans la gestion des appareils mobiles (MDM). Vous pouvez utiliser l’appareil avec un compte Microsoft, télécharger et installer l’application de messagerie et ajouter un compte de messagerie directement.

- Vous pouvez vérifier l’état de synchronisation MDM d’un appareil dans **paramètres**  >  **comptes**  >  **accéder aux informations professionnelles ou scolaires**  >  . Dans la section État de la **synchronisation des appareils** , vous pouvez démarrer une synchronisation, voir zones gérées par MDM et créer et exporter un rapport de diagnostics avancés.
