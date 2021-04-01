---
title: Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind
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
description: Mehr zu Datensätzen, die Ihnen bei der Implementierung einer Datensatzverwaltungslösung in Microsoft 365 unterstützen.
ms.openlocfilehash: 5c828f06f2ce9e2bd18869f897f1f372c1a62f21
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471124"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="f2a19-103">Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind</span><span class="sxs-lookup"><span data-stu-id="f2a19-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="f2a19-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="f2a19-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

>[!NOTE] 
> <span data-ttu-id="f2a19-105">Da regulatorische Datensätze die Bearbeitung blockieren, ist die Versionsverwaltung für diese Datensätze nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2a19-105">Because regulatory records block editing, record versioning is not available for regulatory records.</span></span>

<span data-ttu-id="f2a19-106">Die Möglichkeit, ein Dokument als [Datensatz](records-management.md#records) zu markieren und Aktionen einzuschränken, die für den Datensatz ausgeführt werden können, ist ein wesentliches Ziel jeder Datensatzverwaltungslösung.</span><span class="sxs-lookup"><span data-stu-id="f2a19-106">The ability to mark a document as a [record](records-management.md#records) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="f2a19-107">Möglicherweise ist jedoch auch eine Zusammenarbeit erforderlich, damit Benutzer nachfolgende Versionen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f2a19-107">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="f2a19-108">Beispielsweise können Sie einen Kaufvertrag als Datensatz markieren, müssen dann jedoch den Vertrag mit neuen Bedingungen aktualisieren und die neueste Version als neuen Datensatz markieren, während die vorherige Datensatzversion beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="f2a19-108">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="f2a19-109">Bei diesen Szenarien unterstützt SharePoint und OneDrive die *Versionsverwaltung für Datensätze*.</span><span class="sxs-lookup"><span data-stu-id="f2a19-109">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="f2a19-110">OneNote-Notizbuchordner unterstützen keine Datensatzversionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f2a19-110">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="f2a19-111">Wenn Sie die Datensatzversionsverwaltung verwenden möchten, [bezeichnen Sie zunächst das Dokument markieren es als Datensatz](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="f2a19-111">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="f2a19-112">Zu diesem Zeitpunkt wird neben der Aufbewahrungsbezeichnung eine Dokumenteigenschaft mit dem Namen *Datensatzstatus* angezeigt, und der anfängliche Datensatzstatus ist **Gesperrt**.</span><span class="sxs-lookup"><span data-stu-id="f2a19-112">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="f2a19-113">Sie können jetzt Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="f2a19-113">You can now do the following things:</span></span>

  - <span data-ttu-id="f2a19-114">**Bearbeiten und speichern Sie einzelne Versionen des Dokuments kontinuierlich als Datensätze, indem Sie die Eigenschaft Datensatzstatus entsperren und sperren.**</span><span class="sxs-lookup"><span data-stu-id="f2a19-114">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="f2a19-115">Nur wenn die Eigenschaft **Datensatzstatus** auf **Gesperrt** gesetzt ist, wird eine neue Version des Datensatzes beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f2a19-115">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="f2a19-116">Durch das Umschalten zwischen gesperrt und entsperrt wird das Risiko verringert, dass unnötige Versionen und Kopien des Dokuments aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="f2a19-116">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="f2a19-117">**Lassen Sie die Datensätze automatisch in einem in-situ-Datensatzrepository speichern, das sich in der Websitesammlung befindet.**</span><span class="sxs-lookup"><span data-stu-id="f2a19-117">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="f2a19-118">Jede Websitesammlung in SharePoint und OneDrive bewahrt Inhalte in ihrer Aufbewahrungsspeicherbibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="f2a19-118">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="f2a19-119">Datensatzversionen werden im Ordner „Datensätze“ in dieser Bibliothek gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f2a19-119">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="f2a19-120">**Verwalten Sie ein erneuerndes Dokument, das alle Versionen enthält.**</span><span class="sxs-lookup"><span data-stu-id="f2a19-120">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="f2a19-121">Standardmäßig enthält jedes SharePoint- und OneDrive-Dokument einen Versionsverlauf, der im Element „Menü“ zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="f2a19-121">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="f2a19-122">In diesem Versionsverlauf können Sie leicht sehen, welche Versionen Datensätze sind und diese Dokumente anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2a19-122">In this version history, you can easily see which versions are records and view those documents.</span></span>

> [!TIP]
> <span data-ttu-id="f2a19-123">Wenn Sie die Datensatzversionierung mit einer Aufbewahrungsbezeichnung verwenden, das eine Löschaktion umfasst, empfiehlt es sich, auch die Aufbewahrungseinstellung so zu konfigurieren, dass der **Aufbewahrungszeitraum darauf basiert** werden **wann Elemente bezeichnet wurden**.</span><span class="sxs-lookup"><span data-stu-id="f2a19-123">When you use record versioning with a retention label that has a delete action, consider configuring the retention setting **Start the retention period based on:** to be **When items were labeled**.</span></span> <span data-ttu-id="f2a19-124">Mit dieser Bezeichnungseinstellung wird der Beginn des Aufbewahrungszeitraums für jede neue Datensatzversion zurückgesetzt, wodurch sichergestellt wird, dass ältere Versionen vor neueren Versionen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f2a19-124">With this label setting, the start of the retention period is reset for each new record version, which ensures that older versions will be deleted before newer versions.</span></span>

<span data-ttu-id="f2a19-125">Die Datensatzversionsverwaltung ist automatisch für alle Dokumente verfügbar, deren Aufbewahrungsbezeichnung das Element als Datensatz kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f2a19-125">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="f2a19-126">Wenn ein Benutzer die Dokumenteigenschaften im Detailbereich anzeigt, kann er den **Datensatzstatus** von **Gesperrt** auf **Entsperrt** umschalten.</span><span class="sxs-lookup"><span data-stu-id="f2a19-126">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="f2a19-127">Diese Aktion erstellt einen Datensatz im Ordner "Datensätze" in dem permanenten Dokumentarchiv, in dem er sich für den Rest seiner Aufbewahrungsdauer befindet.</span><span class="sxs-lookup"><span data-stu-id="f2a19-127">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="f2a19-128">Während das Dokument entsperrt ist, kann jeder Benutzer mit Standardbearbeitungsberechtigungen die Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f2a19-128">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="f2a19-129">Benutzer können die Datei jedoch nicht löschen, da es sich immer noch um einen Datensatz handelt.</span><span class="sxs-lookup"><span data-stu-id="f2a19-129">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="f2a19-130">Wenn die Bearbeitung abgeschlossen ist, kann ein Benutzer den **Datensatzstatus** von **Entsperrt** auf **Gesperrt** umschalten, wodurch weitere Änderungen in diesem Status verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="f2a19-130">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Datensatzstatus-Eigenschaft in einem Dokument, das als Datensatz gekennzeichnet ist](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="f2a19-132">Sperren und Entsperren eines Datensatzes</span><span class="sxs-lookup"><span data-stu-id="f2a19-132">Locking and unlocking a record</span></span>

<span data-ttu-id="f2a19-133">Nachdem eine Aufbewahrungsbezeichnung, die den Inhalt als Datensatz kennzeichnet, auf ein Dokument angewendet wurde, kann jeder Benutzer mit Beitragsberechtigungen oder einer engeren Berechtigungsstufe einen Datensatz entsperren oder einen entsperrten Datensatz sperren.</span><span class="sxs-lookup"><span data-stu-id="f2a19-133">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Der Datensatzstatus zeigt, dass das Datensatzdokument entsperrt ist](../media/recordversioning9.png)

