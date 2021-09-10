---
title: Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC
description: Comment inscrire l’adresse MAC pour le réseau sur les appareils HoloLens 2
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
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427047"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC

Ce document décrit un scénario courant que nous avons identifié dans les environnements clients où l’accès au Wi-Fi est restreint par adresses MAC, ou quand des certificats sont nécessaires pour se connecter à des réseaux sans fil.

## <a name="example-scenario"></a>Exemple de scénario

De nombreux clients sont soumis dans des environnements sécurisés à des restrictions sur leurs réseaux sans fil ou câblés, qui vont permettre aux seuls approuvés de se connecter (en fonction de leur adresse MAC). Cela peut être appliqué via un filtrage des adresses MAC sur un point d’accès sans fil ou via un serveur DHCP. De plus, certains réseaux sans fil peuvent être protégés avec PEAP, qui impose qu’un certificat soit appliqué sur l’appareil avant l’authentification sur le réseau sans fil.

Dans ce scénario, deux exigences importantes peuvent introduire des retards ou nécessiter une intervention manuelle pour joindre des appareils HoloLens au réseau :

- Le certificat PEAP sans fil doit être appliqué à l’appareil avant qu’il puisse se joindre au réseau sans fil.
- L’adresse MAC de l’adaptateur Wi-Fi HoloLens doit être inscrite.

Les problématiques principales liées aux exigences ci-dessus sont les suivantes :

1. L’adresse MAC peut actuellement être identifiée seulement depuis l’application Paramètres sur l’appareil ou depuis Intune après une inscription réussie.

2. Sans l’adresse MAC, l’appareil ne peut pas se joindre au réseau Wi-Fi pour commencer l’inscription.

3. Pour contourner manuellement ces problèmes, un technicien doit interagir avec l’appareil.

## <a name="solutions"></a>Solutions

Il existe de nombreuses façons d’améliorer cette situation, en fonction de l’infrastructure disponible au sein de l’environnement.

| Solution | Avantages | Spécifications |
| --- | --- | --- |
| Package de provisionnement avec adaptateur Ethernet | Améliore l’expérience OOBE et permet une intervention plus rapide du technicien. | Adaptateur USB-C Hub + Ethernet compatible HoloLens : le technicien aura néanmoins toujours besoin d’interagir avec l’appareil pour la capture de l’adresse MAC et la finalisation de l’expérience OOBE. |
| Autopilot avec l’inscription Intune via Ethernet | Il s’agit de la connexion et de l’inscription en une seule étape de l’appareil à l’environnement du client. La capture de l’adresse MAC peut être effectuée sans devoir interagir avec l’appareil | Intune activé pour le locataire AAD du client et un adaptateur Ethernet USB-C compatible HoloLens |
| Indication automatique des adresses MAC | Quand des appareils sont inscrits auprès du locataire Intune, un script peut indiquer l’adresse MAC au technicien. | Applets de commande PowerShell Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Package de provisionnement avec adaptateur Ethernet

> [!NOTE] 
> Si le réseau câblé est également soumis à des restrictions MAC, l’adresse MAC de l’adaptateur USB-C Hub + Ethernet doit également être préapprouvée. Il convient de prendre soin de cet adaptateur, car il va permettre d’accéder au réseau à partir d’autres appareils.

### <a name="requirements"></a>Spécifications

- Port de réseau câblé avec accès au réseau du client
- Hub USB-C compatible HoloLens avec adaptateur Ethernet : tout adaptateur qui ne nécessite pas de pilotes ni d’installations d’applications supplémentaires convient.
- Contenu du package de provisionnement :
  - Contenant des informations sur le réseau sans fil et un certificat
  - Contenant éventuellement des informations d’inscription pour l’annuaire Azure AD de l’organisation
  - Contenant les éventuels autres paramètres de configuration nécessaires

### <a name="process"></a>Process

