---
title: Bewährte Methoden für die erweiterte Jagd Abfrage in Microsoft Threat Protection
description: Hier erfahren Sie, wie Sie schnell, effizient und fehlerfrei Jagd Abfragen für Bedrohungen mit Advanced Hunting erstellen.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID, optimieren, bewährte Methode, Analyse, Join, Zusammenfassung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 29e5eb64445c6c5c45b8e1fd1633c030b5f32b86
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649667"
---
# <a name="advanced-hunting-query-best-practices"></a>Bewährte Methoden für Erweiterte Suchanfragen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Wenden Sie diese Empfehlungen an, um schneller Ergebnisse zu erzielen und Timeouts beim durchführen komplexer Abfragen zu vermeiden. Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Grundlegendes zu CPU-Ressourcen Kontingenten
Je nach Größe hat jeder Mandant Zugriff auf eine festgelegte Menge an CPU-Ressourcen, die für die Ausführung von erweiterten Jagd Abfragen reserviert sind. Ausführliche Informationen zu verschiedenen Dienst Beschränkungen finden [Sie unter Erweiterte Jagd Kontingente und Nutzungsparameter](advanced-hunting-limits.md).

Kunden, die mehrere Abfragen regelmäßig ausführen, sollten den Verbrauch nachverfolgen und die Optimierungs Anleitungen in diesem Artikel anwenden, um die Unterbrechung zu minimieren, die durch Überschreitung der Kontingente oder Nutzungsparameter verursacht wird.

## <a name="general-optimization-tips"></a>Allgemeine Optimierungstipps

