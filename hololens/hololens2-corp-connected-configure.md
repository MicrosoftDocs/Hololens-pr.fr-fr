---
title: Guide de déploiement - HoloLens 2 connecté à l’entreprise avec les guides Dynamics 365 - Configurer
description: Découvrez comment configurer des configurations pour déployer des appareils HoloLens 2 sur un réseau connecté d’entreprise à l’aide des guides Dynamics 365.
keywords: HoloLens, gestion, connexion d’entreprise, guides Dynamics 365, AAD, Azure AD, GESTION DES PÉRIPHÉRIQUES MOBILES, Gestion des appareils mobiles
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448544"
---
# <a name="configure---corporate-connected-guide"></a>Configurer - Guide connecté à l’entreprise

## <a name="azure-users-and-groups"></a>Utilisateurs et groupes Azure

Azure et Intune par cette extension utilisent des utilisateurs et des groupes pour vous aider à attribuer des configurations et des licences. Pour valider ce flux de déploiement et vérifier que vous pouvez auteur et utiliser un guide, vous&#39;besoin d’un compte d’utilisateur.

Nous pouvons faire un seul groupe d’utilisateurs spécifiquement pour l’attribution de licences.

Si vous n'&#39;pas déjà accès à deux comptes Azure AD dans un groupe d’utilisateurs, vous pouvez utiliser ; voici les guides de démarrage rapide pour :

