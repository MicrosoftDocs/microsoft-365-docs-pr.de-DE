---
title: Bewährte Methoden für erweiterte Suchabfragen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie schnelle, effiziente und fehlerfreie Abfragen zur Bedrohungssuche mit erweiterter Suche erstellen.
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID, optimieren, bewährte Methoden, analysieren, verknüpfen, zusammenfassen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae2e7fb960dd8ce2a42ce62fe0b8da7675e00ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228375"
---
# <a name="advanced-hunting-query-best-practices"></a>Bewährte Methoden für Erweiterte Suchanfragen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Wenden Sie diese Empfehlungen an, um ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden. Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Grundlegendes zu CPU-Ressourcenkontingenten
Je nach Größe hat jeder Mandant Zugriff auf eine festgelegte Menge an CPU-Ressourcen, die für die Ausführung erweiterter Suchabfragen zugeordnet sind. Ausführliche Informationen zu verschiedenen Dienstgrenzwerten [finden Sie unter "Erweiterte Suchkontingente und Verwendungsparameter".](advanced-hunting-limits.md)

Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und die Optimierungsanleitungen in diesem Artikel anwenden, um Unterbrechungen aufgrund von Überschreitung von Kontingenten oder Verwendungsparametern zu minimieren.

## <a name="general-optimization-tips"></a>Allgemeine Optimierungstipps

