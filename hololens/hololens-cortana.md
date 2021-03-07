---
title: Utiliser votre voix pour faire fonctionner HoloLens
description: Découvrez comment Cortana peut vous aider à réaliser toutes sortes d’actions sur vos appareils HoloLens à réalité mixte, notamment les commandes vocales, la dictée et les interactions avec un histogramme.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393868"
---
# <a name="use-your-voice-to-operate-hololens"></a>Utiliser votre voix pour faire fonctionner HoloLens

Vous pouvez utiliser votre voix pour effectuer presque n’importe quelle action sur HoloLens, par exemple prendre une photo rapidement ou ouvrir une application. De nombreuses commandes vocales sont intégrées à HoloLens, tandis que d’autres sont disponibles par le biais de Cortana.

Cet article vous explique comment commander HoloLens et votre univers holographique avec votre voix et avec Cortana.

> [!NOTE]
> La reconnaissance vocale est uniquement prise en charge dans [certaines langues](hololens2-language-support.md). La langue vocale est basée sur la langue d’affichage de Windows, et non sur la langue du clavier.  
>  
> Vous pouvez vérifier la langue d’affichage de Windows en sélectionnant **Paramètres** > **Heure et langue** > **Langue**.

## <a name="built-in-voice-commands"></a>Commandes vocales prédéfinies

Prenez en main HoloLens plus rapidement grâce à ces commandes de base. Pour pouvoir les utiliser, vous devez activer la reconnaissance vocale lors de la première exécution de l’appareil ou dans **Paramètres** > **Confidentialité** > **Voix**. Vous pouvez toujours vérifier si la reconnaissance vocale est activée en examinant l’État en haut du menu Démarrer. Pour obtenir les meilleurs résultats de reconnaissance vocale, HoloLens 2 utilise les services Cloud de Microsoft. Toutefois, vous pouvez utiliser les paramètres pour désactiver cette fonctionnalité. Pour ce faire, dans paramètres, désactivez la** Reconnaissance vocale en ligne**. Une fois que vous avez modifié ce paramètre, HoloLens 2 traite uniquement les données vocales de façon locale pour reconnaître les commandes et la dictée, et Cortana ne sera pas disponible.

### <a name="general-speech-commands"></a>Commandes vocales générales

Pour une utilisation plus rapide de ces commandes dans Windows Mixed Reality. Certaines commandes utilisent le curseur oculaire. Dites «Sélectionner» pour le faire apparaître.

> [!NOTE]
> Les rayons émanant de la main ne sont pas pris en charge sur HoloLens (1èregénération).

| Dites | Pour |
| - | - |
| «Sélectionner» | Dites «sélectionner» pour afficher le curseur oculaire. Tournez ensuite la tête pour déplacer le curseur sur l’élément que vous souhaitez sélectionner, puis dites «Sélectionner» à nouveau. |
| «Menu Démarrer» |  Ouvrir le menu Démarrer |
| «Fermer»  | Fermer le menu Démarrer |
| Dites «Menu Démarrer» pour afficher le menu des actions rapides, puis dites «Accueil réalité mixte».  | Quitter une application immersive |
| «Masquer le rayon émanant de la main»/«Afficher le rayon émanant de la main» | Masquer et afficher le rayon émanant de la main |
| «Que puis-je dire?»  | Voir les commandes vocales disponibles |

À partir de la version19041.x de HoloLens2, vous pouvez également utiliser les commandes suivantes:

| Dites | Pour ce faire |
| - | - |
| «Redémarrer l’appareil» | Ouvrir une boîte de dialogue permettant de confirmer que vous voulez redémarrer l’appareil. Vous pouvez dire «oui» pour redémarrer. |
| «Arrêter l’appareil» | Ouvrir une boîte de dialogue permettant de confirmer que vous voulez éteindre l’appareil. Vous pouvez dire «oui» pour confirmer. |
| «Augmenter/réduire la luminosité» | Augmenter ou diminuer la luminosité de l’affichage de 10%. |
| «Monter/baisser le volume» | Augmenter ou diminuer le volume de 10%. |
| «Quelle est mon adresse IP» | Ouvrir une boîte de dialogue affichant l’adresse IP actuelle de votre appareil sur le réseau local. |
| «Prendre une photo» | Capturer une photo de réalité mixte de ce que vous voyez actuellement. |
| «Faire une vidéo» | Démarrer l’enregistrement d’une vidéo de réalité mixte. | 
| «Arrêter l’enregistrement» | Arrête l’enregistrement vidéo de réalité mixte actuel s’il est en cours. |

### <a name="hologram-commands"></a>Commandes d’hologramme

Pour utiliser ces commandes, pointez du regard un objet3D, un hologramme ou une fenêtre d’application.

