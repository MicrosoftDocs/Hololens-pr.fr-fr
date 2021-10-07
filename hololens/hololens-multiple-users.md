---
title: partager votre HoloLens avec plusieurs personnes
description: vous pouvez configurer HoloLens pour qu’il soit partagé par plusieurs comptes Azure Active Directory ou par plusieurs utilisateurs qui utilisent un seul compte.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600727"
---
# <a name="share-your-hololens-with-multiple-people"></a>partager votre HoloLens avec plusieurs personnes

## <a name="overview"></a>Vue d'ensemble

les entreprises investissent souvent dans de nombreux appareils HoloLens partagés. la façon dont vous utilisez HoloLens est flexible dans le tableau, en fonction de vos besoins spécifiques. Voici un exemple d’expériences multi-utilisateurs :

- une flotte de HoloLens 2 appareils est configurée via Windows autopilot pour HoloLens 2, avec un portefeuille cohérent d’applications d’entreprise sur chaque appareil. Vous avez configuré plusieurs profils kiosque, ciblant différents groupes de Azure AD. chaque utilisateur se connecte au HoloLens à l’aide de clés FIDO2 et se connecte à son propre compte Azure AD, et est présenté avec une expérience personnalisée.
- un éditeur de logiciels indépendant (ISV) loue des appareils HoloLens 2 avec l’assistance à distance D365 et leur application métier à l’entreprise d’un client. Ces appareils sont configurés pour les bornes qui incluent uniquement leur application LOB et l’assistance à distance, et qui sont partagées entre plusieurs utilisateurs finaux. WDAC est utilisé pour empêcher le lancement de l’application Paramètres et Microsoft Edge. La location est un pack de batterie USB-C qui permet de maintenir les appareils à pleine charge sur plusieurs équipes.
- un utilisateur final dans une entreprise tente d’apporter des ajustements à Bluetooth sur l’appareil afin qu’il puisse se connecter à un nouvel appareil, mais la page Paramètres la stratégie de visibilité est activée pour limiter l’affichage de la page des appareils. Ils sont toujours autorisés à accéder à d’autres pages en fonction des besoins, par exemple Wi-Fi pour pouvoir utiliser l’assistance à distance dans plusieurs emplacements avec le même HoloLens.

## <a name="best-practices"></a>Bonnes pratiques

Lorsque vous envisagez de partager vos appareils, plusieurs éléments sont à prendre en considération pour optimiser votre environnement d’appareil en fonction des besoins de votre entreprise.

