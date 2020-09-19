---
title: URI paramètres
description: Liste des URI pris en charge par HoloLens pour PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 09/16/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque, page paramètres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 17959fa25763d2c6b89d0956f29b9999b3012e60
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016698"
---
# URI paramètres

L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie paramètres/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application paramètres. PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées. 

> [!IMPORTANT]
> Pour l’instant, cette fonctionnalité est uniquement disponible dans les [builds Windows Insider](hololens-insider.md). Assurez-vous que les appareils que vous avez l’intention d’utiliser sont sur la build 19041.1349+.

L’exemple suivant illustre une stratégie qui autoriserait l’accès uniquement aux pages « À propos de» et Bluetooth, avec l’URI «ms-settings: Network-WiFi» et «ms-settings: Bluetooth» respectivement:
- AfficherSeulement: réseau-WiFi;réseau-proxy;bluetooth

Pour le spécifier via un package Provsioning: 
1. Lorsque vous créez votre package dans le concepteur de configuration Windows, accédez à **Stratégies > Paramètres > PageVisibilityList**
1. Entrez la chaîne : **AfficherSeulement: réseau-WiFi;réseau-proxy;bluetooth**
1. Exporter votre package Provsioning.
1. Appliquer le package aux appareils. Pour plus d’informations sur la création et l’application d’un package provsioning, visitez [cette page](hololens-provisioning.md). 

Cette opération peut être effectuée via Intune à l’aide de OMA-URI.
1. Créer une **stratégie personnalisée**.
1. Lorsque vous définissez l’URI OMA, utilisez la chaîne: **./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. Lorsque vous sélectionnez le prélèvement de données, sélectionnez: **Chaîne**
1. Lorsque vous tapez la valeur, utilisez : **AfficherSeulement: réseau-WiFi;réseau-proxy;bluetooth**
1. Veillez à attribuer la configuration personnalisée de l’appareil au groupe dans lequel l’appareil est destiné.
Pour plus d’informations sur les groupes Intune et les configurations d’appareils [visitez ici](hololens-mdm-configure.md).

Quelle que soit la méthode choisie, votre appareil doit maintenant recevoir les modifications et les utilisateurs verront l’application Paramètres suivante. 

![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

Pour configurer les pages de l’application Paramètres de façon à afficher ou masquer votre propre sélection de pages, consultez les paramètres d’URI avalible sur HoloLens. 

## URI paramètres

Les appareils HoloLens et les appareils Windows10 ont une sélection de pages différente dans l’application paramètres. Dans cette page, vous trouverez uniquement les paramètres qui existent sur HoloLens. 

### Comptes
| Page de paramètres           | URI                                            |
|-------------------------|------------------------------------------------|
| Options de connexion         | ms-settings:signinoptions                      |
| Inscription Iris       | ms-settings:signinoptions-launchirisenrollment |
| Accéder à un compte professionnel ou scolaire | ms-settings:workplace                          |

### Périphériques
| Page de paramètres | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### Confidentialité
| Page de paramètres            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informations sur le compte             | ms-settings:privacy-accountinfo                 |
| Diagnostics des applications        | ms-settings:privacy-appdiagnostics              |
| Applications en arrière-plan        | ms-settings:privacy-backgroundapps              |
| Mouvements des utilisateurs           | ms-settings:privacy-backgroundspatialperception |
| Système de fichiers              | ms-settings:privacy-broadfilesystemaccess       |
| Calendrier                 | ms-settings:privacy-calendar                    |
| Historique des appels             | ms-settings:privacy-callhistory                 |
| Contacts                 | ms-settings:privacy-contacts                    |
| Autres appareils            | ms-settings:privacy-customdevices               |
| Documents                | ms-settings:privacy-documents                   |
| E-mail                    | ms-settings:privacy-email                       |
| Commentaires et diagnostics | ms-settings:privacy-feedback                    |
| Location                 | ms-settings:privacy-location                    |
| Messages                | ms-settings:privacy-messaging                   |
| Micro               | ms-settings:privacy-microphone                  |
| Notifications            | ms-settings:privacy-notifications               |
| Images                 | ms-settings:privacy-pictures                    |
| Radios                   | ms-settings:privacy-radios                      |
| Voix                   | ms-settings:privacy-speech                      |
| Tâches                    | ms-settings:privacy-tasks                       |
| Vidéos                   | ms-settings:privacy-videos                      |
| Activation vocale       | ms-settings:privacy-voiceactivation             |
| Appareil photo                   | ms-settings:privacy-webcam                      |

### Réseau et Internet
| Page de paramètres | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

### Système
| Page de paramètres      | URI                                |
|--------------------|------------------------------------|
| Expériences partagées | ms-settings:crossdevice            |
| Couleurs             | ms-settings:colors<br>ms-settings:personalization-colors |
| Notifications et actions  | ms-settings:notifications          |
| Stockage            | ms-settings:storagesense           |

### Heure et langue
| Page de paramètres | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Langue      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### Mise à jour et sécurité
| Page de paramètres                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programme WindowsInsider               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| WindowsUpdate                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update: recherche les mises à jour | ms-settings:windowsupdate-action          |
| Options avancées                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 Les deux URI suivants ne vous permettent pas réellement d'accéder à la page Options avancées ou Options, ils ne feront que bloquer / afficher la page principale Windows Update. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Pour obtenir la liste complète des URI des paramètres Windows10, visitez [ici](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
