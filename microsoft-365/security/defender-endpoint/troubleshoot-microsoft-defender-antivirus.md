---
title: Microsoft Defender AV-Ereignis-IDs und Fehlercodes
description: Suchen der Ursachen und Lösungen für Microsoft Defender Antivirus-Ereignis-IDs und -Fehler
keywords: Ereignis, Fehlercode, Siem, Protokollierung, Problembehandlung, Wef, Windows-Ereignis-Weiterleitung
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f7e8d6428360e5fe45a377f3ed6611a76f0a7911
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765815"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Überprüfen von Ereignisprotokollen und Fehlercodes zur Problembehandlung bei Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Wenn sie ein Problem mit Microsoft Defender Antivirus haben, können Sie in den Tabellen in diesem Thema nach einem übereinstimmenden Problem und einer potenziellen Lösung suchen.

Die Tabellenliste:

- [Microsoft Defender Antivirus-Ereignis-IDs](#windows-defender-av-ids) (diese gelten für Windows 10 und Windows Server 2016)
- [Microsoft Defender Antivirus-Clientfehlercodes](#error-codes)
- [Interne Microsoft Defender Antivirus-Clientfehlercodes (die von Microsoft während der Entwicklung und beim Testen verwendet werden)](#internal-error-codes)

> [!TIP]
> Sie können auch die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren:
> 
> - In der Cloud zugestellter Schutz
> - Schnelles Lernen (einschließlich "Bei erster Sicht blockieren")
> - Potenziell unerwünschte Anwendungsblockierung

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender Antivirus-Ereignis-IDs

Microsoft Defender Antivirus zeichnet Ereignis-IDs im Windows-Ereignisprotokoll auf.

Sie können das Ereignisprotokoll direkt anzeigen, oder wenn Sie über ein Tool für die Sicherheitsinformationen und Ereignisverwaltung (SIEM) eines Drittanbieters verfügen, können Sie auch [Microsoft Defender Antivirus-Clientereignis-IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) verwenden, um bestimmte Ereignisse und Fehler von Ihren Endpunkten zu überprüfen.

In der Tabelle in diesem Abschnitt sind die wichtigsten Microsoft Defender Antivirus-Ereignis-IDs aufgeführt und, sofern möglich, Lösungsvorschläge zum Beheben oder Beheben des Fehlers. 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>So zeigen Sie ein Microsoft Defender Antivirus-Ereignis an

1.  Öffnen **Sie die Ereignisanzeige**.
2.  Erweitern Sie in der Konsolenstruktur **Anwendungen- und Dienstprotokolle,** dann **Microsoft**, dann **Windows** und **dann Windows Defender**.
3.  Doppelklicken Sie auf **Betriebs .**
4.  Zeigen Sie im Detailbereich die Liste der einzelnen Ereignisse an, um Ihr Ereignis zu finden.
5.  Klicken Sie auf das Ereignis, um bestimmte Details zu einem Ereignis im unteren Bereich unter den Registerkarten **Allgemein** und **Details** anzuzeigen.

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
<b>Eine Antischalwarescan wurde gestartet. </b>
</td>
</tr>
<tr>
<td >
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:<ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Scannen von Ressourcen: &lt; Gescannte Ressourcen (z. B. Dateien/Verzeichnisse/BHO). &gt; </dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; User &gt; </dt>
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
<b>Eine Antischalwarescan wurde abgeschlossen.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:<ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerscanzeit: &lt; Die Dauer eines &gt; Scans.</dt>
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
<b>Eine Antischalwarescan wurde beendet, bevor sie abgeschlossen wurde. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:<ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domain &gt; &amp; lt; &gt;</dt>
<dt>Benutzerscanzeit: &lt; Die Dauer eines &gt; Scans.</dt>
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
<b>Eine Antischalwarescan wurde angehalten. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:<ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; User&gt;</dt>
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
<b>Eine Antischalwarescan wurde fortgesetzt. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:<ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; User&gt;</dt>
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
<b>Fehler bei einer Antischalwarescan. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
<dl>
<dt>Scan-ID: &lt; ID-Nummer der relevanten Überprüfung. &gt; </dt> 
<dt> Scantyp: &lt; Scantyp &gt; , z. B.:<ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
</ul>
</dt>
<dt>Scanparameter: &lt; Scanparameter &gt; , z. B.:<ul>
<li>Vollständiger Scan</li>
<li>Schnellscan</li>
<li>Kundenscan</li>
</ul>
</dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Beim Antivirusclient ist ein Fehler aufgetreten, und die aktuelle Überprüfung wurde beendet. Die Überprüfung kann aufgrund eines clientseitigen Problems fehlschlagen. Dieser Ereignisdatensatz enthält die Scan-ID, den Scantyp (Microsoft Defender Antivirus, Antischa spyware, Antischansoftware), Scanparameter, den Benutzer, der die Überprüfung gestartet hat, den Fehlercode und eine Beschreibung des Fehlers.
So behandeln Sie dieses Ereignis:
<ol>
<li>Führen Sie den Scan erneut aus.</li>
<li>Wenn es auf dieselbe Weise fehlschlägt, wechseln Sie zur Microsoft <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Support-Website,</a>geben Sie die Fehlernummer in das Feld Suche ein, um nach dem Fehlercode zu suchen.</li>
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
<b>Das Antischalwaremodul hat Schadsoftware oder andere potenziell unerwünschte Software gefunden. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Concrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:<ul>
<li>Benutzer: Vom Benutzer initiiert</li>
<li>System: System initiiert</li>
<li>Echtzeit: In Echtzeit initiierte Echtzeitkomponente</li>
<li>IOAV: IE Downloads und Outlook Express Attachments initiiert</li>
<li>NIS: Netzwerkinspektionssystem</li>
<li>IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</li>
<li>Early Launch Antimalware (ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remote-Nachweis</li>
</ul>Antischalware Scan Interface (AMSI). Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>#A0 : &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>
<dt> &lt; &gt; Version</dt>des Definitionsmoduls:
<dt> &lt; Antischalwaremodulversion &gt; </dt>
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
<b>Die Antischalwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; Schweregrad , &gt; z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt> Aktion: &lt; Aktion &gt; , z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde isoliert</li>
<li>Remove: Die Ressource wurde gelöscht</li>
<li>Allow: Die Ressource konnte ausgeführt/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
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
<b>Die Antischalwareplattform hat versucht, eine Aktion zum Schutz Ihres Systems vor Schadsoftware oder anderer potenziell unerwünschter Software durchzuführen, die Aktion ist jedoch fehlgeschlagen.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software auf einen Fehler gestoßen. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Id des &lt; &gt; Bedrohungsnamens:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; Schweregrad , &gt; z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfadaktion: &gt; </dt> 
<dt> Aktion , &lt; &gt; z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde isoliert</li>
<li>Remove: Die Ressource wurde gelöscht</li>
<li>Allow: Die Ressource konnte ausgeführt/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
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
<b>Die Antischalwareplattform hat ein Element aus der Quarantäne wiederhergestellt. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat ein Element aus der Quarantäne wiederhergestellt. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
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
<b>Die Antischalwareplattform konnte ein Element nicht aus der Quarantäne wiederherstellen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Beim Versuch, ein Element aus der Quarantäne wiederherzustellen, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten. Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
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
<b>Die Antischalwareplattform hat ein Element aus der Quarantäne gelöscht. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat ein Element aus der Quarantäne gelöscht.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzersignaturversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt>Version des &lt; Antischalwaremoduls &gt; </dt>
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
<b>Die Antischalwareplattform konnte ein Element nicht aus der Quarantäne löschen.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Beim Versuch, ein Element aus der Quarantäne zu löschen, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.
Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; Dateipfad &gt; </dt>
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
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
<b>Die Antischalwareplattform hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software gelöscht.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software entfernt.
<dl>Zeit: Der Zeitpunkt, zu dem das Ereignis aufgetreten ist, z. B. 
<dt>wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um Korrekturzeit oder Infektionszeit handelt. Für diese werden sie speziell als Aktionszeit oder Erkennungszeit bezeichnet.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; User &gt; </dt>
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
Die Antischalwareplattform konnte den Verlauf von Schadsoftware und anderer potenziell unerwünschter Software nicht löschen.
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat einen Fehler beim Entfernen des Verlaufs von Schadsoftware und anderer potenziell unerwünschter Software festgestellt.
<dl>Zeit: Der Zeitpunkt, zu dem das Ereignis aufgetreten ist, z. B. 
<dt>wenn der Verlauf gelöscht wird. Dieser Parameter wird nicht in Bedrohungsereignissen verwendet, sodass keine Verwirrung darüber besteht, ob es sich um Korrekturzeit oder Infektionszeit handelt. Für diese werden sie speziell als Aktionszeit oder Erkennungszeit bezeichnet.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte. </dt> 
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
<b>Die Antischalwareplattform hat verdächtiges Verhalten erkannt.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat ein verdächtiges Verhalten erkannt.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Concrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:<ul>
<li>Benutzer: Vom Benutzer initiiert</li>
<li>System: System initiiert</li>
<li>Echtzeit: In Echtzeit initiierte Echtzeitkomponente</li>
<li>IOAV: IE Downloads und Outlook Express Attachments initiiert</li>
<li>NIS: Netzwerkinspektionssystem</li>
<li>IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</li>
<li>Early Launch Antimalware (ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remote-Nachweis</li>
</ul>Antischalware Scan Interface (AMSI). Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>#A0 : &lt; &gt; Statusbenutzer:</dt>
<dt>Domäne &lt; &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signatur-ID:</dt>
<dt>Aufzählungsvergleichsschweregrad.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; &gt; Antischalwaremodulversion</dt>
<dt>Fidelity Label:</dt>
<dt>Zieldateiname: &lt; Dateiname Name der &gt; Datei.</dt>
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
<b>Die Antischalwareplattform hat Schadsoftware oder andere potenziell unerwünschte Software erkannt. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat Schadsoftware oder andere potenziell unerwünschte Software erkannt.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Concrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:<ul>
<li>Benutzer: Vom Benutzer initiiert</li>
<li>System: System initiiert</li>
<li>Echtzeit: In Echtzeit initiierte Echtzeitkomponente</li>
<li>IOAV: IE Downloads und Outlook Express Attachments initiiert</li>
<li>NIS: Netzwerkinspektionssystem</li>
<li>IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</li>
<li>Early Launch Antimalware (ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remote-Nachweis</li>
</ul>Antischalware Scan Interface (AMSI). Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Signaturversion:</dt>
<dt> &lt; &gt; Version</dt>des Definitionsmoduls:
<dt> &lt; Antischalwaremodulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Microsoft Defender Antivirus kann diese Bedrohung anhalten und Routinemaßnahmen ergreifen. Wenn Sie die Bedrohung manuell entfernen möchten, klicken Sie auf der Microsoft Defender Antivirus-Schnittstelle auf <b>Clean Computer</b>.
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
<b>Die Antischalwareplattform hat eine Aktion ausgeführt, um Ihr System vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat Maßnahmen ergriffen, um diesen Computer vor Schadsoftware oder anderer potenziell unerwünschter Software zu schützen.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Concrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:<ul>
<li>Benutzer: Vom Benutzer initiiert</li>
<li>System: System initiiert</li>
<li>Echtzeit: In Echtzeit initiierte Echtzeitkomponente</li>
<li>IOAV: IE Downloads und Outlook Express Attachments initiiert</li>
<li>NIS: Netzwerkinspektionssystem</li>
<li>IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</li>
<li>Early Launch Antimalware (ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remote-Nachweis</li>
</ul>Antischalware Scan Interface (AMSI). Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt>Aktion , 
<dt> &lt; &gt; z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde isoliert</li>
<li>Remove: Die Ressource wurde gelöscht</li>
<li>Allow: Die Ressource konnte ausgeführt/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>Definitionsmoduls:
<dt> &lt; &gt; AntischalwaremodulVersion</dt> HINWEIS: Wenn Microsoft Defender Antivirus, Microsoft Security Essentials, Tool zum Entfernen bösartiger Software oder System Center Endpoint Protection eine Schadsoftware erkennt, werden die folgenden Systemeinstellungen und Dienste wiederhergestellt, die die Schadsoftware möglicherweise geändert hat:<ul>
<li>Standardeinstellung für Internet Explorer oder Microsoft Edge</li>
<li>Einstellungen für die Benutzerzugriffssteuerung</li>
<li>Chrome-Einstellungen</li>
<li>Startsteuerungsdaten</li>
<li>Registrierungseinstellungen für Regedit und Task Manager</li>
<li>Windows Update-, Background Intelligent Transfer Service- und Remoteprozedur-Anrufdienst</li>
<li>Windows-Betriebssystemdateien</li></ul>
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
Es ist keine Aktion erforderlich. Microsoft Defender Antivirus hat eine Bedrohung entfernt oder isoliert. 
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
<b>Die Antischalwareplattform hat versucht, eine Aktion zum Schutz Ihres Systems vor Schadsoftware oder anderer potenziell unerwünschter Software durchzuführen, die Aktion ist jedoch fehlgeschlagen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus ist beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software auf einen nicht kritischen Fehler gestoßen.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Concrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:<ul>
<li>Benutzer: Vom Benutzer initiiert</li>
<li>System: System initiiert</li>
<li>Echtzeit: In Echtzeit initiierte Echtzeitkomponente</li>
<li>IOAV: IE Downloads und Outlook Express Attachments initiiert</li>
<li>NIS: Netzwerkinspektionssystem</li>
<li>IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</li>
<li>Early Launch Antimalware (ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remote-Nachweis</li>
</ul>Antischalware Scan Interface (AMSI). Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt>Aktion , 
<dt> &lt; &gt; z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde isoliert</li>
<li>Remove: Die Ressource wurde gelöscht</li>
<li>Allow: Die Ressource konnte ausgeführt/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Microsoft Defender Antivirus konnte eine Aufgabe im Zusammenhang mit der Schadsoftwarebehebung nicht abschließen. Dies ist kein kritischer Fehler.
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
<b>Die Antischantischungsplattform ist beim Versuch, Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software zu ergreifen, auf einen kritischen Fehler gestoßen. Die Ereignisnachricht enthält weitere Details.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat einen kritischen Fehler beim Ergreifen von Maßnahmen gegen Schadsoftware oder andere potenziell unerwünschte Software festgestellt.<br/>Weitere Informationen finden Sie unter den folgenden Themen:
<dl>
<dt>Name: &lt; &gt;Bedrohungsname-ID:</dt>Schweregrad der
<dt> &lt; &gt; Bedrohungs-ID:</dt> 
<dt> &lt; &gt; Schweregrad , z. B.:<ul>
<li>Niedrig</li>
<li>Mittel</li>
<li>Hoch</li>
<li>Schwerwiegend</li>
</ul>
</dt>
<dt>Kategorie: &lt; &gt;Kategoriebeschreibung, z. B. jeder Bedrohungs- oder Schadsoftwaretyp.</dt> 
<dt>Pfad: &lt; &gt;</dt> 
<dt> DateipfadErkennungsherkunft: &lt; Erkennungsherkunft &gt; , z. B.:
<ul>
<li>Unbekannt</li>
<li>Lokaler Computer</li>
<li>Netzwerkfreigabe</li>
<li>Internet</li>
<li>Eingehender Datenverkehr</li>
<li>Ausgehender Datenverkehr</li>
</ul>
</dt>
<dt>Erkennungstyp: &lt; &gt; Erkennungstyp , z. B.:<ul>
<li>Heuristics</li>
<li>Generic</li>
<li>Concrete</li>
<li>Dynamische Signatur</li>
</ul>
</dt>
<dt>Erkennungsquelle: &lt; &gt; Erkennungsquelle, z. B.:<ul>
<li>Benutzer: Vom Benutzer initiiert</li>
<li>System: System initiiert</li>
<li>Echtzeit: In Echtzeit initiierte Echtzeitkomponente</li>
<li>IOAV: IE Downloads und Outlook Express Attachments initiiert</li>
<li>NIS: Netzwerkinspektionssystem</li>
<li>IEPROTECT: IE - IExtensionValidation; Dies schützt vor schädlichen Webseitensteuerelementen</li>
<li>Early Launch Antimalware (ELAM). Dies schließt Schadsoftware ein, die von der Startsequenz erkannt wird.</li>
<li>Remote-Nachweis</li>
</ul>Antischalware Scan Interface (AMSI). Wird hauptsächlich zum Schutz von Skripts (PS, VBS) verwendet, kann aber auch von Drittanbietern aufgerufen werden.
</dt>
<dt>UAC-Benutzer: &lt; Domain &gt; \& lt; &gt;Benutzername:</dt>
<dt>Prozess in der &lt; &gt; PID-Aktion:</dt>Aktion , 
<dt> &lt; &gt; z. B.:<ul>
<li>Clean: Die Ressource wurde bereinigt</li>
<li>Quarantäne: Die Ressource wurde isoliert</li>
<li>Remove: Die Ressource wurde gelöscht</li>
<li>Allow: Die Ressource konnte ausgeführt/vorhanden sein</li>
<li>Benutzerdefiniert: Benutzerdefinierte Aktion, die normalerweise eine aus dieser Liste von Aktionen ist, die der Benutzer angegeben hat</li>
<li>Keine Aktion: Keine Aktion</li>
<li>Block: Die Ausführung der Ressource wurde blockiert.</li>
</ul>
</dt>
<dt>Aktionsstatus: &lt; Beschreibung zusätzlicher &gt; Aktionen</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Der Microsoft Defender Antivirus-Client ist aufgrund kritischer Probleme auf diesen Fehler gestoßen. Der Endpunkt ist möglicherweise nicht geschützt. Überprüfen Sie die Fehlerbeschreibung, und führen Sie dann die unten aufgeführten Schritte <b>für die Benutzeraktion</b> aus.
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
Aktualisieren Sie die Definitionen, und vergewissern Sie sich, dass die Entfernung erfolgreich war.
</td>
</tr>
<tr>
<td>
<b>Clean</b>
</td>
<td>
Aktualisieren Sie die Definitionen, und vergewissern Sie sich, dass die Korrektur erfolgreich war.
</td>
</tr>
<tr>
<td>
<b>Quarantäne</b>
</td>
<td>
Aktualisieren Sie die Definitionen, und überprüfen Sie, ob der Benutzer über die Berechtigung zum Zugriff auf die erforderlichen Ressourcen verfügt.
</td>
</tr>
<tr>
<td>
<b>Zulassen</b>
</td>
<td>
Stellen Sie sicher, dass der Benutzer über die Berechtigung zum Zugriff auf die erforderlichen Ressourcen verfügt.
</td>
</tr>
</table>

Wenn dieses Ereignis weiterhin besteht:<ol>
<li>Führen Sie den Scan erneut aus.</li>
<li>Wenn es auf dieselbe Weise fehlschlägt, wechseln Sie zur Microsoft <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Support-Website,</a>geben Sie die Fehlernummer in das Feld Suche ein, um nach dem Fehlercode zu suchen.</li>
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
Der Microsoft Defender Antivirus-Client ist in einem fehlerfreien Zustand ausgeführt.
<dl>
<dt>Aktuelle Plattformversion: &lt; Aktuelle Plattformversion &gt; </dt>
<dt>Bedrohungsressourcenpfad: &lt; &gt; Pfadhashes:</dt>
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
<b>Wenn Die Antischalwareplattform den Status einer Überwachungsplattform meldet, weist dieses Ereignis darauf hin, dass die Antischalwareplattform ausgeführt wird und sich in einem fehlerfreien Zustand befindet. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Der Microsoft Defender Antivirus-Client ist in einem fehlerfreien Zustand ausgeführt.
<dl>
<dt>Plattformversion: &lt; Signaturversion &gt; der aktuellen</dt>
<dt>Plattformversion: &lt; Version &gt; des Definitionsmoduls:</dt>
<dt> &lt; Antischalwaremodulversion &gt; </dt>
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
<b>Endpoint Protection-Clientinte health report (Time in UTC) </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Antivirusclientinte health report.
<dl>
<dt>Plattformversion: &lt; &gt;</dt>Aktuelle Plattformversion
<dt>Modulversion: &lt; &gt; </dt>Antischalwaremodulversion Netzwerk Echtzeitprüfungsmodulversion: Version des
<dt> &lt; Netzwerk-Realtime-Inspektionsmoduls &gt; </dt>Antivirussignaturversion:
<dt> &lt; &gt; Antivirussignaturversion</dt>
<dt>Anspoywaresignaturversion Netzwerk &lt; &gt; </dt>Echtzeitprüfung Signaturversion: Network
<dt> &lt; Realtime Inspection &gt; </dt>Signature Version
<dt>RTP state: &lt; Realtime protection state &gt; (Enabled or Disabled)</dt>
<dt>OA state: On Access state &lt; &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: Status "IE Downloads and Outlook Express &lt; Attachments" (Aktiviert oder &gt; Deaktiviert):</dt>Status der Verhaltensüberwachung (Aktiviert oder
<dt> &lt; &gt; Deaktiviert)</dt>Antivirussignaturalter: Alter der Antivirussignatur
<dt> &lt; &gt; (in Tagen)</dt>
<dt>Antisywaresignaturalter: Alter der Ansywaresignatur &lt; &gt; (in Tagen)</dt>Alter der letzten Schnellscan: Alter der letzten Schnellscan
<dt> &lt; &gt; (in Tagen)</dt>Alter der letzten vollständigen Überprüfung: Alter der letzten vollständigen Überprüfung
<dt> &lt; &gt; (in Tagen)</dt>Erstellungszeit der Antivirussignatur:
<dt>? &lt; Erstellungszeit für &gt; AntivirensignaturEntschmieren</dt>
<dt>der Signatur antispyware: ? &lt; Erstellungszeit der &gt; Ansywaresignatur</dt>letzte
<dt>Schnellscanstartzeit: ? &lt; Startzeit der &gt; letzten Schnellscans</dt>
<dt>Letzte Endzeit des Schnellscans: ? &lt; &gt;Endzeit</dt>der letzten Schnellscans Letzte Schnellscanquelle: Quelle der letzten Schnellscans (0 = Scan&#39;wurde nicht
<dt> &lt; ausgeführt, 1 = Benutzer &gt; initiiert, 2 = System initiiert)</dt>Letzte vollständige Scanstartzeit:
<dt>? &lt; Startzeit der &gt; letzten vollständigen Überprüfung</dt>
<dt>Letzte vollständige Scanendezeit: ? &lt; &gt;Endzeit</dt>der letzten vollständigen Überprüfung Letzte vollständige Scanquelle: Letzte vollständige Scanquelle
<dt> &lt; (0 = Scan wurde&#39;nicht &gt; ausgeführt, 1 = Benutzer initiiert, 2 = System initiiert)</dt> 
<dt> Produktstatus: Zur internen Problembehandlung
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
<b>Die Antischalwaredefinitionen wurden erfolgreich aktualisiert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Antivirussignaturversion wurde aktualisiert.
<dl>
<dt>Aktuelle Signaturversion: &lt; Aktuelle &gt; Signaturversion</dt>
<dt>Vorherige Signaturversion: &lt; &gt; Signaturtyp</dt>der vorherigen 
<dt> Signaturversion: &lt; Signaturtyp , &gt; z. B.: <ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder Vollständig oder Delta.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; Aktuelle &gt; </dt>
<dt>Modulversion des Benutzers: &lt; Aktuelle Modulversion &gt; </dt>Vorherige
<dt>Modulversion: &lt; Frühere Modulversion &gt; </dt>
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
<b>Fehler beim Sicherheitsintelligenzupdate. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Bei Microsoft Defender Antivirus ist ein Fehler beim Aktualisieren von Signaturen aufgetreten.
<dl>
<dt>Neue Security Intelligence-Version: &lt; Neue Versionsnummer &gt; </dt>
<dt>Frühere Sicherheitsintelligenzversion: &lt; Vorherige &gt; </dt>Version 
<dt> Updatequelle: &lt; Updatequelle , &gt; z. B.:
<ul>
<li>Ordner für Sicherheitsintelligenzupdates</li>
<li>Interner Updateserver für Sicherheitsintelligenz</li>
<li>Microsoft Update Server</li>
<li>Dateifreigabe</li>
<li>Microsoft Center zum Schutz vor Malware (MMPC)</li>
</ul>
</dt>
<dt>Updatephase: &lt; Updatephase &gt; , z. B.:
<ul>
<li>Suchen</li>
<li>Herunterladen</li>
<li>Installieren</li>
</ul>
</dt>
<dt>Quellpfad: Dateifreigabename für universelle Benennungskonvention (Universal Naming Convention, UNC), Servername für Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Signaturtyp: &lt; Signaturtyp &gt; , z. B.: <ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Updatetyp: &lt; Updatetyp &gt; , entweder Vollständig oder Delta.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; Aktuelle &gt; </dt>
<dt>Modulversion des Benutzers: &lt; Aktuelle Modulversion &gt; </dt>
<dt>Vorherige &lt; &gt; Modulversion:</dt>Frühere Modulversion
<dt>Fehlercode: &lt; Fehlercode Ergebniscode, der dem &gt; Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Dieser Fehler tritt auf, wenn bei der Aktualisierung von Definitionen ein Problem auftritt.
So behandeln Sie dieses Ereignis:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aktualisieren Sie Definitionen,</a> und erzwingen Sie einen erneuten Scan direkt auf dem Endpunkt.</li>
<li>Weitere Informationen zu diesem Fehler finden Sie in den Einträgen in der Datei %Windir%\WindowsUpdate.log.</li>
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
<b>Das Antischalwaremodul wurde erfolgreich aktualisiert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Version des Microsoft Defender Antivirus-Moduls wurde aktualisiert.
<dl>
<dt>Aktuelle Modulversion: &lt; Aktuelle Modulversion &gt; </dt>
<dt>Vorherige Modulversion: &lt; &gt; Modultyp</dt>der vorherigen Modulversion: Modultyp , entweder Antischalwaremodul oder
<dt> &lt; &gt; Netzwerkinspektionssystemmodul.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; User &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand. Dieses Ereignis wird gemeldet, wenn das Antischalwaremodul erfolgreich aktualisiert wird.
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
<b>Fehler beim Update des Antischalwaremoduls. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Beim Versuch, das Modul zu aktualisieren, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.
<dl>
<dt>Neue Modulversion:</dt>
<dt>Frühere Modulversion: &lt; &gt; Modultyp</dt>der vorherigen Modulversion: Modultyp , entweder Antischalwaremodul
<dt>oder &lt; &gt; Netzwerkinspektionssystemmodul.</dt> 
<dt>Benutzer: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Benutzerfehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Fehler beim Microsoft Defender Antivirus-Clientupdate. Dieses Ereignis tritt auf, wenn der Client sich selbst nicht aktualisieren kann. Dieses Ereignis ist in der Regel auf eine Unterbrechung der Netzwerkverbindung während eines Updates bedingt.
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
<b>Beim Laden von Antischalwaredefinitionen ist ein Problem vorhanden. Das Antischalwaremodul versucht, den zuletzt bekannten guten Satz von Definitionen zu laden.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat einen Fehler beim Laden von Signaturen festgestellt und versucht, zu einem bekannten Satz von Signaturen zurück zu kehren.
<dl>
<dt>Signaturen versucht:</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Signaturversion: &lt; Version &gt; des</dt>
<dt>Definitionsmoduls: &lt; Antischalwaremodulversion &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Der Microsoft Defender Antivirus-Client hat versucht, die neueste Definitionsdatei herunterzuladen und zu installieren, und es ist ein Fehler fehlgeschlagen. Dieser Fehler kann auftreten, wenn auf dem Client beim Laden der Definitionen ein Fehler auftritt oder wenn die Datei beschädigt ist. Microsoft Defender Antivirus versucht, zu einem bekannten Satz von Definitionen zurück zu kehren.
So behandeln Sie dieses Ereignis:
<ol>
<li>Starten Sie den Computer neu, und versuchen Sie es erneut.</li>
<li>Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence-Website herunter.</a>
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
<b>Das Antischalwaremodul konnte nicht geladen werden, da die Antischalwareplattform veraltet ist. Die Antischalwareplattform wird das zuletzt bekannte gute Antischalwaremodul laden und versuchen, es zu aktualisieren.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus konnte das Antischalwaremodul nicht laden, da die aktuelle Plattformversion nicht unterstützt wird. Microsoft Defender Antivirus kehrt zum letzten bekannten Modul zurück, und es wird versucht, ein Plattformupdate zu installieren.
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
<b>Fehler beim Plattformupdate. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Beim Versuch, die Plattform zu aktualisieren, ist ein Fehler bei Microsoft Defender Antivirus aufgetreten.
<dl>
<dt>Aktuelle Plattformversion: &lt; Fehlercode &gt; der aktuellen</dt>
<dt>Plattformversion: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
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
<b>Die Plattform ist bald veraltet. Laden Sie die neueste Plattform herunter, um den aktuellen Schutz auf dem neuesten Stand zu halten.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus benötigt in Kürze eine neuere Plattformversion, um zukünftige Versionen des Antischammungsmoduls zu unterstützen. Laden Sie die neueste Microsoft Defender Antivirus-Plattform herunter, um den bestmöglichen Schutz zu gewährleisten.
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
<b>Das Antischalwaremodul verwendet den dynamischen Signaturdienst, um zusätzliche Definitionen zu erhalten. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat <i>den Dynamischen Signaturdienst verwendet,</i> um zusätzliche Signaturen abzurufen, um Ihren Computer zu schützen.
<dl>
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen</dt> 
<dt> Signaturversion: &lt; &gt; Signaturtyp , z. B.: <ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle &gt; Modulversion</dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp , &gt; z. B.:
<ul>
<li>Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
<li>Dauer</li>
</ul>
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Versionsnummer &gt; </dt>Dynamic Signature Compilation
<dt> &lt; Timestamp: Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; z. B.:
<ul>
<li>VDM-Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
</ul>
</dt>
<dt>Persistenzgrenzwert: Persistenzgrenzwert der Fastpathsignatur.</dt>
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
<b>Der dynamische Signaturdienst hat die veralteten dynamischen Definitionen gelöscht. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat <i>den dynamischen Signaturdienst verwendet,</i> um veraltete Signaturen zu verwerfen.
<dl>
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen</dt> 
<dt> Signaturversion: &lt; &gt; Signaturtyp , z. B.: <ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Aktuelle Modulversion: &lt; Aktuelle &gt; Modulversion</dt> 
<dt> Dynamischer Signaturtyp: Dynamischer &lt; Signaturtyp , &gt; z. B.:
<ul>
<li>Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
<li>Dauer</li>
</ul>
</dt>
<dt>Persistenzpfad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:
<ul>
<li>VDM-Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
</ul>
</dt>
<dt>Persistenzgrenzwert: Persistenzgrenzwert der Fastpathsignatur.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Es ist keine Aktion erforderlich. Der Microsoft Defender Antivirus-Client befindet sich in einem fehlerfreien Zustand. Dieses Ereignis wird gemeldet, wenn der dynamische Signaturdienst veraltete dynamische Definitionen erfolgreich löscht.
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
<b>Das Antischantischungsmodul ist beim Versuch, den dynamischen Signaturdienst zu verwenden, auf einen Fehler gestoßen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat einen Fehler beim Verwenden des <i>Dynamischen Signaturdiensts festgestellt.</i>
<dl>
<dt>Aktuelle Signaturversion: &lt; Signaturtyp &gt; der aktuellen</dt> 
<dt> Signaturversion: &lt; &gt; Signaturtyp , z. B.: <ul>
<li>Antivirus</li>
<li>Ansyware</li>
<li>Antischalware</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Aktuelle Modulversion: &lt; Fehlercode &gt; der aktuellen</dt>
<dt>Modulversion: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
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
<dt>Dynamic Signature Version: &lt; Versionsnummer &gt; </dt>Dynamic Signature Compilation
<dt> &lt; Timestamp: Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; z. B.:
<ul>
<li>VDM-Version</li>
<li>Zeitstempel</li>
<li>Keine Begrenzung</li>
</ul>
</dt>
<dt>Persistenzgrenzwert: Persistenzgrenzwert der Fastpathsignatur.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Überprüfen Sie ihre Internetverbindungseinstellungen.
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
<b>Der dynamische Signaturdienst hat alle dynamischen Definitionen gelöscht. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat alle <i>Signaturen des dynamischen Signaturdiensts</i> verworfen.
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
<b>Das Antischalwaremodul hat eine clean-Datei heruntergeladen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat eine neue Datei heruntergeladen.
<dl>
<dt>Dateiname: &lt; Dateiname &gt; Name der Datei.</dt> 
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
<b>Fehler beim Herunterladen einer sauberen Datei durch das Antischalwaremodul. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Bei Microsoft Defender Antivirus ist ein Fehler beim Herunterladen einer sauberen Datei aufgetreten.
<dl>
<dt>Dateiname: &lt; Dateiname &gt; Name der Datei.</dt> 
<dt>Aktuelle Signaturversion: &lt; Aktuelle Signaturversion &gt; </dt>
<dt>Aktuelle Modulversion: Aktuelle &lt; Modulversion &gt; </dt>
<dt>Fehlercode: &lt; Fehlercode Ergebniscode, der dem &gt; Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Überprüfen Sie ihre Internetverbindungseinstellungen.
Beim Microsoft Defender Antivirus-Client ist ein Fehler aufgetreten, wenn er den dynamischen Signaturdienst zum Herunterladen der neuesten Definitionen für eine bestimmte Bedrohung verwendet. Dieser Fehler wird wahrscheinlich durch ein Netzwerkverbindungsproblem verursacht. 
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
<b>Das Antischadwaremodul wurde heruntergeladen und ist so konfiguriert, dass es beim nächsten Systemneustart offline ausgeführt wird.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat den Offline antivirus heruntergeladen und so konfiguriert, dass er beim nächsten Neustart ausgeführt wird.
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
<b>Das Antischadwaremodul konnte einen Offlinescan nicht herunterladen und konfigurieren.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Bei Microsoft Defender Antivirus ist ein Fehler beim Herunterladen und Konfigurieren von Offline antivirus aufgetreten.
<dl>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
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
<b>Die Antischalwareunterstützung für diese Betriebssystemversion wird bald beendet. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Unterstützung für Ihr Betriebssystem läuft in Kürze ab. Das Ausführen von Microsoft Defender Antivirus auf einem Betriebssystem ohne Support ist keine geeignete Lösung zum Schutz vor Bedrohungen.
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
<b>Die Antischalwareunterstützung für dieses Betriebssystem wurde beendet. Sie müssen das Betriebssystem aktualisieren, damit die Unterstützung fortgesetzt wird. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Unterstützung für Ihr Betriebssystem ist abgelaufen. Das Ausführen von Microsoft Defender Antivirus auf einem Betriebssystem ohne Support ist keine geeignete Lösung zum Schutz vor Bedrohungen.
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
<b>Das Antischalwaremodul unterstützt dieses Betriebssystem nicht mehr und schützt Ihr System nicht mehr vor Schadsoftware. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Unterstützung für Ihr Betriebssystem ist abgelaufen. Microsoft Defender Antivirus wird auf Ihrem Betriebssystem nicht mehr unterstützt, funktioniert nicht mehr und schützt nicht vor Schadsoftwarebedrohungen.
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
Microsoft Defender Antivirus Real-Time Protection-Funktion ist auf einen Fehler und einen Fehler gestoßen.
<dl>
<dt>Feature: &lt; Feature &gt; , z. B.:
<ul>
<li>On Access</li>
<li>Internet Explorer-Downloads und Microsoft Outlook Express-Anlagen</li>
<li>Verhaltensüberwachung</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt> 
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus echtzeitschutz ein Feature neu gestartet hat.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Starten Sie das System neu, und führen Sie dann einen vollständigen Scan aus,&#39;das System möglicherweise einige Zeit nicht geschützt war.
Der Microsoft Defender Antivirus-Client&#39;Echtzeitschutzfunktion auf einen Fehler gestoßen, da einer der Dienste nicht gestartet werden konnte. Wenn darauf eine 3007-Ereignis-ID folgt, war der Fehler temporär, und der Antischalwareclient wurde nach dem Fehler wiederhergestellt. 
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
<b>Echtzeitschutz nach einem Fehler wiederhergestellt. Es wird empfohlen, eine vollständige Systemscan ausführen, wenn dieser Fehler angezeigt wird. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus Real-time Protection hat ein Feature neu gestartet. Es wird empfohlen, dass Sie eine vollständige Systemscan ausführen, um Elemente zu erkennen, die während des Herunters dieses Agents möglicherweise verpasst wurden.
<dl>
<dt>Feature: &lt; Feature &gt; , z. B.:
<ul>
<li>On Access</li>
<li>IE-Downloads und Outlook Express-Anlagen</li>
<li>Verhaltensüberwachung</li>
<li>Netzwerkinspektionssystem</li>
</ul>
</dt>
<dt>Grund: Der Grund, warum Microsoft Defender Antivirus echtzeitschutz ein Feature neu gestartet hat.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Das Echtzeitschutzfeature wurde neu gestartet. Wenn dieses Ereignis erneut eintritt, wenden Sie sich <a href="https://go.microsoft.com/fwlink/?LinkId=215491">an den technischen Support von Microsoft.</a> 
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
<b>Echtzeitschutz ist aktiviert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Echtzeitschutzprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.
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
Die Echtzeitschutzprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software wurde deaktiviert. 
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
Die Konfiguration von Microsoft Defender Antivirus-Echtzeitschutzfeatures hat sich geändert.
<dl>
<dt>Feature: &lt; Feature &gt; , z. B.:
<ul>
<li>On Access</li>
<li>IE-Downloads und Outlook Express-Anlagen</li>
<li>Verhaltensüberwachung</li>
<li>Netzwerkinspektionssystem</li>
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
<b>Die Konfiguration der Antischalwareplattform wurde geändert.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Microsoft Defender Antivirus-Konfiguration hat sich geändert. Wenn dies ein unerwartetes Ereignis ist, sollten Sie die Einstellungen überprüfen, da dies das Ergebnis von Schadsoftware sein kann.
<dl>
<dt>Alter Wert: &lt; Alter Wert Zahl &gt; Alter Antiviruskonfigurationswert.</dt> 
<dt>Neuer Wert: &lt; Neue Wertnummer &gt; Neuer Antiviruskonfigurationswert.</dt>
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
<b>Beim Antischantischungsmodul ist ein Fehler aufgetreten und ein Fehler aufgetreten.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Das Microsoft Defender Antivirus-Modul wurde aufgrund eines unerwarteten Fehlers beendet.
<dl>
<dt>Fehlertyp: &lt; Fehlertyp &gt; , z. B.: Crash or Hang</dt>Exception
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
<li>Geben Sie für Antischansoftware, Antivirensoftware und Spyware an einer Eingabeaufforderung mit erhöhten Rechten <b>net stop msmpsvc</b>ein, und geben Sie dann <b>net start msmpsvc</b> ein, um das Antischantischungsmodul neu zu starten.</li>
<li>Geben <i></i>Sie für das Netzwerkinspektionssystem an einer Eingabeaufforderung mit erhöhten Rechten net <b>start nissrv</b>ein, und geben Sie dann <b>net start nissrv</b> ein, um das <i>Netzwerkinspektionssystemmodul</i> mithilfe der NiSSRV.exe neu zu starten.
</li>
</ul>
</li>
<li>Wenn es auf dieselbe Weise fehlschlägt, suchen Sie den Fehlercode, indem Sie <b></b> auf die <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-Website</a> zugreifen und die Fehlernummer im Feld Suchen eingeben, und wenden Sie sich an <a href="https://go.microsoft.com/fwlink/?LinkId=215491">den technischen Support</a>von Microsoft.</li>
</ol>
</td>
</tr>
<tr>
<td>
Benutzeraktion:
</td>
<td >
Das Microsoft Defender Antivirus-Clientmodul wurde aufgrund eines unerwarteten Fehlers beendet.
So behandeln Sie dieses Ereignis:
<ol>
<li>Führen Sie den Scan erneut aus.</li>
<li>Wenn es auf dieselbe Weise fehlschlägt, wechseln Sie zur Microsoft <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Support-Website,</a>geben Sie die Fehlernummer in das Feld Suche ein, um nach dem Fehlercode zu suchen.</li>
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
Die Überprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software wurde aktiviert.
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
Die Überprüfung von Microsoft Defender Antivirus auf Schadsoftware und andere potenziell unerwünschte Software ist deaktiviert.
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
<b>Die Überprüfung auf Viren ist aktiviert.</b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Überprüfung von Microsoft Defender Antivirus auf Viren wurde aktiviert. 
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
<b>Die Überprüfung auf Viren ist deaktiviert. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Überprüfung von Microsoft Defender Antivirus auf Viren ist deaktiviert. 
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
<b>Die Antischalwareplattform läuft bald ab. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Microsoft Defender Antivirus hat eine Nachfrist eingegeben und läuft bald ab. Nach ablaufen deaktiviert dieses Programm den Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software.
<dl>
<dt>Ablaufgrund: Der Grund, warum Microsoft Defender Antivirus abläuft.</dt> 
<dt>Ablaufdatum: Das Datum, an dem Microsoft Defender Antivirus abläuft.</dt>
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
<b>Die Antischalwareplattform ist abgelaufen. </b>
</td>
</tr>
<tr>
<td>
Beschreibung:
</td>
<td >
Die Kulanzfrist für Microsoft Defender Antivirus ist abgelaufen. Der Schutz vor Viren, Spyware und anderer potenziell unerwünschter Software ist deaktiviert.
<dl>
<dt>Ablaufgrund:</dt>
<dt>Ablaufdatum: </dt> 
<dt>Fehlercode: &lt; Fehlercode &gt; Ergebniscode, der dem Bedrohungsstatus zugeordnet ist. Standard-HRESULT-Werte.</dt> 
<dt>Fehlerbeschreibung: &lt; Fehlerbeschreibung &gt; Beschreibung des Fehlers.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus-Clientfehlercodes Wenn Microsoft Defender Antivirus Probleme hat, erhalten Sie in der Regel einen Fehlercode, der Ihnen bei der Problembehandlung hilft. Meistens bedeutet ein Fehler, dass beim Installieren eines Updates ein Problem aufgetreten ist.
Dieser Abschnitt enthält die folgenden Informationen zu Microsoft Defender Antivirus-Clientfehlern.
-   Der Fehlercode -   Der mögliche Grund für den Fehler Hinweise zu den jetzt zu -   tunen

Verwenden Sie die Informationen in diesen Tabellen, um Bei der Problembehandlung von Microsoft Defender Antivirus-Fehlercodes zu helfen.


<table> 
<tr>
<th colspan="2">Fehlercode: 0x80508007</th>
</tr>
<tr>
<td>Message</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
Möglicher Grund
</td>
<td>
Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Arbeitsspeicher vorhanden ist. 
</td>
</tr>
<tr>
<td>Lösung</td>
<td>
<ol>
<li>Überprüfen Sie den verfügbaren Speicher auf Ihrem Gerät.</li>
<li>Schließen Sie alle nicht verwendeten Anwendungen, die ausgeführt werden, um Speicherplatz auf Ihrem Gerät frei zu erhalten.</li>
<li>Starten Sie das Gerät neu, und führen Sie den Scan erneut aus. 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x8050800C</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass möglicherweise ein Problem mit Ihrem Sicherheitsprodukt vor liegt.
</td>
</tr><tr><td>Lösung</td><td>
<ol>
<li>Aktualisieren Sie die Definitionen. Eine der beiden:<ol>
<li>Klicken Sie <b>auf der</b> Registerkarte <b>Update</b> in Microsoft Defender Antivirus auf die Schaltfläche Definitionen aktualisieren. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>Oder:
</li>
<li>Laden Sie die neuesten Definitionen von der <a href="https://aka.ms/wdsi">Microsoft Security Intelligence-Website herunter.</a>
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
</tr><tr><td>Message</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler weist darauf hin, dass möglicherweise ein Modulkonfigurationsfehler aufgetreten ist. Häufig ist dies mit Eingabedaten verbunden, die eine einwandfreie Funktionsweise des Moduls nicht zulassen. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x805080211
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler weist darauf hin, dass Microsoft Defender Antivirus eine Bedrohung nicht unter Quarantäne stellen konnte. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508022
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass ein Neustart erforderlich ist, um die Bedrohungsentfernung abschließen zu können. 
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler weist darauf hin, dass die Bedrohung möglicherweise nicht mehr auf den Medien vorhanden ist, oder Schadsoftware hält Sie möglicherweise am Scannen Ihres Geräts ab. 
</tr><tr><td>Lösung
</td>
<td>
Führen Sie <a href="https://www.microsoft.com/security/scanner/default.aspx">den Microsoft Safety Scanner</a> aus, und aktualisieren Sie die Sicherheitssoftware, und versuchen Sie es erneut. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508024 </th></tr>
<tr>
<td>Message</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass möglicherweise eine vollständige Systemscan erforderlich ist. 
</td></tr>
<tr>
<td>Lösung</td><td>
Führen Sie eine vollständige Systemscan aus. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508025
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass manuelle Schritte erforderlich sind, um die Bedrohungsentfernung abschließen zu können. 
</td></tr><tr><td>Lösung</td><td>
Führen Sie die manuellen Korrekturschritte aus, die in <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">der Microsoft Malware Protection-Enzyklopädie beschrieben sind.</a> Sie finden einen bedrohungsspezifischen Link im Ereignisverlauf.<br/></td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508026
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass das Entfernen innerhalb des Containertyps möglicherweise nicht unterstützt wird. 
</td></tr><tr><td>Lösung</td><td>
Microsoft Defender Antivirus ist nicht in der Lage, im Archiv erkannte Bedrohungen zu beabwehren. Erwägen Sie, die erkannten Ressourcen manuell zu entfernen. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508027
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler weist darauf hin, dass das Entfernen niedriger und mittlerer Bedrohungen möglicherweise deaktiviert ist. 
</td></tr><tr><td>Lösung</td><td>
Überprüfen Sie die erkannten Bedrohungen, und beheben Sie sie nach Bedarf. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508029
</th>
</tr><tr><td>Message</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass ein erneutes Scannen der Bedrohung erforderlich ist. 
</td></tr><tr><td>Lösung</td><td>
Führen Sie eine vollständige Systemscan aus. 
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508030
</th>
</tr><tr><td>Message</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass eine Offlinescan erforderlich ist. 
</td></tr><tr><td>Lösung</td><td>
Führen Sie Microsoft Defender Antivirus offline aus. Informationen dazu finden Sie im <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Microsoft Defender Antivirus-Offlineartikel</a>.
</td>
</tr>
<tr>
<th colspan="2">Fehlercode: 0x80508031
</th>
</tr><tr><td>Message</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>Möglicher Grund</td>
<td>
Dieser Fehler gibt an, dass Microsoft Defender Antivirus die aktuelle Version der Plattform nicht unterstützt und eine neue Version der Plattform erfordert. 
</td></tr><tr><td>Lösung</td><td>
Sie können Microsoft Defender Antivirus nur unter Windows 10 verwenden. Für Windows 8 Windows 7 und Windows Vista können Sie <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection verwenden.</a><br/></td>
</tr>
</table>

<a id="internal-error-codes"></a> Die folgenden Fehlercodes werden bei internen Tests von Microsoft Defender Antivirus verwendet.

Wenn diese Fehler angezeigt werden, können Sie versuchen, Definitionen [zu](manage-updates-baselines-microsoft-defender-antivirus.md) aktualisieren und einen erneuten Scan direkt auf dem Endpunkt zu erzwingen.


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
Überprüfen Sie Ihre Internetverbindung, und führen Sie den Scan erneut aus.
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
Interner Fehler. Die Ursache ist nicht klar definiert.
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
Interner Fehler. Es kann ausgelöst werden, wenn die Schadsoftwareentfernung nicht erfolgreich ist. 
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
Interner Fehler. Es kann ausgelöst worden sein, wenn eine Überprüfung nicht abgeschlossen wurde. 
</td>
</tr>
</table>

## <a name="related-topics"></a>Verwandte Themen

- [Bericht zum Schutz von Microsoft Defender Antivirus](report-monitor-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)