- **Größe neuer Abfragen**– Wenn Sie vermuten, dass eine Abfrage ein umfangreiches Resultset zurückgibt, bewerten Sie Sie zunächst mithilfe des [Count-Operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Use [Limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) oder sein Synonym `take` , um große Resultsets zu vermeiden.
- **Filter früh anwenden**– Anwenden von Zeit Filtern und anderen Filtern, um das DataSet zu reduzieren, insbesondere vor der Verwendung von Transformations-und Analysefunktionen wie [SUBSTRING ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Im Beispiel unten wird die Analysefunktion [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem die Anzahl der Datensätze durch die Filteroperatoren reduziert wurde.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Has Beats enthält**– um unnötige Suche nach Teilzeichenfolgen in Wörtern zu vermeiden, verwenden Sie den- `has` Operator anstelle von `contains` . [Informationen zu Zeichenfolgenoperatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **In bestimmten Spalten suchen**– suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen in allen Spalten auszuführen. Verwenden Sie nicht `*` , um alle Spalten zu überprüfen.
- **Groß-** und Kleinschreibung für die Geschwindigkeit – bei der Suche nach Groß-/Kleinschreibung werden spezifischere und meist leistungsfähigere Suchvorgänge durchgeführt. Namen von [Zeichenfolgenoperatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)mit Berücksichtigung der Groß-/Kleinschreibung, beispielsweise `has_cs` und `contains_cs` , werden normalerweise mit beendet `_cs` . Sie können auch den gleich-Operator mit Berücksichtigung der groß `==` -/Kleinschreibung anstelle von verwenden `=~` .
- **Analysieren, nicht extrahieren**– wenn möglich, verwenden Sie den [Analyse Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) oder eine Analysefunktion wie [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Vermeiden `matches regex` Sie den Zeichenfolgenoperator oder die [extract ()-Funktion](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), die beide regulären Ausdruck verwenden. Reservieren Sie die Verwendung von regulärem Ausdruck für komplexere Szenarien. [Lesen Sie mehr über Analysefunktionen](#parse-strings)
- **Filter Tables not Expressions**: Filtern Sie nicht nach einer berechneten Spalte, wenn Sie nach einer Tabellenspalte filtern können.
- **Kein drei**stelliger Begriff – vermeiden Sie einen Vergleich oder eine Filterung mit Ausdrücken mit drei oder weniger Zeichen. Diese Begriffe sind nicht indiziert und entsprechen diesen, erfordern mehr Ressourcen.
- **Projekt selektiv**– machen Sie Ihre Ergebnisse leichter verständlich, indem Sie nur die benötigten Spalten projizieren. Das projizieren bestimmter Spalten vor dem Ausführen eines [Joins](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) oder ähnlicher Vorgänge trägt ebenfalls zur Leistungsverbesserung bei.

## <a name="optimize-the-join-operator"></a>Optimieren des `join` Operators
Der [Join-Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen zusammen, indem er Werte in angegebenen Spalten abstimmt. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Kleinere Tabelle links**– der `join` Operator vergleicht Datensätze in der Tabelle auf der linken Seite der JOIN-Anweisung mit Datensätzen auf der rechten Seite. Durch die kleinere Tabelle auf der linken Seite müssen weniger Datensätze abgeglichen werden, wodurch die Abfrage beschleunigt wird. 

    In der folgenden Tabelle reduzieren wir die linke Tabelle `DeviceLogonEvents` auf nur drei bestimmte Geräte abdecken, bevor Sie es mit `IdentityLogonEvents` SIDs-Konten hinzufügen.
 
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

- **Verwenden Sie die Geschmacksrichtung Inner Join**– das standardmäßige [Join-Aroma](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) oder der [innerunique-Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) dedupliziert Zeilen in der linken Tabelle mit dem Join-Schlüssel, bevor eine Zeile für jede Übereinstimmung mit der rechten Tabelle zurückgegeben wird. Wenn die linke Tabelle mehrere Zeilen mit dem gleichen Wert für den Schlüssel aufweist `join` , werden diese Zeilen dedupliziert, um für jeden eindeutigen Wert eine einzelne zufällige Zeile zu hinterlassen.

    Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weglassen, die nützliche Einblicke bieten können. Beispielsweise wird in der folgenden Abfrage nur eine e-Mail mit einer bestimmten Anlage angezeigt, auch wenn dieselbe Anlage mit mehreren e-Mail-Nachrichten gesendet wurde:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Um diese Einschränkung zu beheben, wenden wir den Geschmacksmuster [Inner Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem `kind=inner` Sie angeben, dass alle Zeilen in der linken Tabelle mit übereinstimmenden Werten in der rechten angezeigt werden sollen:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Beitreten von Datensätzen aus einem Zeitfenster**– bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die um den gleichen Zeitraum erfolgen. Das Anwenden des gleichen Ansatzes bei Verwendung `join` von profitiert auch von der Leistung, indem die Anzahl der zu überprüfenden Datensätze reduziert wird
    
    Die folgende Abfrage sucht innerhalb von 30 Minuten nach dem Empfang einer schädlichen Datei nach Anmeldeereignissen:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Anwenden von Zeit Filtern auf beiden Seiten**– selbst wenn Sie ein bestimmtes Zeitfenster nicht untersuchen, kann das Anwenden von Zeit Filtern sowohl auf der linken als auch auf der rechten Seite die Anzahl der zu überprüfenden Datensätze verringern und die Leistung verbessern `join` . Die folgende Abfrage gilt `Timestamp > ago(1h)` für beide Tabellen, sodass nur Datensätze aus der letzten Stunde verknüpft werden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Verwenden von Hints for Performance**– verwenden Sie Hinweise mit dem `join` Operator, um das Back-End anzuweisen, die Last zu verteilen, wenn ressourcenintensive Vorgänge ausgeführt werden. [Weitere Informationen über Join-Hinweise](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Beispielsweise hilft der **[shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** beim Verknüpfen von Tabellen mithilfe eines Schlüssels mit hoher Kardinalität die Abfrageleistung – ein Schlüssel mit vielen eindeutigen Werten wie der `AccountObjectId` in der folgenden Abfrage:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Der **[Übertragungs Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** hilft, wenn die linke Tabelle klein ist (bis zu 100.000 Datensätze), und die Rechte Tabelle ist extrem groß. Die folgende Abfrage versucht beispielsweise, an einigen e-Mails teilzunehmen, bei denen es sich um bestimmte Themen mit _allen_ Nachrichten mit Links in der `EmailUrlInfo` Tabelle handelt:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimieren des `summarize` Operators
Der [Operator "zusammenfassen](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) " aggregiert den Inhalt einer Tabelle. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- Suchen Sie nach unter **schiedlichen Werten**– verwenden Sie im allgemeinen `summarize` die Suche nach unterschiedlichen Werten, die sich wiederholende Werte haben können. Es kann nicht erforderlich sein, es zum Aggregieren von Spalten zu verwenden, die keine sich wiederholenden Werte aufweisen.

    Während eine einzelne e-Mail Teil mehrerer Ereignisse sein kann, ist das Beispiel unten _keine_ effiziente Verwendung, `summarize` da eine Netzwerknachrichten-ID für eine einzelne e-Mail immer mit einer eindeutigen Absenderadresse geliefert wird.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Der `summarize` Operator kann problemlos durch ersetzt werden `project` , wodurch möglicherweise dieselben Ergebnisse erzielt werden, während weniger Ressourcen beansprucht werden:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Das folgende Beispiel ist eine effizientere Verwendung von `summarize` , da es mehrere unterschiedliche Instanzen einer Absenderadresse geben kann, die eine e-Mail an dieselbe Empfängeradresse sendet. Solche Kombinationen sind unterschiedlich und sind wahrscheinlich Duplikate.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Die Abfrage shuffle**– während Sie `summarize` am besten in Spalten mit sich wiederholenden Werten verwendet wird, können dieselben Spalten auch eine _hohe Kardinalität_ oder eine große Anzahl eindeutiger Werte aufweisen. Wie der `join` Operator können Sie auch den [shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) anwenden, `summarize` um die Verarbeitungslast zu verteilen und möglicherweise die Leistung zu verbessern, wenn Sie auf Spalten mit hoher Kardinalität arbeiten.

    Die folgende Abfrage verwendet `summarize` , um eine eindeutige Empfänger-e-Mail-Adresse zu zählen, die in den Hunderttausenden in großen Organisationen ausgeführt werden kann. Um die Leistung zu verbessern, umfasst es `hint.shufflekey` Folgendes:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Abfrage Szenarien

### <a name="identify-unique-processes-with-process-ids"></a>Identifizieren von eindeutigen Prozessen mit Prozess-IDs
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

### <a name="query-command-lines"></a>Abfragebefehls Zeilen
Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen. Beispielsweise kann ein Angreifer auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen. Der Angreifer kann auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.

Wenden Sie die folgenden Methoden an, um dauerhafte Abfragen um Befehlszeilen zu erstellen:

- Identifizieren Sie die bekannten Prozesse (beispielsweise *net.exe* oder *psexec.exe*), indem Sie Sie in den dateinamenfeldern abgleichen, anstatt die Befehlszeile selbst zu filtern.
- Analysieren von Befehlszeilen Abschnitten mithilfe der [parse_command_line ()-Funktion](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge. Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.
- Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung. Verwenden Sie beispielsweise, und `=~` `in~` `contains` anstelle von `==` , `in` und `contains_cs` .
- Um die Methoden zur Verschleierung von Befehlszeilen zu verringern, sollten Sie das Entfernen von Anführungszeichen, das Ersetzen von Kommas durch Leerzeichen und das Ersetzen mehrerer aufeinander folgender Leerzeichen durch ein einzelnes Leerzeichen Es gibt komplexere Verschleierung-Techniken, die andere Ansätze erfordern, aber diese Optimierungen können dazu beitragen, häufige zu behandeln.

Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen einer Abfrage, die nach der Datei *net.exe* sucht, um den Firewalldienst "mpssvc" zu beenden:

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

### <a name="ingest-data-from-external-sources"></a>Aufnehmen von Daten aus externen Quellen
Wenn Sie lange Listen oder große Tabellen in Ihre Abfrage einbeziehen möchten, verwenden Sie den [externaldata-Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) , um Daten aus einem angegebenen URI zu erfassen. Sie können Daten aus Dateien in txt, CSV, JSON oder [anderen Formaten](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)abrufen. Im folgenden Beispiel wird gezeigt, wie Sie die umfangreiche Liste der von MalwareBazaar (abuse.ch) bereitgestellten SHA-256-Hashes für Schadsoftware verwenden können, um Anhänge in e-Mails zu überprüfen:

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
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Analysieren von Zeichenfolgen
Es gibt verschiedene Funktionen, die Sie verwenden können, um Zeichenfolgen effizient zu verarbeiten, die analysiert oder konvertiert werden müssen. 

| Zeichenfolge | Funktion | Verwendungsbeispiel |
|--|--|--|
| Befehlszeilen | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extrahieren Sie den Befehl und alle Argumente. | 
| Paths | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extrahieren Sie die Abschnitte eines Datei-oder Ordnerpfads. |
| Versionsnummern | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Dekonstruieren Sie eine Versionsnummer mit bis zu vier Abschnitten und bis zu acht Zeichen pro Abschnitt. Verwenden Sie die analysierten Daten, um das Versions Alter zu vergleichen. |
| IPv4-Adressen | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertiert eine IPv4-Adresse in eine lange ganze Zahl. Verwenden Sie [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction), um IPv4-Adressen ohne Konvertierung zu vergleichen. |
| IPv6-Adressen | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertieren Sie eine IPv4-oder IPv6-Adresse in die kanonische IPv6-Notation. Verwenden Sie [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction), um IPv6-Adressen zu vergleichen. |

Informationen zu allen unterstützten Analysefunktionen finden [Sie unter Kusto String Functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Verwandte Themen
- [Dokumentation zur Kusto-Abfragesprache](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Kontingente und Nutzungsparameter](advanced-hunting-limits.md)
- [Behandeln von erweiterten Jagd Fehlern](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
