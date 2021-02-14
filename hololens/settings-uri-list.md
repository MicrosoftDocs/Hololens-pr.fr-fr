---
title: Visibilité des paramètres de la page
description: Tenez-vous au courant de notre liste d'URI pris en charge pour PageVisibilityList et Guide sur les appareils de réalité mixte HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque, page paramètres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327388"
---
# Visibilité des paramètres de la page

L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie paramètres/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application paramètres. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées.

> [!NOTE]
> Cette fonctionnalité est uniquement disponible dans [Windows Holographic version20H2](hololens-release-notes.md#windows-holographic-version-20h2) pour les appareils HoloLens2. Veuillez vérifier que les appareils pour lesquels vous envisagez d’utiliser cette fonctionnalité sont à jour.

> [!NOTE]
> Plus de 20 nouvelles SettingsURIs seront prochainement ajoutées. Consultez [la page Windows Insider – Nouvelles SettingsURIs pour la visibilité des paramètres de page](hololens-insider.md#new-settingsuris-for-page-settings-visibility) si vous êtes intéressé par la prévisualisation de ce paramètre sur une build [HoloLens Insider](hololens-insider.md).

L’exemple suivant illustre une stratégie qui autoriserait l’accès uniquement aux pages « À propos de» et Bluetooth, avec l’URI «ms-settings: Network-WiFi» et «ms-settings: Bluetooth» respectivement:
- `showonly:network-wifi;network-proxy;bluetooth`

Pour le définir via un package d’approvisionnement:

1. Lorsque vous créez votre package dans le concepteur de configuration Windows, accédez à **Stratégies > Paramètres > PageVisibilityList**
1. Entrez la chaîne : **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportez votre package d’approvisionnement.
1. Appliquer le package aux appareils.
Pour plus d’informations sur la création et l’application d’un package d’approvisionnement, consultez [cette page.](hololens-provisioning.md)

Vous pouvez le faire via Intune à l’aide d’OMA-URI :

1. Créer une **stratégie personnalisée**.
1. Lors de la définition de l’OMA-URI, utilisez la chaîne : **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Lorsque vous sélectionnez le choix de prélèvement de données, sélectionnez: **Chaîne**
1. Lorsque vous tapez la valeur, utilisez : **`showonly:network-wifi;network-proxy;bluetooth`**
1. Veillez à affecter la configuration d’appareil personnalisée à un groupe auquel l’appareil est destiné.

Pour plus d’informations sur les groupes et configurations d’appareils Intune, consultez [Configuration de la gestion des appareils pour HoloLens](hololens-mdm-configure.md).

Quelle que soit la méthode choisie, votre appareil doit maintenant recevoir les modifications et les utilisateurs recevront l’application Paramètres suivante.

![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

Pour configurer les pages de l’application Paramètres afin d’afficher ou de masquer votre propre sélection de pages, jetez un œil aux URL de paramètres disponibles sur HoloLens.

## URI de paramètres

Les appareils HoloLens et les appareils Windows10 ont une sélection de pages différente dans l’application Paramètres. Sur cette page, vous trouverez uniquement les paramètres qui existent sur HoloLens.

### Comptes
| Page de paramètres           | URI                                            |
|-------------------------|------------------------------------------------|
| Options de connexion         | ` ms-settings:signinoptions `                   |
| Inscription Iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Accéder à un compte professionnel ou scolaire | `ms-settings:workplace`                         |

### Appareils
| Page de paramètres | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### Confidentialité
| Page de paramètres            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informations sur le compte             | `ms-settings:privacy-accountinfo`              |
| Diagnostics des applications        | `ms-settings:privacy-appdiagnostics`              |
| Applications en arrière-plan        | `ms-settings:privacy-backgroundapps`              |
| Mouvements des utilisateurs           | `ms-settings:privacy-backgroundspatialperception` |
| Système de fichiers              | `ms-settings:privacy-broadfilesystemaccess`       |
| Calendrier                 | `ms-settings:privacy-calendar`                    |
| Historique des appels             | `ms-settings:privacy-callhistory`                 |
| Contacts                 | `ms-settings:privacy-contacts`                    |
| Autres appareils            | `ms-settings:privacy-customdevices`               |
| Documents                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| Commentaires et diagnostics | `ms-settings:privacy-feedback`                    |
| Location                 | `ms-settings:privacy-location`                    |
| Messages                | `ms-settings:privacy-messaging`                   |
| Micro               | `ms-settings:privacy-microphone`                  |
| Notifications            | `ms-settings:privacy-notifications`               |
| Images                 | `ms-settings:privacy-pictures`                    |
| Radios                   | `ms-settings:privacy-radios`                      |
| Voix                   | `ms-settings:privacy-speech`                      |
| Tâches                    | `ms-settings:privacy-tasks`                       |
| Vidéos                   | `ms-settings:privacy-videos`                      |
| Activation vocale       | `ms-settings:privacy-voiceactivation`             |
| Appareil photo                   | `ms-settings:privacy-webcam`                      |

### Réseau et Internet
| Page de paramètres | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| VPN   | `ms-settings:network-vpn`          |
| Proxy | `ms-settings:network-proxy`        |

### Système
| Page de paramètres      | URI                                |
|--------------------|------------------------------------|
| Expériences partagées | `ms-settings:crossdevice`            |
| Couleurs             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Notifications et actions  | `ms-settings:notifications`          |
| Stockage            | `ms-settings:storagesense`           |

### Heure et langue
| Page de paramètres | URI                                           |
|---------------|-----------------------------------------------|
| Région        | `ms-settings:regionformatting`                  |
| Langue      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### Mise à jour et sécurité
| Page de paramètres                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programme WindowsInsider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update: recherche les mises à jour | `ms-settings:windowsupdate-action`          |
| Options avancées                    | `ms-settings:windowsupdate-options`         |

>  <sup>1</sup> Les deux URI suivants ne vous permettent pas réellement d'accéder à la page **Options avancées** ou **Options**, ils ne feront que bloquer ou afficher la page principale Windows Update.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Pour obtenir la liste complète des URL des paramètres de Windows 10, visitez la documentation [paramètres du lancement](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
