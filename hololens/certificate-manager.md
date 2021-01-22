---
title: Gestionnaire de certificats
description: Découvrez comment installer, gérer et supprimer manuellement des certificats sur des appareils de réalité mixte HoloLens 2.
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
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283685"
---
# Gestionnaire de certificats

- Amélioration des outils d’audit, de diagnostic et de validation pour la sécurité et la conformité des appareils via le nouveau Gestionnaire de certificats. Cette fonctionnalité vous permettra de déployer, dépanner et valider vos certificats à l’échelle des environnements commerciaux.

Dans Windows Holographic, version 20H2, nous ajoutons un gestionnaire de certificats dans l’application Paramètres HoloLens 2. Go to **Settings > Update & Security > Certificates**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs ont désormais amélioré les outils d’audit, de diagnostic et de validation pour garantir que les appareils restent sécurisés et conformes. 

-   **Audit :** Possibilité de vérifier qu’un certificat est déployé correctement ou de confirmer qu’il a été supprimé correctement. 
-   **Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de résoudre les problèmes. 
-   **Validation :** Vérifier qu’un certificat a l’objectif et qu’il est fonctionnel peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux, avant de déployer des certificats à grande échelle.

Pour trouver rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher des propriétés de certificat individuelles, sélectionnez le certificat et cliquez sur **Info.** 

L’installation de certificat prend actuellement en charge les fichiers .cer et .crt. Les propriétaires d’appareils peuvent installer des certificats dans l’ordinateur local et l’utilisateur actuel ;  Tous les autres utilisateurs peuvent uniquement s’installer dans l’utilisateur actuel. Les utilisateurs peuvent uniquement supprimer les certificats installés directement à partir de l’interface utilisateur paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme.

## Pour installer un certificat : 

1.  Connectez votre HoloLens 2 à un PC.
1.  Placez le fichier de certificat que vous souhaitez installer à un emplacement sur votre HoloLens 2.
1.  Accédez **à Paramètres App > Update & Security > Certificates**et sélectionnez Installer un certificat.
1.  Cliquez **sur Importer un** fichier et accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **l’emplacement de la boutique.**
1.  Sélectionnez **magasin de certificats.**
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

## Pour supprimer un certificat : 
1. Accédez à **Paramètres App > Update et Security > Certificates**.
1. Recherchez le certificat par nom dans la zone de recherche.
1. Sélectionnez le certificat.
1. Cliquez sur **Supprimer**
1. Sélectionnez **Oui** lorsque vous y invitez une confirmation.


![Visionneuse de certificats dans l’application Paramètres sous Ceritifcates](images/certificate-viewer-device.jpg)

![Image montrant comment utiliser l’interface utilisateur certificat pour installer un certificat dans Paramètres.](images/certificate-device-install.jpg)
