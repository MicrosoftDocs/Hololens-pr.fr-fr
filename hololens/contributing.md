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
# <span data-ttu-id="c3c73-103">Contribution à la documentation HoloLens</span><span class="sxs-lookup"><span data-stu-id="c3c73-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="c3c73-104">Bienvenue dans la [documentation HoloLens](https://github.com/MicrosoftDocs/Hololens).</span><span class="sxs-lookup"><span data-stu-id="c3c73-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="c3c73-105">Tout article créé ou modifié dans ce référentiel Samples **sera visible par le public.**</span><span class="sxs-lookup"><span data-stu-id="c3c73-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="c3c73-106">Les documents HoloLens sont affichés sur la plateforme docs.microsoft.com, qui utilise la démarque GitHub-parfumée avec des fonctions Markdig.</span><span class="sxs-lookup"><span data-stu-id="c3c73-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="c3c73-107">Le contenu que vous modifiez dans ce référentiel Samples est mis en forme en pages stylisées qui s’affichent à l’adresse https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="c3c73-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="c3c73-108">Cette page présente les étapes de base et les recommandations en matière de connaissances et de liens vers des notions de base de la marque.</span><span class="sxs-lookup"><span data-stu-id="c3c73-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="c3c73-109">Merci pour votre contribution.</span><span class="sxs-lookup"><span data-stu-id="c3c73-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="c3c73-110">Pensions disponibles</span><span class="sxs-lookup"><span data-stu-id="c3c73-110">Available repos</span></span>

