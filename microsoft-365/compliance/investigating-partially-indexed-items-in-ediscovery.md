---
title: Untersuchen teilweise indizierter Elemente in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: Erfahren Sie, wie Sie teilweise indizierte Elemente (auch als nicht indizierte Elemente bezeichnet) aus Exchange, SharePoint und OneDrive for Business in Ihrer Organisation verwalten.
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311454"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="a5c09-103">Untersuchen teilweise indizierter Elemente in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a5c09-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="a5c09-104">Eine eDiscovery-Suche, die Sie über das Microsoft 365 Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="a5c09-105">Teilweise indizierte Elemente Exchange Postfachelemente und Dokumente auf SharePoint- und OneDrive for Business-Websites, die aus einem bestimmten Grund nicht vollständig für die Suche indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="a5c09-106">Die meisten E-Mail-Nachrichten und Websitedokumente werden erfolgreich indiziert, da sie innerhalb der Indizierungsgrenzwerte für [E-Mail-Nachrichten liegen.](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="a5c09-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="a5c09-107">Einige Elemente überschreiten jedoch möglicherweise diese Indizierungsgrenzwerte und werden teilweise indiziert.</span><span class="sxs-lookup"><span data-stu-id="a5c09-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="a5c09-108">Es gibt weitere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine eDiscovery-Suche ausführen:</span><span class="sxs-lookup"><span data-stu-id="a5c09-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="a5c09-109">E-Mail-Nachrichten verfügen über eine angefügte Datei ohne gültigen Handler, z. B. Bilddateien. Dies ist die häufigste Ursache für teilweise indizierte E-Mail-Elemente.</span><span class="sxs-lookup"><span data-stu-id="a5c09-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="a5c09-110">Die E-Mail enthält zu viele Dateien im Anhang.</span><span class="sxs-lookup"><span data-stu-id="a5c09-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="a5c09-111">Die an die E-Mail angehängte Datei ist zu groß.</span><span class="sxs-lookup"><span data-stu-id="a5c09-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="a5c09-112">Der Dateityp wird für die Indizierung unterstützt, aber es ist ein Indizierungsfehler für eine bestimmte Datei aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="a5c09-113">Obwohl dies unterschiedlich ist, verfügen die meisten Organisationen über weniger als 1 % des Inhalts nach Volumen und weniger als 12 % des Teils indizierten Inhalts.</span><span class="sxs-lookup"><span data-stu-id="a5c09-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="a5c09-114">Der Grund für den Unterschied zwischen dem Volume und der Größe ist, dass größere Dateien eine höhere Wahrscheinlichkeit haben, Inhalte zu enthalten, die nicht vollständig indiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="a5c09-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="a5c09-115">Warum ändert sich die teilweise indizierte Elementanzahl für eine Suche?</span><span class="sxs-lookup"><span data-stu-id="a5c09-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="a5c09-116">Nachdem Sie eine eDiscovery-Suche ausgeführt haben, werden die Gesamtanzahl und Größe teilweise indizierter Elemente an den durchsuchten Speicherorten in den Suchergebnisstatistiken aufgeführt, die in den detaillierten Statistiken für die Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="a5c09-117">Beachten Sie, dass diese  *elemente in der Suchstatistik*  als nicht indizierte Elemente bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="a5c09-118">Hier sind einige Dinge, die sich auf die Anzahl der teilweise indizierten Elemente auswirken, die in den Suchergebnissen zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="a5c09-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="a5c09-119">Wenn ein Element teilweise indiziert ist und der Suchabfrage entspricht, ist es sowohl in der Anzahl (und Größe) von Suchergebnissen als auch in teilweise indizierten Elementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="a5c09-120">Wenn jedoch die Ergebnisse derselben Suche exportiert werden, wird das Element nur in einer Reihe von Suchergebnissen enthalten. es ist nicht als teilweise indiziertes Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="a5c09-121">Teilweise indizierte Elemente, die sich in SharePoint-  und OneDrive-Websites befinden, sind nicht in der Schätzung teilweise indizierter Elemente enthalten, die in den detaillierten Statistiken für die Suche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-121">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="a5c09-122">Teilweise indizierte Elemente können jedoch exportiert werden, wenn Sie die Ergebnisse einer eDiscovery-Suche exportieren.</span><span class="sxs-lookup"><span data-stu-id="a5c09-122">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="a5c09-123">Wenn Sie beispielsweise nur Websites durchsuchen, ist die geschätzte Anzahl teilweise indizierter Elemente null.</span><span class="sxs-lookup"><span data-stu-id="a5c09-123">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="a5c09-124">Berechnen des Verhältnisses teilweise indizierter Elemente in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a5c09-124">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="a5c09-125">Um die Belastung Ihrer Organisation gegenüber teilweise indizierten Elementen zu verstehen, können Sie eine Suche nach allen Inhalten in allen Postfächern (mithilfe einer leeren Schlüsselwortabfrage) ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-125">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="a5c09-126">Im folgenden Beispiel sind 1.629.904 (146,46 GB) vollständig indizierte Elemente und 10.025 (10,27 GB) teilweise indizierte Elemente.</span><span class="sxs-lookup"><span data-stu-id="a5c09-126">In the following example, there are 1,629,904 (146.46 GB) fully indexed items and 10,025 (10.27 GB) partially indexed items.</span></span>
  
