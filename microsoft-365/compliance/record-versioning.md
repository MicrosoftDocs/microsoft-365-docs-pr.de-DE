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
ms.openlocfilehash: 943bf3949ab57eb4603695495d7a8ca0c4b90db7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695249"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="2f67e-103">Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind</span><span class="sxs-lookup"><span data-stu-id="2f67e-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="2f67e-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="2f67e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="2f67e-105">Die Möglichkeit, ein Dokument als [Datensatz](records.md) zu markieren und Aktionen einzuschränken, die für den Datensatz ausgeführt werden können, ist ein wesentliches Ziel jeder Datensatzverwaltungslösung.</span><span class="sxs-lookup"><span data-stu-id="2f67e-105">The ability to mark a document as a [record](records.md) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="2f67e-106">Möglicherweise ist jedoch auch eine Zusammenarbeit erforderlich, damit Benutzer nachfolgende Versionen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="2f67e-106">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="2f67e-107">Beispielsweise können Sie einen Kaufvertrag als Datensatz markieren, müssen dann jedoch den Vertrag mit neuen Bedingungen aktualisieren und die neueste Version als neuen Datensatz markieren, während die vorherige Datensatzversion beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="2f67e-107">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="2f67e-108">Bei diesen Szenarien unterstützt SharePoint und OneDrive die *Versionsverwaltung für Datensätze*.</span><span class="sxs-lookup"><span data-stu-id="2f67e-108">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="2f67e-109">OneNote-Notizbuchordner unterstützen keine Datensatzversionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="2f67e-109">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="2f67e-110">Wenn Sie die Datensatzversionsverwaltung verwenden möchten, [bezeichnen Sie zunächst das Dokument markieren es als Datensatz](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="2f67e-110">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="2f67e-111">Zu diesem Zeitpunkt wird neben der Aufbewahrungsbezeichnung eine Dokumenteigenschaft mit dem Namen *Datensatzstatus* angezeigt, und der anfängliche Datensatzstatus ist **Gesperrt**.</span><span class="sxs-lookup"><span data-stu-id="2f67e-111">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="2f67e-112">Sie können jetzt Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="2f67e-112">You can now do the following things:</span></span>

  - <span data-ttu-id="2f67e-113">**Bearbeiten und speichern Sie einzelne Versionen des Dokuments kontinuierlich als Datensätze, indem Sie die Eigenschaft Datensatzstatus entsperren und sperren.**</span><span class="sxs-lookup"><span data-stu-id="2f67e-113">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="2f67e-114">Nur wenn die Eigenschaft **Datensatzstatus** auf **Gesperrt** gesetzt ist, wird eine neue Version des Datensatzes beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2f67e-114">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="2f67e-115">Durch das Umschalten zwischen gesperrt und entsperrt wird das Risiko verringert, dass unnötige Versionen und Kopien des Dokuments aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="2f67e-115">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="2f67e-116">**Lassen Sie die Datensätze automatisch in einem in-situ-Datensatzrepository speichern, das sich in der Websitesammlung befindet.**</span><span class="sxs-lookup"><span data-stu-id="2f67e-116">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="2f67e-117">Jede Websitesammlung in SharePoint und OneDrive bewahrt Inhalte in ihrer Aufbewahrungsspeicherbibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="2f67e-117">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="2f67e-118">Datensatzversionen werden im Ordner „Datensätze“ in dieser Bibliothek gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2f67e-118">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="2f67e-119">**Verwalten Sie ein erneuerndes Dokument, das alle Versionen enthält.**</span><span class="sxs-lookup"><span data-stu-id="2f67e-119">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="2f67e-120">Standardmäßig enthält jedes SharePoint- und OneDrive-Dokument einen Versionsverlauf, der im Element „Menü“ zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="2f67e-120">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="2f67e-121">In diesem Versionsverlauf können Sie leicht sehen, welche Versionen Datensätze sind und diese Dokumente anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f67e-121">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="2f67e-122">Die Datensatzversionsverwaltung ist automatisch für alle Dokumente verfügbar, deren Aufbewahrungsbezeichnung das Element als Datensatz kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="2f67e-122">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="2f67e-123">Wenn ein Benutzer die Dokumenteigenschaften im Detailbereich anzeigt, kann er den **Datensatzstatus** von **Gesperrt** auf **Entsperrt** umschalten.</span><span class="sxs-lookup"><span data-stu-id="2f67e-123">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="2f67e-124">Diese Aktion erstellt einen Datensatz im Ordner "Datensätze" in dem permanenten Dokumentarchiv, in dem er sich für den Rest seiner Aufbewahrungsdauer befindet.</span><span class="sxs-lookup"><span data-stu-id="2f67e-124">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="2f67e-125">Während das Dokument entsperrt ist, kann jeder Benutzer mit Standardbearbeitungsberechtigungen die Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2f67e-125">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="2f67e-126">Benutzer können die Datei jedoch nicht löschen, da es sich immer noch um einen Datensatz handelt.</span><span class="sxs-lookup"><span data-stu-id="2f67e-126">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="2f67e-127">Wenn die Bearbeitung abgeschlossen ist, kann ein Benutzer den **Datensatzstatus** von **Entsperrt** auf **Gesperrt** umschalten, wodurch weitere Änderungen in diesem Status verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="2f67e-127">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Datensatzstatus-Eigenschaft in einem Dokument, das als Datensatz gekennzeichnet ist](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="2f67e-129">Sperren und Entsperren eines Datensatzes</span><span class="sxs-lookup"><span data-stu-id="2f67e-129">Locking and unlocking a record</span></span>

<span data-ttu-id="2f67e-130">Nachdem eine Aufbewahrungsbezeichnung, die den Inhalt als Datensatz kennzeichnet, auf ein Dokument angewendet wurde, kann jeder Benutzer mit Beitragsberechtigungen oder einer engeren Berechtigungsstufe einen Datensatz entsperren oder einen entsperrten Datensatz sperren.</span><span class="sxs-lookup"><span data-stu-id="2f67e-130">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Der Datensatzstatus zeigt, dass das Datensatzdokument entsperrt ist](../media/recordversioning9.png)