- [Identité et authentification](#identity-and-authentication)
- [Gestion des appareils](#device-management)
- [Gestion avancée des appareils-kiosque et WDAC](#advanced-device-management---kiosk-and-wdac)
- [Gestion physique](#physical-management)

### <a name="identity-and-authentication"></a>[Identité et authentification](hololens-identity.md)

Si vous envisagez de disposer de plusieurs comptes sur un appareil, vous avez Azure AD comptes avec tous les modes d’authentification. ces méthodes d’authentification seront basées sur [Windows Hello](/windows-hardware/design/device-experiences/windows-hello), y compris les clés Iris et FIDO2.

- Les clés de sécurité de l’Rex 2 sont excellentes si vous avez plusieurs appareils, de nombreux utilisateurs ou si vous utilisez constamment de nouveaux appareils.
- Si vous disposez de 10 utilisateurs ou moins, IRIS est une solution rapide pour connecter des utilisateurs qui se sont déjà connectés au même appareil.

### <a name="device-management"></a>[Gestion des appareils](hololens-csp-policy-overview.md)

Si des appareils sont partagés entre des utilisateurs, vous souhaiterez probablement utiliser des restrictions d’appareil. À l’aide de la gestion des périphériques, vous pouvez définir des stratégies pour mieux permettre à vos utilisateurs d’utiliser l’appareil, de gérer des mises à jour ou de limiter ce que l’appareil peut faire. Nous vous recommandons de consulter nos [restrictions d’appareils courantes](hololens-common-device-restrictions.md)et de voir si ces recommandations semblent adaptées à votre organisation. une fois que vous connaissez les stratégies que vous souhaitez utiliser, vous pouvez les appliquer à [l’aide de la Endpoint Manager de Microsoft (MDM)](hololens-mdm-configure.md) ou des packages d’approvisionnement.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Gestion avancée des appareils- [kiosque](hololens-kiosk.md) et [WDac](windows-defender-application-control-wdac.md)

Dans certains cas, vous souhaiterez peut-être limiter les applications accessibles aux utilisateurs finaux. Vous pouvez limiter les applications auxquelles les utilisateurs sont présentés dans le menu Démarrer à l’aide du [mode plein écran](hololens-kiosk.md). La borne peut être configurée pour présenter des menus Démarrer différents en fonction de l’utilisateur, des groupes Azure ou des types d’utilisateurs spéciaux. ce visiteur ou l’exclusion des propriétaires d’appareils. Vous pouvez choisir plusieurs applications ou une seule application. Une borne multi-applications n’empêche pas une application de lancer une autre. par conséquent, si le magasin ou une autre application est disponible, les utilisateurs peuvent toujours lancer une autre application.

vous pouvez également souhaiter arrêter complètement le lancement d’applications ou de services à l’aide du [contrôle d’Application Windows Defender (WDAC)](windows-defender-application-control-wdac.md) pour restreindre les applications. WDAC est différent de cette borne, car elle ne modifie pas l’interface utilisateur de HoloLens mais n’autorise pas l’application bloquée à se lancer.

la [visibilité des Paramètres de Page](settings-uri-list.md) est une autre façon d’ajouter des restrictions à un appareil. dans le cas où vous devez accorder aux utilisateurs l’accès à certaines pages de l’application Paramètres, vous ne pouvez pas utiliser la Page Paramètres visibilité pour limiter l’accès. Cela est utile, par exemple, si vos utilisateurs ont besoin de modifier le Wi-Fi, mais que vous ne voulez pas qu’ils accèdent à la page des comptes.

### <a name="physical-management"></a>Gestion physique

Lors du partage de l’appareil entre plusieurs utilisateurs, il existe des considérations physiques.

- Vérifiez que les appareils sont en charge entre les décalages.
- Si un appareil est requis pour une équipe de travail, et qu’il doit disposer de la dernière équipe, vous pouvez utiliser une batterie externe au début d’une équipe alors que l’appareil a toujours une charge importante pour les [directions de chaleur de gestion](hololens2-charging.md#managing-heat).
- Lorsque vous stockez des appareils, assurez-vous qu’ils sont branchés et connectés à un réseau. C’est le meilleur moyen de s’assurer des mises à jour du système d’exploitation et des applications.
- Pensez à la façon dont vous envisagez de [nettoyer l’appareil](hololens2-maintenance.md) entre les utilisateurs.
- Pour un appareil avec un seul utilisateur partagé si vous utilisez un code confidentiel/mot de passe partagé pour un seul utilisateur, ne placez pas le code confidentiel/le mot de passe sur le côté de l’appareil.
- Pour plusieurs appareils avec un seul utilisateur partagé, utilisez différents pin/mots de passe.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Partager avec plusieurs personnes, chacune utilisant son propre compte

les comptes d’Azure Active Directory individuels (Azure AD) sont le cas d’utilisation d’identité préféré et le plus sécurisé pour les utilisateurs HoloLens 2. Lors de l’utilisation de leurs propres comptes Azure AD, plusieurs utilisateurs peuvent conserver leurs propres paramètres utilisateur et données utilisateur sur l’appareil. Un seul utilisateur peut être connecté à la fois. lorsqu’un utilisateur se connecte, HoloLens déconnecte l’utilisateur précédent.

pour vous assurer que plusieurs personnes peuvent utiliser leurs propres comptes sur votre HoloLens, procédez comme suit pour le configurer :

1. Quand vous [configurez l’appareil](hololens2-start.md), sélectionnez **mon entreprise ou école en est propriétaire** et connectez-vous à l’aide d’un compte Azure ad.
1. une fois l’installation terminée, assurez-vous que les paramètres du compte (comptes Paramètres >) incluent d' **autres utilisateurs**.

> [!NOTE]
> Si votre appareil n’a pas été configuré avec un compte Azure AD, il doit être [réinitialisé ou reflash](hololens-recovery.md) et configuré correctement.

pour utiliser HoloLens, chaque utilisateur suit les étapes suivantes :

1. Si un autre utilisateur utilise l’appareil, choisissez l’une des options suivantes :
   - Appuyez une fois sur le bouton d’alimentation pour accéder à la mise en veille, puis appuyez de nouveau sur le bouton d’alimentation pour revenir à l’écran de verrouillage
   - sélectionnez la vignette de l’utilisateur dans la **menu Démarrer** ou choisissez se déconnecter dans le menu de l' **alimentation** pour déconnecter l’utilisateur actuel.

1. Utilisez les informations d’identification de votre compte Azure AD pour vous connecter à l’appareil.  
    - si c’est la première fois que vous utilisez l’appareil, vous êtes invité à [étalonner](hololens-calibration.md) le HoloLens à vos propres yeux.
    - Si vous avez déjà utilisé l’appareil :
        - [Windows holographique, version 20H2, build 19041,1128](hololens-release-notes.md#windows-holographic-version-20h2) ou version ultérieure, l’affichage s’ajuste en toute transparence à la qualité et à une expérience d’affichage confortable.
        - Les versions précédentes auront besoin d’un étalonnage manuel pour s’adapter à vos yeux.

> [!TIP]
> Si un utilisateur ne s’est pas connecté à un appareil, essayez l’une de ces deux méthodes pour une connexion plus rapide :
>
> - **Clé de sécurité Rex 2** : votre clé de sécurité FIDO2 sera automatiquement reconnue et l’utilisateur n’aura pas besoin de taper ses informations d’identification utilisateur ni d’utiliser l’authentification multifacteur. Il s’agit de la méthode la plus rapide pour vous connecter à un nouvel appareil.
> - **Authentification Web** : quand vous vous connectez à un nouvel appareil, vous pouvez sélectionner le lien **se connecter à partir d’un autre appareil** , ce qui génère un code à 9 caractères que vous pouvez utiliser sur [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) pour vous connecter en tant qu’utilisateur sur l’appareil, ou taper votre nom d’utilisateur et votre mot de passe à l’aide d’un clavier à des fins pratiques.

pour afficher la liste des utilisateurs d’appareils ou pour supprimer un utilisateur de l’appareil, accédez à **Paramètres**  >  **comptes**  >  **autres utilisateurs**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Partager avec plusieurs personnes, toutes utilisant le même compte

plusieurs utilisateurs peuvent également partager un appareil HoloLens lors de l’utilisation d’un compte d’utilisateur unique. bien qu’il soit préférable pour HoloLens utilisateurs de se connecter à l’appareil avec leurs identités individuelles (comptes Azure AD), il ne s’agit pas d’une option dans certaines organisations.

Deux méthodes d’appareil partagé sont disponibles :

- **plusieurs utilisateurs finaux partageant 1 appareil** : un appareil HoloLens est alloué à un espace désigné où un employé peut utiliser l’appareil. Il peut s’agir, par exemple, d’une salle propre ou d’une suite chirurgicale.

- **plusieurs utilisateurs finaux partageant plusieurs appareils** : HoloLens appareils se trouvent dans un espace de stockage partagé où les employés peuvent utiliser n’importe quel appareil. Il peut s’agir, par exemple, d’une plate-forme pétrolière ou d’une concession automatique/garage.

Quand un nouvel utilisateur place sur l’appareil pour la première fois tout en conservant le même compte connecté, l’appareil invite l’utilisateur à étalonner et à personnaliser rapidement l’expérience d’affichage. L’appareil stocke les informations d’étalonnage pour optimiser automatiquement la qualité et le confort de l’expérience d’affichage de chaque utilisateur. Les utilisateurs n’ont pas besoin d’étalonner à nouveau l’appareil.
