---
title: Microsoft Defender für Endpunkt für Kunden der US-Regierung
description: Erfahren Sie mehr über die Microsoft Defender for Endpoint for US Government-Kundenanforderungen und -funktionen, die verfügbar sind
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 16a7d289889940754a6d56058544a675b31192be
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933997"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender für Endpunkt für Kunden der US-Regierung

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint für Us Government-Kunden, die in der Azure US Government-Umgebung erstellt wurden, verwendet dieselben zugrunde liegenden Technologien wie Defender for Endpoint in Azure Commercial.

Dieses Angebot steht GCC-, GCC High- und DoD-Kunden zur Verfügung und basiert auf der gleichen Prävention, Erkennung, Untersuchung und Behebung wie die kommerzielle Version. Es gibt jedoch einige Unterschiede bei der Verfügbarkeit von Funktionen für dieses Angebot.

> [!NOTE]
> Wenn Sie GCC-Kunde sind, der Defender for Endpoint in Commercial verwendet, lesen Sie die öffentlichen Dokumentationsseiten.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Microsoft Defender for Endpoint for US Government-Kunden benötigen eines der folgenden Microsoft-Volumenlizenzangebote:

### <a name="desktop-licensing"></a>Desktoplizenzierung
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 für GCC High | Windows 10 Enterprise E5 für DOD
| | Microsoft 365 E5 für GCC High | Microsoft 365 G5 für DOD
| | Microsoft 365 G5 Security for GCC High | Microsoft 365 G5 Security for DOD
Microsoft Defender for Endpoint – GCC | Microsoft Defender for Endpoint for GCC High | Microsoft Defender for Endpoint for DOD

### <a name="server-licensing"></a>Serverlizenzierung
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender für Endpoint Server GCC | Microsoft Defender für Endpoint Server für GCC High | Microsoft Defender für Endpunktserver für DOD
Azure Defender für Server | Azure Defender for Servers – Government | Azure Defender for Servers – Government

<br />

## <a name="portal-urls"></a>Portal-URLs
Im Folgenden finden Sie die URLs des Microsoft Defender for Endpoint-Portals für Kunden der US-Regierung:

Kundentyp | Portal-URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Endpunktversionen

### <a name="standalone-os-versions"></a>Eigenständige Betriebssystemversionen
Die folgenden Betriebssystemversionen werden unterstützt:

