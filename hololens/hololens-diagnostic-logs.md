---
title: Collecter et utiliser des informations de diagnostic sur les appareils HoloLens
description: Découvrez comment collecter, utiliser et conserver des informations de diagnostic à partir d’appareils HoloLens.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
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
ms.openlocfilehash: 206a31476820e8722b1b72fbd501345a089379b1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283225"
---
# Collecter et utiliser des informations de diagnostic sur les appareils HoloLens

Les utilisateurs et les administrateurs HoloLens peuvent choisir parmi quatre méthodes différentes pour collecter des informations de diagnostic à partir de HoloLens :

- Application Hub de commentaires
- Fournisseur de services de configuration DiagnosticLog
- Application Paramètres

> [!IMPORTANT]  
> Les journaux de diagnostic des appareils contiennent des informations d’identification personnelle (PII), telles que les processus ou applications que l’utilisateur démarre pendant les opérations classiques. Lorsque plusieurs utilisateurs partagent un appareil HoloLens (par exemple, les utilisateurs se connectent au même appareil à l’aide de différents comptes Microsoft Azure Active Directory (Azure AD), les journaux de diagnostic peuvent contenir des informations piI qui s’appliquent à plusieurs utilisateurs. Pour plus d’informations, voir [déclaration de confidentialité Microsoft.](https://privacy.microsoft.com/privacystatement)

Le tableau suivant compare les trois méthodes de collection. Les noms des méthodes sont des liens vers des informations plus détaillées dans les sections qui suivent le tableau.

|Méthode |Conditions préalables |Emplacements de données |Accès et utilisation des données |Rétention des données |
| --- | --- | --- | --- | --- |
|[Hub de commentaires](#feedback-hub) |Connexion réseau et Internet<br /><br />Application Hub de commentaires<br /><br />Autorisation de charger des fichiers dans le cloud Microsoft |Cloud Microsoft<br /><br />Appareil HoloLens (facultatif) |L’utilisateur demande de l’aide, accepte les conditions d’utilisation et charge les données<br /><br />Les employés de Microsoft visualisent les données de façon cohérente avec les conditions d’utilisation |Les données dans le cloud sont conservées pendant la période définie par la politique de confidentialité de nouvelle génération (NGP). Ensuite, les données sont supprimées automatiquement.<br /><br />Les données sur l’appareil peuvent être supprimées **** à tout moment par un utilisateur qui dispose d’autorisations d’administrateur ou de propriétaire **** d’appareil. |
|[Résolution des problèmes des paramètres](#settings-troubleshooter) |Application Paramètres |AppareilHoloLens<br /><br />Ordinateur connecté (facultatif) |L’utilisateur stocke les données et seul l’utilisateur accède aux données (sauf si l’utilisateur partage spécifiquement les données avec un autre utilisateur). |Les données sont conservées jusqu’à ce que l’utilisateur les supprime.* |
|[Fournisseur de services de configuration DiagnosticLog](#diagnosticlog-csp) |Connexion réseau<br /><br />Environnement de gestion des appareils de gestion des appareils qui prend en charge le programme CSP DiagnosticLog |L’administrateur configure les emplacements de stockage |Dans l’environnement géré, l’utilisateur consent implicitement à l’accès administrateur aux données.<br /><br />L’administrateur configure les rôles d’accès et les autorisations. | L’administrateur configure la stratégie de rétention. |
|[Diagnostics hors connexion](#offline-diagnostics) |Configuration de l’appareil :<ul><li>Sous tension et connecté à l’ordinateur</li><li>Boutons d’alimentation et de volume fonctionnant</li></ul> |AppareilHoloLens<br /><br />Ordinateur connecté |L’utilisateur stocke les données et seul l’utilisateur accède aux données (sauf si l’utilisateur partage spécifiquement les données avec un autre utilisateur). |Les données sont conservées jusqu’à ce que l’utilisateur les supprime. | 


-   L’utilisateur final est responsable du partage des journaux de manière responsable avec quelqu’un d’autre. Ces fichiers sont principalement utiles pour contacter le service clientèle et le support technique.  

## Hub de commentaires

Un utilisateur HoloLens peut utiliser l’application de bureau Microsoft Feedback Hub pour envoyer des informations de diagnostic au Support Microsoft. Pour plus d’informations et pour obtenir des instructions complètes, [voir Nous faire part de vos commentaires.](hololens-feedback.md)  

> [!NOTE]  
> **Utilisateurs commerciaux ou d’entreprise :** Si vous utilisez l’application Hub de commentaires pour signaler un problème lié à la gestion des **** périphériques de gestion des appareils, à l’approvisionnement ou à tout autre aspect de gestion des appareils, modifiez la catégorie d’application en catégorie d’appareil de gestion  >  **d’entreprise.**

### Conditions préalables

- L’appareil est connecté à un réseau.
- L’application Hub de commentaires est disponible sur l’ordinateur de bureau de l’utilisateur et l’utilisateur peut télécharger des fichiers dans le cloud Microsoft.

### Emplacements de données, accès et rétention

En acceptant les conditions d’utilisation du Hub de commentaires, l’utilisateur accepte explicitement le stockage et l’utilisation des données (comme défini par ce contrat).

Le Hub de commentaires fournit deux endroits où l’utilisateur peut stocker des informations de diagnostic :

- **Le cloud Microsoft**. Les données téléchargées par l’utilisateur à l’aide de l’application Hub de commentaires sont stockées pendant le nombre de jours qui correspond aux exigences de confidentialité de nouvelle génération (NGP). Les employés de Microsoft peuvent utiliser une visionneuse compatible NGP pour accéder aux informations pendant cette période.
   > [!NOTE]  
   > Ces exigences s’appliquent aux données de toutes les catégories du Hub de commentaires.

- **L’appareil HoloLens**. Lors du classement d’un rapport dans le Hub de commentaires, l’utilisateur peut sélectionner Enregistrer une copie locale des diagnostics et des pièces jointes créés lors de **l’avis.** Si l’utilisateur sélectionne cette option, le Hub de commentaires stocke une copie des informations de diagnostic sur l’appareil HoloLens. Ces informations restent accessibles à l’utilisateur (ou à toute personne qui utilise ce compte pour se connecter à HoloLens). Pour supprimer ces informations, **** un utilisateur **** doit avoir des autorisations de propriétaire d’appareil ou d’administrateur sur l’appareil. Un utilisateur qui dispose des autorisations appropriées peut se connecter au Hub de commentaires, sélectionner l’affichage des **paramètres**des journaux de  >  **diagnostic et**supprimer les informations.

## Résolution des problèmes des paramètres

Un utilisateur HoloLens peut utiliser l’application Paramètres sur l’appareil pour résoudre les problèmes et collecter des informations de diagnostic. Pour ce faire, procédez comme suit:

1. Ouvrez l’application Paramètres et sélectionnez Mettre à **jour & la**page Résolution des problèmes de  >  **sécurité.**
1. Sélectionnez la zone appropriée, puis sélectionnez **Démarrer.**
1. Reproduisez le problème.
1. Après avoir reproduit le problème, revenir aux paramètres, puis sélectionnez **Arrêter.**

### Conditions préalables

- L’application Paramètres est installée sur l’appareil et est disponible pour l’utilisateur.

### Emplacements de données, accès et rétention

Étant donné que l’utilisateur démarre la collecte de données, il consent implicitement au stockage des informations de diagnostic. Seul l’utilisateur, ou toute personne avec laquelle il partage les données, peut accéder aux données.

Les informations de diagnostic sont stockées sur l’appareil. Si l’appareil est connecté à l’ordinateur de l’utilisateur, les informations résident également sur l’ordinateur dans le fichier suivant :

> Ce PC\\ \<*HoloLens device name*> \\Stockage interne\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Dans ce nom et chemin d’accès au fichier, représente le nom de l’appareil HoloLens et représente la date et l’heure de création \<*HoloLens device name*> \<*ddmmyyhhmmss*> du fichier.

Les informations de diagnostic restent à ces emplacements jusqu’à ce que l’utilisateur les supprime.

## Fournisseur de services de configuration DiagnosticLog

Dans un environnement de gestion des périphériques mobiles (MDM), l’administrateur informatique peut utiliser le fournisseur de services de [configuration DiagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) pour configurer les paramètres de diagnostic sur les appareils HoloLens inscrits. L’administrateur informatique peut configurer ces paramètres pour collecter les journaux des appareils inscrits.

### Conditions préalables

- L’appareil est connecté à un réseau.
- L’appareil est inscrit dans un environnement de gestion des périphériques de gestion des périphériques qui prend en charge le CSP DiagnosticLog.

### Emplacements de données, accès et rétention

Étant donné que l’appareil fait partie de l’environnement géré, l’utilisateur consent implicitement à l’accès administratif aux informations de diagnostic.

L’administrateur informatique utilise le CSP DiagnosticLog pour configurer les stratégies de stockage, de rétention et d’accès des données, y compris les stratégies qui régissent les stratégies suivantes :

- Infrastructure cloud qui stocke les informations de diagnostic.
- Période de rétention pour les informations de diagnostic.
- Autorisations qui contrôlent l’accès aux informations de diagnostic.

## Diagnostics hors connexion
Dans les situations où l’appareil n’est pas en mesure de collecter des diagnostics via le Hub de commentaires ou l’outil de résolution des problèmes de paramètres, vous pouvez collecter les diagnostics manuellement. L’un des scénarios où cela est nécessaire est lorsque l’appareil ne peut pas se connecter au Wi-Fi. Les diagnostics collectent les vidages sur incident et les journaux de l’appareil qui aident un ingénieur du support technique Microsoft à isoler les problèmes.

Cela fonctionne lorsque l’appareil s’affiche dans l’Explorateur de fichiers après l’avoir connecté à un PC via un câble USB. 

> [!NOTE]
> La génération et la gestion des diagnostics hors connexion sont contrôlées différemment en fonction de la version de votre système d’exploitation. Auparavant, il était contrôlé par le paramètre de télémétrie, mais il est désormais contrôlé directement via la stratégie. 

Comportement antérieur [à Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - Les diagnostics hors connexion sont activés uniquement lorsque l’utilisateur passe par OOBE ou system\La valeur de stratégie [AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) est définie sur Full (Basic est la valeur par défaut sur HoloLens). 
- Pour désactiver les diagnostics hors connexion, sélectionnez **Paramètres app > confidentialité** et sélectionnez **Données** de diagnostic de **base.** Dans les builds où les diagnostics hors connexion dépendent du paramètre de télémétrie, cela n’a d’impact que sur la collecte ou non de tous les journaux. Cela n’a pas d’impact sur les fichiers collectés.
- Si l’appareil est verrouillé, les journaux n’apparaissent pas.

Sur les builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) et les années suivantes :
- Lorsque les diagnostics de retour sont activés, ils sont contrôlés par une stratégie de gestion des appareils de gestion des appareils de récupération spécifique avec les paramètres [correspondants MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Si l’appareil est verrouillé, les journaux n’apparaissent pas.


Regardez cette vidéo pour en savoir plus. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Pour collecter les diagnostics, suivez les étapes suivantes :
1.  Connectez l’appareil avec un câble USB à votre PC.
2.  Dans l’Explorateur de fichiers de votre PC, accédez à **« Ce PC \<hololens-device> \Stockage interne**».
3.  Si le **dossier Stockage** interne ne s’affiche pas, l’appareil attend qu’un utilisateur se connecte. Connectez-vous ou cyclez l’appareil en maintenant le bouton d’alimentation enfoncé pendant 10 secondes.
4.  Appuyez et relâchez immédiatement les boutons **POWER + VOLUME DOWN** ensemble.
5.  Patientez une minute pour que l’appareil prépare les archives zip. (Un fichier temporaire nommé HololensDiagnostics.temp peut devenir visible pendant que l’appareil génère les archives zip. N’accédez pas à ce fichier ou n’enregistrez pas ce fichier. Une fois le processus terminé, il est remplacé par les archives zip.)
6.  Actualisez l’Explorateur de fichiers et accédez au **dossier « \Documents** ».
7.  Copiez les fichiers ZIP de diagnostic et partagez-les avec l’équipe de support Technique Microsoft.

> [!NOTE]
> Certains fichiers ZIP de diagnostic peuvent contenir des informations d’identification personnelle.



