---
title: Anzeigen von Statistiken für eDiscovery-Suchergebnisse
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie das Suchstatistikfeature verwenden, um Statistiken für Inhaltssuchen und -suchen anzuzeigen, die einem Core eDiscovery-Fall im Microsoft 365 zugeordnet sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311113"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="8c8fb-103">Anzeigen von Statistiken für eDiscovery-Suchergebnisse</span><span class="sxs-lookup"><span data-stu-id="8c8fb-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="8c8fb-104">Nachdem Sie eine Inhaltssuche oder eine Suche erstellt und ausgeführt haben, die einem Core eDiscovery-Fall zugeordnet ist, können Sie Statistiken zu den geschätzten Suchergebnissen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="8c8fb-105">Dies umfasst eine Zusammenfassung der Suchergebnisse (ähnlich der Zusammenfassung der geschätzten Suchergebnisse, die auf der Flyoutseite der Suche angezeigt werden), die Abfragestatistiken wie die Anzahl der Inhaltsspeicherorte mit Elementen, die mit der Suchabfrage übereinstimmen, und die Identität von Inhaltsspeicherorten mit den am besten übereinstimmenden Elementen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="8c8fb-106">Darüber hinaus können Sie die Stichwörterliste verwenden, um eine Suche so zu konfigurieren, dass Statistiken für jedes Schlüsselwort in einer Suchabfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="8c8fb-107">Auf diese Weise können Sie die Anzahl der Ergebnisse vergleichen, die von jedem Schlüsselwort in einer Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="8c8fb-108">Sie können suchstatistiken auch in eine CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="8c8fb-109">Auf diese Weise können Sie die Filter- und Sortierfunktionen in Excel dazu verwenden, um Ergebnisse zu vergleichen und Berichte für Ihre Suchergebnisse vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="8c8fb-110">Statistiken für Suchen erhalten</span><span class="sxs-lookup"><span data-stu-id="8c8fb-110">Get statistics for searches</span></span>

<span data-ttu-id="8c8fb-111">So zeigen Sie Statistiken für eine Inhaltssuche oder eine Suche an, die einem Core eDiscovery-Fall zugeordnet ist::</span><span class="sxs-lookup"><span data-stu-id="8c8fb-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="8c8fb-112">Klicken Sie Microsoft 365 Compliance Center auf **Alle** anzeigen, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8c8fb-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="8c8fb-113">Klicken **Sie auf Inhaltssuche,** und wählen Sie dann eine Suche aus, um die Flyoutseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="8c8fb-114">ODER</span><span class="sxs-lookup"><span data-stu-id="8c8fb-114">OR</span></span>

   - <span data-ttu-id="8c8fb-115">Klicken **Sie auf eDiscovery** Core, wählen Sie einen Fall aus, und wählen Sie dann auf der Registerkarte Suchen eine Suche aus, um die  >  Flyoutseite anzeigen zu können. </span><span class="sxs-lookup"><span data-stu-id="8c8fb-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="8c8fb-116">Klicken Sie auf der Flyoutseite der ausgewählten Suche auf die Registerkarte **Suchstatistik.**</span><span class="sxs-lookup"><span data-stu-id="8c8fb-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![Die Registerkarte Suchstatistik](../media/SearchStatistics1.png)

<span data-ttu-id="8c8fb-118">Die **Registerkarte Suchstatistik** enthält für die folgenden Abschnitte, die unterschiedliche Arten von Statistiken zur Suche enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="8c8fb-119">Suchinhalt</span><span class="sxs-lookup"><span data-stu-id="8c8fb-119">Search content</span></span>

<span data-ttu-id="8c8fb-120">In diesem Abschnitt wird eine grafische Zusammenfassung der von der Suche zurückgegebenen geschätzten Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="8c8fb-121">Dies gibt die Anzahl der Elemente an, die den Suchkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="8c8fb-122">Diese Informationen geben Ihnen eine Vorstellung von der geschätzten Anzahl von Elementen, die von der Suche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Suchschätzungen für eine Suche](../media/SearchContentReport.png)

