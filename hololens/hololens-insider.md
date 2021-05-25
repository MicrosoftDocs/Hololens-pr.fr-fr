---
title: Version préliminaire d’Insider pour Microsoft HoloLens
description: Découvrez comment prendre en main les builds Insider et fournir des commentaires précieux pour la prochaine mise à jour majeure du système d’exploitation pour HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397820"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Version préliminaire d’Insider pour Microsoft HoloLens

Bienvenue dans les dernières versions préliminaires d’Insider pour HoloLens ! Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) précieux pour la prochaine mise à jour majeure du système d’exploitation pour HoloLens.

## <a name="windows-insider-release-notes"></a>Notes de publication de Windows Insider

Nous sommes ravis de commencer à effectuer le vol de nouvelles fonctionnalités vers Windows Insider. Les nouvelles builds feront l’d’un vol vers les canaux dev et bêta pour les dernières mises à jour. Nous continuerons à mettre à jour cette page à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider. Soyez enthousiaste et prêt à mélanger ces mises à jour dans votre réalité. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>Chargement par progression de l’appareil photo de OneDrive entreprise ou scolaire

*Introduit dans la build 20346,1402*

Nous avons ajouté une nouvelle fonctionnalité à l’application paramètres HoloLens 2, qui permet aux clients de charger automatiquement des photos et des vidéos de réalité mixte à partir des images de l’appareil > dossier pellicule vers le dossier OneDrive for Work ou School correspondant. Cette fonctionnalité s’adresse à un [écart de fonctionnalités au sein de l’application OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) sur HoloLens 2, qui prend uniquement en charge le chargement automatique du rouleau de la caméra sur le compte Microsoft personnel d’un client (et non sur son compte professionnel ou scolaire).

**Fonctionnement**

- Visitez **paramètres > système > appareil photo de la réalité mixte** pour activer le « chargement de l’appareil photo ».
- En définissant cette fonctionnalité sur la position **on** , toutes les photos ou vidéos de réalité mixte capturées sur votre appareil seront automatiquement mises en file d’attente pour téléchargement dans le dossier images > pellicule de votre compte OneDrive entreprise ou établissement scolaire.
    >[!NOTE]
    >Les photos et vidéos capturées avant l’activation de cette fonctionnalité *ne seront pas* mises en file d’attente pour le téléchargement et devront tout de même être chargées manuellement.
- Un message d’État sur la page paramètres affiche le nombre de fichiers en attente de chargement (ou la lecture de « OneDrive est à jour » lorsque tous les fichiers en attente ont été téléchargés).
- Si vous vous inquiétez de la bande passante ou souhaitez « suspendre » le téléchargement pour une raison quelconque, vous pouvez faire passer la fonctionnalité à la position **off** . La désactivation temporaire de la fonctionnalité garantit que la file d’attente de téléchargement continuera à augmenter lorsque vous ajouterez de nouveaux fichiers au dossier pellicule, mais que les fichiers ne seront pas téléchargés tant que vous n’aurez pas réactivé la fonctionnalité.
- Les fichiers les plus récents seront téléchargés en premier (dernière connexion, premier sorti).
- Si votre compte OneDrive rencontre des problèmes (par exemple, après la modification de votre mot de passe), un bouton **corriger maintenant** s’affiche sur la page Paramètres.
- Il n’y a pas de taille de fichier maximale, mais notez que le chargement des fichiers volumineux prendra plus de temps (surtout si votre bande passante de chargement est limitée). Si vous « suspendez » ou si vous désactivez le téléchargement pendant le chargement d’un fichier volumineux, le téléchargement est immédiatement annulé. Le téléchargement redémarre lorsque vous réactivez la fonctionnalité. vous ne perdrez aucun fichier, mais le téléchargement partiel sera ignoré.

**Problèmes connus et avertissements**

- Ce paramètre n’a pas de limitation intégrée basée sur l’utilisation de la bande passante actuelle. Si vous avez besoin d’optimiser la bande passante pour un autre scénario, désactivez manuellement le paramètre. Le chargement sera suspendu, mais la fonctionnalité continuera à surveiller les fichiers récemment ajoutés à la pellicule. Réactivez le téléchargement lorsque vous êtes prêt à continuer.
- Cette fonctionnalité doit être activée pour chaque compte d’utilisateur sur l’appareil, et elle peut uniquement charger activement des fichiers pour l’utilisateur actuellement connecté à l’appareil.
- Si vous prenez des photos ou des vidéos tout en regardant le nombre de téléchargements dans la page paramètres en temps réel, Notez que le nombre de fichiers en attente peut ne pas changer tant que le téléchargement du fichier actuel n’est pas terminé.
- Le chargement s’interrompt si votre appareil est en veille ou hors tension. Pour vous assurer que vos chargements en attente sont terminés, utilisez activement l’appareil jusqu’à ce que la page des paramètres indique « OneDrive est à jour » ou ajustez les paramètres de veille de votre **& d’alimentation** .

