---
title: Automatisieren der ereignisgesteuerten Aufbewahrung
ms.author: stephow
author: stephow-MSFT
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
ms.openlocfilehash: 3a5dc3efb88eaa4eabe1b01731d17f5ac418f99d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081075"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="637a7-103">Automatisieren der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="637a7-103">Automate event-based retention</span></span>

<span data-ttu-id="637a7-p101">Die explosionsartige Zunahme von Inhalten in Unternehmen und wie erreicht werden kann, dass diese keine Rolle mehr spielt, ist eine ernste Angelegenheit. Um auch weiterhin den Herausforderungen im Zusammenhang mit der Einhaltung gesetzlicher und geschäftlicher Bestimmungen gerecht zu werden, müssen Unternehmen in der Lage sein, wichtige Informationen aufzubewahren und zu schützen und schnell herauszufinden, was relevant ist. Die Aufbewahrung ausschließlich wichtiger, relevanter Informationen ist der Schlüssel zum Erfolg eines Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="637a7-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="637a7-p102">Daher können Unternehmen die Aufbewahrungslösungen im Office 365 Security & Compliance Center nutzen. Aufbewahrung kann mithilfe von [Aufbewahrungsbezeichnungen](labels.md) ausgelöst werden. Eine Aufbewahrungsbezeichnung kann als [Grundlage für den Aufbewahrungszeitraum für ein bestimmtes Ereignis](event-driven-retention.md) dienen. In der Regel basiert der Aufbewahrungszeitraum auf einem bekannten Datum, z. B. dem Erstellungsdatum oder dem Datum der letzten Änderung der Inhalte. Unternehmen müssen jedoch auch Inhalte aufgrund des Eintretens eines Ereignisses entfernen, zum Beispiel 7 Jahre nach dem Austritt eines Mitarbeiters aus dem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="637a7-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="637a7-p103">Um ein ordnungsgemäßes Entfernen der Inhalte sicherzustellen, ist es zwingend erforderlich zu wissen, wann ein Ereignis eintritt. Da die Inhaltsmenge rasant zunimmt, wird es immer schwieriger, Inhalte zeitnah und ordnungsgemäß aufzubewahren und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="637a7-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="637a7-p104">Die ereignisbasierte Aufbewahrung stellt eine Lösung für dieses Problem dar. In diesem Thema wird erläutert, wie Sie Geschäftsprozessabläufe über Ereignisse mithilfe der Microsoft 365-REST-API einrichten können, um die Aufbewahrung zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="637a7-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="637a7-116">Grundlegendes zur ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="637a7-116">About event-based retention</span></span>

<span data-ttu-id="637a7-p105">Es gibt kleine, mittelständige und Großunternehmen. Die Anzahl der Geschäftsdokumente, Rechtsdokumente, Mitarbeiterdateien, Verträgen und Produktdokumenten, die täglich erstellt und verwaltet werden, nimmt dramatisch zu.</span><span class="sxs-lookup"><span data-stu-id="637a7-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="637a7-p106">Zum Beispiel werden täglich Dutzende Mitarbeiter eingestellt, und es verlassen auch Dutzende Mitarbeiter die Unternehmen. Die Personalabteilung erstellt, aktualisiert oder löscht weiterhin mitarbeiterbezogene Dokumente gemäß den Geschäftsanforderungen. Dieser Prozess unterliegt verschiedenen Aufbewahrungsrichtlinien, die für das Unternehmen festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="637a7-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="637a7-p107">**Der Aufbewahrungszeitraum für die Inhalte kann ein bekanntes Datum sein,** z. B. das Datum, an dem der Inhalt erstellt, zuletzt geändert oder mit einer Bezeichnung versehen wurde. Beispiel: Dokumente werden möglicherweise sieben Jahre lang ab Erstellung aufbewahrt und anschließend gelöscht.</span><span class="sxs-lookup"><span data-stu-id="637a7-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="637a7-p108">**Der Aufbewahrungszeitraum für den Inhalt kann auch ein unbekanntes Datum sein**. Mit Aufbewahrungsbezeichnungen können Sie zum Beispiel als Basis für den Aufbewahrungszeitraum ein bestimmtes Ereignis festlegen, zum Beispiel den Austritt eines Mitarbeiters aus dem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="637a7-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="637a7-p109">Mit dem Ereignis wird der Anfang des Aufbewahrungszeitraums ausgelöst. Für alle Inhalte mit einer Bezeichnung, die für diese Art des Ereignisses angewendet wurde, werden die Aufbewahrungsmaßnahmen der Bezeichnung erzwungen. Dies wird auch als ereignisbasierte Aufbewahrung bezeichnet. Weitere Informationen hierzu finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="637a7-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="637a7-128">Einrichten der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="637a7-128">Set up event-based retention</span></span>

<span data-ttu-id="637a7-129">Dieser Abschnitt beinhaltet die für die Aufbewahrung von Inhalten erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="637a7-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="637a7-130">Identifizieren von Rollen</span><span class="sxs-lookup"><span data-stu-id="637a7-130">Identify roles</span></span>

