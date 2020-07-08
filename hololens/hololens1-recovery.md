---
title: Redémarrer, réinitialiser ou récupérer HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Comment utiliser l’outil récupération d’appareils Windows pour flasher une image dans HoloLens 1ère génération.
keywords: procédure de réinitialisation, de réinitialisation, de récupération, de réinitialisation matérielle, de réinitialisation à chaud, de cycle de démarrage, HoloLens, arrêt, wdrt, outil de récupération des appareils Windows
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 36192315e234db16c7747457e69d6d6281c31bfe
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857732"
---
# Redémarrer, réinitialiser ou récupérer HoloLens (1ère génération)

Si vous rencontrez des problèmes avec votre HoloLens, vous souhaiterez peut-être essayer d’effectuer un redémarrage, de réinitialiser ou même de relancer la récupération des appareils.

Voici quelques solutions à essayer si votre service HoloLens ne fonctionne pas correctement.  Cet article vous guide dans les étapes de récupération recommandées successivement.

Si vous cherchez à récupérer un contrôle HoloLens 2, consultez la page de [Récupération d’unHoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), car les processus présentent des différences.

Cet article se concentre sur l’appareil et les logiciels HoloLens, si vos hologrammes ne s’affichent pas correctement, [cet article](hololens-environment-considerations.md) parle de facteurs environnementaux qui améliorent la qualité de l’hologramme.

## Redémarrer

### Effectuer un redémarrage en toute sécurité à l’aide de Cortana

Le moyen le plus sûr de redémarrer le HoloLens consiste à utiliser Cortana. Il s’agit généralement d’une première étape facile pour rencontrer un problème avec HoloLens. 

> [!NOTE]
> Cortana n’est pas disponible sur tous les appareils. Cortana est disponible à tous les appareils HoloLens (1ère génération).
> Cortana est disponible sur les appareils HoloLens 2 sur une version antérieure à la mise à jour de la version 2004 de Windows.

1. Placer sur votre appareil
1. Assurez-vous qu’il est alimenté, qu’un utilisateur est connecté et que l’appareil n’attend pas de mot de passe pour le déverrouiller.
1. Dites «Hey Cortana, redémarrez» ou «Hey Cortana, redémarrez».
1. Lorsqu’elle reconnaît, elle vous demandera de confirmer votre choix. Patientez pendant la lecture d’un signal sonore une fois qu’il a terminé sa question, indiquant qu’il vous écoute et dites «oui».
1. L’appareil redémarre maintenant.

### Effectuer un redémarrage en toute sécurité à l’aide du bouton arrêter l’ordinateur

Si vous ne parvenez pas à redémarrer votre appareil, vous pouvez essayer de le redémarrer à l’aide du bouton arrêter l’ordinateur:

1. Appuyez de façon prolongée sur le bouton de mise sous tension pendant cinq secondes.
   1. Après une seconde, les cinq voyants s’allument, puis s’éteignent lentement de droite à gauche.
   1. Après cinq secondes, tous les voyants sont désactivés, indiquant que la commande d’arrêt a été correctement émise.
   1. Notez qu’il est important de ne pas appuyer sur le bouton immédiatement après que tous les voyants ont été désactivés.
1. Patientez une minute pour que l’arrêt aboutisse correctement. Notez que l’arrêt peut être encore en cours, même si les affichages sont désactivés.
1. Rallumez l’appareil en appuyant sur le bouton de mise sous tension pendant une seconde.

### Effectuer un redémarrage en toute sécurité à l’aide du portail d’appareils Windows

