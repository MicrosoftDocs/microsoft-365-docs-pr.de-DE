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
ms.openlocfilehash: 14afd3c098c99a6e1e6ccfc7e9f6accbf8bf0e7d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899082"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="2d84c-104">Arbeiten mit erweiterten Jagd Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="2d84c-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="2d84c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2d84c-105">**Applies to:**</span></span>
- <span data-ttu-id="2d84c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2d84c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2d84c-107">Während Sie Ihre [erweiterten Jagd](advanced-hunting-overview.md) Abfragen erstellen können, um sehr genaue Informationen zurückzugeben, können Sie auch mit den Abfrageergebnissen zusammenarbeiten, um weitere Einblicke zu gewinnen und bestimmte Aktivitäten und Indikatoren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="2d84c-108">Sie können die folgenden Aktionen für die Abfrageergebnisse ausführen:</span><span class="sxs-lookup"><span data-stu-id="2d84c-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="2d84c-109">Anzeigen von Ergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="2d84c-109">View results as a table or chart</span></span>
- <span data-ttu-id="2d84c-110">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="2d84c-110">Export tables and charts</span></span>
- <span data-ttu-id="2d84c-111">Drilldown zu detaillierten Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="2d84c-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="2d84c-112">Optimieren der Abfragen direkt aus den Ergebnissen oder Anwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="2d84c-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="2d84c-113">Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm</span><span class="sxs-lookup"><span data-stu-id="2d84c-113">View query results as a table or chart</span></span>
<span data-ttu-id="2d84c-114">Standardmäßig zeigt Advanced Hunting Abfrageergebnisse als tabellarische Daten an.</span><span class="sxs-lookup"><span data-stu-id="2d84c-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="2d84c-115">Sie können auch dieselben Daten wie ein Diagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="2d84c-116">Die erweiterte Suche unterstützt die folgenden Ansichten:</span><span class="sxs-lookup"><span data-stu-id="2d84c-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="2d84c-117">Ansichtstyp</span><span class="sxs-lookup"><span data-stu-id="2d84c-117">View type</span></span> | <span data-ttu-id="2d84c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d84c-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="2d84c-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="2d84c-119">**Table**</span></span> | <span data-ttu-id="2d84c-120">Zeigt die Abfrageergebnisse im tabellarischen Format an.</span><span class="sxs-lookup"><span data-stu-id="2d84c-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="2d84c-121">**Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-121">**Column chart**</span></span> | <span data-ttu-id="2d84c-122">Rendert eine Reihe von eindeutigen Elementen auf der x-Achse als vertikale Balken, deren Höhe numerische Werte aus einem anderen Feld darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d84c-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="2d84c-123">**Gestapeltes Säulendiagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-123">**Stacked column chart**</span></span> | <span data-ttu-id="2d84c-124">Rendert eine Reihe von eindeutigen Elementen auf der x-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="2d84c-125">**Kreisdiagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-125">**Pie chart**</span></span> | <span data-ttu-id="2d84c-126">Rendert Abschnitts Torten, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="2d84c-127">Die Größe jedes Kreises stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="2d84c-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="2d84c-128">**Donut-Diagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-128">**Donut chart**</span></span> | <span data-ttu-id="2d84c-129">Rendert Abschnitts Bögen, die eindeutige Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="2d84c-130">Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar.</span><span class="sxs-lookup"><span data-stu-id="2d84c-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="2d84c-131">**Liniendiagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-131">**Line chart**</span></span> | <span data-ttu-id="2d84c-132">Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen und verbindet die geplotteten Werte.</span><span class="sxs-lookup"><span data-stu-id="2d84c-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="2d84c-133">**Streudiagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-133">**Scatter chart**</span></span> | <span data-ttu-id="2d84c-134">Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="2d84c-135">**Flächendiagramm**</span><span class="sxs-lookup"><span data-stu-id="2d84c-135">**Area chart**</span></span> | <span data-ttu-id="2d84c-136">Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen und füllt die Abschnitte unter den geplotteten Werten aus.</span><span class="sxs-lookup"><span data-stu-id="2d84c-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="2d84c-137">Erstellen von Abfragen für effektive Diagramme</span><span class="sxs-lookup"><span data-stu-id="2d84c-137">Construct queries for effective charts</span></span>
<span data-ttu-id="2d84c-138">Beim Rendern von Diagrammen identifiziert die erweiterte Suche automatisch die relevanten Spalten und die zu aggregierenden numerischen Werte.</span><span class="sxs-lookup"><span data-stu-id="2d84c-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="2d84c-139">Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurückzugeben, die Sie visuell anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d84c-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="2d84c-140">Hier sind einige Beispielabfragen und die daraus resultierenden Diagramme.</span><span class="sxs-lookup"><span data-stu-id="2d84c-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="2d84c-141">Warnungen nach Schweregrad</span><span class="sxs-lookup"><span data-stu-id="2d84c-141">Alerts by severity</span></span>
<span data-ttu-id="2d84c-142">Verwenden `summarize` Sie den-Operator, um eine numerische Anzahl der Werte zu erhalten, die Sie chartern möchten.</span><span class="sxs-lookup"><span data-stu-id="2d84c-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="2d84c-143">In der folgenden Abfrage wird der `summarize` Operator verwendet, um die Anzahl der Warnungen nach Schweregrad abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="2d84c-144">Beim Rendern der Ergebnisse zeigt ein Säulendiagramm jeden Schweregrad als separate Spalte an:</span><span class="sxs-lookup"><span data-stu-id="2d84c-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="2d84c-145">![Bild der erweiterten Jagd Abfrageergebnisse als Spalte Diagramm- ](../../media/advanced-hunting-column-chart.jpg)
 *Abfrageergebnisse für Warnungen nach Schweregrad angezeigt als Säulendiagramm*</span><span class="sxs-lookup"><span data-stu-id="2d84c-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="2d84c-146">Warnungsschweregrad nach Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="2d84c-146">Alert severity by operating system</span></span>
