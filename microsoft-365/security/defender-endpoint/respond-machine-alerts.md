---
title: Ausführen von Reaktionsaktionen auf einem Gerät in Microsoft Defender for Endpoint
description: Führen Sie Reaktionsaktionen auf einem Gerät aus, z. B. das Isolieren von Geräten, das Sammeln eines Untersuchungspakets, das Verwalten von Tags, das Ausführen von av Scan und das Einschränken der App-Ausführung.
keywords: reagieren, isolieren, isolieren Gerät, sammeln Untersuchungspaket, Aktionszentrum, beschränken, verwalten Tags, av Scan, beschränken App
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
ms.openlocfilehash: ae8b08ce3d5bcc34e91f031223108fca053348ce
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572393"
---
# <a name="take-response-actions-on-a-device"></a>Ergreifen von Reaktionen auf einem Gerät

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender for Endpoint erleben? [Melden Sie sich für eine kostenlose Testversion an.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-respondmachine-abovefoldlink) 

Schnelle Reaktion auf erkannte Angriffe durch Isolieren von Geräten oder Sammeln eines Untersuchungspakets. Nachdem Sie Aktionen auf Geräten ergriffen haben, können Sie die Aktivitätsdetails im Aktionscenter überprüfen.

Reaktionsaktionen werden oben auf einer bestimmten Geräteseite ausgeführt und umfassen Folgendes:

- Verwalten von Kategorien
- Initiieren einer automatisierten Untersuchung
- Initiieren von Live-Antwortsitzungen
- Untersuchungspaket sammeln
- Antivirusscan ausführen
- Einschränken der App-Ausführung
- Isolieren des Geräts
- Wenden Sie sich an einen Bedrohungsexperten
- Info-Center

