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
description: Das Markieren von Dokumenten in einem Prüfdateisatz trägt dazu bei, unnötige Inhalte zu entfernen und relevante Inhalte in einem Advanced eDiscovery Fall zu identifizieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736274"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="66ca5-103">Markieren von Dokumenten in einem Prüfdateisatz in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="66ca5-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="66ca5-104">Das Organisieren von Inhalten in einem Prüfdateisatz ist wichtig, um verschiedene Workflows im eDiscovery-Prozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="66ca5-105">Dies umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="66ca5-105">This includes:</span></span>

- <span data-ttu-id="66ca5-106">Culling von unnötigen Inhalten</span><span class="sxs-lookup"><span data-stu-id="66ca5-106">Culling unnecessary content</span></span>

- <span data-ttu-id="66ca5-107">Identifizieren relevanter Inhalte</span><span class="sxs-lookup"><span data-stu-id="66ca5-107">Identifying relevant content</span></span>

- <span data-ttu-id="66ca5-108">Identifizieren von Inhalten, die von einem Experten oder Anwalt überprüft werden müssen</span><span class="sxs-lookup"><span data-stu-id="66ca5-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="66ca5-109">Wenn Experten, Anwälte oder andere Benutzer Inhalte in einem Prüfdateisatz überprüfen, können ihre Ansichten zu den Inhalten mithilfe von Tags erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="66ca5-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="66ca5-110">Wenn z. B. der Zweck darin besteht, unnötige Inhalte zu entfernen, kann ein Benutzer Dokumente mit einem Tag wie z. B. "nicht reaktionsfähig" markieren.</span><span class="sxs-lookup"><span data-stu-id="66ca5-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="66ca5-111">Nachdem Inhalte überprüft und markiert wurden, kann eine Prüfdateisatzsuche erstellt werden, um alle Inhalte auszuschließen, die als "nicht reaktionsfähig" gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="66ca5-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="66ca5-112">Dadurch werden die nicht reaktionsfähigen Inhalte aus den nächsten Schritten im eDiscovery-Workflow entfernt.</span><span class="sxs-lookup"><span data-stu-id="66ca5-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="66ca5-113">Der Tagging-Bereich in einem Prüfdateisatz kann für jeden Fall angepasst werden, sodass die Tags den beabsichtigten Überprüfungsworkflow für den Fall unterstützen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="66ca5-114">Der Bereich von Tags ist ein Advanced eDiscovery Fall.</span><span class="sxs-lookup"><span data-stu-id="66ca5-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="66ca5-115">Das bedeutet, dass ein Fall nur einen Satz von Tags enthalten kann, die Prüfer zum Markieren von Dokumenten mit Prüfdateisatz verwenden können.</span><span class="sxs-lookup"><span data-stu-id="66ca5-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="66ca5-116">Sie können keinen anderen Satz von Tags für die Verwendung in verschiedenen Prüfdateisätzen im selben Fall einrichten.</span><span class="sxs-lookup"><span data-stu-id="66ca5-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="66ca5-117">Tagtypen</span><span class="sxs-lookup"><span data-stu-id="66ca5-117">Tag types</span></span>

<span data-ttu-id="66ca5-118">Advanced eDiscovery bietet zwei Arten von Tags:</span><span class="sxs-lookup"><span data-stu-id="66ca5-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="66ca5-119">**Single Choice Tags:** Beschränkt Prüfer auf die Auswahl eines einzelnen Tags innerhalb einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="66ca5-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="66ca5-120">Diese Arten von Tags können nützlich sein, um sicherzustellen, dass Prüfer keine widersprüchlichen Tags wie "reaktionsfähig" und "nicht reaktionsfähig" auswählen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="66ca5-121">Einzelne Auswahltags werden als Optionsfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66ca5-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="66ca5-122">**Multiple Choice-Tags:** Rezensionen erlauben, mehrere Tags innerhalb einer Gruppe auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="66ca5-123">Diese Arten von Tags werden als Kontrollkästchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66ca5-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="66ca5-124">Tag-Struktur</span><span class="sxs-lookup"><span data-stu-id="66ca5-124">Tag structure</span></span>

