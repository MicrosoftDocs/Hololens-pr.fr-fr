---
title: Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC
description: Inscription de l’adresse MAC pour le réseau sur les appareils HoloLens2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253141"
---
# Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC

Ce document décrit un scénario courant que nous avons identifié dans les environnements clients où l’accès au Wi-Fi est restreint par adresses MAC, ou des certificats sont requis pour se connecter aux réseaux sans fil.

## Exemple de scénario

De nombreux clients en environnement sécurisé sont soumis à des restrictions sur leurs réseaux sans fil ou câblés, ce qui permet uniquement aux périphériques approuvés (en fonction de leur adresse MAC) de se connecter correctement (avec le filtrage des adresses MAC sur un point d’accès sans fil ou sur un serveur DHCP). De plus, certains réseaux sans fil peuvent être protégés par PEAP, ce qui nécessite qu’un certificat soit appliqué à l’appareil avant de pouvoir authentifier correctement le réseau sans fil.

Deux problèmes clés peuvent se produire avec les appareils HoloLens, qui peuvent entraîner des délais et une intervention manuelle pour connecter les appareils HoloLens au réseau.

- Le certificat PEAP sans fil doit être appliqué à l’appareil pour qu’il puisse se connecter au réseau sans fil.
- L’adresse MAC de l’adaptateur Wi-Fi HoloLens doit être inscrite.

Les principaux défis à relever sont les suivants:

1. Pour l’instant, il est possible d’identifier l’adresse MAC uniquement à partir de l’application Paramètres sur l’appareil, ou à partir d’Intune suite à une inscription Intune réussie.
2. Sans l’adresse MAC, l’appareil ne peut pas se connecter au réseau Wi-Fi pour commencer l’inscription.
3. Les solutions manuelles pour résoudre ces défis nécessitent l’implication du technicien sur les appareils.

## Solutions

Il existe de nombreuses façons d’améliorer cette situation, en fonction de l’infrastructure disponible au sein de l’environnement.

| Solution | Avantages | Conditions requises |
| --- | --- | --- |
| Package de configuration avec adaptateur Ethernet | Améliore l’expérience OOBE et accélère l’intervention du technicien. | Compatible HoloLens USB C HubTechnician continuera à interagir avec la version de capture de l’appareil pour MAC et la finalisation de la version OOBE |
| Autopilot avec l’inscription Intune via Ethernet | Connexion et enregistrement de l’appareil à l’environnement client en une étape. La capture MAC peut être effectuée sans interaction avec l’appareil. | Intune activé pour le client Azure AD du client. Adaptateur réseau compatible USB-C HoloLens |
| Création automatique de rapports sur les adresses MAC | Lorsque des appareils ont été enregistrés dans le client Intune, scriptez la notification de l’adresse MAC au technicien. | Commandlets PowerShell pour Intune |

## Package de configuration avec adaptateur Ethernet

> [!NOTE] 
> Si le réseau câblé est également soumis aux restrictions MAC, l’adresse MAC du concentrateur/de l’adaptateur Ethernet USB-C doit être pré-approuvée. Vous devez faire preuve de précaution avec ce concentrateur, car il permettra d’accéder au réseau à partir d’autres appareils.

### Conditions requises

- Port réseau câblé avec accès au réseau du client
- Concentrateur USB-C compatible HoloLens contenant un adaptateur Ethernet: tout concentrateur qui ne nécessite pas de pilotes ni d’installations d’applications supplémentaires convient.
- Contenu du package de configuration:
  - Certificat et informations sur le réseau sans fil
  - Informations d’inscription pour l’AzureAD de l’organisation (facultatif)
  - Tout autre paramètre de configuration requis

### Process

