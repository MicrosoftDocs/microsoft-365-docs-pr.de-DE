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
description: Das Markieren von Dokumenten in einem Überprüfungssatz hilft, unnötige Inhalte zu entfernen und relevante Inhalte in einem Advanced eDiscovery identifizieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285281"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="216a0-103">Markieren von Dokumenten in einem Überprüfungssatz in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="216a0-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="216a0-104">Das Organisieren von Inhalten in einem Überprüfungssatz ist wichtig, um verschiedene Workflows im eDiscovery-Prozess abschließen zu können.</span><span class="sxs-lookup"><span data-stu-id="216a0-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="216a0-105">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="216a0-105">This includes:</span></span>

- <span data-ttu-id="216a0-106">Culling unnecessary content</span><span class="sxs-lookup"><span data-stu-id="216a0-106">Culling unnecessary content</span></span>

- <span data-ttu-id="216a0-107">Identifizieren relevanter Inhalte</span><span class="sxs-lookup"><span data-stu-id="216a0-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="216a0-108">Identifizieren von Inhalten, die von einem Experten oder einem Anwalt überprüft werden müssen</span><span class="sxs-lookup"><span data-stu-id="216a0-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="216a0-109">Wenn Experten, Anwälte oder andere Benutzer Inhalte in einem Bewertungssatz überprüfen, können ihre Ansichten zu den Inhalten mithilfe von Tags erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="216a0-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="216a0-110">Wenn beispielsweise die Absicht besteht, nicht benötigte Inhalte zu markieren, kann ein Benutzer Dokumente mit einem Tag markieren, z. B. "nicht reaktionsfähig".</span><span class="sxs-lookup"><span data-stu-id="216a0-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="216a0-111">Nachdem Inhalte überprüft und markiert wurden, kann eine Überprüfungssatzsuche erstellt werden, um alle Inhalte auszuschließen, die als "nicht reaktionsfähig" gekennzeichnet sind, wodurch dieser Inhalt aus den nächsten Schritten im eDiscovery-Workflow entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="216a0-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="216a0-112">Der Tagbereich kann für jeden Fall angepasst werden, damit die Tags den beabsichtigten Überprüfungsworkflow unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="216a0-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="216a0-113">Tagtypen</span><span class="sxs-lookup"><span data-stu-id="216a0-113">Tag types</span></span>

<span data-ttu-id="216a0-114">Advanced eDiscovery bietet zwei Arten von Tags:</span><span class="sxs-lookup"><span data-stu-id="216a0-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="216a0-115">**Tags mit einer einzelnen** Auswahl – Schränkt Benutzer ein, ein einzelnes Tag innerhalb einer Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="216a0-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="216a0-116">Dies kann hilfreich sein, um sicherzustellen, dass Benutzer keine in Konflikt enden Tags auswählen, z. B. "reaktionsfähig" und "nicht reaktionsfähig".</span><span class="sxs-lookup"><span data-stu-id="216a0-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="216a0-117">Diese werden als Optionsfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="216a0-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="216a0-118">**Tags mit mehreren** Auswahlmöglichkeiten : Benutzern die Auswahl mehrerer Tags innerhalb einer Gruppe ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="216a0-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="216a0-119">Diese werden als Kontrollkästchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="216a0-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="216a0-120">Tagstruktur</span><span class="sxs-lookup"><span data-stu-id="216a0-120">Tag structure</span></span>

<span data-ttu-id="216a0-121">Zusätzlich zu den Tagtypen kann die Struktur der Tags im Tagbereich verwendet werden, um das Tagging von Dokumenten intuitiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="216a0-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="216a0-122">Tags werden nach Abschnitten unterteilt.</span><span class="sxs-lookup"><span data-stu-id="216a0-122">Tags are grouped by sections.</span></span> <span data-ttu-id="216a0-123">Die Überprüfungssatzsuche unterstützt die Möglichkeit, nach Tag und Nach-Tag-Abschnitt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="216a0-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="216a0-124">Dies bedeutet, dass Sie eine Überprüfungssatzsuche erstellen können, um Dokumente abzurufen, die mit einem beliebigen Tag in einem Abschnitt markiert sind.</span><span class="sxs-lookup"><span data-stu-id="216a0-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Markierungsabschnitte im Tagbereich](../media/Tagtypes.png)