<span data-ttu-id="66ca5-125">Zusätzlich zu den Tagtypen kann die Struktur der Organisation von Tags im Tag-Bereich verwendet werden, um das Tagging von Dokumenten intuitiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="66ca5-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="66ca5-126">Tags sind nach Abschnitten gruppiert.</span><span class="sxs-lookup"><span data-stu-id="66ca5-126">Tags are grouped by sections.</span></span> <span data-ttu-id="66ca5-127">Die Suche nach Prüfdateisatz unterstützt die Möglichkeit, nach Tag und Nach-Tag-Abschnitt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="66ca5-128">Dies bedeutet, dass Sie eine Prüfdateisatzsuche erstellen können, um Dokumente abzurufen, die mit einem beliebigen Tag in einem Abschnitt markiert sind.</span><span class="sxs-lookup"><span data-stu-id="66ca5-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![Tag-Abschnitte im Tag-Bereich](../media/TagTypes.png)

<span data-ttu-id="66ca5-130">Sie können Tags weiter organisieren, indem Sie sie in einem Abschnitt verschachteln.</span><span class="sxs-lookup"><span data-stu-id="66ca5-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="66ca5-131">Wenn beispielsweise privilegierte Inhalte identifiziert und markiert werden sollen, kann die Schachtelung verwendet werden, um deutlich zu machen, dass ein Bearbeiter ein Dokument als "Privileged" markieren und den Typ der Berechtigung auswählen kann, indem das entsprechende geschachtelte Tag überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="66ca5-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![Geschachtelte Tags in einem Tag-Abschnitt](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="66ca5-133">Erstellen von Tags</span><span class="sxs-lookup"><span data-stu-id="66ca5-133">Create tags</span></span>

<span data-ttu-id="66ca5-134">Bevor Sie Tags auf Dokumente im Prüfdateisatz anwenden, müssen Sie eine Tagstruktur erstellen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="66ca5-135">Öffnen Sie einen Prüfdateisatz, navigieren Sie zur Befehlsleiste, und wählen Sie **Tag nach Abfrage** aus.</span><span class="sxs-lookup"><span data-stu-id="66ca5-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="66ca5-136">Wählen Sie im Bereich "Tagging" die Option **"Tag verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="66ca5-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="66ca5-137">Wählen Sie **"Tag hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="66ca5-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="66ca5-138">Geben Sie einen Taggruppentitel und eine optionale Beschreibung ein, und klicken Sie dann auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="66ca5-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="66ca5-139">Wählen Sie das Dropdownmenü mit drei Punkten neben dem Taggruppentitel aus, und klicken Sie auf das **Kontrollkästchen "Hinzufügen"** oder **auf die Schaltfläche "Option hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="66ca5-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="66ca5-140">Geben Sie einen Namen und eine Beschreibung für das Kontrollkästchen oder die Optionsschaltfläche ein.</span><span class="sxs-lookup"><span data-stu-id="66ca5-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="66ca5-141">Wiederholen Sie diesen Vorgang, um neue Tagabschnitte, Tagoptionen und Kontrollkästchen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![Konfigurieren der Tagstruktur](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="66ca5-143">Anwenden von Tags</span><span class="sxs-lookup"><span data-stu-id="66ca5-143">Applying tags</span></span>

<span data-ttu-id="66ca5-144">Wenn die Tagstruktur vorhanden ist, können Prüfer Tags auf Dokumente in einem Prüfdateisatz anwenden.</span><span class="sxs-lookup"><span data-stu-id="66ca5-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="66ca5-145">Es gibt zwei verschiedene Möglichkeiten zum Anwenden von Tags:</span><span class="sxs-lookup"><span data-stu-id="66ca5-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="66ca5-146">Tag-Dateien</span><span class="sxs-lookup"><span data-stu-id="66ca5-146">Tag files</span></span>

- <span data-ttu-id="66ca5-147">Tag nach Abfrage</span><span class="sxs-lookup"><span data-stu-id="66ca5-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="66ca5-148">Tag-Dateien</span><span class="sxs-lookup"><span data-stu-id="66ca5-148">Tag files</span></span>

<span data-ttu-id="66ca5-149">Unabhängig davon, ob Sie ein einzelnes Element oder mehrere Elemente in einem Prüfdateisatz auswählen, können Sie Tags auf ihre Auswahl anwenden, indem Sie auf der Befehlsleiste auf **"Tag"-Dateien** klicken.</span><span class="sxs-lookup"><span data-stu-id="66ca5-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="66ca5-150">Im Tagging-Bereich können Sie ein Tag auswählen, das automatisch auf die ausgewählten Dokumente angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="66ca5-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![Markieren ausgewählter Dateien](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="66ca5-152">Tags werden nur auf ausgewählte Elemente in der Liste der Elemente angewendet.</span><span class="sxs-lookup"><span data-stu-id="66ca5-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="66ca5-153">Tag nach Abfrage</span><span class="sxs-lookup"><span data-stu-id="66ca5-153">Tag by query</span></span>

<span data-ttu-id="66ca5-154">Mit tagging by query können Sie Tags auf alle Elemente anwenden, die von einer Filterabfrage angezeigt werden, die derzeit im Prüfdateisatz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="66ca5-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="66ca5-155">Heben Sie die Auswahl aller Elemente im Prüfdateisatz auf, wechseln Sie zur Befehlsleiste, und wählen Sie **Tag nach Abfrage** aus.</span><span class="sxs-lookup"><span data-stu-id="66ca5-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="66ca5-156">Wählen Sie im Tagging-Bereich das Tag aus, das Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="66ca5-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="66ca5-157">Unter der Dropdownliste **"Tagauswahl"** gibt es drei Optionen, die festlegen, auf welche Elemente das Tag angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="66ca5-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="66ca5-158">**Elemente, die mit der angewendeten Abfrage übereinstimmen:** Wendet Tags auf bestimmte Elemente an, die den Filterabfragebedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="66ca5-159">**Zugeordnete Familienelemente einschließen:** Wendet Tags auf bestimmte Elemente an, die den Filterabfragebedingungen und den zugehörigen Familienelementen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="66ca5-160">*Familienelemente* sind Elemente, die denselben FamilyId-Metadatenwert verwenden.</span><span class="sxs-lookup"><span data-stu-id="66ca5-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="66ca5-161">**Zugeordnete Unterhaltungselemente einschließen:** Wendet Tags auf Elemente an, die den Filterabfragebedingungen und den zugehörigen Unterhaltungselementen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="66ca5-162">*Unterhaltungselemente* sind Elemente, die dieselben ConversationId-Metadatenwerte verwenden.</span><span class="sxs-lookup"><span data-stu-id="66ca5-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![Tagauswahl](../media/TagByQuery2.png)

4. <span data-ttu-id="66ca5-164">Klicken Sie auf **"Taggingauftrag starten",** um den Taggingauftrag auszulösen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="66ca5-165">Tagfilter</span><span class="sxs-lookup"><span data-stu-id="66ca5-165">Tag filter</span></span>

<span data-ttu-id="66ca5-166">Verwenden Sie den Tagfilter im Prüfdateisatz, um Elemente basierend auf der Markierung eines Elements schnell zu finden oder aus den Abfrageergebnissen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="66ca5-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="66ca5-167">Wählen Sie **Filter** aus, um den Filterbereich zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="66ca5-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="66ca5-168">Auswählen und Erweitern **von Elementeigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="66ca5-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="66ca5-169">Scrollen Sie nach unten, um den Filter **"Tag"** zu suchen, aktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **"Fertig".**</span><span class="sxs-lookup"><span data-stu-id="66ca5-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="66ca5-170">Führen Sie einen der folgenden Schritte aus, um Elemente mit einem bestimmten Tag in eine Abfrage einzuschließen oder auszuschließen:</span><span class="sxs-lookup"><span data-stu-id="66ca5-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="66ca5-171">**Elemente einschließen:** Wählen Sie den Tagwert aus, und wählen Sie im Dropdownmenü **"Gleich"** aus.</span><span class="sxs-lookup"><span data-stu-id="66ca5-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="66ca5-172">Oder</span><span class="sxs-lookup"><span data-stu-id="66ca5-172">Or</span></span>

   - <span data-ttu-id="66ca5-173">**Elemente ausschließen:** Wählen Sie den Tagwert aus, und wählen Sie **"Gleich" im** Dropdownmenü aus.</span><span class="sxs-lookup"><span data-stu-id="66ca5-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![Ausschließen von Elementen durch Tagfilter](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="66ca5-175">Aktualisieren Sie die Seite unbedingt, um sicherzustellen, dass der Tagfilter die neuesten Änderungen an der Tagstruktur anzeigt.</span><span class="sxs-lookup"><span data-stu-id="66ca5-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