<span data-ttu-id="2f67e-132">Wenn ein Benutzer einen Datensatz entsperrt, werden die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="2f67e-132">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="2f67e-133">Wenn für die aktuelle Websitesammlung kein Permanentes Dokumentarchiv vorhanden ist, wird eine erstellt.</span><span class="sxs-lookup"><span data-stu-id="2f67e-133">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="2f67e-134">Wenn das permanente Dokumentarchiv nicht über einen Datensatzordner verfügt, wird einer erstellt.</span><span class="sxs-lookup"><span data-stu-id="2f67e-134">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="2f67e-135">Eine **Kopieren in**-Aktion kopiert die neueste Version des Dokuments in den Ordner „Datensätze“.</span><span class="sxs-lookup"><span data-stu-id="2f67e-135">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="2f67e-136">Die Aktion **Kopieren in** ist nur für die neueste Version und für keine früheren Versionen wirksam.</span><span class="sxs-lookup"><span data-stu-id="2f67e-136">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="2f67e-137">Dieses kopierte Dokument wird jetzt als Datensatzversion des Dokuments betrachtet, und der Dateiname hat das Format: \[Titel GUID Version\#\]</span><span class="sxs-lookup"><span data-stu-id="2f67e-137">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="2f67e-138">Die im Ordner "Datensätze" erstellte Kopie wird dem Versionsverlauf des Originaldokuments hinzugefügt. In dieser Version wird das Wort **Datensatz** im Kommentarfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f67e-138">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="2f67e-139">Das Originaldokument ist eine neue Version, die bearbeitet, aber nicht gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f67e-139">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="2f67e-140">In der Spalte Dokumentbibliothek **Element ist ein Datensatz** wird weiterhin der Wert **Ja** angezeigt, da das Dokument weiterhin ein Datensatz ist, auch wenn es jetzt bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f67e-140">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="2f67e-141">Wenn ein Benutzer einen Datensatz sperrt, kann das ursprüngliche Dokument erneut nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2f67e-141">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="2f67e-142">Es handelt sich aber um die Aktion zum Entsperren eines Datensatzes, der eine Version in den Ordner „Datensätze“ in dem permanenten Dokumentarchiv kopiert.</span><span class="sxs-lookup"><span data-stu-id="2f67e-142">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="2f67e-143">Datensatzversionen</span><span class="sxs-lookup"><span data-stu-id="2f67e-143">Record versions</span></span>

<span data-ttu-id="2f67e-144">Jedes Mal, wenn ein Benutzer einen Datensatz entsperrt, wird die aktuelle Version in den Ordner Datensätze in dem permanenten Dokumentarchiv kopiert, und diese Version enthält den Wert **Datensatz** im Feld **Kommentare** des Versionsverlaufs.</span><span class="sxs-lookup"><span data-stu-id="2f67e-144">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Datensatz, der in dem permanenten Dokumentarchiv angezeigt wird](../media/recordversioning10.png)

