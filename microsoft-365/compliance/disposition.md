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
ms.openlocfilehash: cb48d2eb6d2d06093ddea74f13269faeb4798b97
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "43950106"
---
# <a name="disposition-of-content"></a><span data-ttu-id="e5fea-103">Disposition von Inhalten</span><span class="sxs-lookup"><span data-stu-id="e5fea-103">Disposition of content</span></span>

><span data-ttu-id="e5fea-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e5fea-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e5fea-105">Verwenden Sie die Registerkarte **Disposition** aus der **Datensatzverwaltung** im Microsoft 365 Compliance Center, um Dispositions Überprüfungen zu verwalten und [Datensätze](records.md) anzuzeigen, die am Ende des Aufbewahrungszeitraums automatisch gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="e5fea-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="e5fea-106">Voraussetzungen für das Anzeigen von Inhalts Abstellungen</span><span class="sxs-lookup"><span data-stu-id="e5fea-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="e5fea-107">Zum Verwalten von Dispositions Überprüfungen und zum bestätigen, dass Datensätze gelöscht wurden, müssen Sie über ausreichende Berechtigungen verfügen und die Überwachung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="e5fea-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="e5fea-108">Berechtigungen für die Disposition</span><span class="sxs-lookup"><span data-stu-id="e5fea-108">Permissions for disposition</span></span>

<span data-ttu-id="e5fea-109">Zum erfolgreichen Zugriff auf die Registerkarte " **Disposition** " im Microsoft 365 Compliance Center müssen Sie Mitglied der **Dispositions-Verwaltungs** Rolle und der Rolle " **nur Überwachungsprotokolle anzeigen** " sein.</span><span class="sxs-lookup"><span data-stu-id="e5fea-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, you must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="e5fea-110">Es wird empfohlen, eine neue Rollengruppe mit dem Namen **Dispositions Prüfer**zu erstellen und diese beiden Rollen zu dieser Rollengruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5fea-110">We recommend creating a new role group called **Disposition Reviewers**, and add these two roles to that role group.</span></span> 

