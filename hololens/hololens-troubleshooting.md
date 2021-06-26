---
title: Résolution des problèmes des appareils HoloLens
description: Restez à jour sur les solutions les plus courantes aux problèmes liés aux appareils HoloLens et aux techniques de dépannage.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problèmes, bogue, dépannage, correction, aide, support, HoloLens, émulateur
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924619"
---
# <a name="device-troubleshooting"></a>Dépannage des appareils

Cet article explique comment résoudre plusieurs problèmes courants liés à HoloLens.

>[!IMPORTANT]
> Avant de commencer une procédure de résolution des problèmes, assurez-vous que votre appareil est facturé à **20 à 40%** de la capacité de la batterie, si possible. Les [voyants](hololens2-setup.md#lights-that-indicate-the-battery-level) de la batterie situés sous le bouton d’alimentation constituent un moyen rapide de vérifier la capacité de la batterie sans se connecter à l’appareil.

<a id="list"></a>

**Problèmes connus**
- [La vidéo assistance à distance se fige après 20 minutes](#remote-assist-video-freezes-after-20-minutes)
- [La connexion automatique demande une connexion](#auto-login-asks-for-log-in)
- [Échec du lancement de Microsoft Edge](#microsoft-edge-fails-to-launch)
- [Le clavier ne bascule pas vers les caractères spéciaux](#keyboard-doesnt-switch-to-special-characters)
- [Le téléchargement des fichiers verrouillés n’affiche pas d’erreur](#downloading-locked-files-doesnt-error)
- [Délai de chargement/téléchargement du fichier du portail de l’appareil](#device-portal-file-uploaddownload-times-out)
- [Écran bleu après annulation de l’inscription de la version préliminaire d’Insider sur un appareil flashé avec une build Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive ne charge pas automatiquement les images](#onedrive-doesnt-automatically-upload-pictures)

**Général**
- [HoloLens ne répond pas ou ne démarre pas](#hololens-is-unresponsive-or-wont-start)
- [Erreur « espace disque insuffisant »](#low-disk-space-error)
- [Échec de l’étalonnage](#calibration-fails)
- [Impossible de se connecter, car mon HoloLens a été configuré précédemment pour quelqu’un d’autre](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity ne fonctionne pas](#unity-isnt-working)
- [Le portail des appareils Windows ne fonctionne pas correctement](#windows-device-portal-isnt-working-correctly)
- [L’émulateur HoloLens ne fonctionne pas](#the-hololens-emulator-isnt-working)

**Input**
- [Les commandes vocales ne fonctionnent pas](#voice-commands-arent-working)
- [L’entrée manuelle ne fonctionne pas](#hand-input-isnt-working)

**Connectivité**
- [Impossible de se connecter au Wi-Fi](#cant-connect-to-wi-fi)

**Périphériques externes** 
- [Les appareils Bluetooth ne sont pas couplés](#bluetooth-devices-arent-pairing)
- [Le microphone USB-C ne fonctionne pas](#usb-c-microphone-isnt-working)
- [Les appareils listés comme disponibles dans les paramètres ne fonctionnent pas](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>La vidéo assistance à distance se fige après 20 minutes

> [!NOTE]
> En raison de la gravité de ce problème connu, nous avons actuellement suspendu la disponibilité de Windows holographique, version 21H1. Si vous souhaitez toujours mettre à jour vos appareils vers 21H1, reportez-vous aux [instructions figurant dans les notes de publication en haut de la page.](hololens-release-notes.md)

Sur la dernière version de [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), certains utilisateurs de l’assistance à distance ont subi une congélation vidéo pendant les appels de plus de 20 minutes. Il s’agit d’un **problème connu**.

### <a name="workarounds"></a>Solutions de contournement

#### <a name="restart-in-between-calls"></a>Redémarrer entre les appels

Si vos appels repassent une durée de 20 minutes et que vous rencontrez ce problème, essayez de redémarrer votre appareil. Le redémarrage de votre appareil entre les appels d’assistance à distance permet d’actualiser votre appareil et de le remettre dans un état correct.

Pour redémarrer rapidement un appareil sur [Windows holographique, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) Ouvrez le menu Démarrer, sélectionnez l’icône utilisateur, puis sélectionnez **redémarrer**.

#### <a name="revert-to-an-older-build"></a>Revenir à une version antérieure

Certains clients ont découvert qu’en restaurant une version antérieure du système d’exploitation, ils ne rencontrent plus ce problème. Si vous avez détecté que vos appareils rencontrent ce problème, essayez les étapes suivantes :


Solutions de contournement :

- Si vous êtes viable pour votre entreprise, le chargement automatique de l’appareil photo est pris en charge sur les comptes Microsoft. Vous pouvez vous connecter à votre compte Microsoft en plus de votre compte professionnel ou scolaire (l’application OneDrive prend en charge la connexion double). À partir de votre profil de compte Microsoft dans OneDrive, vous pouvez activer le chargement automatique de l’appareil photo en arrière-plan.

- Si vous ne pouvez pas utiliser un compte Microsoft consommateur en toute sécurité pour télécharger vos photos automatiquement, vous pouvez charger manuellement des photos sur votre compte professionnel ou scolaire à partir de l’application OneDrive. Pour ce faire, assurez-vous que vous êtes connecté à votre compte professionnel ou scolaire dans l’application OneDrive. Sélectionnez le **+** bouton et choisissez **Télécharger**. Recherchez les photos ou vidéos que vous souhaitez télécharger en accédant à **images > pellicule**. Sélectionnez les photos ou vidéos que vous souhaitez télécharger, puis cliquez sur le bouton **ouvrir** .


1. [Télécharger la build pour Windows holographique, version 20H2 – mai 2021 Update](https://aka.ms/hololens2download/10.0.19041.1146)
1. Suivez les [instructions pour revenir à une version précédente du système d’exploitation](hololens-update-hololens.md#go-back-to-a-previous-version)
1. [Suspendez les mises à jour du système d’exploitation sur l’appareil manuellement](hololens-updates.md#pause-updates-via-device) ou, pour de nombreux appareils, utilisez le [Report via MDM](hololens-updates.md#configure-an-update-deferral-policy).

[Retour à la liste](#list)

## <a name="auto-login-asks-for-log-in"></a>La connexion automatique demande une connexion

Un appareil HoloLens 2 peut être configuré pour se connecter automatiquement à via les **paramètres**  ->    ->  **options de connexion** de comptes-> et sous **obligatoire** , définissez la valeur sur **jamais**. Certains utilisateurs peuvent être amenés à se connecter à nouveau à l’appareil lors de la mise à jour d’un appareil avec une mise à jour substantielle, telle qu’une mise à jour de fonctionnalité. Il s’agit d’un **problème connu**.

Exemple de cas de figure :

- Mise à jour d’un appareil à partir de Windows holographique, version 2004 (Build 19041. xxxx) vers Windows holographique, version 21H1 (Build 20346. xxxx)
- Mise à jour d’un appareil pour effectuer une mise à jour importante sur la même version majeure, par exemple Windows holographique, version 2004 vers Windows holographique, version 20H2
- Mise à jour d’un appareil à partir d’une image de fabrique vers la dernière image

Cela ne doit pas se produire pendant :

- Appareils effectuant une mise à jour de maintenance mensuelle

Contourner les méthodes :

- Méthodes de connexion telles que PIN, mot de passe, IRIS, authentification Web ou clés FIDO2.
- Si le code PIN de l’appareil ne peut pas être mémorisé et que d’autres méthodes d’authentification ne sont pas disponibles, un utilisateur peut utiliser le mode de reverrouillage [Manuel](hololens-recovery.md#manual-procedure).

[Retour à la liste](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Échec du lancement de Microsoft Edge

> [!NOTE]
> Ce problème a été créé à l’origine avec la version d’expédition de Microsoft Edge à l’esprit. Ce problème peut être résolu dans le [nouveau Microsoft Edge](hololens-new-edge.md). Si ce n’est pas le cas, veuillez envoyer un commentaire.

Quelques clients ont signalé un problème où le lancement de Microsoft Edge a échoué. Pour ces clients, le problème persiste via le redémarrage et n’est pas résolu avec les mises à jour de Windows ou d’application. Si vous rencontrez ce problème et que vous avez confirmé que [Windows est à jour](hololens-updates.md#manually-check-for-updates), veuillez signaler un bogue à partir de l' [application Hub de commentaires](hololens-feedback.md) avec la catégorie et la sous-catégorie suivantes : installer et mettre à jour > le téléchargement, l’installation et la configuration de Windows Update.

Il n’existe aucune solution de contournement connue, car nous n’avons pas pu générer le problème jusqu’à présent. L’enregistrement d’un bogue via Feedback Hub vous aide à effectuer notre investigation. Il s’agit d’un **problème connu**.

[Retour à la liste](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Le clavier ne bascule pas vers les caractères spéciaux

Il y a un problème au cours de l’OOBE, où une fois que l’utilisateur a choisi un compte professionnel ou scolaire et qu’il entre son mot de passe, en tentant de basculer vers les caractères spéciaux du clavier en appuyant sur le bouton &123 ne devient pas un caractère spécial. Il s’agit d’un **problème connu**.

Solution de contournement :
-   Fermez le clavier et rouvrez-le en appuyant sur le champ de texte.
-   Entrez votre mot de passe de manière incorrecte. La prochaine fois que le clavier est relancé, il fonctionnera comme prévu.
- Authentification Web, fermez le clavier et sélectionnez **se connecter à partir d’un autre appareil**.
-   Si vous entrez uniquement des chiffres, un utilisateur peut appuyer sur certaines touches et les maintenir enfoncé pour ouvrir un menu développé.
-   À l’aide d’un clavier USB.

Cela n’affecte pas les éléments suivants :
- Utilisateurs qui choisissent d’utiliser un compte personnel.

[Retour à la liste](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Le téléchargement des fichiers verrouillés n’est pas une erreur
> ! Notez qu’il s’agit d’un **problème connu** qui est résolu dans Windows Insider Build, version 20348,1403.


Dans les versions précédentes de Windows holographique, lorsque vous tentez de télécharger un fichier verrouillé, le résultat est une page d’erreur HTTP. Dans Windows holographique, version 21H1 Update, si vous tentez de télécharger un fichier verrouillé, rien n’est visible : le fichier n’est pas téléchargé et il n’y a pas d’erreur. 

[Retour à la liste](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Délai de chargement/téléchargement du fichier du portail de l’appareil
> ! Notez qu’il s’agit d’un **problème connu** qui est résolu dans Windows Insider Build, version 20348,1403. Si vous avez précédemment désactivé la connexion SSL dans le cadre de la solution de contournement, nous vous recommandons vivement de la réactiver.


Certains clients ont trouvé, lors de la tentative de chargement ou de téléchargement de fichiers, l’opération peut sembler bloquée, puis expirer ou ne jamais se terminer. Cela est indépendant du[problème connu « fichier verrouillé »](#downloading-locked-files-doesnt-error) . cela affecte les versions 2004, 20H2 et 21H1 de Windows holographique. Le problème est dû à un bogue dans la gestion par le portail de l’appareil de certaines demandes et est le plus souvent utilisé lors de l’utilisation du protocole HTTPS, qui est la valeur par défaut. 

### <a name="workaround"></a>Solution de contournement

Cette solution de contournement, qui s’applique également à Wi-Fi et UsbNcm, consiste à désactiver l’option « obligatoire » sous « connexion SSL ». Pour ce faire, accédez au portail de l’appareil, au **système**, puis sélectionnez la page **Préférences** . Dans la section sécurité de l' **appareil** , localisez la **connexion SSL**, puis désactivez la case à cocher **.**

L’utilisateur doit ensuite accéder à http://, et non https://(adresse IP) et des fonctionnalités telles que le chargement et le téléchargement de fichiers fonctionnent.

[Retour à la liste](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Écran bleu après annulation de l’inscription de la version préliminaire d’Insider sur un appareil flashé avec une build Insider

Il s’agit d’un problème affectant les utilisateurs qui se trouvaient sur une version d’évaluation d’Insider, de rééclairer HoloLens 2 avec une nouvelle build Insider Preview, puis désinscrit du programme Insider. Il s’agit d’un **problème connu**.

Cela n’affecte pas les éléments suivants :
- Utilisateurs qui ne sont pas inscrits à Windows Insider 
- Insiders
    - Si un appareil a été inscrit depuis la version des builds Insider 18362. x
    - S’ils ont flashé une build 19041. x signée à l’intérieur et restent inscrits dans le programme d’Insider

Solution de contournement : 
- Éviter le problème 
    - Flashez une génération non Insider. L’une des mises à jour mensuelles régulières.
    - Restez sur la version préliminaire d’Insider
- Refaire clignoter l’appareil

    1. Mettez manuellement le [HoloLens 2 en mode clignotant](hololens-recovery.md) en l’arrêtant tout en étant connecté. Puis, tout en maintenant le volume enfoncé, appuyez sur le bouton d’alimentation.
    
    1. Connectez-vous à l’ordinateur et ouvrez le compagnon de récupération avancée.
    
    1. Flasher HoloLens 2 à la build par défaut.

[Retour à la liste](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive ne charge pas automatiquement les images

L’application OneDrive pour HoloLens ne prend pas en charge le chargement automatique de l’appareil photo pour les comptes professionnels ou scolaires. Il s’agit d’un **problème connu**.

Solutions de contournement :

- Si vous êtes viable pour votre entreprise, le chargement automatique de l’appareil photo est pris en charge sur les comptes Microsoft. Vous pouvez vous connecter à votre compte Microsoft en plus de votre compte professionnel ou scolaire (l’application OneDrive prend en charge la connexion double). À partir de votre profil de compte Microsoft dans OneDrive, vous pouvez activer le chargement automatique de l’appareil photo en arrière-plan.

- Si vous ne pouvez pas utiliser un compte Microsoft consommateur en toute sécurité pour télécharger vos photos automatiquement, vous pouvez charger manuellement des photos sur votre compte professionnel ou scolaire à partir de l’application OneDrive. Pour ce faire, assurez-vous que vous êtes connecté à votre compte professionnel ou scolaire dans l’application OneDrive. Sélectionnez le **+** bouton et choisissez **Télécharger**. Recherchez les photos ou vidéos que vous souhaitez télécharger en accédant à **images > pellicule**. Sélectionnez les photos ou vidéos que vous souhaitez télécharger, puis cliquez sur le bouton **ouvrir** .

[Retour à la liste](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens ne répond pas ou ne démarre pas

Si votre HoloLens ne démarre pas :

- Si les voyants situés à côté du bouton d’alimentation ne s’allument pas, ou si un seul LED clignote brièvement, vous devrez peut-être [charger votre HoloLens.](hololens2-charging.md#charging-the-device)
- Si les voyants s’allument lorsque vous appuyez sur le bouton d’alimentation mais que vous ne voyez rien dans les affichages, [effectuez une réinitialisation matérielle de l’appareil](hololens-recovery.md#hard-reset-procedure).

Si votre HoloLens est gelé ou ne répond pas :

- Éteignez votre HoloLens en appuyant sur le bouton d’alimentation jusqu’à ce que les cinq LED soient désactivées ou pendant 15 secondes si les LED ne répondent pas. Pour démarrer votre HoloLens, appuyez de nouveau sur le bouton d’alimentation.

Si ces étapes ne fonctionnent pas, vous pouvez essayer [de récupérer votre appareil hololens 2 ou votre](hololens-recovery.md) [appareil hololens (1er génération).](hololens1-recovery.md)

[Retour à la liste](#list)

## <a name="low-disk-space-error"></a>Erreur « espace disque insuffisant »

Vous devez libérer de l’espace de stockage en exécutant une ou plusieurs des opérations suivantes :

- Supprimez des espaces inutilisés. Accédez à **paramètres**  >    >  **espaces** système, sélectionnez un espace dont vous n’avez plus besoin, puis sélectionnez **supprimer**.
- Retirez certains des hologrammes que vous avez placés.
- Supprimez des images et des vidéos de l’application photos.
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

Si vous avez suivi toutes les instructions et que l’étalonnage est toujours en échec, vous pouvez désactiver l’invite d’étalonnage dans paramètres. Faites-nous également part de vos commentaires dans le [Hub de commentaires](hololens-feedback.md).

Consultez également les informations connexes pour la [résolution des problèmes de couleur d’image ou de luminosité.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

La définition de IPD n’est pas applicable à HoloLens 2, car les positions oculaires sont calculées par le système. 

[Retour à la liste](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Impossible de se connecter, car mon HoloLens a été configuré précédemment pour quelqu’un d’autre

Vous pouvez [mettre l’appareil en **mode clignotant** et utiliser le compagnon de récupération avancé](hololens-recovery.md#clean-reflash-the-device) pour récupérer l’appareil.

[Retour à la liste](#list)


## <a name="unity-isnt-working"></a>Unity ne fonctionne pas

- Consultez [installer les outils](/windows/mixed-reality/install-the-tools) pour la version la plus à jour d’Unity recommandée pour le développement HoloLens.
- Les problèmes connus avec Unity HoloLens Technical Preview sont documentés dans les [Forums Hololens Unity](https://forum.unity3d.com/threads/known-issues.394627/).

[Retour à la liste](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Le portail des appareils Windows ne fonctionne pas correctement

- La fonctionnalité d’aperçu instantané de la capture de la réalité mixte peut présenter plusieurs secondes de latence.

- Sur la page d’entrée virtuelle, les contrôles de mouvement et de défilement sous la section des mouvements virtuels ne sont pas fonctionnels. Leur utilisation n’aura aucun effet. Le clavier virtuel sur la page d’entrée virtuelle fonctionne correctement.

- Après l’activation du mode développeur dans les paramètres, l’activation du commutateur Device Portal peut prendre quelques secondes.

[Retour à la liste](#list)

## <a name="emulator"></a>Émulateur
### <a name="the-hololens-emulator-isnt-working"></a>L’émulateur HoloLens ne fonctionne pas

Des informations sur l’émulateur HoloLens se trouvent dans la documentation du développeur.  En savoir plus sur [le dépannage de l’émulateur HoloLens](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).


- Toutes les applications dans le Microsoft Store ne sont pas compatibles avec l’émulateur. Par exemple, les Conker et les fragments de Young ne sont pas lisibles sur l’émulateur.
- Vous ne pouvez pas utiliser la webcam de l’ordinateur dans l’émulateur.
- La fonctionnalité d’aperçu instantané du portail de périphériques Windows ne fonctionne pas avec l’émulateur. Vous pouvez toujours capturer des vidéos et des images de réalité mixte.

[Retour à la liste](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Je ne trouve pas ou n’utilise pas le clavier pour taper dans l’émulateur HoloLens 2

*À venir*

[Retour à la liste](#list)

## <a name="voice-commands-arent-working"></a>Les commandes vocales ne fonctionnent pas

Si Cortana ne répond pas à vos commandes vocales, vérifiez que Cortana est activé. Dans la liste toutes les applications, sélectionnez  >    >  paramètres du **bloc-notes**  >   du menu Cortana pour apporter des modifications. Pour en savoir plus sur ce que vous pouvez prononcer, consultez [utiliser votre voix avec HoloLens](hololens-cortana.md).

Sur HoloLens (1re génération), la reconnaissance vocale intégrée n’est pas configurable. Il est toujours activé. Sur HoloLens 2, vous pouvez choisir d’activer la reconnaissance vocale et Cortana pendant la configuration de l’appareil.

Si votre HoloLens 2 ne répond pas à votre voix, vérifiez que la reconnaissance vocale est activée. Accédez à paramètres de **démarrage**  >    >    >  **voix** sur la confidentialité et activez la **reconnaissance vocale**.

[Retour à la liste](#list)

## <a name="hand-input-isnt-working"></a>L’entrée manuelle ne fonctionne pas

Pour vous assurer que HoloLens peut voir vos mains, vous devez les conserver dans le cadre de mouvement.  La page d’hébergement de la réalité mixte fournit des commentaires qui vous permettent de savoir quand vos mains sont suivies.  Les commentaires sont différents sur les différentes versions de HoloLens :
- Sur HoloLens (1re génération), le curseur en regard passe d’un point à un anneau
- Sur HoloLens 2, un curseur à main s’affiche lorsque la main est proche d’un ardoise, et un rayon de la main apparaît lorsque les ardoises sont éloignées

De nombreuses applications immersifs suivent des modèles d’entrée similaires à la réalité mixte.  En savoir plus sur l’utilisation de la saisie manuelle sur [hololens (1re génération)](hololens1-basic-usage.md#use-hololens-with-your-hands) et [hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Si vous portez des gants, Notez que certains types de gants ne fonctionnent pas avec le suivi des mains.  Un exemple courant est le noir en caoutchouc, qui a tendance à absorber la lumière infrarouge et n’est pas récupéré par l’appareil photo de profondeur.  Si votre travail implique des gants en caoutchouc, nous vous recommandons d’essayer une couleur plus claire, telle que le bleu ou le gris.  Un autre exemple est un grand gants Baggy, qui a tendance à obscurcir la forme de votre main. Nous vous recommandons d’utiliser les gants qui sont aussi adaptés à la forme que possible pour des résultats optimaux.

Si votre visière présente des empreintes digitales ou des traînées, utilisez le chiffon de nettoyage microfiber fourni avec le HoloLens pour nettoyer doucement votre visière.

[Retour à la liste](#list)

## <a name="cant-connect-to-wi-fi"></a>Impossible de se connecter à Wi-Fi

Voici quelques points à essayer si vous ne pouvez pas connecter votre HoloLens à un réseau Wi-Fi :

- Assurez-vous que Wi-Fi est activé. Pour vérifier, utilisez le mouvement Démarrer, puis sélectionnez **paramètres**  >  **réseau &amp; Internet**  >  **Wi-Fi**. Si Wi-Fi est activé, essayez de le mettre hors tension puis de nouveau sous tension.
- Rapprochez-vous du routeur ou du point d’accès.
- Redémarrez votre routeur Wi-Fi, puis [Redémarrez HoloLens](hololens-recovery.md). Réessayez de vous connecter.
- Si aucun de ces éléments ne fonctionne, assurez-vous que votre routeur utilise le microprogramme le plus récent. Vous pouvez trouver ces informations sur le site Web du fabricant.

[Retour à la liste](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Les appareils Bluetooth ne sont pas couplés

Si vous rencontrez des problèmes pour [associer un périphérique Bluetooth](hololens-connect-devices.md), essayez les opérations suivantes :

- Accédez à **paramètres**  >  **appareils**, puis assurez-vous que Bluetooth est activé. Si c’est le cas, éteignez-le et réactivez-le.
- Assurez-vous que votre appareil Bluetooth est entièrement débité ou qu’il contient des piles neuves.
- Si vous ne pouvez toujours pas vous connecter, [Redémarrez HoloLens](hololens-recovery.md).

[Retour à la liste](#list)

## <a name="usb-c-microphone-isnt-working"></a>Le microphone USB-C ne fonctionne pas
Sachez que certains microtéléphones USB-C se signalent incorrectement comme un microphone *et* un orateur. Il s’agit d’un problème avec le microphone et non avec HoloLens. Lors du branchement de l’un de ces microphones dans HoloLens, le son peut être perdu. Heureusement, il existe un correctif simple.  

Dans **paramètres**  ->    ->  **sons** système, définissez explicitement les haut-parleurs intégrés **(pilote audio de fonctionnalité analogique)** comme **périphérique par défaut**. HoloLens doit se souvenir de ce paramètre même si le microphone est supprimé et reconnecté ultérieurement.

![Résolution des problèmes de microphones USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Les appareils listés comme disponibles dans les paramètres ne fonctionnent pas

HoloLens (1re génération) ne prend pas en charge les profils audio Bluetooth. Les périphériques audio Bluetooth, tels que les haut-parleurs et les casques, peuvent apparaître comme étant disponibles dans les paramètres HoloLens, mais ils ne sont pas pris en charge.

HoloLens 2 prend en charge le profil audio Bluetooth A2DP pour la lecture stéréo. Le profil mains libres Bluetooth qui active la capture du microphone à partir d’un périphérique Bluetooth n’est pas pris en charge sur HoloLens 2.

Si vous rencontrez des problèmes lors de l’utilisation d’un périphérique Bluetooth, assurez-vous qu’il s’agit d’un appareil pris en charge. Les appareils pris en charge sont les suivants :

- Claviers Bluetooth QWERTY en langue anglaise (vous pouvez les utiliser partout où vous utilisez le clavier holographique).
- Souris Bluetooth.
- [Clicker de HoloLens](hololens1-clicker.md).

Vous pouvez associer d’autres périphériques HID et du GATT Bluetooth à votre HoloLens. Toutefois, vous devrez peut-être installer les applications auxiliaires correspondantes à partir de Microsoft Store pour utiliser réellement les appareils.

[Retour à la liste](#list)
