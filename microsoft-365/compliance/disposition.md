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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Überwachen und Verwalten der Freigabe von Inhalten, unabhängig davon, ob Sie eine Dispositions Überprüfung oder Inhalte verwenden, wird automatisch entsprechend den von Ihnen konfigurierten Einstellungen gelöscht.
ms.openlocfilehash: 5751857f8b3bf0a7f63df73e9bfaa244897bf429
ms.sourcegitcommit: 4ac96855d7c269a0055ca8943000b762a70ca4ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321994"
---
# <a name="disposition-of-content"></a><span data-ttu-id="5d28d-103">Disposition von Inhalten</span><span class="sxs-lookup"><span data-stu-id="5d28d-103">Disposition of content</span></span>

><span data-ttu-id="5d28d-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="5d28d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5d28d-105">Verwenden Sie die Registerkarte **Disposition** aus der **Datensatzverwaltung** im Microsoft 365 Compliance Center, um Dispositions Überprüfungen zu verwalten und [Datensätze](records-management.md#records) anzuzeigen, die am Ende des Aufbewahrungszeitraums automatisch gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="5d28d-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="5d28d-106">Voraussetzungen für das Anzeigen von Inhalts Abstellungen</span><span class="sxs-lookup"><span data-stu-id="5d28d-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="5d28d-107">Zum Verwalten von Dispositions Überprüfungen und zum bestätigen, dass Datensätze gelöscht wurden, müssen Sie über ausreichende Berechtigungen verfügen und die Überwachung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="5d28d-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="5d28d-108">Berechtigungen für die Disposition</span><span class="sxs-lookup"><span data-stu-id="5d28d-108">Permissions for disposition</span></span>

<span data-ttu-id="5d28d-109">Für einen erfolgreichen Zugriff auf die Registerkarte " **Disposition** " im Microsoft 365 Compliance Center müssen Benutzer über die Verwaltungsrolle " **Disposition Management** " verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="5d28d-110">Diese Rolle ist in den standardmäßigen Administratorrollengruppen " **Compliance Administrator** " und " **Compliance Data Administrator**" enthalten.</span><span class="sxs-lookup"><span data-stu-id="5d28d-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="5d28d-111">Um Benutzern diese erforderliche Dispositions-Verwaltungsrolle zu gewähren, fügen Sie diese entweder einer dieser Standardrollengruppen hinzu, oder erstellen Sie eine benutzerdefinierte Rollengruppe (beispielsweise "Dispositions Prüfer"), und erteilen Sie dieser Gruppe die Dispositions Verwaltungsrolle.</span><span class="sxs-lookup"><span data-stu-id="5d28d-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="5d28d-112">Selbst einem globalen Administrator muss die **Dispositions Verwaltungs** Rolle erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="5d28d-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="5d28d-113">Anweisungen finden Sie unter [Gewähren des Zugriffs auf das Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5d28d-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="5d28d-114">Aktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="5d28d-114">Enable auditing</span></span>

<span data-ttu-id="5d28d-115">Stellen Sie sicher, dass die Überwachung mindestens einen Tag vor der ersten Dispositionsaktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5d28d-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="5d28d-116">Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="5d28d-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="5d28d-117">Dispositionsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="5d28d-117">Disposition reviews</span></span>

