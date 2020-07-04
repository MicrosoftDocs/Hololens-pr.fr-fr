---
title: Gérer les points de terminaison de connexion de HoloLens
description: Vous devrez vous connecter à un réseau Wi-Fi pour configurer HoloLens.
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
ms.openlocfilehash: f40d5adec0a8c0dc4bde5583a080ceedc0950fdb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828370"
---
# Gérer les points de terminaison de connexion de HoloLens

Certains composants, applications et services connexes HoloLens transfèrent des données aux points de terminaison du réseau Microsoft. Cet article répertorie plusieurs points de terminaison et URL que vous devez autoriser dans la configuration de votre réseau (par exemple, proxy ou pare-feu) pour que ces composants soient fonctionnels.    

## Configuration quasiment hors connexion

HoloLens prend en charge un nombre limité d’expériences hors connexion pour les clients soumis à des restrictions d’environnement réseau. Toutefois, HoloLens nécessite une connexion réseau pour passer par la configuration initiale de l’appareil. En outre, vous devez activer les URL suivantes:

| Objectif | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| Repère AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| Repère MSA | https://account.live.com/msangc?fl=enroll |

## Configuration du point de terminaison

En plus de la liste ci-dessus, vous devez activer les points de terminaison suivants dans la configuration de votre réseau pour tirer pleinement parti des fonctionnalités HoloLens.


