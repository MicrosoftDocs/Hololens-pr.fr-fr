---
title: Windows Autopilot pour HoloLens 2
description: Découvrez comment installer, configurer et dépanner Autopilot sur les appareils HoloLens 2.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: sekerawa
ms.openlocfilehash: 05eb629e05395f04ddb8723d58d41db4161896fa
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964579"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pour HoloLens 2

## <a name="overview"></a>Vue d’ensemble

Pour un déploiement à grande échelle, nous vous recommandons de commencer avec Windows Autopilot. Il nécessite une interaction minimale (« low touch ») et simplifie considérablement la configuration des appareils HoloLens pour le service informatique et les utilisateurs finaux. 

À un niveau élevé, un administrateur informatique crée généralement des configurations prêtes à l’emploi et inscrit les appareils HoloLens 2 auprès des portails MDM. Quand les appareils HoloLens 2 démarrent en mode OOBE (out-of-box experience) et se connectent à Internet, ces configurations sont automatiquement téléchargées sur les appareils HoloLens 2 inscrits et appliquées. Les appareils sont alors prêts à l’emploi sans aucune intervention de l’utilisateur.

Pour plus d’informations, consultez l’article [Vue d’ensemble de Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot).

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Scénario Autopilot pris en charge sur HoloLens 2

> [!NOTE]
> La configuration d’Autopilot pour HoloLens dans Microsoft Endpoint Manager passe de **Préversion publique** à **Disponibilité générale**. Tous les locataires pourront configurer Autopilot dans le centre d’administration MEM.

À partir de la version 2004 de Windows Holographique, l’HoloLens 2 prend en charge le [mode de déploiement automatique](/mem/autopilot/self-deploying) de Windows Autopilot avec Microsoft Intune (les MDM tiers ne sont pas en charge). Vous pouvez ainsi réduire les frais généraux de gestion des stocks, le coût de préparation des appareils et les appels au support des employés pendant la configuration. Découvrez-en plus dans la documentation de [Windows Autopilot](/mem/autopilot/windows-autopilot).

