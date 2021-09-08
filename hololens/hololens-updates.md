---
title: Gérer les mises à jour de HoloLens
description: Découvrez comment vos administrateurs peuvent utiliser la gestion des appareils mobiles pour gérer les mises à jour des appareils HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190036"
---
# <a name="manage-hololens-updates"></a>Gérer les mises à jour de HoloLens

HoloLens utilise Windows Update de la même manière que les autres appareils Windows 10. Lorsqu'une mise à jour est disponible, elle est automatiquement téléchargée et installée dès que votre appareil est branché et connecté à Internet. Cet article explique comment gérer les mises à jour dans une entreprise ou un autre environnement géré. Pour plus d'informations sur la gestion des mises à jour sur les appareils HoloLens individuels, consultez [Mettre à jour HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Gérer les mises à jour automatiquement

### <a name="managing-updates-by-using-windows-update-for-business"></a>Gérer les mises à jour à l'aide de Windows Update for Business

Windows Holographic for Business peut utiliser [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) pour gérer les mises à jour. Tous les appareils HoloLens 2 peuvent utiliser Windows Holographic for Business. Assurez-vous qu'ils utilisent Windows Holographic for Business Build 10.0.18362.1042 ou une version ultérieure. Si vous disposez d'appareils HoloLens (1ère génération), vous devez [les mettre à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md) afin de gérer leurs mises à jour.

Windows Update for Business connecte directement les appareils HoloLens au service Windows Update. Windows Update for Business vous permet de contrôler différents aspects du processus de mise à jour&mdash;autrement dit, quels appareils reçoivent telle ou telle mise à jour à un moment donné. Par exemple, vous pouvez déployer les mises à jour sur un sous-ensemble d'appareils pour les tester, puis poursuivre le déploiement ultérieurement sur les autres appareils. Vous pouvez également définir différents calendriers de mise à jour pour différents types de mises à jour.

> [!NOTE]  
> Pour les appareils HoloLens, vous pouvez gérer automatiquement les mises à jour des fonctionnalités (publiées deux fois par an) et les mises à jour qualité (publiées tous les mois ou selon les besoins, y compris les mises à jour de sécurité critiques). Pour plus d'informations sur les types de mises à jour, consultez [Types de mises à jour gérées par Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Vous pouvez configurer les paramètres de Windows Update for Business pour HoloLens à l'aide de stratégies dans une solution de gestion des appareils mobiles telle que Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Gérer les paramètres de Windows Update for Business à l'aide de Microsoft Intune

Pour plus d'informations sur l'utilisation d'Intune pour configurer Windows Update for Business, consultez [Gérer les mises à jour logicielles Windows 10 dans Intune](/intune/protect/windows-update-for-business-configure). Pour plus d'informations sur les fonctionnalités d'Intune prises en charge par HoloLens, consultez [Fonctions de gestion des mises à jour Intune prises en charge par HoloLens](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune fournit deux types de stratégies pour la gestion des mises à jour : l'*Anneau de mise à jour Windows 10* et la *Mise à jour des fonctionnalités Windows 10*. Le type de stratégie Mise à jour des fonctionnalités Windows 10, actuellement en phase de préversion publique, n'est pas pris en charge pour HoloLens.
>  
> Vous pouvez utiliser des stratégies de type Anneau de mise à jour Windows 10 pour gérer les mises à jour d'HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configurer des stratégies de mise à jour pour HoloLens 2 ou HoloLens (1ère génération)

Cette section décrit les stratégies que vous pouvez utiliser pour gérer les mises à jour d'HoloLens 2 ou HoloLens (1ère génération). Pour plus d'informations sur les fonctionnalités disponibles pour HoloLens 2, consultez [Planifier et configurer les déploiements de mises à jour pour HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Fournisseurs de services de configuration de stratégies - Mise à jour](/windows/client-management/mdm/policy-csp-update) définit les stratégies qui permettent de configurer Windows Update for Business.

> [!NOTE]  
> Pour obtenir la liste des fournisseurs de services de configuration de stratégies pris en charge par les différentes éditions d'HoloLens, consultez [Fournisseurs de services de configuration de stratégies pris en charge par les appareils HoloLens](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Configurer la recherche automatique des mises à jour

Vous pouvez utiliser la stratégie **Update/AllowAutoUpdate** pour gérer le comportement des mises à jour automatiques, comme l'analyse, le téléchargement et l'installation de celles-ci. Pour plus d'informations sur les paramètres disponibles pour cette stratégie, consultez [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Dans Microsoft Intune, vous pouvez utiliser **Comportement des mises à jour automatiques** pour modifier cette stratégie. Pour plus d’informations, consultez [Gérer les mises à jour logicielles de Windows 10 dans Intune](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Configurer un calendrier de mise à jour

Pour configurer les modalités d'application des mises à jour, utilisez les stratégies suivantes :

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valeurs : **0**–**7** (0 = tous les jours, 7 = dimanche, 0 = samedi)
  - Valeur par défaut : **0** (tous les jours)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valeurs : 0–23 (0 = minuit, 23 = 23h00)
  - Valeur par défaut : 15h00

#### <a name="configure-active-hours"></a>Configurer les heures d’activité
À partir de la [version 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2), un administrateur informatique peut spécifier la plage des heures d'activité des appareils HoloLens 2.

Heures d’activité identifie la période lors de laquelle l’appareil est censé être utilisé. Les redémarrages automatiques suite à une mise à jour surviennent en dehors des heures d’activité. La plage spécifiée est calculée dès l'heure de début des heures d'activité. Vous pouvez utiliser GPM, comme décrit dans [Configurer les heures d'activité à l'aide de GPM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). GPM utilise les paramètres Update/ActiveHoursStart, Update/ActiveHoursEnd et Update/ActiveHoursMaxRange du fournisseur de services de configuration de stratégies pour configurer les heures d'activité.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) : cette valeur définit l'heure de fin. 12 heures maximum sont possibles entre l'heure de début et l'heure de fin.
    -   Les valeurs prises en charge sont comprises entre 0 et 23. 0 correspond à minuit, 1 correspond à 1h00 du matin, etc.
    -   La valeur par défaut est 17 (17h00).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) : cette valeur définit le nombre maximal d'heures d'activité à partir de l'heure de début.
    -   Les valeurs prises en charge sont comprises entre 8 et 18.
    -   La valeur par défaut est 18 heures.
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) : cette valeur définit l'heure de début. 12 heures maximum sont possibles entre l'heure de début et l'heure de fin.
    -   Les valeurs prises en charge sont comprises entre 0 et 23. 0 correspond à minuit, 1 correspond à 1h00 du matin, etc.
    -   La valeur par défaut est 8 (8h00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Pour les appareils qui exécutent la version 1607 de Windows 10 uniquement

Vous pouvez utiliser les stratégies de mise à jour suivantes pour configurer les appareils de façon à obtenir les mises à jour à partir du service WSUS (Windows Server Update Service) au lieu de Windows Update :

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planifier et configurer les déploiements de mises à jour pour HoloLens 2

HoloLens 2 prend en charge davantage de fonctionnalités d'automatisation des mises à jour que HoloLens (1ère génération). Notamment si vous utilisez Microsoft Intune pour gérer les stratégies Windows Update for Business. Ces fonctionnalités facilitent la planification et l'implémentation des déploiements de mises à jour au sein de votre organisation.

#### <a name="plan-the-update-strategy"></a>Planifier la stratégie de mise à jour

Windows Updates for Business prend en charge les stratégies de report. Après la publication d'une mise à jour par Microsoft, vous pouvez utiliser une stratégie de report pour définir le délai à respecter avant d'installer cette mise à jour sur les appareils. En associant des sous-ensembles de vos appareils (également appelés *anneaux de mise à jour*) à différentes stratégies de report, vous pouvez coordonner une stratégie de déploiement des mises à jour au sein de votre organisation.

Prenons l'exemple d'une organisation qui possède 1 000 appareils qu'elle doit mettre à jour en cinq vagues. L'organisation peut créer cinq anneaux de mise à jour, comme le montre le tableau suivant.

|Group |Nombre d’appareils |Report (jours) |
| ---| :---: | :---: |
|Groupe 1 (personnel informatique) |5 |0 |
|Groupe 2 (utilisateurs précoces) |50 |60 |
|Groupe 3 (utilisateurs principaux 1) |250 |120 |
|Groupe 4 (utilisateurs principaux 2) |300 |150 |
|Groupe 5 (utilisateurs principaux 3) |395 |180 |

Progression du déploiement à l'échelle de l'organisation :

![Calendrier de déploiement des mises à jour.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configurer une stratégie de report des mises à jour

Une stratégie de report spécifie le nombre de jours entre la date à laquelle une mise à jour devient disponible et la date à laquelle elle est proposée à un appareil.

Vous pouvez configurer différents reports pour les mises à jour des fonctionnalités et les mises à jour qualité. Le tableau suivant répertorie les stratégies à utiliser pour chaque type, et le report maximal correspondant.

|Category |Policy |Report maximal |
| --- | --- | --- |
|Mises à jour des fonctionnalités |DeferFeatureUpdatesPeriodInDays |365 jours |
|Mises à jour qualité |DeferQualityUpdatesPeriodInDays |30 jours |

#### <a name="pause-updates-via-device"></a>Suspendre les mises à jour via l'appareil

Sur un appareil HoloLens 2 doté de [Windows Holographic version 2004](hololens-release-notes.md#windows-holographic-version-2004) ou versions ultérieures, un utilisateur qui n'a pas accès à GPM peut manuellement suspendre chaque mise à jour pour une durée maximale de 35 jours. Les utilisateurs peuvent accéder à ce paramètre via **Paramètres > Mise à jour et sécurité > Options avancées**, puis faire défiler jusqu'à **Suspendre les mises à jour** et sélectionner la date jusqu'à laquelle ils souhaitent suspendre les mises à jour. Une fois la date limite de suspension atteinte, l'appareil doit recevoir de nouvelles mises à jour avant que l'utilisateur puisse de nouveau les suspendre. 

À partir de la [version 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2), cette fonctionnalité de suspension des mises à jour peut être gérée pour les appareils HoloLens 2. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (par défaut) – Activé
    - 1 – Désactivé

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Fonctionnalités de gestion des mises à jour Intune prises en charge par HoloLens

Vous pouvez utiliser les fonctions de gestion des mises à jour Intune suivantes afin de gérer les mises à jour relatives à HoloLens.

- **Créer** et **Attribuer** : ces fonctions permettent d'ajouter un anneau de mise à jour Windows 10 à la liste des anneaux de mise à jour. Pour plus d'informations, consultez [Créer et attribuer des anneaux de mise à jour](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Suspendre** : si vous rencontrez un problème lors du déploiement d'une fonctionnalité ou d'une mise à jour qualité, vous pouvez suspendre la mise à jour pendant 35 jours (à partir d'une date spécifiée). Cette suspension empêche les autres appareils d'installer la mise à jour jusqu'à ce que vous ayez résolu ou éliminé le problème. Si vous suspendez une mise à jour de fonctionnalités, les mises à jour qualité sont maintenues pour garantir la sécurité des appareils. Lorsqu’un type de mise à jour est suspendu, le volet Vue d’ensemble de cet anneau affiche le nombre de jours restants avant la reprise de ce type de mise à jour. Une fois le temps spécifié écoulé, la suspension expire automatiquement et le processus de mise à jour reprend.

  Lorsque l'anneau de mise à jour est suspendu, vous pouvez sélectionner une des options suivantes :

  - **Prolonger** : permet de prolonger de 35 jours la période de suspension d'un type de mise à jour.
  - **Reprendre** : permet de reprendre les mises à jour de cet anneau. Vous pouvez de nouveau suspendre l'anneau de mise à jour si nécessaire.

  > [!NOTE]  
  > L'opération **Désinstaller** des anneaux de mise à jour n'est pas prise en charge pour les appareils HoloLens 2.

### <a name="delivery-optimization-preview"></a>Aperçu de l'optimisation de la distribution

La [version 21H1 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1) intègre une préversion précoce des paramètres d'optimisation de la distribution afin de réduire la consommation de bande passante des téléchargements lancés à partir de plusieurs appareils HoloLens. Une description plus complète de cette fonctionnalité ainsi que la configuration réseau recommandée sont disponibles ici : [Optimisation de la distribution pour les mises à jour Windows 10](/windows/deployment/update/waas-delivery-optimization).

Les paramètres suivants sont activés dans le cadre de la gestion et [peuvent être configurés à partir d'Intune](/mem/intune/configuration/delivery-optimization-settings) :

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Avertissements relatifs à cette préversion :

- Dans cette préversion, la prise en charge d'HoloLens est réservée aux mises à jour du système d'exploitation.
- Windows Holographic for Business prend uniquement en charge les modes de téléchargement HTTP et les téléchargements à partir d'un [point de terminaison Cache connecté Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) ; les modes de téléchargement pair à pair et les attributions de groupe ne sont actuellement pas pris en charge pour les appareils HoloLens.
- HoloLens ne prend pas en charge l'optimisation du déploiement ou de la distribution pour les points de terminaison Windows Server Update Services.
- La résolution des problèmes nécessite des diagnostics sur le serveur de Cache connecté ou la collecte d'une trace sur HoloLens via **Paramètres** > **Mise à jour et sécurité** >  **Résolution des problèmes** >  **Windows Update**.

## <a name="manually-check-for-updates"></a>Rechercher manuellement les mises à jour

Bien qu'HoloLens recherche régulièrement les mises à jour du système, vous pouvez être amené à effectuer des recherches manuellement.

Pour rechercher manuellement les mises à jour, accédez à **Paramètres** > **Mise à jour et sécurité** > **Rechercher les mises à jour**. Si l'application Paramètres indique que votre appareil est à jour, cela signifie que vous disposez de toutes les mises à jour disponibles à ce moment-là.

## <a name="manually-roll-back-an-update"></a>Annuler manuellement une mise à jour

Dans certains cas, il peut être nécessaire de revenir à une version antérieure du logiciel HoloLens. La procédure à suivre dépend de la façon dont vous utilisez HoloLens 2 ou HoloLens (1ère génération).

### <a name="revert-to-a-previous-version-hololens-2"></a>Revenir à une version antérieure (HoloLens 2)

Vous pouvez annuler les mises à jour et revenir à une version antérieure d'HoloLens 2 en utilisant [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab).

> [!NOTE]
> La restauration d'une version antérieure entraîne la suppression de vos fichiers et paramètres personnels.

Pour revenir à une version antérieure d'HoloLens 2, procédez comme suit :

1. Assurez-vous qu'aucun téléphone ou appareil Windows n'est connecté à votre ordinateur.
1. Sur votre ordinateur, téléchargez [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) à partir du Microsoft Store.
1. Téléchargez la [version la plus récente d'HoloLens 2](https://aka.ms/hololens2download).
1. Une fois ces téléchargements terminés, ouvrez **Explorateur de fichiers** > **Téléchargements**, cliquez avec le bouton droit sur le dossier compressé (.zip) que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour développer le fichier.
1. Utilisez un câble USB-A vers USB-C pour connecter votre appareil HoloLens à votre ordinateur. Même si vous avez utilisé d'autres câbles pour connecter votre appareil HoloLens, ce type de câble fonctionne mieux.
1. Advanced Recovery Companion détecte automatiquement votre appareil HoloLens. Sélectionnez la vignette **Microsoft HoloLens**.
1. Sur l'écran suivant, sélectionnez **Sélection manuelle des packages**, puis ouvrez le dossier que vous avez développé précédemment.
1. Sélectionnez le fichier d'installation (.ffu).
1. Sélectionnez **Installer le logiciel** et suivez les instructions.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Revenir à une version antérieure (HoloLens, 1ère génération)

Vous pouvez annuler les mises à jour et revenir à une version antérieure d'HoloLens (1ère génération) en utilisant [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).

> [!NOTE]
> La restauration d'une version antérieure d'HoloLens entraîne la suppression de vos fichiers et paramètres personnels.

Pour revenir à une version antérieure d'HoloLens (1ère génération), procédez comme suit :

1. Assurez-vous qu'aucun téléphone ou appareil Windows n'est connecté à votre ordinateur.
1. Sur votre ordinateur, téléchargez [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Téléchargez le [package de récupération HoloLens Anniversary Update](https://aka.ms/hololensrecovery).
1. Une fois les téléchargements terminés, ouvrez **Explorateur de fichiers** > **Téléchargements**, cliquez avec le bouton droit sur le dossier compressé (.zip) que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour développer le fichier.
1. Utilisez le câble micro-USB fourni avec votre appareil HoloLens pour connecter celui-ci à votre ordinateur. Même si vous avez utilisé d'autres câbles pour connecter votre appareil HoloLens, ce type de câble fonctionne mieux.
1. WDRT détecte automatiquement votre appareil HoloLens. Sélectionnez la vignette **Microsoft HoloLens**.
1. Sur l'écran suivant, sélectionnez **Sélection manuelle des packages**, puis ouvrez le dossier que vous avez développé précédemment.
1. Sélectionnez le fichier d'installation (.ffu).
1. Sélectionnez **Installer le logiciel** et suivez les instructions.

**Si WDRT ne détecte pas votre appareil**

Si WDRT ne détecte pas votre appareil HoloLens, essayez de redémarrer votre ordinateur. Si le problème persiste, sélectionnez **Mon appareil n'a pas été détecté**, choisissez **Microsoft HoloLens**, puis suivez les instructions.

## <a name="related-articles"></a>Articles connexes

- [Notes de publication de HoloLens 2](hololens-release-notes.md)
- [Qu'est-ce que Windows Update for Business ?](/windows/deployment/update/waas-manage-updates-wufb)
- [Attribuer des appareils à des canaux de maintenance pour les mises à jour Windows 10](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gérer les mises à jour logicielles de Windows 10 dans Intune](/mem/intune/protect/windows-update-for-business-configure)
