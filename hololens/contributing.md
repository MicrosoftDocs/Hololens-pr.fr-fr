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
# <span data-ttu-id="4313f-103">Contribution à la documentation HoloLens</span><span class="sxs-lookup"><span data-stu-id="4313f-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="4313f-104">Bienvenue dans la [documentation HoloLens](https://github.com/MicrosoftDocs/Hololens)!</span><span class="sxs-lookup"><span data-stu-id="4313f-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="4313f-105">Tous les articles que vous créez ou modifiez dans ce repo **seront visibles pour le public.**</span><span class="sxs-lookup"><span data-stu-id="4313f-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="4313f-106">Les documents HoloLens sont affichés sur la plateforme docs.microsoft.com, qui utilise les fonctionnalités Markdown de GitHub avec Markdig.</span><span class="sxs-lookup"><span data-stu-id="4313f-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="4313f-107">Le contenu que vous modifiez dans ce repo est mis en forme dans des pages stylisées qui s’affiche dans https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="4313f-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="4313f-108">Cette page présente les étapes de base et les instructions relatives à la contribution et aux liens vers les principes de base de Markdown.</span><span class="sxs-lookup"><span data-stu-id="4313f-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="4313f-109">Merci pour votre contribution !</span><span class="sxs-lookup"><span data-stu-id="4313f-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="4313f-110">Repos disponibles</span><span class="sxs-lookup"><span data-stu-id="4313f-110">Available repos</span></span>