Comme pour les appareils Surface, il est conseillé aux utilisateurs de se rapprocher de leur [fournisseur de solutions Microsoft Cloud](https://partner.microsoft.com/cloud-solution-provider) (revendeur ou distributeur) pour obtenir des appareils inscrits auprès du service Autopilot via l’Espace partenaires.

Lorsqu’un utilisateur démarre le processus de déploiement automatique d’Autopilot, Autopilot effectue les étapes suivantes :

1. Joindre l’appareil à Azure Active Directory (Azure AD). Autopilot pour HoloLens ne prend pas en charge la jonction Active Directory ou la jonction Azure AD Hydride.

1. Utiliser Azure AD pour inscrire l’appareil dans le Gestionnaire de points de terminaison Microsoft (ou un autre service GPM).

1. Télécharger et appliquer des stratégies ciblées sur l’appareil, des certificats, des profils et applications réseau.

1. Présenter l’écran de connexion à l’utilisateur.

## <a name="configuring-autopilot-for-hololens-2"></a>Configurer Autopilot pour HoloLens 2

Suivez les étapes ci-dessous pour configurer votre environnement :

1. [Consulter la configuration requise pour Windows Autopilot pour HoloLens 2](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Activer l’inscription automatique pour le GPM](#2-enable-automatic-mdm-enrollment)

1. (Pour Intune uniquement) [Vérifiez que l’inscription MDM n’est pas bloquée pour les appareils Windows.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Inscrire des appareils dans Windows Autopilot](#4-register-devices-in-windows-autopilot)

1. [Créer un groupe d'appareils](#5-create-a-device-group)

1. [Créer un profil AutoPilot et l’affecter au groupe d’appareils.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Créer une configuration Page d’état d’inscription (ESP) et l’affecter au groupe d’appareils.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Vérifier l’état du profil des appareils HoloLens.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Consulter la configuration requise pour Windows Autopilot pour HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Consultez les sections suivantes de l’article relatif aux conditions requises pour Windows Autopilot :

- [Configuration requise pour le réseau](/mem/autopilot/networking-requirements)  
- [Exigences en termes de licence](/mem/autopilot/licensing-requirements)  
- [Exigences de configuration](/mem/autopilot/configuration-requirements)

**Consultez la section « [Configuration requise](/windows/deployment/windows-autopilot/self-deploying#requirements) » de l’article relatif au mode de déploiement autonome Windows Autopilot.** Votre environnement doit répondre à ces exigences et à la configuration standard requise pour Windows Autopilot. Vous n’êtes pas tenu de consulter les sections « Étape par étape » et « Validation » de l’article. Les procédures décrites plus loin dans cet article indiquent les étapes correspondantes spécifiques à l’HoloLens.

Assurez-vous que les appareils ne sont pas déjà membres d’Azure AD et inscrits dans Intune (ou dans un autre système GPM). Le processus de déploiement autonome Autopilot effectue ces étapes. Pour vous assurer que toutes les informations relatives aux appareils sont nettoyées, consultez les pages **Appareils** dans les portails Azure AD et Intune. Actuellement, la fonctionnalité « Convertir tous les appareils ciblés en Autopilot » n’est pas prise en charge sur HoloLens.

#### <a name="review-hololens-os-requirements"></a>Consultez la configuration requise pour le système d’exploitation HoloLens :

Pour vérifier la version de la build sur votre appareil ou effectuer une réinitialisation vers le dernier système d’exploitation, utilisez l’[Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) ainsi que nos [instructions sur la réinitialisation des appareils](hololens-recovery.md). Les appareils livrés jusqu’à fin septembre 2020 disposent de la version 1903 préinstallée de Windows Holographique. Contactez votre revendeur pour vous assurer que les appareils qui vous sont envoyés sont compatibles avec Autopilot.

 Version minimale du système d’exploitation | Fonctionnalité prise en charge | Remarques
 ------ | ------ | ------  
 [Windows Holographique, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) ou ultérieure | 1. Scénario de déploiement automatique d’Autopilot sur HoloLens 2. | Le téléchargement du profil Autopilot n’est pris en charge qu’avec une connexion Ethernet. Assurez-vous que l’HoloLens est connecté à Ethernet à l’aide d’un adaptateur USB-C vers Ethernet **avant de le mettre sous tension**.  Si vous envisagez d’utiliser un déploiement Autopilot sur de nombreux appareils HoloLens, nous vous conseillons de planifier l’infrastructure des adaptateurs. Nous déconseillons les hubs USB, car ils impliquent souvent l’installation de pilotes tiers non pris en charge sur HoloLens.
 [Windows Holographique, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) ou ultérieure | 1. Téléchargement du profil Autopilot sur Wi-Fi. <br> 2. [CSP TenantLockdown et Autopilot](#tenant-lockdown-csp-and-autopilot) pour verrouiller les appareils à un locataire spécifié par Autopilot. | Vous pouvez toujours utiliser des adaptateurs Ethernet si vous le souhaitez. Pour les appareils connectés via un réseau Wi-Fi, l’utilisateur doit : <ul> <li> Passer la scène du colibri. </li> <li> Choisir la langue et les paramètres régionaux. </li> <li> Effectuer l’étalonnage oculaire. </li> <li> Se connecter au réseau Wi-Fi souhaité. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Activer l’inscription automatique pour le GPM

Pour permettre le bon fonctionnement d’Autopilot, vous devez activer l’inscription automatique pour le GPM dans votre portail Azure. Cela permet à l’appareil de s’inscrire sans utilisateur.

Pour de plus amples informations, reportez-vous au [guide d’activation de l’inscription automatique MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) et au [guide de démarrage rapide sur l’inscription automatique](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Vérifier que l’inscription MDM n’est pas bloquée pour les appareils Windows

Pour qu’Autopilot puisse fonctionner, vous devez vérifier que vos appareils HoloLens peuvent s’inscrire. L’HoloLens étant considéré comme un appareil Windows, aucune restriction d’inscription ne doit bloquer votre déploiement. [Passez en revue cette liste de restrictions](/mem/intune/enrollment/enrollment-restrictions-set) pour vérifier que vos appareils pourront être inscrits.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Inscrire des appareils dans Windows Autopilot

Vos appareils doivent être inscrits dans Windows Autopilot avant la première configuration.

Il existe trois méthodes principales pour inscrire des appareils HoloLens :

 - **Le revendeur peut inscrire des appareils dans l’Espace partenaires lorsque vous passez une commande.**

   > [!NOTE]  
   > Il s’agit de la solution recommandée pour ajouter des appareils au service Autopilot. [Plus d’informations](/mem/autopilot/partner-registration)  

 - **Vous pouvez [Envoyer une demande de support](hololens2-autopilot-registration-support.md) directement à Microsoft.**
 - **Récupérez le hachage matériel (également appelé ID matériel) et inscrivez l’appareil manuellement dans le centre d’administration MEM**.

#### <a name="obtain-hardware-hash"></a>Obtenir le hachage matériel

Vous pouvez récupérer le hachage matériel à partir de l’appareil. L’appareil enregistre son hachage dans un fichier CSV lors du processus OOBE, ou par la suite lorsque le propriétaire d’un appareil démarre le processus de collecte des journaux de diagnostic (décrit dans la procédure ci-dessous). En règle générale, le propriétaire de l’appareil est le premier utilisateur à s’y connecter.

> [!WARNING]
> Dans les builds antérieures à 20H2, si vous avez parcouru OOBE et que la télémétrie a été définie sur Obligatoire, vous ne pouvez pas utiliser cette méthode pour récupérer le hachage matériel destiné à Autopilot. Pour récupérer le hachage matériel avec cette méthode, définissez votre option de télémétrie sur Intégral dans l’application Paramètres et sélectionnez **Confidentialité** > **Diagnostics**.

1. Démarrez l’appareil HoloLens 2.

1. Sur l’appareil, appuyez simultanément sur les boutons **Alimentation** and **Baisser le volume**, puis relâchez-les. L’appareil collecte les journaux de diagnostic et le hachage matériel, puis les stocke dans plusieurs fichiers .zip.

1. Pour obtenir des informations complètes et visionner une vidéo explicative, consultez [Diagnostics hors connexion](hololens-diagnostic-logs.md#offline-diagnostics).

1. Utilisez un câble USB-C pour connecter l’appareil à un ordinateur.

1. Sur l’ordinateur, ouvrez l’Explorateur de fichiers. Ouvrez <b>Ce PC\\</b><*Nom de l’appareil HoloLens*><b>\\Stockage interne\\Documents</b>, puis recherchez le fichier AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Le fichier .zip peut ne pas être immédiatement disponible. Si ce fichier n’est pas prêt, vous pouvez afficher un fichier HoloLensDiagnostics.temp dans le dossier Documents. Actualisez la fenêtre pour mettre à jour la liste des fichiers.

1. Extrayez le contenu du fichier AutopilotDiagnostics.zip.

1. Dans les fichiers extraits, localisez le fichier CSV comportant le préfixe de nom de fichier « DeviceHash ». Copiez ce fichier sur un lecteur de l’ordinateur afin de pouvoir y accéder ultérieurement.  

   > [!IMPORTANT]  
   > Les données du fichier CSV doivent utiliser le format d’en-tête et de ligne suivant :
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Inscrire l’appareil à l’aide de MEM

1. Dans le [centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com), sélectionnez **Appareils** > **Windows** > **Inscription Windows**, puis **Appareils** > **Importer** sous **Programme Windows Autopilot Deployment**.

1. Sous **Ajouter des appareils Windows Autopilot**, sélectionnez le fichier CSV DeviceHash, **Ouvrir**, puis **Importer**.  

   > [!div class="mx-imgBorder"]
   > ![Utilisez la commande Importer pour importer le hachage matériel.](./images/hololens-ap-hash-import.png)

1. Une fois l’importation terminée, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Appareils** > **Synchronisation**. L’exécution du processus peut prendre quelques minutes, en fonction du nombre d’appareils en cours de synchronisation. Pour afficher l’appareil inscrit, sélectionnez **Actualiser**.  

   > [!div class="mx-imgBorder"]
   > ![Utilisez les commandes Synchroniser et Actualiser pour afficher la liste des appareils.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Créer un groupe d’appareils

1. Dans le [centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com), sélectionnez **Groupes** > **Nouveau groupe**.

1. Pour le **Type de groupe**, sélectionnez **Sécurité**, puis entrez le nom et la description du groupe.

1. Pour **Type d’appartenance**, sélectionnez **Affecté** ou **Appareil dynamique**.

1. Effectuez l’une des opérations suivantes :  

   - Si vous avez sélectionné **Affecté** pour **Type d’appartenance** à l’étape précédente, sélectionnez **Membres**, puis ajoutez des appareils Autopilot au groupe. Les appareils Autopilot qui ne sont pas encore inscrits sont répertoriés à l’aide de leur numéro de série comme nom d’appareil.
   - Si vous avez sélectionné **Appareils dynamiques** pour **Type d’appartenance** à l’étape précédente, sélectionnez **Membres d’appareils dynamiques**, puis entrez un code dans **Règle avancée** semblable au suivant :
     - Si vous souhaitez créer un groupe comprenant tous vos appareils Autopilot, tapez `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
     - Le champ de balises de groupe d’Intune est mis en correspondance avec l’attribut **OrderID** sur les appareils Azure AD. Pour créer un groupe incluant tous vos appareils Autopilot dotés d’une balise de groupe spécifique (OrderID de l’appareil Azure AD), vous devez taper : `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Pour créer un groupe incluant tous vos appareils Autopilot doté d’un ID de commande fournisseur, tapez : `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Ces règles ciblent des attributs propres aux appareils Autopilot.
1. Sélectionnez **Enregistrer**, puis **Créer**.

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Créer un profil AutoPilot et l’affecter au groupe d’appareils

1. Dans le [centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com), sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Profils de déploiement Windows Autopilot** > **Créer un profil** > **HoloLens**.
   ![La liste déroulante de création de profil inclut un élément HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Entrez le nom et la description du profil, puis sélectionnez **Suivant**.  
   Une liste comprenant **HoloLens** doit s’afficher. Si cette option n’est pas disponible, utilisez l’une des options [Commentaires](hololens2-autopilot.md#feedback-and-support-for-autopilot) pour nous contacter.

   > [!div class="mx-imgBorder"]
   > ![Ajoutez le nom et la description du profil.](./images/hololens-ap-profile-name.png)

1. Dans la page **OOBE (Out-of-box experience)** , la plupart des paramètres sont préconfigurés pour simplifier OOBE dans cette évaluation. Vous pouvez configurer les paramètres suivants :  

   - **Langue (région)**  : sélectionnez la langue pour OOBE. Nous vous recommandons de sélectionner une langue dans la liste des [langues prises en charge pour HoloLens 2](hololens2-language-support.md).
   - **Configurer automatiquement le clavier** : pour vous assurer que le clavier correspond à la langue sélectionnée, sélectionnez **Oui**.
   - **Appliquer un modèle de nom d’appareil** : pour configurer automatiquement le nom de l’appareil pendant le processus OOBE, sélectionnez **Oui**, puis entrez la phrase du modèle et les espaces réservés dans **Entrer un nom** Par exemple, entrez un préfixe et `%RAND:4%`&mdash;un espace réservé pour un nombre aléatoire à 4 chiffres.
     > [!NOTE]  
     > Si vous utilisez un modèle de nom d’appareil, le processus OOBE redémarre l’appareil après l’application du nom d’appareil et avant qu’il ne joigne l’appareil à Azure AD. Ce redémarrage permet l’application du nouveau nom.  

   > [!div class="mx-imgBorder"]
   > ![Configurer les paramètres OOBE.](./images/hololens-ap-profile-oobe.png)

1. Après avoir configuré les paramètres, sélectionnez **Suivant**.
1. Sur la page **Balises d’étendue**, ajoutez les balises d’étendue que vous souhaitez appliquer à ce profil (facultatif). Pour plus d’informations sur les balises d’étendue, voir [Utiliser le contrôle d’accès en fonction du rôle et les balises d’étendue pour l’informatique distribuée](/mem/intune/fundamentals/scope-tags.md). Quand vous avez terminé, sélectionnez **Suivant**.
1. Sur la page **Affectations**, sélectionnez **Groupes sélectionnés** pour **Affecter à**.
1. Sous **GROUPES SÉLECTIONNÉS**, sélectionnez **+ Sélectionner les groupes à inclure**.
1. Dans la liste **Sélectionner les groupes à inclure**, sélectionnez le groupe d’appareils que vous avez créé pour les appareils Autopilot HoloLens, puis sélectionnez **Suivant**.  
  
   Pour exclure des groupes, sélectionnez **Sélectionner les groupes à exclure**, puis les groupes que vous souhaitez exclure.

   > [!div class="mx-imgBorder"]
   > ![Affectation d’un groupe d’appareils au profil.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Sur la page **Vérifier et créer**, vérifiez les paramètres, puis sélectionnez **Créer** pour créer le profil.  

   > [!div class="mx-imgBorder"]
   > ![Examiner + créer](./images/hololens-ap-profile-summ.png).

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Créer une configuration Page d’état d’inscription (ESP) et l’affecter au groupe d’appareils

La page d’état d’inscription (ESP) affiche l’état du processus de configuration d’un appareil complet qui s’exécute quand un utilisateur géré par MDM se connecte à un appareil pour la première fois. Assurez-vous que votre configuration ESP se présente comme suit et vérifiez que les affectations sont correctes.  

> [!div class="mx-imgBorder"]
> ![Configuration ESP.](./images/hololens-ap-profile-settings.png)

Pour plus d’informations sur ESP, consultez [Configurer la page d’état d’inscription (ESP) - Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status).

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Vérifier l’état du profil des appareils HoloLens

1. Dans le centre d’administration Microsoft Endpoint Manager, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Appareils**.

1. Vérifiez que les appareils HoloLens sont répertoriés et que leur état de profil est **Affecté**.  

   > [!NOTE]  
   > L’affectation du profil à l’appareil peut prendre quelques minutes.  

   > [!div class="mx-imgBorder"]
   > ![Affectations d’appareil et de profil.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Expérience utilisateur Windows Autopilot pour HoloLens 2

Une fois les instructions ci-dessus terminées, vos utilisateurs HoloLens 2 accèdent à l’expérience suivante pour configurer leurs appareils HoloLens :  

1. L’interface Autopilot nécessite un accès à Internet. Utilisez l’une des options suivantes pour fournir un accès à Internet :

    - Connectez votre appareil à un réseau Wi-Fi dans OOBE, puis laissez-le détecter automatiquement l’expérience Autopilot. C’est le seul moment où vous devrez interagir avec OOBE, et ce jusqu’à ce que l’expérience Autopilot se termine d’elle-même.

    - Connectez votre appareil à Ethernet à l’aide d’adaptateurs « USB-C vers Ethernet » pour une connexion Internet filaire et laissez HoloLens 2 compléter automatiquement l’expérience Autopilot.

    - Connectez votre appareil avec des adaptateurs « USB-C vers Wi-Fi » pour une connexion Internet sans fil, puis laissez HoloLens 2 s’occuper automatiquement d’Autopilot.

        > [!IMPORTANT]  
       > Les appareils essayant d’utiliser des réseaux Wi-Fi dans OOBE pour Autopilot doivent exécuter [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Pour les appareils utilisant des adaptateurs Ethernet, vous devez connecter l’appareil au réseau avant le démarrage d’OOBE. L’appareil détermine s’il est configuré en tant qu’appareil Autopilot lorsqu’il est sur le premier écran d’OOBE. Si l’appareil ne parvient pas à se connecter au réseau, ou si vous décidez de ne pas configurer l’appareil en tant qu’appareil Autopilot, vous ne pourrez pas utiliser l’approvisionnement Autopilot ultérieurement. Vous devrez alors recommencer cette procédure pour configurer l’appareil en tant qu’appareil Autopilot.

1. L’appareil doit automatiquement démarrer OOBE. N’interagissez pas avec OOBE.

    > [!IMPORTANT]
    > Veuillez ne pas interagir avec OOBE ni appuyer sur le bouton d’alimentation pour mettre le système en veille/arrêt pendant qu’Autopilot est en cours. Cela peut entraîner l’arrêt du flux Autopilot.

   Laissez HoloLens 2 détecter la connectivité réseau et permettez-lui d’exécuter automatiquement OOBE. Il est possible que l’appareil redémarre pendant le processus OOBE. Les écrans OOBE doivent se présenter comme suit.

   ![Étape 1 OOBE.](./images/autopilot-welcome.jpg)
   ![Étape 2 OOBE](./images/autopilot-step-complete.jpg)
   ![Étape 3 OOBE.](./images/autopilot-device-setup.jpg)

1. Au terme du processus OOBE, vous pouvez vous connecter à l’appareil à l’aide de votre nom d’utilisateur et de votre mot de passe.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>CSP TenantLockdown et Autopilot

Les appareils HoloLens 2 prennent en charge le fournisseurs de services TenantLockdown à partir de la version 20H2 de Windows Holographic. Ce fournisseur de solutions Cloud conserve les appareils sur le client de l’organisation en les verrouillant vers ce client, même en cas de réinitialisation ou de redémarrage de l’appareil.

Le fournisseur de solutions Cloud [TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) permet de lier HoloLens 2 à l’inscription GPM en utilisant Autopilot uniquement. Une fois que le nœud RequireNetworkInOOBE du fournisseur de solutions Cloud TenantLockdown a été défini sur la valeur true ou false (initialement définie) dans HoloLens 2, cette valeur est conservée même en cas de réinitialisation, de mise à jour du système d’exploitation, etc.

Une fois le nœud RequireNetworkInOOBE du fournisseur de solutions Cloud TenantLockdown défini sur true sur HoloLens 2, OOBE attend indéfiniment que le profil Autopilot soit téléchargé et appliqué avec succès, après la connectivité réseau.

Une fois le nœud RequireNetworkInOOBE du fournisseur de solutions Cloud TenantLockdown défini sur true sur HoloLens 2, les opérations suivantes ne sont pas autorisées dans OOBE :

- Créer un utilisateur local à l’aide de la configuration de l’exécution
- Exécuter une opération de jointure Azure AD via la configuration de l’exécution
- Sélectionner le propriétaire de l’appareil dans OOBE

#### <a name="how-to-set-this-using-intune"></a>Comment définir cette configuration à l’aide d’Intune ?

1. Créez un profil de configuration d’appareil OMA URI personnalisé et spécifiez true pour le nœud RequireNetworkInOOBE comme indiqué ci-dessous.
La valeur OMA-URI doit être ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Définition du verrouillage du client via OMA-URI.](images/hololens-tenant-lockdown.png)

1. Créez un groupe et attribuez le profil de configuration d’appareil à ce groupe d’appareils.

1. Faites de l’appareil HoloLens 2 un membre du groupe créé à l’étape précédente et déclenchez la synchronisation.  

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Après application de cette configuration à l’appareil HoloLens 2, les effets de TenantLockdown sont actifs.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Comment annuler la configuration de RequireNetworkInOOBE de TenantLockdown sur HoloLens 2 à l’aide d’Intune ?

1. Supprimez HoloLens 2 du groupe d’appareils auquel la configuration d’appareil créée ci-dessus a été précédemment affectée.

1. Créez un profil de configuration d’appareil basé sur OMA URI personnalisé et spécifiez false pour RequireNetworkInOOBE comme indiqué ci-dessous.
La valeur OMA-URI doit être ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de la définition de RequireNetworkInOOBE sur false via OMA-URI dans Intune.](images/hololens-tenant-lockdown-false.png)

1. Créez un groupe et attribuez le profil de configuration d’appareil à ce groupe d’appareils.

1. Faites de l’appareil HoloLens 2 un membre du groupe créé à l’étape précédente et déclenchez la synchronisation.

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois la configuration de l’appareil HoloLens 2 appliquée, les effets de TenantLockdown sont inactifs.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Que se passe-t-il lors du processus OOBE, si le profil Autopilot n’est pas affecté sur un HoloLens après la définition de TenantLockdown sur true ?

OOBE attend indéfiniment le téléchargement du profil Autopilot et la boîte de dialogue suivante s’affiche. Afin de supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit auprès de son client d’origine à l’aide d’Autopilot uniquement et RequireNetworkInOOBE doit être annulé comme décrit à l’étape précédente avant que les restrictions introduites par le fournisseur de solutions Cloud TenantLockdown ne soient supprimées.

![Vue de l’appareil lorsque la stratégie est appliquée.](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Pourquoi l’expérience Autopilot ne s’affiche-t-elle pas, même si le profil Autopilot est attribué dans Intune ?

Par défaut, HoloLens 2 attend 15 secondes avant de détecter Autopilot après avoir détecté Internet. Si aucun profil Autopilot n’est détecté dans les 15 secondes, cela signifie qu’Autopilot n’a pas été découvert correctement. La page du CLUF s’affiche alors.

Redémarrez votre appareil et réessayez. Pour plus d’informations, consultez [Problèmes connus et limitations](hololens2-autopilot.md#known-issues-and-limitations) ou [Résolution des problèmes](hololens2-autopilot.md#troubleshooting).

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Pourquoi est-ce que je vois 0x80180014 pendant Autopilot ?

Il s’agit d’une erreur affichée pendant le processus Autopilot sur l’appareil. Ce problème apparaît seulement quand un appareil HoloLens a effectué les opérations suivantes :

1. Il a déjà subi Autopilot au moins une fois.
1. Il va maintenant être réinitialisé et réutilisé pour Autopilot.

L’expérience est qu’Autopilot échoue avec une erreur spécifique.

![Code d’erreur d’échec Autopilot d’HoloLens](images/autopilot-0x80180014-failure.jpg)

Quelles sont les étapes à suivre pour résoudre cette erreur ?

1. Suivez les étapes de [Résoudre les problèmes liés à l’importation et à l’inscription d’appareils Autopilot](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) pour supprimer l’appareil d’Intune. (Votre administrateur Intune devra effectuer cette tâche)
1. Une fois l’étape 1 terminée, redémarrez l’appareil et connectez-vous.
1. Accédez à **Paramètres** -> **Mise à jour et sécurité** -> **Réinitialiser et récupérer**, puis sélectionnez **Bien démarrer**.
    1. Si vous rencontrez des problèmes avec les étapes 2 et 3, reportez-vous aux alternatives à la réinitialisation de l’appareil dans [Réinitialiser /reflasher HoloLens](hololens-recovery.md).

Autopilot doit alors s’inscrire correctement.

### <a name="troubleshooting"></a>Dépannage

Les articles suivants vous permettront d’en savoir plus et de résoudre les problèmes liés à Autopilot. Toutefois, ces articles sont basés sur la version bureau de Windows 10 et certaines informations ne s’appliquent pas à HoloLens :

- [Windows AutoPilot : problèmes connus](/mem/autopilot/known-issues)
- [Résolution des problèmes d’inscription d’appareils Windows dans Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot : conflits de stratégie](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Commentaires et support pour Autopilot

Pour formuler des commentaires ou signaler des problèmes, utilisez l’une des méthodes suivantes :

- Pour un support relatif à l’inscription des appareils, contactez votre revendeur ou votre distributeur.
- Pour un support relatif à Windows Autopilot ou pour des problèmes tels que les affectations de profil, les contrôles de création de groupe ou de portail MEM, [contactez le support Microsoft Endpoint Manager](/mem/get-support).  
- Si votre appareil est inscrit au service Autopilot et que le profil est affecté sur le portail MEM, contactez le [support](/hololens/) HoloLens (voir la carte « Support »). Ouvrez un ticket de support et, le cas échéant, incluez des captures d’écran et des journaux en capturant les [journaux de diagnostic hors connexion](hololens-diagnostic-logs.md#offline-diagnostics) durant le processus OOBE.
- Pour signaler un problème à partir de l’appareil, utilisez l’application Hub de commentaires sur votre HoloLens. Dans le Hub de commentaires, sélectionnez la catégorie **Gestion d’entreprise** > **Appareil**.
- Pour formuler des commentaires généraux sur Autopilot pour HoloLens, vous pouvez retourner cette [enquête](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993).

## <a name="delete-autopilot-devices"></a>Supprimer des appareils Autopilot

Vous souhaiterez peut-être ne plus utiliser un appareil pour Autopilot ou inscrire vos appareils à un autre locataire. Si c’est le cas, lisez le [guide pratique pour supprimer des appareils Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)
