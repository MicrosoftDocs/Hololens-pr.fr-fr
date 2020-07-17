---
title: Accès global affecté
description: Guide pour l’utilisation des OMA-URI pour les Kiosques Accès affecté
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, Access affecté, Kiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882443"
---
# <span data-ttu-id="44e64-104">Accès global affecté – Kiosque</span><span class="sxs-lookup"><span data-stu-id="44e64-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="44e64-105">Cette fonctionnalité configure l’appareil Hololens 2 pour le mode kiosque de plusieurs applications applicable au niveau du système, ne dispose d’aucune affinité avec une identité sur le système et s’applique à toutes les personnes qui se connectent à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="44e64-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="44e64-106">Pour l’instant, cette fonctionnalité est uniquement disponible dans les builds Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="44e64-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="44e64-107">Si vous souhaitez essayer cette fonctionnalité avant qu’elle ne soit généralement disponible dans les versions HoloLens, veuillez en savoir plus sur builds [Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="44e64-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="44e64-108">Comment l’utiliser dans Intune?</span><span class="sxs-lookup"><span data-stu-id="44e64-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="44e64-109">Notez les zones marquées par «<!-».</span><span class="sxs-lookup"><span data-stu-id="44e64-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="44e64-110">Dans ces zones, vous devez apporter des modifications en fonction de vos préférences.</span><span class="sxs-lookup"><span data-stu-id="44e64-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="44e64-111">Créez un profil de configuration d’appareil OMA URI personnalisé comme suit et appliquez-le au groupe de périphériques HoloLens: ![accès global affecté OMA-URI dans Intune</span><span class="sxs-lookup"><span data-stu-id="44e64-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="44e64-112">Pour valeur, mettre à jour et coller le contenu suivant:</span><span class="sxs-lookup"><span data-stu-id="44e64-112">For value, update and paste following content:</span></span> 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## <span data-ttu-id="44e64-113">Comment utiliser ceci dans le Concepteur de configuration Windows?</span><span class="sxs-lookup"><span data-stu-id="44e64-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="44e64-114">Mettez à jour et enregistrez le blob XML mentionné ci-dessus en tant que fichier XML.</span><span class="sxs-lookup"><span data-stu-id="44e64-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="44e64-115">Suivez les étapes décrites dans [Utiliser un package d’approvisionnement pour configurer une borne d’application ou une station multi-applications](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), notamment la section «Prov.</span><span class="sxs-lookup"><span data-stu-id="44e64-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="44e64-116">Pack, étape 2: ajouter le fichier XML de configuration Kiosque à un package d’approvisionnement» et faire référence au fichier XML enregistré à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="44e64-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="44e64-117">Puis-je créer une configuration où le groupe général s’applique à tout le monde sauf 1 compte AAD ou un groupe AAD?</span><span class="sxs-lookup"><span data-stu-id="44e64-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="44e64-118">Oui, consultez l’exemple d’objet blob XML ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="44e64-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="44e64-119">Le profil d’accès attribué global est appliqué sur Hololens lorsque celui-ci n’est pas trouvé pour l’utilisateur connecté. Par conséquent, il s’agit de la configuration par défaut en mode kiosque pour l’utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="44e64-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="44e64-120">Voici un exemple de blob XML à utiliser :</span><span class="sxs-lookup"><span data-stu-id="44e64-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="44e64-121">N’oubliez pas les zones marquées par <!-ces zones nécessitent d’apporter des modifications en fonction de vos préférences.</span><span class="sxs-lookup"><span data-stu-id="44e64-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
