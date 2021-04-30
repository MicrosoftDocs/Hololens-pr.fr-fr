---
title: Rechercher et enregistrer des fichiers sur HoloLens
description: Découvrez comment utiliser l’Explorateur de fichiers sur HoloLens pour ouvrir, afficher et gérer des fichiers sur votre appareil de réalité mixte.
keywords: procédure, sélecteur de fichiers, fichiers, photos, vidéos, images, OneDrive, stockage, Explorateur de fichiers, hololens
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308597"
---
# <a name="find-open-and-save-files-on-hololens"></a>Rechercher, ouvrir et enregistrer des fichiers sur HoloLens

Les fichiers que vous créez sur HoloLens, y compris les photos et les vidéos, sont enregistrés directement sur votre appareil HoloLens. Affichez et gérez-les de la même façon que vous gérez les fichiers sur Windows 10 :

- Utilisation de l’application de l’Explorateur de fichiers pour accéder aux dossiers locaux.
- Dans le stockage d’une application.
- Dans un dossier spécial (tel que la bibliothèque vidéo ou musicale).
- Utilisation d’un service de stockage qui comprend un sélecteur d’application et de fichier (par exemple, OneDrive).
- À l’aide d’un ordinateur de bureau connecté à votre HoloLens à l’aide d’un câble USB, en prenant en charge MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Afficher les fichiers sur HoloLens à l’aide de l’Explorateur de fichiers

> S’applique à tous les appareils HoloLens 2 et à HoloLens (1re génération) à partir de la [mise à jour 2018 d’avril de Windows 10 (RS4) pour HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Utilisez l’Explorateur de fichiers sur HoloLens pour afficher et gérer les fichiers sur votre appareil, y compris les objets 3D, les documents et les images. Accédez à **Démarrer** l'   >  Explorateur de fichiers de **tous les applications**   >   pour commencer.

> [!TIP]
> Si aucun fichier n’est répertorié dans l’Explorateur de fichiers, sélectionnez **ce périphérique** dans le volet supérieur gauche.

Si vous ne voyez aucun fichier dans l’Explorateur de fichiers, le filtre « récent » peut être actif (l’icône d’horloge est mise en surbrillance dans le volet gauche). Pour résoudre ce problème, sélectionnez l’icône de document de **ce périphérique** dans le volet gauche (sous l’icône d’horloge) ou ouvrez le menu et sélectionnez **cet appareil**.

## <a name="find-and-view-your-photos-and-videos"></a>Rechercher et afficher vos photos et vidéos

La [capture de réalité mixte](holographic-photos-and-videos.md) vous permet de prendre des photos et des vidéos de réalité mixte sur HoloLens.  Ces photos et vidéos sont enregistrées dans le dossier pellicule de l’appareil.

Vous pouvez accéder aux photos et vidéos prises avec HoloLens en :

- accès à l’appareil photo directement par le biais de l' [application photos](holographic-photos-and-videos.md).
- Téléchargement de photos et de vidéos dans le stockage cloud en synchronisant vos photos et vidéos sur OneDrive.
- à l’aide de la page de capture de la réalité mixte du [portail de périphériques Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Application Photos

L’application photos est l’une des applications par défaut dans le menu **Démarrer** et est intégrée avec HoloLens. En savoir plus sur [l’utilisation de l’application photos pour afficher le contenu](holographic-photos-and-videos.md).

Vous pouvez également installer l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir de la Microsoft Store pour synchroniser des photos avec d’autres appareils.

### <a name="onedrive-app"></a>Application OneDrive

[OneDrive](https://onedrive.live.com/) vous permet d’accéder, de gérer et de partager vos photos et vidéos avec n’importe quel appareil et avec n’importe quel utilisateur. Pour accéder aux photos et vidéos capturées sur HoloLens, téléchargez l' [application OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) à partir du Microsoft Store sur votre hololens. Une fois le téléchargement terminé, ouvrez l’application OneDrive et sélectionnez **paramètres**  >  **appareil photo Télécharger**, puis activez l’option chargement de l' **appareil photo**.

### <a name="connect-to-a-pc"></a>Se connecter à un PC

Si votre HoloLens exécute la [mise à jour 2018 de Windows 10 avril](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou une version ultérieure, vous pouvez connecter votre hololens à un PC Windows 10 à l’aide d’un câble USB pour parcourir les photos et les vidéos sur l’appareil à l’aide du protocole MTP (Media Transfer Protocol). Vous devrez vous assurer que l’appareil est déverrouillé pour parcourir les fichiers si vous avez configuré un code confidentiel ou un mot de passe sur votre appareil.  

Si vous avez activé le [portail de périphériques Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), vous pouvez l’utiliser pour parcourir, récupérer et gérer les photos et vidéos stockées sur votre appareil.

## <a name="access-files-within-an-app"></a>Accéder aux fichiers dans une application

Si une application enregistre des fichiers sur votre appareil, vous pouvez utiliser cette application pour y accéder.

### <a name="requesting-files-from-another-app"></a>Demande de fichiers à partir d’une autre application

Une application peut demander l’enregistrement d’un fichier ou l’ouverture d’un fichier à partir d’une autre application à l’aide de [sélecteurs de fichiers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Dossiers connus

HoloLens prend en charge un certain nombre de [dossiers connus](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) auxquels les applications peuvent demander une autorisation d’accès.

## <a name="view-hololens-files-on-your-pc"></a>Afficher des fichiers HoloLens sur votre PC

À l’instar des autres appareils mobiles, connectez HoloLens à votre ordinateur de bureau à l’aide du protocole MTP (Media Transfer Protocol) et ouvrez l’Explorateur de fichiers sur le PC pour accéder à vos bibliothèques HoloLens en vue de faciliter le transfert.

Pour afficher vos fichiers HoloLens dans l’Explorateur de fichiers sur votre ordinateur :

1. Connectez-vous à HoloLens, puis branchez-le sur le PC à l’aide du câble USB fourni avec le HoloLens.

1. Sélectionnez **ouvrir l’appareil pour afficher les fichiers avec l’Explorateur de fichiers** ou ouvrez l’Explorateur de fichiers sur le PC et accédez à l’appareil.

Pour afficher des informations sur votre HoloLens, cliquez avec le bouton droit sur le nom de l’appareil dans l’Explorateur de fichiers sur votre ordinateur, puis sélectionnez **Propriétés**.

> [!NOTE]
> HoloLens (1re génération) ne prend pas en charge la connexion à des disques durs externes ou à des cartes SD.

## <a name="sync-to-the-cloud"></a>Synchroniser avec le Cloud

Pour synchroniser des photos et d’autres fichiers entre votre HoloLens et le Cloud, installez et configurez OneDrive sur HoloLens. Pour obtenir OneDrive, recherchez-le dans le Microsoft Store sur votre HoloLens.

HoloLens ne sauvegarde pas les fichiers et les données de l’application. il est donc judicieux d’enregistrer vos éléments importants sur OneDrive. De cette façon, si vous réinitialisez votre appareil ou que vous désinstallez une application, vos informations seront sauvegardées.
