---
title: Préparer un nouveau HoloLens 2
description: Découvrez comment configurer et ajuster votre appareil HoloLens 2 pour la première fois, notamment les conseils en matière d’état de santé et de sécurité et les guides matériels.
keywords: hololens, lumières, ajustement, confort, pièces
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b17ad031cfd49ac7a7553765633bc948bafc01d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282905"
---
# Préparer votre HoloLens 2 pour utilisation

Les procédures ci-dessous vous aideront à configurer un HoloLens 2 pour la première fois.

## Charger votre HoloLens

Raccordez l’alimentation au port de charge à l’aide du câble USB-C (fourni). Branchez le bloc d’alimentation à une prise de courant. Le bloc d’alimentation et le câble USB-C vers C fournis avec l’appareil constituent le meilleur moyen de charger votre HoloLens 2. Le chargeur fournit 18 W d’alimentation (9V à 2A). À l’aide du chargeur mural fourni, les appareils HoloLens 2 peuvent charger la batterie à l’intégralité en moins de 65 minutes lorsque l’appareil est en veille.

Le taux de charge et la vitesse peuvent varier en fonction de l’environnement où l'appareil s'exécute.

- Lorsque l’appareil est en charge, l’indicateur de batterie s’allume pour indiquer le niveau de charge actuel.  Le dernier voyant clignote lentement pour indiquer que l’appareil est en charge.
- Lorsque votre HoloLens est allumé, le témoin de la batterie affiche le niveau de la batterie par incréments.
- Lorsqu’un seul des cinq voyants est allumé, le niveau de batterie est inférieur à 20 %.
- Si le niveau de batterie est extrêmement faible et que vous essayez d’allumer l’appareil, un voyant clignote brièvement, puis s’éteint.

