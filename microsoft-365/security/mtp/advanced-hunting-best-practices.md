---
title: Bewährte Methoden für erweiterte Suchabfragen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie schnelle, effiziente und fehlerfreie Abfragen zur Bedrohungssuche mit erweiterter Suche erstellen.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID, optimieren, bewährte Methode, analysieren, beitreten, zusammenfassen
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928474"
---
# <a name="advanced-hunting-query-best-practices"></a>Bewährte Methoden für Erweiterte Suchanfragen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Wenden Sie diese Empfehlungen an, um ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden. Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Verstehen von CPU-Ressourcenkontingenten
Je nach Größe hat jeder Mandant Zugriff auf eine bestimmte Menge von CPU-Ressourcen, die für die Ausführung von Abfragen für die erweiterte Suche reserviert sind. Ausführliche Informationen zu verschiedenen Dienstbeschränkungen finden Sie unter Kontingente für die erweiterte [Suche und Verwendungsparameter.](advanced-hunting-limits.md)

Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und die Optimierungsanleitungen in diesem Artikel anwenden, um Unterbrechungen aufgrund von Überschreitungen von Kontingenten oder Verwendungsparametern zu minimieren.

## <a name="general-optimization-tips"></a>Allgemeine Optimierungstipps

- **Größe neuer Abfragen –** Wenn Sie vermuten, dass eine Abfrage ein umfangreiches Ergebnisset zurück gibt, bewerten Sie es zuerst mit dem [Count-Operator.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator) Verwenden [Sie den Grenzwert](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) oder sein `take` Synonym, um große Ergebnismengen zu vermeiden.
- Frühzeitiges Anwenden von Filtern **–** Wenden Sie Zeitfilter und andere Filter an, um den Datensatz zu reduzieren, insbesondere vor der Verwendung von Transformations- und Analysefunktionen, wie z. B. [Teilzeichenfolge()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Im folgenden Beispiel wird die Analysefunktion [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem Filteroperatoren die Anzahl der Datensätze reduziert haben.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Has-Takte enthält**- Um zu vermeiden, dass Teilzeichenfolgen in Wörtern unnötig durchsucht werden, verwenden Sie den `has` Operator anstelle von `contains` . [Informationen zu Zeichenfolgenoperatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **In bestimmten Spalten suchen –** Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen über alle Spalten hinweg ausführen. Überprüfen Sie nicht `*` alle Spalten.
- **Geschwindigkeitssensibles bei der Schreibung**– Suche unter Schreibungsempfindlicher ist spezifischer und in der Regel performanter. Namen von Zeichenfolgenoperatoren, bei der [die Kleinschreibung beachtet](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)wird, z. B. `has_cs` und , `contains_cs` enden im Allgemeinen mit `_cs` . Sie können auch den Operator "Equals" anstelle von "Equals" verwenden, bei dem die `==` Zwischen- und Kleinschreibung beachtet `=~` wird.
- **Analysieren, nicht extrahieren –** Verwenden Sie [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) nach Möglichkeit den Analyseoperator oder eine Analysefunktion wie [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Vermeiden Sie `matches regex` den Zeichenfolgenoperator oder die [Extract()-Funktion,](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)die beide einen regulären Ausdruck verwenden. Reservieren Sie die Verwendung regulärer Ausdrücke für komplexere Szenarien. [Weitere Informationen zur Analyse von Funktionen](#parse-strings)
- **Filtern von Tabellen ohne Ausdrücke**– Filtern Sie nicht nach einer berechneten Spalte, wenn Sie nach einer Tabellenspalte filtern können.
- **Keine Drei-Zeichen-Begriffe**– Vermeiden Sie das Vergleichen oder Filtern mit Begriffen mit drei oder weniger Zeichen. Diese Begriffe werden nicht indiziert, und für deren Abgleich sind weitere Ressourcen erforderlich.
- **Projekt selektiv –** Vereinfachen Sie das Verständnis Ihrer Ergebnisse, indem Sie nur die benötigten Spalten projiziert. Das Projiziert bestimmter Spalten vor dem Ausführen von [Verknüpfungsvorgängen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) oder ähnlichen Vorgängen hilft auch, die Leistung zu verbessern.

## <a name="optimize-the-join-operator"></a>Optimieren des `join` Operators
Der [Verknüpfungsoperator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen zusammen, indem Werte in angegebenen Spalten übereinstimmen. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Kleinere Tabelle links –** Der Operator gleicht Datensätze in der Tabelle auf der linken Seite der Join-Anweisung mit Datensätzen `join` auf der rechten Seite ab. Wenn die kleinere Tabelle auf der linken Seite angezeigt wird, müssen weniger Datensätze übereinstimmen, was die Abfrage beschleunigt. 

    In der folgenden Tabelle reduzieren wir die linke Tabelle so, dass nur drei bestimmte Geräte berücksichtigt werden, bevor sie mit `DeviceLogonEvents` den Konto-SIDs `IdentityLogonEvents` verknüpfen.
 
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

- Verwenden Sie die **inner-join-Variante**– Die standardmäßige Verknüpfungskonfiguration oder die [innerunique-join dedupliziert](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) Zeilen in der linken Tabelle durch die Verknüpfungsschlüssel, bevor für jede Übereinstimmung mit der rechten Tabelle eine Zeile zurückgegeben wird. [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) Wenn die linke Tabelle mehrere Zeilen mit demselben Wert für den Schlüssel enthält, werden diese Zeilen so dedupliziert, dass für jeden eindeutigen Wert eine einzelne zufällige `join` Zeile übrig bleibt.

    Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weg lassen, die nützliche Einblicke liefern können. Die folgende Abfrage zeigt beispielsweise nur eine E-Mail mit einer bestimmten Anlage an, auch wenn dieselbe Anlage mit mehreren E-Mail-Nachrichten gesendet wurde:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Um diese Einschränkung zu umgehen, wenden wir die inner [-Join-Variante](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem wir angeben, dass alle Zeilen in der linken Tabelle mit übereinstimmenden `kind=inner` Werten rechts angezeigt werden:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Datensätze aus einem Zeitfenster** verbinden – Bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die ungefähr während desselben Zeitraums auftreten. Das Anwenden desselben Ansatzes bei Verwendung hat auch Vorteile für die Leistung, indem die Anzahl der `join` zu überprüfende Datensätze reduziert wird.
    
    Die folgende Abfrage prüft innerhalb von 30 Minuten nach Dem Empfang einer schädlichen Datei auf Anmeldeereignisse:

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
- **Anwenden von** Zeitfiltern auf beide Seiten – Auch wenn Sie ein bestimmtes Zeitfenster nicht untersuchen, kann das Anwenden von Zeitfiltern sowohl für die linke als auch für die rechte Tabelle die Anzahl der Datensätze reduzieren, um die Leistung zu überprüfen und `join` zu verbessern. Die folgende Abfrage gilt für beide Tabellen, sodass nur Datensätze aus der letzten `Timestamp > ago(1h)` Stunde zusammen treten:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Verwenden Sie Hinweise für die** Leistung – Verwenden Sie Hinweise mit dem Operator, um das Back-End anweisen, die Last beim Ausführen `join` ressourcenintensiver Vorgänge zu verteilen. [Weitere Informationen zu Verknüpfungshinweisen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Der Hinweis **["Shuffle"](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** trägt beispielsweise zur Verbesserung der Abfrageleistung bei, wenn Tabellen mit einem Schlüssel mit hoher Karität ( einem Schlüssel mit vielen eindeutigen Werten) wie der folgenden Abfrage zusammengef?pft `AccountObjectId` werden:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Der **[Übertragungshinweis hilft,](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** wenn die linke Tabelle klein (bis zu 100.000 Datensätze) und die rechte Tabelle sehr groß ist. Die folgende Abfrage versucht beispielsweise, einige E-Mails mit  bestimmten Themen mit allen Nachrichten zu verbinden, die Links in der Tabelle `EmailUrlInfo` enthalten:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimieren des `summarize` Operators
Der [Operator "Summarize"](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregiert den Inhalt einer Tabelle. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Suche nach unterschiedlichen** Werten – im Allgemeinen verwenden Sie diese, um `summarize` unterschiedliche Werte zu finden, die sich wiederholen können. Es kann unnötig sein, damit Spalten zu aggregieren, die keine sich wiederholenden Werte haben.

    Obwohl eine einzelne E-Mail Teil mehrerer Ereignisse  sein kann, ist das folgende Beispiel keine effiziente Verwendung, da eine Netzwerknachrichten-ID für eine einzelne E-Mail immer eine eindeutige Absenderadresse `summarize` enthält.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Der Operator kann einfach durch ersetzt werden, was potenziell dieselben Ergebnisse liefert `summarize` `project` und weniger Ressourcen verbraucht:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Das folgende Beispiel ist eine effizientere Verwendung, da es mehrere unterschiedliche Instanzen einer Absenderadresse gibt, die E-Mails an dieselbe `summarize` Empfängeradresse sendet. Solche Kombinationen sind weniger unterschiedlich und haben wahrscheinlich Duplikate.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Verfälsten** Sie die Abfrage . Dies wird zwar am besten in Spalten mit sich wiederholenden Werten verwendet, aber dieselben Spalten können auch eine hohe Karoität oder eine große Anzahl `summarize` eindeutiger Werte haben.  Wie der Operator können Sie auch den `join` [Shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) anwenden, um die Verarbeitungslast zu verteilen und die Leistung beim Arbeiten mit Spalten mit hoher `summarize` Karoität potenziell zu verbessern.

    Die folgende Abfrage wird verwendet, um unterschiedliche Empfänger-E-Mail-Adressen zu zählen, die in großen Organisationen in Hunderten von Tausenden `summarize` ausgeführt werden können. Um die Leistung zu verbessern, umfasst `hint.shufflekey` es:

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
Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen. Beispielsweise könnte ein Angreifer auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mithilfe von Umgebungsvariablen oder mit Anführungszeichen verweisen. Der Angreifer könnte auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.

Wenden Sie die folgenden Methoden an, um dauerhaftere Abfragen um Befehlszeilen zu erstellen:

- Identifizieren Sie die bekannten Prozesse (z. *B.net.exe* oder *psexec.exe),* indem Sie die Dateinamenfelder abgleichen, anstatt nach der Befehlszeile selbst zu filtern.
- Analysieren von Befehlszeilenabschnitten mithilfe der [parse_command_line()-Funktion](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge. Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.
- Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung. Verwenden Sie z. B. `=~` , und anstelle von , und `in~` `contains` `==` `in` `contains_cs` .
- Um Techniken zur Verhängung von Befehlszeilen zu minimieren, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinander folgende Leerzeichen durch ein einziges Leerzeichen ersetzen. Es gibt komplexere Verschleierungstechniken, die andere Ansätze erfordern, aber diese Optimierungen können dabei helfen, allgemeine Techniken zu adressieren.

Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen einer Abfrage, die nach der Datei sucht, *net.exe* den Firewalldienst "MpsSvc" zu beenden:

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

### <a name="ingest-data-from-external-sources"></a>Aufnahmedaten aus externen Quellen
Um lange Listen oder große Tabellen in ihre Abfrage zu integrieren, verwenden Sie den [Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) für externe Daten, um Daten aus einem angegebenen URI zu übernehmen. Sie können Daten aus Dateien in TXT-, CSV-, JSON- oder anderen [Formaten erhalten.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) Das folgende Beispiel zeigt, wie Sie die umfangreiche Liste der Schadsoftware SHA-256-Hashes verwenden können, die von MalwareBazaar (abuse.ch) bereitgestellt werden, um Anlagen in E-Mails zu überprüfen:

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
Es gibt verschiedene Funktionen, mit deren Hilfe Sie Zeichenfolgen effizient verarbeiten können, die eine Analyse oder Konvertierung benötigen. 

| Zeichenfolge | Funktion | Verwendungsbeispiel |
|--|--|--|
| Befehlszeilen | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extrahieren Sie den Befehl und alle Argumente. | 
| Paths | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extrahieren Sie die Abschnitte eines Datei- oder Ordnerpfads. |
| Versionsnummern | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct a version number with up to four sections and up to eight characters per section. Verwenden Sie die analysierten Daten, um das Versionsalter zu vergleichen. |
| IPv4-Adressen | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertieren Einer IPv4-Adresse in eine lange ganze Zahl. Verwenden Sie zum Vergleichen von IPv4-Adressen, ohne sie zu [konvertieren, ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-Adressen | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertieren Sie eine IPv4- oder eine IPv6-Adresse in die kanonische IPv6-Notation. Verwenden Sie zum Vergleichen von IPv6-Adressen [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Informationen zu allen unterstützten Analysefunktionen finden Sie [unter Kusto-Zeichenfolgenfunktionen.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Verwandte Themen
- [Dokumentation zur Abfragesprache von Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Kontingente und Verwendungsparameter](advanced-hunting-limits.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
