---
title: Windows Autopilot pour HoloLens2 (préversion privée)
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 8f62c09fd569e6c5dbeb961ae023c6f3cefff879
ms.sourcegitcommit: 72be5b64e90dde339323012997440dfaca182027
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2020
ms.locfileid: "10895788"
---
# Windows Autopilot pour HoloLens2

Lorsque vous configurez les appareils HoloLens 2 pour le programme Windows Autopilot, vos utilisateurs peuvent suivre un processus simple pour configurer les appareils dans le cloud.

Ce programme Autopilot prend en charge le mode Autopilot de déploiement autonome pour configurer les appareils HoloLens2 en tant qu’appareils partagés sous votre client. Le mode de déploiement autonome exploite l’image et les pilotes préinstallés par le fabricant de l’appareil au cours du processus de mise en service. Un utilisateur peut configurer l’appareil sans le mettre en route et passer par l’application out-of-box experience (OOBE). Pour en savoir plus sur Windows AutoPilot pour Windows10, cliquez [ici](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

Lorsqu’un utilisateur démarre le processus Autopilot de déploiement autonome, le processus effectue les étapes suivantes:

1. Joindre l’appareil à Azure ActiveDirectory (AzureAD).
   > [!NOTE]  
   > Autopilot pour HoloLens ne prend pas en charge la jonction Active Directory ou Azure AD Hybride.
1. Utilisez Azure AD pour inscrire l’appareil dans Microsoft Intune (ou un autre service GPM).
1. Téléchargez les stratégies destinées aux appareils, les applications destinées aux utilisateurs, les certificats et les profils de réseau.
1. Mettez en service l’appareil.
1. Présentez l’écran de connexion à l’utilisateur.

## Windows Autopilot pour HoloLens2 Préversion privée

Suivez les étapes ci-dessous pour configurer votre environnement pour la préversion privée:

1. Vérifiez que vous remplissez les conditions requises de Windows Autopilot pour HoloLens2
1. Inscrivez-vous au programme Windows Autopilot pour HoloLens 2 préversion privée
1. Vérifiez que votre locataire est activé (inscrit pour participer au programme).
1. Inscrivez vous appareils dans Windows Autopilot
1. Créez un groupe d’appareils
1. Créez un profil de déploiement
1. Vérifiez la configuration de la Page du statut de l’inscription (ESP)
1. Configurez un profil de configuration personnalisé pour les appareils HoloLens (problème connu)
1. Vérifiez le statut du profil des appareils HoloLens.


### 1. Vérifiez que vous remplissez les conditions requises de Windows Autopilot pour HoloLens2

**Consultez les sections suivantes de l’article sur les conditions requises pour Windows Autopilot:**

- [Configuration requise pour le réseau](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Conditions d'octroi de licence](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Configuration requise](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Consultez la section «[Configuration requise](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)» de l’article sur le mode de déploiement autonome Windows Autopilot.** Votre environnement doit répondre à ces exigences, ainsi qu’à la configuration standard requise pour Windows Autopilot. Vous n’avez pas besoin d’étudier les sections «Étape par étape» et «validation» de l’article. Les procédures décrites plus loin dans cet article indiquent les étapes correspondantes spécifiques à HoloLens. Pour plus d’informations sur l’enregistrement des appareils et la configuration des profils, voir [4. Inscrire des appareils dans Windows Autopilot](#4-register-devices-in-windows-autopilot) et [6. Créez un profil de déploiement](#6-create-a-deployment-profile) dans cet article. Ces sections indiquent les étapes spécifiques à HoloLens.

> [!IMPORTANT]  
> Contrairement aux autres programmes Windows Autopilot, Windows Autopilot pour HoloLens 2 exige une configuration de système d’exploitation particulière. Autopilot s’appuie sur Windows holographique version2004 (Build 19041,1103 ou version ultérieure) préinstallé sur les appareils HoloLens. Les appareils livrés jusqu’à la fin août 2020 ont la version Windows holographique version1903 préinstallée. Veuillez contacter votre distributeur pour savoir quand les appareils prêts pour Autopilot peuvent vous être expédiés. Si vous souhaitez participer à la préversion privée, veuillez consulter les instructions et les conditions requises ci-dessous.

**Si vous souhaitez essayer la préversion Autopilot, avant de démarrer le processus OOBE et la mise en service, assurez-vous que les appareils HoloLens respectent les conditions suivantes:**

- Vous devez installer manuellement la dernière version du système d’exploitation (Windows holographique version2004 (Build 19041,1103 ou version ultérieure) à l’aide de l’[Outil de récupération avancée (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). Vous trouverez des instructions [ici](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). 
- Vos appareils doivent être inscrits dans Windows AutoPilot. Pour plus d’informations sur l’inscription des appareils, consultez [4. Inscrivez les appareils dans Windows Autopilot](#4-register-devices-in-windows-autopilot). 
- Dans la version actuelle, les appareils doivent être connectés à Internet avant d’activer le service HoloLens et de lancer le processus de mise en service de Autopilot. Connectez votre appareil à Ethernet à l’aide des adaptateurs «USB C vers Ethernet» pour la connectivité internet câblée ou des adaptateurs «USB C vers WiFi» pour la connectivité internet sans fil. 
- Les appareils ne sont pas membres d’Azure AD et ne sont pas inscrits dans Intune (ou dans un autre système GPM). Le processus de déploiement autonome Autopilot effectue ces étapes. Pour vous assurer que toutes les informations relatives à l’appareil sont nettoyées, vérifiez les pages sur les **Appareils** dans les Portails Azure AD et Intune.
- Pour configurer et gérer les profils du mode de déploiement autonome Autopilot, assurez-vous que vous avez accès au [Centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com).


### 2. Inscrivez-vous au programme Windows Autopilot pour HoloLens 2

**Pour participer au programme, vous devez faire en sorte que votre locataire soit inscrit au programme de préversion privée pour obtenir les contrôles d’interface utilisateur Intune propres à HoloLens pour Autopilot.** Pour ce faire, accédez à [Demande d’aperçu privé Windows Autopilot pour HoloLens](https://aka.ms/APHoloLensTAP) ou utilisez le code QR suivant pour envoyer une demande.  

![Code QR Autopilot](./images/hololens-ap-qrcode.png)  

Dans cette demande, fournissez les informations suivantes:

- Domaine du client
- ID du client
- Nombre d’appareils HoloLens 2 participant à cette évaluation
- Nombre d’appareils HoloLens 2 que vous envisagez de déployer en utilisant le mode de déploiement autonome Autopilot

### 3. Vérifiez que votre client est activé

Pour vérifier que votre client est activé pour le programme Autopilot après avoir envoyé votre demande, procédez comme suit:

1. Connectez-vous au [Centre d’administration Microsoft Endpoint Manager](https://endpoint.microsoft.com).
1. Sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Profils de déploiement Windows Autopilot** > **Créer un profil**.  
   
   ![La liste déroulante de création de profil inclut un élément HoloLens.](./images/hololens-ap-enrollment-profiles.png)
  Une liste comprenant **HoloLens** doit s’afficher. Si cette option n’est pas disponible, utilisez l’une des options de [Commentaires](#feedback) pour nous contacter.

### 4. Inscrivez les appareils dans Windows Autopilot

Dans la phase de préparation, deux méthodes s’offrent à vous pour inscrire des appareils dans Windows Autopilot: 

1. **Contacter votre distributeur ou revendeur lorsque vous passez une commande pour que vos appareils soient inscrits** ou
2. **Récupérez le code de hachage matériel (également appelé ID matériel) et inscrivez l’appareil manuellement.** 

Pour plus d’informations sur l’inscription de l’appareil, consultez la documentation [ajout d’appareils à Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices).  

**Récupérer un hachage matériel d’appareil**

L’appareil peut enregistrer son hachage matériel dans un fichier CSV durant le processus OOBE, ou ultérieurement lorsqu’un propriétaire d’appareil démarre le processus de collecte de journal de diagnostic (décrit dans la procédure ci-dessous). En règle générale, le propriétaire de l’appareil est le premier utilisateur à se connecter sur l’appareil.

1. Démarrez l’appareil HoloLens2.
1. Sur l’appareil, appuyez sur les boutons Alimentation et Baisser le volume en même temps, puis relâchez-les. L’appareil recueille les journaux de diagnostics et le hachage matériel, puis les stocke dans un ensemble de fichiers .zip.
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

**Inscrivez l’appareil dans Windows Autopilot**

1. Dans le Centre d’administration Microsoft Endpoint Manager, sélectionnez **Appareils** > **Windows** > **Inscription Windows**, puis sélectionnez **Appareils** > **Importer** sous le**Programme de déploiement Windows Autopilot**.

1. Sous **Ajouter des appareils Windows Autopilot**, sélectionnez le fichier CSV DeviceHash, puis sélectionnez **Ouvrir**, et enfin **Importer**.  
   
   ![Utilisez la commande Importer pour importer le hachage matériel.](./images/hololens-ap-hash-import.png)
1. Une fois l’importation terminée, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Appareils** > **Synchronisation**. L’exécution du processus peut prendre quelques minutes, en fonction du nombre d’appareils en cours de synchronisation. Pour afficher l’appareil enregistré, sélectionnez **Actualiser**.  
   
   ![Utilisez les commandes Synchroniser et Actualiser pour afficher la liste des appareils.](./images/hololens-ap-devices-sync.png)  

### 5. Créez un groupe d’appareils

1. Dans le Centre d’administration Microsoft Endpoint Manager, sélectionnez **Groupes** > **Nouveau groupe**.
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

### 6. Créez un profil de déploiement

1. Dans le centre d’administration Microsoft Endpoint Manager, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Profils de déploiement Windows Autopilot** > **Créer un profil** > **HoloLens**.
1. Entrez le nom et la description du profil, puis sélectionnez **Suivant**.  
   
   ![Ajoutez le nom et la description du profil](./images/hololens-ap-profile-name.png)
1. Dans la page **Out-of-box experience (OOBE)**, la plupart des paramètres sont préconfigurés pour simplifier OOBE dans cette évaluation. Vous pouvez configurer de manière facultative les paramètres suivants:  

   - **Langue (région)**: sélectionnez la langue pour l’application OOBE. Nous vous recommandons de sélectionner une langue dans la liste des [Langues prises en charge pour HoloLens 2](hololens2-language-support.md).
   - **Configurer automatiquement le clavier**: pour vous assurer que le clavier correspond à la langue sélectionnée, sélectionnez **Oui**.
   - **Appliquer le modèle de nom d’appareil**: pour configurer automatiquement le nom de l’appareil pendant le processus OOBE, sélectionnez **Oui**, puis entrez la phrase du modèle et les espaces réservés dans **Entrer un nom** Par exemple, saisissez un préfixe et `%RAND:4%`&mdash;un espace réservé pour un nombre aléatoire à 4chiffres.
     > [!NOTE]  
     > Si vous utilisez un modèle de nom d’appareil, l’application OOBE redémarre l’appareil une nouvelle fois après l’application du nom d’appareil et avant qu’il ne joigne l’appareil à Azure AD. Ce redémarrage permet l’application du nouveau nom.  

   ![Configurez les paramètres de l’application OOBE](./images/hololens-ap-profile-oobe.png)
1. Après avoir configuré les paramètres, sélectionnez **Suivant**.
1. Sur la page **Balises d’étendue**, ajoutez les balises d’étendue que vous voulez appliquer à ce profil si vous le souhaitez. Pour plus d’informations sur les balises d’étendue, voir [Utiliser le contrôle d’accès en fonction du rôle (RBAC) et les balises d’étendue pour l’informatique distribuée](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Lorsque vous avez terminé, sélectionnez **Suivant**.
1. Dans la page **Affectations**, sélectionnez **Groupes sélectionnés** pour les **Attribuer**.
1. Sous **GROUPES SÉLECTIONNÉS**, sélectionnez **+ sélectionner les groupes à inclure**.
1. Dans la liste **sélectionner les groupes à inclure**, sélectionnez le groupe d’appareils que vous avez créé pour les appareils Autopilot HoloLens, puis sélectionnez **Suivant**.  
  
   Si vous voulez exclure des groupes, sélectionnez **Sélectionner des groupes à exclure**, puis sélectionnez les groupes que vous voulez exclure.

   ![Affectation d’un groupe d’appareils au profil.](./images/hololens-ap-profile-assign-devicegroup.png)
1. Sur la page **Examiner et créer**, examinez les paramètres, puis sélectionnez **Créer** pour créer le profil.  
   
   ![Examiner et créer](./images/hololens-ap-profile-summ.png)

### 7. Vérifiez la configuration de la Page du statut de l’inscription (ESP)

La page du statut de l’inscription (ESP) affiche l’état du processus de configuration d’un appareil complet qui s’exécute lorsqu’un utilisateur géré par MDM se connecte à un appareil pour la première fois. Assurez-vous que votre configuration de la Page du statut de l’inscription (ESP) ressemble à ce qui suit et vérifiez que les affectations sont correctes.  

![Configuration de la Page du statut de l’inscription (ESP)](./images/hololens-ap-profile-settings.png)

### 8. Vérifiez le statut du profil des appareils HoloLens.

1. Dans le Centre d’administration Microsoft Endpoint Manager, sélectionnez **Appareils** > **Windows** > **Inscription Windows** > **Appareils**.
1. Vérifiez que les appareils HoloLens sont répertoriés et que leur statut de profil est **Attribué**.  
   > [!NOTE]  
   > L’attribution du profil de l’appareil peut prendre quelques minutes.  
   
   ![Attributions d’appareil et de profil.](./images/hololens-ap-devices-assignments.png)

## Expérience utilisateur de Windows Autopilot pour HoloLens2

Une fois les instructions ci-dessus terminées, vos utilisateurs HoloLens 2 passent par l’expérience suivante pour configurer leurs appareils HoloLens:  

1. Comme mentionné dans la version actuelle, les appareils doivent être connectés à Internet avant d’activer le service HoloLens et de lancer le processus de mise en service de Autopilot. Connectez votre appareil à Ethernet à l’aide des adaptateurs «USB C vers Ethernet» pour la connectivité internet câblée ou des adaptateurs «USB C vers WiFi» pour la connectivité internet sans fil.
   
   > [!IMPORTANT]  
   > Vous devez connecter l’appareil au réseau avant le démarrage de l’application Out-of-the-Box-Experience (OOBE). L’appareil détermine s’il est configuré en tant qu’appareil Autopilot lors de l’affichage du premier écran de l’application OOBE. Si l’appareil ne parvient pas à se connecter au réseau, ou si vous décidez de ne pas configurer l’appareil en tant qu’appareil Autopilot, vous ne pourrez pas utiliser la mise en service Autopilot à une date ultérieure. Au lieu de cela, vous devrez recommencer cette procédure pour configurer l’appareil en tant qu’appareil Autopilot.

1. L’appareil doit démarrer l’application OOBE automatiquement. Ne pas interférer avec l’application OOBE. Au lieu de cela, il ne vous reste qu’à vous détendre. Laissez HoloLens 2 détecter la connectivité réseau et permettez-lui d’exécuter l’application OOBE automatiquement. Il est possible que l’appareil redémarre pendant le processus OOBE. Les écrans de l’application OOBE doivent ressembler à ce qui suit.
   
   ![OOBE étape 1](./images/hololens-ap-uex-1.png)
   ![OOBE étape 2](./images/hololens-ap-uex-2.png)
   ![OOBE étape 3](./images/hololens-ap-uex-3.png)
   ![OOBE étape 4](./images/hololens-ap-uex-4.png)

1. À la fin du processus OOBE, vous pouvez vous connecter à l’appareil à l’aide de votre nom d’utilisateur et de votre mot de passe.

  ![Étape 5 du processus OOBE](./images/hololens-ap-uex-5.png)

## Problèmes connus

- Vous ne pouvez pas installer d’applications qui utilisent le contexte de sécurité de l’appareil.

## Commentaires

Pour fournir des commentaires ou signaler des problèmes, utilisez l’une des méthodes suivantes:

- Utilisez l’application Hub de commentaires. Cette application est accessible depuis un ordinateur connecté à HoloLens. Dans le Hub de commentaires, sélectionnez la catégorie **Gestion d’entreprise** > **Appareil**.  

  Lorsque vous envoyez des commentaires ou signalez un problème, fournissez une description détaillée. Le cas échéant, inclure des captures d’écran et des journaux.
- Envoyez un courrier électronique à [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com). En ce qui concerne l’objet de l’e-mail, saisissez **\<*Tenant*>Commentaire d’évaluation sur Autopilot HoloLens 2** (où \<*Tenant*> est le nom de votre client Intune).

  Fournissez une description détaillée dans votre message. Cependant, sauf si l’équipe du support le demande spécifiquement, n’incluez pas de données telles que des captures d’écran ou des journaux. Ces données peuvent comprendre des informations privées ou d’identification personnelle (PII).