Pour plus d’informations, vous pourrez trouver des [détails complets sur le chargement des appareils ici](hololens-recovery.md#charge-the-device). 

## Ajuster la taille

Placez le HoloLens 2 sur votre tête. Si vous portez des lunettes, conservez-les.  Le clavier de navigateur doit reposer confortablement sur votre front et la sangle arrière doit être placée au milieu de votre tête.

Le cas échéant, agrandissez l’arceau en tournant la molette d’ajustement, puis desserrez la sangle.

![Ajuster et régler HoloLens 2](images/hololens2-fit.png)

### Attacher et détacher la sangle

La sangle n’est pas obligatoire, mais elle peut augmenter le confort d’utilisation de HoloLens 2 sur de longues périodes d’utilisation.

Pour retirer l’avant de la sangle, détachez-la et faites-la glisser dans la boucle rétractable du clavier de navigateur. Pour la fixer à nouveau, tirez la boucle et faites glisser la sangle à l’intérieur.

Pour retirer l’arrière de la sangle, appuyez sur le bouton situé sous chaque languette, puis tirez doucement. Pour la fixer à nouveau, replacez les languettes dans les encoches jusqu’à entendre un clic.

![fixer ou retirer la sangle de HoloLens 2](images/hololens2-headstrap.png)

## Allumer HoloLens 2

Pour allumer votre HoloLens 2, appuyez sur le bouton d’alimentation.  Les voyants lumineux situés sous le bouton d’alimentation indiquent le niveau de la batterie.

> [!NOTE]
> Pour mettre sous tension HoloLens 2 pour la première fois, appuyez sur le bouton d’alimentation pendant au moins 4 secondes pour l’allumer. La fois suivante, HoloLens 2 démarre après une brève pression sur le bouton d’alimentation.

### Actions sur le bouton d’alimentation pour différentes transitions d’alimentation

| Pour | Effectuer cette action | Réactions de HoloLens 2 |
| - | - | - |
| Allumer | Appuyer une fois sur le bouton. | Les cinq voyants s’allument, puis changent pour indiquer le niveau de la batterie. Après 4 secondes, le son est émis. |
| Mette en veille | Appuyer une fois sur le bouton. | Les cinq voyants s’allument, puis s’éteignent un par un. Une fois les voyants éteints, un son est émis et l’écran affiche « Au-revoir ». |
| Sortir du mode veille | Appuyer une fois sur le bouton. | Les cinq voyants s’allument, puis changent pour indiquer le niveau de la batterie. Un son est amis immédiatement. |
| Éteindre | Appuyez de façon prolongée pendant 5 secondes. |  Les cinq voyants s’allument, puis s’éteignent un par un. Après la désactivation des voyants, un son est émis et l’écran affiche « Au-revoir ». |
| Forcer le redémarrage de HoloLens s’il ne répond pas | Appuyer de façon prolongée pendant 10 secondes. | Les cinq voyants s’allument, puis s’éteignent un par un. Après la désactivation des voyants. |

## Référence de comportement HoloLens

Vous ne savez pas exactement ce qu’indiquent les témoins de votre HoloLens ? Vous voulez savoir comment HoloLens doit se comporter lors de la charge ?  Voici de l’aide.

### Comportement de chargement

| État de l’appareil | Action | HoloLens 2 effectue |
| - | - | - |
| Désactivée | Brancher le câble USB | L’appareil bascule sur activé. Les témoins lumineux indiquent le niveau de batterie et l’appareil commence à charger.
| ACTIVÉ | Retirer le câble USB | L’appareil cesse de se charger
| ACTIVÉ | Brancher le câble USB | L’appareil commence à charger
| VEILLE | Brancher un câble USB | L’appareil commence à charger
| VEILLE | Retirer le câble USB | L’appareil cesse de charger
| ACTIVÉ avec câble USB branché | Éteindre l’appareil | L’appareil bascule sur activé. Les témoins lumineux indiquent le niveau de batterie et l’appareil commence à charger |

### Voyants indiquant le niveau de la batterie

| Nombre de voyants | Niveau de la batterie |
| - | - |
| Quatre voyants allumés en continu, un clignotant | Entre 100 % et 81 % (charge complète) |
| Trois voyants allumés en continu, un clignotant | Entre 80 % et 61 % |
| Trois voyants allumés en continu, un clignotant | Entre 60 % et 41 % |
| Un voyant allumé en continu, un clignotant | Entre 40 % et 21 % |
| Un voyant clignotant | Entre 20 % et 5 % ou moins (niveau de batterie critique) |

### Comportement en veille

| État de l’appareil | Action | HoloLens 2 effectue |
| - | - | - |
| ACTIVÉ | Pression unique sur le bouton d’alimentation | L’appareil bascule en VEILLE et tous les témoins sont éteints |
| ACTIVÉ | Aucun mouvement pendant 3 minutes | L’appareil bascule en VEILLE et tous les témoins sont éteints |
| VEILLE | Pression unique sur le bouton d’alimentation | L’appareil bascule sur ACTIVÉ et les témoins s’allument |

### Voyants signalant des problèmes

| Lorsque vous effectuez cette action | Les voyants réagissent ainsi | Cela signifie que |
| - | - | - |
| Appuyer sur le bouton d’alimentation. | Un voyant clignote cinq fois, puis s’éteint. | La batterie HoloLens est très basse. Chargez votre HoloLens. |
| Appuyer sur le bouton d’alimentation. | Les cinq voyants clignotent cinq fois, puis s’éteignent. |  HoloLens ne parvient pas à démarrer correctement ; il est dans un état d’erreur. [Réinstallez le système d’exploitation](hololens-recovery.md) pour récupérer votre appareil. |
| Appuyer sur le bouton d’alimentation. | Le premier, troisième et cinquième voyants clignotent continuellement. |  HoloLens peut présenter une défaillance matérielle. Contacter le [support](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb). |

## Sécurité et confort

### Utiliser HoloLens dans un environnement sûr

Utilisez votre HoloLens dans un espace sûr, sans obstacles, dans lequel vous ne risquez pas de trébucher. Ne l’utilisez pas quand vous avez besoin d’un champ de vision dégagé ou que vous ne pouvez pas vous concentrer pleinement, par exemple lorsque vous utilisez un véhicule ou que vous effectuez d’autres activités potentiellement dangereuses.

### Confort

Faites en sorte que vos premières séances avec HoloLens soient brèves et faites des pauses. Si vous éprouvez une sensation d’inconfort, arrêtez-vous jusqu’à ce que vous vous sentiez mieux. Les troubles ressentis peuvent être des nausées, le mal des transports, des étourdissements, des maux de tête, une sensation de fatigue, une fatigue oculaire ou les yeux secs.

Voir [Instructions et avertissements relatifs à la sécurité des produits](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Prendre en main et configurer votre HoloLens 2](hololens2-start.md)
