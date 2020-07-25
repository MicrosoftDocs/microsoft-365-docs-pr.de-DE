---
title: Informationen zu Datensätzen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie mehr über Datensätze, um Sie beim Implementieren einer Datensatzverwaltungslösung in Microsoft 365 zu unterstützen.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372520"
---
# <a name="learn-about-records"></a><span data-ttu-id="df2f3-103">Informationen zu Datensätzen</span><span class="sxs-lookup"><span data-stu-id="df2f3-103">Learn about records</span></span>

><span data-ttu-id="df2f3-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="df2f3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="df2f3-105">Die Verwaltung von Datensätzen in Microsoft 365 hilft Ihrer Organisation bei der Einhaltung von Unternehmensrichtlinien und gesetzlichen oder regulatorischer Verpflichtungen bei gleichzeitiger Verringerung der Risiken und der gesetzlichen Haftung.</span><span class="sxs-lookup"><span data-stu-id="df2f3-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="df2f3-106">Wenn Inhalt als Datensatz markiert ist:</span><span class="sxs-lookup"><span data-stu-id="df2f3-106">When content is marked as a record:</span></span>

- <span data-ttu-id="df2f3-107">Die Elemente werden hinsichtlich der [zulässigen oder blockierten Aktionen](#compare-restrictions-for-what-actions-are-allowed-or-blocked) eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="df2f3-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="df2f3-108">Andere Aktivitäten in Verbindung mit dem Element werden protokolliert.</span><span class="sxs-lookup"><span data-stu-id="df2f3-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="df2f3-109">Sie haben einen Verfügungsnachweis, wenn die Elemente am Ende ihrer Aufbewahrungsfrist gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="df2f3-110">Verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als Datensätze zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="df2f3-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="df2f3-111">Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df2f3-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="df2f3-112">Durch die Verwendung von Aufbewahrungsbezeichnungen zum Markieren von Inhalten als Datensätze können Sie eine einzige und konsistente Strategie für die Verwaltung von Datensätzen in Ihrer Microsoft 365-Umgebung implementieren.</span><span class="sxs-lookup"><span data-stu-id="df2f3-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="df2f3-113">Vergleichen Sie die Einschränkungen für die zulässigen oder blockierten Aktionen</span><span class="sxs-lookup"><span data-stu-id="df2f3-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="df2f3-114">Verwenden Sie die folgende Tabelle, um zu ermitteln, welche Einschränkungen für den Inhalt durch das Anwenden einer Standardaufbewahrungsbezeichnung und von Aufbewahrungsbezeichnungen, die den Inhalt als Datensatz kennzeichnen, gelten.</span><span class="sxs-lookup"><span data-stu-id="df2f3-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="df2f3-115">Eine Standardaufbewahrungsbezeichnung kann Daten speichern, ohne den Inhalt als Datensatz zu markieren.</span><span class="sxs-lookup"><span data-stu-id="df2f3-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="df2f3-116">Der Vollständigkeit halber enthält die Tabelle Spalten für einen gesperrten und entsperrten Datensatz, die für SharePoint und OneDrive gelten, jedoch nicht für Exchange.</span><span class="sxs-lookup"><span data-stu-id="df2f3-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="df2f3-117">Die Möglichkeit zum Sperren und Entsperren eines Datensatzes verwendet die [Datensatzversionsverwaltung](#record-versioning), die für Exchange-Elemente nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="df2f3-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="df2f3-118">Für alle Exchange-Elemente, die als Datensatz markiert sind, ist das Verhalten der Spalte **Datensatz gesperrt** und der Spalte **Datensatz entsperrt** nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="df2f3-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="df2f3-119">Aktion</span><span class="sxs-lookup"><span data-stu-id="df2f3-119">Action</span></span>| <span data-ttu-id="df2f3-120">Aufbewahrungsbezeichnung</span><span class="sxs-lookup"><span data-stu-id="df2f3-120">Retention label</span></span> |<span data-ttu-id="df2f3-121">Datensatz – gesperrt</span><span class="sxs-lookup"><span data-stu-id="df2f3-121">Record - locked</span></span>| <span data-ttu-id="df2f3-122">Datensatz – entsperrt</span><span class="sxs-lookup"><span data-stu-id="df2f3-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df2f3-123">Inhalt bearbeiten</span><span class="sxs-lookup"><span data-stu-id="df2f3-123">Edit contents</span></span>|<span data-ttu-id="df2f3-124">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-124">Allowed</span></span> | <span data-ttu-id="df2f3-125">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="df2f3-125">**Blocked**</span></span> | <span data-ttu-id="df2f3-126">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-126">Allowed</span></span>|
|<span data-ttu-id="df2f3-127">Bearbeiten Sie Eigenschaften, einschließlich Umbenennen</span><span class="sxs-lookup"><span data-stu-id="df2f3-127">Edit properties, including rename</span></span>|<span data-ttu-id="df2f3-128">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-128">Allowed</span></span> |<span data-ttu-id="df2f3-129">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-129">Allowed</span></span> | <span data-ttu-id="df2f3-130">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-130">Allowed</span></span>|
|<span data-ttu-id="df2f3-131">Löschen</span><span class="sxs-lookup"><span data-stu-id="df2f3-131">Delete</span></span>|<span data-ttu-id="df2f3-132">Zulässig <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="df2f3-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="df2f3-133">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="df2f3-133">**Blocked**</span></span> | <span data-ttu-id="df2f3-134">**Gesperrt**</span><span class="sxs-lookup"><span data-stu-id="df2f3-134">**Blocked**</span></span>|
|<span data-ttu-id="df2f3-135">Kopie</span><span class="sxs-lookup"><span data-stu-id="df2f3-135">Copy</span></span>|<span data-ttu-id="df2f3-136">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-136">Allowed</span></span> |<span data-ttu-id="df2f3-137">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-137">Allowed</span></span> | <span data-ttu-id="df2f3-138">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-138">Allowed</span></span>|
|<span data-ttu-id="df2f3-139">Innerhalb eines Containers bewegen<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="df2f3-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="df2f3-140">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-140">Allowed</span></span> |<span data-ttu-id="df2f3-141">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-141">Allowed</span></span> | <span data-ttu-id="df2f3-142">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-142">Allowed</span></span>|
|<span data-ttu-id="df2f3-143">Über Container hinweg bewegen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="df2f3-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="df2f3-144">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-144">Allowed</span></span> |<span data-ttu-id="df2f3-145">Zulässig, wenn nie entsperrt</span><span class="sxs-lookup"><span data-stu-id="df2f3-145">Allowed if never unlocked</span></span> | <span data-ttu-id="df2f3-146">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-146">Allowed</span></span>|
|<span data-ttu-id="df2f3-147">Öffnen/Lesen</span><span class="sxs-lookup"><span data-stu-id="df2f3-147">Open/Read</span></span>|<span data-ttu-id="df2f3-148">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-148">Allowed</span></span> |<span data-ttu-id="df2f3-149">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-149">Allowed</span></span> | <span data-ttu-id="df2f3-150">Allowed</span><span class="sxs-lookup"><span data-stu-id="df2f3-150">Allowed</span></span>|
|<span data-ttu-id="df2f3-151">Ändern der Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="df2f3-151">Change label</span></span>|<span data-ttu-id="df2f3-152">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-152">Allowed</span></span> |<span data-ttu-id="df2f3-153">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="df2f3-153">Allowed - container admin only</span></span> | <span data-ttu-id="df2f3-154">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="df2f3-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="df2f3-155">Bezeichnung entfernen</span><span class="sxs-lookup"><span data-stu-id="df2f3-155">Remove label</span></span>|<span data-ttu-id="df2f3-156">Zulässig</span><span class="sxs-lookup"><span data-stu-id="df2f3-156">Allowed</span></span> |<span data-ttu-id="df2f3-157">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="df2f3-157">Allowed - container admin only</span></span> | <span data-ttu-id="df2f3-158">Zulässig – nur Container-Administrator</span><span class="sxs-lookup"><span data-stu-id="df2f3-158">Allowed - container admin only</span></span>|

<span data-ttu-id="df2f3-159">Fußnoten:</span><span class="sxs-lookup"><span data-stu-id="df2f3-159">Footnotes:</span></span>

<span data-ttu-id="df2f3-160"><sup>1</sup> Unterstützt von OneDrive und Exchange durch Aufbewahren einer Kopie an einem gesicherten Ort, jedoch blockiert von SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df2f3-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="df2f3-161">Nachricht, die ein Benutzer sieht, wenn er versucht, ein beschriftetes Dokument in SharePoint zu löschen:</span><span class="sxs-lookup"><span data-stu-id="df2f3-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Nachricht, dass das Element nicht aus SharePoint gelöscht wurde](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="df2f3-163"><sup>2</sup> Zu den Containern gehören SharePoint-Dokumentbibliotheken und Exchange-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="df2f3-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="df2f3-164">Verwenden von Aufbewahrungsbezeichnungen zum Kennzeichnen von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="df2f3-164">Using retention labels to declare records</span></span>

<span data-ttu-id="df2f3-165">Wenn Sie eine Aufbewahrungsbezeichnung erstellen, können Sie die Aufbewahrungsbezeichnung dazu verwenden, Inhalte als Datensatz zu kennzeichnen:</span><span class="sxs-lookup"><span data-stu-id="df2f3-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="df2f3-166">Wechseln Sie im Microsoft 365 Compliance Center zu **Records Management-** \> **Dateiplan**.</span><span class="sxs-lookup"><span data-stu-id="df2f3-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="df2f3-167">Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="df2f3-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="df2f3-168">Wählen Sie auf der Seite **Bezeichnungseinstellungen** im Assistenten die Option zum Klassifizieren von Inhalten als Datensatz aus.</span><span class="sxs-lookup"><span data-stu-id="df2f3-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Aktivieren Sie das Kontrollkästchen „Bezeichnung zum Klassifizieren von Inhalt als „Datensatz“ verwenden“](../media/recordversioning6.png)

