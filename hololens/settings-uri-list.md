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
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190427"
---
# <a name="page-settings-visibility"></a>Visibilité des paramètres de la page

L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie Settings/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application Paramètres. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées.

> [!NOTE]
> Cette fonctionnalité est uniquement disponible dans [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou ultérieure pour les appareils HoloLens 2. Vérifiez que les appareils pour lesquels vous envisagez d’utiliser cette fonctionnalité sont à jour.


## <a name="examples"></a>Exemples
Les pages sont identifiées par une version abrégée de leurs URI publiées, c’est-à-dire l’URI sans le préfixe « ms-settings: ».

L’exemple suivant illustre une stratégie autorisant seulement l’accès aux pages « À propos de » et « Bluetooth », qui ont respectivement l’URI « network-wifi » et « bluetooth » :
- `showonly:network-wifi;network-proxy;bluetooth`

L’exemple suivant illustre une stratégie qui masque la page de réinitialisation du système d’exploitation :
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Déploiement de cette stratégie via Intune

Voici les valeurs de configuration qui seront fournies à Intune :

- **Nom :** Nom d’affichage par défaut de l’administrateur pour le profil.
- **OMA-URI :** URI complet de la page des paramètres, y compris son [étendue](/windows/client-management/mdm/policy-configuration-service-provider). Les exemples de cette page utilisent l’étendue `./Device`.
- **Valeur :** Valeur de chaîne qui indique s’il faut masquer ou afficher *seulement*  les pages spécifiées. Les valeurs possibles sont `hide:<pagename>` et `showonly:<pagename>`. 
 
Plusieurs pages peuvent être spécifiées en les séparant par un point-virgule, et une liste de pages communes est disponible ci-dessous.

1. Créez une **stratégie personnalisée**.
1. Lors de la définition de l’**OMA-URI**, entrez l’URI pour l’étendue complète. Par exemple : **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Lorsque vous sélectionnez le choix de prélèvement de données, sélectionnez : **Chaîne**
1. Quand vous spécifiez **Valeur**, utilisez les instructions ci-dessus. Par exemple : **`showonly:network-wifi;network-proxy;bluetooth`** ou **`hide:reset`** 
> [!IMPORTANT]
> Veillez à affecter la configuration d’appareil personnalisée à un groupe auquel l’appareil est destiné. Si cette étape n’est pas effectuée, la stratégie sera envoyée (push), mais ne sera pas appliquée.

Pour plus d’informations sur les groupes et configurations d’appareils Intune, consultez [Configuration GPM HoloLens](hololens-mdm-configure.md).


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Déploiement de cette stratégie via un package de provisionnement

Il s’agit des valeurs de configuration qui seront spécifiées dans le Concepteur de configuration Windows :

**Valeur :** Valeur de chaîne qui indique s’il faut masquer ou afficher *seulement*  les pages spécifiées. Les valeurs possibles sont `hide:<pagename>` et `showonly:<pagename>`. Plusieurs pages peuvent être spécifiées en les séparant par un point-virgule, et une liste de pages communes est disponible ci-dessous.


1. Lorsque vous créez votre package dans le Concepteur de configuration Windows, accédez à **Stratégies > Paramètres > PageVisibilityList**.
1. Entrez la chaîne : **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportez votre package de configuration.
1. Appliquez le package à votre appareil.
Pour plus d’informations sur la création et l’application d’un package de provisionnement, consultez la [page de provisionnement de HoloLens](hololens-provisioning.md).


Quelle que soit la méthode choisie, votre appareil doit maintenant recevoir les modifications et les utilisateurs se voir présenter l’application Paramètres suivante.

![Capture d’écran d’heures actives modifiées dans l’application Paramètres.](images/hololens-page-visibility-list.jpg)

Pour configurer les pages de l’application Paramètres afin d’afficher ou de masquer votre propre sélection de pages, consultez les URL de paramètres disponibles sur HoloLens.

## <a name="settings-uris"></a>URI de paramètres

Les appareils HoloLens et Windows 10 présentent une sélection de pages différente dans l’application Paramètres. Sur cette page, vous trouverez uniquement les paramètres présents sur HoloLens.

### <a name="accounts"></a>Comptes
| Page Paramètres           | URI                                            |
|-------------------------|------------------------------------------------|
| Accès Professionnel ou Scolaire | `workplace`                         |
| Inscription Iris       | `signinoptions-launchirisenrollment` |
| Options de connexion         | ` signinoptions `                   |

### <a name="apps"></a>Applications
| Page Paramètres | URI                          |
|---------------|------------------------------|
| Applications et fonctionnalités <sup>2</sup>     | `appsfeatures` <br> |
| Applications et fonctionnalités > Options avancées <sup>2</sup>     | `appsfeatures-app` <br> |
| Applications et fonctionnalités > Cartes hors connexion <sup>2</sup>     | `maps-maps` <br> |
| Applications et fonctionnalités > Cartes hors connexion > Télécharger des cartes <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Appareils
| Page Paramètres | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Souris <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Confidentialité
| Page Paramètres            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informations sur le compte             | `privacy-accountinfo`              |
| Diagnostics d'application        | `privacy-appdiagnostics`              |
| Applications en arrière-plan        | `privacy-backgroundapps`              |
| Calendrier                 | `privacy-calendar`                    |
| Historique des appels             | `privacy-callhistory`                 |
| Appareil photo                   | `privacy-webcam`                      |
| Contacts                 | `privacy-contacts`                    |
| Diagnostics et commentaires | `privacy-feedback`                    |
| Documents                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| Système de fichiers              | `privacy-broadfilesystemaccess`       |
| Général <sup>2</sup>             | `privacy-general`       |
| Entrée manuscrite et personnalisation de la saisie <sup>2</sup>             | `privacy-speechtyping`       |
| Emplacement                 | `privacy-location`                    |
| Messagerie                | `privacy-messaging`                   |
| Microphone               | `privacy-microphone`                  |
| Mouvement <sup>2</sup>               | `privacy-motion`                  |
| Notifications            | `privacy-notifications`               |
| Autres appareils            | `privacy-customdevices`               |
| Images                 | `privacy-pictures`                    |
| Radios                   | `privacy-radios`                      |
| Bordures d’écran <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Captures d’écran et applications <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Speech                   | `privacy-speech`                      |
| Tâches                    | `privacy-tasks`                       |
| Mouvements des utilisateurs           | `privacy-backgroundspatialperception` |
| Vidéos                   | `privacy-videos`                      |
| Activation vocale       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Réseau et Internet
| Page Paramètres | URI                              |
|---------------|----------------------------------|
| Mode avion <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Système
| Page Paramètres      | URI                                |
|--------------------|------------------------------------|
| Batterie <sup>2</sup>           | `batterysaver`<br>|
| Batterie <sup>2</sup>           | `batterysaver-settings`<br>|
| Couleurs             | `colors`<br>`personalization-colors` |
| Hologrammes <sup>2</sup>  |  `holograms`  |
| Étalonnage <sup>2</sup> |  `calibration` |
| Notifications et actions  | `notifications`          |
| Expériences partagées | `crossdevice` 
| Son <sup>2</sup>           | `sound`<br>|
| Son > Volume de l’application et préférence d’appareil <sup>2</sup>           | `apps-volume`<br>|
| Son > Gérer les périphériques audio <sup>2</sup>           | `sound-devices`<br>|
| Stockage            | `storagesense`           |
| Stockage > Configurer l’Assistant Stockage <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Heure et langue
| Page Paramètres | URI                                           |
|---------------|-----------------------------------------------|
| Date et heure <sup>2</sup> | `dateandtime`                  |
| Clavier <sup>2</sup> | `keyboard`                  |
| Langue <sup>2</sup> | `language`                  |
| Langue <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Langage      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Région        | `regionformatting`                  |

### <a name="update--security"></a>Mise à jour et sécurité
| Page Paramètres                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Options avancées                    | `windowsupdate-options`         |
| Réinitialisation et récupération <sup>2</sup>      | `reset`         |
| Programme Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Update - Recherche de mises à jour | `windowsupdate-action`          |


- <sup>1</sup> - Pour les versions antérieures à Windows Holographic 21H1, les deux URI suivants ne vous permettent pas d’accéder aux pages **Options** ou **Options avancées** ; ils ne feront que bloquer ou afficher la page principale Windows Update.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> - Disponible dans Windows Holographic, version 21H1 ou ultérieure.


Pour obtenir la liste complète des URI des paramètres Windows 10, consultez la documentation relative aux [paramètres de lancement](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