Betriebssystemversion | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10, Version 20H2 (mit [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 2004 (mit [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1909 (mit [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1903 (mit [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1809 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1803 (mit [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1709 | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Ja ](images/svg/check-yes.svg) mit [KB4499147](https://support.microsoft.com/help/4499147)<br />Hinweis: [Veraltet,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)aktualisieren Sie bitte | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt
Windows 10, Version 1703 und früher | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt
Windows Server 2019 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Ja](images/svg/check-yes.svg) In der Vorschau<br />Siehe Hinweis unten | ![Ja](images/svg/check-yes.svg) In der Vorschau<br />Siehe Hinweis unten | ![Ja](images/svg/check-yes.svg) In der Vorschau<br />Siehe Hinweis unten
macOS | ![Ja](images/svg/check-yes.svg) In der Vorschau<br />Siehe Hinweis unten | ![Ja](images/svg/check-yes.svg) In der Vorschau<br />Siehe Hinweis unten | ![Ja](images/svg/check-yes.svg) In der Vorschau<br />Siehe Hinweis unten
Android | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
iOS | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog

> [!NOTE]
> Wenn ein Patch angegeben ist, muss er vor dem Geräte onboarding bereitgestellt werden, um Defender for Endpoint für die richtige Umgebung zu konfigurieren.

> [!NOTE]
> Versuchen Sie, Windows-Geräte, die älter als Windows 10 oder Windows Server 2019 sind, mithilfe von [Microsoft Monitoring Agent zu integrieren?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Sie müssen "Azure US Government" unter "Azure Cloud" [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)auswählen, wenn Sie [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript [verwenden–](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.

> [!NOTE]
> Sie benötigen Version 101.25.72 und höher für Linux und Version 101.25.69 und höher für macOS. Während der Vorschau sind diese Versionen nur im Kanal "Insider Fast" verfügbar. Anweisungen [finden Sie unter Configure the Linux software repository](linux-install-manually.md#configure-the-linux-software-repository) oder Set the channel name [(macOS).](mac-updates.md#set-the-channel-name)

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Betriebssystemversionen bei Verwendung von Azure Defender für Server
Die folgenden Betriebssystemversionen werden bei Verwendung von [Azure Defender für Server unterstützt:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

Betriebssystemversion | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Erforderliche Konnektivitätseinstellungen
Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

In der folgenden herunterladbaren Tabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann. Überprüfen Sie, ob es keine Firewall- oder Netzwerkfilterregeln gibt,  die den Zugriff auf diese URLs verweigern oder eine speziell für sie zulässige Regel erstellen würden.

Tabellenkalkulation der Domänenliste | Beschreibung
:-----|:-----
![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/> | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br /><br />[Laden Sie die Tabelle hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Weitere Informationen finden Sie unter [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen.](configure-proxy-internet.md)

> [!NOTE]
> Die Tabelle enthält auch kommerzielle URLs, stellen Sie sicher, dass Sie die Registerkarten "US Gov" überprüfen.
> 
> Suchen Sie beim Filtern nach den Datensätzen mit der Bezeichnung "US Gov" und Ihrer spezifischen Cloud unter der Spalte Geografie.

### <a name="service-backend-ip-ranges"></a>Dienst-Back-End-IP-Bereiche

Wenn Ihre Netzwerkgeräte KEINE DNS-basierten Regeln unterstützen, verwenden Sie stattdessen IP-Bereiche.

Defender for Endpoint für Us Government-Kunden ist in der Azure US Government-Umgebung aufgebaut, die in den folgenden Regionen bereitgestellt wird:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Die Azure-IP-Bereiche finden Sie unter [Azure IP Ranges and Service Tags – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Als cloudbasierte Lösung können sich die IP-Adressbereiche ändern. Es wird empfohlen, zu DNS-basierten Regeln zu wechseln.

<br />

## <a name="api"></a>API
Anstelle der in der API-Dokumentation aufgeführten öffentlichen [URIs](apis-intro.md)müssen Sie die folgenden URIs verwenden:

Endpunkttyp | GCC | GCC High & DoD
:---|:---|:---
Anmeldung | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender für Endpunkt-API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Featureparität mit kommerziellen
Kunden von Defender for Endpoint für US Government haben keine vollständige Parität mit dem kommerziellen Angebot. Unser Ziel besteht zwar in der Bereitstellung aller kommerziellen Features und Funktionen für unsere Kunden in den USA, es gibt jedoch noch nicht verfügbare Funktionen, die wir hervorheben möchten.

Dies sind die bekannten Lücken ab März 2021:

Featurename | GCC | GCC High | DoD
:---|:---|:---|:---
Automatisierte Untersuchung und Behebung: Liveantwort | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Automatisierte Untersuchung und Behebung: Reaktion auf Office 365-Warnungen | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
E-Mail-Benachrichtigungen | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Evaluierungslabor | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Verwaltung und APIs: Bericht über geräteintehitäts- und compliance | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Verwaltung und APIs: Integration in Drittanbieterprodukte | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Verwaltung und APIs: Streaming-API | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Verwaltung und APIs: Bedrohungsschutzbericht | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Bedrohungs- und Sicherheitsrisikomanagement | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Bedrohungsanalyse | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Internet-Inhaltsfilterung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Microsoft Cloud App Security | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
Integrationen: Microsoft Compliance Manager | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
Integrationen: Microsoft Defender for Identity | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
Integrationen: Microsoft Defender für Office 365 | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
Integrationen: Microsoft Endpoint DLP | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
Integrationen: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Skype for Business / Teams | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Microsoft-Bedrohungsexperten | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
