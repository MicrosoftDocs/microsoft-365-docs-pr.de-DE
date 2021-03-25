---
title: Techniken in der Gerätezeitachse
description: Grundlegendes zur Gerätezeitachse in Microsoft Defender for Endpoint
keywords: Gerätezeitachse, Endpunkt, MITRE, MITRE ATT&CK, Techniken, Taktiken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185467"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="a96f7-104">Techniken in der Gerätezeitachse</span><span class="sxs-lookup"><span data-stu-id="a96f7-104">Techniques in the device timeline</span></span>


<span data-ttu-id="a96f7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a96f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="a96f7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a96f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="a96f7-107">Sie können mehr Einblick in eine Untersuchung gewinnen, indem Sie die Ereignisse analysieren, die auf einem bestimmten Gerät passiert sind.</span><span class="sxs-lookup"><span data-stu-id="a96f7-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="a96f7-108">Wählen Sie zunächst das gerät von Interesse in der [Liste Geräte aus.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a96f7-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="a96f7-109">Auf der Geräteseite können Sie die Registerkarte **Zeitachse** auswählen, um alle Ereignisse anzuzeigen, die auf dem Gerät aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="a96f7-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="a96f7-110">Verstehen von Techniken in der Zeitachse</span><span class="sxs-lookup"><span data-stu-id="a96f7-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="a96f7-111">Einige Informationen beziehen sich auf ein vorab veröffentlichtes Produktfeature in der öffentlichen Vorschau, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a96f7-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a96f7-112">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="a96f7-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a96f7-113">In Microsoft Defender for Endpoint sind **Techniken** ein zusätzlicher Datentyp in der Ereigniszeitachse.</span><span class="sxs-lookup"><span data-stu-id="a96f7-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="a96f7-114">Techniken bieten mehr Einblick in Aktivitäten im Zusammenhang mit [MITRE ATT&CK-Techniken](https://attack.mitre.org/) oder Untertechniken.</span><span class="sxs-lookup"><span data-stu-id="a96f7-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="a96f7-115">Dieses Feature vereinfacht die Untersuchungserfahrung, indem Analysten die Aktivitäten verstehen, die auf einem Gerät beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="a96f7-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="a96f7-116">Analysten können dann entscheiden, weitere Untersuchungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="a96f7-117">Für die öffentliche Vorschau sind Techniken standardmäßig verfügbar und werden zusammen mit Ereignissen angezeigt, wenn die Zeitachse eines Geräts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a96f7-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![Screenshot der Techniken in der Gerätezeitachse](images/device-timeline-2.png)

<span data-ttu-id="a96f7-119">Techniken werden in fett formatiertem Text hervorgehoben und mit einem blauen Symbol auf der linken Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a96f7-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="a96f7-120">Die entsprechende MITRE ATT-&CK-ID und dem Techniknamen werden auch unter Zusätzliche Informationen als Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a96f7-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="a96f7-121">Such- und Exportoptionen sind auch für Techniken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a96f7-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="a96f7-122">Untersuchen der Verwendung des Seitenbereichs</span><span class="sxs-lookup"><span data-stu-id="a96f7-122">Investigate using the side pane</span></span>

<span data-ttu-id="a96f7-123">Wählen Sie eine Technik aus, um den entsprechenden Seitenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="a96f7-124">Hier finden Sie weitere Informationen und Einblicke wie verwandte ATT-&CK-Techniken, Taktiken und Beschreibungen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="a96f7-125">Wählen Sie die spezifische *Angriffstechnik aus,* um die zugehörige ATT-&CK-Technikseite zu öffnen, auf der Sie weitere Informationen dazu finden.</span><span class="sxs-lookup"><span data-stu-id="a96f7-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="a96f7-126">Sie können die Details einer Entität kopieren, wenn rechts ein blaues Symbol angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a96f7-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="a96f7-127">Wenn Sie beispielsweise sha1 einer verwandten Datei kopieren möchten, wählen Sie das blaue Seitensymbol aus.</span><span class="sxs-lookup"><span data-stu-id="a96f7-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![Kopieren von Entitätsdetails](images/techniques-side-pane-clickable.png)

<span data-ttu-id="a96f7-129">Sie können dasselbe für Befehlszeilen ausführen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-129">You can do the same for command lines.</span></span>

![Befehlszeile kopieren](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="a96f7-131">Untersuchen verwandter Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a96f7-131">Investigate related events</span></span>

<span data-ttu-id="a96f7-132">Wenn Sie die [erweiterte Suche verwenden](advanced-hunting-overview.md) möchten, um Ereignisse im Zusammenhang mit der ausgewählten Technik zu finden, wählen Sie Hunt for related events **aus.**</span><span class="sxs-lookup"><span data-stu-id="a96f7-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="a96f7-133">Dies führt zur erweiterten Suchseite mit einer Abfrage, um Ereignisse im Zusammenhang mit der Technik zu finden.</span><span class="sxs-lookup"><span data-stu-id="a96f7-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![Suche nach verwandten Ereignissen](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="a96f7-135">Beim Abfragen mithilfe der Schaltfläche **"Suche** nach verwandten Ereignissen" aus einem Seitenbereich Technik werden alle Ereignisse im Zusammenhang mit der identifizierten Technik angezeigt, die Technik selbst wird jedoch nicht in die Abfrageergebnisse ein.</span><span class="sxs-lookup"><span data-stu-id="a96f7-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="a96f7-136">Anpassen der Gerätezeitachse</span><span class="sxs-lookup"><span data-stu-id="a96f7-136">Customize your device timeline</span></span>

<span data-ttu-id="a96f7-137">Auf der oberen rechten Seite der Gerätezeitachse können Sie einen Datumsbereich auswählen, um die Anzahl der Ereignisse und Techniken auf der Zeitachse zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="a96f7-138">Sie können anpassen, welche Spalten verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-138">You can customize which columns to expose.</span></span> <span data-ttu-id="a96f7-139">Sie können auch nach gekennzeichneten Ereignissen nach Datentyp oder Ereignisgruppe filtern.</span><span class="sxs-lookup"><span data-stu-id="a96f7-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="a96f7-140">Spalten auswählen, die verfügbar gemacht werden sollen</span><span class="sxs-lookup"><span data-stu-id="a96f7-140">Choose columns to expose</span></span>
<span data-ttu-id="a96f7-141">Sie können auswählen, welche Spalten in der Zeitachse verfügbar gemacht werden sollen, indem Sie die **Schaltfläche Spalten auswählen** auswählen auswählen.</span><span class="sxs-lookup"><span data-stu-id="a96f7-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![Anpassen von Spalten](images/filter-customize-columns.png)

<span data-ttu-id="a96f7-143">Dort können Sie auswählen, welche Informationen enthalten sein sollten.</span><span class="sxs-lookup"><span data-stu-id="a96f7-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="a96f7-144">Filtern, um nur Techniken oder Ereignisse anzeigen zu können</span><span class="sxs-lookup"><span data-stu-id="a96f7-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="a96f7-145">Wenn Sie nur Ereignisse oder Techniken anzeigen möchten, wählen Sie **auf** der Gerätezeitachse Filter aus, und wählen Sie Den bevorzugten Datentyp aus, der angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a96f7-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![Screenshot "Filter"](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="a96f7-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a96f7-147">See also</span></span>
- [<span data-ttu-id="a96f7-148">Anzeigen und Organisieren der Geräteliste</span><span class="sxs-lookup"><span data-stu-id="a96f7-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="a96f7-149">Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen</span><span class="sxs-lookup"><span data-stu-id="a96f7-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
