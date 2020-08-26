---
title: URI paramètres
description: Liste des URI pris en charge par HoloLens pour PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 8/1/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque, page paramètres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6b506b36915c8f34b90c455410db67e55a2cca09
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963712"
---
# URI paramètres

L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie paramètres/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application paramètres. Les appareils HoloLens et les appareils Windows10 ont une sélection de pages différente dans l’application paramètres. Dans cette page, vous trouverez uniquement les paramètres qui existent sur HoloLens. 

## Comptes
| Page de paramètres           | URI                                            |
|-------------------------|------------------------------------------------|
| Options de connexion         | ms-settings:signinoptions                      |
| Inscription Iris       | ms-settings:signinoptions-launchirisenrollment |
| Accéder à un compte professionnel ou scolaire | ms-settings:workplace                          |

## Périphériques
| Page de paramètres | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

## Confidentialité
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

## Réseau et Internet
| Page de paramètres | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

## Système
| Page de paramètres      | URI                                |
|--------------------|------------------------------------|
| Expériences partagées | ms-settings:crossdevice            |
| Couleurs             | ms-settings:colors<br>ms-settings:personalization-colors |
| Notifications et actions  | ms-settings:notifications          |
| Stockage            | ms-settings:storagesense           |

## Heure et langue
| Page de paramètres | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Langue      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

## Mise à jour et sécurité
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