<span data-ttu-id="5d28d-118">Wenn der Inhalt das Ende seines Aufbewahrungszeitraums erreicht, gibt es mehrere Gründe, warum Sie diesen Inhalt möglicherweise überprüfen möchten, um zu entscheiden, ob er sicher gelöscht werden kann ("verworfen").</span><span class="sxs-lookup"><span data-stu-id="5d28d-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="5d28d-119">Beispielsweise müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="5d28d-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="5d28d-120">Das Löschen relevanter Inhalte im Fall eines Rechtsstreits oder einer Überwachung anhalten.</span><span class="sxs-lookup"><span data-stu-id="5d28d-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="5d28d-121">Entfernen Sie Inhalte aus der Dispositionsliste, die in einem Archiv gespeichert werden sollen, wenn diese Inhalte Forschungs-oder Verlaufswerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="5d28d-122">Weisen Sie dem Inhalt eine andere Beibehaltungsdauer zu, möglicherweise weil die ursprünglichen Aufbewahrungseinstellungen eine vorübergehende oder provisorische Lösung waren.</span><span class="sxs-lookup"><span data-stu-id="5d28d-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="5d28d-123">Zurückgeben der Inhalte an Clients oder übertragen an eine andere Organisation.</span><span class="sxs-lookup"><span data-stu-id="5d28d-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="5d28d-124">Wenn eine Dispositions Überprüfung am Ende des Aufbewahrungszeitraums ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="5d28d-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="5d28d-125">Die Personen, die Sie auswählen, erhalten eine e-Mail-Benachrichtigung, dass Sie Inhalte zur Überprüfung haben.</span><span class="sxs-lookup"><span data-stu-id="5d28d-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="5d28d-126">Diese Bearbeiter können einzelne Benutzer oder e-Mail-aktivierte Sicherheitsgruppen sein.</span><span class="sxs-lookup"><span data-stu-id="5d28d-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="5d28d-127">Beachten Sie, dass Benachrichtigungen auf wöchentlicher Basis gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d28d-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="5d28d-128">Die Bearbeiter wechseln zur Registerkarte " **Disposition** " im Microsoft 365 Compliance Center, um die Inhalte zu überprüfen und zu entscheiden, ob Sie sie dauerhaft löschen, den Aufbewahrungszeitraum verlängern oder eine andere Aufbewahrungs Bezeichnung anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5d28d-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="5d28d-129">Eine Dispositions Überprüfung kann Inhalte in Exchange-Postfächern, SharePoint-Websites, OneDrive-Konten und Microsoft 365-Gruppen umfassen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="5d28d-130">Inhalte, die auf eine Dispositions Überprüfung an diesen Speicherorten warten, werden erst gelöscht, nachdem ein Prüfer die Inhalte endgültig gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="5d28d-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="5d28d-131">Ein Postfach muss mindestens 10 MB Daten zur Unterstützung von Dispositions Prüfungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="5d28d-132">Sie können eine Übersicht über alle ausstehenden Dispositionen auf der Registerkarte **Übersicht** sehen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d28d-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Ausstehende Dispositionen in der Datensatzverwaltung (Übersicht)](../media/dispositions-overview.png)

<span data-ttu-id="5d28d-134">Wenn Sie die Option **alle ausstehenden Dispositionen anzeigen**auswählen, werden Sie zur Seite **Disposition** geleitet.</span><span class="sxs-lookup"><span data-stu-id="5d28d-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="5d28d-135">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d28d-135">For example:</span></span>

