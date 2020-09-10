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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3ca475ef6dbdbd66af47216c4130d748788730c2
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419132"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="cf624-104">Bewährte Methoden für Erweiterte Suchanfragen</span><span class="sxs-lookup"><span data-stu-id="cf624-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="cf624-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cf624-105">**Applies to:**</span></span>
- <span data-ttu-id="cf624-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cf624-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cf624-107">Wenden Sie diese Empfehlungen an, um schneller Ergebnisse zu erzielen und Timeouts beim durchführen komplexer Abfragen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="cf624-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="cf624-108">Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="cf624-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="general-guidance"></a><span data-ttu-id="cf624-109">Allgemeine Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf624-109">General guidance</span></span>

- <span data-ttu-id="cf624-110">**Größe neuer Abfragen**– Wenn Sie vermuten, dass eine Abfrage ein umfangreiches Resultset zurückgibt, bewerten Sie Sie zunächst mithilfe des [Count-Operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="cf624-110">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="cf624-111">Use [Limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) oder sein Synonym `take` , um große Resultsets zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="cf624-111">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="cf624-112">**Filter früh anwenden**– Anwenden von Zeit Filtern und anderen Filtern, um das DataSet zu reduzieren, insbesondere vor der Verwendung von Transformations-und Analysefunktionen wie [SUBSTRING ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="cf624-112">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="cf624-113">Im Beispiel unten wird die Analysefunktion [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem die Anzahl der Datensätze durch die Filteroperatoren reduziert wurde.</span><span class="sxs-lookup"><span data-stu-id="cf624-113">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="cf624-114">**Has Beats enthält**– um unnötige Suche nach Teilzeichenfolgen in Wörtern zu vermeiden, verwenden Sie den- `has` Operator anstelle von `contains` .</span><span class="sxs-lookup"><span data-stu-id="cf624-114">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="cf624-115">Informationen zu Zeichenfolgenoperatoren</span><span class="sxs-lookup"><span data-stu-id="cf624-115">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="cf624-116">**In bestimmten Spalten suchen**– suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen in allen Spalten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cf624-116">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="cf624-117">Verwenden Sie nicht `*` , um alle Spalten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cf624-117">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="cf624-118">**Groß-** und Kleinschreibung für die Geschwindigkeit – bei der Suche nach Groß-/Kleinschreibung werden spezifischere und meist leistungsfähigere Suchvorgänge durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf624-118">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="cf624-119">Namen von [Zeichenfolgenoperatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)mit Berücksichtigung der Groß-/Kleinschreibung, beispielsweise `has_cs` und `contains_cs` , werden normalerweise mit beendet `_cs` .</span><span class="sxs-lookup"><span data-stu-id="cf624-119">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="cf624-120">Sie können auch den gleich-Operator mit Berücksichtigung der groß `==` -/Kleinschreibung anstelle von verwenden `~=` .</span><span class="sxs-lookup"><span data-stu-id="cf624-120">You can also use the case-sensitive equals operator `==` instead of `~=`.</span></span>
- <span data-ttu-id="cf624-121">**Analysieren, nicht extrahieren**– wenn möglich, verwenden Sie den [Analyse Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) oder eine Analysefunktion wie [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="cf624-121">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="cf624-122">Vermeiden `matches regex` Sie den Zeichenfolgenoperator oder die [extract ()-Funktion](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), die beide regulären Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf624-122">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="cf624-123">Reservieren Sie die Verwendung von regulärem Ausdruck für komplexere Szenarien.</span><span class="sxs-lookup"><span data-stu-id="cf624-123">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="cf624-124">Lesen Sie mehr über Analysefunktionen</span><span class="sxs-lookup"><span data-stu-id="cf624-124">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="cf624-125">**Filter Tables not Expressions**: Filtern Sie nicht nach einer berechneten Spalte, wenn Sie nach einer Tabellenspalte filtern können.</span><span class="sxs-lookup"><span data-stu-id="cf624-125">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="cf624-126">**Kein drei**stelliger Begriff – vermeiden Sie einen Vergleich oder eine Filterung mit Ausdrücken mit drei oder weniger Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cf624-126">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="cf624-127">Diese Begriffe sind nicht indiziert und entsprechen diesen, erfordern mehr Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="cf624-127">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="cf624-128">**Projekt selektiv**– machen Sie Ihre Ergebnisse leichter verständlich, indem Sie nur die benötigten Spalten projizieren.</span><span class="sxs-lookup"><span data-stu-id="cf624-128">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="cf624-129">Das projizieren bestimmter Spalten vor dem Ausführen eines [Joins](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) oder ähnlicher Vorgänge trägt ebenfalls zur Leistungsverbesserung bei.</span><span class="sxs-lookup"><span data-stu-id="cf624-129">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="cf624-130">Optimieren des `join` Operators</span><span class="sxs-lookup"><span data-stu-id="cf624-130">Optimize the `join` operator</span></span>
<span data-ttu-id="cf624-131">Der [Join-Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen zusammen, indem er Werte in angegebenen Spalten abstimmt.</span><span class="sxs-lookup"><span data-stu-id="cf624-131">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="cf624-132">Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf624-132">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="cf624-133">**Kleinere Tabelle links**– der `join` Operator vergleicht Datensätze in der Tabelle auf der linken Seite der JOIN-Anweisung mit Datensätzen auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="cf624-133">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="cf624-134">Durch die kleinere Tabelle auf der linken Seite müssen weniger Datensätze abgeglichen werden, wodurch die Abfrage beschleunigt wird.</span><span class="sxs-lookup"><span data-stu-id="cf624-134">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="cf624-135">In der folgenden Tabelle reduzieren wir die linke Tabelle `DeviceLogonEvents` auf nur drei bestimmte Geräte abdecken, bevor Sie es mit `IdentityLogonEvents` SIDs-Konten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf624-135">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="cf624-136">**Verwenden Sie die Geschmacksrichtung Inner Join**– das standardmäßige [Join-Aroma](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) oder der [innerunique-Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) dedupliziert Zeilen in der linken Tabelle mit dem Join-Schlüssel, bevor eine Zeile für jede Übereinstimmung mit der rechten Tabelle zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cf624-136">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="cf624-137">Wenn die linke Tabelle mehrere Zeilen mit dem gleichen Wert für den Schlüssel aufweist `join` , werden diese Zeilen dedupliziert, um für jeden eindeutigen Wert eine einzelne zufällige Zeile zu hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="cf624-137">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="cf624-138">Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weglassen, die nützliche Einblicke bieten können.</span><span class="sxs-lookup"><span data-stu-id="cf624-138">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="cf624-139">Beispielsweise wird in der folgenden Abfrage nur eine e-Mail mit einer bestimmten Anlage angezeigt, auch wenn dieselbe Anlage mit mehreren e-Mail-Nachrichten gesendet wurde:</span><span class="sxs-lookup"><span data-stu-id="cf624-139">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="cf624-140">Um diese Einschränkung zu beheben, wenden wir den Geschmacksmuster [Inner Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem `kind=inner` Sie angeben, dass alle Zeilen in der linken Tabelle mit übereinstimmenden Werten in der rechten angezeigt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="cf624-140">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="cf624-141">**Beitreten von Datensätzen aus einem Zeitfenster**– bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die um den gleichen Zeitraum erfolgen.</span><span class="sxs-lookup"><span data-stu-id="cf624-141">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="cf624-142">Das Anwenden des gleichen Ansatzes bei Verwendung `join` von profitiert auch von der Leistung, indem die Anzahl der zu überprüfenden Datensätze reduziert wird</span><span class="sxs-lookup"><span data-stu-id="cf624-142">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="cf624-143">Die folgende Abfrage sucht innerhalb von 30 Minuten nach dem Empfang einer schädlichen Datei nach Anmeldeereignissen:</span><span class="sxs-lookup"><span data-stu-id="cf624-143">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="cf624-144">**Anwenden von Zeit Filtern auf beiden Seiten**– selbst wenn Sie ein bestimmtes Zeitfenster nicht untersuchen, kann das Anwenden von Zeit Filtern sowohl auf der linken als auch auf der rechten Seite die Anzahl der zu überprüfenden Datensätze verringern und die Leistung verbessern `join` .</span><span class="sxs-lookup"><span data-stu-id="cf624-144">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="cf624-145">Die folgende Abfrage gilt `Timestamp > ago(1h)` für beide Tabellen, sodass nur Datensätze aus der letzten Stunde verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="cf624-145">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="cf624-146">**Verwenden von Hints for Performance**– verwenden Sie Hinweise mit dem `join` Operator, um das Back-End anzuweisen, die Last zu verteilen, wenn ressourcenintensive Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf624-146">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="cf624-147">Weitere Informationen über Join-Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf624-147">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="cf624-148">Beispielsweise hilft der **[shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** beim Verknüpfen von Tabellen mithilfe eines Schlüssels mit hoher Kardinalität die Abfrageleistung – ein Schlüssel mit vielen eindeutigen Werten wie der `AccountObjectId` in der folgenden Abfrage:</span><span class="sxs-lookup"><span data-stu-id="cf624-148">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="cf624-149">Der **[Übertragungs Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** hilft, wenn die linke Tabelle klein ist (bis zu 100.000 Datensätze), und die Rechte Tabelle ist extrem groß.</span><span class="sxs-lookup"><span data-stu-id="cf624-149">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="cf624-150">Die folgende Abfrage versucht beispielsweise, an einigen e-Mails teilzunehmen, bei denen es sich um bestimmte Themen mit _allen_ Nachrichten mit Links in der `EmailUrlInfo` Tabelle handelt:</span><span class="sxs-lookup"><span data-stu-id="cf624-150">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="cf624-151">Optimieren des `summarize` Operators</span><span class="sxs-lookup"><span data-stu-id="cf624-151">Optimize the `summarize` operator</span></span>
<span data-ttu-id="cf624-152">Der [Operator "zusammenfassen](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) " aggregiert den Inhalt einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf624-152">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="cf624-153">Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf624-153">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="cf624-154">Suchen Sie nach unter **schiedlichen Werten**– verwenden Sie im allgemeinen `summarize` die Suche nach unterschiedlichen Werten, die sich wiederholende Werte haben können.</span><span class="sxs-lookup"><span data-stu-id="cf624-154">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="cf624-155">Es kann nicht erforderlich sein, es zum Aggregieren von Spalten zu verwenden, die keine sich wiederholenden Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cf624-155">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="cf624-156">Während eine einzelne e-Mail Teil mehrerer Ereignisse sein kann, ist das Beispiel unten _keine_ effiziente Verwendung, `summarize` da eine Netzwerknachrichten-ID für eine einzelne e-Mail immer mit einer eindeutigen Absenderadresse geliefert wird.</span><span class="sxs-lookup"><span data-stu-id="cf624-156">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="cf624-157">Der `summarize` Operator kann problemlos durch ersetzt werden `project` , wodurch möglicherweise dieselben Ergebnisse erzielt werden, während weniger Ressourcen beansprucht werden:</span><span class="sxs-lookup"><span data-stu-id="cf624-157">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="cf624-158">Das folgende Beispiel ist eine effizientere Verwendung von `summarize` , da es mehrere unterschiedliche Instanzen einer Absenderadresse geben kann, die eine e-Mail an dieselbe Empfängeradresse sendet.</span><span class="sxs-lookup"><span data-stu-id="cf624-158">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="cf624-159">Solche Kombinationen sind unterschiedlich und sind wahrscheinlich Duplikate.</span><span class="sxs-lookup"><span data-stu-id="cf624-159">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="cf624-160">**Die Abfrage shuffle**– während Sie `summarize` am besten in Spalten mit sich wiederholenden Werten verwendet wird, können dieselben Spalten auch eine _hohe Kardinalität_ oder eine große Anzahl eindeutiger Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cf624-160">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="cf624-161">Wie der `join` Operator können Sie auch den [shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) anwenden, `summarize` um die Verarbeitungslast zu verteilen und möglicherweise die Leistung zu verbessern, wenn Sie auf Spalten mit hoher Kardinalität arbeiten.</span><span class="sxs-lookup"><span data-stu-id="cf624-161">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="cf624-162">Die folgende Abfrage verwendet `summarize` , um eine eindeutige Empfänger-e-Mail-Adresse zu zählen, die in den Hunderttausenden in großen Organisationen ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cf624-162">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="cf624-163">Um die Leistung zu verbessern, umfasst es `hint.shufflekey` Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cf624-163">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="cf624-164">Abfrage Szenarien</span><span class="sxs-lookup"><span data-stu-id="cf624-164">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="cf624-165">Identifizieren von eindeutigen Prozessen mit Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="cf624-165">Identify unique processes with process IDs</span></span>
<span data-ttu-id="cf624-166">Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="cf624-166">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="cf624-167">Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen.</span><span class="sxs-lookup"><span data-stu-id="cf624-167">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="cf624-168">Um einen eindeutiger Bezeichner für einen Prozess auf einer bestimmten Maschine abzurufen, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="cf624-168">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="cf624-169">Wenn Sie Daten um Prozesse zusammenführen oder zusammenfassen, fügen Sie Spalten für die Maschinenkennung (entweder `DeviceId` oder`DeviceName`), die Prozess-ID (`ProcessId`oder`InitiatingProcessId`) und die Prozesserstellungszeit (`ProcessCreationTime` oder`InitiatingProcessCreationTime`) hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf624-169">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="cf624-170">Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.</span><span class="sxs-lookup"><span data-stu-id="cf624-170">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="cf624-171">Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="cf624-171">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="cf624-172">Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.</span><span class="sxs-lookup"><span data-stu-id="cf624-172">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="cf624-173">Abfragebefehls Zeilen</span><span class="sxs-lookup"><span data-stu-id="cf624-173">Query command lines</span></span>
<span data-ttu-id="cf624-174">Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cf624-174">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="cf624-175">Beispielsweise kann ein Angreifer auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen.</span><span class="sxs-lookup"><span data-stu-id="cf624-175">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="cf624-176">Der Angreifer kann auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf624-176">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="cf624-177">Wenden Sie die folgenden Methoden an, um dauerhafte Abfragen um Befehlszeilen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="cf624-177">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="cf624-178">Identifizieren Sie die bekannten Prozesse (beispielsweise *net.exe* oder *psexec.exe*), indem Sie Sie in den dateinamenfeldern abgleichen, anstatt die Befehlszeile selbst zu filtern.</span><span class="sxs-lookup"><span data-stu-id="cf624-178">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="cf624-179">Analysieren von Befehlszeilen Abschnitten mithilfe der [parse_command_line ()-Funktion](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="cf624-179">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="cf624-180">Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="cf624-180">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="cf624-181">Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.</span><span class="sxs-lookup"><span data-stu-id="cf624-181">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="cf624-182">Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="cf624-182">Use case insensitive matches.</span></span> <span data-ttu-id="cf624-183">Verwenden Sie beispielsweise, und `=~` `in~` `contains` anstelle von `==` , `in` und `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="cf624-183">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="cf624-184">Um die Methoden zur Verschleierung von Befehlszeilen zu verringern, sollten Sie das Entfernen von Anführungszeichen, das Ersetzen von Kommas durch Leerzeichen und das Ersetzen mehrerer aufeinander folgender Leerzeichen durch ein einzelnes Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="cf624-184">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="cf624-185">Es gibt komplexere Verschleierung-Techniken, die andere Ansätze erfordern, aber diese Optimierungen können dazu beitragen, häufige zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="cf624-185">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="cf624-186">Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen einer Abfrage, die nach der Datei *net.exe* sucht, um den Firewalldienst "mpssvc" zu beenden:</span><span class="sxs-lookup"><span data-stu-id="cf624-186">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="cf624-187">Aufnehmen von Daten aus externen Quellen</span><span class="sxs-lookup"><span data-stu-id="cf624-187">Ingest data from external sources</span></span>
<span data-ttu-id="cf624-188">Wenn Sie lange Listen oder große Tabellen in Ihre Abfrage einbeziehen möchten, verwenden Sie den [externaldata-Operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) , um Daten aus einem angegebenen URI zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="cf624-188">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="cf624-189">Sie können Daten aus Dateien in txt, CSV, JSON oder [anderen Formaten](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)abrufen.</span><span class="sxs-lookup"><span data-stu-id="cf624-189">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="cf624-190">Im folgenden Beispiel wird gezeigt, wie Sie die umfangreiche Liste der von MalwareBazaar (abuse.ch) bereitgestellten SHA-256-Hashes für Schadsoftware verwenden können, um Anhänge in e-Mails zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="cf624-190">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="cf624-191">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="cf624-191">Parse strings</span></span>
<span data-ttu-id="cf624-192">Es gibt verschiedene Funktionen, die Sie verwenden können, um Zeichenfolgen effizient zu verarbeiten, die analysiert oder konvertiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cf624-192">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="cf624-193">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="cf624-193">String</span></span> | <span data-ttu-id="cf624-194">Funktion</span><span class="sxs-lookup"><span data-stu-id="cf624-194">Function</span></span> | <span data-ttu-id="cf624-195">Verwendungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="cf624-195">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="cf624-196">Befehlszeilen</span><span class="sxs-lookup"><span data-stu-id="cf624-196">Command-lines</span></span> | [<span data-ttu-id="cf624-197">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="cf624-197">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="cf624-198">Extrahieren Sie den Befehl und alle Argumente.</span><span class="sxs-lookup"><span data-stu-id="cf624-198">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="cf624-199">Paths</span><span class="sxs-lookup"><span data-stu-id="cf624-199">Paths</span></span> | [<span data-ttu-id="cf624-200">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="cf624-200">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="cf624-201">Extrahieren Sie die Abschnitte eines Datei-oder Ordnerpfads.</span><span class="sxs-lookup"><span data-stu-id="cf624-201">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="cf624-202">Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="cf624-202">Version numbers</span></span> | [<span data-ttu-id="cf624-203">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="cf624-203">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="cf624-204">Dekonstruieren Sie eine Versionsnummer mit bis zu vier Abschnitten und bis zu acht Zeichen pro Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cf624-204">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="cf624-205">Verwenden Sie die analysierten Daten, um das Versions Alter zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="cf624-205">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="cf624-206">IPv4-Adressen</span><span class="sxs-lookup"><span data-stu-id="cf624-206">IPv4 addresses</span></span> | [<span data-ttu-id="cf624-207">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="cf624-207">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="cf624-208">Konvertiert eine IPv4-Adresse in eine lange ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="cf624-208">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="cf624-209">Verwenden Sie [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction), um IPv4-Adressen ohne Konvertierung zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="cf624-209">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="cf624-210">IPv6-Adressen</span><span class="sxs-lookup"><span data-stu-id="cf624-210">IPv6 addresses</span></span> | [<span data-ttu-id="cf624-211">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="cf624-211">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="cf624-212">Konvertieren Sie eine IPv4-oder IPv6-Adresse in die kanonische IPv6-Notation.</span><span class="sxs-lookup"><span data-stu-id="cf624-212">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="cf624-213">Verwenden Sie [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction), um IPv6-Adressen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="cf624-213">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="cf624-214">Informationen zu allen unterstützten Analysefunktionen finden [Sie unter Kusto String Functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="cf624-214">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="cf624-215">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cf624-215">Related topics</span></span>
- [<span data-ttu-id="cf624-216">Dokumentation zur Kusto-Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="cf624-216">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="cf624-217">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="cf624-217">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cf624-218">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="cf624-218">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cf624-219">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="cf624-219">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="cf624-220">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="cf624-220">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cf624-221">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="cf624-221">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cf624-222">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="cf624-222">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
