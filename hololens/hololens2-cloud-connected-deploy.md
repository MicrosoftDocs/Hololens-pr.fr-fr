---
title: Guide de déploiement – Déploiement HoloLens 2 connecté au cloud à l’échelle avec Remote Assist - Déployer
description: Découvrez comment valider l’inscription et Remote Assist pour les appareils HoloLens sur un réseau connecté au cloud.
keywords: HoloLens, gestion, cloud connecté, Remote Assist, AAD, Azure AD, MDM, Gestion des appareils mobiles
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282935"
---
# Déployer - Guide connecté au cloud

Maintenant que tout est configuré, vous devez être prêt à distribuer des appareils. Toutefois, c’est maintenant que vous devez valider votre configuration pour la première fois. Tout d’abord, le processus azure AD Join et d’inscription MDM doit être validé, puis vérifiez qu’un appel Remote Assist peut être passé.

## Validation de l’inscription

Maintenant que tout est correctement configuré pour Azure AD et l’inscription MDM, le reste doit maintenant être un logiciel enfichable. Vous&#39;besoin d’une connexion Wi-Fi et de l’appareil HoloLens, ainsi que de l’un des comptes d’utilisateur AAD précédemment configurés.

Si votre appareil n&#39;pas actuellement dans un état de paramètres d’usine, il est temps de le [réessaier.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Une fois que votre appareil est en OOBE,&#39;devez commencer à interagir et à suivre les invites. 
1. L’invite critique sera lorsque vous serez invité à **qui appartient ce HoloLens ?** Sélectionnez **Mon entreprise ou mon établissement scolaire et** entrez vos informations d’identification de compte Azure AD.
1. Lorsque l’inscription réussit,&#39;êtes invité à configurer un code confidentiel. Ce code confidentiel est propre à cet appareil pour cet utilisateur. Vous serez également invité à effectuer des analyses de l’iris, des données vocales et des paramètres de télémétrie. Enfin, vous&#39;serez en mesure d’ouvrir le menu Démarrer et de terminer la OOBE.
1. Une fois que vous êtes arrivé dans la maison virtuelle, ouvrez le menu Démarrer à l’aide **du** mouvement Démarrer que vous avez appris.
1. Sélectionnez **l’application Paramètres,** puis **Système.** La première information que vous&#39;voir est le nom de votre appareil, qui pour votre appareil HoloLens 2 sera HOLOLENS suivi d’une chaîne de &quot; &quot; six caractères.
1. Prenez note de ce nom.

![Paramètres HoloLens 2 - À propos de](./images/hololens2-settings-about.jpg)

7. Vous pouvez vérifier que votre appareil est correctement inscrit dans Azure AD dans l’application Paramètres. Dans **Paramètres,** **sélectionnez Accès**aux  ->  **comptes, scolaire ou scolaire.** À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en voyant &quot; Connected to _nameofAAD_&#39;azure AD. Connecté par _le nom de yourusernameofAAD_ @ __.onmicrosoft.com &quot; .


Pour vérifier que l’appareil est joint à Azure AD, nous pouvons vérifier Azure Active Directory à partir du portail [Azure](https://portal.azure.com/#home)Active Directory Devices All devices et rechercher le nom  ->  ****  ->  ****  ->  **** de l’appareil. Vous&#39;pouvez voir que l’appareil fait partie d’Azure Active Directory.


![Azure Active Directory - Appareil](./images/aad-enrollment.png)

Ensuite,&#39;devez vous connecter au Centre d’administration [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Connectez-vous et **sélectionnez Appareils,** **puis Tous les appareils.** À partir de là, vous pouvez rechercher votre appareil HoloLens&#39;nom. Vous devriez être en mesure de voir votre HoloLens répertorié sur Intune.

![Intune - Appareil](./images/endpoint-all-devices-enrolled.png)

## Validation d’appel d’assistance à distance

Une fois que&#39;avez vérifié que votre appareil est inscrit à la fois dans votre AAD et dans la gestion des périphériques de gestion des périphériques, il est&#39;de tester un appel d’assistance à distance. Pour cette validation,&#39;devez avoir l’appareil HoloLens et un PC Windows 10, ainsi qu’un deuxième compte d’utilisateur Azure AD pour le PC.

Cette étape de validation suppose que vous avez déjà effectué la dernière étape de validation et que votre appareil est inscrit et que votre utilisateur Azure AD est sur l’appareil.


1. Si Microsoft Teams n’est pas déjà installé sur votre PC, vous pouvez [télécharger Teams ici.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Connectez-vous à Teams à l’aide du deuxième compte d’utilisateur Azure AD que celui actuellement associé à votre HoloLens. Une fois que vous êtes inscrit sur votre PC, vous êtes prêt à recevoir l’appel.
3. Déverrouillez votre HoloLens et connectez-vous.
4. Pour lancer l’application Remote Assist, ouvrez **le menu Démarrer** et sélectionnez Remote **Assist**. Remote Assist n’est pas seulement regroupé en tant qu’application de boîte de réception, mais il est épinglé au menu démarrer&#39;HoloLens 2. Dans un cas où vous ne le&#39;pas épinglé **** au menu Démarrer, ouvrez la liste Toutes les applications pour la rechercher.
5. Une fois l’assistance à distance démarre, elle doit identifier l’utilisateur de l’appareil via [sso](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) et se connecter à l’application.
6. À partir de l’application, **sélectionnez Rechercher** et recherchez le deuxième utilisateur sur le PC. Sélectionnez l’utilisateur pour démarrer l’appel.
7. À partir de votre PC, répondez à l’appel.

Félicitations, vous&#39;vous êtes connecté et êtes sur votre appel d’assistance à distance. Veillez à tester des fonctionnalités d’assistance à distance spécifiques, telles que l’utilisation de :

- [Annotations manuscrites](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Partager un fichier et un affichage en réalité mixte](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtenir de l’aide dans une autre application HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au cloud : maintenir](hololens2-cloud-connected-maintain.md)