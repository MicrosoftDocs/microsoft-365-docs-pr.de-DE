---
title: Microsoft Defender für Endpunkt für Kunden der US-Regierung
description: Erfahren Sie mehr über die Kundenanforderungen und Funktionen von Microsoft Defender für Endpunkt für US Government.
keywords: Government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
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
ms.openlocfilehash: 7956c1454cd7bd962eda984cc9d93be9824d7458
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822105"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender für Endpunkt für Kunden der US-Regierung

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender für Endpunkt für US Government-Kunden, die in der Azure US Government-Umgebung erstellt wurden, verwendet die gleichen zugrunde liegenden Technologien wie Defender für Endpunkt in Azure Commercial.

Dieses Angebot steht GCC, GCC High- und DoD-Kunden zur Verfügung und basiert auf der gleichen Verhinderung, Erkennung, Untersuchung und Wartung wie die kommerzielle Version. Es gibt jedoch einige Unterschiede bei der Verfügbarkeit von Funktionen für dieses Angebot.

> [!NOTE]
> Wenn Sie ein GCC Kunde sind, der Defender für Endpunkt in Commercial verwendet, lesen Sie bitte die öffentlichen Dokumentationsseiten.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Microsoft Defender für Endpunkt für US Government-Kunden erfordert eines der folgenden Microsoft-Volumenlizenzierungsangebote:

### <a name="desktop-licensing"></a>Desktoplizenzierung
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 für GCC Hoch | Windows 10 Enterprise E5 für DOD
| | Microsoft 365 E5 für GCC High | Microsoft 365 G5 für DOD
| | Microsoft 365 G5 Security for GCC High | Microsoft 365 G5-Sicherheit für DOD
Microsoft Defender für Endpunkt – GCC | Microsoft Defender für Endpunkt für GCC Hoch | Microsoft Defender für Endpunkt für DOD

### <a name="server-licensing"></a>Serverlizenzierung
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender für Endpoint Server GCC | Microsoft Defender für Endpunktserver für GCC Hoch | Microsoft Defender für Endpunktserver für DOD
Azure Defender für Server | Azure Defender für Server – Behörden | Azure Defender für Server – Behörden

<br />

## <a name="portal-urls"></a>Portal-URLs
Nachfolgend sind die URLs des Microsoft Defender für Endpunkt-Portals für US Government-Kunden dargestellt:

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
Windows 10, Version 1709 | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Ja ](images/svg/check-yes.svg) mit [KB4499147](https://support.microsoft.com/help/4499147)<br />Hinweis: [Veraltet,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)bitte upgraden | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt
Windows 10, Version 1703 und früher | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt
Windows Server 2019 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1-Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1-Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
macOS | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Android | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
iOS | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog

> [!NOTE]
> Wenn ein Patch angegeben ist, muss er vor dem Onboarding des Geräts bereitgestellt werden, um Defender für Endpunkt in der richtigen Umgebung zu konfigurieren.

> [!NOTE]
> Sie möchten Windows Geräte integrieren, die älter als Windows 10 oder Windows Server 2019 sind, indem [Sie Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)verwenden? Wenn Sie den [Setup-Assistenten](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)verwenden oder eine [Befehlszeile](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) oder ein [Skript](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) verwenden, müssen Sie "Azure US Government" unter "Azure Cloud" auswählen. Legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1 fest.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Betriebssystemversionen bei Verwendung von Azure Defender für Server
Die folgenden Betriebssystemversionen werden bei Verwendung von [Azure Defender für Server](/azure/security-center/security-center-wdatp)unterstützt:

Betriebssystemversion | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2019 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Erforderliche Verbindungseinstellungen
Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

In der folgenden herunterladbaren Tabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit denen Ihr Netzwerk eine Verbindung herstellen kann. Stellen Sie sicher, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern oder eine *spezielle Zulassungsregel* erstellen würden.

Kalkulationstabelle der Domänenliste | Beschreibung
:-----|:-----
![Miniaturbild für Microsoft Defender für Endpunkt-URLs-Tabellenkalkulation](images/mdatp-urls.png)<br/> | Kalkulationstabelle für bestimmte DNS-Einträge für Dienststandorte, geografische Standorte und Das Betriebssystem. <br /><br />[Laden Sie das Arbeitsblatt hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Weitere Informationen finden Sie unter [Konfigurieren von Einstellungen für Geräteproxy und Internetverbindung.](configure-proxy-internet.md)

> [!NOTE]
> Das Arbeitsblatt enthält auch kommerzielle URLs, stellen Sie sicher, dass Sie die Registerkarten "US Gov" überprüfen.
> 
> Suchen Sie beim Filtern nach den Datensätzen mit der Bezeichnung "US Gov" und Ihrer spezifischen Cloud unter der Spalte "Geografie".

### <a name="service-backend-ip-ranges"></a>Dienst-Back-End-IP-Bereiche

Wenn Ihre Netzwerkgeräte keine DNS-basierten Regeln unterstützen, verwenden Sie stattdessen IP-Bereiche.

Defender für Endpunkt für US Government-Kunden ist in der Azure US Government-Umgebung integriert und wird in den folgenden Regionen bereitgestellt:

- AzureCloud.usgov tex
- AzureCloud.usgovvirginia

Sie finden die Azure-IP-Bereiche in [Azure-IP-Bereichen und Diensttags – US Government Cloud.](https://www.microsoft.com/download/details.aspx?id=57063)

> [!NOTE]
> Als cloudbasierte Lösung können sich die IP-Adressbereiche ändern. Es wird empfohlen, zu DNS-basierten Regeln zu wechseln.

<br />

## <a name="api"></a>API
Anstelle der öffentlichen URIs, die in unserer [API-Dokumentation](apis-intro.md)aufgeführt sind, müssen Sie die folgenden URIs verwenden:

Endpunkttyp | GCC | GCC High & DoD
:---|:---|:---
Login | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender für Endpunkt-API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Featureparität mit kommerziellem
Defender für Endpunkt für US Government-Kunden haben keine vollständige Parität mit dem kommerziellen Angebot. Unser Ziel ist es zwar, alle kommerziellen Features und Funktionen für unsere US Government-Kunden bereitzustellen, aber es gibt einige Funktionen, die wir noch nicht hervorheben möchten.

Dies sind die bekannten Lücken:

Featurename | GCC | GCC High | DoD
:---|:---|:---|:---
Verwaltung und APIs: Streaming-API | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Internet-Inhaltsfilterung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) Warnungen <br /> ![Nein](images/svg/check-no.svg) Vorfälle & Rohdaten: In der Entwicklung | ![Ja](images/svg/check-yes.svg) Warnungen <br /> ![Nein](images/svg/check-no.svg) Vorfälle & Rohdaten: In der Entwicklung
Integrationen: Microsoft Cloud App Security | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Microsoft Compliance Manager | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Microsoft Defender for Identity | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Microsoft Endpoint DLP | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Integrationen: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Integrationen: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In der Entwicklung | ![Nein](images/svg/check-no.svg) In der Entwicklung
Microsoft-Bedrohungsexperten | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog | ![Nein](images/svg/check-no.svg) On Engineering Backlog
