---
title: Windows Autopilot pour HoloLens2
description: Comment configurer AutoPilot sur les appareils HoloLens2.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 95f187b2a4b6a86b59e05f3b12414c84ca0f6460
ms.sourcegitcommit: fac3e62c1fd4dd531c2c8620870213cd570980dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205766"
---
# Windows Autopilot pour HoloLens2

À partir de la version2004 de Windows Holographic, HoloLens2 prend en charge le [mode de déploiement automatique](https://docs.microsoft.com/mem/autopilot/self-deploying) de Windows Autopilot. Les administrateurs peuvent configurer l’OOBE (out-of-Box Experience) dans le Gestionnaire de points de terminaison Microsoft et permettre aux utilisateurs finaux de préparer les appareils pour une utilisation professionnelle avec peu ou pas d’interaction. Ainsi, vous réduisez les frais généraux de gestion des stocks, le coût de préparation des appareils et les appels d’assistance des employés pendant la configuration. Si vous souhaitez en savoir plus sur Windows Autopilot, cliquez [ici](https://docs.microsoft.com/mem/autopilot/windows-autopilot).

Comme pour les appareils Surface, il est recommandé que les utilisateurs travaillent avec un [fournisseur de solutions cloud](https://partner.microsoft.com/cloud-solution-provider) Microsoft (revendeur ou distributeur) pour obtenir des appareils inscrits auprès du service Autopilot via l’Espace partenaires. D’autres méthodes d’inscription des appareils sont décrites dans [cet article](https://docs.microsoft.com/mem/autopilot/add-devices), même si les partenaires de canal de Microsoft propose la solution de bout en bout la plus efficace. 

> [!NOTE]
> À partir du 20/11/2020, la configuration de Autopilot pour HoloLens dans le Gestionnaire de point de terminaison Microsoft est passée en **Préversion publique**. Les clients n’ont plus besoin de s’inscrire à la préversion privée et tous les clients pourront configurer Autopilot dans le centre d’administration du Gestionnaire de point de terminaison.

Lorsqu’un utilisateur démarre le processus de déploiement automatique d’Autopilot, Autopilot effectue les étapes suivantes:

1. Joindre l’appareil à AzureActiveDirectory (AzureAD). Notez qu’Autopilot pour HoloLens ne prend pas en charge la jointure ActiveDirectory ou la jointure hybride AzureAD.
   
1. Utiliser AzureAD pour inscrire l’appareil dans le Gestionnaire de points de terminaison Microsoft (ou un autre service de gestion des périphériques mobiles).

1. Télécharger et appliquer des stratégies ciblées sur l’appareil, des certificats, des profils et applications réseau.

1. Mettre en service l’appareil.

1. Présenter l’écran de connexion à l’utilisateur.


## Configurer Autopilot pour HoloLens2

Suivez les étapes ci-dessous pour configurer votre environnement:

1. [Consulter la configuration requise pour Windows Autopilot pour HoloLens2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Inscrire des appareils dans Windows Autopilot.](#2-register-devices-in-windows-autopilot)

1. [Créez un groupe d’appareils.](#3-create-a-device-group)

1. [Créer un profil de déploiement.](#4-create-a-deployment-profile)

1. [Vérifier la configuration de la page d’état d’inscription (ESP).](#5-verify-the-esp-configuration)

1. [Vérifiez l’état du profil des appareils HoloLens.](#6-verify-the-profile-status-of-the-hololens-devices)


#### 1. Consulter la configuration requise pour Windows Autopilot pour HoloLens2.

**Consultez les sections suivantes de l’article sur les conditions requises pour Windows Autopilot:**

- [Configuration requise pour le réseau](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Conditions d'octroi de licence](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Configuration requise](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Consultez la section «[Configuration requise](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)» de l’article sur le mode de déploiement autonome Windows Autopilot.** Votre environnement doit répondre à ces exigences, ainsi qu’à la configuration standard requise pour Windows Autopilot. Vous n’avez pas besoin d’étudier les sections «Étape par étape» et «validation» de l’article. Les procédures décrites plus loin dans cet article indiquent les étapes correspondantes spécifiques à HoloLens. Si vous souhaitez en savoir plus sur l’inscription des appareils et la configuration des profils, consultez les sections [2. Inscrire des appareils dans Windows Autopilot](#2-register-devices-in-windows-autopilot) et [4. Créer un profil de déploiement](#4-create-a-deployment-profile) de cet article. Pour configurer et gérer les profils du mode de déploiement automatique de Autopilot, assurez-vous d’avoir accès au [centre d’administration du Gestionnaire de point de terminaison Microsoft](https://endpoint.microsoft.com).

**Consultez la configuration requise pour le système d’exploitation HoloLens:**

- Les appareils doivent utilisés la [version2004 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) ou une version ultérieure. Pour vérifier la version de la build sur votre appareil ou redémarrez le dernier système d’exploitation, vous pouvez utiliser l’[Outil de récupération avancée](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). Vous trouverez des instructions [ici](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). Notez que les appareils livrés jusqu’à fin septembre2020 disposent de la version1903 préinstallée de Windows Holographic. Veuillez contacter votre revendeur pour vous assurer que les appareils qui vous sont expédiés sont compatibles avec Autopilot.

- La version2004 de Windows Holographic ne prend en charge Autopilot que via une connexion Ethernet. Assurez-vous que le HoloLens est connecté à Ethernet à l’aide d’un adaptateur USB-C vers Ethernet **avant de l’allumer**. Aucune interaction utilisateur n’est requise lors du démarrage de l’appareil. Si vous envisagez d’utiliser un déploiement Autopilot sur de nombreux appareils HoloLens, nous vous conseillons de planifier l’infrastructure des adaptateurs. Nous déconseillons les concentrateurs USB, car ils nécessitent souvent l’installation de pilotes tiers supplémentaires qui ne sont pas pris en charge sur HoloLens. 

- La [version20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) ou les versions ultérieures prennent en charge Autopilot via un réseau Wi-Fi, même si vous pouvez toujours utiliser des adaptateurs Ethernet. Pour les appareils connectés via un réseau Wi-Fi, l’utilisateur doit:

     - passer la scène du colibri
     - choisir la langue et les paramètres régionaux
     - effectuer le calibrage visuel
     - établir une connexion réseau


- La version20H2 de Windows Holographic prend en charge le [CSP Tenantlockdown et Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), qui verrouillent un appareil à un client et vérifient que l’appareil reste lié au client en cas de réinitialisation accidentelle ou intentionnelle.  

- Assurez-vous que les appareils ne sont pas déjà membres d’AzureAD et ne sont pas inscrits dans Intune (ou dans un autre système de gestion des périphériques mobiles). Le processus de déploiement automatique Autopilot effectue ces étapes. Pour vous assurer que toutes les informations relatives aux appareils sont nettoyées, consultez les pages **Appareils** dans les Portails AzureAD et Intune. Notez que la fonctionnalité «Convertir tous les appareils ciblés en Autopilot» n’est pas prise en charge sur HoloLens pour le moment.  

### 2. Inscrire des appareils dans Windows Autopilot

Vos appareils doivent être inscrits dans Windows Autopilot avant la première configuration. Pour la documentation du Gestionnaire de point de terminaison sur l’enregistrement des appareils, veuillez consulter l’article [Ajouter des appareils au pilote automatique](https://docs.microsoft.com/mem/autopilot/add-devices).  

Il existe deux méthodes principales pour inscrire des appareils HoloLens: 

 - **Le revendeur peut inscrire des appareils dans l’Espace partenaires lorsque vous passez une commande.** 

   > [!NOTE]  
   > Il s’agit de la solution recommandée pour ajouter des appareils au service Autopilot. [En savoir plus ](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).  
   
 - **Récupérez le hachage du matériel (également connu sous le nom d'ID matériel) et enregistrez l'appareil manuellement dans le centre d'administration MEM**. 

**Récupérer le hachage du matériel**

L’appareil enregistre son hachage au sein d’un fichier CSV lors du processus OOBE, ou par la suite lorsque le propriétaire d’un appareil démarre le processus de collection du journal de diagnostic (décrit dans la procédure ci-dessous). En règle générale, le propriétaire de l’appareil est le premier utilisateur à se connecter sur l’appareil.

1. Démarrez l’appareil HoloLens2.

1. Sur l’appareil, appuyez en même temps sur les boutons **Marche/arrêt** et **Baisser le volume** , puis relâchez-les. L’appareil recueille les journaux de diagnostics et le hachage matériel, puis les stocke dans un ensemble de fichiers .zip. 

   1. Si vous souhaitez obtenir des informations complètes et une vidéo d’instructions sur la façon de procéder, consultez l’article [Diagnostics hors connexion](hololens-diagnostic-logs.md#offline-diagnostics). 
   
1. Utilisez un câble USB-C pour connecter l’appareil à un ordinateur.

1. Ouvrez l’Explorateur de fichiers sur l’ordinateur. Ouvrez **Ce PC\\\<*HoloLens device name*>\\Stockage interne\\Documents**, puis recherchez le fichier AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Il se peut que le fichier .zip ne soit pas immédiatement disponible. Si le fichier n’est pas encore prêt, vous pouvez afficher un fichier HoloLensDiagnostics.temp dans le dossier Documents. Actualisez la fenêtre pour mettre à jour la liste des fichiers.

1. Extrayez le contenu du fichier AutopilotDiagnostics.zip.

1. Dans les fichiers extraits, localisez le fichier CSV comportant le préfixe de nom de fichier «DeviceHash». Copiez ce fichier sur un lecteur d’un ordinateur auquel vous pouvez accéder ultérieurement.  

   > [!IMPORTANT]  
   > Les données du fichier CSV doivent utiliser le format d’en-tête et de ligne suivant:
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**Inscrire l’appareil à l’aide du Gestionnaire de point de terminaison**

1. Dans le [centre d’administration du Gestionnaire de point de terminaison Microsoft](https://endpoint.microsoft.com), sélectionnez **Appareils** > **Windows** > **Inscription Windows**, puis **Appareils** > **Importer** sous **Programme Windows Autopilot Deployment**.

1. Sous **Ajouter des appareils Windows Autopilot**, sélectionnez le fichier CSV DeviceHash, puis **Ouvrir**, et enfin **Importer**.  
   
   > [!div class="mx-imgBorder"]
   > ![Utilisez la commande Importer pour importer le hachage matériel.](./images/hololens-ap-hash-import.png)
   
1. Une fois l’importation terminée, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Appareils** > **Synchronisation**. L’exécution du processus peut prendre quelques minutes, en fonction du nombre d’appareils en cours de synchronisation. Pour afficher l’appareil enregistré, sélectionnez **Actualiser**.  
   
   > [!div class="mx-imgBorder"]
   > ![Utilisez les commandes Synchroniser et Actualiser pour afficher la liste des appareils.](./images/hololens-ap-devices-sync.png)  

### 3. Créer un groupe d’appareils

1. Dans le [centre d’administration du Gestionnaire de point de terminaison Microsoft](https://endpoint.microsoft.com), sélectionnez **Groupes** > **Nouveau groupe**.

1. Pour le **Type de groupe**, sélectionnez **Sécurité**, puis saisissez le nom et la description du groupe.

1. Pour le **Type d’appartenance**, sélectionnez **Attribué** ou **Appareil dynamique**.

1. Effectuez l'une des opérations suivantes:  
   
   - Si vous avez sélectionné **Attribué** pour le **Type d’appartenance** au cours de l’étape précédente, sélectionnez **Membres**, puis ajoutez des appareils Autopilot au groupe. Les appareils Autopilot qui ne sont pas encore inscrits sont répertoriés en utilisant le numéro de série de l’appareil comme nom d’appareil.
   - Si vous avez sélectionné **Appareil dynamique** pour le **Type d’appartenance** à l’étape précédente, sélectionnez **Membres de l’appareil dynamique**, puis saisissez un code dans **Règle avancée** semblable à celui qui suit:
     - Si vous souhaitez créer un groupe qui inclut tous vos appareils Autopilot, tapez: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Le champ Balise du groupe Intune met en correspondance vers l’attribut **OrderID** sur les appareils Azure AD. Si vous voulez créer un groupe qui inclut tous vos appareils Autopilot qui ont une Balise de groupe spécifique (OrderID de l’appareil Azure AD), vous devez taper: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Si vous voulez créer un groupe qui inclut tous vos appareils Autopilot qui ont un ID de commande fournisseur, tapez: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Ces règles ciblent des attributs propres aux appareils Autopilot.
1. Cliquez sur **Enregistrer**, puis sélectionnez **Créer**.

### 4. Créer un profil de déploiement

1. Dans le [centre d’administration du Gestionnaire de point de terminaison Microsoft](https://endpoint.microsoft.com), sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Profils de déploiement Windows Autopilot ** > **Créer un profil** > **HoloLens**.
   ![La liste déroulante de création de profil inclut un élément HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Entrez le nom et la description du profil, puis sélectionnez **Suivant**.  
   Une liste comprenant **HoloLens** doit s’afficher. Si cette option n’est pas disponible, utilisez l’une des options de [Commentaires](hololens2-autopilot.md#feedback-and-support-for-autopilot) pour nous contacter.

   > [!div class="mx-imgBorder"]
   > ![Ajoutez le nom et la description du profil](./images/hololens-ap-profile-name.png)
   
1. Dans la page **Out-of-box experience (OOBE)**, la plupart des paramètres sont préconfigurés pour simplifier OOBE dans cette évaluation. Vous pouvez configurer de manière facultative les paramètres suivants:  

   - **Langue (région)**: sélectionnez la langue pour l’application OOBE. Nous vous recommandons de sélectionner une langue dans la liste des [Langues prises en charge pour HoloLens 2](hololens2-language-support.md).
   - **Configurer automatiquement le clavier**: pour vous assurer que le clavier correspond à la langue sélectionnée, sélectionnez **Oui**.
   - **Appliquer le modèle de nom d’appareil**: pour configurer automatiquement le nom de l’appareil pendant le processus OOBE, sélectionnez **Oui**, puis entrez la phrase du modèle et les espaces réservés dans **Entrer un nom** Par exemple, saisissez un préfixe et `%RAND:4%`&mdash;un espace réservé pour un nombre aléatoire à 4chiffres.
     > [!NOTE]  
     > Si vous utilisez un modèle de nom d’appareil, l’application OOBE redémarre l’appareil une nouvelle fois après l’application du nom d’appareil et avant qu’il ne joigne l’appareil à Azure AD. Ce redémarrage permet l’application du nouveau nom.  

   > [!div class="mx-imgBorder"]
   > ![Configurez les paramètres de l’application OOBE](./images/hololens-ap-profile-oobe.png)
   
1. Après avoir configuré les paramètres, sélectionnez **Suivant**.
1. Sur la page **Balises d’étendue**, ajoutez les balises d’étendue que vous voulez appliquer à ce profil si vous le souhaitez. Pour plus d’informations sur les balises d’étendue, voir [Utiliser le contrôle d’accès en fonction du rôle (RBAC) et les balises d’étendue pour l’informatique distribuée](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Lorsque vous avez terminé, sélectionnez **Suivant**.
1. Dans la page **Affectations**, sélectionnez **Groupes sélectionnés** pour les **Attribuer**.
1. Sous **GROUPES SÉLECTIONNÉS**, sélectionnez **+ sélectionner les groupes à inclure**.
1. Dans la liste **sélectionner les groupes à inclure**, sélectionnez le groupe d’appareils que vous avez créé pour les appareils Autopilot HoloLens, puis sélectionnez **Suivant**.  
  
   Si vous voulez exclure des groupes, sélectionnez **Sélectionner des groupes à exclure**, puis sélectionnez les groupes que vous voulez exclure.

   > [!div class="mx-imgBorder"]
   > ![Affectation d’un groupe d’appareils au profil.](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. Sur la page **Examiner et créer**, examinez les paramètres, puis sélectionnez **Créer** pour créer le profil.  
   
   > [!div class="mx-imgBorder"]
   > ![Examiner et créer](./images/hololens-ap-profile-summ.png)

### 5. Vérifier la configuration ESP

La page du statut de l’inscription (ESP) affiche l’état du processus de configuration d’un appareil complet qui s’exécute lorsqu’un utilisateur géré par MDM se connecte à un appareil pour la première fois. Assurez-vous que votre configuration de la Page du statut de l’inscription (ESP) ressemble à ce qui suit et vérifiez que les affectations sont correctes.  

> [!div class="mx-imgBorder"]
> ![Configuration ESP](./images/hololens-ap-profile-settings.png)

### 6. Vérifier l’état du profil des appareils HoloLens

1. Dans le Centre d’administration du Gestionnaire de point de terminaison Microsoft, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Appareils**.

1. Vérifiez que les appareils HoloLens sont répertoriés et que leur statut de profil est **Attribué**.  

   > [!NOTE]  
   > L’attribution du profil de l’appareil peut prendre quelques minutes.  

   > [!div class="mx-imgBorder"]   
   > ![Attributions d’appareil et de profil.](./images/hololens-ap-devices-assignments.png)

## Expérience utilisateur de Windows Autopilot pour HoloLens2

Une fois les instructions ci-dessus terminées, vos utilisateurs HoloLens2 passent par l’expérience suivante pour configurer leurs appareils HoloLens:  

1. L’interface de Autopilot nécessite un accès à Internet. Utilisez l’une des options suivantes pour fournir un accès à Internet:

    - Connectez votre appareil à un réseau Wi-Fi dans l’application OOBE, puis laissez-le détecter automatiquement l’expérience Autopilot. C’est le seul moment où vous devrez interagir avec l’application OOBE, et ce jusqu’à ce que l’expérience de Autopilot se termine d’elle-même. Notez que, par défaut, HoloLens2 attend 10secondes avant de détecter Autopilot après avoir détecté Internet. Si aucun profil AutoPilot n’est détecté dans un délai de 10secondes, l’application OOBE présentera le CLUF. Si vous rencontrez ce problème, redémarrez votre appareil pour pouvoir détecter AutoPilot. Notez également que l’application OOBE peut attendre indéfiniment Autopilot uniquement si la stratégie TenantLockdown est définie sur l’appareil.
    
    - Connectez votre appareil à Ethernet à l’aide d’adaptateurs «USB-C vers Ethernet» pour une connexion Internet filaire et laissez HoloLens2 compléter automatiquement l’expérience Autopilot.
    
    - Connectez votre appareil avec des adaptateurs «USB-C vers Wifi» pour une connexion Internet sans fil et laissez HoloLens2 compléter l’expérience Autopilot automatiquement.

        > [!IMPORTANT]  
       > Les appareils qui tentent d’utiliser les réseaux Wi-Fi dans l’application OOBE pour Autopilot doivent disposer de la [version20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Pour les périphériques utilisant des adaptateurs Ethernet, vous devez connecter le périphérique au réseau avant le démarrage de l’application Out-of-the-Box-Experience (OOBE). L’appareil détermine s’il est configuré en tant qu’appareil Autopilot lorsqu’il est sur le premier écran de l’application OOBE. Si l’appareil ne parvient pas à se connecter au réseau, ou si vous décidez de ne pas configurer l’appareil en tant qu’appareil Autopilot, vous ne pourrez pas utiliser la mise en service Autopilot à une date ultérieure. Au lieu de cela, vous devrez recommencer cette procédure pour configurer l’appareil en tant qu’appareil Autopilot.

1. L’appareil doit démarrer l’application OOBE automatiquement. Ne pas interférer avec l’application OOBE. Au lieu de cela, il ne vous reste qu’à vous détendre. Laissez HoloLens 2 détecter la connectivité réseau et permettez-lui d’exécuter l’application OOBE automatiquement. Il est possible que l’appareil redémarre pendant le processus OOBE. Les écrans de l’application OOBE doivent ressembler à ce qui suit.
   
   ![OOBE étape1](./images/autopilot-welcome.jpg)
   ![OOBE étape2](./images/autopilot-step-complete.jpg)
   ![OOBE étape3](./images/autopilot-device-setup.jpg)

1. À la fin du processus OOBE, vous pouvez vous connecter à l’appareil à l’aide de votre nom d’utilisateur et de votre mot de passe.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## CSP Tenantlockdown et Autopilot

Les appareils HoloLens2 prennent en charge le fournisseurs de services TenantLockdown à partir de la version20H2 de Windows Holographic. Ce CSP conserve les appareils sur le client de l’organisation en les verrouillant vers ce client, même avec une réinitialisation ou un redémarrage de l’appareil. 

Le CSP [TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) permet à HoloLens2 d’être lié à l’inscription de la gestion des périphériques mobiles à l’aide de Autpilot uniquement. Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur la valeur true ou false (initialement définie) sur HoloLens2, cette valeur reste sur l’appareil malgré le redémarrage, les mises à jour du système d’exploitation, etc. 

Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur true sur HoloLens2, l’application OOBE attend indéfiniment que le profil Autopilot soit téléchargé et appliqué avec succès, après la connectivité réseau. 

Une fois que le nœud RequireNetworkInOOBE du CSP TenantLockdown est défini sur true sur HoloLens2, les opérations suivantes ne sont pas autorisées dans l’application OOBE: 
- Créer un utilisateur local à l’aide de la configuration de l’exécution 
- Exécuter une opération de jointure AAD via la configuration de l’exécution 
- Sélectionner le propriétaire de l’appareil dans l’application OOBE 

#### Comment définir cette configuration à l’aide de Intune? 
1. Créez un profil de configuration de périphérique URI OMA personnalisé et spécifiez true pour le nœud RequireNetworkInOOBE comme indiqué ci-dessous.
La valeur OMA-URI doit être ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Définition du verrouillage du client via OMA-URI](images/hololens-tenant-lockdown.png)

1. Créez un groupe et attribuez le profil de configuration de périphérique à ce groupe d’appareils. 

1. Faites de l’appareil HoloLens2 un membre du groupe créé à l’étape précédente et déclenchez la synchronisation.  

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois que la configuration de l’appareil HoloLens 2 s’applique correctement, les effets de TenantLockdown seront actifs.

#### Comment annuler la configuration de RequireNetworkInOOBE de TenantLockdown sur HoloLens2 avec Intune? 
1. Supprimez HoloLens2 du groupe d’appareils auquel la configuration d’appareil créée ci-dessus a été précédemment affectée. 

1. Créez un profil de configuration de périphérique basé sur OMA URI personnalisé et spécifiez false pour RequireNetworkInOOBE comme indiqué ci-dessous. La valeur OMA-URI doit être ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran de la définition de RequireNetworkInOOBE sur false via un URI OMA dans Intune](images/hololens-tenant-lockdown-false.png)

1. Créez un groupe et attribuez le profil de configuration de périphérique à ce groupe d’appareils. 

1. Faites de l’appareil HoloLens2 un membre du groupe créé à l’étape précédente et déclenchez la synchronisation.

Vérifiez que la configuration de l’appareil a été appliquée dans le portail Intune. Une fois la configuration de l’appareil HoloLens 2 appliquée, les effets de TenantLockdown seront désactivés. 

#### Que se passe-t-il pendant le processus OOBE, si le profil Autopilot n’est pas affecté sur un HoloLens après la définition de TenantLockdown sur true. 
L’application OOBE attend indéfiniment le téléchargement du profil AutoPilot et la boîte de dialogue suivante s’affichera. Afin de supprimer les effets de TenantLockdown, l’appareil doit d’abord être inscrit auprès de son client d’origine à l’aide de Autopilot uniquement et RequireNetworkInOOBE doit être annulé comme décrit à l’étape précédente avant que les restrictions introduites par le CSP TenantLockdown ne soient supprimées. 

![Vue de l’appareil lorsque la stratégie est appliquée à l’appareil.](images/hololens-autopilot-lockdown.png)

## Problèmes connus et limitations

- Nous travaillons à la résolution d’un problème dans lequel l’installation de l’application basée sur le périphérique configurée dans le GPM ne s’applique pas au HoloLens. [En savoir plus sur les installations de contexte des appareils et des utilisateurs.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Lors de la configuration d’Autopilot sur un réseauWi-Fi, il se peut que le profile Autopilot n’est pas téléchargé lors de la première connexion à Internet. Dans ce cas, le Contrat de Licence Utilisateur Final (CLUF) est présenté et l’utilisateur a la possibilité de procéder à l’installation sans AutoPilot. Pour réessayer la configuration avec Autopilot, mettez l’appareil en veille, puis rallumez-le, ou redémarrez l’appareil et laissez-le réessayer.
- La fonctionnalité «convertir tous les appareils ciblés en Autopilot» n’est pas prise en charge sur HoloLens pour le moment.  

### Résolution des problèmes

Les articles suivants peuvent être utiles pour vous permettre d’obtenir plus d’informations et de résoudre les problèmes liés à Autopilot. Ces articles sont basés sur la version bureau Windows10, certaines informations ne s’appliquent donc pas à HoloLens:
- [Windows AutoPilot: problèmes connus](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Résoudre les problèmes d’inscription des appareils Windows dans Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: conflits de stratégie](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Commentaires et support pour Autopilot

Pour donner votre avis ou signaler des problèmes, utilisez l’une des méthodes suivantes:

- Pour obtenir de l’aide concernant l’inscription des appareils, contactez votre revendeur ou votre distributeur.
- Pour obtenir une assistance générale concernant Windows Autopilot ou pour des problèmes tels que les affectations de profil, les contrôles de création de groupe ou de portail de gestion des point de terminaison, [contactez le support du Gestionnaire de point de terminaison Microsoft](https://docs.microsoft.com/mem/get-support)  
- Si votre appareil est inscrit au service Autopilot et que le profil est affecté sur le portail de gestion des points de terminaison, contactez le [support](https://docs.microsoft.com/hololens/) HoloLens (voir la carte «Support»). Ouvrez un ticket de support et, le cas échéant, incluez des captures d’écran et des journaux en capturant les [journaux de diagnostic hors connexion](hololens-diagnostic-logs.md#offline-diagnostics) pendant le processus OOBE (out-of-Box-Experience).
- Pour signaler un problème à partir de l’appareil, utilisez l’application Hub de commentaires sur votre HoloLens. Dans le Hub de commentaires, sélectionnez la catégorie **Gestion d’entreprise** > **Appareil**. 
- Pour fournir des commentaires généraux sur Autopilot pour HoloLens, vous pouvez retourner ce [sondage](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) . 


