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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407619"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Inscription des appareils HoloLens en entreprise dans un environnement Wi-Fi restreignant les adresses MAC

Ce document décrit un scénario courant que nous avons identifié dans les environnements clients où l’accès au Wi-Fi est restreint par adresses MAC, ou des certificats sont requis pour se connecter aux réseaux sans fil.

## <a name="example-scenario"></a>Exemple de scénario

De nombreux clients en environnement sécurisé sont soumis à des restrictions sur leurs réseaux sans fil ou câblés, ce qui permet uniquement aux périphériques approuvés (en fonction de leur adresse MAC) de se connecter correctement. Cela peut être appliqué par le biais du filtrage des adresses MAC sur un point d’accès sans fil ou via un serveur DHCP. De plus, certains réseaux sans fil peuvent être protégés par PEAP, ce qui exige qu’un certificat soit appliqué sur l’appareil avant l’authentification sur le réseau sans fil.

Dans ce scénario, deux exigences clés peuvent introduire des retards ou nécessiter une intervention manuelle lors de la connexion des appareils HoloLens au réseau:

- Le certificat PEAP sans fil doit être appliqué à l’appareil pour qu’il puisse se connecter au réseau sans fil.
- L’adresse MAC de l’adaptateur Wi-Fi HoloLens doit être inscrite.

Les principaux défis liés aux exigences ci-dessus sont les éléments ci-dessus:

1. L’adresse MAC ne peut actuellement être identifiée qu’à partir de l’application Paramètres sur l’appareil ou à partir d’Intune après une inscription réussie.

2. Sans l’adresse MAC, l’appareil ne peut pas se connecter au réseau Wi-Fi pour commencer l’inscription.

3. Pour contourner manuellement ces problèmes, un technicien doit interagir avec l’appareil.

## <a name="solutions"></a>Solutions

Il existe de nombreuses façons d’améliorer cette situation, en fonction de l’infrastructure disponible au sein de l’environnement.

| Solution | Avantages | Conditions requises |
| --- | --- | --- |
| Package de configuration avec adaptateur Ethernet | Améliore l’expérience OOBE et accélère l’intervention du technicien. | Concentrateur USB C compatible HoloLens + adaptateur Ethernet et le technicien doit continuer à interagir avec l’appareil pour la capture MAC et la finalisation de l’expérience OOBE. |
| Autopilot avec l’inscription Intune via Ethernet | Il s’agit d’une connexion à une étape et d’une inscription de l’appareil à l’environnement du client. La capture MAC peut être effectuée sans avoir à interagir avec l’appareil | Intune activé pour le client client AAD et un adaptateur Ethernet USB-C compatible HoloLens |
| Création automatique de rapports sur les adresses MAC | Lorsque des appareils sont enregistrés auprès du client Intune, un script peut signaler l’adresse MAC au technicien. | Cmdlets Intune PowerShell |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Package de configuration avec adaptateur Ethernet

> [!NOTE] 
> Si le réseau câblé est également soumis à des restrictions mac, l’adresse Mac du concentrateur USB-C + adapteur Ethernet doit également être pré-approuvée. Il convient de prendre soin de cet adaptateur, car elle permet d’accéder au réseau à partir d’autres appareils.

### <a name="requirements"></a>Configuration requise

- Port réseau câblé avec accès au réseau du client
- Concentrateur USB-C compatible HoloLens avec adaptateur Ethernet: tout adaptateur qui ne nécessite pas de pilotes ni d’installations d’applications supplémentaires convient.
- Contenu du package de configuration:
  - Certificat et informations sur le réseau sans fil
  - Informations d’inscription pour l’AzureAD de l’organisation (facultatif)
  - Tout autre paramètre de configuration requis

### <a name="process"></a>Process

