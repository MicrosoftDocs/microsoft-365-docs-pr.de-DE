---
title: Zusätzliche Endpunkte, die nicht im Office 365-IP-Adress- und -URL-Webdienst enthalten sind
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/29/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 'Zusammenfassung: In den neuen Endpunkt-Webdiensten ist eine kleine Anzahl von Endpunkten für bestimmte Szenarien nicht enthalten.'
hideEdit: true
ms.openlocfilehash: 7922730957be93b2cdfbd06a48d39fc54ac4af89
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711976"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Zusätzliche Endpunkte, die nicht im Office 365-IP-Adress- und -URL-Webdienst enthalten sind

Einige Netzwerkendpunkte wurden früher veröffentlicht und wurden nicht im [Office 365-IP-Adress- und -URL-Webdienst](microsoft-365-ip-web-service.md) aufgenommen. Der Webdienstbereich besteht aus Netzwerkendpunkten, die für die Konnektivität eines Endbenutzers von Office 365 über ein Unternehmens-Umkreisnetzwerk hinweg erforderlich sind. Dies umfasst aktuell die folgenden Punkte nicht:

1. Netzwerkkonnektivität, die möglicherweise zwischen einem Microsoft-Rechenzentrum und einem Kundennetzwerk erforderlich ist (eingehender Server-Netzwerkdatenverkehr in Hybridbereitstellungen).
2. Netzwerkkonnektivität von Servern in einem Kundennetzwerk über das Umkreisnetzwerk des Unternehmens hinweg (ausgehender Server-Netzwerkdatenverkehr)
3. Ungewöhnliche Szenarien für Netzwerkverbindungsanforderungen eines Benutzers
4. Konnektivitätsanforderung für DNS-Auflösung (unten nicht aufgeführt)
5. Vertrauenswürdige Websites von Internet Explorer oder Microsoft Edge

Abgesehen von DNS sind alle diese Punkte für die meisten Benutzer optional, es sei denn, Sie müssen das bestimmte beschriebene Szenario berücksichtigen.

