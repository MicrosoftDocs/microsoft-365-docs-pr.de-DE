---
title: Arbeiten mit erweiterten Suchabfrageergebnissen in Microsoft 365 Defender
description: Nutzen der Abfrageergebnisse, die von der erweiterten Suche in Microsoft 365 Defender zurückgegeben werden
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft 365 Defender, microsoft 365, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Visualisierung, Diagramm, Filter, Drilldown
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
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952596"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="b9c13-104">Arbeiten mit erweiterten Suchabfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="b9c13-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b9c13-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b9c13-105">**Applies to:**</span></span>
- <span data-ttu-id="b9c13-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9c13-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b9c13-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b9c13-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b9c13-108">Während Sie Ihre [](advanced-hunting-overview.md) erweiterten Suchabfragen erstellen können, um sehr genaue Informationen zurück zu geben, können Sie auch mit den Abfrageergebnissen arbeiten, um weitere Einblicke zu erhalten und bestimmte Aktivitäten und Indikatoren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="b9c13-109">Sie können die folgenden Aktionen für Die Abfrageergebnisse ausführen:</span><span class="sxs-lookup"><span data-stu-id="b9c13-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="b9c13-110">Anzeigen von Ergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="b9c13-110">View results as a table or chart</span></span>
- <span data-ttu-id="b9c13-111">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="b9c13-111">Export tables and charts</span></span>
- <span data-ttu-id="b9c13-112">Drilldown zu detaillierten Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="b9c13-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="b9c13-113">Optimieren Sie Ihre Abfragen direkt aus den Ergebnissen, oder wenden Sie Filter an.</span><span class="sxs-lookup"><span data-stu-id="b9c13-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="b9c13-114">Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="b9c13-114">View query results as a table or chart</span></span>
<span data-ttu-id="b9c13-115">Standardmäßig zeigt die erweiterte Suche Abfrageergebnisse als tabellarische Daten an.</span><span class="sxs-lookup"><span data-stu-id="b9c13-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="b9c13-116">Sie können auch die gleichen Daten wie ein Diagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="b9c13-117">Die erweiterte Suche unterstützt die folgenden Ansichten:</span><span class="sxs-lookup"><span data-stu-id="b9c13-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="b9c13-118">Ansichtstyp</span><span class="sxs-lookup"><span data-stu-id="b9c13-118">View type</span></span> | <span data-ttu-id="b9c13-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9c13-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="b9c13-120">**Table**</span><span class="sxs-lookup"><span data-stu-id="b9c13-120">**Table**</span></span> | <span data-ttu-id="b9c13-121">Zeigt die Abfrageergebnisse im tabellarischen Format an</span><span class="sxs-lookup"><span data-stu-id="b9c13-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="b9c13-122">**Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-122">**Column chart**</span></span> | <span data-ttu-id="b9c13-123">Rendert eine Reihe eindeutiger Elemente auf der X-Achse als vertikale Balken, deren Höhen numerische Werte aus einem anderen Feld darstellen</span><span class="sxs-lookup"><span data-stu-id="b9c13-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="b9c13-124">**Gestapelte Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-124">**Stacked column chart**</span></span> | <span data-ttu-id="b9c13-125">Rendert eine Reihe eindeutiger Elemente auf der X-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen</span><span class="sxs-lookup"><span data-stu-id="b9c13-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="b9c13-126">**Kreisdiagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-126">**Pie chart**</span></span> | <span data-ttu-id="b9c13-127">Rendert Abschnitts-Kreise, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="b9c13-128">Die Größe der einzelnen Kreise stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="b9c13-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="b9c13-129">**Donut-Diagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-129">**Donut chart**</span></span> | <span data-ttu-id="b9c13-130">Rendert Abschnittsbögen, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="b9c13-131">Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="b9c13-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="b9c13-132">**Liniendiagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-132">**Line chart**</span></span> | <span data-ttu-id="b9c13-133">Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und verbindet die plotten Werte.</span><span class="sxs-lookup"><span data-stu-id="b9c13-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="b9c13-134">**Punktdiagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-134">**Scatter chart**</span></span> | <span data-ttu-id="b9c13-135">Zeichnet numerische Werte für eine Reihe eindeutiger Elemente</span><span class="sxs-lookup"><span data-stu-id="b9c13-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="b9c13-136">**Flächendiagramm**</span><span class="sxs-lookup"><span data-stu-id="b9c13-136">**Area chart**</span></span> | <span data-ttu-id="b9c13-137">Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und füllt die Abschnitte unterhalb der dargestellten Werte aus.</span><span class="sxs-lookup"><span data-stu-id="b9c13-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="b9c13-138">Erstellen von Abfragen für effektive Diagramme</span><span class="sxs-lookup"><span data-stu-id="b9c13-138">Construct queries for effective charts</span></span>
<span data-ttu-id="b9c13-139">Beim Rendern von Diagrammen identifiziert die erweiterte Suche automatisch die von Interesse interessierten Spalten und die numerischen Werte, die aggregiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="b9c13-140">Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurück zu geben, die visualisiert angezeigt werden möchten.</span><span class="sxs-lookup"><span data-stu-id="b9c13-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="b9c13-141">Hier sind einige Beispielabfragen und die resultierenden Diagramme.</span><span class="sxs-lookup"><span data-stu-id="b9c13-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="b9c13-142">Warnungen nach Schweregrad</span><span class="sxs-lookup"><span data-stu-id="b9c13-142">Alerts by severity</span></span>
<span data-ttu-id="b9c13-143">Verwenden Sie den Operator, um eine numerische Anzahl der Werte zu `summarize` erhalten, die Sie diagrammen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9c13-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="b9c13-144">Die folgende Abfrage verwendet den Operator, um die Anzahl der Warnungen nach `summarize` Schweregrad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9c13-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="b9c13-145">Beim Rendern der Ergebnisse zeigt ein Spaltendiagramm jeden Schweregrad als separate Spalte an:</span><span class="sxs-lookup"><span data-stu-id="b9c13-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="b9c13-146">![Abbildung der erweiterten Suchabfrageergebnisse, die als Spaltendiagramm angezeigt werden Abfrageergebnisse für Warnungen nach Schweregrad, die ](../../media/advanced-hunting-column-chart.jpg)
 *als Spaltendiagramm angezeigt werden*</span><span class="sxs-lookup"><span data-stu-id="b9c13-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="b9c13-147">Warnungsschweregrad nach Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="b9c13-147">Alert severity by operating system</span></span>
