---
title: Erlernen der Abfragesprache für die erweiterte Suche in Microsoft Threat Protection
description: Erstellen Sie Ihre erste Suchabfrage für Bedrohungen, und erfahren Sie mehr über die allgemeinen Operatoren und andere Aspekte der Abfragesprache für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungssuche, Cyber-Bedrohungssuche, Suche, Abfrage, Sprache, lernen, erste Abfrage, Telemetrie, Ereignisse, benutzerdefinierte Erkennungen, Schema, Kusto, Operatoren, Datentypen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ed5dd99d2ac569353ed72ddf67d906dfe21e7cd0
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911101"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="ee037-104">Erlernen der Abfragesprache für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ee037-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="ee037-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ee037-105">**Applies to:**</span></span>
- <span data-ttu-id="ee037-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee037-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="ee037-107">Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="ee037-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="ee037-108">Sie können die Kusto-Syntax und -Operatoren verwenden, um Abfragen zu erstellen, die Informationen im [Schema](advanced-hunting-schema-tables.md) suchen, die speziell für die erweiterte Suche strukturiert sind.</span><span class="sxs-lookup"><span data-stu-id="ee037-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="ee037-109">Wenn Sie diese Konzepte besser verstehen möchten, führen Sie Ihre erste Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="ee037-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="ee037-110">Testen Ihrer ersten Abfrage</span><span class="sxs-lookup"><span data-stu-id="ee037-110">Try your first query</span></span>

<span data-ttu-id="ee037-111">Wechseln Sie im Microsoft 365 Security Center zu **Hunting**, um Ihre erste Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ee037-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="ee037-112">Verwenden Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ee037-112">Use the following example as a guide.</span></span>

```
// Finds PowerShell execution events that could involve a download.
ProcessCreationEvents  
| where EventTime > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project EventTime, ComputerName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by EventTime
```

<span data-ttu-id="ee037-113">So sieht es in der erweiterten Suche aus.</span><span class="sxs-lookup"><span data-stu-id="ee037-113">This is how it will look like in advanced hunting.</span></span>

![Abbildung einer erweiterten Suchabfrage in Microsoft Defender ATP](../images/advanced-hunting-query-example.png)

<span data-ttu-id="ee037-115">Die Abfrage beginnt mit einem kurzen Kommentar, der beschreibt, wofür die Abfrage dient.</span><span class="sxs-lookup"><span data-stu-id="ee037-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="ee037-116">Dies ist hilfreich, wenn Sie sich später entscheiden, Ihre Abfrage zu speichern und sie für andere Personen in Ihrer Organisation freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ee037-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```
// Finds PowerShell execution events that could involve a download.
ProcessCreationEvents
```

<span data-ttu-id="ee037-117">Die Abfrage selbst beginnt in der Regel mit einem Tabellennamen gefolgt von einer Reihe von Elementen, die mit einer Pipe (`|`) beginnen.</span><span class="sxs-lookup"><span data-stu-id="ee037-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="ee037-118">In diesem Beispiel beginnen wir, indem wir den Tabellennamen `ProcessCreationEvents` und bei Bedarf weitere Pipe-Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee037-118">In this example, we start by adding  with the table name `ProcessCreationEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="ee037-119">Das erste Pipe-Element ist ein Zeitfilter, der in der letzten sieben Tagen festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="ee037-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="ee037-120">Wenn Sie den Zeitabschnitt so eng wie möglich lassen, wird sichergestellt, dass Abfragen gut ausgeführt werden, überschaubare Ergebnisse zurückgeben und keine Zeitüberschreitungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="ee037-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```
| where EventTime > ago(7d)
```

