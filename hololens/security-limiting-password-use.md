---
title: Limitation de l’utilisation d’un mot de passe
description: limitation de l’utilisation d’un mot de passe pour holoLens
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: sécurité, hololens, limitation de l’utilisation d’un mot de passe, mot de passe, mot de passe hololens, connexion, connexion, connexion windowshello, hello, gestionnaire de comptes windows, connexion FIDO2, FIDO2, WEBAUTHN, compte local, sécurité hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 61330e77bc3aca5b0b21b58f18d087f7d5c06f3b
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865741"
---
# Limitation de l’utilisation d’un mot de passe

La plupart des systèmes informatiques utilisent aujourd’hui les informations d’identification des utilisateurs comme base de sécurité, ce qui les rend dépendants des mots de passe réutilisables créés par l’utilisateur. Les mots de passe sont ainsi devenus la principale cause de compromission de compte et de violation de données. À titre d’exemple, les mots de passe peuvent être interceptés lors de la transmission ou volés à un serveur (par hameçonnage ou attaques par pulvérisation de mot de passe) et compromis pour accéder à un compte d’utilisateur.

Pour améliorer la sécurité et la protection des comptes, HoloLens2 peut activer des informations d’identification «sans mot de passe» renforcées et sécurisées (y compris WindowsHello) pour la connexion de l’appareil, offrant un accès transparent au cloud Microsoft. 

## Se connecter à partir d’un autre appareil

HoloLens2 offre des options de connexion à un appareil distant pour les comptes professionnels AzureActiveDirectory lors de la configuration initiale de l’appareil et de la connexion utilisateur. Cela permet de réduire la nécessité de taper des mots de passe complexes et de minimiser le besoin de mots de passe comme informations d’identification. Les utilisateurs et les organisations qui utilisent des cartes à puce pour s’authentifier ont des difficultés à utiliser ces informations d’identification sur des appareils tels que HoloLens2 et les organisations doivent souvent développer des systèmes complexes et des processus coûteux pour contourner le problème. Pour résoudre ce problème, AzureAD propose deux options de connexion sans mot de passe sur HoloLens2. 

La première méthode d’authentification s’appuie sur les nouvelles fonctionnalités de l’application Microsoft Authenticator pour fournir une authentification basée sur des clés qui active les informations d’identification d’un utilisateur liées à un appareil. Une fois activé sur un client par l’administrateur, un message s’affichera lors de la configuration de l’appareil HoloLens pour indiquer aux utilisateurs de taper un numéro sur leur application. Ils doivent ensuite faire correspondre le numéro sur leur application d’authentification, choisir Approuver, fournir leur code PIN ou une authentification biométrique et complète pour que leur configuration HoloLens puisse être appliquée. Vous trouverez tous les détails de cette opération dans l’article [Connexion sans mot de passe](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone).

La seconde est un flux de code de l’appareil, intuitif pour les utilisateurs et ne nécessitant aucune infrastructure supplémentaire.  Ce comportement de connexion à distance repose sur un autre appareil approuvé qui prend en charge le mécanisme d’authentification préféré de l’organisation et, une fois terminé, les jetons sont renvoyés à HoloLens pour terminer la connexion ou la configuration de l’appareil. Les étapes de ce flux sont les suivantes:

  1.    Un utilisateur, effectuant la configuration initiale de l’appareil ou les flux de connexion sur OOBE, voit s’afficher un lien indiquant «Se connecter à partir d’un autre appareil» et appuie dessus. Ceci lance une session de connexion à distance.
  2.    L’utilisateur voit ensuite une page d’interrogation qui contient un court URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) qui pointe vers le point de terminaison d’authentification de l’appareil du service d’émission de jeton sécurisé (STS) AzureAD. L’utilisateur voit également un code à usage unique qui est généré de façon sûre dans le cloud et a une durée de vie maximale de 15minutes. Parallèlement à la génération de code, AzureAD crée également une session chiffrée lors du lancement de la demande de connexion à distance de l’étape précédente et ensemble, l’URI et le code sont utilisés pour approuver la demande de connexion à distance. 
  3.    L’utilisateur accède ensuite à l’URI à partir d’un autre appareil et est invité à saisir le code affiché sur son appareil HoloLens2. 
  4.    Une fois que l’utilisateur a entré le code, le STS AzureAD affiche une page indiquant l’appareil HoloLens2 de l’utilisateur à l’origine de la demande de connexion à distance et de la génération du code. L’utilisateur est ensuite invité à confirmer pour empêcher toute attaque d’hameçonnage. 
  5.    Si l’utilisateur choisit de continuer à se connecter à l ’«application» affichée, le STS AzureAD invite l’utilisateur à saisir ses informations d’identification. Une fois l’authentification réussie, le STS AzureAD met à jour la session distante mise en cache comme «approuvée» avec un code d’autorisation.
  6.    Enfin, la page d’interrogation sur l’appareil HoloLens2 de l’utilisateur reçoit une réponse «autorisée» d’AzureAD et procède à la validation du code utilisateur, de son code d’autorisation stocké associé et génère des jetons OAuth comme demandé pour terminer la configuration de l’appareil. Le jeton d’authentification créé est valide pendant uneheure et le jeton d’actualisation a une durée de vie de 90jours. 