<span data-ttu-id="f2a19-135">Wenn ein Benutzer einen Datensatz entsperrt, werden die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="f2a19-135">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="f2a19-136">Wenn für die aktuelle Websitesammlung kein Permanentes Dokumentarchiv vorhanden ist, wird eine erstellt.</span><span class="sxs-lookup"><span data-stu-id="f2a19-136">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="f2a19-137">Wenn das permanente Dokumentarchiv nicht über einen Datensatzordner verfügt, wird einer erstellt.</span><span class="sxs-lookup"><span data-stu-id="f2a19-137">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="f2a19-138">Eine **Kopieren in**-Aktion kopiert die neueste Version des Dokuments in den Ordner „Datensätze“.</span><span class="sxs-lookup"><span data-stu-id="f2a19-138">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="f2a19-139">Die Aktion **Kopieren in** ist nur für die neueste Version und für keine früheren Versionen wirksam.</span><span class="sxs-lookup"><span data-stu-id="f2a19-139">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="f2a19-140">Dieses kopierte Dokument wird jetzt als Datensatzversion des Dokuments betrachtet, und der Dateiname hat das Format: \[Titel GUID Version\#\]</span><span class="sxs-lookup"><span data-stu-id="f2a19-140">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="f2a19-141">Die im Ordner "Datensätze" erstellte Kopie wird dem Versionsverlauf des Originaldokuments hinzugefügt. In dieser Version wird das Wort **Datensatz** im Kommentarfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2a19-141">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="f2a19-142">Das Originaldokument ist eine neue Version, die bearbeitet, aber nicht gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2a19-142">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="f2a19-143">In der Spalte Dokumentbibliothek **Element ist ein Datensatz** wird weiterhin der Wert **Ja** angezeigt, da das Dokument weiterhin ein Datensatz ist, auch wenn es jetzt bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2a19-143">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="f2a19-144">Wenn ein Benutzer einen Datensatz sperrt, kann das ursprüngliche Dokument erneut nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f2a19-144">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="f2a19-145">Es handelt sich aber um die Aktion zum Entsperren eines Datensatzes, der eine Version in den Ordner „Datensätze“ in dem permanenten Dokumentarchiv kopiert.</span><span class="sxs-lookup"><span data-stu-id="f2a19-145">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="f2a19-146">Datensatzversionen</span><span class="sxs-lookup"><span data-stu-id="f2a19-146">Record versions</span></span>

<span data-ttu-id="f2a19-147">Jedes Mal, wenn ein Benutzer einen Datensatz entsperrt, wird die aktuelle Version in das permanente Dokumentarchiv kopiert, und diese Version enthält den Wert **Datensatz** im Feld **Kommentare** des Versionsverlaufs.</span><span class="sxs-lookup"><span data-stu-id="f2a19-147">Each time a user unlocks a record, the latest version is copied to the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Datensatz, der in dem permanenten Dokumentarchiv angezeigt wird](../media/recordversioning10.png)