<span data-ttu-id="2f67e-146">Um den Versionsverlauf anzuzeigen, wählen Sie ein Dokument in der Dokumentbibliothek aus, und klicken Sie dann im Element „Menü“ auf **Versionsverlauf**.</span><span class="sxs-lookup"><span data-stu-id="2f67e-146">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="2f67e-147">Speicherort von Datensätzen</span><span class="sxs-lookup"><span data-stu-id="2f67e-147">Where records are stored</span></span>

<span data-ttu-id="2f67e-148">Die Datensätze werden im Ordner „Datensätze“ in dem permanenten Dokumentarchiv auf der Website auf oberster Ebene in der Websitesammlung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2f67e-148">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="2f67e-149">Wählen Sie in der linken Navigation auf der Site der obersten Ebene die Option **Siteinhalte** \> **Permanentes Dokumentarchiv**.</span><span class="sxs-lookup"><span data-stu-id="2f67e-149">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Permanentes Dokumentarchiv](../media/recordversioning11.png)

<br/><br/>

![Datensatzordner in dem permanenten Dokumentarchiv](../media/recordversioning12.png)

<span data-ttu-id="2f67e-152">Das permanente Dokumentarchiv ist nur für Websitesammlungsadministratoren sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2f67e-152">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="2f67e-153">Außerdem ist das permanente Dokumentarchiv nicht standardmäßig vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2f67e-153">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="2f67e-154">Er wird nur erstellt, wenn Inhalte, die einer Aufbewahrungsbezeichnung oder einer Aufbewahrungsrichtlinie unterliegen, zum ersten Mal in der Websitesammlung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="2f67e-154">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="2f67e-155">Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="2f67e-155">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="2f67e-156">Die Aktionen zum Sperren und Entsperren von Datensätzen werden im Überwachungsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="2f67e-156">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="2f67e-157">Sie können nach den spezifischen Aktivitäten **Datensatzstatus auf „gesperrt“ geändert** und **Datensatzstatus auf „entsperrt“ geändert** suchen, die sich im Abschnitt **Datei- und Seitenaktivitäten** auf der Dropdownliste **Aktivitäten** auf der Seite **Überprüfungsprotokoll durchsuchen** im Security & Compliance Center befinden.</span><span class="sxs-lookup"><span data-stu-id="2f67e-157">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Durchsuchen des Überwachungsprotokolls nach Ereignissen für die Versionsverwaltung](../media/recordversioning13.png)

<span data-ttu-id="2f67e-159">Weitere Informationen zum Durchsuchen dieser Ereignisse finden Sie im Abschnitt „Datei- und Seitenaktivitäten“ im [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="2f67e-159">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f67e-160">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2f67e-160">Next steps</span></span>

<span data-ttu-id="2f67e-161">Mehr zu Inhalte als Datensatz markieren finden Sie unter [Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="2f67e-161">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>

<span data-ttu-id="2f67e-162">Informationen zur Löschung von Datensätzen finden Sie unter [Löschen von Inhalten](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="2f67e-162">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
