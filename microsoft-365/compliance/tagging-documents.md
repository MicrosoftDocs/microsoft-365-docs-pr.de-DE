---
title: Markieren von Dokumenten in einem Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Das Markieren von Dokumenten in einer Überprüfungsgruppe hilft, unnötigen Inhalt zu entfernen und relevante Inhalte in einem erweiterten eDiscovery-Fall zu identifizieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285281"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="b7838-103">Markieren von Dokumenten in einer Überprüfungsgruppe in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b7838-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="b7838-104">Das Organisieren von Inhalten in einem Überprüfungs Satzes ist wichtig, um verschiedene Workflows im eDiscovery-Prozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b7838-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="b7838-105">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b7838-105">This includes:</span></span>

- <span data-ttu-id="b7838-106">Ausmerzen unnötiger Inhalte</span><span class="sxs-lookup"><span data-stu-id="b7838-106">Culling unnecessary content</span></span>

- <span data-ttu-id="b7838-107">Identifizieren relevanter Inhalte</span><span class="sxs-lookup"><span data-stu-id="b7838-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="b7838-108">Identifizieren von Inhalten, die von einem Experten oder einem Anwalt überprüft werden müssen</span><span class="sxs-lookup"><span data-stu-id="b7838-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="b7838-109">Wenn Experten, Anwälte oder andere Benutzer Inhalte in einem Überprüfungs Satzes überprüfen, können Ihre Meinungen im Zusammenhang mit den Inhalten mithilfe von Tags erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="b7838-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="b7838-110">Wenn beispielsweise unnötige Inhalte ausgemerzt werden sollen, kann ein Benutzer Dokumente mit einem Tag wie "nicht reagierende" markieren.</span><span class="sxs-lookup"><span data-stu-id="b7838-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="b7838-111">Nachdem der Inhalt überprüft und markiert wurde, kann eine Überprüfungs Sätze-Suche erstellt werden, um alle Inhalte auszuschließen, die als "nicht ansprechbar" gekennzeichnet sind, wodurch dieser Inhalt nicht aus den nächsten Schritten im eDiscovery-Workflow entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b7838-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="b7838-112">Der Tag-Bereich kann für jeden Fall angepasst werden, sodass die Tags den beabsichtigten Überprüfungsworkflow unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="b7838-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="b7838-113">Tag-Typen</span><span class="sxs-lookup"><span data-stu-id="b7838-113">Tag types</span></span>

<span data-ttu-id="b7838-114">Advanced eDiscovery bietet zwei Typen von Tags:</span><span class="sxs-lookup"><span data-stu-id="b7838-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="b7838-115">**Einzelne Tags** – schränkt Benutzer ein, um ein einzelnes Tag in einer Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b7838-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="b7838-116">Dies kann hilfreich sein, um sicherzustellen, dass Benutzer nicht in Konflikt stehende Tags wie "reagieren" und "nicht reagierende" auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7838-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="b7838-117">Diese werden als Optionsfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7838-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="b7838-118">**Mehrfachauswahl-Tags** – Benutzer können mehrere Tags in einer Gruppe auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7838-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="b7838-119">Diese werden als Kontrollkästchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7838-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="b7838-120">Tag-Struktur</span><span class="sxs-lookup"><span data-stu-id="b7838-120">Tag structure</span></span>

<span data-ttu-id="b7838-121">Zusätzlich zu den Tag-Typen kann die Struktur, wie Tags im Tag-Panel organisiert werden, verwendet werden, um das Markieren von Dokumenten intuitiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="b7838-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="b7838-122">Tags werden nach Abschnitten gruppiert.</span><span class="sxs-lookup"><span data-stu-id="b7838-122">Tags are grouped by sections.</span></span> <span data-ttu-id="b7838-123">Überprüfen die Option "Suche festlegen" unterstützt die Suche nach Tag und Tag.</span><span class="sxs-lookup"><span data-stu-id="b7838-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="b7838-124">Dies bedeutet, dass Sie eine Überprüfungs Sätze-Suche erstellen können, um Dokumente mit einem beliebigen Tag in einem Abschnitt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b7838-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Markieren von Abschnitten im Tag-Panel](../media/Tagtypes.png)