<span data-ttu-id="2d84c-147">Sie können auch den `summarize` -Operator verwenden, um Ergebnisse für Diagrammwerte aus mehreren Feldern vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="2d84c-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="2d84c-148">Beispielsweise sollten Sie verstehen, wie Warnungs severities über Betriebssysteme verteilt werden (OS).</span><span class="sxs-lookup"><span data-stu-id="2d84c-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="2d84c-149">In der folgenden Abfrage wird ein Operator verwendet, `join` um Betriebssysteminformationen aus der `DeviceInfo` Tabelle abzurufen, und verwendet dann `summarize` , um Werte in den `OSPlatform` Spalten und zu zählen `Severity` :</span><span class="sxs-lookup"><span data-stu-id="2d84c-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="2d84c-150">Diese Ergebnisse werden am besten mit einem gestapelten Säulendiagramm visualisiert:</span><span class="sxs-lookup"><span data-stu-id="2d84c-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="2d84c-151">![Bild der erweiterten Suchabfrageergebnisse als gestapelte Diagramm ](../../media/advanced-hunting-stacked-chart.jpg)
 *Abfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad angezeigt als gestapeltes Diagramm*</span><span class="sxs-lookup"><span data-stu-id="2d84c-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="2d84c-152">Phishing-e-Mails in den oberen zehn Absenderdomänen</span><span class="sxs-lookup"><span data-stu-id="2d84c-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="2d84c-153">Wenn es sich um eine Liste von Werten handelt, die nicht endlich sind, können Sie den `Top` Operator verwenden, um nur die Werte mit den meisten Instanzen zu chartern.</span><span class="sxs-lookup"><span data-stu-id="2d84c-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="2d84c-154">Um beispielsweise die oberen zehn Absenderdomänen mit den meisten Phishing-e-Mails zu erhalten, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="2d84c-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="2d84c-155">Verwenden Sie die Kreisdiagrammansicht, um die Verteilung in den oberen Domänen effektiv anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="2d84c-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="2d84c-156">![Bild der erweiterten Hunting-Abfrageergebnisse als Kreisdiagramm angezeigt, das eine ](../../media/advanced-hunting-pie-chart.jpg)
 *Verteilung von Phishing-e-Mails über die oberen Absenderdomänen hinweg zeigt*</span><span class="sxs-lookup"><span data-stu-id="2d84c-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="2d84c-157">Dateiaktivitäten im Laufe der Zeit</span><span class="sxs-lookup"><span data-stu-id="2d84c-157">File activities over time</span></span>
<span data-ttu-id="2d84c-158">Mithilfe des `summarize` Operators mit der `bin()` -Funktion können Sie über einen bestimmten Zeitraum nach Ereignissen suchen, bei denen ein bestimmter Indikator angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2d84c-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="2d84c-159">In der folgenden Abfrage werden Ereignisse gezählt, bei denen die Datei `invoice.doc` in 30 Minuten Intervallen angezeigt wird, um Spikes in Aktivitäten im Zusammenhang mit dieser Datei anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="2d84c-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="2d84c-160">Im folgenden Diagramm werden die Zeiträume mit mehr Aktivität deutlich hervorgehoben `invoice.doc` , darunter:</span><span class="sxs-lookup"><span data-stu-id="2d84c-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="2d84c-161">![Bild der erweiterten Hunting-Abfrageergebnisse als ](../../media/advanced-hunting-line-chart.jpg)
 *Diagramm Diagramm mit der Anzahl der Ereignisse angezeigt, die mit einer Datei im Laufe der Zeit* in Verbindung stehen</span><span class="sxs-lookup"><span data-stu-id="2d84c-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="2d84c-162">Exportieren von Tabellen und Diagrammen</span><span class="sxs-lookup"><span data-stu-id="2d84c-162">Export tables and charts</span></span>
