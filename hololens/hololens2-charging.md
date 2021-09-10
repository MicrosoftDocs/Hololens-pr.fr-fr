---
title: Batterie et charge de l’HoloLens 2
description: Charger votre HoloLens et utiliser des batteries externes
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427285"
---
# <a name="hololens-2-battery-and-charging"></a>Batterie et charge de l’HoloLens 2

Cette page fournit des détails relatifs à la charge de l’HoloLens 2 et à l’utilisation de batteries externes.

## <a name="charging-the-device"></a>Charge de l’appareil

Utilisez le [chargeur et le câble de type USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) fournis avec l’HoloLens 2 pour charger votre appareil de manière optimale. Le chargeur inclus avec HoloLens 2 permet jusqu’à 9V @ 2a (18W). À l’aide du chargeur mural fourni, les appareils HoloLens 2 peuvent intégralement charger la batterie en moins de 65 minutes lorsque l’appareil est en veille. Si ces accessoires ne sont pas disponibles, assurez-vous que le chargeur mis à disposition peut supporter au moins 15 W de puissance.

> [!NOTE]
> Si possible, évitez d’utiliser un PC pour charger l’appareil par câble USB car ce processus est lent.

## <a name="checking-the-battery-charge-level"></a>Vérifier le niveau de charge de la batterie
Si l’appareil est correctement initialisé et en cours d’exécution, trois méthodes s’offrent à vous pour vérifier le niveau de charge de la batterie :

- Dans le menu principal de l’interface utilisateur de l’appareil HoloLens.
- Regardez le voyant situé près du bouton d’alimentation (pour une charge de 40 %, vous devriez voir au moins deux voyants pleins).
    - Lorsque l’appareil est en charge, l’indicateur de batterie s’allume pour indiquer le niveau de charge actuel.  Le dernier voyant clignote lentement pour indiquer que l’appareil est en charge.
    - Lorsque votre HoloLens est allumé, le témoin de la batterie affiche le niveau de la batterie par cinq incréments.
    - Lorsqu’un seul des cinq voyants est allumé, le niveau de la batterie est inférieur à 20 %.
    - Si le niveau de la batterie est extrêmement faible et que vous essayez d’allumer l’appareil, un voyant clignote brièvement, puis s’éteint.
- Sur votre ordinateur hôte, ouvrez l’**Explorateurs de fichiers** et recherchez votre appareil HoloLens 2 sur le côté gauche sous **Ce PC**. Cliquez avec le bouton droit sur l’appareil, puis sélectionnez **Propriétés**. Une boîte de dialogue indique le niveau de charge de la batterie.

   ![Un écran Propriétés HoloLens 2 affiche le niveau de charge de la batterie.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Autres spécifications de charge

HoloLens 2 peut être chargé via des sources de [distribution d’alimentation USB](https://www.usb.org/usb-charger-pd) jusqu’à 27 watts. Si la source est en mesure de fournir au moins 10 watts, l’autonomie de l’HoloLens peut être étendue (parfois indéfiniment pour certaines charges de travail). 

> [!NOTE]
> L’utilisation d’un câble de charge USB-A vers USB-C limite la charge à 7,5 watts. L’autonomie reste étendue mais moindre par rapport à USB-C vers C.

Lorsque l’HoloLens est en mode de veille, 18 watts suffisent pour obtenir une charge maximale de la batterie interne. Lorsque l’HoloLens est en cours d’utilisation, la vitesse de charge peut-être réduite car l’appareil privilégie le fonctionnement par rapport à la charge.

> [!IMPORTANT]
> Il est recommandé de charger l’HoloLens 2 à un minimum de 5V/1,5A. Les chargeurs ne pouvant offrir un minimum de 5V/1,5A sont déconseillés. 

### <a name="external-battery-packs"></a>Batteries externes

Les batteries répondant aux spécifications ci-dessus peuvent être utilisées avec l’HoloLens 2. Notez cependant que certaines batteries USB-C rechargent et alimentent via le même port USB-C. Il est important que ces batteries implémentent [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) pour veiller à ce qu’elles chargent l’HoloLens plutôt que de s’en servir pour charger. 

### <a name="managing-heat"></a>Gestion de la chaleur

Comme tout appareil, la charge de l’HoloLens génère de la chaleur. Plus la charge est rapide, plus la quantité de chaleur générée est importante. En outre, le démarrage d’une charge à un niveau de batterie inférieur génère plus de chaleur que le démarrage d’une charge lorsque la batterie est quasiment pleine. Les clients qui ont besoin d’utiliser l’HoloLens pendant des périodes prolongées dans des environnements chauds peuvent recourir aux techniques suivantes :

- Il est possible de connecter l’HoloLens 2 à une source d’alimentation externe même lorsque la batterie interne est entièrement chargée.
- Lorsqu’une batterie externe est vide, l’HoloLens continue de fonctionner sur sa batterie interne.    
- Si la chaleur demeure un problème à l’issue des étapes ci-dessus, envisagez d’utiliser un chargeur ou une batterie qui limite la charge à 1,5A. Notez que cette option n’offre pas autant d’autonomie car la batterie interne se vide progressivement.

## <a name="troubleshooting"></a>Résolution des problèmes


### <a name="hololens-charges-external-battery"></a>L’HoloLens charge la batterie externe
Si l’HoloLens 2 charge une batterie externe au lieu de s’en servir pour se charger, cela signifie que la batterie n’implémente pas [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Utiliser une batterie plus récente permet de résoudre ce problème, mais vous pouvez également opter pour un câble USB-A vers USB-C. Gardez à l’esprit que cela limite la vitesse de charge à 7,5 watts.
