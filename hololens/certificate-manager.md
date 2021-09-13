---
title: Gestionnaire de certificats
description: découvrez comment installer, gérer et supprimer manuellement des certificats sur des appareils de réalité mixte HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032435"
---
# <a name="certificate-manager"></a>Gestionnaire de certificats

- Amélioration de l’audit, du diagnostic et des outils de validation pour la sécurité et la conformité des appareils par le biais du nouveau gestionnaire de certificats. Cette fonctionnalité vous permettra de déployer, de dépanner et de valider vos certificats à grande échelle dans les environnements commerciaux.

dans Windows holographique, version 20H2, nous ajoutons un gestionnaire de certificats à l’application HoloLens 2 Paramètres. accédez à **Paramètres > mettre à jour & les certificats > de sécurité**. Cette fonctionnalité offre un moyen simple et convivial d’afficher, d’installer et de supprimer des certificats sur votre appareil. Avec le nouveau gestionnaire de certificats, les administrateurs et les utilisateurs disposent désormais d’outils d’audit, de diagnostic et de validation améliorés pour garantir que les appareils restent sécurisés et conformes. 

-   **Audit :** Possibilité de valider le déploiement correct d’un certificat ou de confirmer qu’il a été supprimé de manière appropriée. 
-   **Diagnostic :** Lorsque des problèmes surviennent, la validation de l’existence des certificats appropriés sur l’appareil permet de gagner du temps et de faciliter la résolution des problèmes. 
-   **Validation :** Vérifier qu’un certificat est destiné à l’usage prévu et qu’il fonctionne, peut faire gagner beaucoup de temps, en particulier dans les environnements commerciaux avant de déployer des certificats à grande échelle.

Pour rechercher rapidement un certificat spécifique dans la liste, il existe des options de tri par nom, magasin ou date d’expiration. Les utilisateurs peuvent également rechercher directement un certificat. Pour afficher les propriétés d’un certificat, sélectionnez le certificat, puis cliquez sur **info**. 

L’installation de certificat prend actuellement en charge les fichiers. cer et. CRT. Les propriétaires d’appareils peuvent installer des certificats sur l’ordinateur local et l’utilisateur actuel.  tous les autres utilisateurs ne peuvent s’installer que dans l’utilisateur actuel.

## <a name="to-install-a-certificate"></a>Pour installer un certificat : 

1.  Connecter votre HoloLens 2 sur un PC.
1.  Placez le fichier de certificat que vous souhaitez installer à l’emplacement de votre HoloLens 2.
1.  accédez à **Paramètres application > mettre à jour & les certificats > de sécurité**, puis sélectionnez installer un certificat.
1.  Cliquez sur **Importer un fichier** et accédez à l’emplacement où vous avez enregistré le certificat.
1.  Sélectionnez **emplacement du magasin**.
1.  Sélectionnez **magasin de certificats**.
1.  Cliquez sur **Installer**.

Le certificat doit maintenant être installé sur l’appareil.

![visionneuse de certificats dans l’application Paramètres sous certificats.](images/certificate-viewer-device.jpg)

![image illustrant l’utilisation de l’interface utilisateur de certificat pour installer un certificat dans Paramètres.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Pour supprimer un certificat :

> [!WARNING]
> à l’aide du gestionnaire de certificats, les utilisateurs peuvent uniquement supprimer des certificats installés directement à partir de l’interface utilisateur Paramètres. Si un certificat a été installé par d’autres moyens, il doit également être supprimé par le même mécanisme et ne peut pas être supprimé du gestionnaire de certificats. Le Gestionnaire de certificats vous permet de visualiser les certificats déployés via GPM, mais pas de les désinstaller. Pour les désinstaller, vous devez utiliser GPM.

1. accédez à **Paramètres application > des certificats de sécurité et de mise à jour >**.
1. Recherchez le certificat par son nom dans la zone de recherche.
1. Sélectionnez le certificat.
1. Cliquez sur **supprimer**
1. Lorsque vous êtes invité à confirmer l’opération, sélectionnez **Oui**.

