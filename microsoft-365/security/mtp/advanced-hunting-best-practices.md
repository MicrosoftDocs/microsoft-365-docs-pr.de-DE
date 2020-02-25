---
title: Bewährte Methoden für Erweiterte Suche in Microsoft Threat Protection
description: Erfahren Sie, wie Sie schnelle, effiziente und fehlerfreie Suchanfragen bei der Bedrohungssuche mit Hilfe der erweiterten Suche erstellen können.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID
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
ms.openlocfilehash: a859aa201b43813d6c66a797cbfee160051d5103
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235064"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="06eb4-104">Bewährte Methoden für Erweiterte Suchanfragen</span><span class="sxs-lookup"><span data-stu-id="06eb4-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="06eb4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="06eb4-105">**Applies to:**</span></span>
- <span data-ttu-id="06eb4-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="06eb4-106">Microsoft Threat Protection</span></span>



## <a name="optimize-query-performance"></a><span data-ttu-id="06eb4-107">Optimieren der Abfrageleistung</span><span class="sxs-lookup"><span data-stu-id="06eb4-107">Optimize query performance</span></span>
<span data-ttu-id="06eb4-108">Wenden Sie diese Empfehlungen an, um Ergebnisse schneller zu erhalten und Timeouts bei der Ausführung komplexer Abfragen zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="06eb4-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="06eb4-109">Verwenden Sie beim Ausprobieren neuer Abfragen immer `limit`, um extrem große Resultset zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="06eb4-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="06eb4-110">Sie können die Größe der Resultsets auch mithilfe von `count` bewerten.</span><span class="sxs-lookup"><span data-stu-id="06eb4-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="06eb4-111">Verwenden Sie zunächst Zeitfilter.</span><span class="sxs-lookup"><span data-stu-id="06eb4-111">Use time filters first.</span></span> <span data-ttu-id="06eb4-112">Im Idealfall sollten Sie Ihre Suchanfragen auf geradzahlige Tage beschränken.</span><span class="sxs-lookup"><span data-stu-id="06eb4-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="06eb4-113">Setzen Sie Filter, die die meisten Daten zu Beginn der Abfrage entfernen sollen, direkt nach dem Zeitfilter.</span><span class="sxs-lookup"><span data-stu-id="06eb4-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="06eb4-114">Verwenden Sie den Operator`has` anstatt`contains`, wenn Sie nach vollständigen Token suchen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="06eb4-115">Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen über alle Spalten hinweg durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="06eb4-116">Wenn Sie Tabellen zusammenfügen, geben Sie zuerst die Tabelle mit weniger Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="06eb4-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="06eb4-117">`project` nur die notwendigen Spalten aus den Tabellen, die Sie verknüpft haben.</span><span class="sxs-lookup"><span data-stu-id="06eb4-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="06eb4-118">Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="06eb4-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="06eb4-119">Tipps und Probleme mit der Suchanfrage</span><span class="sxs-lookup"><span data-stu-id="06eb4-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="06eb4-120">Abfragen mit Prozess-IDs</span><span class="sxs-lookup"><span data-stu-id="06eb4-120">Queries with process IDs</span></span>
<span data-ttu-id="06eb4-121">Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="06eb4-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="06eb4-122">Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="06eb4-123">Um einen eindeutiger Bezeichner für einen Prozess auf einer bestimmten Maschine abzurufen, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit.</span><span class="sxs-lookup"><span data-stu-id="06eb4-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="06eb4-124">Wenn Sie Daten um Prozesse zusammenführen oder zusammenfassen, fügen Sie Spalten für die Maschinenkennung (entweder `DeviceId` oder`DeviceName`), die Prozess-ID (`ProcessId`oder`InitiatingProcessId`) und die Prozesserstellungszeit (`ProcessCreationTime` oder`InitiatingProcessCreationTime`) hinzu.</span><span class="sxs-lookup"><span data-stu-id="06eb4-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="06eb4-125">Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="06eb4-126">Beispielabfrage:</span><span class="sxs-lookup"><span data-stu-id="06eb4-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="06eb4-127">Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="06eb4-128">Abfragen mit Befehlszeilen</span><span class="sxs-lookup"><span data-stu-id="06eb4-128">Queries with command lines</span></span>

<span data-ttu-id="06eb4-129">Befehlszeilen können variieren.</span><span class="sxs-lookup"><span data-stu-id="06eb4-129">Command lines can vary.</span></span> <span data-ttu-id="06eb4-130">Filtern Sie ggf. nach Dateinamen und führen Sie Fuzzyübereinstimmungen durch.</span><span class="sxs-lookup"><span data-stu-id="06eb4-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="06eb4-131">Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="06eb4-132">Ein Angreifer könnte beispielsweise auf eine Bilddatei mit oder ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="06eb4-133">Darüber hinaus kann der Angreifer auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="06eb4-134">Um dauerhaftere Abfragen über Befehlszeilen zu erstellen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="06eb4-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="06eb4-135">Identifizieren Sie die bekannten Prozesse (wie *net.exe* oder *psexec.exe*), indem Sie die Felder mit dem Dateinamen übereinstimmen, anstatt nach dem Befehlszeilenfeld zu filtern.</span><span class="sxs-lookup"><span data-stu-id="06eb4-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="06eb4-136">Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="06eb4-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="06eb4-137">Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.</span><span class="sxs-lookup"><span data-stu-id="06eb4-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="06eb4-138">Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="06eb4-138">Use case insensitive matches.</span></span> <span data-ttu-id="06eb4-139">Verwenden Sie beispielsweise `=~`, `in~`, und `contains` anstelle von `==`, `in`und `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="06eb4-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="06eb4-140">Um die DOS-Befehlszeilenverschleierungstechniken abzuschwächen, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinanderfolgende Leerzeichen durch ein einziges Leerzeichen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="06eb4-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="06eb4-141">Beachten Sie, dass es komplexere DOS-Verschleierungstechniken gibt, die andere Ansätze erfordern, aber diese helfen die gängigsten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="06eb4-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="06eb4-142">Die folgenden Beispiele zeigen verschiedene Möglichkeiten, eine Abfrage zu erstellen, die nach der Datei *net.exe* sucht, um den Dienst Windows Defender Firewall zu beenden:</span><span class="sxs-lookup"><span data-stu-id="06eb4-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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
## <a name="related-topics"></a><span data-ttu-id="06eb4-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="06eb4-143">Related topics</span></span>
- [<span data-ttu-id="06eb4-144">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="06eb4-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06eb4-145">Die Abfragesprache erlernen</span><span class="sxs-lookup"><span data-stu-id="06eb4-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06eb4-146">Verwendung von freigegebenen Abfragen</span><span class="sxs-lookup"><span data-stu-id="06eb4-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06eb4-147">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="06eb4-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06eb4-148">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="06eb4-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
