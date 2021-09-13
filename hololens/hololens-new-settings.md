---
title: Présentation de la nouvelle application Paramètres
description: Découvrez-en plus sur la nouvelle application Paramètres.
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, paramètres, sélecteur d'application, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034385"
---
# <a name="new-settings-app"></a>Nouvelle application Paramètres

Une nouvelle version de l'application Paramètres est introduite avec [Windows Holographic version 21H1](hololens-release-notes.md#windows-holographic-version-21h1). La nouvelle application Paramètres comprend de nouvelles fonctionnalités et des paramètres étendus pour HoloLens 2 dans les domaines suivants : Son, Alimentation et veille, Réseau et Internet, Applications, Comptes, Options d'ergonomie, etc.

> [!NOTE]
> Comme la nouvelle application Paramètres est distincte de l'ancienne, toutes les fenêtres Paramètres précédemment placées dans votre environnement seront supprimées lors de la mise à jour.

![Nouvelle page d’accueil de l’application Paramètres.](images/new-settings-app.png)

**Nouvelles fonctionnalités et nouveaux paramètres**
- Recherche de paramètres : recherchez des paramètres à partir de la page d'accueil de l'application Paramètres en utilisant des mots-clés ou le nom du paramètre.
- Système > [Étalonnage des couleurs](hololens2-display.md#how-to-use-display-color-calibration)
    - Sélectionnez un autre profil de couleurs pour votre affichage HoloLens 2.
- Système > Son :
  - Périphériques audio d'entrée et de sortie : choisissez indépendamment vos périphériques audio d'entrée et de sortie (par exemple, écoutez de l'audio via un casque Bluetooth et utilisez un microphone USB-C pour l'entrée audio).
    > [!NOTE]
    > Les microphones Bluetooth ne sont pas pris en charge par l'HoloLens 2.
  - Volume des applications : réglez indépendamment le volume de chaque application. Consultez [Contrôle du volume par application](holographic-home.md#per-app-volume-control).
- Système > Alimentation et veille : choisissez quand l'appareil doit se mettre en veille après une période d'inactivité.
- Système > Batterie : activez manuellement le mode Économiseur de batterie ou définissez un seuil de batterie à partir duquel le mode Économiseur de batterie doit automatiquement s'activer.
- Périphériques > USB : vous pouvez désactiver les connexions USB par défaut.
- Réseau et Internet
  - Les adaptateurs Ethernet USB-C apparaissent désormais dans Réseau et Internet.
  - Les paramètres des adaptateurs Ethernet USB-C sont désormais disponibles, adresse IP comprise.
  - Vous pouvez désormais activer le mode Avion sur l'HoloLens 2.
- Applications : vous pouvez réinitialiser les applications par défaut utilisées pour les types de fichiers et de liens. Pour plus d'informations, consultez [Sélecteur d'application par défaut](holographic-home.md#default-app-picker).
- Comptes > Autres utilisateurs : les propriétaires d'appareils peuvent ajouter des utilisateurs, promouvoir des utilisateurs standard au statut de propriétaires d'appareils, rétrograder des propriétaires d'appareils au statut d'utilisateurs standard et supprimer des utilisateurs.
- Options d'ergonomie : modifiez la taille du texte et certains effets visuels.

**Problèmes connus**
- Les fenêtres Paramètres précédemment placées seront supprimées (voir la note ci-dessus).
- Vous ne pouvez plus renommer votre appareil avec l'application Paramètres. Les administrateurs informatiques peuvent renommer les appareils à l'aide du modèle de nom d'appareil [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) ou du nœud GPM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La page Ethernet affiche en permanence un périphérique Ethernet virtuel (« UsbNcm »).
- L'utilisation de la batterie pour le nouveau navigateur Microsoft Edge peut ne pas être précise, en raison de sa nature d'application de bureau Win32 prise en charge par une couche d'adaptation UWP (aucun correctif prévu dans l'immédiat).

