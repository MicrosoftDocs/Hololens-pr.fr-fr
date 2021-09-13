---
title: Utilisation de 3D Viewer Beta sur HoloLens (1ère génération)
description: Décrit les types de fichiers et les fonctionnalités pris en charge par 3D Viewer Beta sur HoloLens (1ère génération), et comment utiliser et dépanner l’application.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034096"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Utilisation de 3D Viewer Beta sur HoloLens (1ère génération)

3D Viewer Beta vous permet de visualiser des modèles 3D sur HoloLens (1ère génération). Vous pouvez ouvrir et visualiser les fichiers .fbx  *pris en charge* depuis Microsoft Edge, OneDrive et d’autres applications.

>[!NOTE]
>Cet article concerne l’application immersive **3D Viewer Beta** d’Unity qui prend en charge les fichiers .fbx et est disponible seulement sur HoloLens (1ère génération). L’application **3D Viewer Beta** préinstallée sur HoloLens 2 prend en charge l’ouverture de modèles 3D .glb personnalisés dans la réalité mixte (pour plus d’informations, consultez [Vue d’ensemble des exigences en ressources](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)).

>[!IMPORTANT]
>Si la version 3D Viewer Beta reste disponible dans le Microsoft Store pour HoloLens (1ère génération), elle ne fait plus l’objet de développements actifs et n’est plus prise en charge.

