---
title: Überprüfen von Unterhaltungen in Advanced eDiscovery
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
ms.assetid: ''
description: Erfahren Sie mehr über das Unterhaltungsrekonstruktionsfeature in Advanced eDiscovery (unterhaltungsthreading) zum Rekonstruieren, Überprüfen und Exportieren von Chatunterhaltungen in Microsoft Teams und Yammer Gruppen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838304"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="61cee-103">Unterhaltungsthreading in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="61cee-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="61cee-104">Instant Messaging ist eine bequeme Möglichkeit, Fragen zu stellen, Ideen auszutauschen oder schnell über große Zielgruppen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="61cee-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="61cee-105">Da Instant Messaging-Plattformen wie Microsoft Teams und Yammer-Gruppen zum Kern der Zusammenarbeit in Unternehmen werden, müssen Organisationen bewerten, wie ihr eDiscovery-Workflow diese neuen Formen der Kommunikation und Zusammenarbeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="61cee-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="61cee-106">Das Feature Unterhaltungsrekonstruktion in Advanced eDiscovery soll Ihnen dabei helfen, kontextbezogene Inhalte zu identifizieren und unterschiedliche Unterhaltungsansichten zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="61cee-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="61cee-107">Mit dieser Funktion können Sie vollständige Chatunterhaltungen (auch Threadunterhaltungen *genannt)* effizient und schnell überprüfen, die auf Plattformen wie Microsoft Teams generiert werden.</span><span class="sxs-lookup"><span data-stu-id="61cee-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="61cee-108">Mit der Unterhaltungsrekonstruktion können Sie integrierte Funktionen zum Rekonstruieren, Überprüfen und Exportieren von Threadunterhaltungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="61cee-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="61cee-109">Verwenden Sie Advanced eDiscovery Conversation Reconstruction für:</span><span class="sxs-lookup"><span data-stu-id="61cee-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="61cee-110">Bewahren Sie eindeutige Metadaten auf Nachrichtenebene für alle Nachrichten in einer Unterhaltung auf.</span><span class="sxs-lookup"><span data-stu-id="61cee-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="61cee-111">Sammeln von Kontextnachrichten rund um Ihre Suchergebnisse.</span><span class="sxs-lookup"><span data-stu-id="61cee-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="61cee-112">Überprüfen, Kommentieren und Redact-Threadunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="61cee-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="61cee-113">Exportieren einzelner Nachrichten oder Threadunterhaltungen</span><span class="sxs-lookup"><span data-stu-id="61cee-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="61cee-114">Terminologie</span><span class="sxs-lookup"><span data-stu-id="61cee-114">Terminology</span></span>

