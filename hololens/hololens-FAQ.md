---
title: Forum aux questions sur les appareils et les hologrammes HoloLens
description: Vous avez une question rapide concernant HoloLens ou l’interaction avec les hologrammes ?  Cet article fournit une réponse rapide et plus de ressources.
keywords: hololens, FAQ, problème connu, aide
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924024"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Résolution des problèmes des hologrammes et des interactions

Cet article vous aide à résoudre les problèmes liés à la mise en place d’hologrammes, à l’utilisation d’espaces et à la création de rapports sur les hologrammes.

À chaque fois que vous rencontrez des problèmes, assurez-vous que :
- Essayez de [le redémarrer](hololens-restart-recover.md) pour voir si cela permet de résoudre les problèmes.
- Avant de résoudre le problème, assurez-vous que le HoloLens est [facturé](hololens2-charging.md) (facturé pendant au moins une heure). 


Utilisez l’application de commentaires pour nous envoyer des informations sur le problème. Vous trouverez l’application commentaires dans le menu [ **Démarrer**](holographic-home.md). 

Pour obtenir des conseils sur l’usure de votre HoloLens, consultez [ajuster la taille](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Impossible de créer des espaces](#new-spaces-cant-be-created)
- [Les espaces ne peuvent pas être identifiés ou chargés](#spaces-cant-be-identified-or-loaded)
- [Comment faire supprimer tous les espaces ?](#how-do-i-delete-all-spaces)
- [Les hologrammes ne s’affichent pas correctement ou sont en mouvement](#holograms-dont-look-right-or-are-moving-around)
- [Message « recherche de votre espace »](#finding-your-space-message)
- [Les hologrammes attendus ne s’affichent pas dans mon espace](#expected-holograms-arent-showing-in-my-space)
- [Impossible de placer des hologrammes ou d’afficher les hologrammes précédemment placés](#cant-place-holograms-or-see-previously-placed-holograms)
- [Les hologrammes disparaissent ou se trouvent dans d’autres hologrammes ou objets](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Les hologrammes apparaissent de l’autre côté d’un mur](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Après avoir placé un hologramme sur un mur, il semble flotter](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Les applications s’affichent trop près après les avoir déplacées](#apps-appear-too-close-after-moving-them)
- [Signalement des problèmes liés à des hologrammes instables ou inexacts](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Impossible de créer des espaces

Le problème le plus probable est que vous manquez d’espace de stockage. [Libérez de l’espace disque](hololens-troubleshooting.md#low-disk-space-error) , puis réessayez.

[Retour à la liste](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Les espaces ne peuvent pas être identifiés ou chargés

Si votre HoloLens ne parvient pas à identifier et à charger l’espace dont vous disposez automatiquement, vérifiez les facteurs suivants :

- Assurez-vous que vous êtes connecté à Wi-Fi
- Assurez-vous qu’il y a beaucoup de lumière dans la pièce
- Assurez-vous que les modifications majeures n’ont pas été apportées à l’environnement.

Vous pouvez également charger un espace manuellement ou gérer vos espaces en accédant à **paramètres**  >    >  **espaces** système.

[Retour à la liste](#list)

## <a name="how-do-i-delete-all-spaces"></a>Comment faire supprimer tous les espaces ?

*À venir*

[Retour à la liste](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Les hologrammes ne s’affichent pas correctement ou sont en mouvement

Si vos hologrammes ne s’affichent pas correctement (par exemple, s’ils sont instables ou tremblent, ou si vous voyez des correctifs noirs sur ceux-ci), essayez l’une des solutions suivantes :

- [Nettoyez votre visière d’appareils](hololens1-hardware.md#care-and-cleaning) et assurez-vous que rien ne bloque les capteurs.
- Assurez-vous que vous êtes dans une salle bien éclairante qui n’a pas beaucoup de lumière solaire directe.
- Essayez de vous rendre à l’Gazing et à votre environnement afin que HoloLens puisse les analyser plus complètement.
- Si vous avez placé de nombreux hologrammes, essayez de les supprimer.

Si vous rencontrez toujours des problèmes, essayez d’exécuter l’application d’étalonnage. Cette application étalonne votre HoloLens uniquement pour vous aider à faire en sorte que vos hologrammes cherchent le mieux. Pour ce faire, accédez à **paramètres**  >  **système**  >  **utilitaires**. Sous **étalonnage**, sélectionnez **ouvrir l’étalonnage**.

[Retour à la liste](#list)

## <a name="finding-your-space-message"></a>Message « recherche de votre espace »

Lorsque HoloLens apprend ou charge un espace, vous pouvez voir un message succinct indiquant « recherche de votre espace ». Si ce message s’affiche pendant plus de quelques secondes, vous verrez un autre message dans le menu Démarrer qui indique « toujours en train de chercher votre espace ».

Ces messages signifient que HoloLens rencontre des difficultés pour mapper votre espace. Dans ce cas, vous pouvez ouvrir des applications, mais vous ne pouvez pas placer des hologrammes dans votre environnement.

Si ces messages s’affichent souvent, essayez un ou plusieurs des correctifs suivants :

- Assurez-vous que vous êtes dans une salle bien éclairante qui n’a pas beaucoup de lumière solaire directe.
- Assurez-vous que votre visière d’appareil est propre. [Découvrez comment nettoyer votre visière](hololens1-hardware.md#care-and-cleaning).
- Assurez-vous que vous disposez d’un signal Wi-Fi élevé. Si vous entrez un nouvel environnement qui n’a pas de Wi-Fi ou un signal Wi-Fi faible, HoloLens ne peut pas trouver votre espace. Vérifiez votre connexion Wi-Fi en accédant à **paramètres**  >  **réseau &amp; Internet**  >  **Wi-Fi**.
- Essayez de vous déplacer plus lentement.

[Retour à la liste](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Les hologrammes attendus ne s’affichent pas dans mon espace

Si vous ne voyez pas les hologrammes que vous avez placés ou si vous voyez certains que vous ne vous attendez pas, essayez un ou plusieurs des correctifs suivants :

- Allumez des lumières. HoloLens fonctionne mieux dans un espace bien éclairé.
- Pour supprimer des hologrammes dont vous n’avez pas besoin, accédez à **paramètres**  >    >  **hologrammes** système  >  **Supprimer les hologrammes à proximité**. Ou, si nécessaire, sélectionnez **Supprimer tous les hologrammes**.

  > [!NOTE]
  > Si la disposition ou l’éclairage de votre espace change de façon significative, il se peut que votre appareil ait des difficultés à identifier votre espace et à montrer vos hologrammes.

[Retour à la liste](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Impossible de placer des hologrammes ou d’afficher les hologrammes précédemment placés

Si HoloLens ne peut pas mapper ou charger votre espace, il passe en mode limité et vous ne pouvez pas placer d’hologrammes ni voir les hologrammes que vous avez placés. Voici quelques points à essayer :

- Assurez-vous qu’il y a suffisamment de lumière dans votre environnement pour que HoloLens puisse voir et mapper l’espace.
- Mettez entre un et trois mètres à partir duquel vous essayez de placer l’hologramme.
- Ne placez pas les hologrammes sur des surfaces noires ou réfléchissantes.
- Assurez-vous que vous êtes connecté à un réseau Wi-Fi. Si vous n’êtes pas connecté au Wi-Fi, HoloLens ne peut pas identifier et charger un espace connu.
- Parcourez les salles afin que HoloLens puisse relancer l’analyse de votre environnement. Pour voir ce qui a déjà été analysé, appuyez sur air pour afficher le graphique de maillage de mappage.
- Si vous avez besoin de créer un nouvel espace, connectez-vous au Wi-Fi, puis redémarrez votre HoloLens.
- Pour voir si l’espace correct est actif ou pour charger manuellement un espace, accédez à **paramètres**  >    >  **espaces** système.
- Si l’espace correct est chargé et que vous rencontrez toujours des problèmes, l’espace est peut-être endommagé. Pour résoudre ce problème, sélectionnez l’espace, puis sélectionnez **supprimer**. Une fois que vous avez supprimé l’espace, HoloLens commence à mapper votre environnement et à créer un nouvel espace.

[Retour à la liste](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Les hologrammes disparaissent ou se trouvent dans d’autres hologrammes ou objets

Si vous êtes trop proche d’un hologramme, il disparaît temporairement &mdash; pour restaurer l’hologramme, mais ne vous en éloignez pas. En outre, si vous avez placé plusieurs hologrammes, certains peuvent disparaître. Essayez de supprimer quelques-uns.

Les hologrammes peuvent également être bloqués ou encasés par d’autres hologrammes ou par des objets tels que des murs. Dans ce cas, essayez l’un des correctifs suivants :

- Si l’hologramme est placé dans un autre hologramme, déplacez-le vers un autre emplacement. Pour ce faire, sélectionnez **ajuster**, puis appuyez et maintenez la touche enfoncée pour positionner le curseur.
- Si l’hologramme est présent dans un mur, sélectionnez **ajuster**, puis parcourez le mur jusqu’à ce que l’hologramme apparaisse. Appuyez et maintenez, puis tirez l’hologramme vers l’avant et l’arrière du mur.
- Si vous ne pouvez pas déplacer l’hologramme à l’aide de gestes, utilisez votre voix pour le supprimer. Pointez avec le regard de l’hologramme, puis dites « supprimer ». Rouvrez ensuite l’hologramme et placez-le à un nouvel emplacement.

[Retour à la liste](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Les hologrammes apparaissent de l’autre côté d’un mur

Si vous êtes très proche d’un mur ou si HoloLens n’a pas encore numérisé le mur, vous pouvez voir les hologrammes qui se trouvent dans la salle suivante. Pour numériser le mur, mettez entre un et trois mètres du mur et pointez dessus.

Un objet noir ou réfléchissant (par exemple, un canapé noir ou un réfrigérateur en acier inoxydable) à proximité du mur peut entraîner des problèmes lorsque HoloLens tente d’analyser le mur. S’il y a un tel objet, analysez l’autre côté du mur.

[Retour à la liste](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Après avoir placé un hologramme sur un mur, il semble flotter

Un hologramme que vous placez sur un mur semble généralement être un pouce ou donc éloigné du mur. S’il semble être plus éloigné, essayez un ou plusieurs des correctifs suivants :

- Lorsque vous placez un hologramme sur un mur, placez-le entre un et trois mètres du mur et retrouvez-le sur le mur.
- Air Appuyez sur le mur pour afficher le graphique de maillage de mappage. Assurez-vous que le maillage est aligné sur le mur. Si ce n’est pas le cas, supprimez l’hologramme, relancez l’analyse du mur, puis réessayez.
- Si le problème persiste, exécutez l’application d’étalonnage. Vous le trouverez dans **paramètres**  >  **système**  >  **utilitaires**.

[Retour à la liste](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Les applications s’affichent trop près après les avoir déplacées

Essayez de vous pencher sur la zone dans laquelle vous placez l’application afin que HoloLens analyse la zone à partir de différents angles. [Le nettoyage de votre visière d’appareils](hololens1-hardware.md#care-and-cleaning) peut également être utile.

[Retour à la liste](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Signalement des problèmes liés à des hologrammes instables ou inexacts
 
1. Veuillez enregistrer et une [réalité mixte pour capturer la vidéo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) du problème. Cette vidéo peut être téléchargée ultérieurement via le hub de commentaires sous forme de fichier joint.  
1. Activez la télémétrie complète via les **paramètres** application- **> confidentialité**  ->  **Diagnostics & commentaires** et sous données de **diagnostic facultatives** , vérifiez que le bouton bascule est défini **sur activé** .
1. Procurez-vous les dernières mises à l’échelle et stabilité des hologrammes en mettant à jour le [système d’exploitation Windows holographique le plus récent (20H2 ou version ultérieure)](hololens-release-notes.md#windows-holographic-version-20h2). Après la mise à jour, procédez comme suit :
    1. Retirez tous les hologrammes via les **paramètres** application ->  ->  **hologrammes** du système-> puis sélectionnez **Supprimer tous les hologrammes** et commencez avec un nouveau mappage.
    1. Créez un nouveau mappage de votre espace en portant la carte HoloLens et en vous reportant à l’ensemble des zones et des surfaces dans l’espace. Procédez ainsi pendant 2-3 minutes.
    1. Effectuez un étalonnage IPD. Accédez à **paramètres**  >  **système**  >  **utilitaires**. Sous **étalonnage**, sélectionnez **ouvrir l’étalonnage**.
    1. Testez à nouveau le scénario et voyez s’il persiste.
1. Si la mise à jour ne résout pas le problème, veuillez envoyer un [problème au hub de commentaires](hololens-feedback.md). Une fois que vous avez rempli vos commentaires, vous pouvez utiliser le bouton **partager** pour créer un lien facile à partager qui peut être envoyé lorsque vous contactez le support technique.

[Retour à la liste](#list)