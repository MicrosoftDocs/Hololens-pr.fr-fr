---
title: Collecter et utiliser des informations de diagnostic sur des appareils HoloLens
description: découvrez comment collecter, utiliser et conserver des informations de diagnostic à partir d’appareils HoloLens.
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
ms.openlocfilehash: e977d0d42831760749bb5c6c469d2482e2ca72e7
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833520"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Collecter et utiliser des informations de diagnostic sur des appareils HoloLens

HoloLens les utilisateurs et les administrateurs peuvent choisir parmi quatre méthodes différentes pour collecter des informations de diagnostic à partir de HoloLens :

- Application Hub de commentaires
- Fournisseur CSP DiagnosticLog
- Application Paramètres
- Diagnostics hors connexion

> [!IMPORTANT]  
> Les journaux de diagnostic des appareils contiennent des informations d’identification personnelle (PII), telles que les processus ou les applications que l’utilisateur démarre pendant les opérations courantes. quand plusieurs utilisateurs partagent un appareil HoloLens (par exemple, les utilisateurs se connectent au même appareil à l’aide de différents comptes Microsoft Azure Active Directory (Azure AD)), les journaux de diagnostic peuvent contenir des informations personnelles qui s’appliquent à plusieurs utilisateurs. Pour plus d’informations, consultez la [déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).

Le tableau suivant compare différentes méthodes de collection. Les noms de méthode sont liés à des informations plus détaillées dans les sections qui suivent le tableau.

