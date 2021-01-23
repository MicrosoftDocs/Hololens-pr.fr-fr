---
title: Problèmes connus avec HoloLens
description: Restez à jour avec notre liste des problèmes connus et des solutions de contournement qui peuvent affecter les clients et les développeurs HoloLens à l’aide d’Unity et de Windows Device Portal.
keywords: résolution des problèmes, problème connu, aide
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284075"
---
# Problèmes connus avec HoloLens

Il s’agit de la liste actuelle des problèmes connus pour les appareils HoloLens. Vérifiez d’abord ici si vous voyez un comportement impair. Cette liste sera mise à jour à mesure que de nouveaux problèmes seront détectés ou signalés, ou que des problèmes seront résolus dans les futures mises à jour logicielles HoloLens.

>[!NOTE]
> - Si vous découvrez un problème qui ne bloque pas, signalez-le sur votre appareil HoloLens via [le Hub de commentaires.](hololens-feedback.md)
> - Si le problème que vous êtes confronté vous bloque, en plus de classer les commentaires, [déposez une demande de support.](https://aka.ms/hlsupport)

- [Problèmes connus pour toutes les générations HoloLens](#known-issues-for-all-hololens-generations)
- [Problèmes connus pour les appareils HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problèmes connus pour HoloLens (1ère génération)](#known-issues-for-hololens-1st-gen)
- [Problèmes connus pour l’émulateur HoloLens](#known-issues-for-hololens-emulator)

## Problèmes connus pour toutes les générations HoloLens

### Unity

- Voir [Installer les outils](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pour la version la plus récente d’Unity recommandée pour le développement HoloLens.
- Les problèmes connus avec unity HoloLens Technical Preview sont documentés dans les [forums HoloLens Unity](https://forum.unity3d.com/threads/known-issues.394627/).

### WindowsDevicePortal

- La fonctionnalité Aperçu en direct dans la capture de réalité mixte peut présenter plusieurs secondes de latence.

- Dans la page Entrée virtuelle, les contrôles Mouvement et Défilement sous la section Mouvements virtuels ne sont pas fonctionnels. Leur utilisation n’aura aucun effet. Le clavier virtuel sur la même page fonctionne correctement.

- Après l’activation du Mode développeur dans Paramètres, l’activation du portail d’appareil peut prendre quelques secondes avant que le commutateur soit activé.

### Chargement de l’appareil photo OneDrive

L’application OneDrive pour HoloLens ne prend pas en charge le chargement automatique de l’appareil photo pour les comptes scolaires ou de travail.

Solutions de contournement :

- S’il est viable pour votre entreprise, le chargement automatique d’appareil photo est pris en charge sur les comptes Microsoft grand public. Vous pouvez vous inscrire à votre compte Microsoft en plus de votre compte scolaire ou scolaire (l’application OneDrive prend en charge la double sign-in). À partir de votre profil de compte Microsoft dans OneDrive, vous pouvez activer le chargement automatique de l’appareil photo en arrière-plan.

- Si vous ne pouvez pas utiliser en toute sécurité un compte Microsoft grand public pour télécharger automatiquement vos photos, vous pouvez charger manuellement des photos sur votre compte scolaire ou scolaire à partir de l’application OneDrive. Pour ce faire, assurez-vous que vous êtes bien inscrit à votre compte scolaire ou scolaire dans l’application OneDrive. Sélectionnez **+** le bouton et choisissez **Télécharger.** Recherchez les photos ou vidéos que vous souhaitez télécharger en naviguant vers **Images > pellicule .** Sélectionnez les photos ou vidéos que vous souhaitez télécharger, puis sélectionnez le **bouton** Ouvrir.

## Problèmes connus pour les appareils HoloLens 2

### Le lancement de Microsoft Edge échoue

Quelques clients ont signalé un problème dans lequel Microsoft Edge ne parvient pas à se lancer. Pour ces clients, le problème persiste lors du redémarrage et n’est pas résolu avec les mises à jour windows ou d’applications. Si vous rencontrez ce problème et que vous avez confirmé que [Windows](hololens-updates.md#manually-check-for-updates)est à [](hololens-feedback.md) jour, veuillez déposer un bogue à partir de l’application Hub de commentaires avec la catégorie et la sous-catégorie suivantes : Installer et mettre à jour les > Téléchargement, installation et configuration de Windows Update.

Il n’existe aucune solution de contournement connue, car nous n’avons pas pu à l’origine du problème jusqu’à présent. Le classement d’un bogue via le Hub de commentaires nous aidera à faire l’objet d’une enquête !

### Le clavier ne bascule pas vers des caractères spéciaux

Il existe un problème lors de la OOBE, où une fois que l’utilisateur a choisi un compte scolaire ou scolaire et a entré son mot de passe, en essayant de basculer vers les caractères spéciaux du clavier en appuyant sur le bouton &123 ne change pas en caractères spéciaux. 

Les contourner :
-   Fermez le clavier et rouvrez-le en appuyant sur le champ de texte.
-   Entrez votre mot de passe de manière incorrecte. Lorsque le clavier est relancé la prochaine fois, il fonctionne comme prévu.
- Authentification web, fermez le clavier et **sélectionnez Se connectez à partir d’un autre appareil.** 
-   Si vous entrez uniquement des nombres, un utilisateur peut appuyer et maintenir certaines touches pour ouvrir un menu développé.
-   Utilisation d’un clavier USB.

Cela n’affecte pas :
- Utilisateurs qui choisissent d’utiliser un compte personnel.

### L’écran bleu s’affiche après la désinscrire des builds Insider Preview sur un appareil réessaillé avec une build Insider

This is an issue affecting that affects users who are on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unnrolled from the Insider program. 

Cela n’affecte pas :
- Utilisateurs qui ne sont pas inscrits à Windows Insider 
- Insiders :
    - Si un appareil a été inscrit depuis la version 18362.x des builds Insider
    - S’ils ont flashé une build Insider 19041.x et restent inscrits au programme Insider 

Contourner : 
- Éviter le problème 
    - Flashez une build non insider. Une des mises à jour mensuelles régulières. 
    - Restez sur Insider Preview
- Barre oblique inverse de l’appareil

    1. Mettez [manuellement l’HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) en mode clignotant en l’élémentant complètement sans se connecter. Ensuite, tout en maintenant le volume enfoncé, appuyez sur le bouton d’alimentation.
    
    1. Connectez-vous au PC et ouvrez Advanced Recovery Companion. 
    
    1. Flashez HoloLens 2 sur la build par défaut.   

## Problèmes connus pour HoloLens (1ère génération)

### Impossible de se connecter à HoloLens et de le déployer via Visual Studio

> [!NOTE]
> Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue. Nous vous recommandons de mettre à jour cette dernière version pour éviter cette erreur.

Visual Studio a publié VS 2019 Version 16.2, qui inclut un correctif à ce problème. Nous vous recommandons de mettre à jour cette dernière version pour éviter cette erreur.

Cause première du problème : les utilisateurs qui ont utilisé Visual Studio 2015 ou les versions antérieures d’Visual Studio 2017 pour déployer et déboguer des applications sur leur HoloLens, puis qui ont ensuite utilisé les dernières versions de Visual Studio 2017 ou Visual Studio 2019 avec le même HoloLens seront affectés. Les versions les plus récentes de Visual Studio déploient une nouvelle version d’un composant, mais les fichiers de l’ancienne version sont laissés sur l’appareil, entraînant l’échec de la nouvelle version.  Cela provoque le message d’erreur suivant : DEP0100 : Assurez-vous que le mode développeur est activé sur l’appareil cible. Could not obtain a developer license on \<ip\> due to error 80004005.

#### Solution de contournement

Notre équipe travaille actuellement sur un correctif. En attendant, vous pouvez utiliser les étapes suivantes pour contourner le problème et débloquer le déploiement et le débogage :  

1. Ouvrez Visual Studio.

1. Sélectionner **un nouveau**  >  **projet**de  >  **fichier.**

1. Sélectionnez **Visual C#**  >  **Application de console**de bureau Windows  >  **(.NET Framework).**

1. Donnez un nom au projet (par exemple, « HoloLensDeploymentFix ») et assurez-vous que l’infrastructure est définie sur au moins .NET Framework 4.5, puis sélectionnez **OK**.

1. Cliquez avec le bouton droit sur le nœud **Références** dans l’Explorateur de solutions et ajoutez les références suivantes (sélectionnez la **section** Parcourir et sélectionnez **Parcourir)**:

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Si la version 10.0.18362.0 n’est pas installée, utilisez la version la plus récente. 

1. Cliquez avec le bouton droit sur le projet dans l’Explorateur de solutions et **sélectionnez Ajouter**  >  **un élément existant.**

1. Accédez à C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 et modifiez le filtre en **All Files (\*.\*).**

1. Sélectionnez les SirepClient.dll et SshClient.dll, puis sélectionnez **Ajouter.**

1. Recherchez et sélectionnez les deux fichiers dans l’Explorateur de solutions **** (ils doivent se **** trouver en bas de la liste des fichiers) et modifiez Copier dans le répertoire de sortie dans la fenêtre Propriétés pour toujours **copier.**

1. En haut du fichier, ajoutez ce qui suit à la liste `using` d’instructions existante :

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. À `static void Main(...)` l’intérieur de , ajoutez le code suivant :

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Sélectionnez ****  >  **Build Build Solution**.

1. Ouvrez une fenêtre d’invite de commandes et cd vers le dossier qui contient le fichier .exe compilé (par exemple, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Exécutez l’exécutable et fournissez l’adresse IP de l’appareil en tant qu’argument de ligne de commande. (Si vous êtes connecté à l’aide d’une clé USB, vous pouvez utiliser 127.0.0.1, sinon utilisez l’adresse IP Wi-Fi'appareil.)  Par exemple, « HoloLensDeploymentFix 127.0.0.1 ».

1. Une fois l’outil sorti sans aucun message (cela ne devrait prendre que quelques secondes), vous pourrez désormais déployer et déboguer à partir d’Visual Studio 2017 ou d’une nouvelle génération.  L’utilisation continue de l’outil n’est pas nécessaire.

Nous fournirons d’autres mises à jour dès qu’elles seront disponibles.

### Problèmes lors du lancement du Microsoft Store et des applications sur HoloLens

> [!NOTE]
> Dernière mise à jour : 02/04/2010 - Problème résolu. 

Vous pouvez être face à des problèmes lors de la tentative de lancement du Microsoft Store et des applications sur HoloLens. Nous avons déterminé que le problème se produit lorsque des mises à jour d’application en arrière-plan déploient une version plus récente des packages d’infrastructure dans des séquences spécifiques pendant qu’une ou plusieurs de leurs applications dépendantes sont toujours en cours d’exécution. Dans ce cas, une mise à jour automatique de l’application a remis une nouvelle version de .NET Native Framework (version 10.0.25531 à 10.0.27413) a provoqué une mise à jour non correcte des applications en cours d’exécution pour toutes les applications qui utilisent la version antérieure de l’infrastructure.  Le flux pour la mise à jour de l’infrastructure est le suivant : 

1. Le nouveau package d’infrastructure est téléchargé à partir du Store et installé.

1. Toutes les applications utilisant l’ancienne infrastructure sont « mises à jour » pour utiliser la version la plus récente.

Si l’étape 2 est interrompue avant la fin, toutes les applications pour lesquelles la nouvelle infrastructure n’a pas été inscrite ne pourront pas être lancées à partir du menu Démarrer.  Nous pensons que n’importe quelle application sur HoloLens pourrait être affectée par ce problème.

Certains utilisateurs ont signalé que la fermeture d’applications suspendues et le lancement d’autres applications telles que le Hub de commentaires, la visionneuse 3D ou Photos résout le problème pour eux. Toutefois, cela ne fonctionne pas 100 % du &mdash; temps.

Nous avons dû à la racine que ce problème n’était pas à l’origine de la mise à jour proprement dite, mais d’un bogue dans le système d’exploitation qui a entraîné une gestion incorrecte de la mise à jour de .NET Native Framework. Nous sommes heureux d’annoncer que nous avons identifié un correctif et publié une mise à jour (os version 17763.380) contenant le correctif.  

Pour voir si votre appareil peut prendre la mise à jour, veuillez :

1. Go to the Settings app and open **Update & Security**.

1. Sélectionnez **Vérifier les mises à jour.**

1. Si la mise à jour vers 17763.380 est disponible, mettez à jour cette build pour recevoir le correctif du bogue d’hang de l’application.

1. Lors de la mise à jour vers cette version du système d’exploitation, les applications doivent fonctionner comme prévu.

En outre, comme nous le faisons avec chaque version du système d’exploitation HoloLens, nous avons publié l’image FFU dans le [Centre de téléchargement Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Si vous ne souhaitez pas prendre la mise à jour, nous avons publié une nouvelle version de l’application UWP du Microsoft Store à partir du 29/03/2013. Une fois que vous avez mis à jour la version du Store :

1. Ouvrez le Store et confirmez son chargement.
1. Utilisez le geste d’ouverture du menu à l’appel.
1. Essayez d’ouvrir des applications précédemment rompues.
1. Si elle ne peut toujours pas être lancée, appuyez et maintenez l’icône de l’application rompue, puis sélectionnez Désinstaller.
1. Réinstallez ces applications à partir du Store.

Si votre appareil ne parvient toujours pas à charger des applications, vous pouvez charger une version de .NET Native Framework et d’Runtime via le centre de téléchargement en suivant les étapes suivantes :

1. Téléchargez [ce fichier zip à partir](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) du Centre de téléchargement Microsoft. Unzipping produit deux fichiers.  Microsoft.NET.Native.Runtime.1.7.appx et Microsoft.NET.Native.Framework.1.7.appx.

1. Vérifiez que votre appareil est déverrouillé.  Si vous ne l’avez pas encore fait, [consultez l’outil Utilisation](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) de Windows Device Portal pour obtenir des instructions.

1. Vous souhaitez ensuite vous rendre dans Windows Device Portal. Il est recommandé de le faire sur USB, en tapant dans http://127.0.0.1:10080 votre navigateur.

1. Une fois windows Device Portal en place, nous avons besoin que vous « chargez de côté » les deux fichiers que vous avez téléchargés. Pour ce faire, vous devez descendre dans la barre de gauche jusqu’à ce que vous arrivez à la section **Applications** et sélectionnez **Applications.**

1. Vous verrez ensuite un écran semblable à celui ci-dessous.  Vous souhaitez aller à la section qui indique **Installer** l’application et accédez à l’endroit où vous avez décompressé ces deux fichiers APPX. Vous ne pouvez en faire qu’une seule à la fois. Ainsi, après avoir sélectionné le premier, cliquez sur « Aller » dans la section Déployer. Ensuite, faites-le pour le deuxième fichier APPX.

   ![Windows Device Portal pour installer Side-Loaded application](images/20190322-DevicePortal.png)
   
1. À ce stade, nous pensons que vos applications doivent recommencer à fonctionner et que vous pouvez également vous rendre dans le Store.

1. Dans certains cas, il est nécessaire d’exécuter l’étape supplémentaire de lancement de l’application visionneuse 3D avant que les applications concernées ne se lancent. 

Nous vous remercions de votre patience au fil du processus de résolution de ce problème, et nous attendons avec intérêt de continuer à collaborer avec notre communauté pour créer des expériences de réalité mixte réussies.

### Mise à jour de périphérique

- 30 secondes après une nouvelle mise à jour, l’shell peut disparaître une fois. Effectuez le geste **d’ouverture** pour reprendre votre session.

### Visual Studio

- Voir [Installer les outils](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pour la version la plus récente de Visual Studio recommandée pour le développement HoloLens.

- Lors du déploiement d’une application de Visual Studio vers votre HoloLens, vous pouvez voir l’erreur : l’opération demandée ne peut pas être effectuée sur un fichier avec une section mappée par **l’utilisateur ouverte. (Exception de HRESULT : 0x800704C8).** Si cela se produit, essayez à nouveau et votre déploiement réussit généralement.

### API

- Si l’application définit le [point de focus](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) derrière l’utilisateur ou la normale sur camera.forward, les hologrammes n’apparaissent pas dans les photos ou vidéos de capture de réalité mixte. Tant que ce bogue n’est pas résolu dans Windows, si les applications définissent activement le point de [focus,](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) elles doivent s’assurer que le plan normal est mis en face de la caméra (par exemple, normal = -camera.forward).

### Manette sans fil Xbox

- La manette sans fil Xbox S doit être mise à jour avant de pouvoir être utilisée avec HoloLens. Assurez-vous que [vous êtes à jour](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) avant d’essayer de jumeler votre contrôleur avec un HoloLens.

- Si vous redémarrez votre HoloLens pendant que la manette sans fil Xbox est connectée, la manette ne se reconnecte pas automatiquement à HoloLens. La lumière du bouton Guide clignote lentement jusqu’à ce que le contrôleur s’allume après 3 minutes. Pour reconnecter immédiatement votre contrôleur, allumez-le en maintenant le bouton Guide enfoncé jusqu’à ce que la lumière soit éteinte. Lorsque vous reconnectez votre contrôleur, il se reconnecte à HoloLens.

- Si votre HoloLens entre en veille pendant que la manette sans fil Xbox est connectée, toute entrée sur la manette va s’enserr le HoloLens. Vous pouvez éviter cela en éteint votre contrôleur lorsque vous avez terminé de l’utiliser.

## Problèmes connus pour l’émulateur HoloLens

- Toutes les applications du Microsoft Store ne sont pas compatibles avec l’émulateur. Par exemple, Young Conker et Fragments ne sont pas lisibles sur l’émulateur.
- Vous ne pouvez pas utiliser la webcam du PC dans l’émulateur.
- La fonctionnalité Aperçu en direct de Windows Device Portal ne fonctionne pas avec l’émulateur. Vous pouvez toujours capturer des vidéos et des images de réalité mixte.
