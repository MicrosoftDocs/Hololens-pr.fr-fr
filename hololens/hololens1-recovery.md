---
title: redémarrage, réinitialisation ou récupération HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: comment utiliser Windows outil de récupération d’appareil pour flasher une image sur HoloLens 1ère génération.
keywords: procédure, redémarrage, réinitialisation, récupération, réinitialisation matérielle, réinitialisation à chaud, cycle de HoloLens, arrêt, wdrt, outil de récupération d’appareil windows
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635226"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>redémarrage, réinitialisation ou récupération HoloLens (1re génération)

si vous rencontrez des problèmes avec votre HoloLens, vous pouvez essayer d’effectuer un redémarrage ou une réinitialisation, ou même de relancer l’appareil à l’aide de la récupération de l’appareil. Cet article vous guide tout au long des étapes de récupération recommandées dans l’ordre.

si vous envisagez de récupérer une HoloLens 2, consultez récupération [d’une HoloLens 2](hololens-recovery.md), car ce processus diffère.

> [!NOTE]
> cet article se concentre sur le HoloLens appareil et le logiciel. si vos hologrammes ne sont pas corrects, consultez **[HoloLens considérations](hololens-environment-considerations.md)** relatives à l’environnement pour plus d’informations sur les facteurs qui améliorent la qualité de l’hologramme.

## <a name="restart"></a>Redémarrer

### <a name="do-a-safe-restart-by-using-cortana"></a>Effectuez un redémarrage en toute sécurité à l’aide de Cortana

le moyen le plus sûr de redémarrer le HoloLens consiste à utiliser Cortana, qui est généralement la première chose à essayer lorsque vous rencontrez un problème avec HoloLens.

> [!NOTE] 
> Cortana n’est pas disponible sur tous les appareils.
> - Cortana est disponible sur tous les appareils HoloLens (1er génération). 
> - Cortana est disponible sur les appareils HoloLens 2s sur les builds antérieures à la mise à jour Windows Holograpic, Version 2004.

1. Activez votre HoloLens.
1. Assurez-vous qu’un utilisateur est connecté et que l’appareil n’attend pas de mot de passe pour le déverrouiller.
2. dites « hey Cortana, restart » ou « hey Cortana, restart ».
3. Cortana répondra et vous invitera à confirmer l’opération. Attendez qu’un son soit lu après la question, puis dites « oui ». L’appareil redémarre.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Utilisez le bouton marche/arrêt pour effectuer un redémarrage sécurisé

Si vous ne pouvez toujours pas redémarrer votre appareil, essayez de le redémarrer à l’aide du bouton **d’alimentation** :

1. Appuyez sur le bouton **d’alimentation** et maintenez-le enfoncé pendant 5 secondes. Après 1 seconde, les cinq LED s’allument, puis arrêtent lentement un par un de droite à gauche. Après 5 secondes, tous les LED sont désactivés, ce qui indique un arrêt réussi.
      
   > [!IMPORTANT]
   > Arrêtez l’appui sur le bouton dès que tous les voyants sont désactivés.
1. Attendez 1 minute que l’arrêt se termine. L’arrêt peut encore être en cours même si les affichages sont désactivés.
2. Réactivez l’appareil en appuyant sur le bouton **d’alimentation** et en le maintenant enfoncé pendant 1 seconde.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>effectuer un redémarrage en toute sécurité à l’aide du portail des appareils Windows

> [!NOTE]
> pour ce processus, HoloLens doit être configuré en tant qu’appareil développeur. pour en savoir plus, consultez [Windows le portail des appareils](/windows/mixed-reality/using-the-windows-device-portal).

si la procédure précédente ne fonctionne pas, essayez de redémarrer l’appareil à l’aide de [Windows portail d’appareils](/windows/mixed-reality/using-the-windows-device-portal). Dans l’angle supérieur droit, recherchez l’option de redémarrage ou d’arrêt de l’appareil.

### <a name="do-an-unsafe-forced-restart"></a>Effectuer un redémarrage forcé non sécurisé

si les méthodes précédentes n’ont pas redémarré votre HoloLens, forcez un redémarrage. Cette méthode est équivalente à la suppression et à la réinstallation de la batterie. C’est dangereux, car cela peut rendre votre appareil dans un état endommagé. Si cela se produit, vous devrez flasher votre HoloLens.  

> [!WARNING]
> Il s’agit d’une méthode potentiellement dangereuse qui ne doit être utilisée que si les méthodes mentionnées précédemment n’ont pas fonctionné.

1. Appuyez sur le bouton **d’alimentation** et maintenez-le enfoncé pendant au moins 10 secondes.
   - Il est possible de conserver le bouton pendant plus de 10 secondes.
   - Il est possible d’ignorer toute activité LED.
1. Relâchez le bouton et attendez 2-3 secondes.
1. Appuyez sur le bouton **d’alimentation** et maintenez-le enfoncé pendant 1 seconde.
1. Si vous rencontrez toujours des problèmes, appuyez sur le bouton **d’alimentation** pendant 4 secondes, jusqu’à ce que tous les indicateurs de la batterie disparaisse et que l’écran cesse d’afficher les hologrammes. Attendez 1 minute, puis appuyez à nouveau sur le bouton **d’alimentation** pour allumer l’appareil.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>revenir à une version précédente-HoloLens (1re génération)

dans certains cas, vous souhaiterez peut-être revenir à une version précédente du logiciel HoloLens. pour ce faire, vous pouvez utiliser l’outil de récupération des appareils Windows pour réinitialiser votre HoloLens à la version antérieure.

