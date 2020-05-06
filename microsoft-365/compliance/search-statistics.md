---
title: Suchstatistiken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Suchstatistiken sind eine effektive Möglichkeit, Ihre Suchergebnisse zu überprüfen und unter Status auf der Flyout-Seite mit den Suchdetails anzuzeigen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc6aea96e86388ae7ecfa0fa545bc5571eeff0cd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035837"
---
# <a name="search-statistics"></a><span data-ttu-id="a5051-103">Suchstatistiken</span><span class="sxs-lookup"><span data-stu-id="a5051-103">Search statistics</span></span>

<span data-ttu-id="a5051-104">Eine effektive Möglichkeit zum Überprüfen Ihrer Suchergebnisse bei der Untersuchung eines Daten Vorfalls besteht darin, die Statistiken zu Ihren Suchergebnissen anzuzeigen, um sicherzustellen, dass Sie Ihren Erwartungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a5051-104">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="a5051-105">Wenn eine Suche als abgeschlossen ausgeführt wird, werden die folgenden allgemeinen Statistiken unter **Status** auf der Flyout-Seite "Suchdetails" angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a5051-105">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![Statisics auf der Such Detail-Flyout-Seite suchen](../media/SearchDetailsFlyout.png)

- <span data-ttu-id="a5051-107">Die geschätzte Anzahl und Größe der Elemente, die mit den Suchkriterien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5051-107">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="a5051-108">Anzahl und Größe der teilweise indizierten Elemente (auch als nicht indizierte *Elemente*bezeichnet), die nicht durchsuchbar sind, sondern in den Inhaltsspeicherorten gefunden wurden, die in die Suche einbezogen wurden.</span><span class="sxs-lookup"><span data-stu-id="a5051-108">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="a5051-109">Die Anzahl der Postfächer und Websites, die durchsucht wurden.</span><span class="sxs-lookup"><span data-stu-id="a5051-109">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="a5051-110">Wenn Sie detailliertere Statistiken anzeigen möchten, klicken Sie auf der Flyout-Seite mit den Suchdetails auf **Statistik** .</span><span class="sxs-lookup"><span data-stu-id="a5051-110">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="a5051-111">Auf der Seite **Suchstatistik** können Sie die Suchzusammenfassung, die erste Position mit Elementen, die mit den Suchergebnissen übereinstimmen, und detaillierte Statistiken zur Suchabfrage anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5051-111">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![Dropdownliste "Suchstatistik"](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="a5051-113">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a5051-113">Summary</span></span>

<span data-ttu-id="a5051-114">In der **Zusammenfassungs** Ansicht werden die Suchergebnisse nach Standorttypen aufgeschlüsselt angezeigt (beispielsweise Speicherorte wie Exchange-Postfächer und SharePoint-Websites).</span><span class="sxs-lookup"><span data-stu-id="a5051-114">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="a5051-115">Die folgenden Informationen werden für jeden Location-Typ angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a5051-115">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="a5051-116">Die Anzahl der Speicherorte, an denen Elemente gefunden wurden, die den Suchkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a5051-116">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="a5051-117">Die Gesamtzahl der Elemente aus jedem Standorttyp, die mit den Suchkriterien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5051-117">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="a5051-118">Die Gesamtgröße der Elemente aus jedem Standorttyp, der mit den Suchkriterien übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a5051-118">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="a5051-119">Top-Standorte</span><span class="sxs-lookup"><span data-stu-id="a5051-119">Top locations</span></span>

<span data-ttu-id="a5051-120">In der Ansicht " **Top Locations** " werden die einzelnen inhaltsspeicherorte mit den meisten Elementen angezeigt, die mit den Suchkriterien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5051-120">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="a5051-121">Für jeden Inhaltsspeicherort werden die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a5051-121">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="a5051-122">Der Name des Speicherorts; die e-Mail-Adresse für Postfächer und die URL für SharePoint-Websites</span><span class="sxs-lookup"><span data-stu-id="a5051-122">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="a5051-123">Der Location-Typ</span><span class="sxs-lookup"><span data-stu-id="a5051-123">The location type</span></span>

- <span data-ttu-id="a5051-124">Anzahl der Elemente, die mit den Suchkriterien übereinstimmen</span><span class="sxs-lookup"><span data-stu-id="a5051-124">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="a5051-125">Die Gesamtgröße aller Elemente, die mit den Suchkriterien übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5051-125">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="a5051-126">Abfragen</span><span class="sxs-lookup"><span data-stu-id="a5051-126">Queries</span></span>

<span data-ttu-id="a5051-127">In der Ansicht **Abfragen** können Sie detaillierte Statistiken zu jeder Komponente der Suchabfrage anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5051-127">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="a5051-128">Wenn Sie die Stichwortliste in der Suchabfrage verwendet haben, können Sie in der Ansicht **Abfragen** Erweiterte Statistiken anzeigen, in denen angezeigt wird, wie viele Elemente mit jedem Stichwort oder stichwortausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5051-128">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="a5051-129">Auf diese Weise können Sie schnell erkennen, welche Teile der Abfrage am häufigsten (und am wenigsten) effektiv sind.</span><span class="sxs-lookup"><span data-stu-id="a5051-129">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="a5051-130">Die folgenden Informationen werden in der Ansicht **Abfragen** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a5051-130">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="a5051-131">**Location Type** – der Typ des Inhaltsspeichers für die in der Zeile angezeigten Statistiken.</span><span class="sxs-lookup"><span data-stu-id="a5051-131">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="a5051-132">**Part – in** dieser Spalte wird einer der folgenden Werte angezeigt: **Primary** oder **Keyword**.</span><span class="sxs-lookup"><span data-stu-id="a5051-132">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="a5051-133">**Primäre** bedeutet, dass die Zeile Statistiken für die gesamte Abfrage enthält. **Schlüsselwort** bedeutet, dass die Statistik in der Zeile für eine der Abfragekomponenten gilt.</span><span class="sxs-lookup"><span data-stu-id="a5051-133">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="a5051-134">**Condition** – die tatsächliche Abfragekomponente der Suchabfrage, auf die sich die Zeile bezieht.</span><span class="sxs-lookup"><span data-stu-id="a5051-134">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="a5051-135">Wenn der Wert in der Spalte " **Part** " **primär**ist, werden die Statistiken für die gesamte Suchabfrage angezeigt; Wenn der Wert **Schlüsselwort**ist, werden die Statistiken für die in der **Abfrage** Spalte angezeigte Komponente der Abfrage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5051-135">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="a5051-136">Wenn beispielsweise die Stichwortliste verwendet wurde, wird die Statistik eines der Schlüsselwörter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5051-136">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="a5051-137">Hier sind einige andere Dinge, die Sie über die in der Spalte **Abfragen** angezeigte Statistik wissen sollten:</span><span class="sxs-lookup"><span data-stu-id="a5051-137">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="a5051-138">Wenn Sie nach allen Inhalten in Postfächern suchen (indem Sie keine Stichwörter angeben), lautet die tatsächliche Abfrage **(Size >= 0)** , sodass alle Elemente zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5051-138">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="a5051-139">Wenn Sie SharePoint-und OneDrive-Websites Durchsuchen, werden die beiden folgenden Komponenten zur Suchabfrage hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="a5051-139">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="a5051-140">**Not IsExternalContent: 1** -Dies schließt jeglichen Inhalt aus einer lokalen SharePoint-Organisation aus</span><span class="sxs-lookup"><span data-stu-id="a5051-140">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="a5051-141">**Not isOneNotePage: 1** -Dies schließt alle OneNote-Dateien aus, da es sich dabei um Duplikate eines Dokuments handeln würde, das mit der Suchabfrage übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a5051-141">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="a5051-142">**Standorte in der Suche** Die Anzahl der inhaltsspeicherorte mit Elementen, die mit der Suchabfrage für die in der Zeile angezeigte Komponente/Bedingung übereinstimmten.</span><span class="sxs-lookup"><span data-stu-id="a5051-142">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="a5051-143">Beachten Sie, dass Archivpostfächer als separater Ort gezählt werden, wenn Sie Elemente enthalten, die den Suchkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a5051-143">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="a5051-144">**Items** – die Gesamtzahl der Elemente, die den Suchkriterien für die in der Zeile angezeigte Komponente/Bedingung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a5051-144">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="a5051-145">**Size** – die Gesamtzahl der Elemente, die den Suchkriterien für die in der Zeile angezeigte Komponente/Bedingung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a5051-145">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