![Beispiel für Suchstatistiken mit teilweise indizierten Elementen](../media/PartiallyIndexedItemsTest.png)
  
<span data-ttu-id="a5c09-128">Sie können den Prozentsatz teilweise indizierter Elemente mithilfe der folgenden Berechnungen bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-128">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="a5c09-129">**So berechnen Sie das Verhältnis von teilweise indizierten Elementen in Ihrer Organisation:**</span><span class="sxs-lookup"><span data-stu-id="a5c09-129">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

<span data-ttu-id="a5c09-130">Mithilfe der Suchergebnisse aus dem vorherigen Beispiel werden 0,62 % aller Postfachelemente teilweise indiziert.</span><span class="sxs-lookup"><span data-stu-id="a5c09-130">By using the search results from the previous example, 0.62% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="a5c09-131">**So berechnen Sie den Prozentsatz der Größe teilweise indizierter Elemente in Ihrer Organisation:**</span><span class="sxs-lookup"><span data-stu-id="a5c09-131">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

<span data-ttu-id="a5c09-132">Im vorherigen Beispiel sind also 7 % der Gesamtgröße von Postfachelementen aus teilweise indizierten Elementen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-132">So in the previous example, 7% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="a5c09-133">Wie bereits erwähnt, verfügen die meisten Organisationen über weniger als 1 % des Inhalts nach Volumen und weniger als 12 % des Teils indizierten Inhalts.</span><span class="sxs-lookup"><span data-stu-id="a5c09-133">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="a5c09-134">Arbeiten mit teilweise indizierten Elementen</span><span class="sxs-lookup"><span data-stu-id="a5c09-134">Working with partially indexed items</span></span>

<span data-ttu-id="a5c09-135">In Fällen, in denen Sie teilweise Elemente untersuchen müssen, um zu [](export-a-content-search-report.md) überprüfen, ob sie keine relevanten Informationen enthalten, können Sie einen Inhaltssuchbericht exportieren, der Informationen zu teilweise indizierten Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="a5c09-135">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="a5c09-136">Wenn Sie einen Inhaltssuchbericht exportieren, müssen Sie eine der Exportoptionen auswählen, die teilweise indizierte Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-136">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Auswählen der zweiten oder dritten Option zum Exportieren teilweise indizierter Elemente](../media/PartiallyIndexedItemsExportOptions.png)
  
