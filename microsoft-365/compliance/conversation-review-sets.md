---
title: Überprüfen von Unterhaltungen in Advanced eDiscovery
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
ms.openlocfilehash: 01f2e6f9ceccd1903f62e8661f2cfc8f4cc2b47e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078127"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="391d7-102">Überprüfen von Unterhaltungen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="391d7-102">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="391d7-103">Instant Messaging ist eine bequeme Möglichkeit, Fragen zu stellen, Ideen auszutauschen oder schnell über große Zielgruppen hinweg zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-103">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="391d7-104">Als Instant Messaging-Plattformen wie Microsoft Teams werden Kernkompetenzen für die Zusammenarbeit in Unternehmen, müssen Organisationen bewerten, wie Ihre eDiscovery-Workflow diese neuen Formen der Kommunikation und Zusammenarbeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="391d7-104">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="391d7-105">Das Feature zur Wiederherstellung von Unterhaltungen in Advanced eDiscovery dient dazu, kontextbezogene Inhalte zu identifizieren und unterschiedliche Unterhaltungs Ansichten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="391d7-105">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="391d7-106">Mit dieser Funktion können Sie vollständige Sofortnachrichtenunterhaltungen (auch als *Thread Unterhaltung*bezeichnet) effizient und schnell überprüfen, die in Plattformen wie Microsoft Teams generiert werden.</span><span class="sxs-lookup"><span data-stu-id="391d7-106">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="391d7-107">Bei der Wiederherstellung von Unterhaltungen können Sie integrierte Funktionen verwenden, um threadbezogene Unterhaltungen neu zu erstellen, zu überprüfen und zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-107">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="391d7-108">Verwenden Sie die erweiterte eDiscovery Conversation Reconstruction für:</span><span class="sxs-lookup"><span data-stu-id="391d7-108">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="391d7-109">Beibehalten eindeutiger Metadaten auf Nachrichtenebene für alle Nachrichten in einer Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="391d7-109">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="391d7-110">Sammeln Sie kontextbezogene Nachrichten um Ihre Suchergebnisse.</span><span class="sxs-lookup"><span data-stu-id="391d7-110">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="391d7-111">Überprüfen, kommentieren und redact-Thread Unterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="391d7-111">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="391d7-112">Exportieren einzelner Nachrichten oder Thread Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="391d7-112">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="391d7-113">Terminologie</span><span class="sxs-lookup"><span data-stu-id="391d7-113">Terminology</span></span>

<span data-ttu-id="391d7-114">Hier sind einige Definitionen, die Sie beim Einstieg in die Wiederherstellung von Unterhaltungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="391d7-114">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="391d7-115">**Nachrichten:** Stellt die kleinste Einheit einer Unterhaltung dar.</span><span class="sxs-lookup"><span data-stu-id="391d7-115">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="391d7-116">Nachrichten können in Größe, Struktur und Metadaten variieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-116">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="391d7-117">Unter **Haltung:** Stellt eine Gruppierung von einer oder mehreren Nachrichten dar.</span><span class="sxs-lookup"><span data-stu-id="391d7-117">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="391d7-118">In verschiedenen Anwendungen können Unterhaltungen auf verschiedene Weise dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="391d7-118">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="391d7-119">In einigen Anwendungen gibt es eine explizite Aktion, die sich aus der Antwort auf eine vorhandene Nachricht ergibt.</span><span class="sxs-lookup"><span data-stu-id="391d7-119">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="391d7-120">Unterhaltungen werden explizit als Ergebnis dieser Benutzeraktion gebildet.</span><span class="sxs-lookup"><span data-stu-id="391d7-120">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="391d7-121">Hier ist beispielsweise ein Screenshot einer Kanal Unterhaltung in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="391d7-121">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams-Kanal Unterhaltung](../media/threadedchat.png)

   <span data-ttu-id="391d7-123">In anderen apps (wie 1xN Chatnachrichten in Microsoft Teams) gibt es keine formelle Antwort Kette, und stattdessen werden Nachrichten in einem einzelnen Thread als "Flat River of messages" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="391d7-123">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="391d7-124">In diesen Typen apps werden Unterhaltungen aus einer Gruppe von Nachrichten abgeleitet, die innerhalb eines bestimmten Zeitraums auftreten.</span><span class="sxs-lookup"><span data-stu-id="391d7-124">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="391d7-125">Diese "weiche Gruppierung" von Nachrichten (im Gegensatz zu einer Antwort Kette) stellen die Unterhaltung "hin und her" zu einem bestimmten interessanten Thema dar.</span><span class="sxs-lookup"><span data-stu-id="391d7-125">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="391d7-126">Schritt 1: Ausführen einer Suche</span><span class="sxs-lookup"><span data-stu-id="391d7-126">Step 1: Run a search</span></span>

