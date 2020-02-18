---
title: Automatisieren der ereignisgesteuerten Aufbewahrung
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In diesem Thema wird erläutert, wie Sie Geschäftsprozessabläufe über Ereignisse mithilfe der Microsoft 365-REST-API einrichten können, um die Aufbewahrung zu automatisieren.
ms.openlocfilehash: 692671ca5e7d956cb168ac0de2e409e7023cfd04
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079081"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="37656-103">Automatisieren der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="37656-103">Automate event-based retention</span></span>

<span data-ttu-id="37656-p101">Die explosionsartige Zunahme von Inhalten in Unternehmen und wie erreicht werden kann, dass diese keine Rolle mehr spielt, ist eine ernste Angelegenheit. Um auch weiterhin den Herausforderungen im Zusammenhang mit der Einhaltung gesetzlicher und geschäftlicher Bestimmungen gerecht zu werden, müssen Organisationen in der Lage sein, wichtige Informationen aufzubewahren und zu schützen und schnell herauszufinden, was relevant ist. Die Aufbewahrung ausschließlich wichtiger, relevanter Informationen ist der Schlüssel zum Erfolg einer Organisation.</span><span class="sxs-lookup"><span data-stu-id="37656-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="37656-p102">Um dieser Anforderung gerecht zu werden, können Unternehmen die Aufbewahrungslösungen im Office 365 Security & Compliance Center nutzen. Aufbewahrung kann mithilfe von [Aufbewahrungsbezeichnungen](labels.md) ausgelöst werden. Eine Aufbewahrungsbezeichnung kann als [Grundlage für den Aufbewahrungszeitraum für ein bestimmtes Ereignis](event-driven-retention.md) dienen. In der Regel basiert der Aufbewahrungszeitraum auf einem bekannten Datum, z. B. dem Erstellungsdatum oder dem Datum der letzten Änderung der Inhalte. Unternehmen müssen jedoch auch Inhalte aufgrund des Eintretens eines Ereignisses entfernen, zum Beispiel 7 Jahre nach dem Austritt eines Mitarbeiters aus dem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="37656-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="37656-p103">Um ein ordnungsgemäßes Entfernen der Inhalte sicherzustellen, ist es zwingend erforderlich zu wissen, wann ein Ereignis eintritt. Da die Inhaltsmenge rasant zunimmt, wird es immer schwieriger, Inhalte zeitnah und ordnungsgemäß aufzubewahren und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="37656-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="37656-p104">Die ereignisbasierte Aufbewahrung stellt eine Lösung für dieses Problem dar. In diesem Thema wird erläutert, wie Sie Geschäftsprozessabläufe über Ereignisse mithilfe der Microsoft 365-REST-API einrichten können, um die Aufbewahrung zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="37656-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="37656-116">Grundlegendes zur ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="37656-116">About event-based retention</span></span>

<span data-ttu-id="37656-p105">Es gibt kleine, mittelständige und Großunternehmen. Die Anzahl der Geschäftsdokumente, Rechtsdokumente, Mitarbeiterdateien, Verträgen und Produktdokumenten, die täglich erstellt und verwaltet werden, nimmt dramatisch zu.</span><span class="sxs-lookup"><span data-stu-id="37656-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="37656-p106">Zum Beispiel werden täglich Dutzende Mitarbeiter eingestellt, und es verlassen auch Dutzende Mitarbeiter die Unternehmen. Die Personalabteilung erstellt, aktualisiert oder löscht weiterhin mitarbeiterbezogene Dokumente gemäß den Geschäftsanforderungen. Dieser Prozess unterliegt verschiedenen Aufbewahrungsrichtlinien, die für das Unternehmen festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="37656-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="37656-p107">**Der Aufbewahrungszeitraum für die Inhalte kann ein bekanntes Datum sein,** z. B. das Datum, an dem der Inhalt erstellt, zuletzt geändert oder mit einer Bezeichnung versehen wurde. Beispiel: Dokumente werden möglicherweise sieben Jahre lang ab Erstellung aufbewahrt und anschließend gelöscht.</span><span class="sxs-lookup"><span data-stu-id="37656-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="37656-p108">**Der Aufbewahrungszeitraum für den Inhalt kann auch ein unbekanntes Datum sein**. Mit Aufbewahrungsbezeichnungen können Sie zum Beispiel als Basis für den Aufbewahrungszeitraum ein bestimmtes Ereignis festlegen, zum Beispiel den Austritt eines Mitarbeiters aus dem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="37656-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="37656-p109">Mit dem Ereignis wird der Anfang des Aufbewahrungszeitraums ausgelöst. Für alle Inhalte mit einer Bezeichnung, die für diese Art des Ereignisses angewendet wurde, werden die Aufbewahrungsmaßnahmen der Bezeichnung erzwungen. Dies wird auch als ereignisbasierte Aufbewahrung bezeichnet. Weitere Informationen hierzu finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="37656-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="37656-129">Einrichten der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="37656-129">Set up event-based retention</span></span>

<span data-ttu-id="37656-130">Dieser Abschnitt beinhaltet die für die Aufbewahrung von Inhalten erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="37656-130">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="37656-131">Identifizieren von Rollen</span><span class="sxs-lookup"><span data-stu-id="37656-131">Identify roles</span></span>

