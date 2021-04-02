---
title: Abfrage bewährter Methoden für die erweiterte Suche
description: Erfahren Sie, wie Sie schnelle, effiziente und fehlerfreie Suchanfragen bei der Bedrohungssuche mit Hilfe der erweiterten Suche erstellen können.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499257"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="2074f-104">Bewährte Methoden für Erweiterte Suchanfragen</span><span class="sxs-lookup"><span data-stu-id="2074f-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2074f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2074f-105">**Applies to:**</span></span>
- [<span data-ttu-id="2074f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2074f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="2074f-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2074f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2074f-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2074f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="2074f-109">Optimieren der Abfrageleistung</span><span class="sxs-lookup"><span data-stu-id="2074f-109">Optimize query performance</span></span>

<span data-ttu-id="2074f-110">Wenden Sie diese Empfehlungen an, um Ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2074f-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="2074f-111">Verwenden Sie beim Ausprobieren neuer Abfragen immer `limit`, um extrem große Resultset zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2074f-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="2074f-112">Sie können die Größe der Resultsets auch mithilfe von `count` bewerten.</span><span class="sxs-lookup"><span data-stu-id="2074f-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="2074f-113">Verwenden Sie zunächst Zeitfilter.</span><span class="sxs-lookup"><span data-stu-id="2074f-113">Use time filters first.</span></span> <span data-ttu-id="2074f-114">Im Idealfall beschränken Sie Ihre Abfragen auf sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="2074f-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="2074f-115">Setzen Sie Filter, die die meisten Daten zu Beginn der Abfrage entfernen sollen, direkt nach dem Zeitfilter.</span><span class="sxs-lookup"><span data-stu-id="2074f-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="2074f-116">Verwenden Sie den Operator`has` anstatt`contains`, wenn Sie nach vollständigen Token suchen.</span><span class="sxs-lookup"><span data-stu-id="2074f-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="2074f-117">Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen über alle Spalten hinweg durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="2074f-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="2074f-118">Wenn Sie Tabellen zusammenfügen, geben Sie zuerst die Tabelle mit weniger Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="2074f-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="2074f-119">`project` nur die notwendigen Spalten aus den Tabellen, die Sie verknüpft haben.</span><span class="sxs-lookup"><span data-stu-id="2074f-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="2074f-120">Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="2074f-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="2074f-121">Tipps und Probleme mit der Suchanfrage</span><span class="sxs-lookup"><span data-stu-id="2074f-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="2074f-122">Abfragen mit Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="2074f-122">Queries with process IDs</span></span>

<span data-ttu-id="2074f-123">Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="2074f-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="2074f-124">Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen.</span><span class="sxs-lookup"><span data-stu-id="2074f-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="2074f-125">Um einen eindeutigen Bezeichner für einen Prozess auf einem bestimmten Gerät zu erhalten, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="2074f-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="2074f-126">Wenn Sie Daten mit Prozessen verbinden oder zusammenfassen, fügen Sie Spalten für die Geräte-ID (entweder oder ), die Prozess-ID ( oder ) und die `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` Prozesserstellungszeit ( oder `ProcessCreationTime` ) ein. `InitiatingProcessCreationTime`</span><span class="sxs-lookup"><span data-stu-id="2074f-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="2074f-127">Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.</span><span class="sxs-lookup"><span data-stu-id="2074f-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="2074f-128">Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.</span><span class="sxs-lookup"><span data-stu-id="2074f-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="2074f-129">Abfragen mit Befehlszeilen</span><span class="sxs-lookup"><span data-stu-id="2074f-129">Queries with command lines</span></span>

<span data-ttu-id="2074f-130">Befehlszeilen können variieren.</span><span class="sxs-lookup"><span data-stu-id="2074f-130">Command lines can vary.</span></span> <span data-ttu-id="2074f-131">Filtern Sie ggf. nach Dateinamen und führen Sie Fuzzyübereinstimmungen durch.</span><span class="sxs-lookup"><span data-stu-id="2074f-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="2074f-132">Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2074f-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="2074f-133">Ein Angreifer könnte beispielsweise auf eine Bilddatei mit oder ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen.</span><span class="sxs-lookup"><span data-stu-id="2074f-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="2074f-134">Darüber hinaus kann der Angreifer auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2074f-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="2074f-135">Um dauerhaftere Abfragen über Befehlszeilen zu erstellen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2074f-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="2074f-136">Identifizieren Sie die bekannten Prozesse (wie *net.exe* oder *psexec.exe*), indem Sie die Felder mit dem Dateinamen übereinstimmen, anstatt nach dem Befehlszeilenfeld zu filtern.</span><span class="sxs-lookup"><span data-stu-id="2074f-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="2074f-137">Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="2074f-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="2074f-138">Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.</span><span class="sxs-lookup"><span data-stu-id="2074f-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="2074f-139">Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="2074f-139">Use case insensitive matches.</span></span> <span data-ttu-id="2074f-140">Verwenden Sie z. B. `=~` , und anstelle von , `in~` `contains` `==` `in` und `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="2074f-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="2074f-141">Um die DOS-Befehlszeilenverschleierungstechniken abzuschwächen, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinanderfolgende Leerzeichen durch ein einziges Leerzeichen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2074f-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="2074f-142">Beachten Sie, dass es komplexere DOS-Verschleierungstechniken gibt, die andere Ansätze erfordern, aber diese helfen die gängigsten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2074f-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="2074f-143">Die folgenden Beispiele zeigen verschiedene Möglichkeiten, eine Abfrage zu erstellen, die nach der Datei *net.exe* sucht, um den Dienst Windows Defender Firewall zu beenden:</span><span class="sxs-lookup"><span data-stu-id="2074f-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> <span data-ttu-id="2074f-144">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2074f-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2074f-145">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2074f-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="2074f-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2074f-146">Related topics</span></span>

- [<span data-ttu-id="2074f-147">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="2074f-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2074f-148">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="2074f-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2074f-149">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="2074f-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="2074f-150">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="2074f-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2074f-151">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="2074f-151">Custom detections overview</span></span>](overview-custom-detections.md)
