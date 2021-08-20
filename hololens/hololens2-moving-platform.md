---
title: Mode plateforme mobile (MPM) d’HoloLens 2
description: Comment utiliser HoloLens sur les plateformes mobiles
keywords: plateformes mobiles, mouvement dynamique, hololens, mode plateforme mobile
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2c0e6e285b2eb86342450e8f05876e0cc3bccfe8
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858667"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Mode plateforme mobile (MPM) sur les plateformes mobiles à mouvements dynamiques faibles

Dans **Insider build 20348.1411**, nous avons ajouté le support de la version bêta pour le suivi sur les plateformes mobiles à mouvements dynamiques faibles sur HoloLens 2. Après avoir installé la version et activé le mode MPM, vous pouvez utiliser votre HoloLens 2 dans des environnements auparavant inaccessibles, tels que les grands navires. Actuellement, cette fonctionnalité ne vise qu’à activer ces plateformes mobiles spécifiques. Bien que rien ne vous empêche d’essayer d’utiliser la fonctionnalité dans d’autres environnements, celle-ci prend en charge ces environnements avant tout.

> [!NOTE]
> Cette fonctionnalité est actuellement disponible uniquement par le biais de Windows [Insiders](hololens-insider.md).

Cet article couvre les points suivants :

1. [Pourquoi une plateforme mobile est-elle nécessaire ?](#why-moving-platform-mode-is-necessary)
1. [Activation du mode MPM](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Pourquoi le mode MPM est-il nécessaire ?

L’HoloLens doit être capable de suivre la position de votre tête avec [6 degrés de liberté](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (translation X, Y, Z et rotation en roulis, tangage et lacet) afin d’afficher des hologrammes stables. Pour ce faire, HoloLens effectue le suivi de deux éléments similaires d’informations provenant de deux sources distinctes :

1. Caméras à lumière visible – qui suivent l’activité de l’environnement, par exemple la pièce dans laquelle vous utilisez l’HoloLens.
1. Unité de mesure d’inertie (IMU) – qui se compose d’un accéléromètre, d’un gyroscope et d’un magnétomètre qui effectue le suivi des mouvements et de l’orientation de votre tête par rapport à la terre

Les informations provenant de ces deux sources sont combinées pour suivre la position de votre tête à une faible latence et à une fréquence suffisamment élevée pour l’affichage fluide des hologrammes.

Cependant, cette approche repose sur une hypothèse critique : l’environnement (suivi par les caméras) reste stationnaire par rapport à la terre (et par rapport à laquelle l’unité effectue des mesures). Lorsque cela n’est pas le cas, comme sur un bateau qui navigue, les informations des deux sources peuvent entrer en conflit les unes avec les autres et perturber le dispositif de suivi. Ce conflit, qui produit des informations de position incorrectes, engendre des hologrammes saccadés, voire une perte de suivi.

Le mode MPM résout ce problème. Lorsque vous activez le mode MPM, cela indique à notre dispositif de suivi que nous ne pouvons pas compter sur la cohésion des données de nos capteurs au fil du temps. Au lieu de cela, nous devons nous appuyer davantage sur le suivi visuel, identifier rapidement les données de mouvement inertiel aberrantes et les filtrer en conséquence avant de pouvoir utiliser l’entrée de l’IMU.

## <a name="supported-environments-and-known-limitations"></a>Environnements pris en charge et limitations connues

Le mode MPM a été mis au point pour traiter intelligemment les conflits entre les données inertielles et visuelles, mais il est actuellement réservé aux grands navires dont le roulis et le tangage sont faibles. Cela signifie qu’il existe certainement des limitations et des scénarios non pris en charge.

### <a name="known-limitations"></a>Limites connues

- Les seuls environnements pris en charge dans le mode de plateforme mobile (MPM) sont les grands navires à tangage et roulis faibles. En d’autres termes, de nombreux environnements/situations courants ne sont **pas** encore pris en charge, car ils subissent des mouvements de grande amplitudes, de fortes accélérations ou des [secousses](https://en.wikipedia.org/wiki/Jerk_(physics)). Exemple : avions, trains, voitures, vélos, bus, petits bateaux, ascenseurs, etc.
- Les hologrammes peuvent osciller légèrement lorsque la fonction MPM est activée, notamment sur des eaux agitées.
- Rien n’empêche les utilisateurs de tenter d’utiliser le mode MPM dans des environnements non pris en charge. Toutefois, les utilisateurs peuvent observer des effets secondaires indésirables si l’appareil est en mesure de maintenir le suivi dans l’espace non pris en charge. Par exemple, avec MPM, les utilisateurs peuvent constater qu’il est possible d’utiliser un ascenseur tout en changeant d’étage, alors que cela était impossible auparavant. Malheureusement, bien que le mode MPM permette à l’appareil de conserver le suivi, il ne gère pas la gestion des cartes pour le moment. Ainsi, les utilisateurs constateront qu’en changeant d’étage avec un ascenseur, l’appareil confond les étages supérieurs et inférieurs et dégrade la qualité de la carte.

## <a name="prerequisites"></a>Prérequis

La prise en charge de la version bêta du mode Plateforme mobile ne nécessite que quelques conditions préalables :

1. Installez la build 20348.1411 ou une version plus récente [en flashant la build d’Insider la plus récente via ARC](hololens-insider.md#ffu-download-and-flash-directions) ou [en inscrivant votre appareil et en le mettant à jour ensuite](hololens-insider.md#start-receiving-insider-builds).
   - Remarque : cette build est actuellement disponible uniquement sur le [Canal développeurs Windows Insider](hololens-insider.md#start-receiving-insider-builds).
2. Activer [le mode développeur et le Portail d'appareil](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Activation du mode MPM

Pour activer le mode MPM mobile, commencez par [activer le Portail d’appareil](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Sélectionnez l’accordéon **Système** dans le menu de gauche.
2. Sélectionnez la page **Moving Platform Mode** et cochez la case **Moving Platform Mode**.

![Première image](.\images\moving-platform-1.png) ![Deuxième image](.\images\moving-platform-2.png)

3. Lorsque vous y êtes invité, sélectionnez **OK**.

![Troisième image](.\images\moving-platform-3.png)

4. Redémarrez votre appareil. Pour ce faire, sélectionnez le menu **Power** (Allumer) dans le Portail d’appareil en haut à droite ou dites la commande &quot;Redémarrer l’appareil&quot; à haute voix et sélectionnez &quot;Oui&quot;.

![Quatrième image](.\images\moving-platform-4.png)

Si vous ne parvenez pas à voir l’option Moving Platform Mode dans le Portail d’appareil, cela signifie probablement que vous ne travaillez pas encore avec la build appropriée. Consultez la section [Conditions préalables](#prerequisites).