<span data-ttu-id="b7838-126">Tags können weiter organisiert werden, indem Sie in einem Abschnitt verschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="b7838-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="b7838-127">Wenn beispielsweise privilegierte Inhalte identifiziert und markiert werden sollen, kann durch Verschachtelung deutlich gemacht werden, dass ein Benutzer ein Dokument als "privilegiert" markieren und den gewünschten Berechtigungstyp auswählen kann, indem das entsprechende geschachtelte Tag überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="b7838-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Geschachtelte Tags innerhalb eines Tag-Abschnitts](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="b7838-129">Anwenden von Tags</span><span class="sxs-lookup"><span data-stu-id="b7838-129">Applying tags</span></span>

<span data-ttu-id="b7838-130">Es gibt verschiedene Möglichkeiten, ein Tag auf Inhalte anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b7838-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="b7838-131">Markieren eines einzelnen Dokuments</span><span class="sxs-lookup"><span data-stu-id="b7838-131">Tagging a single document</span></span>

<span data-ttu-id="b7838-132">Wenn Sie ein Dokument in einem Überprüfungs Satzes anzeigen, können Sie die Tags anzeigen, die eine Überprüfung verwenden kann, indem Sie auf **Markierungsbereich**klicken.</span><span class="sxs-lookup"><span data-stu-id="b7838-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Klicken Sie auf Tag Panel, um das Tag-Panel anzuzeigen](../media/Singledoctag.png)

<span data-ttu-id="b7838-134">Auf diese Weise können Sie Tags auf das im Viewer angezeigte Dokument anwenden.</span><span class="sxs-lookup"><span data-stu-id="b7838-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="b7838-135">Massen Markierung</span><span class="sxs-lookup"><span data-stu-id="b7838-135">Bulk tagging</span></span>

<span data-ttu-id="b7838-136">Das Massen-Tagging kann durch Auswählen mehrerer Dateien im Ergebnisraster und anschließendes Verwenden der Tags im **taggingbereich** wie das Markieren einzelner Dokumente erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b7838-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="b7838-137">Das Massen-UN-Tagging kann durch zweimaliges Markieren von Tags erfolgen. mit dem ersten Klick wird das Tag angewendet, und die zweite Auswahl stellt sicher, dass das Tag für alle ausgewählten Dateien gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b7838-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Ein Screenshot einer Handy Beschreibung, die automatisch generiert wird](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="b7838-139">Bei der Massen Markierung wird im Markierungsbereich die Anzahl der Dateien angezeigt, die für jedes Tag im Bereich markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b7838-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="b7838-140">Tagging in anderen Überprüfungs Bereichen</span><span class="sxs-lookup"><span data-stu-id="b7838-140">Tagging in other review panels</span></span>

<span data-ttu-id="b7838-141">Bei der Überprüfung von Dokumenten können Sie die anderen Überprüfungs Bereiche verwenden, um andere Merkmale von Dokumenten im Ergebnisraster zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b7838-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="b7838-142">Dies umfasst das Überprüfen anderer verwandter Dokumente, e-Mail-Threads, nahe Duplikate und Hash Duplikate.</span><span class="sxs-lookup"><span data-stu-id="b7838-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="b7838-143">Wenn Sie beispielsweise Verwandte Dokumente (mithilfe des Bereichs " **Dokument Familien** Überprüfung") überprüfen, können Sie die Überprüfungszeit erheblich verringern, indem Sie zugehörige Dokumente in Massen markieren.</span><span class="sxs-lookup"><span data-stu-id="b7838-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="b7838-144">Wenn beispielsweise eine e-Mail-Nachricht mehrere Anlagen enthält und Sie sicherstellen möchten, dass die gesamte Familie einheitlich markiert ist.</span><span class="sxs-lookup"><span data-stu-id="b7838-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="b7838-145">Hier erfahren Sie, wie Sie den **Markierungsbereich** bei Verwendung des **Dokument Familien** Überprüfungs Bereichs anzeigen:</span><span class="sxs-lookup"><span data-stu-id="b7838-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="b7838-146">Wenn der Überprüfungsbereich für ein ausgewähltes Dokument geöffnet ist (beispielsweise wird die Liste der verwandten Inhalte im **Dokument Familien** Überprüfungsbereich angezeigt wird, klicken Sie im Dokument Familien Überprüfungsbereich auf **Dokumente markieren** .</span><span class="sxs-lookup"><span data-stu-id="b7838-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="b7838-147">Der Markierungsbereich wird als Popupfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7838-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="b7838-148">Wählen Sie ein oder mehrere Tags aus, um das ausgewählte Dokument anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b7838-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="b7838-149">Zum Markieren aller Dokumente wählen Sie im Bedienfeld " **Dokument Familie** " alle Dokumente aus, klicken Sie auf **Tag-Dokumente**, und wählen Sie dann die Tags aus, die auf die gesamte Dokumenten Familie angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b7838-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Screenshot einer sozialen Medien Bereitstellungs Beschreibung, die automatisch generiert wird](../media/Relatedtag.png)
