---
title: Gérer les points de terminaison de connexion pour HoloLens
description: Découvrez comment configurer un appareil HoloLens sur un réseau Wi-Fi lors de la gestion et de la configuration de points de terminaison de connexion.
keywords: hololens, hors connexion, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427775"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Gérer les points de terminaison de connexion pour HoloLens

Certains composants, applications et services associés à HoloLens transfèrent des données aux points de terminaison du réseau Microsoft. Cet article liste différents points de terminaison et URL que vous devez autoriser dans la configuration de votre réseau (par exemple le proxy ou le pare-feu) pour que ces composants soient fonctionnels.    

## <a name="near-offline-setup"></a>Configuration quasiment hors connexion

HoloLens prend en charge un nombre limité d’expériences hors connexion pour les clients soumis à des restrictions d’environnement réseau. Cependant, HoloLens nécessite une connexion réseau pour la configuration initiale de l’appareil. En outre, vous devez activer les URL suivantes :

| Objectif | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Configuration du point de terminaison

En plus de la liste ci-dessus, vous devez activer les points de terminaison suivants dans la configuration de votre réseau pour tirer pleinement parti des fonctionnalités HoloLens.


| Objectif | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Authentification multifacteur Azure AD                | https://secure.aadcdn.microsoftonline-p.com                         |
| Configurations Intune et MDM                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certificats                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana et recherche                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Authentification d'appareil                               | login.live.com*                                                     |
| Métadonnées de l’appareil                                     | dmd.metaservices.microsoft.com                                      |
| Emplacement                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Données de diagnostic                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licences                                           | licensing.mp.microsoft.com                                          |
| Compte Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Service de redirection de liaison montante Microsoft (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Indicateur d’état de la connexion réseau (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Application Photos                                          | evoke-windowsservices-tas.msedge.net                                |
| Paramètres                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows à la une                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Références

> [!NOTE]
> Si vous déployez D365 Remote Assist, vous devez activer les points de terminaison listés pour SharePoint Online et OneDrive Entreprise dans [URL et plages d’adresses IP pour Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- [Configurer les données de diagnostic Windows dans votre organisation](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Gérer les points de terminaison de connexion pour Windows 10 Entreprise, version 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Gérer les connexions des composants du système d’exploitation Windows 10 aux services Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gérer les connexions des composants du système d’exploitation Windows 10 aux services Microsoft en utilisant le serveur MDM Microsoft Intune](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Configuration requise pour le réseau Intune et bande passante](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Points de terminaison réseau pour Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [URL et plages d’adresses IP Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Conditions préalables pour Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>Limitations d’HoloLens

Une fois votre appareil HoloLens configuré, vous pouvez l’utiliser sans connexion Wi-Fi. Cependant, les applications qui utilisent des connexions Internet auront des fonctionnalités limitées quand vous utilisez HoloLens hors connexion.
