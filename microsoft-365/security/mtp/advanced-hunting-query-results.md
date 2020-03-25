---
title: Arbeiten mit erweiterten Jagd Abfrageergebnissen im Microsoft Threat Protection
description: Nutzen Sie die von Advanced Hunting zurückgegebenen Abfrageergebnisse in Microsoft Threat Protection.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, Visualisierung, Diagramm, Filter, Drilldown
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929151"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="25e2e-104">Arbeiten mit erweiterten Jagd Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="25e2e-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="25e2e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="25e2e-105">**Applies to:**</span></span>
- <span data-ttu-id="25e2e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="25e2e-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="25e2e-107">Während Sie Ihre [erweiterten Jagd](advanced-hunting-overview.md) Abfragen erstellen können, um sehr genaue Informationen zurückzugeben, können Sie auch mit den Abfrageergebnissen zusammenarbeiten, um weitere Einblicke zu gewinnen und bestimmte Aktivitäten und Indikatoren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="25e2e-108">Sie können die folgenden Aktionen für die Abfrageergebnisse ausführen:</span><span class="sxs-lookup"><span data-stu-id="25e2e-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="25e2e-109">Anzeigen von Ergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="25e2e-109">View results as a table or chart</span></span>
- <span data-ttu-id="25e2e-110">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="25e2e-110">Export tables and charts</span></span>
- <span data-ttu-id="25e2e-111">Drilldown zu detaillierten Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="25e2e-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="25e2e-112">Optimieren der Abfragen direkt aus den Ergebnissen oder Anwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="25e2e-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="25e2e-113">Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="25e2e-113">View query results as a table or chart</span></span>
<span data-ttu-id="25e2e-114">Standardmäßig zeigt Advanced Hunting Abfrageergebnisse als tabellarische Daten an.</span><span class="sxs-lookup"><span data-stu-id="25e2e-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="25e2e-115">Sie können auch dieselben Daten wie ein Diagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="25e2e-116">Die erweiterte Suche unterstützt die folgenden Ansichten:</span><span class="sxs-lookup"><span data-stu-id="25e2e-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="25e2e-117">Ansichtstyp</span><span class="sxs-lookup"><span data-stu-id="25e2e-117">View type</span></span> | <span data-ttu-id="25e2e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25e2e-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="25e2e-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="25e2e-119">**Table**</span></span> | <span data-ttu-id="25e2e-120">Zeigt die Abfrageergebnisse im tabellarischen Format an.</span><span class="sxs-lookup"><span data-stu-id="25e2e-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="25e2e-121">**Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-121">**Column chart**</span></span> | <span data-ttu-id="25e2e-122">Rendert eine Reihe von eindeutigen Elementen auf der x-Achse als vertikale Balken, deren Höhe numerische Werte aus einem anderen Feld darstellt.</span><span class="sxs-lookup"><span data-stu-id="25e2e-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="25e2e-123">**Gestapeltes Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-123">**Stacked column chart**</span></span> | <span data-ttu-id="25e2e-124">Rendert eine Reihe von eindeutigen Elementen auf der x-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="25e2e-125">**Kreisdiagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-125">**Pie chart**</span></span> | <span data-ttu-id="25e2e-126">Rendert Abschnitts Torten, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="25e2e-127">Die Größe jedes Kreises stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="25e2e-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="25e2e-128">**Donut-Diagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-128">**Donut chart**</span></span> | <span data-ttu-id="25e2e-129">Rendert Abschnitts Bögen, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="25e2e-130">Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="25e2e-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="25e2e-131">**Liniendiagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-131">**Line chart**</span></span> | <span data-ttu-id="25e2e-132">Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen und verbindet die geplotteten Werte.</span><span class="sxs-lookup"><span data-stu-id="25e2e-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="25e2e-133">**Streudiagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-133">**Scatter chart**</span></span> | <span data-ttu-id="25e2e-134">Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="25e2e-135">**Flächendiagramm**</span><span class="sxs-lookup"><span data-stu-id="25e2e-135">**Area chart**</span></span> | <span data-ttu-id="25e2e-136">Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen und füllt die Abschnitte unter den geplotteten Werten aus.</span><span class="sxs-lookup"><span data-stu-id="25e2e-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="25e2e-137">Erstellen von Abfragen für effektive Diagramme</span><span class="sxs-lookup"><span data-stu-id="25e2e-137">Construct queries for effective charts</span></span>
<span data-ttu-id="25e2e-138">Beim Rendern von Diagrammen identifiziert die erweiterte Suche automatisch die relevanten Spalten und die zu aggregierenden numerischen Werte.</span><span class="sxs-lookup"><span data-stu-id="25e2e-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="25e2e-139">Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurückzugeben, die Sie visuell anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="25e2e-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="25e2e-140">Hier sind einige Beispielabfragen und die daraus resultierenden Diagramme.</span><span class="sxs-lookup"><span data-stu-id="25e2e-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="25e2e-141">Warnungen nach Schweregrad</span><span class="sxs-lookup"><span data-stu-id="25e2e-141">Alerts by severity</span></span>
<span data-ttu-id="25e2e-142">Verwenden Sie `summarize` den-Operator, um eine numerische Anzahl der Werte zu erhalten, die Sie chartern möchten.</span><span class="sxs-lookup"><span data-stu-id="25e2e-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="25e2e-143">In der folgenden Abfrage wird `summarize` der Operator verwendet, um die Anzahl der Warnungen nach Schweregrad abzurufen.</span><span class="sxs-lookup"><span data-stu-id="25e2e-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="25e2e-144">Beim Rendern der Ergebnisse zeigt ein Säulendiagramm jeden Schweregrad als separate Spalte an:</span><span class="sxs-lookup"><span data-stu-id="25e2e-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="25e2e-145">![Bild der erweiterten Jagd Abfrageergebnisse als Spalte Diagramm](../../media/advanced-hunting-column-chart.jpg)
-*Abfrageergebnisse für Warnungen nach Schweregrad angezeigt als Säulendiagramm*</span><span class="sxs-lookup"><span data-stu-id="25e2e-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="25e2e-146">Warnungsschweregrad nach Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="25e2e-146">Alert severity by operating system</span></span>
<span data-ttu-id="25e2e-147">Sie können auch den `summarize` -Operator verwenden, um Ergebnisse für Diagrammwerte aus mehreren Feldern vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="25e2e-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="25e2e-148">Beispielsweise sollten Sie verstehen, wie Warnungs severities über Betriebssysteme verteilt werden (OS).</span><span class="sxs-lookup"><span data-stu-id="25e2e-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="25e2e-149">In der folgenden Abfrage wird `join` ein Operator verwendet, um Betriebssysteminformationen `DeviceInfo` aus der Tabelle abzurufen, `summarize` und verwendet dann, um Werte `OSPlatform` in `Severity` den Spalten und zu zählen:</span><span class="sxs-lookup"><span data-stu-id="25e2e-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="25e2e-150">Diese Ergebnisse werden am besten mit einem gestapelten Säulendiagramm visualisiert:</span><span class="sxs-lookup"><span data-stu-id="25e2e-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="25e2e-151">![Bild der erweiterten Suchabfrageergebnisse als gestapelte Diagramm](../../media/advanced-hunting-stacked-chart.jpg)
*Abfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad angezeigt als gestapeltes Diagramm*</span><span class="sxs-lookup"><span data-stu-id="25e2e-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="25e2e-152">Phishing-e-Mails in den oberen zehn Absenderdomänen</span><span class="sxs-lookup"><span data-stu-id="25e2e-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="25e2e-153">Wenn es sich um eine Liste von Werten handelt, die nicht endlich sind, können Sie `Top` den Operator verwenden, um nur die Werte mit den meisten Instanzen zu chartern.</span><span class="sxs-lookup"><span data-stu-id="25e2e-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="25e2e-154">Um beispielsweise die oberen zehn Absenderdomänen mit den meisten Phishing-e-Mails zu erhalten, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="25e2e-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="25e2e-155">Verwenden Sie die Kreisdiagrammansicht, um die Verteilung in den oberen Domänen effektiv anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="25e2e-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="25e2e-156">![Bild der erweiterten Hunting-Abfrageergebnisse als Kreis](../../media/advanced-hunting-pie-chart.jpg)
Diagramm angezeigt, das eine*Verteilung von Phishing-e-Mails über die oberen Absenderdomänen hinweg zeigt*</span><span class="sxs-lookup"><span data-stu-id="25e2e-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="25e2e-157">Dateiaktivitäten im Laufe der Zeit</span><span class="sxs-lookup"><span data-stu-id="25e2e-157">File activities over time</span></span>
<span data-ttu-id="25e2e-158">Mithilfe des `summarize` Operators mit `bin()` der-Funktion können Sie über einen bestimmten Zeitraum nach Ereignissen suchen, bei denen ein bestimmter Indikator angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="25e2e-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="25e2e-159">In der folgenden Abfrage werden Ereignisse gezählt, `invoice.doc` bei denen die Datei in 30 Minuten Intervallen angezeigt wird, um Spikes in Aktivitäten im Zusammenhang mit dieser Datei anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="25e2e-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="25e2e-160">Im folgenden Diagramm werden die Zeiträume mit mehr Aktivität deutlich hervor `invoice.doc`gehoben, darunter:</span><span class="sxs-lookup"><span data-stu-id="25e2e-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="25e2e-161">![Bild der erweiterten Hunting-Abfrageergebnisse als](../../media/advanced-hunting-line-chart.jpg)
*Diagramm Diagramm mit der Anzahl der Ereignisse angezeigt, die mit einer Datei im Laufe der Zeit* in Verbindung stehen</span><span class="sxs-lookup"><span data-stu-id="25e2e-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="25e2e-162">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="25e2e-162">Export tables and charts</span></span>
<span data-ttu-id="25e2e-163">Wählen Sie nach dem Ausführen einer Abfrage **Export** aus, um die Ergebnisse in der lokalen Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="25e2e-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="25e2e-164">Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:</span><span class="sxs-lookup"><span data-stu-id="25e2e-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="25e2e-165">**Tabellenansicht** – die Abfrageergebnisse werden als Microsoft Excel Arbeitsmappe in tabellarischer Form exportiert.</span><span class="sxs-lookup"><span data-stu-id="25e2e-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="25e2e-166">**Beliebiges Diagramm** – die Abfrageergebnisse werden als JPEG-Bild des gerenderten Diagramms exportiert.</span><span class="sxs-lookup"><span data-stu-id="25e2e-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="25e2e-167">Drilldown von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="25e2e-167">Drill down from query results</span></span>
<span data-ttu-id="25e2e-168">Wenn Sie weitere Informationen zu Entitäten, z. B. Computern, Dateien, Benutzern, IP-Adressen und URLs, anzeigen möchten, klicken Sie in den Abfrageergebnissen einfach auf den Entitätsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="25e2e-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="25e2e-169">Dadurch wird eine detaillierte Profilseite für die ausgewählte Entität im Microsoft Defender Security Center geöffnet.</span><span class="sxs-lookup"><span data-stu-id="25e2e-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="25e2e-170">Optimieren von Abfragen aus den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="25e2e-170">Tweak your queries from the results</span></span>
<span data-ttu-id="25e2e-171">Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="25e2e-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="25e2e-172">Sie können die folgenden Optionen für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="25e2e-172">You can use the options to:</span></span>