<span data-ttu-id="216a0-126">Tags können weiter organisiert werden, indem sie in einem Abschnitt geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="216a0-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="216a0-127">Wenn beispielsweise die Absicht besteht, privilegierte Inhalte zu identifizieren und zu kennzeichnen, kann mit der Verschachtelung klar gemacht werden, dass ein Benutzer ein Dokument als "Privileged" kennzeichnen und den Berechtigungstyp auswählen kann, indem das entsprechende geschachtelte Tag überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="216a0-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Geschachtelte Tags in einem Tag-Abschnitt](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="216a0-129">Anwenden von Tags</span><span class="sxs-lookup"><span data-stu-id="216a0-129">Applying tags</span></span>

<span data-ttu-id="216a0-130">Es gibt mehrere Möglichkeiten, ein Tag auf Inhalte anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="216a0-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="216a0-131">Taggen eines einzelnen Dokuments</span><span class="sxs-lookup"><span data-stu-id="216a0-131">Tagging a single document</span></span>

<span data-ttu-id="216a0-132">Wenn Sie ein Dokument in einem Überprüfungssatz anzeigen, können Sie die Tags anzeigen, die eine Überprüfung verwenden kann, indem Sie auf **Tagging-Bereich klicken.**</span><span class="sxs-lookup"><span data-stu-id="216a0-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![Klicken Sie auf Tag-Bereich, um den Tagbereich anzeigen zu können.](../media/Singledoctag.png)

<span data-ttu-id="216a0-134">Auf diese Weise können Sie Tags auf das im Viewer angezeigte Dokument anwenden.</span><span class="sxs-lookup"><span data-stu-id="216a0-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="216a0-135">Massentagging</span><span class="sxs-lookup"><span data-stu-id="216a0-135">Bulk tagging</span></span>

<span data-ttu-id="216a0-136">Massentagging kann durch Auswählen mehrerer Dateien im Ergebnisraster und anschließendes Verwenden der Tags im **Tagging-Bereich** wie das Markieren einzelner Dokumente durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="216a0-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="216a0-137">Das Massenentfing kann durch zweimalige Auswahl von Tags durchgeführt werden. Der erste Klick wird das Tag anwenden, und die zweite Auswahl stellt sicher, dass das Tag für alle ausgewählten Dateien gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="216a0-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![Screenshot eines automatisch generierten Mobiltelefons Beschreibung](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="216a0-139">Beim Massentaging zeigt der Taggingbereich eine Anzahl von Dateien an, die für jedes Tag im Bereich markiert sind.</span><span class="sxs-lookup"><span data-stu-id="216a0-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="216a0-140">Tagging in anderen Überprüfungspanels</span><span class="sxs-lookup"><span data-stu-id="216a0-140">Tagging in other review panels</span></span>

<span data-ttu-id="216a0-141">Beim Überprüfen von Dokumenten können Sie die anderen Überprüfungspanels verwenden, um andere Merkmale von Dokumenten im Ergebnisraster zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="216a0-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="216a0-142">Dies umfasst das Überprüfen anderer verwandter Dokumente, E-Mail-Threads, beinahe doppelter Objekte und Hashduplizierter.</span><span class="sxs-lookup"><span data-stu-id="216a0-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="216a0-143">Wenn Sie z. B. verwandte Dokumente  überprüfen (mithilfe des Überprüfungspanels für die Dokumentfamilie), können Sie die Überprüfungszeit erheblich reduzieren, indem Sie verwandte Dokumente in Massen taggen.</span><span class="sxs-lookup"><span data-stu-id="216a0-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="216a0-144">Wenn beispielsweise eine E-Mail-Nachricht mehrere Anlagen enthält und Sie sicherstellen möchten, dass die gesamte Familie konsistent markiert ist.</span><span class="sxs-lookup"><span data-stu-id="216a0-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="216a0-145">Hier erfahren Sie beispielsweise, wie Sie den **Tagging-Bereich** anzeigen, wenn Sie den Überprüfungsbereich für die **Dokumentfamilie** verwenden:</span><span class="sxs-lookup"><span data-stu-id="216a0-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="216a0-146">Wenn der Überprüfungsbereich für ein ausgewähltes Dokument geöffnet ist (z. B. wenn die Liste der zugehörigen Inhalte im Überprüfungsfenster Dokumentfamilie angezeigt wird, klicken Sie im Überprüfungsbereich Dokumentfamilie auf **Dokumente** markieren. </span><span class="sxs-lookup"><span data-stu-id="216a0-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="216a0-147">Der Taggingbereich wird als Popupfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="216a0-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="216a0-148">Wählen Sie ein oder mehrere Tags aus, um das ausgewählte Dokument anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="216a0-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="216a0-149">Um alle Dokumente zu kennzeichnen,  wählen Sie alle Dokumente im Bereich Dokumentfamilie aus, klicken Sie auf **Dokumente markieren,** und wählen Sie dann die Tags aus, die auf die gesamte Dokumentfamilie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="216a0-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![Screenshot eines automatisch generierten Social Media-Beitrags Beschreibung](../media/Relatedtag.png)
