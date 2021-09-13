---
title: informations de référence sur les kiosques HoloLens
description: informations et exemples pour les bornes sur des appareils HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032564"
---
# <a name="hololens-kiosk-reference-information"></a>Informations de référence sur le kiosque HoloLens

cette page contient des informations utiles sur la configuration du mode plein écran de votre appareil HoloLens. Ces références incluent AUMIDs pour les applications de boîte de réception et recherchent les vôtres, ainsi que plusieurs exemples XML pour le mode plein écran, qui ne sont que quelques modifications qui ne peuvent pas être prêtes à être utilisées dans différents scénarios. Pour plus d’informations sur la configuration d’une borne, consultez la [page Configurer une borne.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens ID de modèle d’utilisateur d’application (AUMIDs)  

Pour obtenir des informations générales sur la façon de choisir des applications Kiosk, consultez [instructions pour choisir une application pour l’accès affecté (mode plein écran)](/windows/configuration/guidelines-for-assigned-access-app).

Si vous utilisez un système de gestion des appareils mobiles (MDM) ou un package d’approvisionnement pour configurer le mode plein écran, vous utilisez le [fournisseur de services de configuration (CSP) AssignedAccess](/windows/client-management/mdm/assignedaccess-csp) pour spécifier les applications. Le CSP utilise des [ID de modèle d’utilisateur d’application (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) pour identifier les applications. Le tableau suivant répertorie les AUMIDs de certaines applications intégrées que vous pouvez utiliser dans une borne multi-application.

<a id="aumids"></a>

|Nom de l’application |AUMID |
| --- | --- |
|Visionneuse 3D |Microsoft. Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendrier |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. les. Calendar |
|Appareil photo<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Application 8wekyb3d8bbwe Microsoft. 549981C3F5F10 \_ \! |
|sélecteur d’appareils sur HoloLens (1ère génération) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Sélecteur d’appareils sur HoloLens 2 |Librairie. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. repères \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub de commentaires &nbsp; |Application 8wekyb3d8bbwe Microsoft. WindowsFeedbackHub \_ \! |
|Explorateur de fichiers |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Messagerie |microsoft.windowscommunicationsapps_8wekyb3d8bbwe ! Microsoft. les. mail |
|Ancien Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Nouveau Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe ! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|Films et TV |Microsoft. ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |application 8wekyb3d8bbwe Microsoft. microsoftskydrive \_ \! |
|Photo |Librairie. Windows. Photos \_ \!application 8wekyb3d8bbwe |
|ancien Paramètres |HolographicSystemSettings_cw5n1h2txyewy ! Lancement |
|nouvelle Paramètres |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy ! Lancement |
|Conseils |HoloLensTips 8wekyb3d8bbwe Microsoft. HoloLensTips \_ \! |

> <sup>1</sup> pour activer la capture de photos ou de vidéos, vous devez activer l’application d’appareil photo en tant qu’application Kiosk.  
> <sup>2</sup> lorsque vous activez l’application d’appareil photo, tenez compte des conditions suivantes :
> - Le menu actions rapides comprend les boutons photo et vidéo.
> - vous devez également activer une application (par exemple, Photos, Mail ou OneDrive) qui peut interagir avec les images ou les récupérer.  
>  
> <sup>3</sup> même si vous n’activez pas Cortana comme application kiosk, les commandes vocales intégrées sont activées. Toutefois, les commandes associées aux fonctionnalités désactivées n’ont aucun effet.  
> <sup>4</sup> vous ne pouvez pas activer Miracast directement. Pour activer Miracast en tant qu’application Kiosk, activez l’application caméra et l’application sélecteur d’appareil.

En outre, la page d’hébergement de la réalité mixte ne peut pas être définie en tant qu’application Kiosk.

Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Exemples de code Kiosk XML

1. [Profil d’accès global affecté à plusieurs applications](#multiple-app-global-assigned-access-profile)
1. [Un profil d’accès global affecté à plusieurs applications, en excluant les propriétaires d’appareils](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Profil d’accès à plusieurs applications affecté pour un compte local ou un compte d’utilisateur AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Plusieurs profils d’accès attribués aux applications pour deux utilisateurs AAD ou plus](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Profil d’accès à plusieurs applications affecté pour un groupe AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Profil d’accès à plusieurs applications affecté pour deux groupes AAD ou plus](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Profil d’accès à plusieurs applications affecté pour un compte AAD et un groupe AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Profil d’accès à plusieurs applications affecté pour les visiteurs](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Remplacez les actions TODO par vos besoins.

### <a name="multiple-app-global-assigned-access-profile"></a>Profil d’accès global affecté à plusieurs applications

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Un profil d’accès global affecté à plusieurs applications, en excluant les propriétaires d’appareils

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Profil d’accès à plusieurs applications affecté pour un compte local ou un compte d’utilisateur AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Plusieurs profils d’accès attribués aux applications pour deux utilisateurs AAD ou plus

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Profil d’accès à plusieurs applications affecté pour un groupe AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Profil d’accès à plusieurs applications affecté pour deux groupes AAD ou plus

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Profil d’accès à plusieurs applications affecté pour un compte AAD et un groupe AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Profil d’accès à plusieurs applications affecté pour les visiteurs

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Retour à la liste](#kiosk-xml-code-samples) <br>
Revenir aux [scénarios pris en charge pour le mode plein écran basé sur le type d’identité](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
