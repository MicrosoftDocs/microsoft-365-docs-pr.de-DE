---
title: Konfigurieren von Einstellungen für Geräteproxy und Internetverbindung
description: Konfigurieren Sie die Proxy- und Interneteinstellungen von Microsoft Defender für Endpunkt, um die Kommunikation mit dem Clouddienst zu ermöglichen.
keywords: konfigurieren, Proxy, Internet, Internetverbindung, Einstellungen, Proxyeinstellungen, netsh, winhttp, Proxyserver
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
ms.openlocfilehash: 6a3bbc46bb5859743d5170451b0d1c68793f93bf
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338721"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Der Defender für Endpunkt-Sensor erfordert, dass Microsoft Windows HTTP (WinHTTP) Sensordaten meldet und mit dem Defender für Endpunkt-Dienst kommuniziert.

Der eingebettete Defender für Endpunkt-Sensor wird im Systemkontext mithilfe des LocalSystem-Kontos ausgeführt. Der Sensor verwendet Microsoft Windows HTTP Services (WinHTTP), um die Kommunikation mit dem Defender für Endpunkt-Clouddienst zu ermöglichen.

> [!TIP]
> Organisationen, die Weiterleitungsproxys als Gateway zum Internet verwenden, können mithilfe des Netzwerkschutzes Untersuchungen hinter einem Proxy durchführen. Weitere Informationen finden Sie unter [Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys](investigate-behind-proxy.md).

Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Browserproxyeinstellungen für Windows Internet (WinINet) und kann nur mithilfe der folgenden Ermittlungsmethoden einen Proxyserver ermitteln:

- Methoden für die automatische Ermittlung:

  - Transparenter Proxy

  - Web Proxy Auto-Discovery Protocol (WPAD)

    > [!NOTE]
    > Wenn Sie einen transparenten Proxy oder WPAD in Ihrer Netzwerktopologie verwenden, benötigen Sie keine speziellen Konfigurationseinstellungen. Weitere Informationen zu Defender für Endpunkt-URL-Ausschlüssen im Proxy finden Sie unter Aktivieren des [Zugriffs auf Defender für Endpunkt-Dienst-URLs auf dem Proxyserver.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- Manuelle Konfiguration von statischen Proxys:

  - Registrierungsbasierte Konfiguration

  - WinHTTP-Konfiguration mithilfe des netsh-Befehls: nur für Desktops in einer stabilen Topologie geeignet (beispielsweise ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys

Konfigurieren Sie einen registrierungsbasierten statischen Proxy, damit nur der Defender für Endpunkt-Sensor Diagnosedaten melden und mit Defender für Endpunkt-Diensten kommunizieren kann, wenn ein Computer keine Verbindung mit dem Internet herstellen darf.

> [!NOTE]
> Wenn Sie diese Option auf Windows 10 oder Windows Server 2019 verwenden, wird empfohlen, den folgenden (oder späteren) Build- und kumulativen Updaterollup zu verwenden:
>
> - Windows 10, Version 1809 oder Windows Server 2019 –https://support.microsoft.com/kb/5001384
> - Windows 10, Version 1909 –https://support.microsoft.com/kb/4601380
> - Windows 10, Version 2004 –https://support.microsoft.com/kb/4601382
> - Windows 10, Version 20H2 –https://support.microsoft.com/kb/4601382
>
> Diese Updates verbessern die Konnektivität und Zuverlässigkeit des CnC(Command and Control)-Kanals.

Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden. Die Gruppenrichtlinien finden Sie unter:

- **Administrative Vorlagen > Windows Komponenten > Datensammlungs- und Vorschaubuilds > Konfigurieren der Verwendung authentifizierter Proxys für den Dienst "Benutzererfahrung und Telemetrie im verbundenen Modus"**

  Legen Sie sie auf **"Aktiviert"** fest, und wählen Sie **"Authentifizierte Proxyverwendung deaktivieren"** aus.

  ![Abbildung der Gruppenrichtlinieneinstellung1](images/atp-gpo-proxy1.png)

- **Administrative Vorlagen > Windows Komponenten > Datensammlungs- und Vorschaubuilds > Konfigurieren verbundener Benutzeroberflächen und Telemetrie:**

  Konfigurieren des Proxys

  ![Abbildung der Gruppenrichtlinieneinstellung2](images/atp-gpo-proxy2.png)

  Die Richtlinie legt zwei Registrierungswerte `TelemetryProxyServer` als REG_SZ und als REG_DWORD unter dem `DisableEnterpriseAuthProxy` Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.

  Der Registrierungswert `TelemetryProxyServer` hat das folgende Zeichenfolgenformat:

  ```text
  <server name or ip>:<port>
  ```

  Beispiel: 10.0.0.6:8080.

  Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Manuelles Konfigurieren des Proxyservers mithilfe des netsh-Befehls

Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.

> [!NOTE]
>
> - Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden.</br>
> - Laptops, die die Topologie ändern (z. B. von Büro zu Zuhause), funktionieren nicht mit netsh. Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.

1. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:

   1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

   1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Beispiel: `netsh winhttp set proxy 10.0.0.6:8080`

Wenn Sie den WinHTTP-Proxy zurücksetzen möchten, geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

```PowerShell
netsh winhttp reset proxy
```

Weitere Informationen hierzu finden Sie unter [netsh-Befehl: Syntax, Kontexte und Formatierung](/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Aktivieren des Zugriffs auf Microsoft Defender für Endpunktdienst-URLs auf dem Proxyserver

Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

In der folgenden herunterladbaren Tabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit denen ihr Netzwerk eine Verbindung herstellen kann. Sie sollten sicherstellen, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine *spezielle Zulassungsregel* erstellen.

| Kalkulationstabelle der Domänenliste | Beschreibung |
|:-----|:-----|
|![Miniaturbild für Microsoft Defender für Endpunkt-URLs-Tabellenkalkulation](images/mdatp-urls.png)<br/>  | Kalkulationstabelle mit bestimmten DNS-Einträgen für Dienststandorte, geografische Standorte und Das Betriebssystem. <br><br>[Laden Sie das Arbeitsblatt hier herunter.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

Wenn bei einem Proxy oder einer Firewall die HTTPS-Überprüfung aktiviert ist (SSL-Inspektion), schließen Sie die in der obigen Tabelle aufgeführten Domänen von der HTTPS-Überprüfung aus.

> [!NOTE]
> settings-win.data.microsoft.com ist nur erforderlich, wenn Sie über Windows 10 Geräte verfügen, auf denen Version 1803 oder früher ausgeführt wird.<br>
>
> URLs, die v20 enthalten, sind nur erforderlich, wenn Sie über Windows 10 Geräte verfügen, auf denen Version 1803 oder höher ausgeführt wird. Wird beispielsweise für ein Windows 10 Gerät benötigt, auf `us-v20.events.data.microsoft.com` dem Version 1803 oder höher ausgeführt wird und das in die REGION "US Data Storage" integriert ist.
>
> Wenn Sie Microsoft Defender Antivirus in Ihrer Umgebung verwenden, finden Sie weitere Informationen unter [Konfigurieren von Netzwerkverbindungen mit dem Microsoft Defender Antivirus Clouddienst.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, da sich der Defender für Endpunkt-Sensor aus dem Systemkontext verbindet, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) – Proxy- und Firewallanforderungen für ältere Versionen von Windows Client oder Windows Server

Die folgenden Informationen enthalten die Proxy- und Firewallkonfigurationsinformationen, die für die Kommunikation mit dem Log Analytics-Agent (häufig als Microsoft Monitoring Agent bezeichnet) für die vorherigen Versionen von Windows wie Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 und Windows Server 2016 erforderlich sind.

|Agent-Ressource|Ports |Richtung |HTTPS-Inspektion umgehen|
|------|---------|--------|--------|
|*.ods.opinsights.azure.com |Port 443 |Ausgehend|Ja |  
|*.oms.opinsights.azure.com |Port 443 |Ausgehend|Ja |  
|*.blob.core.windows.net |Port 443 |Ausgehend|Ja |
|*.azure-automation.net |Port 443 |Ausgehend|Ja |  

> [!NOTE]
> Als cloudbasierte Lösung kann sich der IP-Bereich ändern. Es wird empfohlen, zur DNS-Auflösungseinstellung zu wechseln.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Bestätigen Microsoft Monitoring Agent (MMA)-Dienst-URL-Anforderungen 

Lesen Sie die folgenden Anleitungen, um die Platzhalter -(*)-Anforderung für Ihre spezifische Umgebung zu vermeiden, wenn Sie die Microsoft Monitoring Agent (MMA) für frühere Versionen von Windows verwenden.

1. Onboarding eines vorherigen Betriebssystems mit dem Microsoft Monitoring Agent (MMA) in Defender für Endpunkt (weitere Informationen finden Sie unter [Onboarding vorheriger Versionen von Windows auf Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2010326) und [Onboarding Windows Server.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)

2. Stellen Sie sicher, dass der Computer erfolgreich Berichte im Microsoft 365 Defender-Portal anmeldet.

3. Führen Sie das TestCloudConnection.exe-Tool unter "C:\Programme\Microsoft Monitoring Agent\Agent" aus, um die Konnektivität zu überprüfen und die erforderlichen URLs für Ihren spezifischen Arbeitsbereich anzuzeigen.

4. In der Microsoft Defender für Endpunkt-URLs-Liste finden Sie die vollständige Liste der Anforderungen für Ihre Region (siehe Tabelle mit dienstbasierten [URLs).](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

    ![Abbildung des Administrators in Windows PowerShell](images/admin-powershell.png)

Die \* in \* ODS.OPINSIGHTS.AZURE.COM-, \* OMS.OPINSIGHTS.AZURE.COM- und \* AGENTSVC.AZURE-AUTOMATION.NET-URL-Endpunkten verwendeten Platzhalter können durch Ihre spezifische Arbeitsbereichs-ID ersetzt werden. Die Arbeitsbereichs-ID ist für Ihre Umgebung und Ihren Arbeitsbereich spezifisch und befindet sich im Onboarding-Abschnitt Ihres Mandanten im Microsoft 365 Defender Portal.

Der \* BLOB.CORE.WINDOWS.NET-URL-Endpunkt kann durch die URLs ersetzt werden, die im Abschnitt "Firewallregel: \* .blob.core.windows.net" der Testergebnisse angezeigt werden.

> [!NOTE]
> Im Fall des Onboardings über Azure Defender werden möglicherweise mehrere Arbeitsbereiche verwendet. Sie müssen die oben beschriebene TestCloudConnection.exe-Prozedur auf einem integrierten Computer aus jedem Arbeitsbereich ausführen (um festzustellen, ob änderungen an den *.blob.core.windows.net-URLs zwischen den Arbeitsbereichen vorhanden sind).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Überprüfen der Clientkonnektivität mit Microsoft Defender für Endpunkt-Dienst-URLs

Vergewissern Sie sich, dass die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP ermitteln und über den Proxyserver in Ihrer Umgebung kommunizieren kann und dass der Proxyserver Datenverkehr zu Defender für Endpunkt-Dienst-URLs zulässt.

1. Laden Sie das [TOOL MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) auf den PC herunter, auf dem der Defender für Endpunkt-Sensor ausgeführt wird.

2. Extrahieren Sie den Inhalt von MDATPClientAnalyzer.zip auf dem Gerät.

3. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:

   1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

   1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

4. Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Ersetzen Sie *HardDrivePath* durch den Pfad, in den das MDATPClientAnalyzer-Tool heruntergeladen wurde, z. B.:

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Extrahieren Sie die vom Tool erstellte *MDATPClientAnalyzerResult.zipdatei* in den Ordner, der in *HardDrivePath* verwendet wird.

6. Öffnen Sie *MDATPClientAnalyzerResult.txt*, und vergewissern Sie sich, dass Sie die Schritte zur Proxykonfiguration durchgeführt haben, um die Serverermittlung und den Zugriff auf die Dienst-URLs zu aktivieren.

   Das Tool überprüft die Konnektivität von Defender für Endpunkt-Dienst-URLs, mit denen der Defender für Endpunkt-Client laut Konfiguration interagieren kann. Anschließend werden die Ergebnisse für jede URL, die potentiell für die Kommunikation mit den Defender für Endpunkt-Diensten verwendet werden kann, in die Datei *MDATPClientAnalyzerResult.txt* gedruckt. Beispiel:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Wenn mindestens eine der Verbindungsoptionen einen (200)-Status zurückgibt, kann der Defender für Endpunkt-Client über diese Verbindungsmethode ordnungsgemäß mit der getesteten URL kommunizieren.

Wenn die Ergebnisse der Verbindungsüberprüfung hingegen auf einen Fehler hindeuten, wird ein HTTP-Fehler angezeigt (siehe HTTP-Status-Codes). Sie können dann die URLs in der Tabelle unter Aktivieren des [Zugriffs auf Defender für Endpunkt-Dienst-URLs auf dem Proxyserver](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)verwenden. Welche URLs Sie verwenden werden, hängt von der Region ab, die während des Onboardings ausgewählt wurde.

> [!NOTE]
> Das Tool für die Verbindungsanalyse ist nicht kompatibel mit der ASR-Regel [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Sie müssen diese Regel vorübergehend deaktivieren, um das Verbindungstool auszuführen.
>
> Wenn der TelemetryProxyServer in der Registrierung oder über eine Gruppenrichtlinie festgelegt ist, greift Defender für Endpunkt auf direct zurück, wenn er nicht auf den definierten Proxy zugreifen kann.

## <a name="related-topics"></a>Verwandte Themen

- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