Le processus peut varier en fonction du niveau du logiciel de l’appareil. Si l’appareil présente la [mise à jour2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.

1. Placez le package de configuration sur la racine d’une clé USB et branchez-la sur le concentrateur.
2. Connectez le câble Ethernet à l’adaptateur Hub + Ethernet.
3. Connectez le Hub USB-C à l’appareil HoloLens.
4. Activer HoloLens et activer l’appareil.
5. Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.
6. Le technicien peut désormais suivre la OOBE et, une fois terminé, ouvrez l’application Paramètres pour récupérer l’adresse MAC de l’appareil.

Si la build du système d'exploitation de l’appareil est antérieure à la [mise à jour2004](hololens-release-notes.md#windows-holographic-version-2004), procédez comme suit.

1. Activez HoloLens et brancher l’appareil sur un PC.
2. L’appareil doit apparaître sur le PC en tant que dispositif de stockage de fichiers.
3. Copiez le package de configuration sur l’appareil.
4. Connectez le câble Ethernet au concentrateur.
5. Connectez le Hub USB-C à l’appareil HoloLens.
6. Mettez l'HoloLens en marche
7. Pour appliquer le package de configuration, appuyez sur le **bouton Baisser le volume et le bouton d’alimentation**.
8. Le technicien peut désormais suivre la OOBE et, une fois terminé, ouvrez l’application Paramètres pour récupérer l’adresse MAC de l’appareil.

### <a name="benefits"></a>Avantages

Cela permettra, en une «Seule pression» sur l’appareil, d’appliquer le package de configuration correct et d’obtenir l’adresse MAC de l’appareil. [Vous pouvez créer les packages de configuration à l’aide des instructions fournies ici.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot avec l’inscription Intune

### <a name="requirements"></a>Conditions requises

- Port réseau câblé avec accès au réseau du client
- Appareils HoloLens exécutant Windows Holographic2004
- Adaptateur Ethernet USB-C compatible HoloLens
- Intune configuré et activé pour le client du client
- Appareil inscrit pour Autopilot et importé dans le client du client
- Stratégies Intune définies pour l’appareil:
   - Certificat et informations sur le réseau sans fil
   - Tout autre paramètre de configuration requis

Cela permet à un client ayant besoin d’une configuration réseau avancée d’inscrire les appareils en utilisant une approche pratique et évolutive.

Des conditions préalables supplémentaires sont requises comme suit:
1. [Activez le client pour l’aperçu Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).
1. Créez les stratégies HoloLens pour remplacer le package de configuration dans Intune.
1. Créez les stratégies Intune HoloLens.
1. Attribuez les appareils au groupe approprié.

### <a name="process"></a>Processus

1. Connectez le câble Ethernet à l’adaptateur et branchez-le au port USB-C sur l’appareil HoloLens2.

2. Activer l’HoloLens.

3. L’appareil doit se connecter automatiquement à Internet pendant l’utilisation de la connexion Internet via l’adaptateur Ethernet. Il doit détecter la configuration Autopilot et s’inscrire automatiquement auprès d’Azure AD et d’Intune.

4. L’appareil applique les certificats Wi-Fi requis et d’autres configurations si nécessaire via Intune.

5. Une fois terminé, le technicien peut charger le portail Intune (Gestionnaire de point de terminaison) et effectuer une recherche dans la page des propriétés de l’appareil sur home **-> Devices -> DeviceName -> Hardware**.

6. L’adresse MAC Wi-Fi sera visible dans le portail Intune.

   ![Adresse MAC via Intune](images/mac-address-intune.jpg)

7. Le technicien ajoutera cette adresse MAC en tant qu’appareil autorisé.

### <a name="benefits"></a>Avantages

Cela permet une expérience de déploiement «Sans port sur la tête» pour le technicien. Il peut en effet inscrire l’appareil sur Azure AD et Intune sans avoir à le porter ni à interagir manuellement avec l’environnement HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Notification des adresses MAC au technicien

### <a name="requirements"></a>Configuration requise

- Autorisation de « Intune Graph PowerShell » sur le client
- Installation du PowerShell Graph Intune sur l’ordinateur du technicien.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Accès en lecture aux éléments « Appareils gérés » d’Intune. (Opérateur de support technique ou supérieur, ou rôle personnalisé)

Pour l’instant, il n’existe aucun moyen «simple» de déclencher une commande d’automatisation basée sur l’inscription d’un nouvel appareil dans Intune. Par conséquent, cette commande offre au technicien une méthode simple pour récupérer l’adresse MAC sans avoir à se connecter au portail et récupérer celle-ci manuellement.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Cette opération renvoie le nom et l’adresse MAC de tous les appareils HoloLens inscrits au cours des 30derniers jours.

![Adresse MAC via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Processus

Une fois l’inscription à Intune terminée, le technicien exécutait le script ci-dessus pour récupérer l’adresse MAC.
