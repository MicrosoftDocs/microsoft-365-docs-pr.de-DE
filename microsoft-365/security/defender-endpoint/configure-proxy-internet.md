---
title: Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen
description: Konfigurieren Sie den Microsoft Defender for Endpoint-Proxy und die Interneteinstellungen, um die Kommunikation mit dem Clouddienst zu ermöglichen.
keywords: configure, proxy, internet, internet connectivity, settings, proxy settings, netsh, winhttp, proxy server
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8f25b924109823951c331fe744b548d372eaf11
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957617"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Für den Defender for Endpoint-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Defender for Endpoint-Dienst kommunizieren.

Der eingebettete Defender for Endpoint-Sensor wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt. Der Sensor verwendet Microsoft Windows HTTP Services (WinHTTP), um die Kommunikation mit dem Defender for Endpoint-Clouddienst zu ermöglichen.

>[!TIP]
>Organisationen, die Weiterleitungsproxys als Gateway zum Internet verwenden, können mithilfe des Netzwerkschutzes Untersuchungen hinter einem Proxy durchführen. Weitere Informationen finden Sie unter [Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys](investigate-behind-proxy.md).

Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Windows Internet (WinINet)-Internet-Browserproxyeinstellungen und kann nur mithilfe der folgenden Ermittlungsmethoden einen Proxyserver ermitteln:

- Methoden für die automatische Ermittlung:
  - Transparenter Proxy
  - Web Proxy Auto-Discovery Protocol (WPAD)

    > [!NOTE]
    > Wenn Sie transparenten Proxy oder WPAD in Ihrer Netzwerktopologie verwenden, benötigen Sie keine speziellen Konfigurationseinstellungen. Weitere Informationen zu Defender for Endpoint-URL-Ausschlüssen im Proxy finden Sie unter [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).

