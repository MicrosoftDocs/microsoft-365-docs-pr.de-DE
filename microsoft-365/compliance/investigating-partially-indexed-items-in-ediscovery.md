---
title: Untersuchen von teilweise indizierten Elementen in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Informationen zum Verwalten von teilweise indizierten (oder nicht indizierten) Elementen aus Exchange, SharePoint und OneDrive für Unternehmen in Ihrer Organisation.
ms.openlocfilehash: 132a174f0c163c75939b75906baa3833c6387fa7
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588562"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="4b08c-103">Untersuchen von teilweise indizierten Elementen in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4b08c-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="4b08c-104">Eine eDiscovery-Suche, die Sie im Microsoft 365 Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="4b08c-105">Teilweise indizierte Elemente sind Exchange-Postfachelemente und Dokumente in SharePoint und OneDrive für Unternehmen Websites, die aus irgendeinem Grund nicht vollständig für die Suche indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="4b08c-106">Die meisten e-Mail-Nachrichten und Website Dokumente werden erfolgreich indiziert, da Sie innerhalb der [Grenzwerte für e-Mail-Nachrichten](limits-for-content-search.md#indexing-limits-for-email-messages)liegen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="4b08c-107">Einige Elemente können diese Grenzwerte für die Indizierung jedoch überschreiten und teilweise indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="4b08c-108">Im folgenden finden Sie weitere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine eDiscovery-Suche ausführen:</span><span class="sxs-lookup"><span data-stu-id="4b08c-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="4b08c-109">E-Mail-Nachrichten weisen eine angefügte Datei ohne gültigen Handler auf, beispielsweise Bilddateien; Dies ist die häufigste Ursache für teilweise indizierte e-Mail-Elemente.</span><span class="sxs-lookup"><span data-stu-id="4b08c-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="4b08c-110">Die E-Mail enthält zu viele Dateien im Anhang.</span><span class="sxs-lookup"><span data-stu-id="4b08c-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="4b08c-111">Die an die E-Mail angehängte Datei ist zu groß.</span><span class="sxs-lookup"><span data-stu-id="4b08c-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="4b08c-112">Der Dateityp wird für die Indizierung unterstützt, aber es ist ein Indizierungsfehler für eine bestimmte Datei aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="4b08c-113">Obwohl es variiert, haben die meisten Organisationen Kunden weniger als 1% des Inhalts und weniger als 12% des Inhalts nach Größe, die teilweise indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="4b08c-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="4b08c-114">Der Grund für den Unterschied zwischen dem Volume und der Größe besteht darin, dass größere Dateien eine höhere Wahrscheinlichkeit enthalten, Inhalte zu enthalten, die nicht vollständig indiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="4b08c-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="4b08c-115">Warum ändert sich die teilweise indizierte Elementanzahl für eine Suche?</span><span class="sxs-lookup"><span data-stu-id="4b08c-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="4b08c-116">Nachdem Sie eine eDiscovery-Suche ausgeführt haben, werden die Gesamtzahl und die Größe der teilweise indizierten Elemente an den durchsuchten Speicherorten in den Suchergebnis Statistiken aufgeführt, die in den detaillierten Statistiken für die Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="4b08c-117">Hinweis Diese werden als nicht  *indizierte Elemente*  in den Suchstatistiken bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4b08c-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="4b08c-118">Hier sind einige Dinge, die sich auf die Anzahl der teilweise indizierten Elemente auswirken, die in den Suchergebnissen zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="4b08c-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="4b08c-119">Wenn ein Element teilweise indiziert wird und mit der Suchabfrage übereinstimmt, ist es sowohl in der Anzahl (und der Größe) von Suchergebnis Elementen als auch in teilweise indizierten Elementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="4b08c-120">Wenn die Ergebnisse der gleichen Suche jedoch exportiert werden, ist das Element nur mit einer Reihe von Suchergebnissen enthalten; Es ist nicht als teilweise indiziertes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="4b08c-121">Wenn Sie einen Datumsbereich für eine Suchabfrage angeben (indem Sie ihn in die Stichwortabfrage oder mithilfe einer Bedingung einbeziehen), ist ein teilweise indiziertes Element, das nicht mit dem Datumsbereich übereinstimmt, nicht Bestandteil der Anzahl der teilweise indizierten Elemente.</span><span class="sxs-lookup"><span data-stu-id="4b08c-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="4b08c-122">Nur die teilweise indizierten Elemente, die innerhalb des Datumsbereichs liegen, sind in der Anzahl der indizierten Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-122">Only the partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4b08c-123">Teilweise indizierte Elemente, die sich in SharePoint-und OneDrive-Websites befinden, *sind nicht* in der Schätzung der teilweise indizierten Elemente enthalten, die in den detaillierten Statistiken für die Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="4b08c-124">Teilweise indizierte Elemente können jedoch exportiert werden, wenn Sie die Ergebnisse einer eDiscovery-Suche exportieren.</span><span class="sxs-lookup"><span data-stu-id="4b08c-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="4b08c-125">Wenn Sie beispielsweise nur Websites Durchsuchen, ist die geschätzte Anzahl der teilweise indizierten Elemente gleich NULL.</span><span class="sxs-lookup"><span data-stu-id="4b08c-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="4b08c-126">Berechnen des Verhältnisses von teilweise indizierten Elementen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4b08c-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="4b08c-127">Um die Exposition ihrer Organisation gegenüber teilweise indizierten Elementen zu verstehen, können Sie eine Suche nach allen Inhalten in allen Postfächern ausführen (mithilfe einer leeren Stichwortabfrage).</span><span class="sxs-lookup"><span data-stu-id="4b08c-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="4b08c-128">Im folgenden Beispiel sind 56.208 (4.830 MB) vollständig indizierte Elemente und teilweise indizierte Elemente mit 470 (316 MB) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Beispiel für Suchstatistiken mit teilweise indizierten Elementen](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="4b08c-130">Sie können den Prozentsatz der teilweise indizierten Elemente mit den folgenden Berechnungen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4b08c-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="4b08c-131">**So berechnen Sie das Verhältnis von teilweise indizierten Elementen in Ihrer Organisation:**</span><span class="sxs-lookup"><span data-stu-id="4b08c-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="4b08c-132">Bei Verwendung der Suchergebnisse aus dem vorherigen Beispiel sind. 84% aller Postfachelemente teilweise indiziert.</span><span class="sxs-lookup"><span data-stu-id="4b08c-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="4b08c-133">**So berechnen Sie den Prozentsatz der Größe von teilweise indizierten Elementen in Ihrer Organisation:**</span><span class="sxs-lookup"><span data-stu-id="4b08c-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="4b08c-134">Im vorherigen Beispiel stammt 6,54% der Gesamtgröße der Postfachelemente aus teilweise indizierten Elementen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="4b08c-135">Wie bereits erwähnt, haben die meisten Kunden von Organisationen weniger als 1% des Inhalts und weniger als 12% des Inhalts nach Größe, die teilweise indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="4b08c-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="4b08c-136">Arbeiten mit teilweise indizierten Elementen</span><span class="sxs-lookup"><span data-stu-id="4b08c-136">Working with partially indexed items</span></span>