<span data-ttu-id="391d7-127">Nachdem Sie relevante Verwalter und inhaltsspeicherorte identifiziert haben, können Sie eine Suche erstellen, um potenziell relevante Inhalte zu finden.</span><span class="sxs-lookup"><span data-stu-id="391d7-127">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="391d7-128">Auf der Registerkarte **Suchen** im erweiterten eDiscovery-Fall können Sie eine Suche erstellen, indem Sie auf **neue Suche** klicken und dem Assistenten folgen.</span><span class="sxs-lookup"><span data-stu-id="391d7-128">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="391d7-129">Weitere Informationen zum Erstellen einer Suche, zum Erstellen einer Suchabfrage und zum Anzeigen der Suchergebnisse finden Sie unter [Sammeln von Daten für einen Fall](create-search-to-collect-data.md).</span><span class="sxs-lookup"><span data-stu-id="391d7-129">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="391d7-130">Schritt 2: Erstellen eines Unterhaltungs Überprüfungs Satzes</span><span class="sxs-lookup"><span data-stu-id="391d7-130">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="391d7-131">In einer Überprüfungsgruppe können Sie Dokumente, e-Mail-Nachrichten und Chat Unterhaltungen durchsuchen, markieren, kommentieren und redact.</span><span class="sxs-lookup"><span data-stu-id="391d7-131">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="391d7-132">In Advanced eDiscovery können Sie die Überprüfung von Unterhaltungen anpassen, basierend auf einzelnen Nachrichten oder Thread Unterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="391d7-132">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="391d7-133">Dies wird durch den Typ des Überprüfungs Satzes bestimmt, den Sie die Ergebnisse der in Schritt 1 erstellten Suche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="391d7-133">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="391d7-134">Es gibt zwei verschiedene Typen von Überprüfungs Sätzen:</span><span class="sxs-lookup"><span data-stu-id="391d7-134">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="391d7-135">**Standard Überprüfungs Sätze:** Nachrichten in Unterhaltungen werden verarbeitet und als einzelne Elemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="391d7-135">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="391d7-136">**Konversations Überprüfungs Sätze:** Nachrichten in Unterhaltungen werden einzeln verarbeitet, aber in einer Unterhaltungsansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="391d7-136">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="391d7-137">In einer Konversations Überprüfungsgruppe können Sie Nachrichten in einer Diskussionsfadenansicht kommentieren, markieren und redact.</span><span class="sxs-lookup"><span data-stu-id="391d7-137">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="391d7-138">Weitere Informationen zum Überprüfen und Verwalten von Inhalten in einem Überprüfungs Satz finden Sie unter [Manage Review Sets](managing-review-sets.md).</span><span class="sxs-lookup"><span data-stu-id="391d7-138">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="391d7-139">Schritt 3: Aktivieren der Optionen für den Unterhaltungs Abruf</span><span class="sxs-lookup"><span data-stu-id="391d7-139">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="391d7-140">Nachdem Sie Ihre Suchabfrage überprüft und abgeschlossen haben, können Sie die Suchergebnisse zu einer Überprüfungsgruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="391d7-140">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="391d7-141">Wenn Sie Ihre Suchergebnisse zu einer Überprüfungsgruppe hinzufügen, werden die ursprünglichen Daten in einen Azure-Speicherbereich kopiert, um den Überprüfungs-und Analyseprozess zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="391d7-141">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="391d7-142">Weitere Informationen zum Hinzufügen von Suchergebnissen zu einer Überprüfungsgruppe finden Sie unter [Hinzufügen von Suchergebnissen zu einer Überprüfungsgruppe](add-data-to-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="391d7-142">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="391d7-143">Wenn Sie Daten aus Unterhaltungen zu einem Überprüfungs Sätze hinzufügen, können Sie die Optionen zum Abrufen von Unterhaltungen verwenden, um die Suche zu erweitern und kontextbezogene Nachrichten einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="391d7-143">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="391d7-144">Nachdem Sie die Optionen für den Abruf von Unterhaltungen festgelegt haben, können die folgenden Dinge passieren:</span><span class="sxs-lookup"><span data-stu-id="391d7-144">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![Unterhaltung abrufen](../media/messagesandconversations.png)
  
1. <span data-ttu-id="391d7-146">Bei Verwendung einer Schlüsselwort-und Datumsbereichs Abfrage hat die Suche einen Treffer bei *Nachricht 3*zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="391d7-146">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="391d7-147">Diese Nachricht war Teil einer größeren Unterhaltung, illustriert von *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="391d7-147">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="391d7-148">Wenn Sie die Daten in einem Überprüfungs hinzufügen und die Unterhaltungs Abrufoptionen aktivieren, wird Advanced eDiscovery zurückgegeben und sammelt andere Elemente in *CRC1*.</span><span class="sxs-lookup"><span data-stu-id="391d7-148">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="391d7-149">Nachdem die Elemente zum Überprüfungs Sätze hinzugefügt wurden, können Sie alle einzelnen Nachrichten von *CRC1*überprüfen.</span><span class="sxs-lookup"><span data-stu-id="391d7-149">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 



<span data-ttu-id="391d7-150">So aktivieren Sie den Unterhaltungs Abruf:</span><span class="sxs-lookup"><span data-stu-id="391d7-150">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="391d7-151">Wählen Sie auf der Registerkarte **Suchen** im Fall Advanced eDiscovery eine Suche aus, und klicken Sie dann auf der Flyout-Seite auf **zu Überarbeitungs Gruppe hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="391d7-151">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="391d7-152">Auswählen eines vorhandenen Überprüfungs Satzes oder Erstellen eines Überprüfungs Satzes.</span><span class="sxs-lookup"><span data-stu-id="391d7-152">Select an existing review set or create a review set.</span></span> <span data-ttu-id="391d7-153">Sie können Abrufoptionen beim Hinzufügen von Suchergebnissen zu einer Standard-oder Unterhaltungs Überprüfungsgruppe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-153">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="391d7-154">Konfigurieren Sie unter **Sammlungsoptionen**die Optionen für den Unterhaltungs Abruf für die Inhaltsquellen, die Sie in Ihrer Suche erweitern möchten, und klicken Sie dann auf **Hinzufügen** , um den Prozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="391d7-154">Under **Collection options**, configure the conversation retrieval options for the content sources that you want to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="391d7-155">Nachdem der Auftrag **zum Überprüfen hinzufügen** auf der Registerkarte **Aufträge** abgeschlossen ist, können Sie mit der Überprüfung der Unterhaltungen beginnen.</span><span class="sxs-lookup"><span data-stu-id="391d7-155">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-conversations-in-the-review-set"></a><span data-ttu-id="391d7-156">Schritt 4: Überprüfen der Unterhaltungen in der Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="391d7-156">Step 4: Review conversations in the review set</span></span>

<span data-ttu-id="391d7-157">Nachdem der Inhalt verarbeitet und dem Überprüfungs hinzugefügt wurde, können Sie mit der Überprüfung der Daten im Überprüfungs-Datensatz beginnen.</span><span class="sxs-lookup"><span data-stu-id="391d7-157">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="391d7-158">Die Überprüfungsfunktionen unterscheiden sich in Abhängigkeit davon, ob der Inhalt einem Standard Überprüfungs oder einer Konversations Überprüfungsgruppe hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="391d7-158">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="391d7-159">Überprüfen von Unterhaltungen in einer Standard Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="391d7-159">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="391d7-160">In einer Standard Überprüfungsgruppe werden Nachrichten verarbeitet und als einzelne Elemente angezeigt, ähnlich wie Sie in einem Postfachordner gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="391d7-160">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="391d7-161">In diesem Workflow wird jede Nachricht als separates Element verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="391d7-161">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="391d7-162">Daher sind die Optionen für den threaded Summary and Export in einer Standard Überprüfungsgruppe nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="391d7-162">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

  ![Standard Überprüfungsgruppe](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="391d7-164">Überprüfen von Unterhaltungen in einer Konversations Überprüfungsgruppe</span><span class="sxs-lookup"><span data-stu-id="391d7-164">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="391d7-165">In einer Konversations Überprüfungsgruppe werden einzelne Nachrichten mit einem Thread zusammengefasst und als Unterhaltungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="391d7-165">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="391d7-166">Auf diese Weise können Sie kontextbezogene Unterhaltungen überprüfen und exportieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-166">This lets you review and export contextual conversations.</span></span> 

  ![Konversations Überprüfungsgruppe](../media/ConversationRSOptions.PNG)

<span data-ttu-id="391d7-168">In den folgenden Abschnitten wird das überprüfen und Exportieren von Unterhaltungen in einer Konversations Überprüfungsgruppe beschrieben.</span><span class="sxs-lookup"><span data-stu-id="391d7-168">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="391d7-169">Überprüfen von Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="391d7-169">Reviewing conversations</span></span>

<span data-ttu-id="391d7-170">In einer Konversations Überprüfungsgruppe können Sie die folgenden Optionen verwenden, um den Überprüfungsprozess zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="391d7-170">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="391d7-171">**Nach Unterhaltung gruppieren:** Gruppiert Nachrichten innerhalb der gleichen Unterhaltung zusammen, um Benutzer beim vereinfachen und beschleunigen Ihres Überprüfungsprozesses zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="391d7-171">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="391d7-172">**Zusammenfassungsansicht:** Zeigt die gethreadte Unterhaltung an.</span><span class="sxs-lookup"><span data-stu-id="391d7-172">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="391d7-173">In dieser Ansicht können Sie die gesamte Unterhaltung sehen und auch auf die Metadaten für jede einzelne Nachricht zugreifen.</span><span class="sxs-lookup"><span data-stu-id="391d7-173">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="391d7-174">Anzeigen von Metadaten für einzelne Nachrichten</span><span class="sxs-lookup"><span data-stu-id="391d7-174">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="391d7-175">Einzelne Nachrichten herunterladen</span><span class="sxs-lookup"><span data-stu-id="391d7-175">Download individual messages</span></span>

- <span data-ttu-id="391d7-176">**Text Ansicht:** Stellt den extrahierten Text für die gesamte Unterhaltung bereit.</span><span class="sxs-lookup"><span data-stu-id="391d7-176">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="391d7-177">**Ansicht mit Anmerkungen versehen:** Hiermit können Sie eine Threadansicht der Unterhaltung markieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-177">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="391d7-178">Alle Nachrichten in der Unterhaltung verwenden dasselbe Dokument mit Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="391d7-178">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="391d7-179">**Tagging:** Wenn Sie Unterhaltungen in einem Überprüfungs Satzes anzeigen, können Sie Tags anzeigen und anwenden, indem Sie im Coding Panel auf Markierungs **Bereich** klicken.</span><span class="sxs-lookup"><span data-stu-id="391d7-179">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="391d7-180">Unter **Haltungs Konvertierung erneut ausführen:** Wenn Nachrichten zu einer Konversations Überprüfungsgruppe hinzugefügt werden, wird automatisch ein Konvertierungsauftrag ausgeführt, um die Zusammenfassung mit Threads zu erstellen und Ansichten zu kommentieren.</span><span class="sxs-lookup"><span data-stu-id="391d7-180">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="391d7-181">Wenn der Auftrag für die Wiederherstellung der Unterhaltung fehlschlägt, können Sie diesen Auftrag erneut ausführen, indem Sie auf **Aktion > Erstellen von Unterhaltungs PDFs** in der Überprüfungsgruppe klicken.</span><span class="sxs-lookup"><span data-stu-id="391d7-181">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>


#### <a name="exporting-conversations"></a><span data-ttu-id="391d7-182">Exportieren von Unterhaltungen</span><span class="sxs-lookup"><span data-stu-id="391d7-182">Exporting conversations</span></span>

<span data-ttu-id="391d7-183">In einer Konversations Überprüfungsgruppe können Sie die folgenden Optionen zum Exportieren von Unterhaltungen festlegen:</span><span class="sxs-lookup"><span data-stu-id="391d7-183">In a conversation review set, you can set the following options to export conversations:</span></span>

![Export](../media/export.png)

<span data-ttu-id="391d7-185">a.</span><span class="sxs-lookup"><span data-stu-id="391d7-185">a.</span></span> <span data-ttu-id="391d7-186">Metadaten-Optionen</span><span class="sxs-lookup"><span data-stu-id="391d7-186">Metadata options</span></span>

   - <span data-ttu-id="391d7-187">**Datei laden:** Metadaten sind für jede einzelne Nachricht, e-Mail und jedes Dokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="391d7-187">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="391d7-188">Es gibt eine Zeile für jede Nachricht in einer Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="391d7-188">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="391d7-189">**Tags:** Tags aus dem Überprüfungsprozess sind in der Metadatendatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="391d7-189">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="391d7-190">Nachrichten in einer Unterhaltung verwenden dieselben Tags.</span><span class="sxs-lookup"><span data-stu-id="391d7-190">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="391d7-191">b.</span><span class="sxs-lookup"><span data-stu-id="391d7-191">b.</span></span> <span data-ttu-id="391d7-192">Unterhaltungsoptionen</span><span class="sxs-lookup"><span data-stu-id="391d7-192">Conversation options</span></span>
  
   - <span data-ttu-id="391d7-193">**Unterhaltungsdateien:** Wenn Sie Unterhaltungsdateien exportieren, wird die kommentierte Ansicht in eine PDF-Datei konvertiert und in den Exportordner heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="391d7-193">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="391d7-194">Nachrichten in einer Unterhaltungs Datei deuten auf die PDF-Version der gleichen Unterhaltungs Datei.</span><span class="sxs-lookup"><span data-stu-id="391d7-194">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="391d7-195">**Einzelne Chatnachrichten:** Wenn Sie einzelne Nachrichten exportieren, wird jede eindeutige Nachricht in der Unterhaltung als eigenständiges Element exportiert.</span><span class="sxs-lookup"><span data-stu-id="391d7-195">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="391d7-196">Die Datei wird in dem Format exportiert, in dem Sie im Postfach gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="391d7-196">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="391d7-197">Für eine bestimmte Unterhaltung erhalten Sie mehrere msg-Dateien.</span><span class="sxs-lookup"><span data-stu-id="391d7-197">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="391d7-198">Wenn Sie Anmerkungen auf die Unterhaltungs Datei angewendet haben, werden diese Anmerkungen nicht an die einzelnen Nachrichten übertragen.</span><span class="sxs-lookup"><span data-stu-id="391d7-198">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="391d7-199">c.</span><span class="sxs-lookup"><span data-stu-id="391d7-199">c.</span></span> <span data-ttu-id="391d7-200">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="391d7-200">Other options</span></span>

   - <span data-ttu-id="391d7-201">**Generieren von Textdateien für alle exportierten Inhalte:** Generiert eine Textdatei für jede Unterhaltung, die aus der Überprüfungsgruppe exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="391d7-201">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="391d7-202">**Ersetzen exportierter Inhalte durch redigierte PDFs:** Wenn während des Überprüfungsprozesses unter Haltungs Dateien generiert werden, stehen diese Dateien während des Exports zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="391d7-202">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="391d7-203">Sie können entscheiden, ob nur die systemeigenen Dateien exportiert werden sollen (indem Sie diese Option nicht auswählen) oder die systemeigenen Dateien durch die behandelten Versionen der systemeigenen Dateien ersetzen (indem Sie diese Option auswählen), die als PDF-Dateien exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="391d7-203">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="391d7-204">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="391d7-204">More information</span></span>

<span data-ttu-id="391d7-205">Weitere Informationen zum Überprüfen von Falldaten in Advanced eDiscovery finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="391d7-205">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="391d7-206">Anzeigen von Daten in Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="391d7-206">View case data</span></span>](view-documents-in-review-set.md) 

- [<span data-ttu-id="391d7-207">Analysieren von Falldaten</span><span class="sxs-lookup"><span data-stu-id="391d7-207">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="391d7-208">Exportieren von Falldaten</span><span class="sxs-lookup"><span data-stu-id="391d7-208">Export case data</span></span>](exporting-data-ediscover20.md)
