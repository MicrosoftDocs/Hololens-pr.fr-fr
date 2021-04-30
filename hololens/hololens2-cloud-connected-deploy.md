---
title: Guide de déploiement – déploiement d’un système HoloLens 2 connecté au Cloud à grande échelle avec l’assistance à distance-déployer
description: Découvrez comment valider l’inscription et l’assistance à distance pour les appareils HoloLens sur un réseau connecté au Cloud.
keywords: HoloLens, gestion, Cloud connected, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308940"
---
# <a name="deploy---cloud-connected-guide"></a>Déployer-Guide connecté au Cloud

Maintenant que tout est configuré, vous devez être prêt à distribuer des appareils. Toutefois, c’est à présent que vous devez d’abord valider votre configuration. Tout d’abord, le processus d’inscription de la Azure AD et de la gestion des appareils mobiles doit être validé, puis vérifier qu’un appel d’assistance à distance peut être placé.

## <a name="enrollment-validation"></a>Validation de l’inscription

Maintenant que tout est correctement configuré pour l’inscription Azure AD et MDM, le reste doit maintenant être un composant logiciel enfichable. Vous&#39;avoir besoin d’une connexion Wi-Fi et de l’appareil HoloLens, ainsi que de l’un des comptes d’utilisateur AAD configurés précédemment.

Si votre appareil n’est pas&#39;qui se trouve actuellement dans un état des paramètres de la fabrique, il est judicieux de [le réinitialiser](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Une fois que votre appareil est en OOBE, vous&#39;faire interagir et suivre les invites. 
1. L’invite critique est quand vous êtes invité à **qui est propriétaire de l’HoloLens ?** Sélectionnez **mon entreprise ou établissement scolaire en est propriétaire** , puis entrez vos informations d’identification de compte Azure ad.
1. Lorsque l’inscription est réussie, vous&#39;ll est invité à configurer un code confidentiel. Ce code PIN est propre à cet appareil pour cet utilisateur. Vous serez également invité à entrer des analyses d’IRIS, des données vocales et des paramètres de télémétrie. Enfin, vous&#39;être en mesure d’ouvrir le menu Démarrer et d’exécuter OOBE.
1. Une fois que vous êtes dans la réalité mixte, ouvrez le menu Démarrer à l’aide du **geste de départ** que vous venez d’apprendre.
1. Sélectionnez l’application **paramètres** et sélectionnez **système.** La première information que vous&#39;ll est le nom de votre appareil, lequel est appliqué à votre appareil HoloLens 2, &quot; &quot; suivi d’une chaîne de six caractères.
1. Prenez note de ce nom.

![Paramètres HoloLens 2-à propos de](./images/hololens2-settings-about.jpg)

7. Vous pouvez vérifier que votre appareil est correctement inscrit dans le Azure AD dans l’application paramètres. Dans **paramètres** , sélectionnez **comptes**  ->  **accéder à l’entreprise ou à l’école**. À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en vous &quot; connectant à _nameofAAD_&#39;s Azure ad. Connecté par _yourusername_ @ _nameofAAD_. onmicrosoft.com &quot; .


Pour valider que l’appareil n’a Azure ad joint, nous pouvons vérifier le Azure Active Directory à partir du [portail Azure](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **appareils**  ->  **tous les appareils**, puis rechercher le nom de l’appareil. Vous&#39;ll sera en mesure de voir que l’appareil fait partie du Azure Active Directory.


![Azure Active Directory-appareil](./images/aad-enrollment.png)

Ensuite, vous&#39;devez vous connecter au [Centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Connectez-vous et sélectionnez **appareils** , puis **tous les appareils**. À partir de là, vous pouvez rechercher le nom de votre appareil HoloLens&#39;s. Vous devriez être en mesure de voir votre HoloLens listé sur Intune.

![Intune-appareil](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validation de l’appel d’assistance à distance

Une fois que vous avez&#39;vérifié que votre appareil est inscrit à la fois dans AAD et MDM, il&#39;temps de passer un appel d’assistance à distance test. Pour cette validation, vous&#39;devez avoir l’appareil HoloLens et un PC Windows 10, ainsi qu’un deuxième compte d’utilisateur Azure AD pour le PC.

Cette étape de validation suppose que vous avez déjà effectué la dernière étape de validation et que votre appareil est inscrit et que votre Azure AD utilisateur se trouve sur l’appareil.


1. Si vous n’avez pas encore installé Microsoft teams sur votre PC, vous pouvez [Télécharger des équipes ici](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Connectez-vous à teams à l’aide du deuxième Azure AD compte d’utilisateur que celui actuellement connecté à votre HoloLens. Une fois que vous êtes connecté à votre PC, vous êtes prêt à recevoir l’appel.
3. Déverrouillez votre HoloLens et connectez-vous.
4. Pour lancer l’application assistance à distance, ouvrez le **menu Démarrer** et sélectionnez **assistance à distance**. L’assistance à distance n’est pas regroupée en tant qu’application de boîte de réception, mais épinglée au menu Démarrer HoloLens 2&#39;s. Dans un événement,&#39;vous ne voyez pas s’afficher épinglé dans le menu Démarrer, puis ouvrez la liste **toutes les applications** pour le Rechercher.
5. Une fois que l’assistance à distance est lancée, elle doit identifier l’utilisateur de l’appareil par le biais de l' [authentification unique](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) et se connecter à l’application.
6. À partir de l’application, sélectionnez **Rechercher** et recherchez le deuxième utilisateur sur le PC. Sélectionnez l’utilisateur pour démarrer l’appel.
7. À partir de votre PC, répondez à l’appel.

Félicitations, vous&#39;correctement connecté et êtes sur votre appel à distance Assist. Veillez à essayer des fonctionnalités d’assistance à distance spécifiques, telles que l’utilisation de :

- [Annotations manuscrites](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Partager un fichier et afficher en réalité mixte](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtenir de l’aide dans une autre application HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au Cloud-gérer](hololens2-cloud-connected-maintain.md)