Si vous avez des difficultés à ouvrir un modèle 3D dans 3D Viewer Beta ou si certaines fonctionnalités de votre modèle 3D ne sont pas prises en charge, consultez [Spécifications du contenu pris en charge](#supported-content-specifications) ci-dessous.

Pour créer ou optimiser des modèles 3D à utiliser avec 3D Viewer Beta, consultez [Optimisation des modèles 3D pour 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) ci-dessous.

Vous pouvez ouvrir un modèle 3D sur HoloLens de deux façons. Pour plus d’informations, consultez [Visualisation des fichiers FBX sur HoloLens](#viewing-fbx-files-on-hololens) ci-dessous.

Si vous rencontrez des problèmes après avoir lu ces rubriques, consultez [Résolution des problèmes](#troubleshooting) ci-dessous.

## <a name="supported-content-specifications"></a>Spécifications du contenu pris en charge

### <a name="file-format"></a>Format de fichier

- Format FBX
- Version maximale de FBX : 2015.1.0

### <a name="file-size"></a>Taille du fichier

- Minimum 5 Ko
- Maximum 500 Mo

### <a name="geometry"></a>Géométrie

- Modèles polygonaux uniquement. Pas de surfaces de subdivision ni de NURB
- Système de coordonnées des droitiers
- La découpe dans les matrices de transformation n’est pas prise en charge

### <a name="textures"></a>Textures

- Les mappages de texture doivent être incorporés dans le fichier FBX
- Formats d’image pris en charge
  - Images JPEG et PNG
  - Images BMP (Couleurs réelles RVB 24 bits)
  - Images TGA (Couleurs réelles RVB 24 bits et RGBQ 32 bits)
- Résolution maximale de la texture 2 048 x 2 048
- Au maximum un mappage de diffusion, un mappage normal et un cube de réflexion par maille
- Le canal alpha dans les textures de diffusion ignore les pixels si le pourcentage est inférieur à 50 %.

### <a name="animation"></a>Animation

- Animation d’échelle/rotation/translation sur des objets individuels
- Animation de squelette (simulée) avec application d’apparence
  - Maximum de 4 influences par sommet

### <a name="materials"></a>Matériaux

- Les matériaux Lambert et Phong sont pris en charge avec des paramètres ajustables
- Propriétés des matériaux prises en charge pour Lambert
  - Texture principale (RVB + test alpha)
  - Couleur diffuse (RVB)
  - Couleur ambiante (RVB)
- Propriétés des matériaux prises en charge pour Phong
  - Texture principale (RVB + test alpha)
  - Couleur diffuse (RVB)
  - Couleur ambiante (RVB)
  - Couleur spéculaire (RVB)
  - Brillance
  - Réflectivité
- Les matériaux personnalisés ne sont pas pris en charge
- Maximum d’un matériau par maille
- Maximum d’une couche de matériau
- Maximum de 8 matériaux par fichier

### <a name="file-and-model-limitations"></a>Limitations relatives aux fichiers et aux modèles

Il existe des limites strictes quant à la taille des fichiers ainsi qu’au nombre de modèles, de sommets et de mailles pouvant être ouverts simultanément dans 3D Viewer Beta :

- Taille de fichier maximale de 500 Mo par modèle
- Vertex : 600 000 combinés sur tous les modèles ouverts
- Mailles : 1 600 combinées sur tous les modèles ouverts
- Maximum de 40 modèles ouverts en même temps

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optimisation des modèles 3D pour 3D Viewer Beta

### <a name="special-considerations"></a>Considérations spéciales

- Évitez les matériaux noirs ou les zones noires dans les cartes de texture. Les hologrammes sont constitués de lumière, donc HoloLens affiche le noir (l’absence de lumière) comme transparent.
- Avant d’exporter au format FBX depuis votre outil de création, vérifiez que toute la géométrie est visible et déverrouillée, et qu’aucune couche contenant de la géométrie n’est désactivée ou modélisée. La visibilité n’est pas respectée.
- Évitez les très grands décalages de translation entre les nœuds (par exemple 100 000 unités). Ceci peut entraîner une instabilité du modèle quand il est déplacé, mis à l’échelle ou pivoté.

### <a name="performance-optimization"></a>Optimisation des performances

Gardez les performances à l’esprit lors de la création de contenu et vérifiez-les dans l’application 3D Viewer Beta sur HoloLens pendant le processus de création pour obtenir les meilleurs résultats. 3D Viewer Beta rend le contenu en temps réel et les performances dépendent capacités du matériel HoloLens.  

De nombreuses variables dans un modèle 3D peuvent affecter les performances. 3D Viewer Beta va afficher un avertissement au chargement s’il y a plus de 150 000 vertex ou plus de 400 mailles. Les animations peuvent avoir une incidence sur les performances des autres modèles ouverts. Il existe également des limites strictes quant au nombre total de modèles, de vertex et de mailles qui peuvent être ouverts simultanément dans 3D Viewer Beta (voir [Limitations relatives aux fichiers et aux modèles](#file-and-model-limitations)).  

Si le modèle 3D ne fonctionne pas correctement en raison de la complexité du modèle, vous pouvez envisager ceci :

- La réduction du nombre de polygones
- La réduction du nombre d’os dans les animations simulées
- Éviter l’auto-occlusion

Le rendu double face est pris en charge dans 3D Viewer Beta, bien qu’il soit désactivé par défaut pour des raisons de performances. Vous pouvez l’activer via le bouton **Double Sided** sur la page **Details**. Pour optimiser les performances, évitez d’avoir recours à un rendu double face dans votre contenu.

### <a name="validating-your-3d-model"></a>Validation de votre modèle 3D

Validez votre modèle en l’ouvrant dans 3D Viewer Beta sur HoloLens. Sélectionnez le bouton **Details** pour voir les caractéristiques de votre modèle et les avertissements relatifs au contenu non pris en charge (le cas échéant).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Rendu des modèles 3D aux dimensions réelles

Par défaut, 3D Viewer Beta affiche les modèles 3D à une taille et une position confortables par rapport à l’utilisateur. Cependant, si le rendu d’un modèle 3D avec des mesures réelles est important (par exemple lors de l’évaluation de modèles de meubles dans une pièce), le créateur de contenu peut placer un indicateur dans les métadonnées du fichier pour empêcher le redimensionnement de ce modèle à la fois par l’application et par l’utilisateur.

Pour empêcher la mise à l’échelle du modèle, vous pouvez ajouter un attribut personnalisé booléen nommé Microsoft_DisableScale à tout objet de la scène et le définir sur true. 3D Viewer Beta prendra alors en compte les informations de FbxSystemUnit intégrées dans le fichier FBX. L’échelle de 3D Viewer Beta est de 1 mètre par unité FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Visualisation des fichiers FBX sur HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Ouvrir un fichier FBX à partir de Microsoft Edge

Les fichiers FBX peuvent être ouverts directement à partir d’un site web en utilisant Microsoft Edge sur HoloLens.

1. Dans Microsoft Edge, accédez à la page web contenant le fichier FBX que vous voulez visualiser.
1. Sélectionnez le fichier pour le télécharger.
1. Une fois le téléchargement terminé, sélectionnez le bouton **Ouvrir** dans Microsoft Edge pour ouvrir le fichier dans 3D Viewer Beta.

Vous pouvez accéder au fichier téléchargé et le rouvrir plus tard en utilisant Téléchargements dans Microsoft Edge. Pour enregistrer un modèle 3D et en garantir l’accès continu, téléchargez le fichier sur votre PC et enregistrez-le dans votre compte OneDrive. Le fichier peut alors être ouvert à partir de l’application OneDrive sur HoloLens.

> [!NOTE]
> Certains sites web avec des modèles FBX téléchargeables les fournissent au format ZIP compressé. 3D Viewer Beta ne peut pas ouvrir directement les fichiers ZIP. Utilisez alors votre PC pour extraire le fichier FBX et l’enregistrer dans votre compte OneDrive. Le fichier peut alors être ouvert à partir de l’application OneDrive sur HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Ouvrir un fichier FBX à partir de OneDrive

Les fichiers FBX peuvent être ouverts à partir de OneDrive en utilisant l’application OneDrive sur HoloLens. Vérifiez que vous avez installé OneDrive en utilisant l’application Microsoft Store sur HoloLens et que vous avez déjà chargé le fichier FBX sur OneDrive sur votre PC.

Une fois dans OneDrive, les fichiers FBX peuvent être ouverts sur HoloLens en utilisant 3D Viewer Beta de l’une des deux façons suivantes :

- Lancez OneDrive sur HoloLens et sélectionnez le fichier FBX pour l’ouvrir dans 3D Viewer Beta.
- Lancez 3D Viewer Beta, cliquez dans l’air pour afficher la barre d’outils, puis sélectionnez **Open File**. OneDrive est alors lancé et vous permet de sélectionner un fichier FBX.

## <a name="troubleshooting"></a>Dépannage

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Je vois un avertissement quand j’ouvre un modèle 3D

Vous voyez un avertissement si vous tentez d’ouvrir un modèle 3D qui contient des fonctionnalités qui ne sont pas prises en charge par 3D Viewer Beta, ou si le modèle est trop complexe et que ses performances peuvent être affectées. 3D Viewer Beta va néanmoins charger le modèle 3D, mais les performances ou la fidélité visuelle peuvent être compromises.

Pour plus d’informations, consultez [Spécifications du contenu pris en charge](#supported-content-specifications) et [Optimisation des modèles 3D pour 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Je vois un avertissement et le modèle 3D ne se charge pas

Vous voyez un message d’erreur quand 3D Viewer Beta ne peut pas charger un modèle 3D en raison de sa complexité ou de la taille du fichier, ou si le fichier FBX est corrompu ou non valide. Un message d’erreur s’affiche également si vous avez atteint la limite du nombre total de modèles, de vertex ou de mailles qui peuvent être ouverts simultanément.  

Pour plus d’informations, consultez [Spécifications du contenu pris en charge](#supported-content-specifications) et [Limitations relatives aux fichiers et aux modèles](#file-and-model-limitations).

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Mon modèle 3D se charge, mais il ne s’affiche pas comme prévu

Si votre modèle 3D n’a pas l’aspect attendu dans 3D Viewer Beta, cliquez dans l’aire pour afficher la barre d’outils, puis sélectionnez **Details**. Les aspects du fichier qui ne sont pas pris en charge par 3D Viewer Beta seront mis en évidence sous forme d’avertissements.

Le problème le plus fréquent que vous pourriez rencontrer est l’absence de textures, probablement parce qu’elles ne sont pas incorporées dans le fichier FBX. Dans ce cas, le modèle apparaît en blanc. Vous pouvez résoudre ce problème dans le processus de création en exportant à partir de votre outil de création au format FBX avec l’option d’incorporation des textures sélectionnée.

Pour plus d’informations, consultez [Spécifications du contenu pris en charge](#supported-content-specifications) et [Optimisation des modèles 3D pour 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Je rencontre des baisses de performances lors de l’affichage de mon modèle 3D

Les performances de chargement et d’affichage d’un modèle 3D peuvent être affectées par la complexité du modèle, le nombre de modèles ouverts simultanément ou le nombre de modèles avec des animations actives.

Pour plus d’informations, consultez [Optimisation des modèles 3D pour 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) et [Limitations relatives aux fichiers et aux modèles](#file-and-model-limitations).

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Quand j’ouvre un fichier FBX sur HoloLens, il ne s’ouvre pas dans 3D Viewer Beta

3D Viewer Beta est automatiquement associée à l’extension de fichier .fbx quand elle est installée.

Si vous essayez d’ouvrir un fichier FBX et que vous voyez une boîte de dialogue qui vous dirige vers le Microsoft Store, cela signifie que vous n’avez actuellement pas d’application associée à l’extension de fichier .fbx sur HoloLens.

Vérifiez que 3D Viewer Beta est installée. Si elle n’est pas installée, téléchargez-la à partir du Microsoft Store sur HoloLens.

Si 3D Viewer Beta est déjà installé, lancez 3D Viewer Beta, puis réessayez d’ouvrir le fichier. Si le problème persiste, désinstallez et réinstallez 3D Viewer Beta. Ceci va réassocier l’extension de fichier .fbx à 3D Viewer Beta.

Si la tentative d’ouverture d’un fichier FBX ouvre une application autre que 3D Viewer Beta, c’est que cette application a probablement été installée après 3D Viewer Beta et a pris l’association avec l’extension de fichier .fbx. Si vous préférez que 3D Viewer Beta soit associé à l’extension de fichier .fbx, désinstallez et réinstallez 3D Viewer Beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Le bouton Open File dans 3D Viewer Beta ne lance pas d’application

Le bouton **Open File** ouvre l’application associée à la fonction de sélecteur de fichier sur HoloLens. Si OneDrive est installé, le bouton **Open File** doit lancer OneDrive. Cependant, s’il n’y a actuellement pas d’application associée à la fonction de sélecteur de fichier installée sur HoloLens, vous serez redirigé vers le Microsoft Store.

Si le bouton **Open File** démarre une application autre que OneDrive, il est possible que l’application ait été installée après OneDrive et qu’elle ait pris l’association avec la fonction de sélecteur de fichier. Si vous préférez que OneDrive se lance quand vous sélectionnez le bouton **Open File** dans 3D Viewer Beta, désinstallez et réinstallez OneDrive.

Si le bouton **Open File** n’est pas actif, il est possible que vous ayez atteint la limite des modèles pouvant être ouverts en même temps dans 3D Viewer Beta. Si vous avez 40 modèles ouverts dans 3D Viewer Beta, vous devrez en fermer certains avant de pouvoir ouvrir des modèles supplémentaires.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Forums de support](http://forums.hololens.com/categories/3d-viewer-beta) : à des fins d’archive uniquement. Ce forum n’est plus actif.
- [Mentions tierces](https://www.microsoft.com/{lang-locale}/legal/products)
