---
title: Mettre à jour HoloLens
description: Consultez le numéro de build, la mise à jour et la restauration des mises à jour de HoloLens.
keywords: procédures, mise à jour, restauration, HoloLens, vérification de la build, numéro de build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828055"
---
# Mettre à jour HoloLens

HoloLens utilise Windows Update comme d’autres appareils Windows 10. Votre HoloLens télécharge et installe automatiquement les mises à jour du système dès qu’il est connecté et qu’il est connecté à Internet, même en mode veille.

Cet article vous guide à travers les outils HoloLens pour:

- affichage de votre version actuelle du système d’exploitation (numéro de Build)
- vérification des mises à jour
- mise à jour manuelle HoloLens
- revenir à une ancienne mise à jour

## Vérifier la version de votre système d’exploitation (numéro de Build)

Vous pouvez vérifier le numéro de version du système (numéro de Build) en ouvrant l’application paramètres et en sélectionnant **système**  >  **à propos**de.

## Rechercher les mises à jour et les mises à jour manuelles

Vous pouvez à tout moment Rechercher les mises à jour dans les paramètres.  Pour afficher les mises à jour disponibles et rechercher les nouvelles mises à jour:

1. Ouvrez l’application **paramètres** .
1. Accédez à **mettre à jour & sécurité**  >  **Windows Update**.
1. Sélectionnez **Rechercher les mises à jour**.

Si une mise à jour est disponible, elle va commencer à télécharger la nouvelle version. Une fois le téléchargement terminé, sélectionnez le bouton **redémarrer maintenant pour lancer** l’installation. Si votre appareil est inférieur à 40% et qu’il n’est pas branché, le redémarrage ne démarrera pas l’installation de la mise à jour.

Lors de l’installation de la mise à jour, le HoloLens affiche les engrenages tournants et un indicateur de progression. Ne désactivez pas votre HoloLens pendant ce temps. Elle redémarrera automatiquement une fois l’installation terminée.

HoloLens applique une mise à jour à la fois.  Si votre HoloLens est supérieur ou égal à 1, vous devrez peut-être exécuter plusieurs fois le processus de mise à jour pour le mettre à jour.

## Revenir à une version précédente-HoloLens 2

Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. Pour cela, vous pouvez utiliser l’Assistant de récupération avancée pour rétablir votre HoloLens sur une version antérieure.

> [!NOTE]
> Revenir à une version antérieure supprime vos fichiers et paramètres personnels.

Pour revenir à une version antérieure de HoloLens 2, procédez comme suit:

1. Assurez-vous que vous n’avez pas de téléphone ou d’appareil Windows branché sur votre ordinateur.
1. Sur votre PC, téléchargez l' [Assistant de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) sur le Microsoft Store.
1. Téléchargez la [version d’HoloLens 2 la plus récente](https://aka.ms/hololens2download).
1. Lorsque vous avez terminé ces téléchargements, ouvrez l' **Explorateur de fichiers**  >  **Downloads**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C. Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.
1. Le compagnon de récupération avancée détecte automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens** .
1. Dans l’écran suivant, sélectionnez **sélection manuelle du package** , puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier avec l’extension. FFU.)
1. Sélectionnez **installer le logiciel**, puis suivez les instructions.

## Revenir à une version précédente-HoloLens (1ère génération)

Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. Pour cela, vous pouvez utiliser l’outil de récupération d’appareils Windows pour réinitialiser votre HoloLens vers la version antérieure.

> [!NOTE]
> Revenir à une version antérieure supprime vos fichiers et paramètres personnels.

Pour revenir à une version antérieure de HoloLens 1, procédez comme suit:

1. Assurez-vous que vous n’avez pas de téléphone ou d’appareil Windows branché sur votre ordinateur.
1. Sur votre PC, téléchargez l' [outil de récupération de périphériques Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Téléchargez le [package de récupération des mises à jour d’anniversaire HoloLens](https://aka.ms/hololensrecovery).
1. À la fin des téléchargements, ouvrez le dossier téléchargements de l' **Explorateur de fichiers**  >  **Downloads**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extract** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide du câble micro-USB qui vous est fourni. Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.
1. Le WDRT détecte automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens** .
1. Dans l’écran suivant, sélectionnez **sélection manuelle du package** , puis choisissez le fichier d’installation contenu dans le dossier que vous avez sélectionné dans l’étape 4. (Recherchez un fichier avec l’extension. FFU.)
1. Sélectionnez **installer le logiciel**, puis suivez les instructions.

> [!NOTE]
> Si WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre PC. Si cela ne fonctionne pas, sélectionnez **mon périphérique n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.

## Programme Windows Insider sur HoloLens

Vous voulez découvrir les dernières fonctionnalités de HoloLens?  Si tel est le cas, rejoignez le programme Windows Insider; vous aurez accès à des versions d’évaluation des mises à jour du logiciel HoloLens avant qu’elles ne soient disponibles pour le grand public.

[Obtenez Windows Insider Preview pour Microsoft HoloLens](hololens-insider.md).
