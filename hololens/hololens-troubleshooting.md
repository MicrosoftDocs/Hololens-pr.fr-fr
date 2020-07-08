---
title: Résolution des problèmes
description: Solutions pour les problèmes courants de HoloLens.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: problèmes, bogue, résolution des problèmes, correction, aide, support, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 15998fe11de1e7be4f12087a2724bec7e22337b0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857742"
---
# Résolution des problèmes

Cet article décrit comment résoudre plusieurs problèmes courants de HoloLens.

## Mon HoloLens ne répond pas ou ne démarre pas

Si votre HoloLens ne démarre pas:

- Si les voyants situés à côté du bouton d’alimentation ne s’allument pas ou qu’un seul voyant clignote, il est possible que vous deviez [facturer votre HoloLens.](hololens-recovery.md#charging-the-device)
- Si les voyants s’allument lorsque vous appuyez sur le bouton d’alimentation et que vous ne voyez aucun élément sur les écrans, [Préformez une réinitialisation matérielle de l’appareil](hololens-recovery.md#hard-reset-procedure).

Si votre HoloLens devient figé ou ne répond pas, procédez comme suit:

- Désactivez votre HoloLens en appuyant sur le bouton d’alimentation jusqu’à ce que les cinq voyants soient éteints ou qu’il n’y ait pas de réponse pendant 15 secondes. Pour démarrer votre HoloLens, appuyez de nouveau sur le bouton d’alimentation.

Si les étapes suivantes ne fonctionnent pas, vous pouvez essayer [de récupérer votre appareil hololens 2 ou votre](hololens-recovery.md) [appareil hololens (1ère génération).](hololens1-recovery.md)

## Les hologrammes ne conviennent pas

Si vos hologrammes sont instables, inversement ou ne vous convient pas, essayez l’une des opérations suivantes:

- Nettoyage de votre visière de périphériques et de la barre des capteurs au premier plan de votre HoloLens.
- Augmenter la luminosité dans votre salon.
- Lorsque vous parcourez et regardez votre environnement, le HoloLens peut les analyser plus complètement.
- Étalonner votre HoloLens pour les yeux. Accédez à **paramètres**  >  **système**  >  **Utilities**. Sous **Étalonnage**, sélectionnez **Ouvrir l'étalonnage**.

## Le HoloLens ne répond pas aux gestes

Pour vous assurer que HoloLens peut voir vos gestes.  Gardez votre mains dans le cadre du mouvement: lorsque HoloLens peut voir votre mains, le curseur se transforme en anneau.

En savoir plus sur l’utilisation des gestes sur [hololens (1er génération)](hololens1-basic-usage.md#use-hololens-with-your-hands) ou [hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si votre environnement est trop sombre, le HoloLens peut ne pas voir votre mains, alors assurez-vous qu’il y a suffisamment de lumière.

Si votre visière est dotée d’empreintes digitales ou de traînées, utilisez le microfiber de nettoyage fourni avec le HoloLens pour nettoyer légèrement votre visière.

## HoloLens ne répond pas aux commandes vocales

Si Cortana ne répond pas à vos commandes vocales, vérifiez que Cortana est activée. Dans la liste toutes les applications, **Cortana**sélectionnez  >  **Menu**  >  paramètres du**bloc-notes**du menu Cortana  >  **Settings** pour apporter des modifications. Pour en savoir plus sur ce que vous pouvez dire, voir [Utiliser votre voix avec HoloLens](hololens-cortana.md).

## Je ne peux pas insérer d’hologrammes ou voir les hologrammes que j’ai déjà placés

Si HoloLens ne peut pas mapper ou charger votre espace, il passe en mode d’affichage limité et vous ne pouvez pas placer d’hologrammes ni voir les hologrammes que vous avez placés. Voici quelques opérations que vous pouvez tenter:

- Assurez-vous qu’il y a suffisamment de lumière dans votre environnement pour que HoloLens puisse voir et mapper l’espace.
- Vérifiez que vous êtes connecté à un réseau Wi-Fi. Si vous n’êtes pas connecté à un réseau Wi-Fi, HoloLens ne peut pas identifier et charger un espace connu.
- Si vous avez besoin de créer un nouvel espace, connectez-vous à un réseau Wi-Fi, puis redémarrez votre HoloLens.
- Pour savoir si l’espace approprié est actif ou si vous voulez charger manuellement un espace, accédez à **paramètres**  >  **System**  >  **espaces**système.
- Si l’espace disponible est suffisant et que vous rencontrez toujours des problèmes, l’espace est peut-être corrompu. Pour résoudre ce problème, sélectionnez l’espace, puis cliquez sur **supprimer**. Après suppression de l’espace, HoloLens commence à mapper votre environnement et crée un nouvel espace.

## Mon HoloLens ne peut pas déterminer l’espace

Si votre HoloLens ne peut pas identifier et charger l’espace que vous avez automatiquement, vérifiez les éléments suivants:

- Vérifiez que vous êtes connecté au Wi-Fi.
- Assurez-vous que la pièce est suffisamment éclairée
- Assurez-vous que les changements importants n’ont pas été apportés à l’environnement.

Vous pouvez également charger un espace manuellement ou gérer vos espaces en accédant à **paramètres**des  >  **System**  >  **espaces**système.

## Je reçois un message d’erreur «espace disque insuffisant»

Vous devez libérer de l’espace de stockage en effectuant l’une des opérations suivantes:

- Supprimez des espaces inutilisés. Accédez à **paramètres**  >  **System**  >  **espaces**système, sélectionnez un espace dont vous n’avez plus besoin, puis sélectionnez **supprimer**.
- Supprimez l’ensemble des hologrammes que vous avez placés.
- Supprimez des images et des vidéos à partir de l’application photos.
- Désinstallez des applications dans votre HoloLens. Dans la liste **toutes les applications** , appuyez de façon prolongée sur l’application que vous voulez désinstaller, puis cliquez sur **désinstaller**.

## Mon HoloLens ne peut pas créer un nouvel espace

Le problème le plus probable réside dans le fait que vous utilisez un espace de stockage insuffisant. Essayez l’une des [suggestions précédentes](#im-getting-a-low-disk-space-error) pour libérer de l’espace sur le disque.

## L’émulateur HoloLens ne fonctionne pas

Pour plus d’informations sur l’émulateur HoloLens, voir documentation du développeur.  En savoir plus sur [la résolution des problèmes liés à l’émulateur HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