> [!NOTE]
> Pour ce faire, HoloLens doit être configuré en tant qu’appareil développeur.  
> En savoir plus sur le [Portail d’appareils de Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Si la procédure précédente ne fonctionne pas, vous pouvez essayer de redémarrer l’appareil à l’aide du [Portail d’appareils de Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). Dans le coin supérieur droit, vous pouvez redémarrer ou arrêter l’appareil.

### Effectuer un redémarrage forcé non sécurisé

Si aucune des méthodes précédentes ne peut redémarrer votre appareil, vous pouvez forcer un redémarrage. Cette méthode revient à tirer la batterie de HoloLens.  Il s’agit d’une opération dangereuse qui peut rendre votre appareil endommagé.  Dans ce cas, vous devez flasher votre HoloLens.  

> [!WARNING]
> Il s’agit d’une méthode potentiellement nuisible qui ne doit être utilisée que dans le cas où aucune des méthodes ci-dessus ne fonctionne.

1. Appuyez de façon prolongée sur le bouton de mise sous tension pendant au moins 10 secondes.
   - Il est possible de maintenir le bouton enfoncé pendant plus de 10 secondes.
   - Il est possible d’ignorer toute activité LED.
1. Relâchez le bouton et attendez deux ou trois secondes.
1. Rallumez l’appareil en appuyant sur le bouton de mise sous tension pendant une seconde.
Si vous rencontrez toujours des problèmes, appuyez sur le bouton de mise sous tension pendant 4 secondes, jusqu’à ce que tous les indicateurs de batterie disparaisse et que l’écran cesse d’afficher les hologrammes. Patientez 1 minute, puis appuyez de nouveau sur le bouton Power pour allumer l’appareil.

## Rétablir les paramètres par défaut

> [!NOTE]
> La batterie nécessite au moins 40% de charge pour la réinitialisation.

Si vous rencontrez encore des problèmes après avoir redémarré votre HoloLens, essayez de le réinitialiser à l’état d’origine.  La réinitialisation de votre contrôle HoloLens conserve la version du logiciel Windows holographique qui est installé dessus et renvoie tous les autres paramètres aux paramètres d’usine.

Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels sont supprimés, y compris la réinitialisation du TPM. La réinitialisation de n’installera que la dernière version de Windows holographique. vous devrez rétablir toutes les étapes d’initialisation (étalonner, connecter à Wi-Fi, créer un compte d’utilisateur, télécharger des applications, etc.).

1. Lancez l’application paramètres, puis sélectionnez **Mise à jour** > **Réinitialiser**.
1. Sélectionnez l’option **Réinitialiser l’appareil** et lisez le message de confirmation.
1. Si vous acceptez de réinitialiser votre appareil, l’appareil redémarre et affiche un série de rapports tournants avec une barre de progression.
1. Patientez environ 30 minutes l’exécution de ce processus.
1. La réinitialisation se termine et l’appareil redémarre dans le cadre de l’utilisation.

## Réinstaller le système d'exploitation

Si le problème persiste après le redémarrage et la réinitialisation de l’appareil, vous pouvez utiliser un outil de récupération sur votre ordinateur pour réinstaller le système d’exploitation et le microprogramme HoloLens.  

La réinitialisation de tous les données de HoloLens est incluse dans une mise à jour Flash complète (FFU).  Il s’agit du même type que les normes ISO, Wim et VHD.  [En savoir plus sur les formats de fichier image FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Si nécessaire, vous pouvez installer un système d’exploitation totalement nouveau sur votre HoloLens (1ère génération) à l’aide de l’outil de récupération d’appareils Windows.

Avant d’utiliser cet outil, déterminez si le redémarrage ou la réinitialisation de votre outil HoloLens permet de résoudre le problème. Le processus de récupération peut prendre du temps.  Lorsque vous avez terminé, la dernière version du logiciel Windows holographique approuvée pour votre HoloLens sera installée.

Pour utiliser l’outil, vous avez besoin d’un ordinateur exécutant Windows 10 ou version ultérieure, avec au moins 4 Go d’espace de stockage disponible.  Notez que vous ne pouvez pas exécuter cet outil sur une machine virtuelle.

### Récupérer votre HoloLens:

1. Téléchargez et installez [Windows Device Recovery Tool sur votre ordinateur](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
1. Connectez HoloLens (1ère génération) à votre ordinateur à l’aide du câble USB fourni avec votre HoloLens.
1. Exécutez l’outil récupération d’appareils Windows et suivez les instructions.

Si le système HoloLens (1ère génération) n’est pas détecté automatiquement, sélectionnez **Mon appareil n’a pas été détecté** et suivez les instructions pour passer en mode de récupération.

### Mode clignotant manuel:

Dans le cas où votre appareil n’est pas détecté, veuillez utiliser la méthode suivante pour le placer manuellement en mode clignotant.

1. Débranchez l’appareil de toutes les sources d’alimentation.
1. Si l’appareil est allumé, maintenez le bouton Power enfoncé jusqu’à ce qu’il soit complètement désactivé.
1. Maintenez le bouton **Monter le volume**, puis appuyez sur le **bouton Alimentation**. 
1. L’appareil doit être amorcé et afficher uniquement le voyant du milieu.
1. Branchez l’appareil sur votre PC.
1. Lancez l’outil récupération des appareils Windows.
1. Vous devrez sélectionner * mon appareil n’a pas été détecté * *, puis sélectionner **HoloLens**. 
1. Suivez les instructions permettant de récupérer votre appareil.
