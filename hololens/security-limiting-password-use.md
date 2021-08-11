---
title: Limitation de l’utilisation d’un mot de passe
description: limitation de l’utilisation d’un mot de passe pour HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, limitation de l’utilisation d’un mot de passe, mot de passe, mot de passe hololens, connexion, windows hello, hello, gestionnaire de comptes windows, connexion FIDO2, FIDO 2, WEBAUTHN, compte local, sécurité hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a4ceaa1a741ec63153cd9112d04547165b46b0fa72c32ee7f9580f15368a2f88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665450"
---
# <a name="limiting-password-use"></a>Limitation de l’utilisation d’un mot de passe

La plupart des systèmes informatiques utilisent aujourd’hui les informations d’identification des utilisateurs comme base de la sécurité, ce qui les rend dépendants des mots de passe réutilisables créés par l’utilisateur. Les mots de passe sont ainsi devenus la principale cause de compromission des comptes et des violations des données. À titre d’exemple, les mots de passe peuvent être interceptés lors de la transmission, ou volés sur un serveur (par hameçonnage ou via des attaques par pulvérisation de mot de passe) et compromis pour accéder à un compte d’utilisateur.

Pour améliorer la sécurité et la protection des comptes, HoloLens 2 peut imposer des informations d’identification « sans mot de passe » renforcées et sécurisées (y compris Windows Hello) pour la connexion de l’appareil, offrant un accès fluide au cloud Microsoft.

## <a name="signing-in-from-another-device"></a>Connexion à partir d’un autre appareil

HoloLens 2 offre des options de connexion à un appareil distant pour les comptes professionnels Azure Active Directory lors de la configuration initiale de l’appareil et de la connexion utilisateur. Ceci permet de réduire la nécessité de taper des mots de passe complexes et de minimiser le besoin de mots de passe comme informations d’identification. Les utilisateurs et les organisations qui utilisent des cartes à puce pour l’authentification ont des difficultés à utiliser ces informations d’identification sur des appareils comme HoloLens 2, et les organisations doivent souvent développer des systèmes complexes et des processus coûteux pour contourner le problème. Pour résoudre ce problème, Azure AD offre deux options de connexion sans mot de passe sur HoloLens 2.

La première méthode d’authentification s’appuie sur les nouvelles fonctionnalités de l’application Microsoft Authenticator pour fournir une authentification basée sur des clés qui active les informations d’identification d’un utilisateur liées à un appareil. Une fois qu’elle est activée sur un locataire par l’administrateur, les utilisateurs vont voir un message lors de la configuration de l’appareil HoloLens pour leur demander de taper un numéro sur leur application. Ils doivent ensuite taper le même nombre sur leur application d’authentification, choisir Approuver, fournir leur code PIN ou une authentification biométrique, et effectuer leur authentification pour que la configuration de l’appareil HoloLens puisse continuer. Ceci est décrit plus en détail dans [Connexion sans mot de passe](/azure/active-directory/authentication/howto-authentication-passwordless-phone).

