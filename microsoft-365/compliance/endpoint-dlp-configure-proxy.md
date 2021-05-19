---
title: Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Erfahren Sie Näheres über das Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt (Data Loss Prevention, DLP).
ms.openlocfilehash: f2a62b5c7913b6f41c414310a97ab5f072f59642
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538615"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a>Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt

Microsoft Endpunkt-DLP stützt sich auf Microsoft Windows-HTTP (WinHTTP) für die Datenmeldung und um mit dem Microsoft Endpunkt-Clouddienst zu kommunizieren. Das eingebettete Endpunkt-DLP-Feature wird im Systemkontext unter Verwendung des LocalSystem-Kontos ausgeführt.

> [!TIP]
> Organisationen, die Weiterleitungsproxys als Gateway zum Internet verwenden, können mithilfe des Netzwerkschutzes Untersuchungen hinter einem Proxy durchführen. Weitere Informationen finden Sie unter [Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).

Die WinHTTP-Konfigurationseinstellung ist unabhängig von den Proxyeinstellungen von Windows Internet (WinINet) für das Browsen im Internet und kann einen Proxyserver nur mithilfe der folgenden Methoden der automatischen Ermittlung erkennen:

- Transparenter Proxy
- Web Proxy Auto-Discovery Protocol (WPAD)

> [!NOTE]
> Wenn Sie in Ihrer Netzwerktopologie einen transparenten Proxy oder WPAD verwenden, sind keine speziellen Konfigurationseinstellungen erforderlich. Weitere Informationen zu Defender für Endpunkt-URL-Ausschlüssen im Proxy finden Sie unter [Aktivieren des Zugriffs auf Endpunkt-DLP-Clouddienst-URLs im Proxy Server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).

