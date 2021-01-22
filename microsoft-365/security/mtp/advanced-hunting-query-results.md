---
title: Arbeiten mit Abfrageergebnissen für die erweiterte Suche in Microsoft 365 Defender
description: Nutzen der von der erweiterten Suche zurückgegebenen Abfrageergebnisse in Microsoft 365 Defender
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, Visualisierung, Diagramm, Filter, Drilldown
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932322"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="e78cd-104">Arbeiten mit Abfrageergebnissen für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="e78cd-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e78cd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e78cd-105">**Applies to:**</span></span>
- <span data-ttu-id="e78cd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e78cd-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e78cd-107">Während Sie Ihre [](advanced-hunting-overview.md) erweiterten Suchabfragen so erstellen können, dass sehr genaue Informationen zurückgegeben werden, können Sie auch mit den Abfrageergebnissen arbeiten, um weitere Einblicke zu erhalten und bestimmte Aktivitäten und Indikatoren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="e78cd-108">Sie können die folgenden Aktionen für Die Abfrageergebnisse ausführen:</span><span class="sxs-lookup"><span data-stu-id="e78cd-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="e78cd-109">Anzeigen von Ergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="e78cd-109">View results as a table or chart</span></span>
- <span data-ttu-id="e78cd-110">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="e78cd-110">Export tables and charts</span></span>
- <span data-ttu-id="e78cd-111">Drilldown zu detaillierten Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="e78cd-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="e78cd-112">Optimieren Sie Ihre Abfragen direkt aus den Ergebnissen, oder wenden Sie Filter an.</span><span class="sxs-lookup"><span data-stu-id="e78cd-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="e78cd-113">Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="e78cd-113">View query results as a table or chart</span></span>
<span data-ttu-id="e78cd-114">Bei der erweiterten Suche werden Abfrageergebnisse standardmäßig als tabellarische Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e78cd-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="e78cd-115">Sie können auch die gleichen Daten wie ein Diagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="e78cd-116">Die erweiterte Suche unterstützt die folgenden Ansichten:</span><span class="sxs-lookup"><span data-stu-id="e78cd-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="e78cd-117">Ansichtstyp</span><span class="sxs-lookup"><span data-stu-id="e78cd-117">View type</span></span> | <span data-ttu-id="e78cd-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e78cd-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="e78cd-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="e78cd-119">**Table**</span></span> | <span data-ttu-id="e78cd-120">Zeigt die Abfrageergebnisse im tabellarischen Format an.</span><span class="sxs-lookup"><span data-stu-id="e78cd-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="e78cd-121">**Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="e78cd-121">**Column chart**</span></span> | <span data-ttu-id="e78cd-122">Rendert eine Reihe eindeutiger Elemente auf der X-Achse als vertikale Balken, deren Höhen numerische Werte aus einem anderen Feld darstellen</span><span class="sxs-lookup"><span data-stu-id="e78cd-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="e78cd-123">**Gestapelte Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="e78cd-123">**Stacked column chart**</span></span> | <span data-ttu-id="e78cd-124">Rendert eine Reihe eindeutiger Elemente auf der X-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen</span><span class="sxs-lookup"><span data-stu-id="e78cd-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="e78cd-125">**Kreisdiagramm**</span><span class="sxs-lookup"><span data-stu-id="e78cd-125">**Pie chart**</span></span> | <span data-ttu-id="e78cd-126">Rendert Abschnitts kreisdiagramme, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="e78cd-127">Die Größe jedes Kreises stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="e78cd-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="e78cd-128">**Donut (Diagramm)**</span><span class="sxs-lookup"><span data-stu-id="e78cd-128">**Donut chart**</span></span> | <span data-ttu-id="e78cd-129">Rendert Abschnittsbögen, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="e78cd-130">Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="e78cd-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="e78cd-131">**Liniendiagramm**</span><span class="sxs-lookup"><span data-stu-id="e78cd-131">**Line chart**</span></span> | <span data-ttu-id="e78cd-132">Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und verbindet die zeichnungsierten Werte.</span><span class="sxs-lookup"><span data-stu-id="e78cd-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="e78cd-133">**Punkt (Punkt)-Diagramm**</span><span class="sxs-lookup"><span data-stu-id="e78cd-133">**Scatter chart**</span></span> | <span data-ttu-id="e78cd-134">Zeichnet numerische Werte für eine Reihe eindeutiger Elemente</span><span class="sxs-lookup"><span data-stu-id="e78cd-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="e78cd-135">**Flächendiagramm**</span><span class="sxs-lookup"><span data-stu-id="e78cd-135">**Area chart**</span></span> | <span data-ttu-id="e78cd-136">Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und füllt die Abschnitte unterhalb der dargestellten Werte.</span><span class="sxs-lookup"><span data-stu-id="e78cd-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="e78cd-137">Erstellen von Abfragen für effektive Diagramme</span><span class="sxs-lookup"><span data-stu-id="e78cd-137">Construct queries for effective charts</span></span>
<span data-ttu-id="e78cd-138">Beim Rendern von Diagrammen werden bei der erweiterten Suche automatisch die für sie interessantsten Spalten und die zu aggregierenden numerischen Werte identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e78cd-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="e78cd-139">Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurück, die Sie visualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e78cd-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="e78cd-140">Hier sind einige Beispielabfragen und die resultierenden Diagramme.</span><span class="sxs-lookup"><span data-stu-id="e78cd-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="e78cd-141">Warnungen nach Schweregrad</span><span class="sxs-lookup"><span data-stu-id="e78cd-141">Alerts by severity</span></span>
<span data-ttu-id="e78cd-142">Verwenden Sie den Operator, um eine numerische Anzahl der Werte zu `summarize` erhalten, die Sie diagrammen möchten.</span><span class="sxs-lookup"><span data-stu-id="e78cd-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="e78cd-143">Die folgende Abfrage verwendet den Operator, um die Anzahl der Warnungen nach `summarize` Schweregrad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e78cd-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="e78cd-144">Beim Rendern der Ergebnisse zeigt ein Säulendiagramm jeden Schweregradwert als separate Spalte an:</span><span class="sxs-lookup"><span data-stu-id="e78cd-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="e78cd-145">![Abbildung der Abfrageergebnisse der erweiterten Suche, die als Spaltendiagramm angezeigt werden. Abfrageergebnisse für Warnungen nach Schweregrad, ](../../media/advanced-hunting-column-chart.jpg)
 *angezeigt als Säulendiagramm*</span><span class="sxs-lookup"><span data-stu-id="e78cd-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="e78cd-146">Warnungsschweregrad nach Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="e78cd-146">Alert severity by operating system</span></span>
