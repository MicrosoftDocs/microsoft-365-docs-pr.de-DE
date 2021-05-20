---
title: Microsoft Defender für Endpunkt für Kunden der US-Regierung
description: Erfahren Sie mehr über die Anforderungen und Funktionen von Microsoft Defender for Endpoint für Kunden der US-Regierung
keywords: Regierung, gcc, high, Anforderungen, Fähigkeiten, Verteidiger, Microsoft Defender für Endpunkt, Endpunkt, dod
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
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572669"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender für Endpunkt für Kunden der US-Regierung

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint für KUNDEN der US-Regierung, die in der Azure US Government-Umgebung erstellt wurden, verwendet dieselben zugrunde liegenden Technologien wie Defender for Endpoint in Azure Commercial.

Dieses Angebot steht GCC-, GCC-High- und DoD-Kunden zur Verfügung und basiert auf der gleichen Prävention, Erkennung, Untersuchung und Behebung wie die kommerzielle Version. Es gibt jedoch einige Unterschiede in der Verfügbarkeit von Funktionen für dieses Angebot.

> [!NOTE]
> Wenn Sie ein GCC Kunde sind, der Defender for Endpoint in Commercial verwendet, lesen Sie bitte die öffentlichen Dokumentationsseiten.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Microsoft Defender for Endpoint für KUNDEN der US-Regierung erfordert eines der folgenden Microsoft-Volumenlizenzangebote:

### <a name="desktop-licensing"></a>Desktoplizenzierung
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 für GCC High | Windows 10 Enterprise E5 für DOD
| | Microsoft 365 E5 für GCC High | Microsoft 365 G5 für DOD
| | Microsoft 365 G5-Sicherheit für GCC High | Microsoft 365 G5-Sicherheit für DOD
Microsoft Defender für Endpunkt - GCC | Microsoft Defender für Endpoint für GCC High | Microsoft Defender für Endpunkt für DOD

### <a name="server-licensing"></a>Serverlizenzierung
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender für Endpoint Server GCC | Microsoft Defender für Endpoint Server für GCC High | Microsoft Defender für Endpoint Server für DOD
Azure Defender für Server | Azure Defender für Server - Regierung | Azure Defender für Server - Regierung

<br />

## <a name="portal-urls"></a>Portal-URLs
Im Folgenden sind die Microsoft Defender for Endpoint-Portal-URLs für KUNDEN der US-Regierung:

Kundentyp | Portal-URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Endpunktversionen

### <a name="standalone-os-versions"></a>Eigenständige Betriebssystemversionen
Die folgenden Betriebssystemversionen werden unterstützt:

OS-Version | GCC | GCC High | DoD
:---|:---|:---|:---
Windows 10, Version 20H2 (mit [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 2004 (mit [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1909 (mit [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1903 (mit [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1809 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1803 (mit [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 1709 | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Ja ](images/svg/check-yes.svg) Mit [KB4499147](https://support.microsoft.com/help/4499147)<br />Hinweis: [Veraltet,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)bitte aktualisieren | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt
Windows 10, Version 1703 und früher | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt | ![Nein](images/svg/check-no.svg)<br />Hinweis: Wird nicht unterstützt
Windows Server 2019 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
macOS | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Android | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand
iOS | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand

> [!NOTE]
> Wenn ein Patch angegeben ist, muss er vor dem Onboarding des Geräts bereitgestellt werden, um Defender for Endpoint in der richtigen Umgebung zu konfigurieren.

> [!NOTE]
> Versuchen Sie, Windows Geräte, die älter als Windows 10 oder Windows Server 2019 sind, mit [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)einzusteigen? Wenn Sie den [Setup-Assistenten](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)verwenden oder eine [Befehlszeile](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) oder ein [Skript](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) verwenden, müssen Sie unter "Azure US Government" unter "Azure Cloud" "Azure US Government" auswählen oder den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1 setzen.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Betriebssystemversionen bei Verwendung von Azure Defender für Server
Die folgenden Betriebssystemversionen werden bei verwendung von [Azure Defender für Server](/azure/security-center/security-center-wdatp)unterstützt:

OS-Version | GCC | GCC High | DoD
:---|:---|:---|:---
Windows Server 2019 | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Erforderliche Konnektivitätseinstellungen
Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

In der folgenden herunterladbaren Kalkulationstabelle werden die Dienste und die zugehörigen URLs aufgeführt, mit der Ihr Netzwerk eine Verbindung herstellen kann. Stellen Sie sicher, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern würden, oder erstellen Sie eine *Zulassungsregel* speziell für sie.

Tabellenkalkulation der Domänenliste | Beschreibung
:-----|:-----
![Thumb-Bild für Microsoft Defender für Endpoint URLs-Tabelle](images/mdatp-urls.png)<br/> | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br /><br />[Laden Sie die Tabelle hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Weitere Informationen finden Sie unter Konfigurieren von [Geräteproxy- und Internetverbindungseinstellungen](configure-proxy-internet.md).

> [!NOTE]
> Die Tabelle enthält auch kommerzielle URLs, stellen Sie sicher, dass Sie die Registerkarten "US Gov" überprüfen.
> 
> Suchen Sie beim Filtern nach den Datensätzen, die als "US Gov" gekennzeichnet sind, und Nach Ihrer spezifischen Cloud unter der Geographiespalte.

### <a name="service-backend-ip-ranges"></a>Service-Backend-IP-Bereiche

Wenn Ihre Netzwerkgeräte keine DNS-basierten Regeln unterstützen, verwenden Sie stattdessen IP-Bereiche.

Defender for Endpoint für Kunden der US-Regierung wird in der Azure US Government-Umgebung erstellt und in den folgenden Regionen bereitgestellt:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Die Azure-IP-Bereiche finden Sie in [Azure IP Ranges und Service Tags – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Als Cloud-basierte Lösung können sich die IP-Adressbereiche ändern. Es wird empfohlen, zu DNS-basierten Regeln zu wechseln.

<br />

## <a name="api"></a>API
Anstelle der in unserer [API-Dokumentation](apis-intro.md)aufgeführten öffentlichen URIs müssen Sie die folgenden URIs verwenden:

Endpunkttyp | GCC | GCC High & DoD
:---|:---|:---
Anmeldung | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender für Endpoint-API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Feature-Parität mit kommerziellen
Defender for Endpoint für Kunden der US-Regierung hat keine vollständige Parität mit dem kommerziellen Angebot. Unser Ziel ist es zwar, unseren Kunden der US-Regierung alle kommerziellen Funktionen und Funktionen zur Verfügung zu stellen, aber es gibt einige Funktionen, die wir noch nicht hervorheben möchten.

Dies sind die bekannten Lücken:

Featurename | GCC | GCC High | DoD
:---|:---|:---|:---
Verwaltung und APIs: Streaming-API | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Internet-Inhaltsfilterung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Integrationen: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) Warnungen <br /> ![Nein](images/svg/check-no.svg) Vorfälle & Rohdaten: In der Entwicklung | ![Ja](images/svg/check-yes.svg) Warnungen <br /> ![Nein](images/svg/check-no.svg) Vorfälle & Rohdaten: In der Entwicklung
Integrationen: Microsoft Cloud App Security | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Integrationen: Microsoft Compliance Manager | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Integrationen: Microsoft Defender für Identität | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Integrationen: Microsoft Endpoint DLP | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Integrationen: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Integrationen: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nein](images/svg/check-no.svg) In Entwicklung | ![Nein](images/svg/check-no.svg) In Entwicklung
Microsoft-Bedrohungsexperten | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand | ![Nein](images/svg/check-no.svg) Auf Engineering-Rückstand
