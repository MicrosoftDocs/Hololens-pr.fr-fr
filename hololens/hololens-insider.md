---
title: Insider Preview pour Microsoft HoloLens
description: Découvrez comment prendre en main les builds Insider et fournir des commentaires précieux pour la prochaine mise à jour du système d’exploitation pour HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924355"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pour Microsoft HoloLens

Bienvenue dans les dernières versions préliminaires d’Insider pour HoloLens ! Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) précieux pour la prochaine mise à jour du système d’exploitation pour HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notes de publication d’Insider

Nous sommes ravis que toutes nos fonctionnalités récentes ont été rendues publiques ! Si vous souhaitez en savoir plus à ce sujet, consultez la [page notes de publication](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Commencer à recevoir des builds Insider

> [!NOTE]
> Si vous n’avez pas récemment mis à jour votre appareil, redémarrez-le pour mettre à jour l’État et vous procurer la build la plus récente.
>
> - La commande vocale « reboot Device » fonctionne bien.
> - vous pouvez également choisir le bouton redémarrer dans Paramètres/Windows programme insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez pu rencontrer, ce qui vous permettra de revenir en arrière.

sur un appareil HoloLens 2, accédez à **Paramètres**  >  **mettre à jour & Security**  >  **Windows programme insider** et sélectionnez **prise en main**. liez le compte que vous avez utilisé pour vous inscrire en tant que Windows insider.

> [!NOTE]
> Pour inscrire votre appareil dans les builds Insider, vous devez activer la télémétrie facultative. si vous ne l’avez pas déjà fait, ouvrez l’application Paramètres, puis sélectionnez **confidentialité**  ->  **diagnostics & commentaires** , puis sélectionnez **données de diagnostic facultatives**.

Windows insider se déplace désormais vers les canaux. La sonnerie **rapide** deviendra le **canal de développement**, l’anneau **lent** deviendra le **canal bêta** et l’anneau de **version** préliminaire deviendra le **canal de version** préliminaire. Voici à quoi ressemble ce mappage :

![Windows Explication des canaux Insider.](images/WindowsInsiderChannels.png)

pour plus d’informations, consultez [présentation des canaux Windows insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur Windows Blogs.
ensuite, sélectionnez **développement actif de Windows**, indiquez si vous souhaitez recevoir des builds du canal de **développement** ou du **canal bêta** et passez en revue les termes du programme.
Sélectionnez **confirmer > redémarrer maintenant** pour terminer. après avoir redémarré votre appareil, accédez à **Paramètres > mettre à jour & sécurité > rechercher les mises à jour** pour obtenir la build la plus récente.

### <a name="update-error-0x80070490-work-around"></a>Mettre à jour l’erreur de contournement 0x80070490

Si vous rencontrez une erreur de mise à jour 0x80070490 lors de la mise à jour sur le canal dev ou bêta, essayez la solution de contournement à la une suivante. Il implique le déplacement de votre canal Insider, la sélection de la mise à jour, puis le déplacement de votre canal Insider.

#### <a name="stage-one---release-preview"></a>Version préliminaire de l’étape 1

1. Paramètres, mettez à jour & Security, Windows programme insider, sélectionnez **version preview Channel**.

2. Paramètres, mettez à jour & Security, Windows Update, **recherchez les mises à jour**. Après la mise à jour, passez à l’étape 2.

#### <a name="stage-two---dev-channel"></a>Deuxième étape-canal de développement

1. Paramètres, mettre à jour & Security, Windows programme insider, sélectionnez **canal de développement**.

2. Paramètres, mettez à jour & Security, Windows Update, **recherchez les mises à jour**.

## <a name="ffu-download-and-flash-directions"></a>FFU téléchargement et itinéraires Flash

Pour effectuer un test avec un FFU signé par un vol, vous devez d’abord déverrouiller votre appareil avant de faire clignoter le FFU de vol signé.

1. Sur PC :
    1. Téléchargez FFU sur votre ordinateur à partir de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installez ARC (complément de récupération avancé) à partir du Microsoft Store : [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. sur HoloLens-Flight Unlock : ouvrez **Paramètres**  >  **mettre à jour & sécurité**  >  **Windows programme d’insider** , puis inscrivez-vous et redémarrez l’appareil.

1. Flash FFU : vous pouvez désormais faire clignoter le FFU de vol signé à l’aide d’ARC.

### <a name="provide-feedback-and-report-issues"></a>Fournir des commentaires et signaler des problèmes

utilisez [l’application Hub de commentaires](hololens-feedback.md) sur votre HoloLens pour fournir des commentaires et signaler des problèmes. L’utilisation de feedback Hub garantit que toutes les informations de diagnostic nécessaires sont incluses pour aider nos ingénieurs à déboguer et résoudre rapidement le problème.  les problèmes liés à la version chinoise et japonaise de HoloLens doivent être signalés de la même façon.

> [!NOTE]
> Veillez à accepter l’invite qui vous demande si vous souhaitez que le hub de commentaires accède à votre dossier documents (sélectionnez **Oui** lorsque vous y êtes invité).

## <a name="note-for-developers"></a>Remarque pour les développeurs

Nous vous invitons à essayer de développer vos applications à l’aide des builds Insider de HoloLens.  consultez la [Documentation du développeur HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) pour commencer. Ces mêmes instructions fonctionnent avec les builds Insider de HoloLens.  vous pouvez utiliser les mêmes builds unity et Visual Studio que vous utilisez déjà pour le développement HoloLens.

## <a name="stop-receiving-insider-builds"></a>Arrêter de recevoir les builds Insider

si vous ne souhaitez plus recevoir les builds insider d’Windows holographique, vous pouvez vous désabonner lorsque votre HoloLens exécute une build de production, ou vous pouvez [récupérer votre appareil](hololens-recovery.md) à l’aide de l’assistant de récupération avancé pour récupérer votre appareil sur une version non-insider de Windows holographique.

> [!CAUTION]
> Il existe un problème connu dans lequel les utilisateurs qui annulent l’inscription à partir de la version préliminaire d’Insider, après la réinstallation manuelle d’une nouvelle version préliminaire, rencontrent un écran bleu. Ensuite, ils doivent récupérer manuellement leur appareil. Pour plus d’informations sur si vous pourriez être affecté ou non, consultez plus d’informations sur ce [problème connu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).

pour vérifier que votre HoloLens exécute une build de production :

1. accédez à **Paramètres > système > sur** et recherchez le numéro de build.

1. [Consultez les notes de publication pour les numéros de version de production](hololens-release-notes.md).

Pour refuser les builds Insider :

1. sur un HoloLens exécutant une version de production, accédez à **Paramètres > Update & Security > Windows programme insider**, puis sélectionnez **arrêter les builds insider**.

1. Suivez les instructions pour désinscrire votre appareil.
