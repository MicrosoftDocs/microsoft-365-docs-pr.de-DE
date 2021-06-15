---
title: Microsoft Defender AV-Ereignis-IDs und Fehlercodes
description: Nachschlagen der Ursachen und Lösungen für Microsoft Defender Antivirus Ereignis-IDs und -Fehler
keywords: Ereignis, Fehlercode, Siem, Protokollierung, Problembehandlung, Wef, Windows-Ereignisweiterleitung
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: cba7a9d6ed23ac1dc72ef6cbcecfdfc7a0f4c60b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926283"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Überprüfen von Ereignisprotokollen und Fehlercodes zum Behandeln von Problemen mit Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Wenn ein Problem mit Microsoft Defender Antivirus auftritt, können Sie in den Tabellen in diesem Thema nach einem übereinstimmenden Problem und einer potenziellen Lösung suchen.

Die Tabellenliste:

- [Microsoft Defender Antivirus Ereignis-IDs](#windows-defender-av-ids) (diese gelten sowohl für Windows 10 als auch für Windows Server 2016)
- [Microsoft Defender Antivirus Clientfehlercodes](#error-codes)
- [Interne Microsoft Defender Antivirus Clientfehlercodes (von Microsoft während der Entwicklung und beim Testen verwendet)](#internal-error-codes)

> [!TIP]
> Sie können auch die Demowebsite von Microsoft Defender für Endpunkt unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die folgenden Features funktionieren:
> 
> - Aus der Cloud gelieferter Schutz
> - Schnelles Lernen (einschließlich "Bei erster Anzeige blockieren")
> - Blockieren potenziell unerwünschter Anwendungen

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender Antivirus-Ereignis-IDs

Microsoft Defender Antivirus zeichnet Ereignis-IDs im Windows-Ereignisprotokoll auf.

Sie können das Ereignisprotokoll direkt anzeigen, oder wenn Sie über ein SIEM-Tool (Security Information and Event Management) eines Drittanbieters verfügen, können Sie auch [Microsoft Defender Antivirus Clientereignis-IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) verwenden, um bestimmte Ereignisse und Fehler von Ihren Endpunkten zu überprüfen.

In der Tabelle in diesem Abschnitt sind die wichtigsten Microsoft Defender Antivirus Ereignis-IDs aufgeführt, und nach Möglichkeit werden Lösungsvorschläge zum Beheben oder Beheben des Fehlers bereitgestellt. 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>So zeigen Sie ein Microsoft Defender Antivirus-Ereignis an

1.  Öffnen **Sie die Ereignisanzeige.**
2.  Erweitern Sie in der Konsolenstruktur **Anwendungs- und Dienstprotokolle,** dann **Microsoft**, dann **Windows** und **dann Windows Defender**.
3.  Doppelklicken Sie auf **"Betriebsbereit".**
4.  Zeigen Sie im Detailbereich die Liste der einzelnen Ereignisse an, um Ihr Ereignis zu finden.
5.  Klicken Sie auf das Ereignis, um bestimmte Details zu einem Ereignis im unteren Bereich unter den Registerkarten **"Allgemein"** und **"Details"** anzuzeigen.

<table> 
<tr>
<th colspan="2" >Ereignis-ID: 1000</th>
</tr>
<tr>
<td>
Symbolischer Name:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Ein Antischadsoftwarescan wurde gestartet. </b>
</td>
</tr>
<tr>
<td >
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Scannen von Ressourcen: &lt; Ressourcen (z. B. Dateien/Verzeichnisse/BHO), &gt; die gescannt wurden.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1001</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Ein Antischadsoftwarescan wurde abgeschlossen.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;Scanzeit</dt>des
<dt>Benutzers: &lt; Die Dauer einer Überprüfung. &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1002</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Ein Antischadsoftwarescan wurde beendet, bevor er abgeschlossen wurde. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domäne &gt; &amp; lt; &gt;Scanzeit</dt>des
<dt>Benutzers: &lt; Die Dauer einer Überprüfung. &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1003</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Ein Antischadsoftwarescan wurde angehalten. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1004</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Ein Antischadsoftwarescan wurde fortgesetzt. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1005</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Fehler bei einem Antischadsoftwarescan. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer des entsprechenden &gt; Scans.</dt> 
<dt> Scantyp: &lt; &gt; Scantyp, z. B.:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; &gt; Scanparameter, z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Der Antivirenclient ist auf einen Fehler gestoßen, und die aktuelle Überprüfung wurde beendet. Die Überprüfung schlägt möglicherweise aufgrund eines clientseitigen Problems fehl. Dieser Ereignisdatensatz enthält die Scan-ID, den Scantyp (Microsoft Defender Antivirus, Antispyware, Antischadsoftware), Scanparameter, den Benutzer, der die Überprüfung gestartet hat, den Fehlercode und eine Beschreibung des Fehlers.
So behandeln Sie dieses Ereignis:
<ol>
<li>Führen Sie den Scan erneut aus.</li>
<li>Wenn auf die gleiche Weise ein Fehler auftritt, wechseln Sie zur <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite,</a>und geben Sie die Fehlernummer in das <b>Suchfeld</b> ein, um nach dem Fehlercode zu suchen.</li>
<li>Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1006</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul hat Schadsoftware oder andere potenziell unerwünschte Software gefunden. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:<ul>
<li>Heuristik</li>
<li>Generic</li>
<li>Konkrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:<ul>
<li>Benutzer: benutzerinitiierte</li>
<li>System: systeminitiiertes System</li>
<li>Echtzeit: In Echtzeit initiierte Komponente</li>
<li>IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</li>
<li>NIS: Netzwerküberprüfungssystem</li>
<li>IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</li>
<li>Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remotenachweis</li>
</ul>Antischadsoftware-Scanschnittstelle (AMSI). Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Status: &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>Version des
<dt> &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 1007</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; Bedrohungs-ID: &gt; </dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt> Aktion: &lt; &gt; Aktion, z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde unter Quarantäne gestellt</li>
<li>Entfernen: Die Ressource wurde gelöscht.</li>
<li>Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 1008</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat versucht, eine Aktion auszuführen, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen, die Aktion ist jedoch fehlgeschlagen.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software auf einen Fehler gestoßen. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; Bedrohungs-ID: &gt; </dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadaktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde unter Quarantäne gestellt</li>
<li>Entfernen: Die Ressource wurde gelöscht.</li>
<li>Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Fehlercode: &lt; &gt;Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 1009</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat ein Element aus der Quarantäne wiederhergestellt. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus ein Element aus der Quarantäne wiederhergestellt hat. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 1010</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform konnte ein Element nicht aus der Quarantäne wiederherstellen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, ein Element aus der Quarantäne wiederherzustellen, ist ein Fehler aufgetreten. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1011</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat ein Element aus der Quarantäne gelöscht. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus ein Element aus der Quarantäne gelöscht hat.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: Version des &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 1012</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform konnte ein Element nicht aus der Quarantäne löschen.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, ein Element aus der Quarantäne zu löschen, ist ein Fehler aufgetreten.
Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;Dateipfadbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1013</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software gelöscht.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software entfernt.
<dl>
<dt>Uhrzeit: Die Uhrzeit, zu der das Ereignis aufgetreten ist, z. B. wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um die Wiederherstellungszeit oder die Infektionszeit handelt. Für diese bezeichnen wir sie ausdrücklich als Aktionszeit oder Erkennungszeit.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1014</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
Die Antischadsoftwareplattform konnte den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software nicht löschen.
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software zu entfernen, ist ein Fehler aufgetreten.
<dl>
<dt>Uhrzeit: Die Uhrzeit, zu der das Ereignis aufgetreten ist, z. B. wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um die Wiederherstellungszeit oder die Infektionszeit handelt. Für diese bezeichnen wir sie ausdrücklich als Aktionszeit oder Erkennungszeit.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1015</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat verdächtiges Verhalten erkannt.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat ein verdächtiges Verhalten erkannt.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:<ul>
<li>Heuristik</li>
<li>Generic</li>
<li>Konkrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:<ul>
<li>Benutzer: benutzerinitiierte</li>
<li>System: systeminitiiertes System</li>
<li>Echtzeit: In Echtzeit initiierte Komponente</li>
<li>IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</li>
<li>NIS: Netzwerküberprüfungssystem</li>
<li>IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</li>
<li>Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remotenachweis</li>
</ul>Antischadsoftware-Scanschnittstelle (AMSI). Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Status: &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signatur-ID:</dt>
<dt>Aufzählungsabgleichsschweregrad.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt>Antischadsoftware-Engine &lt; &gt; Version</dt>
<dt>Fidelity Label:</dt>
<dt>Zieldateiname: &lt; &gt; Dateinamename der Datei.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1116</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat Schadsoftware oder andere potenziell unerwünschte Software erkannt. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Schadsoftware oder andere potenziell unerwünschte Software erkannt hat.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:<ul>
<li>Heuristik</li>
<li>Generic</li>
<li>Konkrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:<ul>
<li>Benutzer: benutzerinitiierte</li>
<li>System: systeminitiiertes System</li>
<li>Echtzeit: In Echtzeit initiierte Komponente</li>
<li>IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</li>
<li>NIS: Netzwerküberprüfungssystem</li>
<li>IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</li>
<li>Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remotenachweis</li>
</ul>Antischadsoftware-Scanschnittstelle (AMSI). Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>Version des
<dt> &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Microsoft Defender Antivirus können diese Bedrohung anhalten und routinemäßig maßnahmen. Wenn Sie die Bedrohung manuell entfernen möchten, klicken Sie auf der Microsoft Defender Antivirus Benutzeroberfläche auf <b>"Computer bereinigen".</b>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1117</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:<ul>
<li>Heuristik</li>
<li>Generic</li>
<li>Konkrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:<ul>
<li>Benutzer: benutzerinitiierte</li>
<li>System: systeminitiiertes System</li>
<li>Echtzeit: In Echtzeit initiierte Komponente</li>
<li>IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</li>
<li>NIS: Netzwerküberprüfungssystem</li>
<li>IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</li>
<li>Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remotenachweis</li>
</ul>Antischadsoftware-Scanschnittstelle (AMSI). Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde unter Quarantäne gestellt</li>
<li>Entfernen: Die Ressource wurde gelöscht.</li>
<li>Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt>Antischadsoftware-Engine &lt; Version &gt; </dt> HINWEIS: Wenn Microsoft Defender Antivirus, Microsoft Security Essentials, Tool zum Entfernen bösartiger Software oder System Center Endpoint Protection eine Schadsoftware erkennt, werden die folgenden Systemeinstellungen und Dienste wiederhergestellt, die die Schadsoftware möglicherweise geändert hat:<ul>
<li>Standardeinstellung für Internet Explorer oder Microsoft Edge</li>
<li>Einstellungen für die Benutzerzugriffssteuerung</li>
<li>Chrome-Einstellungen</li>
<li>Startsteuerungsdaten</li>
<li>Registrierungseinstellungen für Regedit und Task-Manager</li>
<li>Windows Update-, Background Intelligent Transfer Service- und Remoteprozedur-Aufrufdienst</li>
<li>Windows Betriebssystemdateien</li></ul>
Der obige Kontext gilt für die folgenden Client- und Serverversionen:
<table>
<tr>
<th>Betriebssystem</th>
<th>Betriebssystemversion</th>
</tr>
<tr>
<td>
Clientbetriebssystem
</td>
<td>
Windows Vista (Service Pack 1 oder Service Pack 2), Windows 7 und höher
</td>
</tr>
<tr>
<td>
Serverbetriebssystem
</td>
<td>
Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 und Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Microsoft Defender Antivirus eine Bedrohung entfernt oder isoliert. 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1118</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform hat versucht, eine Aktion auszuführen, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen, die Aktion ist jedoch fehlgeschlagen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software ein nicht schwerwiegender Fehler aufgetreten.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:<ul>
<li>Heuristik</li>
<li>Generic</li>
<li>Konkrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:<ul>
<li>Benutzer: benutzerinitiierte</li>
<li>System: systeminitiiertes System</li>
<li>Echtzeit: In Echtzeit initiierte Komponente</li>
<li>IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</li>
<li>NIS: Netzwerküberprüfungssystem</li>
<li>IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</li>
<li>Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remotenachweis</li>
</ul>Antischadsoftware-Scanschnittstelle (AMSI). Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde unter Quarantäne gestellt</li>
<li>Entfernen: Die Ressource wurde gelöscht.</li>
<li>Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Microsoft Defender Antivirus konnte eine Aufgabe im Zusammenhang mit der Schadsoftwarebehebung nicht abschließen. Dies ist kein schwerwiegender Fehler.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1119</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform ist beim Versuch, Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software zu ergreifen, auf einen kritischen Fehler gestoßen. Die Ereignisnachricht enthält weitere Details.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software einen kritischen Fehler festgestellt hat.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; Id &gt; des Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad, z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. bedrohungs- oder schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Erkennungsursprung des &gt; Dateipfads:</dt> 
<dt> &lt; Erkennungsursprung, &gt; z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; Erkennungstyp, &gt; z. B.:<ul>
<li>Heuristik</li>
<li>Generic</li>
<li>Konkrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; Erkennungsquelle &gt; zum Beispiel:<ul>
<li>Benutzer: benutzerinitiierte</li>
<li>System: systeminitiiertes System</li>
<li>Echtzeit: In Echtzeit initiierte Komponente</li>
<li>IOAV: Initiierte IE-Downloads und Outlook Express-Anlagen</li>
<li>NIS: Netzwerküberprüfungssystem</li>
<li>IEPROTECT: IE – IExtensionValidation; Dies schützt vor bösartigen Webseitensteuerelementen</li>
<li>Antischadsoftware -Frühstart (Early Launch Antimalware, ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remotenachweis</li>
</ul>Antischadsoftware-Scanschnittstelle (AMSI). Wird in erster Linie zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt> 
<dt> &lt; &gt; Aktion, z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde unter Quarantäne gestellt</li>
<li>Entfernen: Die Ressource wurde gelöscht.</li>
<li>Zulassen: Die Ressource konnte ausgeführt werden/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; &gt; Antischadsoftware-Engine Version</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Der Microsoft Defender Antivirus-Client ist aufgrund kritischer Probleme auf diesen Fehler gestoßen. Der Endpunkt ist möglicherweise nicht geschützt. Überprüfen Sie die Fehlerbeschreibung, und führen Sie dann die entsprechenden Schritte <b>für die Benutzeraktion</b> unten aus.
<table>
<tr>
<th>Aktion</th>
<th>Benutzeraktion</th>
</tr>
<tr>
<td>
<b>Entfernen</b>
</td>
<td>
Aktualisieren Sie die Definitionen, und stellen Sie sicher, dass die Entfernung erfolgreich war.
</td>
</tr>
<tr>
<td>
<b>Sauber</b>
</td>
<td>
Aktualisieren Sie die Definitionen, und überprüfen Sie dann, ob die Korrektur erfolgreich war.
</td>
</tr>
<tr>
<td>
<b>Quarantäne</b>
</td>
<td>
Aktualisieren Sie die Definitionen, und stellen Sie sicher, dass der Benutzer über die Berechtigung für den Zugriff auf die erforderlichen Ressourcen verfügt.
</td>
</tr>
<tr>
<td>
<b>Ermöglichen</b>
</td>
<td>
Stellen Sie sicher, dass der Benutzer über die Berechtigung zum Zugriff auf die erforderlichen Ressourcen verfügt.
</td>
</tr>
</table>

Wenn dieses Ereignis weiterhin besteht:<ol>
<li>Führen Sie den Scan erneut aus.</li>
<li>Wenn auf die gleiche Weise ein Fehler auftritt, wechseln Sie zur <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite,</a>und geben Sie die Fehlernummer in das <b>Suchfeld</b> ein, um nach dem Fehlercode zu suchen.</li>
<li>Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1120</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Microsoft Defender Antivirus hat die Hashes für eine Bedrohungsressource abgeleitet.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Client ist in einem fehlerfreien Zustand ausgeführt.
<dl>
<dt>Aktuelle Plattformversion: &lt; Threat &gt; </dt>Resource Path der aktuellen
<dt>Plattformversion: &lt; &gt; Pfadhashes:</dt>
<dt> &lt; Hashes &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Hinweis: Dieses Ereignis wird nur protokolliert, wenn die folgende Richtlinie festgelegt ist: <b>ThreatFileHashLogging unsigned</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 1150</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Wenn Ihre Antischadsoftwareplattform den Status an eine Überwachungsplattform meldet, gibt dieses Ereignis an, dass die Antischadsoftwareplattform ausgeführt wird und sich in einem fehlerfreien Zustand befindet. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Client ist in einem fehlerfreien Zustand ausgeführt.
<dl>
<dt>Plattformversion: &lt; Signaturversion &gt; der aktuellen Plattformversion:</dt>Version des
<dt> &lt; &gt; Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftware-Engine Version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand. Dieses Ereignis wird stündlich gemeldet.
</td>
</tr>

<tr>
<th colspan="2">Ereignis-ID: 1151</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Endpoint Protection Clientintegritätsbericht (Uhrzeit in UTC)</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Antivirus-Clientintegritätsbericht.
<dl>
<dt>Plattformversion: &lt; Aktuelle Version &gt; des Plattformversionsmoduls:</dt>
<dt>Antischadsoftware-Engine &lt; &gt; Version</dt>des Network Realtime Inspection-Moduls: Version der Antivirus-Signaturversion des
<dt> &lt; Network Realtime &gt; Inspection-Moduls:</dt>
<dt> &lt; &gt; Antivirensignaturversion</dt>
<dt>Antispyware-Signaturversion: &lt; Antispyware-Signaturversion &gt; </dt>der Network Realtime Inspection-Signaturversion: RTP-Status der
<dt> &lt; Netzwerk-Echtzeitüberprüfungssignaturversion: &gt; </dt>Echtzeit Protection State
<dt> &lt; &gt; (Enabled or Disabled)</dt>
<dt>OA &lt; state: On Access state &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt; IE Downloads and Outlook Express Attachments state &gt; (Enabled or Disabled)</dt>BM
<dt>state: Behavior Monitoring state &lt; &gt; (Enabled or Disabled)</dt>Antivirus signature
<dt>age: Antivirus signature &lt; age: Antivirus signature age &gt;(in Tagen)</dt>Alter der
<dt>Antispyware-Signatur: Alter der &lt; Antispyware-Signatur &gt; (in Tagen)</dt>
<dt>Letztes Schnelle &lt; scanalter: Letztes Schnelle scanalter &gt; (in Tagen)</dt>
<dt>Letztes vollständiges &lt; Scanalter: Letztes vollständiges Scanalter &gt; (in Tagen)</dt>
<dt>Erstellungszeit der Antivirus-Signatur: ? &lt; &gt;</dt>Zeit für die Erstellung von
<dt>Antispyware-Signaturen durch Antivirus: ? &lt; Erstellungszeit der &gt; Antispyware-Signatur</dt>
<dt>zum Zeitpunkt des letzten Schnellscanstarts: ? &lt; Startzeit des &gt; letzten Schnellscans</dt>
<dt>Letztes Ende des Schnellscans: ? &lt; Letzte &gt; Schnellscanendzeit</dt>
<dt>letzte Schnellscanquelle: Letzte &lt; Schnellscanquelle &gt; (0 = Scan wurde nicht ausgeführt&#39;, 1 = vom Benutzer initiiert, 2 = vom System initiiert)</dt>
<dt>Letzte Startzeit des vollständigen Scans: ? &lt; Startzeit &gt; des letzten vollständigen Scans</dt>
<dt>Letzte Vollständige Scan-Endzeit: ? &lt; Letzte vollständige &gt; Scanendzeit</dt>letzte vollständige
<dt>Scanquelle: Letzte Quelle des &lt; vollständigen Scans &gt; (0 = Scan wurde nicht ausgeführt&#39;, 1 = vom Benutzer initiiert, 2 = vom System initiiert)</dt> 
<dt> Produktstatus: Für interne Problembehandlung
</dl>
</td>
</tr>

<tr>
<th colspan="2">Ereignis-ID: 2000</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwaredefinitionen wurden erfolgreich aktualisiert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Antivirensignaturversion wurde aktualisiert.
<dl>
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Vorherige Signaturversion: Signaturtyp der &lt; vorherigen &gt; Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder "Full" oder "Delta".</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Aktuelle &gt; Modulversion</dt>
<dt>des Benutzers: &lt; Aktuelle Modulversion &gt; </dt>Vorherige
<dt>Modulversion: &lt; Vorherige Modulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand. Dieses Ereignis wird gemeldet, wenn Signaturen erfolgreich aktualisiert werden.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2001</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Update zur Sicherheitsintelligenz ist fehlgeschlagen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, Signaturen zu aktualisieren, ist ein Fehler aufgetreten.
<dl>
<dt>Neue Security Intelligence-Version: &lt; Neue &gt; Versionsnummer</dt>
<dt>Frühere Security Intelligence-Version: &lt; Updatequelle der vorherigen &gt; Version:</dt> 
<dt> &lt; &gt; Updatequelle, z. B.:
<ul>
<li>Security Intelligence Update-Ordner</li>
<li>Interner Security Intelligence Update-Server</li>
<li>Microsoft Update Server</li>
<li>Dateifreigabe</li>
<li>Microsoft Center zum Schutz vor Malware (MMPC)</li>
</ul>
</dt>
<dt>Updatephase: &lt; &gt; Updatephase, z. B.:
<ul>
<li>Suche</li>
<li>Herunterladen</li>
<li>Installieren</li>
</ul>
</dt>
<dt>Quellpfad: Dateifreigabename für Universal Naming Convention (UNC), Servername für Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, z. B.: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder "Full" oder "Delta".</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Dieser Fehler tritt auf, wenn beim Aktualisieren von Definitionen ein Problem auftritt.
So behandeln Sie dieses Ereignis:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</li>
<li>Überprüfen Sie die Einträge in der Datei "%Windir%\WindowsUpdate.log", um weitere Informationen zu diesem Fehler zu erfahren.</li>
<li>Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2002</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul wurde erfolgreich aktualisiert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Modulversion wurde aktualisiert.
<dl>
<dt>Aktuelle Modulversion: &lt; Aktuelle &gt; Modulversion</dt>
<dt>Vorherige Modulversion: Modultyp der &lt; vorherigen &gt; Modulversion:</dt>
<dt> &lt; &gt; Modultyp, entweder Antischadsoftwaremodul oder Netzwerküberprüfungssystemmodul.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; Benutzer &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand. Dieses Ereignis wird gemeldet, wenn das Antischadsoftwaremodul erfolgreich aktualisiert wurde.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2003</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Fehler beim Update des Antischadsoftwaremoduls. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, das Modul zu aktualisieren, ist ein Fehler aufgetreten.
<dl>
<dt>Neue Modulversion:</dt>
<dt>Frühere Modulversion: Modultyp der &lt; vorherigen &gt; Modulversion:</dt>
<dt> &lt; Modultyp, &gt; antischadsoftwaremodul oder Netzwerküberprüfungssystemmodul.</dt> 
<dt>Benutzer: &lt; Domäne &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Fehler bei der Microsoft Defender Antivirus Clientaktualisierung. Dieses Ereignis tritt auf, wenn der Client sich selbst nicht aktualisieren kann. Dieses Ereignis ist in der Regel auf eine Unterbrechung der Netzwerkkonnektivität während eines Updates zurückzuführen.
So behandeln Sie dieses Ereignis:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</li>
<li>Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2004</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Beim Laden von Antischadsoftwaredefinitionen ist ein Problem aufgetreten. Das Antischadsoftwaremodul versucht, den letzten bekannten ordnungsgemäßen Satz von Definitionen zu laden.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, Signaturen zu laden, einen Fehler aufgetreten ist, und versucht, einen bekannten Satz von Signaturen wiederhergestellt zu werden.
<dl>
<dt>Versuchte Signaturen:</dt>
<dt>Fehlercode: &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des Definitionsversionsmoduls:</dt>
<dt> &lt; Antischadsoftwaremodulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Der Microsoft Defender Antivirus-Client hat versucht, die neueste Definitionsdatei herunterzuladen und zu installieren, und es ist ein Fehler aufgetreten. Dieser Fehler kann auftreten, wenn der Client beim Laden der Definitionen auf einen Fehler stößt oder wenn die Datei beschädigt ist. Microsoft Defender Antivirus versuchen, zu einem bekannten Satz von Definitionen zurückzukehren.
So behandeln Sie dieses Ereignis:
<ol>
<li>Starten Sie den Computer neu, und versuchen Sie es erneut.</li>
<li>Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence Website</a>herunter.
Hinweis: Die Größe der von der Website heruntergeladenen Definitionsdatei kann 60 MB überschreiten und sollte nicht als langfristige Lösung zum Aktualisieren von Definitionen verwendet werden.
</li>
<li>Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2005</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul konnte nicht geladen werden, da die Antischadsoftwareplattform veraltet ist. Die Antischadsoftwareplattform lädt das zuletzt als gut bekannte Antischadsoftwaremodul und versucht, es zu aktualisieren.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus konnte das Antischadsoftwaremodul nicht laden, da die aktuelle Plattformversion nicht unterstützt wird. Microsoft Defender Antivirus kehren zum letzten als gut bekannten Modul zurück, und es wird versucht, ein Plattformupdate auszuführen.
<dl>
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2006</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Plattformupdate ist fehlgeschlagen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, die Plattform zu aktualisieren, ist ein Fehler aufgetreten.
<dl>
<dt>Aktuelle Plattformversion: &lt; Fehlercode &gt; der aktuellen Plattformversion:</dt>
<dt> &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2007</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Plattform ist in Kürze veraltet. Laden Sie die neueste Plattform herunter, um den Schutz auf dem neuesten Stand zu halten.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus benötigen in Kürze eine neuere Plattformversion, um zukünftige Versionen des Antischadsoftwaremoduls zu unterstützen. Laden Sie die neueste Microsoft Defender Antivirus-Plattform herunter, um das beste verfügbare Schutzniveau aufrechtzuerhalten.
<dl>
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2010</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul hat den Dienst für dynamische Signaturen verwendet, um zusätzliche Definitionen abzurufen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus den <i>Dienst für dynamische Signaturen</i> verwendet, um zusätzliche Signaturen abzurufen, um Ihren Computer zu schützen.
<dl>
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle Modulversion &gt; </dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp, &gt; z. B.:
<ul>
<li>Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
<li>Dauer</li>
</ul>
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit &gt; type, for example:
<ul>
<li>VDM-Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
</ul>
</dt>
<dt>Persistenzgrenzwert: Persistenzlimit der FastPath-Signatur.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 2011</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Der Dienst für dynamische Signaturen hat die veralteten dynamischen Definitionen gelöscht. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus <i>den Dienst für dynamische Signaturen</i> verwendet, um veraltete Signaturen zu verwerfen.
<dl>
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle Modulversion &gt; </dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp, &gt; z. B.:
<ul>
<li>Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
<li>Dauer</li>
</ul>
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit &gt; type, for example:
<ul>
<li>VDM-Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
</ul>
</dt>
<dt>Persistenzgrenzwert: Persistenzlimit der FastPath-Signatur.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand. Dieses Ereignis wird gemeldet, wenn der Dienst für dynamische Signaturen veraltete dynamische Definitionen erfolgreich löscht.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2012</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Beim Versuch, den Dienst für dynamische Signaturen zu verwenden, ist beim Antischadsoftwaremodul ein Fehler aufgetreten. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, den Dienst für <i>dynamische Signaturen</i>zu verwenden, ein Fehler aufgetreten ist.
<dl>
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen Signaturversion:</dt> 
<dt> &lt; &gt; Signaturtyp, z. B.: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Aktuelle Modulversion: &lt; Fehlercode &gt; der aktuellen Modulversion:</dt>
<dt> &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt> Dynamischer Signaturtyp: &lt; Dynamischer &gt; Signaturtyp, z. B.:
<ul>
<li>Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
<li>Dauer</li>
</ul>
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit &gt; type, for example:
<ul>
<li>VDM-Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
</ul>
</dt>
<dt>Persistenzgrenzwert: Persistenzlimit der FastPath-Signatur.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Überprüfen Sie ihre Internetkonnektivitätseinstellungen.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2013</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Der Dienst für dynamische Signaturen hat alle dynamischen Definitionen gelöscht. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus alle Signaturen <i>des Diensts für dynamische Signaturen</i> verworfen.
<dl>
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2020</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul hat eine fehlerfreie Datei heruntergeladen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus eine bereinigte Datei heruntergeladen.
<dl>
<dt>Dateiname: &lt; Dateiname &gt; der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Aktuelle Modulversion: Aktuelle &lt; Modulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2021</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul konnte keine fehlerfreie Datei herunterladen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, eine fehlerfreie Datei herunterzuladen, ist ein Fehler aufgetreten.
<dl>
<dt>Dateiname: &lt; Dateiname &gt; der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle &gt; Signaturversion</dt>
<dt>Aktuelle Modulversion: Fehlercode der &lt; aktuellen Modulversion: &gt; </dt>
<dt> &lt; &gt; Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Überprüfen Sie ihre Internetkonnektivitätseinstellungen.
Beim Microsoft Defender Antivirus Client ist beim Verwenden des Diensts für dynamische Signaturen ein Fehler aufgetreten, um die neuesten Definitionen für eine bestimmte Bedrohung herunterzuladen. Dieser Fehler wird wahrscheinlich durch ein Netzwerkverbindungsproblem verursacht. 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2030</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul wurde heruntergeladen und ist so konfiguriert, dass es beim nächsten Systemneustart offline ausgeführt wird.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus offline Antivirus heruntergeladen und konfiguriert, um beim nächsten Neustart ausgeführt zu werden.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2031</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul konnte einen Offlinescan nicht herunterladen und konfigurieren.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus beim Versuch, Offline-Antivirus herunterzuladen und zu konfigurieren, ist ein Fehler aufgetreten.
<dl>
<dt>Fehlercode: &lt; &gt;Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2040</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareunterstützung für diese Betriebssystemversion wird bald beendet. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Unterstützung für Ihr Betriebssystem läuft in Kürze ab. Das Ausführen von Microsoft Defender Antivirus auf einem nicht unterstützten Betriebssystem ist keine angemessene Lösung zum Schutz vor Bedrohungen.
</td>
</tr>
<tr>
<th colspan="2">Ereigniskennung: 2041</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareunterstützung für dieses Betriebssystem wurde beendet. Sie müssen das Betriebssystem aktualisieren, um den Support fortzusetzen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Unterstützung für Ihr Betriebssystem ist abgelaufen. Das Ausführen von Microsoft Defender Antivirus auf einem nicht unterstützten Betriebssystem ist keine angemessene Lösung zum Schutz vor Bedrohungen.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 2042</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Das Antischadsoftwaremodul unterstützt dieses Betriebssystem nicht mehr und schützt Ihr System nicht mehr vor Schadsoftware. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Unterstützung für Ihr Betriebssystem ist abgelaufen. Microsoft Defender Antivirus wird auf Ihrem Betriebssystem nicht mehr unterstützt, funktioniert nicht mehr und schützt nicht mehr vor Schadsoftwarebedrohungen.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 3002</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Beim Echtzeitschutz ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Real-Time Protection-Feature ist ein Fehler aufgetreten und fehlgeschlagen.
<dl>
<dt>Feature: &lt; &gt; Feature, z. B.:
<ul>
<li>Bei Zugriff</li>
<li>Internet Explorer-Downloads und Microsoft Outlook Express-Anlagen</li>
<li>Verhaltensüberwachung</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Fehlercode: &lt; &gt;Fehlercode-Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus Echtzeitschutz ein Feature neu gestartet hat.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Starten Sie das System neu, und führen Sie dann einen vollständigen Scan durch, da es&#39;, dass das System für einige Zeit nicht geschützt war.
Das Echtzeitschutzfeature des Microsoft Defender Antivirus-Clients&#39;ist auf einen Fehler gestoßen, da einer der Dienste nicht gestartet werden konnte. Wenn auf sie eine 3007-Ereignis-ID folgt, war der Fehler temporär, und der Antischadsoftwareclient wurde nach dem Fehler wiederhergestellt. 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 3007</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Echtzeitschutz, der nach einem Fehler wiederhergestellt wurde. Es wird empfohlen, eine vollständige Systemüberprüfung auszuführen, wenn dieser Fehler angezeigt wird. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Der Echtzeitschutz hat ein Feature neu gestartet. Es wird empfohlen, dass Sie einen vollständigen Systemscan ausführen, um Elemente zu erkennen, die während des Ausfalls dieses Agents möglicherweise übersehen wurden.
<dl>
<dt>Feature: &lt; &gt; Feature, z. B.:
<ul>
<li>Bei Zugriff</li>
<li>IE-Downloads und Outlook Express-Anlagen</li>
<li>Verhaltensüberwachung</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus Echtzeitschutz ein Feature neu gestartet hat.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Das Echtzeitschutzfeature wurde neu gestartet. Wenn dieses Ereignis erneut auftritt, wenden Sie sich an <a href="https://go.microsoft.com/fwlink/?LinkId=215491">den technischen Support von Microsoft.</a> 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5000</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Der Echtzeitschutz ist aktiviert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Echtzeitschutzüberprüfung auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5001</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Der Echtzeitschutz ist deaktiviert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Echtzeitschutzüberprüfung auf Schadsoftware und andere potenziell unerwünschte Software wurde deaktiviert. 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5004</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Echtzeitschutzkonfiguration wurde geändert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Konfiguration der Echtzeitschutzfunktion wurde geändert.
<dl>
<dt>Feature: &lt; &gt; Feature, z. B.:
<ul>
<li>Bei Zugriff</li>
<li>IE-Downloads und Outlook Express-Anlagen</li>
<li>Verhaltensüberwachung</li>
<li>Netzwerküberprüfungssystem</li>
</ul>
</dt>
<dt>Konfiguration: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5007</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Konfiguration der Antischadsoftwareplattform wurde geändert.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Konfiguration wurde geändert. Wenn dies ein unerwartetes Ereignis ist, sollten Sie die Einstellungen überprüfen, da dies das Ergebnis von Schadsoftware sein kann.
<dl>
<dt>Alter Wert: &lt; Alter Wert Zahl &gt; Alter Antivirus-Konfigurationswert.</dt> 
<dt>Neuer Wert: &lt; New value number &gt; New antivirus configuration value.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5008</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Beim Antischadsoftwaremodul ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Modul wurde aufgrund eines unerwarteten Fehlers beendet.
<dl>
<dt>Fehlertyp: &lt; &gt;Fehlertyp, z. B.: Crash or Hang</dt>Exception
<dt>Code: Error &lt; code &gt; </dt>
<dt>Resource: &lt; Resource &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
So behandeln Sie dieses Ereignis:<ol>
<li>Versuchen Sie, den Dienst neu zu starten.<ul>
<li>Geben Sie für Antischadsoftware, Antivirus und Spyware an einer Eingabeaufforderung mit erhöhten Rechten <b>"net stop msmpsvc"</b>ein, und geben Sie dann <b>"net start msmpsvc"</b> ein, um das Antischadsoftwaremodul neu zu starten.</li>
<li>Geben Sie für das <i>Netzwerküberprüfungssystem</i>an einer Eingabeaufforderung mit erhöhten Rechten <b>"net start nissrv"</b>und dann <b>"net start nissrv"</b> ein, um das <i>Netzwerküberprüfungssystem-Modul</i> mithilfe der NiSSRV.exe-Datei neu zu starten.
</li>
</ul>
</li>
<li>Wenn auf die gleiche Weise ein Fehler auftritt, suchen Sie nach dem Fehlercode, indem Sie auf die <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite</a> zugreifen und die Fehlernummer in das <b>Suchfeld</b> eingeben, und wenden Sie sich an den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft.</a></li>
</ol>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Das Microsoft Defender Antivirus Clientmodul wurde aufgrund eines unerwarteten Fehlers beendet.
So behandeln Sie dieses Ereignis:
<ol>
<li>Führen Sie den Scan erneut aus.</li>
<li>Wenn auf die gleiche Weise ein Fehler auftritt, wechseln Sie zur <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-Supportwebsite,</a>und geben Sie die Fehlernummer in das <b>Suchfeld</b> ein, um nach dem Fehlercode zu suchen.</li>
<li>Kontaktieren Sie den <a href="https://go.microsoft.com/fwlink/?LinkId=215491">technischen Support von Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5009</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist aktiviert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5010</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Überprüfung auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5011</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Virenüberprüfung ist aktiviert.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Virenüberprüfung wurde aktiviert. 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5012</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Virenüberprüfung ist deaktiviert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Virenüberprüfung ist deaktiviert. 
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5100</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform läuft in Kürze ab. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat eine Nachfrist begonnen und läuft bald ab. Nach ablaufen deaktiviert dieses Programm den Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software.
<dl>
<dt>Ablaufgrund: Der Grund, warum Microsoft Defender Antivirus abläuft.</dt> 
<dt>Ablaufdatum: Das Datum Microsoft Defender Antivirus abläuft.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Ereignis-ID: 5101</th>
</tr>
<tr><td>
Symbolischer Name:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
Meldung:
</td>
<td >
<b>Die Antischadsoftwareplattform ist abgelaufen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Karenzzeit abgelaufen ist. Der Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software ist deaktiviert.
<dl>
<dt>Ablaufgrund:</dt>
<dt>Ablaufdatum: </dt> 
<dt>Fehlercode: &lt; Fehlercode-Ergebniscode, der dem &gt; Bedrohungsstatus zugeordnet ist. HRESULT-Standardwerte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Microsoft Defender Antivirus Clientfehlercodes Wenn Microsoft Defender Antivirus Probleme auftreten, erhalten Sie in der Regel einen Fehlercode, der Ihnen bei der Problembehandlung hilft. In den meisten Fällen bedeutet ein Fehler, dass beim Installieren eines Updates ein Problem aufgetreten ist.
Dieser Abschnitt enthält die folgenden Informationen zu Microsoft Defender Antivirus Clientfehlern.
-   Der Fehlercode -   Der mögliche Grund für den -   Fehler. Hinweise dazu, was jetzt zu tun ist

Verwenden Sie die Informationen in diesen Tabellen zur Problembehandlung Microsoft Defender Antivirus Fehlercodes.


<table> 
<tr>
<th colspan="2">Fehlercode: 0x80508007</th>
</tr>
<tr>
<td>Meldung</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
Mögliche Ursache
</td>
<td>
Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Arbeitsspeicher vorhanden ist. 
</td>
</tr>
<tr>
<td>Lösung</td>
<td>
<ol>
<li>Überprüfen Sie den verfügbaren Arbeitsspeicher auf Ihrem Gerät.</li>
<li>Schließen Sie alle nicht verwendeten Anwendungen, die ausgeführt werden, um Arbeitsspeicher auf Ihrem Gerät freizugeben.</li>
<li>Starten Sie das Gerät neu, und führen Sie den Scan erneut aus. 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x8050800C</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass möglicherweise ein Problem mit Ihrem Sicherheitsprodukt vorliegt.
</td>
</tr><tr><td>Lösung</td><td>
<ol>
<li>Aktualisieren Sie die Definitionen. Entweder:<ol>
<li>Klicken Sie auf der Registerkarte <b>"Aktualisieren"</b> in Microsoft Defender Antivirus auf die Schaltfläche <b>"Definitionen</b> aktualisieren". <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>Oder:
</li>
<li>Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence Website</a>herunter.
Hinweis: Die Größe der von der Website heruntergeladenen Definitionsdatei kann 60 MB überschreiten und sollte nicht als langfristige Lösung zum Aktualisieren von Definitionen verwendet werden.
</li>
</ol>
</li>
<li>Führen Sie einen vollständigen Scan aus.
</li>
<li>Starten Sie das Gerät neu, und versuchen Sie es erneut.</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508020</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass möglicherweise ein Modulkonfigurationsfehler vorliegt. In der Regel bezieht sich dies auf Eingabedaten, die nicht zulassen, dass das Modul ordnungsgemäß funktioniert. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x805080211
</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass Microsoft Defender Antivirus eine Bedrohung nicht unter Quarantäne stellen konnten. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508022
</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass ein Neustart erforderlich ist, um die Bedrohung zu entfernen. 
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass die Bedrohung möglicherweise nicht mehr auf den Medien vorhanden ist, oder dass Schadsoftware Sie daran hindert, Ihr Gerät zu scannen. 
</tr><tr><td>Lösung
</td>
<td>
Führen Sie die <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> aktualisieren Sie dann Ihre Sicherheitssoftware, und versuchen Sie es erneut. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508024 </th></tr>
<tr>
<td>Meldung</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass möglicherweise eine vollständige Systemüberprüfung erforderlich ist. 
</td></tr>
<tr>
<td>Lösung</td><td>
Führen Sie eine vollständige Systemüberprüfung aus. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508025
</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass manuelle Schritte erforderlich sind, um die Bedrohungsentfernung abzuschließen. 
</td></tr><tr><td>Lösung</td><td>
Führen Sie die manuellen Korrekturschritte aus, die im <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection-Abschnitt</a>beschrieben sind. Sie finden einen bedrohungsspezifischen Link im Ereignisverlauf.<br/></td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508026
</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass das Entfernen innerhalb des Containertyps möglicherweise nicht unterstützt wird. 
</td></tr><tr><td>Lösung</td><td>
Microsoft Defender Antivirus können im Archiv erkannte Bedrohungen nicht beheben. Erwägen Sie, die erkannten Ressourcen manuell zu entfernen. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508027
</th>
</tr><tr><td>Meldung</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass das Entfernen von niedrigen und mittleren Bedrohungen möglicherweise deaktiviert ist. 
</td></tr><tr><td>Lösung</td><td>
Überprüfen Sie die erkannten Bedrohungen, und beheben Sie sie nach Bedarf. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508029
</th>
</tr><tr><td>Meldung</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass eine erneute Überprüfung der Bedrohung erforderlich ist. 
</td></tr><tr><td>Lösung</td><td>
Führen Sie eine vollständige Systemüberprüfung aus. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508030
</th>
</tr><tr><td>Meldung</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass eine Offlineüberprüfung erforderlich ist. 
</td></tr><tr><td>Lösung</td><td>
Führen Sie offline Microsoft Defender Antivirus aus. Informationen dazu finden Sie im <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Artikel "Offline Microsoft Defender Antivirus".</a>
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508031
</th>
</tr><tr><td>Meldung</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>Mögliche Ursache</td>
<td>
Dieser Fehler weist darauf hin, dass Microsoft Defender Antivirus die aktuelle Version der Plattform nicht unterstützt und eine neue Version der Plattform erfordert. 
</td></tr><tr><td>Lösung</td><td>
Sie können Microsoft Defender Antivirus nur in Windows 10 verwenden. Für Windows 8, Windows 7 und Windows Vista können Sie <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>verwenden.<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>Die folgenden Fehlercodes werden bei internen Tests von Microsoft Defender Antivirus verwendet.

Wenn diese Fehler angezeigt werden, können Sie versuchen, [Definitionen](manage-updates-baselines-microsoft-defender-antivirus.md) zu aktualisieren und einen erneuten Scan direkt auf dem Endpunkt zu erzwingen.


<table> 
<tr>
<th colspan="3">Interne Fehlercodes</th>
</tr>
<tr>
<th><b>Fehlercode</b></th>
<th>Angezeigte Nachricht</th>
<th>Mögliche Ursache für Fehler und Lösung</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
Überprüfen Sie Ihre Internetverbindung, und führen Sie die Überprüfung dann erneut aus.
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E
</td>
<td rowspan="34">
Interner Fehler. Die Ursache ist nicht eindeutig definiert.
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
Interner Fehler. Er kann ausgelöst werden, wenn die Entfernung von Schadsoftware nicht erfolgreich ist. 
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
Interner Fehler. Er kann ausgelöst worden sein, wenn eine Überprüfung nicht abgeschlossen werden kann. 
</td>
</tr>
</table>

## <a name="related-topics"></a>Verwandte Themen

- [Bericht über Microsoft Defender Antivirus Schutz](report-monitor-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)