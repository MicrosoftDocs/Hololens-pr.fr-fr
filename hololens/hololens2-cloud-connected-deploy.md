---
title: Guide de déploiement-déploiement d’HoloLens 2 sur le Cloud connecté à la mise à l’échelle via Remote Assist-déploiement
description: Valider les inscriptions et l’assistance à distance pour les appareils HoloLens sur un réseau connecté sur le Cloud
keywords: HoloLens, gestion, Cloud connecté, assistance à distance, AAD, Azure AD, GPM, gestion des appareils mobiles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196301"
---
# Déploiement-Guide connecté dans le Cloud

Maintenant que tout est configuré, vous devez être prêt à distribuer les appareils. Néanmoins, c’est la première fois que vous devez valider votre configuration. Tout d’abord, le processus d’inscription de AAD et de GPM doit être validé, puis vérifier qu’un appel d’assistance à distance peut être placé.

## Validation de l’inscription

Tout ce qui est configuré correctement pour l’inscription AAD et de la gestion des périphériques mobiles doit maintenant être un élément d’alignement. Vous&#39;avoir besoin d’une connexion Wi-Fi et de l’appareil HoloLens, ainsi que de l’un des comptes d’utilisateurs AAD déjà configurés.

Si votre appareil n’est pas&#39;ne se trouve pas dans un état de paramètres d’usine, c’est le moment de refaire [clignoter l’appareil](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Lorsque votre appareil est dans OOBE, vous&#39;devez commencer à interagir et à suivre les invites. 
1. Vous serez invité à indiquer qui est propriétaire de **ce HoloLens?** Sélectionnez **mon entreprise ou mon établissement scolaire propriétaire** , puis entrez les informations d’identification de votre compte AAD.
1. Lorsque l’inscription est réussie, vous&#39;êtes invité à configurer un code confidentiel. Ce périphérique est unique pour cet utilisateur. Vous serez également invité à entrer les paramètres d’examen par Iris, de données audio et de télémétrie, et enfin, vous&#39;découvrir comment ouvrir le menu Démarrer et compléter OOBE.
1. Lorsque vous débarquez dans la page d’accueil de la réalité, ouvrez le menu démarrer en utilisant le **geste de début** que vous venez d’apprendre. 
1. Sélectionnez l’application **paramètres** , puis **système.** Le premier type d’informations que vous&#39;voir est le nom de votre appareil, lequel pour votre appareil HoloLens 2 sera &quot; &quot; appliqué par hololens, suivi d’une chaîne à 6 caractères. 
1. Prenez note de ce nom.

![Paramètres HoloLens 2-à propos de](./images/hololens2-settings-about.jpg)

7. Vous pouvez vérifier que votre appareil est correctement inscrit dans le système AAD au sein de l’application paramètres. Dans **paramètres** , **Accounts**sélectionnez  ->  **accès aux comptes professionnel ou scolaire**. À partir de cet écran, vous pouvez vérifier que votre inscription s’est déroulée correctement en vous &quot; connectant à _nameofAAD_&#39;s Azure ad. Connecté par _yourusername_ @ _nameofAAD_. onmicrosoft.com &quot; .

Pour vérifier que l’appareil a rejoint AAD, nous pouvons vérifier l’annuaire Azure Active Directory sur le [portail](https://portal.azure.com/#home)Azure  ->  **Active Directory**  ->  **périphériques**  ->  **tous les appareils** et rechercher le nom de l’appareil. Vous&#39;être en mesure de voir l’appareil fait partie d’Azure Active Directory.

![Azure Active Directory-appareil](./images/aad-enrollment.png)

Ensuite, vous&#39;devez vous connecter au [Centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Connectez-vous et sélectionnez **périphériques** , puis **tous les appareils**. À partir de cet emplacement, vous pouvez effectuer une recherche sur votre appareil HoloLens&#39;nom s. Vous devriez être en mesure de voir votre HoloLens répertorié sur Intune.

![Intune-appareil](./images/endpoint-all-devices-enrolled.png)

## Validation des appels d’assistance à distance

Une fois que vous avez&#39;vérifié que votre appareil est inscrit à votre application AAD et à la gestion des périphériques mobiles, il&#39;temps de passer un appel de test d’assistance à distance. Pour cette validation, vous&#39;utiliser le périphérique HoloLens et un PC Windows 10, ainsi qu’un second compte d’utilisateur AAD pour le PC.

Cette étape de validation suppose que vous avez déjà effectué la dernière étape de validation et que votre appareil est inscrit et que votre utilisateur AAD est sur l’appareil.

1. Si&#39;vous n’avez pas encore installé Microsoft teams sur votre PC, vous pouvez [Télécharger teams ici](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Connectez-vous à teams à l’aide du deuxième compte d’utilisateur AAD et de celui actuellement connecté à votre HoloLens. Lorsque vous êtes connecté (e) à votre ordinateur, vous pouvez recevoir l’appel.
3. Déverrouillez votre HoloLens et connectez-vous.
4. Pour lancer l’application Remote Assist, ouvrez le **menu Démarrer** , puis sélectionnez **assistance à distance**. L’assistance à distance n’est pas seulement une application de boîte de réception, mais elle est épinglée au menu Démarrer de HoloLens 2&#39;. Dans le cas d’un événement que vous n’avez pas&#39;qu’il n’est pas épinglé au menu Démarrer, ouvrez la liste **toutes les applications** pour le Rechercher.
5. Dès qu’une assistance à distance est lancée, elle doit identifier l’utilisateur de l’appareil via l' [authentification unique](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) et se connecter à l’application.
6. À partir de l’application, sélectionnez **Rechercher** , puis recherchez le second utilisateur sur le PC. Sélectionnez l’utilisateur pour démarrer l’appel.
7. Sur votre PC, répondez à l’appel.

Félicitations, vous&#39;que vous avez réussi à vous connecter et à votre appel d’assistance à distance. Prenez soin de tester les fonctionnalités d’assistance à distance spécifiques, telles que l’utilisation de:

- [Annotations d’entrée manuscrite](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Partager un fichier et afficher en environnement mixte](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtenir de l’aide dans une autre application HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté dans le Cloud-maintenance](hololens2-cloud-connected-maintain.md)