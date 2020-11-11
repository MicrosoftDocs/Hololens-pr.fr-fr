---
title: Gestionnaire de certificats
description: Apprenez-en davantage sur la gestion manuelle des certificats sur HoloLens 2.
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
- HoloLens 2
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163218"
---
# Gestionnaire de certificats

- Amélioration de l’audit, du diagnostic et de l’outil de validation pour la sécurité et la conformité des périphériques via le nouveau gestionnaire de certificats. Cette fonctionnalité vous permet de déployer, de résoudre les problèmes et de valider vos certificats à des fins d’évolution en environnement commercial.

Dans Windows holographique, version 20H2, nous ajoutons un gestionnaire de certificats à l’application paramètres HoloLens 2. Accédez à **paramètres > mettre à jour & certificats de sécurité >**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir la sécurité et la conformité des appareils. 

-   **Audit:** Possibilité de vérifier que le déploiement d’un certificat est correct ou qu’il a été supprimé de manière appropriée. 
-   **Diagnostic:** En cas de problème, le fait de vérifier que les certificats appropriés existent sur l’appareil permet de gagner du temps et d’aider à résoudre les problèmes. 
-   **Validation:** Le fait de vérifier qu’un certificat répond à la finalité prévue et est opérationnel, peut faire gagner du temps, en particulier dans les environnements commerciaux avant de déployer des certificats à des fins d’évolution plus importantes.

Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher les propriétés de chaque certificat, sélectionnez le certificat, puis cliquez sur **informations**. 

Le certificat installation prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent être installés que dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur des paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

## Pour installer un certificat: 

1.  Connectez votre HoloLens 2 à un PC.
1.  Sur votre HoloLens 2, placez le fichier de certificat que vous voulez installer.
1.  Accédez à **paramètres de l’application > mettre à jour & sécurité > certificats**et sélectionnez Installer un certificat.
1.  Cliquez sur **importer le fichier** , puis accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **emplacement du magasin**.
1.  Sélectionnez **magasin de certificats**.
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

## Pour supprimer un certificat: 
1. Accédez à **paramètres d’application de paramètres > de mise à jour et de sécurité > certificats**.
1. Recherchez le certificat par nom dans la zone de recherche.
1. Cliquez sur le certificat.
1. Cliquez sur **supprimer** .
1. Sélectionnez **Oui** lorsque vous êtes invité à confirmer.


![Visionneuse de certificats dans l’application paramètres sous Ceritifcates](images/certificate-viewer-device.jpg)

![Image illustrant l’utilisation de l’interface utilisateur de certificats pour l’installation d’un certificat dans les paramètres.](images/certificate-device-install.jpg)