<span data-ttu-id="61cee-115">Im Folgenden finden Sie einige Definitionen, mit deren Hilfe Sie mit der Unterhaltungsrekonstruktion beginnen können.</span><span class="sxs-lookup"><span data-stu-id="61cee-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="61cee-116">**Nachrichten:** Stellen Sie die kleinste Einheit einer Unterhaltung dar.</span><span class="sxs-lookup"><span data-stu-id="61cee-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="61cee-117">Nachrichten können in Größe, Struktur und Metadaten variieren.</span><span class="sxs-lookup"><span data-stu-id="61cee-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="61cee-118">**Unterhaltung:** Stellt eine Gruppierung einer oder mehreren Nachrichten dar.</span><span class="sxs-lookup"><span data-stu-id="61cee-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="61cee-119">In verschiedenen Anwendungen können Unterhaltungen auf unterschiedliche Weise dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="61cee-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="61cee-120">In einigen Anwendungen gibt es eine explizite Aktion, die aus der Antwort auf eine vorhandene Nachricht resultiert.</span><span class="sxs-lookup"><span data-stu-id="61cee-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="61cee-121">Unterhaltungen werden explizit als Ergebnis dieser Benutzeraktion gebildet.</span><span class="sxs-lookup"><span data-stu-id="61cee-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="61cee-122">Hier finden Sie beispielsweise einen Screenshot einer Kanal unterhaltung in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="61cee-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams Channel Conversation](../media/threadedchat.png)

   <span data-ttu-id="61cee-124">In anderen Apps (z. B. 1xN-Chatnachrichten in Teams) gibt es keine formale Antwortkette, sondern Nachrichten werden in einem einzigen Thread als "flacher Fluss von Nachrichten" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="61cee-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="61cee-125">In diesen Typen von Apps werden Unterhaltungen aus einer Gruppe von Nachrichten abgeleitet, die innerhalb einer bestimmten Zeit auftreten.</span><span class="sxs-lookup"><span data-stu-id="61cee-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="61cee-126">Diese "soft-grouping" von Nachrichten (im Gegensatz zu einer Antwortkette) stellt die "Hin und Her"-Unterhaltung zu einem bestimmten Thema dar, das von Interesse ist.</span><span class="sxs-lookup"><span data-stu-id="61cee-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="61cee-127">Schritt 1: Erstellen einer Entwurfssammlung</span><span class="sxs-lookup"><span data-stu-id="61cee-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="61cee-128">Nachdem Sie relevante Custodians und Inhaltsstandorte identifiziert haben, können Sie eine Suche erstellen, um potenziell relevante Inhalte zu finden.</span><span class="sxs-lookup"><span data-stu-id="61cee-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="61cee-129">Auf der **Registerkarte Sammlungen** im Fall Advanced eDiscovery können Sie eine Auflistung erstellen, indem Sie auf Neue Auflistung **klicken** und dem Assistenten folgen.</span><span class="sxs-lookup"><span data-stu-id="61cee-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="61cee-130">Informationen dazu, wie Sie eine Auflistung erstellen, eine Suchabfrage erstellen und eine Vorschau der Suchergebnisse anzeigen können, finden Sie unter [Create a draft collection](create-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="61cee-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="61cee-131">Schritt 2: Commit einer Entwurfssammlung für einen Überprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="61cee-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="61cee-132">Nachdem Sie die Suchabfrage in einer Auflistung überprüft und abschließend erstellt haben, können Sie die Suchergebnisse einem Überprüfungssatz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="61cee-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="61cee-133">Wenn Sie Ihre Suchergebnisse zu einem Überprüfungssatz hinzufügen, werden die ursprünglichen Daten in einen Azure Storage-Bereich kopiert, um den Überprüfungs- und Analyseprozess zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="61cee-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="61cee-134">Weitere Informationen zum Hinzufügen von Suchergebnissen zu einem Überprüfungssatz finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md).</span><span class="sxs-lookup"><span data-stu-id="61cee-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="61cee-135">Wenn Sie Einem Überprüfungssatz Elemente aus Unterhaltungen hinzufügen, können Sie die Option Threadunterhaltungen verwenden, um kontextbezogene Nachrichten aus Unterhaltungen zu sammeln, die Elemente enthalten, die den Suchkriterien der Auflistung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="61cee-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="61cee-136">Nachdem Sie die Option Threadunterhaltungen ausgewählt haben, können die folgenden Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="61cee-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![Unterhaltungsabruf](../media/messagesandconversations.png)
  
1. <span data-ttu-id="61cee-138">Mithilfe einer Schlüsselwort- und Datumsbereichsabfrage hat die Suche einen Treffer in *Nachricht 3 zurückgegeben.*</span><span class="sxs-lookup"><span data-stu-id="61cee-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="61cee-139">Diese Nachricht war Teil einer größeren Unterhaltung, dargestellt von *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="61cee-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>
  
2. <span data-ttu-id="61cee-140">Wenn Sie die Daten zu einem Überprüfungssatz hinzufügen und die Unterhaltungsabrufoptionen aktivieren, wird Advanced eDiscovery zurück und sammelt andere Elemente in *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="61cee-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>
  
3. <span data-ttu-id="61cee-141">Nachdem die Elemente dem Überprüfungssatz hinzugefügt wurden, können Sie alle einzelnen Nachrichten aus *CRC1 überprüfen.*</span><span class="sxs-lookup"><span data-stu-id="61cee-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="61cee-142">Informationen zum Aktivieren der Option threaded conversations finden Sie unter [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="61cee-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>
  
## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="61cee-143">Schritt 3: Überprüfen und Exportieren von Threadunterhaltungen</span><span class="sxs-lookup"><span data-stu-id="61cee-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="61cee-144">Nachdem der Inhalt verarbeitet und dem Überprüfungssatz hinzugefügt wurde, können Sie mit der Überprüfung der Daten im Überprüfungssatz beginnen.</span><span class="sxs-lookup"><span data-stu-id="61cee-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="61cee-145">Die Überprüfungsfunktionen unterscheiden sich je nachdem, ob der Inhalt einem Standardüberprüfungssatz oder einem Unterhaltungsüberprüfungssatz hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="61cee-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="61cee-146">Überprüfen von Unterhaltungen in einem Standardüberprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="61cee-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="61cee-147">In einem Standardüberprüfungssatz werden Nachrichten wie in einem Postfachordner verarbeitet und als einzelne Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="61cee-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="61cee-148">In diesem Workflow wird jede Nachricht als separates Element verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="61cee-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="61cee-149">Dies hat zur Folge, dass die Zusammenfassungs- und Exportoptionen im Thread nicht in einem Standardüberprüfungssatz verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="61cee-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![Standardüberprüfungssatz](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="61cee-151">Überprüfen von Unterhaltungen in einem Unterhaltungsüberprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="61cee-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="61cee-152">In einem Unterhaltungsüberprüfungssatz werden einzelne Nachrichten zusammengefädelt und als Unterhaltungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="61cee-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="61cee-153">Auf diese Weise können Sie Kontextunterhaltungen überprüfen und exportieren.</span><span class="sxs-lookup"><span data-stu-id="61cee-153">This lets you review and export contextual conversations.</span></span> 

  ![Unterhaltungsüberprüfungssatz](../media/ConversationRSOptions.PNG)

<span data-ttu-id="61cee-155">In den folgenden Abschnitten wird das Überprüfen und Exportieren von Unterhaltungen in einem Unterhaltungsüberprüfungssatz beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61cee-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="61cee-156">Überprüfen von Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="61cee-156">Reviewing conversations</span></span>

<span data-ttu-id="61cee-157">In einem Unterhaltungsüberprüfungssatz können Sie die folgenden Optionen verwenden, um den Überprüfungsprozess zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="61cee-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="61cee-158">**Gruppieren nach Unterhaltung:** Gruppen von Nachrichten in derselben Unterhaltung, um Benutzern zu helfen, ihren Überprüfungsprozess zu vereinfachen und zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="61cee-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="61cee-159">**Zusammenfassungsansicht:** Zeigt die Thread-Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="61cee-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="61cee-160">In dieser Ansicht können Sie die gesamte Unterhaltung anzeigen und auch auf die Metadaten für jede einzelne Nachricht zugreifen.</span><span class="sxs-lookup"><span data-stu-id="61cee-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="61cee-161">Anzeigen von Metadaten für einzelne Nachrichten</span><span class="sxs-lookup"><span data-stu-id="61cee-161">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="61cee-162">Herunterladen einzelner Nachrichten</span><span class="sxs-lookup"><span data-stu-id="61cee-162">Download individual messages</span></span>

- <span data-ttu-id="61cee-163">**Textansicht:** Stellt den extrahierten Text für die gesamte Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="61cee-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="61cee-164">**Anmerkungsansicht:** Ermöglicht das Markup einer Threadansicht der Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="61cee-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="61cee-165">Alle Nachrichten in der Unterhaltung haben dasselbe mit Anmerkungen versehene Dokument.</span><span class="sxs-lookup"><span data-stu-id="61cee-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="61cee-166">**Tagging:** Wenn Sie Unterhaltungen in einem Überprüfungssatz anzeigen, können Sie Tags anzeigen und anwenden, indem Sie im Codierungspanel auf **Tagging-Bereich** klicken.</span><span class="sxs-lookup"><span data-stu-id="61cee-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="61cee-167">**Erneutes Ausführen der Unterhaltungskonvertierung:** Wenn Nachrichten zu einem Unterhaltungsüberprüfungssatz hinzugefügt werden, wird automatisch ein Konvertierungsauftrag ausgeführt, um die Zusammenfassung im Thread zu erstellen und Ansichten mit Anmerkungen zu versehen.</span><span class="sxs-lookup"><span data-stu-id="61cee-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="61cee-168">Wenn beim Auftrag Unterhaltungsrekonstruktion ein Fehler auftritt, können Sie diesen Auftrag erneut ausführen, indem Sie im Überprüfungssatz auf Aktion **> Unterhaltungs-PDFs** erstellen klicken.</span><span class="sxs-lookup"><span data-stu-id="61cee-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="61cee-169">Exportieren von Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="61cee-169">Exporting conversations</span></span>

<span data-ttu-id="61cee-170">In einem Unterhaltungsüberprüfungssatz können Sie die folgenden Optionen zum Exportieren von Unterhaltungen festlegen:</span><span class="sxs-lookup"><span data-stu-id="61cee-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![Exportoptionen für Unterhaltungen](../media/export.png)