<span data-ttu-id="f2a19-149">Um den Versionsverlauf anzuzeigen, wählen Sie ein Dokument in der Dokumentbibliothek aus, und klicken Sie dann im Element „Menü“ auf **Versionsverlauf**.</span><span class="sxs-lookup"><span data-stu-id="f2a19-149">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="f2a19-150">Speicherort von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="f2a19-150">Where records are stored</span></span>

<span data-ttu-id="f2a19-151">Die Datensätze werden im Ordner „Datensätze“ in dem permanenten Dokumentarchiv auf der Website auf oberster Ebene in der Websitesammlung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f2a19-151">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="f2a19-152">Wählen Sie in der linken Navigation auf der Site der obersten Ebene die Option **Siteinhalte** \> **Permanentes Dokumentarchiv**.</span><span class="sxs-lookup"><span data-stu-id="f2a19-152">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Permanentes Dokumentarchiv](../media/recordversioning11.png)

<br/><br/>

![Datensatzordner in dem permanenten Dokumentarchiv](../media/recordversioning12.png)

<span data-ttu-id="f2a19-155">Weitere Informationen zur Funktionsweise des permanenten Dokumentarchivs finden Sie unter [Funktionsweise der Aufbewahrung für SharePoint und OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span><span class="sxs-lookup"><span data-stu-id="f2a19-155">For more information about how the Preservation Hold library works, see [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="f2a19-156">Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f2a19-156">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="f2a19-157">Die Aktionen zum Sperren und Entsperren von Datensätzen werden im Überwachungsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="f2a19-157">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="f2a19-158">Wählen Sie unter **Datei- und Seitenaktivitäten** die Optionen **Datensatzstatus in „Gesperrt“ geändert** und **Datensatzstatus in „Entsperrt“ geändert** aus.</span><span class="sxs-lookup"><span data-stu-id="f2a19-158">From **File and page activities**, select **Changed record status to locked** and **Changed record status to unlocked**.</span></span>

<span data-ttu-id="f2a19-159">Weitere Informationen für die Suche nach diesen Ereignissen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="f2a19-159">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2a19-160">Weitere Schritte</span><span class="sxs-lookup"><span data-stu-id="f2a19-160">Next steps</span></span>

<span data-ttu-id="f2a19-161">Weitere von der Datensatzverwaltung unterstützte Szenarien finden Sie unter [Häufige Szenarios für die Datensatzverwaltung](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="f2a19-161">For other scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>