Les algorithmes de génération et de chiffrement de code utilisés dans ce flux sont tous deux conformes aux normes FIPS. Les appareils HoloLens2 utilisent le TPM pour sécuriser les clés de l’appareil et chiffrer les jetons générés après l’authentification des utilisateurs à l’aide de clés protégées par le matériel. Si vous souhaitez obtenir plus d’informations sur la sécurité des jetons sur HoloLens2, consultez la page [Qu’est-ce qu’un jeton d’actualisation principal (PRT)](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token).

## Connexion à l’appareil avec WindowsHello

[WindowsHello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) propose des options sans mot de passe intégrées directement dans le système d’exploitation permettant aux utilisateurs de se connecter à l’appareil en utilisant la reconnaissance de l’iris ou un code PIN. Le code PIN peut toujours être utilisé en tant qu’informations d’identification et est requis pour la configuration de l’appareil, tandis que la connexion par reconnaissance de l’iris est facultative et peut être ignorée. Les utilisateurs peuvent se connecter aux appareils HoloLens à l’aide de leur compte Microsoft personnel ou de leur [compte professionnel AzureActiveDirectory *sans* entrer de mot de passe](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless). De telles options offrent aux utilisateurs un accès rapide et sécurisé à leur expérience Windows complète, à leurs applications, données, sites web et services. La stratégie de Microsoft en matière d’expérience de connexion sans mot de passe est détaillée ici.

Lorsqu’une information d’identification WindowsHello est créée, elle établit une relation de confiance avec un fournisseur d’identité et crée une paire de clés asymétriques pour l’authentification. Un mouvement WindowsHello (tel que la reconnaissance par l’iris ou le code PIN) fournit l’entropie pour déchiffrer une clé privée soutenue par le processeur du Module de plateforme sécurisée (TPM) de l’appareil. Cette clé privée est ensuite utilisée pour signer les demandes envoyées à un serveur d’authentification et une fois l’authentification réussie, l’utilisateur a accès à sa messagerie, à ses photos et à d’autres paramètres de compte. 

Si vous souhaitez obtenir plus d’informations, consultez l’infographie suivante:

  ![Connexion à WindowsHello](images/security-hello-sign-in.png)
  
Dans le graphique présenté ci-dessus, notez que nonce signifie «numéro une seule fois» et est un nombre généré de façon aléatoire ou semi-aléatoire. Une fois que les informations d’identification biométrique ou le code PIN WindowsHello sont configurés, il ne quitte jamais l’appareil sur lequel ils sont configurés. Même si le code PIN WindowsHello de l’utilisateur est volé, par exemple par une attaque d’hameçonnage, il est [inutile sans l’appareil physique de l’utilisateur](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password). 

