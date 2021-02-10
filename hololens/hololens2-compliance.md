---
title: Conformité holoLens 2 et R GDPR
description: Documentation R GDPR
keywords: HoloLens, R GDPR, confidentialité, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324870"
---
# Déclaration de confidentialité HoloLens 2

L’un des principaux éléments du R GDPR est la « protection des données par conception ». Ce concept s’applique particulièrement aux appareils mobiles, comme HoloLens 2, en raison de leur portabilité, de leurs connexions Internet illimitées et de leurs canaux de communication ouverts. Par conséquent, la sécurité de HoloLens 2 a été repensée pour fournir une protection avancée et innovantes de la sécurité et de la confidentialité, de bout en bout, en incorporant l’approche de Microsoft en matière de confidentialité et de réglementations R [GDPR.](https://privacy.microsoft.com/) [](https://docs.microsoft.com/hololens/security-architecture)

 >[!NOTE]
> Ce document ne s’applique pas à HoloLens (1ère génération).

## Vue d’ensemble de la confidentialité

HoloLens 2 est un ordinateur Windows autonome, exécutant Windows Holographique, qui exécute des applications et des solutions dans un environnement de réalité mixte immersif. Il peut être utilisé comme appareil hors connexion sécurisé ou déployé en tant qu’appareil [géré](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) au sein de votre organisation. Consultez les liens suivants pour comprendre comment HoloLens 2 et Microsoft utilisent et protègent vos données :
1. [Déclaration de confidentialité Microsoft - HoloLens](https://privacy.microsoft.com/privacystatement) : développez la **section** Entreprise et développeur dans le menu de navigation de gauche et sélectionnez Les logiciels et appliances d’entreprise **et de développement.** Go to the **HoloLens** section.
2.  [Windows 10 et vos services en ligne](https://privacy.microsoft.com/windows10privacy)
3.  [Guide Windows 10 et conformité avec la politique de confidentialité](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Confidentialité et données personnelles dans Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## Sécurité réseau
Dans le cadre des [scénarios](https://docs.microsoft.com/hololens/common-scenarios)de déploiement courants HoloLens 2, vos données seront protégées par la conformité de niveau mondial [d’Azure,](https://docs.microsoft.com/azure/compliance/) ainsi que par l’intégration de normes juridiques/réglementaires. Si vous débutez avec Azure AD et Dynamics 365 Remote Assist, référencez la liste de vérification de préparation sur la responsabilité Azure et [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)pour le R GDPR.

En outre, Windows Defender pare-feu fournit des fonctionnalités essentielles pour sécuriser la connectivité des appareils. Avec HoloLens2, le pare-feu est toujours activé et il n’y a aucun moyen de le désactiver par programme ou par le biais de l’interface utilisateur. Lorsque HoloLens 2 est déployé en tant qu’appareil géré à l’aide [d’Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)davantage de fonctionnalités de conformité sont disponibles avec l’intégration du point de terminaison avec [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) en tant que solution de défense contre les menaces mobiles. 

En savoir plus sur la sécurité et [l’architecture](https://docs.microsoft.com/hololens/security-architecture)de HoloLens 2.

## Sécurité du système d’exploitation
Les mises à jour sont réalisées automatiquement (par défaut) afin que votre HoloLens 2 soit toujours à jour avec la dernière version de Windows Holographic et toutes les applications installées. Consultez les informations suivantes pour en savoir plus sur la conception sécurisée de notre système d’exploitation :
1. [Séparation et isolation d’état](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Système d’exploitation sans administrateur](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitation de l’utilisation d’un mot de passe](https://docs.microsoft.com/hololens/security-limiting-password-use)

## Sécurité physique
HoloLens 2 dispose d’une mémoire flash protégée par le [chiffrement BitLocker.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Votre appareil et ses données locales peuvent être flashés hors connexion à l’aide de [l’Outil](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) de récupération avancée ou nettoyés à distance via la gestion des périphériques multi-appareils s’ils ont été déployés en tant qu’appareil géré.

## Protection des données
Les mises à jour Windows sont automatiquement exécutés (par défaut) et l’intégration [Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protège les données circulant entre lui-même et le cloud. 

Lors du déploiement de HoloLens 2 sur des clients externes, [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garantit que les données et ressources sensibles de votre entreprise sont à la fois distinctes et sécurisées. 

Le partage des données de diagnostic avec Microsoft peut être configuré manuellement par mdM ou par l’utilisateur pendant la OOBE. Deux options s’offrent à vous : les données de diagnostic facultatives et les données de diagnostic requises. Si votre paramètre de diagnostic d’origine doit être modifié ultérieurement à des fins de dépannage, il peut être modifié par l’utilisateur dans **Paramètres -> Confidentialité -> Diagnostics &** Commentaires ou administrateur informatique (MDM) s’il s’agit d’un appareil géré. En savoir plus [sur les diagnostics, les commentaires et la confidentialité dans Windows 10.](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> Les journaux de diagnostic des appareils contiennent des informations d’identification personnelle (PII), telles que les processus ou applications que l’utilisateur démarre pendant les opérations classiques. Lorsque plusieurs utilisateurs partagent un appareil HoloLens (par exemple, les utilisateurs se connectent au même appareil à l’aide de différents comptes Microsoft Azure Active Directory (Azure AD), les journaux de diagnostic peuvent contenir des informations piI qui s’appliquent à plusieurs utilisateurs.

 

Il existe [plusieurs méthodes de collecte et stratégies](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) de rétention des données pour collecter des données de diagnostic à partir de HoloLens 2.  Pour plus d’informations sur la façon dont Microsoft collecte et utilise les données de diagnostic, voir Déclaration de confidentialité [Microsoft - Diagnostics](https://privacy.microsoft.com/privacystatement) - Développez **Windows** dans le menu de navigation de gauche et sélectionnez **Diagnostics.** Go to the **Diagnostics** section.