|Méthode |Prérequis |Emplacements des données |Accès aux données et utilisation |Conservation des données |
| --- | --- | --- | --- | --- |
|[Hub de commentaires](#feedback-hub) |Connexion réseau et Internet<br /><br />Application Hub de commentaires<br /><br />Autorisation de charger des fichiers dans le Cloud Microsoft |Cloud Microsoft<br /><br />appareil HoloLens (facultatif) |L’utilisateur demande de l’aide, accepte les conditions d’utilisation et charge les données<br /><br />Les employés de Microsoft affichent les données en fonction des conditions d’utilisation. |Les données dans le Cloud sont conservées pendant la période définie par la confidentialité de nouvelle génération (NGP). Ensuite, les données sont automatiquement supprimées.<br /><br />Les données de l’appareil peuvent être supprimées à tout moment par un utilisateur disposant des autorisations d' **administrateur** ou de propriétaire de l' **appareil** . |
|[Paramètres Résolution des problèmes](#settings-troubleshooter) |Application Paramètres |Appareil HoloLens<br /><br />Ordinateur connecté (facultatif) |L’utilisateur stocke les données, et seul l’utilisateur accède aux données (sauf si l’utilisateur partage spécifiquement les données avec un autre utilisateur). |Les données sont conservées sur l’appareil jusqu’à ce que l’utilisateur les supprime. * |
|[Fournisseur CSP DiagnosticLog](#diagnosticlog-csp) |Connexion réseau<br /><br />Environnement MDM qui prend en charge le CSP DiagnosticLog |L’administrateur configure les emplacements de stockage |Dans l’environnement managé, l’utilisateur accepte implicitement l’accès administrateur aux données.<br /><br />L’administrateur configure les autorisations et les rôles d’accès. | Les données sont conservées dans le stockage cloud et l’administrateur configure la stratégie de rétention. |
|[Diagnostics hors connexion](#offline-diagnostics) |Configuration de l’appareil :<ul><li>Sous tension et connecté à l’ordinateur</li><li>Les boutons d’alimentation et de volume fonctionnent</li></ul> |Appareil HoloLens<br /><br />Ordinateur connecté |L’utilisateur stocke les données, et seul l’utilisateur accède aux données (sauf si l’utilisateur partage spécifiquement les données avec un autre utilisateur). |Les données sont conservées sur l’appareil jusqu’à ce que l’utilisateur le supprime. |

* L’utilisateur final est chargé de partager les journaux de manière responsable avec une autre personne. Ces fichiers sont principalement utiles pour contacter le service clientèle et le support technique.  

## <a name="feedback-hub"></a>Hub de commentaires

un utilisateur HoloLens peut utiliser l’application de bureau Microsoft Feedback Hub pour envoyer des informations de diagnostic à Support Microsoft. Pour plus d’informations et pour obtenir des instructions, consultez [nous faire part de vos commentaires](hololens-feedback.md).  

> [!NOTE]  
> **Utilisateurs commerciaux ou d’entreprise :** si vous utilisez l’application Hub de commentaires pour signaler un problème lié à MDM, à la configuration ou à tout autre aspect de la gestion des périphériques, remplacez la catégorie d’application par **Enterprise**  >  **catégorie d’appareils** de gestion.

>[!IMPORTANT]
> Pour fournir les meilleures données possibles pour la résolution des problèmes, nous vous recommandons vivement de définir la télémétrie de votre appareil sur **facultatif**. vous pouvez définir cette valeur pendant l’expérience OOBE (Out-of-box-experience) ou à l’aide de l’application **Paramètres** . pour ce faire, à l’aide de Paramètres, sélectionnez **Start > Paramètres > Privacy > application diagnostics > sur**.

### <a name="prerequisites"></a>Prérequis

- L’appareil est connecté à un réseau.
- L’application Hub de commentaires est disponible sur l’ordinateur de bureau de l’utilisateur, et l’utilisateur peut charger des fichiers dans le Cloud Microsoft.

### <a name="data-locations-access-and-retention"></a>Emplacements, accès et rétention des données

En acceptant les conditions d’utilisation du Hub de commentaires, l’utilisateur accepte explicitement le stockage et l’utilisation des données (comme défini par cet accord).

Le hub de commentaires fournit deux emplacements permettant à l’utilisateur de stocker les informations de diagnostic :

- **Le Cloud Microsoft**. Les données que l’utilisateur charge à l’aide de l’application Hub de commentaires sont stockées pendant le nombre de jours qui est compatible avec les exigences de la confidentialité de la prochaine génération (NGP). Les employés de Microsoft peuvent utiliser une visionneuse compatible NGP pour accéder aux informations pendant cette période.

   > [!NOTE]  
   > Ces exigences s’appliquent aux données de toutes les catégories de hub de commentaires.

- **appareil HoloLens**. Lors du classement d’un rapport dans le hub de commentaires, l’utilisateur peut sélectionner **enregistrer une copie locale des diagnostics et pièces jointes créés lors** de l’envoi de commentaires. si l’utilisateur sélectionne cette option, le Hub de commentaires stocke une copie des informations de diagnostic sur l’appareil HoloLens. Ces informations restent accessibles à l’utilisateur (ou à toute personne qui utilise ce compte pour se connecter à HoloLens). Pour supprimer ces informations, un utilisateur doit disposer des autorisations d' **administrateur** ou de **propriétaire** de l’appareil sur l’appareil. un utilisateur disposant des autorisations appropriées peut se connecter au Hub de commentaires, sélectionner **Paramètres**  >  **afficher les journaux de diagnostic** et supprimer les informations.

## <a name="settings-troubleshooter"></a>Paramètres Résolution des problèmes

un utilisateur HoloLens peut utiliser l’application **Paramètres** sur l’appareil pour résoudre les problèmes et collecter des informations de diagnostic. Pour ce faire, procédez comme suit :

1. ouvrez l’application Paramètres et sélectionnez **mettre à jour &**  >  page **résolution des problèmes** de sécurité.
1. Sélectionnez la zone appropriée, puis cliquez sur **Démarrer**.
1. Reproduisez le problème.
1. une fois que vous avez reproduit le problème, revenez à Paramètres puis sélectionnez **arrêter**.

un utilisateur peut également configurer le comportement des diagnostics de secours à partir de l’application **Paramètres** . Accédez à **confidentialité-> la page de résolution des problèmes** pour configurer ce paramètre.
> [!NOTE]
> Si une stratégie MDM est configurée pour l’appareil, l’utilisateur ne sera pas en mesure de remplacer ce comportement.

### <a name="os-update-troubleshooter"></a>Dépannage des mises à jour du système d’exploitation

sur les builds [Windows holographique, version 21H1 et versions](hololens-release-notes.md#windows-holographic-version-21h1) ultérieures :
- en plus des dépannages précédents au sein de l’application Paramètres, un nouvel utilitaire de résolution des problèmes a été ajouté avec l’ajout de la nouvelle application Paramètres pour les mises à jour du système d’exploitation. accédez à **Paramètres-> Update & Security-> Troubleshoot-> Windows Update** et sélectionnez **Start**. Cela vous permet de collecter des traces tout en reproduisant votre problème avec les mises à jour du système d’exploitation afin d’améliorer la résolution des problèmes avec votre service informatique ou votre support technique.

### <a name="prerequisites"></a>Prérequis

- l’application **Paramètres** est installée sur l’appareil et est disponible pour l’utilisateur.

### <a name="data-locations-access-and-retention"></a>Emplacements, accès et rétention des données

Étant donné que l’utilisateur démarre la collecte de données, l’utilisateur accepte implicitement le stockage des informations de diagnostic. Seul l’utilisateur, ou toute personne avec laquelle l’utilisateur partage les données, peut accéder aux données.

Les informations de diagnostic sont stockées sur l’appareil. Si l’appareil est connecté à l’ordinateur de l’utilisateur, les informations se trouvent également sur l’ordinateur dans le fichier suivant :

> cet ordinateur \\ \<*HoloLens device name*> \\ interne Stockage \\ Documents \\ Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> dans ce chemin d’accès et ce nom de fichier, \<*HoloLens device name*> représente le nom du HoloLens périphérique et \<*ddmmyyhhmmss*> représente la date et l’heure de création du fichier.

Les informations de diagnostic sont conservées dans ces emplacements jusqu’à ce que l’utilisateur les supprime.

### <a name="view-diagnostic-report"></a>Afficher le rapport de diagnostic

pour afficher les diagnostics MDM sur HoloLens 2, sélectionnez votre icône WiFi, accédez à **Paramètres**  ->  **comptes**  >  **accès professionnel ou scolaire** , puis sélectionnez **exporter les journaux de gestion**. HoloLens envoie les fichiers journaux à votre compte et affiche leur emplacement sur votre ordinateur de bureau.

## <a name="diagnosticlog-csp"></a>Fournisseur CSP DiagnosticLog

dans un environnement de gestion des appareils mobiles (MDM), l’administrateur informatique peut utiliser le [fournisseur de services de configuration (CSP) DiagnosticLog](/windows/client-management/mdm/diagnosticlog-csp) pour configurer les paramètres de diagnostic sur les appareils inscrits HoloLens. L’administrateur informatique peut configurer ces paramètres pour collecter des journaux à partir d’appareils inscrits.

En savoir plus :
- [Collecter les diagnostics à partir d’un appareil Windows](/mem/intune/remote-actions/collect-diagnostics)
- [version préliminaire publique d’Intune-diagnostics de l’appareil Windows 10](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Prérequis

- L’appareil est connecté à un réseau.
- L’appareil est inscrit dans un environnement MDM qui prend en charge le CSP DiagnosticLog.

### <a name="data-locations-access-and-retention"></a>Emplacements, accès et rétention des données

Étant donné que l’appareil fait partie de l’environnement géré, l’utilisateur accepte implicitement l’accès administratif aux informations de diagnostic.

L’administrateur informatique utilise le CSP DiagnosticLog pour configurer les stratégies de stockage, de rétention et d’accès aux données, y compris les stratégies qui régissent les éléments suivants :

- L’infrastructure cloud qui stocke les informations de diagnostic.
- Période de rétention pour les informations de diagnostic.
- Autorisations qui contrôlent l’accès aux informations de diagnostic.

## <a name="offline-diagnostics"></a>Diagnostics hors connexion

dans les situations où l’appareil n’est pas en mesure de collecter des diagnostics via le Hub de commentaires ou l’utilitaire de résolution des problèmes de Paramètres, vous pouvez collecter les diagnostics manuellement. Cela est nécessaire lorsque l’appareil ne peut pas se connecter à Wi-Fi ou que vous ne pouvez pas accéder à d’autres méthodes mentionnées ci-dessus. Les diagnostics collectent les vidages sur incident et les journaux de l’appareil qui aident un ingénieur du support technique Microsoft à isoler les problèmes.

Cela fonctionne lorsque l’appareil s’affiche dans l’Explorateur de fichiers après l’avoir connecté à un PC via un câble USB.

> [!NOTE]
> La gestion et la génération des diagnostics hors connexion sont contrôlées différemment en fonction de la version de votre système d’exploitation. Auparavant, elle était contrôlée par le paramètre de télémétrie, mais elle est maintenant directement contrôlée via la stratégie MDM. S’il est désactivé via l’un ou l’autre paramètre ou la stratégie MDM, les journaux de diagnostic ne peuvent pas être collectés à l’aide de ce mécanisme.

comportement avant [Windows holographique, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - Les diagnostics hors connexion sont activés uniquement lorsque l’utilisateur passe par la valeur de la stratégie OOBE ou [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) définie sur Full (la valeur par défaut de base est définie sur HoloLens). 
- pour désactiver les diagnostics hors connexion, accédez à **Paramètres page > confidentialité** de l’application et sélectionnez de **base** dans **données de Diagnostic**. Sur les builds où les diagnostics hors connexion dépendent du paramètre de télémétrie, il n’a d’incidence que sur la collecte ou non des journaux. Elle n’a aucun impact sur les fichiers qui sont collectés.
- Si l’appareil est verrouillé, les journaux ne s’affichent pas.

sur les builds [Windows holographique, version 20H2 et versions](hololens-release-notes.md#windows-holographic-version-20h2) ultérieures :
- Lorsque les diagnostics de secours sont activés, ils sont contrôlés par une stratégie MDM spécifique avec le paramètre correspondant [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Si l’appareil est verrouillé, les journaux ne s’affichent pas.

Regardez cette vidéo pour en savoir plus.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Pour collecter les Diagnostics, procédez comme suit :

1.  Connecter l’appareil à l’aide d’un câble USB sur votre PC.

2.  dans l’explorateur de fichiers sur votre pc, accédez à **« This PC \<hololens-device> \Internal Stockage »**.

3.  si le dossier **interne Stockage** n’apparaît pas, l’appareil attend qu’un utilisateur se connecte. Connectez-vous ou mettez hors tension l’appareil en maintenant enfoncé le bouton d’alimentation pendant 10 secondes.

4.  Appuyez sur le bouton **d’alimentation** et relâchez-le immédiatement.

5.  Attendez une minute que l’appareil prépare les archives zip. (Un fichier temporaire nommé HololensDiagnostics. Temp peut devenir visible pendant que l’appareil génère les archives zip. N’accédez pas à ce fichier ou ne l’enregistrez pas. Une fois le processus terminé, il est remplacé par les archives zip.)

6.  Actualisez l’Explorateur de fichiers et accédez au dossier **« \Documents »** .

7.  Copiez les fichiers ZIP de diagnostics et partagez-les avec l’équipe du support technique Microsoft.

    > [!NOTE]
    > Certains fichiers ZIP de diagnostic peuvent contenir des PII.
