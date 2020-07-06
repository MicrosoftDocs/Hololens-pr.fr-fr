---
title: Gérer les mises à jour de HoloLens
description: Les administrateurs peuvent utiliser la gestion des appareils mobiles pour gérer les mises à jour sur les appareils HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828066"
---
# Gérer les mises à jour de HoloLens

HoloLens utilise Windows Update de la même manière que les autres appareils Windows 10. Lorsqu'une mise à jour est disponible, elle est automatiquement téléchargée et installée la prochaine fois que votre appareil est branché et connecté à l'internet. Cet article explique comment gérer les mises à jour dans une entreprise ou un autre environnement géré. Pour plus d’informations sur la gestion des mises à jour sur les appareils HoloLens individuels, voir [Mise à jour de HoloLens](hololens-update-hololens.md).

## Gérer les mises à jour automatiquement

Windows Holographic for Business peut utiliser [Windows Update pour Entreprise](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) pour gérer les mises à jour. Tous les appareils HoloLens 2 peuvent utiliser Windows Holographic for Business. Assurez-vous qu’ils utilisent Windows Holographic for Business Build 10.0.18362.1042 ou une version ultérieure. Si vous disposez d’appareils HoloLens (1ère génération), vous devez [les mettre à niveau vers Windows Holographic for Business](hololens1-upgrade-enterprise.md) pour gérer leurs mises à jour.

Windows Update pour Entreprise connecte les appareils HoloLens directement au service Windows Update. À l’aide de Windows Update pour Entreprise, vous pouvez contrôler plusieurs aspects du processus de mise à jour&mdash;autrement dit, quels appareils reçoivent les mises à jour à l’heure qui leur est associée. Par exemple, vous pouvez déployer les mises à jour sur un sous-ensemble d’appareils pour les tester, puis déployer les mises à jour sur les autres appareils à une date ultérieure. Vous pouvez également définir différents calendriers de mise à jour pour différents types de mises à jour.