<span data-ttu-id="e5fea-111">Spezifisch für die Rolle " **nur Ansichts Überwachungsprotokolle** ":</span><span class="sxs-lookup"><span data-stu-id="e5fea-111">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="e5fea-112">Da es sich bei dem zugrunde liegenden Cmdlet, das zum Durchsuchen des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt, müssen Sie Benutzer diese Rolle mithilfe des [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)anstatt mithilfe der Seite **Berechtigungen** im Security & Compliance Center zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e5fea-112">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="e5fea-113">Anweisungen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="e5fea-113">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="e5fea-114">Microsoft 365-Gruppen ([früher Office 365 Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) werden für diese Rolle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5fea-114">Microsoft 365 Groups ([formerly Office 365 Groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="e5fea-115">Weisen Sie stattdessen Benutzerpostfächer, e-Mail-Benutzer oder e-Mail-aktivierte Sicherheitsgruppen zu.</span><span class="sxs-lookup"><span data-stu-id="e5fea-115">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="e5fea-116">Anweisungen zum Erteilen von Benutzern der **Dispositions Verwaltungs** Rolle und zum Erstellen Ihrer neuen Funktion " **Dispositions Prüfer** " finden Sie unter [Erteilen von Benutzern den Zugriff auf das Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e5fea-116">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="e5fea-117">Aktivieren der Überwachung</span><span class="sxs-lookup"><span data-stu-id="e5fea-117">Enable auditing</span></span>

<span data-ttu-id="e5fea-118">Stellen Sie sicher, dass die Überwachung mindestens einen Tag vor der ersten Dispositionsaktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e5fea-118">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="e5fea-119">Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="e5fea-119">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="e5fea-120">Dispositionsüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="e5fea-120">Disposition reviews</span></span>

<span data-ttu-id="e5fea-121">Wenn der Inhalt das Ende seines Aufbewahrungszeitraums erreicht, gibt es mehrere Gründe, warum Sie diesen Inhalt möglicherweise überprüfen möchten, um zu entscheiden, ob er sicher gelöscht werden kann ("verworfen").</span><span class="sxs-lookup"><span data-stu-id="e5fea-121">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="e5fea-122">Beispielsweise müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="e5fea-122">For example, you might need to:</span></span>
  
- <span data-ttu-id="e5fea-123">Das Löschen relevanter Inhalte im Fall eines Rechtsstreits oder einer Überwachung anhalten.</span><span class="sxs-lookup"><span data-stu-id="e5fea-123">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="e5fea-124">Entfernen Sie Inhalte aus der Dispositionsliste, die in einem Archiv gespeichert werden sollen, wenn diese Inhalte Forschungs-oder Verlaufswerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e5fea-124">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="e5fea-125">Weisen Sie dem Inhalt eine andere Beibehaltungsdauer zu, möglicherweise weil die ursprünglichen Aufbewahrungseinstellungen eine vorübergehende oder provisorische Lösung waren.</span><span class="sxs-lookup"><span data-stu-id="e5fea-125">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="e5fea-126">Zurückgeben der Inhalte an Clients oder übertragen an eine andere Organisation.</span><span class="sxs-lookup"><span data-stu-id="e5fea-126">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="e5fea-127">Wenn eine Dispositions Überprüfung am Ende des Aufbewahrungszeitraums ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="e5fea-127">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="e5fea-128">Die Personen, die Sie auswählen, erhalten eine e-Mail-Benachrichtigung, dass Sie Inhalte zur Überprüfung haben.</span><span class="sxs-lookup"><span data-stu-id="e5fea-128">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="e5fea-129">Bei diesen Prüfern kann es sich um einzelne Benutzer, Verteilungs-oder Sicherheitsgruppen oder Office 365 Gruppen handeln.</span><span class="sxs-lookup"><span data-stu-id="e5fea-129">These reviewers can be individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="e5fea-130">Beachten Sie, dass Benachrichtigungen auf wöchentlicher Basis gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5fea-130">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="e5fea-131">Die Bearbeiter wechseln zur Registerkarte " **Disposition** " im Microsoft 365 Compliance Center, um die Inhalte zu überprüfen und zu entscheiden, ob Sie sie dauerhaft löschen, den Aufbewahrungszeitraum verlängern oder eine andere Aufbewahrungs Bezeichnung anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e5fea-131">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="e5fea-132">Eine Dispositions Überprüfung kann Inhalte in Exchange-Postfächern, SharePoint-Websites, OneDrive-Konten und Microsoft 365-Gruppen umfassen.</span><span class="sxs-lookup"><span data-stu-id="e5fea-132">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="e5fea-133">Inhalte, die auf eine Dispositions Überprüfung an diesen Speicherorten warten, werden erst gelöscht, nachdem ein Prüfer die Inhalte endgültig gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="e5fea-133">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

<span data-ttu-id="e5fea-134">Sie können eine Übersicht über alle ausstehenden Dispositionen auf der Registerkarte **Übersicht** sehen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5fea-134">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Ausstehende Dispositionen in der Datensatzverwaltung (Übersicht)](../media/dispositions-overview.png)

<span data-ttu-id="e5fea-136">Wenn Sie die Option **alle ausstehenden Dispositionen anzeigen**auswählen, werden Sie zur Seite **Disposition** geleitet.</span><span class="sxs-lookup"><span data-stu-id="e5fea-136">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="e5fea-137">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5fea-137">For example:</span></span>

![Seite "Dispositions" im Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="e5fea-139">Workflow für eine Dispositions Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e5fea-139">Workflow for a disposition review</span></span>

<span data-ttu-id="e5fea-140">Dies ist der grundlegende Workflow für eine Dispositions Überprüfung, wenn eine Aufbewahrungs Bezeichnung veröffentlicht und dann manuell von einem Benutzer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5fea-140">This is the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="e5fea-141">Alternativ kann eine für eine Dispositions Überprüfung konfigurierte Aufbewahrungs Bezeichnung automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5fea-141">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Diagramm zum Anzeigen des Ablaufs der Dispositions Funktion](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="e5fea-143">Das Auslösen einer Dispositions Überprüfung am Ende des Aufbewahrungszeitraums ist eine Konfigurationsoption, die nur mit einer [Aufbewahrungs Bezeichnung](labels.md)verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e5fea-143">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a [retention label](labels.md).</span></span> <span data-ttu-id="e5fea-144">Diese Option steht in einer Aufbewahrungsrichtlinie nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e5fea-144">This option is not available in a retention policy.</span></span>
  
![Aufbewahrungseinstellungen für eine Bezeichnung](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="e5fea-146">Wenn Sie die Option **diese Personen Benachrichtigen auswählen, wenn Elemente zur Überarbeitung verfügbar sind**, geben Sie einen Benutzer oder eine e-Mail-aktivierte Sicherheitsgruppe an.</span><span class="sxs-lookup"><span data-stu-id="e5fea-146">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="e5fea-147">Microsoft 365-Gruppen ([früher Office 365 Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) werden für diese Option nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5fea-147">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="e5fea-148">Anzeigen und Freigeben von Inhalten</span><span class="sxs-lookup"><span data-stu-id="e5fea-148">Viewing and disposing of content</span></span>

<span data-ttu-id="e5fea-149">Wenn ein Prüfer per e-Mail benachrichtigt wird, dass der Inhalt überprüft werden kann, wechseln Sie zur Registerkarte " **Disposition** " von der **Datensatzverwaltung** im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e5fea-149">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e5fea-150">Die Bearbeiter können sehen, wie viele Elemente für jede Aufbewahrungs Bezeichnung auf die Disposition warten, und wählen dann eine Aufbewahrungs Bezeichnung aus, um den gesamten Inhalt mit dieser Bezeichnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5fea-150">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="e5fea-151">Nachdem Sie eine Aufbewahrungs Bezeichnung ausgewählt haben, werden auf der Registerkarte **ausstehende Disposition** alle ausstehenden Dispositionen für diese Bezeichnung angezeigt. Wählen Sie ein oder mehrere Elemente aus, in denen Sie eine Aktion auswählen und einen Ausrichtungs Kommentar eingeben können:</span><span class="sxs-lookup"><span data-stu-id="e5fea-151">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Dispositions Optionen](../media/retention-disposition-options.png)

<span data-ttu-id="e5fea-153">Wie Sie aus dem Bild sehen können, werden die folgenden Aktionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e5fea-153">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="e5fea-154">Dauerhaftes Löschen des Elements</span><span class="sxs-lookup"><span data-stu-id="e5fea-154">Permanently delete the item</span></span>
- <span data-ttu-id="e5fea-155">Verlängern des Aufbewahrungszeitraums</span><span class="sxs-lookup"><span data-stu-id="e5fea-155">Extend the retention period</span></span>
- <span data-ttu-id="e5fea-156">Anwenden einer anderen Aufbewahrungs Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="e5fea-156">Apply a different retention label</span></span>

<span data-ttu-id="e5fea-157">Wenn Sie über Berechtigungen für den Speicherort und den Inhalt verfügen, können Sie den Link in der Spalte **Speicherort** verwenden, um Dokumente an Ihrem ursprünglichen Speicherort anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5fea-157">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="e5fea-158">Während einer Dispositions Überprüfung werden die Inhalte nie von Ihrem ursprünglichen Speicherort verschoben, und Sie werden erst gelöscht, wenn sich der Bearbeiter dafür entscheidet.</span><span class="sxs-lookup"><span data-stu-id="e5fea-158">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="e5fea-159">Die e-Mail-Benachrichtigungen werden wöchentlich automatisch an Prüfer gesendet.</span><span class="sxs-lookup"><span data-stu-id="e5fea-159">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="e5fea-160">Dieser geplante Vorgang bedeutet, dass beim Erreichen des Endes des Aufbewahrungszeitraums durch Inhalte bis zu sieben Tage dauern kann, bis die Bearbeiter die e-Mail-Benachrichtigung erhalten, dass der Inhalt die Disposition wartet.</span><span class="sxs-lookup"><span data-stu-id="e5fea-160">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="e5fea-161">Alle Dispositionsaktionen können überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="e5fea-161">All disposition actions can be audited.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="e5fea-162">Wie lange, bis verworfene Inhalte endgültig gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="e5fea-162">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="e5fea-163">Inhalte, die auf eine Dispositions Überprüfung warten, werden erst gelöscht, nachdem ein Prüfer die Inhalte endgültig gelöscht hat.</span><span class="sxs-lookup"><span data-stu-id="e5fea-163">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="e5fea-164">Wenn der Bearbeiter diese Option auswählt, wird der Inhalt der SharePoint-Website oder des OneDrive-Kontos für den standardmäßigen Cleanupprozess in Betracht gezogen, der unter [How a Retention Policy Works with Content in Place](retention-policies.md#how-a-retention-policy-works-with-content-in-place)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e5fea-164">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="e5fea-165">Disposition von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="e5fea-165">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="e5fea-166">Die Möglichkeit zum Anzeigen von Datensätzen, die automatisch ohne Dispositions Überprüfung gelöscht wurden, wird schrittweise für die Mandanten im April und Mai 2020, sodass diese Benutzeroberfläche möglicherweise nicht sofort angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e5fea-166">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="e5fea-167">Verwenden Sie die Registerkarte **Disposition** auf der Seite **Datensatzverwaltung** , um Datensätze zu identifizieren, die automatisch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e5fea-167">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="e5fea-168">Diese Elemente zeigen **Datensätze** an, die in der Spalte **Typ** angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e5fea-168">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="e5fea-169">Im Vergleich werden Verworfene Datensätze, die genehmigt werden, durch eine Dispositions Überprüfung gelöscht werden, **ausstehende Disposition**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5fea-169">In comparison, disposed records that are approved to be deleted through a disposition review display **Pending Disposition**.</span></span> <span data-ttu-id="e5fea-170">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5fea-170">For example:</span></span>

![Elemente, die ohne eine Dispositions Überprüfung verworfen wurden](../media/records-disposed2.png)

<span data-ttu-id="e5fea-172">Elemente, die auf der Registerkarte " **verworfene Elemente** " für Daten Satzbezeichnungen angezeigt werden, werden bis zu 7 Jahre nach der Freigabe des Elements aufbewahrt, mit einem Grenzwert von 1 Million Elementen pro Datensatz für diesen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="e5fea-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="e5fea-173">Wenn die **Zähl** Nummer, die diesem Grenzwert von 1 Million nähert, angezeigt wird und Sie einen Nachweis der Disposition für Ihre Datensätze benötigen, wenden Sie sich an den [Microsoft-Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="e5fea-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="e5fea-174">Diese Funktion basiert auf Informationen aus dem [vereinheitlichten Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) und erfordert daher die Überwachung, um [aktiviert und durchsuchbar](turn-audit-log-search-on-or-off.md) zu sein, damit die entsprechenden Ereignisse erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="e5fea-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="e5fea-175">Filtern und Exportieren der Ansichten</span><span class="sxs-lookup"><span data-stu-id="e5fea-175">Filter and export the views</span></span>

<span data-ttu-id="e5fea-176">Wenn Sie auf der Seite **Disposition** eine Aufbewahrungs Bezeichnung auswählen, können Sie auf der Registerkarte **ausstehende Disposition** (falls zutreffend) und auf der Registerkarte **verworfene Elemente** die Ansichten filtern, damit Sie leichter nach Elementen suchen können.</span><span class="sxs-lookup"><span data-stu-id="e5fea-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="e5fea-177">Für ausstehende Dispositionen basiert der Zeitbereich auf dem Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="e5fea-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="e5fea-178">Bei freigestellten Elementen basiert der Zeitbereich auf dem Löschdatum.</span><span class="sxs-lookup"><span data-stu-id="e5fea-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="e5fea-179">Sie können Informationen zu den Elementen in beiden Ansichten als CSV-Datei exportieren, die Sie dann mithilfe von Excel sortieren und verwalten können:</span><span class="sxs-lookup"><span data-stu-id="e5fea-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Export Option für Disposition](../media/retention-export-option.png)
  
![Exportierte Dispositionsdaten in Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