<span data-ttu-id="2d84c-163">Wählen Sie nach dem Ausführen einer Abfrage **Export** aus, um die Ergebnisse in der lokalen Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d84c-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="2d84c-164">Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:</span><span class="sxs-lookup"><span data-stu-id="2d84c-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="2d84c-165">**Tabellenansicht** – die Abfrageergebnisse werden als Microsoft Excel Arbeitsmappe in tabellarischer Form exportiert.</span><span class="sxs-lookup"><span data-stu-id="2d84c-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="2d84c-166">**Beliebiges Diagramm** – die Abfrageergebnisse werden als JPEG-Bild des gerenderten Diagramms exportiert.</span><span class="sxs-lookup"><span data-stu-id="2d84c-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="2d84c-167">Drilldown von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="2d84c-167">Drill down from query results</span></span>
<span data-ttu-id="2d84c-168">Wenn Sie einen Datensatz in Ihren Abfrageergebnissen schnell überprüfen möchten, wählen Sie die entsprechende Zeile aus, um die Registerkarte " **Daten Satz prüfen** " zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="2d84c-169">Der Bereich enthält die folgenden Informationen basierend auf dem ausgewählten Datensatz:</span><span class="sxs-lookup"><span data-stu-id="2d84c-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="2d84c-170">**Objekte** – zusammengefasste Ansicht der Hauptobjekte (Postfächer, Geräte und Benutzer), die im Datensatz gefunden wurden, mit verfügbaren Informationen wie Risiko-und Expositions Stufen angereichert</span><span class="sxs-lookup"><span data-stu-id="2d84c-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="2d84c-171">**Prozessstruktur** – wird für Datensätze mit Prozessinformationen generiert und mithilfe von verfügbaren Kontextinformationen erweitert; im Allgemeinen können Abfragen, die mehr Spalten zurückgeben, zu umfangreicheren Prozessstrukturen führen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="2d84c-172">**Alle Details** – alle Werte aus den Spalten im Datensatz</span><span class="sxs-lookup"><span data-stu-id="2d84c-172">**All details** — all the values from the columns in the record</span></span>  

![Bild des ausgewählten Datensatzes mit dem Bereich für die Überprüfung des Datensatzes](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="2d84c-174">Wenn Sie weitere Informationen zu einer bestimmten Entität in Ihren Abfrageergebnissen anzeigen möchten, beispielsweise einen Computer, eine Datei, einen Benutzer, eine IP-Adresse oder eine URL, wählen Sie den Entitäts Bezeichner aus, um eine detaillierte Profilseite für diese Entität zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d84c-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="2d84c-175">Optimieren von Abfragen aus den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="2d84c-175">Tweak your queries from the results</span></span>
<span data-ttu-id="2d84c-176">Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2d84c-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="2d84c-177">Sie können die folgenden Optionen für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="2d84c-177">You can use the options to:</span></span>

- <span data-ttu-id="2d84c-178">Explizites Suchen nach dem ausgewählten Wert (`==`)</span><span class="sxs-lookup"><span data-stu-id="2d84c-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="2d84c-179">Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)</span><span class="sxs-lookup"><span data-stu-id="2d84c-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="2d84c-180">Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with`</span><span class="sxs-lookup"><span data-stu-id="2d84c-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Bild des erweiterten Jagd Ergebnissatzes](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="2d84c-182">Filtern der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="2d84c-182">Filter the query results</span></span>
<span data-ttu-id="2d84c-183">Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="2d84c-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="2d84c-184">Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="2d84c-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="2d84c-185">Verfeinern Sie die Abfrage, indem `+` `-` Sie die Schaltflächen oder für die Werte auswählen, die Sie einschließen oder ausschließen möchten, und wählen Sie dann **Abfrage ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="2d84c-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Abbildung eines erweiterten Suchfilters](../../media/advanced-hunting-filter.png)

<span data-ttu-id="2d84c-187">Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2d84c-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d84c-188">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2d84c-188">Related topics</span></span>
- [<span data-ttu-id="2d84c-189">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="2d84c-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2d84c-190">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="2d84c-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2d84c-191">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="2d84c-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2d84c-192">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="2d84c-192">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2d84c-193">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="2d84c-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2d84c-194">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="2d84c-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2d84c-195">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="2d84c-195">Custom detections overview</span></span>](custom-detections-overview.md)
