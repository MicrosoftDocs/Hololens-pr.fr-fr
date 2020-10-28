---
title: Comment installer des applications via le programme d’installation Web
description: Installer des applications via le programme d’installation Web du programme d’installation d’applications
keywords: gestion des applications, application, hololens, programme d’installation de l’application, installation Web
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135441"
---
# Installation d’applications à partir d’une page Web

Les utilisateurs peuvent installer une application directement à partir d’un serveur Web. Cela nécessite une utilisation du programme d’installation de l’application combinée à une méthode simple de distribution et d’installation. 

> [!IMPORTANT]
> Pour le moment, cette fonctionnalité est uniquement avalible dans les builds Insider 19041.1366 +. En [savoir plus sur l’inscription aux builds Insider pour Windows](hololens-insider.md).

## Configuration:
1.  Assurez-vous que votre application est correctement configurée pour l’installation.
1.  Procédez comme [suit pour l’activer sur une page Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 
1.  Choisissez une méthode de déploiement de certificats. 
    1.  Les [packages de mise en service](hololens-provisioning.md) peuvent être appliqués aux périphériques locaux.
    1.  La gestion des périphériques mobiles peut être utilisée pour [appliquer des certificats avec des configurations d’appareil](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
    1.  Utiliser le gestionnaire de [certificats](hololens-insider.md#certificate-manager)d’appareil. 

## Utilisation de l’utilisateur final:
1.  Un utilisateur reçoit et installe un certificat sur l’appareil à l’aide de la méthode choisie précédemment. 
1.  Un utilisateur visite l’URL créée à l’étape ci-dessus.

L’application sera désormais installée sur l’appareil. Pour Rechercher l’application, ouvrez le **menu Démarrer** , puis sélectionnez le bouton **toutes les applications** pour rechercher votre application. 

-   Pour obtenir de l’aide pour résoudre ce problème, consultez la rubrique [résoudre les problèmes du programme](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)d’installation de l’application. 

> [!NOTE]
> Le processus de mise à jour de l’interface utilisateur n’est pas pris en charge. Par conséquent, l’option ShowPrompt sur [cette page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) et les options associées ne sont pas prises en charge.
