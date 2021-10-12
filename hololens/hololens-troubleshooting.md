---
title: HoloLens Dépannage des appareils
description: restez à jour sur les solutions les plus courantes pour HoloLens les problèmes des appareils et les techniques de dépannage.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problèmes, bogues, dépannage, correction, aide, support, HoloLens, émulateur
ms.openlocfilehash: ceb6f2670b15f46d17a0cb36f6602ae3d4e3ec1d
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800536"
---
# <a name="device-troubleshooting"></a>Dépannage des appareils

cet article explique comment résoudre plusieurs problèmes courants liés au HoloLens.

>[!IMPORTANT]
> Avant d'entamer une procédure de résolution des problèmes, assurez-vous que la batterie de votre appareil est, si possible, chargée à **20 ou 40 %** de sa capacité. Les [témoins](hololens2-setup.md#lights-that-indicate-the-battery-level) situés sous le bouton d'alimentation permettent de vérifier rapidement la capacité de la batterie sans se connecter à l'appareil.

<a id="list"></a>

**Problèmes connus**
- [Chaque fois que la puissance passe à 18%, l’appareil s’arrête soudainement automatiquement](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive l’application UWP ne fonctionne pas pour les utilisateurs Azure AD](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [La vidéo assistance à distance se fige après 20 minutes](#remote-assist-video-freezes-after-20-minutes)
- [La connexion automatique demande une connexion](#auto-login-asks-for-log-in)
- [Microsoft Edge ne parvient pas à démarrer](#microsoft-edge-fails-to-launch)
- [Le clavier ne bascule pas vers les caractères spéciaux](#keyboard-doesnt-switch-to-special-characters)
- [Le téléchargement des fichiers verrouillés n’affiche pas d’erreur](#downloading-locked-files-doesnt-error)
- [Délai de chargement/téléchargement du fichier du portail de l’appareil](#device-portal-file-uploaddownload-times-out)
- [Écran bleu après annulation de l’inscription de la version préliminaire d’Insider sur un appareil flashé avec une build Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive ne charge pas automatiquement les images](#onedrive-doesnt-automatically-upload-pictures)

**Généralités**
- [HoloLens ne répond pas ou ne démarre pas](#hololens-is-unresponsive-or-wont-start)
- [Erreur « espace disque insuffisant »](#low-disk-space-error)
- [Échec de l’étalonnage](#calibration-fails)
- [impossible de se connecter, car mon HoloLens a été configuré précédemment pour quelqu’un d’autre](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity ne fonctionne pas](#unity-isnt-working)
- [Windows Le portail de l’appareil ne fonctionne pas correctement](#windows-device-portal-isnt-working-correctly)
- [le Emulator HoloLens ne fonctionne pas](#the-hololens-emulator-isnt-working)

**Input**
- [Les commandes vocales ne fonctionnent pas](#voice-commands-arent-working)
- [L’entrée manuelle ne fonctionne pas](#hand-input-isnt-working)

**Connectivité**
- [Impossible de se connecter au Wi-Fi](#cant-connect-to-wi-fi)

**Périphériques externes** 
- [les appareils Bluetooth ne sont pas couplés](#bluetooth-devices-arent-pairing)
- [Le microphone USB-C ne fonctionne pas](#usb-c-microphone-isnt-working)
- [les appareils listés comme disponibles dans Paramètres ne fonctionnent pas](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Chaque fois que la puissance passe à 18%, l’appareil s’arrête soudainement automatiquement

Il existe un problème connu connu où, lorsque l’appareil atteint 18% de la batterie, il s’arrête de manière inattendue. Il s’agit d’un problème logiciel, et non d’un problème de matériel ou de batterie. n’échangez donc pas les appareils. Si vous ne savez pas si votre problème correspond à ce bogue, procédez comme suit :

1. Vérifiez que les diagnostics facultatifs sont activés sur vos appareils
1. Reproduire le problème
1. Soumettre un problème de [Hub de commentaires](hololens-feedback.md)
1. Partager l’URL du problème de commentaires
1. [Contacter le support technique](https://aka.ms/hololenssupport)

[Retour à la liste](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive l’application UWP ne fonctionne pas pour les utilisateurs Azure AD

si vous utilisez OneDrive pour l’entreprise à l’aide de votre compte Azure AD, vous avez peut-être rencontré une erreur lors de la connexion à votre application de boîte de réception OneDrive. le fait de ne pas pouvoir se connecter à l’application OneDrive n’affecte pas les chargements automatiques d’images et de vidéos capturés par l’application d’appareil photo. vos fichiers peuvent toujours être enregistrés et accessibles à partir du stockage cloud OneDrive Entreprise. les équipes OneDrive et HoloLens travaillent sur le problème.

### <a name="workarounds"></a>Solutions de contournement

condition préalable : les clients peuvent utiliser Microsoft Edge et le système d’exploitation de l’appareil est mis à jour vers une Windows holographique, 21H1 build ou une version plus récente.

Si vous rencontrez ce problème, essayez l’une des opérations suivantes :

- les utilisateurs peuvent accéder directement à OneDrive For Business à partir de Microsoft Edge et interagir avec leurs fichiers sur le site web à partir de leur navigateur.
- les utilisateurs peuvent installer l’application OneDrive PWA pour HoloLens en la téléchargeant à partir de Microsoft Edge. Cela permettra aux utilisateurs de visualiser et de gérer à nouveau les fichiers sur l’appareil. lisez et suivez ces [instructions pour l’installation de l’application OneDrive PWA sur votre HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Retour à la liste](#list)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>La vidéo assistance à distance se fige après 20 minutes

> [!NOTE]
> Une version plus récente de l’assistance à distance est à l’aide d’un correctif pour résoudre ce problème. Pour éviter ce problème, [Mettez à jour l’assistance à distance](holographic-store-apps.md#update-apps) vers la dernière version.

> [!NOTE]
> en raison de la gravité de ce problème connu, nous avons temporairement suspendu la disponibilité de Windows holographique, version 21H1. La build 21H1 est à nouveau disponible, de sorte que les appareils peuvent être de nouveau mis à jour vers la build 21H1 la plus récente.

sur la dernière version de [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), certains utilisateurs de l’assistance à distance ont subi une congélation vidéo pendant les appels de plus de 20 minutes. Il s’agit d’un **problème connu**.

### <a name="workarounds"></a>Solutions de contournement

Si vous ne parvenez pas à mettre à jour l’assistance à distance vers une version plus récente, essayez la solution suivante.

#### <a name="restart-in-between-calls"></a>Redémarrer entre les appels

Si vos appels repassent une durée de 20 minutes et que vous rencontrez ce problème, essayez de redémarrer votre appareil. Le redémarrage de votre appareil entre les appels d’assistance à distance permet d’actualiser votre appareil et de le remettre dans un état correct.

pour redémarrer rapidement un appareil sur [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ouvrez le menu démarrer, sélectionnez l’icône utilisateur, puis sélectionnez **redémarrer**.

[Retour à la liste](#list)

## <a name="auto-login-asks-for-log-in"></a>La connexion automatique demande une connexion

un appareil HoloLens 2 peut être configuré pour se connecter automatiquement à via les Options de connexion de **Paramètres**  ->  **comptes**  ->   -> et sous **requis** , définissez la valeur sur **jamais**. Certains utilisateurs peuvent être amenés à se connecter à nouveau à l’appareil lors de la mise à jour d’un appareil avec une mise à jour substantielle, telle qu’une mise à jour de fonctionnalité. Il s’agit d’un **problème connu**.

Exemple de cas de figure :

- mise à jour d’un appareil à partir d’Windows holographique, version 2004 (build 19041. xxxx) pour Windows holographique, version 21H1 (build 20346. xxxx)
- mise à jour d’un appareil pour effectuer une mise à jour importante sur la même version majeure, par exemple Windows holographique, version 2004 à Windows holographique, version 20H2
- Mise à jour d’un appareil à partir d’une image de fabrique vers la dernière image

Cela ne doit pas se produire pendant :

- Appareils effectuant une mise à jour de maintenance mensuelle

Contourner les méthodes :

- Méthodes de connexion telles que PIN, mot de passe, IRIS, authentification Web ou clés FIDO2.
- Si le code PIN de l’appareil ne peut pas être mémorisé et que d’autres méthodes d’authentification ne sont pas disponibles, un utilisateur peut utiliser le mode de reverrouillage [Manuel](hololens-recovery.md#manual-procedure).

[Retour à la liste](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge ne parvient pas à démarrer

> [!NOTE]
> ce problème a été créé à l’origine avec la version d’expédition de Microsoft Edge à l’esprit. Ce problème peut être résolu dans le [nouveau Microsoft Edge](hololens-new-edge.md). Si ce n’est pas le cas, veuillez envoyer un commentaire.

quelques clients ont signalé un problème où Microsoft Edge ne peut pas démarrer. pour ces clients, le problème persiste via le redémarrage et n’est pas résolu avec les mises à jour de Windows ou d’application. si vous rencontrez ce problème et que vous avez confirmé que [Windows est à jour](hololens-updates.md#manually-check-for-updates), veuillez signaler un bogue à partir de l' [application Hub de commentaires](hololens-feedback.md) avec la catégorie et la sous-catégorie suivantes : installer et mettre à jour > téléchargement, installation et configuration de Windows Update.

Il n’existe aucune solution de contournement connue, car nous n’avons pas pu générer le problème jusqu’à présent. L’enregistrement d’un bogue via Feedback Hub vous aide à effectuer notre investigation. Il s’agit d’un **problème connu**.

[Retour à la liste](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Le clavier ne bascule pas vers les caractères spéciaux

Il y a un problème au cours de l’OOBE, où une fois que l’utilisateur a choisi un compte professionnel ou scolaire et qu’il entre son mot de passe, en tentant de basculer vers les caractères spéciaux du clavier en appuyant sur le bouton &123 ne devient pas un caractère spécial. Il s’agit d’un **problème connu**.

Solution de contournement :

- Fermez le clavier et rouvrez-le en appuyant sur le champ de texte.
- Entrez votre mot de passe de manière incorrecte. La prochaine fois que le clavier est relancé, il fonctionnera comme prévu.
- Authentification Web, fermez le clavier et sélectionnez **se connecter à partir d’un autre appareil**.
- Si vous entrez uniquement des chiffres, un utilisateur peut appuyer sur certaines touches et les maintenir enfoncé pour ouvrir un menu développé.
- À l’aide d’un clavier USB.

Cela n’affecte pas les éléments suivants :

- Utilisateurs qui choisissent d’utiliser un compte personnel.

[Retour à la liste](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Le téléchargement des fichiers verrouillés n’est pas une erreur

> [!NOTE]
> il s’agit d’un **problème connu** qui a été résolu dans [Windows holographique, version 21H1-mise à jour 2021 de juillet](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

dans les versions précédentes de Windows holographique, lorsque vous tentez de télécharger un fichier verrouillé, le résultat est une page d’erreur HTTP. dans la Windows holographique, version 21H1 update, si vous tentez de télécharger un fichier verrouillé, rien n’est visible : le fichier n’est pas téléchargé et il n’y a pas d’erreur.

[Retour à la liste](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Délai de chargement/téléchargement du fichier du portail de l’appareil
> [!NOTE]
> il s’agit d’un **problème connu** qui a été résolu dans [Windows holographique, version 21H1-mise à jour 2021 de juillet](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Si vous avez précédemment désactivé la connexion SSL dans le cadre de la solution de contournement, nous vous recommandons vivement de la réactiver.

Certains clients ont trouvé, lors de la tentative de chargement ou de téléchargement de fichiers, l’opération peut sembler bloquée, puis expirer ou ne jamais se terminer. cela est indépendant du[problème connu « fichier verrouillé »](#downloading-locked-files-doesnt-error) , ce qui affecte Windows les versions 2004, 20H2 et 21H1 de la version commercialisée. Le problème est dû à un bogue dans la gestion par le portail de l’appareil de certaines demandes et est le plus souvent utilisé lors de l’utilisation du protocole HTTPS, qui est la valeur par défaut.

### <a name="workaround"></a>Solution de contournement

Cette solution de contournement, qui s’applique également à Wi-Fi et UsbNcm, consiste à désactiver l’option « obligatoire » sous « connexion SSL ». Pour ce faire, accédez au portail de l’appareil, au **système**, puis sélectionnez la page **Préférences** . Dans la section sécurité de l' **appareil** , localisez la **connexion SSL**, puis désactivez la case à cocher **.**

L’utilisateur doit ensuite accéder à http://, et non https://(adresse IP) et des fonctionnalités telles que le chargement et le téléchargement de fichiers fonctionnent.

[Retour à la liste](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Écran bleu après annulation de l’inscription de la version préliminaire d’Insider sur un appareil flashé avec une build Insider

il s’agit d’un problème affectant les utilisateurs qui se trouvaient sur une version d’évaluation d’insider, de rééclairer leurs HoloLens 2 avec une nouvelle build insider preview, puis désinscrit du programme insider. Il s’agit d’un **problème connu**.

Cela n’affecte pas les éléments suivants :

- utilisateurs qui ne sont pas inscrits à Windows insider
- Insiders
    - Si un appareil a été inscrit depuis la version des builds Insider 18362. x
    - S’ils ont flashé une build 19041. x signée à l’intérieur et restent inscrits dans le programme d’Insider

Solution de contournement :

- Éviter le problème
    - Flashez une génération non Insider. L’une des mises à jour mensuelles régulières.
    - Restez sur la version préliminaire d’Insider
- Refaire clignoter l’appareil

    1. mettez manuellement le [HoloLens 2 en mode clignotant](hololens-recovery.md) en l’arrêtant tout en étant connecté. Puis, tout en maintenant le volume enfoncé, appuyez sur le bouton d’alimentation.

    1. Connecter au PC et ouvrez le guide de récupération avancée.

    1. flashez le HoloLens 2 à la build par défaut.

[Retour à la liste](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive ne charge pas automatiquement les images

l’application OneDrive pour HoloLens ne prend pas en charge le chargement automatique de l’appareil photo pour les comptes professionnels ou scolaires. Il s’agit d’un **problème connu**.

Solutions de contournement :

- Si vous êtes viable pour votre entreprise, le chargement automatique de l’appareil photo est pris en charge sur les comptes Microsoft. vous pouvez vous connecter à votre compte Microsoft en plus de votre compte professionnel ou scolaire (l’application OneDrive prend en charge la connexion double). à partir de votre profil de compte Microsoft dans OneDrive vous pouvez activer le chargement automatique de l’appareil photo en arrière-plan.

- si vous ne pouvez pas utiliser un compte Microsoft consommateur en toute sécurité pour télécharger vos photos automatiquement, vous pouvez charger manuellement des photos sur votre compte professionnel ou scolaire à partir de l’application OneDrive. pour ce faire, assurez-vous que vous êtes connecté à votre compte professionnel ou scolaire dans l’application OneDrive. sélectionnez le **+** bouton, puis choisissez **Télécharger**. Recherchez les photos ou vidéos que vous souhaitez télécharger en accédant à **images > pellicule**. Sélectionnez les photos ou vidéos que vous souhaitez télécharger, puis cliquez sur le bouton **ouvrir** .

[Retour à la liste](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens ne répond pas ou ne démarre pas

si votre HoloLens ne démarre pas :

- Si les voyants situés à côté du bouton d’alimentation ne s’allument pas, ou si un seul LED clignote brièvement, vous devrez peut-être [charger votre HoloLens.](hololens2-charging.md#charging-the-device)
- Si les voyants s’allument lorsque vous appuyez sur le bouton d’alimentation mais que vous ne voyez rien dans les affichages, [effectuez une réinitialisation matérielle de l’appareil](hololens-recovery.md#hard-reset-procedure).

si votre HoloLens devient figé ou ne répond pas :

- éteignez votre HoloLens en appuyant sur le bouton d’alimentation jusqu’à ce que les cinq led soient désactivées ou pendant 15 secondes si les led ne répondent pas. pour démarrer votre HoloLens, appuyez de nouveau sur le bouton d’alimentation.

si ces étapes ne fonctionnent pas, vous pouvez essayer [de récupérer votre appareil HoloLens 2 ou votre](hololens-recovery.md) appareil [HoloLens (1er génération).](hololens1-recovery.md)

[Retour à la liste](#list)

## <a name="low-disk-space-error"></a>Erreur « espace disque insuffisant »

Vous devez libérer de l’espace de stockage en exécutant une ou plusieurs des opérations suivantes :

- Supprimez des espaces inutilisés. accédez à **Paramètres**  >    >  **espaces** système, sélectionnez un espace dont vous n’avez plus besoin, puis sélectionnez **supprimer**.
- Retirez certains des hologrammes que vous avez placés.
- supprimez des images et des vidéos de l’application Photos.
- Désinstallez des applications de votre HoloLens. Dans la liste **toutes les applications** , appuyez sur l’application que vous souhaitez désinstaller, maintenez-la enfoncée, puis sélectionnez **désinstaller**.

[Retour à la liste](#list)

## <a name="calibration-fails"></a>Échec de l’étalonnage

L’étalonnage doit fonctionner pour la plupart des gens, mais dans certains cas, l’étalonnage échoue.
  
Les raisons possibles de l’échec de l’étalonnage sont les suivantes :

- Se détourner et ne pas suivre les objectifs d’étalonnage
- Visière d’appareil sale ou rayé ou visière d’appareil non positionné correctement
- Verres sale ou rayé
- Certains types de lentilles et de lunettes de contact (lentilles de contact colorées, certaines lentilles de contact Toric, lunettes de blocage IR, des verres de prescription élevés, des lunettes de soleil ou similaires)
- Composition plus prononcée et certaines extensions cils
- Des cheveux ou des montures de lunettes épaisses s’ils empêchent l’appareil de voir vos yeux
- Une certaine physiologie, des conditions oculaires ou une chirurgie oculaire comme des yeux étroits, des cils longs, amblyopia, nystagmus, certains cas de LASIK ou d’autres Surgeries oculaires

Si l’étalonnage échoue, essayez :

- Nettoyage de votre visière d’appareils
- Nettoyage de vos lunettes
- Poussez vos visières d’appareils aussi près que possible de vos yeux
- Déplacement d’objets dans votre visière (par exemple, cheveux)
- Activation d’une lumière dans votre pièce ou déplacement hors du soleil

si vous avez suivi toutes les instructions et que l’étalonnage est toujours en échec, vous pouvez désactiver l’invite d’étalonnage dans Paramètres. Faites-nous également part de vos commentaires dans le [Hub de commentaires](hololens-feedback.md).

Consultez également les informations connexes pour la [résolution des problèmes de couleur d’image ou de luminosité.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

la définition de l’IPD ne s’applique pas aux HoloLens 2, car les positions oculaires sont calculées par le système. 

[Retour à la liste](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>impossible de se connecter, car mon HoloLens a été configuré précédemment pour quelqu’un d’autre

Vous pouvez [mettre l’appareil en **mode clignotant** et utiliser le compagnon de récupération avancé](hololens-recovery.md#clean-reflash-the-device) pour récupérer l’appareil.

[Retour à la liste](#list)


## <a name="unity-isnt-working"></a>Unity ne fonctionne pas

- consultez [installer les outils](/windows/mixed-reality/install-the-tools) pour la version la plus récente d’unity recommandée pour le développement de HoloLens.
- les problèmes connus avec unity HoloLens Technical Preview sont documentés dans les [forums HoloLens unity](https://forum.unity3d.com/threads/known-issues.394627/).

[Retour à la liste](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Le portail de l’appareil ne fonctionne pas correctement

- La fonctionnalité d’aperçu instantané de la capture de la réalité mixte peut présenter plusieurs secondes de latence.

- Sur la page d’entrée virtuelle, les contrôles de mouvement et de défilement sous la section des mouvements virtuels ne sont pas fonctionnels. Leur utilisation n’aura aucun effet. Le clavier virtuel sur la page d’entrée virtuelle fonctionne correctement.

- après avoir activé le Mode développeur dans Paramètres, la mise sous tension du portail de l’appareil peut prendre quelques secondes.

[Retour à la liste](#list)

## <a name="the-hololens-emulator-isnt-working"></a>le Emulator HoloLens ne fonctionne pas

les informations relatives à l’émulateur HoloLens se trouvent dans la documentation du développeur.  en savoir plus sur [le dépannage de l’émulateur de HoloLens](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


- toutes les applications dans le Microsoft Store ne sont pas compatibles avec l’émulateur. Par exemple, les Conker et les fragments de Young ne sont pas lisibles sur l’émulateur.
- Vous ne pouvez pas utiliser la Webcam PC dans le Emulator.
- la fonctionnalité d’aperçu instantané du portail des appareils Windows ne fonctionne pas avec l’émulateur. Vous pouvez toujours capturer des vidéos et des images de réalité mixte.

[Retour à la liste](#list)

## <a name="voice-commands-arent-working"></a>Les commandes vocales ne fonctionnent pas

si Cortana ne répond pas à vos commandes vocales, vérifiez que Cortana est activé. dans la liste toutes les applications, sélectionnez **Cortana**  >    >  Paramètres **bloc-notes**  >   pour apporter des modifications. Pour en savoir plus sur ce que vous pouvez prononcer, consultez [utiliser votre voix avec HoloLens](hololens-cortana.md).

sur HoloLens (1re génération), la reconnaissance vocale intégrée n’est pas configurable. Il est toujours activé. sur HoloLens 2, vous pouvez choisir d’activer la reconnaissance vocale et les Cortana lors de la configuration de l’appareil.

si votre HoloLens 2 ne répond pas à votre voix, vérifiez que la reconnaissance vocale est activée. accédez à **démarrer**  >  **Paramètres** la  >    >  **voix** sur la confidentialité et activez la **reconnaissance vocale**.

[Retour à la liste](#list)

## <a name="hand-input-isnt-working"></a>L’entrée manuelle ne fonctionne pas

pour vous assurer que HoloLens pouvez voir vos mains, vous devez les conserver dans le cadre de mouvement.  La page d’hébergement de la réalité mixte fournit des commentaires qui vous permettent de savoir quand vos mains sont suivies.  Les commentaires sont différents sur les différentes versions de HoloLens :

- sur HoloLens (1re génération), le curseur en regard passe d’un point à un anneau
- sur HoloLens 2, un curseur à main s’affiche lorsque la main est proche d’un ardoise, et un rayon de la main apparaît lorsque les ardoises sont éloignées

De nombreuses applications immersifs suivent des modèles d’entrée similaires à la réalité mixte.  en savoir plus sur l’utilisation de la saisie manuelle sur [HoloLens (1er génération)](hololens1-basic-usage.md#use-hololens-with-your-hands) et [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si vous portez des gants, Notez que certains types de gants ne fonctionnent pas avec le suivi des mains.  Un exemple courant est le noir en caoutchouc, qui a tendance à absorber la lumière infrarouge et n’est pas récupéré par l’appareil photo de profondeur.  Si votre travail implique des gants en caoutchouc, nous vous recommandons d’essayer une couleur plus claire, telle que le bleu ou le gris.  Un autre exemple est un grand gants Baggy, qui a tendance à obscurcir la forme de votre main. Nous vous recommandons d’utiliser les gants qui sont aussi adaptés à la forme que possible pour des résultats optimaux.

si votre visière présente des empreintes digitales ou des taches, utilisez le chiffon de nettoyage microfiber fourni avec le HoloLens pour nettoyer doucement votre visière.

[Retour à la liste](#list)

## <a name="cant-connect-to-wi-fi"></a>Impossible de se connecter à Wi-Fi

Si vous ne parvenez pas à connecter votre HoloLens à un réseau Wi-Fi, vous pouvez essayer ce qui suit :

- Vérifiez que le Wi-Fi est activé. pour vérifier, utilisez le mouvement démarrer, puis sélectionnez **Paramètres**  >  **réseau &amp; Internet**  >  **Wi-Fi**. Si le Wi-Fi est activé, essayez de le désactiver puis de le réactiver.
- Rapprochez-vous du routeur ou du point d'accès.
- Redémarrez votre routeur Wi-Fi, puis [redémarrez HoloLens](hololens-recovery.md). Réessayez de vous connecter.
- Si le problème persiste, vérifiez que votre routeur utilise le microprogramme le plus récent. Cette information est disponible sur le site web du fabricant.

[Retour à la liste](#list)

## <a name="bluetooth-devices-arent-pairing"></a>les appareils Bluetooth ne sont pas couplés

si vous rencontrez des problèmes pour [associer un appareil Bluetooth](hololens-connect-devices.md), procédez comme suit :

- accédez à **Paramètres**  >  **appareils** et assurez-vous que Bluetooth est activé. Si c’est le cas, éteignez-le et réactivez-le.
- assurez-vous que votre appareil Bluetooth est entièrement chargé ou qu’il contient des piles neuves.
- Si vous ne pouvez toujours pas vous connecter, [Redémarrez le HoloLens](hololens-recovery.md).

[Retour à la liste](#list)

## <a name="usb-c-microphone-isnt-working"></a>Le microphone USB-C ne fonctionne pas

Sachez que certains microtéléphones USB-C se signalent incorrectement comme un microphone *et* un orateur. Il s’agit d’un problème avec le microphone et pas avec HoloLens. lors du branchement de l’un de ces microphones dans HoloLens, le son peut être perdu. Heureusement, il existe un correctif simple.  

dans **Paramètres**  ->    ->  **son** système, définissez explicitement les haut-parleurs intégrés **(pilote Audio de fonctionnalité analogique)** comme **périphérique par défaut**. HoloLens mémoriser ce paramètre même si le microphone est supprimé et reconnecté ultérieurement.

![Résolution des problèmes de microtéléphones USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>les appareils listés comme disponibles dans Paramètres ne fonctionnent pas

HoloLens (1re génération) ne prend pas en charge les profils audio Bluetooth. Bluetooth les périphériques audio, tels que les haut-parleurs et les casques, peuvent apparaître comme étant disponibles dans les paramètres de HoloLens, mais ils ne sont pas pris en charge.

HoloLens 2 prend en charge le profil audio A2DP Bluetooth pour la lecture stéréo. le profil Bluetooth mains libres qui permet la capture du microphone à partir d’un périphérique Bluetooth n’est pas pris en charge sur HoloLens 2.

si vous rencontrez des problèmes lors de l’utilisation d’un appareil Bluetooth, assurez-vous qu’il s’agit d’un appareil pris en charge. Les appareils pris en charge sont les suivants :

- claviers en anglais Bluetooth QWERTY (vous pouvez les utiliser partout où vous utilisez le clavier holographique).
- Bluetooth souris.
- [cliquez sur le HoloLens](hololens1-clicker.md).

vous pouvez associer d’autres appareils Bluetooth HID et GATT à vos HoloLens. toutefois, vous devrez peut-être installer les applications auxiliaires correspondantes à partir de Microsoft Store pour utiliser réellement les appareils.

[Retour à la liste](#list)
