---
title: Insider Preview pour Microsoft HoloLens
description: Découvrez comment prendre en main les builds Insider et fournir des commentaires précieux pour la prochaine mise à jour du système d’exploitation pour HoloLens.
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
ms.openlocfilehash: df0cb555c8445ef4d8f8165996a33e0f8c1a38653b45514594f893e3c761f65a
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2021
ms.locfileid: "120364283"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pour Microsoft HoloLens

Bienvenue dans les dernières versions préliminaires d’Insider pour HoloLens ! Il est facile de [commencer et de fournir des commentaires](hololens-insider.md#start-receiving-insider-builds) précieux pour la prochaine mise à jour du système d’exploitation pour HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notes de publication d’Insider

nous sommes ravis de commencer à utiliser de nouvelles fonctionnalités pour Windows insider. Les nouvelles builds feront l’d’un vol vers les canaux dev et bêta pour les dernières mises à jour. nous continuerons à mettre à jour cette page à mesure que nous ajouterons des fonctionnalités et des mises à jour à nos Windows builds insider. Soyez enthousiaste et prêt à mélanger ces mises à jour dans votre réalité.

| Fonctionnalité                 | Description                | Utilisateur ou scénario | Build introduite |
|-------------------------|----------------------------|--------------|------------------|
| [modifications du CSP pour la création de rapports HoloLens détails](#csp-changes-for-reporting-hololens-details) | Nouveaux fournisseurs de services de chiffrement pour l’interrogation des données | Administrateurs informatiques    | 20348,1403                 |
| [Stratégie de connexion automatique contrôlée par CSP](#auto-login-policy-controlled-by-csp) | Utilisé pour se connecter automatiquement à un compte | Administrateurs informatiques | 20348,1405 |
| [Prise en charge des fichiers PFX pour le gestionnaire de certificats](#pfx-file-support-for-certificate-manager) | ajouter des certificats PFX via l’interface utilisateur Paramètres | Utilisateur final | 20348,1405 |
| [affichez le rapport de diagnostic avancé dans Paramètres sur HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Afficher les journaux de diagnostic MDM sur l’appareil | Dépannage | 20348,1405 |
| [Notifications de diagnostics hors connexion](#offline-diagnostics-notifications) | Commentaires audiovisuels pour la collecte de journaux | Dépannage | 20348,1405 |
| [Utiliser uniquement des applications de magasin privé pour Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurer l’application du Windows Store pour afficher uniquement les applications de l’Organisation | IT Admin | 20348,1408 |
| [Améliorations de la collecte des journaux de faible capacité de stockage](#low-storage-log-collection-improvements) | Améliorations apportées aux scénarios de collecte des journaux dans des situations de faible stockage. | IT Admin | 20348,1412 |
| [Déplacement du mode de plateforme](#moving-platform-mode) | introduit la version bêta du Mode de plateforme mobile, qui, lorsqu’elle est configurée, permet l’utilisation de HoloLens 2 sur les grands navires marins ayant un mouvement faiblement dynamique. | Tous | 20348,1411 |
| [Correctifs et améliorations](#fixes-and-improvements) | Correctifs et améliorations pour HoloLens. | Tous | 20348,1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>modifications du CSP pour la création de rapports HoloLens détails

- introduite dans Windows build insider, 20348,1403

les fournisseurs de services de chiffrement suivants ont été mis à jour avec de nouvelles méthodes pour signaler des informations à partir de vos appareils HoloLens.

#### <a name="devdetail-csp---free-storage"></a>CSP DevDetail-gratuit Stockage

désormais, le fournisseur de services cloud DevDetail indique également l’espace de stockage disponible sur HoloLens appareil. cela doit correspondre approximativement à la valeur indiquée dans Paramètres page de Stockage de l’application. Voici le nœud spécifique qui contient ces informations.

- ./DevDetail/Ext/Microsoft/FreeStorage (opération d’extraction uniquement)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP DeviceStatus-SSID et BSSID

DeviceStatus CSP signale désormais également les SSID et BSSID de Wi-Fi réseau avec lequel HoloLens est connecté activement. Voici les nœuds spécifiques qui contiennent ces informations.

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

### <a name="auto-login-policy-controlled-by-csp"></a>Stratégie de connexion automatique contrôlée par CSP

Cette nouvelle stratégie de AutoLogonUser détermine si un utilisateur est connecté automatiquement. Certains clients souhaitent configurer des appareils qui sont liés à une identité, mais ne veulent pas une expérience de connexion. Imagine la sélection d’un appareil et l’utilisation immédiate de l’assistance à distance. ou ont l’avantage de pouvoir distribuer rapidement HoloLens appareils et permettre à leurs utilisateurs finaux d’accélérer la connexion.

Lorsque la stratégie est définie sur une valeur non vide, elle spécifie l’adresse de messagerie de l’utilisateur de connexion automatique. L’utilisateur spécifié doit ouvrir une session au moins une fois sur l’appareil pour activer l’ouverture de session automatique.

OMA-URI de la nouvelle valeur de chaîne de stratégie `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- L’ouverture de session automatique est activée pour l’utilisateur avec la même adresse de messagerie.

Sur un appareil sur lequel cette stratégie est configurée, l’utilisateur spécifié dans la stratégie doit se connecter au moins une fois. Les redémarrages ultérieurs de l’appareil après la première ouverture de session permettront à l’utilisateur spécifié d’ouvrir une session automatiquement. Un seul utilisateur de connexion automatique est pris en charge. Une fois activé, l’utilisateur connecté automatiquement n’est pas en mesure de se déconnecter manuellement. Pour ouvrir une session en tant qu’utilisateur différent, vous devez d’abord désactiver la stratégie.

> [!NOTE]
> - Certains événements, tels que les mises à jour majeures du système d’exploitation, peuvent obliger l’utilisateur spécifié à se reconnecter à l’appareil pour reprendre le comportement de connexion automatique. 
> - L’ouverture de session automatique est uniquement prise en charge pour les utilisateurs MSA et AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Prise en charge des fichiers PFX pour le gestionnaire de certificats

introduit dans Windows insider build 20348,1405. Nous avons ajouté la prise en charge du [Gestionnaire de certificats](certificate-manager.md) pour utiliser les certificats. pfx. lorsque les utilisateurs accèdent à **Paramètres**  >  **mettre à jour &**  >  les **certificats** de sécurité, puis sélectionnez **installer un certificat** , le fichier de certificat. pfx est pris en charge par l’interface utilisateur.
Les utilisateurs peuvent importer le certificat. pfx, avec la clé privée, dans le magasin de l’utilisateur ou le magasin de l’ordinateur.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>affichez le rapport de diagnostic avancé dans Paramètres sur HoloLens

Pour les appareils gérés lors de la résolution du problème, il est important de vérifier qu’une configuration de stratégie attendue est appliquée. auparavant, cette nouvelle fonctionnalité devait être désactivée via MDM ou proche de l’appareil après l’exportation des journaux de diagnostic MDM collectés via des comptes d' **Paramètres**  ->    >  **accéder à l’entreprise ou à l’école**, puis sélectionner **exporter les journaux de gestion** et les afficher sur un PC proche.

Les diagnostics MDM peuvent maintenant être affichés sur l’appareil à l’aide du navigateur Edge. Pour afficher plus facilement le rapport de diagnostic MDM, accédez à la page accès professionnel ou scolaire, puis sélectionnez **afficher le rapport de diagnostic avancé**. Cette opération génère et ouvre le rapport dans une nouvelle fenêtre de bord.

![affichez le rapport de diagnostic avancé dans Paramètres application.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notifications de diagnostics hors connexion

Il s’agit d’une mise à jour pour une fonctionnalité existante appelée [Diagnostics hors connexion](hololens-diagnostic-logs.md#offline-diagnostics). Auparavant, il n’existait pas d’indicateur clair pour les utilisateurs qu’ils avaient déclenché la collecte de diagnostics ou qu’ils se sont terminés.
à présent ajouté dans Windows builds insider, il existe deux formes de commentaires audiovisuels pour les diagnostics hors connexion. Les notifications de toasts s’affichent pour les deux moment où le regroupement démarre et se termine. Celles-ci s’affichent lorsque l’utilisateur est connecté et dispose d’éléments visuels.

![Toast pour la collecte des journaux.](./images/logcollection1.jpg)

![Toast lorsque la collecte des journaux est terminée.](./images/logcollection2.jpg)
 
Étant donné que les utilisateurs utilisent souvent les diagnostics hors connexion en tant que mécanisme de collecte de journaux de secours lorsqu’ils n’ont pas accès à un affichage, ne peuvent pas se connecter ou se trouvent toujours dans OOBE. un signal audio est également lu lors de la collecte des journaux. Ce son sera lu en plus de la notification Toast.

Cette nouvelle fonctionnalité est activée lorsque votre appareil est mis à jour et n’a pas besoin d’être activé ou géré. Dans tous les cas où ces nouveaux commentaires ne peuvent pas être affichés ou audibles, les diagnostics hors connexion seront toujours générés.

Nous espérons que ce nouvel ajout de commentaires audiovisuels est plus facile à recueillir des données de diagnostic et plus rapidement à résoudre vos problèmes.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Utiliser uniquement des applications de magasin privé pour Microsoft Store

La stratégie RequirePrivateStoreOnly a été activée pour HoloLens. cette stratégie permet à l’application Microsoft Store d’être configurée pour afficher uniquement la banque privée configurée pour votre organisation. Limiter l’accès aux seules applications que vous avez mises à disposition.

En savoir plus sur [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Améliorations de la collecte des journaux de faible capacité de stockage

Dans les scénarios où un appareil semble manquer d’espace disque lors de la collecte des journaux de diagnostic, un rapport supplémentaire nommé **StorageDiagnostics.zip** est créé. le seuil de stockage faible est déterminé automatiquement par Windows [sens du stockage](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

### <a name="moving-platform-mode"></a>Déplacement du mode de plateforme

À partir de la **Build Insider 20348,1411** , nous avons ajouté la prise en charge de la version bêta pour le suivi sur les plateformes de déplacement à faible dynamique sur HoloLens 2. après l’installation de la build et l’activation du Mode de plateforme mobile, vous serez en mesure d’utiliser votre HoloLens 2 dans les environnements précédemment inaccessibles, tels que les grands navires et les grands navires marins. Actuellement, la fonctionnalité est destinée à l’activation de ces plateformes mobiles spécifiques uniquement. Bien que rien ne vous empêche de tenter d’utiliser la fonctionnalité dans d’autres environnements, la fonctionnalité est axée sur l’ajout d’une prise en charge pour ces environnements en premier.

Pour en savoir plus sur ce qui est pris en charge et sur l’activation de cette nouvelle fonctionnalité, [consultez la page déplacement de la plateforme.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Correctifs et améliorations

- Correction d’un [problème connu pour le portail des appareils où aucune invite n’a été téléchargée pour le téléchargement des fichiers verrouillés.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Correction d’un [problème connu pour le portail des appareils avec délais de chargement et de téléchargement de fichiers.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- résout les problèmes liés à la création de rapports sur les propriétés de conformité des appareils HoloLens ; un redémarrage peut être nécessaire pour que les rapports corrects soient déclenchés sur les builds Insider.  
- activation d’une [API d’accès affectée](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) afin que les applications puissent désormais déterminer si une HoloLens s’exécute en mode plein écran pour l’utilisateur connecté à la HoloLens.
- Mise à jour de la version intégrée de l’assistance à distance qui est installée sur des clignotements actualisés.

## <a name="start-receiving-insider-builds"></a>Commencer à recevoir des builds Insider

> [!NOTE]
> Si vous n’avez pas récemment mis à jour votre appareil, redémarrez-le pour mettre à jour l’État et vous procurer la build la plus récente.
> - La commande vocale « reboot Device » fonctionne bien. 
> - vous pouvez également choisir le bouton redémarrer dans Paramètres/Windows programme insider.
>
> Nous avons rencontré un bogue sur le serveur principal que vous avez pu rencontrer, ce qui vous permettra de revenir en arrière.

sur un appareil HoloLens 2, accédez à **Paramètres**  >  **mettre à jour & Security**  >  **Windows programme insider** et sélectionnez **prise en main**. liez le compte que vous avez utilisé pour vous inscrire en tant que Windows insider.

Windows insider se déplace désormais vers les canaux. La sonnerie **rapide** deviendra le **canal de développement**, l’anneau **lent** deviendra le **canal bêta** et l’anneau de **version** préliminaire deviendra le **canal de version** préliminaire. Voici à quoi ressemble ce mappage :

![Windows Explication des canaux Insider](images/WindowsInsiderChannels.png)

pour plus d’informations, consultez [présentation des canaux Windows insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) sur Windows Blogs.
ensuite, sélectionnez **développement actif de Windows**, indiquez si vous souhaitez recevoir des builds du canal de **développement** ou du **canal bêta** et passez en revue les termes du programme.
Sélectionnez **confirmer > redémarrer maintenant** pour terminer. après avoir redémarré votre appareil, accédez à **Paramètres > mettre à jour & sécurité > rechercher les mises à jour** pour obtenir la build la plus récente.

### <a name="update-error-0x80070490-work-around"></a>Mettre à jour l’erreur de contournement 0x80070490

Si vous rencontrez une erreur de mise à jour 0x80070490 lors de la mise à jour sur le canal dev ou bêta, essayez le contournement à terme suivant. Il implique le déplacement de votre canal Insider, la sélection de la mise à jour, puis le déplacement de votre canal Insider.

#### <a name="stage-one---release-preview"></a>Version préliminaire de l’étape 1

1.  Paramètres, mettez à jour & Security, Windows programme insider, sélectionnez **version preview Channel**.

2.  Paramètres, mettez à jour & Security, Windows Update, **recherchez les mises à jour**. Après la mise à jour, passez à l’étape 2.

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
