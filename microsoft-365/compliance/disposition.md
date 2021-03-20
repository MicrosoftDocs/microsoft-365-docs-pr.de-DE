---
title: Disposition von Inhalten
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
description: Überwachen und Verwalten der Entsorgung von Inhalten, unabhängig davon, ob Sie die Löschungsprüfung verwenden oder Inhalte automatisch entsprechend den von Ihnen konfigurierten Einstellungen gelöscht werden.
ms.openlocfilehash: d2c2e4e469efe16277f34a902f6720dc2b39e908
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918041"
---
# <a name="disposition-of-content"></a><span data-ttu-id="06ba4-103">Disposition von Inhalten</span><span class="sxs-lookup"><span data-stu-id="06ba4-103">Disposition of content</span></span>

><span data-ttu-id="06ba4-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="06ba4-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="06ba4-105">Verwenden Sie die Registerkarte **Disposition** aus der **Datensatzverwaltung** im Microsoft 365 Compliance Center, um die Löschungsprüfungen zu verwalten und [Datensätze](records-management.md#records) anzuzeigen, die am Ende des Aufbewahrungszeitraums automatisch gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="06ba4-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="06ba4-106">Voraussetzungen für die Anzeige von Inhaltsdispositionen</span><span class="sxs-lookup"><span data-stu-id="06ba4-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="06ba4-107">Zum Verwalten von Löschungsprüfungen und zum bestätigen, dass Datensätze gelöscht wurden, müssen Sie über ausreichende Berechtigungen verfügen, und die Überwachung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="06ba4-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="06ba4-108">Berechtigungen für Dispositionen</span><span class="sxs-lookup"><span data-stu-id="06ba4-108">Permissions for disposition</span></span>

<span data-ttu-id="06ba4-109">Wenn Sie im Microsoft 365 Compliance Center auf die Registerkarte **Disposition** erfolgreich zugreifen möchten, müssen die Benutzer über die Administratorrolle der **Dispositionsverwaltung** verfügen.</span><span class="sxs-lookup"><span data-stu-id="06ba4-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="06ba4-110">Ab Dezember 2020 ist diese Rolle nun in der Standardadministrator-Rollengruppe **Datensatzverwaltung** enthalten.</span><span class="sxs-lookup"><span data-stu-id="06ba4-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="06ba4-111">Die Rolle **Dispositionsverwaltung** wird einem globalen Administrator standardmäßig nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="06ba4-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="06ba4-112">Um Benutzern nur die Berechtigungen zu gewähren, die sie für Dispositionsprüfungen benötigen, ohne ihnen Berechtigungen zum Anzeigen und Konfigurieren anderer Features für die Aufbewahrung und die Datensatzverwaltung zu gewähren, erstellen Sie eine benutzerdefinierte Rollengruppe (z. B. mit dem Namen „Dispositionsprüfer“) und gewähren dieser Gruppe die Rolle „Dispositionsverwaltung“.</span><span class="sxs-lookup"><span data-stu-id="06ba4-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="06ba4-113">Um den Inhalt von Elementen während des Dispositionsvorgangs anzuzeigen, fügen Sie zusätzlich Benutzer zu den folgenden beiden Rollengruppen hinzu: **Inhalts-Explorer-Inhaltsanzeige** und **Inhalts-Explorer-Listenanzeige**.</span><span class="sxs-lookup"><span data-stu-id="06ba4-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="06ba4-114">Verfügen Benutzer nicht über die Berechtigungen dieser Rollengruppen, können sie zwar trotzdem eine Löschungsprüfungsaktion auswählen, um die Löschungsprüfung abzuschließen, müssen dies jedoch tun, ohne den Inhalt des Artikels im Compliance Center anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="06ba4-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="06ba4-115">Anweisungen zum Konfigurieren dieser Berechtigungen finden Sie unter [Gewähren des Zugriffs auf das Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="06ba4-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="06ba4-116">Überwachung aktivieren</span><span class="sxs-lookup"><span data-stu-id="06ba4-116">Enable auditing</span></span>

<span data-ttu-id="06ba4-117">Vergewissern Sie sich, dass die Überwachung mindestens einen Tag vor der ersten Dispositionsaktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="06ba4-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="06ba4-118">Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="06ba4-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="06ba4-119">Löschungsprüfungen</span><span class="sxs-lookup"><span data-stu-id="06ba4-119">Disposition reviews</span></span>

<span data-ttu-id="06ba4-120">Wenn Inhalte das Ende des Aufbewahrungszeitraums erreichen, kann es verschiedene Gründe geben, die Inhalte zu überprüfen und sicherzustellen, dass sie endgültig gelöscht („verworfen“) werden können.</span><span class="sxs-lookup"><span data-stu-id="06ba4-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed").</span></span> <span data-ttu-id="06ba4-121">Anstatt den Inhalt zu löschen, ist es möglicherweise erforderlich, folgende Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="06ba4-121">For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="06ba4-122">Aussetzten der Löschung relevanter Inhalte im Falle eines Rechtsstreits oder einer Prüfung.</span><span class="sxs-lookup"><span data-stu-id="06ba4-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>

- <span data-ttu-id="06ba4-123">Zuweisen eines anderen Aufbewahrungszeitraums für die Inhalte, vielleicht, weil die ursprünglichen Aufbewahrungseinstellungen eine vorübergehende oder vorläufige Lösung waren.</span><span class="sxs-lookup"><span data-stu-id="06ba4-123">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="06ba4-124">Verschieben des Inhalts von seinem bisherigen Speicherort an einen Archivspeicherort, z. B. wenn dieser Inhalt von wissenschaftlichem oder historischem Wert ist.</span><span class="sxs-lookup"><span data-stu-id="06ba4-124">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="06ba4-125">Wenn am Ende des Aufbewahrungszeitraums eine Löschungsprüfung ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="06ba4-125">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="06ba4-126">Die von Ihnen ausgewählten Personen erhalten eine E-Mail-Benachrichtigung, dass für sie Inhalte zur Überprüfung bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="06ba4-126">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="06ba4-127">Bei diesen Prüfern kann es sich um einzelne Benutzer oder E-Mail-aktivierte Sicherheitsgruppen handeln.</span><span class="sxs-lookup"><span data-stu-id="06ba4-127">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="06ba4-128">Beachten Sie, dass Benachrichtigungen wöchentlich gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="06ba4-128">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="06ba4-129">Die Bearbeiter wechseln im Microsoft 365 Compliance Center zur Registerkarte **Disposition**, um den Inhalt zu überprüfen und zu entscheiden, ob er endgültig gelöscht, der Aufbewahrungszeitraum verlängert oder ein anderes Aufbewahrungsetikett angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06ba4-129">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="06ba4-130">Eine Löschungsprüfung kann Inhalte in Exchange-Postfächern, SharePoint-Websites, OneDrive-Konten und Microsoft 365-Gruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="06ba4-130">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="06ba4-131">Inhalte, die an diesen Speicherorten auf eine Löschungsprüfung warten, werden erst gelöscht, nachdem ein Prüfer die endgültige Löschung der Inhalte verfügt hat.</span><span class="sxs-lookup"><span data-stu-id="06ba4-131">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="06ba4-132">Ein Postfach muss mindestens 10 MB Daten aufweisen, um Löschungsprüfungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="06ba4-132">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="06ba4-133">Sie können eine Übersicht aller ausstehenden Löschungen auf der Registerkarte **Übersicht** anzeigen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="06ba4-133">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Ausstehende Löschungen in der Übersicht der Datensatzverwaltung](../media/dispositions-overview.png)

<span data-ttu-id="06ba4-135">Wenn Sie **Alle ausstehenden Löschungen anzeigen** auswählen, werden Sie zur Seite **Disposition** geleitet.</span><span class="sxs-lookup"><span data-stu-id="06ba4-135">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="06ba4-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="06ba4-136">For example:</span></span>

![Seite "Dispositionen" im Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="06ba4-138">Workflow für die Löschungsprüfung</span><span class="sxs-lookup"><span data-stu-id="06ba4-138">Workflow for a disposition review</span></span>

<span data-ttu-id="06ba4-139">Das folgende Diagramm zeigt den grundlegenden Arbeitsablauf einer Löschungsprüfung, wenn eine Aufbewahrungsbezeichnung veröffentlicht und dann manuell von einem Benutzer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="06ba4-139">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="06ba4-140">Alternativ kann eine für eine Löschungsprüfung konfigurierte Aufbewahrungsbezeichnung automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="06ba4-140">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Diagramm, in dem die Funktionsweise der Disposition angezeigt wird](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="06ba4-142">Das Auslösen einer Löschungsprüfung am Ende des Aufbewahrungszeitraums ist eine Konfigurationsoption, die nur mit einer Aufbewahrungsbezeichnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="06ba4-142">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="06ba4-143">Diese Option steht nicht für eine Aufbewahrungsrichtlinie zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="06ba4-143">This option is not available for a retention policy.</span></span> <span data-ttu-id="06ba4-144">Weitere Informationen zu diesen beiden Aufbewahrungslösungen finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md).</span><span class="sxs-lookup"><span data-stu-id="06ba4-144">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="06ba4-145">Von der Seite **Aufbewahrungseinstellungen definieren** für eine Aufbewahrungsbezeichnung:</span><span class="sxs-lookup"><span data-stu-id="06ba4-145">From the **Define retention settings** page for a retention label:</span></span>

![Aufbewahrungseinstellungen für eine Bezeichnung](../media/disposition-review-option.png)
 
<span data-ttu-id="06ba4-147">Nachdem Sie die Option **Löschungsprüfung auslösen** ausgewählt haben, geben Sie auf der nächsten Seite des Assistenten die Dispositionsprüfer an:</span><span class="sxs-lookup"><span data-stu-id="06ba4-147">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Angeben von Dispositionsprüfern](../media/disposition-reviewers.png)

