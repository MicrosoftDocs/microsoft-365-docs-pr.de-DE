---
title: Überprüfen von Nachweisdaten
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 20ac1adb67014439110e355025b31753a4a6bcfe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082551"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="897fb-102">Überprüfen von Nachweisdaten</span><span class="sxs-lookup"><span data-stu-id="897fb-102">Review the data in evidence</span></span>

<span data-ttu-id="897fb-103">Die Daten in einem in einer Daten Untersuchung festgelegten Beweis sind eine Momentaufnahme der Suchergebnisse, die Sie gesammelt und dem Beweissatz hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="897fb-103">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="897fb-104">Wenn Sie Suchergebnisse zu beweisen hinzufügen, wird ein Prozess ausgelöst, um Dateien, Metadaten und Text aus den Elementen zu extrahieren, die von der Suche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="897fb-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="897fb-105">Anschließend erstellt das Tool Daten Untersuchungen (Vorschau) einen neuen Index (durch einen Prozess mit dem Namen *Advanced Indexing*) aller Daten und fügt einen auf der Registerkarte **Beweise** festgelegten Beweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="897fb-105">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="897fb-106">Bei zeitkritischen Untersuchungen können Sie dadurch schnell die Umgebung eindämmen, indem Sie die tatsächlichen verschütteten oder bösartigen Daten löschen, die sich in der ursprünglichen Datenquelle befinden, und gleichzeitig die Möglichkeit haben, die neu erstellten Beweise in einer in Quarantäne befindliche Umgebungen, in diesem Fall die Daten, die in den Beweissatz kopiert werden).</span><span class="sxs-lookup"><span data-stu-id="897fb-106">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="897fb-107">Nachdem die Beweise gesammelt und dem Beweissatz hinzugefügt wurden, können Sie einzelne Dokumente in ihrem systemeigenen Format, im Text Format oder in einem fast systemeigenen Format überprüfen, das Sie zum Beschriften und redact von Dokumenten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="897fb-107">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="897fb-108">Darüber hinaus können Sie Abfragen ausführen, um die festgelegten Daten nach Zeitbereich, Dateitypen, Datenbesitzern und vielen anderen Eigenschaften und Suchbedingungen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="897fb-108">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="897fb-109">Beispielsweise können Sie mithilfe der Autoren-, Absender-oder Empfängerbedingungen schnell erkennen, welche Personen an dem Vorfall beteiligt sind und ob Daten aus Ihrer Organisation für externe Benutzer freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="897fb-109">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="897fb-110">Weitere Informationen zum Durchsuchen von Daten in einem Beweis Sätze finden Sie unter [Abfragen der Daten in Evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="897fb-110">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="897fb-111">Um Dokumente zu gruppieren und weitere Unterstützung für Ihre Überprüfung zu erhalten, wählen Sie auf der Registerkarte **Beweise** einen Beweissatz aus, und klicken Sie dann auf **Beweise verwalten**.</span><span class="sxs-lookup"><span data-stu-id="897fb-111">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="897fb-112">Klicken Sie in der **Analyse** Kachel auf **Analyse für die gesamte Gruppe neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="897fb-112">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="897fb-113">Dadurch werden erweiterte Analysen wie doppelte Erkennung, e-Mail-Threading und Design Analyse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="897fb-113">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="897fb-114">Anschließend können Sie die allgemeinen Themen der Daten anzeigen und auch Dokumente per e-Mail-Threads, in der Nähe von Duplikaten und genaue Duplikate organisieren, um Ihre Untersuchung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="897fb-114">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="897fb-115">Weitere Informationen finden Sie unter [Ausführen von Analysen, um schneller zu untersuchen](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="897fb-115">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="897fb-116">Anzeigen von Dokumenten in Evidence</span><span class="sxs-lookup"><span data-stu-id="897fb-116">View documents in evidence</span></span>

<span data-ttu-id="897fb-117">Mit den Daten Ermittlungen (Preview) können Sie Inhalte in verschiedenen Viewern anzeigen, wobei jeder Betrachter einen anderen Zweck hat.</span><span class="sxs-lookup"><span data-stu-id="897fb-117">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="897fb-118">Diese Viewer sind:</span><span class="sxs-lookup"><span data-stu-id="897fb-118">These viewers are:</span></span>