<span data-ttu-id="a5c09-138">Wenn Sie eDiscovery-Suchergebnisse oder einen Suchbericht mit einer dieser Optionen exportieren, enthält der Export einen Bericht namens Unindexed Items.csv.</span><span class="sxs-lookup"><span data-stu-id="a5c09-138">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="a5c09-139">Dieser Bericht enthält die meisten der gleichen Informationen wie die ResultsLog.csv Datei. Die Datei Nicht indizierte Items.csv enthält jedoch auch zwei Felder im Zusammenhang mit teilweise indizierten Elementen: **Fehlertags** und **Fehlereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a5c09-139">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="a5c09-140">Diese Felder enthalten Informationen zum Indizierungsfehler für jedes teilweise indizierte Element.</span><span class="sxs-lookup"><span data-stu-id="a5c09-140">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="a5c09-141">Mithilfe der Informationen in diesen beiden Feldern können Sie ermitteln, ob sich der Indizierungsfehler für eine bestimmte Untersuchung auf Ihre Untersuchung aus wirkt.</span><span class="sxs-lookup"><span data-stu-id="a5c09-141">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="a5c09-142">In diesem Fall können Sie eine gezielte Suche durchführen und bestimmte E-Mail-Nachrichten und SharePoint- oder OneDrive-Dokumente abrufen und exportieren, damit Sie diese untersuchen können, um festzustellen, ob sie für Ihre Untersuchung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="a5c09-142">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="a5c09-143">Schrittweise Anweisungen finden Sie unter [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="a5c09-143">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a5c09-144">Die Nicht indizierte Items.csv enthält auch felder mit dem Namen **Fehlertyp** und **Fehlermeldung**.</span><span class="sxs-lookup"><span data-stu-id="a5c09-144">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="a5c09-145">Dies sind Legacyfelder, die Informationen enthalten, die  den Informationen in den Feldern **Fehlertags** und Fehlereigenschaften ähneln, jedoch mit weniger detaillierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-145">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="a5c09-146">Sie können diese Legacyfelder sicher ignorieren.</span><span class="sxs-lookup"><span data-stu-id="a5c09-146">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="a5c09-147">Fehler im Zusammenhang mit teilweise indizierten Elementen</span><span class="sxs-lookup"><span data-stu-id="a5c09-147">Errors related to partially indexed items</span></span>