Pour plus de sécurité, les informations d’identification WindowsHello sont protégées par le Module de plateforme sécurisée (TPM), pour rendre les informations d’identification inviolables, et complétées par des protections anti-martèlement contre plusieurs entrées incorrectes et les logiciels malveillants pour empêcher l’exposition. Si vous souhaitez en savoir plus sur l’authentification unique (SSO), lisez cette [présentation des méthodes SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

L’authentification par reconnaissance de l’iris fonctionne de la même façon que le code PIN. Pour configurer un nouveau code PIN (un authentificateur puissant) sur l’appareil, l’utilisateur doit avoir récemment effectué une [authentification multifacteur (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) afin de terminer le processus.

## Authentification unique avec le gestionnaire de comptes web 

L’authentification unique (SSO) permet aux utilisateurs sans mot de passe de se connecter à l’appareil, en utilisant leur compte personnel, professionnel ou scolaire. L’utilisateur est automatiquement autorisé avec l’authentification unique sur toutes les applications et tous les services intégrés via les [API du gestionnaire de comptes web](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041).

Une fois qu’une identité a été ajoutée via une application, elle peut, avec le consentement de l’utilisateur, devenir disponible pour toutes les applications et tous les services à l’aide de l’intégration au niveau du système. Cela réduit considérablement la charge de connexion à l’application et offre aux utilisateurs une expérience d’identité transparente.

Si vous souhaitez en savoir plus sur l’implémentation des API du gestionnaire de comptes web, accédez à la page [Implémentation des API Web Account Manager](https://docs.microsoft.com/windows/uwp/security/web-account-manager).

  ![Connexion à WindowsHello](images/security-api-img.png)
  
Pour les suites d’applications avec des exigences d’authentification spécialisées, l’infrastructure du gestionnaire de comptes web est extensible aux fournisseurs d’identité personnalisées. Les utilisateurs peuvent télécharger le fournisseur d’identité personnalisé, présenté sous la forme d’une application plateforme Windows universelle (UWP) du Microsoft Store, pour activer l’authentification unique sur d’autres applications intégrées à ce fournisseur d’identité. 

Si vous souhaitez en savoir plus sur l’implémentation de fournisseurs d’identité du gestionnaire de comptes web personnalisés, consultez la page [Référence API du fournisseur d’identité du gestionnaire de comptes web personnalisée](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041).

## Connexion WindowsHello et FIDO2 avec WebAuthn

HoloLens2 peut utiliser les informations d’identification sans mot de passe de l’utilisateur (telles que les clés de sécurité WindowsHello ou FIDO2) pour se connecter en toute sécurité sur le web via MicrosoftEdge et aux sites web qui prennent en charge WebAuthn. FIDO2 permet aux informations d’identification des utilisateurs de profiter des appareils normalisés pour s’authentifier auprès des services en ligne.

> [!Note] 
> Les spécifications [WebAuthn](https://www.w3.org/TR/webauthn/) et FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) sont implémentées dans les services. Les métadonnées signées spécifiées par WebAuthn et FIDO2 fournissent des informations, telles que la présence ou non de l’utilisateur, et vérifient l’authentification via le mouvement local.

Comme avec WindowsHello, lorsque l’utilisateur crée et enregistre des informations d’identification FIDO2, l’appareil (HoloLens2 ou la clé de sécurité FIDO2), génère une clé privée et une clé publique sur l’appareil. La clé privée est stockée en toute sécurité sur l’appareil et ne peut être utilisée qu’après avoir été déverrouillée à l’aide d’un mouvement local tel qu’un code biométrique ou un code PIN. Lorsque la clé privée est stockée, la clé publique est envoyée au système de compte Microsoft dans le cloud et est enregistrée avec le compte d’utilisateur associé.

Une fois connecté avec un compte MSA et AAD, le système envoie un nombre ou une variable de données généré à HoloLens2 ou à l’appareil FIDO2. Le HoloLens2, ou l’appareil, utilise la clé privée pour signer l’identification. L’identification et les métadonnées signées sont renvoyées au système de compte Microsoft et sont vérifiées à l’aide de la clé publique.

Les appareils WindowsHello et FIDO2 implémentent des informations d’identification basées sur l’appareil HoloLens, en particulier l’enclave sécurisée Module de plateforme sécurisée (TPM) intégrée. L’enclave TPM stocke la clé privée et nécessite un code biométrique ou un code PIN pour la déverrouiller. De même, une clé de sécurité FIDO2 est un petit appareil externe avec une enclave sécurisée intégrée qui stocke la clé privée et nécessite un code biométrique ou un code PIN pour la déverrouiller.

Les deux options offrent une authentification à 2 facteurs en une seule étape, nécessitant à la fois un appareil enregistré et un code biométrique ou un code PIN pour se connecter avec succès. Si vous souhaitez en savoir plus, reportez-vous au graphique d’authentification forte avec clé de sécurité FIDO2 qui suit:

  ![img FIDO](images/security-fido2-whfb.png)

MSA et AAD font parties des premières parties à s’appuyer sur l’authentification sans mot de passe en implémentant WebAuthn. 

Si vous souhaitez en savoir plus sur l’utilisation de WebAuthn avec des applications et/ou des SDK, consultez la page [API WebAuthn pour l’authentification sans mot de passe sur Windows10](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis).

## Comptes locaux

Un seul compte local peut être configuré pour les déploiements en mode hors ligne. Les comptes locaux ne sont pas activés par défaut et doivent être configurés lors du provisionnement des appareils. Ils doivent se connecter à l’aide d’un mot de passe et ne prennent pas en charge les méthodes d’authentification alternatives (telles que [WindowsHelloEntreprise](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) ou [WindowsHello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)). 

Si vous souhaitez obtenir plus de détails sur les comptes d’utilisateurs HoloLens, consultez la page [Identité HoloLens](https://docs.microsoft.com/hololens/hololens-identity). 

Les administrateurs informatiques déterminent si l’utilisateur est autorisé à utiliser un compte MSA pour l’authentification et les services de connexion non liés à la messagerie via [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Pour les stratégies de configuration de mot de passe, les stratégies de ralenti et les stratégies d’écran de verrouillage, consultez la page [Verrouillage des appareils](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock). 