<span data-ttu-id="e78cd-147">Sie können den Operator auch `summarize` verwenden, um Ergebnisse für die Diagrammwerte aus mehreren Feldern vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="e78cd-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="e78cd-148">Sie sollten beispielsweise wissen, wie Warnungsschweregrade auf alle Betriebssysteme verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="e78cd-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="e78cd-149">Die folgende Abfrage verwendet einen Operator, um Betriebssysteminformationen aus der Tabelle zu ziehen, und verwendet dann die Anzahl der Werte in der Tabelle und `join` `DeviceInfo` den `summarize` `OSPlatform` `Severity` Spalten:</span><span class="sxs-lookup"><span data-stu-id="e78cd-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="e78cd-150">Diese Ergebnisse werden am besten mithilfe eines gestapelten Säulendiagramms visualisiert:</span><span class="sxs-lookup"><span data-stu-id="e78cd-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="e78cd-151">![Abbildung der Abfrageergebnisse der erweiterten Suche, die als gestapelte Diagramm angezeigt werden Abfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad, die als ](../../media/advanced-hunting-stacked-chart.jpg)
 *gestapeltes Diagramm angezeigt werden*</span><span class="sxs-lookup"><span data-stu-id="e78cd-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="e78cd-152">Phishing-E-Mails in den Top-Ten-Absenderdomänen</span><span class="sxs-lookup"><span data-stu-id="e78cd-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="e78cd-153">Wenn Es sich um eine Liste von Werten handelt, die nicht begrenzt ist, können Sie den Operator verwenden, um nur die Werte mit den meisten `Top` Instanzen zu diagrammieren.</span><span class="sxs-lookup"><span data-stu-id="e78cd-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="e78cd-154">Um beispielsweise die zehn häufigsten Absenderdomänen mit den meisten Phishing-E-Mails zu erhalten, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="e78cd-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="e78cd-155">Verwenden Sie die Kreisdiagrammansicht, um die Verteilung in den top-Domänen effektiv zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="e78cd-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="e78cd-156">![Abbildung der Abfrageergebnisse der erweiterten Suche, angezeigt als Kreisdiagramm Kreisdiagramm, das die Verteilung von Phishing-E-Mails über die Domänen ](../../media/advanced-hunting-pie-chart.jpg)
 *der obersten Absender hinweg zeigt*</span><span class="sxs-lookup"><span data-stu-id="e78cd-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="e78cd-157">Dateiaktivitäten im Laufe der Zeit</span><span class="sxs-lookup"><span data-stu-id="e78cd-157">File activities over time</span></span>