<span data-ttu-id="b9c13-148">Sie können den Operator auch `summarize` verwenden, um Ergebnisse für die Diagrammwerte aus mehreren Feldern vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="b9c13-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="b9c13-149">Sie sollten beispielsweise wissen, wie Warnungsschweregrade auf betriebssystemübergreifend verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="b9c13-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="b9c13-150">Die folgende Abfrage verwendet einen Operator, um Betriebssysteminformationen aus der Tabelle zu ziehen, und verwendet dann die Anzahl von Werten in den Spalten und `join` `DeviceInfo` in den `summarize` `OSPlatform` `Severity` Spalten:</span><span class="sxs-lookup"><span data-stu-id="b9c13-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="b9c13-151">Diese Ergebnisse werden am besten mithilfe eines gestapelten Säulendiagramms visualisiert:</span><span class="sxs-lookup"><span data-stu-id="b9c13-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="b9c13-152">![Abbildung der erweiterten Suchabfrageergebnisse, die als gestapelte Diagrammabfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad angezeigt werden, die als ](../../media/advanced-hunting-stacked-chart.jpg)
 *gestapeltes Diagramm angezeigt werden*</span><span class="sxs-lookup"><span data-stu-id="b9c13-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="b9c13-153">Phishing-E-Mails in den top 10 Absenderdomänen</span><span class="sxs-lookup"><span data-stu-id="b9c13-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="b9c13-154">Wenn Sie es mit einer Liste von Werten zu tun haben, die nicht endlich ist, können Sie den Operator verwenden, um nur die Werte mit den meisten `Top` Instanzen zu diagrammieren.</span><span class="sxs-lookup"><span data-stu-id="b9c13-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="b9c13-155">Um beispielsweise die zehn häufigsten Absenderdomänen mit den meisten Phishing-E-Mails zu erhalten, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="b9c13-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="b9c13-156">Verwenden Sie die Kreisdiagrammansicht, um die Verteilung über die obersten Domänen effektiv zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="b9c13-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="b9c13-157">![Abbildung der erweiterten Suchabfrageergebnisse, die als Kreisdiagramm angezeigt werden Kreisdiagramm, das die Verteilung von Phishing-E-Mails ](../../media/advanced-hunting-pie-chart.jpg)
 *auf die Domänen mit den meisten Absendern zeigt*</span><span class="sxs-lookup"><span data-stu-id="b9c13-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="b9c13-158">Dateiaktivitäten im Laufe der Zeit</span><span class="sxs-lookup"><span data-stu-id="b9c13-158">File activities over time</span></span>
<span data-ttu-id="b9c13-159">Mithilfe des Operators mit der Funktion können Sie im Laufe der Zeit nach Ereignissen mit `summarize` `bin()` einem bestimmten Indikator suchen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="b9c13-160">Die folgende Abfrage zählt Ereignisse, die die Datei in Intervallen von 30 Minuten enthalten, um Spitzen der Aktivität im Zusammenhang mit `invoice.doc` dieser Datei zu zeigen:</span><span class="sxs-lookup"><span data-stu-id="b9c13-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="b9c13-161">Das folgende Liniendiagramm zeigt deutlich Zeiträume mit mehr Aktivität `invoice.doc` an:</span><span class="sxs-lookup"><span data-stu-id="b9c13-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="b9c13-162">![Abbildung erweiterter Suchabfrageergebnisse, die als Liniendiagramm angezeigt werden Liniendiagramm mit der Anzahl der Ereignisse, die eine Datei im Laufe der ](../../media/advanced-hunting-line-chart.jpg)
 *Zeit enthalten*</span><span class="sxs-lookup"><span data-stu-id="b9c13-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="b9c13-163">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="b9c13-163">Export tables and charts</span></span>