![Seite "Dispositions" im Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="5d28d-137">Workflow für eine Dispositions Überprüfung</span><span class="sxs-lookup"><span data-stu-id="5d28d-137">Workflow for a disposition review</span></span>

<span data-ttu-id="5d28d-138">Das folgende Diagramm zeigt den grundlegenden Workflow für eine Dispositions Überprüfung, wenn eine Aufbewahrungs Bezeichnung veröffentlicht und anschließend manuell von einem Benutzer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d28d-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="5d28d-139">Alternativ kann eine für eine Dispositions Überprüfung konfigurierte Aufbewahrungs Bezeichnung automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d28d-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Diagramm zum Anzeigen des Ablaufs der Dispositions Funktion](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="5d28d-141">Das Auslösen einer Dispositions Überprüfung am Ende des Aufbewahrungszeitraums ist eine Konfigurationsoption, die nur mit einer Aufbewahrungs Bezeichnung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5d28d-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="5d28d-142">Diese Option ist für eine Aufbewahrungsrichtlinie nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d28d-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="5d28d-143">Weitere Informationen zu diesen beiden aufbewahrungslösungen finden Sie unter Informationen [zu Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen](retention.md).</span><span class="sxs-lookup"><span data-stu-id="5d28d-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![Aufbewahrungseinstellungen für eine Bezeichnung](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="5d28d-145">Wenn Sie die Option **diese Personen Benachrichtigen auswählen, wenn Elemente zur Überarbeitung verfügbar sind**, geben Sie einen Benutzer oder eine e-Mail-aktivierte Sicherheitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="5d28d-145">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="5d28d-146">Microsoft 365-Gruppen ([früher Office 365 Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) werden für diese Option nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5d28d-146">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="5d28d-147">Anzeigen und Freigeben von Inhalten</span><span class="sxs-lookup"><span data-stu-id="5d28d-147">Viewing and disposing of content</span></span>

<span data-ttu-id="5d28d-148">Wenn ein Prüfer per e-Mail benachrichtigt wird, dass der Inhalt überprüft werden kann, wechseln Sie zur Registerkarte " **Disposition** " von der **Datensatzverwaltung** im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5d28d-148">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5d28d-149">Die Bearbeiter können sehen, wie viele Elemente für jede Aufbewahrungs Bezeichnung auf die Disposition warten, und wählen dann eine Aufbewahrungs Bezeichnung aus, um den gesamten Inhalt mit dieser Bezeichnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-149">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="5d28d-150">Nachdem Sie eine Aufbewahrungs Bezeichnung ausgewählt haben, werden auf der Registerkarte **ausstehende Disposition** alle ausstehenden Dispositionen für diese Bezeichnung angezeigt. Wählen Sie mindestens ein Element aus, in dem Sie eine Aktion auswählen und einen Ausrichtungs Kommentar eingeben können:</span><span class="sxs-lookup"><span data-stu-id="5d28d-150">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Dispositions Optionen](../media/retention-disposition-options.png)

<span data-ttu-id="5d28d-152">Wie Sie aus dem Bild sehen können, werden die folgenden Aktionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5d28d-152">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="5d28d-153">Dauerhaftes Löschen des Elements</span><span class="sxs-lookup"><span data-stu-id="5d28d-153">Permanently delete the item</span></span>
- <span data-ttu-id="5d28d-154">Verlängern des Aufbewahrungszeitraums</span><span class="sxs-lookup"><span data-stu-id="5d28d-154">Extend the retention period</span></span>
- <span data-ttu-id="5d28d-155">Anwenden einer anderen Aufbewahrungs Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="5d28d-155">Apply a different retention label</span></span>

<span data-ttu-id="5d28d-156">Wenn Sie über Berechtigungen für den Speicherort und den Inhalt verfügen, können Sie den Link in der Spalte **Speicherort** verwenden, um Dokumente an Ihrem ursprünglichen Speicherort anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-156">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="5d28d-157">Während einer Dispositions Überprüfung werden die Inhalte nie von Ihrem ursprünglichen Speicherort verschoben, und Sie werden erst gelöscht, wenn sich der Bearbeiter dafür entscheidet.</span><span class="sxs-lookup"><span data-stu-id="5d28d-157">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="5d28d-158">Die e-Mail-Benachrichtigungen werden wöchentlich automatisch an Prüfer gesendet.</span><span class="sxs-lookup"><span data-stu-id="5d28d-158">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="5d28d-159">Dieser geplante Vorgang bedeutet, dass beim Erreichen des Endes des Aufbewahrungszeitraums durch Inhalte bis zu sieben Tage dauern kann, bis die Bearbeiter die e-Mail-Benachrichtigung erhalten, dass der Inhalt die Disposition wartet.</span><span class="sxs-lookup"><span data-stu-id="5d28d-159">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="5d28d-160">Alle Dispositionsaktionen können überwacht werden, und der vom Bearbeiter eingegebene Begründungstext wird gespeichert und in der Spalte **Kommentar** auf der Seite **verworfene Elemente** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d28d-160">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="5d28d-161">Wie lange, bis verworfene Inhalte endgültig gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="5d28d-161">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="5d28d-162">Inhalte, die auf eine Dispositions Überprüfung warten, werden erst gelöscht, nachdem ein Prüfer die Inhalte endgültig gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="5d28d-162">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="5d28d-163">Wenn der Bearbeiter diese Option auswählt, wird der Inhalt der SharePoint-Website oder des OneDrive-Kontos für den standardmäßigen Cleanupprozess in Betracht gezogen, der unter [How Retention Settings with Content in Place](retention.md#how-retention-settings-work-with-content-in-place)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5d28d-163">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="5d28d-164">Disposition von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="5d28d-164">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="5d28d-165">Der Rollout für den Nachweis der Verfügung für Datensätze in SharePoint und OneDrive ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5d28d-165">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span>
>
> <span data-ttu-id="5d28d-166">Der Nachweis der Verfügung für Datensätze in Exchange wurde gerade erst gestartet, um den Rollout auszuführen. Wenn dieser Rollout abgeschlossen ist, werden wir diesen Hinweis aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5d28d-166">Proof of disposal for records in Exchange has just started to roll out. When this rollout is complete, we will update this note.</span></span>

<span data-ttu-id="5d28d-167">Verwenden Sie die Registerkarte **Disposition** auf der Seite **Datensatzverwaltung** , um Datensätze zu identifizieren, die jetzt entweder automatisch oder nach einer Dispositions Überprüfung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5d28d-167">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="5d28d-168">Diese Elemente zeigen **Datensätze** an, die in der Spalte **Typ** angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5d28d-168">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="5d28d-169">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5d28d-169">For example:</span></span>

![Elemente, die ohne eine Dispositions Überprüfung verworfen wurden](../media/records-disposed2.png)

<span data-ttu-id="5d28d-171">Elemente, die auf der Registerkarte " **verworfene Elemente** " für Daten Satzbezeichnungen angezeigt werden, werden bis zu sieben Jahre nach der Freigabe des Elements mit einem Grenzwert von 1 Million Elementen pro Datensatz für diesen Zeitraum aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="5d28d-171">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="5d28d-172">Wenn die **Zähl** Nummer, die diesem Grenzwert von 1 Million nähert, angezeigt wird und Sie einen Nachweis der Disposition für Ihre Datensätze benötigen, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="5d28d-172">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="5d28d-173">Diese Funktion basiert auf Informationen aus dem [vereinheitlichten Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) und erfordert daher die Überwachung, um [aktiviert und durchsuchbar](turn-audit-log-search-on-or-off.md) zu sein, damit die entsprechenden Ereignisse erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="5d28d-173">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="5d28d-174">Filtern und Exportieren der Ansichten</span><span class="sxs-lookup"><span data-stu-id="5d28d-174">Filter and export the views</span></span>

<span data-ttu-id="5d28d-175">Wenn Sie auf der Seite **Disposition** eine Aufbewahrungs Bezeichnung auswählen, können Sie auf der Registerkarte **ausstehende Disposition** (falls zutreffend) und auf der Registerkarte **verworfene Elemente** die Ansichten filtern, damit Sie leichter nach Elementen suchen können.</span><span class="sxs-lookup"><span data-stu-id="5d28d-175">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="5d28d-176">Für ausstehende Dispositionen basiert der Zeitbereich auf dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="5d28d-176">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="5d28d-177">Bei freigestellten Elementen basiert der Zeitbereich auf dem Löschdatum.</span><span class="sxs-lookup"><span data-stu-id="5d28d-177">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="5d28d-178">Sie können Informationen zu den Elementen in beiden Ansichten als CSV-Datei exportieren, die Sie dann mithilfe von Excel sortieren und verwalten können:</span><span class="sxs-lookup"><span data-stu-id="5d28d-178">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Export Option für Disposition](../media/retention-export-option.png)
  
![Exportierte Dispositionsdaten in Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


