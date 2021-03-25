---
title: Guide de déploiement – HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Déployer
description: Découvrez comment configurer des déploiements d’appareils HoloLens 2 sur un réseau connecté d’entreprise à l’aide des guides Dynamics 365.
keywords: HoloLens, gestion, connecté à l’entreprise, guides Dynamics 365, AAD, Azure AD, GESTION DES PÉRIPHÉRIQUES MOBILES, Gestion des appareils mobiles
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448545"
---
# <a name="deploy---corporate-connected-guide"></a>Déployer - Guide connecté à l’entreprise

Une partie importante de chaque déploiement consiste à s’assurer que votre déploiement est correctement installé avant de le tester vous-même afin de garantir une expérience fluide pour l’utilisateur final.

Étant donné que nous déployons le certificat Wi-Fi via la gestion des périphériques mobiles, nous devons d’abord configurer HoloLens et inscrire les appareils sur un réseau Wi-Fi ouvert ou sur un réseau qui ne nécessite pas le certificat. Une fois l’holoLens OOBE et inscrit, l’appareil reçoit le certificat réseau et le LOB configurés précédemment, et nous pouvons valider que les deux ont été reçus par l’appareil.

Par la suite, vous serez en mesure de confirmer que vous pouvez à la fois auteur et utiliser un guide de test.

## <a name="enrollment-validation"></a>Validation de l’inscription

Maintenant que tout est correctement configuré pour Azure AD et l’inscription MDM, le reste doit maintenant être un logiciel enfichable. Vous aurez besoin d’une connexion Wi-Fi et de l’appareil HoloLens, ainsi que de l’un des comptes d’utilisateur Azure AD précédemment configurés.

