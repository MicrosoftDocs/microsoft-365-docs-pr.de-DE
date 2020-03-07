---
title: Markieren von Dokumenten in einem Prüfdateisatz
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
description: ''
ms.openlocfilehash: 1c0eaed5d5971a55e4e9851bac3133bcd961eb36
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557695"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="8ce29-102">Markieren von Dokumenten in einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="8ce29-102">Tag documents in a review set</span></span>

<span data-ttu-id="8ce29-103">Das Organisieren von Inhalten in einem Überprüfungs Satzes ist wichtig, um verschiedene Workflows im eDiscovery-Prozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="8ce29-104">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8ce29-104">This includes:</span></span>

- <span data-ttu-id="8ce29-105">Ausmerzen unnötiger Inhalte</span><span class="sxs-lookup"><span data-stu-id="8ce29-105">Culling unnecessary content</span></span>

- <span data-ttu-id="8ce29-106">Identifizieren relevanter Inhalte</span><span class="sxs-lookup"><span data-stu-id="8ce29-106">Identifying relevant content</span></span>
 
- <span data-ttu-id="8ce29-107">Identifizieren von Inhalten, die von einem Experten oder einem Anwalt überprüft werden müssen</span><span class="sxs-lookup"><span data-stu-id="8ce29-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="8ce29-108">Wenn Experten, Anwälte oder andere Benutzer Inhalte in einem Überprüfungs Satzes überprüfen, können Ihre Meinungen im Zusammenhang mit den Inhalten mithilfe von Tags erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="8ce29-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="8ce29-109">Wenn beispielsweise unnötige Inhalte ausgemerzt werden sollen, kann ein Benutzer Dokumente mit einem Tag wie "nicht reagierende" markieren.</span><span class="sxs-lookup"><span data-stu-id="8ce29-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="8ce29-110">Nachdem der Inhalt überprüft und markiert wurde, kann eine Überprüfungs Sätze-Suche erstellt werden, um alle Inhalte auszuschließen, die als "nicht ansprechbar" gekennzeichnet sind, wodurch dieser Inhalt nicht aus den nächsten Schritten im eDiscovery-Workflow entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="8ce29-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="8ce29-111">Der Tag-Bereich kann für jeden Fall angepasst werden, sodass die Tags den beabsichtigten Überprüfungsworkflow unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="8ce29-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="8ce29-112">Tag-Typen</span><span class="sxs-lookup"><span data-stu-id="8ce29-112">Tag types</span></span>

<span data-ttu-id="8ce29-113">Advanced eDiscovery bietet zwei Typen von Tags:</span><span class="sxs-lookup"><span data-stu-id="8ce29-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="8ce29-114">**Einzelne Tags** – schränkt Benutzer ein, um ein einzelnes Tag in einer Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="8ce29-115">Dies kann hilfreich sein, um sicherzustellen, dass Benutzer nicht in Konflikt stehende Tags wie "reagieren" und "nicht reagierende" auswählen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> <span data-ttu-id="8ce29-116">Diese werden als Optionsfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ce29-116">These will appear as radio buttons.</span></span>

- <span data-ttu-id="8ce29-117">**Mehrfachauswahl-Tags** – Benutzer können mehrere Tags in einer Gruppe auswählen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-117">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="8ce29-118">Diese werden als Kontrollkästchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ce29-118">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="8ce29-119">Tag-Struktur</span><span class="sxs-lookup"><span data-stu-id="8ce29-119">Tag structure</span></span>

<span data-ttu-id="8ce29-120">Zusätzlich zu den Tag-Typen kann die Struktur, wie Tags im Tag-Panel organisiert werden, verwendet werden, um das Markieren von Dokumenten intuitiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="8ce29-120">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="8ce29-121">Tags werden nach Abschnitten gruppiert.</span><span class="sxs-lookup"><span data-stu-id="8ce29-121">Tags are grouped by sections.</span></span> <span data-ttu-id="8ce29-122">Überprüfen die Option "Suche festlegen" unterstützt die Suche nach Tag und Tag.</span><span class="sxs-lookup"><span data-stu-id="8ce29-122">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="8ce29-123">Dies bedeutet, dass Sie eine Überprüfungs Sätze-Suche erstellen können, um Dokumente mit einem beliebigen Tag in einem Abschnitt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-123">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Markieren von Abschnitten im Tag-Panel](../media/Tagtypes.png)