<span data-ttu-id="637a7-131">Identifizieren Sie die verschiedenen Rollen in einem Unternehmen, die Aufgaben für die Datensatzverwaltung ausführen und für eine effektive und effiziente Aufbewahrung von Geschäftsdokumenten verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="637a7-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="637a7-132">**Persona**</span><span class="sxs-lookup"><span data-stu-id="637a7-132">**Persona**</span></span>| <span data-ttu-id="637a7-133">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="637a7-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="637a7-134">Admin</span><span class="sxs-lookup"><span data-stu-id="637a7-134">Admin</span></span> | <span data-ttu-id="637a7-135">Erstellt Ereignistypen für die Aufbewahrung, Aufbewahrungsbezeichnungen und Repositorys für die Aufbewahrung in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="637a7-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="637a7-136">Datensatzverwalter</span><span class="sxs-lookup"><span data-stu-id="637a7-136">Records Manager</span></span>                                  | <span data-ttu-id="637a7-137">Stellt Details zur Einhaltung von Aufbewahrungsrichtlinien und Aufbewahrungszeitplänen bereit.</span><span class="sxs-lookup"><span data-stu-id="637a7-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="637a7-138">Systemadministrator (Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="637a7-138">System Admin (business)</span></span>                          | <span data-ttu-id="637a7-139">Richtet externe Systeme für die Verwendung mit Microsoft 365 ein, und verwaltet diese.</span><span class="sxs-lookup"><span data-stu-id="637a7-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="637a7-140">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="637a7-140">Information Worker</span></span>                               | <span data-ttu-id="637a7-141">Verwaltet den Lebenszyklus der Geschäftsabläufe (HR, Finanzen, IT usw.).</span><span class="sxs-lookup"><span data-stu-id="637a7-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="637a7-142">Einrichten des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="637a7-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="637a7-143">Der Compliance-Administrator erstellt einen Ereignistyp, zum Beispiel Ende der Beschäftigung, Vertragsablauf oder Ende der Produktherstellung (eine schrittweise Anleitung finden Sie unter [Ereignisgesteuerte Aufbewahrung](event-driven-retention.md)).</span><span class="sxs-lookup"><span data-stu-id="637a7-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
1. <span data-ttu-id="637a7-144">Der Compliance-Administrator erstellt eine Aufbewahrungsbezeichnung auf der Grundlage eines Ereignisses und weist die Bezeichnung einem Ereignistyp zu.</span><span class="sxs-lookup"><span data-stu-id="637a7-144">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
1. <span data-ttu-id="637a7-145">Es gibt die 4 Arten von Auslösern für Aufbewahrungsbezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="637a7-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="637a7-146">Erstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="637a7-146">Create date</span></span>
                
    1. <span data-ttu-id="637a7-147">Zuletzt geändert</span><span class="sxs-lookup"><span data-stu-id="637a7-147">Last modified</span></span>
                
    1. <span data-ttu-id="637a7-148">Datum der Bezeichnung (Zeitpunkt, zu dem die Inhalte mit der Bezeichnung versehen wurden)</span><span class="sxs-lookup"><span data-stu-id="637a7-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="637a7-149">Ereignis-basiert</span><span class="sxs-lookup"><span data-stu-id="637a7-149">Event-based</span></span>
    
1. <span data-ttu-id="637a7-150">Der Compliance-Administrator veröffentlicht die Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="637a7-150">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="637a7-151">Einrichten von SharePoint</span><span class="sxs-lookup"><span data-stu-id="637a7-151">Set up SharePoint</span></span>
   
<span data-ttu-id="637a7-152">Der Compliance-Administrator geht wie folgt vor, um ein Repository für Datensätze zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="637a7-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="637a7-153">Er erstellt eine SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="637a7-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="637a7-154">Er führt einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="637a7-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="637a7-p110">Er erstellt eine SharePoint-Bibliothek: er legt eine ereignisbasierte Bezeichnung auf Bibliotheksebene fest. Weitere Informationen finden Sie unter [Anwenden einer Aufbewahrungsbezeichnung auf alle Inhalte in einer Bibliothek, einem Ordner oder einer Dokumentenmappe in SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="637a7-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="637a7-p111">Er richtet einen Dokumentsatz in SharePoint ein. Weitere Informationen finden Sie unter [Einführung in Dokumentenmappen](https://support.office.com/de-DE/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="637a7-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/de-DE/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="637a7-p112">Er weist jeder Dokumentenmappe eine Asset-ID zu (Asset-ID ist ein Produktname oder eine Code, der von dem Unternehmen verwendet wird, eine Mitarbeiternummer kann zum Beispiel eine Asset-ID sein). (Bei Zuweisung einer Asset-ID zu einem Ordner erben alle Elemente in diesem Ordner automatisch die gleiche Asset-ID. Das bedeutet, dass der Aufbewahrungszeitraum für alle Elemente durch dasselbe Ereignis ausgelöst wird.)</span><span class="sxs-lookup"><span data-stu-id="637a7-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="637a7-161">Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="637a7-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="637a7-162">Es gibt zwei Möglichkeiten zum Auslösen der ereignisbasierten Aufbewahrung:</span><span class="sxs-lookup"><span data-stu-id="637a7-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="637a7-p113">**Über die Benutzeroberfläche des Admin Center** Dies ist ein Prozess, der verwendet werden kann, um weniger Inhalte aufzubewahren oder wenn die Aufbewahrung nicht so häufig ausgelöst wird, zum Beispiel monatlich oder jährlich ist. Weitere Informationen zu dieser Methode finden Sie unter [Übersicht über die ereignisgesteuerte Aufbewahrung](event-driven-retention.md). Diese Art der Aufbewahrungsauslösung kann zeitaufwändig und fehleranfällig sein und die Skalierbarkeit beeinträchtigen. Aus diesem Grund kann eine automatisierte, nahtlose Lösung für die Auslösung der Aufbewahrung die Sicherheit und Compliance von Daten verbessern.</span><span class="sxs-lookup"><span data-stu-id="637a7-p113">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="637a7-p114">**Mithilfe einer Microsoft 365-REST-API**Dieser Prozess kann verwendet werden, wenn sehr viele Inhalte aufbewahrt werden und/oder die Aufbewahrung häufig ausgelöst wird, zum Beispiel täglich oder wöchentlich. Der Ablauf erkennt, wenn ein Ereignis in Ihrem Branchensystem eintritt, und erstellt automatisch ein zugehöriges Ereignis im Security & Compliance Center. Sie müssen keine Ereignisse in der Benutzeroberfläche manuell erstellen, wenn diese eintreten.</span><span class="sxs-lookup"><span data-stu-id="637a7-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="637a7-170">Es gibt zwei Optionen für die Verwendung der REST-API:</span><span class="sxs-lookup"><span data-stu-id="637a7-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="637a7-p115">Sie können **Microsoft Flow oder eine ähnliche Anwendung** verwenden, um das Eintreten eines Ereignisses automatisch auszulösen. Microsoft Flow ist ein Orchestrator für die Verbindung zu anderen Systemen. Bei Verwendung von Microsoft Flow ist keine benutzerdefinierte Lösung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="637a7-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="637a7-174">**PowerShell oder ein HTTP-Client zum Aufrufen der REST-API** Sie können PowerShell (Version 6 oder höher) zum Aufrufen der Microsoft 365-REST-API verwenden, um Ereignisse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="637a7-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="637a7-p116">Bei einer REST-API handelt es sich um einen Dienstendpunkt, der Sätze von HTTP-Vorgängen (Methoden) unterstützt, die den Zugriff auf die Ressourcen des Diensts erstellen/abrufen/aktualisieren/löschen. Weitere Informationen finden Sie unter [Komponenten der REST-API-Anforderung/-Antwort](https://docs.microsoft.com/de-DE/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse) . In diesem Fall können mit der Microsoft 365-REST-API über die POST- und GET-Vorgänge (Methoden) Ereignisse erstellt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="637a7-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/de-DE/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="637a7-177">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="637a7-177">Example scenarios</span></span>

<span data-ttu-id="637a7-178">Betrachten Sie die folgenden Szenarien.</span><span class="sxs-lookup"><span data-stu-id="637a7-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="637a7-179">Scenario 1: Mitarbeiter tritt aus dem Unternehmen aus</span><span class="sxs-lookup"><span data-stu-id="637a7-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="637a7-p117">Ein Unternehmen erstellt und speichert pro Mitarbeiter zahlreiche mitarbeiterbezogene Dokumente. Diese Dokumente werden während der Beschäftigung jedes Mitarbeiters verwaltet und aufbewahrt. Wenn der Mitarbeiter jedoch aus dem Unternehmen austritt oder das Arbeitsverhältnis beendet wird, ist das Unternehmen aufgrund gesetzlicher und geschäftlicher Bestimmungen verpflichtet, die Dokumente dieses Mitarbeiters über einen bestimmten Zeitraum aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="637a7-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="637a7-183">Wenn nun täglich mehrere Mitarbeiter aus dem Unternehmen austreten, muss das Unternehmen die Aufbewahrungszeit von Hunderten, wenn nicht Tausenden von Dokumenten pro Tag auslösen.</span><span class="sxs-lookup"><span data-stu-id="637a7-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="637a7-p118">Darüber hinaus muss für jeden dieser Mitarbeiter die Aufbewahrungsfrist als Datum des Austritts aus dem Unternehmen + Anzahl der Tage, Monate oder Jahre je nach Art des Mitarbeiterdatensatzes berechnet werden. So kann beispielsweise die Vergütung des Mitarbeiters gegenüber den Leistungsanmeldungen desselben Arbeitnehmers eine unterschiedliche Aufbewahrung erfordern.</span><span class="sxs-lookup"><span data-stu-id="637a7-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="637a7-p119">Das folgende Diagramm zeigt, wie mehrere Bezeichnungen einem einzelnen Ereignis zugeordnet werden können. Alle Dateien unter der Bezeichnung „Vergütung“ und alle Dateien unter der Bezeichnung „Leistungen an Arbeitnehmer“ sind hier mit einem einzelnen Ereignis verknüpft, und zwar dem Austritt aus dem Unternehmen. Jede dieser verschiedenen Dateien hat unterschiedliche Aufbewahrungszeiten. Wenn also ein Mitarbeiter aus dem Unternehmen austritt, gilt für jede dieser Datei mit einer Bezeichnung eine unterschiedliche Aufbewahrungsdauer.Die Auslösung all dieser unterschiedlichen Aufbewahrungszeiten für jeden Dateityp oder jede Bezeichnung der Mitarbeiter kann eine sehr anspruchsvolle Aufgabe sein. Stellen Sie sich vor, Sie müssen dies für mehrere Mitarbeiter tun.</span><span class="sxs-lookup"><span data-stu-id="637a7-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![Diagramm zu Ereignistypen, Ereignissen und Bezeichnungen](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="637a7-193">Ein automatisierter Prozess zum Auslösen dieser unterschiedlicher Aufbewahrungszeiten für mehrere Mitarbeiter ist daher zeitsparend, fehlerfrei und äußerst effizient.</span><span class="sxs-lookup"><span data-stu-id="637a7-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="637a7-194">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="637a7-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aktionen für das Szenario, in dem Mitarbeiter aus dem Unternehmen austreten](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="637a7-196">Der Administrator erstellt in der Dokumentenmappe mehrere Mitarbeiterordner, zum Beispiel Jane Doe, John Smith.</span><span class="sxs-lookup"><span data-stu-id="637a7-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="637a7-197">Der Administrator fügt zu jedem Mitarbeiterordner mitarbeiterbezogene Dateien hinzu, zum Beispiel Leistungen, Lohn, Vergütung.</span><span class="sxs-lookup"><span data-stu-id="637a7-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="637a7-198">Der Administrator weist jedem Mitarbeiterordner eine Asset-ID zu.</span><span class="sxs-lookup"><span data-stu-id="637a7-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="637a7-199">Der SCC-Administrator</span><span class="sxs-lookup"><span data-stu-id="637a7-199">SCC Admin l</span></span>

  - <span data-ttu-id="637a7-200">Meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="637a7-200">Logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="637a7-201">SCC-Administrator erstellt mitarbeiterbezogene Ereignistypen wie „Beschäftigungsende“, „Einstellung des Mitarbeiters“.</span><span class="sxs-lookup"><span data-stu-id="637a7-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="637a7-202">SCC-Administrator erstellt Bezeichnung „Mitarbeiterbindung“.</span><span class="sxs-lookup"><span data-stu-id="637a7-202">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="637a7-203">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Dateien des Mitarbeiters in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="637a7-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="637a7-204">Ein HR-Managementsystem wie Workday kann regelmäßig mit Microsoft Flow verwendet werden, um die Dateien von Mitarbeitern zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="637a7-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="637a7-205">Wenn ein Mitarbeiter aus dem Unternehmen ausgetreten ist, löst der Ablauf die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Dateien eines bestimmten Mitarbeiters startet.</span><span class="sxs-lookup"><span data-stu-id="637a7-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="637a7-206">Verwenden von Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="637a7-206">Using Microsoft Flow</span></span>

<span data-ttu-id="637a7-207">Schritt 1: Erstellen eines Ablaufs zum Erstellen einer Ereignisses mithilfe der Microsoft 365-REST-API</span><span class="sxs-lookup"><span data-stu-id="637a7-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Verwenden von Flow zum Erstellen eines Ereignisses](media/automate-event-driven-retention-flow-1.png)

![Verwenden des Ablaufs zum Aufrufen der REST-API](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="637a7-210">Erstellen eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="637a7-210">Create an event</span></span>

<span data-ttu-id="637a7-211">Beispielcode zum Aufrufen der REST-API</span><span class="sxs-lookup"><span data-stu-id="637a7-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="637a7-212">Methode</span><span class="sxs-lookup"><span data-stu-id="637a7-212">Method</span></span></th>
<th><span data-ttu-id="637a7-213">POST</span><span class="sxs-lookup"><span data-stu-id="637a7-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="637a7-214">URL</span><span class="sxs-lookup"><span data-stu-id="637a7-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-215">Header</span><span class="sxs-lookup"><span data-stu-id="637a7-215">Headers</span></span></td>
<td><span data-ttu-id="637a7-216">Content-Type</span><span class="sxs-lookup"><span data-stu-id="637a7-216">Content-Type</span></span></td>
<td><span data-ttu-id="637a7-217">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="637a7-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="637a7-218">Body</span><span class="sxs-lookup"><span data-stu-id="637a7-218">Body</span></span></td>
<td><p><span data-ttu-id="637a7-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="637a7-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="637a7-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="637a7-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="637a7-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="637a7-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="637a7-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="637a7-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="637a7-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="637a7-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="637a7-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="637a7-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="637a7-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="637a7-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="637a7-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="637a7-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="637a7-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-234">Authentication</span><span class="sxs-lookup"><span data-stu-id="637a7-234">Authentication</span></span></td>
<td><span data-ttu-id="637a7-235">Basic</span><span class="sxs-lookup"><span data-stu-id="637a7-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="637a7-236">Username</span><span class="sxs-lookup"><span data-stu-id="637a7-236">Username</span></span></td>
<td><span data-ttu-id="637a7-237">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="637a7-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-238">Password</span><span class="sxs-lookup"><span data-stu-id="637a7-238">Password</span></span></td>
<td><span data-ttu-id="637a7-239">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="637a7-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="637a7-240">Verfügbare Parameter</span><span class="sxs-lookup"><span data-stu-id="637a7-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="637a7-241"><strong>Parameter</strong></span><span class="sxs-lookup"><span data-stu-id="637a7-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="637a7-242"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="637a7-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="637a7-243"><strong>Hinweise</strong></span><span class="sxs-lookup"><span data-stu-id="637a7-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="637a7-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="637a7-245">Geben Sie einen eindeutigen Namen für das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="637a7-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="637a7-p120">Der Name darf nachfolgende Leerzeichen und die folgenden Zeichen nicht enthalten: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="637a7-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="637a7-249">Geben Sie den Namen des Ereignistyps (oder GUID) ein.</span><span class="sxs-lookup"><span data-stu-id="637a7-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="637a7-p121">Beispiel: „Austritt eines Mitarbeiters“. Der Ereignistyp muss mit einer Aufbewahrungsbezeichnung verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="637a7-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="637a7-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="637a7-253">Geben Sie „ComplianceAssetId:“ und die Mitarbeiter-ID ein.</span><span class="sxs-lookup"><span data-stu-id="637a7-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="637a7-254">Beispiel:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="637a7-256">Datum und Uhrzeit des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="637a7-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="637a7-257">Format: jjjj-MM-ttTHH:mm:ssZ, Beispiel:</span><span class="sxs-lookup"><span data-stu-id="637a7-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="637a7-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="637a7-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="637a7-259">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="637a7-259">Response codes</span></span>

| <span data-ttu-id="637a7-260">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="637a7-260">**Response Code**</span></span> | <span data-ttu-id="637a7-261">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="637a7-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="637a7-262">302</span><span class="sxs-lookup"><span data-stu-id="637a7-262">302</span></span>               | <span data-ttu-id="637a7-263">Umleiten</span><span class="sxs-lookup"><span data-stu-id="637a7-263">Redirect</span></span>              |
| <span data-ttu-id="637a7-264">201</span><span class="sxs-lookup"><span data-stu-id="637a7-264">201</span></span>               | <span data-ttu-id="637a7-265">Erstellt</span><span class="sxs-lookup"><span data-stu-id="637a7-265">Created</span></span>               |
| <span data-ttu-id="637a7-266">403</span><span class="sxs-lookup"><span data-stu-id="637a7-266">403</span></span>               | <span data-ttu-id="637a7-267">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-267">Authorization Failed</span></span>  |
| <span data-ttu-id="637a7-268">401</span><span class="sxs-lookup"><span data-stu-id="637a7-268">401</span></span>               | <span data-ttu-id="637a7-269">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="637a7-270">Abrufen von Ereignissen basierend auf dem Zeitraum</span><span class="sxs-lookup"><span data-stu-id="637a7-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="637a7-271">Methode</span><span class="sxs-lookup"><span data-stu-id="637a7-271">Method</span></span></th>
<th><span data-ttu-id="637a7-272">GET</span><span class="sxs-lookup"><span data-stu-id="637a7-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="637a7-273">URL</span><span class="sxs-lookup"><span data-stu-id="637a7-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="637a7-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="637a7-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-275">Header</span><span class="sxs-lookup"><span data-stu-id="637a7-275">Headers</span></span></td>
<td><span data-ttu-id="637a7-276">Content-Type</span><span class="sxs-lookup"><span data-stu-id="637a7-276">Content-Type</span></span></td>
<td><span data-ttu-id="637a7-277">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="637a7-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-278">Authentication</span><span class="sxs-lookup"><span data-stu-id="637a7-278">Authentication</span></span></td>
<td><span data-ttu-id="637a7-279">Basic</span><span class="sxs-lookup"><span data-stu-id="637a7-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="637a7-280">Username</span><span class="sxs-lookup"><span data-stu-id="637a7-280">Username</span></span></td>
<td><span data-ttu-id="637a7-281">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="637a7-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="637a7-282">Password</span><span class="sxs-lookup"><span data-stu-id="637a7-282">Password</span></span></td>
<td><span data-ttu-id="637a7-283">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="637a7-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="637a7-284">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="637a7-284">Response codes</span></span>

| <span data-ttu-id="637a7-285">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="637a7-285">**Response Code**</span></span> | <span data-ttu-id="637a7-286">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="637a7-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="637a7-287">200</span><span class="sxs-lookup"><span data-stu-id="637a7-287">200</span></span>               | <span data-ttu-id="637a7-288">OK, eine Liste der Ereignisse in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="637a7-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="637a7-289">404</span><span class="sxs-lookup"><span data-stu-id="637a7-289">404</span></span>               | <span data-ttu-id="637a7-290">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="637a7-290">Not found</span></span>                         |
| <span data-ttu-id="637a7-291">302</span><span class="sxs-lookup"><span data-stu-id="637a7-291">302</span></span>               | <span data-ttu-id="637a7-292">Umleiten</span><span class="sxs-lookup"><span data-stu-id="637a7-292">Redirect</span></span>                          |
| <span data-ttu-id="637a7-293">401</span><span class="sxs-lookup"><span data-stu-id="637a7-293">401</span></span>               | <span data-ttu-id="637a7-294">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-294">Authorization Failed</span></span>              |
| <span data-ttu-id="637a7-295">403</span><span class="sxs-lookup"><span data-stu-id="637a7-295">403</span></span>               | <span data-ttu-id="637a7-296">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="637a7-297">Abrufen eines Ereignisses nach ID</span><span class="sxs-lookup"><span data-stu-id="637a7-297">Get an event by ID</span></span>

| <span data-ttu-id="637a7-298">Methode</span><span class="sxs-lookup"><span data-stu-id="637a7-298">Method</span></span>         | <span data-ttu-id="637a7-299">GET</span><span class="sxs-lookup"><span data-stu-id="637a7-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="637a7-300">URL</span><span class="sxs-lookup"><span data-stu-id="637a7-300">URL</span></span>            | <span data-ttu-id="637a7-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="637a7-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="637a7-302">Header</span><span class="sxs-lookup"><span data-stu-id="637a7-302">Header</span></span>         | <span data-ttu-id="637a7-303">Content-Type</span><span class="sxs-lookup"><span data-stu-id="637a7-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="637a7-304">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="637a7-304">application/atom+xml</span></span> |
| <span data-ttu-id="637a7-305">Authentication</span><span class="sxs-lookup"><span data-stu-id="637a7-305">Authentication</span></span> | <span data-ttu-id="637a7-306">Basic</span><span class="sxs-lookup"><span data-stu-id="637a7-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="637a7-307">Username</span><span class="sxs-lookup"><span data-stu-id="637a7-307">Username</span></span>       | <span data-ttu-id="637a7-308">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="637a7-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="637a7-309">Password</span><span class="sxs-lookup"><span data-stu-id="637a7-309">Password</span></span>       | <span data-ttu-id="637a7-310">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="637a7-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="637a7-311">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="637a7-311">Response codes</span></span>

| <span data-ttu-id="637a7-312">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="637a7-312">**Response Code**</span></span> | <span data-ttu-id="637a7-313">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="637a7-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="637a7-314">200</span><span class="sxs-lookup"><span data-stu-id="637a7-314">200</span></span>               | <span data-ttu-id="637a7-315">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="637a7-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="637a7-316">404</span><span class="sxs-lookup"><span data-stu-id="637a7-316">404</span></span>               | <span data-ttu-id="637a7-317">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="637a7-317">Not found</span></span>                                            |
| <span data-ttu-id="637a7-318">302</span><span class="sxs-lookup"><span data-stu-id="637a7-318">302</span></span>               | <span data-ttu-id="637a7-319">Umleiten</span><span class="sxs-lookup"><span data-stu-id="637a7-319">Redirect</span></span>                                             |
| <span data-ttu-id="637a7-320">401</span><span class="sxs-lookup"><span data-stu-id="637a7-320">401</span></span>               | <span data-ttu-id="637a7-321">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="637a7-322">403</span><span class="sxs-lookup"><span data-stu-id="637a7-322">403</span></span>               | <span data-ttu-id="637a7-323">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="637a7-324">Abrufen eines Ereignisses anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="637a7-324">Get an event by name</span></span>

| <span data-ttu-id="637a7-325">Methode</span><span class="sxs-lookup"><span data-stu-id="637a7-325">Method</span></span>         | <span data-ttu-id="637a7-326">GET</span><span class="sxs-lookup"><span data-stu-id="637a7-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="637a7-327">URL</span><span class="sxs-lookup"><span data-stu-id="637a7-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="637a7-328">Header</span><span class="sxs-lookup"><span data-stu-id="637a7-328">Headers</span></span>        | <span data-ttu-id="637a7-329">Content-Type</span><span class="sxs-lookup"><span data-stu-id="637a7-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="637a7-330">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="637a7-330">application/atom+xml</span></span> |
| <span data-ttu-id="637a7-331">Authentication</span><span class="sxs-lookup"><span data-stu-id="637a7-331">Authentication</span></span> | <span data-ttu-id="637a7-332">Basic</span><span class="sxs-lookup"><span data-stu-id="637a7-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="637a7-333">Username</span><span class="sxs-lookup"><span data-stu-id="637a7-333">Username</span></span>       | <span data-ttu-id="637a7-334">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="637a7-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="637a7-335">Password</span><span class="sxs-lookup"><span data-stu-id="637a7-335">Password</span></span>       | <span data-ttu-id="637a7-336">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="637a7-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="637a7-337">Antwortcodes</span><span class="sxs-lookup"><span data-stu-id="637a7-337">Response codes</span></span>

| <span data-ttu-id="637a7-338">**Antwortcode**</span><span class="sxs-lookup"><span data-stu-id="637a7-338">**Response Code**</span></span> | <span data-ttu-id="637a7-339">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="637a7-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="637a7-340">200</span><span class="sxs-lookup"><span data-stu-id="637a7-340">200</span></span>               | <span data-ttu-id="637a7-341">OK, der Antworttext enthält das Ereignis in Atom + XML</span><span class="sxs-lookup"><span data-stu-id="637a7-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="637a7-342">404</span><span class="sxs-lookup"><span data-stu-id="637a7-342">404</span></span>               | <span data-ttu-id="637a7-343">Nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="637a7-343">Not found</span></span>                                            |
| <span data-ttu-id="637a7-344">302</span><span class="sxs-lookup"><span data-stu-id="637a7-344">302</span></span>               | <span data-ttu-id="637a7-345">Umleiten</span><span class="sxs-lookup"><span data-stu-id="637a7-345">Redirect</span></span>                                             |
| <span data-ttu-id="637a7-346">401</span><span class="sxs-lookup"><span data-stu-id="637a7-346">401</span></span>               | <span data-ttu-id="637a7-347">Autorisierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="637a7-348">403</span><span class="sxs-lookup"><span data-stu-id="637a7-348">403</span></span>               | <span data-ttu-id="637a7-349">Authentifizierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="637a7-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="637a7-350">Verwenden von PowerShell (Version 6 oder höher) oder eines beliebigen HTTP-Clients</span><span class="sxs-lookup"><span data-stu-id="637a7-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="637a7-351">Schritt 1: Stellen Sie eine Verbindung zu PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="637a7-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="637a7-352">Schritt 2: Führen Sie das folgende Skript aus.</span><span class="sxs-lookup"><span data-stu-id="637a7-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="637a7-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="637a7-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="637a7-354">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="637a7-355">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="637a7-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="637a7-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="637a7-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="637a7-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="637a7-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="637a7-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="637a7-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="637a7-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="637a7-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="637a7-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="637a7-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="637a7-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="637a7-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="637a7-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="637a7-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="637a7-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="637a7-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="637a7-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="637a7-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="637a7-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="637a7-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="637a7-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="637a7-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="637a7-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="637a7-374">$event = $null</span></span></p>
<p><span data-ttu-id="637a7-375">try</span><span class="sxs-lookup"><span data-stu-id="637a7-375">try</span></span></p>
<p><span data-ttu-id="637a7-376">{</span><span class="sxs-lookup"><span data-stu-id="637a7-376">{</span></span></p>
<p><span data-ttu-id="637a7-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="637a7-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="637a7-378">}</span><span class="sxs-lookup"><span data-stu-id="637a7-378">}</span></span></p>
<p><span data-ttu-id="637a7-379">catch</span><span class="sxs-lookup"><span data-stu-id="637a7-379">catch</span></span></p>
<p><span data-ttu-id="637a7-380">{</span><span class="sxs-lookup"><span data-stu-id="637a7-380">{</span></span></p>
<p><span data-ttu-id="637a7-381">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="637a7-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="637a7-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="637a7-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="637a7-383">{</span><span class="sxs-lookup"><span data-stu-id="637a7-383">{</span></span></p>
<p><span data-ttu-id="637a7-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="637a7-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="637a7-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="637a7-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="637a7-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="637a7-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="637a7-387">}</span><span class="sxs-lookup"><span data-stu-id="637a7-387">}</span></span></p>
<p><span data-ttu-id="637a7-388">}</span><span class="sxs-lookup"><span data-stu-id="637a7-388">}</span></span></p>
<p><span data-ttu-id="637a7-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="637a7-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="637a7-390">Überprüfen der Ausgabe bei beiden Optionen</span><span class="sxs-lookup"><span data-stu-id="637a7-390">Verify the outcome in both options</span></span>

<span data-ttu-id="637a7-391">Schritt 1: Wechseln Sie zu Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="637a7-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="637a7-392">Schritt 2: Klicken Sie unter Datenkontrolle auf Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="637a7-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="637a7-393">Schritt 3: Überprüfen Sie, ob das Ereignis erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="637a7-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="637a7-394">Ebenso können die aufgeführten Optionen zum Automatisieren der ereignisbasierten Aufbewahrung auch für die folgenden Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="637a7-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="637a7-395">Szenario 2: Ablauf von Verträgen</span><span class="sxs-lookup"><span data-stu-id="637a7-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="637a7-p122">Ein Unternehmen kann mehrere Datensätze für einen einzigen Vertrag mit Kunden, Lieferanten und Partnern haben. Diese Dokumente können sich in einer Dokumentenbibliothek wie SharePoint befinden. Das Ende eines Vertrages bestimmt den Beginn des Aufbewahrungszeitraums der Dokumente, die mit dem Vertrag verknüpft sind. Zum Beispiel: Alle Datensätze, die sich auf die Verträge beziehen, müssen fünf Jahre lang ab Ablauf des Vertrages aufbewahrt werden. Das Ereignis, das die fünfjährige Aufbewahrungsdauer auslöst, ist der Ablauf des Vertrages.</span><span class="sxs-lookup"><span data-stu-id="637a7-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="637a7-401">Ein CRM-System kann mit Microsoft 365 verwendet werden und die Aufbewahrung für Vertragsdokumente auslösen.</span><span class="sxs-lookup"><span data-stu-id="637a7-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="637a7-402">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="637a7-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aufgaben für das Szenario zum Ablauf von Verträgen](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="637a7-404">Der Administrator erstellt eine SharePoint-Bibliothek mit verschiedenen Ordnern für jeden Vertragstyp.</span><span class="sxs-lookup"><span data-stu-id="637a7-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="637a7-405">Der Administrator fügt Vertragsdateien zu jedem Vertragsordner hinzu, zum Beispiel Lizenzverträge, Entwicklungsverträge.</span><span class="sxs-lookup"><span data-stu-id="637a7-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="637a7-406">Der Administrator weist jedem Vertragsordner eine Asset-ID zu.</span><span class="sxs-lookup"><span data-stu-id="637a7-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="637a7-407">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="637a7-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="637a7-408">Der SCC-Administrator erstellt vertragsbezogene Ereignisse wie „Erstellung des Vertrags“, „Ablauf des Vertrags“.</span><span class="sxs-lookup"><span data-stu-id="637a7-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="637a7-409">Der SCC-Administrator erstellt die Bezeichnung „Vertragsende“.</span><span class="sxs-lookup"><span data-stu-id="637a7-409">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="637a7-410">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Vertragsdateien in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="637a7-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="637a7-411">Ein Vertragsmanagementsystem kann mit Microsoft Flow oder einer ähnlichen Anwendung regelmäßig verwendet werden, um Vertragsdateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="637a7-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="637a7-412">Wenn ein Vertrag abläuft, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Vertragsdateien startet.</span><span class="sxs-lookup"><span data-stu-id="637a7-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="637a7-413">Szenario 3: Ende der Produktherstellung</span><span class="sxs-lookup"><span data-stu-id="637a7-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="637a7-p123">Ein Produktionsunternehmen, das verschiedene Produktlinien herstellt, erstellt viele Fertigungsspezifikationen und Preisgestaltungsdokumente. Wenn das Produkt nicht mehr hergestellt wird, müssen alle mit diesem Produkt verknüpften Spezifikationen und Dokumente über einen bestimmten Zeitraum ab Ende der Lebensdauer des Produkts aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="637a7-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="637a7-416">Ein ERP-System kann mit Microsoft 365 und Microsoft Flow verwendet werden, um die Aufbewahrung auszulösen.</span><span class="sxs-lookup"><span data-stu-id="637a7-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="637a7-417">**Konfigurieren der automatisierten ereignisbasierten Aufbewahrung für dieses Szenario:**</span><span class="sxs-lookup"><span data-stu-id="637a7-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagramm zu Rollen und Aufgaben für ein Produktlebenszyklusszenario](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="637a7-419">Der Administrator erstellt in der Dokumentenmappe Produktordner wie Produkt 1, Produkt 2 usw.</span><span class="sxs-lookup"><span data-stu-id="637a7-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="637a7-420">Der Administrator fügt jedem Produktordner Produktdateien hinzu, zum Beispiel Fertigungsspezifikationen, Produktpreisgestaltung, Produktlizenzierung.</span><span class="sxs-lookup"><span data-stu-id="637a7-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="637a7-421">Der Administrator weist jedem Produktordner eine Asset-ID zu.</span><span class="sxs-lookup"><span data-stu-id="637a7-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="637a7-422">Der SCC-Administrator meldet sich beim Security & Compliance Center an.</span><span class="sxs-lookup"><span data-stu-id="637a7-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="637a7-423">Der SCC-Administrator erstellt produktbezogene Ereignistypen, zum Beispiel „Beginn der Produktherstellung“, „Ende der Produktherstellung“.</span><span class="sxs-lookup"><span data-stu-id="637a7-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="637a7-424">Der SCC-Administrator erstellt die Bezeichnung „Ende der Produktherstellung“.</span><span class="sxs-lookup"><span data-stu-id="637a7-424">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="637a7-425">Diese Bezeichnung wird veröffentlicht und manuell oder automatisch auf die Produktdateien in SharePoint angewendet.</span><span class="sxs-lookup"><span data-stu-id="637a7-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="637a7-426">ERP-Systeme können mit Microsoft Flow oder ähnlichen Anwendungen regelmäßig verwendet werden, um Produktdateien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="637a7-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="637a7-427">Wenn die Herstellung eines Produkts endet, löst Microsoft Flow die Microsoft 365-REST-API für die ereignisbasierte Aufbewahrung aus, die den Aufbewahrungszeitraum für die Produktdateien startet.</span><span class="sxs-lookup"><span data-stu-id="637a7-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="637a7-428">Anhang</span><span class="sxs-lookup"><span data-stu-id="637a7-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="637a7-429">Verwenden der Redirect 302-Antwortergebnisse zum Aufrufen der REST-API</span><span class="sxs-lookup"><span data-stu-id="637a7-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="637a7-430">Rufen Sie einen POST-Aufbewahrungsereignisaufruf mithilfe der REST-API-URL auf <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (globale Administratorrechte sind erforderlich).</span><span class="sxs-lookup"><span data-stu-id="637a7-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="637a7-p124">Überprüfen Sie den Antwortcode. Wenn dies 302 ist, rufen Sie die Umleitungs-URL aus der Location-Eigenschaft des Antwortheaders ab.</span><span class="sxs-lookup"><span data-stu-id="637a7-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="637a7-433">Rufen Sie den POST-Aufbewahrungsereignisaufruf erneut mithilfe der Umleitungs-URL auf.</span><span class="sxs-lookup"><span data-stu-id="637a7-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="637a7-434">Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="637a7-434">Credits</span></span>

<span data-ttu-id="637a7-435">Dieses Thema wurde von überprüft von:</span><span class="sxs-lookup"><span data-stu-id="637a7-435">This topic was reviewed by:</span></span>

<span data-ttu-id="637a7-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="637a7-436">Antonio Maio</span></span><br/><span data-ttu-id="637a7-437">MVP für Microsoft Office-Apps und -Dienste</span><span class="sxs-lookup"><span data-stu-id="637a7-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="637a7-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="637a7-438">Antonio.Maio@Protiviti.com</span></span>
