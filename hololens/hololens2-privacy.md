---
title: HoloLens 2 Confidentialité et protection des données
description: Documentation sur la confidentialité
keywords: HoloLens, rgpd, confidentialité, PII, protection des données
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: 548550f309010fa95f674a7ff688166a31cf1963
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2021
ms.locfileid: "122336736"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 Confidentialité et protection des données

L’un des principaux éléments du RGPD est « protection des données par conception ». ce concept s’applique particulièrement aux périphériques mobiles, comme le HoloLens 2, en raison de leur portabilité, de connexions internet illimitées et de canaux de communication ouverts. par conséquent, la [sécurité](/hololens/security-architecture) de l’HoloLens 2 a été repensée pour fournir une protection avancée et innovante de la sécurité et de la confidentialité, de bout en bout, incorporant à la fois l’approche de Microsoft en [matière de confidentialité et de rgpd](https://privacy.microsoft.com/).

 >[!NOTE]
> ce document ne s’applique pas aux HoloLens (1er génération).

## <a name="privacy-overview"></a>Présentation de la confidentialité

HoloLens 2 est un ordinateur de Windows autonome, exécuté Windows holographique, qui exécute des applications et des solutions dans un environnement de réalité mixte immersif. Il peut être utilisé comme périphérique hors connexion sécurisé ou déployé en tant qu' [appareil géré](/mem/intune/fundamentals/windows-holographic-for-business) au sein de votre organisation. pour comprendre comment les HoloLens 2 et Microsoft utilisent et protègent vos données, consultez les liens suivants :

1. [déclaration de confidentialité Microsoft-HoloLens](https://privacy.microsoft.com/privacystatement) : développez la section **Enterprise et développeur** dans le menu de navigation de gauche, puis sélectionnez **Enterprise et logiciels de développement et applications**. accédez à la section **HoloLens** .
2. [Windows 10 et votre services en ligne](https://privacy.microsoft.com/windows10privacy)
3. [Guide de conformité de la confidentialité de Windows 10 &](/windows/privacy/windows-10-and-privacy-compliance)
4. [Confidentialité et données personnelles dans Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Sécurité réseau
à la suite de la HoloLens 2 [scénarios de déploiement courants](/hololens/common-scenarios), vos données sont protégées par la [conformité de classe mondiale d’Azure](/azure/compliance/) , ainsi que par l’intégration de normes légales/réglementaires. si vous débutez avec Azure AD et Dynamics 365 Remote Assist, reportez-vous à la [liste de contrôle Azure et Dynamics 365 accountability readiness readiness pour rgpd](/compliance/regulatory/gdpr-arc-azure-dynamics).

en outre, Windows Defender pare-feu offre des fonctionnalités critiques pour sécuriser la connectivité des appareils. Avec HoloLens 2, le pare-feu est toujours activé et il n’y a aucun moyen de le désactiver par programmation ou via l’interface utilisateur. lorsque le HoloLens 2 est déployé en tant qu’appareil géré à l’aide d' [Intune](/mem/intune/protect/device-compliance-get-started), davantage de fonctionnalités de conformité sont disponibles avec l’intégration pour [Endpoint avec Microsoft Intune](/mem/intune/protect/advanced-threat-protection) en tant que solution Mobile Threat Defense.

en savoir plus sur la [sécurité et l’architecture](/hololens/security-architecture)de HoloLens 2.

## <a name="os-security"></a>Sécurité du système d’exploitation
les mises à jour sont effectuées automatiquement (par défaut) afin que votre HoloLens 2 soit toujours à jour avec la dernière version de Windows holographique et toutes les applications installées. Pour en savoir plus sur la façon dont notre système d’exploitation est conçu en toute sécurité, consultez les rubriques suivantes :

1. [Séparation et isolation d’état](/hololens/security-state-separation-isolation)
1. [Système d’exploitation sans administrateur](/hololens/security-adminless-os)
1. [Limitation de l’utilisation d’un mot de passe](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Sécurité physique
HoloLens 2 dispose d’une mémoire flash qui est protégée par le [chiffrement BitLocker](/hololens/security-encryption-data-protection). Votre appareil et ses données locales peuvent être mis en mode hors connexion à l’aide de l' [Assistant de récupération avancé](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou être réinitialisés à distance via MDM s’il a été déployé en tant qu’appareil géré.

## <a name="data-protection"></a>Protection des données
Windows mises à jour sont exécutées automatiquement (par défaut) et [Azure integration](/hololens/security-encryption-data-protection#Azure-integration) protège les données circulant entre elles-mêmes et le cloud.

lors du déploiement de HoloLens 2 vers des clients externes, [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) garantit que vos données et ressources d’entreprise sensibles sont à la fois distinctes et sécurisées.

Le partage des données de diagnostic avec Microsoft peut être configuré manuellement par MDM ou par l’utilisateur lors de l’OOBE. Deux options s’offrent à vous : les données de diagnostic facultatives et les données de diagnostic requises. si votre paramètre de diagnostic d’origine doit être modifié ultérieurement à des fins de résolution des problèmes, il peut être modifié par l’utilisateur dans **Paramètres > Privacy-> diagnostics & les commentaires** ou l’administrateur informatique (MDM) si est un appareil géré. Pour en savoir plus sur [les Diagnostics, les commentaires et la confidentialité](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319), consultez Windows 10.

> [!Important]
> Les journaux de diagnostic des appareils contiennent des informations d’identification personnelle (PII), telles que les processus ou les applications que l’utilisateur démarre pendant les opérations courantes. quand plusieurs utilisateurs partagent un appareil HoloLens (par exemple, les utilisateurs se connectent au même appareil à l’aide de différents comptes Microsoft Azure Active Directory (Azure AD)), les journaux de diagnostic peuvent contenir des informations personnelles qui s’appliquent à plusieurs utilisateurs.

Il existe [plusieurs méthodes de collecte et stratégies de rétention des données](/hololens/hololens-diagnostic-logs) pour collecter les données de diagnostic à partir du HoloLens 2.  pour plus d’informations sur la façon dont microsoft recueille et utilise les données de diagnostic, consultez [déclaration de confidentialité microsoft-diagnostics](https://privacy.microsoft.com/privacystatement) -développez **Windows** dans le menu de navigation de gauche et sélectionnez **diagnostics**. Accédez à la section **Diagnostics** .
