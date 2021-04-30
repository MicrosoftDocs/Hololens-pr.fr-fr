---
title: Dépannage
description: Restez à jour sur les solutions les plus courantes aux problèmes liés aux appareils HoloLens et aux techniques de dépannage.
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
keywords: problèmes, bogue, dépannage, correction, aide, support, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308812"
---
# <a name="troubleshooting"></a>Dépannage

Cet article explique comment résoudre plusieurs problèmes courants liés à HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Mon HoloLens ne répond pas ou ne démarre pas

Si votre HoloLens ne démarre pas :

- Si les voyants situés à côté du bouton d’alimentation ne s’allument pas, ou si un seul LED clignote brièvement, vous devrez peut-être [charger votre HoloLens.](hololens-recovery.md#charge-the-device)
- Si les voyants s’allument lorsque vous appuyez sur le bouton d’alimentation mais que vous ne voyez rien dans les affichages, [Préformez une réinitialisation matérielle de l’appareil](hololens-recovery.md#hard-reset-procedure).

Si votre HoloLens est gelé ou ne répond pas :

- Éteignez votre HoloLens en appuyant sur le bouton d’alimentation jusqu’à ce que les cinq LED soient désactivées ou pendant 15 secondes si les LED ne répondent pas. Pour démarrer votre HoloLens, appuyez de nouveau sur le bouton d’alimentation.

Si ces étapes ne fonctionnent pas, vous pouvez essayer [de récupérer votre appareil hololens 2 ou votre](hololens-recovery.md) [appareil hololens (1er génération).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Les hologrammes ne sont pas corrects

Si vos hologrammes sont instables, sautent ou ne semblent pas corrects, essayez :

- Nettoyage de votre visière d’appareil et de la barre de capteur à l’avant de votre HoloLens.
- En accroissant la lumière dans votre salle.
- Vous pouvez vous pencher sur votre environnement pour que HoloLens puisse les analyser plus complètement.
- Étalonnage de votre HoloLens pour vos yeux. Accédez à **paramètres**  >  **système**  >  **utilitaires**. Sous **étalonnage**, sélectionnez **ouvrir l’étalonnage**.
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Signalement de problèmes où les hologrammes sont instables ou ne semblent pas corrects
 
1. Veuillez enregistrer et une [réalité mixte pour capturer la vidéo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) du problème. Cette vidéo peut être téléchargée ultérieurement via le hub de commentaires sous forme de fichier joint.  
1. Activez la télémétrie complète via les **paramètres** application- **> confidentialité**  ->  **Diagnostics & commentaires** et sous données de **diagnostic facultatives** , vérifiez que le bouton bascule est défini **sur activé** .
1. Procurez-vous les dernières mises à l’échelle et stabilité des hologrammes en mettant à jour le [système d’exploitation Windows holographique le plus récent (20H2 ou version ultérieure)](hololens-release-notes.md#windows-holographic-version-20h2). Après la mise à jour, procédez comme suit :
    1. Retirez tous les hologrammes via les **paramètres** application ->  ->  **hologrammes** du système-> puis sélectionnez **Supprimer tous les hologrammes** et commencez avec un nouveau mappage.
    1. Créez un nouveau mappage de votre espace en portant la carte HoloLens et en vous reportant à l’ensemble des zones et des surfaces dans l’espace. Procédez ainsi pendant 2-3 minutes.
    1. Effectuez un étalonnage IPD. Accédez à **paramètres**  >  **système**  >  **utilitaires**. Sous **étalonnage**, sélectionnez **ouvrir l’étalonnage**.
    1. Testez à nouveau le scénario et voyez s’il persiste.
1. Si la mise à jour ne résout pas le problème, veuillez envoyer un [problème au hub de commentaires](hololens-feedback.md). Une fois que vous avez rempli vos commentaires, vous pouvez utiliser le bouton **partager** pour créer un lien facile à partager qui peut être envoyé lorsque vous contactez le support technique.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens ne répond pas à l’entrée manuelle

Pour vous assurer que HoloLens peut voir vos mains, vous devez les conserver dans le cadre de mouvement.  La page d’hébergement de la réalité mixte fournit des commentaires qui vous permettent de savoir quand vos mains sont suivies.  Les commentaires sont différents sur les différentes versions de HoloLens :
- Sur HoloLens (1re génération), le curseur en regard passe d’un point à un anneau
- Sur HoloLens 2, un curseur à main s’affiche lorsque la main est proche d’un ardoise, et un rayon de la main apparaît lorsque les ardoises sont éloignées

De nombreuses applications immersifs suivent des modèles d’entrée similaires à la réalité mixte.  En savoir plus sur l’utilisation de la saisie manuelle sur [hololens (1re génération)](hololens1-basic-usage.md#use-hololens-with-your-hands) et [hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si vous portez des gants, Notez que certains types de gants ne fonctionnent pas avec le suivi des mains.  Un exemple courant est le noir en caoutchouc, qui a tendance à absorber la lumière infrarouge et n’est pas récupéré par l’appareil photo de profondeur.  Si votre travail implique des gants en caoutchouc, nous vous recommandons d’essayer une couleur plus claire, telle que le bleu ou le gris.  Un autre exemple est un grand gants Baggy, qui a tendance à obscurcir la forme de votre main. Nous vous recommandons d’utiliser les gants qui sont aussi adaptés à la forme que possible pour des résultats optimaux.

Si votre visière présente des empreintes digitales ou des traînées, utilisez le chiffon de nettoyage microfiber fourni avec le HoloLens pour nettoyer doucement votre visière.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens ne répond pas à mes commandes vocales

Si Cortana ne répond pas à vos commandes vocales, vérifiez que Cortana est activé. Dans la liste toutes les applications, sélectionnez  >    >  paramètres du **bloc-notes**  >   du menu Cortana pour apporter des modifications. Pour en savoir plus sur ce que vous pouvez prononcer, consultez [utiliser votre voix avec HoloLens](hololens-cortana.md).

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Je ne peux pas placer d’hologrammes ou voir les hologrammes que j’ai placés précédemment

Si HoloLens ne peut pas mapper ou charger votre espace, il passe en mode limité et vous ne pouvez pas placer d’hologrammes ni voir les hologrammes que vous avez placés. Voici quelques points à essayer :

- Assurez-vous qu’il y a suffisamment de lumière dans votre environnement pour que HoloLens puisse voir et mapper l’espace.
- Assurez-vous que vous êtes connecté à un réseau Wi-Fi. Si vous n’êtes pas connecté au Wi-Fi, HoloLens ne peut pas identifier et charger un espace connu.
- Si vous avez besoin de créer un nouvel espace, connectez-vous au Wi-Fi, puis redémarrez votre HoloLens.
- Pour voir si l’espace correct est actif ou pour charger manuellement un espace, accédez à **paramètres**  >    >  **espaces** système.
- Si l’espace correct est chargé et que vous rencontrez toujours des problèmes, l’espace est peut-être endommagé. Pour résoudre ce problème, sélectionnez l’espace, puis sélectionnez **supprimer**. Une fois que vous avez supprimé l’espace, HoloLens commence à mapper votre environnement et à créer un nouvel espace.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Mon HoloLens ne peut pas indiquer l’espace dans lequel je suis

Si votre HoloLens ne parvient pas à identifier et à charger l’espace dont vous disposez automatiquement, vérifiez les facteurs suivants :

- Assurez-vous que vous êtes connecté à Wi-Fi
- Assurez-vous qu’il y a beaucoup de lumière dans la pièce
- Assurez-vous que les modifications majeures n’ont pas été apportées à l’environnement.

Vous pouvez également charger un espace manuellement ou gérer vos espaces en accédant à **paramètres**  >    >  **espaces** système.

## <a name="im-getting-a-low-disk-space-error"></a>J’obtiens une erreur « espace disque insuffisant »

Vous devez libérer de l’espace de stockage en exécutant une ou plusieurs des opérations suivantes :

- Supprimez des espaces inutilisés. Accédez à **paramètres**  >    >  **espaces** système, sélectionnez un espace dont vous n’avez plus besoin, puis sélectionnez **supprimer**.
- Retirez certains des hologrammes que vous avez placés.
- Supprimez des images et des vidéos de l’application photos.
- Désinstallez des applications de votre HoloLens. Dans la liste **toutes les applications** , appuyez sur l’application que vous souhaitez désinstaller, maintenez-la enfoncée, puis sélectionnez **désinstaller**.

## <a name="my-hololens-cant-create-a-new-space"></a>Mon HoloLens ne peut pas créer d’espace

Le problème le plus probable est que vous manquez d’espace de stockage. Essayez l’une des [astuces précédentes](#im-getting-a-low-disk-space-error) pour libérer de l’espace disque.

## <a name="the-hololens-emulator-isnt-working"></a>L’émulateur HoloLens ne fonctionne pas

Des informations sur l’émulateur HoloLens se trouvent dans la documentation du développeur.  En savoir plus sur [le dépannage de l’émulateur HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
