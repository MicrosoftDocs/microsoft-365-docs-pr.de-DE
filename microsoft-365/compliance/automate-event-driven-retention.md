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
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068114"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="e5423-103">Automatisieren der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="e5423-103">Automate event-based retention</span></span>

><span data-ttu-id="e5423-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e5423-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e5423-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span><span class="sxs-lookup"><span data-stu-id="e5423-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span></span> <span data-ttu-id="e5423-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span><span class="sxs-lookup"><span data-stu-id="e5423-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span></span> <span data-ttu-id="e5423-107">Retaining only important, pertinent information is key to an organization's success.</span><span class="sxs-lookup"><span data-stu-id="e5423-107">Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="e5423-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e5423-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="e5423-109">Retention can be triggered by using [retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="e5423-109">Retention can be triggered by using [retention labels](labels.md).</span></span> <span data-ttu-id="e5423-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="e5423-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span></span> <span data-ttu-id="e5423-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span><span class="sxs-lookup"><span data-stu-id="e5423-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span></span> <span data-ttu-id="e5423-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span><span class="sxs-lookup"><span data-stu-id="e5423-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="e5423-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span><span class="sxs-lookup"><span data-stu-id="e5423-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span></span> <span data-ttu-id="e5423-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span><span class="sxs-lookup"><span data-stu-id="e5423-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="e5423-115">Event-based retention solves this problem.</span><span class="sxs-lookup"><span data-stu-id="e5423-115">Event-based retention solves this problem.</span></span> <span data-ttu-id="e5423-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span><span class="sxs-lookup"><span data-stu-id="e5423-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="e5423-117">Grundlegendes zur ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="e5423-117">About event-based retention</span></span>

<span data-ttu-id="e5423-118">An organization can be small, medium, or large.</span><span class="sxs-lookup"><span data-stu-id="e5423-118">An organization can be small, medium, or large.</span></span> <span data-ttu-id="e5423-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span><span class="sxs-lookup"><span data-stu-id="e5423-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="e5423-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span><span class="sxs-lookup"><span data-stu-id="e5423-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span></span> <span data-ttu-id="e5423-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span><span class="sxs-lookup"><span data-stu-id="e5423-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span></span> <span data-ttu-id="e5423-122">This process is subject to the different retention policies outlined for the business:</span><span class="sxs-lookup"><span data-stu-id="e5423-122">This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="e5423-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span><span class="sxs-lookup"><span data-stu-id="e5423-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span></span> <span data-ttu-id="e5423-124">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="e5423-124">For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="e5423-125">**The period of retention of content can also be an unknown date**.</span><span class="sxs-lookup"><span data-stu-id="e5423-125">**The period of retention of content can also be an unknown date**.</span></span> <span data-ttu-id="e5423-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="e5423-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="e5423-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="e5423-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span> <span data-ttu-id="e5423-128">This is called event-based retention.</span><span class="sxs-lookup"><span data-stu-id="e5423-128">This is called event-based retention.</span></span> <span data-ttu-id="e5423-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="e5423-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="e5423-130">Einrichten der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="e5423-130">Set up event-based retention</span></span>

<span data-ttu-id="e5423-131">Dieser Abschnitt beinhaltet die für die Aufbewahrung von Inhalten erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="e5423-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="e5423-132">Identifizieren von Rollen</span><span class="sxs-lookup"><span data-stu-id="e5423-132">Identify roles</span></span>