3. <span data-ttu-id="df2f3-170">Wenden Sie die Aufbewahrungsbezeichnung nach Bedarf auf SharePoint- oder OneDrive-Dokumente und Exchange-E-Mails an.</span><span class="sxs-lookup"><span data-stu-id="df2f3-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="df2f3-171">Für Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="df2f3-171">For instructions:</span></span>
    
    - [<span data-ttu-id="df2f3-172">Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps</span><span class="sxs-lookup"><span data-stu-id="df2f3-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="df2f3-173">Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="df2f3-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="df2f3-174">Anwenden der konfigurierten Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="df2f3-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="df2f3-175">Wenn Aufbewahrungsbezeichnungen, die Inhalte als Datensatz markieren, Benutzern zur Verfügung gestellt werden, um sie in Apps anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="df2f3-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="df2f3-176">Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach diese Bezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="df2f3-177">Bei SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe "Mitglieder" (Berechtigungsstufe "Beitrag") diese Bezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="df2f3-178">Beispiel für ein Dokument, das mithilfe einer Aufbewahrungsbezeichnung als Datensatz markiert wurde:</span><span class="sxs-lookup"><span data-stu-id="df2f3-178">Example of a document marked as record by using a retention label:</span></span>

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="df2f3-180">Datensatzversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="df2f3-180">Record versioning</span></span>

<span data-ttu-id="df2f3-181">Die Möglichkeit, ein Dokument als Datensatz zu markieren und Aktionen einzuschränken, die für den Datensatz ausgeführt werden können, ist ein wesentliches Ziel jeder Datensatzverwaltungslösung.</span><span class="sxs-lookup"><span data-stu-id="df2f3-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="df2f3-182">Möglicherweise ist jedoch auch eine Zusammenarbeit erforderlich, damit Benutzer nachfolgende Versionen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="df2f3-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="df2f3-183">Beispielsweise können Sie einen Kaufvertrag als Datensatz markieren, müssen dann jedoch den Vertrag mit neuen Bedingungen aktualisieren und die neueste Version als neuen Datensatz markieren, während die vorherige Datensatzversion beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="df2f3-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="df2f3-184">Bei diesen Szenarien unterstützt SharePoint und OneDrive die *Versionsverwaltung für Datensätze*.</span><span class="sxs-lookup"><span data-stu-id="df2f3-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="df2f3-185">OneNote-Notizbuchordner unterstützen keine Datensatzversionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="df2f3-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="df2f3-186">Um die Datensatzversionsverwaltung zu verwenden, beschriften Sie zuerst das Dokument und markieren Sie es als Datensatz.</span><span class="sxs-lookup"><span data-stu-id="df2f3-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="df2f3-187">Zu diesem Zeitpunkt wird neben der Aufbewahrungsbezeichnung eine Dokumenteigenschaft mit dem Namen *Datensatzstatus* angezeigt, und der anfängliche Datensatzstatus ist **Gesperrt**.</span><span class="sxs-lookup"><span data-stu-id="df2f3-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="df2f3-188">Sie können jetzt Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="df2f3-188">You can now do the following things:</span></span>

  - <span data-ttu-id="df2f3-189">**Bearbeiten und speichern Sie einzelne Versionen des Dokuments kontinuierlich als Datensätze, indem Sie die Eigenschaft Datensatzstatus entsperren und sperren.**</span><span class="sxs-lookup"><span data-stu-id="df2f3-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="df2f3-190">Nur wenn die Eigenschaft **Datensatzstatus** auf **Gesperrt** gesetzt ist, wird eine neue Version des Datensatzes beibehalten.</span><span class="sxs-lookup"><span data-stu-id="df2f3-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="df2f3-191">Durch das Umschalten zwischen gesperrt und entsperrt wird das Risiko verringert, dass unnötige Versionen und Kopien des Dokuments aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="df2f3-192">**Lassen Sie die Datensätze automatisch in einem in-situ-Datensatzrepository speichern, das sich in der Websitesammlung befindet.**</span><span class="sxs-lookup"><span data-stu-id="df2f3-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="df2f3-193">Jede Websitesammlung in SharePoint und OneDrive bewahrt Inhalte in ihrer Aufbewahrungsspeicherbibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="df2f3-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="df2f3-194">Datensatzversionen werden im Ordner „Datensätze“ in dieser Bibliothek gespeichert.</span><span class="sxs-lookup"><span data-stu-id="df2f3-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="df2f3-195">**Verwalten Sie ein erneuerndes Dokument, das alle Versionen enthält.**</span><span class="sxs-lookup"><span data-stu-id="df2f3-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="df2f3-196">Standardmäßig enthält jedes SharePoint- und OneDrive-Dokument einen Versionsverlauf, der im Element „Menü“ zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="df2f3-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="df2f3-197">In diesem Versionsverlauf können Sie leicht sehen, welche Versionen Datensätze sind und diese Dokumente anzeigen.</span><span class="sxs-lookup"><span data-stu-id="df2f3-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="df2f3-198">Die Datensatzversionsverwaltung ist automatisch für alle Dokumente verfügbar, deren Aufbewahrungsbezeichnung das Element als Datensatz kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="df2f3-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="df2f3-199">Wenn ein Benutzer die Dokumenteigenschaften im Detailbereich anzeigt, kann er den **Datensatzstatus** von **Gesperrt** auf **Entsperrt** umschalten.</span><span class="sxs-lookup"><span data-stu-id="df2f3-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="df2f3-200">Diese Aktion erstellt einen Datensatz im Ordner "Datensätze" in dem permanenten Dokumentarchiv, in dem er sich für den Rest seiner Aufbewahrungsdauer befindet.</span><span class="sxs-lookup"><span data-stu-id="df2f3-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="df2f3-201">Während das Dokument entsperrt ist, kann jeder Benutzer mit Standardbearbeitungsberechtigungen die Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="df2f3-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="df2f3-202">Benutzer können die Datei jedoch nicht löschen, da es sich immer noch um einen Datensatz handelt.</span><span class="sxs-lookup"><span data-stu-id="df2f3-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="df2f3-203">Wenn die Bearbeitung abgeschlossen ist, kann ein Benutzer den **Datensatzstatus** von **Entsperrt** auf **Gesperrt** umschalten, wodurch weitere Änderungen in diesem Status verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Datensatzstatus-Eigenschaft in einem Dokument, das als Datensatz gekennzeichnet ist](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="df2f3-205">Sperren und Entsperren eines Datensatzes</span><span class="sxs-lookup"><span data-stu-id="df2f3-205">Locking and unlocking a record</span></span>

<span data-ttu-id="df2f3-206">Nachdem eine Aufbewahrungsbezeichnung, die den Inhalt als Datensatz kennzeichnet, auf ein Dokument angewendet wurde, kann jeder Benutzer mit Beitragsberechtigungen oder einer engeren Berechtigungsstufe einen Datensatz entsperren oder einen entsperrten Datensatz sperren.</span><span class="sxs-lookup"><span data-stu-id="df2f3-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Der Datensatzstatus zeigt, dass das Datensatzdokument entsperrt ist](../media/recordversioning9.png)

<span data-ttu-id="df2f3-208">Wenn ein Benutzer einen Datensatz entsperrt, werden die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="df2f3-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="df2f3-209">Wenn für die aktuelle Websitesammlung kein Permanentes Dokumentarchiv vorhanden ist, wird eine erstellt.</span><span class="sxs-lookup"><span data-stu-id="df2f3-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="df2f3-210">Wenn das permanente Dokumentarchiv nicht über einen Datensatzordner verfügt, wird einer erstellt.</span><span class="sxs-lookup"><span data-stu-id="df2f3-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="df2f3-211">Eine **Kopieren in**-Aktion kopiert die neueste Version des Dokuments in den Ordner „Datensätze“.</span><span class="sxs-lookup"><span data-stu-id="df2f3-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="df2f3-212">Die Aktion **Kopieren in** ist nur für die neueste Version und für keine früheren Versionen wirksam.</span><span class="sxs-lookup"><span data-stu-id="df2f3-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="df2f3-213">Dieses kopierte Dokument wird jetzt als Datensatzversion des Dokuments betrachtet, und der Dateiname hat das Format: \[Titel GUID Version\#\]</span><span class="sxs-lookup"><span data-stu-id="df2f3-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="df2f3-214">Die im Ordner "Datensätze" erstellte Kopie wird dem Versionsverlauf des Originaldokuments hinzugefügt. In dieser Version wird das Wort **Datensatz** im Kommentarfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df2f3-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="df2f3-215">Das Originaldokument ist eine neue Version, die bearbeitet, aber nicht gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="df2f3-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="df2f3-216">In der Spalte Dokumentbibliothek **Element ist ein Datensatz** wird weiterhin der Wert **Ja** angezeigt, da das Dokument weiterhin ein Datensatz ist, auch wenn es jetzt bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="df2f3-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="df2f3-217">Wenn ein Benutzer einen Datensatz sperrt, kann das ursprüngliche Dokument erneut nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="df2f3-218">Es handelt sich aber um die Aktion zum Entsperren eines Datensatzes, der eine Version in den Ordner „Datensätze“ in dem permanenten Dokumentarchiv kopiert.</span><span class="sxs-lookup"><span data-stu-id="df2f3-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="df2f3-219">Datensatzversionen</span><span class="sxs-lookup"><span data-stu-id="df2f3-219">Record versions</span></span>

<span data-ttu-id="df2f3-220">Jedes Mal, wenn ein Benutzer einen Datensatz entsperrt, wird die aktuelle Version in den Ordner Datensätze in dem permanenten Dokumentarchiv kopiert, und diese Version enthält den Wert **Datensatz** im Feld **Kommentare** des Versionsverlaufs.</span><span class="sxs-lookup"><span data-stu-id="df2f3-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Datensatz, der in dem permanenten Dokumentarchiv angezeigt wird](../media/recordversioning10.png)

<span data-ttu-id="df2f3-222">Um den Versionsverlauf anzuzeigen, wählen Sie ein Dokument in der Dokumentbibliothek aus, und klicken Sie dann im Element „Menü“ auf **Versionsverlauf**.</span><span class="sxs-lookup"><span data-stu-id="df2f3-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="df2f3-223">Speicherort von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="df2f3-223">Where records are stored</span></span>

<span data-ttu-id="df2f3-224">Die Datensätze werden im Ordner „Datensätze“ in dem permanenten Dokumentarchiv auf der Website auf oberster Ebene in der Websitesammlung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="df2f3-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="df2f3-225">Wählen Sie in der linken Navigation auf der Site der obersten Ebene die Option **Siteinhalte** \> **Permanentes Dokumentarchiv**.</span><span class="sxs-lookup"><span data-stu-id="df2f3-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Permanentes Dokumentarchiv](../media/recordversioning11.png)

