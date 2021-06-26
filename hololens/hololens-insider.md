---
title: Insider Preview pour Microsoft HoloLens
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924364"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pour Microsoft HoloLens

Bienvenue dans les dernières versions préliminaires d’Insider pour HoloLens ! Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) précieux pour la prochaine mise à jour majeure du système d’exploitation pour HoloLens.

## <a name="windows-insider-release-notes"></a>Notes de publication de Windows Insider

Nous sommes ravis de commencer à effectuer le vol de nouvelles fonctionnalités vers Windows Insider. Les nouvelles builds feront l’d’un vol vers les canaux dev et bêta pour les dernières mises à jour. Nous continuerons à mettre à jour cette page à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos builds Windows Insider. Soyez enthousiaste et prêt à mélanger ces mises à jour dans votre réalité. 

### <a name="csp-changes-on-hololens"></a>Modifications du CSP sur HoloLens
 
- Présenté dans la version Windows Insider, 20348,1403

#### <a name="devdetail-csp"></a>Fournisseur CSP DevDetail

DevDetail CSP signale désormais également un espace de stockage libre sur l’appareil HoloLens. Cela doit correspondre approximativement à la valeur affichée dans la page de stockage de l’application de paramètres. Voici le nœud spécifique qui contient ces informations.

- ./DevDetail/Ext/Microsoft/FreeStorage (opération d’extraction uniquement)

#### <a name="devicestatus-csp"></a>Fournisseur CSP DeviceStatus

DeviceStatus CSP signale désormais également le SSID et le BSSID du réseau WiFi avec lequel HoloLens est connecté activement. Voici les nœuds spécifiques qui contiennent ces informations.

- /Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresse MAC de Wi-Fi adaptateur*/SSID
- /Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresse MAC de Wi-Fi adaptateur*/BSSID

Exemple d’objet BLOB SyncML (pour les fournisseurs MDM) à interroger pour NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>Correctifs et améliorations :

- Correction d’un [problème connu pour le portail des appareils où aucune invite n’a été téléchargée pour le téléchargement des fichiers verrouillés.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Correction d’un [problème connu pour le portail des appareils avec délais de chargement et de téléchargement de fichiers.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

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
> Il existe un problème connu dans lequel les utilisateurs qui annulent l’inscription à partir de la version préliminaire d’Insider, après la réinstallation manuelle d’une nouvelle version préliminaire, rencontrent un écran bleu. Ensuite, ils doivent récupérer manuellement leur appareil. Pour plus d’informations sur si vous pourriez être affecté ou non, consultez plus d’informations sur ce [problème connu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).
Pour vérifier que votre HoloLens exécute une build de production :
1. Accédez à **paramètres > système > à propos** de et recherchez le numéro de Build.
1. [Consultez les notes de publication pour les numéros de version de production](hololens-release-notes.md).
Pour refuser les builds Insider :
1. Sur un HoloLens exécutant une build de production, accédez à **paramètres > mettre à jour & sécurité > programme Windows Insider**, puis sélectionnez **arrêter les builds Insider**.
1. Suivez les instructions pour désinscrire votre appareil.
