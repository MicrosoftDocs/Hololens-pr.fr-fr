---
title: Mettre à jour HoloLens 2
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924109"
---
# <a name="update-hololens-2"></a>Mettre à jour HoloLens 2

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

## <a name="go-back-to-a-previous-version"></a>Revenir à une version précédente

Dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. Les étapes recommandées sont les suivantes :

1. Contactez le support technique pour voir s’ils peuvent résoudre votre problème.
    1. Assurez-vous que les données de télémétrie **facultatives** ou **complètes** sont activées. cela rend votre bogue plus exploitable et plus facile pour les ingénieurs à diagnostiquer.
    1. [Commentaires de fichier](hololens-feedback.md) aussi descriptifs que possible. Prenez note du titre ou utilisez la fonctionnalité partager pour pouvoir partager votre bogue avec la prise en charge.
    1. Contactez le [support technique](https://aka.ms/hlsupport). S’il s’agit d’un problème qui doit être résolu en revenant à une version antérieure, il peut vous fournir le FFU pour flasher votre appareil.

1. Si cela ne fonctionne pas, [réinitialisez ou redémarrez votre HoloLens 2 avec le compagnon de récupération avancé](hololens-recovery.md).
    1. Sur votre PC, téléchargez l' [Assistant de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) à partir du Microsoft Store.
    1. Assurez-vous que vous n’avez aucun téléphone ou appareil Windows branché sur votre PC.
    1. Choisissez la version à utiliser pour le flash :
        1. Vous pouvez télécharger la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).
        1. Vous pouvez utiliser la build par défaut qu’ARC héberge. (Si vous choisissez cette option, ignorez l’étape suivante.)
        1. Vous pouvez utiliser une prise en charge de build fournie avec.
    1. Une fois ces téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  **téléchargements**. Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.
    1. Connectez votre HoloLens à votre PC à l’aide d’un câble USB-A à USB-C. (Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)
    1. L’Assistant de récupération avancée détecte automatiquement votre HoloLens. Sélectionnez la vignette **Microsoft HoloLens** .
    1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages** , puis sélectionnez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier avec l’extension. FFU.)
    1. Sélectionnez **installer le logiciel** et suivez les instructions.

> [!NOTE]
> En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

En outre, si vous souhaitez rester sur la version actuellement installée, vous pouvez également suspendre manuellement les [mises à jour](hololens-updates.md#pause-updates-via-device). Cela permet à l’équipe d’ingénierie de résoudre le problème.

## <a name="windows-insider-program-on-hololens"></a>Programme Windows Insider sur HoloLens

Vous souhaitez afficher les fonctionnalités les plus récentes dans HoloLens ?  Si c’est le cas, participez au programme Windows Insider. vous pouvez accéder à des versions préliminaires des mises à jour logicielles HoloLens avant qu’elles ne soient disponibles pour le grand public.

[Obtenir la version préliminaire de Windows Insider pour Microsoft HoloLens](hololens-insider.md).