- **Größe neuer Abfragen**– Wenn Sie vermuten, dass eine Abfrage ein großes Resultset zurückgibt, bewerten Sie sie zuerst mithilfe des [Count-Operators.](/azure/data-explorer/kusto/query/countoperator) Verwenden Sie [ Limit ](/azure/data-explorer/kusto/query/limitoperator) oder sein `take` Synonym, um große Resultsets zu vermeiden.
- **Frühzeitiges Anwenden von Filtern**– Wenden Sie Zeitfilter und andere Filter an, um den Datensatz zu reduzieren, insbesondere vor der Verwendung von Transformations- und Analysefunktionen, z. [B. teilzeichenfolge()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Im folgenden Beispiel wird die Analysefunktion [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem filteroperatoren die Anzahl der Datensätze reduziert haben.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Has beats contains**-To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains` . [Informationen zu Zeichenfolgenoperatoren](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Suchen In bestimmten Spalten**– Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen in allen Spalten auszuführen. Verwenden Sie diese Option `*` nicht, um alle Spalten zu überprüfen.
- Bei der Geschwindigkeit wird **die Groß-/Kleinschreibung beachtet–** Suchvorgänge, bei denen die Groß-/Kleinschreibung berücksichtigt wird, sind spezifischer und im Allgemeinen leistungsstärker. Namen von [Zeichenfolgenoperatoren](/azure/data-explorer/kusto/query/datatypes-string-operators)mit Groß-/Kleinschreibung, z. B. `has_cs` und , `contains_cs` enden in der Regel mit `_cs` . Sie können auch den Operator "Gleichheit zwischen Groß- und Kleinschreibung" `==` anstelle von `=~` verwenden.
- **Parse, don't extract**-Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Vermeiden Sie den `matches regex` Zeichenfolgenoperator oder die [Extract()-Funktion,](/azure/data-explorer/kusto/query/extractfunction)die beide einen regulären Ausdruck verwenden. Reservieren Sie die Verwendung des regulären Ausdrucks für komplexere Szenarien. [Weitere Informationen zu Analysefunktionen](#parse-strings)
- **Filter tables not expressions**- Don't filter on a calculated column if you can filter on a table column.
- **Keine Ausdrücke** mit drei Zeichen – Vermeiden Sie das Vergleichen oder Filtern mit Begriffen mit maximal drei Zeichen. Diese Begriffe sind nicht indiziert, und für den Abgleich dieser Begriffe sind weitere Ressourcen erforderlich.
- **Project selektiv**– Machen Sie Ihre Ergebnisse leichter verständlich, indem Sie nur die benötigten Spalten projizieren. Das Projizieren bestimmter Spalten vor dem Ausführen von [Verknüpfungsvorgängen](/azure/data-explorer/kusto/query/joinoperator) oder ähnlichen Vorgängen verbessert auch die Leistung.

## <a name="optimize-the-join-operator"></a>Optimieren des `join` Operators
Der [Verknüpfungsoperator](/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen zusammen, indem Werte in angegebenen Spalten übereinstimmen. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Kleinere Tabelle links**– Der `join` Operator gleicht Datensätze in der Tabelle auf der linken Seite der Join-Anweisung mit Datensätzen auf der rechten Seite ab. Wenn die kleinere Tabelle auf der linken Seite vorhanden ist, müssen weniger Datensätze abgeglichen werden, wodurch die Abfrage beschleunigt wird.

    In der folgenden Tabelle wird die linke Tabelle so reduziert, dass nur drei bestimmte Geräte abgedeckt werden, `DeviceLogonEvents` bevor sie `IdentityLogonEvents` mithilfe von Konto-SIDs verbunden wird.

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

- **Verwenden Sie den inneren Join-Typ**– die [Standardverknüpfungsart](/azure/data-explorer/kusto/query/joinoperator#join-flavors) oder die [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) dedupliziert Zeilen in der linken Tabelle durch die Verknüpfungsschlüssel, bevor Sie eine Zeile für jede Übereinstimmung an die rechte Tabelle zurückgeben. Wenn die linke Tabelle mehrere Zeilen mit demselben Wert für den `join` Schlüssel aufweist, werden diese Zeilen dedupliziert, um eine einzelne zufällige Zeile für jeden eindeutigen Wert zu belassen.

    Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weglassen, die nützliche Einblicke liefern können. Die folgende Abfrage zeigt beispielsweise nur eine E-Mail mit einer bestimmten Anlage an, auch wenn dieselbe Anlage mit mehreren E-Mail-Nachrichten gesendet wurde:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    Um diese Einschränkung zu beheben, wenden wir die [innere Verknüpfungsart](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem wir angeben, `kind=inner` dass alle Zeilen in der linken Tabelle mit übereinstimmenden Werten auf der rechten Seite angezeigt werden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- **Verknüpfen von Datensätzen aus einem Zeitfenster**– Bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die ungefähr im gleichen Zeitraum auftreten. Das Anwenden desselben Ansatzes bei Verwendung `join` hat auch Vorteile bei der Leistung, da die Anzahl der zu überprüfenden Datensätze reduziert wird.

    Die folgende Abfrage überprüft innerhalb von 30 Minuten nach Dem Empfang einer schädlichen Datei auf Anmeldeereignisse:

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
- **Anwenden von Zeitfiltern auf beiden Seiten**– Auch wenn Sie kein bestimmtes Zeitfenster untersuchen, kann das Anwenden von Zeitfiltern auf der linken und rechten Tabelle die Anzahl der Datensätze reduzieren, um die Leistung zu überprüfen und zu `join` verbessern. Die folgende Abfrage gilt für `Timestamp > ago(1h)` beide Tabellen, sodass nur Datensätze aus der letzten Stunde verknüpft werden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- **Verwenden Sie Hinweise zur Leistung**– Verwenden Sie Hinweise mit dem `join` Operator, um das Back-End anzuweisen, Last zu verteilen, wenn ressourcenintensive Vorgänge ausgeführt werden. [Weitere Informationen zu Verknüpfungshinweisen](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Beispielsweise verbessert der **[Shuffle-Hinweis](/azure/data-explorer/kusto/query/shufflequery)** die Abfrageleistung beim Verknüpfen von Tabellen mithilfe eines Schlüssels mit hoher Kardinalität – einem Schlüssel mit vielen eindeutigen Werten – wie z. B. `AccountObjectId` der folgenden Abfrage:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    Der **[Übertragungshinweis hilft,](/azure/data-explorer/kusto/query/broadcastjoin)** wenn die linke Tabelle klein ist (bis zu 100.000 Datensätze) und die rechte Tabelle extrem groß ist. Die folgende Abfrage versucht beispielsweise, einige E-Mails mit bestimmten Betreffzeilen mit _allen_ Nachrichten zu verknüpfen, die Links in der `EmailUrlInfo` Tabelle enthalten:

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a>Optimieren des `summarize` Operators
Der [Zusammenfassungsoperator](/azure/data-explorer/kusto/query/summarizeoperator) aggregiert den Inhalt einer Tabelle. Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.

- **Unterschiedliche Werte** finden – Verwenden Sie im Allgemeinen `summarize` unterschiedliche Werte, die wiederholt werden können. Es kann nicht erforderlich sein, sie zum Aggregieren von Spalten zu verwenden, die keine wiederholten Werte aufweisen.

    Während eine einzelne E-Mail Teil mehrerer Ereignisse sein kann, ist das folgende Beispiel _keine_ effiziente Verwendung, `summarize` da eine Netzwerknachrichten-ID für eine einzelne E-Mail immer eine eindeutige Absenderadresse enthält.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    Der `summarize` Operator kann einfach durch ersetzt `project` werden, sodass potenziell dieselben Ergebnisse erzielt werden, während weniger Ressourcen verbraucht werden:

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    Das folgende Beispiel ist eine effizientere Verwendung, `summarize` da es mehrere unterschiedliche Instanzen einer Absenderadresse geben kann, die E-Mails an dieselbe Empfängeradresse sendet. Solche Kombinationen sind weniger unterschiedlich und weisen wahrscheinlich Duplikate auf.

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- **Mischen Sie die Abfrage**: Die Abfrage wird zwar `summarize` am besten in Spalten mit sich wiederholenden Werten verwendet, aber dieselben Spalten können auch _eine hohe Kardinälität_ oder eine große Anzahl eindeutiger Werte aufweisen. Wie der `join` Operator können Sie auch den [Shuffle-Hinweis](/azure/data-explorer/kusto/query/shufflequery) anwenden, `summarize` um die Verarbeitungslast zu verteilen und die Leistung beim Arbeiten mit Spalten mit hoher Kardinalität potenziell zu verbessern.

    Die folgende Abfrage `summarize` verwendet, um unterschiedliche Empfänger-E-Mail-Adressen zu zählen, die in Hunderten von Tausenden in großen Organisationen ausgeführt werden können. Um die Leistung zu verbessern, umfasst es `hint.shufflekey` Folgendes:

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
Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen. Ein Angreifer könnte beispielsweise auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen. Der Angreifer könnte auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.

Wenden Sie die folgenden Methoden an, um dauerhafte Abfragen rund um Befehlszeilen zu erstellen:

- Identifizieren Sie die bekannten Prozesse (z. *B.net.exe* oder *psexec.exe),* indem Sie nach den Dateinamenfeldern suchen, anstatt nach der Befehlszeile selbst zu filtern.
- Analysieren von Befehlszeilenabschnitten mithilfe der [funktion parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)
- Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge. Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.
- Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung. Verwenden Sie beispielsweise `=~` , und anstelle von , und `in~` `contains` `==` `in` `contains_cs` .
- Um Befehlszeilen-Verschleierungstechniken zu vermeiden, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinander folgende Leerzeichen durch ein einzelnes Leerzeichen ersetzen. Es gibt komplexere Verschleierungstechniken, die andere Ansätze erfordern, aber diese Optimierungen können dabei helfen, gängige Methoden zu beheben.

Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen einer Abfrage, die nach der Datei *net.exe* sucht, um den Firewalldienst "MpsSvc" zu beenden:

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

### <a name="ingest-data-from-external-sources"></a>Erfassen von Daten aus externen Quellen
Um lange Listen oder große Tabellen in die Abfrage zu integrieren, verwenden Sie den [Operator für externe Daten,](/azure/data-explorer/kusto/query/externaldata-operator) um Daten von einem angegebenen URI zu erfassen. Sie können Daten aus Dateien im TXT-, CSV-, JSON- oder [anderen Formaten](/azure/data-explorer/ingestion-supported-formats)abrufen. Das folgende Beispiel zeigt, wie Sie die umfangreiche Liste der SCHADSOFTWARE SHA-256-Hashes nutzen können, die von MalwareBazaar (abuse.ch) bereitgestellt werden, um Anlagen in E-Mails zu überprüfen:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string)
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
Es gibt verschiedene Funktionen, mit denen Sie Zeichenfolgen effizient verarbeiten können, die eine Analyse oder Konvertierung erfordern.

| Zeichenfolge | Funktion | Verwendungsbeispiel |
|--|--|--|
| Befehlszeilen | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Extrahieren Sie den Befehl und alle Argumente. |
| Paths | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Extrahieren Sie die Abschnitte eines Datei- oder Ordnerpfads. |
| Versionsnummern | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct a version number with up to four sections and up to eight characters per section. Verwenden Sie die analysierten Daten, um das Versionszeitalter zu vergleichen. |
| IPv4-Adressen | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertieren sie eine IPv4-Adresse in eine lange ganze Zahl. Um IPv4-Adressen zu vergleichen, ohne sie zu konvertieren, verwenden [Sie ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-Adressen | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertieren Sie eine IPv4- oder IPv6-Adresse in die kanonische IPv6-Schreibweise. Um IPv6-Adressen zu vergleichen, verwenden [Sie ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Informationen zu allen unterstützten Analysefunktionen [finden Sie unter Kusto-Zeichenfolgenfunktionen.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)

>[!NOTE]
>Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender für Endpunkt verfügbar. [Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um nach Bedrohungen mithilfe weiterer Datenquellen zu suchen. Sie können Ihre Workflows für die erweiterte Suche von Microsoft Defender für Endpunkt in Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrieren erweiterter Suchabfragen von Microsoft Defender für Endpunkt ausführen.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Verwandte Themen
- [Kusto-Abfragesprachendokumentation](/azure/data-explorer/kusto/query/)
- [Kontingente und Verwendungsparameter](advanced-hunting-limits.md)
- [Behandeln von Fehlern bei der erweiterten Suche](advanced-hunting-errors.md)
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)