---
title: Collecter et utiliser les informations de diagnostic provenant des appareils HoloLens
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828401"
---
# Collecter et utiliser les informations de diagnostic provenant des appareils HoloLens

Les utilisateurs et administrateurs HoloLens peuvent choisir parmi quatre méthodes différentes pour collecter les informations de diagnostic du HoloLens:

- Application Hub de commentaires
- Fournisseur de services de configuration DiagnosticLog
- Application Paramètres

> [!IMPORTANT]  
> Les journaux de diagnostic des appareils contiennent des informations d’identification personnelle, par exemple sur les processus ou applications lancés par l’utilisateur dans le cadre d’opérations typiques. Lorsque plusieurs utilisateurs partagent un appareil HoloLens (par exemple, les utilisateurs se connectent au même appareil à l’aide de différents comptes Microsoft Azure Active Directory (AAD)) les journaux de diagnostic peuvent contenir des informations d’identification personnelle qui s’appliquent à plusieurs utilisateurs. Pour plus d’informations, consultez la [déclaration de confidentialité de Microsoft](https://privacy.microsoft.com/privacystatement).

Le tableau suivant compare les trois méthodes de collection. Les noms de méthode sont liés à des informations plus détaillées dans les sections qui suivent le tableau.

|Méthode |Conditions préalables |Emplacements des données |Accès aux données et utilisation |Rétention des données |
| --- | --- | --- | --- | --- |
|[Hub de commentaires](#feedback-hub) |Connexion réseau et Internet<br /><br />Application Hub de commentaires<br /><br />Autorisation de chargement de fichiers dans le Cloud Microsoft |Cloud Computing Microsoft<br /><br />Appareil HoloLens (facultatif) |L’utilisateur demande une assistance, accepte les conditions d’utilisation et charge les données<br /><br />Les employés Microsoft affichent les données de la même manière que les conditions d’utilisation. |Les données du Cloud sont conservées pendant la période définie par la déclaration de confidentialité de nouvelle génération (NGP). Les données sont alors supprimées automatiquement.<br /><br />Les données sur l’appareil peuvent être supprimées à tout moment par un utilisateur disposant des autorisations de propriétaire de l' **appareil** ou d' **administrateur** . |
|[Utilitaire de dépannage des paramètres](#settings-troubleshooter) |Application Paramètres |AppareilHoloLens<br /><br />Ordinateur connecté (facultatif) |L’utilisateur stocke les données, et seul l’utilisateur accède aux données (sauf si l’utilisateur partage spécifiquement les données avec un autre utilisateur). |Les données sont conservées tant que l’utilisateur ne les supprime pas. * |
|[Fournisseur de services de configuration DiagnosticLog](#diagnosticlog-csp) |Connexion réseau<br /><br />Environnement GPM prenant en charge le fournisseur de services de DiagnosticLog |L’administrateur configure les emplacements de stockage |Dans l’environnement géré, l’utilisateur est implicitement autorisé à accéder aux données de l’administrateur.<br /><br />Un administrateur configure les rôles et les autorisations d’accès. | Un administrateur configure une stratégie de rétention. |


-   L’utilisateur final est responsable du partage du journal de manière responsable avec une autre personne. Ces fichiers sont principalement utiles lorsque vous contactez le service clientèle et le support technique.  

## Hub de commentaires

Un utilisateur HoloLens peut utiliser l’application de bureau Hub de commentaires Microsoft pour envoyer des informations de diagnostic au support technique Microsoft. Pour plus d’informations et pour obtenir des instructions complètes, voir [Donnez-nous des commentaires](hololens-feedback.md).  

> [!NOTE]  
> **Utilisateurs commerciaux ou d’entreprise:** Si vous utilisez l’application Hub de commentaires pour signaler un problème lié à la gestion des périphériques mobiles, la mise en service ou tout autre aspect de la gestion des **Enterprise Management**appareils, remplacez la catégorie application par la  >  **catégorie appareil**de gestion de l’entreprise.

### Conditions préalables

- Le périphérique est connecté à un réseau.
- L’application Hub de commentaires est disponible sur l’ordinateur de bureau de l’utilisateur et permet de télécharger des fichiers sur le Cloud Microsoft.

### Emplacements, accès et rétention des données

En acceptant les conditions d’utilisation du Hub de commentaires, l’utilisateur est explicitement autorisé à utiliser le stockage et l’utilisation des données (tel qu’il est défini par ce contrat).

Le hub de commentaires fournit deux emplacements pour l’utilisateur dans le stockage des informations de diagnostic:

- **Le Cloud Microsoft**. Les données que l’utilisateur charge à l’aide de l’application Hub de commentaires sont stockées en fonction du nombre de jours conformément à la configuration requise pour la confidentialité de nouvelle génération. Les employés Microsoft peuvent utiliser une visionneuse compatible NGP pour accéder aux informations au cours de cette période.
   > [!NOTE]  
   > Ces exigences s’appliquent aux données de toutes les catégories du Hub de commentaires.

- **Appareil HoloLens**. Lors de l’archivage d’un rapport dans le hub de commentaires, l’utilisateur peut sélectionner **enregistrer une copie locale de diagnostics et de pièces jointes créées lors de l’apport de commentaires**. Si l’utilisateur sélectionne cette option, le hub de commentaires stocke une copie des informations de diagnostic sur le périphérique HoloLens. Ces informations sont accessibles à l’utilisateur (ou quiconque utilise ce compte pour se connecter à HoloLens). Pour supprimer ces informations, un utilisateur doit disposer d’autorisations de **propriétaire d’appareil** ou d' **administrateur** sur l’appareil. Un utilisateur disposant des autorisations appropriées peut se connecter au hub de commentaires, sélectionner **Settings**  >  les**journaux d’affichage**des paramètres et supprimer les informations.

## Utilitaire de dépannage des paramètres

Un utilisateur HoloLens peut utiliser l’application paramètres sur l’appareil pour résoudre les problèmes et collecter des informations de diagnostic. Pour cela, procédez comme suit:

1. Ouvrez l’application paramètres, puis sélectionnez **mettre à jour &**  >  page**résolution des problèmes** de sécurité.
1. Sélectionnez la zone appropriée, puis cliquez sur **Démarrer**.
1. Reproduisez le problème.
1. Après avoir reproduire le problème, revenez aux paramètres, puis sélectionnez **arrêter**.

### Conditions préalables

- L’application paramètres est installée sur l’appareil et est disponible pour l’utilisateur.

### Emplacements, accès et rétention des données

Dans la mesure où l’utilisateur démarre la collection de données, l’utilisateur est implicitement transféré pour le stockage des informations de diagnostic. Seul l’utilisateur, ou quiconque avec lequel l’utilisateur partage les données, peut accéder aux données.

Les informations de diagnostic sont stockées sur l’appareil. Si l’appareil est connecté à l’ordinateur de l’utilisateur, les informations résident également sur l’ordinateur dans le fichier suivant:

> Ce PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> Dans ce nom et chemin d’accès \<*HoloLens device name*> de fichier, représente le nom de l’appareil HoloLens et \<*ddmmyyhhmmss*> représente la date et l’heure auxquelles le fichier a été créé.

Les informations de diagnostic restent dans ces emplacements tant que l’utilisateur ne les supprime pas.

## Fournisseur de services de configuration DiagnosticLog

Dans un environnement de gestion des périphériques mobiles (GPM), l’administrateur informatique peut utiliser le [fournisseur de services de configuration (CSP) DiagnosticLog](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) pour configurer les paramètres de diagnostic sur les appareils HoloLens inscrits. L’administrateur informatique peut configurer ces paramètres pour collecter les journaux de périphériques inscrits.

### Conditions préalables

- Le périphérique est connecté à un réseau.
- L’appareil est inscrit dans un environnement MDM qui prend en charge le fournisseur de services de DiagnosticLog.

### Emplacements, accès et rétention des données

Dans la mesure où l’appareil fait partie de l’environnement géré, l’utilisateur passe implicitement à l’accès administratif aux informations de diagnostic.

L’administrateur informatique utilise le fournisseur de services de DiagnosticLog pour configurer les stratégies de stockage, de rétention et d’accès aux données, y compris les politiques qui gouvernent les éléments suivants:

- Infrastructure cloud qui stocke les informations de diagnostic.
- Durée de rétention des informations de diagnostic.
- Autorisations qui contrôlent l’accès aux informations de diagnostic.


