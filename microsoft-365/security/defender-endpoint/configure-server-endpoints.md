---
title: Onboarding von Windows-Servern in den Microsoft Defender for Endpoint-Dienst
description: Onboarding von Windows-Servern, damit sie Sensordaten an den Microsoft Defender for Endpoint-Sensor senden können.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Windows ATP servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bd92b44892b49a007316acb97296a44514db0578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061703"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Onboarding von Windows-Servern in den Microsoft Defender for Endpoint-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server (SAC) Version 1803 und höher
- Windows Server 2019 und höher
- Windows Server 2019 Core Edition

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


Defender for Endpoint erweitert die Unterstützung auch auf das Windows Server-Betriebssystem. Diese Unterstützung bietet erweiterte Angriffserkennungs- und Untersuchungsfunktionen nahtlos über die Microsoft Defender Security Center-Konsole.

Eine praktische Anleitung dazu, was für Lizenzierung und Infrastruktur erforderlich ist, finden Sie unter [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).

Anleitungen zum Herunterladen und Verwenden von Windows Security Baselines für Windows-Server finden Sie unter [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016

Sie können Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016 in Defender for Endpoint integrieren, indem Sie eine der folgenden Optionen verwenden:

- **Option 1**: [Onboarding durch Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)
- **Option 2**: [Onboarding über Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)
- **Option 3**: [Onboarding über Microsoft Endpoint Manager, Version 2002 und höher](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)


Nachdem Sie die Onboardingschritte mit einer der bereitgestellten Optionen abgeschlossen haben, müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)


> [!NOTE]
> Die eigenständige Defender for Endpoint-Serverlizenz ist pro Knoten erforderlich, um einen Windows-Server über den Microsoft Monitoring Agent (Option 1) oder den Microsoft Endpoint Manager (Option 3) zu integrieren. Alternativ ist eine Azure Defender for Servers-Lizenz pro Knoten erforderlich, um einen Windows-Server über Azure Security Center (Option 2) zu integrieren. Weitere Informationen finden Sie unter Unterstützte Features, die [in Azure Security Center verfügbar sind.](https://docs.microsoft.com/azure/security-center/security-center-services)


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>Option 1: Onboarding durch Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA)
Sie müssen MMA für Windows-Server installieren und konfigurieren, um Sensordaten an Defender for Endpoint zu melden. Weitere Informationen finden Sie unter [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).

Wenn Sie bereits System Center Operations Manager (SCOM) oder Azure Monitor (ehemals Operations Management Suite (OMS) verwenden, fügen Sie den Microsoft Monitoring Agent (MMA) an, um ihren Defender for Endpoint-Arbeitsbereich über die Multihomingunterstützung zu melden.

Im Allgemeinen müssen Sie die folgenden Schritte ausführen:
1. Erfüllen Sie die im Abschnitt Before you begin beschriebenen **Onboardinganforderungen.**
2. Aktivieren Sie die Serverüberwachung vom Microsoft Defender Security Center aus.
3. Installieren und konfigurieren Sie MMA für den Server, um Sensordaten an Defender for Endpoint zu melden.
4. Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients.


> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob es ordnungsgemäß in den Dienst integrierte ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Endpunkt](run-detection-test.md).