<span data-ttu-id="a5c09-148">Fehlertags besteht aus zwei Informationsteilen, dem Fehler und dem Dateityp.</span><span class="sxs-lookup"><span data-stu-id="a5c09-148">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="a5c09-149">Beispiel: In diesem Fehler-Datei-Typ-Paar:</span><span class="sxs-lookup"><span data-stu-id="a5c09-149">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="a5c09-150">`parseroutputsize` ist der Fehler und `xls` der Dateityp der Datei, in der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a5c09-150">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="a5c09-151">In Fällen, in denen der Dateityp nicht erkannt wurde oder der Dateityp nicht auf den Fehler angewendet wurde, wird der Wert statt des `noformat` Dateityps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5c09-151">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="a5c09-152">Im Folgenden finden Sie eine Liste der Indizierungsfehler und eine Beschreibung der möglichen Ursache des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="a5c09-152">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="a5c09-153">Fehlertag</span><span class="sxs-lookup"><span data-stu-id="a5c09-153">Error tag</span></span> | <span data-ttu-id="a5c09-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5c09-154">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="a5c09-155">Eine E-Mail-Nachricht hatte zu viele Anlagen, und einige dieser Anlagen wurden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a5c09-155">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="a5c09-156">Der Inhalts-Retriever und der Dokumentparser haben zu viele Ebenen von Anlagen gefunden, die in anderen Anlagen geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="a5c09-156">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="a5c09-157">Einige dieser Anlagen wurden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a5c09-157">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="a5c09-158">Fehler beim Decodieren einer Anlage, da sie RMS-geschützt war.</span><span class="sxs-lookup"><span data-stu-id="a5c09-158">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="a5c09-159">Eine an eine E-Mail-Nachricht angefügte Datei war zu groß und konnte nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-159">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="a5c09-160">Beim Schreiben der verarbeiteten E-Mail-Nachricht in den Index war eine der indexierbaren Eigenschaften zu groß und wurde abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-160">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="a5c09-161">Die abgeschnittenen Eigenschaften werden im Feld Fehlereigenschaften aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5c09-161">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="a5c09-162">Eine E-Mail-Nachricht enthielt Text, der nicht als gültiger Unicode-Code verarbeitet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="a5c09-162">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="a5c09-163">Die Indizierung für dieses Element kann unvollständig sein.</span><span class="sxs-lookup"><span data-stu-id="a5c09-163">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="a5c09-164">Der Inhalt der Anlage oder E-Mail-Nachricht ist verschlüsselt, und Microsoft 365 inhalte konnten nicht decodiert werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-164">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="a5c09-165">Bei der Analyse ist ein unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-165">An unknown error occurred during parsing.</span></span> <span data-ttu-id="a5c09-166">Dies resultiert in der Regel aus einem Softwarefehler oder einem Dienstabsturz.</span><span class="sxs-lookup"><span data-stu-id="a5c09-166">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="a5c09-167">Eine Anlage war für den Parser zu groß, und die Analyse dieser Anlage wurde nicht durchgeführt oder nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-167">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="a5c09-168">Eine Anlage wurde falsch formatiert und konnte vom Parser nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-168">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="a5c09-169">Dieses Ergebnis kann auf alte Dateiformate, dateien, die von inkompatibler Software erstellt wurden, oder Viren, die vorgeben, etwas anderes als beansprucht zu sein, verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-169">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="a5c09-170">Die Ausgabe aus der Analyse einer Anlage war zu groß und musste abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-170">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="a5c09-171">Eine Anlage hatte einen Dateityp, Microsoft 365 nicht erkannt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="a5c09-171">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="a5c09-172">Eine Anlage hatte einen Dateityp, den Office 365 erkennen konnte, aber die Analyse dieses Dateityps wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a5c09-172">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="a5c09-173">Der Wert einer E-Mail-Eigenschaft in Exchange Store war zu groß, um abgerufen zu werden, und die Nachricht konnte nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a5c09-173">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="a5c09-174">Dies geschieht in der Regel nur für die body-Eigenschaft einer E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a5c09-174">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="a5c09-175">Der Inhalts-Retriever konnte eine RMS-geschützte Nachricht nicht decodieren.</span><span class="sxs-lookup"><span data-stu-id="a5c09-175">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="a5c09-176">Zu viele Wörter wurden während der Indizierung im Dokument identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a5c09-176">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="a5c09-177">Die Verarbeitung der Eigenschaft wurde beendet, wenn der Grenzwert erreicht wurde, und die Eigenschaft wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="a5c09-177">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="a5c09-178">Fehlerfelder beschreiben, welche Felder vom Verarbeitungsfehler betroffen sind, der im Feld Fehlertags aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a5c09-178">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="a5c09-179">Wenn Sie eine Eigenschaft wie or durchsuchen, haben Fehler im Nachrichtentext keine Auswirkungen auf die Ergebnisse  `subject`  `participants` Ihrer Suche.</span><span class="sxs-lookup"><span data-stu-id="a5c09-179">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="a5c09-180">Dies kann hilfreich sein, wenn Sie genau bestimmen, welche teilweise indizierten Elemente Sie möglicherweise weiter untersuchen müssen.</span><span class="sxs-lookup"><span data-stu-id="a5c09-180">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="a5c09-181">Verwenden eines PowerShell-Skripts zum Bestimmen der Belastung Ihrer Organisation gegenüber teilweise indizierten E-Mail-Elementen</span><span class="sxs-lookup"><span data-stu-id="a5c09-181">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="a5c09-182">In den folgenden Schritten wird gezeigt, wie Sie ein PowerShell-Skript ausführen, das nach allen Elementen in allen Exchange-Postfächern sucht und anschließend einen Bericht über das Verhältnis ihrer Organisation aus teilweise indizierten E-Mail-Elementen (nach Anzahl und Größe) generiert und die Anzahl der Elemente (und deren Dateityp) für jeden aufgetretenen Indizierungsfehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a5c09-182">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="a5c09-183">Verwenden Sie die Beschreibungen des Fehlertags im vorherigen Abschnitt, um den Indizierungsfehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a5c09-183">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="a5c09-184">Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie ein Dateinamensuffix von .ps1; Beispiel: `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="a5c09-184">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="a5c09-185">[Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5c09-185">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="a5c09-186">Wechseln Sie & Compliance Center PowerShell zu dem Ordner, in dem Sie das Skript in Schritt 1 gespeichert haben, und führen Sie das Skript aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5c09-186">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="a5c09-187">Hier sehen Sie ein Beispiel für die vom Skript zurückgegebene Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a5c09-187">Here's an example fo the output returned by the script.</span></span>
  
![Beispiel für die Ausgabe aus einem Skript, das einen Bericht über die Belastung Ihrer Organisation gegenüber teilweise indizierten E-Mail-Elementen generiert](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="a5c09-189">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a5c09-189">Note the following:</span></span>
>  
> - <span data-ttu-id="a5c09-190">Die Gesamtanzahl und Größe der E-Mail-Elemente und das Verhältnis Ihrer Organisation zu teilweise indizierten E-Mail-Elementen (nach Anzahl und Größe).</span><span class="sxs-lookup"><span data-stu-id="a5c09-190">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="a5c09-191">Ein Listenfehlertags und die entsprechenden Dateitypen, für die der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a5c09-191">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5c09-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5c09-192">See also</span></span>

[<span data-ttu-id="a5c09-193">Teilweise indizierte Elemente in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a5c09-193">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)