- <span data-ttu-id="8c8fb-124">**Geschätzte Elemente nach Speicherorten:** Die Gesamtanzahl der geschätzten Elemente, die von der Suche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="8c8fb-125">Die bestimmte Anzahl von Elementen, die sich in Postfächern und auf Websites befinden, wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="8c8fb-126">**Geschätzte Speicherorte mit Treffern:** Die Gesamtanzahl der Inhaltsstandorte, die von der Suche zurückgegebene Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="8c8fb-127">Die spezifische Anzahl von Postfach- und Standortspeicherorten wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="8c8fb-128">**Datenvolumen nach Speicherort (in MB):** Die Gesamtgröße aller geschätzten Elemente, die von der Suche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="8c8fb-129">Die spezifische Größe von Postfachelementen und Websiteelementen wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="8c8fb-130">Bedingungsbericht</span><span class="sxs-lookup"><span data-stu-id="8c8fb-130">Condition report</span></span>

<span data-ttu-id="8c8fb-131">In diesem Abschnitt werden Statistiken zur Suchabfrage und zur Anzahl der geschätzten Elemente angezeigt, die verschiedenen Teilen der Suchabfrage entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="8c8fb-132">Sie können diese Statistiken verwenden, um die Anzahl der Elemente zu analysieren, die mit jeder Komponente der Suchabfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="8c8fb-133">Dies kann Ihnen helfen, die Suchkriterien zu verfeinern und bei Bedarf den Bereich zu einenten.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="8c8fb-134">Sie können auch eine Kopie dieses Berichts im CSV-Format herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-134">You can also download a copy of this report in CSV format.</span></span>

