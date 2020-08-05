---
title: Redémarrer, réinitialiser ou récupérer HoloLens 1
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915943"
---
# Redémarrer, réinitialiser ou récupérer HoloLens (1ère génération)

Si vous rencontrez des problèmes avec votre HoloLens, vous pouvez essayer d’effectuer un redémarrage ou de le réinitialiser, voire même de réinstaller le système d’exploitation à l’aide de la récupération d’appareils. Cet article vous guidera à travers les étapes de récupération recommandées.

Si vous cherchez à récupérer votre HoloLens2, consultez[Récupération de l’HoloLens2](https://docs.microsoft.com/hololens/hololens-recovery), car ce processus est différent.

> [!NOTE]
> Cet article se concentre sur l’appareil et le logiciel HoloLens. Si le rendu de vos hologrammes est mauvais, consultez **[Considérations sur l’environnement HoloLens](hololens-environment-considerations.md)** pour obtenir des informations sur les facteurs qui améliorent la qualité de l’hologramme.

## Redémarrer

### Effectuer un redémarrage en toute sécurité à l’aide de Cortana

Le moyen le plus sûr de redémarrer votre HoloLens consiste à utiliser Cortana, qui est en règle générale la première chose à essayer lorsque vous rencontrez un problème avec HoloLens.

> [!NOTE] 
> Cortana n’est pas disponible sur tous les appareils.
> - Cortana est disponible sur tous les appareils HoloLens (1ère génération). 
> - Cortana est disponible sur les appareils HoloLens2 sur des builds antérieures à WindowsHolograpic, version mise à jour 2004.

1. Allumez votre HoloLens.
1. Assurez-vous qu’un utilisateur a ouvert une session et que l’appareil n’attend pas de mot de passe pour le déverrouiller.
2. Dites «Hey Cortana, redémarrez» ou «Hey Cortana, redémarrez».
3. Cortana vous répondra et vous invitera à confirmer votre choix. Attendez d’entendre un son après la question, puis dites «oui». L’appareil redémarrera.

### Utiliser le bouton d’alimentation pour effectuer un redémarrage en toute sécurité

Si vous ne parvenez pas à redémarrer votre appareil, essayez de le redémarrer à l’aide du bouton **d’alimentation**:

1. Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 5secondes. Après 1seconde, les cinq voyants s’illuminent, puis s’éteignent les un après les autres, de droite à gauche. Après 5secondes, tous les voyants sont éteints, ce qui indique que l’arrêt est terminé.
      
   > [!IMPORTANT]
   > Relâchez le bouton immédiatement après que tous les voyants se sont éteints.
1. Patientez 1minute pour que l’arrêt soit complet. L’arrêt peut être encore en cours, même si les affichages sont désactivés.
2. Réactivez l’appareil en maintenant le bouton **d’alimentation** enfoncé pendant 1seconde.

### Effectuer un redémarrage en toute sécurité à l’aide du Portail d’appareil Windows

> [!NOTE]
> Pour ce faire, HoloLens doit être configuré en tant qu’appareil développeur. Plus d’informations sur [Portail d’appareil Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Si la procédure précédente ne fonctionne pas, essayez de redémarrer l’appareil à l’aide de du [Portail d’appareil Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). Dans le coin supérieur droit, recherchez l’option permettant de redémarrer ou d’éteindre l’appareil.

### Effectuer un redémarrage forcé non sécurisé

Si les méthodes précédentes n’ont pas redémarré votre HoloLens, forcez un redémarrage. Cette méthode revient à enlever et réinstaller la batterie. Cette procédure est dangereuse, car elle peut endommager votre appareil. Dans ce cas, vous devez flasher votre HoloLens.  

> [!WARNING]
> Il s’agit d’une méthode potentiellement nuisible qui ne doit être utilisée que si les méthodes précédemment mentionnées ne fonctionnent pas.

1. Appuyez de façon prolongée sur le bouton **d’alimentation** pendant au moins 10secondes.
   - Il est possible de maintenir le bouton enfoncé pendant plus de 10 secondes.
   - Il est possible d’ignorer toute activité LED.
1. Relâchez le bouton et attendez 2-3secondes.
1. Appuyez de façon prolongée sur le bouton **d’alimentation** pendant 1secondes.
1. Si vous rencontrez toujours des problèmes, appuyez sur le bouton **d’alimentation** pendant 4secondes, jusqu’à ce que tous les indicateurs de batterie disparaissent et que l’écran cesse d’afficher les hologrammes. Patientez 1minute, puis appuyez de nouveau sur le bouton **d’alimentation** pour allumer l’appareil.

## Rétablir les paramètres par défaut

> [!NOTE]
> La batterie nécessite au moins 40% de charge pour la réinitialisation.

Si votre HoloLens rencontre encore un problème, essayez de le réinitialiser à l’état de sortie d’usine. Cette étape conserve la version du logiciel WindowsHolographique installé sur celle-ci et réinitialise tous les autres paramètres aux paramètres d’usine.

>[!WARNING]
> Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels sont supprimés, y compris les informations de réinitialisation du TPM. La réinitialisation ne permet d’installer que la dernière version installée de WindowsHolographique. Vous devrez rétablir toutes les étapes d’initialisation (étalonnage, connexion Wi-Fi, création d’un compte d’utilisateur, téléchargement d’applications, etc.).

1. Lancez l'application Paramètres, puis sélectionnez **Mettre à jour** > **Récupération**.
1. Sélectionnez l’option **Réinitialiser l’appareil** et lisez le message de confirmation.
1. Confirmez la réinitialisation. L’appareil redémarre et affiche une animation d’engrenages et une barre de progression.
1. Patientez environ 30 minutes l’exécution de ce processus. Une fois l’opération terminée, l’appareil redémarre «comme neuf».

## Réinstaller le système d’exploitation

Si le problème persiste après le redémarrage et la réinitialisation de l’appareil, vous pouvez utiliser un outil de récupération sur votre ordinateur pour réinstaller le système d’exploitation HoloLens et le microprogramme.  

Les données requises par HoloLens pour la réinitialisation sont incluses dans une mise à jour FullFlashUpdate (FFU), ce qui est similaire à un fichier .iso, .wim ou .vhd. [En savoir plus sur les formats de fichier image FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Vous pouvez installer un nouveau système d’exploitation sur votre HoloLens (1èregénération) à l’aide de l’Outil de récupération d’appareils Windows. Avant d’utiliser cet outil, essayez de voir si le redémarrage ou la réinitialisation de votre HoloLens permet de résoudre le problème.

Le processus de récupération peut prendre du temps. Une fois l’opération terminée, la dernière version du logiciel WindowsHolographique est installée.

Pour utiliser l’outil, vous avez besoin d’un ordinateur exécutant Windows10 ou une version ultérieure, avec au moins 4Go d’espace de stockage disponible. Notez que vous ne pouvez pas exécuter cet outil sur une machine virtuelle.

### Récupérer votre HoloLens

1. Téléchargez et installez [Windows Device Recovery Tool sur votre ordinateur](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
1. Connectez l’HoloLens (1èregénération) à votre ordinateur à l’aide du câbleUSB fourni avec votre HoloLens.
1. Exécutez l’Outil de récupération d’appareils Windows et suivez les instructions.

Si le système HoloLens (1èregénération) n’est pas détecté automatiquement, sélectionnez **Mon appareil n’a pas été détecté**. Suivez ensuite les instructions pour placer l’appareil en mode de récupération.

### Mode clignotant manuel

Si votre appareil n’est pas détecté, procédez comme suit pour le placer en mode clignotant:

1. Débranchez l’appareil de toute source d’alimentation.
1. Si l’appareil est allumé, maintenez le bouton **d’alimentation** enfoncé jusqu’à ce qu’il s’éteigne complètement.
2. Maintenez le bouton **d’augmentation du volume**, puis appuyez brièvement sur le bouton **d’alimentation**. L’appareil devrait démarrer et afficher uniquement le voyant du milieu.
3. Branchez l’appareil sur votre PC.
4. Exécutez l’Outil récupération d’appareils Windows.
5. Sélectionnez **Mon appareil n’a pas été détecté** puis **Hololens**. 
6. Suivez les instructions permettant de récupérer votre appareil.
