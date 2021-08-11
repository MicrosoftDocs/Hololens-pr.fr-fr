---
title: Prise en charge de l'inscription Windows Autopilot pour HoloLens 2
description: Découvrez comment bénéficier de la prise en charge de l'inscription Autopilot sur les appareils HoloLens 2.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: ylempidakis
ms.openlocfilehash: 2304e7ec18eb531cce431fb93c7abf38f2c9a1cef30f0d6c6fcaac6c95281f8e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661775"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Prise en charge de l'inscription des appareils HoloLens 2 pour AutoPilot

Les clients et les fournisseurs de solutions Microsoft Cloud peuvent désormais inscrire des appareils HoloLens 2 en envoyant directement des demandes au Support Microsoft. Cette page décrit les conditions requises pour les scénarios d'inscription AutoPilot pris en charge suivants :

- **Inscription AutoPilot d'appareils HoloLens 2**. Envoie une demande d'inscription d'appareils HoloLens 2 dans Windows Autopilot.
- **Demande de hachage matériel d'appareils HoloLens 2**. Envoie au Support Microsoft une demande de hachages matériels que les clients ou fournisseurs de solutions Cloud peuvent utiliser pour inscrire eux-mêmes des appareils via Microsoft Intune ou l'Espace partenaires Microsoft.
- **Désinscription AutoPilot d'appareils HoloLens 2**. Envoie une demande de suppression d'appareils de Windows Autopilot (généralement dans les scénarios de fin de vie des appareils).

Le tableau suivant détaille les informations que vous devrez collecter *avant* d'adresser des demandes d'inscription au Support Microsoft.

| Informations requises | Description | Inscription AutoPilot  | Demande de hachage matériel | Désinscription Autopilot |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  ID de locataire Azure Active Directory    |    Votre ID de locataire Azure Active Directory est un identificateur global unique (GUID) différent du nom ou du domaine de votre organisation.    Pour accéder à votre ID de locataire, connectez-vous au [portail Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).    |     ✔️                         |                              |                         ✔️                        |
|  Nom de domaine Azure Active Directory    |   Votre nom de domaine de premier niveau ; par exemple, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Preuve de propriété    |   Confirmez que les appareils vous appartiennent en chargeant l'original du contrat de vente ou de la facture au format PDF. Les captures d'écran ne sont pas acceptées. Le contrat de vente ou la facture doit inclure ce qui suit : numéros de série des appareils. Nom de la société     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Numéros de série des appareils    |   Chargez au format CSV le fichier Excel contenant les numéros de série de chaque appareil sur une ligne distincte.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Envoyer les demandes de prise en charge

> [!div class="nextstepaction"]
> [Envoyer la prise en charge de l'inscription AutoPilot pour HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