[![Bild der Reaktionsaktionen ](images/response-actions.png)](images/response-actions.png#lightbox)

 Sie können Geräteseiten aus einer der folgenden Ansichten finden:

- **Sicherheitsoperations-Dashboard** – Wählen Sie einen Gerätenamen auf der Karte Geräte mit Risiko aus.
- **Warnungswarteschlange** – Wählen Sie den Gerätenamen neben dem Gerätesymbol aus der Warnungswarteschlange aus.
- **Geräteliste** - Wählen Sie die Überschrift des Gerätenamens aus der Geräteliste aus.
- **Suchfeld** - Wählen Sie Gerät aus dem Dropdown-Menü und geben Sie den Gerätenamen ein.

>[!IMPORTANT]
> - Diese Reaktionsaktionen sind nur für Geräte auf Windows 10 Version 1703 oder höher verfügbar. 
> - Bei Plattformen, die nicht Windows, sind Antwortfunktionen (z. B. Geräteisolation) von den Funktionen von Drittanbietern abhängig.

## <a name="manage-tags"></a>Verwalten von Kategorien

Hinzufügen oder Verwalten von Tags, um eine logische Gruppenzugehörigkeit zu erstellen. Geräte-Tags unterstützen eine ordnungsgemäße Zuordnung des Netzwerks, sodass Sie verschiedene Tags anfügen können, um den Kontext zu erfassen und die dynamische Listenerstellung als Teil eines Vorfalls zu ermöglichen.

Weitere Informationen zum Kennungsgerät finden Sie unter Erstellen und Verwalten von [Geräte-Tags](machine-tags.md).

## <a name="initiate-automated-investigation"></a>Initiieren einer automatisierten Untersuchung

Sie können bei Bedarf eine neue allgemeine automatisierte Untersuchung auf dem Gerät starten. Während eine Untersuchung ausgeführt wird, wird jede andere vom Gerät generierte Warnung einer laufenden automatisierten Untersuchung hinzugefügt, bis diese Untersuchung abgeschlossen ist. Wenn die gleiche Bedrohung auf anderen Geräten angezeigt wird, werden diese Geräte der Untersuchung hinzugefügt.

Weitere Informationen zu automatisierten Untersuchungen finden Sie unter [Übersicht über automatisierte Untersuchungen](automated-investigations.md).

## <a name="initiate-live-response-session"></a>Initiieren von Live-Antwortsitzungen

Live-Antwort ist eine Funktion, die Ihnen sofortigen Zugriff auf ein Gerät über eine Remote-Shell-Verbindung ermöglicht. Dies gibt Ihnen die Möglichkeit, eingehende Ermittlungsarbeit zu leisten und sofortige Reaktionsmaßnahmen zu ergreifen, um identifizierte Bedrohungen – in Echtzeit – schnell einzudämmen.

Live-Antwort wurde entwickelt, um Untersuchungen zu verbessern, indem Sie forensische Daten sammeln, Skripte ausführen, verdächtige Entitäten zur Analyse senden, Bedrohungen beheben und proaktiv nach neu auftretenden Bedrohungen suchen können.

Weitere Informationen zur Live-Antwort finden Sie unter Untersuchen von [Entitäten auf Geräten, die Live-Antwort](live-response.md)verwenden.

## <a name="collect-investigation-package-from-devices"></a>Sammeln von Untersuchungspaketen von Geräten

Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät sammeln. Durch das Sammeln des Untersuchungspakets können Sie den aktuellen Status des Geräts identifizieren und die vom Angreifer verwendeten Tools und Techniken weiter verstehen.

So laden Sie das Paket herunter (Zip-Datei) und untersuchen die Ereignisse, die auf einem Gerät aufgetreten sind

1. Wählen Sie **Untersuchungspaket** sammeln aus der Zeile der Antwortaktionen oben auf der Geräteseite aus.
2. Geben Sie im Textfeld an, warum Sie diese Aktion ausführen möchten. Wählen Sie **Bestätigen** aus.
3. Die ZIP-Datei wird heruntergeladen

Alternativer Weg:

1. Wählen Sie **Aktionscenter** aus dem Abschnitt Reaktionsaktionen auf der Geräteseite aus.

    ![Bild der ActionCenter-Schaltfläche](images/action-center-package-collection.png)

3. Wählen Sie im Flyout des Aktionszentrums **paketpaket** aus, das zum Herunterladen der ZIP-Datei verfügbar ist.
  
    ![Bild des Download-Paket-Buttons](images/collect-package.png)

Das Paket enthält die folgenden Ordner:

| Ordner | Beschreibung |
|:---|:---------|
|Autoruns | Enthält eine Reihe von Dateien, die jeweils den Inhalt der Registrierung eines bekannten automatischen Starteingangspunkts (ASEP) darstellen, um die Persistenz des Angreifers auf dem Gerät zu identifizieren. </br></br> <div class="alert"><b>HINWEIS:</b> Wenn der Registrierungsschlüssel nicht gefunden wird, enthält die Datei die folgende Meldung: "FEHLER: Das System konnte den angegebenen Registrierungsschlüssel oder -wert nicht finden."</div>                                                                                                                                |
|Installierte Programme | Diese .CSV Datei enthält die Liste der installierten Programme, die helfen können, zu identifizieren, was derzeit auf dem Gerät installiert ist. Weitere Informationen finden Sie unter [Win32_Product Klasse](https://go.microsoft.com/fwlink/?linkid=841509).                                                                                  |
|Netzwerkverbindungen | Dieser Ordner enthält eine Reihe von Datenpunkten im Zusammenhang mit den Konnektivitätsinformationen, die bei der Identifizierung der Verbindung zu verdächtigen URLs, der Befehls- und Steuerungsinfrastruktur des Angreifers (C&C), jeder seitlichen Bewegung oder Remoteverbindungen hilfreich sein können.</br></br> - ActiveNetConnections.txt – Zeigt Protokollstatistiken und aktuelle TCP/IP-Netzwerkverbindungen an. Bietet die Möglichkeit, nach verdächtigen Verbindungen zu suchen, die von einem Prozess hergestellt werden. </br></br> - Arp.txt – Zeigt die aktuellen ARP-Cachetabellen (Address Resolution Protocol) für alle Schnittstellen an. </br></br> Der ARP-Cache kann zusätzliche Hosts in einem Netzwerk anzeigen, die kompromittiert wurden oder verdächtige Systeme im Netzwerk, die möglicherweise zum Ausführen eines internen Angriffs verwendet wurden.</br></br> - DnsCache.txt - Zeigt den Inhalt des DNS-Client-Resolver-Cache an, der sowohl Einträge enthält, die aus der lokalen Hosts-Datei vorinstalliert wurden, als auch alle kürzlich abgerufenen Ressourceneinträge für Namensabfragen, die vom Computer gelöst wurden. Dies kann helfen, verdächtige Verbindungen zu identifizieren. </br></br> - IpConfig.txt – Zeigt die vollständige TCP/IP-Konfiguration für alle Adapter an. Adapter können physische Schnittstellen darstellen, z. B. installierte Netzwerkadapter oder logische Schnittstellen, z. B. DFÜ-Verbindungen. </br></br> - FirewallExecutionLog.txt und Pfirewall.log                                                                                  |
| Prefetch-Dateien| Windows Prefetch-Dateien wurden entwickelt, um den Startvorgang der Anwendung zu beschleunigen. Es kann verwendet werden, um alle Dateien zu verfolgen, die kürzlich im System verwendet wurden, und Nachverfolgungen für Anwendungen zu finden, die möglicherweise gelöscht wurden, aber immer noch in der Liste der Prefetch-Dateien gefunden werden können. </br></br> - Prefetch-Ordner – Enthält eine Kopie der Prefetch-Dateien aus `%SystemRoot%\Prefetch` . HINWEIS: Es wird empfohlen, einen Prefetch-Dateibetrachter herunterzuladen, um die Prefetch-Dateien anzuzeigen. </br></br> - PrefetchFilesList.txt – Enthält die Liste aller kopierten Dateien, die verwendet werden können, um nachzuverfolgen, wenn es Kopierfehler in den Prefetch-Ordner gab.                                                                                                      |
| Prozesse| Enthält eine .CSV Datei, in der die ausgeführten Prozesse aufgeführt sind, die die Möglichkeit bietet, aktuelle Prozesse zu identifizieren, die auf dem Gerät ausgeführt werden. Dies kann nützlich sein, wenn Sie einen verdächtigen Prozess und seinen Status identifizieren.                                                                                                                                                                                                       |
| Geplante Aufgaben| Enthält eine .CSV Datei mit den geplanten Aufgaben, die verwendet werden können, um automatisch auf einem ausgewählten Gerät ausgeführte Routinen zu identifizieren, um nach verdächtigem Code zu suchen, der so eingestellt wurde, dass er automatisch ausgeführt wird.                                                                                                                                                                                                      |
| Sicherheitsereignisprotokoll| Enthält das Sicherheitsereignisprotokoll, das Datensätze über Anmelde- oder Abmeldeaktivitäten oder andere sicherheitsbezogene Ereignisse enthält, die in der Überwachungsrichtlinie des Systems angegeben sind. </br></br><div class="alert"><b>HINWEIS:</b> Öffnen Sie die Ereignisprotokolldatei mit der Ereignisanzeige.</div>                                                                                    |
| Dienste| Enthält eine .CSV Datei, in der Dienste und deren Zustände aufgeführt sind.                                                                                      |
| Windows SMB-Sitzungen (Server Message Block) | Listet den gemeinsamen Zugriff auf Dateien, Drucker und serielle Ports sowie die sonstige Kommunikation zwischen Knoten in einem Netzwerk auf. Dies kann helfen, Datenexfiltration oder seitliche Bewegung zu identifizieren. </br></br> Enthält Dateien für SMBInboundSessions und SMBOutboundSession. </br></br> <div class="alert"><b>HINWEIS:</b> Wenn keine Sitzungen (ein- oder ausgehend) vorhanden sind, erhalten Sie eine Textdatei, die Ihnen mitteilt, dass keine SMB-Sitzungen gefunden wurden.</div>                                                                                                                          |
| Systeminformationen| Enthält eine SystemInformation.txt Datei, die Systeminformationen wie Betriebssystemversion und Netzwerkkarten auflistet.                                                                                     |
| Temp-Verzeichnisse| Enthält eine Reihe von Textdateien, die die Dateien in %Temp% für jeden Benutzer im System auflisten. </br></br> Dies kann helfen, verdächtige Dateien zu verfolgen, die ein Angreifer möglicherweise auf dem System abgelegt hat. </br></br> <div class="alert"><b>HINWEIS:</b> Wenn die Datei die folgende Meldung enthält: "Das System kann den angegebenen Pfad nicht finden", bedeutet dies, dass es kein temporäres Verzeichnis für diesen Benutzer gibt, und möglicherweise, weil sich der Benutzer nicht am System angemeldet hat.</div>                                                                                                                                         |
| Benutzer und Gruppen| Stellt eine Liste der Dateien bereit, die jeweils eine Gruppe und ihre Mitglieder darstellen.                                                                                                                   |
|WdSupportLogs| Bietet die MpCmdRunLog.txt und MPSupportFiles.cab  </br></br> <div class="alert"><b>HINWEIS:</b> Dieser Ordner wird nur auf Windows 10, Version 1709 oder höher mit dem Updaterollup im Februar 2020 oder neueren Installierten erstellt:</br> Win10 1709 (RS3) Build 16299.1717 : [KB4537816](https://support.microsoft.com/en-us/help/4537816/windows-10-update-kb4537816) </br> Win10 1803 (RS4) Build 17134.1345 : [KB4537795](https://support.microsoft.com/en-us/help/4537795/windows-10-update-kb4537795) </br> Win10 1809 (RS5) Build 17763.1075 : [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818) </br> Win10 1903/1909 (19h1/19h2) Builds 18362.693 und 18363.693 : [KB4535996](https://support.microsoft.com/en-us/help/4535996/windows-10-update-kb4535996) </div>                                                                                                                    |
| CollectionSummaryReport.xls| Diese Datei ist eine Zusammenfassung der Sammlung des Untersuchungspakets, sie enthält die Liste der Datenpunkte, den Befehl zum Extrahieren der Daten, den Ausführungsstatus und den Fehlercode im Falle eines Fehlers. Sie können diesen Bericht verwenden, um nachzuverfolgen, ob das Paket alle erwarteten Daten enthält, und zu ermitteln, ob Fehler aufgetreten sind. |

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>Ausführen Microsoft Defender Antivirus Scan auf Geräten

Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie aus der Ferne einen Antiviren-Scan initiieren, um Malware zu identifizieren und zu beheben, die möglicherweise auf einem kompromittierten Gerät vorhanden ist.

>[!IMPORTANT]
>- Diese Aktion ist für Geräte auf Windows 10, Version 1709 oder höher verfügbar.
>- Ein Microsoft Defender Antivirus (Microsoft Defender AV)-Scan kann zusammen mit anderen Antivirenlösungen ausgeführt werden, unabhängig davon, ob Microsoft Defender AV die aktive Antiviruslösung ist oder nicht. Microsoft Defender AV kann sich im passiven Modus befinden. Weitere Informationen finden Sie [unter Microsoft Defender Antivirus Kompatibilität](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md).

Eine, die Sie **Antivirus-Scan** ausführen ausgewählt haben, wählen Sie den Scantyp aus, den Sie ausführen möchten (schnell oder vollständig), und fügen Sie einen Kommentar hinzu, bevor Sie den Scan bestätigen.

![Bild der Benachrichtigung, um schnelles Scannen oder vollständigen Scan auszuwählen und Kommentar hinzuzufügen](images/run-antivirus.png)

Das Aktionscenter zeigt die Scaninformationen an, und die Zeitachse des Geräts enthält ein neues Ereignis, das darauf hindeutet, dass eine Scanaktion auf dem Gerät gesendet wurde. Microsoft Defender AV-Warnungen spiegeln alle Erkennungen wider, die während des Scans angezeigt wurden.

>[!NOTE]
>Beim Auslösen eines Scans mit Defender for Endpoint-Antwortaktion wird der Microsoft Defender Antivirus-Wert "ScanAvgCPULoadFactor" weiterhin angewendet und begrenzt die CPU-Auswirkungen des Scans.<br> Wenn ScanAvgCPULoadFactor nicht konfiguriert ist, ist der Standardwert ein Grenzwert von 50 % maximaler CPU-Last während eines Scans.<br>
>Weitere Informationen finden Sie [unter configure-advanced-scan-types-microsoft-defender-antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus).

## <a name="restrict-app-execution"></a>Einschränken der App-Ausführung

Zusätzlich zum Einschließen eines Angriffs durch Beenden bösartiger Prozesse können Sie auch ein Gerät sperren und die Ausführung nachfolgender Versuche potenziell schädlicher Programme verhindern.

>[!IMPORTANT]
> - Diese Aktion ist für Geräte auf Windows 10, Version 1709 oder höher verfügbar.
> - Diese Funktion ist verfügbar, wenn Ihre Organisation Microsoft Defender Antivirus verwendet.
> - Diese Aktion muss die Windows Defender Anwendungssteuerungscodeintegritätsrichtlinienformate und Signaturanforderungen erfüllen. Weitere Informationen finden Sie unter [Codeintegritätsrichtlinienformate und Signieren](https://docs.microsoft.com/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing).

Um die Ausführung einer Anwendung einzuschränken, wird eine Codeintegritätsrichtlinie angewendet, die die Ausführung von Dateien nur dann zulässt, wenn sie von einem von Microsoft ausgestellten Zertifikat signiert sind. Diese Einschränkungsmethode kann dazu beitragen, dass ein Angreifer kompromittierte Geräte kontrolliert und weitere böswillige Aktivitäten ausführt.

>[!NOTE]
>Sie können die Einschränkung von Anwendungen jederzeit von der Ausführung rückgängig machen. Die Schaltfläche auf der Geräteseite ändert sich so, dass **App-Einschränkungen entfernen** angezeigt wird, und Sie führen dann die gleichen Schritte wie das Einschränken der App-Ausführung.

Nachdem Sie die **App-Ausführung** auf der Geräteseite einschränken ausgewählt haben, geben Sie einen Kommentar ein, und wählen Sie **Bestätigen** aus. Das Aktionscenter zeigt die Scaninformationen an, und die Zeitachse des Geräts enthält ein neues Ereignis.

![Bild der App-Einschränkungsbenachrichtigung](images/restrict-app-execution.png)

**Benachrichtigung über Gerätebenutzer**:</br>
Wenn eine App eingeschränkt ist, wird die folgende Benachrichtigung angezeigt, um den Benutzer darüber zu informieren, dass die Ausführung einer App eingeschränkt wird:

![Bild der App-Einschränkung](images/atp-app-restriction.png)

## <a name="isolate-devices-from-the-network&quot;></a>Isolieren von Geräten aus dem Netzwerk

Abhängig vom Schweregrad des Angriffs und der Empfindlichkeit des Geräts können Sie das Gerät vom Netzwerk isolieren. Diese Aktion kann dazu beitragen, dass der Angreifer das kompromittierte Gerät nicht steuert und weitere Aktivitäten wie Datenexfiltration und seitliche Bewegung ausführt.

>[!IMPORTANT]
>- Die vollständige Isolierung ist für Geräte auf Windows 10 Version 1703 verfügbar.
>- Die selektive Isolierung ist für Geräte auf Windows 10 Version 1709 oder höher verfügbar.
>- Beim Isolieren eines Geräts sind nur bestimmte Prozesse und Ziele zulässig. Daher können Geräte, die sich hinter einem vollständigen VPN-Tunnel befinden, den Microsoft Defender for Endpoint-Clouddienst nicht mehr erreichen, nachdem das Gerät isoliert wurde. Es wird empfohlen, ein Split-Tunneling-VPN für Microsoft Defender für Endpoint und Microsoft Defender Antivirus cloudbasierten Schutzdatenverkehrs zu verwenden.

Diese Geräteisolationsfunktion trennt das kompromittierte Gerät vom Netzwerk, während die Verbindung zum Defender for Endpoint-Dienst beibehalten wird, der das Gerät weiterhin überwacht.

Auf Windows 10, Version 1709 oder höher, haben Sie zusätzliche Kontrolle über die Netzwerkisolationsstufe. Sie können auch Outlook, Microsoft Teams und Skype for Business Konnektivität aktivieren (auch &quot;Selektive Isolierung").

>[!NOTE]
>Sie können das Gerät jederzeit wieder mit dem Netzwerk verbinden. Die Schaltfläche auf der Geräteseite ändert sich, um **"Aus der Isolation freigeben"** zu sagen, und Sie führen dann die gleichen Schritte wie das Isolieren des Geräts.

Nachdem Sie auf der Geräteseite **Gerät isolieren** ausgewählt haben, geben Sie einen Kommentar ein, und wählen Sie **Bestätigen** aus. Das Aktionscenter zeigt die Scaninformationen an, und die Zeitachse des Geräts enthält ein neues Ereignis.

![Bild des Isolatgeräts](images/isolate-device.png)

>[!NOTE]
>Das Gerät bleibt mit dem Defender for Endpoint-Dienst verbunden, auch wenn es vom Netzwerk isoliert ist. Wenn Sie Outlook und Skype for Business Kommunikation aktivieren möchten, können Sie mit dem Benutzer kommunizieren, während das Gerät isoliert ist.

**Benachrichtigung über Gerätebenutzer**:</br>
Wenn ein Gerät isoliert wird, wird die folgende Benachrichtigung angezeigt, um den Benutzer darüber zu informieren, dass das Gerät vom Netzwerk isoliert wird:

![Bild ohne Netzwerkverbindung](images/atp-notification-isolate.png)

## <a name="consult-a-threat-expert"></a>Wenden Sie sich an einen Bedrohungsexperten

Sie können einen Microsoft-Bedrohungsexperten konsultieren, um weitere Informationen zu einem potenziell kompromittierten oder bereits kompromittierten Gerät zu erhalten. Microsoft-Bedrohungsexperten können direkt aus dem Microsoft Defender Security Center für eine zeitnahe und genaue Antwort eingebunden werden. Experten bieten Einblicke nicht nur in Bezug auf ein potenziell kompromittiertes Gerät, sondern auch, um komplexe Bedrohungen, gezielte Angriffsbenachrichtigungen, die Sie erhalten, oder wenn Sie mehr Informationen über die Warnungen benötigen, oder einen Kontext zur Bedrohungsintelligenz, der auf Ihrem Portal-Dashboard angezeigt wird, besser zu verstehen.

Weitere Informationen finden Sie unter [Konsultieren Sie einen Microsoft Threat Expert.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization)


## <a name="check-activity-details-in-action-center"></a>Überprüfen von Aktivitätsdetails im Aktionscenter

Das **Aktionscenter** enthält Informationen zu Aktionen, die auf einem Gerät oder einer Datei ausgeführt wurden. Sie können die folgenden Details anzeigen:

- Sammlung von Untersuchungspaketen
- Antivirus-Scan
- App-Einschränkung
- Geräteisolierung

Alle anderen zugehörigen Details werden auch angezeigt, z. B. Übermittlungsdatum/-zeit, sendender Benutzer und ob die Aktion erfolgreich war oder fehlgeschlagen ist.

![Bild des Aktionszentrums mit Informationen](images/action-center-details.png)

## <a name="related-topic"></a>Verwandtes Thema
- [Ergreifen von Reaktionen auf eine Datei](respond-file-alerts.md)
- [Ungenauigkeit melden](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
