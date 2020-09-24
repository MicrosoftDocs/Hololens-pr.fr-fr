---
title: HoloLens (Gen) Notes de publication
description: En savoir plus sur les mises à jour de chaque nouvelle version de HoloLens.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/12/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: f610de413c9990bd3f8bc4df63fa8c7ed821e32b
ms.sourcegitcommit: 8c036f12a341a063eb7827ee7b70784402dad57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2020
ms.locfileid: "11077671"
---
# HoloLens (Gen) Notes de publication

## HoloLens (1ère génération) maintenance longue durée
HoloLens (1er génération) a entré l’état de maintenance à long terme (LTS). Les mises à jour ultérieures se concentreront sur les correctifs de problème et de sécurité, tout en conservant la parité de fonctionnalité avec la version 1809 de Windows 10, version pour HoloLens (1er génération).

### Windows 10 holographique, version 1809

> **S’applique à:** Hololens (1ère génération)

| Fonctionnalité | Détails |
|---|---|
| **Menu actions rapides** | Lorsque vous travaillez dans une application, le geste de la barre d’activités entraîne l’ouverture d’un menu d’action rapide qui vous permet d’accéder rapidement aux fonctionnalités système fréquemment utilisées sans avoir à quitter l’application. <br> Voir [configurer HoloLens en mode plein écran](hololens-kiosk.md) pour plus d’informations sur le menu actions rapides dans le mode plein écran.<br><br> |
| **Arrêter la capture vidéo à partir du menu Démarrer ou actions rapides** | Si vous démarrez la capture vidéo à partir du menu Démarrer ou du menu actions rapides, vous pouvez arrêter l’enregistrement à partir du même endroit. (N’oubliez pas, vous pouvez toujours le faire avec les commandes vocales.) |
| **Projet sur un appareil compatible Miracast** | Projetez votre contenu HoloLens sur un appareil surface à proximité ou une télévision/moniteur si vous utilisez la carte vidéo Microsoft.  Dans l' **Accueil**, sélectionnez **se connecter**, puis sélectionnez l’appareil sur lequel vous souhaitez projeter. **Remarque:** Vous pouvez déployer HoloLens pour utiliser la projection Miracast sans activer le mode développeur. |
| **Nouvelles notifications** | Affichez et répondez aux notifications Toast sur HoloLens, de la même manière que sur un PC. Pointez dessus pour répondre à ces derniers ou les ignorer (ou, si vous êtes en mode immersive, utilisez le geste de floraison). |
| **Superpositions HoloLens**<br>(sélecteur de fichiers, clavier, boîtes de dialogue, etc.) | Vous verrez désormais des superpositions telles que le clavier, les boîtes de dialogue, le sélecteur de fichiers, etc. lors de l’utilisation des applications immersives. |
| **Interface utilisateur de superposition de retour visuel pour le changement de volume** | Lorsque vous utilisez les boutons monter/descendre du volume sur votre HoloLens, vous verrez un affichage visuel du niveau de volume. |
| **Nouvelle interface utilisateur pour le démarrage de l’appareil** | Un indicateur de chargement a été ajouté lors du processus de démarrage pour fournir un retour visuel que le système charge. Redémarrez votre appareil pour voir le nouvel indicateur de chargement, c’est-à-dire entre le message «Bonjour» et le logo de démarrage de Windows. |
| **Partage à proximité** | L’ajout de l’interface de partage à proximité de Windows, qui vous permet de partager une capture à l’aide d’un appareil Windows proche. Lorsque vous capturez une photo ou une vidéo sur HoloLens (ou utilisez le bouton partager d’une application telle que Microsoft Edge), sélectionnez un appareil Windows à proximité duquel partager. |
| **Partager à partir de Microsoft Edge** | Le bouton partager est désormais disponible dans les fenêtres Microsoft Edge sur HoloLens. Dans Microsoft Edge, sélectionnez **partager**. Utilisez le sélecteur de partage HoloLens pour partager du contenu Web. |

#### Pour les clients internationaux

| Fonctionnalité | Détails |
| --- | --- |
| Builds en chinois et en japonais | Utiliser HoloLens avec une interface utilisateur localisée pour le chinois simplifié ou le japonais, y compris le clavier pinyin localisé, la dictée et les commandes vocales.<br>[Découvrez comment installer les versions en chinois et en japonais de HoloLens.](hololens1-install-localized.md) |
| Synthèse vocale (TTS) | La fonctionnalité de synthèse vocale prend désormais en charge le chinois, le japonais et l’anglais. |

#### Pour les administrateurs