Si votre appareil n’est pas actuellement dans un état de paramètres d’usine, il est temps de le [réesseriller.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Une fois que votre appareil est en OOBE, vous devez commencer à interagir et à suivre les invites.

2. Connectez-vous à un réseau Wi-Fi ouvert qui ne nécessite pas de certificats pour rejoindre le Wi-Fi. Cela permet à l’appareil de télécharger le certificat à utiliser sur les ordinateurs de l'Wi-Fi après la configuration initiale.

3. L’invite critique sera lorsque vous serez invité à **qui appartient ce HoloLens ?** Sélectionnez **Mon entreprise ou mon établissement scolaire et** entrez vos informations d’identification de compte Azure AD.

4. Lorsque l’inscription réussit, vous êtes invité à configurer un code confidentiel. Ce code confidentiel est propre à cet appareil pour cet utilisateur. Vous serez également invité à effectuer des analyses de l’iris, des données vocales et des paramètres de télémétrie. Enfin, vous serez en mesure d’apprendre à ouvrir le menu Démarrer et à terminer la OOBE.

5. Une fois que vous êtes arrivé dans la maison de réalité mixte, ouvrez le menu Démarrer à l’aide **du** mouvement Démarrer que vous avez appris.

6. Sélectionnez **l’application Paramètres** et sélectionnez **Système.** La première information que vous verrez est le nom de votre appareil, qui pour votre appareil HoloLens 2 sera HOLOLENS, suivi d’une chaîne &quot; &quot; de six caractères.

7. Prenez note de ce nom.

    ![Écran Paramètres HoloLens 2](./images/hololens2-settings-about.jpg)

8. Vérifiez que votre appareil est correctement joint à Azure AD. Il existe deux façons :

    1.  Application Paramètres. Dans **Paramètres,** **sélectionnez Accès**aux  ->  **comptes, scolaire ou scolaire.** À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en voyant &quot; Connected to nameofAAD&#39;azure AD. Connecté par *yourusername@nameofAAD.onmicrosoft.com*. Cela permet de vérifier que votre appareil est joint à votre organisation&#39;Azure AD.

    1. Le [portail Azure](https://portal.azure.com/#home). Go to **Azure Active Directory**  ->  **Devices**  ->  **All devices**, and search the device name. Sous Join Type, il s’affiche comme étant « Joint à Azure AD ».
        ![Vérifier le type d’adhésion dans Azure AD](./images/hololens2-devices-all-devices.png)

9. Vérifiez que votre appareil est inscrit auprès de la gestion des périphériques de gestion des périphériques. Il existe deux façons :

    1. À partir **des paramètres,** sélectionnez Accès aux ****  ->  **comptes, scolaire ou scolaire.** À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en voyant &quot; Connected to nameofAAD&#39;azure AD. Connecté par *yourusername@nameofAAD.onmicrosoft.com*. À partir de ce compte scolaire ou scolaire Access, sélectionnez &quot; Connected to nameofAAD&#39;azure AD. Connecté par yourusername@nameofAAD.onmicrosoft.com &quot; et sélectionnez le **bouton Informations.**

    1. [Centre d’administration Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Connectez-vous et **sélectionnez Appareils,** **puis Tous les appareils.** À partir de là, vous pouvez rechercher votre appareil HoloLens&#39;nom. Vous devriez être en mesure de voir votre HoloLens répertorié sur Intune.

        ![Vérifier la gestion par Intune dans Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi validation de certificat

À l’heure actuelle, l’appareil doit avoir reçu Wi-Fi certificat. La validation la plus simple consiste à essayer de vous connecter à la connexion Wi-Fi pour laquelle vous&#39;reçu le certificat. Ouvrez **l’application Paramètres,** accédez au Réseau ** &amp; Internet**  ->  **Wi-Fi** et sélectionnez la connexion Wi-Fi. Une fois connecté, ouvrez l’application Microsoft Edge et confirmez que vous pouvez accéder à un site web.

Pour confirmer que vous avez reçu le certificat sur l’appareil, vous pouvez utiliser le Gestionnaire [de certificats.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Valider l’installation de l’application LOB

Pour voir la progression de l’installation d’une application gérée, vous pouvez voir si l’application est installée ou vérifier les paramètres. En configurant une application LOB en tant qu’installation requise pour notre groupe, après l’inscription de HoloLens auprès d’un utilisateur dans le groupe affecté, l’application se télécharge automatiquement sur HoloLens.

Ouvrez le menu Démarrer et sélectionnez **Toutes les applications.** Selon le nombre d’applications dont vous avez besoin, vous devrez peut-être utiliser les boutons **Page** haut **ou Page suivante.**

Pour valider l’installation de l’application sur l’appareil, vous pouvez le faire via l’accès aux comptes **Paramètres**Accès au travail ou à l’établissement scolaire ; sélectionnez le compte, puis le bouton Informations, puis faites défiler vers le bas pour voir les différentes configurations et applications appliquées à l’appareil à partir de la gestion des périphériques  ->  ****  ->  **** mobiles. ****

Pour valider l’installation à partir d’Intune, accédez à la page d’état d’installation de l’appareil du portail [MEM](https://endpoint.microsoft.com/#home)-> Toutes les applications  ->  **** ****  -> *TheNameOfYourApp*Device  ->  **Install.**

En savoir plus : [Déploiement d’applications Intune pour HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Valider les guides Dynamics 365

Il existe des modes pour l’application Guides sur HoloLens, la authoring et le fonctionnement. Vous devez terminer la auteur d’un guide avant de l’exploiter.

### <a name="authoring-the-guide"></a>Auteur du Guide

Nous n’avons pas besoin de faire grand chose pour cette validation rapide. Sélectionnez simplement le guide que vous avez préparé sur votre PC. Vous devez ancrer [le guide,](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)pour une validation rapide, vous pouvez utiliser un ancrage holographique. Ensuite, vous devez [placer vos étapes et modèles.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Vous aurez besoin du **rôle de authoring** pour vous connecter au PC et à l’auteur sur holoLens. Le rôle Opérateur est en lecture seule et n’a pas accès à l’application PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Fonctionnement du Guide

Une fois vos hologrammes en place, vous pouvez tester l’utilisation de votre guide. 
- Sélectionner **le mode Opérateur**
- Cliquez sur les étapes de votre guide.

Pour obtenir des instructions plus détaillées sur l’exploitation d’un guide, consultez les ressources ci-après :

[Vue d’ensemble de l’utilisation d’un guide dans les guides Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Orientation avec la carte Pas à pas en tant qu’opérateur dans les guides Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté à l’entreprise - Maintenance](hololens2-corp-connected-maintain.md)