- Manuelle Konfiguration von statischen Proxys:
  - Registrierungsbasierte Konfiguration
  - WinHTTP-Konfiguration mithilfe des netsh-Befehls: nur für Desktops in einer stabilen Topologie geeignet (beispielsweise ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys

Konfigurieren Sie einen registrierungsbasierten statischen Proxy, damit nur defender for Endpoint-Sensor Diagnosedaten melden und mit Defender for Endpoint-Diensten kommunizieren kann, wenn ein Computer keine Verbindung mit dem Internet herstellen darf.

> [!NOTE]
> - Wenn Sie diese Option unter Windows 10 oder Windows Server 2019 verwenden, wird empfohlen, das folgende (oder höher) Build- und kumulative Updaterollup zu verwenden:</br>
> Windows 10, Version 1809 oder Windows Server 2019 – https://support.microsoft.com/kb/5001384 <br>
> Windows 10, Version 1909 – https://support.microsoft.com/kb/4601380</br>
> Windows 10, Version 2004 – https://support.microsoft.com/kb/4601382</br>
> Windows 10, Version 20H2 – https://support.microsoft.com/kb/4601382</br>
> Diese Updates verbessern die Konnektivität und Zuverlässigkeit des CnC(Command and Control)-Kanals.</br>

Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden. Die Gruppenrichtlinien finden Sie unter:

- Administrative Vorlagen > Windows-Komponenten > Datensammlungs- und Vorschaubuilds > Konfigurieren der authentifizierten Proxyverwendung für den verbundenen Benutzererfahrungs- und Telemetriedienst
  - Legen Sie es **auf Aktiviert,** und wählen **Sie Authentifizierte Proxyverwendung deaktivieren** aus: Abbildung der ![ Gruppenrichtlinieneinstellung1](images/atp-gpo-proxy1.png)
- **Administrative Vorlagen > Windows-Komponenten > Datensammlungs- und Vorschaubuilds**> Konfigurieren von verbundenen Benutzererfahrungen und Telemetrie :
  - Konfigurieren des Proxys:<br>
    ![Abbildung der Gruppenrichtlinieneinstellung2](images/atp-gpo-proxy2.png)

    Die Richtlinie setzt zwei Registrierungswerte (`TelemetryProxyServer` als "REG_SZ&quot; und `DisableEnterpriseAuthProxy` als &quot;REG_DWORD") unter dem Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.

    Der Registrierungswert `TelemetryProxyServer` hat das folgende Zeichenfolgenformat:

    ```text
    <server name or ip>:<port>
    ```

    Beispiel: 10.0.0.6:8080.

    Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Konfigurieren des Proxyservers manuell mithilfe des Befehls netsh

Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.

> [!NOTE]
> - Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</br>
> - Laptops, die die Topologie ändern (z. B. von Büro zu Haus) können mit netsh nicht mehr verwendet werden. Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.

1. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:

    a. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    b. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Beispiel: netsh winhttp set proxy 10.0.0.6:8080

Geben Sie zum Zurücksetzen des winhttp-Proxys den folgenden Befehl ein, und drücken Sie die **EINGABETASTE.**

```PowerShell
netsh winhttp reset proxy
```

Weitere Informationen hierzu finden Sie unter [netsh-Befehl: Syntax, Kontexte und Formatierung](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Aktivieren des Zugriffs auf Microsoft Defender for Endpoint-Dienst-URLs auf dem Proxyserver

Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann. Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den  Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.


|**Tabellenkalkulation der Domänenliste**|**Beschreibung**|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br><br>[Laden Sie die Tabelle hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


Wenn bei einem Proxy oder einer Firewall die HTTPS-Überprüfung aktiviert ist (SSL-Inspektion), schließen Sie die in der obigen Tabelle aufgeführten Domänen von der HTTPS-Überprüfung aus.

> [!NOTE]
> settings-win.data.microsoft.com ist nur erforderlich, wenn Windows 10-Geräte mit Version 1803 oder früher ausgeführt werden.<br>


> [!NOTE]
> URLs, die v20 enthalten, werden nur benötigt, wenn Windows 10-Geräte mit Version 1803 oder höher ausgeführt werden. Ist beispielsweise für ein Windows 10-Gerät mit Version 1803 oder höher erforderlich und in die ```us-v20.events.data.microsoft.com``` Region "US Data Storage" onboarded.


> [!NOTE]
> Wenn Sie Microsoft Defender Antivirus in Ihrer Umgebung verwenden, lesen Sie Konfigurieren von Netzwerkverbindungen [mit dem Microsoft Defender Antivirus-Clouddienst](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, da der Defender for Endpoint-Sensor eine Verbindung aus dem Systemkontext verbindet, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) – Proxy- und Firewallanforderungen für ältere Versionen von Windows Client oder Windows Server

In den folgenden Informationen sind die Proxy- und Firewallkonfigurationsinformationen aufgeführt, die für die Kommunikation mit dem Log Analytics-Agent (häufig als Microsoft Monitoring Agent bezeichnet) für die vorherigen Versionen von Windows wie Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 und Windows Server 2016 erforderlich sind.

|Agent-Ressource|Ports |Direction |Umgehen der HTTPS-Überprüfung|
|------|---------|--------|--------|   
|*.ods.opinsights.azure.com |Port 443 |Ausgehend|Ja |  
|*.oms.opinsights.azure.com |Port 443 |Ausgehend|Ja |  
|*.blob.core.windows.net |Port 443 |Ausgehend|Ja |
|*.azure-automation.net |Port 443 |Ausgehend|Ja |  


> [!NOTE]
> Als cloudbasierte Lösung kann sich der IP-Bereich ändern. Es wird empfohlen, zur Einstellung für die DNS-Auflösung zu wechseln.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Bestätigen der Microsoft Monitoring Agent (MMA)-Dienst-URL-Anforderungen 

Lesen Sie die folgenden Anleitungen, um die Platzhalter (*)-Anforderung für Ihre spezifische Umgebung zu beseitigen, wenn Sie den Microsoft Monitoring Agent (MMA) für frühere Versionen von Windows verwenden.

1.  Onboarding a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, [see Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).

2.  Stellen Sie sicher, dass der Computer erfolgreich über das Microsoft Defender Security Center-Portal berichtet.

3.  Führen Sie TestCloudConnection.exe "C:\Program Files\Microsoft Monitoring Agent\Agent" aus, um die Konnektivität zu überprüfen und die erforderlichen URLs für Ihren bestimmten Arbeitsbereich zu sehen.

4.  In der Liste der Microsoft Defender for Endpoint-URLs finden Sie die vollständige Liste der Anforderungen für Ihre Region (weitere Informationen finden Sie unter Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

![Abbildung des Administrators in Windows PowerShell](images/admin-powershell.png)

Die Platzhalter (*) in *.ods.opinsights.azure.com-, *.oms.opinsights.azure.com- und *.agentsvc.azure-automation.net-URL-Endpunkten können durch Ihre spezifische Arbeitsbereich-ID ersetzt werden. Die Workspace-ID ist spezifisch für Ihre Umgebung und Ihren Arbeitsbereich und ist im Abschnitt Onboarding Ihres Mandanten im Microsoft Defender Security Center-Portal zu finden.

Der *.blob.core.windows.net-URL-Endpunkt kann durch die URLs ersetzt werden, die im Abschnitt "Firewallregel: *.blob.core.windows.net" der Testergebnisse angezeigt werden. 

> [!NOTE]
> Im Falle des Onboardings über Azure Defender werden möglicherweise mehrere Arbeitsbereiche verwendet. Sie müssen das oben beschriebene TestCloudConnection.exe auf einem integrierten Computer aus jedem Arbeitsbereich ausführen (um zu ermitteln, ob änderungen an den URLs *.blob.core.windows.net zwischen den Arbeitsbereichen vorhanden sind).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs

Vergewissern Sie sich, dass die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP ermitteln und über den Proxyserver in Ihrer Umgebung kommunizieren kann und dass der Proxyserver Datenverkehr zu Defender für Endpunkt-Dienst-URLs zulässt.

1. Laden Sie [das MDATP Client Analyzer-Tool](https://aka.ms/mdatpanalyzer) auf den PC herunter, auf dem der Defender for Endpoint-Sensor ausgeführt wird.

2. Extrahieren Sie den Inhalt von MDATPClientAnalyzer.zip auf dem Gerät.

3. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:

    a. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    b.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

4. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Ersetzen Sie *HardDrivePath* durch den Pfad, in den das MDATPClientAnalyzer-Tool heruntergeladen wurde (z. B.

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Extrahieren Sie *dieMDATPClientAnalyzerResult.zip,* die vom Tool im Ordner erstellt wurde, der in *HardDrivePath verwendet wird.*

6. Öffnen Sie *MDATPClientAnalyzerResult.txt*, und vergewissern Sie sich, dass Sie die Schritte zur Proxykonfiguration durchgeführt haben, um die Serverermittlung und den Zugriff auf die Dienst-URLs zu aktivieren. <br><br>
   Das Tool überprüft die Konnektivität von Defender für Endpunkt-Dienst-URLs, mit denen der Defender für Endpunkt-Client laut Konfiguration interagieren kann. Anschließend werden die Ergebnisse für jede URL, die potentiell für die Kommunikation mit den Defender für Endpunkt-Diensten verwendet werden kann, in die Datei *MDATPClientAnalyzerResult.txt* gedruckt. Beispiel:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Wenn mindestens eine der Verbindungsoptionen einen (200)-Status zurückgibt, kann der Defender für Endpunkt-Client über diese Verbindungsmethode ordnungsgemäß mit der getesteten URL kommunizieren. <br><br>

Wenn die Ergebnisse der Verbindungsüberprüfung hingegen auf einen Fehler hindeuten, wird ein HTTP-Fehler angezeigt (siehe HTTP-Status-Codes). Anschließend können Sie die URLs in der Tabelle unter Zugriff auf [Defender for Endpoint-Dienst-URLs auf dem Proxyserver aktivieren verwenden.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) Die verwendeten URLs hängen von der Region ab, die während des Onboardings ausgewählt wurde.

> [!NOTE]
>  Das Tool für die Verbindungsanalyse ist nicht kompatibel mit der ASR-Regel [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Sie müssen diese Regel vorübergehend deaktivieren, um das Verbindungstool auszuführen.


> [!NOTE]
> Wenn TelemetryProxyServer festgelegt ist, wird Defender for Endpoint in der Registrierung oder über Eine Gruppenrichtlinie auf "Direct" zurückfallen, wenn er nicht auf den definierten Proxy zugreifen kann.

## <a name="related-topics"></a>Verwandte Themen

- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
