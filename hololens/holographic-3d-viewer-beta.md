---
title: Utilisation du Viewer 3D Beta sur HoloLens (1ère génération)
description: Décrit les types de fichiers et les fonctionnalités que 3D Viewer Beta sur HoloLens (1ère génération) supporte, et comment utiliser et dépanner l'application.
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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016285"
---
# Utilisation du Viewer 3D Beta sur HoloLens (1ère génération)

3D Viewer Beta vous permet de visualiser des modèles 3D sur HoloLens (1ère génération). Vous pouvez ouvrir et visualiser les fichiers .fbx *pris en charge* pris en charge par Microsoft Edge, OneDrive et d'autres applications.

>[!NOTE]
>Cet article s'applique à l'application immersive Unité **3D Viewer Beta**qui prend en charge les fichiers .fbx et n'est disponible que sur HoloLens (1ère génération). L’application préinstallée **Visionneuse 3D** sur HoloLens 2 permet d'ouvrir des modèles 3D .glb personnalisés dans la famille de la réalité mixte (voir[l'aperçu des exigences en matière d'actifs](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) pour plus d’informations.

>[!IMPORTANT]
>Si la version bêta de 3D Viewer reste disponible dans le Microsoft Store pour HoloLens (1ère génération), elle n'est plus en développement actif et n'est plus prise en charge.

Si vous avez des difficultés à ouvrir un modèle 3D dans la version bêta de 3D Viewer, ou si certaines caractéristiques de votre modèle 3D ne sont pas prises en charge, voir [ les spécifications du contenu pris en charge](#supported-content-specifications) ci-dessous.

Pour construire ou optimiser des modèles 3D à utiliser avec le 3D Viewer Beta, voir [ ci-dessous Optimisation des modèles 3D pour le 3D Viewer Beta.](#optimizing-3d-models-for-3d-viewer-beta)

Vous pouvez ouvrir un modèle 3D sur HoloLens de deux manières. Pour en savoir plus [la section Visualisation des fichiers FBX sur HoloLens](#viewing-fbx-files-on-hololens) ci-dessous.

Si vous avez des difficultés après avoir lu ces sujets, voir [la section Dépannage](#troubleshooting)ci-dessous.

## Spécifications de contenu prises en charge

### Format de fichier

- Format FBX
- FBX version maximale 2015.1.0

### Taille du fichier

- Minimum 5 Ko
- Maximum 500 Mo

### Géométrie

- Modèles polygonales uniquement. Aucune surface de subdivision ni NURBs
- Système de coordonnées des droitiers
- La cisaillement dans les matrices de transformation n’est pas prise en charge

### Textures

- Les cartes de texture doivent être intégrées dans le fichier FBX
- Types d’images pris en charge
  - Images JPEG et PNG
  - Images BMP (24 bits RVB vraie couleur)
  - Images TGA (24 bits RVB et 32 bits RGBQ vraie couleur)
- Résolution maximale de la texture 2048 x 2048
- Maximum d'une carte diffuse, d'une carte normale et d'un cube de réflexion par maille
- Le canal alpha dans les textures diffuses entraîne le rejet des pixels si leur pourcentage est inférieur à 50%.

### Animation

- Animation d'échelle / rotation / traduction sur des objets individuels
- Animation squelettique (truquée) avec écorchage
  - Maximum de 4 influences par sommet

### Matériaux:

- Les matériaux Lambert et Phong sont pris en charge avec des paramètres réglables
- Propriétés de matériel prises en charge pour Lambert
  - Texture principale (RVB + test alpha)
  - Couleur diffuse (RVB)
  - Couleur ambiante (RVB)
- Propriétés de matériel prises en charge pour Phong
  - Texture principale (RVB + test alpha)
  - Couleur diffuse (RVB)
  - Couleur ambiante (RVB)
  - Couleur spéculaire (RVB)
  - Brillance
  - Réflectivité
- Les matériaux personnalisés ne sont pas pris en charge
- Maximum d’un matériau par maillage
- Maximum d'une couche de matériau
- Maximum de 8 matériaux par fichier

### Limitations relatives aux fichiers et aux modèles

Il existe des limites strictes quant à la taille des fichiers, ainsi qu'au nombre de modèles, de sommets et de maillages pouvant être ouverts simultanément dans la version bêta de 3D Viewer :

- taille de fichier maximale de 500 Mo par modèle
- Sommets: 600 000 combinés sur tous les modèles ouverts
- Maillages: 1 600 combinés sur tous les modèles ouverts
- Maximum de 40 modèles ouverts en même temps

## Optimisation des modèles 3D pour la version bêta de 3D Viewer

### Considérations pratiques

- Évitez les matériaux noirs ou les zones noires dans les cartes de texture. Les hologrammes sont faits de lumière, donc l'HoloLens affiche le noir (l’absence de lumière) comme transparent.
- Avant d'exporter vers FBX depuis votre outil de création, assurez-vous que toute la géométrie est visible et déverrouillée et qu'aucune couche contenant de la géométrie n'est désactivée ou modélisée. La visibilité n’est pas respectée.
- Évitez les très grands décalages de traduction entre les nœuds (par exemple, 100 000 unités). Cela peut entraîner une instabilité du modèle lorsqu'il est déplacé, mis à l'échelle ou tourné.

### Optimisation des performances

Gardez les performances à l'esprit lors de la création de contenu et validez dans l'application 3D Viewer Beta sur HoloLens pendant le processus de création pour obtenir les meilleurs résultats. La version bêta de 3D Viewer rend le contenu en temps réel et les performances sont soumises aux capacités du matériel HoloLens.  

De nombreuses variables dans un modèle 3D peuvent affecter les performances. La version bêta de 3D Viewer affichera un avertissement au chargement s'il y a plus de 150 000 sommets ou plus de 400 mailles. Les animations peuvent avoir une incidence sur les performances des autres modèles ouverts. Il existe également des limites strictes quant au nombre total de modèles, de sommets et de maillages qui peuvent être ouverts simultanément dans le Viewer 3D Beta (voir [Limitations des fichiers et des modèles](#file-and-model-limitations)).  

Si le modèle 3D ne fonctionne pas correctement en raison de la complexité du modèle, vous devez prendre en considération :

- La réduction du nombre de polygones
- La réduction du nombre d’os dans les animations truquées
- Éviter l’occlusion automatique

Le rendu double face est pris en charge dans la version bêta de 3D Viewer, bien qu'il soit désactivé par défaut pour des raisons de performances. Pour ce faire, vous pouvez utiliser le bouton **recto-verso** sur la page **Détails**. Pour optimiser les performances, évitez d'avoir recours à un rendu recto verso dans votre contenu.

### Validation de votre modèle 3D

Validez votre modèle en l'ouvrant en 3D Viewer Beta sur HoloLens. Sélectionnez le bouton **Détails** pour afficher les caractéristiques de votre modèle et les avertissements relatifs au contenu non pris en charge (le cas échéant).

### Affichage des modèles 3D aux dimensions réelles

Par défaut, 3D Viewer Beta affiche les modèles 3D à une taille et une position confortables par rapport à l'utilisateur. Cependant, si le rendu d'un modèle 3D avec des mesures réelles est important (par exemple, lors de l'évaluation de modèles de meubles dans une pièce), le créateur de contenu peut placer un drapeau dans les métadonnées du fichier pour empêcher le redimensionnement de ce modèle par l'application et l'utilisateur.

Pour empêcher la mise à l’échelle du modèle, vous pouvez ajouter un attribut personnalisé booléen à tout objet dans la scène nommée Microsoft_DisableScale et le régler à vrai. La version bêta de 3D Viewer respectera alors les informations FbxSystemUnit intégrées dans le fichier FBX. L'échelle du Viewer 3D Beta est de 1 mètre par unité FBX.

## Visualisation des fichiers FBX sur HoloLens

### Ouvrir un fichier FBX à partir de Microsoft Edge

Les fichiers FBX peuvent être ouverts directement à partir d'un site web en utilisant Microsoft Edge sur HoloLens.

1. Dans Microsoft Edge, accédez à la page Web contenant le fichier FBX que vous voulez afficher.
1. Sélectionnez le fichier pour le télécharger.
1. Lorsque le téléchargement est terminé, sélectionnez le bouton **Ouvrir ** dans Microsoft Edge pour ouvrir le fichier dans la version bêta de 3D Viewer.

Vous pouvez accéder aux fichiers téléchargés et les ouvrir à nouveau plus tard en utilisant les téléchargements dans Microsoft Edge. Pour enregistrer un modèle 3D et garantir l’accès continu, téléchargez le fichier sur votre PC et enregistrez-le dans votre compte OneDrive. Le fichier peut ensuite être ouvert à partir de l’application OneDrive sur HoloLens.

> [!NOTE]
> Certains sites Web disposant de modèles FBX téléchargeables les proposent au format ZIP compressé. La version bêta de 3D Viewer ne peut pas ouvrir directement les fichiers ZIP. Utilisez plutôt votre PC pour extraire le fichier FBX et l’enregistrer dans votre compte OneDrive. Le fichier peut ensuite être ouvert à partir de l’application OneDrive sur HoloLens.

### Ouvrir un fichier FBX à partir de OneDrive

Les fichiers FBX peuvent être ouverts à partir de OneDrive en utilisant l'application OneDrive sur HoloLens. Assurez-vous d’avoir installé OneDrive à l’aide de l’application Microsoft Store sur HoloLens et que vous avez déjà chargé le fichier FBX sur OneDrive sur votre PC.

Une fois dans OneDrive, les fichiers FBX peuvent être ouverts sur HoloLens à l'aide de 3D Viewer Beta de l'une des deux façons suivantes

- Lancez OneDrive sur HoloLens et sélectionnez le fichier FBX pour l'ouvrir dans la version bêta de 3D Viewer.
- Lancez la version bêta du Viewer 3D, appuyez sur le bouton pour afficher la barre d'outils, puis sélectionnez**Ouvrir un fichier**. OneDrive sera lancé, vous permettant de sélectionner un fichier FBX.

## Résolution des problèmes

### Un avertissement s’affiche lorsque j’ouvre un modèle 3D

Vous verrez un avertissement si vous tentez d'ouvrir un modèle 3D qui contient des fonctionnalités qui ne sont pas prises en charge par la version bêta de 3D Viewer, ou si le modèle est trop complexe et que ses performances peuvent être affectées. La version bêta de 3D Viewer chargera toujours le modèle 3D, mais les performances ou la fidélité visuelle peuvent être compromises.

Pour plus d'informations, voir [ Spécifications du contenu pris en charge ](#supported-content-specifications) et [ Optimisation des modèles 3D pour le Viewer 3D Beta ](#optimizing-3d-models-for-3d-viewer-beta).

### Un avertissement s’affiche et le modèle 3D ne se charge pas

Vous verrez un message d'erreur lorsque 3D Viewer Beta ne peut pas charger un modèle 3D en raison de sa complexité ou de la taille du fichier, ou si le fichier FBX est corrompu ou non valide. Un message d’erreur s’affiche également si vous avez atteint la limite du nombre total de modèles, de sommets ou de maillages qui peuvent être ouverts simultanément.  

Pour plus d’informations, voir [Spécifications de contenu prises en charge](#supported-content-specifications) et [Limitations relatives aux fichiers et aux modèles](#file-and-model-limitations).

### Mon modèle 3D se charge, mais il ne s’affiche pas comme prévu

Si votre modèle 3D n'a pas l'aspect attendu dans la version bêta de 3D Viewer, appuyez sur pour afficher la barre d'outils, puis sélectionnez **Détails**. Les aspects du fichier qui ne sont pas pris en charge par la version bêta de 3D Viewer seront mis en évidence sous forme d'avertissements.

Le problème le plus fréquent que vous pourriez rencontrer est l'absence de textures, probablement parce qu'elles ne sont pas intégrées dans le fichier FBX. Dans ce cas, le modèle s’affiche en blanc. Vous pouvez résoudre ce problème dans le processus de création en exportant à partir de votre outil de création vers FBX avec l'option d'incorporation de textures sélectionnée.

Pour plus d'informations, voir [ Spécifications du contenu pris en charge ](#supported-content-specifications) et [ Optimisation des modèles 3D pour le Viewer 3D Beta ](#optimizing-3d-models-for-3d-viewer-beta).

### Je rencontre des baisses de performances lors de l’affichage de mon modèle 3D

Les performances de chargement et d’affichage d’un modèle 3D peuvent être affectées par la complexité du modèle, le nombre de modèles ouverts simultanément ou le nombre de modèles avec animations actives.

Pour plus d'informations, voir [Optimisation des modèles 3D pour la version bêta de 3D Viewer ](#optimizing-3d-models-for-3d-viewer-beta) et [Limitations des fichiers et des modèles](#file-and-model-limitations).

### Lorsque j'ouvre un fichier FBX sur HoloLens, il ne s'ouvre pas dans la version bêta de 3D Viewer

La version bêta de 3D Viewer est automatiquement associée à l'extension de fichier .fbx lorsqu'elle est installée.

Si vous essayez d'ouvrir un fichier FBX et que vous voyez une boîte de dialogue qui vous dirige vers le Microsoft Store, vous n'avez actuellement pas d'application associée à l'extension de fichier .fbx sur HoloLens.

Vérifiez que la version bêta de 3D Viewer est installée. Si elle n’est pas installée, téléchargez-la à partir du Microsoft Store sur HoloLens.

Si 3D Viewer Beta est déjà installé, lancez 3D Viewer Beta, puis essayez d'ouvrir le fichier à nouveau. Si le problème persiste, désinstallez et réinstallez la version bêta de 3D Viewer. Cela permettra de réassocier l'extension de fichier .fbx à 3D Viewer Beta.

Si la tentative d'ouverture d'un fichier FBX ouvre une application autre que 3D Viewer Beta, cette application a probablement été installée après 3D Viewer Beta et a pris en charge l'association avec l'extension de fichier .fbx. Si vous préférez que 3D Viewer Beta soit associé à l'extension de fichier .fbx, désinstallez et réinstallez 3D Viewer Beta.

### Le bouton Ouvrir un fichier dans la version bêta de 3D Viewer ne lance pas d'application

Le bouton **Ouvrir le fichier** ouvre l’application associée à la fonction Sélecteur de fichier sur HoloLens. Si OneDrive est installé, le bouton **Ouvrir le fichier** doit lancer OneDrive. Toutefois, s’il n’existe actuellement aucune application associée à la fonction Sélecteur de fichier installée sur HoloLens, vous serez redirigé vers Microsoft Store.

Si le bouton **Ouvrir le fichier** démarre une application autre que OneDrive, il est possible que l’application ait été installée après OneDrive et qu’elle ait pris en charge l’association avec la fonction Sélecteur de fichier. Si vous préférez que OneDrive se lance en sélectionnant le bouton**Ouvrir un fichier ** dans la version bêta de 3D Viewer, désinstallez et réinstallez OneDrive.

Si le bouton**Ouvrir un fichier** n'est pas actif, il est possible que vous ayez atteint la limite des modèles pouvant être ouverts en une seule fois dans la version bêta de 3D Viewer. Si vous avez 40 modèles ouverts dans la version bêta de 3D Viewer, vous devrez en fermer certains avant de pouvoir ouvrir des modèles supplémentaires.

## Ressources supplémentaires

- [ Forums de soutien](http://forums.hololens.com/categories/3d-viewer-beta) - A des fins d'archivage uniquement. Ce forum n'est plus actif.
- [Notifications tierces](https://www.microsoft.com/{lang-locale}/legal/products)