> [!NOTE]
> En revenons à une version antérieure, vous supprimez vos fichiers et paramètres personnels.

pour revenir à une version précédente de HoloLens 1, procédez comme suit :

1. assurez-vous que vous n’avez aucun téléphone ou Windows appareils branchés sur votre PC.
1. sur votre PC, téléchargez l' [outil Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. téléchargez le [package de récupération de mise à jour anniversaire HoloLens](https://aka.ms/hololensrecovery).
1. Une fois les téléchargements terminés, ouvrez l' **Explorateur de fichiers**  >  . Cliquez avec le bouton droit sur le dossier compressé que vous venez de télécharger, puis sélectionnez **extraire tout**  >  **extraire** pour le décompresser.
1. Connecter votre HoloLens sur votre ordinateur à l’aide du câble micro-USB avec lequel il a été fourni. (même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.)
1. Le WDRT détectera automatiquement votre HoloLens. sélectionnez la vignette **Microsoft HoloLens** .
1. Dans l’écran suivant, sélectionnez **sélection manuelle des packages** et choisissez le fichier d’installation contenu dans le dossier que vous avez décompressé à l’étape 4. (Recherchez un fichier avec l’extension. FFU.)
1. Sélectionnez **installer le logiciel** et suivez les instructions.

> [!NOTE]
> si le WDRT ne détecte pas votre HoloLens, essayez de redémarrer votre ordinateur. si cela ne fonctionne pas, sélectionnez **mon appareil n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.

## <a name="reset-to-factory-settings"></a>Rétablir les paramètres d’usine

> [!NOTE]
> La batterie a besoin d’au moins un débit de 40% pour être réinitialisé.

si votre HoloLens présente toujours un problème, essayez de le réaffecter à l’état factory. cette étape permet de conserver la version du logiciel Windows holographique qui est installé sur celui-ci et de renvoyer tout le reste vers les paramètres d’usine.

>[!WARNING]
> Si vous réinitialisez votre appareil, toutes vos données, applications et paramètres personnels seront effacés, y compris les informations de réinitialisation du module de plateforme sécurisée. la réinitialisation permet d’installer uniquement la dernière version installée de Windows holographique. Vous devrez rétablir toutes les étapes d’initialisation (étalonner, se connecter au Wi-Fi, créer un compte d’utilisateur, télécharger des applications, etc.).

1. ouvrez l’application Paramètres, puis sélectionnez **mettre à jour** la  >  **récupération**.
1. Sélectionnez l’option **Réinitialiser l’appareil** et lisez le message de confirmation.
1. Confirmez la réinitialisation. L’appareil redémarrera et affichera un ensemble d’engrenages rotatifs et une barre de progression.
1. Attendez environ 30 minutes que ce processus se termine. Une fois l’opération terminée, l’appareil redémarre avec l’expérience « prête à l’emploi ».

## <a name="reinstall-the-operating-system"></a>Réinstaller le système d’exploitation

si le problème persiste après le redémarrage et la réinitialisation de l’appareil, vous pouvez utiliser un outil de récupération sur votre ordinateur pour réinstaller le système d’exploitation et le microprogramme de HoloLens.  

les données qui HoloLens ont besoin de la réinitialisation sont empaquetées dans une mise à jour Flash complète (FFU), qui est similaire à un fichier. iso,. wim ou. vhd. [En savoir plus sur les formats de fichier image FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

vous pouvez installer un nouveau système d’exploitation sur votre HoloLens (1re génération) à l’aide de l’outil de récupération des appareils Windows. avant d’utiliser cet outil, consultez si le redémarrage ou la réinitialisation de votre HoloLens résout le problème.

Le processus de récupération peut prendre un certain temps. une fois l’opération terminée, la version la plus récente du logiciel Windows holographique est installée.

pour utiliser l’outil, vous avez besoin d’un ordinateur exécutant Windows 10 ou version ultérieure avec au moins 4 go d’espace de stockage disponible. Vous ne pouvez pas exécuter cet outil sur une machine virtuelle.

### <a name="recover-your-hololens"></a>Récupérer votre HoloLens

1. téléchargez et installez l' [outil de récupération des appareils Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) sur votre ordinateur.
1. Connecter la HoloLens (1ère génération) sur votre ordinateur à l’aide du câble Micro USB fourni avec votre HoloLens.
1. ouvrez l’outil de récupération de l’appareil Windows et suivez les instructions.

si le HoloLens (1re génération) n’est pas détecté automatiquement, sélectionnez **mon appareil n’a pas été détecté**. Suivez ensuite les instructions pour mettre l’appareil en mode de récupération.

### <a name="manual-flashing-mode"></a>Mode clignotant manuel

Si votre appareil n’est pas détecté, procédez comme suit pour le mettre en mode clignotant :

1. Débranchez l’appareil de toute source d’alimentation.
1. Si l’appareil est allumé, maintenez le bouton **d’alimentation** enfoncé jusqu’à ce qu’il soit complètement éteint.
2. Maintenez le bouton **haut du volume** et appuyez brièvement sur le bouton **d’alimentation** . L’appareil doit démarrer et afficher uniquement la del centrale.
3. Connectez l’appareil à votre PC.
4. ouvrez l’outil de récupération de l’appareil Windows.
5. Sélectionnez **mon appareil n’a pas été détecté** , puis **HoloLens**. 
6. Suivez les instructions pour récupérer votre appareil.
