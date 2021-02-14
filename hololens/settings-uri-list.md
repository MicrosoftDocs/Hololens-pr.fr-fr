---
title: Visibilité des paramètres de la page
description: Tenez-vous au courant de notre liste d'URI pris en charge pour PageVisibilityList et Guide sur les appareils de réalité mixte HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque, page paramètres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327388"
---
# <span data-ttu-id="02737-104">Visibilité des paramètres de la page</span><span class="sxs-lookup"><span data-stu-id="02737-104">Page Settings Visibility</span></span>

<span data-ttu-id="02737-105">L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie paramètres/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application paramètres.</span><span class="sxs-lookup"><span data-stu-id="02737-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="02737-106">PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées.</span><span class="sxs-lookup"><span data-stu-id="02737-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="02737-107">Cette fonctionnalité est uniquement disponible dans [Windows Holographic version20H2](hololens-release-notes.md#windows-holographic-version-20h2) pour les appareils HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="02737-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="02737-108">Veuillez vérifier que les appareils pour lesquels vous envisagez d’utiliser cette fonctionnalité sont à jour.</span><span class="sxs-lookup"><span data-stu-id="02737-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="02737-109">Plus de 20 nouvelles SettingsURIs seront prochainement ajoutées.</span><span class="sxs-lookup"><span data-stu-id="02737-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="02737-110">Consultez [la page Windows Insider – Nouvelles SettingsURIs pour la visibilité des paramètres de page](hololens-insider.md#new-settingsuris-for-page-settings-visibility) si vous êtes intéressé par la prévisualisation de ce paramètre sur une build [HoloLens Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="02737-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="02737-111">L’exemple suivant illustre une stratégie qui autoriserait l’accès uniquement aux pages « À propos de» et Bluetooth, avec l’URI «ms-settings: Network-WiFi» et «ms-settings: Bluetooth» respectivement:</span><span class="sxs-lookup"><span data-stu-id="02737-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="02737-112">Pour le définir via un package d’approvisionnement:</span><span class="sxs-lookup"><span data-stu-id="02737-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="02737-113">Lorsque vous créez votre package dans le concepteur de configuration Windows, accédez à **Stratégies > Paramètres > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="02737-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="02737-114">Entrez la chaîne : **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="02737-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="02737-115">Exportez votre package d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="02737-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="02737-116">Appliquer le package aux appareils.</span><span class="sxs-lookup"><span data-stu-id="02737-116">Apply the package to your device.</span></span>
<span data-ttu-id="02737-117">Pour plus d’informations sur la création et l’application d’un package d’approvisionnement, consultez [cette page.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="02737-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="02737-118">Vous pouvez le faire via Intune à l’aide d’OMA-URI :</span><span class="sxs-lookup"><span data-stu-id="02737-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="02737-119">Créer une **stratégie personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="02737-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="02737-120">Lors de la définition de l’OMA-URI, utilisez la chaîne : **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="02737-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="02737-121">Lorsque vous sélectionnez le choix de prélèvement de données, sélectionnez: **Chaîne**</span><span class="sxs-lookup"><span data-stu-id="02737-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="02737-122">Lorsque vous tapez la valeur, utilisez : **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="02737-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="02737-123">Veillez à affecter la configuration d’appareil personnalisée à un groupe auquel l’appareil est destiné.</span><span class="sxs-lookup"><span data-stu-id="02737-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="02737-124">Pour plus d’informations sur les groupes et configurations d’appareils Intune, consultez [Configuration de la gestion des appareils pour HoloLens](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="02737-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="02737-125">Quelle que soit la méthode choisie, votre appareil doit maintenant recevoir les modifications et les utilisateurs recevront l’application Paramètres suivante.</span><span class="sxs-lookup"><span data-stu-id="02737-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="02737-127">Pour configurer les pages de l’application Paramètres afin d’afficher ou de masquer votre propre sélection de pages, jetez un œil aux URL de paramètres disponibles sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="02737-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="02737-128">URI de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-128">Settings URIs</span></span>

<span data-ttu-id="02737-129">Les appareils HoloLens et les appareils Windows10 ont une sélection de pages différente dans l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="02737-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="02737-130">Sur cette page, vous trouverez uniquement les paramètres qui existent sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="02737-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="02737-131">Comptes</span><span class="sxs-lookup"><span data-stu-id="02737-131">Accounts</span></span>
| <span data-ttu-id="02737-132">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-132">Settings page</span></span>           | <span data-ttu-id="02737-133">URI</span><span class="sxs-lookup"><span data-stu-id="02737-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="02737-134">Options de connexion</span><span class="sxs-lookup"><span data-stu-id="02737-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="02737-135">Inscription Iris</span><span class="sxs-lookup"><span data-stu-id="02737-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="02737-136">Accéder à un compte professionnel ou scolaire</span><span class="sxs-lookup"><span data-stu-id="02737-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="02737-137">Appareils</span><span class="sxs-lookup"><span data-stu-id="02737-137">Devices</span></span>
| <span data-ttu-id="02737-138">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-138">Settings page</span></span> | <span data-ttu-id="02737-139">URI</span><span class="sxs-lookup"><span data-stu-id="02737-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="02737-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="02737-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="02737-141">Confidentialité</span><span class="sxs-lookup"><span data-stu-id="02737-141">Privacy</span></span>
| <span data-ttu-id="02737-142">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-142">Settings page</span></span>            | <span data-ttu-id="02737-143">URI</span><span class="sxs-lookup"><span data-stu-id="02737-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="02737-144">Informations sur le compte</span><span class="sxs-lookup"><span data-stu-id="02737-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="02737-145">Diagnostics des applications</span><span class="sxs-lookup"><span data-stu-id="02737-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="02737-146">Applications en arrière-plan</span><span class="sxs-lookup"><span data-stu-id="02737-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="02737-147">Mouvements des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="02737-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="02737-148">Système de fichiers</span><span class="sxs-lookup"><span data-stu-id="02737-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="02737-149">Calendrier</span><span class="sxs-lookup"><span data-stu-id="02737-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="02737-150">Historique des appels</span><span class="sxs-lookup"><span data-stu-id="02737-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="02737-151">Contacts</span><span class="sxs-lookup"><span data-stu-id="02737-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="02737-152">Autres appareils</span><span class="sxs-lookup"><span data-stu-id="02737-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="02737-153">Documents</span><span class="sxs-lookup"><span data-stu-id="02737-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="02737-154">E-mail</span><span class="sxs-lookup"><span data-stu-id="02737-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="02737-155">Commentaires et diagnostics</span><span class="sxs-lookup"><span data-stu-id="02737-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="02737-156">Location</span><span class="sxs-lookup"><span data-stu-id="02737-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="02737-157">Messages</span><span class="sxs-lookup"><span data-stu-id="02737-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="02737-158">Micro</span><span class="sxs-lookup"><span data-stu-id="02737-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="02737-159">Notifications</span><span class="sxs-lookup"><span data-stu-id="02737-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="02737-160">Images</span><span class="sxs-lookup"><span data-stu-id="02737-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="02737-161">Radios</span><span class="sxs-lookup"><span data-stu-id="02737-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="02737-162">Voix</span><span class="sxs-lookup"><span data-stu-id="02737-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="02737-163">Tâches</span><span class="sxs-lookup"><span data-stu-id="02737-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="02737-164">Vidéos</span><span class="sxs-lookup"><span data-stu-id="02737-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="02737-165">Activation vocale</span><span class="sxs-lookup"><span data-stu-id="02737-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="02737-166">Appareil photo</span><span class="sxs-lookup"><span data-stu-id="02737-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="02737-167">Réseau et Internet</span><span class="sxs-lookup"><span data-stu-id="02737-167">Network & Internet</span></span>
| <span data-ttu-id="02737-168">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-168">Settings page</span></span> | <span data-ttu-id="02737-169">URI</span><span class="sxs-lookup"><span data-stu-id="02737-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="02737-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="02737-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="02737-171">VPN</span><span class="sxs-lookup"><span data-stu-id="02737-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="02737-172">Proxy</span><span class="sxs-lookup"><span data-stu-id="02737-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="02737-173">Système</span><span class="sxs-lookup"><span data-stu-id="02737-173">System</span></span>
| <span data-ttu-id="02737-174">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-174">Settings page</span></span>      | <span data-ttu-id="02737-175">URI</span><span class="sxs-lookup"><span data-stu-id="02737-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="02737-176">Expériences partagées</span><span class="sxs-lookup"><span data-stu-id="02737-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="02737-177">Couleurs</span><span class="sxs-lookup"><span data-stu-id="02737-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="02737-178">Notifications et actions</span><span class="sxs-lookup"><span data-stu-id="02737-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="02737-179">Stockage</span><span class="sxs-lookup"><span data-stu-id="02737-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="02737-180">Heure et langue</span><span class="sxs-lookup"><span data-stu-id="02737-180">Time & Language</span></span>
| <span data-ttu-id="02737-181">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-181">Settings page</span></span> | <span data-ttu-id="02737-182">URI</span><span class="sxs-lookup"><span data-stu-id="02737-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="02737-183">Région</span><span class="sxs-lookup"><span data-stu-id="02737-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="02737-184">Langue</span><span class="sxs-lookup"><span data-stu-id="02737-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="02737-185">Mise à jour et sécurité</span><span class="sxs-lookup"><span data-stu-id="02737-185">Update & Security</span></span>
| <span data-ttu-id="02737-186">Page de paramètres</span><span class="sxs-lookup"><span data-stu-id="02737-186">Settings page</span></span>                         | <span data-ttu-id="02737-187">URI</span><span class="sxs-lookup"><span data-stu-id="02737-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="02737-188">Programme WindowsInsider</span><span class="sxs-lookup"><span data-stu-id="02737-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="02737-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="02737-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="02737-190">1</span><span class="sxs-lookup"><span data-stu-id="02737-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="02737-191">1</span><span class="sxs-lookup"><span data-stu-id="02737-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="02737-192">Windows Update: recherche les mises à jour</span><span class="sxs-lookup"><span data-stu-id="02737-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="02737-193">Options avancées</span><span class="sxs-lookup"><span data-stu-id="02737-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="02737-194">1</sup> Les deux URI suivants ne vous permettent pas réellement d'accéder à la page **Options avancées** ou **Options**, ils ne feront que bloquer ou afficher la page principale Windows Update.</span><span class="sxs-lookup"><span data-stu-id="02737-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="02737-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="02737-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="02737-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="02737-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="02737-197">Pour obtenir la liste complète des URL des paramètres de Windows 10, visitez la documentation [paramètres du lancement](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="02737-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
