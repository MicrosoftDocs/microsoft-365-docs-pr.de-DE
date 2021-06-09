---
title: Onboarding früherer Versionen von Windows in Microsoft Defender für Endpunkt
description: Onboarding unterstützter früherer Versionen von Windows Geräten, sodass sie Sensordaten an den Microsoft Defender für Endpunkt-Sensor senden können
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
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844430"
---
# <a name="onboard-previous-versions-of-windows"></a>Onboarding von früheren Windows-Versionen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformen**
- Windows 7 SP1-Enterprise
- Windows 7 SP1-Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender für Endpunkt erweitert die Unterstützung um Vorgängerbetriebssysteme und bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen auf unterstützten Windows Versionen.

Zum Onboarding von untergeordneten Windows Clientendpunkten in Defender für Endpunkt müssen Sie:
- Konfigurieren und Aktualisieren System Center Endpoint Protection Clients.
- Installieren und konfigurieren Sie Microsoft Monitoring Agent (MMA), um Sensordaten wie unten beschrieben an Defender für Endpunkt zu melden.

> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Endpunkt.](run-detection-test.md)

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Konfigurieren und Aktualisieren System Center Endpoint Protection Clients
> [!IMPORTANT]
> Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet.

Defender für Endpunkt lässt sich in System Center Endpoint Protection integrieren, um die Erkennung von Schadsoftware sichtbar zu machen und die Verbreitung eines Angriffs in Ihrer Organisation zu beenden, indem potenziell schädliche Dateien oder verdächtige Schadsoftware verboten werden. 

Die folgenden Schritte sind erforderlich, um diese Integration zu ermöglichen: 
- Installieren des [Plattformupdates für die Antischadsoftware-Plattform vom Januar 2017 für Endpoint Protection Clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Konfigurieren der SCEP-Client-Cloud Protection Service-Mitgliedschaft mit der **Erweiterten** Einstellung
- Konfigurieren Sie Ihr Netzwerk so, dass Verbindungen mit der Microsoft Defender Antivirus Cloud zugelassen werden. Weitere Informationen finden Sie unter [Zulassen von Verbindungen mit der Microsoft Defender Antivirus Cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender für Endpunkt

### <a name="before-you-begin"></a>Bevor Sie beginnen
Überprüfen Sie die Mindestsystemanforderungen anhand der folgenden Details:
- Installieren des [monatlichen Updaterollups vom Februar 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Gilt nur für Windows 7 SP1-Enterprise und Windows 7 SP1-Pro. 

- Installieren des [Updates für Kundenerfahrung und Diagnosetelemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Installieren Von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Gilt nur für Windows 7 SP1-Enterprise und Windows 7 SP1-Pro.
    > Installieren Sie .NET Framework 4.0.x nicht, da die oben genannte Installation nicht mehr ausgeführt wird.

- Erfüllen sie die Mindestsystemanforderungen des Azure Log Analytics-Agents. Weitere Informationen finden Sie unter [Sammeln von Daten von Computern in Ihrer Umgebung mit Log Analytics.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603) oder [Windows 32-Bit-Agent.](https://go.microsoft.com/fwlink/?LinkId=828604)

2. Abrufen der Arbeitsbereichs-ID:
   - Wählen Sie im Navigationsbereich von Defender für Endpunkt **Einstellungen > Geräteverwaltung > Onboarding** aus.
   - Wählen Sie **Windows 7 SP1 und 8.1** als Betriebssystem aus.
   - Kopieren der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels

3. Wählen Sie unter Verwendung der Arbeitsbereichs-ID und des Arbeitsbereichsschlüssels eine der folgenden Installationsmethoden aus, um den Agent zu installieren:
    - [Installieren Sie den Agent manuell mithilfe des Setups.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard) <br>
      Wählen Sie auf der Seite **"Agent-Setupoptionen"** **Verbinden agent zu Azure Log Analytics (OMS)** aus.
    - [Installieren Sie den Agent über die Befehlszeile.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)
    - [Konfigurieren Sie den Agent mithilfe eines Skripts.](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

   > [!NOTE]
   > Wenn Sie [US Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder eine Befehlszeile oder ein Skript verwenden . Legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1 fest.

4. Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt "Proxyeinstellungen konfigurieren".

Nach Abschluss des Vorgangs sollten innerhalb einer Stunde integrierte Endpunkte im Portal angezeigt werden.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor
 
- Jeder Windows Endpunkt muss in der Lage sein, eine Verbindung mit dem Internet über HTTPS herzustellen. Diese Verbindung kann direkt, mithilfe eines Proxys oder über das [OMS-Gateway](/azure/log-analytics/log-analytics-oms-gateway)erfolgen.
- Wenn ein Proxy oder eine Firewall standardmäßig den gesamten Datenverkehr blockiert und nur bestimmte Domänen durchlässt oder HTTPS-Überprüfung (SSL-Überprüfung) aktiviert ist, stellen Sie sicher, dass Sie [den Zugriff auf Defender für Endpunkt-Dienst-URLs aktivieren.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

## <a name="offboard-client-endpoints"></a>Offboard-Clientendpunkte
Um das Offboarding auszuführen, können Sie den MMA-Agent vom Endpunkt deinstallieren oder ihn von der Berichterstellung an Ihren Defender für Endpunkt-Arbeitsbereich trennen. Nach dem Offboarding des Agents sendet der Endpunkt keine Sensordaten mehr an Defender für Endpunkt. 

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)
