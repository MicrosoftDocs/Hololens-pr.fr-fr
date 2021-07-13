---
title: Visibilité des paramètres de la page
description: Tenez-vous au courant de notre liste d'URI pris en charge pour PageVisibilityList et Guide sur les appareils de réalité mixte HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, accès affecté, kiosque, page paramètres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924330"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="23871-104">Visibilité des paramètres de la page</span><span class="sxs-lookup"><span data-stu-id="23871-104">Page Settings Visibility</span></span>

<span data-ttu-id="23871-105">L’une des fonctionnalités gérables pour les appareils HoloLens utilise la [stratégie Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) pour restreindre les pages visibles dans l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="23871-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="23871-106">PageVisibilityList est une stratégie qui permet aux administrateurs informatiques d’empêcher l’affichage ou l’accessibilité de pages spécifiques dans l’application Paramètres système, ou de le faire pour toutes les pages à l’exception de celles spécifiées.</span><span class="sxs-lookup"><span data-stu-id="23871-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="23871-107">Cette fonctionnalité est uniquement disponible dans [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou ultérieure pour les appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="23871-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="23871-108">Vérifiez que les appareils pour lesquels vous envisagez d’utiliser cette fonctionnalité sont à jour.</span><span class="sxs-lookup"><span data-stu-id="23871-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="23871-109">L’exemple suivant illustre une stratégie autorisant l’accès uniquement aux pages « À propos de » et Bluetooth, avec l’URI « ms-settings : Network-WiFi » et « ms-settings : Bluetooth » respectivement :</span><span class="sxs-lookup"><span data-stu-id="23871-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="23871-110">Pour le définir via un package de configuration :</span><span class="sxs-lookup"><span data-stu-id="23871-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="23871-111">Lorsque vous créez votre package dans le Concepteur de configuration Windows, accédez à **Stratégies > Paramètres > PageVisibilityList**.</span><span class="sxs-lookup"><span data-stu-id="23871-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="23871-112">Entrez la chaîne : **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="23871-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="23871-113">Exportez votre package de configuration.</span><span class="sxs-lookup"><span data-stu-id="23871-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="23871-114">Appliquez le package à votre appareil.</span><span class="sxs-lookup"><span data-stu-id="23871-114">Apply the package to your device.</span></span>
<span data-ttu-id="23871-115">Pour plus d’informations sur la création et l’application d’un package de configuration, consultez [cette page](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="23871-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="23871-116">Vous pouvez le faire via Intune à l’aide d’OMA-URI :</span><span class="sxs-lookup"><span data-stu-id="23871-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="23871-117">Créez une **stratégie personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="23871-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="23871-118">Lors de la définition de l’OMA-URI, utilisez la chaîne : **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="23871-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="23871-119">Lorsque vous sélectionnez le choix de prélèvement de données, sélectionnez : **Chaîne**</span><span class="sxs-lookup"><span data-stu-id="23871-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="23871-120">Lorsque vous entrez la valeur, utilisez : **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="23871-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="23871-121">Veillez à affecter la configuration d’appareil personnalisée à un groupe auquel l’appareil est destiné.</span><span class="sxs-lookup"><span data-stu-id="23871-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="23871-122">Pour plus d’informations sur les groupes et configurations d’appareils Intune, consultez [Configuration GPM HoloLens](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="23871-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="23871-123">Quelle que soit la méthode choisie, votre appareil doit maintenant recevoir les modifications et les utilisateurs se voir présenter l’application Paramètres suivante.</span><span class="sxs-lookup"><span data-stu-id="23871-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Capture d’écran d’heures actives modifiées dans l’application Paramètres](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="23871-125">Pour configurer les pages de l’application Paramètres afin d’afficher ou de masquer votre propre sélection de pages, consultez les URL de paramètres disponibles sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="23871-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="23871-126">URI de paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-126">Settings URIs</span></span>

<span data-ttu-id="23871-127">Les appareils HoloLens et Windows 10 présentent une sélection de pages différente dans l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="23871-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="23871-128">Sur cette page, vous trouverez uniquement les paramètres présents sur HoloLens.</span><span class="sxs-lookup"><span data-stu-id="23871-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="23871-129">Comptes</span><span class="sxs-lookup"><span data-stu-id="23871-129">Accounts</span></span>
| <span data-ttu-id="23871-130">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-130">Settings page</span></span>           | <span data-ttu-id="23871-131">URI</span><span class="sxs-lookup"><span data-stu-id="23871-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="23871-132">Accès Professionnel ou Scolaire</span><span class="sxs-lookup"><span data-stu-id="23871-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="23871-133">Inscription Iris</span><span class="sxs-lookup"><span data-stu-id="23871-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="23871-134">Options de connexion</span><span class="sxs-lookup"><span data-stu-id="23871-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="23871-135">Applications</span><span class="sxs-lookup"><span data-stu-id="23871-135">Apps</span></span>
| <span data-ttu-id="23871-136">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-136">Settings page</span></span> | <span data-ttu-id="23871-137">URI</span><span class="sxs-lookup"><span data-stu-id="23871-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="23871-138">Applications et fonctionnalités<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="23871-139">Applications et fonctionnalités > Options avancées <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="23871-140">Applications et fonctionnalités > Cartes hors connexion <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="23871-141">Applications et fonctionnalités > Cartes hors connexion > Télécharger des cartes <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="23871-142">Appareils</span><span class="sxs-lookup"><span data-stu-id="23871-142">Devices</span></span>
| <span data-ttu-id="23871-143">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-143">Settings page</span></span> | <span data-ttu-id="23871-144">URI</span><span class="sxs-lookup"><span data-stu-id="23871-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="23871-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="23871-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="23871-146">Souris <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="23871-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="23871-148">Confidentialité</span><span class="sxs-lookup"><span data-stu-id="23871-148">Privacy</span></span>
| <span data-ttu-id="23871-149">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-149">Settings page</span></span>            | <span data-ttu-id="23871-150">URI</span><span class="sxs-lookup"><span data-stu-id="23871-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="23871-151">Informations sur le compte</span><span class="sxs-lookup"><span data-stu-id="23871-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="23871-152">Diagnostics d'application</span><span class="sxs-lookup"><span data-stu-id="23871-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="23871-153">Applications en arrière-plan</span><span class="sxs-lookup"><span data-stu-id="23871-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="23871-154">Calendrier</span><span class="sxs-lookup"><span data-stu-id="23871-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="23871-155">Historique des appels</span><span class="sxs-lookup"><span data-stu-id="23871-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="23871-156">Appareil photo</span><span class="sxs-lookup"><span data-stu-id="23871-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="23871-157">Contacts</span><span class="sxs-lookup"><span data-stu-id="23871-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="23871-158">Diagnostics et commentaires</span><span class="sxs-lookup"><span data-stu-id="23871-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="23871-159">Documents</span><span class="sxs-lookup"><span data-stu-id="23871-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="23871-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="23871-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="23871-161">Système de fichiers</span><span class="sxs-lookup"><span data-stu-id="23871-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="23871-162">Général <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="23871-163">Entrée manuscrite et personnalisation de la saisie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="23871-164">Emplacement</span><span class="sxs-lookup"><span data-stu-id="23871-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="23871-165">Messagerie</span><span class="sxs-lookup"><span data-stu-id="23871-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="23871-166">Microphone</span><span class="sxs-lookup"><span data-stu-id="23871-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="23871-167">Mouvement <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="23871-168">Notifications</span><span class="sxs-lookup"><span data-stu-id="23871-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="23871-169">Autres appareils</span><span class="sxs-lookup"><span data-stu-id="23871-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="23871-170">Images</span><span class="sxs-lookup"><span data-stu-id="23871-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="23871-171">Radios</span><span class="sxs-lookup"><span data-stu-id="23871-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="23871-172">Bordures d’écran <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="23871-173">Captures d’écran et applications <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="23871-174">Speech</span><span class="sxs-lookup"><span data-stu-id="23871-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="23871-175">Tâches</span><span class="sxs-lookup"><span data-stu-id="23871-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="23871-176">Mouvements des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="23871-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="23871-177">Vidéos</span><span class="sxs-lookup"><span data-stu-id="23871-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="23871-178">Activation vocale</span><span class="sxs-lookup"><span data-stu-id="23871-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="23871-179">Réseau et Internet</span><span class="sxs-lookup"><span data-stu-id="23871-179">Network & Internet</span></span>
| <span data-ttu-id="23871-180">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-180">Settings page</span></span> | <span data-ttu-id="23871-181">URI</span><span class="sxs-lookup"><span data-stu-id="23871-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="23871-182">Mode avion <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="23871-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="23871-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="23871-184">VPN</span><span class="sxs-lookup"><span data-stu-id="23871-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="23871-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="23871-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="23871-186">Système</span><span class="sxs-lookup"><span data-stu-id="23871-186">System</span></span>
| <span data-ttu-id="23871-187">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-187">Settings page</span></span>      | <span data-ttu-id="23871-188">URI</span><span class="sxs-lookup"><span data-stu-id="23871-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="23871-189">Batterie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="23871-190">Batterie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="23871-191">Couleurs</span><span class="sxs-lookup"><span data-stu-id="23871-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="23871-192">Hologrammes <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="23871-193">Étalonnage <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="23871-194">Notifications et actions</span><span class="sxs-lookup"><span data-stu-id="23871-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="23871-195">Expériences partagées</span><span class="sxs-lookup"><span data-stu-id="23871-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="23871-196">Son <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="23871-197">Son > Volume de l’application et préférence d’appareil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="23871-198">Son > Gérer les périphériques audio <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="23871-199">Stockage</span><span class="sxs-lookup"><span data-stu-id="23871-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="23871-200">Stockage > Configurer l’Assistant Stockage <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="23871-201">Heure et langue</span><span class="sxs-lookup"><span data-stu-id="23871-201">Time & Language</span></span>
| <span data-ttu-id="23871-202">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-202">Settings page</span></span> | <span data-ttu-id="23871-203">URI</span><span class="sxs-lookup"><span data-stu-id="23871-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="23871-204">Date et heure <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="23871-205">Clavier <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="23871-206">Langue <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="23871-207">Langue <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="23871-208">Langage</span><span class="sxs-lookup"><span data-stu-id="23871-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="23871-209">Région</span><span class="sxs-lookup"><span data-stu-id="23871-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="23871-210">Mise à jour et sécurité</span><span class="sxs-lookup"><span data-stu-id="23871-210">Update & Security</span></span>
| <span data-ttu-id="23871-211">Page Paramètres</span><span class="sxs-lookup"><span data-stu-id="23871-211">Settings page</span></span>                         | <span data-ttu-id="23871-212">URI</span><span class="sxs-lookup"><span data-stu-id="23871-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="23871-213">Options avancées</span><span class="sxs-lookup"><span data-stu-id="23871-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="23871-214">Réinitialisation et récupération <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23871-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="23871-215">Programme Windows Insider</span><span class="sxs-lookup"><span data-stu-id="23871-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="23871-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="23871-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="23871-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="23871-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="23871-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="23871-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="23871-219">Windows Update - Recherche de mises à jour</span><span class="sxs-lookup"><span data-stu-id="23871-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="23871-220"><sup>1</sup> - Pour les versions antérieures à Windows Holographic 21H1, les deux URI suivants ne vous permettent pas d’accéder aux pages **Options** ou **Options avancées** ; ils ne feront que bloquer ou afficher la page principale Windows Update.</span><span class="sxs-lookup"><span data-stu-id="23871-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="23871-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="23871-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="23871-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="23871-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="23871-223"><sup>2</sup> - Disponible dans Windows Holographic, version 21H1 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="23871-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="23871-224">Pour obtenir la liste complète des URI des paramètres Windows 10, consultez la documentation relative aux [paramètres de lancement](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="23871-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
