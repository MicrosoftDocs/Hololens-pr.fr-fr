---
title: Résolution des problèmes
description: Restez à jour sur les solutions les plus courantes pour les problèmes d’appareil HoloLens et les techniques de dépannage.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problèmes, bogue, résolution des problèmes, résoudre, aide, support, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283045"
---
# Résolution des problèmes

Cet article explique comment résoudre plusieurs problèmes HoloLens courants.

## My HoloLens is unresponsive or won’t start

Si votre HoloLens ne démarre pas :

- Si les voyants en côté du bouton d’alimentation ne s’allument pas ou si un seul voyant clignote brièvement, vous devrez peut-être charger [votre HoloLens.](hololens-recovery.md#charge-the-device)
- Si les LÉD s’allument lorsque vous appuyez sur le bouton d’alimentation, mais que vous ne voyez rien sur les écrans, préformez une réinitialisation matérielle [de l’appareil.](hololens-recovery.md#hard-reset-procedure)

Si votre HoloLens devient figé ou ne répond plus :

- Désélectifez votre HoloLens en appuyant sur le bouton d’alimentation jusqu’à ce que les cinq LD se désélectent eux-mêmes, ou pendant 15 secondes si les LD ne répond pas. Pour démarrer votre HoloLens, appuyez de nouveau sur le bouton d’alimentation.

Si ces étapes ne fonctionnent pas, vous pouvez essayer de récupérer votre appareil [HoloLens 2](hololens-recovery.md) ou [HoloLens (1ère génération).](hololens1-recovery.md)

## Les hologrammes n’ont pas bonne apparence

Si vos hologrammes sont instables, instables ou ne semblent pas à droite, essayez :

- Nettoyage de la visière et de la barre de capteur de votre appareil à l’avant de votre HoloLens.
- Augmentation de la lumière dans votre salle.
- Vous pouvez vous déplacer et regarder votre environnement afin que HoloLens puisse les analyser plus complètement.
- Étalonnage de votre HoloLens pour vos yeux. Go to **Settings**  >  **System**  >  **Utilities**. Sous **Étalonnage**, sélectionnez **Ouvrir l'étalonnage**.
 
### Signalement de problèmes où les hologrammes sont instables ou ne semblent pas à droite
 
1. Veuillez enregistrer et une [vidéo de capture de réalité mixte](holographic-photos-and-videos.md#capture-a-mixed-reality-video) du problème. Cette vidéo peut être téléchargée ultérieurement via le Hub de commentaires en tant que fichier joint.  
1. Activer la télémétrie complète via l’application **** **Paramètres** -> Diagnostics de confidentialité & commentaires et sous Données de  ->  **** **diagnostic facultatives** vérifier que le basculement est **activé**
1. Obtenez les derniers correctifs d’échelle et de stabilité de l’hologramme en mettant à jour le dernier système d’exploitation [Windows Holographique (20H2 ou version supérieure).](hololens-release-notes.md#windows-holographic-version-20h2) Après la mise à jour, effectuez les choses suivantes :
    1. Supprimez tous les hologrammes via **** l’application **Paramètres** ->  ->  **Hologrammes** système -> sélectionnez Supprimer tous les **hologrammes** et commencez par une nouvelle carte.
    1. Créez une carte de votre espace en utilisant holoLens et en parlant de votre salle et en regardant toutes les zones et toutes les surfaces de l’espace. Faites-le pendant 2 à 3 minutes.
    1. Effectuer un étalonnage IPD. Go to **Settings**  >  **System**  >  **Utilities**. Sous **Étalonnage**, sélectionnez **Ouvrir l'étalonnage**.
    1. Retentez le scénario et voyez s’il est toujours persistant.
1. Si la mise à jour ne corrige pas le problème, veuillez déposer un [problème de Hub de commentaires.](hololens-feedback.md) Une fois que vous avez **** rempli vos commentaires, vous pouvez utiliser le bouton Partager pour créer un lien facile à partager qui peut être envoyé lorsque vous contactez le support technique.

## HoloLens ne répond pas aux entrées de la main

Pour vous assurer que HoloLens peut voir vos mains, vous devez les conserver dans le cadre de mouvement.  La maison de réalité mixte fournit des commentaires qui vous font savoir quand vos mains sont suivis.  Les commentaires sont différents sur les différentes versions de HoloLens :
- Sur HoloLens (1ère génération), le curseur du regard passe d’un point à un anneau
- Sur HoloLens 2, un curseur du bout des doigts s’affiche lorsque votre main est proche d’une tablette et un rayon de la main s’affiche lorsque les tablettes sont plus éloigné

De nombreuses applications immersives suivent des modèles d’entrée similaires à mixed Reality Home.  En savoir plus sur l’utilisation de la saisie à la main sur [HoloLens (1ère génération)](hololens1-basic-usage.md#use-hololens-with-your-hands) et [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si vous portez des gant, notez que certains types de gant ne fonctionnent pas avec le suivi des mains.  Un exemple courant est celui des gant gant noir, qui ont tendance à filtrer la lumière infrarouge et ne sont pas pris en main par la caméra de profondeur.  Si votre travail implique des gant gant, nous vous recommandons d’essayer une couleur plus claire telle que le bleu ou le gris.  Un autre exemple est celui des grands gant sac, qui ont tendance à masquer la forme de votre main. Nous vous recommandons d’utiliser des gant aussi appropriés que possible pour obtenir de meilleurs résultats.

Si votre visière a des empreintes digitales ou des empreintes digitales, utilisez le nettoyage en microfibre qui est arrivé avec HoloLens pour nettoyer légèrement votre visière.

## HoloLens ne répond pas à mes commandes vocales

Si Cortana ne répond pas à vos commandes vocales, assurez-vous que Cortana est allumée. Dans la liste Toutes les applications, sélectionnez Paramètres du bloc-notes du menu **Cortana**  >  ****  >  ****  >  **** pour apporter des modifications. Pour en savoir plus sur ce que vous pouvez dire, voir [Utiliser votre voix avec HoloLens](hololens-cortana.md).

## Je ne peux pas placer d’hologrammes ou voir les hologrammes que j’ai placés précédemment

Si HoloLens ne peut pas ma router ou charger votre espace, il entre en mode limité et vous ne pourrez pas placer d’hologrammes ni voir les hologrammes que vous avez placés. Voici quelques opérations que vous pouvez tenter:

- Assurez-vous qu’il y a suffisamment de lumière dans votre environnement pour que HoloLens puisse voir et ma cartographier l’espace.
- Assurez-vous que vous êtes connecté à un Wi-Fi réseau. Si vous n’êtes pas connecté au Wi-Fi, HoloLens ne peut pas identifier et charger un espace connu.
- Si vous devez créer un espace, connectez-vous au Wi-Fi, puis redémarrez votre HoloLens.
- Pour voir si l’espace correct est actif ou pour charger manuellement un espace, rendez-vous sur **Espaces système**des  >  ****  >  **paramètres.**
- Si l’espace correct est chargé et que vous avez encore des problèmes, il se peut que l’espace soit endommagé. Pour résoudre ce problème, sélectionnez l’espace, puis sélectionnez **Supprimer.** Une fois que vous avez supprimé l’espace, HoloLens commence à ma cartographier votre environnement et à créer un espace.

## My HoloLens can’t tell what space I’m in

Si votre HoloLens ne peut pas identifier et charger l’espace que vous êtes automatiquement, vérifiez les facteurs suivants :

- Assurez-vous que vous êtes connecté à Wi-Fi
- Assurez-vous qu’il y a beaucoup de lumière dans la salle
- Assurez-vous qu’aucune modification majeure n’a été apportée à l’environnement.

Vous pouvez également charger un espace manuellement ou gérer vos espaces en allant dans **Espaces**  >  **système de**  >  **paramètres.**

## J’ai une erreur « Espace disque faible »

Vous devez libérer de l’espace de stockage en faisant une ou plusieurs des choses suivantes :

- Supprimez certains espaces inutilisés. Go to **Settings**  >  **System**  >  **Spaces,** select a space that you no longer need, and then select **Remove**.
- Supprimez certains hologrammes que vous avez placés.
- Supprimez des images et des vidéos de l’Photos’application.
- Désinstallez des applications dans votre HoloLens. Dans la **liste Toutes les applications,** appuyez longuement sur l’application à désinstaller, puis sélectionnez **Désinstaller.**

## My HoloLens can’t create a new space

Le problème le plus probable est que vous avez peu d’espace de stockage. Essayez l’un des [conseils précédents](#im-getting-a-low-disk-space-error) pour libérer de l’espace disque.

## L’émulateur HoloLens ne fonctionne pas

Les informations sur l’émulateur HoloLens se trouvent dans notre documentation du développeur.  En savoir plus [sur la résolution des problèmes de l’émulateur HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