<span data-ttu-id="e5423-133">Identifizieren Sie die verschiedenen Rollen in einem Unternehmen, die Aufgaben für die Datensatzverwaltung ausführen und für eine effektive und effiziente Aufbewahrung von Geschäftsdokumenten verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="e5423-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="e5423-134">Persona</span><span class="sxs-lookup"><span data-stu-id="e5423-134">Persona</span></span> | <span data-ttu-id="e5423-135">Rolle</span><span class="sxs-lookup"><span data-stu-id="e5423-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="e5423-136">Administrator</span><span class="sxs-lookup"><span data-stu-id="e5423-136">Admin</span></span> | <span data-ttu-id="e5423-137">Erstellt Ereignistypen für die Aufbewahrung, Aufbewahrungsbezeichnungen und Repositorys für die Aufbewahrung in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e5423-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="e5423-138">Datensatzverwalter</span><span class="sxs-lookup"><span data-stu-id="e5423-138">Records Manager</span></span>                                  | <span data-ttu-id="e5423-139">Stellt Details zur Einhaltung von Aufbewahrungsrichtlinien und Aufbewahrungszeitplänen bereit.</span><span class="sxs-lookup"><span data-stu-id="e5423-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="e5423-140">Systemadministrator (Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="e5423-140">System Admin (business)</span></span>                          | <span data-ttu-id="e5423-141">Richtet externe Systeme für die Verwendung mit Microsoft 365 ein, und verwaltet diese.</span><span class="sxs-lookup"><span data-stu-id="e5423-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="e5423-142">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="e5423-142">Information Worker</span></span>                               | <span data-ttu-id="e5423-143">Verwaltet den Lebenszyklus der Geschäftsabläufe (HR, Finanzen, IT usw.).</span><span class="sxs-lookup"><span data-stu-id="e5423-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="e5423-144">Einrichten des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e5423-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="e5423-145">Der Compliance-Administrator erstellt einen Ereignistyp &ndash;, zum Beispiel Ende der Beschäftigung, Vertragsablauf oder Ende der Produktherstellung.</span><span class="sxs-lookup"><span data-stu-id="e5423-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="e5423-146">(Eine schrittweise Anleitung finden Sie unter [Ereignisgesteuerte Aufbewahrung](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="e5423-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="e5423-147">Der Compliance-Administrator erstellt eine Aufbewahrungsbezeichnung auf der Grundlage eines Ereignisses und weist die Bezeichnung einem Ereignistyp zu.</span><span class="sxs-lookup"><span data-stu-id="e5423-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="e5423-148">Es gibt vier Arten von Auslösern für Aufbewahrungsbezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="e5423-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="e5423-149">Erstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="e5423-149">Create date</span></span>
                
    2. <span data-ttu-id="e5423-150">Zuletzt geändert</span><span class="sxs-lookup"><span data-stu-id="e5423-150">Last modified</span></span>
                
    3. <span data-ttu-id="e5423-151">Datum der Bezeichnung (Zeitpunkt, zu dem die Inhalte mit der Bezeichnung versehen wurden)</span><span class="sxs-lookup"><span data-stu-id="e5423-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="e5423-152">Ereignis-basiert</span><span class="sxs-lookup"><span data-stu-id="e5423-152">Event-based</span></span>
    
3. <span data-ttu-id="e5423-153">Der Compliance-Administrator veröffentlicht die Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="e5423-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="e5423-154">Einrichten von SharePoint</span><span class="sxs-lookup"><span data-stu-id="e5423-154">Set up SharePoint</span></span>
   
<span data-ttu-id="e5423-155">Der Compliance-Administrator geht wie folgt vor, um ein Repository für Datensätze zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e5423-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="e5423-156">Er erstellt eine SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="e5423-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="e5423-157">Er führt einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e5423-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="e5423-158">Creates a SharePoint library: Set event-based label at the library level.</span><span class="sxs-lookup"><span data-stu-id="e5423-158">Creates a SharePoint library: Set event-based label at the library level.</span></span> <span data-ttu-id="e5423-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="e5423-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="e5423-160">Richtet eine Dokumentenmappe in SharePoint ein.</span><span class="sxs-lookup"><span data-stu-id="e5423-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="e5423-161">Weitere Informationen finden Sie unter [Einführung in Dokumentenmappen](https://support.microsoft.com/de-DE/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span><span class="sxs-lookup"><span data-stu-id="e5423-161">For more information, see [Introduction to document sets](https://support.microsoft.com/de-DE/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="e5423-162">Weist jeder Dokumentenmappe eines Mitarbeiters eine Objekt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="e5423-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="e5423-163">Bei einer Objekt-ID handelt es sich um einen Produktnamen oder Code, der von der Organisation verwendet wird; die Mitarbeiternummer kann z. B. eine Objekt-ID sein.</span><span class="sxs-lookup"><span data-stu-id="e5423-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="e5423-164">Durch Zuweisen der Objekt-ID zum Ordner erbt jedes Element in diesem Ordner automatisch dieselbe Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="e5423-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="e5423-165">Dies bedeutet, dass der Aufbewahrungszeitraum aller Elemente durch das gleiche Ereignis ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5423-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="e5423-166">Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="e5423-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="e5423-167">Es gibt zwei Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung:</span><span class="sxs-lookup"><span data-stu-id="e5423-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="e5423-168">**Verwenden der Benutzeroberfläche des Admin Centers** Dies ist ein Prozess, der verwendet werden kann, um weniger Inhalte gleichzeitig zu speichern, oder wenn Häufigkeit, mit der die Aufbewahrung ausgelöst wird, gering ist, z. B. monatlich oder jährlich.</span><span class="sxs-lookup"><span data-stu-id="e5423-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="e5423-169">Weitere Informationen über diese Methode finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="e5423-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="e5423-170">Allerdings kann diese Methode des Auslösens der Aufbewahrung zeitaufwändig und fehleranfällig sein, wodurch die Skalierbarkeit eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="e5423-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="e5423-171">Daher kann eine automatisierte, nahtlose Lösung zum Auslösen der Aufbewahrung die Datensicherheit und Compliance verbessern.</span><span class="sxs-lookup"><span data-stu-id="e5423-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="e5423-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span><span class="sxs-lookup"><span data-stu-id="e5423-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span></span> <span data-ttu-id="e5423-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e5423-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span></span> <span data-ttu-id="e5423-174">You don't need to manually create an event in the UI each time one occurs.</span><span class="sxs-lookup"><span data-stu-id="e5423-174">You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="e5423-175">Es gibt zwei Optionen für die Verwendung der REST-API:</span><span class="sxs-lookup"><span data-stu-id="e5423-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="e5423-176">**Microsoft Flow oder eine ähnliche Anwendung** kann verwendet werden, um das Ereignis automatisch auszulösen.</span><span class="sxs-lookup"><span data-stu-id="e5423-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="e5423-177">Microsoft Flow ist ein Orchestrator zum Herstellen einer Verbindung zu anderen Systemen.</span><span class="sxs-lookup"><span data-stu-id="e5423-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="e5423-178">Für die Verwendung von Microsoft Flow ist keine benutzerdefinierte Lösung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5423-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="e5423-179">**PowerShell oder ein HTTP-Client zum Aufrufen der REST-API** Sie können PowerShell (Version 6 oder höher) zum Aufrufen der Microsoft 365-REST-API verwenden, um Ereignisse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5423-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="e5423-180">Bei einer Rest-API handelt es sich um einen Dienstendpunkt, der Gruppen von HTTP-Vorgängen (Methoden) unterstützt, die Zugriff zum Erstellen/Abrufen/Aktualisieren/Löschen der Dienstressourcen bieten.</span><span class="sxs-lookup"><span data-stu-id="e5423-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="e5423-181">Weitere Informationen finden Sie unter [Komponenten einer REST-API-Anfrage/-Anfrage](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="e5423-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="e5423-182">In diesem Fall können mithilfe der Microsoft 365 Rest-API Ereignisse erstellt und mit POST- und GET-Operationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5423-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="e5423-183">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="e5423-183">Example scenarios</span></span>

<span data-ttu-id="e5423-184">Betrachten Sie die folgenden Szenarien.</span><span class="sxs-lookup"><span data-stu-id="e5423-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="e5423-185">Scenario 1: Mitarbeiter tritt aus dem Unternehmen aus</span><span class="sxs-lookup"><span data-stu-id="e5423-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="e5423-186">Eine Organisation erstellt und speichert zahlreiche mitarbeiterbezogene Dokumente pro Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="e5423-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="e5423-187">Diese Dokumente werden während der Beschäftigungsdauer jedes Mitarbeiters verwaltet und aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="e5423-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="e5423-188">Wenn der Mitarbeiter aber die Organisation verlässt oder das Beschäftigungsverhältnis beendet wird, ist die Organisation gemäß gesetzlicher und geschäftlicher Anforderungen verpflichtet, die Dokumente des Mitarbeiters für einen festgelegten Zeitraum aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="e5423-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="e5423-189">Wenn nun täglich mehrere Mitarbeiter aus dem Unternehmen austreten, muss das Unternehmen die Aufbewahrungszeit von Hunderten, wenn nicht Tausenden von Dokumenten pro Tag auslösen.</span><span class="sxs-lookup"><span data-stu-id="e5423-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="e5423-190">Darüber hinaus muss für jeden dieser Mitarbeiter die Aufbewahrungsfrist als Datum des Austritts aus dem Unternehmen + Anzahl der Tage, Monate oder Jahre je nach Art des Mitarbeiterdatensatzes berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="e5423-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="e5423-191">So kann beispielsweise die Vergütung des Mitarbeiters gegenüber den Leistungsanmeldungen desselben Arbeitnehmers eine unterschiedliche Aufbewahrung erfordern.</span><span class="sxs-lookup"><span data-stu-id="e5423-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="e5423-192">Das nachstehende Diagramm zeigt, dass mehrere Beschriftungen vorhanden sein können, die einem einzelnen Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e5423-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="e5423-193">Hier werden alle Dateien unter der Bezeichnung „Mitarbeitervergütung“ und alle Dateien unter der Bezeichnung „Leistungen“ mit einem einzelnen Ereignis verknüpft, und zwar, dass der Mitarbeiter das Unternehmen verlässt.</span><span class="sxs-lookup"><span data-stu-id="e5423-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="e5423-194">Jede dieser unterschiedlichen Dateien weist unterschiedliche Aufbewahrungszeitpläne auf.</span><span class="sxs-lookup"><span data-stu-id="e5423-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="e5423-195">Wenn ein Mitarbeiter das Unternehmen verlässt, haben diese Dateien innerhalb der einzelnen Bezeichnungen einen anderen Aufbewahrungszeitraum.</span><span class="sxs-lookup"><span data-stu-id="e5423-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="e5423-196">Das Auslösen dieser unterschiedlichen Aufbewahrungszeitpläne für jeden Dateityp oder jede Bezeichnung für jeden Mitarbeiter ist eine große Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="e5423-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="e5423-197">Stellen Sie sich vor, dies für mehrere Mitarbeiter auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e5423-197">Imagine doing this for multiple employees.</span></span>

![Diagramm zu Ereignistypen, Ereignissen und Bezeichnungen](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="e5423-199">Ein automatisierter Prozess zum Auslösen dieser unterschiedlicher Aufbewahrungszeiten für mehrere Mitarbeiter ist daher zeitsparend, fehlerfrei und äußerst effizient.</span><span class="sxs-lookup"><span data-stu-id="e5423-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="e5423-200">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="e5423-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aktionen für das Szenario, in dem Mitarbeiter aus dem Unternehmen austreten](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="e5423-202">Der Administrator erstellt in der Dokumentenmappe mehrere Mitarbeiterordner, zum Beispiel Jane Doe, John Smith.</span><span class="sxs-lookup"><span data-stu-id="e5423-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="e5423-203">Der Administrator fügt zu jedem Mitarbeiterordner mitarbeiterbezogene Dateien hinzu, zum Beispiel Leistungen, Lohn, Vergütung.</span><span class="sxs-lookup"><span data-stu-id="e5423-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="e5423-204">Der Administrator weist jedem Mitarbeiterordner eine Asset-ID zu.</span><span class="sxs-lookup"><span data-stu-id="e5423-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="e5423-205">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="e5423-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="e5423-206">SCC-Administrator erstellt mitarbeiterbezogene Ereignistypen wie „Beschäftigungsende“, „Einstellung des Mitarbeiters“.</span><span class="sxs-lookup"><span data-stu-id="e5423-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="e5423-207">SCC-Administrator erstellt Bezeichnung „Mitarbeiterbindung“.</span><span class="sxs-lookup"><span data-stu-id="e5423-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="e5423-208">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Dateien des Mitarbeiters in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="e5423-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="e5423-209">Ein HR-Managementsystem wie Workday kann regelmäßig mit Microsoft Flow verwendet werden, um die Dateien von Mitarbeitern zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e5423-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="e5423-210">Wenn ein Mitarbeiter aus dem Unternehmen ausgetreten ist, löst der Ablauf die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Dateien eines bestimmten Mitarbeiters startet.</span><span class="sxs-lookup"><span data-stu-id="e5423-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="e5423-211">Verwenden von Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="e5423-211">Using Microsoft Flow</span></span>

<span data-ttu-id="e5423-212">Schritt 1: Erstellen eines Ablaufs zum Erstellen einer Ereignisses mithilfe der Microsoft 365-REST-API</span><span class="sxs-lookup"><span data-stu-id="e5423-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Verwenden von Flow zum Erstellen eines Ereignisses](../media/automate-event-driven-retention-flow-1.png)

![Verwenden des Ablaufs zum Aufrufen der REST-API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="e5423-215">Erstellen eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e5423-215">Create an event</span></span>

<span data-ttu-id="e5423-216">Beispielcode zum Aufrufen der REST-API:</span><span class="sxs-lookup"><span data-stu-id="e5423-216">Sample code to call the REST API:</span></span>

- <span data-ttu-id="e5423-217">**Method**: POST</span><span class="sxs-lookup"><span data-stu-id="e5423-217">**Method**: POST</span></span>
- <span data-ttu-id="e5423-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="e5423-218">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="e5423-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e5423-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="e5423-220">**Body**:</span><span class="sxs-lookup"><span data-stu-id="e5423-220">**Body**:</span></span>
    
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
- <span data-ttu-id="e5423-221">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e5423-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="e5423-222">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e5423-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="e5423-223">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e5423-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="e5423-224">Verfügbare Parameter</span><span class="sxs-lookup"><span data-stu-id="e5423-224">Available parameters</span></span>


|<span data-ttu-id="e5423-225">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5423-225">Parameters</span></span>|<span data-ttu-id="e5423-226">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5423-226">Description</span></span>|<span data-ttu-id="e5423-227">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e5423-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="e5423-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="e5423-228"><d:Name></d:Name></span></span>|<span data-ttu-id="e5423-229">Geben Sie einen eindeutigen Namen für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="e5423-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="e5423-230">Der Name darf nachfolgende Leerzeichen und die folgenden Zeichen nicht enthalten: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="e5423-230">Cannot contain trailing spaces, and the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="e5423-231">, : ;</span><span class="sxs-lookup"><span data-stu-id="e5423-231">, : ;</span></span>|
|<span data-ttu-id="e5423-232"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="e5423-232"><d:EventType></d:EventType></span></span>|<span data-ttu-id="e5423-233">Geben Sie den Namen des Ereignistyps (oder GUID) ein.</span><span class="sxs-lookup"><span data-stu-id="e5423-233">Enter event type name (or Guid),</span></span>|<span data-ttu-id="e5423-234">Example: “Employee termination”.</span><span class="sxs-lookup"><span data-stu-id="e5423-234">Example: “Employee termination”.</span></span> <span data-ttu-id="e5423-235">Event type has to be associated with a retention label.</span><span class="sxs-lookup"><span data-stu-id="e5423-235">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="e5423-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="e5423-236"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="e5423-237">Geben Sie "ComplianceAssetId:" + Mitarbeiter-ID ein</span><span class="sxs-lookup"><span data-stu-id="e5423-237">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="e5423-238">Beispiel: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="e5423-238">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="e5423-239"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="e5423-239"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="e5423-240">Datum und Uhrzeit des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="e5423-240">Event Date and Time</span></span>|<span data-ttu-id="e5423-241">Format: jjjj-MM-ttTHH:mm:ssZ, Beispiel: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="e5423-241">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="e5423-242">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e5423-242">Response codes</span></span>

| <span data-ttu-id="e5423-243">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e5423-243">Response Code</span></span> | <span data-ttu-id="e5423-244">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5423-244">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="e5423-245">302</span><span class="sxs-lookup"><span data-stu-id="e5423-245">302</span></span>               | <span data-ttu-id="e5423-246">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e5423-246">Redirect</span></span>              |
| <span data-ttu-id="e5423-247">201</span><span class="sxs-lookup"><span data-stu-id="e5423-247">201</span></span>               | <span data-ttu-id="e5423-248">Erstellt</span><span class="sxs-lookup"><span data-stu-id="e5423-248">Created</span></span>               |
| <span data-ttu-id="e5423-249">403</span><span class="sxs-lookup"><span data-stu-id="e5423-249">403</span></span>               | <span data-ttu-id="e5423-250">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-250">Authorization Failed</span></span>  |
| <span data-ttu-id="e5423-251">401</span><span class="sxs-lookup"><span data-stu-id="e5423-251">401</span></span>               | <span data-ttu-id="e5423-252">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-252">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="e5423-253">Abrufen von Ereignissen basierend auf dem Zeitraum</span><span class="sxs-lookup"><span data-stu-id="e5423-253">Get Events based on time range</span></span>

- <span data-ttu-id="e5423-254">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="e5423-254">**Method**: GET</span></span>

- <span data-ttu-id="e5423-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="e5423-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="e5423-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e5423-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="e5423-257">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e5423-257">**Authentication**: Basic</span></span>

- <span data-ttu-id="e5423-258">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e5423-258">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="e5423-259">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e5423-259">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="e5423-260">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e5423-260">Response codes</span></span>

| <span data-ttu-id="e5423-261">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e5423-261">Response Code</span></span> | <span data-ttu-id="e5423-262">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5423-262">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="e5423-263">200</span><span class="sxs-lookup"><span data-stu-id="e5423-263">200</span></span>               | <span data-ttu-id="e5423-264">OK, eine Liste der Ereignisse in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="e5423-264">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="e5423-265">404</span><span class="sxs-lookup"><span data-stu-id="e5423-265">404</span></span>               | <span data-ttu-id="e5423-266">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e5423-266">Not found</span></span>                         |
| <span data-ttu-id="e5423-267">302</span><span class="sxs-lookup"><span data-stu-id="e5423-267">302</span></span>               | <span data-ttu-id="e5423-268">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e5423-268">Redirect</span></span>                          |
| <span data-ttu-id="e5423-269">401</span><span class="sxs-lookup"><span data-stu-id="e5423-269">401</span></span>               | <span data-ttu-id="e5423-270">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-270">Authorization Failed</span></span>              |
| <span data-ttu-id="e5423-271">403</span><span class="sxs-lookup"><span data-stu-id="e5423-271">403</span></span>               | <span data-ttu-id="e5423-272">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-272">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="e5423-273">Abrufen eines Ereignisses nach ID</span><span class="sxs-lookup"><span data-stu-id="e5423-273">Get an event by ID</span></span>

- <span data-ttu-id="e5423-274">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="e5423-274">**Method**: GET</span></span>

- <span data-ttu-id="e5423-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="e5423-275">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="e5423-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e5423-276">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="e5423-277">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e5423-277">**Authentication**: Basic</span></span>

- <span data-ttu-id="e5423-278">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e5423-278">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="e5423-279">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e5423-279">**Password**: "Compliancepassword"</span></span>



##### <a name="response-codes"></a><span data-ttu-id="e5423-280">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e5423-280">Response codes</span></span>

| <span data-ttu-id="e5423-281">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e5423-281">Response Code</span></span> | <span data-ttu-id="e5423-282">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5423-282">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="e5423-283">200</span><span class="sxs-lookup"><span data-stu-id="e5423-283">200</span></span>               | <span data-ttu-id="e5423-284">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="e5423-284">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="e5423-285">404</span><span class="sxs-lookup"><span data-stu-id="e5423-285">404</span></span>               | <span data-ttu-id="e5423-286">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e5423-286">Not found</span></span>                                            |
| <span data-ttu-id="e5423-287">302</span><span class="sxs-lookup"><span data-stu-id="e5423-287">302</span></span>               | <span data-ttu-id="e5423-288">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e5423-288">Redirect</span></span>                                             |
| <span data-ttu-id="e5423-289">401</span><span class="sxs-lookup"><span data-stu-id="e5423-289">401</span></span>               | <span data-ttu-id="e5423-290">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-290">Authorization Failed</span></span>                                 |
| <span data-ttu-id="e5423-291">403</span><span class="sxs-lookup"><span data-stu-id="e5423-291">403</span></span>               | <span data-ttu-id="e5423-292">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-292">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="e5423-293">Abrufen eines Ereignisses anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="e5423-293">Get an event by name</span></span>

- <span data-ttu-id="e5423-294">**Method**: GET</span><span class="sxs-lookup"><span data-stu-id="e5423-294">**Method**: GET</span></span>

- <span data-ttu-id="e5423-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="e5423-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="e5423-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="e5423-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="e5423-297">**Authentication**: Basic</span><span class="sxs-lookup"><span data-stu-id="e5423-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="e5423-298">**Username**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="e5423-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="e5423-299">**Password**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="e5423-299">**Password**: "Compliancepassword"</span></span>


##### <a name="response-codes"></a><span data-ttu-id="e5423-300">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="e5423-300">Response codes</span></span>

| <span data-ttu-id="e5423-301">Antwortcode</span><span class="sxs-lookup"><span data-stu-id="e5423-301">Response Code</span></span> | <span data-ttu-id="e5423-302">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5423-302">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="e5423-303">200</span><span class="sxs-lookup"><span data-stu-id="e5423-303">200</span></span>               | <span data-ttu-id="e5423-304">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="e5423-304">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="e5423-305">404</span><span class="sxs-lookup"><span data-stu-id="e5423-305">404</span></span>               | <span data-ttu-id="e5423-306">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e5423-306">Not found</span></span>                                            |
| <span data-ttu-id="e5423-307">302</span><span class="sxs-lookup"><span data-stu-id="e5423-307">302</span></span>               | <span data-ttu-id="e5423-308">Umleiten</span><span class="sxs-lookup"><span data-stu-id="e5423-308">Redirect</span></span>                                             |
| <span data-ttu-id="e5423-309">401</span><span class="sxs-lookup"><span data-stu-id="e5423-309">401</span></span>               | <span data-ttu-id="e5423-310">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-310">Authorization Failed</span></span>                                 |
| <span data-ttu-id="e5423-311">403</span><span class="sxs-lookup"><span data-stu-id="e5423-311">403</span></span>               | <span data-ttu-id="e5423-312">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="e5423-312">Authentication Failed</span></span>                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a><span data-ttu-id="e5423-313">Verwenden von PowerShell (Version 6 oder höher) oder eines beliebigen HTTP-Clients</span><span class="sxs-lookup"><span data-stu-id="e5423-313">Using PowerShell (version 6 or later) or any HTTP client</span></span>

<span data-ttu-id="e5423-314">Schritt 1: Stellen Sie eine Verbindung zu PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="e5423-314">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="e5423-315">Schritt 2: Führen Sie das folgende Skript aus.</span><span class="sxs-lookup"><span data-stu-id="e5423-315">Step 2: Run the following script.</span></span>

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


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="e5423-316">Überprüfen der Ausgabe bei beiden Optionen</span><span class="sxs-lookup"><span data-stu-id="e5423-316">Verify the outcome in both options</span></span>

<span data-ttu-id="e5423-317">Schritt 1: Wechseln Sie zum Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e5423-317">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="e5423-318">Schritt 2: Klicken Sie unter **Informationskontrolle** auf **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="e5423-318">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="e5423-319">Schritt 3: Überprüfen Sie, ob das Ereignis erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5423-319">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="e5423-320">Ebenso können die aufgeführten Optionen zum Automatisieren der ereignisbasierten Aufbewahrung auch für die folgenden Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5423-320">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="e5423-321">Szenario 2: Ablauf von Verträgen</span><span class="sxs-lookup"><span data-stu-id="e5423-321">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="e5423-322">Eine Organisation kann mehrere Datensätze für einen einzigen Vertrag mit Kunden, Lieferanten und Partnern haben.</span><span class="sxs-lookup"><span data-stu-id="e5423-322">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="e5423-323">Diese Dokumente können sich in einer Dokumentbibliothek wie SharePoint befinden.</span><span class="sxs-lookup"><span data-stu-id="e5423-323">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="e5423-324">Das Vertragsende bestimmt den Anfang des Aufbewahrungszeitraums der Dokumente, die dem Vertrag zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e5423-324">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="e5423-325">So müssen z. B. alle Datensätze im Zusammenhang mit Verträgen fünf Jahre lang ab dem Zeitpunkt aufbewahrt werden, ab dem der Vertrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="e5423-325">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="e5423-326">Das Ereignis, das den Aufbewahrungszeitraum von fünf Jahren ausgelöst, ist der Ablauf des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="e5423-326">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="e5423-327">Ein CRM-System kann mit Microsoft 365 verwendet werden und die Aufbewahrung für Vertragsdokumente auslösen.</span><span class="sxs-lookup"><span data-stu-id="e5423-327">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="e5423-328">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="e5423-328">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aufgaben für das Szenario zum Ablauf von Verträgen](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="e5423-330">Der Administrator erstellt eine SharePoint-Bibliothek mit verschiedenen Ordnern für jeden Vertragstyp.</span><span class="sxs-lookup"><span data-stu-id="e5423-330">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="e5423-331">Der Administrator fügt Vertragsdateien zu jedem Vertragsordner hinzu, zum Beispiel Lizenzverträge, Entwicklungsverträge.</span><span class="sxs-lookup"><span data-stu-id="e5423-331">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="e5423-332">Der Administrator weist jedem Vertragsordner eine Objekt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="e5423-332">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="e5423-333">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="e5423-333">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="e5423-334">Der SCC-Administrator erstellt vertragsbezogene Ereignisse wie „Erstellung des Vertrags“, „Ablauf des Vertrags“.</span><span class="sxs-lookup"><span data-stu-id="e5423-334">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="e5423-335">Der SCC-Administrator erstellt die Bezeichnung „Vertragsende“.</span><span class="sxs-lookup"><span data-stu-id="e5423-335">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="e5423-336">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Vertragsdateien in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="e5423-336">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="e5423-337">Ein Vertragsmanagementsystem kann mit Microsoft Flow oder einer ähnlichen Anwendung regelmäßig verwendet werden, um Vertragsdateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e5423-337">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="e5423-338">Wenn ein Vertrag abläuft, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Vertragsdateien startet.</span><span class="sxs-lookup"><span data-stu-id="e5423-338">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="e5423-339">Szenario 3: Ende der Produktherstellung</span><span class="sxs-lookup"><span data-stu-id="e5423-339">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="e5423-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span><span class="sxs-lookup"><span data-stu-id="e5423-340">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span></span> <span data-ttu-id="e5423-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span><span class="sxs-lookup"><span data-stu-id="e5423-341">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="e5423-342">Ein ERP-System kann mit Microsoft 365 und Microsoft Flow verwendet werden, um die Aufbewahrung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="e5423-342">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="e5423-343">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="e5423-343">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aufgaben für ein Produktlebenszyklusszenario](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="e5423-345">Der Administrator erstellt in der Dokumentenmappe Produktordner wie Produkt 1, Produkt 2 usw.</span><span class="sxs-lookup"><span data-stu-id="e5423-345">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="e5423-346">Der Administrator fügt jedem Produktordner Produktdateien hinzu, zum Beispiel Fertigungsspezifikationen, Produktpreisgestaltung, Produktlizenzierung.</span><span class="sxs-lookup"><span data-stu-id="e5423-346">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="e5423-347">Der Administrator weist jedem Produktordner eine Objekt-ID zu.</span><span class="sxs-lookup"><span data-stu-id="e5423-347">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="e5423-348">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="e5423-348">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="e5423-349">Der SCC-Administrator erstellt produktbezogene Ereignistypen, zum Beispiel „Beginn der Produktherstellung“, „Ende der Produktherstellung“.</span><span class="sxs-lookup"><span data-stu-id="e5423-349">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="e5423-350">Der SCC-Administrator erstellt die Bezeichnung „Ende der Produktherstellung“.</span><span class="sxs-lookup"><span data-stu-id="e5423-350">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="e5423-351">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Produktdateien in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="e5423-351">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="e5423-352">ERP-Systeme können mit Microsoft Flow oder ähnlichen Anwendungen regelmäßig verwendet werden, um Produktdateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e5423-352">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="e5423-353">Wenn die Herstellung eines Produkts endet, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Produktdateien startet.</span><span class="sxs-lookup"><span data-stu-id="e5423-353">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="e5423-354">Anhang</span><span class="sxs-lookup"><span data-stu-id="e5423-354">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="e5423-355">Verwenden der Redirect 302-Antwortergebnisse zum Aufrufen der REST-API</span><span class="sxs-lookup"><span data-stu-id="e5423-355">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="e5423-356">Aufrufen eines POST-Aufbewahrungsereignisaufrufs mithilfe der REST-API-URL: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="e5423-356">Invoke a POST retention event call by using the REST API URL: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
    
    <span data-ttu-id="e5423-357">Globale Administratorberechtigungen sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5423-357">Global administrator permissions are required.</span></span>

2. <span data-ttu-id="e5423-358">Überprüfen Sie den Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="e5423-358">Check the response code.</span></span> <span data-ttu-id="e5423-359">Wenn dies 302 ist, rufen Sie die Umleitungs-URL aus der Location-Eigenschaft des Antwortheaders ab.</span><span class="sxs-lookup"><span data-stu-id="e5423-359">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="e5423-360">Rufen Sie den POST-Aufbewahrungsereignisaufruf erneut mithilfe der Umleitungs-URL auf.</span><span class="sxs-lookup"><span data-stu-id="e5423-360">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="e5423-361">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="e5423-361">Credits</span></span>

<span data-ttu-id="e5423-362">Dieses Thema wurde von überprüft von:</span><span class="sxs-lookup"><span data-stu-id="e5423-362">This topic was reviewed by:</span></span>

<span data-ttu-id="e5423-363">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="e5423-363">Antonio Maio</span></span><br/><span data-ttu-id="e5423-364">MVP für Microsoft Office-Apps und -Dienste</span><span class="sxs-lookup"><span data-stu-id="e5423-364">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="e5423-365">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="e5423-365">Antonio.Maio@Protiviti.com</span></span>
