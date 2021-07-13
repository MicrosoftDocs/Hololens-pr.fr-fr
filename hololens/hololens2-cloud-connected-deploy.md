---
title: Guide de déploiement – Cloud connecté HoloLens 2 déploiement à grande échelle avec l’assistance à distance-déployer
description: découvrez comment valider l’inscription et l’assistance à distance pour HoloLens appareils sur un réseau connecté au Cloud.
keywords: HoloLens, gestion, cloud connecté, assistance à distance, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635175"
---
# <a name="deploy---cloud-connected-guide"></a>Déployer-Guide connecté au Cloud

Maintenant que tout est configuré, vous devez être prêt à distribuer des appareils. Toutefois, c’est à présent que vous devez d’abord valider votre configuration. Tout d’abord, le processus d’inscription de la Azure AD et de la gestion des appareils mobiles doit être validé, puis vérifier qu’un appel d’assistance à distance peut être placé.

## <a name="enrollment-validation"></a>Validation de l’inscription

Maintenant que tout est correctement configuré pour l’inscription Azure AD et MDM, le reste doit maintenant être un composant logiciel enfichable. vous&#39;avoir besoin d’une connexion Wi-Fi et du périphérique HoloLens, ainsi que de l’un des comptes d’utilisateur AAD précédemment configurés.

Si votre appareil n’est pas&#39;qui se trouve actuellement dans un état des paramètres de la fabrique, il est judicieux de [le réinitialiser](/hololens/hololens-recovery#clean-reflash-the-device).

1. Une fois que votre appareil est en OOBE, vous&#39;faire interagir et suivre les invites. 
1. l’invite critique s’affiche lorsque vous êtes invité **Qui possède ce HoloLens ?** Sélectionnez **mon entreprise ou établissement scolaire en est propriétaire** , puis entrez vos informations d’identification de compte Azure ad.
1. Lorsque l’inscription est réussie, vous&#39;ll est invité à configurer un code confidentiel. Ce code PIN est propre à cet appareil pour cet utilisateur. Vous serez également invité à entrer des analyses d’IRIS, des données vocales et des paramètres de télémétrie. Enfin, vous&#39;être en mesure d’ouvrir le menu Démarrer et d’exécuter OOBE.
1. une fois que vous êtes dans la réalité mixte, ouvrez le menu Démarrer à l’aide du **geste de départ** que vous venez d’apprendre.
1. sélectionnez l’application **Paramètres** et sélectionnez **système.** la première information que vous&#39;ll est que le nom de votre appareil, qui, pour votre appareil HoloLens 2, sera &quot; HoloLens- &quot; suivi d’une chaîne de six caractères.
1. Prenez note de ce nom.

![HoloLens 2 Paramètres-à propos de](./images/hololens2-settings-about.jpg)

7. vous pouvez vérifier que votre appareil est correctement inscrit dans le Azure AD au sein de l’application Paramètres. dans **Paramètres** sélectionnez **comptes**  ->  **accéder à l’entreprise ou à l’école**. À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en vous &quot; connectant à _nameofAAD_&#39;s Azure ad. Connecté par _yourusername_ @ _nameofAAD_. onmicrosoft.com &quot; .


pour valider que l’appareil n’a Azure AD joint, nous pouvons vérifier le Azure Active Directory à partir du [Portail Azure](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **appareils**  ->  **tous les appareils**, puis rechercher le nom de l’appareil. Vous&#39;ll sera en mesure de voir que l’appareil fait partie du Azure Active Directory.


![Azure Active Directory-appareil](./images/aad-enrollment.png)

ensuite, vous&#39;devez vous connecter au [centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Connectez-vous et sélectionnez **appareils** , puis **tous les appareils**. à partir de là, vous pouvez rechercher le nom de votre appareil HoloLens&#39;s. vous devriez être en mesure de voir votre HoloLens listé sur Intune.

![Intune-appareil](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validation de l’appel d’assistance à distance

Une fois que vous avez&#39;vérifié que votre appareil est inscrit à la fois dans AAD et MDM, il&#39;temps de passer un appel d’assistance à distance test. pour cette validation, vous&#39;devez disposer de l’appareil HoloLens et d’un pc Windows 10, ainsi que d’un deuxième compte d’utilisateur Azure AD pour le pc.

Cette étape de validation suppose que vous avez déjà effectué la dernière étape de validation et que votre appareil est inscrit et que votre Azure AD utilisateur se trouve sur l’appareil.


1. si vous n’avez pas encore Microsoft Teams installé sur votre PC, vous pouvez [télécharger Teams ici](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. connectez-vous à Teams à l’aide du deuxième Azure AD compte d’utilisateur que celui actuellement connecté à votre HoloLens. Une fois que vous êtes connecté à votre PC, vous êtes prêt à recevoir l’appel.
3. déverrouillez votre HoloLens et connectez-vous.
4. Pour lancer l’application assistance à distance, ouvrez le **menu Démarrer** et sélectionnez **assistance à distance**. l’assistance à distance n’est pas regroupée en tant qu’application de boîte de réception, mais épinglée au menu démarrer HoloLens 2&#39;s. dans le cas d’un événement, vous ne voyez pas&#39;t épinglé à l’menu Démarrer, puis ouvrez la liste **toutes les applications** pour le rechercher.
5. Une fois que l’assistance à distance est lancée, elle doit identifier l’utilisateur de l’appareil par le biais de l' [authentification unique](/azure/active-directory/manage-apps/what-is-single-sign-on) et se connecter à l’application.
6. À partir de l’application, sélectionnez **Rechercher** et recherchez le deuxième utilisateur sur le PC. Sélectionnez l’utilisateur pour démarrer l’appel.
7. À partir de votre PC, répondez à l’appel.

Félicitations, vous&#39;correctement connecté et êtes sur votre appel à distance Assist. Veillez à essayer des fonctionnalités d’assistance à distance spécifiques, telles que l’utilisation de :

- [Annotations manuscrites](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Partager un fichier et afficher en réalité mixte](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [obtenir de l’aide dans une autre application de HoloLens](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Étape suivante

> [!div class="nextstepaction"]
> [Déploiement connecté au Cloud-gérer](hololens2-cloud-connected-maintain.md)