| Objectif | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |   |   |   
|                                                     | ris-prod-atm.trafficmanager.net                                     |   |   |   |
|                                                     | validation-v2.sls.trafficmanager.net                                |   |   |   |
| Azure AD Multi-Factor Authentication                | https://secure.aadcdn.microsoftonline-p.com                         |   |   |   |
| Configurations Intune et MDM                       | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | cdn.onenote.net                                                     |   |   |   |
|                                                     | client.wns.windows.com                                              |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ctldl.windowsupdate.com                                             |   |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | dm3p.wns.windows.com                                                |   |   |   |
|                                                     | *microsoft.com/pkiops/*                                             |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | r.manage.microsoft.com                                              |   |   |   |
|                                                     | tile-service.weather.microsoft.com                                  |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Certificats                                        | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | https://www.microsoft.com/pkiops/*                                          |   |   |   |
| Cortana et recherche                                  | store-images.*microsoft.com                                         |   |   |   |
|                                                     | www.bing.com/client                                                 |   |   |   |
|                                                     | www.bing.com                                                        |   |   |   |
|                                                     | www.bing.com/proactive                                              |   |   |   |
|                                                     | www.bing.com/threshold/xls.aspx                                     |   |   |   |
|                                                     | exo-ring.msedge.net                                                 |   |   |   |
|                                                     | fp.msedge.net                                                       |   |   |   |
|                                                     | fp-vp.azureedge.net                                                 |   |   |   |
|                                                     | odinvzc.azureedge.net                                               |   |   |   |
|                                                     | spo-ring.msedge.net                                                 |   |   |   |
| Authentification de l’appareil                               | login.live.com*                                                     |   |   |   |
| Métadonnées d’appareil                                     | dmd.metaservices.microsoft.com                                      |   |   |   |
| Location                                            | Inference.Location.Live.NET                                         |   |   |   |
|                                                     | location-inference-westus.cloudapp.net                              |   |   |   |
| Données de diagnostic                                     | v10.events.data.microsoft.com                                       |   |   |   |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |   |   |   |
|                                                     | https://www.microsoft.com                                                   |   |   |   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |   |   |   |
|                                                     | cs11.wpc.v0cdn.net                                                  |   |   |   |
|                                                     | cs1137.wpc.gammacdn.net                                             |   |   |   |
|                                                     | modern.watson.data.microsoft.com *                                   |   |   |   |
|                                                     | watson.telemetry.microsoft.com                                      |   |   |   |
| Licences                                           | licensing.mp.microsoft.com                                          |   |   |   |
| Compte Microsoft                                   | login.msa.akadns6.net                                               |   |   |   |
|                                                     | us.configsvc1.Live.com.akadns.NET                                   |   |   |   |
| MicrosoftEdge                                      | iecvlist.microsoft.com                                              |   |   |   |
| Service de redirection de liaison montante Microsoft (FWLink) | go.microsoft.com                                                    |   |   |   |
| MicrosoftStore                                     | *.wns.windows.com                                                   |   |   |   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |   |   |   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |   |   |   |
|                                                     | store-images.microsoft.com                                          |   |   |   |
|                                                     | . md.mp.microsoft.com                                                |   |   |
|                                                     | * displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | pti.store.microsoft.com                                             |   |   |   |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |   |   |   |
|                                                     | markets.books.microsoft.com                                         |   |   |   |
|                                                     | share.microsoft.com                                                 |   |   |   |
| Indicateur d’état de la connexion réseau (NCSI)          | www.msftconnecttest.com *                                            |   |   |   |
| Office                                              | *.c-msedge.net                                                      |   |   |   |
|                                                     | *.e-msedge.net                                                      |   |   |   |
|                                                     | *.s-msedge.net                                                      |   |   |   |
|                                                     | nexusrules.officeapps.Live.com                                      |   |   |   |
|                                                     | ocos-office365-s2s.msedge.net                                       |   |   |   |
|                                                     | officeclient.Microsoft.com                                          |   |   |   |
|                                                     | outlook.office365.com                                               |   |   |   |
|                                                     | client-office365-tas.msedge.net                                     |   |   |   |
|                                                     | https://www.office.com                                                      |   |   |   |
|                                                     | onecollector. cloudapp. Aria                                          |   |   |   |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |   |   |   |
|                                                     | self.events.data.microsoft.com                                      |   |   |   |
|                                                     | pour do.microsoft.com                                                 |   |   |   |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |   |   |   |
|                                                     | msagfx.live.com                                                     |   |   |   |
|                                                     | oneclient.sfx.ms                                                    |   |   |   |
| Application Photos                                          | evoke-windowsservices-tas.msedge.net                                |   |   |   |
| Paramètres                                            | cy2.settings.data.microsoft.com.akadns.net                          |   |   |   |
|                                                     | settings.data.microsoft.com                                         |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| WindowsDefender                                    | wdcp.microsoft.com                                                  |   |   |   |
|                                                     | definitionupdates.microsoft.com                                     |   |   |   |
|                                                     | go.microsoft.com                                                    |   |   |   |
|                                                     | * smartscreen.microsoft.com                                          |   |   |   |
|                                                     | SmartScreen-sn3p.smartscreen.microsoft.com                          |   |   |   |
|                                                     | unitedstates.SmartScreen-prod.microsoft.com                         |   |   |   |
| Windows à la une                                   | *.search.msn.com                                                    |   |   |   |
|                                                     | arc.msn.com                                                         |   |   |   |
|                                                     | g.msn.com*                                                          |   |   |   |
|                                                     | query.prod.cms.rt.microsoft.com                                     |   |   |   |
|                                                     | ris.api.iris.microsoft.com                                          |   |   |   |
| WindowsUpdate                                      | *.prod.do.dsp.mp.microsoft.com                                      |   |   |   |
|                                                     | cs9.wac.phicdn.net                                                  |   |   |   |
|                                                     | emdl.ws.microsoft.com                                               |   |   |   |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |   |   |   |
|                                                     | *.windowsupdate.com                                                 |   |   |   |
|                                                     | *.delivery.mp.microsoft.com                                         |   |   |   |
|                                                     | *.update.microsoft.com                                              |   |   |   |



## Références

> [!NOTE]
> Si vous déployez D365 Remote Assist, vous devrez activer les points de terminaison sur cette [liste](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 
- [Configurer les données de diagnostic Windows dans votre organisation](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Gérer les points de terminaison de connexion pour Windows 10 entreprise, version 1903](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
- [Gérer les connexions des composants du système d’exploitation Windows 10 aux services Microsoft](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gérer les connexions des composants du système d’exploitation Windows 10 aux services Microsoft à l’aide du serveur GPM Microsoft Intune](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Configuration réseau requise et bande passante pour Intune](https://docs.microsoft.com/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Points de terminaison réseau pour Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/intune-endpoints)
- [URL et plages d’adressesIP Office365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)
- [Conditions préalables pour Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## Limites de HoloLens

Une fois votre HoloLens configuré, vous pouvez l’utiliser sans connexion Wi-Fi. Cependant, les applications qui utilisent des connexions internet offriront des fonctionnalités limitées lorsque vous utiliserez HoloLens hors connexion.
