---
title: Guide de déploiement-connexion d’entreprise HoloLens 2 avec Dynamics 365 Guides-configurer
description: découvrez comment configurer des configurations pour déployer des HoloLens 2 des appareils sur un réseau connecté à l’entreprise avec Dynamics 365 Guides.
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032727"
---
# <a name="configure---corporate-connected-guide"></a>Configurer-Guide connecté à l’entreprise

## <a name="azure-users-and-groups"></a>Utilisateurs et groupes Azure

Azure et Intune par cette extension utilisent des utilisateurs et des groupes pour vous aider à attribuer des configurations et des licences. Pour valider ce processus de déploiement et vérifier que vous pouvez créer et utiliser un guide, vous&#39;aurez besoin d’un compte d’utilisateur.

Nous pouvons créer un groupe d’utilisateurs unique spécifiquement pour l’attribution de licences.

Si vous n’avez pas&#39;avoir accès à deux comptes Azure AD dans un groupe d’utilisateurs que vous pouvez utiliser ; Voici les guides de démarrage rapide pour :

- [Comment créer un utilisateur](/mem/intune/fundamentals/quickstart-create-user)
- [Comment créer un groupe](/mem/intune/fundamentals/quickstart-create-group)
- [Ajouter des utilisateurs à un groupe](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – ajouter des utilisateurs créés à créer un groupe
- [Configurer Azure AD pour permettre à un groupe d’utilisateurs de joindre des appareils](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) : Assurez-vous que le nouveau groupe d’utilisateurs est autorisé à inscrire des appareils sur Azure ad

## <a name="auto-enrollment-on-hololens-2"></a>Inscription automatique sur HoloLens 2

pour bénéficier d’une expérience fluide et transparente, la configuration de Azure Active Directory Join (AADJ) et de l’inscription automatique à Intune pour les appareils HoloLens 2 est la méthode à suivre. Cela permet aux utilisateurs d’entrer leurs informations d’identification de connexion à l’organisation pendant l’OOBE et de s’inscrire automatiquement auprès d’Azure AD et d’inscrire l’appareil dans MDM.

en utilisant [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), vous pouvez sélectionner des services et naviguer dans quelques pages jusqu’à ce que nous puissions sélectionner obtenir une version d’évaluation Premium. vous remarquerez peut-être Azure Active Directory Premium 1 et 2-pour l’inscription automatique P1 est suffisant. Nous pouvons sélectionner Intune et sélectionner l’étendue de l’utilisateur pour l’inscription automatique, puis sélectionner le groupe qui a été créé précédemment.

Pour obtenir des informations détaillées et des étapes, lisez le guide sur [l’activation de l’inscription automatique pour Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Connectivité d’entreprise Wi-Fi

Les connexions de Wi-Fi d’entreprise nécessitent généralement l’authentification basée sur les certificats pour les clients qui utilisent HoloLens 2. Vous devez déployer ces certificats à l’aide d’une infrastructure de certificat Protocole d’inscription de certificats simple (SCEP) ou public Key Cryptography standard (PKCS) qui est intégrée à votre solution MDM. L’utilisation d’Intune pour déployer des Wi-Fi des profils, des certificats et des paramètres de proxy crée une expérience transparente pour les utilisateurs finaux.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Déployer des certificats et des profils de Wi-Fi

pour déployer des certificats et des profils par le biais de Microsoft Endpoint Manager, procédez comme suit :

1. Créez un profil pour chacun des certificats racine et intermédiaires (consultez [créer des profils de certificat approuvés](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Chacun de ces profils doit avoir une description qui comprend une date d’expiration au format JJ/MM/AAAA.

    > [!CAUTION]
    > Les **profils de certificat sans date d’expiration ne seront pas déployés**.

2. Créez un profil pour chaque certificat SCEP ou PKCS (voir [Créer un profil de certificat SCEP ou Créer un profil de certificat PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Chacun de ces profils doit comporter une description qui inclut une date d'expiration au format AAAA/MM/JJ.

    > [!CAUTION]
    > **Les profils de certificat sans date d'expiration ne seront pas déployés.**

    > [!Note]
    > étant donné que la HoloLens 2 est considérée comme un appareil partagé, par exemple, plusieurs utilisateurs par appareil, il est recommandé de déployer des certificats d’appareil plutôt que des certificats utilisateur pour l’authentification Wi-Fi si possible.

3. créez un profil pour votre réseau de Wi-Fi d’entreprise (consultez [paramètres Wi-Fi pour les appareils Windows 10 et versions ultérieures](/intune/wi-fi-settings-windows)). Au sein de votre profil de Wi-Fi, vous pouvez choisir d’utiliser les paramètres de proxy au sein de votre organisation.

    Les options disponibles sont les suivantes :
    - **Aucune** : Aucun paramètre de proxy n’est configuré.
    - **Configurer manuellement** : entrez l’**adresse IP du serveur proxy** et son **numéro de port**.
    - **Configurer automatiquement** : entrez l’URL qui pointe vers un script de configuration automatique du proxy. Par exemple, entrez *http://proxy.contoso.com/proxy.pac* .

    Pour plus d’informations sur les fichiers PAC, consultez [Fichier de configuration automatique de proxy (PAC)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (ouvre un site non-Microsoft).
 
    > [!Note]
    > Dans la mesure du possible, nous vous recommandons d'attribuer le profil Wi-Fi à des groupes d'appareils plutôt qu'à des groupes d'utilisateurs.
     
    > [!Tip]
    > Vous pouvez également exporter un profil Wi-Fi fonctionnel à partir d'un PC Windows 10 sur votre réseau d'entreprise. Cette exportation crée un fichier XML contenant tous les paramètres actuels. Importez ensuite ce fichier dans Intune et utilisez-le comme profil Wi-Fi pour vos appareils HoloLens 2. Consultez [Exporter et importer des paramètres Wi-Fi pour appareils Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [affectez](/mem/intune/configuration/device-profile-assign) les profils d’appareil au groupe d’appareils HoloLens.

2.  [Surveiller](/mem/intune/configuration/device-profile-monitor) les profils d’appareil dans Intune.

En cas de problème avec les profils de Wi-Fi, les informations de référence [Dépannent Wi-Fi les profils de configuration d’appareil dans Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Résolution des problèmes d’accès Internet externe quand Corp est connecté
Lorsque les services essaient de ne pas traverser un proxy Set, ils peuvent tenter de se connecter via le pare-feu. Vous pouvez ajouter une liste de points de terminaison spécifiques à vos règles de pare-feu pour résoudre ces problèmes.

Si vous êtes bloqué sur les ports du pare-feu, activez des [points de terminaison](/hololens/hololens-offline) courants pour HoloLens.

Vous pouvez également activer les repères spécifiques ports : [URL accessibles via Internet requises pour la connectivité à Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Déploiement d'applications

Le déploiement d’une application métier via MDM est une méthode qui est facilement évolutive et qui peut être déployée automatiquement sur vos appareils lors de l’inscription dans un groupe créé.

Si vous développez encore vos applications ou si vous n’en avez pas encore, vous pouvez utiliser un exemple d’application du Hub exemples MRTK. Cet exemple d’application est prêt à être utilisé et ne nécessite pas l’utilisation d’Unity ou de Visual Studio. [Téléchargez l’exemple d’application MRTK Samples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Si vous préférez utiliser votre propre application ou si vous êtes intéressé par le développement d’applications pour la réalité mixte, n’hésitez pas à consulter notre [documentation de développeur de réalité mixte](/windows/mixed-reality/design/design).

> [!NOTE]
> La configuration requise pour les appareils HoloLens dépend de l’architecture de la build de l’application. les appareils HoloLens 2 utilisent l’architecture ARM. lorsque vous créez vos applications dans Visual Studio, assurez-vous que vous avez sélectionné l’architecture appropriée pour l’appareil et incluez les dépendances nécessaires.

> [!IMPORTANT]
> Lors du déploiement d’applications métier, il est important de charger également le certificat sur Intune et de l’affecter au même groupe que celui qui est destiné à utiliser l’application, sinon il ne s’installera pas correctement.

### <a name="upload-and-assign-the-app"></a>Télécharger et assigner l’application

1. Accédez au [Centre d’administration](https://endpoint.microsoft.com/#home)de la mémoire.

2. Sélectionnez **applications**  ->  **toutes les applications** , puis cliquez sur le bouton **+ Ajouter** .

3. Sous autre, sélectionnez **application métier**. Cliquez sur **Sélectionner**.

4. Sélectionnez le fichier de package d’application, il s’agit de votre fichier APPXBUNDLE, ou dans notre cas, l’application est MRTK, exemple _Hub \_ 2.4.2.0 \_ ARM \_ Master. APPXBUNDLE_.

5. Vous serez averti des dépendances manquantes. Dans ce cas, nous devons Télécharger _Microsoft. VCLibs. ARM. 14.00. AppX_. Recherchez-le sous **Sélectionnez un fichier**.

6. Sélectionnez OK.

7. Dans l’écran suivant, les champs obligatoires sont remplis automatiquement. Sélectionnez **Suivant**.

8. Sous requis, ajoutez notre groupe créé précédemment pour rendre cette application obligatoire pour le groupe. L’application sera alors automatiquement téléchargée sur les appareils inscrits dans le groupe. Sélectionnez **Suivant**.

9. Sélectionnez **Create** (Créer).

En savoir plus : [affecter des applications à des groupes dans Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guides d’installation : licences d’application, dataverse et création

pour pouvoir utiliser Dynamics 365 Guides, vous devez effectuer une préparation. Nous devrons préparer trois domaines : Users, dataverse et les guides eux-mêmes.

### <a name="users-and-application-licenses"></a>Utilisateurs et licences d’application

Pour qu’un utilisateur utilise des guides, il doit utiliser un compte Azure AD, que nous avons défini précédemment dans ce guide.

vous devez également attribuer Dynamics 365 Guides licence à l’utilisateur que vous avez créé. vous allez le faire à partir de la [Centre d’administration Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). Attribuez également la licence à votre compte Azure principal.

Suivez [ce raccourci](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) pour obtenir des instructions pas à pas sur l’application de licences d’application.

### <a name="set-up-the-dataverse"></a>Configurer Dataverse

Pour [configurer un environnement de production](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) , vous devez respecter deux conditions préalables. vous devez disposer du rôle d' [**administrateur système**](/power-platform/admin/database-security) , **et** vous devez disposer d’une [**licence Power Apps**](/power-platform/admin/signup-question-and-answer) (ou d’une [**licence Dynamics 365 Guides**](/dynamics365/mixed-reality/guides/setup-step-one) incluant une licence Power Apps). Si vous suivez ce guide, vous avez créé le Azure AD, vous répondez aux exigences de rôle de l’administrateur système. Nous avons également affecté une licence guides à l’étape précédente.

Dans ce guide pour [créer un environnement Microsoft Dataverse](/dynamics365/mixed-reality/guides/setup-step-two):

1. Commencez par utiliser le [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/environments) et créez un nouvel environnement.
2. Lors de la création du **nouvel environnement**, pour le **Type** , vous&#39;sélectionner **production**.
3. Il est important que vous basculiez **créer une base de données pour cet environnement ?**  option sur  **Oui**.
4. Dans la boîte  **de dialogue Ajouter une base de données**  , définissez l’option  **activer les applications Dynamics 365**  sur  **Oui.**

Vous souhaitez augmenter la taille de fichier maximale des éléments dans votre dataverse. L’augmentation de la taille maximale des fichiers vous permet de télécharger des modèles 3D ou des fichiers vidéo plus volumineux, que vous utiliserez ultérieurement dans vos guides. Suivez un bref guide [pour modifier la taille maximale du fichier de téléchargement](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).

Enfin, vous devez [installer et configurer la solution](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). Dans le [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/environments), sélectionnez **ressources** \& gt ;  **Dynamics 365 apps**, sélectionnez **Dynamics 365 Guides** dans la liste, puis sélectionnez **installer**.  

Vous devez [Ajouter un rôle de sécurité guides](/dynamics365/mixed-reality/guides/assign-role) avant de pouvoir utiliser les applications.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Créer un guide de test sur votre PC via la création

Lorsque vous créez des guides, vous démarrez toujours sur votre PC. Création des étapes, sélection des modèles et comment ancrer le repère. pour ce faire, vous devez placer le contenu de votre guide plus tard dans en mode création sur votre appareil HoloLens. Dans le cadre de ce guide, nous vous suggérons de créer un petit guide de test avec des étapes et des modèles minimes.

Si vous souhaitez commencer à vous familiariser avec la création de guides, commencez par la [vue d’ensemble](/dynamics365/mixed-reality/guides/authoring-overview)de la création. Ou pour obtenir une vue d’ensemble rapide, regardez cette brève vidéo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Facultatif : mode plein écran

Le mode plein écran est un mode qui permet à un administrateur informatique de configurer l’interface utilisateur du menu Démarrer pour afficher une seule application ou une sélection d’applications. Une borne peut également être appliquée à des utilisateurs, des groupes ou au niveau de l’appareil spécifiques. dans certains cas, excluez certains utilisateurs de la borne pour leur permettre d’accéder au menu Démarrer normal.

Le mode plein écran présente de nombreuses variables différentes, à la fois dans l’étendue et dans les configurations, qui peuvent être définies, ainsi que les méthodes de déploiement de la borne sur le HoloLens. En raison de toutes ces variables, le mode plein écran est laissé comme _facultatif_ pour ce guide et ne sera pas revisité. si vous pensez que vous avez un besoin professionnel de limiter les applications disponibles aux utilisateurs ou si vous souhaitez en savoir plus, n’hésitez pas à apprendre à [configurer HoloLens en tant que kiosque](/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Facultatif : WDAC

WDAC permet à un administrateur informatique de configurer ses appareils pour bloquer le lancement d’applications sur les appareils. Cela diffère des méthodes de restriction de l’appareil, telles que le mode plein écran, où l’utilisateur voit une interface utilisateur qui masque les applications sur l’appareil, mais qui peut toujours être lancée. Si WDAC est implémenté, les applications sont toujours visibles dans la liste toutes les applications, mais WDAC arrête l’exécution de ces applications et processus par l’utilisateur de l’appareil.

pour plus d’informations, consultez la référence [utiliser WDAC et Windows PowerShell pour autoriser ou bloquer des applications sur des appareils HoloLens 2 avec Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Contrôle d’application Windows Defender - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Étape suivante 
> [!div class="nextstepaction"]
> [Déploiement connecté d’entreprise-déployer](hololens2-corp-connected-deploy.md)