<br/><br/>

![Datensatzordner in dem permanenten Dokumentarchiv](../media/recordversioning12.png)

<span data-ttu-id="df2f3-228">Das permanente Dokumentarchiv ist nur für Websitesammlungsadministratoren sichtbar.</span><span class="sxs-lookup"><span data-stu-id="df2f3-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="df2f3-229">Außerdem ist das permanente Dokumentarchiv nicht standardmäßig vorhanden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="df2f3-230">Er wird nur erstellt, wenn Inhalte, die einer Aufbewahrungsbezeichnung oder einer Aufbewahrungsrichtlinie unterliegen, zum ersten Mal in der Websitesammlung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="df2f3-231">Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="df2f3-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="df2f3-232">Die Aktionen zum Sperren und Entsperren von Datensätzen werden im Überwachungsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="df2f3-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="df2f3-233">Sie können nach den spezifischen Aktivitäten **Datensatzstatus auf „gesperrt“ geändert** und **Datensatzstatus auf „entsperrt“ geändert** suchen, die sich im Abschnitt **Datei- und Seitenaktivitäten** auf der Dropdownliste **Aktivitäten** auf der Seite **Überprüfungsprotokoll durchsuchen** im Security & Compliance Center befinden.</span><span class="sxs-lookup"><span data-stu-id="df2f3-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung](../media/recordversioning13.png)

<span data-ttu-id="df2f3-235">Weitere Informationen zum Durchsuchen dieser Ereignisse finden Sie im Abschnitt „Datei- und Seitenaktivitäten“ im [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="df2f3-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="df2f3-236">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="df2f3-236">Next steps</span></span>

<span data-ttu-id="df2f3-237">Wenn Sie noch keine Aufbewahrungsbezeichnungen für die Datensatzverwaltung besitzen, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="df2f3-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="df2f3-238">Informationen zur Löschung von Datensätzen finden Sie unter [Löschen von Inhalten](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="df2f3-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