La seconde méthode est un flux de code d’appareil, intuitif pour les utilisateurs et qui ne nécessite aucune infrastructure supplémentaire.  Ce comportement de connexion à distance s’appuie sur un autre appareil approuvé qui prend en charge le mécanisme d’authentification préféré de l’organisation et, une fois l’authentification effectuée, les jetons sont renvoyés à l’appareil HoloLens pour effectuer la connexion ou la configuration de l’appareil. Les étapes de ce flux sont les suivantes :

  1. Un utilisateur effectuant la configuration initiale de l’appareil ou les flux de connexion sur OOBE voit s’afficher un lien indiquant « Se connecter à partir d’un autre appareil » et appuie sur celui-ci. Ceci lance une session de connexion à distance.
  1. L’utilisateur voit ensuite une page d’interrogation, qui contient un court URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) qui pointe vers le point de terminaison d’authentification de l’appareil du service d’émission de jeton de sécurité (STS) d’Azure AD. L’utilisateur voit également un code à usage unique qui est généré de façon sécurisée dans le cloud et qui a une durée de vie maximale de 15 minutes. Parallèlement à la génération du code, Azure AD crée également une session chiffrée lors du lancement de la demande de connexion à distance de l’étape précédente ; l’URI et le code sont alors utilisés ensemble pour approuver la demande de connexion à distance.
  1. L’utilisateur accède ensuite à l’URI à partir d’un autre appareil et est invité à entrer le code affiché sur son appareil HoloLens 2.
  1. Une fois que l’utilisateur a entré le code, le service STS d’Azure AD affiche une page indiquant l’appareil HoloLens 2 de l’utilisateur à l’origine de la demande de connexion à distance et de la génération du code. L’utilisateur est ensuite invité à confirmer pour empêcher toute attaque par hameçonnage.
  1. Si l’utilisateur choisit de continuer à se connecter à l’« application » affichée, le service STS d’Azure AD demande à l’utilisateur ses informations d’identification. Une fois l’authentification réussie, le service STS d’Azure AD met à jour la session distante mise en cache comme étant « approuvée » avec un code d’autorisation.
  1. Enfin, la page d’interrogation sur l’appareil HoloLens 2 de l’utilisateur reçoit une réponse « Autorisé » d’Azure AD et procède à la validation du code utilisateur et de son code d’autorisation stocké associé, et génère des jetons OAuth comme demandé pour terminer la configuration de l’appareil. Le jeton d’authentification créé est valide pendant une heure et le jeton d’actualisation a une durée de vie de 90 jours.

Les algorithmes de génération et de chiffrement du code utilisés dans ce flux sont tous deux conformes à FIPS. Les appareils HoloLens 2 utilisent le module de plateforme sécurisée (TPM) pour sécuriser les clés de l’appareil et pour chiffrer les jetons générés après l’authentification des utilisateurs en utilisant des clés protégées par le matériel. Pour plus d’informations sur la sécurité des jetons sur HoloLens 2, consultez [Qu’est-ce qu’un jeton d’actualisation principal ?](/azure/active-directory/devices/concept-primary-refresh-token).

## <a name="device-sign-in-with-windows-hello"></a>Connexion à l’appareil avec Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) offre des options sans mot de passe intégrées directement dans le système d’exploitation, permettant aux utilisateurs de se connecter à l’appareil en utilisant la reconnaissance de l’iris ou un code PIN. Le code PIN est toujours disponible comme informations d’identification et il est obligatoire pour la configuration de l’appareil, tandis que la connexion par reconnaissance de l’iris est facultative et peut être ignorée. Les utilisateurs peuvent se connecter à des appareils HoloLens en utilisant leur compte Microsoft personnel ou leur [compte professionnel Azure Active Directory *sans* entrer un mot de passe](/azure/active-directory/authentication/concept-authentication-passwordless). De telles options offrent aux utilisateurs un accès rapide et sécurisé à leur expérience Windows complète, et à leurs applications, données, sites web et services. La stratégie de Microsoft en matière d’expérience de connexion sans mot de passe est détaillée ici.

Quand des informations d’identification Windows Hello sont créées, elles établissent une relation de confiance avec un fournisseur d’identité et créent une paire de clés asymétriques pour l’authentification. Un mouvement Windows Hello (comme la reconnaissance par l’iris ou le code PIN) fournit l’entropie nécessaire pour déchiffrer une clé privée produite par la puce du module de plateforme sécurisée (TPM) de l’appareil. Cette clé privée est ensuite utilisée pour signer les demandes envoyées à un serveur d’authentification et, une fois l’authentification réussie, l’utilisateur a accès à sa messagerie, à ses photos et à d’autres paramètres du compte.

Pour plus d’informations, consultez l’infographie suivante :

  ![Connexion via Windows Hello](images/security-hello-sign-in.png)
  