<span data-ttu-id="06ba4-149">Geben Sie als Prüfer einen Benutzer oder eine E-Mail-aktivierte Sicherheitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="06ba4-149">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="06ba4-150">Microsoft 365-Gruppen ([vormals Office 365-Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) werden für diese Option nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06ba4-150">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="06ba4-151">Anzeigen und Verwerfen von Inhalten</span><span class="sxs-lookup"><span data-stu-id="06ba4-151">Viewing and disposing of content</span></span>

<span data-ttu-id="06ba4-152">Wenn ein Prüfer per E-Mail benachrichtigt wird, dass Inhalte zur Überprüfung bereitstehen, wechseln sie zur Registerkarte **Disposition** aus der **Datensatzverwaltung** im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="06ba4-152">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="06ba4-153">Die Prüfer können sehen, wie viele Elemente für jede Aufbewahrungsbezeichnung auf Disposition warten und dann eine Aufbewahrungsbezeichnung auswählen, um den gesamten Inhalt dieser Bezeichnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06ba4-153">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="06ba4-154">Nachdem Sie eine Aufbewahrungsbezeichnung ausgewählt haben, werden alle ausstehenden Löschungen für diese Bezeichnung auf der Registerkarte **Ausstehende Löschung** angezeigt. Wählen Sie ein oder mehrere Elemente aus, für welches Sie dann eine Aktion auswählen und einen Begründungskommentar eingeben können:</span><span class="sxs-lookup"><span data-stu-id="06ba4-154">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Dispositionsoptionen](../media/retention-disposition-options.png)

<span data-ttu-id="06ba4-156">Wie Sie im Bild sehen können, sind die unterstützten Aktionen:</span><span class="sxs-lookup"><span data-stu-id="06ba4-156">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="06ba4-157">Das Element endgültig löschen</span><span class="sxs-lookup"><span data-stu-id="06ba4-157">Permanently delete the item</span></span>
- <span data-ttu-id="06ba4-158">Verlängern des Aufbewahrungszeitraums</span><span class="sxs-lookup"><span data-stu-id="06ba4-158">Extend the retention period</span></span>
- <span data-ttu-id="06ba4-159">Anwenden einer anderen Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="06ba4-159">Apply a different retention label</span></span>

<span data-ttu-id="06ba4-160">Wenn Sie über Berechtigungen für den Speicherort und den Inhalt verfügen, können Sie den Link in der Spalte **Speicherort** verwenden, um Dokumente am ursprünglichen Speicherort anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06ba4-160">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="06ba4-161">Während einer Löschungsprüfung werden die Inhalte nie von ihrem ursprünglichen Speicherort fort bewegt und in keinem Fall gelöscht, es sei denn, der Prüfer entscheidet dies.</span><span class="sxs-lookup"><span data-stu-id="06ba4-161">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="06ba4-162">Die E-Mail-Benachrichtigungen werden wöchentlich automatisch an Prüfer gesendet.</span><span class="sxs-lookup"><span data-stu-id="06ba4-162">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="06ba4-163">Dieser geplante Vorgang bedeutet: Wenn der Inhalt das Ende des Aufbewahrungszeitraums erreicht, kann es bis zu sieben Tage dauern, bis Prüfer die E-Mail-Benachrichtigung erhalten, dass Inhalte auf Disposition warten.</span><span class="sxs-lookup"><span data-stu-id="06ba4-163">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="06ba4-164">Alle Dispositionsaktionen können überwacht werden, und der vom Prüfer eingegebene Begründungstext wird gespeichert und in der Spalte **Kommentar** auf der Seite **Verworfene Elemente** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ba4-164">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="06ba4-165">Zeitspanne bis zur endgültigen Löschung verworfener Inhalte</span><span class="sxs-lookup"><span data-stu-id="06ba4-165">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="06ba4-166">Inhalte, für die eine Löschungsprüfung ansteht, werden erst gelöscht, nachdem ein Prüfer die endgültige Löschung der Inhalte entschieden hat.</span><span class="sxs-lookup"><span data-stu-id="06ba4-166">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="06ba4-167">Wenn der Prüfer diese Option auswählt, wird der Inhalt auf der SharePoint-Website oder dem OneDrive-Konto für den Standardbereinigungsprozess qualifiziert, der in [Funktionsweise von Aufbewahrungseinstellungen bei vorhandenem Inhalt](retention.md#how-retention-settings-work-with-content-in-place) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="06ba4-167">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="06ba4-168">Disposition von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="06ba4-168">Disposition of records</span></span>

<span data-ttu-id="06ba4-169">Verwenden Sie die Registerkarte **Disposition** von der Seite **Datensatzverwaltung**, um Datensätze zu identifizieren, die jetzt automatisch oder nach einer Löschungsprüfung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="06ba4-169">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="06ba4-170">Diese Elemente zeigen **Verworfene Datensätze** in der Spalte **Typ** an.</span><span class="sxs-lookup"><span data-stu-id="06ba4-170">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="06ba4-171">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="06ba4-171">For example:</span></span>

![Elemente, die ohne eine Löschungsprüfung verworfen wurden](../media/records-disposed2.png)

<span data-ttu-id="06ba4-173">Elemente, die in der Registerkarte **Verworfene Elemente** für Datensatzbezeichnungen angezeigt werden, werden bis zu sieben Jahre nach der Verwerfung des Elements gespeichert, und es wird ein Limit von 1 Million Elementen pro Datensatz für diesen Zeitraum angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06ba4-173">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="06ba4-174">Wenn sich die **Anzahl** dem Limit von 1 Million nähert und Sie einen Dispositionsnachweis benötigen, wenden Sie sich an [Microsoft-Support](/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="06ba4-174">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="06ba4-175">Diese Funktionalität basiert auf Informationen aus dem [einheitlichen Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) und erfordert daher, dass die Überwachung [aktiviert und durchsuchbar ist](turn-audit-log-search-on-or-off.md) damit die entsprechenden Ereignisse erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="06ba4-175">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="06ba4-176">Suchen Sie für Überwachungen in der Kategorie **Datei- und Seitenaktivitäten** nach **Gelöschte Datei als Datensatz gekennzeichnet**.</span><span class="sxs-lookup"><span data-stu-id="06ba4-176">For auditing, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="06ba4-177">Dieses Überwachungsereignis gilt für Dokumente und E-Mails.</span><span class="sxs-lookup"><span data-stu-id="06ba4-177">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="06ba4-178">Filtern und Exportieren von Ansichten</span><span class="sxs-lookup"><span data-stu-id="06ba4-178">Filter and export the views</span></span>

<span data-ttu-id="06ba4-179">Wenn Sie auf der Seite **Disposition** eine Aufbewahrungsbezeichnung auswählen, können Sie mit der Registerkarte **Ausstehende Löschung** (sofern zutreffend) und der Registerkarte **Verworfene Elemente** die Ansichten filtern, damit Sie Elemente leichter finden können.</span><span class="sxs-lookup"><span data-stu-id="06ba4-179">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="06ba4-180">Bei ausstehenden Löschungen basiert der Zeitraum auf dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="06ba4-180">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="06ba4-181">Bei verworfenen Elementen basiert der Zeitraum auf dem Löschdatum.</span><span class="sxs-lookup"><span data-stu-id="06ba4-181">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="06ba4-182">Sie können Informationen zu den Elementen in einer der beiden Ansichten als CSV-Datei exportieren, die Sie dann mithilfe von Excel sortieren und verwalten können:</span><span class="sxs-lookup"><span data-stu-id="06ba4-182">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Exportoption zur Disposition](../media/retention-export-option.png)