> [!NOTE]  
> Pour les appareils HoloLens, vous pouvez automatiquement gérer les mises à jour de fonctionnalités (publiées deux fois par an) et les mises à jour de qualité (publiées tous les mois ou requises, y compris les mises à jour de sécurité critiques). Pour plus d’informations sur les types de mise à jour, voir [Types de mises à jour gérées par Windows Update pour Entreprise](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Vous pouvez configurer les paramètres de Windows Update pour Entreprise pour HoloLens à l’aide de stratégies dans une solution de gestion des appareils mobiles (MDM, en anglais) telle que Microsoft Intune.

Pour plus d’informations sur l’utilisation de Intune pour configurer Windows Update pour Entreprise, voir [Gérer les mises à jour logicielles Windows 10 dans Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).

> [!IMPORTANT]  
> Intune fournit deux types de stratégie pour gérer les mises à jour: *Sonnerie de mise à jour Windows 10* et *Mises à jour de fonctionnalités Windows 10*. Le type de stratégie de mise à jour des fonctionnalités de Windows 10 est en aperçu public pour le moment et n'est pas pris en charge pour HoloLens.

>  
> Vous pouvez utiliser les stratégies périphériques de mise à jour de Windows 10 Update pour gérer les mises à jour de HoloLens 2.

### Configurer des stratégies de mise à jour pour HoloLens 2 ou HoloLens (1ère génération)

Cette section décrit les stratégies que vous pouvez utiliser pour gérer les mises à jour de HoloLens 2 ou HoloLens (1ère génération). Pour plus d’informations sur les fonctionnalités supplémentaires disponibles pour HoloLens 2, voir [Planifier et configurer les mises à jour de HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

Le[fournisseur de services de configuration de stratégie (CSP, en anglais](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update))[](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)définit les stratégies qui configurent Windows Update pour Entreprise.

> [!NOTE]  
> Pour plus d’informations sur les stratégies spécifiques prises en charge par les éditions spécifiques de HoloLens, voir [Stratégies prises en charge par les appareils HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).

#### Configurer la vérification automatique des mises à jour

Vous pouvez utiliser la **Stratégie de mise à jour / Autoriser la mise à jour automatique** pour gérer le comportement de mise à jour automatique, tel que l’analyse, le téléchargement et l’installation des mises à jour.

Cette stratégie prend en charge les valeurs suivantes:

- **0** - Avertir l’utilisateur quand une mise à jour est prête à être téléchargée qui s’applique à l’appareil.
- **** 1 - Installer automatiquement la mise à jour et informer l’utilisateur qu’il doit planifier le redémarrage de l’appareil.  
- **2** - Installer automatiquement la mise à jour, puis redémarrer l’appareil. Il s’agit de la valeur recommandée. Il s’agit de la valeur par défaut pour cette stratégie.  

- **3** - Installer automatiquement la mise à jour, puis redémarrer à une heure précise. Spécifier la date et l’heure de l’installation. Si aucun jour et aucune heure ne sont spécifiés, la valeur par défaut est 3:00 A.M.  

- **4** - Installer automatiquement la mise à jour, puis redémarrer l’appareil. Cette option met également la page Paramètres en lecture seule.

- **** 5 - Désactiver les mises à jour automatiques.

Pour plus d’informations sur les paramètres disponibles pour cette stratégie, voir [Mise à jour / Autoriser la mise à jour automatique](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Dans Microsoft Intune, vous pouvez utiliser **Comportement de mise à jour automatique** pour modifier cette stratégie. Pour plus d’informations, voir [Gérer les mises à jour logicielles dans Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurer une planification de mise à jour

Pour configurer les modalités d’application des mises à jour, utilisez les stratégies suivantes:

- [Mise à jour / Installation programmée](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).  
   - Valeurs: **0**–**7** (0 = tous les jours, 1 = Dimanche, 7 = Samedi)
   - Valeur par défaut: **0** (tous les jours)
- [Mise à jour / Installation programmée](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).
   - Valeurs: 0–23 (0 = minuit, 23 = 11:00 P.M.)
   - Valeur par défaut : 3:00 P.M.

#### Pour les appareils exécutant Windows 10, version 1607 uniquement

Vous pouvez utiliser les stratégies de mise à jour suivantes pour configurer les appareils de façon à obtenir les mises à jour à partir du service WSUS (Windows Server Update Service) au lieu de Windows Update:

- [Service de mise à jour / Autorisation de mise à jour](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Mise à jour / Demande d'approbation de la mise à jour](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planifier et configurer les mises à jour pour HoloLens 2

HoloLens 2 prend en charge d’autres fonctionnalités d’automatisation de mise à jour que HoloLens (1ère génération). C’est particulièrement vrai si vous utilisez Microsoft Intune pour gérer la stratégie Windows Update pour Entreprise. Ces fonctionnalités simplifient la planification et l’implémentation des mises à jour au sein de votre organisation.

#### Planifier la stratégie de mise à jour

Les mises à jour Windows for Business prennent en charge les stratégies de report. Une fois que Microsoft a publié une mise à jour, vous pouvez utiliser une stratégie de report pour définir le délai d’attente avant d’installer cette mise à jour sur les appareils. En associant des sous-ensembles de vos appareils (appelés *Sonneries de mise à jour*) avec différentes stratégies de report, vous pouvez coordonner une stratégie des mises à jour pour votre organisation.

Par exemple, supposons qu’une organisation dispose de 1 000 appareils et qui doit les mettre à jour de cinq façons. L’organisation peut créer cinq sonneries de mise à jour, comme illustré dans le tableau suivant.

|Groupe |Nombre d’appareils à gérer |Report (jours) |
| ---| :---: | :---: |
|Groupe 1 (personnel informatique) |5 |0 |
|Groupe 2 (utilisateurs précoces) |50 |60 |
|Groupe 3 (principal 1) |250 |120 |
|Groupe 4 (principal 2) |300 |150 |
|Groupe 5 (principal 3) |395 |180 |

Voici comment le déploiement progresse au fil du temps vers toute l’organisation.

![Calendrier pour le déploiement des mises à jour](./images/hololens-updates-timeline.png)

#### Configurer une stratégie de report de mise à jour

Une stratégie de report spécifie le nombre de jours entre la date à laquelle une mise à jour devient disponible et la date à laquelle la mise à jour est proposée à un appareil.

Vous pouvez configurer différents reports pour les mises à jour de fonctionnalités et les mises à jour de la qualité. Le tableau suivant répertorie les stratégies spécifiques à utiliser pour chaque type, ainsi que le report maximal pour chacun.

|Catégorie |Stratégie |Report maximal |
| --- | --- | --- |
|Mises à jour des fonctionnalités |DeferFeatureUpdatesPeriodInDays |365jours |
|Mises à jour qualité |DeferQualityUpdatesPeriodInDays |30jours |

####  Exemples: Utiliser Intune pour gérer les mises à jour

**Exemple 1: Créer et attribuer une sonnerie de mise à jour**

Pour obtenir une version plus détaillée de cet exemple, voir [Créer et attribuer des mises à jour de sonneries](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

1. Connectez-vous au [Centre d’administration Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)et accédez à vos profils Intune.
1. Sélectionnez **Mises à jour logicielles Windows 10** > **Mises à jour de sonneries** > **Créer**.
1. Sous **Élémentaires**, spécifiez un nom et une description (facultatif), puis sélectionnez **Suivant**.
1. Sous **Paramètres de mise à jour de sonneries**, pour Canal de maintenance, sélectionnez Canal semi-annuel, puis modifiez la période de report de la mise à jour des caractéristiques à 120. Sélectionnez **Suivant**.
1. Sous **Affectations**, sélectionnez **+ Sélectionnez les groupes à inclure**, puis affectez la sonnerie de mise à jour à un ou plusieurs groupes. Utilisez **+ Sélectionnez les groupes à inclure** afin d’affiner les affectations. Sélectionnez **Suivant**.
1. Sous **Révision + Créer**, passez en revue les paramètres. Lorsque vous êtes prêt à enregistrer la configuration de la mise à jour de sonnerie, sélectionnez **Créer**.

La liste des sonneries de mise à jour inclut désormais la nouvelle mise à jour de sonnerie pour Windows 10.

**Exemple 2: Interrompre une sonnerie de mise à jour**

Si vous rencontrez un problème lorsque vous déployez une mise à jour de fonctionnalité ou de qualité, vous pouvez suspendre la mise à jour de 35 jours (à partir d’une date spécifique). Cette pause empêche d’autres appareils d’installer la mise à jour jusqu’à ce que vous résolviez ou éliminiez le problème. Si vous suspendez une mise à jour de fonctionnalité, les mises à jour de qualité sont encore proposées aux appareils pour s’assurer qu’ils restent sécurisés. Une fois l’heure spécifiée écoulée, la pause expire automatiquement. À ce stade, le processus de mise à jour reprend.

Pour interrompre une sonnerie de mise à jour dans Intune, procédez comme suit:

1. Dans la page vue d’ensemble de sonnerie de mise à jour, sélectionnez **Suspendre**.
1. Sélectionnez le type de mise à jour (Fonctionnalité ou Qualité) à suspendre, puis sélectionnez **OK**.

Lorsqu'un type de mise à jour est en pause, le volet Aperçu de cette sonnerie affiche le nombre de jours restants avant que ce type de mise à jour ne reprenne.

Lorsque la sonnerie de mise à jour est suspendue, vous pouvez sélectionner l’une des options suivantes:

- Pour prolonger la période de pause d’un type de mise à jour pour 35 jours, sélectionnez **Prolonger**.
- Pour restaurer les mises à jour de cette sonnerie pour l’opération active, sélectionnez **Résumé**. Vous pouvez suspendre la sonnerie de mise à jour si nécessaire.

> [!NOTE]  
> L’opération **Désinstaller** pour les sonneries de mise à jour n’est pas prise en charge pour les appareils HoloLens 2.

## Vérifier manuellement les mises à jour

Bien que HoloLens vérifie régulièrement les mises à jour du système de sorte que vous n’ayez pas à le faire, il peut arriver que vous vouliez vérifier manuellement les mises à jour.

Pour rechercher manuellement les mises à jour, accédez à **Paramètres** > **Mise à jour et sécurité** > **Rechercher les mises à jour**. Si l’application Paramètres indique que votre appareil est à jour, toutes les mises à jour sont actuellement disponibles.

## Rétablir manuellement une mise à jour

Dans certains cas, vous souhaiterez peut-être revenir à une version antérieure du logiciel HoloLens. La procédure à suivre dépend de la façon dont vous utilisez HoloLens 2 ou HoloLens (1ère génération).

### Revenir à une version précédente (HoloLens 2)

Vous pouvez annuler les mises à jour et revenir à une version précédente de l’HoloLens 2 en utilisant l'Assistant de récupération avancée (Advanced Recovery Companion, en anglais) pour réinitialiser votre HoloLens à la version précédente.

> [!NOTE]
> La restauration d’une version antérieure supprime vos fichiers et paramètres personnels.

Pour revenir à une version antérieure de HoloLens 2, procédez comme suit:

1. Assurez-vous que vous n’avez pas de téléphone ou d’appareil Windows branché sur votre ordinateur.
1. Sur votre ordinateur, téléchargez l’ [Assistant de récupération avancée (Advanced Recovery Companion, en anglais](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab))[](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) à partir du Microsoft Store.
1. Téléchargez la [version la plus récente de HoloLens 2](https://aka.ms/hololens2download).
1. Lorsque vous avez terminé ces téléchargements, ouvrez **Explorateur de fichiers** > **Téléchargements**, cliquez avec le bouton droit sur le dossier compressé (zippé) que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour développer le fichier.
1. Utilisez un câble USB-A vers USB-C pour connecter votre appareil HoloLens à votre ordinateur. Même si vous avez utilisé d'autres câbles pour connecter votre HoloLens, ce type de câble fonctionne mieux.
1. L’Assistant de récupération avancée détecte automatiquement votre appareil HoloLens. Sélectionnez la vignette **Microsoft HoloLens**.
1. Dans l’écran suivant, sélectionnez **Sélection manuelle du package**, puis ouvrez le dossier que vous avez développé précédemment. 
1. Sélectionnez le fichier d’installation (fichier ayant une extension .ffu).
1. Sélectionnez**Installer le logiciel**, puis suivez les instructions.

### Revenir à une version précédente (HoloLens, 1ère génération)

Vous pouvez annuler les mises à jour et revenir à une version précédente de l'HoloLens (1ère génération) en utilisant l’Outil de récupération des appareils Windows (Windows Device Recovery Tool, en anglais) pour réinitialiser votre HoloLens à la version précédente.

> [!NOTE]
> La restauration d’une version antérieure supprime vos fichiers et paramètres personnels.

Pour revenir à une version antérieure de HoloLens (1ère génération), procédez comme suit:

1. Assurez-vous que vous n’avez pas de téléphone ou d’appareil Windows branché sur votre ordinateur.
1. Téléchargez et installez l’ [Outil de récupération des appareils Windows (Windows Device Recovery Tool, en anglais](https://support.microsoft.com/help/12379))[](https://support.microsoft.com/help/12379) sur votre ordinateur.
1. Téléchargez le [package de récupération de mise à jour anniversaire HoloLens](https://aka.ms/hololensrecovery).
1. Lorsque vous avez terminé ces téléchargements, ouvrez **Explorateur de fichiers** > **Téléchargements**, cliquez avec le bouton droit sur le dossier compressé (zippé) que vous venez de télécharger, puis sélectionnez **Extraire tout** > **Extraire** pour développer le fichier.
1. Utilisez le câble micro-USB fourni avec votre appareil HoloLens pour connecter votre appareil HoloLens à votre ordinateur. Même si vous avez utilisé d’autres câbles pour connecter votre HoloLens, celui-ci fonctionne mieux.
1. Le WDRT détecte automatiquement votre appareil HoloLens. Sélectionnez la vignette **Microsoft HoloLens**.
1. Dans l’écran suivant, sélectionnez **Sélection manuelle du package**, puis ouvrez le dossier que vous avez développé précédemment. 
1. Sélectionnez le fichier d’installation (fichier ayant une extension .ffu).
1. Sélectionnez**Installer le logiciel**, puis suivez les instructions.

> [!NOTE]
> Si le WDRT ne détecte pas votre appareil HoloLens, essayez de redémarrer votre ordinateur. Si cela ne fonctionne pas, sélectionnez **Mon appareil n’a pas été détecté**, sélectionnez **Microsoft HoloLens**, puis suivez les instructions.

## Articles connexes

- [Déployer les mises à jour à l’aide de Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Affecter des appareils aux canaux de maintenance pour les mises à jour Windows10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gérer les mises à jour du logiciel Windows 10 dans Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
