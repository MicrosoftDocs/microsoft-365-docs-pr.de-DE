---
title: Untersuchen von teilweise indizierten Elementen in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Teilweise indizierte Elemente (auch nicht indexierte Elemente aufrufen) sind Exchange-Postfachelemente und Dokumente auf SharePoint-und OneDrive-Websites, die aus irgendeinem Grund nicht vollständig für die Inhaltssuche indiziert wurden. In diesem Artikel erfahren Sie, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, Suchfehler für teilweise indizierte Elemente identifizieren und ein PowerShell-Skript verwenden, um die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen zu ermitteln.
ms.openlocfilehash: 64b052e5c04019d5937c3763094529ae5c4c9e42
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637463"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="3c3c7-104">Untersuchen von teilweise indizierten Elementen in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3c3c7-104">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="3c3c7-105">Eine Inhaltssuche, die Sie im Security & Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-105">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="3c3c7-106">Teilweise indizierte Elemente sind Exchange-Postfachelemente und Dokumente in SharePoint und OneDrive für Unternehmen Websites, die aus irgendeinem Grund nicht vollständig für die Suche indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-106">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="3c3c7-107">Die meisten e-Mail-Nachrichten und Website Dokumente werden erfolgreich indiziert, da Sie innerhalb der [Grenzwerte für e-Mail-Nachrichten](limits-for-content-search.md#indexing-limits-for-email-messages)liegen.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-107">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="3c3c7-108">Einige Elemente können diese Grenzwerte für die Indizierung jedoch überschreiten und teilweise indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-108">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="3c3c7-109">Im folgenden finden Sie weitere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine Inhaltssuche ausführen:</span><span class="sxs-lookup"><span data-stu-id="3c3c7-109">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="3c3c7-110">E-Mail-Nachrichten weisen eine angefügte Datei eines Dateityps auf, der nicht indiziert werden kann. in den meisten Fällen wird der Dateityp [für die Indizierung nicht erkannt oder nicht unterstützt](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search) .</span><span class="sxs-lookup"><span data-stu-id="3c3c7-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="3c3c7-111">E-Mail-Nachrichten weisen eine angefügte Datei ohne gültigen Handler auf, beispielsweise Bilddateien; Dies ist die häufigste Ursache für teilweise indizierte e-Mail-Elemente</span><span class="sxs-lookup"><span data-stu-id="3c3c7-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="3c3c7-112">Zu viele an eine e-Mail-Nachricht angefügte Dateien</span><span class="sxs-lookup"><span data-stu-id="3c3c7-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="3c3c7-113">Eine an eine e-Mail-Nachricht angefügte Datei ist zu groß</span><span class="sxs-lookup"><span data-stu-id="3c3c7-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="3c3c7-114">Der Dateityp wird für die Indizierung unterstützt, es ist jedoch ein Indizierungsfehler für eine bestimmte Datei aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="3c3c7-115">Obwohl es variiert, haben die meisten Organisationen Kunden weniger als 1% des Inhalts und weniger als 12% des Inhalts nach Größe, die teilweise indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-115">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="3c3c7-116">Der Grund für den Unterschied zwischen dem Volume und der Größe besteht darin, dass größere Dateien eine höhere Wahrscheinlichkeit enthalten, Inhalte zu enthalten, die nicht vollständig indiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-116">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="3c3c7-117">Warum ändert sich die teilweise indizierte Elementanzahl für eine Suche?</span><span class="sxs-lookup"><span data-stu-id="3c3c7-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="3c3c7-118">Nachdem Sie eine Inhaltssuche im Security & Compliance Center ausgeführt haben, werden die Gesamtzahl und die Größe der teilweise indizierten Elemente an den durchsuchten Speicherorten in den Suchergebnis Statistiken aufgeführt, die in den detaillierten Statistiken für die Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-118">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="3c3c7-119">Hinweis Diese werden als nicht *indizierte Elemente* in den Suchstatistiken bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-119">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="3c3c7-120">Hier sind einige Dinge, die sich auf die Anzahl der teilweise indizierten Elemente auswirken, die in den Suchergebnissen zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="3c3c7-120">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="3c3c7-121">Wenn ein Element teilweise indiziert wird und mit der Suchabfrage übereinstimmt, ist es sowohl in der Anzahl (und der Größe) von Suchergebnis Elementen als auch in teilweise indizierten Elementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-121">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="3c3c7-122">Wenn die Ergebnisse der gleichen Suche jedoch exportiert werden, ist das Element nur mit einer Reihe von Suchergebnissen enthalten; Es ist nicht als teilweise indiziertes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-122">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="3c3c7-123">Wenn Sie einen Datumsbereich für eine Suchabfrage angeben (indem Sie ihn in die Stichwortabfrage oder mithilfe einer Bedingung einbeziehen), ist ein teilweise indiziertes Element, das nicht mit dem Datumsbereich übereinstimmt, nicht Bestandteil der Anzahl der teilweise indizierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-123">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="3c3c7-124">Nur die teilweise indizierten Elemente, die innerhalb des Datumsbereichs liegen, sind in der Anzahl der teilweise indizierten Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-124">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="3c3c7-125">**Hinweis:** Teilweise indizierte Elemente, die sich in SharePoint-und OneDrive-Websites befinden, *sind nicht* in der Schätzung der teilweise indizierten Elemente enthalten, die in den detaillierten Statistiken für die Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-125">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="3c3c7-126">Teilweise indizierte Elemente können jedoch exportiert werden, wenn Sie die Ergebnisse einer Inhaltssuche exportieren.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-126">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="3c3c7-127">Wenn Sie beispielsweise nur Websites in einer Inhaltssuche durchsuchen, wird die geschätzte Anzahl der teilweise indizierten Elemente 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-127">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="3c3c7-128">Berechnen des Verhältnisses von teilweise indizierten Elementen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="3c3c7-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="3c3c7-129">Um die Exposition ihrer Organisation gegenüber teilweise indizierten Elementen zu verstehen, können Sie eine Suche nach allen Inhalten in allen Postfächern ausführen (mithilfe einer leeren Stichwortabfrage).</span><span class="sxs-lookup"><span data-stu-id="3c3c7-129">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="3c3c7-130">Im folgenden Beispiel sind 56.208 (4.830 MB) vollständig indizierte Elemente und teilweise indizierte Elemente mit 470 (316 MB) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-130">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Beispiel für Suchstatistiken mit teilweise indizierten Elementen](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="3c3c7-132">Sie können den Prozentsatz der teilweise indizierten Elemente mit den folgenden Berechnungen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="3c3c7-133">**So berechnen Sie das Verhältnis von teilweise indizierten Elementen in Ihrer Organisation:**</span><span class="sxs-lookup"><span data-stu-id="3c3c7-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="3c3c7-134">Bei Verwendung der Suchergebnisse aus dem vorherigen Beispiel sind. 84% aller Postfachelemente teilweise indiziert.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="3c3c7-135">**So berechnen Sie den Prozentsatz der Größe von teilweise indizierten Elementen in Ihrer Organisation:**</span><span class="sxs-lookup"><span data-stu-id="3c3c7-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="3c3c7-136">Im vorherigen Beispiel stammt 6,54% der Gesamtgröße der Postfachelemente aus teilweise indizierten Elementen.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-136">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="3c3c7-137">Wie bereits erwähnt, haben die meisten Kunden von Organisationen weniger als 1% des Inhalts und weniger als 12% des Inhalts nach Größe, die teilweise indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-137">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="3c3c7-138">Arbeiten mit teilweise indizierten Elementen</span><span class="sxs-lookup"><span data-stu-id="3c3c7-138">Working with partially indexed items</span></span>

<span data-ttu-id="3c3c7-139">In Fällen, in denen Sie teilweise Elemente überprüfen müssen, um zu überprüfen, dass Sie keine relevanten Informationen enthalten, können Sie [einen Inhalts Suchbericht exportieren](export-a-content-search-report.md) , der Informationen zu teilweise indizierten Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-139">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="3c3c7-140">Achten Sie beim Exportieren eines Inhalts Suchberichts darauf, eine der Exportoptionen zu wählen, die teilweise indizierte Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-140">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![Auswählen der zweiten oder dritten Option zum Exportieren von teilweise indizierten Elementen](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="3c3c7-142">Wenn Sie Inhalts Suchergebnisse oder einen Inhalts Suchbericht mit einer dieser Optionen exportieren, enthält der Export einen Bericht mit dem Namen nicht indizierte Elemente. CSV.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-142">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="3c3c7-143">Dieser Bericht enthält die meisten der gleichen Informationen wie die ResultsLog. CSV-Datei; die Datei unindexierte Elemente. csv enthält jedoch auch zwei Felder im Zusammenhang mit teilweise indizierten Elementen: **Error-Tags** und **Error-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-143">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="3c3c7-144">Diese Felder enthalten Informationen zum Indizierungsfehler für jedes teilweise indizierte Element.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-144">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="3c3c7-145">Mithilfe der Informationen in diesen beiden Feldern können Sie bestimmen, ob der Indizierungsfehler für einen bestimmten Einfluss auf ihre Untersuchung hat.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-145">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="3c3c7-146">Wenn dies der Fall ist, können Sie eine gezielte Inhaltssuche durchführen und bestimmte e-Mail-Nachrichten und SharePoint-oder OneDrive-Dokumente abrufen und exportieren, sodass Sie Sie überprüfen können, um festzustellen, ob Sie für Ihre Untersuchung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-146">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="3c3c7-147">Eine Schritt-für-Schritt-Anleitung finden Sie unter [Vorbereiten einer CSV-Datei für eine gezielte Inhaltssuche in Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="3c3c7-147">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="3c3c7-148">**Hinweis:** Die Datei "unindizierte Elemente. csv" enthält auch die Felder " **Error Type** " und " **Error Message**".</span><span class="sxs-lookup"><span data-stu-id="3c3c7-148">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="3c3c7-149">Hierbei handelt es sich um Legacy Felder, die Informationen enthalten, die den Informationen in den Feldern **Error-Tags** und **Error-Eigenschaften** ähneln, jedoch mit kleineren detaillierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-149">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="3c3c7-150">Sie können diese Legacy Felder problemlos ignorieren.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-150">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="3c3c7-151">Fehler im Zusammenhang mit teilweise indizierten Elementen</span><span class="sxs-lookup"><span data-stu-id="3c3c7-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="3c3c7-152">Fehler Tags bestehen aus zwei Informationselementen, dem Fehler und dem Dateityp.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-152">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="3c3c7-153">Beispielsweise in diesem Fehler/filetype-paar:</span><span class="sxs-lookup"><span data-stu-id="3c3c7-153">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="3c3c7-154">`parseroutputsize`ist der Fehler und `xls` ist der Dateityp der Datei, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-154">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="3c3c7-155">In Fällen, in denen der Dateityp nicht erkannt wurde oder der Dateityp nicht auf den Fehler angewendet wurde, wird der Wert `noformat` anstelle des Dateityps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-155">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="3c3c7-156">Im folgenden finden Sie eine Liste der Indizierungsfehler und eine Beschreibung der möglichen Fehlerursache.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="3c3c7-157">**Error-Tag**</span><span class="sxs-lookup"><span data-stu-id="3c3c7-157">**Error tag**</span></span>|<span data-ttu-id="3c3c7-158">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3c3c7-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="3c3c7-159">Eine e-Mail-Nachricht weist zu viele Anlagen auf, und einige dieser Anlagen wurden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="3c3c7-160">Der Inhalts Such-und Dokumentparser hat zu viele Ebenen von Anlagen gefunden, die in anderen Anlagen geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-160">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="3c3c7-161">Einige dieser Anlagen wurden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-161">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="3c3c7-162">Eine Anlage konnte nicht decodiert werden, da Sie RMS-geschützt war.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="3c3c7-163">Eine an eine e-Mail-Nachricht angefügte Datei war zu groß und konnte nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="3c3c7-164">Beim Schreiben der verarbeiteten e-Mail-Nachricht in den Index war eine der Indexeigenschaften zu groß und wurde abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-164">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="3c3c7-165">Die abgeschnittenen Eigenschaften werden im Feld Fehlereigenschaften aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-165">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="3c3c7-166">Eine e-Mail-Nachricht enthielt Text, der nicht als gültiger Unicode verarbeitet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-166">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="3c3c7-167">Die Indizierung für dieses Element ist möglicherweise unvollständig.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-167">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="3c3c7-168">Der Inhalt der Anlage oder der e-Mail-Nachricht ist verschlüsselt, und Microsoft 365 konnte den Inhalt nicht decodieren.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-168">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="3c3c7-169">Während der Analyse ist ein unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-169">An unknown error occurred during parsing.</span></span> <span data-ttu-id="3c3c7-170">Dies resultiert in der Regel aus einem Softwarefehler oder einem Dienst Absturz.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-170">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="3c3c7-171">Eine Anlage war zu groß, um vom Parser verarbeitet zu werden, und die Analyse dieser Anlage geschah nicht oder wurde nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="3c3c7-172">Eine Anlage war fehlerhaft und konnte vom Parser nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-172">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="3c3c7-173">Das Ergebnis können alte Dateiformate, Dateien, die von inkompatibler Software erstellt wurden, oder Viren, die als etwas anderes als beansprucht gelten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-173">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="3c3c7-174">Die Ausgabe aus der Analyse einer Anlage war zu groß und musste abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="3c3c7-175">Eine Anlage hatte einen Dateityp, den Microsoft 365 nicht erkennen konnte.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-175">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="3c3c7-176">Eine Anlage hat einen Dateityp, den Office 365could erkennt, aber das Analysieren dieses Dateityps wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="3c3c7-177">Der Wert einer e-Mail-Eigenschaft im Exchange-Informationsspeicher war zu groß, um abgerufen werden zu können, und die Nachricht konnte nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-177">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="3c3c7-178">Dies geschieht normalerweise nur mit der Body-Eigenschaft einer e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-178">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="3c3c7-179">Fehler beim Decodieren einer RMS-geschützten Nachricht durch den Inhaltsabruf.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="3c3c7-180">Während der Indizierung wurden im Dokument zu viele Wörter identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-180">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="3c3c7-181">Verarbeitung der Eigenschaft beim Erreichen des Grenzwerts angehalten, und die Eigenschaft wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-181">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="3c3c7-182">In den Fehler Feldern wird beschrieben, welche Felder vom Verarbeitungsfehler betroffen sind, der im Feld Fehler Tags aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-182">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="3c3c7-183">Wenn Sie eine Eigenschaft wie `subject` or `participants`durchsuchen, wirken sich Fehler im Textkörper der Nachricht nicht auf die Ergebnisse Ihrer Suche aus.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-183">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="3c3c7-184">Dies kann hilfreich sein, wenn Sie genau ermitteln, welche teilweise indizierten Elemente Sie möglicherweise noch genauer untersuchen müssen.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-184">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="3c3c7-185">Verwenden eines PowerShell-Skripts, um die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen zu ermitteln</span><span class="sxs-lookup"><span data-stu-id="3c3c7-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="3c3c7-186">In den folgenden Schritten wird gezeigt, wie Sie ein PowerShell-Skript ausführen, das nach allen Elementen in allen Exchange-Postfächern sucht und dann einen Bericht über das Verhältnis ihrer Organisation mit teilweise indizierten e-Mail-Elementen (nach Anzahl und Größe) generiert und die Anzahl der Elemente (und deren Dateityp) für jeden auftretenden Indizierungsfehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-186">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="3c3c7-187">Verwenden Sie die Fehler-Tag-Beschreibungen im vorherigen Abschnitt, um den Indizierungsfehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-187">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="3c3c7-188">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `PartiallyIndexedItems.ps1`.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. <span data-ttu-id="3c3c7-189">[Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="3c3c7-189">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="3c3c7-190">Wechseln Sie in Security & Compliance Center PowerShell zu dem Ordner, in dem Sie das Skript in Schritt 1 gespeichert haben, und führen Sie dann das Skript aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3c3c7-190">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="3c3c7-191">Im folgenden finden Sie ein Beispiel für die vom Skript zurückgegebene Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-191">Here's an example fo the output returned by the script.</span></span>
  
![Beispiel für die Ausgabe von einem Skript, das einen Bericht über die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen generiert](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="3c3c7-193">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3c3c7-193">Note the following:</span></span>
  
1. <span data-ttu-id="3c3c7-194">Die Gesamtanzahl und Größe von e-Mail-Elementen und das Verhältnis ihrer Organisation zu teilweise indizierten e-Mail-Elementen (nach Anzahl und Größe)</span><span class="sxs-lookup"><span data-stu-id="3c3c7-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="3c3c7-195">A List Error Tags und die entsprechenden Dateitypen, für die der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3c3c7-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c3c7-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c3c7-196">See also</span></span>

[<span data-ttu-id="3c3c7-197">Teilweise indizierte Elemente in der Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="3c3c7-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