| Dites | Pour |
| - | - |
| «Plus grand» | Agrandir |
| «Plus petit» | Réduire la taille de votre fichier |
| «Tourne-toi vers moi» | Tourner un élément vers vous |
| «Déplacer» | Déplace run élément (suivre votre point de regard) |
| «Fermer» | Fermer un élément |
| «Me suivre»/«Arrêter le suivi» | Faire en sorte que l’élément vous suive dans vos déplacements |

### <a name="see-it-say-it"></a>Le voir, le dire

De nombreux boutons et autres éléments sur HoloLens répondent également à votre voix (par exemple, **Me suivre** et **Fermer** dans la barre de l’application ou le bouton **Retour** dans Microsoft Edge). Pour savoir si un bouton est activé pour la voix, maintenez **le curseur du regard**, **le curseur tactile** ou **le rayon émanant de la main** sur celui-ci pendant un instant. Si le bouton est activé pour la voix, un conseil vocal apparaît.

### <a name="dictation-mode"></a>Mode dictée

Vous en avez assez de taper? Basculez en mode dictée chaque fois que le clavier holographique est actif. Pour commencer, sélectionnez le bouton de micro ou dites «Démarrer la dictée». Pour arrêter la dictée, sélectionnez le bouton à nouveau ou dites «Arrêter la dictée». Pour supprimer ce que vous venez de dicter, dites «Supprimer cela». 

> [!NOTE]
> Pour utiliser le mode dictée, vous devez disposer d’une connexion Internet.

La dictée HoloLens utilise des signes de ponctuation explicite, ce qui signifie que vous prononcez le nom du signe de ponctuation que vous voulez utiliser. Par exemple, vous pouvez dire «Hey **virgule** que fais-tu **point d’interrogation**.»

Voici les mots-clés que vous pouvez utiliser:

- Point, virgule, point d’interrogation, point d’exclamation
- Nouvelle ligne/nouveau paragraphe
- Point-virgule, deux-points
- Guillemet d’ouverture, guillemet de fermeture
- Mot-dièse, émoticône, clin d’œil
- Dollar, pourcentage

Il peut parfois être utile d’épeler des éléments tels que les adresses de messagerie. Par exemple, pour dicter exemple@outlook.com, vous devez dire «E X E M P L E à Outlook point com».

## <a name="do-more-with-cortana"></a>En faire plus avec Cortana

Cortana peut vous aider à faire toutes sortes d’actions sur votre HoloLens, mais selon la version de Windows Holographique utilisées, les fonctionnalités peuvent être différentes. Vous pouvez en savoir plus sur les fonctionnalités mises à jour de la dernière version de Cortana ici: Cortana dans la prochaine version de [Windows10](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/): axée sur votre productivité avec une sécurité et une confidentialité accrues. 

![Hey Cortana!](images/cortana-on-hololens.png)

Voici quelques conseils que vous pouvez essayer de dire (n’oubliez pas de dire «Hey Cortana» d’abord).

**Hey, Cortana**...

- Que puis-je dire?
- Lancer<*nom de l’application*>.
- Quelle heure est-il?
- Afficher les derniers scores NBA.
- Raconte-moi une blague.

Si vous utilisez la *version18362.x ou une version antérieure*, vous pouvez également utiliser les commandes suivantes:

**Hey, Cortana**...

- Augmenter le volume.
- Diminuer la luminosité de l’écran.
- Arrêter.
- Redémarrer.
- Mettre en veille.
- Muet.
- Déplacer <*nom de l’application*> ici (pointez sur l’emplacement vers lequel vous voulez déplacer l’application).
- Ouvrir le menu Démarrer.
- Prendre une photo.
- Démarrer l’enregistrement. (Démarre l’enregistrement d’une vidéo.)
- Arrêter l’enregistrement. (Arrête l’enregistrement d’une vidéo.)
- Quelle est la charge restante de la batterie?

Certaines fonctionnalités de Cortana auxquelles vous êtes habitué dans Windows sur votre PC ou votre téléphone (par exemple, rappels ou notifications) ne sont pas prises en charge dans Microsoft HoloLens et l’interface de Cortana peut varier d’une région à l’autre.

### <a name="turn-cortana-off"></a>Désactiver Cortana

Cortana est activée la première fois que vous utilisez HoloLens lorsque vous activez la fonctionnalité vocale. Vous pouvez la désactiver dans les Paramètres de Cortana. Dans la liste **Toutes apps**, sélectionnez  **Cortana** > **Paramètres**. Puis Cortana peut vous fournir des suggestions, des idées, des rappels, des alertes, etc..

Si Cortana ne répond pas à «Hey Cortana», vérifiez que la fonctionnalité vocale est activée dans le menu Démarrer, puis accédez aux paramètres de Cortana et vérifiez qu’elle est activée.
