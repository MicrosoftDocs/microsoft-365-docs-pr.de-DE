---
title: Onboarding früherer Windows in Microsoft Defender for Endpoint
description: Onboarding unterstützter früherer Windows,damit sie Sensordaten an den Microsoft Defender for Endpoint-Sensor senden können
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7ed7390f67747d176145bb051d8b1633a7146a23
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730810"
---
# <a name="onboard-previous-versions-of-windows"></a>Onboarding von früheren Windows-Versionen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformen**
- Windows 7 SP1-Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).

Defender for Endpoint erweitert die Unterstützung um Betriebssysteme auf unterer Ebene und bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen für unterstützte Windows Versionen.

Zum Onboarding von Windows Clientendpunkten an Defender for Endpoint müssen Sie:
- Konfigurieren und Aktualisieren System Center Endpoint Protection Clients.
- Installieren und konfigurieren Microsoft Monitoring Agent (MMA), um Sensordaten wie unten beschrieben an Defender for Endpoint zu melden.

> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integrierte ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Endpunkt](run-detection-test.md).

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Konfigurieren und Aktualisieren System Center Endpoint Protection Clients
> [!IMPORTANT]
> Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet.

Defender for Endpoint integriert sich in System Center Endpoint Protection, um Schadsoftwareerkennungen sichtbar zu machen und die Verbreitung eines Angriffs in Ihrer Organisation zu beenden, indem potenziell schädliche Dateien oder mutmaßliche Schadsoftware verboten werden. 

Die folgenden Schritte sind erforderlich, um diese Integration zu aktivieren: 
- Installieren des [Anti-Malware-Plattformupdates vom Januar 2017 für Endpoint Protection Clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Konfigurieren der Cloud Protection Service-Mitgliedschaft des SCEP-Clients auf die **Erweiterte** Einstellung
- Konfigurieren Sie Ihr Netzwerk so, dass Verbindungen mit der Microsoft Defender Antivirus werden. Weitere Informationen finden Sie unter [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installieren und Konfigurieren Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender for Endpoint

### <a name="before-you-begin"></a>Bevor Sie beginnen
Überprüfen Sie die folgenden Details, um die Mindestsystemanforderungen zu überprüfen:
- Installieren des monatlichen Updaterollups vom Februar [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Gilt nur für Windows 7 SP1 Enterprise und Windows 7 SP1 Pro. 

- Installieren des [Updates für Kundenerfahrung und Diagnosetelemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Installieren von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Gilt nur für Windows 7 SP1 Enterprise und Windows 7 SP1 Pro.
    > Installieren Sie nicht .NET Framework 4.0.x, da die oben aufgeführte Installation negiert wird.

- Erfüllen Sie die Mindestsystemanforderungen des Azure Log Analytics-Agents. Weitere Informationen finden Sie unter [Sammeln von Daten von Computern in Ihrer Umgebung mit Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).



1. Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603) oder [Windows 32-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Rufen Sie die Arbeitsbereichs-ID ab:
   - Wählen Sie im Navigationsbereich Defender for Endpoint die **Option Einstellungen > Geräteverwaltung > Onboarding aus.**
   - Wählen **Windows 7 SP1 und 8.1** als Betriebssystem aus
   - Kopieren der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels

3. Wählen Sie unter Verwendung der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels eine der folgenden Installationsmethoden aus, um den Agent zu installieren:
    - [Installieren Sie den Agent manuell mithilfe von Setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      Wählen Sie **auf** der Seite Agent-Setupoptionen **die Option Verbinden Agent in Azure Log Analytics (OMS) aus.**
    - [Installieren Sie den Agent über die Befehlszeile](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Konfigurieren Sie den Agent mithilfe eines Skripts.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

   > [!NOTE]
   > Wenn Sie ein [Us Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript verwenden – legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.

4. Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt Konfigurieren von Proxyeinstellungen.

Sobald sie abgeschlossen sind, sollten integrierte Endpunkte innerhalb einer Stunde im Portal angezeigt werden.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor
 
- Jeder Windows-Endpunkt muss über HTTPS eine Verbindung mit dem Internet herstellen können. Diese Verbindung kann direkt über einen Proxy oder über das [OMS-Gateway hergestellt werden.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)
- Wenn ein Proxy oder eine Firewall standardmäßig den ganzen Datenverkehr blockiert und nur bestimmte Domänen über oder die HTTPS-Überprüfung (SSL-Überprüfung) aktiviert ist, stellen Sie sicher, dass Sie den Zugriff auf [DIE URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)des Defender for Endpoint-Diensts aktivieren.

## <a name="offboard-client-endpoints"></a>Offboard-Clientendpunkte
In offboard können Sie den MMA-Agent vom Endpunkt deinstallieren oder von der Berichterstellung an Ihren Defender for Endpoint-Arbeitsbereich trennen. Nach dem Offboarding des Agents sendet der Endpunkt keine Sensordaten mehr an Defender for Endpoint. 

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).