<span data-ttu-id="b9c13-164">Wählen Sie nach dem Ausführen einer Abfrage **Exportieren** aus, um die Ergebnisse in der lokalen Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b9c13-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="b9c13-165">Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:</span><span class="sxs-lookup"><span data-stu-id="b9c13-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="b9c13-166">**Tabellenansicht** – Die Abfrageergebnisse werden in tabellarischer Form als Microsoft Excel-Arbeitsmappe exportiert.</span><span class="sxs-lookup"><span data-stu-id="b9c13-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="b9c13-167">**Jedes Diagramm** – die Abfrageergebnisse werden als JPEG-Bild des gerenderten Diagramms exportiert.</span><span class="sxs-lookup"><span data-stu-id="b9c13-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="b9c13-168">Drilldown aus Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="b9c13-168">Drill down from query results</span></span>
<span data-ttu-id="b9c13-169">Um einen Datensatz in den Abfrageergebnissen schnell zu überprüfen, wählen Sie die entsprechende Zeile aus, um den **Datensatzbereich** überprüfen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="b9c13-170">Der Bereich stellt die folgenden Informationen basierend auf dem ausgewählten Datensatz zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b9c13-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="b9c13-171">**Assets** – zusammengefasste Ansicht der wichtigsten Objekte (Postfächer, Geräte und Benutzer), die in dem Datensatz enthalten sind, bereichert mit verfügbaren Informationen, z. B. Risiko- und Risikostufen</span><span class="sxs-lookup"><span data-stu-id="b9c13-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="b9c13-172">**Prozessstruktur** – für Datensätze mit Prozessinformationen generiert und mithilfe verfügbarer Kontextinformationen bereichert; Im Allgemeinen können Abfragen, die mehr Spalten zurückgeben, zu reichhaltigeren Prozessstrukturen führen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="b9c13-173">**Alle Details** – alle Werte aus den Spalten im Datensatz</span><span class="sxs-lookup"><span data-stu-id="b9c13-173">**All details** — all the values from the columns in the record</span></span>  

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="b9c13-175">Wenn Sie weitere Informationen zu einer bestimmten Entität in Den Abfrageergebnissen anzeigen möchten, z. B. einen Computer, eine Datei, einen Benutzer, eine IP-Adresse oder eine URL, wählen Sie die Entitäts-ID aus, um eine detaillierte Profilseite für diese Entität zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="b9c13-176">Optimieren von Abfragen aus den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="b9c13-176">Tweak your queries from the results</span></span>
<span data-ttu-id="b9c13-177">Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="b9c13-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="b9c13-178">Sie können die folgenden Optionen für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="b9c13-178">You can use the options to:</span></span>

- <span data-ttu-id="b9c13-179">Explizites Suchen nach dem ausgewählten Wert (`==`)</span><span class="sxs-lookup"><span data-stu-id="b9c13-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="b9c13-180">Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)</span><span class="sxs-lookup"><span data-stu-id="b9c13-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="b9c13-181">Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with`</span><span class="sxs-lookup"><span data-stu-id="b9c13-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Abbildung des erweiterten Ergebnissets für die Suche](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="b9c13-183">Filtern der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="b9c13-183">Filter the query results</span></span>
<span data-ttu-id="b9c13-184">Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="b9c13-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="b9c13-185">Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="b9c13-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="b9c13-186">Verfeinern Sie Ihre Abfrage, indem Sie die Schaltflächen oder für die Werte auswählen, die Sie ein- oder ausschließen möchten, und wählen Sie `+` `-` dann Abfrage ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="b9c13-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Abbildung eines erweiterten Suchfilters](../../media/advanced-hunting-filter.png)

<span data-ttu-id="b9c13-188">Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b9c13-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="b9c13-189">Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender for Endpoint verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9c13-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b9c13-190">[Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um bedrohungen mithilfe von weiteren Datenquellen nach Bedrohungen zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="b9c13-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="b9c13-191">Sie können Ihre erweiterten Suchworkflows von Microsoft Defender for Endpoint zu Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrate advanced hunting queries from Microsoft Defender for Endpoint ausführen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="b9c13-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9c13-192">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b9c13-192">Related topics</span></span>
- [<span data-ttu-id="b9c13-193">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b9c13-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b9c13-194">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="b9c13-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b9c13-195">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="b9c13-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b9c13-196">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="b9c13-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b9c13-197">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="b9c13-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b9c13-198">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="b9c13-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b9c13-199">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="b9c13-199">Custom detections overview</span></span>](custom-detections-overview.md)
