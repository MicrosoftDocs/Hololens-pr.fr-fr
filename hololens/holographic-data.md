---
title: Rechercher et enregistrer des fichiers sur HoloLens
description: Découvrez comment utiliser l’Explorateur de fichiers sur HoloLens pour ouvrir, afficher et gérer des fichiers sur votre appareil de réalité mixte.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283525"
---
# Rechercher, ouvrir et enregistrer des fichiers sur HoloLens

Les fichiers que vous créez sur HoloLens, y compris les photos et les vidéos, sont enregistrés directement sur votre appareil HoloLens. Affichez et gérez-les de la même façon que vous gériez les fichiers sur Windows 10 :

- Utilisation de l’application Explorateur de fichiers pour accéder aux dossiers locaux.
- Dans le stockage d’une application.
- Dans un dossier spécial (par exemple, la vidéothèque ou la bibliothèque de musique).
- Utilisation d’un service de stockage qui inclut une application et un s picker de fichiers (tel que OneDrive).
- Utilisation d’un PC de bureau connecté à votre HoloLens à l’aide d’un câble USB, à l’aide de la prise en charge du protocole MTP (Media Transfer Protocol).

## Afficher des fichiers sur HoloLens à l’aide de l’Explorateur de fichiers

> S’applique à tous les appareils HoloLens 2 et HoloLens (1ère génération) à partir de la mise à jour [d’avril 2018 de Windows 10 (RS4) pour HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Utilisez l’Explorateur de fichiers sur HoloLens pour afficher et gérer des fichiers sur votre appareil, y compris des objets 3D, des documents et des images. Go to **Start**   >  **All apps**File   >  **Explorer** to get started.

> [!TIP]
> Si aucun fichier n’est répertorié dans l’Explorateur de fichiers, sélectionnez **Cet appareil** dans le volet supérieur gauche.

Si vous ne voyez aucun fichier dans l’Explorateur de fichiers, le filtre « Récent » peut être actif (l’icône de l’horloge est mise en surbrillable dans le volet gauche). Pour résoudre ce problème, sélectionnez l’icône de **document** Cet appareil dans le volet gauche (sous l’icône de l’horloge), ou ouvrez le menu et sélectionnez **Cet appareil.**

## Rechercher et afficher vos photos et vidéos

[La capture de réalité](holographic-photos-and-videos.md) mixte vous permet de prendre des photos et des vidéos de réalité mixte sur HoloLens.  Ces photos et vidéos sont enregistrées dans le dossier Pellicule de l’appareil.

Vous pouvez accéder aux photos et vidéos prises avec HoloLens en :

- accès au pellicule directement via [l’application Photos.](holographic-photos-and-videos.md)
- téléchargez des photos et des vidéos sur le stockage cloud en synchroniseant vos photos et vidéos sur OneDrive.
- à l’aide de la page De capture de réalité mixte du [Portail d’appareil Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### Application Photos

L Photos’application est l’une des applications par défaut dans le **menu** Démarrer et est intégrée avec HoloLens. En savoir plus sur [l’utilisation Photos’application pour afficher du contenu.](holographic-photos-and-videos.md)

Vous pouvez également installer [l’application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir du Microsoft Store pour synchroniser des photos avec d’autres appareils.

### Application OneDrive

[OneDrive vous](https://onedrive.live.com/) permet d’accéder, de gérer et de partager vos photos et vidéos avec n’importe quel appareil et avec n’importe quel utilisateur. Pour accéder aux photos et vidéos capturées sur HoloLens, téléchargez l’application [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir du Microsoft Store sur votre HoloLens. Une fois téléchargé, ouvrez l’application OneDrive et sélectionnez Téléchargement de l’appareil photo **paramètres**  >  **** et activer le chargement **de l’appareil photo.**

### Se connecter à un PC

Si votre HoloLens exécute la mise à jour [d’avril 2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou une version ultérieure, vous pouvez connecter votre HoloLens à un PC Windows 10 à l’aide d’un câble USB pour parcourir des photos et des vidéos sur l’appareil à l’aide du protocole MTP (media transfer protocol). Vous devez vous assurer que l’appareil est déverrouillé pour parcourir les fichiers si un code confidentiel ou un mot de passe est installé sur votre appareil.  

Si vous avez activé [Windows Device Portal,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)vous pouvez l’utiliser pour parcourir, récupérer et gérer les photos et vidéos stockées sur votre appareil.

## Accéder aux fichiers au sein d’une application

Si une application enregistre des fichiers sur votre appareil, vous pouvez utiliser cette application pour y accéder.

### Demande de fichiers à partir d’une autre application

Une application peut demander à enregistrer un fichier ou ouvrir un fichier à partir d’une autre application à l’aide de [s pickers de fichiers.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### Dossiers connus

HoloLens prend en charge un certain nombre de [dossiers connus dont](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) les applications peuvent demander l’autorisation d’accès.

## Afficher les fichiers HoloLens sur votre PC

Comme pour les autres appareils mobiles, connectez HoloLens à votre PC de bureau à l’aide du protocole MTP (Media Transfer Protocol) et ouvrez l’Explorateur de fichiers sur le PC pour accéder à vos bibliothèques HoloLens pour faciliter le transfert.

Pour voir vos fichiers HoloLens dans l’Explorateur de fichiers sur votre PC :

1. Connectez-vous à HoloLens, puis branchez-le au PC à l’aide du câble USB qui était associé à HoloLens.

1. Sélectionnez **Ouvrir l’appareil pour afficher les fichiers avec l’Explorateur**de fichiers ou ouvrez l’Explorateur de fichiers sur le PC et accédez à l’appareil.

Pour voir des informations sur votre HoloLens, cliquez avec le bouton droit sur le nom de l’appareil dans l’Explorateur de fichiers sur votre PC, puis sélectionnez **Propriétés.**

> [!NOTE]
> HoloLens (1ère génération) ne prend pas en charge la connexion aux disques durs externes ou aux cartes SD.

## Synchronisation avec le cloud

Pour synchroniser des photos et d’autres fichiers à partir de votre HoloLens sur le cloud, installez et installez OneDrive sur HoloLens. Pour obtenir OneDrive, recherchez-le dans le Microsoft Store sur votre HoloLens.

HoloLens ne sauvegarde pas les fichiers et les données d’application. Il est donc bon d’enregistrer vos informations importantes dans OneDrive. Ainsi, si vous réinitialisez votre appareil ou désinstallez une application, vos informations seront alors backed.
