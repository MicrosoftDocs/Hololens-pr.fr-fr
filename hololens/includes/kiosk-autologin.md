---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859208"
---
# <a name="non-aad-configuration"></a>[Configuration non AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Configuration non AAD

1. Créez un package d’approvisionnement qui :
    1. Configure les paramètres d’exécution/AssignedAccess pour autoriser les comptes de visiteur.
    1. Inscrit éventuellement l’appareil dans MDM (paramètres d’exécution/espace de travail/inscriptions) afin qu’il puisse être géré ultérieurement.
    1. Ne pas créer de compte local
2. [Appliquez le package d’approvisionnement](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[Configuration AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Configuration AAD

Les appareils joints à AAD configurés pour le mode plein écran peuvent se connecter à un compte visiteur à l’aide d’un appui sur un bouton à partir de l’écran de connexion. Une fois connecté au compte visiteur, l’appareil ne demande pas de connexion tant que le visiteur n’est pas explicitement déconnecté du menu Démarrer ou que l’appareil n’a pas été redémarré.

L’ouverture de session automatique des visiteurs peut être gérée par le biais d' [une stratégie OMA-URI personnalisée](/mem/intune/configuration/custom-settings-windows-10):

- Valeur de l’URI :./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Stratégie | Description | Configurations |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Permet à un visiteur de se connecter automatiquement à une borne. | 1 (oui), 0 (non, valeur par défaut.) |