Le processus peut varier en fonction du niveau du logiciel de l’appareil. Si l’appareil dispose de la [mise à jour 2004 de mai](hololens-release-notes.md#windows-holographic-version-2004), effectuez les étapes ci-dessous.

1. Placez le package de provisionnement à la racine d’une clé USB et branchez-la sur le hub.
2. Connectez le câble Ethernet à l’adaptateur Hub + Ethernet.
3. Connectez le Hub USB-C à l’appareil HoloLens.
4. Allumez l’appareil HoloLens et activez l’appareil.
5. Appuyez sur le **bouton d’alimentation et de réduction du volume** pour appliquer le package de provisionnement.
6. Le technicien peut maintenant suivre OOBE et, quand c’est terminé, ouvrez l’application Paramètres pour récupérer l’adresse MAC de l’appareil.

Si la build du système d’exploitation de l’appareil est antérieure à la [mise à jour 2004 de mai](hololens-release-notes.md#windows-holographic-version-2004), effectuez les étapes ci-dessous.

1. Activez l’appareil HoloLens et connectez l’appareil à un PC.
2. L’appareil doit apparaître sur le PC en tant que dispositif de stockage de fichiers.
3. Copiez le package de provisionnement sur l’appareil.
4. Connectez le câble Ethernet au hub.
5. Connectez le Hub USB-C à l’appareil HoloLens.
6. Allumez l’appareil HoloLens.
7. Appuyez sur le **bouton d’alimentation et de réduction du volume** pour appliquer le package de provisionnement.
8. Le technicien peut maintenant suivre OOBE et, quand c’est terminé, ouvrez l’application Paramètres pour récupérer l’adresse MAC de l’appareil.

### <a name="benefits"></a>Avantages

Ceci va permettre d’utiliser une seule touche de l’appareil pour appliquer le package de provisionnement correct et d’obtenir son adresse MAC. [Vous pouvez créer des packages de provisionnement en suivant les instructions fournies ici.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot avec l’inscription Intune

### <a name="requirements"></a>Spécifications

- Port de réseau câblé avec accès au réseau du client
- Appareils HoloLens exécutant Windows Holographic 2004
- Adaptateur Ethernet USB-C compatible HoloLens
- Intune configuré et activé pour le locataire du client
- Appareil inscrit pour Autopilot et importé dans le locataire du client
- Stratégies Intune définies pour l’appareil :
   - Contenant des informations sur le réseau sans fil et un certificat
   - Contenant les éventuels autres paramètres de configuration nécessaires

Ceci permet à un client ayant besoin d’une configuration réseau avancée d’inscrire les appareils en utilisant une approche pratique et évolutive.

Les prérequis supplémentaires suivants seront nécessaires :
1. [Activez le locataire pour la préversion d’Autopilot](hololens2-autopilot.md).
1. Créez les stratégies HoloLens pour remplacer le package de provisionnement dans Intune.
1. Créez les stratégies Intune HoloLens.
1. Affectez les appareils au groupe approprié.

### <a name="process"></a>Process

1. Connectez le câble Ethernet à l’adaptateur et branchez l’adaptateur au port USB-C sur l’appareil HoloLens 2.

2. Allumez l’appareil HoloLens.

3. L’appareil doit se connecter automatiquement à Internet pendant l’OOBE via l’adaptateur Ethernet. Il doit détecter la configuration Autopilot et s’inscrire automatiquement auprès d’Azure AD et d’Intune.

4. L’appareil va appliquer les certificats Wi-Fi requis et si nécessaire, d’autres configurations via Intune.

5. Une fois que c’est terminé, le technicien peut charger le portail Intune (Endpoint Manager) et accéder à la page des propriétés de l’appareil en sélectionnant **Accueil -> Appareils -> Nom_appareil -> Matériel**.

6. L’adresse MAC Wi-Fi sera visible dans le portail Intune.

   ![Adresse MAC via Intune.](images/mac-address-intune.jpg)

7. Le technicien va ajouter cette adresse MAC en tant qu’appareil autorisé.

### <a name="benefits"></a>Avantages

Ceci va permettre une expérience de déploiement « Sans port sur la tête » pour le technicien : il peut en effet inscrire l’appareil sur Azure AD et Intune sans avoir à le porter ni à interagir manuellement avec l’environnement HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Indication des adresses MAC au technicien

### <a name="requirements"></a>Spécifications

- Autorisation du « Intune Graph PowerShell » sur le locataire du client
- Installation du Intune Graph PowerShell sur la machine du technicien.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Accès en lecture aux éléments « Appareils gérés » d’Intune. (Rôle Opérateur de support technique ou supérieur, ou rôle personnalisé)

Pour l’instant, il n’existe pas de moyen « simple » de déclencher une commande d’automatisation basée sur l’inscription d’un nouvel appareil dans Intune. Par conséquent, cette commande offre au technicien une méthode simple pour récupérer l’adresse MAC sans devoir se connecter au portail et récupérer celle-ci manuellement.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Ceci va retourner le nom et l’adresse MAC de tous les appareils HoloLens inscrits au cours des 30 derniers jours.

![Adresse MAC via PowerShell.](images/mac-address-powershell.jpg)

### <a name="process"></a>Process

Une fois l’inscription à Intune terminée, le technicien va exécuter le script ci-dessus pour récupérer l’adresse MAC.
