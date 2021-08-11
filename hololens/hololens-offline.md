---
title: Hantera anslutningsslutpunkter för HoloLens
description: Lär dig hur du konfigurerar en HoloLens över ett Wi-Fi nätverk samtidigt som du hanterar och konfigurerar anslutningsslutpunkter.
keywords: hololens, offline, OOBE
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
ms.openlocfilehash: 63c82e5b1a953ee2f69bf4c22a8442c7bca07f073cc13f1e5e573fde0ccc1976
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662935"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Hantera anslutningsslutpunkter för HoloLens

Vissa HoloLens, appar och relaterade tjänster överför data till Microsofts nätverksslutpunkter. Den här artikeln innehåller olika slutpunkter och URL:er som måste tillåtas i din nätverkskonfiguration (t.ex. proxy eller brandvägg) för att dessa komponenter ska fungera.    

## <a name="near-offline-setup"></a>Nästan offline-installation

HoloLens har stöd för en begränsad uppsättning offlineupplevelser för kunder som har nätverksmiljöbegränsningar. Dock HoloLens nätverksanslutning för att gå igenom den första enhetsuppsättningen och följande URL:er måste vara aktiverade:

| Syfte | URL |
|------|------|
| Internflyktingar | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Slutpunktskonfiguration

Förutom listan ovan måste följande slutpunkter aktiveras i nätverkskonfigurationen för att du ska kunna dra full nytta av HoloLens funktioner.


| Syfte | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD-multifaktorautentisering                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune- och MDM-konfigurationer                       | activation-v2.sls.microsoft.com/*                                   |
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
| Certifikat                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana och sök                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Enhetsautentisering                               | login.live.com*                                                     |
| Enhetsmetadata                                     | dmd.metaservices.microsoft.com                                      |
| Location                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Diagnostikdata                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licensiering                                           | licensing.mp.microsoft.com                                          |
| Microsoft-konto                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft-tjänsten för omdirigering av länkar (FWLink) | go.microsoft.com                                                    |
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
| Statusindikator för nätverksanslutning (NCSI)          | www.msftconnecttest.com*                                            |
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
| Photos App                                          | evoke-windowsservices-tas.msedge.net                                |
| Inställningar                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows Spotlight                                   | *.search.msn.com                                                    |
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



## <a name="references"></a>Referenser

> [!NOTE]
> Om du distribuerar D365 Remote Assist måste du aktivera de slutpunkter som anges för SharePoint Online och OneDrive för företag i Office 365 URL:er och [IP-adressintervall.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- [Konfigurera Windows diagnostikdata i din organisation](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Hantera anslutningsslutpunkter för Windows 10 Enterprise version 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Hantera anslutningar från Windows 10 operativsystemkomponenter till Microsoft-tjänster](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Hantera anslutningar från Windows 10 operativsystemkomponenter till att Microsoft-tjänster med Microsoft Intune MDM-server](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Krav för Intune-nätverkskonfiguration och bandbredd](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Nätverksslutpunkter för Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Webbadresser och IP-adressintervall för Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Förhandskrav för Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens begränsningar

När din HoloLens har ställts in kan du använda den utan en Wi-Fi-anslutning, men appar som använder Internetanslutningar har begränsade funktioner när du använder HoloLens offline.
