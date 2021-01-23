---
title: Mettre à jour HoloLens
description: Découvrez comment vérifier votre numéro de build HoloLens, tenir à jour les mises à jour des appareils, rejoindre le programme Insiders et revenir aux mises à jour.
keywords: how-to, update, roll back, HoloLens, check build, build number
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
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283935"
---
# Mettre à jour HoloLens

HoloLens utilise Windows Update, comme les autres appareils Windows 10. Votre HoloLens télécharge et installe automatiquement les mises à jour système chaque fois qu’il est branché et connecté à Internet, même lorsqu’il est en veille.

Cet article décrit les outils HoloLens pour :

- affichage de la version actuelle de votre système d’exploitation (numéro de build)
- vérification des mises à jour ;
- mise à jour manuelle de HoloLens
- revenir à une mise à jour plus ancienne

## Vérifier la version de votre système d’exploitation (numéro de build)

Vous pouvez vérifier le numéro de version du système (numéro de build) en ouvrant l’application Paramètres et en sélectionnant **System**  >  **About**.

## Vérifier les mises à jour et les mettre à jour manuellement

Vous pouvez vérifier les mises à jour à tout moment dans les paramètres.  Pour voir les mises à jour disponibles et vérifier les nouvelles mises à jour :

1. Ouvrez **l’application Paramètres.**
1. Accédez à **Mettre à jour & sécurité**Windows  >  **Update**.
1. Sélectionnez **Vérifier les mises à jour.**

Si une mise à jour est disponible, elle commence à télécharger la nouvelle version. Une fois le téléchargement terminé, sélectionnez le bouton **Redémarrer maintenant** pour déclencher l’installation. Si votre appareil est inférieur à 40 % et qu’il n’est pas branché, le redémarrage ne démarre pas l’installation de la mise à jour.

Pendant que votre HoloLens installe la mise à jour, il affiche des engrenages de rotation et un indicateur de progression. Ne pas désactiver votre HoloLens pendant cette période. Il redémarre automatiquement une fois l’installation terminée.

HoloLens applique une mise à jour à la fois.  Si votre HoloLens est plus d’une version derrière la dernière version, vous devrez peut-être exécuter le processus de mise à jour plusieurs fois pour le mettre entièrement à jour.

## Revenir à une version précédente - HoloLens 2

Dans certains cas, vous souhaiterez peut-être revenir à une version antérieure du logiciel HoloLens. Pour ce faire, utilisez l’Outil de récupération avancée (Advanced Recovery Companion) pour réinitialiser votre HoloLens à la version antérieure.

> [!NOTE]
> En revenir à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

Pour revenir à une version antérieure de HoloLens 2, procédez comme suit:

1. Assurez-vous que vous n’avez pas de téléphones ou d’appareils Windows branchés sur votre PC.
1. Sur votre PC, téléchargez [l’Outil](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) de récupération avancée à partir du Microsoft Store.
1. Téléchargez la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).
1. Une fois ces téléchargements terminés, ouvrez **l’Explorateur**  >  **de fichiers.** Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C. Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.
1. Advanced Recovery Companion détecte automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens**.
1. Dans l’écran suivant, sélectionnez Sélection manuelle du **package,** puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier avec l’extension .ffu.)
1. Sélectionnez **Installer le**logiciel et suivez les instructions.

## Revenir à une version précédente : HoloLens (1ère génération)

Dans certains cas, vous souhaiterez peut-être revenir à une version antérieure du logiciel HoloLens. Vous pouvez le faire à l’aide de l’outil de récupération d’appareil Windows pour réinitialiser votre HoloLens à la version antérieure.

> [!NOTE]
> En revenir à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

Pour revenir à une version précédente de HoloLens 1, suivez les étapes suivantes :

1. Assurez-vous que vous n’avez pas de téléphones ou d’appareils Windows branchés sur votre PC.
1. Sur votre PC, téléchargez [l’outil de récupération d’appareil Windows (WDRT).](https://support.microsoft.com/help/12379)
1. Téléchargez le [package de récupération de mise à jour anniversaire HoloLens](https://aka.ms/hololensrecovery).
1. Une fois les téléchargements terminés, ouvrez **l’Explorateur**  >  **de fichiers.** Cliquez avec le bouton droit sur le dossier compressé que vous avez téléchargé, puis sélectionnez **Extraire tout**  >  **l’extraction** pour le déziper.
1. Connectez votre HoloLens à votre PC à l’aide du câble micro-USB qu’il a utilisé. Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.
1. Le WDRT détecte automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens**.
1. Dans l’écran suivant, sélectionnez Sélection manuelle du **package** et choisissez le fichier d’installation contenu dans le dossier décompressé à l’étape 4. (Recherchez un fichier avec l’extension .ffu.)
1. Sélectionnez **Installer le**logiciel et suivez les instructions.

> [!NOTE]
> Si le WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre PC. Si cela ne fonctionne pas, sélectionnez **Mon appareil n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.

## Programme Windows Insider sur HoloLens

Vous souhaitez voir les dernières fonctionnalités de HoloLens ?  Si c’est le cas, rejoignez le programme Windows Insider ; Vous aurez accès aux builds d’aperçu des mises à jour logicielles HoloLens avant qu’elles ne soit disponibles pour le grand public.

[Obtenir la prévisualisation de Windows Insider pour Microsoft HoloLens.](hololens-insider.md)
