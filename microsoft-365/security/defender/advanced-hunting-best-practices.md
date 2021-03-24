---
title: Bewährte Methoden für erweiterte Suchabfragen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie schnelle, effiziente und fehlerfreie Suchabfragen für Bedrohungen mit erweiterter Suche erstellen.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID, optimieren, bewährte Methode, analysieren, beitreten, zusammenfassen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 53ec8146080e88b913de1f58d16750ffa766a1b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063591"
---
# <a name="advanced-hunting-query-best-practices"></a>Bewährte Methoden für Erweiterte Suchanfragen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Wenden Sie diese Empfehlungen an, um Ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden. Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Verstehen von CPU-Ressourcenkontingenten
Je nach Größe hat jeder Mandant Zugriff auf eine bestimmte Menge von CPU-Ressourcen, die für die Ausführung erweiterter Suchabfragen zugewiesen sind. Ausführliche Informationen zu verschiedenen Dienstbeschränkungen finden Sie [unter erweiterte Kontingente und Verwendungsparameter.](advanced-hunting-limits.md)

Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und die Optimierungsleitfaden in diesem Artikel anwenden, um Unterbrechungen aufgrund von Überschreitungen von Kontingenten oder Verwendungsparametern zu minimieren.

## <a name="general-optimization-tips"></a>Allgemeine Optimierungstipps

