---
title: Résolution des problèmes liés à l'implémentation et à la gestion des appareils HoloLens 2
description: Résolution des problèmes liés aux appareils HoloLens 2 dans un environnement d'entreprise
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Résolution de problèmes
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961497"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="ca6f3-104">Résolution des problèmes liés à l'implémentation et à la gestion des appareils</span><span class="sxs-lookup"><span data-stu-id="ca6f3-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="ca6f3-105">Cet article explique comment résoudre différents problèmes ou répondre à des questions concernant l'implémentation et la gestion des appareils HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ca6f3-106">Avant d'entamer une procédure de résolution des problèmes, assurez-vous que la batterie de votre appareil est, si possible, chargée à **20 ou 40 %** de sa capacité.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="ca6f3-107">Les [témoins](hololens2-setup.md#lights-that-indicate-the-battery-level) situés sous le bouton d'alimentation permettent de vérifier rapidement la capacité de la batterie sans se connecter à l'appareil.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="ca6f3-108">Résolution des problèmes EAP</span><span class="sxs-lookup"><span data-stu-id="ca6f3-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="ca6f3-109">Résolution des problèmes liés au Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ca6f3-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="ca6f3-110">Résolution des problèmes de réseau</span><span class="sxs-lookup"><span data-stu-id="ca6f3-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="ca6f3-111">Impossible de se connecter à un appareil HoloLens déjà configuré</span><span class="sxs-lookup"><span data-stu-id="ca6f3-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="ca6f3-112">Impossible de se connecter après la mise à jour vers Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="ca6f3-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="ca6f3-113">Résolution des problèmes liés à Autopilot</span><span class="sxs-lookup"><span data-stu-id="ca6f3-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="ca6f3-114">Questions fréquentes (FAQ) sur les appareils HoloLens gérés</span><span class="sxs-lookup"><span data-stu-id="ca6f3-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="ca6f3-115">Résolution des problèmes liés au protocole EAP</span><span class="sxs-lookup"><span data-stu-id="ca6f3-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="ca6f3-116">Vérifiez que les paramètres de votre profil Wi-Fi sont corrects :</span><span class="sxs-lookup"><span data-stu-id="ca6f3-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="ca6f3-117">Le type EAP est correctement configuré. Types EAP courants : EAP-TLS (13), EAP-TTLS (21) et PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="ca6f3-118">Le nom SSID du Wi-Fi est correct et correspond à la chaîne HEX.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="ca6f3-119">Pour EAP-TLS, TrustedRootCA contient le hachage SHA-1 du certificat d'autorité de certification racine de confiance du serveur.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="ca6f3-120">Sur un Windows PC, la commande « certutil.exe -dump cert_file_name » affiche la chaîne de hachage SHA-1 d'un certificat.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="ca6f3-121">Collectez la capture des paquets réseau dans les journaux du point d'accès, du contrôleur ou du serveur AAA pour déterminer où la session EAP échoue.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="ca6f3-122">Si l'identité EAP fournie par l'HoloLens n'est pas attendue, vérifiez que l'identité a été correctement configurée via le profil Wi-Fi ou le certificat client.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="ca6f3-123">Si le serveur rejette le certificat client de l'HoloLens, vérifiez que le certificat client requis a été configuré sur l'appareil.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="ca6f3-124">Si l'HoloLens rejette le certificat du serveur, vérifiez que le certificat d'autorité de certification racine du serveur a été configuré sur l'HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="ca6f3-125">Si le profil d'entreprise est configuré via le package de configuration Wi-Fi, pensez à appliquer ce package sur un PC Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="ca6f3-126">S'il échoue également sur un PC Windows 10, suivez le guide de résolution des problèmes d'authentification du client Windows 802.1X.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="ca6f3-127">Faites-nous part de vos commentaires via le Hub de commentaires.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="ca6f3-128">Retour à la liste</span><span class="sxs-lookup"><span data-stu-id="ca6f3-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="ca6f3-129">Résolution des problèmes liés au Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ca6f3-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="ca6f3-130">Si vous ne parvenez pas à connecter votre HoloLens à un réseau Wi-Fi, vous pouvez essayer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ca6f3-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="ca6f3-131">Vérifiez que le Wi-Fi est activé.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="ca6f3-132">Pour ce faire, utilisez le mouvement associé au menu Démarrer, puis sélectionnez Paramètres > Réseau et Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="ca6f3-133">Si le Wi-Fi est activé, essayez de le désactiver puis de le réactiver.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="ca6f3-134">Rapprochez-vous du routeur ou du point d'accès.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="ca6f3-135">Redémarrez votre routeur Wi-Fi, puis redémarrez l'HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="ca6f3-136">Réessayez de vous connecter.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-136">Try connecting again.</span></span>
4. <span data-ttu-id="ca6f3-137">Si le problème persiste, vérifiez que votre routeur utilise le microprogramme le plus récent.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="ca6f3-138">Cette information est disponible sur le site web du fabricant.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="ca6f3-139">Lorsque vous vous connectez à un compte d'entreprise ou d'organisation sur l'appareil, il peut également appliquer une stratégie de gestion des appareils mobiles (GPM), si votre administrateur informatique en a configuré une.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="ca6f3-140">Résolution des problèmes de réseau</span><span class="sxs-lookup"><span data-stu-id="ca6f3-140">Network Troubleshooting</span></span>
<span data-ttu-id="ca6f3-141">Si des problèmes de réseau empêchent le déploiement et l'utilisation d'appareils HoloLens 2 au sein de votre organisation, les outils de diagnostic réseau Fiddler et Wireshark peuvent vous aider à analyser, diagnostiquer et identifier ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="ca6f3-142">Pour plus d'informations, consultez ce [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) .</span><span class="sxs-lookup"><span data-stu-id="ca6f3-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="ca6f3-143">Retour à la liste</span><span class="sxs-lookup"><span data-stu-id="ca6f3-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="ca6f3-144">Impossible de se connecter à un appareil HoloLens déjà configuré</span><span class="sxs-lookup"><span data-stu-id="ca6f3-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="ca6f3-145">Si votre appareil a déjà été configuré pour un autre utilisateur, comme un client ou un ancien employé, et que vous ne disposez pas de son mot de passe pour déverrouiller l'appareil, vous pouvez utiliser Intune pour [réinitialiser](https://docs.microsoft.com/intune/remote-actions/devices-wipe) l'appareil à distance.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="ca6f3-146">L'appareil se réinitialise alors.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="ca6f3-147">Lorsque vous réinitialisez l'appareil, décochez **Conserver l'état d'inscription et le compte d'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="ca6f3-148">Retour à la liste</span><span class="sxs-lookup"><span data-stu-id="ca6f3-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="ca6f3-149">Impossible de se connecter après la mise à jour vers Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="ca6f3-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="ca6f3-150">Symptômes</span><span class="sxs-lookup"><span data-stu-id="ca6f3-150">Symptoms</span></span>
- <span data-ttu-id="ca6f3-151">La connexion à l'aide du code PIN échoue alors que le bon code PIN a été utilisé.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="ca6f3-152">L'utilisation de la méthode de connexion web échoue après la connexion à la page web.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="ca6f3-153">L'appareil n'est pas répertorié comme « joint à Azure AD » sous [Portail Azure](https://portal.azure.com/) -> Azure Active Directory -> Appareils.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="ca6f3-154">Cause</span><span class="sxs-lookup"><span data-stu-id="ca6f3-154">Cause</span></span>
<span data-ttu-id="ca6f3-155">L'appareil concerné a peut-être été supprimé du locataire Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="ca6f3-156">Cela peut par exemple se produire pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca6f3-156">For example, this may happen because:</span></span>

- <span data-ttu-id="ca6f3-157">Un administrateur ou un utilisateur a supprimé l'appareil sur le portail Azure ou à l'aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="ca6f3-158">L'appareil a été supprimé du locataire Azure AD pour cause d'inactivité.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="ca6f3-159">Pour une gestion efficace de l'environnement, nous recommandons généralement aux administrateurs informatiques de [supprimer les appareils obsolètes et inactifs de leur locataire Azure AD](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="ca6f3-160">Lorsqu'un appareil concerné tente à nouveau de contacter le locataire Azure AD après sa suppression, il ne parvient pas à s'authentifier auprès d'Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="ca6f3-161">Cet effet est souvent invisible pour l'utilisateur de l'appareil, car la connexion en cache via le code PIN continue à permettre à l'utilisateur de se connecter.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="ca6f3-162">Limitation des risques</span><span class="sxs-lookup"><span data-stu-id="ca6f3-162">Mitigation</span></span>
<span data-ttu-id="ca6f3-163">Il n'existe actuellement aucun moyen de rajouter un appareil HoloLens supprimé dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="ca6f3-164">Les appareils concernés doivent être réinitialisés en suivant les instructions de [réinitialisation](hololens-recovery.md#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="ca6f3-165">Résolution des problèmes liés à Autopilot</span><span class="sxs-lookup"><span data-stu-id="ca6f3-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="ca6f3-166">Les articles suivants vous permettront d'en savoir plus et de résoudre les problèmes liés à Autopilot. Sachez toutefois que ces articles sont basés sur la version bureau de Windows 10 et que certaines informations ne s'appliquent pas à l'HoloLens :</span><span class="sxs-lookup"><span data-stu-id="ca6f3-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="ca6f3-167">Windows AutoPilot : problèmes connus</span><span class="sxs-lookup"><span data-stu-id="ca6f3-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="ca6f3-168">Résolution des problèmes d’inscription d’appareils Windows dans Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ca6f3-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="ca6f3-169">Windows Autopilot : conflits de stratégie</span><span class="sxs-lookup"><span data-stu-id="ca6f3-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="ca6f3-170">Questions fréquentes (FAQ) sur les appareils HoloLens gérés</span><span class="sxs-lookup"><span data-stu-id="ca6f3-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="ca6f3-171">Puis-je utiliser System Center Configuration Manager (SCCM) pour gérer les appareils HoloLens ?</span><span class="sxs-lookup"><span data-stu-id="ca6f3-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="ca6f3-172">Non.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-172">No.</span></span> <span data-ttu-id="ca6f3-173">Pour gérer les appareils HoloLens, vous devez utiliser un système GPM.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="ca6f3-174">Puis-je utiliser les services de domaine Active Directory (AD DS) pour gérer les comptes d'utilisateur HoloLens ?</span><span class="sxs-lookup"><span data-stu-id="ca6f3-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="ca6f3-175">Non.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-175">No.</span></span> <span data-ttu-id="ca6f3-176">Pour gérer les comptes d'utilisateur des appareils HoloLens, vous devez utiliser Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="ca6f3-177">L'HoloLens est-il capable d'enregistrer automatiquement les systèmes de capture automatique de données (ADCS) ?</span><span class="sxs-lookup"><span data-stu-id="ca6f3-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="ca6f3-178">Non.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="ca6f3-179">L'HoloLens peut-il participer à l'authentification Windows intégrée ?</span><span class="sxs-lookup"><span data-stu-id="ca6f3-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="ca6f3-180">Non.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="ca6f3-181">L'HoloLens prend-il en charge la personnalisation ?</span><span class="sxs-lookup"><span data-stu-id="ca6f3-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="ca6f3-182">Non.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-182">No.</span></span> <span data-ttu-id="ca6f3-183">Cependant, vous pouvez contourner ce problème en utilisant l'une des approches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca6f3-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="ca6f3-184">Créez une application personnalisée, puis [activez le mode plein écran](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="ca6f3-185">L'application personnalisée peut intégrer une personnalisation et lancer d'autres applications (comme Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="ca6f3-186">Dans Azure AD, remplacez toutes les photos de profil des utilisateurs par le logo de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="ca6f3-187">Ceci n'est toutefois pas souhaitable pour certains scénarios.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="ca6f3-188">Quelles capacités de journalisation l'HoloLens 2 offre-t-il ?</span><span class="sxs-lookup"><span data-stu-id="ca6f3-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="ca6f3-189">La journalisation est limitée aux suivis qui peuvent être capturés dans certains scénarios de développement ou de résolution des problèmes, ou aux données de télémétrie que les appareils envoient aux serveurs Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca6f3-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="ca6f3-190">Questions relatives à la sécurisation des appareils HoloLens</span><span class="sxs-lookup"><span data-stu-id="ca6f3-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="ca6f3-191">Consultez les [informations sur la sécurité de l'HoloLens 2](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="ca6f3-192">Pour les appareils HoloLens de 1ère génération, consultez [ces questions fréquentes (FAQ)](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f3-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="ca6f3-193">Retour à la liste</span><span class="sxs-lookup"><span data-stu-id="ca6f3-193">Back to list</span></span>](#list)
