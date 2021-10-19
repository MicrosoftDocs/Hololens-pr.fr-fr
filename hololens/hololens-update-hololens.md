---
title: Mettre à jour HoloLens 2
description: apprenez à vérifier votre numéro de build HoloLens, tenez-vous informé des mises à jour des appareils, rejoignez le programme insiders et restaurez les mises à jour.
keywords: comment, mettre à jour, restaurer, HoloLens, vérifier la build, numéro de build
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151695"
---
# <a name="update-hololens-2"></a>Mettre à jour HoloLens 2

## <a name="overview"></a>Vue d’ensemble

Nous travaillons toujours sur de nouvelles fonctionnalités, des correctifs de bogues et des mises à jour de sécurité. Vous serez averti lorsque ces mises à jour seront prêtes.

selon vos préférences, votre HoloLens télécharge et installe automatiquement les mises à jour système chaque fois qu’il est branché à l’alimentation, connecté à Internet et même en veille.

pour vous assurer que votre HoloLens est toujours mis à jour, laissez-le branché avec le chargeur fourni avec lui. vous souhaitez également que vos HoloLens connectés à internet. De cette façon, il télécharge et installe automatiquement les mises à jour du système. 

avec Windows Update service, vous pouvez contrôler plusieurs aspects du processus de mise à jour, tels que les appareils qui reçoivent les mises à jour à quel moment. ce contrôle est utile, car vous pouvez déployer des mises à jour sur un sous-ensemble de HoloLens appareils à des fins de test. Ensuite, déployez les mises à jour vers les autres. Vous pouvez également définir différents calendriers de mise à jour pour différents types de mises à jour.

## <a name="types-of-updates"></a>Types de mise à jour

par HoloLens, vous pouvez gérer automatiquement deux types de mises à jour.

- Mises à jour des fonctionnalités : publiées deux fois par an.
- Mises à jour qualité : incluez des mises à jour de sécurité critiques. Elles sont publiées tous les mois ou selon les besoins.

Utilisez **Update** / **AllowAutoUpdate** pour gérer l’analyse, le téléchargement et l’installation des mises à jour. 

## <a name="scheduling-updates"></a>Planification des mises à jour

Vous pouvez également définir une planification de mise à jour. Il peut s’agir d’un jour particulier, ou tous les jours, à un moment donné. Par exemple, à 17 h 00 ou en dehors des heures d’activité.

Enfin, quelques mots sur la planification de votre stratégie de mise à jour. Nous prenons en charge les retards de mise à jour. vous pouvez donc décider du délai d’attente après la publication par Microsoft d’une mise à jour pour installer cette mise à jour sur les appareils.

Parfois, une entreprise souhaite essayer toutes les nouvelles fonctionnalités tout d’abord pour s’assurer que tout fonctionne, et les nouvelles mises à jour sont familières afin que l’équipe de support soit préparée. Une fois qu’ils ont confirmé que tout est correct, ils déployent les mises à jour de l’ensemble de l’entreprise. En associant des sous-ensembles de vos appareils à des stratégies de report différentes, appelées sonneries de mise à jour, vous pouvez coordonner une stratégie de déploiement des mises à jour pour votre organisation.

## <a name="hololens-update-tools"></a>outils de mise à jour HoloLens

cette section vous guide à travers les outils de HoloLens pour :

- recherche de mises à jour
- mise à jour manuelle des HoloLens
- affichage de la version actuelle du système d’exploitation (numéro de version)
- restauration d’une mise à jour antérieure

### <a name="check-for-updates-and-manually-update"></a>Rechercher les mises à jour et les mettre à jour manuellement

Vous pouvez rechercher des mises à jour à tout moment dans paramètres.  Pour afficher les mises à jour disponibles et rechercher les nouvelles mises à jour :

1. Ouvrez l’application **Paramètres**.
1. accédez à **mettre à jour &**  >  **Windows Update** de sécurité.
1. Sélectionnez **Rechercher des mises à jour**.

Si une mise à jour est disponible, le téléchargement de la nouvelle version est lancé. Une fois le téléchargement terminé, sélectionnez le bouton **redémarrer maintenant** pour déclencher l’installation. Si votre appareil est inférieur à 40% et qu’il n’est pas branché, le redémarrage ne démarrera pas l’installation de la mise à jour.

pendant que votre HoloLens installe la mise à jour, elle affiche des engrenages et un indicateur de progression. ne désactivez pas votre HoloLens pendant cette période. Il redémarrera automatiquement une fois l’installation terminée.

HoloLens applique une mise à jour à la fois.  si votre HoloLens correspond à plus d’une version en arrière-plan, vous devrez peut-être exécuter plusieurs fois le processus de mise à jour pour le mettre à jour.

### <a name="check-your-operating-system-version-build-number"></a>Vérifier la version de votre système d’exploitation (numéro de version)

vous pouvez vérifier le numéro de version du système (numéro de build) en ouvrant **Paramètres** et en sélectionnant **système**  >  **à propos** de.

### <a name="go-back-to-a-previous-version"></a>Revenir à une version précédente

dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. Les étapes recommandées sont les suivantes :

1. Contactez le support technique pour voir s’ils peuvent résoudre votre problème.
    1. Assurez-vous que les données de télémétrie **facultatives** ou **complètes** sont activées. cela rend votre bogue plus exploitable et plus facile pour les ingénieurs à diagnostiquer.
    1. Dans les commentaires sur les [fichiers](hololens-feedback.md) sont aussi descriptifs que possible. Prenez note du titre ou utilisez la fonctionnalité partager pour pouvoir partager votre bogue avec la prise en charge.
    1. Contactez le [support technique](https://aka.ms/hlsupport). S’il s’agit d’un problème qui doit être résolu en revenant à une version antérieure, il peut vous fournir le FFU pour flasher votre appareil.

1. vous pouvez également [reflasher votre HoloLens 2 avec le compagnon de récupération avancé](hololens-recovery.md#clean-reflash-the-device).
    1.  Choisissez la version à utiliser pour le flash : 
        1.  vous pouvez télécharger la dernière [version de HoloLens 2](https://aka.ms/hololens2download).
        1.  Vous pouvez utiliser la build par défaut qu’ARC héberge.
        1.  Vous pouvez utiliser une prise en charge de build fournie avec.

> [!NOTE]
> En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

En outre, si vous souhaitez rester sur la version actuellement installée, vous pouvez également suspendre manuellement les [mises à jour](hololens-updates.md#pause-updates-via-device). Cela permet à l’équipe d’ingénierie de résoudre le problème.

## <a name="windows-insider-program-on-hololens"></a>Windows Programme Insider sur HoloLens

Vous souhaitez voir les fonctionnalités les plus récentes de HoloLens ?  si c’est le cas, rejoignez le programme Windows insider. vous pouvez accéder à des versions préliminaires de HoloLens mises à jour logicielles avant qu’elles ne soient disponibles pour le grand public.

[procurez-vous Windows insider preview pour Microsoft HoloLens](hololens-insider.md).