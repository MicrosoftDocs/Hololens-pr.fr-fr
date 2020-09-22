---
title: Accès global affecté
description: Guide pour l’utilisation des OMA-URI pour les Kiosques Accès affecté
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c2be1123d0e8a09d6955fb6e5da782daebc96bcf
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052623"
---
# Accès global affecté – Kiosque

Cette fonctionnalité configure l’appareil Hololens 2 pour le mode kiosque de plusieurs applications applicable au niveau du système, ne dispose d’aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se connectent à l’appareil. 

> [!NOTE]
> Pour l’instant, cette fonctionnalité est uniquement disponible dans les builds Windows Insider. Si vous souhaitez essayer cette fonctionnalité avant qu’elle ne soit généralement disponible dans les versions HoloLens, veuillez en savoir plus sur builds [Windows Insider](hololens-insider.md).
 
## Comment l’utiliser dans Intune? 

> [!NOTE]
> Notez les zones marquées par «<!-». Dans ces zones, vous devez apporter des modifications en fonction de vos préférences. 

1.  Créez un profil de configuration d’appareil OMA URI personnalisé comme suit et appliquez-le au groupe de périphériques HoloLens: ![accès global affecté OMA-URI dans Intune](images/global-assigned-access-omauri.png)

2.  Pour valeur, mettre à jour et coller le contenu suivant: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Comment utiliser ceci dans le Concepteur de configuration Windows? 
 
1.  Mettez à jour et enregistrez le blob XML mentionné ci-dessus en tant que fichier XML. 

2.  Suivez les étapes décrites dans [Utiliser un package d’approvisionnement pour configurer une borne d’application ou une station multi-applications](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), notamment la section «Prov. Pack, étape 2: ajouter le fichier XML de configuration Kiosque à un package d’approvisionnement» et faire référence au fichier XML enregistré à l’étape précédente. 

## Puis-je créer une configuration où le groupe général s’applique à tout le monde et une configuration distincte s’applique à un compte ou groupe AAD? 

Oui, consultez l’exemple d’objet blob XML ci-dessous. Le profil d’accès attribué global est appliqué sur Hololens lorsque celui-ci n’est pas trouvé pour l’utilisateur connecté. Par conséquent, il s’agit de la configuration par défaut en mode kiosque pour l’utilisateur connecté. Voici un exemple de blob XML à utiliser : 

> [!NOTE]
> N’oubliez pas les zones mises en surbrillance avec <!-nécessitent des modifications de votre part en fonction de vos préférences. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Exclusion de DeviceOwners dans le profil d’accès attribué global

Cette fonctionnalité permet à un utilisateur considéré comme «[Propriétaire d’appareil](security-adminless-os.md)» sur Hololens d’être exclu de l’accès attribué global. Pour tirer parti de cette fonctionnalité, dans le blob XML pour la configuration Kiosque multi-applications, vérifiez que les lignes mises en surbrillance sont ajoutées: 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