<span data-ttu-id="ee037-121">Auf den Zeitabschnitt folgt sofort eine Suche nach Dateien, die die PowerShell-Anwendung darstellen.</span><span class="sxs-lookup"><span data-stu-id="ee037-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="ee037-122">Anschließend sucht die Abfrage nach Befehlszeilen, die in der Regeln mit PowerShell verwendet werden, um Dateien herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ee037-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="ee037-123">Da die Abfrage nun die zu suchenden Daten eindeutig identifiziert, können Sie Elemente hinzufügen, die definieren, wie die Ergebnisse aussehen.</span><span class="sxs-lookup"><span data-stu-id="ee037-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="ee037-124">`project` gibt bestimmte Spalten zurück, und `top` schränkt die Anzahl der Ergebnisse ein, sodass die Ergebnisse sinnvoll formatiert sind, eine angemessene Größe aufweisen und einfach zu verarbeiten sind.</span><span class="sxs-lookup"><span data-stu-id="ee037-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```
| project EventTime, ComputerName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by EventTime'
```

<span data-ttu-id="ee037-125">Klicken Sie auf **Abfrage ausführen** aus, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ee037-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="ee037-126">Sie können die Bildschirmansicht erweitern, damit Sie sich auf Ihre Suchabfrage und die Ergebnisse konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="ee037-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="ee037-127">Erlernen häufig verwendeter Operatoren für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ee037-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="ee037-128">Da Sie nun Ihre erste Abfrage ausgeführt und eine allgemeine Vorstellung von deren Komponenten haben, gehen wir einen Schritt zurück und befassen uns mit ein paar Grundlagen.</span><span class="sxs-lookup"><span data-stu-id="ee037-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="ee037-129">Die von der erweiterten Suche verwendete Kusto-Abfragesprache unterstützt eine Reihe von Operatoren, darunter die folgenden allgemeinen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="ee037-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="ee037-130">Operator</span><span class="sxs-lookup"><span data-stu-id="ee037-130">Operator</span></span> | <span data-ttu-id="ee037-131">Beschreibung und Verwendung</span><span class="sxs-lookup"><span data-stu-id="ee037-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="ee037-132">Filtern einer Tabelle auf die Teilmenge von Zeilen, die einem Prädikat entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ee037-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="ee037-133">Erstellen einer Tabelle, in der die Inhalte der Eingabetabelle gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="ee037-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="ee037-134">Zusammenführen der Zeilen von zwei Tabellen, um eine neue Tabelle zu erstellen, indem Werte der angegebenen Spalten aus jeder Tabelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ee037-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="ee037-135">Zurückgeben der Anzahl von Datensätzen im Eingabedatensatz.</span><span class="sxs-lookup"><span data-stu-id="ee037-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="ee037-136">Zurückgeben der ersten n Einträge, sortiert anhand der angegebenen Spalten.</span><span class="sxs-lookup"><span data-stu-id="ee037-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="ee037-137">Zurückkehren nach oben zur angegebenen Zeilenanzahl.</span><span class="sxs-lookup"><span data-stu-id="ee037-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="ee037-138">Auswählen der Spalten, um neue berechnete Spalten aufzunehmen, umzubenennen, zu löschen oder einzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee037-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="ee037-139">Erstellen von berechneten Spalten und Anfügen an das Resultset.</span><span class="sxs-lookup"><span data-stu-id="ee037-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="ee037-140">Zurückgeben eines dynamischen (JSON)-Arrays der Gruppe eindeutiger Werte, die der Ausdruck in der Gruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee037-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="ee037-141">Suchen von Zeilen, die mit einem Prädikat über eine Reihe von Tabellen hinweg übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ee037-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="ee037-142">Wenn Sie ein Beispiel für diese Operatoren sehen möchten, führen Sie diese im Abschnitt **Erste Schritte** in der erweiterten Suche aus.</span><span class="sxs-lookup"><span data-stu-id="ee037-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="ee037-143">Grundlegendes zu Datentypen und deren Auswirkungen auf die Abfragesyntax</span><span class="sxs-lookup"><span data-stu-id="ee037-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="ee037-144">Daten in erweiterten Suchtabellen werden in der Regel in die folgenden Datentypen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="ee037-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="ee037-145">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ee037-145">Data type</span></span> | <span data-ttu-id="ee037-146">Beschreibung und Auswirkungen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="ee037-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="ee037-147">Daten- und Zeitinformationen, die in der Regel Ereigniszeitstempel darstellen</span><span class="sxs-lookup"><span data-stu-id="ee037-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="ee037-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ee037-148">Character string</span></span> |
| `bool` | <span data-ttu-id="ee037-149">„True“ oder „False“</span><span class="sxs-lookup"><span data-stu-id="ee037-149">True or False</span></span> |
| `int` | <span data-ttu-id="ee037-150">Ein numerischer 32-Bit-Wert.</span><span class="sxs-lookup"><span data-stu-id="ee037-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="ee037-151">Ein numerischer 64-Bit-Wert.</span><span class="sxs-lookup"><span data-stu-id="ee037-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="ee037-152">Verwenden von Beispielabfragen</span><span class="sxs-lookup"><span data-stu-id="ee037-152">Use sample queries</span></span>

<span data-ttu-id="ee037-153">Der Abschnitt **Erste Schritte** bietet einige einfache Abfragen mit häufig verwendeten Operatoren.</span><span class="sxs-lookup"><span data-stu-id="ee037-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="ee037-154">Versuchen Sie, diese Abfragen auszuführen und kleine Änderungen daran vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="ee037-154">Try running these queries and making small modifications to them.</span></span>

![Abbildung eines erweiterten Suchfensters](../images/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="ee037-156">Abgesehen von den einfachen Abfragebeispielen können Sie auch auf [freigegebene Abfragen](advanced-hunting-shared-queries.md) für bestimmte Szenarien zur Bedrohungssuche zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ee037-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="ee037-157">Erkunden Sie die freigegebenen Abfragen auf der linken Seite oder das GitHub-Abfragerepository.</span><span class="sxs-lookup"><span data-stu-id="ee037-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="ee037-158">Zugreifen auf die Dokumentation zur Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="ee037-158">Access query language documentation</span></span>

<span data-ttu-id="ee037-159">Weitere Informationen zur Kusto-Abfragesprache und zu unterstützten Operatoren finden Sie unter [Dokumentation zur Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="ee037-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee037-160">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ee037-160">Related topics</span></span>
- [<span data-ttu-id="ee037-161">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="ee037-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ee037-162">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="ee037-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ee037-163">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="ee037-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ee037-164">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="ee037-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ee037-165">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="ee037-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)