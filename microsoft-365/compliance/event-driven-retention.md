---
title: Beginn der Aufbewahrung bei Auftreten eines Ereignisses
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Normalerweise ein Bestandteil einer Datensatzverwaltungslösung. Sie können eine Aufbewahrungsbezeichnung so konfigurieren, dass der Aufbewahrungszeitraum basierend auf einem von Ihnen festgelegten Ereignis gestartet wird.
ms.openlocfilehash: 7286e65be2313f5716bfc59399c1755cadb9f6d6
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778525"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="e39fe-103">Beginn der Aufbewahrung bei Auftreten eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e39fe-103">Start retention when an event occurs</span></span>

><span data-ttu-id="e39fe-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e39fe-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e39fe-p101">Wenn Sie Inhalte aufbewahren, basiert der Aufbewahrungszeitraum häufig auf dem Alter des Inhalts. Sie könnten beispielsweise Dokumente für sieben Jahre nach der Erstellung aufbewahren, und anschließend werden sie gelöscht. Wenn Sie jedoch [Aufbewahrungsbezeichnungen](labels.md) konfigurieren, können Sie auch einen Aufbewahrungszeitraum festlegen, der auf dem Auftreten eines bestimmten Ereignistyps basiert. Das Ereignis löst den Beginn des Aufbewahrungszeitraums aus, und auf alle Inhalte, denen eine Aufbewahrungsbezeichnung für diesen Ereignistyp zugewiesen wurde, werden die Aufbewahrungsaktionen angewendet.</span><span class="sxs-lookup"><span data-stu-id="e39fe-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="e39fe-109">Beispiele für die Verwendung der ereignisgesteuerten Aufbewahrung:</span><span class="sxs-lookup"><span data-stu-id="e39fe-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="e39fe-110">**Mitarbeiter verlassen die Organisation** Angenommen, Mitarbeiterdatensätze müssen ab dem Zeitpunkt, an dem ein Angestellter das Unternehmen verlässt, 10 Jahre lang aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="e39fe-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="e39fe-111">Nach 10 Jahren müssen alle Dokumente im Zusammenhang mit der Einstellung, Leistung und Kündigung dieses Angestellten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e39fe-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="e39fe-112">Das Ereignis, das den Aufbewahrungszeitraum von 10 Jahren auslöst, ist die Beendigung des Beschäftigungsverhältnisses des Mitarbeiters bei der Organisation.</span><span class="sxs-lookup"><span data-stu-id="e39fe-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="e39fe-113">**Vertragsablauf** Angenommen, alle Datensätze im Zusammenhang mit Verträgen müssen fünf Jahre lang ab dem Zeitpunkt aufbewahrt werden, ab dem der Vertrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="e39fe-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="e39fe-114">Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren ausgelöst, ist der Ablauf des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="e39fe-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="e39fe-p104">**Produktlebensdauer** – Ihre Organisation hat möglicherweise Aufbewahrungspflichten, die sich auf das letzte Fertigungsdatum von Produkten für Inhalte wie technische Daten beziehen. In diesem Fall ist das Datum der letzte Fertigung das Ereignis, das den Aufbewahrungszeitraum auslöst.</span><span class="sxs-lookup"><span data-stu-id="e39fe-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="e39fe-p105">Die ereignisgesteuerte Aufbewahrung wird in der Regel als Teil eines Prozesses für die Datensatzverwaltung verwendet. Dies bedeutet:</span><span class="sxs-lookup"><span data-stu-id="e39fe-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="e39fe-119">Bezeichnungen auf Basis von Ereignissen klassifizieren in der Regel auch Inhalte als Datensatz (als Teil einer Lösung für die Datensatzverwaltung).</span><span class="sxs-lookup"><span data-stu-id="e39fe-119">Labels based on events also usually classify content as a record, as a part of a records management solution.</span></span> <span data-ttu-id="e39fe-120">Weitere Informationen finden Sie unter [Informationen zur Datensatzverwaltung](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="e39fe-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="e39fe-121">Ein Dokument, das als Datensatz klassifiziert wurde, dessen Ereignisauslöser jedoch noch nicht eingetreten ist, wird unbegrenzt aufbewahrt (Datensätze können nicht dauerhaft gelöscht werden), bis der Aufbewahrungszeitraum für das Dokument durch ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e39fe-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="e39fe-122">Aufbewahrungsbezeichnungen auf Basis von Ereignissen lösen in der Regel eine Löschungsprüfung am Ende des Aufbewahrungszeitraums aus, damit ein Datensatzverwalter den Inhalt manuell überprüfen und löschen kann.</span><span class="sxs-lookup"><span data-stu-id="e39fe-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="e39fe-123">Weitere Informationen finden Sie unter [Entfernung von Inhalten](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="e39fe-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="e39fe-124">Eine auf einem Ereignis basierende Aufbewahrungsbezeichnung weist die gleichen Funktionen wie jede Aufbewahrungsbezeichnung in Microsoft 365 auf. </span><span class="sxs-lookup"><span data-stu-id="e39fe-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="e39fe-125">Weitere Informationen finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).</span><span class="sxs-lookup"><span data-stu-id="e39fe-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="e39fe-126">Grundlegendes zur Beziehung zwischen Ereignistypen, Bezeichnungen, Ereignissen und Asset-IDs</span><span class="sxs-lookup"><span data-stu-id="e39fe-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="e39fe-127">Um die ereignisgesteuerte Aufbewahrung erfolgreich zu verwenden, müssen Sie die Beziehung zwischen Ereignistypen, Aufbewahrungsbezeichnungen, Ereignissen und Asset-IDs verstehen, wie in den Diagrammen und der nachfolgenden Erklärung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e39fe-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagramm der Ereignistypen, Bezeichnungen, Ereignisse und Anlage IDs](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagramm der Ereignistypen, Bezeichnungen, Ereignisse und Anlage IDs](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="e39fe-130">Sie erstellen Aufbewahrungsbezeichnungen für unterschiedliche Arten von Inhalten und ordnen diesen dann einen Ereignistyp zu.</span><span class="sxs-lookup"><span data-stu-id="e39fe-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="e39fe-131">Aufbewahrungsbezeichnungen für verschiedene Arten von Produktdateien und Datensätzen werden beispielsweise einem Ereignistyp mit der Bezeichnung „Product Lifetime“ zugeordnet, da diese Datensätze ab dem Ende des Produktlebenszyklus für 10 Jahre aufbewahrt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="e39fe-132">Benutzer (in der Regel Datensatzverwalter) wenden diese Aufbewahrungsbezeichnungen auf Inhalte an, und geben (bei SharePoint- und OneDrive-Dokumenten) eine Objekt-ID für jedes Element ein.</span><span class="sxs-lookup"><span data-stu-id="e39fe-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="e39fe-133">In diesem Beispiel ist die Objekt-ID ein von der Organisation verwendeter Produktname oder -code.</span><span class="sxs-lookup"><span data-stu-id="e39fe-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="e39fe-134">Daher wird den Datensätzen jedes Produkts eine Aufbewahrungsbezeichnung zugewiesen, und jeder Datensatz verfügt über eine Eigenschaft, die eine Objekt-ID enthält.</span><span class="sxs-lookup"><span data-stu-id="e39fe-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="e39fe-135">Das Diagramm stellt **alle Inhalte** für alle Produktdatensätze in einer Organisation dar, wobei jedes Element die Objekt-ID des Produkts trägt, um dessen Datensatz es sich handelt.</span><span class="sxs-lookup"><span data-stu-id="e39fe-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="e39fe-p111">„Product Lifetime“ ist der Ereignistyp. Ein bestimmtes Produkt, das das Ende seines Lebenszyklus erreicht, ist ein Ereignis. Wenn ein Ereignis dieses Typs auftritt (in diesem Fall, wenn ein Produkt das Ende seiner Lebensdauer erreicht), erstellen Sie ein Ereignis, das Folgendes angibt:</span><span class="sxs-lookup"><span data-stu-id="e39fe-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="e39fe-138">Eine Asset-ID (für SharePoint- und OneDrive-Dokumente)</span><span class="sxs-lookup"><span data-stu-id="e39fe-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="e39fe-p112">Schlüsselwörter (für Exchange-Elemente). In diesem Beispiel verwendet das Unternehmen einen Produktcode in Nachrichten, die Produktdatensätze enthalten, sodass das Schlüsselwort für Exchange-Elemente der Objekt-ID für SharePoint- und OneDrive-Dokumente entspricht.</span><span class="sxs-lookup"><span data-stu-id="e39fe-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="e39fe-p113">Das Datum, an dem das Ereignis aufgetreten ist. Dieses Datum wird als Beginn des Aufbewahrungszeitraums verwendet. Dieses Datum kann das aktuelle, ein vergangenes oder ein zukünftiges Datum sein.</span><span class="sxs-lookup"><span data-stu-id="e39fe-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="e39fe-144">Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps aufweisen und die angegebene Objekt-ID bzw. das angegebene Schlüsselwort enthalten.</span><span class="sxs-lookup"><span data-stu-id="e39fe-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="e39fe-145">Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="e39fe-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="e39fe-146">Bei allen rot eingekreisten Elementen im vorigen Diagramm wird der Aufbewahrungszeitraum durch dieses Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e39fe-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="e39fe-147">Mit anderen Worten, wenn dieses Produkt das Ende seiner Lebensdauer erreicht, löst dieses Ereignis den Aufbewahrungszeitraum für die Produktdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="e39fe-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="e39fe-148">Folgendes sollten Sie verstehen: Wenn Sie für ein Ereignis keine Objekt-ID und keine Schlüsselwörter angeben, wird der Aufbewahrungszeitraum für **alle Inhalte** mit einer Bezeichnung dieses Ereignistyps durch das Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e39fe-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="e39fe-149">Dies bedeutet, dass im vorherigen Diagramm der Aufbewahrungszeitraum für alle Inhalte beginnen würde.</span><span class="sxs-lookup"><span data-stu-id="e39fe-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="e39fe-150">Dies ist möglicherweise nicht, was Sie beabsichtigen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-150">This might not be what you intend.</span></span> 

<span data-ttu-id="e39fe-151">Denken Sie schließlich daran, dass es zu jeder Aufbewahrungsbezeichnung eigene Aufbewahrungseinstellungen gibt.</span><span class="sxs-lookup"><span data-stu-id="e39fe-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="e39fe-152">In diesem Beispiel ist für alle ein Zeitraum von 10 Jahren angegeben, aber es ist möglich, dass ein Ereignis Aufbewahrungsbezeichnungen mit unterschiedlichen Aufbewahrungszeiträumen auslöst.</span><span class="sxs-lookup"><span data-stu-id="e39fe-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="e39fe-153">So richten Sie die ereignisgesteuerte Aufbewahrung ein</span><span class="sxs-lookup"><span data-stu-id="e39fe-153">How to set up event-driven retention</span></span>

<span data-ttu-id="e39fe-154">Allgemeiner Workflow für die ereignisgesteuerte Aufbewahrung:</span><span class="sxs-lookup"><span data-stu-id="e39fe-154">High-level workflow for event-driven retention:</span></span>
  
![Diagramm des Arbeitsablaufs zum Einrichten der ereignisgesteuerten Aufbewahrung](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="e39fe-156">Unter [Verwenden von Aufbewahrungsbezeichnungen zur Verwaltung des Lebenszyklus von in SharePoint gespeicherten Dokumenten](auto-apply-retention-labels-scenario.md) finden Sie ein detailliertes Szenario zur Verwendung von verwalteten Eigenschaften in SharePoint, um Aufbewahrungsbezeichnungen automatisch anzuwenden und die ereignisgesteuerte Aufbewahrung zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="e39fe-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="e39fe-157">Schritt 1: Eine Bezeichnung erstellen, deren Aufbewahrungszeitraum auf einem Ereignis basiert</span><span class="sxs-lookup"><span data-stu-id="e39fe-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="e39fe-158">Folgen Sie zum Erstellen und Konfigurieren Ihrer Aufbewahrungsbezeichnung den Anweisungen unter [Erstellen und Konfigurieren von Aufbewahrungsbezeichnungen](create-retention-labels.md#create-and-configure-retention-labels), und wählen Sie beim Aktivieren der Aufbewahrung die Option aus, den Inhalt auf der Grundlage eines Ereignisses aufzubewahren oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="e39fe-159">Durch diese Einstellung werden die Aufbewahrungseinstellungen nur wirksam, wenn Sie in Schritt 5 auf der Seite **Ereignisse** ein Ereignis erstellen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="e39fe-160">Die ereignisgesteuerte Aufbewahrung wird in der Regel für Inhalte verwendet, die als Datensatz klassifiziert sind. Dies ist daher ein guter Zeitpunkt, um zu überprüfen, ob Sie auch die Option zum Markieren von Inhalten als Datensatz auswählen müssen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="e39fe-161">Für die ereignisgesteuerte Aufbewahrung sind Aufbewahrungseinstellungen erforderlich, die:</span><span class="sxs-lookup"><span data-stu-id="e39fe-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="e39fe-162">Inhalte aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="e39fe-162">Retain the content.</span></span>
    
- <span data-ttu-id="e39fe-163">den Inhalt automatisch löschen oder eine Dispositionsprüfung am Ende des Aufbewahrungszeitraums auslösen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![Option, um eine Bezeichnung auf einem Ereignis zu basieren](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="e39fe-165">Schritt 2: Einen Ereignistyps für die Bezeichnung auswählen</span><span class="sxs-lookup"><span data-stu-id="e39fe-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="e39fe-166">Nachdem Sie in den Bezeichnungseinstellungen die Option ausgewählt haben, die Bezeichnung auf **einem Ereignis** zu basieren, wird die Option zum **Auswählen eines Ereignistyps** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e39fe-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="e39fe-167">Ein Ereignistyp ist einfach eine allgemeine Beschreibung eines Ereignisses, das Sie einer Bezeichnung zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="e39fe-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="e39fe-168">Wenn Sie zum Beispiel einen Ereignistyp mit dem Namen „Product Lifetime“ haben, erstellen Sie ereignisbasierte Aufbewahrungsbezeichnungen mit Namen, die beschreiben, auf welchen Inhaltstyp die Bezeichnungen angewendet werden sollen, z. B. „Produktentwicklungsdateien“ oder „Produktgeschäft-Entscheidungsdatensätze“.</span><span class="sxs-lookup"><span data-stu-id="e39fe-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="e39fe-169">Wählen Sie einen der integrierten Ereignistypen aus, oder erstellen Sie einen eigenen und wählen Sie diesen dann aus.</span><span class="sxs-lookup"><span data-stu-id="e39fe-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="e39fe-170">Der Ereignistyp kann nicht mehr geändert werden, sobald Sie ihn ausgewählt und die Aufbewahrungsbezeichnung gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="e39fe-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![Optionen zum Erstellen oder Auswählen eines Ereignistyps](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="e39fe-172">Schritt 3: Veröffentlichen oder automatisches Zuweisen der ereignisbasierten Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e39fe-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="e39fe-173">Wie jede Aufbewahrungsbezeichnung müssen Sie auch ereignisbasierte Bezeichnungen veröffentlichen oder automatisch anwenden, damit sie auf Inhalte manuell oder automatisch angewendet werden können:</span><span class="sxs-lookup"><span data-stu-id="e39fe-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="e39fe-174">Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps</span><span class="sxs-lookup"><span data-stu-id="e39fe-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="e39fe-175">Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="e39fe-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="e39fe-176">Wenn Sie eine ereignisbasierte Aufbewahrungsbezeichnung auf der Registerkarte **Datensatzverwaltung** > **Dateiplan** oder der Registerkarte **Datengovernance** > **Bezeichnungen** wählen, ist die Schaltfläche **Bezeichnung automatisch anwenden** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e39fe-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="e39fe-177">Statt dieser Schaltfläche verwenden Sie die Option **Bezeichnung automatisch anwenden** über der Liste der Bezeichnungen oder Richtlinien aus einer der folgenden Speicherorte:</span><span class="sxs-lookup"><span data-stu-id="e39fe-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="e39fe-178">Registerkarte **Datensatzverwaltung** > **Bezeichnungsrichtlinien**</span><span class="sxs-lookup"><span data-stu-id="e39fe-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="e39fe-179">Registerkarte **Datensteuerung** > **Bezeichnungen**  oder Registerkarte **Bezeichnungsrichtlinien**</span><span class="sxs-lookup"><span data-stu-id="e39fe-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![Optionen zum Veröffentlichen oder automatischen Anwenden einer Aufbewahrungsbezeichnung](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="e39fe-181">Schritt 4: Eine Asset-ID eingeben</span><span class="sxs-lookup"><span data-stu-id="e39fe-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="e39fe-182">Nachdem eine ereignisbasierte Bezeichnung auf Inhalte angewendet wurde, können Sie für jedes Element eine Objekt-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="e39fe-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="e39fe-183">Ihre Organisation kann beispielsweise folgende Elemente verwenden:</span><span class="sxs-lookup"><span data-stu-id="e39fe-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="e39fe-184">Produktcodes, um Inhalt nur für ein bestimmtes Produkt aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="e39fe-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="e39fe-185">Projektcodes, um Inhalt nur für ein bestimmtes Projekt aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="e39fe-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="e39fe-186">Mitarbeiter-IDs, die Sie zum Aufbewahren von Inhalten für eine bestimmte Person verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e39fe-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="e39fe-187">Die Objekt-ID ist einfach eine weitere in SharePoint und OneDrive verfügbare Dokumenteigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e39fe-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="e39fe-188">Ihre Organisation verwendet möglicherweise bereits andere Dokumenteigenschaften und IDs zum Klassifizieren von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="e39fe-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="e39fe-189">In diesem Falle können Sie beim Erstellen eines Ereignisses auch diese Eigenschaften und Werte verwenden – siehe nachfolgenden Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="e39fe-189">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="e39fe-190">Wichtig ist hierbei, dass Sie in den Dokumenteigenschaften eine *Kombination aus Eigenschaft und Wert* verwenden müssen, um dieses Element mit einem Ereignistyp zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Textfeld zum Eingeben einer Asset-ID](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="e39fe-192">Schritt 5: Erstellen eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e39fe-192">Step 5: Create an event</span></span>

<span data-ttu-id="e39fe-193">Wenn eine bestimmte Instanz dieses Ereignistyps auftritt – z. B. wenn ein Produkt das Ende seiner Lebensdauer erreicht –, rufen Sie die Seite **Datensatzverwaltung** > **Ereignisse** im Microsoft 365 Compliance Center auf, und erstellen Sie ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e39fe-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="e39fe-194">Ein Ereignis wird durch seine Erstellung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e39fe-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="e39fe-195">Schritt 6: Auswählen des gleichen Ereignistyps, der von der Bezeichnung in Schritt 2 verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e39fe-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="e39fe-196">Wenn Sie ein Ereignis erstellen, wählen Sie den gleichen Ereignistyp aus, der von der Aufbewahrungsbezeichnung in Schritt 2 verwendet wird – z. B. „Product Lifetime“.</span><span class="sxs-lookup"><span data-stu-id="e39fe-196">When you create the event, choose the same event type used by the retention label in step 2—for example, Product Lifetime.</span></span> <span data-ttu-id="e39fe-197">Nur für Inhalte, denen Aufbewahrungsbezeichnungen des betreffenden Ereignistyps zugeordnet wurden, wird der Aufbewahrungszeitraum ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e39fe-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![Option in den Ereigniseinstellungen zum Auswählen eines Ereignistyps](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="e39fe-199">Schritt 7: Stichwörter oder Asset-ID eingeben</span><span class="sxs-lookup"><span data-stu-id="e39fe-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="e39fe-200">Schränken Sie nun den Umfang des Inhalts ein, indem Sie Objekt-IDs für SharePoint- und OneDrive-Inhalte bzw. Schlüsselwörter für Exchange-Inhalte angeben.</span><span class="sxs-lookup"><span data-stu-id="e39fe-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="e39fe-201">Bei Objekt-IDs wird die Aufbewahrung nur für Inhalte mit der angegebenen Kombination aus *Eigenschaft und Wert* erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="e39fe-202">Wird keine Objekt-ID eingegeben, wird auf alle Inhalte mit Bezeichnungen dieses Ereignistyps dasselbe Aufbewahrungslimit angewendet.</span><span class="sxs-lookup"><span data-stu-id="e39fe-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="e39fe-203">Ein Beispiel: Wenn Sie die Eigenschaft "Objekt-ID" verwenden, geben Sie `ComplianceAssetID:<value>` in das untenstehende Feld für Objekt-IDs ein.</span><span class="sxs-lookup"><span data-stu-id="e39fe-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="e39fe-204">Möglicherweise hat Ihre Organisation andere Eigenschaften und IDs auf die mit diesem Ereignistyp verknüpften Dokumente angewendet.</span><span class="sxs-lookup"><span data-stu-id="e39fe-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="e39fe-205">Wenn Sie beispielsweise die Datensätze zu einem bestimmten Produkt ermitteln müssen, könnte die ID eine Kombination aus Ihrer benutzerdefinierten Eigenschaft "ProductID" und dem Wert "XYZ" sein.</span><span class="sxs-lookup"><span data-stu-id="e39fe-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="e39fe-206">In diesem Fall würden Sie in das Feld für Objekt-IDs, das in der folgenden Abbildung dargestellt ist, `ProductID:XYZ` eingeben.</span><span class="sxs-lookup"><span data-stu-id="e39fe-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="e39fe-207">Verwenden Sie für Exchange-Elemente Stichworte.</span><span class="sxs-lookup"><span data-stu-id="e39fe-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="e39fe-208">Für eine Abfrage können Sie Suchoperatoren wie AND, OR und NOT verwenden.</span><span class="sxs-lookup"><span data-stu-id="e39fe-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="e39fe-209">Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="e39fe-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="e39fe-210">Wählen Sie schließlich das Datum aus, an dem das Ereignis eingetreten ist. Dieses Datum wird als Anfang des Aufbewahrungszeitraums verwendet.</span><span class="sxs-lookup"><span data-stu-id="e39fe-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="e39fe-211">Nach der Erstellung eines Ereignisses wird dieses Ereignisdatum mit allen Inhalten synchronisiert, die eine Aufbewahrungsbezeichnung dieses Ereignistyps, die Objekt-ID und die Schlüsselwörter aufweisen. </span><span class="sxs-lookup"><span data-stu-id="e39fe-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="e39fe-212">Wie bei jeder Aufbewahrungsbezeichnung kann die Synchronisierung bis zu 7 Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="e39fe-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Seite „Ereigniseinstellungen“](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="e39fe-214">Nach dem Erstellen eines Ereignisses gelten die Aufbewahrungseinstellungen für bereits bezeichnete und indizierte Inhalte.</span><span class="sxs-lookup"><span data-stu-id="e39fe-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="e39fe-215">Wenn die Aufbewahrungsbezeichnung zu neuen Inhalten hinzugefügt wird, nachdem das Ereignis erstellt wurde, müssen Sie ein neues Ereignis mit den gleichen Details erstellen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="e39fe-216">Wenn Sie ein Ereignis löschen, werden dadurch die Aufbewahrungseinstellungen, die jetzt für bereits bezeichnete Inhalte in Kraft sind, nicht aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="e39fe-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="e39fe-217">Erstellen Sie dazu ein neues Ereignis mit den gleichen Details, lassen Sie das Datum aber leer.</span><span class="sxs-lookup"><span data-stu-id="e39fe-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="e39fe-218">Verwenden der Inhaltssuche zum Auffinden aller Inhalte mit einer bestimmten Bezeichnung oder Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="e39fe-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="e39fe-219">Nachdem Aufbewahrungsbezeichnungen Inhalten zugewiesen wurden, können Sie die Inhaltssuche verwenden, um alle Inhalte aufzufinden, die durch eine bestimmte Aufbewahrungsbezeichnung klassifiziert wurden oder eine bestimmte Objekt-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="e39fe-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="e39fe-220">Um alle Inhalte mit einer bestimmten Aufbewahrungsbezeichnung zu finden, wählen Sie die Bedingung **Aufbewahrungsbezeichnung**, und geben Sie dann den vollständigen oder Bezeichnungsnamen oder einen Teil des Bezeichnungsnamens ein, und verwenden Sie einen Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="e39fe-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="e39fe-221">Um alle Inhalte mit einer bestimmten Objekt-ID zu finden, geben Sie die **ComplianceAssetID**-Eigenschaft und einen Wert ein, und zwar im Format: `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="e39fe-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="e39fe-222">Weitere Informationen finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="e39fe-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="e39fe-223">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e39fe-223">Permissions</span></span>

<span data-ttu-id="e39fe-p129">Um Zugriff auf die Seite **Ereignisse** zu erhalten, müssen Prüfer Mitglied einer Rollengruppe sein, die die Rolle **Disposition Management** und die Rolle **View-Only Audit Logs** hat. Es wird empfohlen, eine neue Rollengruppe namens „Disposition Reviewers“ zu erstellen, diese beiden Rollen zu dieser Rollengruppe hinzuzufügen und anschließend Mitglieder zur Rollengruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="e39fe-226">Weitere Informationen finden Sie unter [Freigeben des Benutzerzugriffs auf das Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e39fe-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="e39fe-227">Automatisieren von Ereignissen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="e39fe-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="e39fe-228">Sie können ereignisbasierte Aufbewahrung aus Ihren Geschäftsanwendungen heraus mithilfe eines PowerShell-Skripts automatisieren.</span><span class="sxs-lookup"><span data-stu-id="e39fe-228">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="e39fe-229">PowerShell-Cmdlets für die ereignisbasierte Aufbewahrung:</span><span class="sxs-lookup"><span data-stu-id="e39fe-229">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="e39fe-230">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="e39fe-230">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="e39fe-231">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="e39fe-231">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="e39fe-232">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="e39fe-232">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="e39fe-233">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="e39fe-233">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="e39fe-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="e39fe-234">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="e39fe-235">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="e39fe-235">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="e39fe-236">Automatisieren von Ereignissen mithilfe einer REST-API</span><span class="sxs-lookup"><span data-stu-id="e39fe-236">Automate events by using a REST API</span></span>

<span data-ttu-id="e39fe-237">Sie können eine REST-API verwenden, um automatisch die Ereignisse zu erstellen, die den Beginn der Aufbewahrungszeit auslösen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-237">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="e39fe-238">Bei einer REST-API handelt es sich um einen Dienstendpunkt, der Gruppen von HTTP-Vorgängen (Methoden) unterstützt, die Zugriff zum Erstellen/Abrufen/Aktualisieren/Löschen der Dienstressourcen bieten.</span><span class="sxs-lookup"><span data-stu-id="e39fe-238">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="e39fe-239">Weitere Informationen finden Sie unter [Komponenten einer REST-API-Anfrage/-Anfrage](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="e39fe-239">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="e39fe-240">Mithilfe der Microsoft 365 REST-API können Ereignisse mit POST- und GET-Operationen erstellt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e39fe-240">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="e39fe-241">Es gibt zwei Optionen für die Verwendung der REST-API:</span><span class="sxs-lookup"><span data-stu-id="e39fe-241">There are two options for using the REST API:</span></span>

- <span data-ttu-id="e39fe-242">**Microsoft Power Automate oder eine ähnliche Anwendung** zum automatischen Auslösen des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e39fe-242">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="e39fe-243">Microsoft Power Automate ist ein Orchestrator zum Herstellen der Verbindung zu anderen Systemen, sodass Sie keine benutzerdefinierte Lösung erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-243">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="e39fe-244">Weitere Informationen finden Sie auf der [Power Automate-Website](https://flow.microsoft.com/de-DE/).</span><span class="sxs-lookup"><span data-stu-id="e39fe-244">For more information, see the [Power Automate website](https://flow.microsoft.com/de-DE/).</span></span>

- <span data-ttu-id="e39fe-245">**PowerShell oder ein HTTP-Client zum Aufrufen der REST-API**, um Ereignisse mithilfe von PowerShell (Version 6 oder höher) zu erstellen, was Teil einer benutzerdefinierten Lösung ist.</span><span class="sxs-lookup"><span data-stu-id="e39fe-245">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="e39fe-246">Bevor Sie die REST-API verwenden, überprüfen Sie als globaler Administrator die URL, die für den Aufruf des Aufbewahrungsereignisses verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e39fe-246">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="e39fe-247">Führen Sie dazu ein GET-Aufbewahrungsereignisaufruf mithilfe der REST-API-URL aus:</span><span class="sxs-lookup"><span data-stu-id="e39fe-247">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="e39fe-248">Überprüfen Sie den Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="e39fe-248">Check the response code.</span></span> <span data-ttu-id="e39fe-249">Wenn es sich um 302 handelt, rufen Sie die umgeleitete URL aus der „Location“-Eigenschaft des Antwortheaders ab, und verwenden Sie diese URL statt `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in den nachfolgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e39fe-249">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="e39fe-250">Die automatisch erstellten Ereignisse können bestätigt werden, indem Sie sie im Microsoft 365 Compliance Center anzeigen > **Datensatzverwaltung** >  **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="e39fe-250">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="e39fe-251">Verwenden von Microsoft Power Automate zum Erstellen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e39fe-251">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="e39fe-252">Erstellen eines Ablaufs zum Erstellen eines Ereignisses mithilfe der Microsoft 365-REST-API:</span><span class="sxs-lookup"><span data-stu-id="e39fe-252">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Verwenden von Flow zum Erstellen eines Ereignisses](../media/automate-event-driven-retention-flow-1.png)

![Verwenden des Ablaufs zum Aufrufen der REST-API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="e39fe-255">Erstellen eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e39fe-255">Create an event</span></span>

<span data-ttu-id="e39fe-256">Beispielcode zum Aufrufen der REST-API:</span><span class="sxs-lookup"><span data-stu-id="e39fe-256">Sample code to call the REST API:</span></span>

- <span data-ttu-id="e39fe-257">**Method**: POST</span><span class="sxs-lookup"><span data-stu-id="e39fe-257">**Method**: POST</span></span>
- <span data-ttu-id="e39fe-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="e39fe-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="e39fe-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e39fe-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="e39fe-260">**Body**:</span><span class="sxs-lookup"><span data-stu-id="e39fe-260">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="e39fe-261">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e39fe-261">**Authentication**: Basic</span></span>
- <span data-ttu-id="e39fe-262">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e39fe-262">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="e39fe-263">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e39fe-263">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="e39fe-264">Verfügbare Parameter</span><span class="sxs-lookup"><span data-stu-id="e39fe-264">Available parameters</span></span>


|<span data-ttu-id="e39fe-265">Parameter</span><span class="sxs-lookup"><span data-stu-id="e39fe-265">Parameters</span></span>|<span data-ttu-id="e39fe-266">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e39fe-266">Description</span></span>|<span data-ttu-id="e39fe-267">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e39fe-267">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="e39fe-268"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="e39fe-268"><d:Name></d:Name></span></span>|<span data-ttu-id="e39fe-269">Geben Sie einen eindeutigen Namen für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="e39fe-269">Provide a unique name for the event,</span></span>|<span data-ttu-id="e39fe-270">Der Name darf nachfolgende Leerzeichen oder die folgenden Zeichen nicht enthalten: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="e39fe-270">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="e39fe-271">, : ;</span><span class="sxs-lookup"><span data-stu-id="e39fe-271">, : ;</span></span>|
|<span data-ttu-id="e39fe-272"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="e39fe-272"><d:EventType></d:EventType></span></span>|<span data-ttu-id="e39fe-273">Geben Sie den Namen des Ereignistyps (oder GUID) ein.</span><span class="sxs-lookup"><span data-stu-id="e39fe-273">Enter event type name (or Guid),</span></span>|<span data-ttu-id="e39fe-274">Beispiel: "Mitarbeiterkündigung".</span><span class="sxs-lookup"><span data-stu-id="e39fe-274">Example: "Employee termination".</span></span> <span data-ttu-id="e39fe-275">Der Ereignistyp muss einer Aufbewahrungsbezeichnung zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="e39fe-275">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="e39fe-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="e39fe-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="e39fe-277">Geben Sie "ComplianceAssetId:" + Mitarbeiter-ID ein</span><span class="sxs-lookup"><span data-stu-id="e39fe-277">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="e39fe-278">Beispiel: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="e39fe-278">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="e39fe-279"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="e39fe-279"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="e39fe-280">Datum und Uhrzeit des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e39fe-280">Event Date and Time</span></span>|<span data-ttu-id="e39fe-281">Format: jjjj-MM-ttTHH:mm:ssZ, Beispiel: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="e39fe-281">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="e39fe-282">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e39fe-282">Response codes</span></span>

| <span data-ttu-id="e39fe-283">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e39fe-283">Response Code</span></span> | <span data-ttu-id="e39fe-284">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e39fe-284">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="e39fe-285">302</span><span class="sxs-lookup"><span data-stu-id="e39fe-285">302</span></span>               | <span data-ttu-id="e39fe-286">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e39fe-286">Redirect</span></span>              |
| <span data-ttu-id="e39fe-287">201</span><span class="sxs-lookup"><span data-stu-id="e39fe-287">201</span></span>               | <span data-ttu-id="e39fe-288">Erstellt</span><span class="sxs-lookup"><span data-stu-id="e39fe-288">Created</span></span>               |
| <span data-ttu-id="e39fe-289">403</span><span class="sxs-lookup"><span data-stu-id="e39fe-289">403</span></span>               | <span data-ttu-id="e39fe-290">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-290">Authorization Failed</span></span>  |
| <span data-ttu-id="e39fe-291">401</span><span class="sxs-lookup"><span data-stu-id="e39fe-291">401</span></span>               | <span data-ttu-id="e39fe-292">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-292">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="e39fe-293">Abrufen von Ereignissen basierend auf einem Zeitraum</span><span class="sxs-lookup"><span data-stu-id="e39fe-293">Get events based on a time range</span></span>

- <span data-ttu-id="e39fe-294">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="e39fe-294">**Method**: GET</span></span>

- <span data-ttu-id="e39fe-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="e39fe-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="e39fe-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e39fe-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="e39fe-297">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e39fe-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="e39fe-298">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e39fe-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="e39fe-299">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e39fe-299">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="e39fe-300">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e39fe-300">Response codes</span></span>

| <span data-ttu-id="e39fe-301">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e39fe-301">Response Code</span></span> | <span data-ttu-id="e39fe-302">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e39fe-302">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="e39fe-303">200</span><span class="sxs-lookup"><span data-stu-id="e39fe-303">200</span></span>               | <span data-ttu-id="e39fe-304">OK, eine Liste der Ereignisse in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="e39fe-304">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="e39fe-305">404</span><span class="sxs-lookup"><span data-stu-id="e39fe-305">404</span></span>               | <span data-ttu-id="e39fe-306">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e39fe-306">Not found</span></span>                         |
| <span data-ttu-id="e39fe-307">302</span><span class="sxs-lookup"><span data-stu-id="e39fe-307">302</span></span>               | <span data-ttu-id="e39fe-308">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e39fe-308">Redirect</span></span>                          |
| <span data-ttu-id="e39fe-309">401</span><span class="sxs-lookup"><span data-stu-id="e39fe-309">401</span></span>               | <span data-ttu-id="e39fe-310">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-310">Authorization Failed</span></span>              |
| <span data-ttu-id="e39fe-311">403</span><span class="sxs-lookup"><span data-stu-id="e39fe-311">403</span></span>               | <span data-ttu-id="e39fe-312">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-312">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="e39fe-313">Abrufen eines Ereignisses nach ID</span><span class="sxs-lookup"><span data-stu-id="e39fe-313">Get an event by ID</span></span>

- <span data-ttu-id="e39fe-314">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="e39fe-314">**Method**: GET</span></span>

- <span data-ttu-id="e39fe-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="e39fe-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="e39fe-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e39fe-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="e39fe-317">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e39fe-317">**Authentication**: Basic</span></span>

- <span data-ttu-id="e39fe-318">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e39fe-318">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="e39fe-319">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e39fe-319">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="e39fe-320">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e39fe-320">Response codes</span></span>

| <span data-ttu-id="e39fe-321">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e39fe-321">Response Code</span></span> | <span data-ttu-id="e39fe-322">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e39fe-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="e39fe-323">200</span><span class="sxs-lookup"><span data-stu-id="e39fe-323">200</span></span>               | <span data-ttu-id="e39fe-324">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="e39fe-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="e39fe-325">404</span><span class="sxs-lookup"><span data-stu-id="e39fe-325">404</span></span>               | <span data-ttu-id="e39fe-326">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e39fe-326">Not found</span></span>                                            |
| <span data-ttu-id="e39fe-327">302</span><span class="sxs-lookup"><span data-stu-id="e39fe-327">302</span></span>               | <span data-ttu-id="e39fe-328">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e39fe-328">Redirect</span></span>                                             |
| <span data-ttu-id="e39fe-329">401</span><span class="sxs-lookup"><span data-stu-id="e39fe-329">401</span></span>               | <span data-ttu-id="e39fe-330">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="e39fe-331">403</span><span class="sxs-lookup"><span data-stu-id="e39fe-331">403</span></span>               | <span data-ttu-id="e39fe-332">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-332">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="e39fe-333">Abrufen eines Ereignisses anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="e39fe-333">Get an event by name</span></span>

- <span data-ttu-id="e39fe-334">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="e39fe-334">**Method**: GET</span></span>

- <span data-ttu-id="e39fe-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="e39fe-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="e39fe-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e39fe-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="e39fe-337">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e39fe-337">**Authentication**: Basic</span></span>

- <span data-ttu-id="e39fe-338">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e39fe-338">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="e39fe-339">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e39fe-339">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="e39fe-340">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e39fe-340">Response codes</span></span>

| <span data-ttu-id="e39fe-341">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e39fe-341">Response Code</span></span> | <span data-ttu-id="e39fe-342">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e39fe-342">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="e39fe-343">200</span><span class="sxs-lookup"><span data-stu-id="e39fe-343">200</span></span>               | <span data-ttu-id="e39fe-344">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="e39fe-344">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="e39fe-345">404</span><span class="sxs-lookup"><span data-stu-id="e39fe-345">404</span></span>               | <span data-ttu-id="e39fe-346">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e39fe-346">Not found</span></span>                                            |
| <span data-ttu-id="e39fe-347">302</span><span class="sxs-lookup"><span data-stu-id="e39fe-347">302</span></span>               | <span data-ttu-id="e39fe-348">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e39fe-348">Redirect</span></span>                                             |
| <span data-ttu-id="e39fe-349">401</span><span class="sxs-lookup"><span data-stu-id="e39fe-349">401</span></span>               | <span data-ttu-id="e39fe-350">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-350">Authorization Failed</span></span>                                 |
| <span data-ttu-id="e39fe-351">403</span><span class="sxs-lookup"><span data-stu-id="e39fe-351">403</span></span>               | <span data-ttu-id="e39fe-352">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e39fe-352">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="e39fe-353">Verwenden von PowerShell oder einem beliebigen HTTP-Client, um das Ereignis zu erstellen</span><span class="sxs-lookup"><span data-stu-id="e39fe-353">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="e39fe-354">Bei PowerShell muss es sich um Version 6 oder höher handeln.</span><span class="sxs-lookup"><span data-stu-id="e39fe-354">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="e39fe-355">Führen Sie in einer PowerShell-Sitzung das folgende Skript aus:</span><span class="sxs-lookup"><span data-stu-id="e39fe-355">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