- <span data-ttu-id="897fb-119">Datei Metadaten</span><span class="sxs-lookup"><span data-stu-id="897fb-119">File metadata</span></span>
- <span data-ttu-id="897fb-120">Systemeigene Ansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-120">Native view</span></span>
- <span data-ttu-id="897fb-121">Text Ansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-121">Text view</span></span>
- <span data-ttu-id="897fb-122">Ansicht mit Anmerkungen versehen</span><span class="sxs-lookup"><span data-stu-id="897fb-122">Annotate view</span></span>

<span data-ttu-id="897fb-123">Um auf einen dieser Viewer zuzugreifen, wählen Sie einfach ein Dokument in einem Beweissatzes aus.</span><span class="sxs-lookup"><span data-stu-id="897fb-123">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="897fb-124">Datei Metadaten</span><span class="sxs-lookup"><span data-stu-id="897fb-124">File metadata</span></span>

<span data-ttu-id="897fb-125">In dieser Ansicht werden verschiedene Metadaten-Eigenschaften angezeigt, die mit dem ausgewählten Dokument verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="897fb-125">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="897fb-126">Sie können diese Ansicht aktivieren und deaktivieren, indem Sie auf **Datei Metadaten**klicken.</span><span class="sxs-lookup"><span data-stu-id="897fb-126">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="897fb-127">Wenn Sie ein Dokument überprüfen, können Sie die Datei Metadaten anzeigen und sich immer noch zwischen den verschiedenen Viewern ändern.</span><span class="sxs-lookup"><span data-stu-id="897fb-127">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="897fb-128">Im folgenden finden Sie ein Beispiel für die Datei Metadaten für ein Dokument.</span><span class="sxs-lookup"><span data-stu-id="897fb-128">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="897fb-129">Weitere Informationen zu den Metadaten-Feldern finden Sie unter [Document Metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="897fb-129">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![Datei Metadaten-Bereich](media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="897fb-131">Systemeigene Ansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-131">Native view</span></span>

<span data-ttu-id="897fb-132">Der systemeigene Viewer zeigt die genaueste Ansicht eines Dokuments im systemeigenen Format an.</span><span class="sxs-lookup"><span data-stu-id="897fb-132">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="897fb-133">Native View wird für Hunderte von Dateitypen unterstützt und ist für die Anzeige von Dokumenten in der wahrsten nativen Umgebung möglich.</span><span class="sxs-lookup"><span data-stu-id="897fb-133">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="897fb-134">Für Microsoft Office Dateien verwendet der systemeigene Viewer die Webversion von Office-Apps.</span><span class="sxs-lookup"><span data-stu-id="897fb-134">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="897fb-135">Auf diese Weise können Sie Inhalte wie Kommentare in verschiedenen Office-Dokumenten, Formeln und ausgeblendeten Zeilen/Spalten in Excel und die Notizenansicht in PowerPoint anzeigen.</span><span class="sxs-lookup"><span data-stu-id="897fb-135">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="897fb-136">Systemeigene Ansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-136">Native view</span></span>
](media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="897fb-137">Text Ansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-137">Text view</span></span>

<span data-ttu-id="897fb-138">Der Text Betrachter bietet eine Ansicht des extrahierten Texts einer Datei.</span><span class="sxs-lookup"><span data-stu-id="897fb-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="897fb-139">Eingebettete Bilder und Formatierungen werden ignoriert, aber diese Ansicht ist sehr nützlich, wenn Sie versuchen, den Inhalt eines Dokuments schnell zu überprüfen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="897fb-139">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="897fb-140">Die Text Ansicht umfasst auch die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="897fb-140">Text view also includes these features:</span></span>

  - <span data-ttu-id="897fb-141">Ein Leistungsindikator, der das verweisen auf bestimmte Teile eines Dokuments erleichtert.</span><span class="sxs-lookup"><span data-stu-id="897fb-141">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="897fb-142">Hervorheben von Suchtreffern, die Begriffe im Dokument sowie auf der Bildlaufleiste hervorheben</span><span class="sxs-lookup"><span data-stu-id="897fb-142">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="897fb-143">Eine diff-Ansicht bietet eine Vergleichsansicht, in der die Textunterschiede beim Anzeigen von Dokumenten mithilfe des Bereichs **nahe Duplikate** hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="897fb-143">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="897fb-144">**Beispiel für einen Leistungsindikator und eine Hervorhebung von Suchtreffern in Text und ScrollBar**</span><span class="sxs-lookup"><span data-stu-id="897fb-144">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="897fb-145">Text Ansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-145">Text view</span></span>
](media/Reviewimage4.png)

<span data-ttu-id="897fb-146">**Beispiel für die diff-Ansicht**</span><span class="sxs-lookup"><span data-stu-id="897fb-146">**Example of the diff view**</span></span>

![<span data-ttu-id="897fb-147">Vergleichsansicht</span><span class="sxs-lookup"><span data-stu-id="897fb-147">Diff view</span></span>
](media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="897fb-148">Ansicht mit Anmerkungen versehen</span><span class="sxs-lookup"><span data-stu-id="897fb-148">Annotate view</span></span>

<span data-ttu-id="897fb-149">Die Ansicht Anmerkungen enthält Features, mit denen Sie während des Überprüfungsprozesses Markup für ein Dokument anwenden können. Dazu gehören die folgenden Tools:</span><span class="sxs-lookup"><span data-stu-id="897fb-149">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="897fb-150">**Area-Aktionen** – Sie können ein deckendes Feld im Dokument zeichnen, in dem vertrauliche Inhalte ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="897fb-150">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="897fb-151">**Bleistift** – Sie können frei Handzeichen für ein Dokument freigeben, um die Aufmerksamkeit auf bestimmte Teile des Inhalts zu lenken.</span><span class="sxs-lookup"><span data-stu-id="897fb-151">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="897fb-152">**Anmerkungen auswählen** – Sie können Anmerkungen in einem Dokument auswählen und löschen.</span><span class="sxs-lookup"><span data-stu-id="897fb-152">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="897fb-153">**Anmerkungs Transparenz umschalten** – Sie können die Transparenz von Anmerkungen umschalten (zwischen opak und halbtransparent), damit Sie den Inhalt hinter der Anmerkung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="897fb-153">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="897fb-154">Dies umfasst das Umschalten der Transparenz von Bleistift Anmerkungen und-Aktionen.</span><span class="sxs-lookup"><span data-stu-id="897fb-154">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="897fb-155">Die anmerkungsansicht bietet auch die folgende Navigationsfunktionalität:</span><span class="sxs-lookup"><span data-stu-id="897fb-155">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="897fb-156">**Vorherige Seite**, **Nächste Seite**, und **Navigieren Sie zu Seiten** Navigationssteuerelementen, die für mehrseitige Dokumente verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="897fb-156">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="897fb-157">**Zoom** – erhöht oder verkleinert die Größe von Dokumenten in der Ansicht Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="897fb-157">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="897fb-158">**Drehen** – Dokumente im Uhrzeigersinn drehen.</span><span class="sxs-lookup"><span data-stu-id="897fb-158">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="897fb-159">**Suche** – suchen Sie nach Stichwörtern in einem Dokument, und verwenden Sie dann die vorherigen und nächsten Steuerelemente, um die Treffer (die hervorgehoben werden) im Dokument anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="897fb-159">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="897fb-160">**Beispiel für die Ansicht "anmerken"**</span><span class="sxs-lookup"><span data-stu-id="897fb-160">**Example of Annotate view**</span></span>

![Ansicht mit Anmerkungen versehen](media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="897fb-162">Anmerkungen werden auf eine Kopie des Dokuments angewendet, die dem Beweissatz hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="897fb-162">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="897fb-163">Die ursprünglichen Dokumente im Live-Dienst werden nicht kommentiert.</span><span class="sxs-lookup"><span data-stu-id="897fb-163">The original documents in the live service aren't annotated.</span></span>