| <span data-ttu-id="4313f-111">Nom du référentiel</span><span class="sxs-lookup"><span data-stu-id="4313f-111">Repository name</span></span> | <span data-ttu-id="4313f-112">URL</span><span class="sxs-lookup"><span data-stu-id="4313f-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="4313f-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="4313f-113">HoloLens</span></span> | [<span data-ttu-id="4313f-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="4313f-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="4313f-115">Réalité mixte</span><span class="sxs-lookup"><span data-stu-id="4313f-115">Mixed Reality</span></span> | [<span data-ttu-id="4313f-116">MicrosoftDocs/réalité mixte</span><span class="sxs-lookup"><span data-stu-id="4313f-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="4313f-117">Guide des fans de VR</span><span class="sxs-lookup"><span data-stu-id="4313f-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="4313f-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="4313f-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="4313f-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4313f-119">Before you start</span></span>

<span data-ttu-id="4313f-120">Si vous n’en avez pas encore, vous devez créer [un compte GitHub.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="4313f-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="4313f-121">Si vous êtes un employé de Microsoft, liez votre compte GitHub à votre alias Microsoft sur le portail [Microsoft Open Source.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="4313f-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="4313f-122">Rejoignez **les organisations « Microsoft »** et « **MicrosoftDocs** ».</span><span class="sxs-lookup"><span data-stu-id="4313f-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="4313f-123">Lors de la configuration de votre compte GitHub, nous vous recommandons également les précautions de sécurité suivantes :</span><span class="sxs-lookup"><span data-stu-id="4313f-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="4313f-124">Créez [un mot de passe fort pour votre compte GitHub.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="4313f-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="4313f-125">Activer [l’authentification à deux facteurs](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="4313f-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="4313f-126">Enregistrez [vos codes de récupération](https://github.com/settings/auth/recovery-codes) en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="4313f-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="4313f-127">Mettez à jour [vos paramètres de profil public.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="4313f-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="4313f-128">Définissez votre nom et envisagez de définir votre courrier *public* sur *Ne pas afficher mon adresse e-mail.*</span><span class="sxs-lookup"><span data-stu-id="4313f-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="4313f-129">Nous vous recommandons de charger une image de profil, car une miniature est affichée sur les pages de documents que vous contribuez.</span><span class="sxs-lookup"><span data-stu-id="4313f-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="4313f-130">Si vous envisagez d’utiliser la ligne de commande, envisagez de définir [Git Credential Manager pour Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="4313f-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="4313f-131">Ainsi, vous n’avez pas besoin d’entrer votre mot de passe chaque fois que vous apporterez une contribution.</span><span class="sxs-lookup"><span data-stu-id="4313f-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="4313f-132">Le système de publication est lié à GitHub. Ces étapes sont donc importantes.</span><span class="sxs-lookup"><span data-stu-id="4313f-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="4313f-133">Vous serez répertorié en tant qu’auteur ou collaborateur de chaque article à l’aide de votre alias GitHub.</span><span class="sxs-lookup"><span data-stu-id="4313f-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="4313f-134">Modification d’un article existant</span><span class="sxs-lookup"><span data-stu-id="4313f-134">Editing an existing article</span></span>

<span data-ttu-id="4313f-135">Utilisez le flux de travail suivant pour mettre à jour un *article existant* via GitHub dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="4313f-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="4313f-136">Accédez à l’article que vous souhaitez modifier dans le dossier « mixed-reality-docs ».</span><span class="sxs-lookup"><span data-stu-id="4313f-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="4313f-137">Sélectionnez le bouton d’édition (icône de crayon) dans le haut à droite, qui bifurque automatiquement une branche jetable de la branche « master ».</span><span class="sxs-lookup"><span data-stu-id="4313f-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Modifiez un article.](images/editpage.png)
   
3. <span data-ttu-id="4313f-139">Modifiez le contenu de l’article en fonction des « informations de base de [Markdown](#markdown-basics)».</span><span class="sxs-lookup"><span data-stu-id="4313f-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="4313f-140">Mettez à jour les métadonnées en haut de chaque article :</span><span class="sxs-lookup"><span data-stu-id="4313f-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="4313f-141">**title**: Titre de la page qui apparaît dans l’onglet du navigateur lorsque l’article est en cours d’affichage.</span><span class="sxs-lookup"><span data-stu-id="4313f-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="4313f-142">Les titres de page sont utilisés pour seO et l’indexation, donc ne modifiez pas le titre sauf si cela est nécessaire (bien que cela soit moins critique avant que la documentation ne soit publique).</span><span class="sxs-lookup"><span data-stu-id="4313f-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="4313f-143">**description**: rédigez une brève description du contenu de l’article, ce qui améliore le seO et la découverte.</span><span class="sxs-lookup"><span data-stu-id="4313f-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="4313f-144">**auteur**: si vous êtes le propriétaire principal de la page, ajoutez votre alias GitHub ici.</span><span class="sxs-lookup"><span data-stu-id="4313f-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="4313f-145">**ms.author**: si vous êtes le propriétaire principal de la page, ajoutez votre alias Microsoft ici (vous n’avez pas besoin de @microsoft.com, mais de l’alias).</span><span class="sxs-lookup"><span data-stu-id="4313f-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="4313f-146">**ms.date**: mettez à jour la date si vous ajoutez du contenu principal à la page, mais pas pour des correctifs tels que la clarification, la mise en forme, la grammaire ou l’orthographe.</span><span class="sxs-lookup"><span data-stu-id="4313f-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="4313f-147">**mots clés :** aide sur les mots clés dans seO (optimisation du moteur de recherche).</span><span class="sxs-lookup"><span data-stu-id="4313f-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="4313f-148">Ajoutez des mots clés, séparés par une virgule et un espace, qui sont spécifiques à votre article, mais pas de ponctuation après le dernier mot clé de votre liste.</span><span class="sxs-lookup"><span data-stu-id="4313f-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="4313f-149">Vous n’avez pas besoin d’ajouter des mots clés globaux qui s’appliquent à tous les articles, car ceux-ci sont gérés ailleurs.</span><span class="sxs-lookup"><span data-stu-id="4313f-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="4313f-150">Lorsque vous avez terminé les modifications de votre article, faites défiler vers le bas et sélectionnez **Proposer une modification de fichier.**</span><span class="sxs-lookup"><span data-stu-id="4313f-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="4313f-151">Sur la page suivante, **sélectionnez Créer** une requête de pull pour fusionner votre branche créée automatiquement en « master ».</span><span class="sxs-lookup"><span data-stu-id="4313f-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="4313f-152">Répétez les étapes ci-dessus pour le prochain article que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="4313f-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="4313f-153">Renommer ou supprimer un article existant</span><span class="sxs-lookup"><span data-stu-id="4313f-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="4313f-154">Si votre modification renomme ou supprime un article existant, n’oubliez pas d’ajouter une redirection.</span><span class="sxs-lookup"><span data-stu-id="4313f-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="4313f-155">Ainsi, toute personne ayant un lien vers l’article existant se retrouve toujours au bon endroit.</span><span class="sxs-lookup"><span data-stu-id="4313f-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="4313f-156">Les redirections sont gérées par le .openpublishing.redirection.jssur le fichier à la racine du dépôt.</span><span class="sxs-lookup"><span data-stu-id="4313f-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="4313f-157">Pour ajouter une redirection vers .openpublishing.redirection.js, ajoutez une entrée au `redirections` tableau :</span><span class="sxs-lookup"><span data-stu-id="4313f-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="4313f-158">Il `source_path` s’agit du chemin d’accès relatif au référentiel de l’ancien article que vous supprimez.</span><span class="sxs-lookup"><span data-stu-id="4313f-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="4313f-159">Assurez-vous que le chemin d’accès commence `mixed-reality-docs` par et se termine par `.md` .</span><span class="sxs-lookup"><span data-stu-id="4313f-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="4313f-160">Il `redirect_url` s’agit de l’URL publique relative de l’ancien article au nouvel article.</span><span class="sxs-lookup"><span data-stu-id="4313f-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="4313f-161">Assurez-vous que cette URL ne contient pas ou, car elle fait référence à **l’URL** publique et non au `mixed-reality-docs` `.md` chemin d’accès du référentiel.</span><span class="sxs-lookup"><span data-stu-id="4313f-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="4313f-162">La liaison à une section dans le nouvel article à l’aide `#section` est autorisée.</span><span class="sxs-lookup"><span data-stu-id="4313f-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="4313f-163">Vous pouvez également utiliser un chemin d’accès absolu à un autre site ici, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4313f-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="4313f-164">indique si vous souhaitez conserver l’ID de document du fichier précédent.</span><span class="sxs-lookup"><span data-stu-id="4313f-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="4313f-165">La valeur par défaut `false` est .</span><span class="sxs-lookup"><span data-stu-id="4313f-165">The default is `false`.</span></span> <span data-ttu-id="4313f-166">À `true` utiliser si vous souhaitez conserver la valeur `ms.documentid` d’attribut de l’article redirigé.</span><span class="sxs-lookup"><span data-stu-id="4313f-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="4313f-167">Si vous conservez l’ID du document, les données, telles que les vues de page et les classements, sont transférées vers l’article cible.</span><span class="sxs-lookup"><span data-stu-id="4313f-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="4313f-168">Faites-le si la redirection est principalement un changement de nom et non un pointeur vers un autre article qui couvre uniquement une partie du même contenu.</span><span class="sxs-lookup"><span data-stu-id="4313f-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="4313f-169">Si vous ajoutez une redirection, assurez-vous également de supprimer l’ancien fichier.</span><span class="sxs-lookup"><span data-stu-id="4313f-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="4313f-170">Création d’un article</span><span class="sxs-lookup"><span data-stu-id="4313f-170">Creating a new article</span></span>

<span data-ttu-id="4313f-171">Utilisez le flux de travail suivant pour *créer des articles* dans le référentiel de documentation via GitHub dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="4313f-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="4313f-172">Créez une bifurcation de la branche « master » \*\*\*\* MicrosoftDocs/réalité mixte (à l’aide du bouton De la bifurcation dans le haut à droite).</span><span class="sxs-lookup"><span data-stu-id="4313f-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcation de la branche principale.](images/forkbranch.png)
   
2. <span data-ttu-id="4313f-174">Dans le dossier « mixed-reality-docs », sélectionnez **Créer** un fichier en haut à droite.</span><span class="sxs-lookup"><span data-stu-id="4313f-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="4313f-175">Créez un nom de page pour l’article (utilisez des traits d’union au lieu d’espaces et n’utilisez pas de ponctuation ou d’apostrophes) et ajoutez « .md »</span><span class="sxs-lookup"><span data-stu-id="4313f-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nommez votre nouvelle page.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="4313f-177">Veillez à créer le nouvel article à partir du dossier « mixed-reality-docs ».</span><span class="sxs-lookup"><span data-stu-id="4313f-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="4313f-178">Vous pouvez le confirmer en vérifiant « /mixed-reality-docs/ » dans la nouvelle ligne de nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="4313f-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="4313f-179">En haut de votre nouvelle page, ajoutez le bloc de métadonnées suivant :</span><span class="sxs-lookup"><span data-stu-id="4313f-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="4313f-180">Remplissez les champs de métadonnées appropriés selon les instructions de la [section ci-dessus.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="4313f-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="4313f-181">Écrire du contenu d’article [à l’aide des principes de base de Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="4313f-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="4313f-182">Ajoutez `## See also` une section au bas de l’article avec des liens vers d’autres articles pertinents.</span><span class="sxs-lookup"><span data-stu-id="4313f-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="4313f-183">Lorsque vous avez terminé, **sélectionnez Valider un nouveau fichier**.</span><span class="sxs-lookup"><span data-stu-id="4313f-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="4313f-184">Sélectionnez **Nouvelle** demande de pull et fusionnez la branche « master » de votre bifurcation dans MicrosoftDocs/mixed-reality 'master' (assurez-vous que la flèche pointe correctement).</span><span class="sxs-lookup"><span data-stu-id="4313f-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Créer une demande de tirer à partir de votre bifurcation dans MicrosoftDocs/réalité mixte](images/pr-to-master.png)

## <span data-ttu-id="4313f-186">Informations de base sur Markdown</span><span class="sxs-lookup"><span data-stu-id="4313f-186">Markdown basics</span></span>

<span data-ttu-id="4313f-187">Les ressources suivantes vous aideront à apprendre à modifier la documentation à l’aide de la langue Markdown :</span><span class="sxs-lookup"><span data-stu-id="4313f-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="4313f-188">Informations de base sur Markdown</span><span class="sxs-lookup"><span data-stu-id="4313f-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="4313f-189">Ressources supplémentaires pour écrire Markdown pour docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4313f-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="4313f-190">Ajout de tables</span><span class="sxs-lookup"><span data-stu-id="4313f-190">Adding tables</span></span>

<span data-ttu-id="4313f-191">En raison de la façon dont docs.microsoft.com tableaux de styles, ils n’auront pas de bordures ou de styles personnalisés, même si vous essayez inline CSS.</span><span class="sxs-lookup"><span data-stu-id="4313f-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="4313f-192">Il semblera fonctionner pendant une courte période de temps, mais finalement, la plateforme sera sans style du tableau.</span><span class="sxs-lookup"><span data-stu-id="4313f-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="4313f-193">Planifiez donc et maintenez vos tableaux simples.</span><span class="sxs-lookup"><span data-stu-id="4313f-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="4313f-194">[Voici un site qui facilite les tables Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="4313f-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="4313f-195">[L’extension Docs Markdown pour Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) facilite également la génération de tableau si vous utilisez Visual Studio Code (voir ci-dessous) pour modifier la documentation. [](#using-visual-studio-code)</span><span class="sxs-lookup"><span data-stu-id="4313f-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="4313f-196">Ajout d’images</span><span class="sxs-lookup"><span data-stu-id="4313f-196">Adding images</span></span>

<span data-ttu-id="4313f-197">Vous devrez charger vos images dans le dossier « mixed-reality-docs/images » dans le repo, puis les référencer correctement dans l’article.</span><span class="sxs-lookup"><span data-stu-id="4313f-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="4313f-198">Les images s’afficheront automatiquement en taille réelle, ce qui signifie que de grandes images rempliront toute la largeur de l’article.</span><span class="sxs-lookup"><span data-stu-id="4313f-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="4313f-199">Nous vous recommandons de pré-ret tailler vos images avant de les télécharger.</span><span class="sxs-lookup"><span data-stu-id="4313f-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="4313f-200">La largeur recommandée est entre 600 et 700 pixels, même si vous devez les dimensionnement vers le haut ou vers le bas s’il s’agit d’une capture d’écran épaisse ou d’une fraction d’une capture d’écran, respectivement.</span><span class="sxs-lookup"><span data-stu-id="4313f-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4313f-201">Vous pouvez uniquement charger des images vers votre repo bifurcation avant la fusion.</span><span class="sxs-lookup"><span data-stu-id="4313f-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="4313f-202">Par exemple, si vous envisagez d’ajouter des images à un article, vous devez d’abord utiliser [Visual Studio Code](#using-visual-studio-code) pour ajouter les images au dossier « images » de votre bifurcation ou vous assurer que vous avez effectué les étapes suivantes dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="4313f-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="4313f-203">Bifurcation du repo MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="4313f-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="4313f-204">Modification de l’article dans votre bifurcation.</span><span class="sxs-lookup"><span data-stu-id="4313f-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="4313f-205">Les images que vous référencez dans votre article ont été téléchargées vers le dossier « mixed-reality-docs/images » dans votre bifurcation.</span><span class="sxs-lookup"><span data-stu-id="4313f-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="4313f-206">Création **d’une demande de** pull pour fusionner votre bifurcation dans la branche MicrosoftDocs/master de réalité mixte.</span><span class="sxs-lookup"><span data-stu-id="4313f-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="4313f-207">Pour apprendre à configurer votre propre repo bifurpé, suivez les instructions de création [d’un article.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="4313f-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="4313f-208">Aperçu de votre travail</span><span class="sxs-lookup"><span data-stu-id="4313f-208">Previewing your work</span></span>

<span data-ttu-id="4313f-209">Lors de la modification dans GitHub via \*\*\*\* un navigateur web, vous pouvez sélectionner l’onglet Aperçu en haut de la page pour afficher un aperçu de votre travail avant de la validation.</span><span class="sxs-lookup"><span data-stu-id="4313f-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="4313f-210">L’aperçu de vos modifications sur review.docs.microsoft.com est disponible uniquement pour les employés de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4313f-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="4313f-211">Employés de Microsoft : une fois que vos contributions ont été fusionnées dans la branche « maître » , vous pouvez consulter le contenu avant qu’il ne soit https://review.docs.microsoft.com/hololens?branch=master public.</span><span class="sxs-lookup"><span data-stu-id="4313f-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="4313f-212">Recherchez votre article à l’aide de la table des matières dans la colonne de gauche.</span><span class="sxs-lookup"><span data-stu-id="4313f-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="4313f-213">Modification dans le navigateur et modification avec un client de bureau</span><span class="sxs-lookup"><span data-stu-id="4313f-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="4313f-214">La modification dans le navigateur est le moyen le plus simple d’apporter des modifications rapides, mais il existe quelques inconvénients :</span><span class="sxs-lookup"><span data-stu-id="4313f-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="4313f-215">Vous n’obtenez pas de vérification orthographie.</span><span class="sxs-lookup"><span data-stu-id="4313f-215">You don't get spell-check.</span></span>
- <span data-ttu-id="4313f-216">Vous n’obtenez aucun lien intelligent vers d’autres articles (vous devez taper manuellement le nom de fichier de l’article).</span><span class="sxs-lookup"><span data-stu-id="4313f-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="4313f-217">Le chargement et la référence d’images peuvent être compliqués.</span><span class="sxs-lookup"><span data-stu-id="4313f-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="4313f-218">Si vous préférez ne pas gérer ces problèmes, utilisez un client de bureau comme [Visual Studio Code](https://code.visualstudio.com/) avec quelques [extensions](#useful-extensions) utiles lors de la contribution.</span><span class="sxs-lookup"><span data-stu-id="4313f-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="4313f-219">Utilisation Visual Studio code</span><span class="sxs-lookup"><span data-stu-id="4313f-219">Using Visual Studio Code</span></span>

<span data-ttu-id="4313f-220">Pour les raisons répertoriées [ci-dessus,](#editing-in-the-browser-vs-editing-with-a-desktop-client)vous pouvez utiliser un client de bureau pour modifier la documentation au lieu d’un navigateur web.</span><span class="sxs-lookup"><span data-stu-id="4313f-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="4313f-221">Nous vous recommandons [d’Visual Studio code.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="4313f-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="4313f-222">Configuration</span><span class="sxs-lookup"><span data-stu-id="4313f-222">Setup</span></span>

<span data-ttu-id="4313f-223">Suivez ces étapes pour configurer Visual Studio code de manière à ce qu’il fonctionne avec ce repo :</span><span class="sxs-lookup"><span data-stu-id="4313f-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="4313f-224">Dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="4313f-224">In a web browser:</span></span>
    1. <span data-ttu-id="4313f-225">Installez [Git pour votre PC.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="4313f-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="4313f-226">Installez [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="4313f-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="4313f-227">Si ce n’est pas déjà fait, bifurquez [MicrosoftDocs/réalité](#creating-a-new-article) mixte.</span><span class="sxs-lookup"><span data-stu-id="4313f-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="4313f-228">Dans votre bifurcation, sélectionnez **Cloner ou téléchargez** et copiez l’URL.</span><span class="sxs-lookup"><span data-stu-id="4313f-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="4313f-229">Créez un clone local de votre bifurcation dans Visual Studio Code :</span><span class="sxs-lookup"><span data-stu-id="4313f-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="4313f-230">Dans le menu **Affichage,** sélectionnez **Palette de commandes.**</span><span class="sxs-lookup"><span data-stu-id="4313f-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="4313f-231">Tapez « Git : Clone ».</span><span class="sxs-lookup"><span data-stu-id="4313f-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="4313f-232">Collez l’URL que vous avez copiée.</span><span class="sxs-lookup"><span data-stu-id="4313f-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="4313f-233">Choisissez où enregistrer le clone sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="4313f-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="4313f-234">Sélectionnez **Ouvrir un repo** dans la fenêtre pop-up.</span><span class="sxs-lookup"><span data-stu-id="4313f-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="4313f-235">Modification de la documentation</span><span class="sxs-lookup"><span data-stu-id="4313f-235">Editing documentation</span></span>

<span data-ttu-id="4313f-236">Utilisez le flux de travail suivant pour apporter des modifications à la documentation avec Visual Studio Code :</span><span class="sxs-lookup"><span data-stu-id="4313f-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="4313f-237">Tous les conseils pour [la](#editing-an-existing-article) modification et la création d’articles, ainsi que les principes de base de la modification de [Markdown,](#markdown-basics)ci-dessus s’appliquent également lors de l’utilisation Visual Studio Code. [](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="4313f-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="4313f-238">Assurez-vous que votre bifurcation clonée est à jour avec le repo officiel.</span><span class="sxs-lookup"><span data-stu-id="4313f-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="4313f-239">Dans un navigateur web, créez une requête de pull pour synchroniser les modifications récentes apportées par d’autres contributeurs dans MicrosoftDocs/mixed-reality « master » à votre bifurcation (assurez-vous que la flèche pointe vers la bonne voie).</span><span class="sxs-lookup"><span data-stu-id="4313f-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchroniser les modifications de MicrosoftDocs/mixed-reality avec votre bifurcation](images/sync-repos.png)
      
   2. <span data-ttu-id="4313f-241">Dans Visual Studio code, sélectionnez le bouton de synchronisation pour synchroniser votre nouvelle bifurcation mise à jour avec le clone local.</span><span class="sxs-lookup"><span data-stu-id="4313f-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Cliquez sur l’image du bouton de synchronisation](images/sync-clone.png)
      
2. <span data-ttu-id="4313f-243">Créez ou modifiez des articles dans votre repo cloné à l’aide Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4313f-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="4313f-244">Modifiez un ou plusieurs articles (ajoutez des images au dossier « images » si nécessaire).</span><span class="sxs-lookup"><span data-stu-id="4313f-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="4313f-245">**Enregistrez** les modifications dans **l’Explorateur.**</span><span class="sxs-lookup"><span data-stu-id="4313f-245">**Save** changes in **Explorer**.</span></span>
      
      ![Sélectionnez « Enregistrer tout » dans l’Explorateur](images/explorer-save.png)
      
   3. <span data-ttu-id="4313f-247">**Valider toutes les modifications** dans le **contrôle de source** (écrire un message de validation lorsque vous y invitez).</span><span class="sxs-lookup"><span data-stu-id="4313f-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Choose «Commit all» in Source Control](images/source-control-commit.png)
      
   4. <span data-ttu-id="4313f-249">Sélectionnez **le bouton** de synchronisation pour synchroniser vos modifications à l’origine (votre bifurcation sur GitHub).</span><span class="sxs-lookup"><span data-stu-id="4313f-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Cliquez sur le bouton synchroniser](images/sync-back.png)
      
3. <span data-ttu-id="4313f-251">Dans un navigateur web, créez une requête de pull pour synchroniser les nouvelles modifications dans votre bifurcation avec MicrosoftDocs/mixed-reality 'master' (assurez-vous que la flèche pointe correctement).</span><span class="sxs-lookup"><span data-stu-id="4313f-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Créer une demande de tirer à partir de votre bifurcation dans MicrosoftDocs/réalité mixte](images/pr-to-master.png)

### <span data-ttu-id="4313f-253">Extensions utiles</span><span class="sxs-lookup"><span data-stu-id="4313f-253">Useful extensions</span></span>

<span data-ttu-id="4313f-254">Les extensions Visual Studio code suivantes sont utiles lors de la modification de la documentation :</span><span class="sxs-lookup"><span data-stu-id="4313f-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="4313f-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span><span class="sxs-lookup"><span data-stu-id="4313f-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="4313f-256">Recherchez et référencez des images que vous avez téléchargées.</span><span class="sxs-lookup"><span data-stu-id="4313f-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="4313f-257">Ajoutez une mise en forme telle que des listes, des tableaux et des call-outs spécifiques à des documents comme `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="4313f-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="4313f-258">Rechercher et référencer des liens internes et des signets (liens vers des sections spécifiques dans une page).</span><span class="sxs-lookup"><span data-stu-id="4313f-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="4313f-259">Les erreurs de mise en forme sont mises en surbrillante (pointez votre souris sur l’erreur pour en savoir plus).</span><span class="sxs-lookup"><span data-stu-id="4313f-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="4313f-260">[Vérification de l’orthographe du code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : les mots mal orthographiés sont soulignés ; cliquez avec le bouton droit sur un mot mal orthographié pour le modifier ou l’enregistrer dans le dictionnaire.</span><span class="sxs-lookup"><span data-stu-id="4313f-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
