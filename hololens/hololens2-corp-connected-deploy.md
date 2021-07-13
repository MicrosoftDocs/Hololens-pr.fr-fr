---
title: Guide de déploiement – connexion à l’entreprise HoloLens 2 avec Dynamics 365 Guides-Deploy
description: découvrez comment configurer des déploiements de HoloLens 2 appareils sur un réseau connecté à l’entreprise avec Dynamics 365 Guides.
keywords: HoloLens, gestion, connecté à l’entreprise, Dynamics 365 Guides, AAD, Azure AD, MDM, gestion des appareils mobiles
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637062"
---
# <a name="deploy---corporate-connected-guide"></a>Deploy-Guide connecté à l’entreprise

Une partie importante de chaque déploiement consiste à vous assurer que votre déploiement est correctement configuré avant de le tester vous-même afin de garantir une expérience sans heurts à l’utilisateur final.

étant donné que nous déployons le certificat Wi-Fi via MDM, nous devrons configurer initialement HoloLens et inscrire des appareils sur un réseau Wi-Fi ouvert, ou sur un réseau qui n’a pas besoin du certificat. une fois que le HoloLens a terminé l’OOBE et l’inscription, l’appareil reçoit le certificat réseau et le LOB configurés précédemment et nous pourrons valider les deux à la fois par l’appareil.

Ensuite, vous serez en mesure de confirmer que vous pouvez créer et utiliser un guide de test.

## <a name="enrollment-validation"></a>Validation de l’inscription

Maintenant que tout est correctement configuré pour l’inscription Azure AD et MDM, le reste doit maintenant être un composant logiciel enfichable. vous devez disposer d’une connexion Wi-Fi et du périphérique HoloLens, ainsi que de l’un des comptes d’utilisateur Azure AD configurés précédemment.