<span data-ttu-id="37656-132">Identifizieren Sie die verschiedenen Rollen in einem Unternehmen, die Aufgaben für die Datensatzverwaltung ausführen und für eine effektive und effiziente Aufbewahrung von Geschäftsdokumenten verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="37656-132">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="37656-133">**Persona**</span><span class="sxs-lookup"><span data-stu-id="37656-133">**Persona**</span></span>| <span data-ttu-id="37656-134">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="37656-134">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="37656-135">Admin</span><span class="sxs-lookup"><span data-stu-id="37656-135">Admin</span></span> | <span data-ttu-id="37656-136">Erstellt Ereignistypen für die Aufbewahrung, Aufbewahrungsbezeichnungen und Repositorys für die Aufbewahrung in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="37656-136">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="37656-137">Datensatzverwalter</span><span class="sxs-lookup"><span data-stu-id="37656-137">Records Manager</span></span>                                  | <span data-ttu-id="37656-138">Stellt Details zur Einhaltung von Aufbewahrungsrichtlinien und Aufbewahrungszeitplänen bereit.</span><span class="sxs-lookup"><span data-stu-id="37656-138">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="37656-139">Systemadministrator (Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="37656-139">System Admin (business)</span></span>                          | <span data-ttu-id="37656-140">Richtet externe Systeme für die Verwendung mit Microsoft 365 ein, und verwaltet diese.</span><span class="sxs-lookup"><span data-stu-id="37656-140">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="37656-141">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="37656-141">Information Worker</span></span>                               | <span data-ttu-id="37656-142">Verwaltet den Lebenszyklus der Geschäftsabläufe (HR, Finanzen, IT usw.).</span><span class="sxs-lookup"><span data-stu-id="37656-142">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="37656-143">Einrichten des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="37656-143">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="37656-144">Der Compliance-Administrator erstellt einen Ereignistyp &ndash;, zum Beispiel Ende der Beschäftigung, Vertragsablauf oder Ende der Produktherstellung.</span><span class="sxs-lookup"><span data-stu-id="37656-144">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="37656-145">(Eine schrittweise Anleitung finden Sie unter [Ereignisgesteuerte Aufbewahrung](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="37656-145">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="37656-146">Der Compliance-Administrator erstellt eine Aufbewahrungsbezeichnung auf der Grundlage eines Ereignisses und weist die Bezeichnung einem Ereignistyp zu.</span><span class="sxs-lookup"><span data-stu-id="37656-146">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="37656-147">Es gibt vier Arten von Auslösern für Aufbewahrungsbezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="37656-147">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="37656-148">Erstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="37656-148">Create date</span></span>
                
    2. <span data-ttu-id="37656-149">Zuletzt geändert</span><span class="sxs-lookup"><span data-stu-id="37656-149">Last modified</span></span>
                
    3. <span data-ttu-id="37656-150">Datum der Bezeichnung (Zeitpunkt, zu dem die Inhalte mit der Bezeichnung versehen wurden)</span><span class="sxs-lookup"><span data-stu-id="37656-150">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="37656-151">Ereignis-basiert</span><span class="sxs-lookup"><span data-stu-id="37656-151">Event-based</span></span>
    
3. <span data-ttu-id="37656-152">Der Compliance-Administrator veröffentlicht die Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="37656-152">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="37656-153">Einrichten von SharePoint</span><span class="sxs-lookup"><span data-stu-id="37656-153">Set up SharePoint</span></span>
   
<span data-ttu-id="37656-154">Der Compliance-Administrator geht wie folgt vor, um ein Repository für Datensätze zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="37656-154">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="37656-155">Er erstellt eine SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="37656-155">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="37656-156">Er führt einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="37656-156">Does one of the following:</span></span>
        
    - <span data-ttu-id="37656-p111">Er erstellt eine SharePoint-Bibliothek: er legt eine ereignisbasierte Bezeichnung auf Bibliotheksebene fest. Weitere Informationen finden Sie unter [Anwenden einer Aufbewahrungsbezeichnung auf alle Inhalte in einer Bibliothek, einem Ordner oder einer Dokumentenmappe in SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="37656-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="37656-159">Richtet eine Dokumentenmappe in SharePoint ein.</span><span class="sxs-lookup"><span data-stu-id="37656-159">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="37656-160">Weitere Informationen finden Sie unter [Einführung in Dokumentenmappen](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="37656-160">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="37656-161">Weist jeder Dokumentenmappe eines Mitarbeiters eine Objekt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="37656-161">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="37656-162">Bei einer Objekt-ID handelt es sich um einen Produktnamen oder Code, der von der Organisation verwendet wird; die Mitarbeiternummer kann z. B. eine Objekt-ID sein.</span><span class="sxs-lookup"><span data-stu-id="37656-162">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="37656-163">Durch Zuweisen der Objekt-ID zum Ordner erbt jedes Element in diesem Ordner automatisch dieselbe Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="37656-163">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="37656-164">Dies bedeutet, dass der Aufbewahrungszeitraum aller Elemente durch das gleiche Ereignis ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="37656-164">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="37656-165">Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="37656-165">Ways to trigger event-based retention</span></span>

<span data-ttu-id="37656-166">Es gibt zwei Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung:</span><span class="sxs-lookup"><span data-stu-id="37656-166">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="37656-167">**Verwenden der Benutzeroberfläche des Admin Centers** Dies ist ein Prozess, der verwendet werden kann, um weniger Inhalte gleichzeitig zu speichern, oder wenn Häufigkeit, mit der die Aufbewahrung ausgelöst wird, gering ist, z. B. monatlich oder jährlich.</span><span class="sxs-lookup"><span data-stu-id="37656-167">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="37656-168">Weitere Informationen über diese Methode finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="37656-168">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="37656-169">Allerdings kann diese Methode des Auslösens der Aufbewahrung zeitaufwändig und fehleranfällig sein, wodurch die Skalierbarkeit eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="37656-169">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="37656-170">Daher kann eine automatisierte, nahtlose Lösung zum Auslösen der Aufbewahrung die Datensicherheit und Compliance verbessern.</span><span class="sxs-lookup"><span data-stu-id="37656-170">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="37656-p115">**Mithilfe einer Microsoft 365-REST-API**Dieser Prozess kann verwendet werden, wenn sehr viele Inhalte aufbewahrt werden und/oder die Aufbewahrung häufig ausgelöst wird, zum Beispiel täglich oder wöchentlich. Der Ablauf erkennt, wenn ein Ereignis in Ihrem Branchensystem eintritt, und erstellt automatisch ein zugehöriges Ereignis im Security & Compliance Center. Sie müssen keine Ereignisse in der Benutzeroberfläche manuell erstellen, wenn diese eintreten.</span><span class="sxs-lookup"><span data-stu-id="37656-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="37656-174">Es gibt zwei Optionen für die Verwendung der REST-API:</span><span class="sxs-lookup"><span data-stu-id="37656-174">There are two options for using the REST API:</span></span>

- <span data-ttu-id="37656-175">**Microsoft Flow oder eine ähnliche Anwendung** kann verwendet werden, um das Ereignis automatisch auszulösen.</span><span class="sxs-lookup"><span data-stu-id="37656-175">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="37656-176">Microsoft Flow ist ein Orchestrator zum Herstellen einer Verbindung zu anderen Systemen.</span><span class="sxs-lookup"><span data-stu-id="37656-176">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="37656-177">Für die Verwendung von Microsoft Flow ist keine benutzerdefinierte Lösung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37656-177">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="37656-178">**PowerShell oder ein HTTP-Client zum Aufrufen der REST-API** Sie können PowerShell (Version 6 oder höher) zum Aufrufen der Microsoft 365-REST-API verwenden, um Ereignisse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37656-178">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="37656-179">Bei einer Rest-API handelt es sich um einen Dienstendpunkt, der Gruppen von HTTP-Vorgängen (Methoden) unterstützt, die Zugriff zum Erstellen/Abrufen/Aktualisieren/Löschen der Dienstressourcen bieten.</span><span class="sxs-lookup"><span data-stu-id="37656-179">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="37656-180">Weitere Informationen finden Sie unter [Komponenten einer REST-API-Anfrage/-Anfrage](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="37656-180">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="37656-181">In diesem Fall können mithilfe der Microsoft 365 Rest-API Ereignisse erstellt und mit POST- und GET-Operationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="37656-181">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="37656-182">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="37656-182">Example scenarios</span></span>

<span data-ttu-id="37656-183">Betrachten Sie die folgenden Szenarien.</span><span class="sxs-lookup"><span data-stu-id="37656-183">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="37656-184">Scenario 1: Mitarbeiter tritt aus dem Unternehmen aus</span><span class="sxs-lookup"><span data-stu-id="37656-184">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="37656-185">Eine Organisation erstellt und speichert zahlreiche mitarbeiterbezogene Dokumente pro Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="37656-185">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="37656-186">Diese Dokumente werden während der Beschäftigungsdauer jedes Mitarbeiters verwaltet und aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="37656-186">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="37656-187">Wenn der Mitarbeiter aber die Organisation verlässt oder das Beschäftigungsverhältnis beendet wird, ist die Organisation gemäß gesetzlicher und geschäftlicher Anforderungen verpflichtet, die Dokumente des Mitarbeiters für einen festgelegten Zeitraum aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="37656-187">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="37656-188">Wenn nun täglich mehrere Mitarbeiter aus dem Unternehmen austreten, muss das Unternehmen die Aufbewahrungszeit von Hunderten, wenn nicht Tausenden von Dokumenten pro Tag auslösen.</span><span class="sxs-lookup"><span data-stu-id="37656-188">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="37656-189">Darüber hinaus muss für jeden dieser Mitarbeiter die Aufbewahrungsfrist als Datum des Austritts aus dem Unternehmen + Anzahl der Tage, Monate oder Jahre je nach Art des Mitarbeiterdatensatzes berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="37656-189">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="37656-190">So kann beispielsweise die Vergütung des Mitarbeiters gegenüber den Leistungsanmeldungen desselben Arbeitnehmers eine unterschiedliche Aufbewahrung erfordern.</span><span class="sxs-lookup"><span data-stu-id="37656-190">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="37656-191">Das nachstehende Diagramm zeigt, dass mehrere Beschriftungen vorhanden sein können, die einem einzelnen Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="37656-191">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="37656-192">Hier werden alle Dateien unter der Bezeichnung „Mitarbeitervergütung“ und alle Dateien unter der Bezeichnung „Leistungen“ mit einem einzelnen Ereignis verknüpft, und zwar, dass der Mitarbeiter das Unternehmen verlässt.</span><span class="sxs-lookup"><span data-stu-id="37656-192">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="37656-193">Jede dieser unterschiedlichen Dateien weist unterschiedliche Aufbewahrungszeitpläne auf.</span><span class="sxs-lookup"><span data-stu-id="37656-193">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="37656-194">Wenn ein Mitarbeiter das Unternehmen verlässt, haben diese Dateien innerhalb der einzelnen Bezeichnungen einen anderen Aufbewahrungszeitraum.</span><span class="sxs-lookup"><span data-stu-id="37656-194">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="37656-195">Das Auslösen dieser unterschiedlichen Aufbewahrungszeitpläne für jeden Dateityp oder jede Bezeichnung für jeden Mitarbeiter ist eine große Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="37656-195">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="37656-196">Stellen Sie sich vor, dies für mehrere Mitarbeiter auszuführen.</span><span class="sxs-lookup"><span data-stu-id="37656-196">Imagine doing this for multiple employees.</span></span>

![Diagramm zu Ereignistypen, Ereignissen und Bezeichnungen](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="37656-198">Ein automatisierter Prozess zum Auslösen dieser unterschiedlicher Aufbewahrungszeiten für mehrere Mitarbeiter ist daher zeitsparend, fehlerfrei und äußerst effizient.</span><span class="sxs-lookup"><span data-stu-id="37656-198">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="37656-199">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="37656-199">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aktionen für das Szenario, in dem Mitarbeiter aus dem Unternehmen austreten](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="37656-201">Der Administrator erstellt in der Dokumentenmappe mehrere Mitarbeiterordner, zum Beispiel Jane Doe, John Smith.</span><span class="sxs-lookup"><span data-stu-id="37656-201">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="37656-202">Der Administrator fügt zu jedem Mitarbeiterordner mitarbeiterbezogene Dateien hinzu, zum Beispiel Leistungen, Lohn, Vergütung.</span><span class="sxs-lookup"><span data-stu-id="37656-202">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="37656-203">Der Administrator weist jedem Mitarbeiterordner eine Asset-ID zu.</span><span class="sxs-lookup"><span data-stu-id="37656-203">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="37656-204">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="37656-204">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="37656-205">SCC-Administrator erstellt mitarbeiterbezogene Ereignistypen wie „Beschäftigungsende“, „Einstellung des Mitarbeiters“.</span><span class="sxs-lookup"><span data-stu-id="37656-205">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="37656-206">SCC-Administrator erstellt Bezeichnung „Mitarbeiterbindung“.</span><span class="sxs-lookup"><span data-stu-id="37656-206">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="37656-207">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Dateien des Mitarbeiters in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="37656-207">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="37656-208">Ein HR-Managementsystem wie Workday kann regelmäßig mit Microsoft Flow verwendet werden, um die Dateien von Mitarbeitern zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="37656-208">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="37656-209">Wenn ein Mitarbeiter aus dem Unternehmen ausgetreten ist, löst der Ablauf die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Dateien eines bestimmten Mitarbeiters startet.</span><span class="sxs-lookup"><span data-stu-id="37656-209">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="37656-210">Verwenden von Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="37656-210">Using Microsoft Flow</span></span>

<span data-ttu-id="37656-211">Schritt 1: Erstellen eines Ablaufs zum Erstellen einer Ereignisses mithilfe der Microsoft 365-REST-API</span><span class="sxs-lookup"><span data-stu-id="37656-211">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Verwenden von Flow zum Erstellen eines Ereignisses](../media/automate-event-driven-retention-flow-1.png)

![Verwenden des Ablaufs zum Aufrufen der REST-API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="37656-214">Erstellen eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="37656-214">Create an event</span></span>

<span data-ttu-id="37656-215">Beispielcode zum Aufrufen der REST-API</span><span class="sxs-lookup"><span data-stu-id="37656-215">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="37656-216">Methode</span><span class="sxs-lookup"><span data-stu-id="37656-216">Method</span></span></th>
<th><span data-ttu-id="37656-217">POST</span><span class="sxs-lookup"><span data-stu-id="37656-217">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="37656-218">URL</span><span class="sxs-lookup"><span data-stu-id="37656-218">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-219">Header</span><span class="sxs-lookup"><span data-stu-id="37656-219">Headers</span></span></td>
<td><span data-ttu-id="37656-220">Content-Type</span><span class="sxs-lookup"><span data-stu-id="37656-220">Content-Type</span></span></td>
<td><span data-ttu-id="37656-221">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="37656-221">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37656-222">Body</span><span class="sxs-lookup"><span data-stu-id="37656-222">Body</span></span></td>
<td><p><span data-ttu-id="37656-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-223">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="37656-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="37656-224">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="37656-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="37656-225">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="37656-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-226">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="37656-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-227">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="37656-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-228">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="37656-229">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-229">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="37656-230">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-230">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="37656-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-231">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="37656-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-232">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="37656-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-233">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="37656-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-234">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="37656-235">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-235">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="37656-236">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-236">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="37656-237">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-237">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-238">Authentication</span><span class="sxs-lookup"><span data-stu-id="37656-238">Authentication</span></span></td>
<td><span data-ttu-id="37656-239">Basic</span><span class="sxs-lookup"><span data-stu-id="37656-239">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37656-240">Username</span><span class="sxs-lookup"><span data-stu-id="37656-240">Username</span></span></td>
<td><span data-ttu-id="37656-241">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="37656-241">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-242">Password</span><span class="sxs-lookup"><span data-stu-id="37656-242">Password</span></span></td>
<td><span data-ttu-id="37656-243">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="37656-243">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="37656-244">Verfügbare Parameter</span><span class="sxs-lookup"><span data-stu-id="37656-244">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="37656-245"><strong>Parameter</strong></span><span class="sxs-lookup"><span data-stu-id="37656-245"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="37656-246"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="37656-246"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="37656-247"><strong>Hinweise</strong></span><span class="sxs-lookup"><span data-stu-id="37656-247"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="37656-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-248">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="37656-249">Geben Sie einen eindeutigen Namen für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="37656-249">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="37656-p121">Der Name darf nachfolgende Leerzeichen und die folgenden Zeichen nicht enthalten: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="37656-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-252">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="37656-253">Geben Sie den Namen des Ereignistyps (oder GUID) ein.</span><span class="sxs-lookup"><span data-stu-id="37656-253">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="37656-p122">Beispiel: „Austritt eines Mitarbeiters“. Der Ereignistyp muss mit einer Aufbewahrungsbezeichnung verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="37656-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37656-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-256">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="37656-257">Geben Sie „ComplianceAssetId:“ und die Mitarbeiter-ID ein.</span><span class="sxs-lookup"><span data-stu-id="37656-257">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="37656-258">Beispiel:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-258">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-259">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="37656-260">Datum und Uhrzeit des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="37656-260">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="37656-261">Format: jjjj-MM-ttTHH:mm:ssZ, Beispiel:</span><span class="sxs-lookup"><span data-stu-id="37656-261">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="37656-262">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="37656-262">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="37656-263">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="37656-263">Response codes</span></span>

| <span data-ttu-id="37656-264">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="37656-264">**Response Code**</span></span> | <span data-ttu-id="37656-265">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="37656-265">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="37656-266">302</span><span class="sxs-lookup"><span data-stu-id="37656-266">302</span></span>               | <span data-ttu-id="37656-267">Umleiten</span><span class="sxs-lookup"><span data-stu-id="37656-267">Redirect</span></span>              |
| <span data-ttu-id="37656-268">201</span><span class="sxs-lookup"><span data-stu-id="37656-268">201</span></span>               | <span data-ttu-id="37656-269">Erstellt</span><span class="sxs-lookup"><span data-stu-id="37656-269">Created</span></span>               |
| <span data-ttu-id="37656-270">403</span><span class="sxs-lookup"><span data-stu-id="37656-270">403</span></span>               | <span data-ttu-id="37656-271">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-271">Authorization Failed</span></span>  |
| <span data-ttu-id="37656-272">401</span><span class="sxs-lookup"><span data-stu-id="37656-272">401</span></span>               | <span data-ttu-id="37656-273">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-273">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="37656-274">Abrufen von Ereignissen basierend auf dem Zeitraum</span><span class="sxs-lookup"><span data-stu-id="37656-274">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="37656-275">Methode</span><span class="sxs-lookup"><span data-stu-id="37656-275">Method</span></span></th>
<th><span data-ttu-id="37656-276">GET</span><span class="sxs-lookup"><span data-stu-id="37656-276">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="37656-277">URL</span><span class="sxs-lookup"><span data-stu-id="37656-277">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="37656-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="37656-278">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-279">Header</span><span class="sxs-lookup"><span data-stu-id="37656-279">Headers</span></span></td>
<td><span data-ttu-id="37656-280">Content-Type</span><span class="sxs-lookup"><span data-stu-id="37656-280">Content-Type</span></span></td>
<td><span data-ttu-id="37656-281">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="37656-281">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-282">Authentication</span><span class="sxs-lookup"><span data-stu-id="37656-282">Authentication</span></span></td>
<td><span data-ttu-id="37656-283">Basic</span><span class="sxs-lookup"><span data-stu-id="37656-283">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37656-284">Username</span><span class="sxs-lookup"><span data-stu-id="37656-284">Username</span></span></td>
<td><span data-ttu-id="37656-285">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="37656-285">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37656-286">Password</span><span class="sxs-lookup"><span data-stu-id="37656-286">Password</span></span></td>
<td><span data-ttu-id="37656-287">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="37656-287">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="37656-288">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="37656-288">Response codes</span></span>

| <span data-ttu-id="37656-289">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="37656-289">**Response Code**</span></span> | <span data-ttu-id="37656-290">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="37656-290">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="37656-291">200</span><span class="sxs-lookup"><span data-stu-id="37656-291">200</span></span>               | <span data-ttu-id="37656-292">OK, eine Liste der Ereignisse in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="37656-292">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="37656-293">404</span><span class="sxs-lookup"><span data-stu-id="37656-293">404</span></span>               | <span data-ttu-id="37656-294">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="37656-294">Not found</span></span>                         |
| <span data-ttu-id="37656-295">302</span><span class="sxs-lookup"><span data-stu-id="37656-295">302</span></span>               | <span data-ttu-id="37656-296">Umleiten</span><span class="sxs-lookup"><span data-stu-id="37656-296">Redirect</span></span>                          |
| <span data-ttu-id="37656-297">401</span><span class="sxs-lookup"><span data-stu-id="37656-297">401</span></span>               | <span data-ttu-id="37656-298">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-298">Authorization Failed</span></span>              |
| <span data-ttu-id="37656-299">403</span><span class="sxs-lookup"><span data-stu-id="37656-299">403</span></span>               | <span data-ttu-id="37656-300">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-300">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="37656-301">Abrufen eines Ereignisses nach ID</span><span class="sxs-lookup"><span data-stu-id="37656-301">Get an event by ID</span></span>

| <span data-ttu-id="37656-302">Methode</span><span class="sxs-lookup"><span data-stu-id="37656-302">Method</span></span>         | <span data-ttu-id="37656-303">GET</span><span class="sxs-lookup"><span data-stu-id="37656-303">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="37656-304">URL</span><span class="sxs-lookup"><span data-stu-id="37656-304">URL</span></span>            | <span data-ttu-id="37656-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="37656-305">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="37656-306">Header</span><span class="sxs-lookup"><span data-stu-id="37656-306">Header</span></span>         | <span data-ttu-id="37656-307">Content-Type</span><span class="sxs-lookup"><span data-stu-id="37656-307">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="37656-308">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="37656-308">application/atom+xml</span></span> |
| <span data-ttu-id="37656-309">Authentication</span><span class="sxs-lookup"><span data-stu-id="37656-309">Authentication</span></span> | <span data-ttu-id="37656-310">Basic</span><span class="sxs-lookup"><span data-stu-id="37656-310">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="37656-311">Username</span><span class="sxs-lookup"><span data-stu-id="37656-311">Username</span></span>       | <span data-ttu-id="37656-312">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="37656-312">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="37656-313">Password</span><span class="sxs-lookup"><span data-stu-id="37656-313">Password</span></span>       | <span data-ttu-id="37656-314">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="37656-314">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="37656-315">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="37656-315">Response codes</span></span>

| <span data-ttu-id="37656-316">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="37656-316">**Response Code**</span></span> | <span data-ttu-id="37656-317">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="37656-317">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="37656-318">200</span><span class="sxs-lookup"><span data-stu-id="37656-318">200</span></span>               | <span data-ttu-id="37656-319">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="37656-319">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="37656-320">404</span><span class="sxs-lookup"><span data-stu-id="37656-320">404</span></span>               | <span data-ttu-id="37656-321">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="37656-321">Not found</span></span>                                            |
| <span data-ttu-id="37656-322">302</span><span class="sxs-lookup"><span data-stu-id="37656-322">302</span></span>               | <span data-ttu-id="37656-323">Umleiten</span><span class="sxs-lookup"><span data-stu-id="37656-323">Redirect</span></span>                                             |
| <span data-ttu-id="37656-324">401</span><span class="sxs-lookup"><span data-stu-id="37656-324">401</span></span>               | <span data-ttu-id="37656-325">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-325">Authorization Failed</span></span>                                 |
| <span data-ttu-id="37656-326">403</span><span class="sxs-lookup"><span data-stu-id="37656-326">403</span></span>               | <span data-ttu-id="37656-327">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-327">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="37656-328">Abrufen eines Ereignisses anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="37656-328">Get an event by name</span></span>

| <span data-ttu-id="37656-329">Methode</span><span class="sxs-lookup"><span data-stu-id="37656-329">Method</span></span>         | <span data-ttu-id="37656-330">GET</span><span class="sxs-lookup"><span data-stu-id="37656-330">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="37656-331">URL</span><span class="sxs-lookup"><span data-stu-id="37656-331">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="37656-332">Header</span><span class="sxs-lookup"><span data-stu-id="37656-332">Headers</span></span>        | <span data-ttu-id="37656-333">Content-Type</span><span class="sxs-lookup"><span data-stu-id="37656-333">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="37656-334">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="37656-334">application/atom+xml</span></span> |
| <span data-ttu-id="37656-335">Authentication</span><span class="sxs-lookup"><span data-stu-id="37656-335">Authentication</span></span> | <span data-ttu-id="37656-336">Basic</span><span class="sxs-lookup"><span data-stu-id="37656-336">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="37656-337">Username</span><span class="sxs-lookup"><span data-stu-id="37656-337">Username</span></span>       | <span data-ttu-id="37656-338">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="37656-338">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="37656-339">Password</span><span class="sxs-lookup"><span data-stu-id="37656-339">Password</span></span>       | <span data-ttu-id="37656-340">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="37656-340">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="37656-341">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="37656-341">Response codes</span></span>

| <span data-ttu-id="37656-342">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="37656-342">**Response Code**</span></span> | <span data-ttu-id="37656-343">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="37656-343">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="37656-344">200</span><span class="sxs-lookup"><span data-stu-id="37656-344">200</span></span>               | <span data-ttu-id="37656-345">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="37656-345">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="37656-346">404</span><span class="sxs-lookup"><span data-stu-id="37656-346">404</span></span>               | <span data-ttu-id="37656-347">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="37656-347">Not found</span></span>                                            |
| <span data-ttu-id="37656-348">302</span><span class="sxs-lookup"><span data-stu-id="37656-348">302</span></span>               | <span data-ttu-id="37656-349">Umleiten</span><span class="sxs-lookup"><span data-stu-id="37656-349">Redirect</span></span>                                             |
| <span data-ttu-id="37656-350">401</span><span class="sxs-lookup"><span data-stu-id="37656-350">401</span></span>               | <span data-ttu-id="37656-351">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-351">Authorization Failed</span></span>                                 |
| <span data-ttu-id="37656-352">403</span><span class="sxs-lookup"><span data-stu-id="37656-352">403</span></span>               | <span data-ttu-id="37656-353">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="37656-353">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="37656-354">Verwenden von PowerShell (Version 6 oder höher) oder eines beliebigen HTTP-Clients</span><span class="sxs-lookup"><span data-stu-id="37656-354">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="37656-355">Schritt 1: Stellen Sie eine Verbindung zu PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="37656-355">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="37656-356">Schritt 2: Führen Sie das folgende Skript aus.</span><span class="sxs-lookup"><span data-stu-id="37656-356">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37656-357">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="37656-357">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="37656-358">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-358">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="37656-359">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-359">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="37656-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="37656-360">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="37656-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="37656-361">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="37656-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-362">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="37656-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-363">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="37656-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-364">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="37656-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="37656-365">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="37656-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="37656-366">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="37656-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-367">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="37656-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-368">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="37656-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-369">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="37656-370">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-370">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="37656-371">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-371">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="37656-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-372">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="37656-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-373">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="37656-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-374">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="37656-375">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-375">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="37656-376">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="37656-376">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="37656-377">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-377">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="37656-378">$event = $null</span><span class="sxs-lookup"><span data-stu-id="37656-378">$event = $null</span></span></p>
<p><span data-ttu-id="37656-379">try</span><span class="sxs-lookup"><span data-stu-id="37656-379">try</span></span></p>
<p><span data-ttu-id="37656-380">{</span><span class="sxs-lookup"><span data-stu-id="37656-380">{</span></span></p>
<p><span data-ttu-id="37656-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="37656-381">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="37656-382">}</span><span class="sxs-lookup"><span data-stu-id="37656-382">}</span></span></p>
<p><span data-ttu-id="37656-383">catch</span><span class="sxs-lookup"><span data-stu-id="37656-383">catch</span></span></p>
<p><span data-ttu-id="37656-384">{</span><span class="sxs-lookup"><span data-stu-id="37656-384">{</span></span></p>
<p><span data-ttu-id="37656-385">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="37656-385">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="37656-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="37656-386">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="37656-387">{</span><span class="sxs-lookup"><span data-stu-id="37656-387">{</span></span></p>
<p><span data-ttu-id="37656-388">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="37656-388">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="37656-389">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="37656-389">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="37656-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="37656-390">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="37656-391">}</span><span class="sxs-lookup"><span data-stu-id="37656-391">}</span></span></p>
<p><span data-ttu-id="37656-392">}</span><span class="sxs-lookup"><span data-stu-id="37656-392">}</span></span></p>
<p><span data-ttu-id="37656-393">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="37656-393">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="37656-394">Überprüfen der Ausgabe bei beiden Optionen</span><span class="sxs-lookup"><span data-stu-id="37656-394">Verify the outcome in both options</span></span>

<span data-ttu-id="37656-395">Schritt 1: Wechseln Sie zum Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="37656-395">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="37656-396">Schritt 2: Klicken Sie unter **Informationskontrolle** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="37656-396">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="37656-397">Schritt 3: Überprüfen Sie, ob das Ereignis erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37656-397">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="37656-398">Ebenso können die aufgeführten Optionen zum Automatisieren der ereignisbasierten Aufbewahrung auch für die folgenden Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37656-398">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="37656-399">Szenario 2: Ablauf von Verträgen</span><span class="sxs-lookup"><span data-stu-id="37656-399">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="37656-400">Eine Organisation kann mehrere Datensätze für einen einzigen Vertrag mit Kunden, Lieferanten und Partnern haben.</span><span class="sxs-lookup"><span data-stu-id="37656-400">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="37656-401">Diese Dokumente können sich in einer Dokumentbibliothek wie SharePoint befinden.</span><span class="sxs-lookup"><span data-stu-id="37656-401">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="37656-402">Das Vertragsende bestimmt den Anfang des Aufbewahrungszeitraums der Dokumente, die dem Vertrag zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="37656-402">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="37656-403">So müssen z. B. alle Datensätze im Zusammenhang mit Verträgen fünf Jahre lang ab dem Zeitpunkt aufbewahrt werden, ab dem der Vertrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="37656-403">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="37656-404">Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren ausgelöst, ist der Ablauf des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="37656-404">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="37656-405">Ein CRM-System kann mit Microsoft 365 verwendet werden und die Aufbewahrung für Vertragsdokumente auslösen.</span><span class="sxs-lookup"><span data-stu-id="37656-405">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="37656-406">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="37656-406">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aufgaben für das Szenario zum Ablauf von Verträgen](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="37656-408">Der Administrator erstellt eine SharePoint-Bibliothek mit verschiedenen Ordnern für jeden Vertragstyp.</span><span class="sxs-lookup"><span data-stu-id="37656-408">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="37656-409">Der Administrator fügt Vertragsdateien zu jedem Vertragsordner hinzu, zum Beispiel Lizenzverträge, Entwicklungsverträge.</span><span class="sxs-lookup"><span data-stu-id="37656-409">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="37656-410">Der Administrator weist jedem Vertragsordner eine Objekt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="37656-410">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="37656-411">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="37656-411">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="37656-412">Der SCC-Administrator erstellt vertragsbezogene Ereignisse wie „Erstellung des Vertrags“, „Ablauf des Vertrags“.</span><span class="sxs-lookup"><span data-stu-id="37656-412">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="37656-413">Der SCC-Administrator erstellt die Bezeichnung „Vertragsende“.</span><span class="sxs-lookup"><span data-stu-id="37656-413">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="37656-414">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Vertragsdateien in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="37656-414">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="37656-415">Ein Vertragsmanagementsystem kann mit Microsoft Flow oder einer ähnlichen Anwendung regelmäßig verwendet werden, um Vertragsdateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="37656-415">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="37656-416">Wenn ein Vertrag abläuft, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Vertragsdateien startet.</span><span class="sxs-lookup"><span data-stu-id="37656-416">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="37656-417">Szenario 3: Ende der Produktherstellung</span><span class="sxs-lookup"><span data-stu-id="37656-417">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="37656-p124">Ein Produktionsunternehmen, das verschiedene Produktlinien herstellt, erstellt viele Fertigungsspezifikationen und Preisgestaltungsdokumente. Wenn das Produkt nicht mehr hergestellt wird, müssen alle mit diesem Produkt verknüpften Spezifikationen und Dokumente über einen bestimmten Zeitraum ab Ende der Lebensdauer des Produkts aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="37656-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="37656-420">Ein ERP-System kann mit Microsoft 365 und Microsoft Flow verwendet werden, um die Aufbewahrung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="37656-420">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="37656-421">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="37656-421">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aufgaben für ein Produktlebenszyklusszenario](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="37656-423">Der Administrator erstellt in der Dokumentenmappe Produktordner wie Produkt 1, Produkt 2 usw.</span><span class="sxs-lookup"><span data-stu-id="37656-423">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="37656-424">Der Administrator fügt jedem Produktordner Produktdateien hinzu, zum Beispiel Fertigungsspezifikationen, Produktpreisgestaltung, Produktlizenzierung.</span><span class="sxs-lookup"><span data-stu-id="37656-424">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="37656-425">Der Administrator weist jedem Produktordner eine Objekt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="37656-425">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="37656-426">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="37656-426">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="37656-427">Der SCC-Administrator erstellt produktbezogene Ereignistypen, zum Beispiel „Beginn der Produktherstellung“, „Ende der Produktherstellung“.</span><span class="sxs-lookup"><span data-stu-id="37656-427">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="37656-428">Der SCC-Administrator erstellt die Bezeichnung „Ende der Produktherstellung“.</span><span class="sxs-lookup"><span data-stu-id="37656-428">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="37656-429">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Produktdateien in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="37656-429">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="37656-430">ERP-Systeme können mit Microsoft Flow oder ähnlichen Anwendungen regelmäßig verwendet werden, um Produktdateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="37656-430">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="37656-431">Wenn die Herstellung eines Produkts endet, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Produktdateien startet.</span><span class="sxs-lookup"><span data-stu-id="37656-431">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="37656-432">Anhang</span><span class="sxs-lookup"><span data-stu-id="37656-432">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="37656-433">Verwenden der Redirect 302-Antwortergebnisse zum Aufrufen der REST-API</span><span class="sxs-lookup"><span data-stu-id="37656-433">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="37656-434">Rufen Sie einen POST-Aufbewahrungsereignisaufruf mithilfe der REST-API-URL auf <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (globale Administratorrechte sind erforderlich).</span><span class="sxs-lookup"><span data-stu-id="37656-434">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="37656-p125">Überprüfen Sie den Antwortcode. Wenn dies 302 ist, rufen Sie die Umleitungs-URL aus der Location-Eigenschaft des Antwortheaders ab.</span><span class="sxs-lookup"><span data-stu-id="37656-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="37656-437">Rufen Sie den POST-Aufbewahrungsereignisaufruf erneut mithilfe der Umleitungs-URL auf.</span><span class="sxs-lookup"><span data-stu-id="37656-437">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="37656-438">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="37656-438">Credits</span></span>

<span data-ttu-id="37656-439">Dieses Thema wurde von überprüft von:</span><span class="sxs-lookup"><span data-stu-id="37656-439">This topic was reviewed by:</span></span>

<span data-ttu-id="37656-440">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="37656-440">Antonio Maio</span></span><br/><span data-ttu-id="37656-441">MVP für Microsoft Office-Apps und -Dienste</span><span class="sxs-lookup"><span data-stu-id="37656-441">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="37656-442">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="37656-442">Antonio.Maio@Protiviti.com</span></span>