![Bedingungsbericht](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="8c8fb-136">**Speicherorttyp**: Der Typ des Inhaltsspeicherorts, auf den die Abfragestatistiken anwendbar sind.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="8c8fb-137">Der Wert von **Exchange** gibt einen Postfachspeicherort an. ein Wert von **SharePoint** einen Standort angibt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="8c8fb-138">**Teil**: Der Teil der Suchabfrage, auf den die Statistiken anwendbar sind.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="8c8fb-139">**Primär** gibt die gesamte Suchabfrage an.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="8c8fb-140">**Schlüsselwort** gibt an, dass die Statistiken in der Zeile für ein bestimmtes Schlüsselwort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="8c8fb-141">Wenn Sie eine Schlüsselwortliste für suchabfragen verwenden, sind Statistiken für jede Komponente der Abfrage in dieser Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="8c8fb-142">Weitere Informationen finden Sie unter [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="8c8fb-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="8c8fb-143">**Bedingung:** Die tatsächliche Komponente (Schlüsselwort oder Bedingung) der Suchabfrage, die die in der entsprechenden Zeile angezeigten Statistiken zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="8c8fb-144">**Speicherorte mit Treffern**: Die Anzahl  der Inhaltsspeicherorte (angegeben durch die Spalte Standorttyp), die Elemente enthalten, die der primären abfrage oder der Schlüsselwortabfrage in der Spalte **Bedingung** entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="8c8fb-145">**Elemente**: Die Anzahl der Elemente (vom angegebenen Inhaltsspeicherort), die der in der Spalte Bedingung aufgeführten **Abfrage** entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="8c8fb-146">Wie bereits erläutert, wird ein Element nur einmal in dieser Spalte gezählt, wenn es mehrere Instanzen eines gesuchten Schlüsselworts enthält.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="8c8fb-147">**Size (MB)**: Die Gesamtgröße aller Gefundenen (am angegebenen Inhaltsspeicherort), die der Suchabfrage in der **Spalte Bedingung** entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="8c8fb-148">Top locations</span><span class="sxs-lookup"><span data-stu-id="8c8fb-148">Top locations</span></span>

<span data-ttu-id="8c8fb-149">In diesem Abschnitt werden Statistiken zu den spezifischen Inhaltsstandorten mit den meisten von der Suche zurückgegebenen Elementen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="8c8fb-150">Es werden die ersten 1.000 Speicherorte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="8c8fb-151">Sie können auch eine Kopie dieses Berichts im CSV-Format herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="8c8fb-152">Der Name des Standortnamens (die E-Mail-Adresse von Postfächern und die URL für Websites).</span><span class="sxs-lookup"><span data-stu-id="8c8fb-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="8c8fb-153">Speicherorttyp (Postfach oder Standort).</span><span class="sxs-lookup"><span data-stu-id="8c8fb-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="8c8fb-154">Geschätzte Anzahl von Elementen am Von der Suche zurückgegebenen Inhaltsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="8c8fb-155">Die Gesamtgröße der geschätzten Elemente an jedem Inhaltsspeicherort.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="8c8fb-156">Get keyword statistics for searches</span><span class="sxs-lookup"><span data-stu-id="8c8fb-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="8c8fb-157">Wie bereits erläutert, zeigt der **Abschnitt Bedingungsbericht** die Suchabfrage und die Anzahl (und Größe) von Elementen an, die mit der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="8c8fb-158">Wenn Sie beim Erstellen oder Bearbeiten einer Suchabfrage eine Stichwortliste verwenden, können Sie erweiterte Statistiken erhalten, die anzeigen, wie viele Elemente mit den einzelnen Schlüsselwort- oder Schlüsselwortausdrücken übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="8c8fb-159">Dadurch können Sie schnell ermitteln, welche Teile der Abfrage am effektivsten (und am wenigsten) sind.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="8c8fb-160">Wenn ein Schlüsselwort beispielsweise eine große Anzahl von Elementen zurückgibt, können Sie die Schlüsselwortabfrage so verfeinern, dass die Suchergebnisse einengt werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="8c8fb-161">So erstellen Sie eine Stichwortliste und zeigen Die Stichwortstatistik für eine Suche an:</span><span class="sxs-lookup"><span data-stu-id="8c8fb-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="8c8fb-162">Erstellen Sie Microsoft 365 Compliance Center eine neue Inhaltssuche oder eine Suche, die einem Core eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="8c8fb-163">Auf der **Seite Bedingungen** des Suchassistenten.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="8c8fb-164">Aktivieren Sie das **Kontrollkästchen Stichwortliste anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="8c8fb-164">select the **Show keyword list** checkbox.</span></span>

   ![Kontrollkästchen Stichwörterliste anzeigen](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="8c8fb-166">Geben Sie ein Schlüsselwort oder eine Schlüsselwortphase in einer Zeile in der Schlüsselwörtertabelle ein.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="8c8fb-167">Geben Sie beispielsweise **budget** in der ersten Zeile ein, geben **Sie** Sicherheit in der zweiten Zeile ein, und geben Sie **FY2021** in die dritte Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Geben Sie bis zu 20 Schlüsselwörter oder Stichwortausdrücke in die Liste ein.](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="8c8fb-169">Um Probleme zu reduzieren, die durch große Stichwortlisten verursacht werden, sind Sie auf maximal 20 Zeilen in der Stichwortliste einer Suchabfrage beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="8c8fb-170">Nachdem Sie die Schlüsselwörter zur Liste hinzugefügt haben, nach der Sie suchen und Statistiken erhalten möchten, führen Sie die Suche aus.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="8c8fb-171">Wenn die Suche abgeschlossen ist, wählen Sie sie aus, um die Flyoutseite angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="8c8fb-172">Klicken Sie **auf der** Registerkarte Suchstatistik auf den **Bedingungsbericht,** um die Stichwortstatistik für die Suche anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![Die Statistiken für jedes Schlüsselwort werden angezeigt.](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="8c8fb-174">Wie im vorherigen Screenshot gezeigt, werden die Statistiken für jedes Schlüsselwort angezeigt. Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="8c8fb-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="8c8fb-175">Die Schlüsselwortstatistik für jeden Inhaltsspeicherort, der in der Suche enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="8c8fb-176">Die Anzahl der nicht indizierten Postfachelemente.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="8c8fb-177">Die tatsächliche Suchabfrage und die Ergebnisse für  jedes Schlüsselwort (identifiziert als **Schlüsselwort** in der Spalte Part), die alle Bedingungen aus der Suchabfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="8c8fb-178">Die vollständige Suchabfrage  (in  der Spalte Teil als Primär identifiziert) und die Statistiken für die vollständige Abfrage für jeden Standorttyp.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="8c8fb-179">Beachten Sie, dass es sich um dieselben Statistiken handelt, die auf der Registerkarte **Zusammenfassung angezeigt** werden.</span><span class="sxs-lookup"><span data-stu-id="8c8fb-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