<span data-ttu-id="61cee-172">a.</span><span class="sxs-lookup"><span data-stu-id="61cee-172">a.</span></span> <span data-ttu-id="61cee-173">Metadatenoptionen</span><span class="sxs-lookup"><span data-stu-id="61cee-173">Metadata options</span></span>

   - <span data-ttu-id="61cee-174">**Datei laden:** Metadaten sind für jede einzelne Nachricht, E-Mail und jedes Dokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="61cee-174">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="61cee-175">Es gibt eine Zeile für jede Nachricht in einer Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="61cee-175">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="61cee-176">**Tags:** Tags aus Ihrem Überprüfungsprozess sind in der Metadatendatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="61cee-176">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="61cee-177">Nachrichten in einer Unterhaltung verwenden dieselben Tags.</span><span class="sxs-lookup"><span data-stu-id="61cee-177">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="61cee-178">b.</span><span class="sxs-lookup"><span data-stu-id="61cee-178">b.</span></span> <span data-ttu-id="61cee-179">Unterhaltungsoptionen</span><span class="sxs-lookup"><span data-stu-id="61cee-179">Conversation options</span></span>
  
   - <span data-ttu-id="61cee-180">**Unterhaltungsdateien:** Wenn Sie Unterhaltungsdateien exportieren, wird die mit Anmerkungen versehene Ansicht in eine PDF-Datei konvertiert und in den Exportordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="61cee-180">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="61cee-181">Nachrichten in einer Unterhaltungsdatei verweisen auf die PDF-Version derselben Unterhaltungsdatei.</span><span class="sxs-lookup"><span data-stu-id="61cee-181">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="61cee-182">**Einzelne Chatnachrichten:** Wenn Sie einzelne Nachrichten exportieren, wird jede eindeutige Nachricht in der Unterhaltung als eigenständiges Element exportiert.</span><span class="sxs-lookup"><span data-stu-id="61cee-182">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="61cee-183">Die Datei wird im gleichen Format exportiert wie im Postfach.</span><span class="sxs-lookup"><span data-stu-id="61cee-183">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="61cee-184">Für eine bestimmte Unterhaltung erhalten Sie mehrere MSG-Dateien.</span><span class="sxs-lookup"><span data-stu-id="61cee-184">For a specific conversation, you receive multiple .msg files.</span></span>

     >[!NOTE]
     > <span data-ttu-id="61cee-185">Wenn Sie Anmerkungen auf die Unterhaltungsdatei angewendet haben, werden diese Anmerkungen nicht auf die einzelnen Nachrichten übertragen.</span><span class="sxs-lookup"><span data-stu-id="61cee-185">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

<span data-ttu-id="61cee-186">c.</span><span class="sxs-lookup"><span data-stu-id="61cee-186">c.</span></span> <span data-ttu-id="61cee-187">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="61cee-187">Other options</span></span>

   - <span data-ttu-id="61cee-188">**Generieren von Textdateien für alle exportierten Inhalte:** Generiert eine Textdatei für jede Unterhaltung, die aus dem Überprüfungssatz exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="61cee-188">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>

   - <span data-ttu-id="61cee-189">**Ersetzen Sie exportierten Inhalt durch redaktierte PDFs:** Wenn während des Überprüfungsprozesses redaktierte Unterhaltungsdateien generiert werden, sind diese Dateien während des Exports verfügbar.</span><span class="sxs-lookup"><span data-stu-id="61cee-189">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="61cee-190">Sie können entscheiden, ob Sie nur die systemeigenen Dateien exportieren (indem Sie diese Option nicht auswählen) oder die systemeigenen Dateien durch die rotierten Versionen der systemeigenen Dateien ersetzen (indem Sie diese Option auswählen), die als PDF-Dateien exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="61cee-190">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="61cee-191">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61cee-191">More information</span></span>

<span data-ttu-id="61cee-192">Weitere Informationen zum Überprüfen von Falldaten in Advanced eDiscovery finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="61cee-192">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="61cee-193">Anzeigen von Falldaten</span><span class="sxs-lookup"><span data-stu-id="61cee-193">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="61cee-194">Analysieren von Falldaten</span><span class="sxs-lookup"><span data-stu-id="61cee-194">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="61cee-195">Exportieren von Falldaten</span><span class="sxs-lookup"><span data-stu-id="61cee-195">Export case data</span></span>](exporting-data-ediscover20.md)
