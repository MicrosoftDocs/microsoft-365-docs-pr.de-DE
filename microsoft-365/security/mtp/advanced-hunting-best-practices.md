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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e838ce873a1c3ecc0f437f96e75cc2a40d3af79d
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727271"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="b4a52-104">Bewährte Methoden für Erweiterte Suchanfragen</span><span class="sxs-lookup"><span data-stu-id="b4a52-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4a52-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b4a52-105">**Applies to:**</span></span>
- <span data-ttu-id="b4a52-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4a52-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b4a52-107">Wenden Sie diese Empfehlungen an, um Ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="b4a52-108">Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="b4a52-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="b4a52-109">Verstehen von CPU-Ressourcenkontingenten</span><span class="sxs-lookup"><span data-stu-id="b4a52-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="b4a52-110">Je nach Größe hat jeder Mandant Zugriff auf eine bestimmte Menge von CPU-Ressourcen, die für die Ausführung erweiterter Suchabfragen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="b4a52-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="b4a52-111">Ausführliche Informationen zu verschiedenen Dienstbeschränkungen finden Sie [unter erweiterte Kontingente und Verwendungsparameter.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="b4a52-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="b4a52-112">Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und die Optimierungsleitfaden in diesem Artikel anwenden, um Unterbrechungen aufgrund von Überschreitungen von Kontingenten oder Verwendungsparametern zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="b4a52-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="b4a52-113">Allgemeine Optimierungstipps</span><span class="sxs-lookup"><span data-stu-id="b4a52-113">General optimization tips</span></span>