<span data-ttu-id="4b08c-137">In Fällen, in denen Sie teilweise Elemente überprüfen müssen, um zu überprüfen, dass Sie keine relevanten Informationen enthalten, können Sie [einen Inhalts Suchbericht exportieren](export-a-content-search-report.md) , der Informationen zu teilweise indizierten Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="4b08c-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="4b08c-138">Achten Sie beim Exportieren eines Inhalts Suchberichts darauf, eine der Exportoptionen zu wählen, die teilweise indizierte Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Auswählen der zweiten oder dritten Option zum Exportieren von teilweise indizierten Elementen](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="4b08c-140">Wenn Sie eDiscovery-Suchergebnisse oder einen Suchbericht mit einer dieser Optionen exportieren, enthält der Export einen Bericht mit dem Namen unindexierte Items.csv.</span><span class="sxs-lookup"><span data-stu-id="4b08c-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="4b08c-141">Dieser Bericht enthält die meisten der gleichen Informationen wie die ResultsLog.csv Datei; die nicht indizierte Items.csv-Datei enthält jedoch auch zwei Felder im Zusammenhang mit teilweise indizierten Elementen: **Error-Tags** und **Error-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4b08c-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="4b08c-142">Diese Felder enthalten Informationen zum Indizierungsfehler für jedes teilweise indizierte Element.</span><span class="sxs-lookup"><span data-stu-id="4b08c-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="4b08c-143">Mithilfe der Informationen in diesen beiden Feldern können Sie bestimmen, ob der Indizierungsfehler für einen bestimmten Einfluss auf ihre Untersuchung hat.</span><span class="sxs-lookup"><span data-stu-id="4b08c-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="4b08c-144">Wenn dies der Fall ist, können Sie eine gezielte Suche durchführen und bestimmte e-Mail-Nachrichten und SharePoint-oder OneDrive-Dokumente abrufen und exportieren, sodass Sie Sie überprüfen können, um festzustellen, ob Sie für Ihre Untersuchung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="4b08c-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="4b08c-145">Eine Schritt-für-Schritt-Anleitung finden Sie unter [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="4b08c-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4b08c-146">Die nicht indizierte Items.csv Datei enthält auch die Felder " **Error Type** " und " **Error Message**".</span><span class="sxs-lookup"><span data-stu-id="4b08c-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="4b08c-147">Hierbei handelt es sich um Legacy Felder, die Informationen enthalten, die den Informationen in den Feldern **Error-Tags** und **Error-Eigenschaften** ähneln, jedoch mit kleineren detaillierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="4b08c-148">Sie können diese Legacy Felder problemlos ignorieren.</span><span class="sxs-lookup"><span data-stu-id="4b08c-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="4b08c-149">Fehler im Zusammenhang mit teilweise indizierten Elementen</span><span class="sxs-lookup"><span data-stu-id="4b08c-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="4b08c-150">Fehler Tags bestehen aus zwei Informationselementen, dem Fehler und dem Dateityp.</span><span class="sxs-lookup"><span data-stu-id="4b08c-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="4b08c-151">Beispielsweise in diesem Error/File-Type-paar:</span><span class="sxs-lookup"><span data-stu-id="4b08c-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="4b08c-152">`parseroutputsize` ist der Fehler und `xls` ist der Dateityp der Datei, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4b08c-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="4b08c-153">In Fällen, in denen der Dateityp nicht erkannt wurde oder der Dateityp nicht auf den Fehler angewendet wurde, wird der Wert `noformat` anstelle des Dateityps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b08c-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="4b08c-154">Im folgenden finden Sie eine Liste der Indizierungsfehler und eine Beschreibung der möglichen Fehlerursache.</span><span class="sxs-lookup"><span data-stu-id="4b08c-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="4b08c-155">Error-Tag</span><span class="sxs-lookup"><span data-stu-id="4b08c-155">Error tag</span></span> | <span data-ttu-id="4b08c-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b08c-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="4b08c-157">Eine e-Mail-Nachricht weist zu viele Anlagen auf, und einige dieser Anlagen wurden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4b08c-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="4b08c-158">Der Inhalts Such-und Dokumentparser hat zu viele Ebenen von Anlagen gefunden, die in anderen Anlagen geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="4b08c-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="4b08c-159">Einige dieser Anlagen wurden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="4b08c-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="4b08c-160">Eine Anlage konnte nicht decodiert werden, da Sie RMS-geschützt war.</span><span class="sxs-lookup"><span data-stu-id="4b08c-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="4b08c-161">Eine an eine e-Mail-Nachricht angefügte Datei war zu groß und konnte nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="4b08c-162">Beim Schreiben der verarbeiteten e-Mail-Nachricht in den Index war eine der Indexeigenschaften zu groß und wurde abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="4b08c-163">Die abgeschnittenen Eigenschaften werden im Feld Fehlereigenschaften aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="4b08c-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="4b08c-164">Eine e-Mail-Nachricht enthielt Text, der nicht als gültiger Unicode verarbeitet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="4b08c-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="4b08c-165">Die Indizierung für dieses Element ist möglicherweise unvollständig.</span><span class="sxs-lookup"><span data-stu-id="4b08c-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="4b08c-166">Der Inhalt der Anlage oder der e-Mail-Nachricht ist verschlüsselt, und Microsoft 365 konnte den Inhalt nicht decodieren.</span><span class="sxs-lookup"><span data-stu-id="4b08c-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="4b08c-167">Während der Analyse ist ein unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="4b08c-168">Dies resultiert in der Regel aus einem Softwarefehler oder einem Dienst Absturz.</span><span class="sxs-lookup"><span data-stu-id="4b08c-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="4b08c-169">Eine Anlage war zu groß, um vom Parser verarbeitet zu werden, und die Analyse dieser Anlage geschah nicht oder wurde nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="4b08c-170">Eine Anlage war fehlerhaft und konnte vom Parser nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="4b08c-171">Dieses Ergebnis kann durch alte Dateiformate, Dateien, die von inkompatibler Software erstellt wurden, oder durch Viren verursacht werden, die als etwas anderes als beansprucht einstehen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="4b08c-172">Die Ausgabe aus der Analyse einer Anlage war zu groß und musste abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="4b08c-173">Eine Anlage hatte einen Dateityp, den Microsoft 365 nicht erkennen konnte.</span><span class="sxs-lookup"><span data-stu-id="4b08c-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="4b08c-174">Eine Anlage hatte einen Dateityp, den Office 365 erkennen konnte, aber das Analysieren des Dateityps wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4b08c-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="4b08c-175">Der Wert einer e-Mail-Eigenschaft im Exchange-Informationsspeicher war zu groß, um abgerufen werden zu können, und die Nachricht konnte nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4b08c-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="4b08c-176">Dies geschieht normalerweise nur mit der Body-Eigenschaft einer e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="4b08c-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="4b08c-177">Fehler beim Decodieren einer RMS-geschützten Nachricht durch den Inhaltsabruf.</span><span class="sxs-lookup"><span data-stu-id="4b08c-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="4b08c-178">Während der Indizierung wurden im Dokument zu viele Wörter identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4b08c-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="4b08c-179">Verarbeitung der Eigenschaft beim Erreichen des Grenzwerts angehalten, und die Eigenschaft wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="4b08c-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="4b08c-180">In den Fehler Feldern wird beschrieben, welche Felder vom Verarbeitungsfehler betroffen sind, der im Feld Fehler Tags aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="4b08c-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="4b08c-181">Wenn Sie eine Eigenschaft wie or durchsuchen  `subject`  `participants` , wirken sich Fehler im Textkörper der Nachricht nicht auf die Ergebnisse Ihrer Suche aus.</span><span class="sxs-lookup"><span data-stu-id="4b08c-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="4b08c-182">Dies kann hilfreich sein, wenn Sie genau ermitteln, welche teilweise indizierten Elemente Sie möglicherweise noch genauer untersuchen müssen.</span><span class="sxs-lookup"><span data-stu-id="4b08c-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="4b08c-183">Verwenden eines PowerShell-Skripts, um die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen zu ermitteln</span><span class="sxs-lookup"><span data-stu-id="4b08c-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="4b08c-184">In den folgenden Schritten wird gezeigt, wie Sie ein PowerShell-Skript ausführen, das nach allen Elementen in allen Exchange-Postfächern sucht und dann einen Bericht über das Verhältnis ihrer Organisation mit teilweise indizierten e-Mail-Elementen (nach Anzahl und Größe) generiert und die Anzahl der Elemente (und deren Dateityp) für jeden auftretenden Indizierungsfehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="4b08c-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="4b08c-185">Verwenden Sie die Fehler-Tag-Beschreibungen im vorherigen Abschnitt, um den Indizierungsfehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4b08c-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="4b08c-186">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4b08c-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="4b08c-187">[Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="4b08c-187">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>

3. <span data-ttu-id="4b08c-188">Wechseln Sie in Security & Compliance Center PowerShell zu dem Ordner, in dem Sie das Skript in Schritt 1 gespeichert haben, und führen Sie dann das Skript aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4b08c-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="4b08c-189">Im folgenden finden Sie ein Beispiel für die vom Skript zurückgegebene Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4b08c-189">Here's an example fo the output returned by the script.</span></span>
  
![Beispiel für die Ausgabe von einem Skript, das einen Bericht über die Exposition ihrer Organisation gegenüber teilweise indizierten e-Mail-Elementen generiert](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="4b08c-191">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b08c-191">Note the following:</span></span>
  
1. <span data-ttu-id="4b08c-192">Die Gesamtanzahl und Größe von e-Mail-Elementen und das Verhältnis ihrer Organisation zu teilweise indizierten e-Mail-Elementen (nach Anzahl und Größe)</span><span class="sxs-lookup"><span data-stu-id="4b08c-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>

2. <span data-ttu-id="4b08c-193">A List Error Tags und die entsprechenden Dateitypen, für die der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4b08c-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b08c-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b08c-194">See also</span></span>

[<span data-ttu-id="4b08c-195">Teilweise indizierte Elemente in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4b08c-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)