#### <a name="before-you-begin"></a>Vorbereitung 
Führen Sie die folgenden Schritte aus, um die Onboardinganforderungen zu erfüllen:

 - Stellen Windows Server 2008 R2 SP1 oder Windows Server 2012 R2 sicher, dass Sie den folgenden Hotfix installieren:
    - [Update für Kundenerfahrung und Diagnosetelemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - Stellen Sie außerdem für Windows Server 2008 R2 SP1 sicher, dass Sie die folgenden Anforderungen erfüllen:
    - Installieren des monatlichen [Updaterollups vom Februar](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
    - Installieren von [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) oder [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

 - Für Windows Server 2008 R2 SP1 und Windows Server 2012 R2: Konfigurieren und Aktualisieren [von System Center Endpoint Protection-Clients](#configure-and-update-system-center-endpoint-protection-clients).

    > [!NOTE]
    > Dieser Schritt ist nur erforderlich, wenn Ihre Organisation System Center Endpoint Protection (SCEP) verwendet und Sie Windows Server 2008 R2 SP1 und Windows Server 2012 R2 integrieren.


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installieren und Konfigurieren von Microsoft Monitoring Agent (MMA) zum Melden von Sensordaten an Microsoft Defender for Endpoint

1. Laden Sie die Agent-Setupdatei herunter: [Windows 64-Bit-Agent](https://go.microsoft.com/fwlink/?LinkId=828603).

2. Wählen Sie mithilfe der im vorherigen Verfahren ermittelten Arbeitsbereichs-ID und des Workspace-Schlüssels eine der folgenden Installationsmethoden aus, um den Agent auf dem Windows-Server zu installieren:
    - [Installieren Sie den Agent manuell mithilfe von Setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
    Wählen Sie auf der Seite **Agent-Setupoptionen** die Option **Agent mit Azure Log Analytics (OMS) verbinden aus.**
    - [Installieren Sie den Agent über die Befehlszeile](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Konfigurieren Sie den Agent mithilfe eines Skripts.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

> [!NOTE]
> Wenn Sie ein [Us Government-Kunde](gov.md)sind, müssen Sie unter "Azure Cloud" "Azure US Government" auswählen, wenn Sie den Setup-Assistenten verwenden oder wenn Sie eine Befehlszeile oder ein Skript verwenden – legen Sie den Parameter "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" auf 1.


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>Konfigurieren von Einstellungen für Windows-Serverproxy und Internetkonnektivität bei Bedarf
Wenn Ihre Server einen Proxy für die Kommunikation mit Defender for Endpoint verwenden müssen, verwenden Sie eine der folgenden Methoden, um das MMA für die Verwendung des Proxyservers zu konfigurieren:


- [Konfigurieren der MMA für die Verwendung eines Proxyservers](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Konfigurieren von Windows für die Verwendung eines Proxyservers für alle Verbindungen](configure-proxy-internet.md)

Wenn ein Proxy oder eine Firewall verwendet wird, stellen Sie sicher, dass Server direkt und ohne SSL-Abfangen auf alle URLs des Microsoft Defender for Endpoint-Diensts zugreifen können. Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Defender for Endpoint-Dienst-URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server). Die Verwendung des SSL-Abfangs verhindert, dass das System mit dem Defender for Endpoint-Dienst kommuniziert. 

Sobald sie abgeschlossen sind, sollten integrierte Windows-Server innerhalb einer Stunde im Portal angezeigt werden.

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>Option 2: Onboarding von Windows-Servern über Azure Security Center
1. Wählen Sie im Navigationsbereich des Microsoft Defender Security Center die Option **Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding aus.**

2. Wählen **Windows Server 2008 R2 SP1, 2012 R2 und 2016** als Betriebssystem aus.

3. Klicken **Sie im Azure Security Center auf Onboard-Server**.

4. Befolgen Sie die Anweisungen zum Onboarding in [Microsoft Defender for Endpoint mit Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).

Nach Abschluss der Onboardingschritte müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
> - Damit das Onboarding über Azure Defender for Servers (zuvor Azure Security Center Standard Edition) wie erwartet funktioniert, muss der Server über einen geeigneten Arbeitsbereich und Schlüssel verfügen, der in den Einstellungen des Microsoft Monitoring Agent (MMA) konfiguriert ist.
> - Nach der Konfiguration wird das entsprechende Cloud Management Pack auf dem Computer bereitgestellt, und der Sensorprozess (MsSenseS.exe) wird bereitgestellt und gestartet. 
> - Dies ist auch erforderlich, wenn der Server für die Verwendung eines OMS-Gatewayservers als Proxy konfiguriert ist.

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>Option 3: Onboarding von Windows-Servern über Microsoft Endpoint Manager, Version 2002 und höher
Sie können Windows Server 2012 R2 und Windows Server 2016 mithilfe von Microsoft Endpoint Manager, Version 2002 und höher, integrieren. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).

Nach Abschluss der Onboardingschritte müssen Sie System Center Endpoint Protection-Clients konfigurieren und [aktualisieren.](#configure-and-update-system-center-endpoint-protection-clients)

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a>Windows Server (SAC) Version 1803, Windows Server 2019 und Windows Server 2019 Core Edition
Sie können Windows Server (SAC) Version 1803, Windows Server 2019 oder Windows Server 2019 Core edition mithilfe der folgenden Bereitstellungsmethoden integrieren:

- [Lokales Skript](configure-endpoints-script.md) 
- [Gruppenrichtlinie](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [VDI-Onboardingskripts für nicht persistente Geräte](configure-endpoints-vdi.md)

> [!NOTE]
> - Das Onboardingpaket für Windows Server 2019 über Microsoft Endpoint Manager enthält derzeit ein Skript. Weitere Informationen zum Bereitstellen von [Skripts](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)in Configuration Manager finden Sie unter Pakete und Programme in Configuration Manager .
> - Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien oder Microsoft Endpoint Configuration Manager empfohlen.

Die Unterstützung für Windows Server bietet tiefere Einblicke in Serveraktivitäten, die Abdeckung der Kernel- und Speicherangriffserkennung und ermöglicht Reaktionsaktionen.

1. Konfigurieren Sie die Einstellungen für das Defender for Endpoint-Onboarding auf dem Windows-Server mit den gleichen Tools und Methoden für Windows 10-Geräte. Weitere Informationen finden Sie unter [Onboarding von Windows 10-Geräten](configure-endpoints.md).

2. Wenn Sie eine Antischalwarelösung eines Drittanbieters ausführen, müssen Sie die folgenden Einstellungen für den passiven Microsoft Defender AV-Modus anwenden. Stellen Sie sicher, dass sie ordnungsgemäß konfiguriert wurde:

    1. Legen Sie den folgenden Registrierungseintrag ein:
       - Pfad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - Name: ForceDefenderPassiveMode
       - Typ: REG_DWORD
       - Value: 1

    1. Führen Sie den folgenden PowerShell-Befehl aus, um zu überprüfen, ob der passive Modus konfiguriert wurde:

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. Vergewissern Sie sich, dass ein aktuelles Ereignis gefunden wurde, das das Passive Mode-Ereignis enthält:

       ![Abbildung des Überprüfungsergebniss für den passiven Modus](images/atp-verify-passive-mode.png)

3. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob Microsoft Defender AV installiert ist:

   ```sc.exe query Windefend```

    Wenn das Ergebnis "Der angegebene Dienst ist nicht als installierter Dienst vorhanden" ist, müssen Sie Microsoft Defender AV installieren. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).
    
    Informationen zur Verwendung von Gruppenrichtlinien zum Konfigurieren und Verwalten von Microsoft Defender Antivirus auf Ihren Windows-Servern finden Sie unter Verwenden von Gruppenrichtlinieneinstellungen zum Konfigurieren und Verwalten [von Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).

<br>

## <a name="integration-with-azure-security-center"></a>Integration in Azure Security Center
Defender for Endpoint kann in Azure Security Center integriert werden, um eine umfassende Windows-Serverschutzlösung zu bieten. Mit dieser Integration kann Azure Security Center die Leistung von Defender for Endpoint nutzen, um eine verbesserte Bedrohungserkennung für Windows-Server zu ermöglichen.

Die folgenden Funktionen sind in dieser Integration enthalten:
- Automatisiertes Onboarding – Der Defender for Endpoint-Sensor wird automatisch auf Windows-Servern aktiviert, die in Azure Security Center onboarded sind. Weitere Informationen zum Azure Security Center-Onboarding finden Sie [unter Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).

    > [!NOTE]
    > Automatisiertes Onboarding gilt nur für Windows Server 2008 R2 SP1, Windows Server 2012 R2 und Windows Server 2016.

- Windows-Server, die vom Azure Security Center überwacht werden, stehen auch in Defender for Endpoint zur Verfügung – Azure Security Center stellt nahtlos eine Verbindung mit dem Defender for Endpoint-Mandanten her und bietet eine einheitliche Ansicht über Clients und Server hinweg.  Darüber hinaus stehen Defender for Endpoint-Warnungen in der Azure Security Center-Konsole zur Verfügung.
- Serveruntersuchung – Azure Security Center-Kunden können auf Microsoft Defender Security Center zugreifen, um eine detaillierte Untersuchung durchzuführen, um den Umfang einer potenziellen Verletzung aufzudecken.

> [!IMPORTANT]
> - Wenn Sie Azure Security Center zum Überwachen von Servern verwenden, wird automatisch ein Defender for Endpoint-Mandant erstellt (in den USA für US-Benutzer, in der EU für europäische und britische Benutzer).<br>
Von Defender for Endpoint erfasste Daten werden am geografischen Standort des Mandanten gespeichert, der während der Bereitstellung identifiziert wird.
> - Wenn Sie Defender for Endpoint vor der Verwendung von Azure Security Center verwenden, werden Ihre Daten an dem Ort gespeichert, den Sie beim Erstellen Ihres Mandanten angegeben haben, auch wenn Sie zu einem späteren Zeitpunkt in Azure Security Center integriert werden.
> - Nach der Konfiguration können Sie den Speicherort ihrer Daten nicht mehr ändern. Wenn Sie Ihre Daten an einen anderen Speicherort verschieben müssen, müssen Sie den Microsoft Support kontaktieren, um den Mandanten zurückzusetzen. <br>
Die Serverendpunktüberwachung, die diese Integration nutzt, wurde für Office 365 GCC-Kunden deaktiviert.

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Konfigurieren und Aktualisieren von System Center Endpoint Protection-Clients

Defender for Endpoint ist in System Center Endpoint Protection integriert. Die Integration bietet Sichtbarkeit für Schadsoftwareerkennungen und zum Beenden der Verbreitung eines Angriffs in Ihrer Organisation, indem potenziell schädliche Dateien oder mutmaßliche Schadsoftware verboten werden.

Die folgenden Schritte sind erforderlich, um diese Integration zu aktivieren:
- Installieren Sie [das Anti-Malware-Plattformupdate vom Januar 2017 für Endpoint Protection-Clients.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)

- [Konfigurieren Sie die ScEP-Client-Cloud Protection Service-Mitgliedschaft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) auf die **Einstellung Erweitert.**

<br>

## <a name="offboard-windows-servers"></a>Offboard-Windows-Server
Sie können Windows Server (SAC), Windows Server 2019 und Windows Server 2019 Core Edition mit derselben Methode ausschalten, die für Windows 10-Clientgeräte verfügbar ist.

Für andere Windows-Serverversionen stehen Ihnen zwei Optionen zur Offboardung von Windows-Servern vom Dienst zur Verfügung:
- Deinstallieren des MMA-Agents
- Entfernen der Konfiguration des Defender for Endpoint-Arbeitsbereichs

> [!NOTE]
> Offboarding bewirkt, dass der Windows-Server das Senden von Sensordaten an das Portal beendet, aber Daten vom Windows-Server, einschließlich Verweis auf alle Warnungen, die er erhalten hat, werden für bis zu 6 Monate aufbewahrt.

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>Deinstallieren von Windows-Servern durch Deinstallieren des MMA-Agents
Zum Offboarden des Windows-Servers können Sie den MMA-Agent vom Windows-Server deinstallieren oder von der Berichterstellung an Ihren Defender for Endpoint-Arbeitsbereich trennen. Nach dem Offboarding des Agents sendet der Windows-Server keine Sensordaten mehr an Defender for Endpoint.
Weitere Informationen finden Sie unter [So deaktivieren Sie einen Agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Entfernen der Konfiguration des Defender for Endpoint-Arbeitsbereichs
Zum Offboarden des Windows-Servers können Sie eine der folgenden Methoden verwenden:

- Entfernen der Defender for Endpoint-Arbeitsbereichskonfiguration aus dem MMA-Agent
- Ausführen eines PowerShell-Befehls zum Entfernen der Konfiguration

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>Entfernen der Defender for Endpoint-Arbeitsbereichskonfiguration aus dem MMA-Agent

1. Wählen Sie **auf der Registerkarte Microsoft Monitoring Agent Properties** die Registerkarte Azure Log Analytics **(OMS)** aus.

2. Wählen Sie den Arbeitsbereich Defender für Endpunkt aus, und klicken Sie auf **Entfernen**.

    ![Abbildung der Microsoft Monitoring Agent-Eigenschaften](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Ausführen eines PowerShell-Befehls zum Entfernen der Konfiguration

1. Ihre Arbeitsbereichs-ID erhalten:

   1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**

   1. Wählen **Windows Server 2008 R2 SP1, 2012 R2 und 2016** als Betriebssystem aus, und erhalten Sie Ihre Arbeitsbereichs-ID:

      ![Abbildung des Onboardings von Windows-Servern](images/atp-server-offboarding-workspaceid.png)

2. Öffnen Sie eine PowerShell mit erhöhten Rechten, und führen Sie den folgenden Befehl aus. Verwenden Sie die arbeitsbereichs-ID, die Sie erhalten haben, und ersetzen `WorkspaceID` Sie:

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Onboarding von Nicht-Windows-Geräten](configure-endpoints-non-windows.md)
- [Konfigurieren von Proxy- und Internetverbindungseinstellungen](configure-proxy-internet.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Defender for Endpoint-Gerät](run-detection-test.md)
- [Beheben von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