Le processus peut varier en fonction du niveau du logiciel de l’appareil. Si l’appareil présente la [mise à jour2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.

1. Placez le package de configuration sur la racine d’une clé USB et branchez-la sur le concentrateur.
2. Connectez le câble Ethernet au concentrateur.
3. Connectez le concentrateur USB-C à l’appareil HoloLens.
4. Activez l’appareil HoloLens et portez l’appareil.
5. Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.
6. Le technicien peut désormais suivre l’expérience OOBE et, une fois terminé, ouvrir l’application Paramètres et récupérer l’adresse MAC de l’appareil.

Si la build du système d'exploitation de l’appareil est antérieure à la [mise à jour2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.

1. Activez l’appareil HoloLens et branchez l’appareil sur un PC.
2. L’appareil doit apparaître sur le PC en tant que dispositif de stockage de fichiers.
3. Copiez le package de configuration sur l’appareil.
4. Connectez le câble Ethernet au concentrateur.
5. Connectez le concentrateur USB-C à l’appareil HoloLens.
6. Portez l’appareil.
7. Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.
8. Le technicien peut désormais suivre l’expérience OOBE et, une fois terminé, ouvrir l’application Paramètres et récupérer l’adresse MAC de l’appareil.

### Avantages

Cela permettra, en &quot;une seule pression&quot; sur l’appareil, d’appliquer le package de configuration correct et d’obtenir l’adresse MAC de l’appareil. [Vous pouvez créer les packages de configuration à l’aide des instructions fournies ici.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Autopilot avec l’inscription Intune

### Conditions requises

- Port réseau câblé avec accès au réseau du client
- Appareils HoloLens exécutant Windows Holographic2004
- Concentrateur USB-C compatible HoloLens
- Intune configuré et activé pour le client du client
- Appareil inscrit pour Autopilot et importé dans le client du client
- Stratégies Intune définies pour l’appareil:
   - Certificat et informations sur le réseau sans fil
   - Tout autre paramètre de configuration requis

Cela permet à un client ayant besoin d’une configuration réseau avancée d’inscrire les appareils en utilisant une approche pratique et évolutive.

Des conditions préalables supplémentaires sont requises comme suit:
1. [Activez le client pour l’aperçu Autopilot.](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. Créez les stratégies HoloLens pour remplacer le package de configuration dans Intune.
1. Créez les stratégies Intune HoloLens.
1. Attribuez les appareils au groupe approprié.

### Process

1. Branchez le concentrateur USB-C et le câble Ethernet sur l’appareil HoloLens2.
2. Activez HoloLens2.
3. L’appareil doit se connecter automatiquement à Internet à l’aide de l’expérience OOBE via l’adaptateur Ethernet, détecter la configuration Autopilot et s’inscrire automatiquement auprès d’Azure AD et d’Intune.
4. L’appareil applique les certificats Wi-Fi requis et d’autres configurations si nécessaire via Intune.
5. Une fois l’opération terminée, le technicien pourra charger le portail Intune (Endpoint Manager), puis explorer la page des propriétés de l’appareil en accédant à **Accueil-> Appareils-> NomDeL’Appareil-> Matériel**.
6. L’adresse MAC Wi-Fi sera visible dans le portail Intune.

![Adresse MAC via Intune](images/mac-address-intune.jpg)

7. Le technicien ajoutera cette adresse MAC en tant qu’appareil autorisé.

### Avantages

Cela permet une expérience de déploiement &quot;sans port sur la tête&quot; pour le technicien. Il peut en effet inscrire l’appareil sur Azure AD et Intune sans avoir à le porter ni à interagir manuellement avec l’environnement HoloLens.

## Notification des adresses MAC au technicien

### Conditions requises

- Autorisation du &quot;PowerShell Graph Intune&quot; sur le client du client
- Installation du PowerShell Graph Intune sur l’ordinateur du technicien.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Accès en lecture sur les éléments &quot;Appareils gérés&quot; d’Intune. (Opérateur de support technique ou supérieur, ou rôle personnalisé)

Pour l’instant, il n’existe aucun moyen &quot;simple&quot; de déclencher une commande d’automatisation basée sur l’inscription d’un nouvel appareil dans Intune. Par conséquent, cette commande offre au technicien une méthode simple pour récupérer l’adresse MAC sans avoir à se connecter au portail et récupérer celle-ci manuellement.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Cette opération renvoie le nom et l’adresse MAC de tous les appareils HoloLens inscrits au cours des 30derniers jours.

![Adresse MAC via PowerShell](images/mac-address-powershell.jpg)

### Process

Une fois l’inscription à Intune terminée, le technicien exécutait le script ci-dessus pour récupérer l’adresse MAC.
