---
title: Utiliser votre voix pour faire fonctionner HoloLens
description: Découvrez comment Cortana peut vous aider à réaliser toutes sortes d’actions sur vos appareils HoloLens de réalité mixte, notamment les commandes vocales, la dictée et les interactions avec un histogramme.
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
ms.openlocfilehash: 2fe7727fb05f983f56f329a6e7f7c25a627a914a1956fc65a9fc047653aae977
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661083"
---
# <a name="use-your-voice-to-operate-hololens"></a>Utiliser votre voix pour faire fonctionner HoloLens

Vous pouvez utiliser votre voix pour effectuer presque n’importe quelle action sur HoloLens, par exemple prendre une photo ou ouvrir une application. De nombreuses commandes vocales sont intégrées à HoloLens, tandis que d’autres sont disponibles par le biais de Cortana.

Cet article vous explique comment commander HoloLens et votre univers holographique avec votre voix et Cortana.

> [!NOTE]
> La reconnaissance vocale est uniquement prise en charge dans [certaines langues](hololens2-language-support.md). La langue de la reconnaissance vocale est basée sur la langue d’affichage de Windows, et non sur la langue du clavier.  
>  
> Pour vérifier la langue d’affichage de Windows, sélectionnez **Paramètres** > **Heure et langue** > **Langue**.

## <a name="built-in-voice-commands"></a>Commandes vocales intégrées

Naviguez dans HoloLens plus rapidement grâce à ces commandes de base. Pour pouvoir les utiliser, vous devez activer la reconnaissance vocale lors de la première exécution de l’appareil ou dans **Paramètres** > **Confidentialité** > **Voix**. Vous pouvez toujours vérifier si la reconnaissance vocale est activée en examinant l’état en haut du menu Démarrer. Pour obtenir les meilleurs résultats de reconnaissance vocale, HoloLens 2 utilise les services cloud de Microsoft. Toutefois, vous pouvez utiliser les paramètres pour désactiver cette fonctionnalité. Pour cela, dans Paramètres, désactivez la **reconnaissance vocale en ligne**. Une fois que vous avez modifié ce paramètre, HoloLens 2 traite uniquement les données vocales de façon locale pour reconnaître les commandes et la dictée, et Cortana ne sera pas disponible.

### <a name="general-speech-commands"></a>Commandes vocales générales

Utilisez ces commandes dans Windows Mixed Reality pour l’utiliser plus rapidement. Certaines commandes utilisent le curseur oculaire. Dites « Sélectionner » pour le faire apparaître.

> [!NOTE]
> Les rayons émanant de la main ne sont pas pris en charge sur HoloLens (1re génération).

| Dites | Pour |
| - | - |
| « Sélectionner » | Dites « Sélectionner » pour afficher le curseur oculaire. Tournez ensuite la tête pour placer le curseur sur l’élément que vous souhaitez sélectionner, puis dites « Sélectionner » une nouvelle fois. |
| « Menu Démarrer » |  Ouverture du menu Démarrer |
| « Fermer »  | Fermer le menu Démarrer |
| Dites « Menu Démarrer » pour afficher le menu des actions rapides, puis dites « Accueil réalité mixte ».  | Quitter une application immersive |
| « Masquer le rayon émanant de la main »/« Afficher le rayon émanant de la main » | Masquer et afficher le rayon émanant de la main |
| Qu’est-ce que je dis ?  | Consulter les commandes vocales disponibles |

À partir de la version 19041.x de HoloLens 2, vous pouvez également utiliser les commandes suivantes :

| Dites | Pour |
| - | - |
| « Redémarrer l’appareil » | Ouvrir une boîte de dialogue permettant de confirmer que vous voulez redémarrer l’appareil. Vous pouvez dire « oui » pour redémarrer. |
| « Arrêter l’appareil » | Ouvrir une boîte de dialogue permettant de confirmer que vous voulez éteindre l’appareil. Vous pouvez dire « oui » pour confirmer. |
| « Augmenter/réduire la luminosité » | Augmenter ou diminuer la luminosité de l’affichage de 10 %. |
| « Monter/baisser le volume » | Augmenter ou diminuer le volume de 10 %. |
| « Quelle est mon adresse IP » | Ouvrir une boîte de dialogue affichant l’adresse IP actuelle de votre appareil sur le réseau local. |
| « Prendre une photo » | Capturer une photo de réalité mixte de ce que vous voyez actuellement. |
| « Faire une vidéo » | Démarrer l’enregistrement d’une vidéo de réalité mixte. | 
| « Arrêter l’enregistrement » | Arrêter l’enregistrement vidéo de réalité mixte actuel s’il est en cours. |

### <a name="hologram-commands"></a>Commandes d’hologramme

Pour utiliser ces commandes, pointez du regard un objet 3D, un hologramme ou une fenêtre d’application.

