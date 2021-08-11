---
title: Accès global affecté
description: Démarrez avec notre guide sur l’utilisation d’OMA-URI pour les kiosques Accès global affecté avec Intune et le concepteur de configuration Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, accès affecté, kiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664042"
---
# <a name="global-assigned-access--kiosk"></a>Accès global affecté - Kiosque

Cette fonctionnalité configure l’appareil HoloLens 2 pour le mode kiosque multi-application, qui est applicable au niveau du système, n’a aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se connectent à l’appareil.

> [!NOTE]
> Pour l’instant, cette fonctionnalité est disponible seulement dans les builds Windows Insider. Si vous voulez essayer cette fonctionnalité avant qu’elle ne soit en disponibilité générale dans les versions d’HoloLens, découvrez plus d’informations sur les builds [Windows Insider](hololens-insider.md).

## <a name="how-to-use-global-assigned-access-in-intune"></a>Comment utiliser l’accès global affecté dans Intune ?

> [!NOTE]
> Notez les zones marquées par « <!- ». Dans ces zones, vous devez apporter des modifications en fonction de vos préférences.

1. Créez un profil de configuration d’appareil OMA URI personnalisé comme suit et appliquez-le au groupe d’appareils HoloLens :

    Valeur de l’URI : ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Accès global affecté OMA-URI dans Intune](images/global-assigned-access-omauri.png)

2. Pour la valeur, mettez à jour et collez le contenu suivant :

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Comment utiliser l’accès global affecté dans le concepteur de configuration Windows ?

1. Mettez à jour et enregistrez l’objet blob XML mentionné ci-dessus en tant que fichier XML. 

2. Suivez les étapes décrites dans [Utiliser un package de provisionnement pour configurer une seule application ou un kiosque multi-application](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en particulier la section « Package de provisionnement, Étape 2 - Ajouter le fichier XML de configuration de kiosque à un package de provisionnement » et reportez-vous au fichier XML enregistré à l’étape précédente.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Puis-je créer une configuration où « global » s’applique à tout le monde et où une configuration distincte s’applique à un compte ou un groupe Azure AD ? 

Oui, reportez-vous à l’exemple d’objet blob XML ci-dessous. Le profil d’accès global affecté est appliqué sur HoloLens quand un profil spécifique n’est pas trouvé pour l’utilisateur connecté : il s’agit donc de la configuration en mode kiosque par défaut pour l’utilisateur connecté.
Voici un exemple d’objet blob XML à utiliser :

> [!NOTE]
> Tenez compte des zones en surbrillance marquées avec `<!-`. Dans ces zones, vous devez apporter des modifications en fonction de vos préférences.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Exclusion des propriétaires d’appareil dans le profil d’accès global affecté

Cette fonctionnalité permet à un utilisateur considéré comme « [Propriétaire d’appareil](security-adminless-os.md) » sur HoloLens d’être exclu de l’accès global affecté. Pour tirer parti de cette fonctionnalité, dans l’objet blob XML pour la configuration de kiosque multi-application, vérifiez que les lignes mises en surbrillance sont ajoutées :

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Autres exemples d’accès global affecté

Il s’agit d’un exemple de kiosque d’accès global affecté qui, quand l’utilisateur se connecte, lui permet de disposer d’un kiosque multi-application avec l’application Paramètres, le hub de feedback et Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Cet exemple est un kiosque d’accès global affecté qui exclut le propriétaire de l’appareil ; quand un autre utilisateur Azure AD se connecte, il dispose d’un kiosque multi-application avec l’application Paramètres, le hub de feedback et Microsoft Edge. Ce kiosque inclut également une configuration de kiosque secondaire pour un compte de visiteur, auquel tout le monde peut se connecter sur l’écran de verrouillage. Quand un utilisateur se connecte au compte visiteur, il dispose d’un kiosque multi-application qui a seulement l’application Hub de feedback.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
