---
title: Problèmes connus avec HoloLens
description: Voici la liste des problèmes connus qui peuvent affecter les développeurs HoloLens.
keywords: résoudre les problèmes, problèmes connus, aide
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: db95edfbadb271b7fc47cf5798e80d9b2cad3c90
ms.sourcegitcommit: 708da7b390fed1fd3aea1a2b2e50461851052683
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881327"
---
# Problèmes connus avec HoloLens

Voici la liste actuelle des problèmes connus des appareils HoloLens. Activez d’abord cette option si vous voyez un comportement étrange. Cette liste sera mise à jour à mesure que de nouveaux problèmes seront détectés ou signalés, ou en cas de problèmes dans les mises à jour de logiciels HoloLens ultérieures.

>[!NOTE]
> - Si vous rencontrez un problème qui ne se bloque pas, signalez-le sur votre appareil HoloLens via le [Hub de commentaires](hololens-feedback.md).
> - Si le problème que vous rencontrez vous empêche, dans addtion de classer votre avis, envoyez [une demande de support](https://aka.ms/hlsupport).

- [Problèmes connus pour toutes les générations HoloLens](#known-issues-for-all-hololens-generations)
- [Problèmes connus pour les appareils HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problèmes connus pour HoloLens (1er génération)](#known-issues-for-hololens-1st-gen)
- [Problèmes connus de HoloLens Emulator](#known-issues-for-hololens-emulator)

## Problèmes connus pour toutes les générations HoloLens

### Unity

- Pour plus d’injour, voir [installer les outils](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pour le développement HoloLens.
- Les problèmes connus liés à la version d’évaluation technique de Unity HoloLens sont décrits dans les [Forums Hololens Unity](https://forum.unity3d.com/threads/known-issues.394627/).

### WindowsDevicePortal

- La fonctionnalité d’aperçu instantané de la capture d’une réalité mixte risque de présenter plusieurs secondes de latence.
- Sur la page d’entrée virtuelle, les contrôles de mouvement et de défilement situés sous la section gestes virtuels ne fonctionnent pas. L’utilisation de ces dernières n’aura aucun effet. Le clavier virtuel sur la même page fonctionne correctement.
- Après avoir activé le mode développeur dans les paramètres, l’activation de Device Portal peut prendre quelques secondes.

### Chargement de l’appareil photo OneDrive

L’application OneDrive pour HoloLens ne prend pas en charge le chargement de caméra automatique pour les comptes professionnels ou scolaires.

Contournement
- Si vous êtes viable pour votre entreprise, le chargement automatique des caméras est pris en charge sur les comptes Microsoft Consumer. Vous pouvez vous connecter à votre compte Microsoft en plus de votre compte professionnel ou scolaire (l’application OneDrive prend en charge la connexion double). À partir du profil de votre compte Microsoft dans OneDrive, vous pouvez activer le chargement automatique de la pellicule en arrière-plan.
- Si vous ne pouvez pas utiliser en toute sécurité un compte Microsoft pour le chargement automatique de vos photos, vous pouvez télécharger manuellement des photos sur votre compte professionnel ou scolaire à partir de l’application OneDrive. Pour cela, assurez-vous que vous êtes connecté à votre compte professionnel ou scolaire dans l’application OneDrive. Sélectionnez le **+** bouton, puis **Télécharger**. Recherchez les photos ou vidéos que vous voulez charger en accédant à **images > pellicule**. Sélectionnez les photos ou vidéos que vous voulez télécharger, puis cliquez sur le bouton **ouvrir** .

## Problèmes connus pour les appareils HoloLens 2

### Un écran bleu s’affiche après l’annulation de l’inscription de builds Insider Preview à partir d’un appareil à l’aide d’une build Insider

Il s’agit d’un problème affectant les utilisateurs qui se sont connectés à une version d’évaluation Insider Preview (HoloLens 2) avec une nouvelle build Insider Preview, puis désinscrit du programme Insider. 

Cela n’affecte pas les éléments suivants:
- Utilisateurs non inscrits à Windows Insider 
- Insider
    - Si un appareil a été inscrit depuis la version Insider Build 18362. x
    - S’il a fait clignoter une build 19041. x Insider et rester inscrit au programme Insider 

Solutions de contournement: 
- Éviter le problème 
    - Faire clignoter une version non-Insider. Une des mises à jour mensuelles standard. 
    - Restez sur la version Insider preview
- Refaire clignoter l’appareil
    1. Mettre le [HoloLens 2 en mode clignotant](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manuellement en le sélectionnant sans être connecté. Puis tout en maintenant le volume enfoncé, appuyez sur le bouton d’alimentation.
    1. Connectez-vous au PC et ouvrez l’Assistant de récupération avancée. 
    1. Éclairez le HoloLens 2 dans la build par défaut.   

## Problèmes connus pour HoloLens (1er génération)

### Impossible de se connecter et de déployer vers HoloLens via Visual Studio

> [!NOTE]
> Dernière mise à jour: 8/8 @ 5:11PM-Visual Studio a publiée VS 2019 version 16,2 qui inclut un correctif à ce problème. Nous vous recommandons d’effectuer la mise à jour vers la version la plus récente afin de ne pas rencontrer cette erreur.

Visual Studio a lancé la version 16,2 de 2019, qui inclut un correctif pour résoudre ce problème. Nous vous recommandons d’effectuer la mise à jour vers la version la plus récente afin de ne pas rencontrer cette erreur.

Problème: cause profonde: les utilisateurs ayant utilisé Visual Studio 2015 ou des versions antérieures de Visual Studio 2017 pour déployer et déboguer des applications sur leur HoloLens, puis utiliser les dernières versions de Visual Studio 2017 ou Visual Studio 2019 avec le même HoloLens seront affectés. Les versions plus récentes de Visual Studio déploient une nouvelle version d’un composant, mais les fichiers de l’ancienne version sont conservés sur l’appareil, provoquant l’échec de la nouvelle version.  Le message d’erreur suivant s’affiche alors: DEP0100: Vérifiez que le mode développeur est activé sur l’appareil cible. Impossible d’obtenir une licence de développeur en \<ip\> raison de l’erreur 80004005.

#### Solution de contournement

Notre équipe travaille actuellement sur un correctif. Entre-temps, vous pouvez utiliser les étapes suivantes pour contourner le problème et vous aider à débloquer le déploiement et le débogage:  

1. Ouvrir Visual Studio
1. Sélectionnez **fichier**  >  **nouveau**  >  **projet**.
1. Sélectionnez **Visual C#**  >  **Windows Desktop**  >  **application de console de bureau Windows Visual C# (.NET Framework)**.
1. Donnez un nom au projet (par exemple, «HoloLensDeploymentFix») et assurez-vous que l’infrastructure est définie sur au moins .NET Framework 4,5, puis sélectionnez **OK**.
1. Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le nœud **références** et ajoutez les références suivantes (sélectionnez la section **Parcourir** , puis sélectionnez **Parcourir**):

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Si vous n’avez pas installé 10.0.18362.0, utilisez la version la plus récente que vous utilisez. 

1. Cliquez avec le bouton droit sur le projet dans l’Explorateur de solutions, puis sélectionnez **Ajouter**un  >  **élément existant**.
1. Accédez à C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 et modifiez le filtre sur **tous les fichiers (\ *. \ *)**.
1. Sélectionnez les SirepClient.dll et SshClient.dll, puis sélectionnez **Ajouter**.
1. Recherchez et sélectionnez les deux fichiers dans l’Explorateur de solutions (ils doivent figurer en bas de la liste des fichiers) et remplacez l’option **copier dans le répertoire de sortie** de la fenêtre **Propriétés** pour pouvoir les **copier toujours**.
1. En haut du fichier, ajoutez ce qui suit à la liste d’instructions existante `using` :

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. À l’intérieur de `static void Main(...)` , ajoutez le code suivant:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Sélectionnez **génération**de la  >  **solution**.
1. Ouvrez une fenêtre d’invite de commandes et un CD-ROM dans le dossier qui contient le fichier. exe compilé (par exemple, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).
1. Exécutez le fichier exécutable et indiquez l’adresse IP de l’appareil en tant qu’argument de la ligne de commande. (Si vous êtes connecté à l’aide de la technologie USB, vous pouvez utiliser 127.0.0.1; sinon, utilisez l’adresse IP Wi-Fi de l’appareil.)  Par exemple, «HoloLensDeploymentFix 127.0.0.1»

1. Une fois que l’outil a quitté sans message (cette opération ne doit durer que quelques secondes), vous pouvez maintenant être en mesure de déployer et de déboguer depuis Visual Studio 2017 ou une version ultérieure.  Il n’est pas nécessaire de continuer à utiliser l’outil.

Nous vous fournirons des mises à jour supplémentaires dès qu’ils seront disponibles.

### Problèmes lors du lancement de Microsoft Store et des applications sur HoloLens

> [!NOTE]
> Dernière mise à jour: 4/2 @ 10 AM-problème résolu. 

Vous pouvez être rencontré lors de la tentative de lancement du Microsoft Store et des applications sur HoloLens. Nous avons déterminé que le problème survient lorsque des mises à jour de l’application en arrière-plan déploient une nouvelle version des packages d’infrastructure dans des séquences spécifiques alors qu’une ou plusieurs de leurs applications dépendantes sont toujours en cours d’exécution. Dans ce cas, une mise à jour automatique d’application a fourni une nouvelle version de l’infrastructure native .NET (version 10.0.25531 à 10.0.27413), car les applications qui ne sont pas correctement mises à jour pour toutes les applications en cours d’exécution utilisent la version antérieure de l’infrastructure.  Le flux de la mise à jour de l’infrastructure se présente comme suit: 

1. Le nouveau package d’infrastructure est téléchargé à partir du Windows Store et installé
1. Toutes les applications utilisant l’infrastructure plus ancienne sont «mises à jour» pour utiliser la version la plus récente

Si vous êtes interrompu avant la fin de l’étape 2, toutes les applications pour lesquelles l’infrastructure plus récente n’est pas enregistrée ne seront pas lancées à partir du menu Démarrer.  Nous pensons que toute application sur HoloLens peut être affectée par ce problème.

Certains utilisateurs ont signalé que le fait de fermer des applications en suspens et de lancer d’autres applications telles que le hub de commentaires, la visionneuse 3D ou des photos résout le problème pour eux &mdash; , mais cela ne fonctionne pas 100% du temps.

Le problème est dû au fait que le problème n’est pas à l’origine de la mise à jour, mais qu’un bogue dans le système d’exploitation entraînait une gestion incorrecte des mises à jour de l’infrastructure .NET native. Nous sommes heureux de vous annoncer que nous avons identifié un correctif et que vous avez mis à jour la version 17763,380 du système d’exploitation contenant le correctif.  

Pour savoir si votre appareil peut procéder à la mise à jour, procédez comme suit:

1. Accédez à l’application paramètres et ouvrez **mise à jour & sécurité**.
1. Sélectionnez **Rechercher les mises à jour**.
1. Si la mise à jour vers 17763,380 est disponible, veuillez effectuer la mise à jour vers cette version pour recevoir le correctif pour le bogue de blocage de l’application.
1. Lors de la mise à jour de cette version du système d’exploitation, les applications doivent fonctionner comme prévu.

De plus, comme nous le faisons pour chaque version de système d’exploitation HoloLens, nous avons publié l’image FFU dans le [Centre de téléchargement Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).

Si vous ne souhaitez pas procéder à la mise à jour, nous avons mis à jour une nouvelle version de l’application UWP Microsoft Store depuis 3/29. Une fois que vous avez installé la version mise à jour du Windows Store:

1. Ouvrez le Windows Store et confirmez son chargement.
1. Utilisez le geste pour ouvrir le menu.
1. Tentez d’ouvrir des applications incorrectes auparavant.
1. S’il ne parvient toujours pas à démarrer, appuyez de façon prolongée sur l’icône de l’application endommagée et sélectionnez Désinstaller.
1. Resinstall ces applications à partir du Windows Store.

Si votre appareil ne parvient toujours pas à charger des applications, vous pouvez charger une version de l’infrastructure et du Runtime .NET natifs par le biais du centre de téléchargement en procédant comme suit:

1. Téléchargez [ce fichier zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) à partir du centre de téléchargement Microsoft. Dézipper génère deux fichiers.  Microsoft. NET. native. Runtime. 1.7. AppX et Microsoft. NET. native. Framework. 1.7. AppX
1. Veuillez vérifier que votre appareil est déverrouillé.  Si vous ne l’avez pas encore fait [, nous ne](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)vous conseillons pas d’effectuer cette procédure.
1. Vous pouvez ensuite accéder à Windows Device Portal. Nous vous conseillons de le faire par le biais de la norme USB et vous le feriez en http://127.0.0.1:10080 le tapant dans votre navigateur.
1. Dès lors que vous disposez de Windows Device Portal, nous avons besoin que vous deviez télécharger les deux fichiers que vous avez téléchargés. Pour cela, vous devez descendre dans la barre latérale gauche jusqu’à atteindre la section **applications** et sélectionner **applications**.
1. Un écran semblable au suivant s’affiche.  Vous voulez accéder à la section «installer l' **application** » et accéder à l’emplacement où vous avez compressé ces deux fichiers Appx. Vous pouvez effectuer l’une à la fois, une fois que vous avez sélectionné la première, puis cliqué sur «Go» sous la section déploiement. Procédez ainsi pour le deuxième fichier APPX.

   ![Windows Device Portal pour installer l’application installée hors Windows Store](images/20190322-DevicePortal.png)
1. Pour le moment, nous pensons que vos applications doivent de nouveau fonctionner et que vous pouvez également accéder au Windows Store.
1. Dans certains cas, il est nécessaire d’exécuter l’étape supplémentaire de lancement de l’application de visionneuse 3D avant le lancement des applications concernées. 

Nous vous remercions de votre patience, car nous avons procédé à la résolution de ce problème, et nous serons heureux de continuer à travailler avec notre communauté pour créer des expériences de réalité mélangées réussies.

### Mise à jour de l’appareil

- 30 secondes après une nouvelle mise à jour, le shell risque de disparaître une fois. Pour reprendre votre session, vous devez effectuer le mouvement de la **floraison** .

### Visual Studio

- Pour obtenir la version la plus à jour de Visual Studio recommandée pour le développement HoloLens, voir [installer les outils](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) .
- Lors du déploiement d’une application à partir de Visual Studio vers votre HoloLens, le message d’erreur suivant peut s’afficher: **l’opération demandée ne peut pas être effectuée sur un fichier dont la section mappée par l’utilisateur est ouverte. (Exception de HRESULT: 0x800704C8)**. Si tel est le cas, essayez de nouveau et votre déploiement fonctionnera généralement.

### API

- Dans le cas contraire, l’application positionne le [point de focalisation](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) sur l’utilisateur ou la caméra normale au mode caméra. transférer, les hologrammes n’apparaissent pas dans la réalité mixte capture de photos ou de vidéos. Tant que ce bogue n’a pas été résolu dans Windows, si les applications définissent activement le point de mise au [point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , il devrait s’assurer que la normale du plan est définie comme suit.

### Contrôleur sans fil Xbox

- Le contrôleur sans fil Xbox doit être mis à jour pour pouvoir être utilisé avec HoloLens. Vérifiez que vous êtes à [jour](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) avant d’essayer de jumeler votre manette avec un HoloLens.
- Si vous redémarrez votre HoloLens alors que le contrôleur sans fil Xbox est connecté, le contrôleur ne se reconnecte pas automatiquement à HoloLens. Le bouton du repère clignote lorsque le contrôleur s’éteint après 3 minutes. Pour reconnecter votre contrôleur immédiatement, allumez le contrôleur en maintenant le bouton de repère enfoncé. Lorsque vous rallumez votre contrôleur, il se reconnecte à HoloLens.
- Si votre HoloLens passe en mode veille alors que le contrôleur sans fil Xbox est connecté, toute entrée sur le contrôleur va sortir du casque HoloLens. Vous pouvez éviter cela en allumant votre manette lorsque vous avez travaillé.

## Problèmes connus de HoloLens Emulator

- Toutes les applications du Microsoft Store ne sont pas compatibles avec l’émulateur. Par exemple, les jeunes Conker et fragments ne peuvent pas être lus dans l’émulateur.
- Vous ne pouvez pas utiliser la webcam du PC dans l’émulateur.
- La fonctionnalité d’aperçu instantané de Windows Device Portal ne fonctionne pas avec l’émulateur. Vous pouvez continuer à capturer des vidéos et des images à la réalité mélangées.
