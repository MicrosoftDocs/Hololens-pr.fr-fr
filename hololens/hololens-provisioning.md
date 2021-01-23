---
title: Configurer HoloLens à l’aide d’un package d’approvisionnement (HoloLens)
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
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284155"
---
# Configurer HoloLens à l’aide d’un package d’approvisionnement

[L’approvisionnement Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) permet aux administrateurs informatiques de configurer facilement les appareils des utilisateurs finaux sans imagerie. Le Concepteur de configuration Windows est un outil de configuration des images et des paramètres d’runtime qui sont ensuite intégrés aux packages d’approvisionnement.

Voici quelques-unes des configurations HoloLens que vous pouvez appliquer dans un package d’approvisionnement :

- Mise à niveau [vers Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Configuration d’un compte local
- Configuration d'une connexion Wi-Fi
- Application de certificats à l’appareil
- Activer le mode développeur
- Configurez le mode plein écran en suivant [nos instructions détaillées.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

## Assistant HoloLens du package d’approvisionnement

L’Assistant HoloLens vous permet de configurer les paramètres suivants dans un package d’approvisionnement :

- Mise à niveau vers l’édition Entreprise

    > [!NOTE]
    > Cela ne doit être utilisé que pour les appareils HoloLens 1ère génération. Les paramètres d’un package d’approvisionnement ne sont appliqués que si le package d’approvisionnement inclut une licence de mise à niveau d’édition vers Windows Holographic for Business ou si l’appareil a déjà été mis à niveau vers [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

- Configurer la première expérience HoloLens (OOBE)
- Configurer le réseau Wi-Fi réseau
- Inscrire l’appareil dans Azure Active Directory ou créer un compte local
- Ajouter des certificats
- Activer le mode développeur
- Configurez le mode plein écran en suivant [des instructions détaillées).](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

> [!WARNING]
> Vous devez exécuter le Concepteur de configuration Windows sur Windows10 pour configurer l’inscription à Azure ActiveDirectory à l’aide d’un des assistants.

Les packages d’approvisionnement peuvent inclure des instructions et des stratégies de gestion, des connexions et des stratégies réseau personnalisées, et bien plus encore.

> [!TIP]
> Utilisez l’assistant bureau pour créer un package avec les paramètres courants, puis basculer vers l’éditeur avancé pour ajouter d’autres paramètres, des applications, des stratégies, etc.

## Étapes de création de packages d’approvisionnement

1. **Option 1 : à** [partir du Microsoft Store.](https://www.microsoft.com/store/apps/9nblggh4tx22) Cela inclut les fonctionnalités HoloLens 2.
2. **Option 2 : à** partir du Kit de déploiement et [d’évaluation Windows (ADK) pour Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Si vous installez le Concepteur de configuration Windows à partir de Windows ADK, sélectionnez Concepteur de **configuration** dans la boîte de dialogue Sélectionner les fonctionnalités **que** vous souhaitez installer. Cette option n’inclut pas les fonctionnalités HoloLens 2.

> [!NOTE]
> Si vous savez que vous allez utiliser un PC hors connexion qui a besoin d’accéder au Concepteur de configuration Windows, suivez les instructions [installation de l’application hors connexion( instructions pour https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) Advanced Recovery Companion. Faites de Votre choix le Concepteur de configuration Windows. 

### 2. Créer le package d’approvisionnement

Utilisez l'outil Concepteur de configuration Windows pour créer un package de configuration.

1. Ouvrez Concepteur de configuration Windows (par défaut, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Sélectionnez **Approvisionnement d’appareils HoloLens.**

   ![Options de démarrage d’ICD](images/icd-create-options-1703.png)

3. Nommez votre projet et sélectionnez **Terminer.**

4. Lisez les instructions de la page **De mise en** page de mise en page et sélectionnez **Suivant.** Les pages de mise en service de bureau vous offrent les étapes suivantes.
  
> [!IMPORTANT]
> Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.

### Configurer les paramètres

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Accédez au fichier de licence d’entreprise et sélectionnez-le pour mettre à niveau l’édition HoloLens.</br></br>Vous pouvez également faire bascule Oui <strong> ou Non pour masquer des parties de la première </strong> <strong> </strong> expérience.</br></br>Pour configurer l’appareil sans avoir besoin de se connecter à un réseau Wi-Fi, basculez l'Wi-Fi <strong> sur </strong> Sur <strong> </strong> .</br></br>Sélectionnez une région et un fuseau horaire dans lesquels l’appareil sera utilisé. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Dans cette section, vous pouvez entrer les détails du Wi-Fi sans fil à qui l’appareil doit se connecter automatiquement. Pour ce faire, sélectionnez Sur, entrez le SSID, le type de réseau <strong> </strong> ( Open ou <strong> </strong> <strong> WPA2-Personal ), et </strong> (si <strong> WPA2-Personal </strong> ) le mot de passe pour le réseau sans fil.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Vous pouvez inscrire l’appareil dans Azure Active Directory ou créer un compte local sur l’appareil.</br></br>Avant d’utiliser un assistant de Concepteur de configuration Windows pour configurer l’inscription en bloc à Azure AD, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configurez Azure AD pour qu'il rejoigne votre organisation</a>. Le paramètre <strong>Nombre maximal d'appareils par utilisateur</strong> dans votre locataire Azure AD détermine le nombre de fois où le jeton en bloc que vous avez obtenu via l’assistant peut être utilisé. Pour inscrire l’appareil dans Azure AD, sélectionnez cette option et entrez un nom convivial pour le jeton en bloc que vous obtiendrez via l’assistant. Définissez une date d’expiration pour le jeton (30jours maximum à compter de la date à laquelle vous avez reçu le jeton). Sélectionnez <strong> Obtenir un jeton en </strong> bloc. Dans la fenêtre&#39;vous êtes connecté, entrez un compte qui dispose des autorisations pour joindre un appareil à Azure AD, puis le <strong> </strong> mot de passe. Sélectionnez <strong> Accepter pour accorder au Concepteur de configuration Windows les </strong> autorisations nécessaires. </br></br>Pour créer un compte local, sélectionnez cette option et entrez un nom d’utilisateur et un mot de passe. </br></br><strong>Important:</strong> <br />(Pour Windows 10, version 1607 uniquement) Si vous créez un compte local dans le package d’approvisionnement, vous devez modifier le mot de passe à l’aide de l’application <strong> Paramètres </strong> tous les 42 jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Pour configurer l’appareil avec un certificat, cliquez sur <strong>Ajouter un certificat</strong>. Entrez un nom pour le certificat, puis recherchez et sélectionnez le certificat à utiliser.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Basculez <strong> Oui </strong> ou Non pour activer le mode développeur sur <strong> </strong> HoloLens. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">En savoir plus sur le mode développeur.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Ne définissez pas de mot de passe pour protéger votre package d’approvisionnement. Si le package d’approvisionnement est protégé par un mot de passe, la mise en service de l’appareil HoloLens échoue.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Une fois que vous avez terminé, sélectionnez **Créer.** Cela ne prend que quelques secondes. Une fois le package créé, l’emplacement du package s’affiche en tant que lien hypertexte au bas de la page.

### 3. Créer un package d’approvisionnement pour HoloLens à l’aide de l’approvisionnement avancé

> [!NOTE]
> Un package d’approvisionnement **** que vous créez dans l’approvisionnement avancé n’a pas besoin d’inclure une licence de mise à niveau d’édition vers Windows Holographic for Business pour s’appliquer correctement à un HoloLens (1ère génération). [En savoir plus sur Windows Holographic for Business pour HoloLens (1ère génération).](hololens1-upgrade-enterprise.md)

1. Sur la page de démarrage du Concepteur de configuration Windows, sélectionnez **Approvisionnement avancé**.
2. Dans la fenêtre **Entrez les détails du projet**, spécifiez un nom et un emplacement pour votre projet. Si vous le souhaitez, saisissez une brève description du projet.

3. Sélectionnez **Suivant**.

4. Dans la **fenêtre Choisir les paramètres à** afficher et à configurer, sélectionnez Windows **10 Holographique,** puis sélectionnez **Suivant**.

5. Sélectionnez **Terminer.**

6. Développez **les paramètres d’runtime** et personnalisez le package à l’aide de l’un des paramètres décrits [plus loin dans cet article.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Pour Windows 10, version 1607 uniquement) Si vous créez un compte local dans le package d’approvisionnement, vous devez modifier le mot de passe à l’aide de l’application **Paramètres** tous les 42 jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter. Si le compte d’utilisateur est verrouillé, vous devez [effectuer une récupération complète de l’appareil](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Sélectionnez **Enregistrer**  >  **un fichier.**

8. Lisez l’avertissement signalant que les fichiers de projet peuvent contenir des informations sensibles, puis sélectionnez **OK.**

    > [!IMPORTANT]
    > Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.
    
9. Sélectionnez **Exporter**  >  **le package d’approvisionnement.**

10. Changez **de propriétaire** en **administrateur informatique.** Cela définit la priorité de ce package d’approvisionnement plus élevée que les packages d’approvisionnement appliqués à cet appareil à partir d’autres sources. Sélectionnez **Suivant**.

11. Définissez une valeur pour **Package Version**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

12. Dans la **sélection des détails de sécurité pour le package d’approvisionnement,** sélectionnez **Suivant**.

    > [!WARNING]
    > Si vous chiffrez le package de configuration, la configuration de l’appareil HoloLens échouera.  

13. Sélectionnez **Suivant** pour spécifier l’emplacement de sortie où vous souhaitez que le package d’approvisionnement soit mis en place une fois qu’il est créé. Par défaut, le Concepteur de configuration Windows utilise le dossier de projet comme emplacement de sortie.

    Si vous le souhaitez, vous pouvez sélectionner **Parcourir** pour modifier l’emplacement de sortie par défaut.

14. Sélectionnez **Suivant**.

15. Sélectionnez **Build** pour commencer à créer le package. Les informations du projet s'affichent sur la page de génération, et la barre de progression indique l'état de la génération.

16. Une fois la build terminée, sélectionnez **Terminer.**

<span id="apply" />

## Appliquer un package d’approvisionnement à HoloLens lors de l’installation

Les appareils HoloLens 2 sur Windows Holographic, version 2004 ou build [19041.1103 ou](hololens-release-notes.md#windows-holographic-version-2004) ultérieure, peuvent utiliser un lecteur USB pour appliquer un package d’approvisionnement. Copiez simplement le fichier .ppkg à la racine du lecteur USB. Les packages d’approvisionnement ne seront appliqués que s’ils seraient à la racine du lecteur USB. Plusieurs packages d’approvisionnement présents seront appliqués séquentiellement.

Les appareils HoloLens 2 sur [Windows Holographique version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou ultérieure disposent de fonctionnalités plus récentes pour simplifier et simplifier ce processus, le rendant automatique. Consultez les sections suivantes :

- [Mise en service de lancement automatique à partir du port USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Confirmer automatiquement les packages d’approvisionnement en mode OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Approvisionnement automatique sans utilisation de l’interface utilisateur](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Utilisez le câble USB pour connecter l’appareil à un PC (ou un lecteur USB pour HoloLens 2, comme mentionné ci-dessus), puis démarrez l’appareil. Ne continuez pas au-delà de la page **First interactable moment** de la OOBE.   
    - Sur HoloLens (1ère génération), cette page contient une zone bleue. 
    - Sur HoloLens 2, cette page contient le hummingbird.

2. Appuyez brièvement sur les boutons **Baisser le volume** et **Marche/Arrêt** en même temps, puis relâchez-les. 

3. HoloLens s’affiche en tant qu’appareil dans l’Explorateur de fichiers sur le PC.

4. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.

5. Appuyez brièvement sur les **** boutons Baisser le **volume** et Alimentation simultanément, puis relâchez-les sur la page First **interactable moment** de la OOBE.

6. L’appareil vous demande si vous faites confiance au package et souhaitez l’appliquer. Confirmez que vous faites confiance au package.

7. Vous verrez si le package a été appliqué avec succès ou non. En cas d’échec, vous pouvez corriger votre package et essayer à nouveau. Si l'opération a réussi, passez à la phase OOBE.

> [!NOTE]
> Si l’appareil a été acheté avant août 2016, vous devez vous y connecté à l’aide d’un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser le système d’exploitation afin d’appliquer le package d’approvisionnement.

### Mise en service de lancement automatique à partir du port USB

- Processus automatisés permettant de réduire l’interaction utilisateur, lorsque des lecteurs USB avec packages d’approvisionnement sont utilisés pendant la OOBE.

Avant cette version, les utilisateurs deviez lancer l’écran d’approvisionnement manuellement pendant la OOBE pour le mettre en service à l’aide d’une combinaison de boutons. Les utilisateurs peuvent maintenant ignorer la combinaison de boutons à l’aide d’un package d’approvisionnement sur un lecteur de stockage USB. 

1. Branchez le lecteur USB avec le package d’approvisionnement lors du premier moment interagi de la première OOBE
1. Lorsque l’appareil est prêt à être mis en service, il ouvre automatiquement l’invite avec la page d’approvisionnement. 

Remarque : si un lecteur USB est laissé branché pendant le démarrage de l’appareil, la OOBE édifiera le périphérique de stockage USB existant et observera les autres disques branchés.

Découvrez [l’application de packages d’approvisionnement pendant la OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### Confirmer automatiquement les packages d’approvisionnement en mode OOBE
- Processus automatisé permettant de réduire l’interaction utilisateur, lorsque la page Package d’approvisionnement s’affiche, elle applique automatiquement tous les packages répertoriés.

Lorsque l’écran principal d’approvisionnement se présente, la OOBE compte moins 10 secondes avant de commencer automatiquement à appliquer tous les packages d’approvisionnement. Les utilisateurs peuvent toujours confirmer ou annuler au cours de cette période de 10 secondes après avoir vérifié les packages attendus.

### Approvisionnement automatique sans utilisation de l’interface utilisateur
- Processus automatiques combinés pour réduire les interactions d’appareil pour l’approvisionnement. 

En combinant le lancement automatique de l’approvisionnement à partir de périphériques USB et la confirmation automatique des packages d’approvisionnement, un utilisateur peut mettre en service les appareils HoloLens 2 automatiquement sans utiliser l’interface utilisateur de l’appareil, ni même porter l’appareil. Vous pouvez continuer à utiliser le même lecteur USB et le même package d’approvisionnement pour plusieurs appareils. Cela est utile pour déployer plusieurs appareils à la fois dans la même zone. 

1. [Créez un package d’approvisionnement à l’aide](hololens-provisioning.md) [du Concepteur de configuration Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copiez le package sur un lecteur de stockage USB.
1. [Flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) vers [la build 19041.1361](https://aka.ms/hololens2previewdownload)ou une build plus nouvelle. 
1. Lorsque [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) a terminé de faire clignoter votre appareil pour débrancher votre câble USB-C. 
1. Branchez votre lecteur USB à l’appareil.
1. Lorsque l’appareil HoloLens 2 démarre en OOBE, il détecte automatiquement le package d’approvisionnement sur le lecteur USB et lance la page d’approvisionnement.
1. Après 10 secondes, l’appareil applique automatiquement le package d’approvisionnement. 

Votre appareil est maintenant configuré et affiche l’écran Configuration réussie.

## Appliquer un package d’approvisionnement à HoloLens après l’installation

> [!NOTE]
> Ces étapes s’appliquent uniquement à Windows 10, version 1809.

Sur votre PC, suivez les étapes suivantes :
1. Créez un package d’approvisionnement comme décrit dans Créer un package d’approvisionnement pour HoloLens à l’aide de [l’Assistant HoloLens.](hololens-provisioning.md)
2. Connectez l’appareil HoloLens à un PC à l’aide d’un câble USB. HoloLens s’affiche en tant qu’appareil dans l’Explorateur de fichiers sur le PC.
3. Faites glisser et déposez le package d’approvisionnement dans le dossier Documents sur HoloLens.

Sur votre HoloLens, suivez les étapes suivantes :
1. Accédez **à Paramètres**  >  **Comptes**Accès Travail ou  >  **Scolaire.** 
2. Dans **paramètres associés,** **sélectionnez Ajouter ou supprimer un package d’approvisionnement.**
3. Sur la page suivante, **sélectionnez Ajouter un package** pour lancer le sélecateur de fichiers et sélectionnez votre package d’approvisionnement. Si le dossier est vide, assurez-vous que vous sélectionnez **Cet appareil** et que vous sélectionnez **Documents.**

Une fois votre package appliqué, il apparaît dans la liste des **packages installés.** Pour afficher les détails du package ou pour supprimer le package de l’appareil, sélectionnez le package répertorié.

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

## Installation de l’application via le package d’approvisionnement

Les applications peuvent être installées via des packages d’approvisionnement sur les appareils HoloLens 2. Cela vous permet de recourir à un package facilement utilisable pour vous aider à distribuer vos applications. Lisez les instructions complètes pour [déployer des applications via des packages d’approvisionnement.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1ère génération) offre une prise en charge limitée de l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package d’approvisionnement. Les appareils HoloLens (1ère génération) ne peuvent installer une application via PPKG qu’en OOBE et uniquement avec les installations de contexte utilisateur.
