---
title: problèmes connus pour HoloLens (1ère génération)
description: restez à jour grâce à notre liste de problèmes connus et de solutions de contournement susceptibles d’affecter HoloLens clients et les développeurs utilisant unity et le portail des appareils Windows.
keywords: résolution des problèmes, problème connu, aide
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: d2a8ae420a0c1d646625fe81b166e2daae07e44652b70f2e4a1b19ccba240cfb
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663944"
---
# <a name="known-issues-for-hololens-1st-gen"></a>problèmes connus pour HoloLens (1ère génération)

voici la liste actuelle des problèmes connus pour HoloLens appareils. Vérifiez ici d’abord si vous constatez un comportement étrange. cette liste est mise à jour à mesure que de nouveaux problèmes sont détectés ou signalés, ou lorsque des problèmes sont résolus dans de futures mises à jour logicielles HoloLens.

>[!NOTE]
> - si vous découvrez un problème qui ne bloque pas, signalez-le sur votre appareil HoloLens par le biais de [commentaires Hub](hololens-feedback.md).
> - Si le problème auquel vous êtes confronté vous empêche, en plus de déposer des commentaires, veuillez envoyer [une demande de support](https://aka.ms/hlsupport).


- [problèmes connus pour toutes les générations de HoloLens](#known-issues-for-all-hololens-generations)
- [problèmes connus pour HoloLens (1ère génération)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>problèmes connus pour toutes les générations de HoloLens

### <a name="unity"></a>Unity

- consultez [installer les outils](/windows/mixed-reality/install-the-tools) pour la version la plus récente d’unity recommandée pour le développement de HoloLens.
- les problèmes connus avec unity HoloLens Technical Preview sont documentés dans les [forums HoloLens unity](https://forum.unity3d.com/threads/known-issues.394627/).

### <a name="windows-device-portal"></a>Portail d’appareil Windows

- La fonctionnalité d’aperçu instantané de la capture de la réalité mixte peut présenter plusieurs secondes de latence.

- Sur la page d’entrée virtuelle, les contrôles de mouvement et de défilement sous la section des mouvements virtuels ne sont pas fonctionnels. Leur utilisation n’aura aucun effet. Le clavier virtuel sur la page d’entrée virtuelle fonctionne correctement.

- après avoir activé le Mode développeur dans Paramètres, la mise sous tension du portail de l’appareil peut prendre quelques secondes.

### <a name="onedrive-camera-upload"></a>OneDrive le chargement de la caméra

l’application OneDrive pour HoloLens ne prend pas en charge le chargement automatique de l’appareil photo pour les comptes professionnels ou scolaires.

Solutions de contournement :

- Si vous êtes viable pour votre entreprise, le chargement automatique de l’appareil photo est pris en charge sur les comptes Microsoft. vous pouvez vous connecter à votre compte Microsoft en plus de votre compte professionnel ou scolaire (l’application OneDrive prend en charge la connexion double). à partir de votre profil de compte Microsoft dans OneDrive vous pouvez activer le chargement automatique de l’appareil photo en arrière-plan.

- si vous ne pouvez pas utiliser un compte Microsoft consommateur en toute sécurité pour télécharger vos photos automatiquement, vous pouvez charger manuellement des photos sur votre compte professionnel ou scolaire à partir de l’application OneDrive. pour ce faire, assurez-vous que vous êtes connecté à votre compte professionnel ou scolaire dans l’application OneDrive. sélectionnez le **+** bouton, puis choisissez **Télécharger**. Recherchez les photos ou vidéos que vous souhaitez télécharger en accédant à **images > pellicule**. Sélectionnez les photos ou vidéos que vous souhaitez télécharger, puis cliquez sur le bouton **ouvrir** .

## <a name="known-issues-for-hololens-1st-gen"></a>problèmes connus pour HoloLens (1ère génération)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>impossible de se connecter et de déployer pour HoloLens via Visual Studio

> [!NOTE]
> dernière mise à jour : 8/8 @ 5:23 h 00-Visual Studio a publié VS 2019 Version 16,2, qui inclut un correctif pour ce problème. Nous vous recommandons d’effectuer la mise à jour vers cette version la plus récente pour éviter d’avoir à rencontrer cette erreur.

Visual Studio a publié VS 2019 Version 16,2, qui inclut un correctif pour ce problème. Nous vous recommandons d’effectuer la mise à jour vers cette version la plus récente pour éviter d’avoir à rencontrer cette erreur.

origine du problème : les utilisateurs qui ont utilisé Visual Studio 2015 ou les versions antérieures de Visual Studio 2017 pour déployer et déboguer des applications sur leur HoloLens, puis utilisaient ensuite les dernières versions de Visual Studio 2017 ou Visual Studio 2019 avec le même HoloLens seront affectés. les nouvelles versions de Visual Studio déployer une nouvelle version d’un composant, mais les fichiers de la version antérieure sont conservés sur l’appareil, ce qui entraîne l’échec de la version plus récente.  Le message d’erreur suivant s’affiche : DEP0100 : Assurez-vous que le mode développeur est activé pour l’appareil cible. Impossible d’obtenir une licence de développeur sur \<ip\> en raison de l’erreur 80004005.

#### <a name="workaround"></a>Solution de contournement

Notre équipe travaille actuellement sur un correctif. En attendant, vous pouvez utiliser les étapes suivantes pour contourner le problème et vous aider à débloquer le déploiement et le débogage :  

1. Ouvrez Visual Studio.

1. Sélectionnez **Fichier** > **Nouveau** > **Projet**.

1. sélectionnez **Visual C#**  >  **Windows**  >  **application Console du bureau (.NET Framework)**.

1. donnez un nom au projet (par exemple, « HoloLensDeploymentFix ») et assurez-vous que l’infrastructure est définie sur au moins .NET Framework 4,5, puis sélectionnez **OK**.

1. Cliquez avec le bouton droit sur le nœud **références** dans Explorateur de solutions et ajoutez les références suivantes (sélectionnez la section **Parcourir** et sélectionnez **Parcourir**) :

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Si 10.0.18362.0 n’est pas installé, utilisez la version la plus récente que vous avez.

1. Dans Explorateur de solutions, cliquez avec le bouton droit sur le projet, puis sélectionnez **Ajouter** un  >  **élément existant**.

1. accédez à C:\Program files (x86) \ Windows Kits\10\bin\10.0.18362.0\x86 et remplacez le filtre par **tous les fichiers ( \* . \* )**.

1. Sélectionnez à la fois SirepClient.dll et SshClient.dll, puis sélectionnez **Ajouter**.

1. Recherchez et sélectionnez les deux fichiers dans Explorateur de solutions (ils doivent être au bas de la liste des fichiers) et remplacez la valeur **toujours** copier dans le **Répertoire de sortie** de la fenêtre **Propriétés** .

1. En haut du fichier, ajoutez ce qui suit à la liste d’instructions existante `using` :

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Dans `static void Main(...)` , ajoutez le code suivant :

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Sélectionnez **Générer** > **Générer la solution**.

1. Ouvrez une fenêtre d’invite de commandes et un CD-ROM vers le dossier qui contient le fichier .exe compilé (par exemple, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Exécutez l’exécutable et fournissez l’adresse IP de l’appareil en tant qu’argument de ligne de commande. (Si vous êtes connecté à l’aide de la norme USB, vous pouvez utiliser 127.0.0.1, sinon, utiliser l’adresse IP de Wi-Fi de l’appareil.)  Par exemple, « HoloLensDeploymentFix 127.0.0.1 ».

1. une fois que l’outil s’est arrêté sans aucun message (cette opération ne doit prendre que quelques secondes), vous pouvez maintenant déployer et déboguer à partir de Visual Studio 2017 ou plus.  L’utilisation continue de l’outil n’est pas nécessaire.

Nous fournirons d’autres mises à jour dès qu’elles seront disponibles.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>problèmes lors du lancement du Microsoft Store et des applications sur HoloLens

> [!NOTE]
> Dernière mise à jour : 4/2 @ 10-problème résolu.

vous pouvez rencontrer des problèmes lors de la tentative de lancement du Microsoft Store et des applications sur HoloLens. Nous avons déterminé que le problème se produit lorsque les mises à jour d’applications en arrière-plan déploient une version plus récente des packages d’infrastructure dans des séquences spécifiques alors qu’une ou plusieurs de leurs applications dépendantes sont toujours en cours d’exécution. dans ce cas, une mise à jour d’application automatique a fourni une nouvelle version de l’infrastructure .NET Native (version 10.0.25531 vers 10.0.27413), a provoqué les applications qui exécutent pour qu’elles ne soient pas correctement mises à jour pour toutes les applications en cours d’exécution qui utilisent la version antérieure du Framework.  Le Flow pour la mise à jour du Framework est le suivant :

1. Le nouveau package d’infrastructure est téléchargé à partir du Store et installé.

1. Toutes les applications utilisant l’ancien Framework sont mises à jour pour utiliser la version la plus récente.

Si l’étape 2 est interrompue avant la fin, toutes les applications pour lesquelles l’infrastructure récente n’a pas été inscrite ne pourront pas être lancées à partir du menu Démarrer.  nous pensons que toute application sur HoloLens pourrait être affectée par ce problème.

certains utilisateurs ont signalé que la fermeture des applications bloquées et le lancement d’autres applications telles que le Hub de commentaires, la visionneuse 3d ou le Photos résout le problème pour eux, mais cela ne fonctionne pas 100% du temps.

la racine a provoqué que ce problème n’a pas provoqué la mise à jour elle-même, mais un bogue dans le système d’exploitation qui a entraîné la gestion incorrecte de la mise à jour .NET Native framework. Nous sommes heureux de vous annoncer que nous avons identifié un correctif et que vous avez publié une mise à jour (version 17763,380) contenant le correctif.  

Pour voir si votre appareil peut effectuer la mise à jour :

1. accédez à l’application Paramètres et ouvrez **Update & Security**.

1. Sélectionnez **Rechercher les mises à jour**.

1. Si la mise à jour vers 17763,380 est disponible, effectuez une mise à jour vers cette build pour recevoir le correctif pour le bogue de blocage de l’application.

1. Lors de la mise à jour vers cette version du système d’exploitation, les applications doivent fonctionner comme prévu.

en outre, comme nous le faisons pour chaque version du système d’exploitation HoloLens, nous avons publié l’image FFU dans le [centre de téléchargement Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).

si vous ne souhaitez pas effectuer la mise à jour, nous avons publié une nouvelle version de l’application Microsoft Store UWP à partir du 3/29. Une fois que vous disposez de la version mise à jour du magasin :

1. Ouvrez le magasin et confirmez qu’il est chargé.
1. Utilisez le geste fleuri pour ouvrir le menu.
1. Essayez d’ouvrir des applications qui ont été interrompues.
1. S’il ne peut toujours pas être lancé, appuyez et maintenez l’icône de l’application endommagée, puis sélectionnez Désinstaller.
1. Réinstallez ces applications à partir du Windows Store.

si votre appareil n’est toujours pas en mesure de charger des applications, vous pouvez chargement une version de l’infrastructure de .NET Native et du Runtime par le biais du centre de téléchargement en procédant comme suit :

1. Téléchargez [ce fichier zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) à partir du centre de téléchargement Microsoft. La décompression produira deux fichiers.  Microsoft. NET. native. Runtime. 1.7. AppX et Microsoft. NET. native. Framework. 1.7. Appx.

1. Vérifiez que votre appareil est déverrouillé.  si vous ne l’avez pas déjà fait, consultez [utilisation du portail des appareils Windows](/windows/mixed-reality/using-the-windows-device-portal) pour obtenir des instructions.

1. vous souhaitez ensuite accéder au portail des appareils Windows. Nous vous recommandons de le faire par le biais d’une interface USB. pour ce faire, vous devez taper http://127.0.0.1:10080 dans votre navigateur.

1. une fois que vous avez Windows le portail des appareils, nous avons besoin de « charger en charge » les deux fichiers que vous avez téléchargés. Pour ce faire, vous devez descendre dans la barre latérale de gauche jusqu’à ce que vous obteniez la section **applications** et que vous sélectionnez **applications**.

1. Un écran similaire à celui ci-dessous s’affiche.  Vous souhaitez accéder à la section qui indique **installer l’application** et accéder à l’emplacement où vous avez décompressé ces deux fichiers Appx. Vous ne pouvez effectuer qu’un seul à la fois. par conséquent, après avoir sélectionné le premier, cliquez sur « Go » sous la section déployer. Effectuez ensuite cette opération pour le deuxième fichier APPX.

   ![Windows Portail de l’appareil pour installer Side-Loaded application](images/20190322-DevicePortal.png)

1. À ce stade, nous pensons que vos applications doivent commencer à fonctionner à nouveau et que vous pouvez également accéder au Store.

1. Dans certains cas, il est nécessaire d’exécuter l’étape supplémentaire de lancement de l’application de visionneuse 3D avant le lancement des applications affectées.

Nous vous remercions de votre patience, car nous avons passé en revue le processus de résolution de ce problème. nous sommes impatients de continuer à travailler avec notre communauté pour créer des expériences de réalité mixte fructueuses.

### <a name="device-update"></a>Mise à jour de l’appareil

- 30 secondes après une nouvelle mise à jour, l’interpréteur de commandes peut disparaître une fois. Effectuez le geste de **floraison** pour reprendre votre session.

### <a name="visual-studio"></a>Visual Studio

- consultez [installer les outils](/windows/mixed-reality/install-the-tools) pour la version la plus à jour de Visual Studio recommandée pour le développement HoloLens.

- lors du déploiement d’une application à partir de Visual Studio vers votre HoloLens, l’erreur suivante peut s’afficher : **l’opération demandée ne peut pas être effectuée sur un fichier avec une section mappée par l’utilisateur ouverte. (Exception de HRESULT : 0x800704C8)**. Si cela se produit, réessayez et votre déploiement fonctionnera généralement.

### <a name="api"></a>API

- Si l’application définit le [point de focus](/windows/mixed-reality/focus-point-in-unity) sous-jacent à l’utilisateur ou normal à Camera. Forward, les hologrammes n’apparaîtront pas dans la réalité mixte capturer des photos ou des vidéos. tant que ce bogue n’a pas été résolu dans Windows, si les applications définissent activement le [point de focalisation](/windows/mixed-reality/focus-point-in-unity) , elles doivent s’assurer que la normale du plan est définie en regard de caméra-forward (par exemple, normal =-camera. forward).

### <a name="xbox-wireless-controller"></a>Manette Xbox Wireless Controller

- Les contrôleurs Xbox Wireless S doivent être mis à jour avant de pouvoir être utilisés avec HoloLens. Vérifiez que vous êtes à [jour](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) avant d’essayer de coupler votre contrôleur à un HoloLens.

- si vous redémarrez votre HoloLens alors que le contrôleur sans fil Xbox est connecté, le contrôleur ne se reconnectera pas automatiquement à HoloLens. La lumière du bouton du repère clignote lentement jusqu’à ce que le contrôleur s’éteigne après 3 minutes. Pour reconnecter immédiatement votre contrôleur, mettez le contrôleur hors tension en maintenant le bouton du repère enfoncé jusqu’à ce que la lumière s’arrête. Lorsque vous remettez votre contrôleur sous tension, il se reconnecte à HoloLens.

- si votre HoloLens entre en veille alors que le contrôleur sans fil Xbox est connecté, toute entrée sur le contrôleur sort du HoloLens. Vous pouvez éviter cela en éteignant votre contrôleur lorsque vous avez fini de l’utiliser.

