---
title: Rechercher et enregistrer des fichiers sur HoloLens
description: Utiliser l’Explorateur de fichiers sur HoloLens pour afficher et gérer des fichiers sur votre appareil
keywords: hololens
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
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828042"
---
# Rechercher, ouvrir et enregistrer des fichiers sur HoloLens

Les fichiers que vous créez sur HoloLens, y compris les photos et vidéos, sont enregistrés directement sur votre appareil HoloLens. Vous pouvez les afficher et les gérer de la même manière que pour gérer les fichiers sur Windows 10:

- Utilisation de l’application Explorateur de fichiers pour accéder aux dossiers locaux.
- Dans le stockage d’une application.
- Dans un dossier spécial (par exemple, la bibliothèque de vidéos ou de musique).
- À l’aide d’un service de stockage incluant une application et un sélecteur de fichiers (par exemple, OneDrive).
- À l’aide d’un PC de bureau connecté à votre HoloLens à l’aide d’un câble USB, avec une prise en charge de MTP (Media Transfer Protocol).

## Afficher des fichiers sur HoloLens à l’aide de l’Explorateur de fichiers

> S’applique à tous les appareils HoloLens 2 et HoloLens (1er génération) en vertu de la [mise à jour 2018 de Windows 10 d’avril (RS4) pour HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Utilisez l’Explorateur de fichiers sur HoloLens pour afficher et gérer des fichiers sur votre appareil, dont des objets, des documents et des images 3D. Accédez à **l'**   >  Explorateur de fichiers de**tous les applications**   >  **File Explorer** pour commencer.

> [!TIP]
> Si aucun fichier n’est répertorié dans l’Explorateur de fichiers, sélectionnez **ce périphérique** dans le volet supérieur gauche.

Si aucun fichier n’apparaît dans l’Explorateur de fichiers, il est possible que le filtre «récent» soit actif (l’icône d’horloge soit mise en évidence dans le volet de gauche). Pour résoudre ce problème, sélectionnez l’icône de document de **ce périphérique** dans le volet gauche, sous l’icône d’horloge, ou ouvrez le menu et sélectionnez **cet appareil**.

## Rechercher et afficher vos photos et vidéos

Le mode de capture de la [réalité combinée](holographic-photos-and-videos.md) vous permet de prendre des photos et vidéos de réalité mélangées sur HoloLens.  Ces photos et vidéos sont enregistrées dans le dossier pellicule de votre appareil.

Vous pouvez accéder aux photos et vidéos prises avec HoloLens par:

- accès à la pellicule directement par le biais de l' [application photos](holographic-photos-and-videos.md).
- Téléchargez des photos et des vidéos dans le stockage cloud en synchronisant vos photos et vidéos sur OneDrive.
- à l’aide de la page de capture de la réalité mixte de [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### Application Photos

L’application photos est l’une des applications par défaut du menu **Démarrer** et est intégrée avec HoloLens. En savoir plus sur [l’utilisation de l’application photos pour afficher du contenu](holographic-photos-and-videos.md).

Vous pouvez également installer l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir de la boutique Microsoft pour synchroniser des photos avec d’autres appareils.

### Application OneDrive

[OneDrive](https://onedrive.live.com/) vous permet d’accéder à vos photos et vidéos et de les partager avec n’importe quel appareil et avec n’importe quel utilisateur. Pour accéder aux photos et vidéos capturées sur HoloLens, téléchargez l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir de la boutique Microsoft sur votre hololens. Une fois le téléchargement terminé, ouvrez l’application OneDrive, sélectionnez **paramètres**de chargement de l'  >  **appareil photo**, puis activez l’option chargement de l' **appareil photo**.

### Se connecter à un PC

Si votre HoloLens exécute la [mise à jour 2018 de Windows 10 d’avril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou version ultérieure, vous pouvez connecter votre hololens à un PC Windows 10 à l’aide d’un câble USB pour parcourir les photos et vidéos de l’appareil à l’aide du protocole MTP (Media Transfer Protocol). Vous devez vous assurer que l’appareil est déverrouillé pour parcourir les fichiers si un code confidentiel ou un mot de passe est configuré sur votre appareil.  

Si vous avez activé [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), vous pouvez l’utiliser pour rechercher, récupérer et gérer les photos et vidéos stockées sur votre appareil.

## Accéder à des fichiers dans une application

Si une application enregistre des fichiers sur votre appareil, vous pouvez utiliser cette application pour y accéder.

### Demande de fichiers à partir d’une autre application

Une application peut demander d’enregistrer un fichier ou d’ouvrir un fichier à partir d’une autre application à l’aide de [sélecteurs de fichiers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### Dossiers connus

HoloLens prend en charge un certain nombre de [dossiers connus](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) auxquels les applications peuvent demander des autorisations d’accès.

## Afficher des fichiers HoloLens sur votre PC

À l’instar des autres appareils mobiles, connectez HoloLens à votre ordinateur de bureau à l’aide du protocole MTP (Media Transfer Protocol), puis ouvrez l’Explorateur de fichiers sur le PC pour accéder à vos bibliothèques HoloLens en vue d’un transfert aisé.

Pour afficher vos fichiers HoloLens dans l’Explorateur de fichiers sur votre PC, procédez comme suit:

1. Connectez-vous à HoloLens, puis branchez-le sur le PC à l’aide du câble USB fourni avec le HoloLens.

1. Sélectionnez **ouvrir l’appareil pour afficher les fichiers**dans l’Explorateur de fichiers ou ouvrir l’Explorateur de fichiers sur le PC, puis accédez à l’appareil.

Pour afficher des informations sur votre HoloLens, cliquez avec le bouton droit sur le nom de l’appareil dans l’Explorateur de fichiers sur votre PC, puis sélectionnez **Propriétés**.

> [!NOTE]
> HoloLens (1ère génération) ne prend pas en charge la connexion à des disques durs externes ou des cartes SD.

## Synchroniser avec le Cloud

Pour synchroniser des photos et d’autres fichiers à partir de votre HoloLens dans le Cloud, installez et configurez OneDrive sur HoloLens. Pour utiliser OneDrive, recherchez-le dans le Microsoft Store sur votre HoloLens.

HoloLens n’enregistre pas les fichiers et les données de l’application, il est donc judicieux d’enregistrer vos éléments importants sur OneDrive. Ainsi, si vous réinitialisez votre appareil ou que vous désinstallez une application, vos informations sont sauvegardées.