| <span data-ttu-id="c3c73-111">Nom du référentiel</span><span class="sxs-lookup"><span data-stu-id="c3c73-111">Repository name</span></span> | <span data-ttu-id="c3c73-112">URL</span><span class="sxs-lookup"><span data-stu-id="c3c73-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="c3c73-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="c3c73-113">HoloLens</span></span> | [<span data-ttu-id="c3c73-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="c3c73-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="c3c73-115">Réalité mixte</span><span class="sxs-lookup"><span data-stu-id="c3c73-115">Mixed Reality</span></span> | [<span data-ttu-id="c3c73-116">MicrosoftDocs/Mixed-Reality</span><span class="sxs-lookup"><span data-stu-id="c3c73-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="c3c73-117">Guide sur les adeptes du VR</span><span class="sxs-lookup"><span data-stu-id="c3c73-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="c3c73-118">MicrosoftDocs/Mixed-Really-Guide</span><span class="sxs-lookup"><span data-stu-id="c3c73-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="c3c73-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c3c73-119">Before you start</span></span>

<span data-ttu-id="c3c73-120">Si vous n’en avez pas encore, vous devez [créer un compte GitHub](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="c3c73-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="c3c73-121">Si vous êtes un employé de Microsoft, liez votre compte GitHub à votre alias Microsoft dans le [portail Microsoft Open source](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c3c73-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="c3c73-122">Rejoignez les organisations « **Microsoft»** et **«MicrosoftDocs»** .</span><span class="sxs-lookup"><span data-stu-id="c3c73-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="c3c73-123">Lorsque vous configurez votre compte GitHub, nous vous recommandons également de procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="c3c73-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="c3c73-124">Créez un [mot de passe sécurisé pour votre compte GitHub](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="c3c73-124">Create a [strong password for your Github account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="c3c73-125">Activez [l’authentification à deux facteurs](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="c3c73-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="c3c73-126">Enregistrez vos [codes de récupération](https://github.com/settings/auth/recovery-codes) en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="c3c73-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="c3c73-127">Mettez à jour vos [paramètres de profil public](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="c3c73-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="c3c73-128">Définissez votre nom et envisagez de configurer votre adresse de *messagerie publique* de façon à *ne pas afficher mon adresse de messagerie*.</span><span class="sxs-lookup"><span data-stu-id="c3c73-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="c3c73-129">Nous vous recommandons de télécharger une image de profil, car une miniature apparaît sur les pages de docs auxquelles vous participez.</span><span class="sxs-lookup"><span data-stu-id="c3c73-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="c3c73-130">Si vous envisagez d’utiliser la ligne de commande, envisagez de configurer le [Gestionnaire d’informations d’identification git pour Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="c3c73-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="c3c73-131">Ainsi, vous n’aurez pas à entrer votre mot de passe chaque fois que vous faites une contribution.</span><span class="sxs-lookup"><span data-stu-id="c3c73-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="c3c73-132">Le système de publication est lié à GitHub; il est donc important de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="c3c73-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="c3c73-133">Dans le cadre de l’utilisation de votre alias GitHub, vous serez répertorié comme auteur ou collaborateur.</span><span class="sxs-lookup"><span data-stu-id="c3c73-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="c3c73-134">Modification d’un article existant</span><span class="sxs-lookup"><span data-stu-id="c3c73-134">Editing an existing article</span></span>

<span data-ttu-id="c3c73-135">Utilisez le flux de travail suivant pour apporter des mises à jour à *un article existant* via github dans un navigateur Web:</span><span class="sxs-lookup"><span data-stu-id="c3c73-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="c3c73-136">Accédez à l’article que vous souhaitez modifier dans le dossier «Mixed-Real-docs».</span><span class="sxs-lookup"><span data-stu-id="c3c73-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>
2. <span data-ttu-id="c3c73-137">Sélectionnez le bouton modifier (icône en forme de crayon) dans le coin supérieur droit, qui répartir automatiquement une branche jetable de la branche «maître».</span><span class="sxs-lookup"><span data-stu-id="c3c73-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Modifier un article](images/editpage.png)
3. <span data-ttu-id="c3c73-139">Modifiez le contenu de l’article en fonction des [principes de base de la démarque](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="c3c73-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>
4. <span data-ttu-id="c3c73-140">Dans la partie supérieure de chaque article, procédez à la mise à jour des métadonnées:</span><span class="sxs-lookup"><span data-stu-id="c3c73-140">Update metadata at the top of each article:</span></span>
   * <span data-ttu-id="c3c73-141">**titre**: titre de page qui s’affiche dans l’onglet du navigateur lors de l’affichage de l’article.</span><span class="sxs-lookup"><span data-stu-id="c3c73-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="c3c73-142">Les titres de page sont utilisés pour les fonctions SEO et indexation; par conséquent, ne modifiez pas le titre sauf nécessité</span><span class="sxs-lookup"><span data-stu-id="c3c73-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="c3c73-143">**Description**: rédigez une brève description du contenu de l’article, qui amplifie le moteur SEO et la découverte.</span><span class="sxs-lookup"><span data-stu-id="c3c73-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="c3c73-144">**auteur**: Si vous êtes le propriétaire principal de la page, ajoutez votre alias GitHub ici.</span><span class="sxs-lookup"><span data-stu-id="c3c73-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="c3c73-145">**ms. Author**: Si vous êtes le propriétaire principal de la page, ajoutez votre alias Microsoft ici (vous n’avez pas besoin de @microsoft. com, uniquement l’alias).</span><span class="sxs-lookup"><span data-stu-id="c3c73-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="c3c73-146">**ms. date**: mettre à jour la date si vous ajoutez du contenu principal à la page, mais pas pour des corrections telles que la clarification, la mise en forme, la grammaire et l’orthographe.</span><span class="sxs-lookup"><span data-stu-id="c3c73-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="c3c73-147">**Mots clés**: aide sur les mots-clés dans SEO (optimisation du moteur de recherche).</span><span class="sxs-lookup"><span data-stu-id="c3c73-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="c3c73-148">Ajoutez des mots-clés, séparés par une virgule et un espace, qui sont propres à votre article, mais pas de ponctuation après le dernier mot clé de votre liste.</span><span class="sxs-lookup"><span data-stu-id="c3c73-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="c3c73-149">Vous n’avez pas besoin d’ajouter des mots clés généraux qui s’appliquent à tous les articles, car ils sont gérés ailleurs.</span><span class="sxs-lookup"><span data-stu-id="c3c73-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
5. <span data-ttu-id="c3c73-150">Lorsque vous avez terminé les modifications apportées à l’article, faites défiler vers le bas, puis sélectionnez **proposer une modification de fichier**.</span><span class="sxs-lookup"><span data-stu-id="c3c73-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>
6. <span data-ttu-id="c3c73-151">Sur la page suivante, sélectionnez **créer une demande d’extraction** pour fusionner votre branche créée automatiquement dans «maître».</span><span class="sxs-lookup"><span data-stu-id="c3c73-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>
7. <span data-ttu-id="c3c73-152">Répétez les étapes ci-dessus pour le prochain article que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="c3c73-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="c3c73-153">Renommer ou supprimer un article existant</span><span class="sxs-lookup"><span data-stu-id="c3c73-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="c3c73-154">Si votre modification doit renommer ou supprimer un article existant, veillez à ajouter une redirection.</span><span class="sxs-lookup"><span data-stu-id="c3c73-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="c3c73-155">Ainsi, toute personne disposant d’un lien vers l’article existant va tout de même se terminer au bon endroit.</span><span class="sxs-lookup"><span data-stu-id="c3c73-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="c3c73-156">Les redirections sont gérées par le .openpublishing.redirection.jssur fichier à la racine du référentiel Samples.</span><span class="sxs-lookup"><span data-stu-id="c3c73-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="c3c73-157">Pour ajouter une redirection à .openpublishing.redirection.js, ajoutez une entrée à la `redirections` matrice:</span><span class="sxs-lookup"><span data-stu-id="c3c73-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="c3c73-158">`source_path`Correspond au chemin d’accès relatif du référentiel de l’ancien article que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="c3c73-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="c3c73-159">Vérifiez que le chemin d’accès commence par `mixed-reality-docs` et se termine par `.md` .</span><span class="sxs-lookup"><span data-stu-id="c3c73-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>
- <span data-ttu-id="c3c73-160">`redirect_url`Est l’URL publique relative de l’ancien article vers le nouvel article.</span><span class="sxs-lookup"><span data-stu-id="c3c73-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="c3c73-161">Assurez-vous que cette URL **ne** contient `mixed-reality-docs` `.md` pas ou, car elle fait référence à l’URL publique et non au chemin d’accès du référentiel.</span><span class="sxs-lookup"><span data-stu-id="c3c73-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="c3c73-162">La création d’un lien vers une section du nouvel article en utilisant `#section` est autorisée.</span><span class="sxs-lookup"><span data-stu-id="c3c73-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="c3c73-163">Le cas échéant, vous pouvez également utiliser un chemin d’accès absolu à un autre site.</span><span class="sxs-lookup"><span data-stu-id="c3c73-163">You can also use an absolute path to another site here, if necessary.</span></span>
- `redirect_document_id` <span data-ttu-id="c3c73-164">indique si vous souhaitez conserver l’ID de document du fichier précédent.</span><span class="sxs-lookup"><span data-stu-id="c3c73-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="c3c73-165">La valeur par défaut est `false` .</span><span class="sxs-lookup"><span data-stu-id="c3c73-165">The default is `false`.</span></span> <span data-ttu-id="c3c73-166">Utilisez `true` cette option si vous souhaitez conserver la `ms.documentid` valeur d’attribut de l’article Redirigé.</span><span class="sxs-lookup"><span data-stu-id="c3c73-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="c3c73-167">Si vous conservez l’ID de document, les données, telles que les vues de page et les classements, seront transférées vers l’article cible.</span><span class="sxs-lookup"><span data-stu-id="c3c73-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="c3c73-168">Procédez ainsi si la redirection est essentiellement un changement de nom et non un pointeur vers un autre article qui ne couvre que le même contenu.</span><span class="sxs-lookup"><span data-stu-id="c3c73-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="c3c73-169">Si vous ajoutez une redirection, veillez à supprimer l’ancien fichier également.</span><span class="sxs-lookup"><span data-stu-id="c3c73-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="c3c73-170">Création d’un article</span><span class="sxs-lookup"><span data-stu-id="c3c73-170">Creating a new article</span></span>

<span data-ttu-id="c3c73-171">Utilisez le flux de travail suivant pour *créer des articles* dans le référentiel samples de documentation via github dans un navigateur Web:</span><span class="sxs-lookup"><span data-stu-id="c3c73-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="c3c73-172">Créez une fourche en dehors de la branche MicrosoftDocs/Mixed-Reality (à l’aide du bouton **Fork** dans le coin supérieur droit).</span><span class="sxs-lookup"><span data-stu-id="c3c73-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcationz la branche principale.](images/forkbranch.png)
2. <span data-ttu-id="c3c73-174">Dans le dossier «Mixed-Reality-docs», sélectionnez **créer un fichier** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="c3c73-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>
3. <span data-ttu-id="c3c73-175">Créer un nom de page pour l’article (utiliser des traits d’Union au lieu d’espaces et utiliser des signes de ponctuation ou des apostrophes) et ajouter ". MD"</span><span class="sxs-lookup"><span data-stu-id="c3c73-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nommez votre nouvelle page.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   ><span data-ttu-id="c3c73-177">Veillez à créer le nouvel article dans le dossier «Mixed-Reality-docs».</span><span class="sxs-lookup"><span data-stu-id="c3c73-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="c3c73-178">Vous pouvez vérifier ceci en recherchant «/Mixed-Reality-docs/» dans la ligne nouveau nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="c3c73-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="c3c73-179">Dans la partie supérieure de votre nouvelle page, ajoutez le bloc de métadonnées suivant:</span><span class="sxs-lookup"><span data-stu-id="c3c73-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="c3c73-180">Entrez les champs de métadonnées pertinents conformément aux instructions de la [section ci-dessus](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="c3c73-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>
6. <span data-ttu-id="c3c73-181">Rédigez le contenu d’un article à l’aide des [règles de démarque](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="c3c73-181">Write article content using [Markdown basics](#markdown-basics).</span></span>
7. <span data-ttu-id="c3c73-182">Ajoutez une `## See also` section en bas de cet article, contenant des liens vers d’autres articles pertinents.</span><span class="sxs-lookup"><span data-stu-id="c3c73-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>
8. <span data-ttu-id="c3c73-183">Lorsque vous avez terminé, sélectionnez **valider le nouveau fichier**.</span><span class="sxs-lookup"><span data-stu-id="c3c73-183">When finished, select **Commit new file**.</span></span>
9. <span data-ttu-id="c3c73-184">Sélectionnez **nouvelle demande d’extraction** , puis fusionnez la branche «maître» de votre bifurcation dans MicrosoftDocs/Mixed-Reality’Master' (Assurez-vous que la flèche pointe correctement).</span><span class="sxs-lookup"><span data-stu-id="c3c73-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Créer une demande d’extraction depuis votre fourche dans MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## <span data-ttu-id="c3c73-186">Notions de base des promotions</span><span class="sxs-lookup"><span data-stu-id="c3c73-186">Markdown basics</span></span>

<span data-ttu-id="c3c73-187">Les ressources suivantes vous permettront de découvrir comment modifier la documentation à l’aide du langage de démarque:</span><span class="sxs-lookup"><span data-stu-id="c3c73-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="c3c73-188">Notions de base des promotions</span><span class="sxs-lookup"><span data-stu-id="c3c73-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="c3c73-189">Affiche démarquez-en un coup d’œil</span><span class="sxs-lookup"><span data-stu-id="c3c73-189">Markdown-at-a-glance reference poster</span></span>](images/MarkdownPoster.pdf)
- [<span data-ttu-id="c3c73-190">Ressources supplémentaires pour l’écriture de la démarque pour docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c3c73-190">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="c3c73-191">Ajout de tables</span><span class="sxs-lookup"><span data-stu-id="c3c73-191">Adding tables</span></span>

<span data-ttu-id="c3c73-192">En raison de la façon dont docs.microsoft.com styles les tableaux, les bordures ou les styles personnalisés ne sont pas appliqués, même si vous essayez la fonction CSS intraligne.</span><span class="sxs-lookup"><span data-stu-id="c3c73-192">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="c3c73-193">Elle semble fonctionner pendant un court laps de temps, mais au final, la plateforme va supprimer le style de la table.</span><span class="sxs-lookup"><span data-stu-id="c3c73-193">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="c3c73-194">Envisagez donc d’anticiper et de garder vos tableaux simples.</span><span class="sxs-lookup"><span data-stu-id="c3c73-194">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="c3c73-195">Vous [trouverez ci-dessous un site qui simplifie la démarque](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="c3c73-195">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="c3c73-196">L' [extension documents pour le code Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) simplifie également la génération de tableaux si vous utilisez du [code Visual Studio (voir ci-dessous)](#using-visual-studio-code) pour modifier la documentation.</span><span class="sxs-lookup"><span data-stu-id="c3c73-196">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="c3c73-197">Ajout d’images</span><span class="sxs-lookup"><span data-stu-id="c3c73-197">Adding images</span></span>

<span data-ttu-id="c3c73-198">Vous aurez besoin de télécharger vos images dans le dossier «Mixed-Real-docs/images» du référentiel samples, puis de les référencer correctement dans l’article.</span><span class="sxs-lookup"><span data-stu-id="c3c73-198">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="c3c73-199">Les images s’affichent automatiquement en taille réelle, ce qui signifie que les images de grande taille remplissent toute la largeur de l’article.</span><span class="sxs-lookup"><span data-stu-id="c3c73-199">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="c3c73-200">Nous vous recommandons d’utiliser le prédimensionnement de vos images avant de les télécharger.</span><span class="sxs-lookup"><span data-stu-id="c3c73-200">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="c3c73-201">La largeur recommandée est comprise entre 600 et 700 pixels, même si la taille de la capture d’écran est densée ou une fraction d’une capture d’écran, respectivement.</span><span class="sxs-lookup"><span data-stu-id="c3c73-201">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c3c73-202">Vous pouvez uniquement transférer des images vers votre référentiel samples en fourche avant la fusion.</span><span class="sxs-lookup"><span data-stu-id="c3c73-202">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="c3c73-203">Par conséquent, si vous envisagez d’ajouter des images à un article, vous devez [utiliser du code Visual Studio](#using-visual-studio-code) pour ajouter d’abord les images dans le dossier «images» de votre bifurcation ou vérifier que vous avez effectué les opérations suivantes dans un navigateur Web:</span><span class="sxs-lookup"><span data-stu-id="c3c73-203">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="c3c73-204">A Fork le référentiel samples de MicrosoftDocs/Mixed-Real.</span><span class="sxs-lookup"><span data-stu-id="c3c73-204">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="c3c73-205">Modification de l’article dans votre bifurcation.</span><span class="sxs-lookup"><span data-stu-id="c3c73-205">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="c3c73-206">Téléchargez les images que vous référencez dans votre article dans le dossier «Mixed-Real-docs/images» dans votre bifurcation.</span><span class="sxs-lookup"><span data-stu-id="c3c73-206">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="c3c73-207">Création d’une **demande d’extraction** permettant de fusionner votre fourche dans la branche MicrosoftDocs/Mixed-Reality.</span><span class="sxs-lookup"><span data-stu-id="c3c73-207">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="c3c73-208">Pour découvrir comment configurer votre propre référentiel samples, suivez les instructions de [création d’un nouvel article](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="c3c73-208">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="c3c73-209">Prévisualiser votre bureau</span><span class="sxs-lookup"><span data-stu-id="c3c73-209">Previewing your work</span></span>

<span data-ttu-id="c3c73-210">Lorsque vous effectuez une modification dans GitHub via un navigateur Web, vous pouvez sélectionner l’onglet **Aperçu** en haut de la page pour afficher un aperçu de votre œuvre avant de l’engager.</span><span class="sxs-lookup"><span data-stu-id="c3c73-210">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="c3c73-211">Pour afficher un aperçu de vos modifications sur review.docs.microsoft.com est uniquement disponible aux employés de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3c73-211">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="c3c73-212">Employés de Microsoft: une fois vos contributions fusionnées dans la succursale «maître», vous pouvez consulter le contenu avant de le rendre public https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="c3c73-212">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="c3c73-213">Recherchez votre article à l’aide de la table des matières dans la colonne de gauche.</span><span class="sxs-lookup"><span data-stu-id="c3c73-213">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="c3c73-214">Modification dans le navigateur et modification avec un client de bureau</span><span class="sxs-lookup"><span data-stu-id="c3c73-214">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="c3c73-215">La modification dans le navigateur est le moyen le plus simple de procéder à des modifications rapides, mais il existe quelques inconvénients:</span><span class="sxs-lookup"><span data-stu-id="c3c73-215">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="c3c73-216">Vous ne recevez pas de vérification de l’orthographe.</span><span class="sxs-lookup"><span data-stu-id="c3c73-216">You don't get spell-check.</span></span>
- <span data-ttu-id="c3c73-217">Vous ne recevez pas de liens hypertexte vers d’autres articles (vous devez taper manuellement le nom de fichier de l’article).</span><span class="sxs-lookup"><span data-stu-id="c3c73-217">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="c3c73-218">C’est un bon risque de télécharger et de référencer des images.</span><span class="sxs-lookup"><span data-stu-id="c3c73-218">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="c3c73-219">Si vous préférez ne pas traiter ces problèmes, utilisez un client de bureau tel que le [code Visual Studio](https://code.visualstudio.com/) avec quelques [Extensions utiles](#useful-extensions) .</span><span class="sxs-lookup"><span data-stu-id="c3c73-219">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="c3c73-220">Utilisation de code Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3c73-220">Using Visual Studio Code</span></span>

<span data-ttu-id="c3c73-221">Pour les raisons répertoriées [ci-dessus](#editing-in-the-browser-vs-editing-with-a-desktop-client), il est possible que vous préfériez utiliser un client de bureau pour modifier la documentation au lieu d’un navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="c3c73-221">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="c3c73-222">Nous vous recommandons d’utiliser du [code Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="c3c73-222">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="c3c73-223">Configuration</span><span class="sxs-lookup"><span data-stu-id="c3c73-223">Setup</span></span>

<span data-ttu-id="c3c73-224">Suivez les étapes ci-dessous pour configurer le code Visual Studio pour qu’il fonctionne avec ce référentiel Samples:</span><span class="sxs-lookup"><span data-stu-id="c3c73-224">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="c3c73-225">Dans un navigateur Web:</span><span class="sxs-lookup"><span data-stu-id="c3c73-225">In a web browser:</span></span>
    1. <span data-ttu-id="c3c73-226">Installez [git pour votre PC](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="c3c73-226">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="c3c73-227">Installez du [code Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="c3c73-227">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="c3c73-228">[Fourche MicrosoftDocs/Mixed-Real,](#creating-a-new-article) si vous ne l’avez pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="c3c73-228">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="c3c73-229">Dans votre bifurcation, sélectionnez **clonage ou téléchargement** , puis copiez l’URL.</span><span class="sxs-lookup"><span data-stu-id="c3c73-229">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="c3c73-230">Créez un clone local de votre bifurcation dans le code Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="c3c73-230">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="c3c73-231">Dans le menu **affichage** , sélectionnez **palette de commandes**.</span><span class="sxs-lookup"><span data-stu-id="c3c73-231">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="c3c73-232">Tapez «git: Clone».</span><span class="sxs-lookup"><span data-stu-id="c3c73-232">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="c3c73-233">Collez l’URL que vous avez copiée.</span><span class="sxs-lookup"><span data-stu-id="c3c73-233">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="c3c73-234">Choisissez l’emplacement d’enregistrement du clone sur votre PC.</span><span class="sxs-lookup"><span data-stu-id="c3c73-234">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="c3c73-235">Dans la fenêtre qui s’affiche, sélectionnez **ouvrir référentiel Samples** .</span><span class="sxs-lookup"><span data-stu-id="c3c73-235">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="c3c73-236">Modification de la documentation</span><span class="sxs-lookup"><span data-stu-id="c3c73-236">Editing documentation</span></span>

<span data-ttu-id="c3c73-237">Utilisez le flux de travail suivant pour modifier la documentation avec du code Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="c3c73-237">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="c3c73-238">Toutes les recommandations en matière de [modification](#editing-an-existing-article) et de [création](#creating-a-new-article) d’articles, ainsi que les [notions de base de la modification de la démarque](#markdown-basics), ci-dessus s’appliquent également à l’utilisation de code Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3c73-238">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="c3c73-239">Assurez-vous que votre fourche clonée est à jour avec l’référentiel Samples officiel.</span><span class="sxs-lookup"><span data-stu-id="c3c73-239">Make sure your cloned fork is up to date with the official repo.</span></span>
   1. <span data-ttu-id="c3c73-240">Dans un navigateur Web, créez une demande de collecte pour synchroniser les modifications récentes d’autres contributeurs dans MicrosoftDocs/Mixed-Reality’Master’dans votre bifurcation (Assurez-vous que la flèche pointe sur la bonne voie).</span><span class="sxs-lookup"><span data-stu-id="c3c73-240">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchroniser les modifications de MicrosoftDocs/Mixed-Reality vers votre bifurcation](images/sync_repos.PNG)
   2. <span data-ttu-id="c3c73-242">Dans le code Visual Studio, sélectionnez le bouton synchroniser pour synchroniser votre branche fraîchement mise à jour sur le clone local.</span><span class="sxs-lookup"><span data-stu-id="c3c73-242">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Cliquez sur l’image du bouton synchroniser](images/sync_clone.png)
2. <span data-ttu-id="c3c73-244">Créez ou modifiez des articles dans votre référentiel Samples cloné à l’aide de code Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3c73-244">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>
   1. <span data-ttu-id="c3c73-245">Modifiez un ou plusieurs articles (ajoutez des images dans le dossier «images» le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="c3c73-245">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   2. <span data-ttu-id="c3c73-246">**Enregistrer** les modifications dans l' **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="c3c73-246">**Save** changes in **Explorer**.</span></span>
      
      ![Sélectionnez «Enregistrer tout» dans l’Explorateur](images/explorer_save.png)
   3. <span data-ttu-id="c3c73-248">**Valider toutes les** modifications dans **le contrôle de code source** (rédiger le message de validation lorsque vous y êtes invité).</span><span class="sxs-lookup"><span data-stu-id="c3c73-248">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
      
      ![Sélectionner «valider tout» dans le contrôle de code source](images/source_control_commit.png)
   4. <span data-ttu-id="c3c73-250">Sélectionnez le bouton **synchroniser** pour synchroniser vos modifications à l’origine (votre fourche sur GitHub).</span><span class="sxs-lookup"><span data-stu-id="c3c73-250">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Cliquez sur le bouton synchroniser.](images/sync_back.png)
3. <span data-ttu-id="c3c73-252">Dans un navigateur Web, créez une demande de collecte pour synchroniser les modifications apportées à votre fourche de nouveau dans MicrosoftDocs/Mixed-Reality' (Assurez-vous que la flèche pointe correctement).</span><span class="sxs-lookup"><span data-stu-id="c3c73-252">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Créer une demande d’extraction depuis votre fourche dans MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### <span data-ttu-id="c3c73-254">Extensions utiles</span><span class="sxs-lookup"><span data-stu-id="c3c73-254">Useful extensions</span></span>

<span data-ttu-id="c3c73-255">Les extensions de code Visual Studio suivantes sont utiles lors de la modification de la documentation:</span><span class="sxs-lookup"><span data-stu-id="c3c73-255">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="c3c73-256">[Extension documents pour le code Visual Studio](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) -utilisez **ALT + M** pour afficher un menu des options de création de documents telles que:</span><span class="sxs-lookup"><span data-stu-id="c3c73-256">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="c3c73-257">Recherchez et référencez des images que vous avez téléchargées.</span><span class="sxs-lookup"><span data-stu-id="c3c73-257">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="c3c73-258">Ajouter des mises en forme, comme des listes, des tableaux et des appels spécifiques aux documents `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="c3c73-258">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="c3c73-259">Recherchez et référencez des liens et des signets internes (liens vers des sections spécifiques d’une page).</span><span class="sxs-lookup"><span data-stu-id="c3c73-259">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="c3c73-260">Erreur de mise en forme mise en évidence (placez le pointeur de la souris sur l’erreur pour en savoir plus).</span><span class="sxs-lookup"><span data-stu-id="c3c73-260">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="c3c73-261">[Vérificateur orthographique du code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : les mots mal orthographiés sont soulignés; Cliquez avec le bouton droit sur un mot mal orthographié pour le modifier ou enregistrez-le dans le dictionnaire.</span><span class="sxs-lookup"><span data-stu-id="c3c73-261">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