Si votre appareil n’est pas actuellement dans un état des paramètres d’usine, il est maintenant judicieux de [le](/hololens/hololens-recovery#clean-reflash-the-device)refaire.

1. Une fois que votre appareil est dans OOBE, vous devez commencer à interagir et à suivre les invites.

2. Connecter à un réseau Wi-Fi ouvert qui ne requiert pas de certificats pour rejoindre le Wi-Fi. Cela permettra à l’appareil de télécharger le certificat à utiliser sur le Wi-Fi de l’Organisation après l’installation initiale.

3. l’invite critique s’affiche lorsque vous êtes invité **Qui possède ce HoloLens ?** Sélectionnez **mon entreprise ou établissement scolaire en est propriétaire** , puis entrez vos informations d’identification de compte Azure ad.

4. Lorsque l’inscription est réussie, vous êtes invité à configurer un code PIN. Ce code PIN est propre à cet appareil pour cet utilisateur. Vous serez également invité à entrer des analyses d’IRIS, des données vocales et des paramètres de télémétrie. Enfin, vous serez en mesure d’ouvrir le menu Démarrer et d’exécuter OOBE.

5. une fois que vous êtes dans la réalité mixte, ouvrez le menu Démarrer à l’aide du **geste de départ** que vous venez d’apprendre.

6. sélectionnez l’application **Paramètres** et sélectionnez **système**. la première information que vous verrez est le nom de votre appareil, qui, pour votre appareil HoloLens 2, est &quot; HoloLens- &quot; suivi d’une chaîne de six caractères.

7. Prenez note de ce nom.

    ![écran de Paramètres HoloLens 2](./images/hololens2-settings-about.jpg)

8. Vérifiez que votre appareil est correctement joint à Azure AD. Il existe deux façons de procéder :

    1.  application Paramètres. dans **Paramètres** sélectionnez **comptes**  ->  **accéder à l’entreprise ou à l’école**. À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en vous &quot; connectant à nameofAAD&#39;s Azure ad. Connecté par *yourusername@nameofAAD.onmicrosoft.com* . Cela permet de vérifier que votre appareil est joint à votre organisation&#39;s Azure AD.

    1. Le [portail Azure](https://portal.azure.com/#home). accédez à **Azure Active Directory**  ->  **appareils**  ->  **tous les appareils**, puis recherchez le nom de l’appareil. Sous type de jointure, il s’affiche comme étant « Azure AD jointe ».
        ![Vérifier le type de jointure dans Azure AD](./images/hololens2-devices-all-devices.png)

9. Vérifiez que votre appareil est inscrit auprès de MDM. Il existe deux façons de procéder :

    1. dans **Paramètres**, sélectionnez **comptes**  ->  **accéder à l’entreprise ou à l’école**. À partir de cet écran, vous pouvez vérifier que vous êtes correctement inscrit en vous &quot; connectant à nameofAAD&#39;s Azure ad. Connecté par *yourusername@nameofAAD.onmicrosoft.com* . À partir de ce compte d’accès professionnel ou scolaire, sélectionnez &quot; connecté à nameofAAD&#39;s Azure ad. Connecté par yourusername@nameofAAD.onmicrosoft.com &quot; et sélectionnez le bouton **info** .

    1. [Microsoft Endpoint Manager le centre d’administration](https://endpoint.microsoft.com/#home). Connectez-vous et sélectionnez  **appareils**  , puis  **tous les appareils**. à partir de là, vous pouvez rechercher le nom de votre appareil HoloLens&#39;s. vous devriez être en mesure de voir votre HoloLens listé sur Intune.

        ![Vérifier géré par Intune dans Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Validation de certificat Wi-Fi

À l’heure actuelle, l’appareil doit avoir reçu le certificat Wi-Fi. La validation la plus simple consiste à tenter de se connecter à la connexion Wi-Fi pour laquelle vous&#39;reçu le certificat. ouvrez l’application **Paramètres** et accédez à **réseau &amp; Internet**  ->  **wi-fi** et sélectionnez la connexion wi-fi. une fois connecté, ouvrez l’application Microsoft Edge et confirmez que vous pouvez accéder à un site web.

Pour confirmer que vous avez reçu le certificat sur l’appareil, vous pouvez utiliser le [Gestionnaire de certificats](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Valider l’installation de l’application métier

pour voir la progression de l’installation d’une application gérée, vous pouvez voir si l’application est installée ou vérifier Paramètres. si vous configurez une application métier en tant qu’installation requise pour notre groupe, après avoir inscrit le HoloLens auprès d’un utilisateur du groupe affecté, l’application est automatiquement téléchargée vers le HoloLens.

ouvrez le menu Démarrer, puis sélectionnez **toutes les applications**. Selon le nombre d’applications dont vous disposez, vous devrez peut-être utiliser les boutons **page précédente** ou **page suivante** .

pour valider l’installation de l’application sur l’appareil, vous pouvez le faire via **Paramètres**  ->  **comptes**  ->  **accès professionnel ou scolaire**; sélectionnez le compte, puis le bouton **Info** et faites défiler vers le niveau pour afficher les différentes configurations et applications appliquées à l’appareil à partir de MDM.

Pour valider l’installation à partir d’Intune, accédez à la page applications du [portail MEM](https://endpoint.microsoft.com/#home)  ->   -> toutes les **applications** TheNameOfYourApp de l’installation de l'  ->   ->  **appareil** .

En savoir plus : [déploiement d’applications Intune pour HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Valider Dynamics 365 Guides

il existe des modes pour l’application Guides sur HoloLens, la création et le fonctionnement. Vous devez terminer la création d’un guide avant de l’utiliser.

### <a name="authoring-the-guide"></a>Création du Guide

Nous n’avons pas besoin de faire grand chose pour cette validation rapide. Il vous suffit de sélectionner le guide que vous avez préparé sur votre PC. Vous devez [ancrer le guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), pour une validation rapide, vous pouvez utiliser une ancre holographique. Ensuite, vous devez [placer vos étapes et vos modèles](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Vous aurez besoin du rôle de **création** pour vous connecter à l’ordinateur et de l’auteur sur le HoloLens. Le rôle opérateur est en lecture seule et n’a pas accès à l’application PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Utilisation du Guide

Une fois vos hologrammes en place, vous pouvez tester le fonctionnement de votre guide. 
- Sélectionner le **mode d’opérateur**
- Cliquez sur les étapes de votre guide.

Pour obtenir des conseils détaillés sur l’utilisation d’un guide, consultez les ressources suivantes :

[Vue d’ensemble de l’utilisation d’un guide dans Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-overview)

[Accédez à l’aide de la carte d’étape en tant qu’opérateur dans Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté d’entreprise-gérer](hololens2-corp-connected-maintain.md)