| Zeile | Zweck | Ziel | Typ |
|:-----|:-----|:-----|:-----|
| 1  | [Importdienst](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) für PST- und Dateierfassung | Informationen zu weiteren Anforderungen finden Sie unter [Importdienst](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6). | Ungewöhnliches ausgehendes Szenario |
| 2   | [Microsoft-Support- und Wiederherstellungs-Assistent für Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>dcs-staging.azure-api.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Ausgehender Serverdatenverkehr |
| 3   | Azure AD Connect (mit SSO-Option) – WinRM und Remote PowerShell | STS-Kundenumgebung (AD FS Server und AD FS Proxy) \| TCP-Ports 80 und 443 | Eingehender Serverdatenverkehr |
| 4   | STS wie AD FS-Proxyserver (nur Kunden mit Partnerverbund) | Kunden-STS (wie etwa AD FS Proxy) \| Ports TCP 443 oder TCP 49443 mit ClientTLS | Eingehender Serverdatenverkehr |
| 5   | [Integration von Exchange Online Unified Messaging/SBC](https://technet.microsoft.com/library/jj673565.aspx) | Bidirektional zwischen lokalem Session Border Controller und *.um.outlook.com | Nur ausgehender Serverdatenverkehr |
| 6   | Migration von Postfächern. Wenn die Migration von Postfächern aus dem lokalen [Exchange Hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) in Office 365 initiiert wird, stellt Office 365 eine Verbindung zu Ihrem öffentlichen Exchange-Webdienste (EWS)/Postfach Replikationsdienste (MRS)-Server her. Wenn Sie die von den Exchange Online-Servern verwendeten, NAT IP-Adressen benötigen, um eingehende Verbindungen von bestimmten IP-Qualladressenbereichen einzuschränken, finden Sie diese in der Liste [Office 365 URL & IP-Bereiche](urls-and-ip-address-ranges.md) im Bereich „Exchange Online“. Es sollte beachtet werden, dass der Zugriff auf veröffentlichte EWS-Endpunkte wie OWA nicht beeinträchtigt wird, wenn der MRS-Proxy in einen separaten FQDN und eine öffentliche IP-Adresse aufgelöst wird, bevor TCP 443-Verbindungen von bestimmten Quell-IP-Bereichen eingeschränkt werden. | Lokaler EWS/MRS-Proxy von Kunden<br> TCP-Port 443 | Eingehender Serverdatenverkehr |
| 7   | [Exchange Hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant)-Funktionen für Koexistenz, wie etwa Teilen der Frei/Gebucht-Informationen. | Lokale Exchange-Kundenserver | Eingehender Serverdatenverkehr |
| 8   | [Exchange Hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant)-Proxyauthentifizierung | Lokaler STS von Kunden | Eingehender Serverdatenverkehr |
| 9   | Zum Konfigurieren von [Exchange-Hybridbereitstellungen](https://docs.microsoft.com/exchange/exchange-deployment-assistant) mit dem [Exchange-Hybridkonfigurations-Assistenten](https://docs.microsoft.com/exchange/hybrid-configuration-wizard) verwendet. <br> Hinweis: Diese Endpunkte sind nur für die Konfiguration von Exchange-Hybridbereitstellungen erforderlich  | domains.live.com an den TCP-Ports 80 und 443, nur für den Exchange 2010 SP3-Hybridkonfigurations-Assistenten erforderlich.<BR> <BR> GCC High, DoD-IP-Adressen: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Weltweite kommerzielle & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <BR> aka.ms/hybridwizard; <BR> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;<BR>  | Nur ausgehender Serverdatenverkehr |
| 10    | Der AutoDetect-Dienst wird in [Exchange-Hybridszenarien](https://docs.microsoft.com/exchange/exchange-deployment-assistant) mit [der modernen Hybridauthentifizierung mit Outlook für iOS und Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) verwendet. <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Lokale Exchange-Kundenserver an TCP-Port 443 | Eingehender Serverdatenverkehr |
| 11  | Exchange-Hybridauthentifizierung mit Azure AD | *.msappproxy.net | Nur DATENVERKEHR für ausgehenden TCP-Server |
| 12   | Skype for Business in Office 2016 umfasst eine videobasierte Bildschirmübertragung, die UDP-Ports verwendet. Vor Skype for Business-Clients in Office 2013 und früher wurde RDP-über-TCP-Port 443 verwendet. | TCP-Port 443 geöffnet bis 52.112.0.0/14 | Altere Clientversionen von Skype for Business in Office 2013 und früheren Versionen |
| 13   | Lokale Serververbindung für Skype für Business-Hybridbereitstellung mit Skype for Business Online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-Ports 50,000-59,999 <BR>  TCP-Ports 50,000-59,999; 5061 | Skype for Business auf lokale Server ausgehende Verbindungen |
| 14   | Für ein Cloud-Telefonfestnetz mit lokaler Hybridverbindung muss die Netzwerkverbindung für die lokalen Hosts geöffnet sein. Weitere Informationen zu Skype for Business Online-Hybridbereitstellungen finden Sie  | Siehe [Planen der Hybridkonnektivität zwischen Skype for Business Server und Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Lokale Skype for Business-Hybridbereitstellung (eingehend) |
| 15   | **FQDNs für Authentifizierung und Identität** <br> Für ordnungsgemäße Funktion muss sich der FQDN ```secure.aadcdn.microsoftonline-p.com``` in der Zone "Vertrauenswürdige Sites" von Internet Explorer (IE) oder Edge des Clients befinden. |  | Vertrauenswürdige Sites |
| 16   |  **FQDNs für Microsoft Teams** <br> Wenn Sie Internet Explorer oder Microsoft Edge verwenden, müssen Sie Cookies von Erst- und Drittanbietern aktivieren und die FQDNs für Teams zu Ihren vertrauenswürdigen Sites hinzufügen. Dies muss zusätzlich zu den in Zeile 14 aufgeführten Werten für FQDNs, CDNs und Telemetrie für die gesamte Suite erfolgen. Weitere Informationen finden Sie unter [Bekannte Probleme bei Microsoft Teams](https://docs.microsoft.com/microsoftteams/known-issues). |  | Vertrauenswürdige Sites |
| 17   |  **FQDNs für SharePoint Online und OneDrive for Business** <br> Für eine ordnungsgemäße Funktion müssen sich alle FQDNs von ".sharepoint.com" mit "\<tenant>" im FQDN in der Zone "Vertrauenswürdige Sites" des IE oder Microsoft Edge Ihres Clients befinden. Sie müssen diese Endpunkte über die in Zeile 14 aufgelisteten, für die gesamte Suite gültigen FQDNs, CDNs und Telemetriewerte hinaus hinzufügen. |  | Vertrauenswürdige Sites |
| 18   | **Yammer**  <br> Yammer steht nur im Browser zur Verfügung und erfordert die Übergabe des authentifizierten Benutzers durch einen Proxy. Alle Yammer-FQDNs müssen sich für eine ordnungsgemäße Funktion in der Zone "Vertrauenswürdige Sites" des IE oder Edge Ihres Clients befinden. |  | Vertrauenswürdige Sites |
| 19  | Verwenden Sie [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) zum Synchronisieren von lokalen Benutzerkonten mit Azure AD. | Siehe [erforderliche Ports und Protokolle zur Hybrid-Identität](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports), [Problembehandlung bei Azure AD-Konnektivitätsproblemen](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity) und [Azure AD Connect Health Agent-Installation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Nur ausgehender Serverdatenverkehr |
| 20  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) mit 21 ViaNet in China, um Benutzerkonten lokal mit Azure AD zu synchronisieren. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Siehe auch [Fehlerbehebung bei Problemen des Eingangs mit Azure AD-Verbindung](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity). | Nur ausgehender Serverdatenverkehr |
|  21  | Microsoft Stream (benötigt das Benutzertoken Azure AD). <BR> Office 365 weltweit (einschließlich GCC) | \**.cloudapp.net <BR> \**.api.microsoftstream.com <BR> \**.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-Port 443  | Eingehender Serverdatenverkehr |
| 22  | Verwenden Sie den MFA-Server für die mehrstufige Authentifizierung, sowohl für neue Installationen des Servers als auch für die Einrichtung von Active Directory Domain Services (AD DS). | Weitere [Informationen finden Sie unter Erste Schritte mit dem Azure AD Multi-Factor Authentication Server](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Nur ausgehender Serverdatenverkehr |
| 23  | Microsoft Graph-Änderungsbenachrichtigungen | Entwickler können [Änderungsbenachrichtigungen](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0) nutzen, um Ereignisse in Microsoft Graph zu abonnieren. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Deutschland: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China, betrieben von 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-Port 443 <BR> Hinweis: Entwickler können beim Erstellen der Abonnements andere Ports angeben.  | Eingehender Serverdatenverkehr |
|||||

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)
  
[Überwachen der Microsoft 365-Konnektivität](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity?view=o365-worldwide)
  
[Clientkonnektivität](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Netzwerke für die Inhaltsübermittlung](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP Ranges and Service Tags – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure-IP-Bereiche und -Diensttags – Deutschland Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP Ranges and Service Tags – China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Öffentlicher Microsoft IP-Bereich](https://www.microsoft.com/download/details.aspx?id=53602)
