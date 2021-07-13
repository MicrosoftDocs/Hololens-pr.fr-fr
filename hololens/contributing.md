---
title: Instructions de contribution
description: apprenez à contribuer aux documents HoloLens sur la plateforme docs.microsoft.com à l’aide de la démarque GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635668"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="2ef24-103">contribution à la documentation HoloLens</span><span class="sxs-lookup"><span data-stu-id="2ef24-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="2ef24-104">bienvenue dans la [documentation de HoloLens](https://github.com/MicrosoftDocs/Hololens).</span><span class="sxs-lookup"><span data-stu-id="2ef24-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="2ef24-105">Tous les articles que vous créez ou modifiez dans ce référentiel **seront visibles par le public.**</span><span class="sxs-lookup"><span data-stu-id="2ef24-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="2ef24-106">HoloLens docs sont affichées sur la plate-forme docs.microsoft.com, qui utilise la démarque GitHub-version avec les fonctionnalités Markdig.</span><span class="sxs-lookup"><span data-stu-id="2ef24-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="2ef24-107">Le contenu que vous modifiez dans ce référentiel est mis en forme dans des pages stylisées qui s’affichent dans/hololens.</span><span class="sxs-lookup"><span data-stu-id="2ef24-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="2ef24-108">Cette page décrit les étapes et les instructions de base pour contribuer et les liens vers les concepts de base de la marque.</span><span class="sxs-lookup"><span data-stu-id="2ef24-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="2ef24-109">Merci pour votre contribution !</span><span class="sxs-lookup"><span data-stu-id="2ef24-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="2ef24-110">Pensions disponibles</span><span class="sxs-lookup"><span data-stu-id="2ef24-110">Available repos</span></span>

| <span data-ttu-id="2ef24-111">Nom du dépôt</span><span class="sxs-lookup"><span data-stu-id="2ef24-111">Repository name</span></span> | <span data-ttu-id="2ef24-112">URL</span><span class="sxs-lookup"><span data-stu-id="2ef24-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="2ef24-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="2ef24-113">HoloLens</span></span> | [<span data-ttu-id="2ef24-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="2ef24-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="2ef24-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="2ef24-115">Mixed Reality</span></span> | [<span data-ttu-id="2ef24-116">MicrosoftDocs/réalité mixte</span><span class="sxs-lookup"><span data-stu-id="2ef24-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="2ef24-117">Guide des passionnés de VR</span><span class="sxs-lookup"><span data-stu-id="2ef24-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="2ef24-118">MicrosoftDocs/Mixed-Reality/passionné-Guide</span><span class="sxs-lookup"><span data-stu-id="2ef24-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="2ef24-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2ef24-119">Before you start</span></span>

<span data-ttu-id="2ef24-120">si vous n’en avez pas déjà un, vous devez [créer un compte GitHub](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="2ef24-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="2ef24-121">si vous êtes un employé de microsoft, liez votre compte GitHub à votre alias microsoft sur le [portail Open Source de microsoft](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2ef24-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="2ef24-122">Rejoignez les organisations **« Microsoft »** et **« MicrosoftDocs »** .</span><span class="sxs-lookup"><span data-stu-id="2ef24-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="2ef24-123">quand vous configurez votre compte GitHub, nous vous recommandons également les précautions de sécurité suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ef24-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="2ef24-124">créez un [mot de passe fort pour votre compte GitHub](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="2ef24-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="2ef24-125">Activez [l’authentification à deux facteurs](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="2ef24-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="2ef24-126">Enregistrez vos [codes de récupération](https://github.com/settings/auth/recovery-codes) dans un endroit sûr.</span><span class="sxs-lookup"><span data-stu-id="2ef24-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="2ef24-127">Mettez à jour vos [paramètres de profil public](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="2ef24-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="2ef24-128">Définissez votre nom et envisagez de configurer votre adresse de messagerie *publique* pour *ne pas afficher mon adresse de messagerie*.</span><span class="sxs-lookup"><span data-stu-id="2ef24-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="2ef24-129">Nous vous recommandons de télécharger une image de profil, car une miniature est affichée sur les pages docs auxquelles vous contribuez.</span><span class="sxs-lookup"><span data-stu-id="2ef24-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="2ef24-130">Si vous envisagez d’utiliser la ligne de commande, vous pouvez configurer [git Credential Manager pour Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="2ef24-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="2ef24-131">De cette façon, vous n’aurez pas à entrer votre mot de passe chaque fois que vous effectuerez une contribution.</span><span class="sxs-lookup"><span data-stu-id="2ef24-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="2ef24-132">le système de publication étant lié à GitHub, ces étapes sont importantes.</span><span class="sxs-lookup"><span data-stu-id="2ef24-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="2ef24-133">vous êtes alors inscrit comme auteur ou contributeur à chaque article à l’aide de votre alias de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2ef24-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="2ef24-134">Modification d’un article existant</span><span class="sxs-lookup"><span data-stu-id="2ef24-134">Editing an existing article</span></span>

<span data-ttu-id="2ef24-135">utilisez le flux de travail suivant pour mettre à jour *un article existant* via GitHub dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="2ef24-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="2ef24-136">Accédez à l’article que vous souhaitez modifier dans le dossier « Mixed-Real-docs ».</span><span class="sxs-lookup"><span data-stu-id="2ef24-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="2ef24-137">Sélectionnez le bouton modifier (icône en forme de crayon) dans le coin supérieur droit, qui dupliquera automatiquement une branche jetable en dehors de la branche « master ».</span><span class="sxs-lookup"><span data-stu-id="2ef24-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Modifier un article.](images/editpage.png)
   
3. <span data-ttu-id="2ef24-139">Modifiez le contenu de l’article en fonction des [« principes de base »](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="2ef24-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="2ef24-140">Mettez à jour les métadonnées en haut de chaque article :</span><span class="sxs-lookup"><span data-stu-id="2ef24-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="2ef24-141">**titre**: titre de la page qui s’affiche sous l’onglet navigateur lorsque l’article est affiché.</span><span class="sxs-lookup"><span data-stu-id="2ef24-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="2ef24-142">Les titres de page sont utilisés pour le SEO et l’indexation. par conséquent, ne modifiez pas le titre, sauf si cela est nécessaire (bien que cela soit moins critique avant que la documentation ne soit publique).</span><span class="sxs-lookup"><span data-stu-id="2ef24-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="2ef24-143">**Description**: rédigez une brève description du contenu de l’article, qui améliore le SEO et la découverte.</span><span class="sxs-lookup"><span data-stu-id="2ef24-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="2ef24-144">**auteur**: si vous êtes le propriétaire principal de la page, ajoutez votre alias de GitHub ici.</span><span class="sxs-lookup"><span data-stu-id="2ef24-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="2ef24-145">**ms. Author**: Si vous êtes le propriétaire principal de la page, ajoutez votre alias Microsoft ici (vous n’en avez pas besoin @microsoft.com , juste l’alias).</span><span class="sxs-lookup"><span data-stu-id="2ef24-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="2ef24-146">**ms. date**: mettez à jour la date si vous ajoutez du contenu majeur à la page, mais pas pour des correctifs tels que la clarification, la mise en forme, la grammaire ou l’orthographe.</span><span class="sxs-lookup"><span data-stu-id="2ef24-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="2ef24-147">**Mots clés**: aide sur les mots clés dans SEO (optimisation du moteur de recherche).</span><span class="sxs-lookup"><span data-stu-id="2ef24-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="2ef24-148">Ajoutez des mots clés, séparés par une virgule et un espace, qui sont spécifiques à votre article, mais pas de ponctuation après le dernier mot clé de votre liste.</span><span class="sxs-lookup"><span data-stu-id="2ef24-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="2ef24-149">Vous n’avez pas besoin d’ajouter des mots clés globaux qui s’appliquent à tous les articles, car ceux-ci sont gérés ailleurs.</span><span class="sxs-lookup"><span data-stu-id="2ef24-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="2ef24-150">Lorsque vous avez terminé les modifications de votre article, faites défiler la liste vers le dessous et sélectionnez **proposer une modification de fichier**.</span><span class="sxs-lookup"><span data-stu-id="2ef24-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="2ef24-151">Sur la page suivante, sélectionnez **créer une demande de tirage (pull Request** ) pour fusionner votre branche créée automatiquement dans « Master ».</span><span class="sxs-lookup"><span data-stu-id="2ef24-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="2ef24-152">Répétez les étapes ci-dessus pour le prochain article que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="2ef24-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="2ef24-153">Attribution d’un nouveau nom ou suppression d’un article existant</span><span class="sxs-lookup"><span data-stu-id="2ef24-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="2ef24-154">Si votre modification renomme ou supprime un article existant, veillez à ajouter une redirection.</span><span class="sxs-lookup"><span data-stu-id="2ef24-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="2ef24-155">De cette façon, toute personne disposant d’un lien vers l’article existant continuera de se retrouver au bon endroit.</span><span class="sxs-lookup"><span data-stu-id="2ef24-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="2ef24-156">Les redirections sont gérées par l' .openpublishing.redirection.jssur le fichier à la racine du référentiel.</span><span class="sxs-lookup"><span data-stu-id="2ef24-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="2ef24-157">Pour ajouter une redirection à .openpublishing.redirection.jssur, ajoutez une entrée au `redirections` tableau :</span><span class="sxs-lookup"><span data-stu-id="2ef24-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="2ef24-158">`source_path`Est le chemin d’accès relatif au référentiel relatif à l’ancien article que vous supprimez.</span><span class="sxs-lookup"><span data-stu-id="2ef24-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="2ef24-159">Assurez-vous que le chemin commence par `mixed-reality-docs` et se termine par `.md` .</span><span class="sxs-lookup"><span data-stu-id="2ef24-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="2ef24-160">`redirect_url`Est l’URL publique relative de l’ancien article vers le nouvel article.</span><span class="sxs-lookup"><span data-stu-id="2ef24-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="2ef24-161">Assurez-vous que cette URL **ne** contient `mixed-reality-docs` `.md` pas ou, car elle fait référence à l’URL publique et non au chemin d’accès au référentiel.</span><span class="sxs-lookup"><span data-stu-id="2ef24-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="2ef24-162">La liaison à une section dans le nouvel article à l’aide de `#section` est autorisée.</span><span class="sxs-lookup"><span data-stu-id="2ef24-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="2ef24-163">Vous pouvez également utiliser un chemin d’accès absolu à un autre site, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2ef24-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="2ef24-164">`redirect_document_id` indique si vous souhaitez conserver l’ID du document dans le fichier précédent.</span><span class="sxs-lookup"><span data-stu-id="2ef24-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="2ef24-165">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="2ef24-165">The default is `false`.</span></span> <span data-ttu-id="2ef24-166">Utilisez `true` si vous souhaitez conserver la `ms.documentid` valeur d’attribut de l’article Redirigé.</span><span class="sxs-lookup"><span data-stu-id="2ef24-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="2ef24-167">Si vous conservez l’ID de document, les données, telles que les affichages de page et les classements, seront transférées vers l’article cible.</span><span class="sxs-lookup"><span data-stu-id="2ef24-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="2ef24-168">Procédez ainsi si la redirection est principalement un changement de nom, et non un pointeur vers un autre article qui couvre uniquement une partie du même contenu.</span><span class="sxs-lookup"><span data-stu-id="2ef24-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="2ef24-169">Si vous ajoutez une redirection, veillez à supprimer également l’ancien fichier.</span><span class="sxs-lookup"><span data-stu-id="2ef24-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="2ef24-170">Création d’un article</span><span class="sxs-lookup"><span data-stu-id="2ef24-170">Creating a new article</span></span>

<span data-ttu-id="2ef24-171">utilisez le flux de travail suivant pour *créer de nouveaux articles* dans la documentation référentiel via GitHub dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="2ef24-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="2ef24-172">Créez une fourche à partir de la branche « master » MicrosoftDocs/de la réalité mixte (à l’aide du bouton de **branchement** dans le coin supérieur droit).</span><span class="sxs-lookup"><span data-stu-id="2ef24-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Dupliquez la branche principale.](images/forkbranch.png)
   
2. <span data-ttu-id="2ef24-174">Dans le dossier « Mixed-Real-docs », sélectionnez **créer un fichier** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="2ef24-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="2ef24-175">Créer un nom de page pour l’article (utilisez des traits d’Union à la place d’espaces et n’utilisez pas de ponctuation ou d’apostrophes) et ajoutez « . MD »</span><span class="sxs-lookup"><span data-stu-id="2ef24-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nommez votre nouvelle page.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="2ef24-177">Veillez à créer le nouvel article dans le dossier « Mixed-Real-docs ».</span><span class="sxs-lookup"><span data-stu-id="2ef24-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="2ef24-178">Vous pouvez le vérifier en recherchant « /Mixed-Reality-docs/ » dans la ligne du nouveau nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="2ef24-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="2ef24-179">En haut de votre nouvelle page, ajoutez le bloc de métadonnées suivant :</span><span class="sxs-lookup"><span data-stu-id="2ef24-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="2ef24-180">Renseignez les champs de métadonnées pertinents conformément aux instructions de la [section ci-dessus](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="2ef24-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="2ef24-181">Écrivez le contenu de l’article à l’aide des [principes fondamentaux](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="2ef24-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="2ef24-182">Ajoutez une `## See also` section au bas de l’article avec des liens vers d’autres articles pertinents.</span><span class="sxs-lookup"><span data-stu-id="2ef24-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="2ef24-183">Lorsque vous avez terminé, sélectionnez **valider le nouveau fichier**.</span><span class="sxs-lookup"><span data-stu-id="2ef24-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="2ef24-184">Sélectionnez **nouvelle demande de tirage (pull Request** ) et fusionnez la branche principale de votre branche dans MicrosoftDocs/Mixed-Reality’Master' (Assurez-vous que la flèche pointe vers la bonne voie).</span><span class="sxs-lookup"><span data-stu-id="2ef24-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Créer une requête de tirage (pull request) à partir de votre fourche dans MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="2ef24-186">Les bases de Markdown</span><span class="sxs-lookup"><span data-stu-id="2ef24-186">Markdown basics</span></span>

<span data-ttu-id="2ef24-187">Les ressources suivantes vous permettront d’apprendre à modifier la documentation à l’aide du langage de démarque :</span><span class="sxs-lookup"><span data-stu-id="2ef24-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="2ef24-188">Principes de base de Markdown</span><span class="sxs-lookup"><span data-stu-id="2ef24-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="2ef24-189">Ressources supplémentaires pour l’écriture de la démarque pour docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2ef24-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="2ef24-190">Ajout de tables</span><span class="sxs-lookup"><span data-stu-id="2ef24-190">Adding tables</span></span>

<span data-ttu-id="2ef24-191">En raison de la façon dont les tableaux de styles docs.microsoft.com, ils n’ont pas de bordures ou de styles personnalisés, même si vous essayez le style CSS en ligne.</span><span class="sxs-lookup"><span data-stu-id="2ef24-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="2ef24-192">Il semblera fonctionner pendant une période de temps limitée, mais la plateforme finira par supprimer le style de la table.</span><span class="sxs-lookup"><span data-stu-id="2ef24-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="2ef24-193">Vous devez donc anticiper et garder vos tables simples.</span><span class="sxs-lookup"><span data-stu-id="2ef24-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="2ef24-194">[Voici un site qui simplifie les tableaux de démarques](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="2ef24-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="2ef24-195">l' [Extension Docs de démarque pour Visual Studio Code](/teamblog/docs-extension) facilite également la génération de table si vous utilisez [Visual Studio Code (voir ci-dessous)](#using-visual-studio-code) pour modifier la documentation.</span><span class="sxs-lookup"><span data-stu-id="2ef24-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="2ef24-196">Ajout d’images</span><span class="sxs-lookup"><span data-stu-id="2ef24-196">Adding images</span></span>

<span data-ttu-id="2ef24-197">Vous devez charger vos images dans le dossier « Mixed-Real-docs/images » dans référentiel, puis les référencer de manière appropriée dans l’article.</span><span class="sxs-lookup"><span data-stu-id="2ef24-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="2ef24-198">Les images s’affichent automatiquement à la taille maximale, ce qui signifie que les images volumineuses remplissent toute la largeur de l’article.</span><span class="sxs-lookup"><span data-stu-id="2ef24-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="2ef24-199">Nous vous recommandons de prédimensionner vos images avant de les charger.</span><span class="sxs-lookup"><span data-stu-id="2ef24-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="2ef24-200">La largeur recommandée est comprise entre 600 et 700 pixels, même si vous devez monter ou diminuer la taille s’il s’agit d’une capture d’écran dense ou d’une fraction d’une capture d’écran, respectivement.</span><span class="sxs-lookup"><span data-stu-id="2ef24-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2ef24-201">Vous pouvez uniquement charger des images sur vos référentiel dupliqués avant la fusion.</span><span class="sxs-lookup"><span data-stu-id="2ef24-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="2ef24-202">par conséquent, si vous envisagez d’ajouter des images à un article, vous devez [utiliser Visual Studio Code](#using-visual-studio-code) pour ajouter d’abord les images au dossier « images » de votre branche, ou vous assurer que vous avez effectué les opérations suivantes dans un navigateur web :</span><span class="sxs-lookup"><span data-stu-id="2ef24-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="2ef24-203">A fait la duplication du référentiel MicrosoftDocs/Mixed-Reality.</span><span class="sxs-lookup"><span data-stu-id="2ef24-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="2ef24-204">Modification de l’article dans votre fourche.</span><span class="sxs-lookup"><span data-stu-id="2ef24-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="2ef24-205">Téléchargez les images que vous référencez dans votre article dans le dossier « Mixed-Real-docs/images » de votre fourche.</span><span class="sxs-lookup"><span data-stu-id="2ef24-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="2ef24-206">Création d’une **requête de tirage** pour fusionner votre fourche dans la branche « master » MicrosoftDocs/de la réalité mixte.</span><span class="sxs-lookup"><span data-stu-id="2ef24-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="2ef24-207">Pour savoir comment configurer vos propres référentiel dupliqués, suivez les instructions de création d' [un nouvel article](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="2ef24-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="2ef24-208">Aperçu de votre travail</span><span class="sxs-lookup"><span data-stu-id="2ef24-208">Previewing your work</span></span>

<span data-ttu-id="2ef24-209">pendant la modification de GitHub via un navigateur web, vous pouvez sélectionner l’onglet d' **aperçu** près du haut de la page pour afficher un aperçu de votre travail avant de le valider.</span><span class="sxs-lookup"><span data-stu-id="2ef24-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="2ef24-210">L’aperçu de vos modifications sur review.docs.microsoft.com est uniquement disponible pour les employés de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ef24-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="2ef24-211">Employés de Microsoft : une fois vos contributions fusionnées dans la branche principale, vous pouvez passer en revue le contenu avant qu’il ne soit public sur </hololens ? Branch = Master>.</span><span class="sxs-lookup"><span data-stu-id="2ef24-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="2ef24-212">Recherchez votre article à l’aide de la table des matières de la colonne de gauche.</span><span class="sxs-lookup"><span data-stu-id="2ef24-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="2ef24-213">Modification dans le navigateur et modification avec un client Desktop</span><span class="sxs-lookup"><span data-stu-id="2ef24-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="2ef24-214">La modification dans le navigateur est le moyen le plus simple pour apporter des modifications rapides, toutefois, il existe quelques inconvénients :</span><span class="sxs-lookup"><span data-stu-id="2ef24-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="2ef24-215">Vous n’avez pas de vérification orthographique.</span><span class="sxs-lookup"><span data-stu-id="2ef24-215">You don't get spell-check.</span></span>
- <span data-ttu-id="2ef24-216">Vous n’avez pas de lien intelligent vers d’autres articles (vous devez taper manuellement le nom de fichier de l’article).</span><span class="sxs-lookup"><span data-stu-id="2ef24-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="2ef24-217">Il peut être laborieux de charger et de référencer des images.</span><span class="sxs-lookup"><span data-stu-id="2ef24-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="2ef24-218">si vous préférez ne pas traiter ces problèmes, utilisez un client de bureau comme [Visual Studio Code](https://code.visualstudio.com/) avec quelques [extensions utiles](#useful-extensions) pour contribuer.</span><span class="sxs-lookup"><span data-stu-id="2ef24-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="2ef24-219">Utilisation de Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2ef24-219">Using Visual Studio Code</span></span>

<span data-ttu-id="2ef24-220">Pour les raisons mentionnées [ci-dessus](#editing-in-the-browser-vs-editing-with-a-desktop-client), vous préférerez peut-être utiliser un client de bureau pour modifier la documentation au lieu d’un navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="2ef24-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="2ef24-221">Nous vous recommandons d’utiliser [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="2ef24-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="2ef24-222">Programme d’installation</span><span class="sxs-lookup"><span data-stu-id="2ef24-222">Setup</span></span>

<span data-ttu-id="2ef24-223">procédez comme suit pour configurer Visual Studio Code pour qu’il fonctionne avec ce référentiel :</span><span class="sxs-lookup"><span data-stu-id="2ef24-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="2ef24-224">Dans un navigateur Web :</span><span class="sxs-lookup"><span data-stu-id="2ef24-224">In a web browser:</span></span>
    1. <span data-ttu-id="2ef24-225">Installez [git pour votre PC](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="2ef24-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="2ef24-226">Installez [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="2ef24-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="2ef24-227">[Duplication de MicrosoftDocs/Mixed-realisation](#creating-a-new-article) si vous ne l’avez pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="2ef24-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="2ef24-228">Dans votre fourche, sélectionnez **cloner ou télécharger** et copiez l’URL.</span><span class="sxs-lookup"><span data-stu-id="2ef24-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="2ef24-229">Créez un clone local de votre fourche dans Visual Studio Code :</span><span class="sxs-lookup"><span data-stu-id="2ef24-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="2ef24-230">Dans le menu **affichage** , sélectionnez **palette de commandes**.</span><span class="sxs-lookup"><span data-stu-id="2ef24-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="2ef24-231">Tapez « git : Clone ».</span><span class="sxs-lookup"><span data-stu-id="2ef24-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="2ef24-232">Collez l’URL que vous avez copiée.</span><span class="sxs-lookup"><span data-stu-id="2ef24-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="2ef24-233">Choisissez l’emplacement où enregistrer le clone sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="2ef24-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="2ef24-234">Sélectionnez **ouvrir référentiel** dans la fenêtre contextuelle.</span><span class="sxs-lookup"><span data-stu-id="2ef24-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="2ef24-235">Modification de la documentation</span><span class="sxs-lookup"><span data-stu-id="2ef24-235">Editing documentation</span></span>

<span data-ttu-id="2ef24-236">Utilisez le flux de travail suivant pour apporter des modifications à la documentation avec Visual Studio Code :</span><span class="sxs-lookup"><span data-stu-id="2ef24-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="2ef24-237">toutes les instructions relatives à la [modification](#editing-an-existing-article) et à la [création](#creating-a-new-article) d’articles, ainsi que les [principes fondamentaux de la modification de la démarque](#markdown-basics), ci-dessus s’appliquent également à l’utilisation de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2ef24-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="2ef24-238">Assurez-vous que votre fourche cloné est à jour avec la référentiel officielle.</span><span class="sxs-lookup"><span data-stu-id="2ef24-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="2ef24-239">Dans un navigateur Web, créez une requête de tirage pour synchroniser les modifications récentes des autres contributeurs de MicrosoftDocs/Mixed-Reality’Master’sur votre fourche (Assurez-vous que la flèche pointe vers la bonne voie).</span><span class="sxs-lookup"><span data-stu-id="2ef24-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchroniser les modifications de MicrosoftDocs/Mixed-Reality avec votre fourche](images/sync-repos.png)
      
   2. <span data-ttu-id="2ef24-241">dans Visual Studio Code, sélectionnez le bouton synchroniser pour synchroniser votre branche fraîchement mise à jour sur le clone local.</span><span class="sxs-lookup"><span data-stu-id="2ef24-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Cliquer sur l’image du bouton de synchronisation](images/sync-clone.png)
      
2. <span data-ttu-id="2ef24-243">Créez ou modifiez des articles dans votre référentiel cloné à l’aide de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2ef24-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="2ef24-244">Modifiez un ou plusieurs articles (ajoutez des images au dossier « images » si nécessaire).</span><span class="sxs-lookup"><span data-stu-id="2ef24-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="2ef24-245">**Enregistrer** les modifications dans l' **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="2ef24-245">**Save** changes in **Explorer**.</span></span>
      
      ![Choisissez « Enregistrer tout » dans l’Explorateur](images/explorer-save.png)
      
   3. <span data-ttu-id="2ef24-247">**Valide toutes les** modifications dans **le contrôle de code source** (message de validation en écriture quand vous y êtes invité).</span><span class="sxs-lookup"><span data-stu-id="2ef24-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Choisissez « valider tout » dans le contrôle de code source](images/source-control-commit.png)
      
   4. <span data-ttu-id="2ef24-249">Sélectionnez le bouton **synchroniser** pour resynchroniser vos modifications avec l’origine (votre fourche sur GitHub).</span><span class="sxs-lookup"><span data-stu-id="2ef24-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Cliquez sur le bouton synchroniser.](images/sync-back.png)
      
3. <span data-ttu-id="2ef24-251">Dans un navigateur Web, créez une requête de tirage pour synchroniser les modifications apportées à votre fourche en MicrosoftDocs/Mixed-Reality’Master' (Assurez-vous que la flèche pointe vers la bonne voie).</span><span class="sxs-lookup"><span data-stu-id="2ef24-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Créer une requête de tirage (pull request) à partir de votre fourche dans MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="2ef24-253">Extensions utiles</span><span class="sxs-lookup"><span data-stu-id="2ef24-253">Useful extensions</span></span>

<span data-ttu-id="2ef24-254">les extensions de Visual Studio Code suivantes sont utiles lors de la modification de la documentation :</span><span class="sxs-lookup"><span data-stu-id="2ef24-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="2ef24-255">[Extension docs de la marque pour Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) -utilisez **Alt + M** pour afficher un menu d’options de création de documents, comme :</span><span class="sxs-lookup"><span data-stu-id="2ef24-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="2ef24-256">Recherchez et référencez des images que vous avez téléchargées.</span><span class="sxs-lookup"><span data-stu-id="2ef24-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="2ef24-257">Ajoutez une mise en forme comme des listes, des tables et des appels spécifiques aux documents, comme `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="2ef24-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="2ef24-258">Recherchez et référencez des liens et des signets internes (liens vers des sections spécifiques dans une page).</span><span class="sxs-lookup"><span data-stu-id="2ef24-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="2ef24-259">Les erreurs de mise en forme sont mises en surbrillance (pointez votre souris sur l’erreur pour en savoir plus).</span><span class="sxs-lookup"><span data-stu-id="2ef24-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="2ef24-260">[Vérificateur orthographique de code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : les mots mal orthographiés sont soulignés. Cliquez avec le bouton droit sur un mot mal orthographié pour le modifier ou enregistrez-le dans le dictionnaire.</span><span class="sxs-lookup"><span data-stu-id="2ef24-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