Dans le graphique présenté ci-dessus, notez que « nonce » signifie « number once » (un nombre une seule fois), et qu’il s’agit d’un nombre généré de façon aléatoire ou semi-aléatoire. Une fois que les informations d’identification biométrique ou le code PIN de Windows Hello sont configurés, elles ne quittent jamais l’appareil sur lequel elles sont configurées. Même si le code PIN Windows Hello de l’utilisateur est volé, par exemple via une attaque par hameçonnage, il est [inutilisable sans l’appareil physique de l’utilisateur](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

Pour plus de sécurité, les informations d’identification Windows Hello sont protégées par le module de plateforme sécurisée (TPM) pour rendre les informations d’identification inviolables, et elles sont complétées par des protections anti-martèlement contre plusieurs entrées incorrectes et contre les logiciels malveillants pour empêcher leur exposition. Pour plus d’informations sur l’authentification unique, lisez cette [vue d’ensemble des méthodes d’authentification unique](/azure/active-directory/manage-apps/what-is-single-sign-on).

L’authentification par reconnaissance de l’iris revient au code PIN. Pour configurer un nouveau code PIN (un authentificateur fort) sur l’appareil, l’utilisateur doit avoir récemment effectué une [authentification multifacteur](/azure/active-directory/authentication/concept-mfa-howitworks) afin de terminer le processus.

## <a name="single-sign-on-with-web-account-manager"></a>Authentification unique avec le gestionnaire de comptes web

L’authentification unique permet aux utilisateurs sans mot de passe de se connecter à l’appareil, en utilisant leur compte personnel, professionnel ou scolaire. L’utilisateur est automatiquement autorisé avec l’authentification unique sur toutes les applications et tous les services intégrés via les [API du gestionnaire de comptes web](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

Une fois qu’une identité a été ajoutée via une application, elle peut, avec le consentement de l’utilisateur, devenir disponible pour toutes les applications et tous les services en utilisant l’intégration au niveau du système. Ceci réduit considérablement la charge de travail nécessaire pour la connexion à l’application et offre aux utilisateurs une expérience d’identité fluide.

Pour plus d’informations sur l’implémentation des API du gestionnaire de comptes web, consultez [Implémentation des API du gestionnaire de comptes web](/windows/uwp/security/web-account-manager).

  ![API de sécurité](images/security-api-img.png)
  
Pour les suites d’applications avec des exigences d’authentification spécialisées, l’infrastructure du gestionnaire de comptes web est extensible aux fournisseurs d’identité personnalisés. Les utilisateurs peuvent télécharger le fournisseur d’identité personnalisé, qui se présente en package sous la forme d’une application de plateforme Windows universelle (UWP) provenant du Microsoft Store, pour activer l’authentification unique sur d’autres applications intégrées avec ce fournisseur d’identité.

Pour plus d’informations sur l’implémentation de fournisseurs d’identité WAM personnalisés, consultez [Informations de référence sur l’API de fournisseur d’identité WAM personnalisé](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Connexion Windows Hello et FIDO2 avec WebAuthn

HoloLens 2 peut utiliser les informations d’identification sans mot de passe de l’utilisateur (comme des clés de sécurité Windows Hello ou FIDO2) pour se connecter de façon sécurisée sur le web via Microsoft Edge et aux sites web qui prennent en charge WebAuthn. FIDO2 permet aux informations d’identification des utilisateurs de profiter des appareils basés sur des standards pour s’authentifier auprès de services en ligne.

> [!Note]
> Les spécifications [WebAuthn](https://www.w3.org/TR/webauthn/) et FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) sont implémentées dans des services. Les métadonnées signées spécifiées par WebAuthn et FIDO2 fournissent des informations, comme la présence ou non de l’utilisateur, et vérifient l’authentification via le geste local.

Comme avec Windows Hello, quand l’utilisateur crée et inscrit des informations d’identification FIDO2, l’appareil (HoloLens 2 ou la clé de sécurité FIDO2) génère une clé privée et une clé publique sur l’appareil. La clé privée est stockée de façon sécurisée sur l’appareil et elle ne peut être utilisée qu’après avoir été déverrouillée via un geste local, comme une identification biométrique ou un code PIN. Quand la clé privée est stockée, la clé publique est envoyée au système de comptes Microsoft dans le cloud et elle est inscrite auprès du compte d’utilisateur associé.

Après la connexion avec un compte MSA et Azure AD, le système envoie un nombre ou une variable de données généré à HoloLens 2 ou l’appareil FIDO2. HoloLens 2 ou l’appareil utilise la clé privée pour signer l’identification. L’identification et les métadonnées signées sont renvoyées au système de comptes Microsoft et sont vérifiées en utilisant la clé publique.

Les appareils Windows Hello et FIDO2 implémentent des informations d’identification basées sur l’appareil HoloLens, en particulier l’enclave sécurisée du module de plateforme sécurisée (TPM) intégrée. L’enclave TPM stocke la clé privée, et demande un code biométrique ou un code PIN pour la déverrouiller. De même, une clé de sécurité FIDO2 est un petit appareil externe avec une enclave sécurisée intégrée qui stocke la clé privée, et qui demande un code biométrique ou un code PIN pour la déverrouiller.

Les deux options offrent une authentification à deux facteurs en une seule étape, nécessitant à la fois un appareil inscrit, et un code biométrique ou un code PIN pour se connecter. Pour plus d’informations, consultez le graphique et le processus d’authentification forte avec la clé de sécurité FIDO2 ci-dessous.

### <a name="strong-authentication-with-fido2-security-key"></a>Authentification forte avec la clé de sécurité FIDO2

  ![Image FIDO](images/security-fido2-whfb-smaller.png)

1. L’utilisateur insère la clé de sécurité FIDO2 dans HoloLens 2
1. Windows détecte la clé de sécurité FIDO2
1. HoloLens envoie une demande d’authentification
1. Azure AD renvoie un nonce
1. L’utilisateur effectue un geste pour déverrouiller les magasins de clés privées dans l’enclave sécurisée de la clé de sécurité
1. La clé de sécurité FIDO2 signe le nonce avec une clé privée
1. La demande de jeton PRT avec un nonce signé est envoyée à Azure AD
1. Azure AD vérifie la clé FIDO
1. Azure AD retourne PRT et TGT pour permettre l’accès aux ressources

MSA et Azure AD sont parmi les premiers composants à s’appuyer sur l’authentification sans mot de passe en implémentant WebAuthn.

Pour plus d’informations sur l’utilisation de WebAuthn avec des applications et/ou des SDK, accédez à [API WebAuthn pour l’authentification sans mot de passe sur Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis).

HoloLens 2 prend en charge les appareils de sécurité FIDO2 qui sont implémentés selon les spécifications et qui satisfont à la configuration requise indiquée dans [Connexion sans mot de passe Azure Active Directory - Clés de sécurité FIDO2](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys).

## <a name="local-accounts"></a>Comptes locaux

Un seul compte local peut être configuré pour les déploiements en mode hors connexion. Les comptes locaux ne sont pas activés par défaut et doivent être configurés lors du provisionnement des appareils. Ils doivent se connecter en utilisant un mot de passe et ne prennent pas en charge les autres méthodes d’authentification (comme [Windows Hello Entreprise](/windows/security/identity-protection/hello-for-business/hello-overview) ou [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)).

Pour plus d’informations sur les comptes d’utilisateur HoloLens, consultez [Identité HoloLens](hololens-identity.md).

Les administrateurs informatiques déterminent si l’utilisateur est autorisé à utiliser un compte MSA pour l’authentification et les services de connexion non liés à la messagerie via [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Pour les stratégies de configuration de mot de passe, les stratégies de mise en veille après une période d’inactivité et les stratégies d’écran de verrouillage, consultez [Verrouillage des appareils](/windows/client-management/mdm/policy-csp-devicelock).