## <a name="start-receiving-insider-builds"></a>Commencer à recevoir des builds Insider
> [!NOTE]
> Si vous n’avez pas récemment mis à jour votre appareil, redémarrez-le pour mettre à jour l’État et vous procurer la build la plus récente.
> - La commande vocale « reboot Device » fonctionne bien. 
> - Vous pouvez également choisir le bouton redémarrer dans paramètres/programme Windows Insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez pu rencontrer, ce qui vous permettra de revenir en arrière.

Sur un appareil HoloLens 2, accédez à **paramètres**  >  **mise à jour & sécurité**  >  **Windows Insider** , puis sélectionnez **prise en main**. Liez le compte que vous avez utilisé pour vous inscrire en tant que Windows Insider.
Windows Insider se déplace désormais vers les canaux. La sonnerie **rapide** deviendra le **canal de développement**, l’anneau **lent** deviendra le **canal bêta** et l’anneau de **version** préliminaire deviendra le **canal de version** préliminaire. Voici à quoi ressemble ce mappage : ![ explication des canaux Windows Insider ](images/WindowsInsiderChannels.png) pour plus d’informations, consultez [Présentation des canaux Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur les blogs Windows.
Ensuite, sélectionnez **développement actif de Windows**, indiquez si vous souhaitez recevoir des builds du canal de **développement** ou du **canal bêta** , et passez en revue les termes du programme.
Sélectionnez **confirmer > redémarrer maintenant** pour terminer. Une fois que votre appareil a redémarré, accédez à **paramètres > mettre à jour & sécurité > Rechercher les mises à jour** pour obtenir la build la plus récente.
### <a name="update-error-0x80070490-work-around"></a>Mettre à jour l’erreur de contournement 0x80070490
Si vous rencontrez une erreur de mise à jour 0x80070490 lors de la mise à jour sur le canal dev ou bêta, essayez le contournement à terme suivant. Il implique le déplacement de votre canal Insider, la sélection de la mise à jour, puis le déplacement de votre canal Insider.
#### <a name="stage-one---release-preview"></a>Version préliminaire de l’étape 1
1.  Paramètres, mettre à jour & Security, programme Windows Insider, sélectionner la **version préliminaire du canal**.
2.  Paramètres, mettre à jour & sécurité, Windows Update, **Rechercher les mises à jour**. Après la mise à jour, passez à l’étape 2.
#### <a name="stage-two---dev-channel"></a>Deuxième étape-canal de développement
1. Paramètres, mettre à jour & Security, programme Windows Insider, sélectionner un **canal de développement**.
2. Paramètres, mettre à jour & sécurité, Windows Update, **Rechercher les mises à jour**.
## <a name="ffu-download-and-flash-directions"></a>FFU téléchargement et itinéraires Flash
Pour effectuer un test avec un FFU signé par un vol, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU de vol signé.
1. Sur PC :
    1. Téléchargez FFU sur votre ordinateur à partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installez ARC (complément de récupération avancé) à partir du Microsoft Store : [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Sur HoloLens-Flight Unlock : ouvrir les **paramètres**  >  **mettre à jour &**  >  **programme Windows Insider** , puis s’inscrire et redémarrer l’appareil.
1. Flash FFU : vous pouvez désormais faire clignoter le FFU de vol signé à l’aide d’ARC.
### <a name="provide-feedback-and-report-issues"></a>Fournir des commentaires et signaler des problèmes
Utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour fournir des commentaires et signaler des problèmes. L’utilisation de feedback Hub garantit que toutes les informations de diagnostic nécessaires sont incluses pour aider nos ingénieurs à déboguer et résoudre rapidement le problème.  Les problèmes liés à la version chinoise et japonaise de HoloLens doivent être signalés de la même façon.
> [!NOTE]
> Veillez à accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).
## <a name="note-for-developers"></a>Remarque pour les développeurs
Nous vous invitons à essayer de développer vos applications à l’aide des versions Insider de HoloLens.  Consultez la [documentation du développeur HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds d’initié de HoloLens.  Vous pouvez utiliser les mêmes builds Unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.
## <a name="stop-receiving-insider-builds"></a>Arrêter de recevoir les builds Insider
Si vous ne souhaitez plus recevoir les versions Insider de Windows holographique, vous pouvez choisir de vous désabonner quand votre HoloLens exécute une génération de production, ou vous pouvez [récupérer votre appareil](hololens-recovery.md) à l’aide de l’Assistant de récupération avancé pour récupérer votre appareil sur une version non-Insider de Windows holographique.
> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui annulent l’inscription à partir de la version préliminaire d’Insider, après la réinstallation manuelle d’une nouvelle version préliminaire, rencontrent un écran bleu. Ensuite, ils doivent récupérer manuellement leur appareil. Pour plus d’informations sur si vous pourriez être affecté ou non, consultez plus d’informations sur ce [problème connu](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).
Pour vérifier que votre HoloLens exécute une build de production :
1. Accédez à **paramètres > système > à propos** de et recherchez le numéro de Build.
1. [Consultez les notes de publication pour les numéros de version de production](hololens-release-notes.md).
Pour refuser les builds Insider :
1. Sur un HoloLens exécutant une build de production, accédez à **paramètres > mettre à jour & sécurité > programme Windows Insider**, puis sélectionnez **arrêter les builds Insider**.
1. Suivez les instructions pour désinscrire votre appareil.
