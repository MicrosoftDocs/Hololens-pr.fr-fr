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
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253201"
---
# Accès global affecté – Kiosque

Cette fonctionnalité configure l’appareil Hololens 2 pour le mode kiosque de plusieurs applications applicable au niveau du système, ne dispose d’aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se connectent à l’appareil.

> [!NOTE]
> Pour l’instant, cette fonctionnalité est uniquement disponible dans les builds Windows Insider. Si vous souhaitez essayer cette fonctionnalité avant qu’elle ne soit généralement disponible dans les versions HoloLens, veuillez en savoir plus sur builds [Windows Insider](hololens-insider.md).

## Comment utiliser l’accès global affecté dans Intune?

> [!NOTE]
> Notez les zones marquées par «<!-». Dans ces zones, vous devez apporter des modifications en fonction de vos préférences.

1. Créez un profil de configuration d’appareil OMA URI personnalisé comme suit et appliquez-le au groupe d’appareils HoloLens:

    Valeur de l’URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Accès affecté global OMA-URI dans Intune](images/global-assigned-access-omauri.png)

2. Pour valeur, mettre à jour et coller le contenu suivant:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Comment utiliser l’accès global accordé dans le concepteur de configuration Windows?

1. Mettez à jour et enregistrez le blob XML mentionné ci-dessus en tant que fichier XML. 

2. Suivez les étapes décrites dans [Utiliser un package d’approvisionnement pour configurer une borne d’application ou une station multi-applications](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), notamment la section «Prov. Pack, étape 2: ajouter le fichier XML de configuration Kiosque à un package d’approvisionnement» et faire référence au fichier XML enregistré à l’étape précédente.

## Puis-je créer une configuration où le groupe général s’applique à tout le monde et une configuration distincte s’applique à un compte ou groupe Azure AD? 

Oui, reportez-vous à l’exemple de BLOB XML ci-dessous. Le profil d’accès affecté global est appliqué sur Hololens lorsque celui-ci n’est pas trouvé pour l’utilisateur connecté. Par conséquent, il s’agit de la configuration par défaut en mode kiosque pour l’utilisateur connecté.
Voici un exemple de blob XML à utiliser :

> [!NOTE]
> Notez les zones mises en surbrillance avec `<!-`. Dans ces zones, vous devez apporter des modifications en fonction de vos préférences.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Exclusion de DeviceOwners dans le profil d’accès affecté global

Cette fonctionnalité permet à un utilisateur considéré comme «[Propriétaire d’appareil](security-adminless-os.md)» sur Hololens d’être exclu de l’accès affecté global. Pour tirer parti de cette fonctionnalité, dans le blob XML pour la configuration Kiosque multi-applications, vérifiez que les lignes mises en surbrillance sont ajoutées:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## Autres exemples d’accès affectés globaux

Il s’agit d’un exemple d’accès global affecté qui, lorsque l’utilisateur se connecte, qu’il dispose d’une borne multi-application avec l’application paramètres, le hub de commentaires et Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Cet exemple est un kiosque d’accès global affecté qui exclut le propriétaire de l’appareil, quand un autre utilisateur d’Azure AD se connecte, il dispose d’une borne multi-application avec l’application paramètres, le hub de commentaires et Microsoft Edge. Ce kiosque inclut également une configuration de kiosque secondaire pour un compte visiteur, auquel tout le monde peut se connecter sur l’écran de verrouillage. Lorsqu’un utilisateur se connecte au compte visiteur, il dispose d’une borne multi-applications qui contient uniquement l’application Hub de commentaires.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