- **Größe neuer Abfragen**– Wenn Sie vermuten, dass eine Abfrage einen großen Ergebnissatz zurücksennt, bewerten Sie ihn zuerst mithilfe des [Count-Operators](/azure/data-explorer/kusto/query/countoperator). Verwenden [Sie Grenzwert](/azure/data-explorer/kusto/query/limitoperator) oder `take` synonym, um große Ergebnissätze zu vermeiden.
- **Frühes** Anwenden von Filtern – Wenden Sie Zeitfilter und andere Filter an, um den Datensatz zu reduzieren, insbesondere vor der Verwendung von Transformations- und Analysefunktionen, z. B. [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Im folgenden Beispiel wird die Analysefunktion [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem Filteroperatoren die Anzahl der Datensätze reduziert haben.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Enthält Beats –** Verwenden Sie den Operator anstelle von , um zu vermeiden, dass Teilzeichenfolgen in Wörtern unnötig `has` durchsucht `contains` werden. [Informationen zu Zeichenfolgenoperatoren](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **In bestimmten Spalten suchen**– Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen in allen Spalten zu ausführen. Verwenden Sie nicht, `*` um alle Spalten zu überprüfen.
- **Hoch-/Kleinschreibung –** Die Suche nach Kleinschreibung ist spezifischer und in der Regel performanter. Die Namen von Zeichenfolgenoperatoren, die bei [der Kleinschreibung](/azure/data-explorer/kusto/query/datatypes-string-operators)beachtet werden, z. `has_cs` B. und `contains_cs` , enden im Allgemeinen mit `_cs` . Sie können auch den Gleichheitsoperator für die Zwischenschreibung anstelle `==` von `=~` verwenden.
- **Analysieren, nicht extrahieren –** Verwenden Sie [](/azure/data-explorer/kusto/query/parseoperator) nach Möglichkeit den Parse-Operator oder eine Analysefunktion wie [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Vermeiden Sie `matches regex` den Zeichenfolgenoperator oder die [extract()-Funktion,](/azure/data-explorer/kusto/query/extractfunction)die beide regulären Ausdruck verwenden. Reservieren Sie die Verwendung regulärer Ausdrücke für komplexere Szenarien. [Weitere Informationen zu Analysefunktionen](#parse-strings)
- **Filtern von Tabellen ohne Ausdrücke**– Filtern Sie nicht nach einer berechneten Spalte, wenn Sie nach einer Tabellenspalte filtern können.
- **Keine 3-Zeichen-Begriffe**– Vermeiden Sie das Vergleichen oder Filtern mit Begriffen mit drei oder weniger Zeichen. Diese Begriffe werden nicht indiziert, und für deren Übereinstimmung sind mehr Ressourcen erforderlich.
- **Projekt selektiv –** Machen Sie Ihre Ergebnisse leichter zu verstehen, indem Sie nur die benötigten Spalten projiziert. Das Projiziert bestimmter Spalten vor dem Ausführen von [Verknüpfungsvorgängen](/azure/data-explorer/kusto/query/joinoperator) oder ähnlichen Vorgängen hilft auch, die Leistung zu verbessern.

## <a name="optimize-the-join-operator"></a>Optimieren des `join` Operators
Der [Verknüpfungsoperator](/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen durch übereinstimmende Werte in angegebenen Spalten zusammen. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Kleinere Tabelle links :** Der Operator gleicht Datensätze in der Tabelle auf der linken Seite der Join-Anweisung mit Datensätzen `join` auf der rechten Seite ab. Wenn die kleinere Tabelle auf der linken Seite angezeigt wird, müssen weniger Datensätze übereinstimmen, was die Abfrage beschleunigt. 

    In der folgenden Tabelle wird die linke Tabelle so reduziert, dass sie nur drei bestimmte Geräte abdecken kann, bevor sie mit den `DeviceLogonEvents` `IdentityLogonEvents` Konto-SIDs verknüpfen wird.
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- Verwenden Sie die **Inner-Join-Variante**– Die Standardmäßige Verknüpfungsrichtung oder die [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) dedupliziert Zeilen in der linken Tabelle durch die Verknüpfungstaste, bevor eine Zeile für jede Übereinstimmung mit der rechten Tabelle zurückgegeben wird. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) Wenn die linke Tabelle mehrere Zeilen mit demselben Wert für den Schlüssel enthält, werden diese Zeilen dedupliziert, um für jeden eindeutigen Wert eine einzelne zufällige `join` Zeile zu hinterlassen.

    Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weg lassen, die nützliche Einblicke bieten können. Die folgende Abfrage zeigt beispielsweise nur eine E-Mail mit einer bestimmten Anlage an, auch wenn dieselbe Anlage mit mehreren E-Mail-Nachrichten gesendet wurde:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Um diese Einschränkung zu umgehen, wenden wir die [Inner-Join-Variante](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem wir angeben, dass alle Zeilen in der linken Tabelle mit übereinstimmenden Werten `kind=inner` rechts angezeigt werden:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Verbinden von Datensätzen aus** einem Zeitfenster – Bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die rund um denselben Zeitraum auftreten. Das Anwenden desselben Ansatzes bei Verwendung hat auch Vorteile für die Leistung, indem die Anzahl der `join` zu überprüfende Datensätze reduziert wird.
    
    Die folgende Abfrage überprüft innerhalb von 30 Minuten nach dem Empfang einer schädlichen Datei auf Anmeldeereignisse:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Anwenden von** Zeitfiltern auf beiden Seiten – Auch wenn Sie ein bestimmtes Zeitfenster nicht untersuchen, kann das Anwenden von Zeitfiltern auf der linken und rechten Tabelle die Anzahl der Datensätze reduzieren, um die Leistung zu überprüfen und `join` zu verbessern. Die folgende Abfrage gilt für beide Tabellen, sodass sie nur Datensätze aus der letzten `Timestamp > ago(1h)` Stunde enthält:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Verwenden Sie Hinweise für die** Leistung – Verwenden Sie Hinweise mit dem Operator, um das Back-End anweisen, die Last beim Ausführen ressourcenintensiver Vorgänge zu `join` verteilen. [Weitere Informationen zu Verknüpfungshinweisen](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Der **[Shuffle-Hinweis](/azure/data-explorer/kusto/query/shufflequery)** hilft beispielsweise bei der Verbesserung der Abfrageleistung beim Verknüpfen von Tabellen mit einem Schlüssel mit hoher Kardinalität – einem Schlüssel mit vielen eindeutigen Werten – wie z. B. dem in der folgenden `AccountObjectId` Abfrage:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Der **[Übertragungshinweis](/azure/data-explorer/kusto/query/broadcastjoin)** hilft, wenn die linke Tabelle klein (bis zu 100.000 Datensätze) und die rechte Tabelle extrem groß ist. Die folgende Abfrage versucht beispielsweise, einige E-Mails mit  bestimmten Themen mit allen Nachrichten zu verbinden, die Links in der Tabelle `EmailUrlInfo` enthalten:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimieren des `summarize` Operators
Der [Zusammenfassungsoperator](/azure/data-explorer/kusto/query/summarizeoperator) aggregiert den Inhalt einer Tabelle. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Suchen nach unterschiedlichen** Werten – Verwenden Sie im Allgemeinen, um `summarize` unterschiedliche Werte zu finden, die sich wiederholen können. Es kann unnötig sein, sie zum Aggregieren von Spalten zu verwenden, die keine sich wiederholenden Werte enthalten.

    Obwohl eine einzelne E-Mail Teil mehrerer Ereignisse  sein kann, ist das folgende Beispiel keine effiziente Verwendung, da eine Netzwerknachrichten-ID für eine einzelne E-Mail immer eine eindeutige Absenderadresse `summarize` enthält.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Der Operator kann problemlos durch ersetzt werden, was potenziell dieselben Ergebnisse liefert `summarize` und gleichzeitig weniger Ressourcen `project` verbraucht:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Das folgende Beispiel ist eine effizientere Verwendung, da es mehrere unterschiedliche Instanzen einer Absenderadresse gibt, die E-Mails an `summarize` dieselbe Empfängeradresse sendet. Solche Kombinationen sind weniger unterschiedlich und haben wahrscheinlich Duplikate.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Abfrage neu** gemischt – Dies wird zwar am besten in Spalten mit sich wiederholenden Werten verwendet, aber dieselben Spalten können auch eine hohe Kardinalität oder eine große Anzahl `summarize` eindeutiger  Werte haben. Wie der Operator können Sie auch den `join` [Shuffle-Hinweis](/azure/data-explorer/kusto/query/shufflequery) anwenden, um die Verarbeitungslast zu verteilen und die Leistung beim Betrieb auf Spalten mit hoher Kardinalität `summarize` zu verbessern.

    Die folgende Abfrage verwendet, um unterschiedliche Empfänger-E-Mail-Adressen zu zählen, die in den Hunderttausenden `summarize` in großen Organisationen ausgeführt werden können. Um die Leistung zu verbessern, umfasst `hint.shufflekey` es:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Abfrageszenarien

### <a name="identify-unique-processes-with-process-ids"></a>Identifizieren eindeutiger Prozesse mit Prozess-IDs
Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet. Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen.

Um einen eindeutiger Bezeichner für einen Prozess auf einer bestimmten Maschine abzurufen, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit. Wenn Sie Daten um Prozesse zusammenführen oder zusammenfassen, fügen Sie Spalten für die Maschinenkennung (entweder `DeviceId` oder`DeviceName`), die Prozess-ID (`ProcessId`oder`InitiatingProcessId`) und die Prozesserstellungszeit (`ProcessCreationTime` oder`InitiatingProcessCreationTime`) hinzu.

Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.

Beispielabfrage:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.

### <a name="query-command-lines"></a>Abfragebefehlszeilen
Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen. Ein Angreifer könnte beispielsweise auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mithilfe von Umgebungsvariablen oder mit Anführungszeichen verweisen. Der Angreifer kann auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.

Wenden Sie die folgenden Methoden an, um dauerhaftere Abfragen um Befehlszeilen zu erstellen:

- Identifizieren Sie die bekannten Prozesse (z. *B.net.exe* oder *psexec.exe*), indem Sie die Dateinamenfelder abgleichen, anstatt in der Befehlszeile selbst zu filtern.
- Analysieren von Befehlszeilenabschnitten mithilfe der [parse_command_line()-Funktion](/azure/data-explorer/kusto/query/parse-command-line) 
- Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge. Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.
- Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung. Verwenden Sie z. B. `=~` , und anstelle von , und `in~` `contains` `==` `in` `contains_cs` .
- Um befehlszeilenverhinderungstechniken zu verringern, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinander folgende Leerzeichen durch ein einzelnes Leerzeichen ersetzen. Es gibt komplexere Verschleierungstechniken, die andere Ansätze erfordern, aber diese Optimierungen können bei der Behandlung gängiger Techniken hilfreich sein.

In den folgenden Beispielen werden verschiedene Möglichkeiten  zum Erstellen einer Abfrage gezeigt, die nach der Datei suchtnet.exeden Firewalldienst "MpsSvc" zu beenden:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a>Aufnahme von Daten aus externen Quellen
Um lange Listen oder große Tabellen in Ihre Abfrage zu integrieren, verwenden Sie den [Externaldata-Operator,](/azure/data-explorer/kusto/query/externaldata-operator) um Daten aus einem angegebenen URI zu übernehmen. Sie können Daten aus Dateien in TXT, CSV, JSON oder anderen [Formaten erhalten.](/azure/data-explorer/ingestion-supported-formats) Das folgende Beispiel zeigt, wie Sie die umfassende Liste der Schadsoftware-SHA-256-Hashes verwenden können, die von MalwareBazaar (abuse.ch) bereitgestellt werden, um Anlagen in E-Mails zu überprüfen:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Analysieren von Zeichenfolgen
Es gibt verschiedene Funktionen, mit deren Hilfe Sie Zeichenfolgen effizient verarbeiten können, die eine Analyse oder Konvertierung benötigen. 

| String | Funktion | Verwendungsbeispiel |
|--|--|--|
| Befehlszeilen | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Extrahieren Sie den Befehl und alle Argumente. | 
| Paths | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Extrahieren Sie die Abschnitte eines Datei- oder Ordnerpfads. |
| Versionsnummern | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct a version number with up to four sections and up to eight characters per section. Verwenden Sie die analysierten Daten, um das Versionsalter zu vergleichen. |
| IPv4-Adressen | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertieren Sie eine IPv4-Adresse in eine lange ganze Zahl. Um IPv4-Adressen zu vergleichen, ohne sie zu konvertieren, verwenden Sie [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-Adressen | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertieren Sie eine IPv4- oder IPv6-Adresse in die kanonische IPv6-Notation. Verwenden Sie zum Vergleichen von IPv6-Adressen [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Informationen zu allen unterstützten Analysefunktionen finden Sie [unter Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Verwandte Themen
- [Kusto-Dokumentation zur Abfragesprache](/azure/data-explorer/kusto/query/)
- [Kontingente und Verwendungsparameter](advanced-hunting-limits.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)