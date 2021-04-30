---
title: Mettre à jour HoloLens
description: Découvrez comment vérifier votre numéro de build HoloLens, tenir à jour les mises à jour des appareils, joindre le programme Insiders et restaurer les mises à jour.
keywords: Comment, mettre à jour, restaurer, HoloLens, vérifier la build, numéro de build
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308811"
---
# <a name="update-hololens"></a>Mettre à jour HoloLens

HoloLens utilise Windows Update, tout comme les autres appareils Windows 10. Votre HoloLens télécharge et installe automatiquement les mises à jour système chaque fois qu’il est connecté à Power et connecté à Internet, même lorsqu’il est en veille.

Cet article passe en revue les outils HoloLens pour :

- affichage de la version actuelle du système d’exploitation (numéro de version)
- recherche de mises à jour
- mise à jour manuelle de HoloLens
- restauration d’une mise à jour antérieure

## <a name="check-your-operating-system-version-build-number"></a>Vérifier la version de votre système d’exploitation (numéro de version)

Vous pouvez vérifier le numéro de version du système (numéro de Build) en ouvrant l’application paramètres et en sélectionnant **système**  >  **à propos** de.

## <a name="check-for-updates-and-manually-update"></a>Rechercher les mises à jour et les mettre à jour manuellement

Vous pouvez rechercher des mises à jour à tout moment dans paramètres.  Pour afficher les mises à jour disponibles et rechercher les nouvelles mises à jour :

1. Ouvrez l’application **Paramètres**.
1. Accédez à **mettre à jour &**  >  **Windows Update** de sécurité.
1. Sélectionnez **Rechercher des mises à jour**.

Si une mise à jour est disponible, le téléchargement de la nouvelle version est lancé. Une fois le téléchargement terminé, sélectionnez le bouton **redémarrer maintenant** pour déclencher l’installation. Si votre appareil est inférieur à 40% et qu’il n’est pas branché, le redémarrage ne démarrera pas l’installation de la mise à jour.

Pendant l’installation de la mise à jour, votre HoloLens affiche des engrenages et un indicateur de progression. Ne désactivez pas votre HoloLens pendant cette période. Il redémarrera automatiquement une fois l’installation terminée.

HoloLens applique une mise à jour à la fois.  Si votre HoloLens est plus d’une version derrière la version la plus récente, vous devrez peut-être exécuter plusieurs fois le processus de mise à jour pour le mettre à jour.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Revenir à une version précédente-HoloLens 2

Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. Pour ce faire, vous pouvez utiliser l’Assistant de récupération avancé pour réinitialiser votre HoloLens à la version antérieure.

> [!NOTE]
> En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

Pour revenir à une version précédente de HoloLens 2, procédez comme suit :

1. Assurez-vous que vous n’avez aucun téléphone ou appareil Windows branché sur votre PC.
1. Sur votre PC, téléchargez l' [Assistant de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) à partir du Microsoft Store.
1. Téléchargez la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).
1. Une fois ces téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  **téléchargements**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C. (Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)
1. L’Assistant de récupération avancée détecte automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens** .
1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages** , puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier avec l’extension. FFU.)
1. Sélectionnez **installer le logiciel** et suivez les instructions.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Revenir à une version précédente-HoloLens (1ère génération)

Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. Pour ce faire, vous pouvez utiliser l’outil de récupération de périphérique de Windows pour réinitialiser votre HoloLens à la version antérieure.

> [!NOTE]
> En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

Pour revenir à une version précédente de HoloLens 1, procédez comme suit :

1. Assurez-vous que vous n’avez aucun téléphone ou appareil Windows branché sur votre PC.
1. Sur votre PC, téléchargez l' [outil de récupération d’appareils Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Téléchargez le [package de récupération de la mise à jour de l’anniversaire HoloLens](https://aka.ms/hololensrecovery).
1. Une fois les téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  . Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.
1. Connectez votre HoloLens à votre PC à l’aide du câble micro-USB avec lequel il a été fourni. (Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)
1. Le WDRT détectera automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens** .
1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages** et choisissez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier avec l’extension. FFU.)
1. Sélectionnez **installer le logiciel** et suivez les instructions.

> [!NOTE]
> Si le WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre ordinateur. Si cela ne fonctionne pas, sélectionnez **mon appareil n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.

## <a name="windows-insider-program-on-hololens"></a>Programme Windows Insider sur HoloLens

Vous souhaitez afficher les fonctionnalités les plus récentes dans HoloLens ?  Si c’est le cas, participez au programme Windows Insider. vous pouvez accéder à des versions préliminaires des mises à jour logicielles HoloLens avant qu’elles ne soient disponibles pour le grand public.

[Obtenir la version préliminaire de Windows Insider pour Microsoft HoloLens](hololens-insider.md).
