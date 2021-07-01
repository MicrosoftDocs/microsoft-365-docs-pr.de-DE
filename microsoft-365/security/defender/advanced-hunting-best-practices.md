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
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="c0b4b-104">Bewährte Methoden für Erweiterte Suchanfragen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c0b4b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c0b4b-105">**Applies to:**</span></span>
- <span data-ttu-id="c0b4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0b4b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c0b4b-107">Wenden Sie diese Empfehlungen an, um ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="c0b4b-108">Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="c0b4b-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="c0b4b-109">Grundlegendes zu CPU-Ressourcenkontingenten</span><span class="sxs-lookup"><span data-stu-id="c0b4b-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="c0b4b-110">Je nach Größe hat jeder Mandant Zugriff auf eine festgelegte Menge an CPU-Ressourcen, die für die Ausführung erweiterter Suchabfragen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="c0b4b-111">Ausführliche Informationen zu verschiedenen Dienstgrenzwerten [finden Sie unter "Erweiterte Suchkontingente und Verwendungsparameter".](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="c0b4b-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="c0b4b-112">Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und die Optimierungsanleitungen in diesem Artikel anwenden, um Unterbrechungen aufgrund von Überschreitung von Kontingenten oder Verwendungsparametern zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="c0b4b-113">Allgemeine Optimierungstipps</span><span class="sxs-lookup"><span data-stu-id="c0b4b-113">General optimization tips</span></span>

- <span data-ttu-id="c0b4b-114">**Größe neuer Abfragen**– Wenn Sie vermuten, dass eine Abfrage ein großes Resultset zurückgibt, bewerten Sie sie zuerst mithilfe des [Count-Operators.](/azure/data-explorer/kusto/query/countoperator)</span><span class="sxs-lookup"><span data-stu-id="c0b4b-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="c0b4b-115">Verwenden Sie [ Limit ](/azure/data-explorer/kusto/query/limitoperator) oder sein `take` Synonym, um große Resultsets zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="c0b4b-116">**Frühzeitiges Anwenden von Filtern**– Wenden Sie Zeitfilter und andere Filter an, um den Datensatz zu reduzieren, insbesondere vor der Verwendung von Transformations- und Analysefunktionen, z. [B. teilzeichenfolge()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="c0b4b-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="c0b4b-117">Im folgenden Beispiel wird die Analysefunktion [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem filteroperatoren die Anzahl der Datensätze reduziert haben.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="c0b4b-118">**Has beats contains**-To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains` .</span><span class="sxs-lookup"><span data-stu-id="c0b4b-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="c0b4b-119">Informationen zu Zeichenfolgenoperatoren</span><span class="sxs-lookup"><span data-stu-id="c0b4b-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="c0b4b-120">**Suchen In bestimmten Spalten**– Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen in allen Spalten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="c0b4b-121">Verwenden Sie diese Option `*` nicht, um alle Spalten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="c0b4b-122">Bei der Geschwindigkeit wird **die Groß-/Kleinschreibung beachtet–** Suchvorgänge, bei denen die Groß-/Kleinschreibung berücksichtigt wird, sind spezifischer und im Allgemeinen leistungsstärker.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="c0b4b-123">Namen von [Zeichenfolgenoperatoren](/azure/data-explorer/kusto/query/datatypes-string-operators)mit Groß-/Kleinschreibung, z. B. `has_cs` und , `contains_cs` enden in der Regel mit `_cs` .</span><span class="sxs-lookup"><span data-stu-id="c0b4b-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="c0b4b-124">Sie können auch den Operator "Gleichheit zwischen Groß- und Kleinschreibung" `==` anstelle von `=~` verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="c0b4b-125">**Parse, don't extract**-Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="c0b4b-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="c0b4b-126">Vermeiden Sie den `matches regex` Zeichenfolgenoperator oder die [Extract()-Funktion,](/azure/data-explorer/kusto/query/extractfunction)die beide einen regulären Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="c0b4b-127">Reservieren Sie die Verwendung des regulären Ausdrucks für komplexere Szenarien.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="c0b4b-128">Weitere Informationen zu Analysefunktionen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="c0b4b-129">**Filter tables not expressions**- Don't filter on a calculated column if you can filter on a table column.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="c0b4b-130">**Keine Ausdrücke** mit drei Zeichen – Vermeiden Sie das Vergleichen oder Filtern mit Begriffen mit maximal drei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="c0b4b-131">Diese Begriffe sind nicht indiziert, und für den Abgleich dieser Begriffe sind weitere Ressourcen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="c0b4b-132">**Project selektiv**– Machen Sie Ihre Ergebnisse leichter verständlich, indem Sie nur die benötigten Spalten projizieren.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="c0b4b-133">Das Projizieren bestimmter Spalten vor dem Ausführen von [Verknüpfungsvorgängen](/azure/data-explorer/kusto/query/joinoperator) oder ähnlichen Vorgängen verbessert auch die Leistung.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="c0b4b-134">Optimieren des `join` Operators</span><span class="sxs-lookup"><span data-stu-id="c0b4b-134">Optimize the `join` operator</span></span>
<span data-ttu-id="c0b4b-135">Der [Verknüpfungsoperator](/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen zusammen, indem Werte in angegebenen Spalten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="c0b4b-136">Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="c0b4b-137">**Kleinere Tabelle links**– Der `join` Operator gleicht Datensätze in der Tabelle auf der linken Seite der Join-Anweisung mit Datensätzen auf der rechten Seite ab.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="c0b4b-138">Wenn die kleinere Tabelle auf der linken Seite vorhanden ist, müssen weniger Datensätze abgeglichen werden, wodurch die Abfrage beschleunigt wird.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span>

    <span data-ttu-id="c0b4b-139">In der folgenden Tabelle wird die linke Tabelle so reduziert, dass nur drei bestimmte Geräte abgedeckt werden, `DeviceLogonEvents` bevor sie `IdentityLogonEvents` mithilfe von Konto-SIDs verbunden wird.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>

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

- <span data-ttu-id="c0b4b-140">**Verwenden Sie den inneren Join-Typ**– die [Standardverknüpfungsart](/azure/data-explorer/kusto/query/joinoperator#join-flavors) oder die [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) dedupliziert Zeilen in der linken Tabelle durch die Verknüpfungsschlüssel, bevor Sie eine Zeile für jede Übereinstimmung an die rechte Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="c0b4b-141">Wenn die linke Tabelle mehrere Zeilen mit demselben Wert für den `join` Schlüssel aufweist, werden diese Zeilen dedupliziert, um eine einzelne zufällige Zeile für jeden eindeutigen Wert zu belassen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="c0b4b-142">Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weglassen, die nützliche Einblicke liefern können.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="c0b4b-143">Die folgende Abfrage zeigt beispielsweise nur eine E-Mail mit einer bestimmten Anlage an, auch wenn dieselbe Anlage mit mehreren E-Mail-Nachrichten gesendet wurde:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    <span data-ttu-id="c0b4b-144">Um diese Einschränkung zu beheben, wenden wir die [innere Verknüpfungsart](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem wir angeben, `kind=inner` dass alle Zeilen in der linken Tabelle mit übereinstimmenden Werten auf der rechten Seite angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- <span data-ttu-id="c0b4b-145">**Verknüpfen von Datensätzen aus einem Zeitfenster**– Bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die ungefähr im gleichen Zeitraum auftreten.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="c0b4b-146">Das Anwenden desselben Ansatzes bei Verwendung `join` hat auch Vorteile bei der Leistung, da die Anzahl der zu überprüfenden Datensätze reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>

    <span data-ttu-id="c0b4b-147">Die folgende Abfrage überprüft innerhalb von 30 Minuten nach Dem Empfang einer schädlichen Datei auf Anmeldeereignisse:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="c0b4b-148">**Anwenden von Zeitfiltern auf beiden Seiten**– Auch wenn Sie kein bestimmtes Zeitfenster untersuchen, kann das Anwenden von Zeitfiltern auf der linken und rechten Tabelle die Anzahl der Datensätze reduzieren, um die Leistung zu überprüfen und zu `join` verbessern.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="c0b4b-149">Die folgende Abfrage gilt für `Timestamp > ago(1h)` beide Tabellen, sodass nur Datensätze aus der letzten Stunde verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- <span data-ttu-id="c0b4b-150">**Verwenden Sie Hinweise zur Leistung**– Verwenden Sie Hinweise mit dem `join` Operator, um das Back-End anzuweisen, Last zu verteilen, wenn ressourcenintensive Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="c0b4b-151">Weitere Informationen zu Verknüpfungshinweisen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="c0b4b-152">Beispielsweise verbessert der **[Shuffle-Hinweis](/azure/data-explorer/kusto/query/shufflequery)** die Abfrageleistung beim Verknüpfen von Tabellen mithilfe eines Schlüssels mit hoher Kardinalität – einem Schlüssel mit vielen eindeutigen Werten – wie z. B. `AccountObjectId` der folgenden Abfrage:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    <span data-ttu-id="c0b4b-153">Der **[Übertragungshinweis hilft,](/azure/data-explorer/kusto/query/broadcastjoin)** wenn die linke Tabelle klein ist (bis zu 100.000 Datensätze) und die rechte Tabelle extrem groß ist.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="c0b4b-154">Die folgende Abfrage versucht beispielsweise, einige E-Mails mit bestimmten Betreffzeilen mit _allen_ Nachrichten zu verknüpfen, die Links in der `EmailUrlInfo` Tabelle enthalten:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="c0b4b-155">Optimieren des `summarize` Operators</span><span class="sxs-lookup"><span data-stu-id="c0b4b-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="c0b4b-156">Der [Zusammenfassungsoperator](/azure/data-explorer/kusto/query/summarizeoperator) aggregiert den Inhalt einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="c0b4b-157">Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="c0b4b-158">**Unterschiedliche Werte** finden – Verwenden Sie im Allgemeinen `summarize` unterschiedliche Werte, die wiederholt werden können.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="c0b4b-159">Es kann nicht erforderlich sein, sie zum Aggregieren von Spalten zu verwenden, die keine wiederholten Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="c0b4b-160">Während eine einzelne E-Mail Teil mehrerer Ereignisse sein kann, ist das folgende Beispiel _keine_ effiziente Verwendung, `summarize` da eine Netzwerknachrichten-ID für eine einzelne E-Mail immer eine eindeutige Absenderadresse enthält.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    <span data-ttu-id="c0b4b-161">Der `summarize` Operator kann einfach durch ersetzt `project` werden, sodass potenziell dieselben Ergebnisse erzielt werden, während weniger Ressourcen verbraucht werden:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    <span data-ttu-id="c0b4b-162">Das folgende Beispiel ist eine effizientere Verwendung, `summarize` da es mehrere unterschiedliche Instanzen einer Absenderadresse geben kann, die E-Mails an dieselbe Empfängeradresse sendet.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="c0b4b-163">Solche Kombinationen sind weniger unterschiedlich und weisen wahrscheinlich Duplikate auf.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- <span data-ttu-id="c0b4b-164">**Mischen Sie die Abfrage**: Die Abfrage wird zwar `summarize` am besten in Spalten mit sich wiederholenden Werten verwendet, aber dieselben Spalten können auch _eine hohe Kardinälität_ oder eine große Anzahl eindeutiger Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="c0b4b-165">Wie der `join` Operator können Sie auch den [Shuffle-Hinweis](/azure/data-explorer/kusto/query/shufflequery) anwenden, `summarize` um die Verarbeitungslast zu verteilen und die Leistung beim Arbeiten mit Spalten mit hoher Kardinalität potenziell zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="c0b4b-166">Die folgende Abfrage `summarize` verwendet, um unterschiedliche Empfänger-E-Mail-Adressen zu zählen, die in Hunderten von Tausenden in großen Organisationen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="c0b4b-167">Um die Leistung zu verbessern, umfasst es `hint.shufflekey` Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="c0b4b-168">Abfrageszenarien</span><span class="sxs-lookup"><span data-stu-id="c0b4b-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="c0b4b-169">Identifizieren eindeutiger Prozesse mit Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="c0b4b-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="c0b4b-170">Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="c0b4b-171">Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="c0b4b-172">Um einen eindeutiger Bezeichner für einen Prozess auf einer bestimmten Maschine abzurufen, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="c0b4b-173">Wenn Sie Daten um Prozesse zusammenführen oder zusammenfassen, fügen Sie Spalten für die Maschinenkennung (entweder `DeviceId` oder`DeviceName`), die Prozess-ID (`ProcessId`oder`InitiatingProcessId`) und die Prozesserstellungszeit (`ProcessCreationTime` oder`InitiatingProcessCreationTime`) hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="c0b4b-174">Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="c0b4b-175">Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="c0b4b-176">Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="c0b4b-177">Abfragebefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-177">Query command lines</span></span>
<span data-ttu-id="c0b4b-178">Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="c0b4b-179">Ein Angreifer könnte beispielsweise auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="c0b4b-180">Der Angreifer könnte auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="c0b4b-181">Wenden Sie die folgenden Methoden an, um dauerhafte Abfragen rund um Befehlszeilen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="c0b4b-182">Identifizieren Sie die bekannten Prozesse (z. *B.net.exe* oder *psexec.exe),* indem Sie nach den Dateinamenfeldern suchen, anstatt nach der Befehlszeile selbst zu filtern.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="c0b4b-183">Analysieren von Befehlszeilenabschnitten mithilfe der [funktion parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="c0b4b-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span>
- <span data-ttu-id="c0b4b-184">Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="c0b4b-185">Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="c0b4b-186">Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-186">Use case insensitive matches.</span></span> <span data-ttu-id="c0b4b-187">Verwenden Sie beispielsweise `=~` , und anstelle von , und `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="c0b4b-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="c0b4b-188">Um Befehlszeilen-Verschleierungstechniken zu vermeiden, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinander folgende Leerzeichen durch ein einzelnes Leerzeichen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="c0b4b-189">Es gibt komplexere Verschleierungstechniken, die andere Ansätze erfordern, aber diese Optimierungen können dabei helfen, gängige Methoden zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="c0b4b-190">Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen einer Abfrage, die nach der Datei *net.exe* sucht, um den Firewalldienst "MpsSvc" zu beenden:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="c0b4b-191">Erfassen von Daten aus externen Quellen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-191">Ingest data from external sources</span></span>
<span data-ttu-id="c0b4b-192">Um lange Listen oder große Tabellen in die Abfrage zu integrieren, verwenden Sie den [Operator für externe Daten,](/azure/data-explorer/kusto/query/externaldata-operator) um Daten von einem angegebenen URI zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="c0b4b-193">Sie können Daten aus Dateien im TXT-, CSV-, JSON- oder [anderen Formaten](/azure/data-explorer/ingestion-supported-formats)abrufen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="c0b4b-194">Das folgende Beispiel zeigt, wie Sie die umfangreiche Liste der SCHADSOFTWARE SHA-256-Hashes nutzen können, die von MalwareBazaar (abuse.ch) bereitgestellt werden, um Anlagen in E-Mails zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="c0b4b-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="c0b4b-195">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-195">Parse strings</span></span>
<span data-ttu-id="c0b4b-196">Es gibt verschiedene Funktionen, mit denen Sie Zeichenfolgen effizient verarbeiten können, die eine Analyse oder Konvertierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span>

| <span data-ttu-id="c0b4b-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c0b4b-197">String</span></span> | <span data-ttu-id="c0b4b-198">Funktion</span><span class="sxs-lookup"><span data-stu-id="c0b4b-198">Function</span></span> | <span data-ttu-id="c0b4b-199">Verwendungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="c0b4b-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="c0b4b-200">Befehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-200">Command-lines</span></span> | [<span data-ttu-id="c0b4b-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="c0b4b-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="c0b4b-202">Extrahieren Sie den Befehl und alle Argumente.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-202">Extract the command and all arguments.</span></span> |
| <span data-ttu-id="c0b4b-203">Paths</span><span class="sxs-lookup"><span data-stu-id="c0b4b-203">Paths</span></span> | [<span data-ttu-id="c0b4b-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="c0b4b-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="c0b4b-205">Extrahieren Sie die Abschnitte eines Datei- oder Ordnerpfads.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="c0b4b-206">Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="c0b4b-206">Version numbers</span></span> | [<span data-ttu-id="c0b4b-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="c0b4b-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="c0b4b-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="c0b4b-209">Verwenden Sie die analysierten Daten, um das Versionszeitalter zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="c0b4b-210">IPv4-Adressen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-210">IPv4 addresses</span></span> | [<span data-ttu-id="c0b4b-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="c0b4b-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="c0b4b-212">Konvertieren sie eine IPv4-Adresse in eine lange ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="c0b4b-213">Um IPv4-Adressen zu vergleichen, ohne sie zu konvertieren, verwenden [Sie ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="c0b4b-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="c0b4b-214">IPv6-Adressen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-214">IPv6 addresses</span></span> | [<span data-ttu-id="c0b4b-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="c0b4b-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="c0b4b-216">Konvertieren Sie eine IPv4- oder IPv6-Adresse in die kanonische IPv6-Schreibweise.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="c0b4b-217">Um IPv6-Adressen zu vergleichen, verwenden [Sie ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="c0b4b-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="c0b4b-218">Informationen zu allen unterstützten Analysefunktionen [finden Sie unter Kusto-Zeichenfolgenfunktionen.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="c0b4b-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span>

>[!NOTE]
><span data-ttu-id="c0b4b-219">Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender für Endpunkt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-219">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c0b4b-220">[Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um nach Bedrohungen mithilfe weiterer Datenquellen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c0b4b-220">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="c0b4b-221">Sie können Ihre Workflows für die erweiterte Suche von Microsoft Defender für Endpunkt in Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrieren erweiterter Suchabfragen von Microsoft Defender für Endpunkt ausführen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="c0b4b-221">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0b4b-222">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c0b4b-222">Related topics</span></span>
- [<span data-ttu-id="c0b4b-223">Kusto-Abfragesprachendokumentation</span><span class="sxs-lookup"><span data-stu-id="c0b4b-223">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="c0b4b-224">Kontingente und Verwendungsparameter</span><span class="sxs-lookup"><span data-stu-id="c0b4b-224">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="c0b4b-225">Behandeln von Fehlern bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="c0b4b-225">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="c0b4b-226">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c0b4b-226">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c0b4b-227">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c0b4b-227">Learn the query language</span></span>](advanced-hunting-query-language.md)