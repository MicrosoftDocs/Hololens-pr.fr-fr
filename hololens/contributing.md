---
title: Instructions d’élaboration
description: Découvrez comment contribuer aux documents HoloLens sur la plateforme docs.microsoft.com à l’aide de GitHub-baversa.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.openlocfilehash: d17d9e30ca3699a7bd6c69b75043c6974a2bde1f
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253635"
---
# Contribution à la documentation HoloLens

Bienvenue dans la [documentation HoloLens](https://github.com/MicrosoftDocs/Hololens). Tout article créé ou modifié dans ce référentiel Samples **sera visible par le public.** 

Les documents HoloLens sont affichés sur la plateforme docs.microsoft.com, qui utilise la démarque GitHub-parfumée avec des fonctions Markdig. Le contenu que vous modifiez dans ce référentiel Samples est mis en forme en pages stylisées qui s’affichent à l’adresse https://docs.microsoft.com/hololens . 

Cette page présente les étapes de base et les recommandations en matière de connaissances et de liens vers des notions de base de la marque. Merci pour votre contribution.

## Pensions disponibles

| Nom du référentiel | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Réalité mixte | [MicrosoftDocs/Mixed-Reality](https://docs.microsoft.com/windows/mixed-reality) |
| Guide sur les adeptes du VR | [MicrosoftDocs/Mixed-Really-Guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Avant de commencer

Si vous n’en avez pas encore, vous devez [créer un compte GitHub](https://github.com/join).

>[!NOTE]
>Si vous êtes un employé de Microsoft, liez votre compte GitHub à votre alias Microsoft dans le [portail Microsoft Open source](https://repos.opensource.microsoft.com/). Rejoignez les organisations « **Microsoft»** et **«MicrosoftDocs»** .

Lorsque vous configurez votre compte GitHub, nous vous recommandons également de procéder comme suit:
- Créez un [mot de passe sécurisé pour votre compte GitHub](https://github.com/settings/admin).
- Activez [l’authentification à deux facteurs](https://github.com/settings/two_factor_authentication/configure).
- Enregistrez vos [codes de récupération](https://github.com/settings/auth/recovery-codes) en lieu sûr.
- Mettez à jour vos [paramètres de profil public](https://github.com/settings/profile).
   - Définissez votre nom et envisagez de configurer votre adresse de *messagerie publique* de façon à *ne pas afficher mon adresse de messagerie*.
   - Nous vous recommandons de télécharger une image de profil, car une miniature apparaît sur les pages de docs auxquelles vous participez.
- Si vous envisagez d’utiliser la ligne de commande, envisagez de configurer le [Gestionnaire d’informations d’identification git pour Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Ainsi, vous n’aurez pas à entrer votre mot de passe chaque fois que vous faites une contribution.

Le système de publication est lié à GitHub; il est donc important de ces étapes. Dans le cadre de l’utilisation de votre alias GitHub, vous serez répertorié comme auteur ou collaborateur.

## Modification d’un article existant

Utilisez le flux de travail suivant pour apporter des mises à jour à *un article existant* via github dans un navigateur Web:

1. Accédez à l’article que vous souhaitez modifier dans le dossier «Mixed-Real-docs».
2. Sélectionnez le bouton modifier (icône en forme de crayon) dans le coin supérieur droit, qui répartir automatiquement une branche jetable de la branche «maître».

   ![Modifier un article](images/editpage.png)
3. Modifiez le contenu de l’article en fonction des [principes de base de la démarque](#markdown-basics).
4. Dans la partie supérieure de chaque article, procédez à la mise à jour des métadonnées:
   * **titre**: titre de page qui s’affiche dans l’onglet du navigateur lors de l’affichage de l’article. Les titres de page sont utilisés pour les fonctions SEO et indexation; par conséquent, ne modifiez pas le titre sauf nécessité
   * **Description**: rédigez une brève description du contenu de l’article, qui amplifie le moteur SEO et la découverte.
   * **auteur**: Si vous êtes le propriétaire principal de la page, ajoutez votre alias GitHub ici.
   * **ms. Author**: Si vous êtes le propriétaire principal de la page, ajoutez votre alias Microsoft ici (vous n’avez pas besoin de @microsoft. com, uniquement l’alias).
   * **ms. date**: mettre à jour la date si vous ajoutez du contenu principal à la page, mais pas pour des corrections telles que la clarification, la mise en forme, la grammaire et l’orthographe.
   * **Mots clés**: aide sur les mots-clés dans SEO (optimisation du moteur de recherche). Ajoutez des mots-clés, séparés par une virgule et un espace, qui sont propres à votre article, mais pas de ponctuation après le dernier mot clé de votre liste. Vous n’avez pas besoin d’ajouter des mots clés généraux qui s’appliquent à tous les articles, car ils sont gérés ailleurs. 
5. Lorsque vous avez terminé les modifications apportées à l’article, faites défiler vers le bas, puis sélectionnez **proposer une modification de fichier**.
6. Sur la page suivante, sélectionnez **créer une demande d’extraction** pour fusionner votre branche créée automatiquement dans «maître».
7. Répétez les étapes ci-dessus pour le prochain article que vous voulez modifier.

## Renommer ou supprimer un article existant

Si votre modification doit renommer ou supprimer un article existant, veillez à ajouter une redirection. Ainsi, toute personne disposant d’un lien vers l’article existant va tout de même se terminer au bon endroit. Les redirections sont gérées par le .openpublishing.redirection.jssur fichier à la racine du référentiel Samples.

Pour ajouter une redirection à .openpublishing.redirection.js, ajoutez une entrée à la `redirections` matrice:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`Correspond au chemin d’accès relatif du référentiel de l’ancien article que vous voulez supprimer. Vérifiez que le chemin d’accès commence par `mixed-reality-docs` et se termine par `.md` .
- `redirect_url`Est l’URL publique relative de l’ancien article vers le nouvel article. Assurez-vous que cette URL **ne** contient `mixed-reality-docs` `.md` pas ou, car elle fait référence à l’URL publique et non au chemin d’accès du référentiel. La création d’un lien vers une section du nouvel article en utilisant `#section` est autorisée. Le cas échéant, vous pouvez également utiliser un chemin d’accès absolu à un autre site.
- `redirect_document_id` indique si vous souhaitez conserver l’ID de document du fichier précédent. La valeur par défaut est `false` . Utilisez `true` cette option si vous souhaitez conserver la `ms.documentid` valeur d’attribut de l’article Redirigé. Si vous conservez l’ID de document, les données, telles que les vues de page et les classements, seront transférées vers l’article cible. Procédez ainsi si la redirection est essentiellement un changement de nom et non un pointeur vers un autre article qui ne couvre que le même contenu.

Si vous ajoutez une redirection, veillez à supprimer l’ancien fichier également.

## Création d’un article

Utilisez le flux de travail suivant pour *créer des articles* dans le référentiel samples de documentation via github dans un navigateur Web:

1. Créez une fourche en dehors de la branche MicrosoftDocs/Mixed-Reality (à l’aide du bouton **Fork** dans le coin supérieur droit).

   ![Bifurcationz la branche principale.](images/forkbranch.png)
2. Dans le dossier «Mixed-Reality-docs», sélectionnez **créer un fichier** dans le coin supérieur droit.
3. Créer un nom de page pour l’article (utiliser des traits d’Union au lieu d’espaces et utiliser des signes de ponctuation ou des apostrophes) et ajouter ". MD"

   ![Nommez votre nouvelle page.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   >Veillez à créer le nouvel article dans le dossier «Mixed-Reality-docs». Vous pouvez vérifier ceci en recherchant «/Mixed-Reality-docs/» dans la ligne nouveau nom de fichier.

4. Dans la partie supérieure de votre nouvelle page, ajoutez le bloc de métadonnées suivant:

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. Entrez les champs de métadonnées pertinents conformément aux instructions de la [section ci-dessus](#editing-an-existing-article).
6. Rédigez le contenu d’un article à l’aide des [règles de démarque](#markdown-basics).
7. Ajoutez une `## See also` section en bas de cet article, contenant des liens vers d’autres articles pertinents.
8. Lorsque vous avez terminé, sélectionnez **valider le nouveau fichier**.
9. Sélectionnez **nouvelle demande d’extraction** , puis fusionnez la branche «maître» de votre bifurcation dans MicrosoftDocs/Mixed-Reality’Master' (Assurez-vous que la flèche pointe correctement).

   ![Créer une demande d’extraction depuis votre fourche dans MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## Notions de base des promotions

Les ressources suivantes vous permettront de découvrir comment modifier la documentation à l’aide du langage de démarque:

- [Notions de base des promotions](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Affiche démarquez-en un coup d’œil](images/MarkdownPoster.pdf)
- [Ressources supplémentaires pour l’écriture de la démarque pour docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Ajout de tables

En raison de la façon dont docs.microsoft.com styles les tableaux, les bordures ou les styles personnalisés ne sont pas appliqués, même si vous essayez la fonction CSS intraligne. Elle semble fonctionner pendant un court laps de temps, mais au final, la plateforme va supprimer le style de la table. Envisagez donc d’anticiper et de garder vos tableaux simples. Vous [trouverez ci-dessous un site qui simplifie la démarque](https://www.tablesgenerator.com/markdown_tables).

L' [extension documents pour le code Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) simplifie également la génération de tableaux si vous utilisez du [code Visual Studio (voir ci-dessous)](#using-visual-studio-code) pour modifier la documentation.

### Ajout d’images

Vous aurez besoin de télécharger vos images dans le dossier «Mixed-Real-docs/images» du référentiel samples, puis de les référencer correctement dans l’article. Les images s’affichent automatiquement en taille réelle, ce qui signifie que les images de grande taille remplissent toute la largeur de l’article. Nous vous recommandons d’utiliser le prédimensionnement de vos images avant de les télécharger. La largeur recommandée est comprise entre 600 et 700 pixels, même si la taille de la capture d’écran est densée ou une fraction d’une capture d’écran, respectivement.

>[!IMPORTANT]
>Vous pouvez uniquement transférer des images vers votre référentiel samples en fourche avant la fusion. Par conséquent, si vous envisagez d’ajouter des images à un article, vous devez [utiliser du code Visual Studio](#using-visual-studio-code) pour ajouter d’abord les images dans le dossier «images» de votre bifurcation ou vérifier que vous avez effectué les opérations suivantes dans un navigateur Web:
>
>1. A Fork le référentiel samples de MicrosoftDocs/Mixed-Real.
>2. Modification de l’article dans votre bifurcation.
>3. Téléchargez les images que vous référencez dans votre article dans le dossier «Mixed-Real-docs/images» dans votre bifurcation.
>4. Création d’une **demande d’extraction** permettant de fusionner votre fourche dans la branche MicrosoftDocs/Mixed-Reality.
>
>Pour découvrir comment configurer votre propre référentiel samples, suivez les instructions de [création d’un nouvel article](#creating-a-new-article).

## Prévisualiser votre bureau

Lorsque vous effectuez une modification dans GitHub via un navigateur Web, vous pouvez sélectionner l’onglet **Aperçu** en haut de la page pour afficher un aperçu de votre œuvre avant de l’engager. 

>[!NOTE]
>Pour afficher un aperçu de vos modifications sur review.docs.microsoft.com est uniquement disponible aux employés de Microsoft.

Employés de Microsoft: une fois vos contributions fusionnées dans la succursale «maître», vous pouvez consulter le contenu avant de le rendre public https://review.docs.microsoft.com/hololens?branch=master . Recherchez votre article à l’aide de la table des matières dans la colonne de gauche.

## Modification dans le navigateur et modification avec un client de bureau

La modification dans le navigateur est le moyen le plus simple de procéder à des modifications rapides, mais il existe quelques inconvénients:

- Vous ne recevez pas de vérification de l’orthographe.
- Vous ne recevez pas de liens hypertexte vers d’autres articles (vous devez taper manuellement le nom de fichier de l’article).
- C’est un bon risque de télécharger et de référencer des images.

Si vous préférez ne pas traiter ces problèmes, utilisez un client de bureau tel que le [code Visual Studio](https://code.visualstudio.com/) avec quelques [Extensions utiles](#useful-extensions) .

## Utilisation de code Visual Studio

Pour les raisons répertoriées [ci-dessus](#editing-in-the-browser-vs-editing-with-a-desktop-client), il est possible que vous préfériez utiliser un client de bureau pour modifier la documentation au lieu d’un navigateur Web. Nous vous recommandons d’utiliser du [code Visual Studio](https://code.visualstudio.com/).

### Configuration

Suivez les étapes ci-dessous pour configurer le code Visual Studio pour qu’il fonctionne avec ce référentiel Samples:

1. Dans un navigateur Web:
    1. Installez [git pour votre PC](https://git-scm.com/downloads).
    2. Installez du [code Visual Studio](https://code.visualstudio.com/).
    3. [Fourche MicrosoftDocs/Mixed-Real,](#creating-a-new-article) si vous ne l’avez pas déjà fait.
    4. Dans votre bifurcation, sélectionnez **clonage ou téléchargement** , puis copiez l’URL.
2. Créez un clone local de votre bifurcation dans le code Visual Studio:
    1. Dans le menu **affichage** , sélectionnez **palette de commandes**.
    2. Tapez «git: Clone».
    3. Collez l’URL que vous avez copiée.
    4. Choisissez l’emplacement d’enregistrement du clone sur votre PC.
    5. Dans la fenêtre qui s’affiche, sélectionnez **ouvrir référentiel Samples** .

### Modification de la documentation

Utilisez le flux de travail suivant pour modifier la documentation avec du code Visual Studio:

>[!NOTE]
>Toutes les recommandations en matière de [modification](#editing-an-existing-article) et de [création](#creating-a-new-article) d’articles, ainsi que les [notions de base de la modification de la démarque](#markdown-basics), ci-dessus s’appliquent également à l’utilisation de code Visual Studio.

1. Assurez-vous que votre fourche clonée est à jour avec l’référentiel Samples officiel.
   1. Dans un navigateur Web, créez une demande de collecte pour synchroniser les modifications récentes d’autres contributeurs dans MicrosoftDocs/Mixed-Reality’Master’dans votre bifurcation (Assurez-vous que la flèche pointe sur la bonne voie).
      
      ![Synchroniser les modifications de MicrosoftDocs/Mixed-Reality vers votre bifurcation](images/sync_repos.PNG)
   2. Dans le code Visual Studio, sélectionnez le bouton synchroniser pour synchroniser votre branche fraîchement mise à jour sur le clone local.
      
      ![Cliquez sur l’image du bouton synchroniser](images/sync_clone.png)
2. Créez ou modifiez des articles dans votre référentiel Samples cloné à l’aide de code Visual Studio.
   1. Modifiez un ou plusieurs articles (ajoutez des images dans le dossier «images» le cas échéant).
   2. **Enregistrer** les modifications dans l' **Explorateur**.
      
      ![Sélectionnez «Enregistrer tout» dans l’Explorateur](images/explorer_save.png)
   3. **Valider toutes les** modifications dans **le contrôle de code source** (rédiger le message de validation lorsque vous y êtes invité).
      
      ![Sélectionner «valider tout» dans le contrôle de code source](images/source_control_commit.png)
   4. Sélectionnez le bouton **synchroniser** pour synchroniser vos modifications à l’origine (votre fourche sur GitHub).
      
      ![Cliquez sur le bouton synchroniser.](images/sync_back.png)
3. Dans un navigateur Web, créez une demande de collecte pour synchroniser les modifications apportées à votre fourche de nouveau dans MicrosoftDocs/Mixed-Reality' (Assurez-vous que la flèche pointe correctement).

   ![Créer une demande d’extraction depuis votre fourche dans MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### Extensions utiles

Les extensions de code Visual Studio suivantes sont utiles lors de la modification de la documentation:

- [Extension documents pour le code Visual Studio](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) -utilisez **ALT + M** pour afficher un menu des options de création de documents telles que:
   - Recherchez et référencez des images que vous avez téléchargées.
   - Ajouter des mises en forme, comme des listes, des tableaux et des appels spécifiques aux documents `>[!NOTE]` .
   - Recherchez et référencez des liens et des signets internes (liens vers des sections spécifiques d’une page).
   - Erreur de mise en forme mise en évidence (placez le pointeur de la souris sur l’erreur pour en savoir plus).
- [Vérificateur orthographique du code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : les mots mal orthographiés sont soulignés; Cliquez avec le bouton droit sur un mot mal orthographié pour le modifier ou enregistrez-le dans le dictionnaire.
