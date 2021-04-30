---
title: Conformité et RGPD HoloLens 2
description: Documentation RGPD
keywords: HoloLens, RGPD, confidentialité, PII
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308988"
---
# <a name="hololens-2-privacy-statement"></a>Déclaration de confidentialité HoloLens 2

L’un des principaux éléments du RGPD est « protection des données par conception ». Ce concept s’applique particulièrement aux périphériques mobiles, comme le HoloLens 2, en raison de leur portabilité, de connexions Internet illimitées et de canaux de communication ouverts. Par conséquent, la [sécurité](https://docs.microsoft.com/hololens/security-architecture) de HoloLens 2 a été repensée pour fournir une protection avancée et innovante de la sécurité et de la confidentialité, de bout en bout, incorporant à la fois l’approche de Microsoft en [matière de confidentialité et de RGPD](https://privacy.microsoft.com/).

 >[!NOTE]
> Ce document ne s’applique pas à HoloLens (1ère génération).

## <a name="privacy-overview"></a>Présentation de la confidentialité

HoloLens 2 est un ordinateur Windows autonome exécutant Windows holographique, qui exécute des applications et des solutions dans un environnement de réalité mixte immersif. Il peut être utilisé comme périphérique hors connexion sécurisé ou déployé en tant qu' [appareil géré](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) au sein de votre organisation. Consultez les liens suivants pour comprendre comment HoloLens 2 et Microsoft utilisent et protègent vos données :
1. [Déclaration de confidentialité Microsoft-HoloLens](https://privacy.microsoft.com/privacystatement) : développez la section **Enterprise et Developer** dans le menu de navigation de gauche, puis sélectionnez **Enterprise and Developer Software and Appliances**. Accédez à la section **HoloLens** .
2.  [Windows 10 et votre services en ligne](https://privacy.microsoft.com/windows10privacy)
3.  [Guide de conformité de la confidentialité Windows 10 &](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Confidentialité et données personnelles dans Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Sécurité réseau
À la suite des [scénarios de déploiement courants](https://docs.microsoft.com/hololens/common-scenarios)HoloLens 2, vos données sont protégées par la [conformité mondiale d’Azure](https://docs.microsoft.com/azure/compliance/) , ainsi que par l’intégration des normes légales/réglementaires. Si vous débutez avec Azure AD et Dynamics 365 à distance, consultez la [liste de contrôle Azure et dynamics 365 Accountability Readiness pour RGPD](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics).

En outre, le pare-feu Windows Defender offre des fonctionnalités critiques pour sécuriser la connectivité des appareils. Avec HoloLens 2, le pare-feu est toujours activé et il n’existe aucun moyen de le désactiver par programmation ou par le biais de l’interface utilisateur. Lorsque HoloLens 2 est déployé en tant qu’appareil géré à l’aide d' [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started), davantage de fonctionnalités de conformité sont disponibles avec l’intégration pour [Endpoint avec Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) en tant que solution de protection contre les menaces mobiles. 

En savoir plus sur la [sécurité et l’architecture](https://docs.microsoft.com/hololens/security-architecture)HoloLens 2.

## <a name="os-security"></a>Sécurité du système d’exploitation
Les mises à jour sont effectuées automatiquement (par défaut) afin que votre HoloLens 2 soit toujours à jour avec la dernière version de Windows holographique et toutes les applications installées. Pour en savoir plus sur la façon dont notre système d’exploitation est conçu en toute sécurité, consultez les rubriques suivantes :
1. [Séparation et isolation d’État](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Système d’exploitation sans administrateur](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitation de l’utilisation du mot de passe](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Sécurité physique
HoloLens 2 a une mémoire flash qui est protégée par le [chiffrement BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection). Votre appareil et ses données locales peuvent être mis en mode hors connexion à l’aide de l' [Assistant de récupération avancé](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou être réinitialisés à distance via MDM s’il a été déployé en tant qu’appareil géré.

## <a name="data-protection"></a>Protection des données
Les mises à jour Windows sont exécutées automatiquement (par défaut) et [Azure Integration](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protège les données circulant entre elles-mêmes et le Cloud. 

Lors du déploiement de HoloLens 2 vers des clients externes, l' [assistance à distance Dynamics 365](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garantit que vos données et ressources d’entreprise sensibles sont à la fois distinctes et sécurisées. 

Le partage des données de diagnostic avec Microsoft peut être configuré manuellement par MDM ou par l’utilisateur lors de l’OOBE. Deux options s’offrent à vous : les données de diagnostic facultatives et les données de diagnostic requises. Si votre paramètre de diagnostic d’origine doit être modifié ultérieurement à des fins de résolution des problèmes, il peut être modifié par l’utilisateur dans **paramètres-> la confidentialité-> diagnostics & les commentaires** ou l’administrateur informatique (MDM) si est un appareil géré. En savoir plus sur [les Diagnostics, les commentaires et la confidentialité dans Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Les journaux de diagnostic des appareils contiennent des informations d’identification personnelle (PII), telles que les processus ou les applications que l’utilisateur démarre pendant les opérations courantes. Quand plusieurs utilisateurs partagent un appareil HoloLens (par exemple, les utilisateurs se connectent au même appareil à l’aide de différents comptes de Microsoft Azure Active Directory (Azure AD)), les journaux de diagnostic peuvent contenir des informations personnelles qui s’appliquent à plusieurs utilisateurs.

 

Il existe [plusieurs méthodes de collecte et stratégies de rétention des données](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) pour collecter les données de diagnostic à partir de HoloLens 2.  Pour plus d’informations sur la façon dont Microsoft recueille et utilise les données de diagnostic, consultez [déclaration de confidentialité Microsoft-Diagnostics](https://privacy.microsoft.com/privacystatement) -développez **fenêtres** dans le menu de navigation de gauche et sélectionnez **Diagnostics**. Accédez à la section **Diagnostics** .