- <span data-ttu-id="25e2e-173">Explizites Suchen nach dem ausgewählten Wert (`==`)</span><span class="sxs-lookup"><span data-stu-id="25e2e-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="25e2e-174">Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)</span><span class="sxs-lookup"><span data-stu-id="25e2e-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="25e2e-175">Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with`</span><span class="sxs-lookup"><span data-stu-id="25e2e-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild des erweiterten Jagd Ergebnissatzes](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="25e2e-177">Filtern der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="25e2e-177">Filter the query results</span></span>
<span data-ttu-id="25e2e-178">Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="25e2e-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="25e2e-179">Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="25e2e-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="25e2e-180">Verfeinern Sie die Abfrage, indem `+` Sie `-` die Schaltflächen oder für die Werte auswählen, die Sie einschließen oder ausschließen möchten, und wählen Sie dann **Abfrage ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="25e2e-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Abbildung eines erweiterten Suchfilters](../../media/advanced-hunting-filter.png)

<span data-ttu-id="25e2e-182">Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="25e2e-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25e2e-183">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="25e2e-183">Related topics</span></span>
- [<span data-ttu-id="25e2e-184">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="25e2e-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="25e2e-185">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="25e2e-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="25e2e-186">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="25e2e-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="25e2e-187">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="25e2e-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="25e2e-188">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="25e2e-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="25e2e-189">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="25e2e-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="25e2e-190">Übersicht über benutzerdefinierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="25e2e-190">Custom detections overview</span></span>](custom-detections-overview.md)