<span data-ttu-id="8ce29-125">Tags können weiter organisiert werden, indem Sie in einem Abschnitt verschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="8ce29-125">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="8ce29-126">Wenn beispielsweise privilegierte Inhalte identifiziert und markiert werden sollen, kann durch Verschachtelung deutlich gemacht werden, dass ein Benutzer ein Dokument als "privilegiert" markieren und den gewünschten Berechtigungstyp auswählen kann, indem das entsprechende geschachtelte Tag überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="8ce29-126">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![Geschachtelte Tags innerhalb eines Tag-Abschnitts](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="8ce29-128">Anwenden von Tags</span><span class="sxs-lookup"><span data-stu-id="8ce29-128">Applying tags</span></span>

<span data-ttu-id="8ce29-129">Es gibt verschiedene Möglichkeiten, ein Tag auf Inhalte anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="8ce29-129">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="8ce29-130">Markieren eines einzelnen Dokuments</span><span class="sxs-lookup"><span data-stu-id="8ce29-130">Tagging a single document</span></span>

<span data-ttu-id="8ce29-131">Wenn Sie ein Dokument in einem Überprüfungs Satzes anzeigen, können Sie die Tags anzeigen, die eine Überprüfung verwenden kann, indem Sie auf **Markierungsbereich**klicken.</span><span class="sxs-lookup"><span data-stu-id="8ce29-131">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Klicken Sie auf Tag Panel, um das Tag-Panel anzuzeigen](../media/Singledoctag.png)

<span data-ttu-id="8ce29-133">Auf diese Weise können Sie Tags auf das Dokument anwenden, das im Viewer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ce29-133">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="8ce29-134">Massen Markierung</span><span class="sxs-lookup"><span data-stu-id="8ce29-134">Bulk tagging</span></span>

<span data-ttu-id="8ce29-135">Das Massen-Tagging kann durch Auswählen mehrerer Dateien im Ergebnisraster und anschließendes Verwenden der Tags im **taggingbereich** wie das Markieren einzelner Dokumente erfolgen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-135">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="8ce29-136">Das Massen-UN-Tagging kann durch zweimaliges Markieren von Tags erfolgen. mit dem ersten Klick wird das Tag angewendet, und die zweite Auswahl stellt sicher, dass das Tag für alle ausgewählten Dateien gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="8ce29-136">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Ein Screenshot einer Handy Beschreibung, die automatisch generiert wird](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="8ce29-138">Bei der Massen Markierung wird im Markierungsbereich die Anzahl der Dateien angezeigt, die für jedes Tag im Bereich markiert sind.</span><span class="sxs-lookup"><span data-stu-id="8ce29-138">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="8ce29-139">Tagging in anderen Überprüfungs Bereichen</span><span class="sxs-lookup"><span data-stu-id="8ce29-139">Tagging in other review panels</span></span>

<span data-ttu-id="8ce29-140">Bei der Überprüfung von Dokumenten können Sie die anderen Überprüfungs Bereiche verwenden, um andere Merkmale von Dokumenten im Ergebnisraster zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-140">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="8ce29-141">Dies umfasst das Überprüfen anderer verwandter Dokumente, e-Mail-Threads, nahe Duplikate und Hash Duplikate.</span><span class="sxs-lookup"><span data-stu-id="8ce29-141">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="8ce29-142">Wenn Sie beispielsweise Verwandte Dokumente (mithilfe des Bereichs " **Dokument Familien** Überprüfung") überprüfen, können Sie die Überprüfungszeit erheblich verringern, indem Sie zugehörige Dokumente in Massen markieren.</span><span class="sxs-lookup"><span data-stu-id="8ce29-142">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="8ce29-143">Wenn beispielsweise eine e-Mail-Nachricht mehrere Anlagen enthält und Sie sicherstellen möchten, dass die gesamte Familie einheitlich markiert ist.</span><span class="sxs-lookup"><span data-stu-id="8ce29-143">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="8ce29-144">Hier erfahren Sie, wie Sie den **Markierungsbereich** bei Verwendung des **Dokument Familien** Überprüfungs Bereichs anzeigen:</span><span class="sxs-lookup"><span data-stu-id="8ce29-144">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="8ce29-145">Wenn der Überprüfungsbereich für ein ausgewähltes Dokument geöffnet ist (beispielsweise wird die Liste der verwandten Inhalte im **Dokument Familien** Überprüfungsbereich angezeigt wird, klicken Sie im Dokument Familien Überprüfungsbereich auf **Dokumente markieren** .</span><span class="sxs-lookup"><span data-stu-id="8ce29-145">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="8ce29-146">Der Markierungsbereich wird als Popupfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ce29-146">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="8ce29-147">Wählen Sie ein oder mehrere Tags aus, um das ausgewählte Dokument anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="8ce29-147">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="8ce29-148">Zum Markieren aller Dokumente wählen Sie im Bedienfeld " **Dokument Familie** " alle Dokumente aus, klicken Sie auf **Tag-Dokumente**, und wählen Sie dann die Tags aus, die auf die gesamte Dokumenten Familie angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8ce29-148">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Screenshot einer sozialen Medien Bereitstellungs Beschreibung, die automatisch generiert wird](../media/Relatedtag.png)
