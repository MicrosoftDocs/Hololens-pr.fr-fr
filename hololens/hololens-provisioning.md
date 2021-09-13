---
title: configurer des HoloLens à l’aide d’un package de configuration (HoloLens)
description: L’approvisionnement Windows aide les administrateurs informatiques à configurer les appareils des utilisateurs finaux sans d’acquisition d’images.
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
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032904"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>configurer des HoloLens à l’aide d’un package d’approvisionnement

l' [approvisionnement Windows](/windows/configuration/provisioning-packages/provisioning-packages) permet aux administrateurs informatiques de configurer facilement des appareils pour les utilisateurs finaux sans créer d’image. Windows Le concepteur de configuration est un outil permettant de configurer les images et les paramètres d’exécution qui sont ensuite intégrés aux packages d’approvisionnement.

voici quelques-unes des configurations HoloLens que vous pouvez appliquer dans un package d’approvisionnement :

- mettre à niveau vers [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Configuration d’un compte local
- Configuration d'une connexion Wi-Fi
- Appliquer des certificats à l’appareil
- Activer le mode développeur
- Configurez le mode plein écran en suivant les [instructions détaillées](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens).

## <a name="provisioning-package-hololens-wizard"></a>assistant HoloLens du package d’approvisionnement

l’assistant HoloLens vous aide à configurer les paramètres suivants dans un package d’approvisionnement :

- Mise à niveau vers l’édition Enterprise

    > [!NOTE]
    > cela ne doit être utilisé que pour HoloLens premier appareil gen. Paramètres dans un package de configuration ne sont appliquées que si le package d’approvisionnement inclut une licence de mise à niveau d’édition pour Windows Holographic for Business ou si [l’appareil a déjà été mis à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- configurer la première expérience HoloLens (OOBE)
- Configurer le réseau Wi-Fi
- inscrire l’appareil dans Azure Active Directory ou créer un compte local
- Ajout de certificats
- Activer le mode développeur
- Configurez le mode plein écran en suivant les [instructions détaillées](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens).

> [!WARNING]
> vous devez exécuter Windows concepteur de Configuration sur Windows 10 pour configurer l’inscription Azure Active Directory à l’aide de l’un des assistants.

Les packages de configuration peuvent inclure des instructions de gestion et des stratégies, des stratégies et des connexions réseau personnalisées, et bien plus encore.

> [!TIP]
> Utilisez l’Assistant de bureau pour créer un package avec les paramètres communs, puis basculez vers l’éditeur avancé pour ajouter d’autres paramètres, applications, stratégies, etc.

## <a name="steps-for-creating-provisioning-packages"></a>Étapes de création de packages d’approvisionnement

1. **Option 1 :** [à partir de Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). cela comprend HoloLens 2 fonctionnalités.
2. **Option 2 :** [dans le Kit de déploiement et d’évaluation (ADK) Windows pour Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). si vous installez Windows concepteur de configuration à partir du Windows ADK, sélectionnez **concepteur de configurations** dans la boîte de dialogue **sélectionner les fonctionnalités à installer** . cette option n’inclut pas les fonctionnalités de HoloLens 2.

> [!NOTE]
> si vous savez que vous allez utiliser un PC hors connexion qui a besoin d’accéder à Windows concepteur de Configuration, suivez les instructions [installation de l’application hors connexion (hololens-recovery. md # download-arc-sans-using-app-store) pour le guide de récupération avancé. faites Windows concepteur de Configuration votre sélection. 

### <a name="2-create-the-provisioning-package"></a>2. créer le package d’approvisionnement

utilisez l’outil concepteur de Configuration Windows pour créer un package d’approvisionnement.

1. ouvrez Windows concepteur de Configuration (par défaut,%windir%\Program Files (x86) \ Windows Kits\10\Assessment and Deployment Kit\Imaging et Configuration Designer\x86\ICD.exe).

2. sélectionnez **approvisionner les appareils HoloLens**.

   ![Options de démarrage d’ICD.](images/icd-create-options-1703.png)

3. Nommez votre projet, puis sélectionnez **Terminer**.

4. Lisez les instructions de la page **mise en route** , puis sélectionnez **suivant**. Les pages pour l’approvisionnement du bureau vous guident tout au long des étapes suivantes.
  
> [!IMPORTANT]
> Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers du projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.

### <a name="configure-settings"></a>Configurer les paramètres

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>recherchez et sélectionnez le fichier de licence d’entreprise pour mettre à niveau l’édition HoloLens.</br></br>Vous pouvez également activer/désactiver <strong>Oui</strong> ou <strong>non</strong> pour masquer les parties de la première expérience.</br></br>Pour configurer l’appareil sans avoir besoin de se connecter à un réseau Wi-Fi, basculez <strong>Wi-Fi le programme d’installation</strong> <strong>sur activé</strong>.</br></br>Sélectionnez une région et un fuseau horaire dans lesquels l’appareil sera utilisé. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Dans cette section, vous pouvez entrer les détails de la Wi-Fi réseau sans fil auquel l’appareil doit se connecter automatiquement. Pour ce faire, sélectionnez <strong>activé</strong>, entrez le SSID, le type de réseau (<strong>ouvert</strong> ou <strong>WPA2-personnel</strong>) et (si <strong>WPA2-personnel</strong>) le mot de passe du réseau sans fil.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>vous pouvez inscrire l’appareil dans Azure Active Directory ou créer un compte local sur l’appareil.</br></br>avant d’utiliser un Windows assistant concepteur de Configuration pour configurer l’inscription d’Azure AD en bloc, configurez <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD jointure dans votre organisation</a>. Le paramètre <strong>nombre maximal de périphériques par utilisateur</strong> dans votre locataire Azure ad détermine le nombre de fois que le jeton en bloc que vous recevez dans l’Assistant peut être utilisé. Pour inscrire l’appareil dans Azure AD, sélectionnez cette option et entrez un nom convivial pour le jeton en bloc que vous allez obtenir à l’aide de l’Assistant. Définissez une date d’expiration pour le jeton (la valeur maximale est de 30 jours à compter de la date d’obtenir le jeton). Sélectionnez <strong>recevoir un jeton en bloc</strong>. Dans la fenêtre <strong>laisser&#39;s vous être connecté</strong> , entrez un compte disposant des autorisations nécessaires pour joindre un appareil à Azure ad, puis le mot de passe. sélectionnez <strong>accepter</strong> pour permettre Windows concepteur de Configuration les autorisations nécessaires. </br></br>Pour créer un compte local, sélectionnez cette option et entrez un nom d’utilisateur et un mot de passe. </br></br><strong>Précieuse</strong> <br />(pour Windows 10, version 1607 uniquement) si vous créez un compte local dans le package d’approvisionnement, vous devez modifier le mot de passe à l’aide de l’application <strong>Paramètres</strong> tous les 42 jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Pour approvisionner l’appareil avec un certificat, cliquez sur <strong>Ajouter un certificat</strong>. Entrez un nom pour le certificat, puis recherchez et sélectionnez le certificat à utiliser.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Activez ou désactivez la <strong>valeur Oui</strong> ou <strong>non</strong> pour activer le Mode développeur sur le HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">En savoir plus sur le mode développeur.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Ne définissez pas un mot de passe pour protéger votre package d’approvisionnement. si le package de configuration est protégé par un mot de passe, l’approvisionnement de l’appareil HoloLens échoue.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Sélectionnez **Créer** quand vous avez terminé. Cela ne prend que quelques secondes. Lorsque le package est généré, l’emplacement où est stocké le package est affiché sous forme de lien hypertexte au bas de la page.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. créer un package d’approvisionnement pour HoloLens à l’aide de l’approvisionnement avancé

> [!NOTE]
> un package d’approvisionnement que vous créez dans l' **approvisionnement avancé** n’a pas besoin d’inclure une licence de mise à niveau d’édition pour Windows Holographic for Business pour s’appliquer correctement à un HoloLens (1er génération). [en savoir plus sur Windows Holographic for Business pour HoloLens (1ère génération)](hololens1-upgrade-enterprise.md).

1. dans la page de démarrage du concepteur de Configuration Windows, sélectionnez **approvisionnement avancé**.
2. Dans la fenêtre **Entrez les détails du projet**, spécifiez un nom et un emplacement pour votre projet. Si vous le souhaitez, saisissez une brève description du projet.

3. Sélectionnez **Suivant**.

4. dans la fenêtre **choisir les paramètres à afficher et à configurer** , sélectionnez **Windows 10 Holographique**, puis cliquez sur **suivant**.

5. Sélectionnez **Terminer**.

6. Développez **paramètres d’exécution** et personnalisez le package en utilisant l’un des paramètres [décrits plus loin dans cet article](#what-you-can-configure).

    > [!IMPORTANT]
    > (pour Windows 10, version 1607 uniquement) si vous créez un compte local dans le package d’approvisionnement, vous devez modifier le mot de passe à l’aide de l’application **Paramètres** tous les 42 jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter. Si le compte d’utilisateur est verrouillé, vous devez [effectuer une récupération complète de l’appareil](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Sélectionnez **fichier**  >  **Enregistrer**.

8. Lisez l’avertissement indiquant que les fichiers projet peuvent contenir des informations sensibles, puis sélectionnez **OK**.

    > [!IMPORTANT]
    > Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers du projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.

9. Sélectionnez **Exporter** le  >  **package de provisionnement**.

10. Changez le **propriétaire** en **administrateur informatique**. Cela permet de définir la priorité de ce package d’approvisionnement à une valeur supérieure à celle des packages d’approvisionnement appliqués à cet appareil à partir d’autres sources. Sélectionnez **Suivant**.

11. Définissez une valeur pour **Package Version**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

12. Dans **Sélectionner les détails de sécurité pour le package d’approvisionnement**, sélectionnez **suivant**.

    > [!WARNING]
    > si vous chiffrez le package d’approvisionnement, l’approvisionnement de l’appareil HoloLens échoue.  

13. Sélectionnez **suivant** pour spécifier l’emplacement de sortie où vous souhaitez que le package de configuration se trouve une fois qu’il a été créé. par défaut, Windows concepteur de Configuration utilise le dossier du projet comme emplacement de sortie.

    Si vous le souhaitez, vous pouvez sélectionner **Parcourir** pour modifier l’emplacement de sortie par défaut.

14. Sélectionnez **Suivant**.

15. Sélectionnez **Build** pour commencer à générer le package. Les informations du projet s'affichent sur la page de génération, et la barre de progression indique l'état de la génération.

16. Une fois la génération terminée, sélectionnez **Terminer**.

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>appliquer un package d’approvisionnement à HoloLens pendant l’installation

HoloLens 2 appareils sur Windows holographique, version 2004 ou version [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) ou ultérieure, peut utiliser un lecteur USB pour appliquer un package d’approvisionnement. Copiez simplement le fichier. ppkg à la racine du lecteur USB. Les packages d’approvisionnement seront appliqués uniquement s’ils sont à la racine du lecteur USB. Le package d’approvisionnement multiple présent sera appliqué de manière séquentielle.

HoloLens 2 appareils sur [Windows version holographique 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou version ultérieure ont des fonctionnalités plus récentes qui permettent de rationaliser et de simplifier ce processus, ce qui le rend automatique. Consultez les sections suivantes :

- [Lancement automatique de l’approvisionnement à partir d’USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Confirmer automatiquement les packages de provisionnement dans OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Approvisionnement automatique sans interface utilisateur](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. utilisez le câble usb pour connecter l’appareil à un PC (ou un lecteur USB pour HoloLens 2 comme indiqué ci-dessus), puis démarrez l’appareil. Ne continuez pas au-delà de la première page du moment de l' **interaction** de OOBE.
    - sur HoloLens (1re génération), cette page contient une zone bleue.
    - sur HoloLens 2, cette page contient hummingbird.

2. Appuyez brièvement sur les boutons **Baisser le volume** et **Alimentation** en même temps, puis relâchez-les.

3. HoloLens apparaît comme un appareil dans l’explorateur de fichiers sur le PC.

4. Dans l’Explorateur de fichiers, faites glisser-déplacer le package d’approvisionnement (.ppkg) sur l'espace de stockage de l’appareil.

5. Appuyez sur la touche et relâchez les boutons de réduction et **d’alimentation** du **volume** simultanément à la première page du moment de l' **interaction** de OOBE.

6. L’appareil vous demande si vous faites confiance au package et que vous souhaitez l’appliquer. Confirmez que vous faites confiance au package.

7. Vous verrez si le package a été appliqué avec succès ou non. En cas d’échec, vous pouvez corriger votre package et essayer à nouveau. Si l'opération a réussi, passez à la phase OOBE.

> [!NOTE]
> Si l’appareil a été acheté avant le 2016 août, vous devez vous connecter à l’appareil à l’aide d’un compte Microsoft, obtenir la dernière mise à jour du système d’exploitation, puis réinitialiser le système d’exploitation afin d’appliquer le package d’approvisionnement.

### <a name="auto-launch-provisioning-from-usb"></a>Lancement automatique de l’approvisionnement à partir d’USB

- Processus automatisés permettant une utilisation moins importante de l’utilisateur quand des lecteurs USB avec des packages d’approvisionnement sont utilisés pendant l’OOBE.

Avant cette version, les utilisateurs devaient lancer l’écran d’approvisionnement manuellement lors de l’approvisionnement à l’aide d’une combinaison de boutons. Désormais, les utilisateurs peuvent ignorer la combinaison de boutons à l’aide d’un package d’approvisionnement sur un lecteur de stockage USB.

1. Brancher le lecteur USB avec le package d’approvisionnement pendant la première heure d’interaction d’OOBE
1. Lorsque l’appareil est prêt à être approvisionné, il ouvre automatiquement l’invite avec la page de configuration.

Remarque : si un lecteur USB reste branché pendant le démarrage de l’appareil, OOBE énumère les dispositifs de stockage USB existants, ainsi que des éléments supplémentaires qui sont connectés.

En savoir plus sur l' [application des packages de provisionnement au cours d’OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmer automatiquement les packages de provisionnement dans OOBE
- Processus automatisé autorisant moins d’intervention de l’utilisateur, lorsque la page package d’approvisionnement s’affiche, tous les packages répertoriés sont automatiquement appliqués.

Lorsque l’écran principal de configuration s’affiche, OOBE compte 10 secondes avant de commencer à appliquer automatiquement tous les packages d’approvisionnement. Les utilisateurs peuvent toujours confirmer ou annuler pendant ces 10 secondes après avoir vérifié les packages attendus.

### <a name="automatic-provisioning-without-using-ui"></a>Approvisionnement automatique sans interface utilisateur
- Processus automatiques combinés pour réduire les interactions de l’appareil pour l’approvisionnement. 

en associant le lancement automatique de l’approvisionnement à partir des périphériques USB et la confirmation automatique des packages de provisionnement, un utilisateur peut approvisionner HoloLens 2 appareils automatiquement sans utiliser l’interface utilisateur de l’appareil, ni même porter l’appareil. Vous pouvez continuer à utiliser le même lecteur USB et le même package de configuration pour plusieurs appareils. Cela est utile pour déployer plusieurs appareils à la fois dans la même zone. 

1. [créez un Package d’approvisionnement](hololens-provisioning.md) à l’aide de [Windows concepteur de Configuration](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copiez le package sur un lecteur de stockage USB.
1. [flashez votre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) sur [19041,1361 ou une version plus récente](https://aka.ms/hololens2previewdownload). 
1. Lorsque l' [Assistant de récupération avancée](https://www.microsoft.com/store/productId/9P74Z35SFRS8) a terminé le clignotement de votre appareil, débranchez le câble USB-C. 
1. Branchez votre lecteur USB sur l’appareil.
1. lorsque l’appareil HoloLens 2 démarre dans OOBE, il détecte automatiquement le package d’approvisionnement sur le lecteur USB et lance la page de configuration.
1. Après 10 secondes, l’appareil applique automatiquement le package d’approvisionnement. 

Votre appareil est maintenant configuré et affiche l’écran de réussite de l’approvisionnement.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>appliquer/supprimer un package d’approvisionnement à HoloLens après l’installation

> [!NOTE]
> ces étapes s’appliquent à tous les appareils HoloLens 2 et aux appareils HoloLens (1er génération) sur Windows holographique, version 1809 et versions ultérieures.

Sur votre PC, procédez comme suit :
1. créez un package d’approvisionnement comme décrit dans [créer un package d’approvisionnement pour HoloLens à l’aide de l’assistant HoloLens](hololens-provisioning.md).
2. Connecter le HoloLens appareil à un PC à l’aide d’un câble USB. HoloLens apparaît comme un appareil dans l’explorateur de fichiers sur le PC.
3. Glissez-déposez le package d’approvisionnement dans le dossier documents du HoloLens.

sur votre HoloLens, procédez comme suit :
1. Accédez à **Paramètres** > **Comptes** > **Accès scolaire ou professionnel**. 
2. dans **Paramètres connexes**, sélectionnez **ajouter ou supprimer un package d’approvisionnement**.
3. Sur la page suivante, sélectionnez **Ajouter un package** pour lancer le sélecteur de fichiers et sélectionner votre package d’approvisionnement. Si le dossier est vide, veillez à sélectionner **cet appareil** , puis sélectionnez **documents**.

Une fois votre package appliqué, il s’affiche dans la liste des **packages installés**. Pour afficher les détails du package ou pour supprimer le package de l’appareil, sélectionnez le package listé.

## <a name="what-you-can-configure"></a>Ce que vous pouvez configurer

Les packages d’approvisionnement utilisent des fournisseurs de services de configuration (CSP). Si vous n’êtes pas familiarisé avec les CSP, lisez la rubrique [Présentation des fournisseurs de services de configuration (CSP) pour les professionnels de l’informatique](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

dans Windows concepteur de Configuration, lorsque vous créez un package d’approvisionnement pour Windows holographique, les paramètres des **personnalisations disponibles** sont basés sur des [fournisseurs de services de chiffrement pris en charge dans Windows holographique](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). Le tableau suivant décrit les paramètres que vous pouvez souhaiter configurer pour HoloLens.

![Paramètres d’exécution courants pour HoloLens.](images/icd-settings.png)

| Paramètre | Description |
| --- | --- |
| **Certificats** | Déployer un certificat pour HoloLens.  |
| **ConnectivityProfiles** | Déployer un profil Wi-Fi pour HoloLens.   |
| **EditionUpgrade** | [Effectuez une mise à niveau vers Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Stratégies** | Autoriser ou interdire le mode développeur sur HoloLens. [Stratégies prises en charge par Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Installation d’application par le biais du package d’approvisionnement

les applications peuvent être installées par le biais de packages de configuration sur des appareils HoloLens 2. Cela permet de disposer d’un package facilement réutilisable que vous pouvez utiliser pour vous aider à distribuer vos applications. Lisez les instructions complètes pour le déploiement d’applications à l' [aide de packages d’approvisionnement](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1re génération) a limité la prise en charge de l’installation d’applications (**UniversalAppInstall**) à l’aide d’un package d’approvisionnement. les appareils HoloLens (1er génération) prennent uniquement en charge l’installation d’une application via PPKG uniquement au cours de l’installation OOBE et uniquement avec les installations de contexte utilisateur.