- Manuelle Konfiguration von statischen Proxys:
    - Registrierungsbasierte Konfiguration
    - WinHTTP-Konfiguration mithilfe des netsh-Befehls: nur für Desktops in einer stabilen Topologie geeignet (beispielsweise ein Desktop in einem Unternehmensnetzwerk hinter demselben Proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Manuelles Konfigurieren des Proxyservers mithilfe eines registrierungsbasierten statischen Proxys

Bei Endpunktgeräten, für die keine Verbindung mit dem Internet zulässig ist, müssen Sie einen registrierungsbasierten statischen Proxy konfigurieren. Sie müssen diesen so konfigurieren, dass nur Microsoft Endpunkt-DLP Diagnosedaten melden und mit dem Microsoft Endpunkt-Clouddienst kommunizieren kann.

Der statische Proxy kann mithilfe von Gruppenrichtlinien konfiguriert werden. Die Gruppenrichtlinien finden Sie unter:

1. Öffnen Sie **Administrative Vorlagen > Windows-Komponenten > Datensammlung und Vorabversionen > Verwendung authentifizierter Proxys für den Dienst "Benutzererfahrung und Telemetrie im verbundenen Modus" konfigurieren**.

2. Legen Sie dies auf **Aktiviert** fest, und wählen Sie **Verwendung von authentifiziertem Proxy deaktivieren**: 

![Abbildung der Gruppenrichtlinieneinstellungen 1](../media/atp-gpo-proxy1.png)
 
3. Öffnen Sie **Administrative Vorlagen > Windows-Komponenten > Datensammlung und Vorabversionen > Benutzererfahrung und Telemetrie im verbundenen Modus konfigurieren**:

 Konfigurieren des Proxys

![Abbildung der Gruppenrichtlinieneinstellungen 2](../media/atp-gpo-proxy2.png)

Die Richtlinie setzt zwei Registrierungswerte (`TelemetryProxyServer` als "REG_SZ&quot; und `DisableEnterpriseAuthProxy` als &quot;REG_DWORD") unter dem Registrierungsschlüssel `HKLM\Software\Policies\Microsoft\Windows\DataCollection` fest.

Der TelemetryProxyServer-Registrierungswert weist dieses Format auf: \<server name or ip\>:\<port\>. Beispiel: **10.0.0.6:8080**.

Der Registrierungswert `DisableEnterpriseAuthProxy` sollte auf 1 festgelegt werden.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Manuelles Konfigurieren des Proxyservers mithilfe des netsh-Befehls

Verwenden Sie den netsh-Befehl, um einen systemweiten statischen Proxy zu konfigurieren.

> [!NOTE]
> Dies wirkt sich auf alle Anwendungen aus, einschließlich Windows-Diensten, die WinHTTP mit Standardproxy verwenden. - Laptops, die Topologie wechseln (z. B. vom Büro nach Hause), funktionieren mit netsh nicht ordnungsgemäß. Verwenden Sie die registrierungsbasierte Konfiguration für statische Proxys.

1. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:
    1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.
    1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.
2.  Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

    `netsh winhttp set proxy <proxy>:<port>`

    Beispiel: **netsh winhttp set proxy 10.0.0.6:8080**

3. Wenn Sie den WinHTTP-Proxy zurücksetzen möchten, geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:

     `netsh winhttp reset proxy`

Weitere Informationen hierzu finden Sie unter [netsh-Befehl: Syntax, Kontexte und Formatierung](/windows-server/networking/technologies/netsh/netsh-contexts).


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a>Aktivieren des Zugriffs auf Endpunkt-DLP-Clouddienst-URLs im Proxy Server

Wenn ein Proxy oder eine Firewall den gesamten Datenverkehr standardmäßig blockiert und nur bestimmte Domänen durchlässt, fügen Sie die im herunterladbaren Blatt aufgeführten Domänen der Liste der zulässigen Domänen hinzu.

Diese [herunterladbare Kalkulationstabelle](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) enthält die Dienste und die zugehörigen URLs, mit denen Ihr Netzwerk sich verbinden können muss. Sie sollten sicherstellen, dass keine Firewall- oder Netzwerkfilterregeln den Zugriff auf diese URLs verhindern. Andernfalls müssen Sie eine eigene Zulassungsregel dafür erstellen.

Wenn bei einem Proxy oder einer Firewall die HTTPS-Überprüfung aktiviert ist (SSL-Inspektion), schließen Sie die in der obigen Tabelle aufgeführten Domänen von der HTTPS-Überprüfung aus.
Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass für die zuvor aufgeführten URLs anonymer Datenverkehr zulässig ist (Endpunkt-DLP stellt eine Verbindung vom Systemkontext aus her).

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a>Überprüfen der Clientkonnektivität mit Microsoft-Clouddienst-URLs

Vergewissern Sie sich, dass die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP ermitteln und über den Proxyserver in Ihrer Umgebung kommunizieren kann und dass der Proxyserver Datenverkehr zu Defender für Endpunkt-Dienst-URLs zulässt.

1. Laden Sie das Tool [MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) auf den PC herunter, auf dem Endpunkt-DLP ausgeführt wird.
2. Extrahieren Sie den Inhalt von MDATPClientAnalyzer.zip auf dem Gerät.
3. Öffnen Sie eine Befehlszeile mit erhöhten Rechten:
    1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.
    1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.
4.  Geben Sie den folgenden Befehl ein, und drücken Sie dann die **Eingabetaste**:
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

Ersetzen Sie *HardDrivePath* durch den Pfad, in den das MDATPClientAnalyzer-Tool heruntergeladen wurde (z. B.
    
**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**).


5.  Extrahieren Sie die Datei **MDATPClientAnalyzerResult.zip** _, die von dem Tool in dem Ordner erstellt wurde, der in _HardDrivePath* verwendet wird.

6.  Öffnen Sie **MDATPClientAnalyzerResult.txt**, und vergewissern Sie sich, dass Sie die Schritte zur Proxykonfiguration durchgeführt haben, um die Serverermittlung und den Zugriff auf die Dienst-URLs zu aktivieren.  Das Tool überprüft die Konnektivität von Defender für Endpunkt-Dienst-URLs, mit denen der Defender für Endpunkt-Client laut Konfiguration interagieren kann. Anschließend werden die Ergebnisse für jede URL, die potentiell für die Kommunikation mit den Defender für Endpunkt-Diensten verwendet werden kann, in die Datei **MDATPClientAnalyzerResult.txt** gedruckt. Beispiel:

    **Getestete URL: https://xxx.microsoft.com/xxx </br> 1 - Standardproxy: Succeeded (200) </br> 2 - Proxy auto-discovery (WPAD): Succeeded (200)</br> 3 - Proxy deaktiviert: Succeeded (200)</br> 4 - Named proxy: Existiert nicht</br> 5 - Befehlszeilenproxy: Existiert nicht**</br>


Wenn mindestens eine der Verbindungsoptionen einen (200)-Status zurückgibt, kann der Defender für Endpunkt-Client über diese Verbindungsmethode ordnungsgemäß mit der getesteten URL kommunizieren. 

Wenn die Ergebnisse der Verbindungsüberprüfung hingegen auf einen Fehler hindeuten, wird ein HTTP-Fehler angezeigt (siehe HTTP-Status-Codes). Sie können dann die URLs in der Tabelle unter [Aktivieren des Zugriffs auf Endpunkt-DLP-Clouddienst-URLs im Proxy Server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server) verwenden. Welche URLs Sie verwenden werden, ist von der Region abhängig, die während des Onboarding-Vorgangs ausgewählt wurde.
[!NOTE] Das Tool für die Verbindungsanalyse ist nicht kompatibel mit der ASR-Regel [Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Sie müssen diese Regel vorübergehend deaktivieren, um das Verbindungstool auszuführen.

[!NOTE] Wenn der TelemetryProxyServer in der Registrierung oder über eine Gruppenrichtlinie festgelegt ist, wird Defender für Endpunkt auf "Direct" zurückgreifen, wenn der Zugriff auf den definierten Proxy nicht möglich ist.
Verwandte Themen • Onboarding von Windows 10-Geräten • Microsoft Endpunkt-DLP: Onboarding-Probleme behandeln





## <a name="see-also"></a>Siehe auch

- [Informationen zur Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-learn-about.md)
- [Verwenden der Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-using.md)
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender für Endpunkt](/windows/security/threat-protection/)
- [Onboarding-Tools und -Methoden für Windows 10-Computer](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD-verbundene Geräte](/azure/active-directory/devices/concept-azure-ad-join)
- [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)