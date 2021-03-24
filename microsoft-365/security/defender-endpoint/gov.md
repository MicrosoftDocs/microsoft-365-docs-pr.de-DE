---
title: Microsoft Defender for Endpoint für Us Government-Kunden
description: Erfahren Sie mehr über die Microsoft Defender for Endpoint for US Government-Kundenanforderungen und -funktionen, die verfügbar sind
keywords: government, gcc, high, requirements, capabilities, defender, defender atp, mdatp, endpoint, dod
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
ms.openlocfilehash: 31928deddc2a504cc0b6c91af287e4977791c920
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065871"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender for Endpoint für Us Government-Kunden

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint for US Government-Kunden, die in der US Azure Government-Umgebung erstellt wurden, verwendet dieselben zugrunde liegenden Technologien wie Defender for Endpoint in Azure Commercial.

Dieses Angebot steht GCC-, GCC High- und DoD-Kunden zur Verfügung und basiert auf der gleichen Prävention, Erkennung, Untersuchung und Behebung wie die kommerzielle Version. Es gibt jedoch einige Unterschiede bei der Verfügbarkeit von Funktionen für dieses Angebot.

> [!NOTE]
> Wenn Sie GCC-Kunde sind, der Defender for Endpoint in Commercial verwendet, lesen Sie die öffentlichen Dokumentationsseiten.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Microsoft Defender for Endpoint for US Government-Kunden benötigen eines der folgenden Microsoft-Volumenlizenzangebote:

### <a name="desktop-licensing"></a>Desktoplizenzierung
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 für GCC High | Windows 10 Enterprise E5 für DOD
| | Microsoft 365 E5 für GCC High | 
| | Microsoft 365 G5 Security for GCC High | 
Microsoft Defender for Endpoint – GCC | Microsoft Defender for Endpoint for GCC High | Microsoft Defender for Endpoint for DOD

### <a name="server-licensing"></a>Serverlizenzierung
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender für Endpoint Server GCC | Microsoft Defender für Endpoint Server für GCC High | Microsoft Defender für Endpunktserver für DOD
Azure Defender für Server | Azure Defender for Servers – Government | Azure Defender for Servers – Government

> [!NOTE]
> Die DoD-Lizenzierung steht nur bei der allgemeinen Verfügbarkeit von DoD zur Verfügung.

<br>

## <a name="portal-urls"></a>Portal-URLs
Im Folgenden finden Sie die URLs des Microsoft Defender for Endpoint-Portals für Kunden der US-Regierung:

Kundentyp | Portal-URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD (PREVIEW) | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>Endpunktversionen

### <a name="standalone-os-versions"></a>Eigenständige Betriebssystemversionen
Die folgenden Betriebssystemversionen werden unterstützt:

Betriebssystemversion | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows 10, Version 20H2 (mit [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, Version 2004 (mit [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 10, Version 1909 (mit [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 10, Version 1903 (mit [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 10, Version 1809 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 10, Version 1803 (mit [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 10, Version 1709 | ![Nein](/security/defender-endpoint/images/svg/check-no)<br>Hinweis: Wird nicht unterstützt | ![Ja ](/security/defender-endpoint/images/svg/check-yes) mit [KB4499147](https://support.microsoft.com/help/4499147)<br>Hinweis: [Veraltet,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)aktualisieren Sie bitte | ![Nein](/security/defender-endpoint/images/svg/check-no)<br>Hinweis: Wird nicht unterstützt
Windows 10, Version 1703 und früher | ![Nein](/security/defender-endpoint/images/svg/check-no)<br>Hinweis: Wird nicht unterstützt | ![Nein](/security/defender-endpoint/images/svg/check-no)<br>Hinweis: Wird nicht unterstützt | ![Nein](/security/defender-endpoint/images/svg/check-no)<br>Hinweis: Wird nicht unterstützt
Windows Server 2019 (mit [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2016 | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 SP1 | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 8.1 Enterprise | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 8 Pro | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 Enterprise | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 Pro | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Linux | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
macOS | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Android | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
iOS | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog

> [!NOTE]
> Wenn ein Patch angegeben ist, muss er vor dem Geräte onboarding bereitgestellt werden, um Defender for Endpoint für die richtige Umgebung zu konfigurieren.

> [!NOTE]
> Versuchen Sie, Windows-Geräte, die älter als Windows 10 oder Windows Server 2019 sind, mithilfe von [Microsoft Monitoring Agent zu integrieren?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Sie müssen "Azure US Government" unter "Azure Cloud" [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)auswählen, wenn Sie [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript [verwenden–](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Betriebssystemversionen bei Verwendung von Azure Defender für Server
Die folgenden Betriebssystemversionen werden bei Verwendung von [Azure Defender für Server unterstützt:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

Betriebssystemversion | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows Server 2016 | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 SP1 | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)

<br>

## <a name="required-connectivity-settings"></a>Erforderliche Konnektivitätseinstellungen
Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

In der folgenden herunterladbaren Tabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann. Überprüfen Sie, ob es keine Firewall- oder Netzwerkfilterregeln gibt,  die den Zugriff auf diese URLs verweigern oder eine speziell für sie zulässige Regel erstellen würden.

Tabellenkalkulation der Domänenliste | Beschreibung
:-----|:-----
![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/> | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br><br>[Laden Sie die Tabelle hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Weitere Informationen finden Sie unter [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen.](configure-proxy-internet.md)

> [!NOTE]
> Die Tabelle enthält auch kommerzielle URLs, stellen Sie sicher, dass Sie die Registerkarten "US Gov" überprüfen. <br> Suchen Sie beim Filtern nach den Datensätzen mit der Bezeichnung "US Gov" und Ihrer spezifischen Cloud unter der Spalte Geografie.

<br>

## <a name="api"></a>API
Anstelle der in der API-Dokumentation aufgeführten öffentlichen [URIs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)müssen Sie die folgenden URIs verwenden:

Endpunkttyp | GCC | GCC High & DoD (PREVIEW)
:---|:---|:---
Anmeldung | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender für Endpunkt-API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>Featureparität mit kommerziellen
Defender for Endpoint hat keine vollständige Parität mit dem kommerziellen Angebot. Unser Ziel besteht zwar in der Bereitstellung aller kommerziellen Features und Funktionen für unsere Kunden in den USA, es gibt jedoch noch nicht verfügbare Funktionen, die wir hervorheben möchten.

Dies sind die bekannten Lücken ab Februar 2021:

Featurename | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Automatisierte Untersuchung und Behebung: Liveantwort | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Automatisierte Untersuchung und Behebung: Reaktion auf Office 365-Warnungen | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
E-Mail-Benachrichtigungen | ![Nein](/security/defender-endpoint/images/svg/check-no) Rollout | ![Nein](/security/defender-endpoint/images/svg/check-no) Rollout | ![Nein](/security/defender-endpoint/images/svg/check-no) Rollout
Evaluierungslabor | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Verwaltung und APIs: Bericht über geräteintehitäts- und compliance | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Verwaltung und APIs: Integration in Drittanbieterprodukte | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Verwaltung und APIs: Streaming-API | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Verwaltung und APIs: Bedrohungsschutzbericht | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Sicherheitsrisikoverwaltung & Bedrohungen | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Bedrohungsanalyse | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Filtern von Webinhalten | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Integrationen: Azure Sentinel | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Integrationen: Microsoft Cloud App Security | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
Integrationen: Microsoft Compliance Manager | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
Integrationen: Microsoft Defender for Identity | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
Integrationen: Microsoft Defender für Office 365 | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
Integrationen: Microsoft Endpoint DLP | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
Integrationen: Microsoft Intune | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Integrationen: Microsoft Power Automate & Azure Logic Apps | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung | ![Nein](/security/defender-endpoint/images/svg/check-no) In der Entwicklung
Integrationen: Skype for Business / Teams | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes) | ![Ja](/security/defender-endpoint/images/svg/check-yes)
Microsoft-Bedrohungsexperten | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog | ![Nein](/security/defender-endpoint/images/svg/check-no) On Engineering Backlog
