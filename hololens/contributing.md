---
title: Instructions de contribution
description: Découvrez comment contribuer aux documents HoloLens sur la plateforme docs.microsoft.com à l’aide de Markdown de GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283658"
---
# Contribution à la documentation HoloLens

Bienvenue dans la [documentation HoloLens](https://github.com/MicrosoftDocs/Hololens)! Tous les articles que vous créez ou modifiez dans ce repo **seront visibles pour le public.** 

Les documents HoloLens sont affichés sur la plateforme docs.microsoft.com, qui utilise les fonctionnalités Markdown de GitHub avec Markdig. Le contenu que vous modifiez dans ce repo est mis en forme dans des pages stylisées qui s’affiche dans https://docs.microsoft.com/hololens . 

Cette page présente les étapes de base et les instructions relatives à la contribution et aux liens vers les principes de base de Markdown. Merci pour votre contribution !

## Repos disponibles

| Nom du référentiel | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Réalité mixte | [MicrosoftDocs/réalité mixte](https://docs.microsoft.com/windows/mixed-reality) |
| Guide des fans de VR | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Avant de commencer

Si vous n’en avez pas encore, vous devez créer [un compte GitHub.](https://github.com/join)

>[!NOTE]
>Si vous êtes un employé de Microsoft, liez votre compte GitHub à votre alias Microsoft sur le portail [Microsoft Open Source.](https://repos.opensource.microsoft.com/) Rejoignez **les organisations « Microsoft »** et « **MicrosoftDocs** ».

Lors de la configuration de votre compte GitHub, nous vous recommandons également les précautions de sécurité suivantes :
- Créez [un mot de passe fort pour votre compte GitHub.](https://github.com/settings/admin)
- Activer [l’authentification à deux facteurs](https://github.com/settings/two_factor_authentication/configure).
- Enregistrez [vos codes de récupération](https://github.com/settings/auth/recovery-codes) en lieu sûr.
- Mettez à jour [vos paramètres de profil public.](https://github.com/settings/profile)
   - Définissez votre nom et envisagez de définir votre courrier *public* sur *Ne pas afficher mon adresse e-mail.*
   - Nous vous recommandons de charger une image de profil, car une miniature est affichée sur les pages de documents que vous contribuez.
- Si vous envisagez d’utiliser la ligne de commande, envisagez de définir [Git Credential Manager pour Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Ainsi, vous n’avez pas besoin d’entrer votre mot de passe chaque fois que vous apporterez une contribution.

Le système de publication est lié à GitHub. Ces étapes sont donc importantes. Vous serez répertorié en tant qu’auteur ou collaborateur de chaque article à l’aide de votre alias GitHub.

## Modification d’un article existant

Utilisez le flux de travail suivant pour mettre à jour un *article existant* via GitHub dans un navigateur web :

1. Accédez à l’article que vous souhaitez modifier dans le dossier « mixed-reality-docs ».

2. Sélectionnez le bouton d’édition (icône de crayon) dans le haut à droite, qui bifurque automatiquement une branche jetable de la branche « master ».

   ![Modifiez un article.](images/editpage.png)
   
3. Modifiez le contenu de l’article en fonction des « informations de base de [Markdown](#markdown-basics)».

4. Mettez à jour les métadonnées en haut de chaque article :

   * **title**: Titre de la page qui apparaît dans l’onglet du navigateur lorsque l’article est en cours d’affichage. Les titres de page sont utilisés pour seO et l’indexation, donc ne modifiez pas le titre sauf si cela est nécessaire (bien que cela soit moins critique avant que la documentation ne soit publique).
   * **description**: rédigez une brève description du contenu de l’article, ce qui améliore le seO et la découverte.
   * **auteur**: si vous êtes le propriétaire principal de la page, ajoutez votre alias GitHub ici.
   * **ms.author**: si vous êtes le propriétaire principal de la page, ajoutez votre alias Microsoft ici (vous n’avez pas besoin de @microsoft.com, mais de l’alias).
   * **ms.date**: mettez à jour la date si vous ajoutez du contenu principal à la page, mais pas pour des correctifs tels que la clarification, la mise en forme, la grammaire ou l’orthographe.
   * **mots clés :** aide sur les mots clés dans seO (optimisation du moteur de recherche). Ajoutez des mots clés, séparés par une virgule et un espace, qui sont spécifiques à votre article, mais pas de ponctuation après le dernier mot clé de votre liste. Vous n’avez pas besoin d’ajouter des mots clés globaux qui s’appliquent à tous les articles, car ceux-ci sont gérés ailleurs. 
   
5. Lorsque vous avez terminé les modifications de votre article, faites défiler vers le bas et sélectionnez **Proposer une modification de fichier.**

6. Sur la page suivante, **sélectionnez Créer** une requête de pull pour fusionner votre branche créée automatiquement en « master ».

7. Répétez les étapes ci-dessus pour le prochain article que vous souhaitez modifier.

## Renommer ou supprimer un article existant

Si votre modification renomme ou supprime un article existant, n’oubliez pas d’ajouter une redirection. Ainsi, toute personne ayant un lien vers l’article existant se retrouve toujours au bon endroit. Les redirections sont gérées par le .openpublishing.redirection.jssur le fichier à la racine du dépôt.

Pour ajouter une redirection vers .openpublishing.redirection.js, ajoutez une entrée au `redirections` tableau :

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- Il `source_path` s’agit du chemin d’accès relatif au référentiel de l’ancien article que vous supprimez. Assurez-vous que le chemin d’accès commence `mixed-reality-docs` par et se termine par `.md` .

- Il `redirect_url` s’agit de l’URL publique relative de l’ancien article au nouvel article. Assurez-vous que cette URL ne contient pas ou, car elle fait référence à **l’URL** publique et non au `mixed-reality-docs` `.md` chemin d’accès du référentiel. La liaison à une section dans le nouvel article à l’aide `#section` est autorisée. Vous pouvez également utiliser un chemin d’accès absolu à un autre site ici, si nécessaire.

- `redirect_document_id` indique si vous souhaitez conserver l’ID de document du fichier précédent. La valeur par défaut `false` est . À `true` utiliser si vous souhaitez conserver la valeur `ms.documentid` d’attribut de l’article redirigé. Si vous conservez l’ID du document, les données, telles que les vues de page et les classements, sont transférées vers l’article cible. Faites-le si la redirection est principalement un changement de nom et non un pointeur vers un autre article qui couvre uniquement une partie du même contenu.

Si vous ajoutez une redirection, assurez-vous également de supprimer l’ancien fichier.

## Création d’un article

Utilisez le flux de travail suivant pour *créer des articles* dans le référentiel de documentation via GitHub dans un navigateur web :

1. Créez une bifurcation de la branche « master » **** MicrosoftDocs/réalité mixte (à l’aide du bouton De la bifurcation dans le haut à droite).

   ![Bifurcation de la branche principale.](images/forkbranch.png)
   
2. Dans le dossier « mixed-reality-docs », sélectionnez **Créer** un fichier en haut à droite.

3. Créez un nom de page pour l’article (utilisez des traits d’union au lieu d’espaces et n’utilisez pas de ponctuation ou d’apostrophes) et ajoutez « .md »

   ![Nommez votre nouvelle page.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Veillez à créer le nouvel article à partir du dossier « mixed-reality-docs ». Vous pouvez le confirmer en vérifiant « /mixed-reality-docs/ » dans la nouvelle ligne de nom de fichier.

4. En haut de votre nouvelle page, ajoutez le bloc de métadonnées suivant :

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

5. Remplissez les champs de métadonnées appropriés selon les instructions de la [section ci-dessus.](#editing-an-existing-article)

6. Écrire du contenu d’article [à l’aide des principes de base de Markdown.](#markdown-basics)

7. Ajoutez `## See also` une section au bas de l’article avec des liens vers d’autres articles pertinents.

8. Lorsque vous avez terminé, **sélectionnez Valider un nouveau fichier**.

9. Sélectionnez **Nouvelle** demande de pull et fusionnez la branche « master » de votre bifurcation dans MicrosoftDocs/mixed-reality 'master' (assurez-vous que la flèche pointe correctement).

   ![Créer une demande de tirer à partir de votre bifurcation dans MicrosoftDocs/réalité mixte](images/pr-to-master.png)

## Informations de base sur Markdown

Les ressources suivantes vous aideront à apprendre à modifier la documentation à l’aide de la langue Markdown :

- [Informations de base sur Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Ressources supplémentaires pour écrire Markdown pour docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Ajout de tables

En raison de la façon dont docs.microsoft.com tableaux de styles, ils n’auront pas de bordures ou de styles personnalisés, même si vous essayez inline CSS. Il semblera fonctionner pendant une courte période de temps, mais finalement, la plateforme sera sans style du tableau. Planifiez donc et maintenez vos tableaux simples. [Voici un site qui facilite les tables Markdown.](https://www.tablesgenerator.com/markdown_tables)

[L’extension Docs Markdown pour Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) facilite également la génération de tableau si vous utilisez Visual Studio Code (voir ci-dessous) pour modifier la documentation. [](#using-visual-studio-code)

### Ajout d’images

Vous devrez charger vos images dans le dossier « mixed-reality-docs/images » dans le repo, puis les référencer correctement dans l’article. Les images s’afficheront automatiquement en taille réelle, ce qui signifie que de grandes images rempliront toute la largeur de l’article. Nous vous recommandons de pré-ret tailler vos images avant de les télécharger. La largeur recommandée est entre 600 et 700 pixels, même si vous devez les dimensionnement vers le haut ou vers le bas s’il s’agit d’une capture d’écran épaisse ou d’une fraction d’une capture d’écran, respectivement.

>[!IMPORTANT]
>Vous pouvez uniquement charger des images vers votre repo bifurcation avant la fusion. Par exemple, si vous envisagez d’ajouter des images à un article, vous devez d’abord utiliser [Visual Studio Code](#using-visual-studio-code) pour ajouter les images au dossier « images » de votre bifurcation ou vous assurer que vous avez effectué les étapes suivantes dans un navigateur web :
>
>1. Bifurcation du repo MicrosoftDocs/mixed-reality.
>2. Modification de l’article dans votre bifurcation.
>3. Les images que vous référencez dans votre article ont été téléchargées vers le dossier « mixed-reality-docs/images » dans votre bifurcation.
>4. Création **d’une demande de** pull pour fusionner votre bifurcation dans la branche MicrosoftDocs/master de réalité mixte.
>
>Pour apprendre à configurer votre propre repo bifurpé, suivez les instructions de création [d’un article.](#creating-a-new-article)

## Aperçu de votre travail

Lors de la modification dans GitHub via **** un navigateur web, vous pouvez sélectionner l’onglet Aperçu en haut de la page pour afficher un aperçu de votre travail avant de la validation. 

>[!NOTE]
>L’aperçu de vos modifications sur review.docs.microsoft.com est disponible uniquement pour les employés de Microsoft

Employés de Microsoft : une fois que vos contributions ont été fusionnées dans la branche « maître » , vous pouvez consulter le contenu avant qu’il ne soit https://review.docs.microsoft.com/hololens?branch=master public. Recherchez votre article à l’aide de la table des matières dans la colonne de gauche.

## Modification dans le navigateur et modification avec un client de bureau

La modification dans le navigateur est le moyen le plus simple d’apporter des modifications rapides, mais il existe quelques inconvénients :

- Vous n’obtenez pas de vérification orthographie.
- Vous n’obtenez aucun lien intelligent vers d’autres articles (vous devez taper manuellement le nom de fichier de l’article).
- Le chargement et la référence d’images peuvent être compliqués.

Si vous préférez ne pas gérer ces problèmes, utilisez un client de bureau comme [Visual Studio Code](https://code.visualstudio.com/) avec quelques [extensions](#useful-extensions) utiles lors de la contribution.

## Utilisation Visual Studio code

Pour les raisons répertoriées [ci-dessus,](#editing-in-the-browser-vs-editing-with-a-desktop-client)vous pouvez utiliser un client de bureau pour modifier la documentation au lieu d’un navigateur web. Nous vous recommandons [d’Visual Studio code.](https://code.visualstudio.com/)

### Configuration

Suivez ces étapes pour configurer Visual Studio code de manière à ce qu’il fonctionne avec ce repo :

1. Dans un navigateur web :
    1. Installez [Git pour votre PC.](https://git-scm.com/downloads)
    2. Installez [Visual Studio Code](https://code.visualstudio.com/).
    3. Si ce n’est pas déjà fait, bifurquez [MicrosoftDocs/réalité](#creating-a-new-article) mixte.
    4. Dans votre bifurcation, sélectionnez **Cloner ou téléchargez** et copiez l’URL.
2. Créez un clone local de votre bifurcation dans Visual Studio Code :
    1. Dans le menu **Affichage,** sélectionnez **Palette de commandes.**
    2. Tapez « Git : Clone ».
    3. Collez l’URL que vous avez copiée.
    4. Choisissez où enregistrer le clone sur votre PC.
    5. Sélectionnez **Ouvrir un repo** dans la fenêtre pop-up.

### Modification de la documentation

Utilisez le flux de travail suivant pour apporter des modifications à la documentation avec Visual Studio Code :

>[!NOTE]
>Tous les conseils pour [la](#editing-an-existing-article) modification et la création d’articles, ainsi que les principes de base de la modification de [Markdown,](#markdown-basics)ci-dessus s’appliquent également lors de l’utilisation Visual Studio Code. [](#creating-a-new-article)

1. Assurez-vous que votre bifurcation clonée est à jour avec le repo officiel.

   1. Dans un navigateur web, créez une requête de pull pour synchroniser les modifications récentes apportées par d’autres contributeurs dans MicrosoftDocs/mixed-reality « master » à votre bifurcation (assurez-vous que la flèche pointe vers la bonne voie).
      
      ![Synchroniser les modifications de MicrosoftDocs/mixed-reality avec votre bifurcation](images/sync-repos.png)
      
   2. Dans Visual Studio code, sélectionnez le bouton de synchronisation pour synchroniser votre nouvelle bifurcation mise à jour avec le clone local.
      
      ![Cliquez sur l’image du bouton de synchronisation](images/sync-clone.png)
      
2. Créez ou modifiez des articles dans votre repo cloné à l’aide Visual Studio Code.

   1. Modifiez un ou plusieurs articles (ajoutez des images au dossier « images » si nécessaire).
   
   2. **Enregistrez** les modifications dans **l’Explorateur.**
      
      ![Sélectionnez « Enregistrer tout » dans l’Explorateur](images/explorer-save.png)
      
   3. **Valider toutes les modifications** dans le **contrôle de source** (écrire un message de validation lorsque vous y invitez).
   
      ![Choose «Commit all» in Source Control](images/source-control-commit.png)
      
   4. Sélectionnez **le bouton** de synchronisation pour synchroniser vos modifications à l’origine (votre bifurcation sur GitHub).
      
      ![Cliquez sur le bouton synchroniser](images/sync-back.png)
      
3. Dans un navigateur web, créez une requête de pull pour synchroniser les nouvelles modifications dans votre bifurcation avec MicrosoftDocs/mixed-reality 'master' (assurez-vous que la flèche pointe correctement).

   ![Créer une demande de tirer à partir de votre bifurcation dans MicrosoftDocs/réalité mixte](images/pr-to-master.png)

### Extensions utiles

Les extensions Visual Studio code suivantes sont utiles lors de la modification de la documentation :

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:
   - Recherchez et référencez des images que vous avez téléchargées.
   - Ajoutez une mise en forme telle que des listes, des tableaux et des call-outs spécifiques à des documents comme `>[!NOTE]` .
   - Rechercher et référencer des liens internes et des signets (liens vers des sections spécifiques dans une page).
   - Les erreurs de mise en forme sont mises en surbrillante (pointez votre souris sur l’erreur pour en savoir plus).
- [Vérification de l’orthographe du code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : les mots mal orthographiés sont soulignés ; cliquez avec le bouton droit sur un mot mal orthographié pour le modifier ou l’enregistrer dans le dictionnaire.