- [Comment créer un utilisateur](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Comment créer un groupe](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Ajouter des utilisateurs à un groupe](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : ajouter des utilisateurs créés pour créer un groupe
- [Configurer Azure AD pour autoriser](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) un groupe d’utilisateurs à joindre des appareils : assurez-vous que le nouveau groupe d’utilisateurs est autorisé à inscrire des appareils dans Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Inscription automatique sur HoloLens 2

Pour que l’expérience soit fluide et transparente, la configuration d’Azure Active Directory Join (AADJ) et de l’inscription automatique à Intune pour les appareils HoloLens 2 est la solution. Cela permet aux utilisateurs d’entrer les informations d’identification de connexion de leur organisation pendant la OOBE, de s’inscrire automatiquement auprès d’Azure AD et d’inscrire l’appareil dans la gestion des périphériques mobiles.

À [l’aide de Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)nous pouvons sélectionner des services et parcourir quelques pages jusqu’à ce que nous sélectionnions Obtenir une version d’évaluation Premium. Vous remarquerez peut-être qu’Azure Active Directory Premium 1 et 2 sont suffisants pour l’inscription automatique P1. Nous pouvons sélectionner Intune et l’étendue utilisateur pour l’inscription automatique et sélectionner le groupe précédemment créé.

Pour obtenir des détails complets et des étapes, lisez le guide sur la façon d’activer l’inscription [automatique pour Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Connectivité Wi-Fi entreprise

Les Wi-Fi d’entreprise nécessitent généralement une authentification basée sur les certificats pour les clients utilisant HoloLens 2. Vous devrez déployer ces certificats à l’aide d’une infrastructure de certificat SCEP (Simple Certificate Enrollment Protocol) ou PKCS (Public Key Cryptography Standard) intégrée à votre solution MDM. L’utilisation d’Intune pour déployer Wi-Fi profils, certificats et paramètres proxy crée une expérience transparente pour les utilisateurs finaux.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Déployer des certificats et des profils Wi-Fi de certificats

Pour déployer des certificats et des profils via Microsoft Endpoint Manager, suivez les étapes suivantes :

1. Créez un profil pour chacun des certificats racines et intermédiaires (voir [Créer des profils de certificats de confiance).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Chacun de ces profils doit avoir une description qui inclut une date d’expiration au format JD/MM/AAA. 

    > [!CAUTION]
    > **Les profils de certificats sans date d’expiration ne seront pas déployés.**

2.  Créer un profil pour chaque certificat SCEP ou PKCS (voir [Créer un profil de certificat SCEP ou Créer un profil de certificat PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Chacun de ces profils doit avoir une description qui comprend une date d'expiration au format JJ/MM/AAAA. 

    > [!CAUTION]
    > **Les profils de certificat sans date d'expiration ne seront pas déployés.**

    > [!Note]
    > Comme HoloLens 2 est considéré pour beaucoup comme un appareil partagé, c’est-à-dire, plusieurs utilisateurs par appareil, il est recommandé de déployer des certificats d’appareil au lieu de certificats d’utilisateur pour l’authentification Wi-Fi lorsque cela est possible.

3.  Créez un profil pour votre réseau Wi-Fi d’entreprise (voir [paramètres Wi-Fi pour les appareils Windows 10 et ultérieurs).](https://docs.microsoft.com/intune/wi-fi-settings-windows) Dans votre profil Wi-Fi, vous pouvez choisir d’utiliser les paramètres proxy au sein de votre organisation.
 
    Vos options :
    - **Aucun**: aucun paramètre proxy n’est configuré.
    - **Configurer manuellement :** entrez l’adresse **IP du serveur proxy** et son numéro de **port.**
    - **Configurer automatiquement : entrez l’URL**pointant vers un script de configuration automatique de proxy (PAC). Par exemple, entrez *http://proxy.contoso.com/proxy.pac* .

    Pour plus d’informations sur les fichiers PAC, voir [fichier PAC (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (ouvre un site non Microsoft).
 
    > [!Note]
    > Il est recommandé d'attribuer le profil Wi-Fi à des groupes  d'appareils plutôt qu'à des groupes d'utilisateurs, dans la mesure du possible.
     
    > [!Tip]
    > Vous pouvez également exporter un profil Wi-Fi fonctionnel à partir d'un ordinateur Windows 10 sur votre réseau corporatif. Cette exportation crée un fichier XML avec tous les paramètres actuels. Ensuite, importez ce fichier dans Intune, et utilisez-le comme profil Wi-Fi pour vos appareils HoloLens 2. Voir [Exporter et importer des Wi-Fi pour les appareils Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

1.  [Affectez](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) les profils d’appareil au groupe d’appareils HoloLens.

2.  [Surveillez](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) les profils d’appareil dans Intune.

En cas de problèmes avec les profils Wi-Fi, référencez résolution des problèmes Wi-Fi profils de [configuration d’appareil dans Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Résolution des problèmes d’accès à Internet externe lorsqu’une entreprise est connectée
Lorsque les services essaient de ne pas passer par un proxy de jeu, ils peuvent tenter de se connecter via le pare-feu. Vous pouvez ajouter une liste de points de terminaison spécifiques à vos règles de pare-feu pour résoudre ces problèmes.

Si vous êtes bloqué sur les ports de pare-feu, activez certains points de [terminaison courants](https://docs.microsoft.com/hololens/hololens-offline) pour HoloLens.

Vous pouvez également activer les ports spécifiques guides : [URL accessibles sur Internet requises](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)pour la connectivité à Microsoft Dynamics CRM Online .

## <a name="app-deployment"></a>Déploiement d’applications

Le déploiement d’une application LOB via la gestion des périphériques mobiles est une méthode facilement évolutive qui peut être déployée automatiquement sur vos appareils lors de l’inscription dans un groupe créé.

Si vous développez toujours vos applications ou si vous n’en avez pas encore, vous pouvez utiliser un exemple d’application du hub d’exemples MRTK. Cet exemple d’application est prêt à être utilisé et ne nécessitera pas l’utilisation d’Unity ou de Visual Studio. [Téléchargez l’exemple d’application MRTK.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Si vous préférez utiliser votre propre application ou si vous êtes intéressé par le développement d’applications pour la réalité mixte, n’hésitez pas à consulter notre documentation pour les développeurs de réalité [mixte.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> La configuration requise pour les appareils HoloLens dépend de l’architecture de la build de l’application. Les appareils HoloLens 2 utilisent ARM architecture. Lorsque vous construisez vos applications dans Visual Studio, assurez-vous que vous avez sélectionné l’architecture correcte pour l’appareil et incluez les dépendances nécessaires.

> [!IMPORTANT]
> Lors du déploiement d’applications LOB, il est important de télécharger également le certificat dans Intune et de l’affecter au même groupe qui est destiné à utiliser l’application, sinon il ne s’installera pas correctement.

### <a name="upload-and-assign-the-app"></a>Charger et affecter l’application

1. Accédez au [Centre d’administration MEM.](https://endpoint.microsoft.com/#home)

2. Sélectionnez ****  ->  **Applications toutes les applications** et **sélectionnez le bouton +** Ajouter.

3. Sous l’autre, **sélectionnez l’application métier.** Cliquez **sur sélectionner.**

4. Sélectionnez le fichier de package d’application, il s’agit de votre fichier APPXBUNDLE, ou dans notre exemple, l’application est _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.

5. Vous serez averti de l’absence de dépendances. Dans ce cas, nous devons télécharger _Microsoft.VCLibs.ARM.14.00.appx_. Recherchez-la sous **Sélectionner un fichier.**

6. Sélectionnez OK.

7. Dans l’écran suivant, les champs obligatoires seront remplis automatiquement. Sélectionnez **Suivant**.

8. Sous Obligatoire, ajoutez notre groupe créé précédemment pour rendre cette application requise pour le groupe. Cela entraîne le téléchargement automatique de l’application sur les appareils inscrits dans le groupe. Sélectionnez **Suivant**.

9. Sélectionnez **Créer**.

En savoir plus : [Attribuer des applications à des groupes dans Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guides d’installation : licences d’application, dataverse et authoring

Pour utiliser les guides Dynamics 365, vous devez préparer l’utilisation. Il existe trois domaines dans lesquels nous devons nous préparer . utilisateurs, dataverse et les guides eux-mêmes.

### <a name="users-and-application-licenses"></a>Utilisateurs et licences d’applications

Pour qu’une personne utilise des guides, elle doit utiliser un compte Azure AD, que nous avons précédemment mis en place dans ce guide.

Vous devez également attribuer une licence Dynamics 365 Guides à l’utilisateur que vous avez créé. Vous allez le faire à partir du Centre d’administration [Microsoft 365.](https://admin.microsoft.com/AdminPortal/Home) Attribuez également la licence à votre compte Azure principal.

Suivez [ce guide court avec](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) des images pour obtenir des instructions détaillées sur l’application de licences d’application.

### <a name="set-up-the-dataverse"></a>Configurer le dataverse

Pour configurer [un environnement de production,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) vous devez respecter deux conditions préalables. Vous devez avoir le rôle [**Administrateur**](https://docs.microsoft.com/power-platform/admin/database-security) système  **et**  vous devez avoir une licence [**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (ou une licence dynamics [**365 guides**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) qui inclut une licence Power Apps). Si vous avez suivi ce guide, vous avez créé Azure AD, vous répondez aux exigences de rôle de l’administrateur système. Nous avons également attribué une licence guides à l’étape précédente.

Dans ce guide pour [créer un environnement Microsoft Dataverse](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two):

1. Commencez par utiliser le Centre [d’administration Power Platform](https://admin.powerplatform.microsoft.com/environments) et créez un nouvel environnement.
2. Lors de la création **du nouvel environnement,** pour le **type**&#39;sélectionnez **Production**.
3. Il est important que vous basculez **Créer une base de données pour cet environnement ?**  option  **oui**.
4. Dans la  **boîte de dialogue**  Ajouter une base de données, définissez l’option Activer les applications Dynamics  **365**  sur  **Oui.**

Vous souhaiterez augmenter la taille de fichier maximale des éléments dans votre dataverse. L’augmentation de la taille maximale des fichiers vous permettra de télécharger des modèles 3D ou des fichiers vidéo plus volumineux que vous utiliserez plus tard dans vos guides. Suivez un court guide pour [modifier la taille maximale du fichier de téléchargement.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Enfin, vous devez installer [et configurer la solution.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Dans le [Centre d’administration Power Platform,](https://admin.powerplatform.microsoft.com/environments)sélectionnez **Ressources**   \ &gt; **Applications Dynamics 365,** sélectionnez **Guides Dynamics 365** dans la liste, puis sélectionnez **Installer**.  

Vous devez [ajouter un rôle de sécurité Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) avant de pouvoir utiliser les applications.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Créer un guide de test sur votre PC via la création

Lorsque vous créez des Guides, vous commencez toujours sur votre PC. Création des étapes, sélection de modèles et ancrage du guide. Pour ce faire, placez le contenu de votre guide ultérieurement en mode de authoring sur votre appareil HoloLens. Pour les besoins de ce guide, nous vous suggérons de faire un guide de test court avec des étapes et des modèles minimaux.

Si vous souhaitez commencer à apprendre à créer des guides, commencez ici avec la vue [d’ensemble de la auteur.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) Ou pour obtenir une vue d’ensemble rapide, regardez cette courte vidéo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Facultatif : mode plein écran

Le mode plein écran est un mode qui permet à un administrateur informatique de configurer l’interface utilisateur du menu Démarrer pour n’afficher qu’une seule application ou une sélection d’applications. Un kiosque peut également être appliqué à des utilisateurs, des groupes ou au niveau de l’appareil spécifiques ; et, dans certains cas, excluez certains utilisateurs du kiosque tout en leur permettant d’accéder au menu Démarrer normal.

Le mode plein écran possède de nombreuses variables différentes, à la fois dans l’étendue et les configurations qui peuvent être définies, ainsi que dans les méthodes de déploiement du kiosque sur HoloLens. En raison de toutes ces variables, __ le mode plein écran est laissé comme facultatif pour ce guide et ne sera pas réexamié. Si vous pensez que vous avez besoin de restreindre les applications disponibles aux utilisateurs ou si vous souhaitez en savoir plus, n’hésitez pas à apprendre à configurer [HoloLens en](https://docs.microsoft.com/hololens/hololens-kiosk)tant que kiosque.

## <a name="optional-wdac"></a>Facultatif : WDAC

WDAC permet à un administrateur informatique de configurer ses appareils pour bloquer le lancement des applications sur les appareils. Ceci est différent des méthodes de restriction d’appareil, telles que le mode plein écran, où l’utilisateur se présente avec une interface utilisateur qui masque les applications sur l’appareil, mais qui peuvent toujours être lancées. Lorsque WDAC est implémenté, les applications sont toujours visibles dans la liste Toutes les applications, mais WDAC empêche le lancement de ces applications et processus par l’utilisateur de l’appareil.

Pour plus d’informations, référencez Utiliser WDAC et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils [HoloLens 2 avec Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

[Contrôle de l’application Windows Defender (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté à l’entreprise : déployer](hololens2-corp-connected-deploy.md)