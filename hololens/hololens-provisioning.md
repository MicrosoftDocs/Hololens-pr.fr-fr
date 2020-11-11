---
title: Configurer HoloLens à l’aide d’un package de mise en service (HoloLens)
description: L’approvisionnement Windows aide les administrateurs informatiques à configurer les appareils des utilisateurs finaux sans acquisition d’images.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6b715a6a43a403ec56119188db0121e0731af37
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162994"
---
# Configurer HoloLens à l’aide d’un package de mise à service

La [mise en service Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) permet aux administrateurs informatiques de configurer facilement les appareils des utilisateurs finaux sans imagerie. Le concepteur de configuration Windows est un outil qui permet de configurer les images et les paramètres d’exécution intégrés aux packages de mise en service.

Voici quelques-unes des configurations HoloLens que vous pouvez appliquer à un package de mise en service:

- Effectuer une mise à niveau vers Windows holographique pour [les entreprises](hololens1-upgrade-enterprise.md)
- Configuration d’un compte local
- Configuration d'une connexion Wi-Fi
- Application de certificats à l’appareil
- Activer le mode développeur
- Configurez le mode plein écran (les instructions détaillées pour configurer le mode kiosque sont accessibles [ici](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

## Assistant HoloLens du package de mise en service

L’Assistant HoloLens vous permet de configurer les paramètres suivants dans un package de mise en service:

- Effectuer une mise à niveau vers l’édition entreprise

    > [!NOTE]
    > Cette méthode ne doit être utilisée que pour les appareils HoloLens de première génération. Les paramètres d’un package de mise en service s’appliquent uniquement si le package de déploiement inclut une licence de mise à niveau d’édition pour Windows holographique entreprise ou si [l’appareil a déjà été mis à niveau vers Windows holographique pour les entreprises](hololens1-upgrade-enterprise.md).

- Configurer la première expérimentation de HoloLens (OOBE)
- Configurer le réseau Wi-Fi
- Inscrire l’appareil dans Azure Active Directory ou créer un compte local
- Ajouter des certificats
- Activer le mode développeur
- Configurez le mode plein écran. (Vous trouverez des instructions détaillées sur la configuration du mode plein écran [ici](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).

> [!WARNING]
> Vous devez exécuter le Concepteur de configuration Windows sur Windows10 pour configurer l’inscription à Azure ActiveDirectory à l’aide d’un des assistants.

Les packages de mise en service peuvent inclure des instructions de gestion et des stratégies, des connexions réseau et des stratégies personnalisées, etc.

> [!TIP]
> Utilisez l’assistant bureau pour créer un package avec les paramètres courants, puis basculer vers l’éditeur avancé pour ajouter d’autres paramètres, des applications, des stratégies, etc.

## Étapes de création de packages de mise en service

1. **Option 1:** [à partir de la boutique Microsoft](https://www.microsoft.com/store/apps/9nblggh4tx22). Cela inclut les fonctionnalités HoloLens 2.
2. **Option 2:** [dans le kit d’évaluation et de déploiement Windows (ADK) pour Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Si vous installez le concepteur de configuration Windows à partir de Windows ADK, sélectionnez **Concepteur de configurations** dans la boîte de dialogue **Sélectionner les fonctionnalités que vous voulez installer** . Cette option n’inclut pas les fonctionnalités HoloLens 2.

> [!NOTE]
> Si vous savez que vous utiliserez un PC hors connexion qui a besoin d’accéder à la configuration de Windows, suivez les étapes de l’installation de l’application en mode hors connexion [ici](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) pour l’Assistant de restauration avancée, mais rendez votre sélection à Windows Confiugration à la place. 

### 2. créer le package de mise en service

Utilisez l'outil Concepteur de configuration Windows pour créer un package de configuration.

1. Ouvrez Concepteur de configuration Windows (par défaut, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Sélectionnez mise en **service des appareils HoloLens**.

   ![Options de démarrage d’ICD](images/icd-create-options-1703.png)

3. Nommez votre projet, puis sélectionnez **Terminer**.

4. Lisez les instructions qui s’affichent sur la page **mise en route** , puis sélectionnez **suivant**. Les pages de l’approvisionnement de bureau vous guident dans les étapes suivantes.
  
> [!IMPORTANT]
> Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.

### Configurer les paramètres

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Recherchez et sélectionnez le fichier de licence d’entreprise pour mettre à niveau l’édition HoloLens.</br></br>Vous pouvez également activer <strong> ou désactiver le bouton Oui </strong> <strong> </strong> pour masquer les parties de la première expérimentation.</br></br>Pour configurer l’appareil sans qu’il soit nécessaire de se connecter à un réseau Wi-Fi, activez la bascule <strong> ignorer Wi-Fi configuration </strong> <strong> </strong> .</br></br>Sélectionnez la région et le fuseau horaire dans lesquels l’appareil doit être utilisé. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Dans cette section, vous pouvez entrer les détails du réseau sans fil Wi-Fi auquel l’appareil doit se connecter automatiquement. Pour cela, sélectionnez <strong> activé </strong> , entrez le SSID, le type du réseau ( <strong> ouvert </strong> ou <strong> WPA2-personnel </strong> ) et (si <strong> WPA2-personnel </strong> ) le mot de passe du réseau sans fil.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Vous pouvez inscrire l’appareil dans Azure Active Directory ou créer un compte local sur l’appareil.</br></br>Avant d’utiliser un assistant de Concepteur de configuration Windows pour configurer l’inscription en bloc à Azure AD, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configurez Azure AD pour qu'il rejoigne votre organisation</a>. Le paramètre <strong>Nombre maximal d'appareils par utilisateur</strong> dans votre locataire Azure AD détermine le nombre de fois où le jeton en bloc que vous avez obtenu via l’assistant peut être utilisé. Pour inscrire l’appareil dans Azure AD, sélectionnez cette option et entrez un nom convivial pour le jeton en bloc que vous obtiendrez via l’assistant. Définissez une date d’expiration pour le jeton (30jours maximum à compter de la date à laquelle vous avez reçu le jeton). Sélectionnez <strong> obtenir un jeton en bloc </strong> . Dans la <strong> fenêtre permettre aux&#39;de vous connecter </strong> , entrez un compte disposant des autorisations nécessaires pour joindre un appareil à Azure ad, puis le mot de passe. Sélectionnez <strong> accepter </strong> pour donner aux concepteurs de configuration Windows les autorisations nécessaires. </br></br>Pour créer un compte local, sélectionnez cette option et entrez un nom d’utilisateur et un mot de passe. </br></br><strong>Important:</strong> <br />(Pour Windows 10, version 1607 uniquement) Si vous créez un compte local dans le package de mise en service, vous devez modifier le mot de passe à l’aide de l' <strong> </strong> application paramètres tous les 42 jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Pour configurer l’appareil avec un certificat, cliquez sur <strong>Ajouter un certificat</strong>. Entrez un nom pour le certificat, puis recherchez et sélectionnez le certificat à utiliser.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong> </strong> Activez oui ou <strong> non </strong> pour activer le mode développeur sur le HoloLens. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">En savoir plus sur le mode développeur.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Ne définissez aucun mot de passe pour protéger votre package de mise en service. Si le package de mise en service est protégé par un mot de passe, la mise en service de l’appareil HoloLens échoue.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Lorsque vous avez terminé, sélectionnez **créer**. Cela ne prend que quelques secondes. Une fois le package créé, l’emplacement du package s’affiche en tant que lien hypertexte au bas de la page.

### 3. créer un package de déploiement pour HoloLens à l’aide de la configuration avancée

> [!NOTE]
> Un package de mise en service créé dans la mise en **service avancée** n’a pas besoin d’inclure une licence de mise à niveau d’édition sur Windows holographique pour les entreprises pour une application réussie à une application HoloLens (1er génération). [En savoir plus sur Windows holographique entreprise pour HoloLens (1er génération)](hololens1-upgrade-enterprise.md).

1. Sur la page de démarrage du Concepteur de configuration Windows, sélectionnez **Approvisionnement avancé**.
2. Dans la fenêtre **Entrez les détails du projet**, spécifiez un nom et un emplacement pour votre projet. Si vous le souhaitez, saisissez une brève description du projet.

3. Sélectionnez **Suivant**.

4. Dans la fenêtre **choisir les paramètres à afficher et à configurer** , sélectionnez **Windows 10 holographique**, puis cliquez sur **suivant**.

5. Cliquez sur **Terminer**.

6. Développez les **paramètres d’exécution** et personnalisez le package à l’aide de l’un des paramètres [décrits plus loin dans cet article](#what-you-can-configure).

    > [!IMPORTANT]
    > (Pour Windows 10, version 1607 uniquement) Si vous créez un compte local dans le package de mise en service, vous devez modifier le mot de passe à l’aide de l’application **paramètres** tous les 42 jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter. Si le compte d’utilisateur est verrouillé, vous devez [effectuer une récupération complète de l’appareil](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Sélectionnez **fichier**  >  **Enregistrer**.

8. Lisez le message d’avertissement indiquant que les fichiers de projet contiennent des informations sensibles, puis sélectionnez **OK**.

    > [!IMPORTANT]
    > Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.
    
9. Sélectionnez **Exporter**le  >  **package de mise en service**.

10. Remplacez **owner** par **admin**. Ce paramètre définit le niveau de priorité de ce package de mise à niveau plus élevé que les packages de mise en service appliqués à cet appareil à partir d’autres sources. Sélectionnez **Suivant**.

11. Définissez une valeur pour **Package Version**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

12. Dans le **dossier sélectionner les détails de sécurité du package de mise en service**, sélectionnez **suivant**.

    > [!WARNING]
    > Si vous chiffrez le package de configuration, la configuration de l’appareil HoloLens échouera.  

13. Sélectionnez **suivant** pour spécifier l’emplacement de sortie dans lequel vous souhaitez que le package de mise en service soit placé une fois qu’il est intégré. Par défaut, le Concepteur de configuration Windows utilise le dossier de projet comme emplacement de sortie.

    Vous pouvez également sélectionner **Parcourir** pour changer l’emplacement de sortie par défaut.

14. Sélectionnez **Suivant**.

15. Pour commencer à générer le package, sélectionnez **Build** . Les informations du projet s'affichent sur la page de génération, et la barre de progression indique l'état de la génération.

16. À la fin de la build, sélectionnez **Terminer**.

<span id="apply" />

## Appliquer un package de mise à service à HoloLens lors de l’installation

Les appareils HoloLens 2 sur Windows holographique, version 2004 ou build [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) ou version ultérieure, pourront utiliser un lecteur USB pour appliquer un package de mise en service. Il suffit de copier le fichier. ppkg à la racine du lecteur USB. Les packages de mise en service ne seront appliqués que s’ils sont à la racine du lecteur USB. La présence de plusieurs packages de mise en service sera appliquée séquentiellement.

Les appareils HoloLens 2 sur [Windows holographique version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou ultérieure possèdent de nouvelles fonctionnalités qui vous permettent de rationaliser et de simplifier ce processus. Veuillez consulter les sections suivantes:

- [Mise en service du lancement automatique à partir d’USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Vérifier automatiquement les packages de mise en service dans OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Configuration automatique sans utiliser d’interface utilisateur](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Utilisez le câble USB pour connecter l’appareil à un PC (ou un lecteur USB pour HoloLens 2, comme mentionné ci-dessus), puis démarrez l’appareil. Ne passez pas à la **première** page de début d’interaction de OOBE.   
    - Sur HoloLens (1ère génération), cette page contient un cadre bleu. 
    - Sur HoloLens 2, cette page contient le Hummingbird.

2. Appuyez brièvement sur les boutons **Baisser le volume** et **Marche/Arrêt** en même temps, puis relâchez-les. 

3. HoloLens est affiché en tant que périphérique dans l’Explorateur de fichiers sur le PC.

4. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.

5. Appuyez de nouveau sur le **volume** et relâchez-le en appuyant sur le bouton d' **alimentation** , puis cliquez sur la première page d’un **moment** interactif de OOBE.

6. L’appareil vous demande si vous faites confiance au package et que vous souhaitez l’appliquer. Confirmez que vous faites confiance au package.

7. Vous verrez si le package a été appliqué avec succès ou non. En cas d’échec, vous pouvez corriger votre package et essayer à nouveau. Si l'opération a réussi, passez à la phase OOBE.

> [!NOTE]
> Si l’appareil a été acheté avant le 2016 août, vous devez vous connecter à l’appareil à l’aide d’un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser le système d’exploitation pour appliquer le package de mise à service.

### Mise en service du lancement automatique à partir d’USB

- Processus automatisés autorisant moins d’interactions utilisateur, lorsque les lecteurs USB avec des packages de mise en service sont utilisés au cours de l’utilisation de la fonction OOBE.

Pour pouvoir lancer l’affichage de l’écran de mise en service manuellement lors de la mise en service de l’utilisation d’une combinaison de boutons Les utilisateurs peuvent désormais ignorer la combinaison de boutons à l’aide d’un package de mise en service sur un lecteur de stockage USB. 

1. Brancher le lecteur USB avec le package de mise en service lors du premier moment de l’interaction de OOBE
1. Lorsque l’appareil est prêt à être approvisionné, il ouvre automatiquement l’invite à l’aide de la page de configuration. 

Remarque: Si vous laissez un lecteur USB branché dans le cadre du démarrage de l’appareil, l’interface OOBE recense le périphérique de stockage USB existant, ainsi que les éléments supplémentaires connectés.

Pour plus d’informations sur l’application des packages de mise en service lors de la configuration de OOBE, continuez à lire [ici](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Vérifier automatiquement les packages de mise en service dans OOBE
- Processus automatisé permettant d’avoir moins d’interactions avec l’utilisateur, lorsque la page package de mise en service s’affiche, il applique automatiquement tous les packages répertoriés.

Lorsque l’écran principal de mise en service s’affiche, OOBE compte 10 secondes avant de commencer à appliquer automatiquement tous les packages de mise en service. Les utilisateurs peuvent toujours confirmer ou annuler dans les 10 secondes qui suivent la vérification des packages attendus.

### Configuration automatique sans utiliser d’interface utilisateur
- Processus automatiques combinés pour réduire les interactions d’appareil pour la mise en service. 

En associant le lancement automatique de la mise en service à partir d’appareils USB et la confirmation automatique des packages de mise en service, un utilisateur peut configurer automatiquement les appareils HoloLens 2 sans utiliser l’interface utilisateur de l’appareil, ni ne porter le périphérique. Vous pouvez continuer à utiliser le même pilote USB et le même package de mise en service pour plusieurs appareils. Cela s’avère utile pour le déploiement de plusieurs appareils à la fois dans la même zone. 

1. [Créer un package de mise à service](hololens-provisioning.md) à l’aide du [Concepteur de configuration Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiez le package sur un lecteur de stockage USB.
1. [Flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) vers [19041,1361 ou version ultérieure](https://aka.ms/hololens2previewdownload). 
1. Lorsque le [compagnon de récupération avancée](https://www.microsoft.com/store/productId/9P74Z35SFRS8) clignote sur votre appareil, débranchez votre câble USB-C. 
1. Branchez votre lecteur USB sur le périphérique.
1. Lors du démarrage de l’appareil HoloLens 2 dans OOBE, le package de mise en service sera automatiquement détecté sur le lecteur USB et lancera la page de configuration.
1. Après 10 secondes, l’appareil applique automatiquement le package de mise en service. 

Votre appareil est désormais configuré et affiche l’écran de mise en service réussi.

## Appliquer un package de mise à service à HoloLens après l’installation

> [!NOTE]
> Ces étapes s’appliquent uniquement à Windows 10, version 1809.

Sur votre PC, procédez comme suit:
1. Pour créer un package de mise en service, voir [créer un package de mise à niveau pour HoloLens à l’aide de l’Assistant hololens](hololens-provisioning.md).
2. Connectez l’appareil HoloLens à un PC à l’aide d’un câble USB. HoloLens est affiché en tant que périphérique dans l’Explorateur de fichiers sur le PC.
3. Faites glisser et déposez le package de mise à niveau vers le dossier documents sur le HoloLens.

Sur votre HoloLens, procédez comme suit:
1. Accédez à **paramètres**  >  **comptes**  >  **accès professionnel ou scolaire**. 
2. Dans **paramètres associés**, sélectionnez **Ajouter ou supprimer un package de mise à service**.
3. Sur la page suivante, sélectionnez **Ajouter un package** pour lancer le sélecteur de fichiers, puis sélectionnez votre package de mise en service. Si le dossier est vide, assurez-vous de sélectionner **cet appareil** et de sélectionner **documents**.

Une fois votre package appliqué, il apparaît dans la liste des **packages installés**. Pour afficher les détails du package ou supprimer le package de l’appareil, sélectionnez le package listé.

## Ce que vous pouvez configurer

Les packages d’approvisionnement utilisent des fournisseurs de services de configuration (CSP). Si vous n’êtes pas familiarisé avec les CSP, lisez la rubrique [Présentation des fournisseurs de services de configuration (CSP) pour les professionnels de l’informatique](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

Dans le Concepteur de configuration Windows, lorsque vous créez un package de configuration pour Windows Holographique, les paramètres des **Personnalisations disponibles** sont basés sur les [CSP pris en charge dans Windows Holographique](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). Le tableau suivant décrit les paramètres que vous pouvez souhaiter configurer pour HoloLens.

![Paramètres d’exécution courants pour HoloLens](images/icd-settings.png)

| Paramètre | Description |
| --- | --- |
| **Certificats** | Déployer un certificat pour HoloLens.  |
| **ConnectivityProfiles** | Déployer un profil Wi-Fi pour HoloLens.   |
| **EditionUpgrade** | [Mise à niveau vers Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Stratégies** | Autoriser ou interdire le mode développeur sur HoloLens. [Stratégies prises en charge par Windows Holographic for Business](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## Installation de l’application via le package de mise en service

Les applications peuvent être installées par le biais de packages de mise en service sur les appareils HoloLens 2. Cela permet de disposer d’un package facilement réutilisable que vous pouvez utiliser pour vous aider à distribuer vos applications. Lisez les instructions complètes pour le [déploiement d’applications par packages de mise en service](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1er génération) dispose d’une prise en charge limitée pour l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package de mise en service. Les appareils HoloLens (1ère génération) ne prennent en charge l’installation d’une application qu’avec PPKG que dans OOBE et uniquement avec les installations de contexte utilisateur.
