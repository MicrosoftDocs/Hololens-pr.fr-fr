---
title: Visibilité des paramètres de la page
description: Tenez-vous au courant de notre liste d'URI pris en charge pour PageVisibilityList et Guide sur les appareils de réalité mixte HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, accès affecté, kiosque, page paramètres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924330"
---
# <a name="page-settings-visibility"></a>Visibilité des paramètres de la page

L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application Paramètres. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées.

> [!NOTE]
> Cette fonctionnalité est uniquement disponible dans [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou ultérieure pour les appareils HoloLens 2. Vérifiez que les appareils pour lesquels vous envisagez d’utiliser cette fonctionnalité sont à jour.

L’exemple suivant illustre une stratégie autorisant l’accès uniquement aux pages « À propos de » et Bluetooth, avec l’URI « ms-settings : Network-WiFi » et « ms-settings : Bluetooth » respectivement :
- `showonly:network-wifi;network-proxy;bluetooth`

Pour le définir via un package de configuration :

1. Lorsque vous créez votre package dans le Concepteur de configuration Windows, accédez à **Stratégies > Paramètres > PageVisibilityList**.
1. Entrez la chaîne : **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportez votre package de configuration.
1. Appliquez le package à votre appareil.
Pour plus d’informations sur la création et l’application d’un package de configuration, consultez [cette page](hololens-provisioning.md).

Vous pouvez le faire via Intune à l’aide d’OMA-URI :

1. Créez une **stratégie personnalisée**.
1. Lors de la définition de l’OMA-URI, utilisez la chaîne : **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Lorsque vous sélectionnez le choix de prélèvement de données, sélectionnez : **Chaîne**
1. Lorsque vous entrez la valeur, utilisez : **`showonly:network-wifi;network-proxy;bluetooth`**
1. Veillez à affecter la configuration d’appareil personnalisée à un groupe auquel l’appareil est destiné.

Pour plus d’informations sur les groupes et configurations d’appareils Intune, consultez [Configuration GPM HoloLens](hololens-mdm-configure.md).

Quelle que soit la méthode choisie, votre appareil doit maintenant recevoir les modifications et les utilisateurs se voir présenter l’application Paramètres suivante.

![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

Pour configurer les pages de l’application Paramètres afin d’afficher ou de masquer votre propre sélection de pages, consultez les URL de paramètres disponibles sur HoloLens.

## <a name="settings-uris"></a>URI de paramètres

Les appareils HoloLens et Windows 10 présentent une sélection de pages différente dans l’application Paramètres. Sur cette page, vous trouverez uniquement les paramètres présents sur HoloLens.

### <a name="accounts"></a>Comptes
| Page Paramètres           | URI                                            |
|-------------------------|------------------------------------------------|
| Accès Professionnel ou Scolaire | `ms-settings:workplace`                         |
| Inscription Iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Options de connexion         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Applications
| Page Paramètres | URI                          |
|---------------|------------------------------|
| Applications et fonctionnalités<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Applications et fonctionnalités > Options avancées <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Applications et fonctionnalités > Cartes hors connexion <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Applications et fonctionnalités > Cartes hors connexion > Télécharger des cartes <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Appareils
| Page Paramètres | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Souris <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Confidentialité
| Page Paramètres            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informations sur le compte             | `ms-settings:privacy-accountinfo`              |
| Diagnostics d'application        | `ms-settings:privacy-appdiagnostics`              |
| Applications en arrière-plan        | `ms-settings:privacy-backgroundapps`              |
| Calendrier                 | `ms-settings:privacy-calendar`                    |
| Historique des appels             | `ms-settings:privacy-callhistory`                 |
| Appareil photo                   | `ms-settings:privacy-webcam`                      |
| Contacts                 | `ms-settings:privacy-contacts`                    |
| Diagnostics et commentaires | `ms-settings:privacy-feedback`                    |
| Documents                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| Système de fichiers              | `ms-settings:privacy-broadfilesystemaccess`       |
| Général <sup>2</sup>             | `ms-settings:privacy-general`       |
| Entrée manuscrite et personnalisation de la saisie <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Emplacement                 | `ms-settings:privacy-location`                    |
| Messagerie                | `ms-settings:privacy-messaging`                   |
| Microphone               | `ms-settings:privacy-microphone`                  |
| Mouvement <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Notifications            | `ms-settings:privacy-notifications`               |
| Autres appareils            | `ms-settings:privacy-customdevices`               |
| Images                 | `ms-settings:privacy-pictures`                    |
| Radios                   | `ms-settings:privacy-radios`                      |
| Bordures d’écran <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Captures d’écran et applications <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `ms-settings:privacy-speech`                      |
| Tâches                    | `ms-settings:privacy-tasks`                       |
| Mouvements des utilisateurs           | `ms-settings:privacy-backgroundspatialperception` |
| Vidéos                   | `ms-settings:privacy-videos`                      |
| Activation vocale       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Réseau et Internet
| Page Paramètres | URI                              |
|---------------|----------------------------------|
| Mode avion <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Système
| Page Paramètres      | URI                                |
|--------------------|------------------------------------|
| Batterie <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Batterie <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Couleurs             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologrammes <sup>2</sup>  |  `ms-settings:holograms`  |
| Étalonnage <sup>2</sup> |  `ms-settings:calibration` |
| Notifications et actions  | `ms-settings:notifications`          |
| Expériences partagées | `ms-settings:crossdevice` 
| Son <sup>2</sup>           | `ms-settings:sound`<br>|
| Son > Volume de l’application et préférence d’appareil <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Son > Gérer les périphériques audio <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Stockage            | `ms-settings:storagesense`           |
| Stockage > Configurer l’Assistant Stockage <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Heure et langue
| Page Paramètres | URI                                           |
|---------------|-----------------------------------------------|
| Date et heure <sup>2</sup> | `ms-settings:dateandtime`                  |
| Clavier <sup>2</sup> | `ms-settings:keyboard`                  |
| Langue <sup>2</sup> | `ms-settings:language`                  |
| Langue <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Langage      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Région        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Mise à jour et sécurité
| Page Paramètres                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Options avancées                    | `ms-settings:windowsupdate-options`         |
| Réinitialisation et récupération <sup>2</sup>      | `ms-settings:reset`         |
| Programme Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update - Recherche de mises à jour | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> - Pour les versions antérieures à Windows Holographic 21H1, les deux URI suivants ne vous permettent pas d’accéder aux pages **Options** ou **Options avancées** ; ils ne feront que bloquer ou afficher la page principale Windows Update.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> - Disponible dans Windows Holographic, version 21H1 ou ultérieure.


Pour obtenir la liste complète des URI des paramètres Windows 10, consultez la documentation relative aux [paramètres de lancement](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