| Fonctionnalité |  Détails  |
|---|----|
| [Activer l’approvisionnement après l’installation](hololens-provisioning.md) | À tout moment, vous pouvez appliquer un package de mise en service de l’exécution à l’aide des **paramètres**. |
| Accès accordé avec les groupes Azure AD | Vous pouvez désormais utiliser les groupes Azure AD pour configurer l’accès accordé à Windows pour configurer une seule ou plusieurs applications Kiosk. |
| ÉPINGLer une connexion sur le commutateur de connexion à partir de l’écran de connexion | Le code confidentiel de connexion est désormais disponible pour les **autres utilisateurs**. |
| Se connecter avec le fournisseur d’informations d’identification Web à l’aide du mot de passe | Vous pouvez maintenant sélectionner l’option de connexion globe pour lancer la connexion Web avec votre mot de passe. Dans l’écran de connexion, sélectionnez **options de connexion** , puis cliquez sur le globe pour lancer la connexion Web. Entrez votre nom d’utilisateur le cas échéant, puis votre mot de passe. <br>**Remarque:** Lorsque vous êtes invité à vous connecter sur le Web, vous pouvez choisir de ne pas utiliser les options code confidentiel/SmartCard. |
| Lire les informations matérielles de périphérique par le biais de la gestion des périphériques mobiles pour pouvoir effectuer le suivi des appareils par numéro de série | Les administrateurs informatiques peuvent consulter et suivre le numéro de série de l’appareil sur son console GPM. Reportez-vous à la documentation de votre GPM pour en savoir plus sur la disponibilité des fonctionnalités. |
| Définir le nom de l’appareil HoloLens via la gestion des périphériques mobiles | Les administrateurs informatiques peuvent afficher et renommer les appareils HoloLens dans leur console GPM. Reportez-vous à la documentation de votre GPM pour en savoir plus sur la disponibilité des fonctionnalités. |

### Windows 10, version 1803 pour Microsoft HoloLens

> **S’applique à:** Hololens (1ère génération)

Windows 10, version 1803, est la première mise à jour de fonctionnalités de Windows holographique pour les entreprises depuis sa publication dans Windows 10, version 1607. Cette mise à jour inclut les modifications suivantes:

- Auparavant, vous pouviez uniquement vérifier que la licence de mise à niveau d’une suite commerciale a été appliquée à votre appareil HoloLens en vérifiant si l’option RPV est disponible sur l’appareil. À présent **Settings**,  >  le**système** de paramètres affiche **Windows holographique pour les entreprises** lorsque la licence de mise à niveau est appliquée. [Découvrez comment déverrouiller les fonctionnalités Windows holographique pour les entreprises](hololens1-upgrade-enterprise.md).

- Vous pouvez afficher le numéro de version du système d’exploitation dans les propriétés de l’appareil dans l’application Explorateur de fichiers et dans l' [outil de récupération de périphériques Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Le déploiement d’un périphérique HoloLens est désormais plus facile grâce à l’Assistant Configuration de **périphériques hololens** dans l’outil concepteur de configuration de Windows. Dans l’Assistant, vous pouvez configurer l’interface de configuration et les connexions réseau, définir le mode développeur et obtenir des jetons Azure AD en bloc. [Découvrez comment utiliser l’Assistant de provisionnement simple pour HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Lorsque vous créez un compte local dans un package de mise en service, le mot de passe n’expire plus tous les 42 jours.

- Vous pouvez [configurer HoloLens en tant que kiosque à une seule application ou à plusieurs applications](hololens-kiosk.md). Le mode Kiosk à plusieurs applications vous permet de configurer une application HoloLens pour exécuter uniquement les applications que vous spécifiez, et empêche les utilisateurs d’apporter des modifications.

- Le protocole MTP (Media Transfer Protocol) est activé de sorte que vous puissiez connecter le périphérique HoloLens à un PC par le biais du protocole USB et transférer des fichiers entre HoloLens et le PC. Vous pouvez également utiliser l’application Explorateur de fichiers pour déplacer et supprimer des fichiers à partir de HoloLens.

- Auparavant, une fois que vous vous êtes connecté à l’appareil à l’aide d’un compte Azure Active Directory (Azure AD), vous deviez **Ajouter l’accès professionnel** aux **paramètres** pour accéder aux ressources de l’entreprise. À présent, vous vous connectez avec un compte Azure AD et l’inscription s’effectue automatiquement.

- Avant de vous connecter, vous pouvez sélectionner l’icône réseau sous le champ mot de passe pour choisir un autre réseau Wi-Fi auquel vous connecter. Vous pouvez également vous connecter à un réseau invité, tel qu’un hôtel, un centre de conférence ou une entreprise.

- Vous pouvez désormais facilement [partager HoloLens avec plusieurs personnes](hololens-multiple-users.md) à l’aide de comptes Azure ad.

- Lors de l’échec de la configuration ou de la connexion, sélectionnez la nouvelle option **collecter les informations** pour obtenir les journaux de diagnostic pour la résolution des problèmes.

- Les utilisateurs individuels peuvent synchroniser leur messagerie d’entreprise sans inscrire leur appareil dans la gestion des périphériques mobiles (GPM). Vous pouvez utiliser l’appareil avec un compte Microsoft, télécharger et installer l’application courrier, et ajouter directement un compte de messagerie.

- Vous pouvez vérifier l’état de synchronisation de la gestion des périphériques mobiles dans les **paramètres**  >  **Accounts**  >  **accéder aux informations de votre entreprise ou de votre établissement scolaire**  >  **Info**. Dans la section État de synchronisation des appareils, vous pouvez démarrer une synchronisation, afficher les zones gérées par la gestion des **périphériques mobiles** , puis créer et exporter un rapport de diagnostics avancés.