<span data-ttu-id="e78cd-158">Wenn Sie den Operator mit der Funktion verwenden, können Sie im Laufe der Zeit nach Ereignissen mit einem `summarize` `bin()` bestimmten Indikator suchen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="e78cd-159">Die folgende Abfrage zählt Ereignisse, an denen die Datei beteiligt ist, in Intervallen von 30 Minuten, um Aktivitätsspitzen im Zusammenhang mit `invoice.doc` dieser Datei zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="e78cd-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="e78cd-160">Das folgende Liniendiagramm zeigt deutlich Zeiträume mit einer stärkeren Aktivität `invoice.doc` an:</span><span class="sxs-lookup"><span data-stu-id="e78cd-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="e78cd-161">![Abbildung der Abfrageergebnisse der erweiterten Suche, die als Liniendiagramm angezeigt werden, das die Anzahl der Ereignisse mit einer Datei im Laufe der ](../../media/advanced-hunting-line-chart.jpg)
 *Zeit zeigt*</span><span class="sxs-lookup"><span data-stu-id="e78cd-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="e78cd-162">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="e78cd-162">Export tables and charts</span></span>
<span data-ttu-id="e78cd-163">Wählen Sie nach dem Ausführen einer Abfrage **"Exportieren"** aus, um die Ergebnisse in der lokalen Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e78cd-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="e78cd-164">Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:</span><span class="sxs-lookup"><span data-stu-id="e78cd-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="e78cd-165">**Tabellenansicht** – Die Abfrageergebnisse werden in tabellarischer Form als Microsoft Excel-Arbeitsmappe exportiert.</span><span class="sxs-lookup"><span data-stu-id="e78cd-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="e78cd-166">**Jedes Diagramm** – die Abfrageergebnisse werden als ein JPEG-Bild des gerenderten Diagramms exportiert.</span><span class="sxs-lookup"><span data-stu-id="e78cd-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="e78cd-167">Drilldown aus Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="e78cd-167">Drill down from query results</span></span>
<span data-ttu-id="e78cd-168">Um einen Datensatz in den Abfrageergebnissen schnell zu überprüfen, wählen Sie die entsprechende Zeile aus, um den **Datensatzbereich "Überprüfen" zu** öffnen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="e78cd-169">Der Bereich enthält die folgenden Informationen basierend auf dem ausgewählten Datensatz:</span><span class="sxs-lookup"><span data-stu-id="e78cd-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="e78cd-170">**Ressourcen** – zusammengefasste Ansicht der wichtigsten Objekte (Postfächer, Geräte und Benutzer), die in dem Datensatz enthalten sind, mit verfügbaren Informationen, z. B. Risiko- und Risikostufen</span><span class="sxs-lookup"><span data-stu-id="e78cd-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="e78cd-171">**Prozessstruktur –** für Datensätze mit Prozessinformationen generiert und mithilfe verfügbarer kontextbezogener Informationen bereichert; Im Allgemeinen können Abfragen, die mehr Spalten zurückgeben, zu reichhaltigeren Prozessstrukturen führen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="e78cd-172">**Alle Details** – alle Werte aus den Spalten im Datensatz</span><span class="sxs-lookup"><span data-stu-id="e78cd-172">**All details** — all the values from the columns in the record</span></span>  

![Abbildung des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="e78cd-174">Wenn Sie weitere Informationen zu einer bestimmten Entität in Den Abfrageergebnissen anzeigen möchten, z. B. einen Computer, eine Datei, einen Benutzer, eine IP-Adresse oder eine URL, wählen Sie den Entitätsbezeichner aus, um eine detaillierte Profilseite für diese Entität zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e78cd-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="e78cd-175">Optimieren von Abfragen aus den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="e78cd-175">Tweak your queries from the results</span></span>
<span data-ttu-id="e78cd-176">Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e78cd-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="e78cd-177">Sie können die folgenden Optionen für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="e78cd-177">You can use the options to:</span></span>

- <span data-ttu-id="e78cd-178">Explizites Suchen nach dem ausgewählten Wert (`==`)</span><span class="sxs-lookup"><span data-stu-id="e78cd-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="e78cd-179">Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)</span><span class="sxs-lookup"><span data-stu-id="e78cd-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="e78cd-180">Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with`</span><span class="sxs-lookup"><span data-stu-id="e78cd-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Abbildung des Ergebnissets für die erweiterte Suche](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="e78cd-182">Filtern der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="e78cd-182">Filter the query results</span></span>
<span data-ttu-id="e78cd-183">Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="e78cd-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="e78cd-184">Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="e78cd-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="e78cd-185">Verfeinern Sie Die Abfrage, indem Sie die Schaltflächen für die Werte auswählen, die Sie ein- oder ausschließen möchten, und dann `+` `-` abfrage ausführen **auswählen.**</span><span class="sxs-lookup"><span data-stu-id="e78cd-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Abbildung eines erweiterten Suchfilters](../../media/advanced-hunting-filter.png)

<span data-ttu-id="e78cd-187">Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e78cd-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e78cd-188">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e78cd-188">Related topics</span></span>
- [<span data-ttu-id="e78cd-189">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="e78cd-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e78cd-190">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="e78cd-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e78cd-191">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="e78cd-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e78cd-192">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="e78cd-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e78cd-193">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="e78cd-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e78cd-194">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="e78cd-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e78cd-195">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="e78cd-195">Custom detections overview</span></span>](custom-detections-overview.md)