| Dites | Pour |
| - | - |
| « Plus grand » | Agrandir |
| « Plus petit » | Réduire la taille |
| « Tourne-toi vers moi » | Tourner un élément vers vous |
| « Déplacer » | Déplacer un élément (suivre votre point de regard) |
| « Fermer » | Fermer un élément |
| « Me suivre »/« Arrêter le suivi » | Faire en sorte que l’élément vous suive dans vos déplacements |

### <a name="see-it-say-it"></a>Voir, prononcer

De nombreux boutons et autres éléments sur HoloLens répondent également à votre voix (par exemple, **Me suivre** et **Fermer** dans la barre de l’application ou le bouton **Précédent** dans Edge). Pour savoir si un bouton est activé pour la voix, maintenez le **curseur oculaire**, le **curseur tactile** ou un **rayon émanant de la main** sur celui-ci pendant un instant. Si le bouton est activé pour la voix, un conseil vocal apparaît.

### <a name="dictation-mode"></a>Mode de dictée

Vous en avez assez de taper ? Passez en mode dictée chaque fois que le clavier holographique est actif. Pour commencer, sélectionnez le bouton du micro ou dites « Démarrer la dictée ». Pour arrêter la dictée, sélectionnez le bouton à nouveau ou dites « Arrêter la dictée ». Pour supprimer ce que vous venez de dicter, dites « Supprimer cela ». 

> [!NOTE]
> Pour utiliser le mode dictée, vous devez disposer d’une connexion Internet.

La dictée HoloLens utilise des signes de ponctuation explicite, ce qui signifie que vous prononcez le nom du signe de ponctuation que vous voulez utiliser. Par exemple, vous pouvez dire « Bonjour **virgule** que fais-tu **point d’interrogation** »

Voici les mots-clés que vous pouvez utiliser pour la ponctuation :

- Point, virgule, point d’interrogation, point d’exclamation
- Nouvelle ligne/nouveau paragraphe
- Point-virgule, deux-points
- Ouvrir les guillemets, fermer les guillemets
- Mot-dièse, smiley, smiley mécontent, clin d’œil
- Dollar, pourcentage

Il peut parfois être utile d’épeler des éléments tels que les adresses de messagerie. Par exemple, pour dicter example@outlook.com, vous devez dire « E X A M P L E à outlook point com ».

## <a name="do-more-with-cortana"></a>En faire plus avec Cortana

Cortana peut vous aider à faire toutes sortes d’actions sur votre HoloLens, mais les fonctionnalités peuvent varier en fonction de la version de Windows Holographique que vous utilisez. Pour en savoir plus sur les fonctionnalités mises à jour de la dernière version de Cortana, consultez [Cortana in the upcoming Windows 10 release: focused on your productivity with enhanced security and privacy](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

![« Hey Cortana »](images/cortana-on-hololens.png)

Voici quelques opérations que vous pouvez essayer de dire (n’oubliez pas de dire « Hey Cortana » d’abord).

**Hey, Cortana**...

- Que puis-je dire ?
- Lancer <*nom de l’application*>.
- Quelle heure est-il ?
- Afficher les derniers scores NBA.
- Raconte-moi une blague.

Si vous utilisez la *version 18362.x ou antérieure*, vous pouvez également utiliser les commandes suivantes :

**Hey, Cortana**...

- Augmenter le volume.
- Diminuer la luminosité.
- Arrêter.
- Redémarrer.
- Mettre en veille.
- Muet.
- Déplacer <*nom de l’application*> ici (pointez sur l’emplacement vers lequel vous voulez déplacer l’application).
- Allez à Démarrer.
- Prendre une photo.
- Démarrez l'enregistrement. (Démarre l’enregistrement d’une vidéo.)
- Arrêter l’enregistrement. (Arrête l’enregistrement d’une vidéo.)
- Quelle est la charge restante de la batterie ?

Certaines fonctionnalités de Cortana auxquelles vous êtes habitué dans Windows sur votre PC ou votre téléphone (par exemple, rappels ou notifications) ne sont pas prises en charge dans Microsoft HoloLens, et l’interface de Cortana peut varier d’une région à l’autre.

### <a name="turn-cortana-off"></a>Désactiver Cortana

Cortana est activé la première fois que vous utilisez HoloLens lorsque vous activez la fonctionnalité vocale. Vous pouvez le désactiver dans les paramètres de Cortana. Dans la liste **Toutes les applications**, sélectionnez **Cortana** > **Paramètres**. Désactivez ensuite Cortana.

Si Cortana ne répond pas à « Hey Cortana », vérifiez que la fonctionnalité vocale est activée dans le menu Démarrer, puis accédez aux paramètres de Cortana et vérifiez qu’il est activé.
