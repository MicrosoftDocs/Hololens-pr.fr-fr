---
title: Microsoft Store pour Entreprises
description: apprenez à utiliser le Microsoft Store pour Entreprises pour publier vos applications de réalité mixte sur votre entreprise.
keywords: Microsoft Store pour Entreprises, msfb, déploiement d’applications, Store
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924316"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store pour Entreprises

le [Microsoft Store pour Entreprises](/microsoft-store/microsoft-store-for-business-overview) est principalement conçu pour les décideurs informatiques et les administrateurs dans les entreprises ou les organisations disposant d’un moyen flexible de rechercher, d’acquérir, de gérer et de distribuer des applications gratuites et payantes dans select markets pour Windows 10 appareils en volume. 

vous pouvez gérer des applications Microsoft Store et des applications métier privées dans un même inventaire, et attribuer et réutiliser des licences en fonction des besoins. vous pouvez également choisir la meilleure méthode de distribution pour votre organisation : attribuer directement des applications à des personnes et des équipes, publier des applications sur des pages privées dans Microsoft Store ou vous connecter à des solutions de gestion pour obtenir davantage d’options.

lorsque Microsoft Store pour Entreprises est utilisé par un utilisateur final, il lance l’application Microsoft Store. Une fois lancé, l’utilisateur est en mesure de sélectionner l’onglet avec le nom de son organisation. les applications qui lui sont disponibles ou ce périphérique sont alors présentées.

> [!Note]
> Microsoft Store pour Entreprises ne télécharge pas automatiquement les applications (push) sur les appareils. toutefois, les applications du Microsoft Store pour Entreprises peuvent être associées à votre serveur de gestion des appareils (MDM) pour cibler et synchroniser des applications sur des appareils.

visitez les pages suivantes pour en savoir plus sur l’utilisation de l’Microsoft Store pour Entreprises :

* [Niveaux d’autorisations utilisés pour l’installation d’applications](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Comment ajouter une application à votre Store pour entreprises](/mem/intune/apps/store-apps-windows)
* [Comment affecter des applications à des groupes d’employés](/mem/intune/apps/windows-store-for-business)

pour associer votre Microsoft Store pour Entreprises, consultez [associer votre Microsoft Store pour Entreprises à Intune](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune).

> [!Tip]
> en savoir plus sur la [distribution d’applications hors connexion](/microsoft-store/distribute-offline-apps) lors de l’utilisation d’applications telles que le compagnon de récupération avancé (ARC) et le concepteur de Configuration Windows (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Utiliser uniquement des applications de magasin privé pour Microsoft Store

- introduit dans [Windows holographique, version 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

La stratégie RequirePrivateStoreOnly a été activée pour HoloLens. cette stratégie permet à l’application Microsoft Store d’être configurée pour afficher uniquement la banque privée configurée pour votre organisation. Limiter l’accès aux seules applications que vous avez mises à disposition.

En savoir plus sur [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Nouvelle tentative intelligente pour les mises à jour d’application

- introduit dans [Windows holographique, version 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

à présent activé pour HoloLens est une nouvelle stratégie qui permet aux administrateurs informatiques de définir une date récurrente ou ponctuelle pour redémarrer les applications dont la mise à jour a échoué parce que l’application est en cours d’utilisation, ce qui permet d’appliquer la mise à jour. Elles peuvent être définies en fonction de différents déclencheurs, tels qu’une heure planifiée ou une connexion. Pour en savoir plus sur l’utilisation de cette stratégie, consultez [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).