- <span data-ttu-id="b4a52-114">**Größe neuer Abfragen**– Wenn Sie vermuten, dass eine Abfrage einen großen Ergebnissatz zurücksennt, bewerten Sie ihn zuerst mithilfe des [Count-Operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="b4a52-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="b4a52-115">Verwenden [Sie Grenzwert](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) oder `take` synonym, um große Ergebnissätze zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="b4a52-116">**Frühes** Anwenden von Filtern – Wenden Sie Zeitfilter und andere Filter an, um den Datensatz zu reduzieren, insbesondere vor der Verwendung von Transformations- und Analysefunktionen, z. B. [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)oder [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="b4a52-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="b4a52-117">Im folgenden Beispiel wird die Analysefunktion [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) verwendet, nachdem Filteroperatoren die Anzahl der Datensätze reduziert haben.</span><span class="sxs-lookup"><span data-stu-id="b4a52-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="b4a52-118">**Enthält Beats –** Verwenden Sie den Operator anstelle von , um zu vermeiden, dass Teilzeichenfolgen in Wörtern unnötig `has` durchsucht `contains` werden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="b4a52-119">Informationen zu Zeichenfolgenoperatoren</span><span class="sxs-lookup"><span data-stu-id="b4a52-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="b4a52-120">**In bestimmten Spalten suchen**– Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen in allen Spalten zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="b4a52-121">Verwenden Sie nicht, `*` um alle Spalten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="b4a52-122">**Hoch-/Kleinschreibung –** Die Suche nach Kleinschreibung ist spezifischer und in der Regel performanter.</span><span class="sxs-lookup"><span data-stu-id="b4a52-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="b4a52-123">Die Namen von Zeichenfolgenoperatoren, die bei [der Kleinschreibung](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)beachtet werden, z. `has_cs` B. und `contains_cs` , enden im Allgemeinen mit `_cs` .</span><span class="sxs-lookup"><span data-stu-id="b4a52-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="b4a52-124">Sie können auch den Gleichheitsoperator für die Zwischenschreibung anstelle `==` von `=~` verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="b4a52-125">**Analysieren, nicht extrahieren –** Verwenden Sie [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) nach Möglichkeit den Parse-Operator oder eine Analysefunktion wie [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="b4a52-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="b4a52-126">Vermeiden Sie `matches regex` den Zeichenfolgenoperator oder die [extract()-Funktion,](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)die beide regulären Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="b4a52-127">Reservieren Sie die Verwendung regulärer Ausdrücke für komplexere Szenarien.</span><span class="sxs-lookup"><span data-stu-id="b4a52-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="b4a52-128">Weitere Informationen zu Analysefunktionen</span><span class="sxs-lookup"><span data-stu-id="b4a52-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="b4a52-129">**Filtern von Tabellen ohne Ausdrücke**– Filtern Sie nicht nach einer berechneten Spalte, wenn Sie nach einer Tabellenspalte filtern können.</span><span class="sxs-lookup"><span data-stu-id="b4a52-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="b4a52-130">**Keine 3-Zeichen-Begriffe**– Vermeiden Sie das Vergleichen oder Filtern mit Begriffen mit drei oder weniger Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="b4a52-131">Diese Begriffe werden nicht indiziert, und für deren Übereinstimmung sind mehr Ressourcen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4a52-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="b4a52-132">**Projekt selektiv –** Machen Sie Ihre Ergebnisse leichter zu verstehen, indem Sie nur die benötigten Spalten projiziert.</span><span class="sxs-lookup"><span data-stu-id="b4a52-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="b4a52-133">Das Projiziert bestimmter Spalten vor dem Ausführen von [Verknüpfungsvorgängen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) oder ähnlichen Vorgängen hilft auch, die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b4a52-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="b4a52-134">Optimieren des `join` Operators</span><span class="sxs-lookup"><span data-stu-id="b4a52-134">Optimize the `join` operator</span></span>
<span data-ttu-id="b4a52-135">Der [Verknüpfungsoperator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) führt Zeilen aus zwei Tabellen durch übereinstimmende Werte in angegebenen Spalten zusammen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="b4a52-136">Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="b4a52-137">**Kleinere Tabelle links :** Der Operator gleicht Datensätze in der Tabelle auf der linken Seite der Join-Anweisung mit Datensätzen `join` auf der rechten Seite ab.</span><span class="sxs-lookup"><span data-stu-id="b4a52-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="b4a52-138">Wenn die kleinere Tabelle auf der linken Seite angezeigt wird, müssen weniger Datensätze übereinstimmen, was die Abfrage beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="b4a52-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="b4a52-139">In der folgenden Tabelle wird die linke Tabelle so reduziert, dass sie nur drei bestimmte Geräte abdecken kann, bevor sie mit den `DeviceLogonEvents` `IdentityLogonEvents` Konto-SIDs verknüpfen wird.</span><span class="sxs-lookup"><span data-stu-id="b4a52-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="b4a52-140">Verwenden Sie die **Inner-Join-Variante**– Die Standardmäßige Verknüpfungsrichtung oder die [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) dedupliziert Zeilen in der linken Tabelle durch die Verknüpfungstaste, bevor eine Zeile für jede Übereinstimmung mit der rechten Tabelle zurückgegeben wird. [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)</span><span class="sxs-lookup"><span data-stu-id="b4a52-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="b4a52-141">Wenn die linke Tabelle mehrere Zeilen mit demselben Wert für den Schlüssel enthält, werden diese Zeilen dedupliziert, um für jeden eindeutigen Wert eine einzelne zufällige `join` Zeile zu hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="b4a52-142">Dieses Standardverhalten kann wichtige Informationen aus der linken Tabelle weg lassen, die nützliche Einblicke bieten können.</span><span class="sxs-lookup"><span data-stu-id="b4a52-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="b4a52-143">Die folgende Abfrage zeigt beispielsweise nur eine E-Mail mit einer bestimmten Anlage an, auch wenn dieselbe Anlage mit mehreren E-Mail-Nachrichten gesendet wurde:</span><span class="sxs-lookup"><span data-stu-id="b4a52-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="b4a52-144">Um diese Einschränkung zu umgehen, wenden wir die [Inner-Join-Variante](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) an, indem wir angeben, dass alle Zeilen in der linken Tabelle mit übereinstimmenden Werten `kind=inner` rechts angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b4a52-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="b4a52-145">**Verbinden von Datensätzen aus** einem Zeitfenster – Bei der Untersuchung von Sicherheitsereignissen suchen Analysten nach verwandten Ereignissen, die rund um denselben Zeitraum auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4a52-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="b4a52-146">Das Anwenden desselben Ansatzes bei Verwendung hat auch Vorteile für die Leistung, indem die Anzahl der `join` zu überprüfende Datensätze reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="b4a52-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="b4a52-147">Die folgende Abfrage überprüft innerhalb von 30 Minuten nach dem Empfang einer schädlichen Datei auf Anmeldeereignisse:</span><span class="sxs-lookup"><span data-stu-id="b4a52-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="b4a52-148">**Anwenden von** Zeitfiltern auf beiden Seiten – Auch wenn Sie ein bestimmtes Zeitfenster nicht untersuchen, kann das Anwenden von Zeitfiltern auf der linken und rechten Tabelle die Anzahl der Datensätze reduzieren, um die Leistung zu überprüfen und `join` zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b4a52-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="b4a52-149">Die folgende Abfrage gilt für beide Tabellen, sodass sie nur Datensätze aus der letzten `Timestamp > ago(1h)` Stunde enthält:</span><span class="sxs-lookup"><span data-stu-id="b4a52-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="b4a52-150">**Verwenden Sie Hinweise für die** Leistung – Verwenden Sie Hinweise mit dem Operator, um das Back-End anweisen, die Last beim Ausführen ressourcenintensiver Vorgänge zu `join` verteilen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="b4a52-151">Weitere Informationen zu Verknüpfungshinweisen</span><span class="sxs-lookup"><span data-stu-id="b4a52-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="b4a52-152">Der **[Shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** hilft beispielsweise bei der Verbesserung der Abfrageleistung beim Verknüpfen von Tabellen mit einem Schlüssel mit hoher Kardinalität – einem Schlüssel mit vielen eindeutigen Werten – wie z. B. dem in der folgenden `AccountObjectId` Abfrage:</span><span class="sxs-lookup"><span data-stu-id="b4a52-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="b4a52-153">Der **[Übertragungshinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** hilft, wenn die linke Tabelle klein (bis zu 100.000 Datensätze) und die rechte Tabelle extrem groß ist.</span><span class="sxs-lookup"><span data-stu-id="b4a52-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="b4a52-154">Die folgende Abfrage versucht beispielsweise, einige E-Mails mit  bestimmten Themen mit allen Nachrichten zu verbinden, die Links in der Tabelle `EmailUrlInfo` enthalten:</span><span class="sxs-lookup"><span data-stu-id="b4a52-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="b4a52-155">Optimieren des `summarize` Operators</span><span class="sxs-lookup"><span data-stu-id="b4a52-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="b4a52-156">Der [Zusammenfassungsoperator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregiert den Inhalt einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b4a52-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="b4a52-157">Wenden Sie diese Tipps an, um Abfragen zu optimieren, die diesen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4a52-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="b4a52-158">**Suchen nach unterschiedlichen** Werten – Verwenden Sie im Allgemeinen, um `summarize` unterschiedliche Werte zu finden, die sich wiederholen können.</span><span class="sxs-lookup"><span data-stu-id="b4a52-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="b4a52-159">Es kann unnötig sein, sie zum Aggregieren von Spalten zu verwenden, die keine sich wiederholenden Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4a52-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="b4a52-160">Obwohl eine einzelne E-Mail Teil mehrerer Ereignisse  sein kann, ist das folgende Beispiel keine effiziente Verwendung, da eine Netzwerknachrichten-ID für eine einzelne E-Mail immer eine eindeutige Absenderadresse `summarize` enthält.</span><span class="sxs-lookup"><span data-stu-id="b4a52-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="b4a52-161">Der Operator kann problemlos durch ersetzt werden, was potenziell dieselben Ergebnisse liefert `summarize` und gleichzeitig weniger Ressourcen `project` verbraucht:</span><span class="sxs-lookup"><span data-stu-id="b4a52-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="b4a52-162">Das folgende Beispiel ist eine effizientere Verwendung, da es mehrere unterschiedliche Instanzen einer Absenderadresse gibt, die E-Mails an `summarize` dieselbe Empfängeradresse sendet.</span><span class="sxs-lookup"><span data-stu-id="b4a52-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="b4a52-163">Solche Kombinationen sind weniger unterschiedlich und haben wahrscheinlich Duplikate.</span><span class="sxs-lookup"><span data-stu-id="b4a52-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="b4a52-164">**Abfrage neu** gemischt – Dies wird zwar am besten in Spalten mit sich wiederholenden Werten verwendet, aber dieselben Spalten können auch eine hohe Kardinalität oder eine große Anzahl `summarize` eindeutiger  Werte haben.</span><span class="sxs-lookup"><span data-stu-id="b4a52-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="b4a52-165">Wie der Operator können Sie auch den `join` [Shuffle-Hinweis](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) anwenden, um die Verarbeitungslast zu verteilen und die Leistung beim Betrieb auf Spalten mit hoher Kardinalität `summarize` zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b4a52-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="b4a52-166">Die folgende Abfrage verwendet, um unterschiedliche Empfänger-E-Mail-Adressen zu zählen, die in den Hunderttausenden `summarize` in großen Organisationen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="b4a52-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="b4a52-167">Um die Leistung zu verbessern, umfasst `hint.shufflekey` es:</span><span class="sxs-lookup"><span data-stu-id="b4a52-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="b4a52-168">Abfrageszenarien</span><span class="sxs-lookup"><span data-stu-id="b4a52-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="b4a52-169">Identifizieren eindeutiger Prozesse mit Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="b4a52-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="b4a52-170">Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="b4a52-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="b4a52-171">Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="b4a52-172">Um einen eindeutiger Bezeichner für einen Prozess auf einer bestimmten Maschine abzurufen, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="b4a52-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="b4a52-173">Wenn Sie Daten um Prozesse zusammenführen oder zusammenfassen, fügen Sie Spalten für die Maschinenkennung (entweder `DeviceId` oder`DeviceName`), die Prozess-ID (`ProcessId`oder`InitiatingProcessId`) und die Prozesserstellungszeit (`ProcessCreationTime` oder`InitiatingProcessCreationTime`) hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4a52-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="b4a52-174">Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="b4a52-175">Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="b4a52-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="b4a52-176">Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="b4a52-177">Abfragebefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b4a52-177">Query command lines</span></span>
<span data-ttu-id="b4a52-178">Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="b4a52-179">Ein Angreifer könnte beispielsweise auf eine Bilddatei ohne Pfad, ohne Dateierweiterung, mithilfe von Umgebungsvariablen oder mit Anführungszeichen verweisen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="b4a52-180">Der Angreifer kann auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="b4a52-181">Wenden Sie die folgenden Methoden an, um dauerhaftere Abfragen um Befehlszeilen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="b4a52-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="b4a52-182">Identifizieren Sie die bekannten Prozesse (z. *B.net.exe* oder *psexec.exe*), indem Sie die Dateinamenfelder abgleichen, anstatt in der Befehlszeile selbst zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b4a52-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="b4a52-183">Analysieren von Befehlszeilenabschnitten mithilfe der [parse_command_line()-Funktion](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="b4a52-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="b4a52-184">Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b4a52-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="b4a52-185">Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.</span><span class="sxs-lookup"><span data-stu-id="b4a52-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="b4a52-186">Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="b4a52-186">Use case insensitive matches.</span></span> <span data-ttu-id="b4a52-187">Verwenden Sie z. B. `=~` , und anstelle von , und `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="b4a52-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="b4a52-188">Um befehlszeilenverhinderungstechniken zu verringern, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinander folgende Leerzeichen durch ein einzelnes Leerzeichen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="b4a52-189">Es gibt komplexere Verschleierungstechniken, die andere Ansätze erfordern, aber diese Optimierungen können bei der Behandlung gängiger Techniken hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="b4a52-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="b4a52-190">In den folgenden Beispielen werden verschiedene Möglichkeiten  zum Erstellen einer Abfrage gezeigt, die nach der Datei suchtnet.exeden Firewalldienst "MpsSvc" zu beenden:</span><span class="sxs-lookup"><span data-stu-id="b4a52-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="b4a52-191">Aufnahme von Daten aus externen Quellen</span><span class="sxs-lookup"><span data-stu-id="b4a52-191">Ingest data from external sources</span></span>
<span data-ttu-id="b4a52-192">Um lange Listen oder große Tabellen in Ihre Abfrage zu integrieren, verwenden Sie den [Externaldata-Operator,](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) um Daten aus einem angegebenen URI zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="b4a52-193">Sie können Daten aus Dateien in TXT, CSV, JSON oder anderen [Formaten erhalten.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="b4a52-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="b4a52-194">Das folgende Beispiel zeigt, wie Sie die umfassende Liste der Schadsoftware-SHA-256-Hashes verwenden können, die von MalwareBazaar (abuse.ch) bereitgestellt werden, um Anlagen in E-Mails zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="b4a52-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="b4a52-195">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b4a52-195">Parse strings</span></span>
<span data-ttu-id="b4a52-196">Es gibt verschiedene Funktionen, mit deren Hilfe Sie Zeichenfolgen effizient verarbeiten können, die eine Analyse oder Konvertierung benötigen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="b4a52-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b4a52-197">String</span></span> | <span data-ttu-id="b4a52-198">Funktion</span><span class="sxs-lookup"><span data-stu-id="b4a52-198">Function</span></span> | <span data-ttu-id="b4a52-199">Verwendungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="b4a52-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="b4a52-200">Befehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b4a52-200">Command-lines</span></span> | [<span data-ttu-id="b4a52-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="b4a52-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="b4a52-202">Extrahieren Sie den Befehl und alle Argumente.</span><span class="sxs-lookup"><span data-stu-id="b4a52-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="b4a52-203">Paths</span><span class="sxs-lookup"><span data-stu-id="b4a52-203">Paths</span></span> | [<span data-ttu-id="b4a52-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="b4a52-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="b4a52-205">Extrahieren Sie die Abschnitte eines Datei- oder Ordnerpfads.</span><span class="sxs-lookup"><span data-stu-id="b4a52-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="b4a52-206">Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="b4a52-206">Version numbers</span></span> | [<span data-ttu-id="b4a52-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="b4a52-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="b4a52-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span><span class="sxs-lookup"><span data-stu-id="b4a52-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="b4a52-209">Verwenden Sie die analysierten Daten, um das Versionsalter zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b4a52-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="b4a52-210">IPv4-Adressen</span><span class="sxs-lookup"><span data-stu-id="b4a52-210">IPv4 addresses</span></span> | [<span data-ttu-id="b4a52-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="b4a52-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="b4a52-212">Konvertieren Sie eine IPv4-Adresse in eine lange ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="b4a52-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="b4a52-213">Um IPv4-Adressen zu vergleichen, ohne sie zu konvertieren, verwenden Sie [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="b4a52-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="b4a52-214">IPv6-Adressen</span><span class="sxs-lookup"><span data-stu-id="b4a52-214">IPv6 addresses</span></span> | [<span data-ttu-id="b4a52-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="b4a52-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="b4a52-216">Konvertieren Sie eine IPv4- oder IPv6-Adresse in die kanonische IPv6-Notation.</span><span class="sxs-lookup"><span data-stu-id="b4a52-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="b4a52-217">Verwenden Sie zum Vergleichen von IPv6-Adressen [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="b4a52-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="b4a52-218">Informationen zu allen unterstützten Analysefunktionen finden Sie [unter Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="b4a52-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b4a52-219">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b4a52-219">Related topics</span></span>
- [<span data-ttu-id="b4a52-220">Kusto-Dokumentation zur Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="b4a52-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="b4a52-221">Kontingente und Verwendungsparameter</span><span class="sxs-lookup"><span data-stu-id="b4a52-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="b4a52-222">Behandeln von Fehlern bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="b4a52-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b4a52-223">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b4a52-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4a52-224">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="b4a52-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
