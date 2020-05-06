---
title: Überprüfen von Nachweisdaten
f1.keywords:
- NOCSH
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
description: Hier finden Sie Informationen zu Methoden zum Überprüfen der Daten in ihren beweisen, beispielsweise zum Anzeigen in systemeigenen, Text-oder near-nativen Formaten.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f094718bd14ee86ff8fdae482e86c22ecfbdc483
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034609"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="d6106-103">Überprüfen von Nachweisdaten</span><span class="sxs-lookup"><span data-stu-id="d6106-103">Review the data in evidence</span></span>

<span data-ttu-id="d6106-104">Die Daten in einem in einer Daten Untersuchung festgelegten Beweis sind eine Momentaufnahme der Suchergebnisse, die Sie gesammelt und dem Beweissatz hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="d6106-104">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="d6106-105">Wenn Sie Suchergebnisse zu beweisen hinzufügen, wird ein Prozess ausgelöst, um Dateien, Metadaten und Text aus den Elementen zu extrahieren, die von der Suche zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d6106-105">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="d6106-106">Anschließend erstellt das Tool Daten Untersuchungen (Vorschau) einen neuen Index (durch einen Prozess mit dem Namen *Advanced Indexing*) aller Daten und fügt einen auf der Registerkarte **Beweise** festgelegten Beweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6106-106">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="d6106-107">Bei zeitkritischen Untersuchungen können Sie dadurch die Umgebung schnell enthalten, indem Sie die tatsächlichen verschütteten oder bösartigen Daten löschen, die sich in der at-ursprünglichen Datenquelle befinden, und gleichzeitig das erneute Erstellen von Beweisen in einer isolierten Umgebung, in diesem Fall die Daten, die in den Beweissatz kopiert werden, untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d6106-107">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="d6106-108">Nachdem die Beweise gesammelt und dem Beweissatz hinzugefügt wurden, können Sie einzelne Dokumente in ihrem systemeigenen Format, im Text Format oder in einem fast systemeigenen Format überprüfen, das Sie zum Beschriften und redact von Dokumenten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d6106-108">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="d6106-109">Darüber hinaus können Sie Abfragen ausführen, um die festgelegten Daten nach Zeitbereich, Dateitypen, Datenbesitzern und vielen anderen Eigenschaften und Suchbedingungen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="d6106-109">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="d6106-110">Beispielsweise können Sie mithilfe der Autoren-, Absender-oder Empfängerbedingungen schnell erkennen, welche Personen an dem Vorfall beteiligt sind und ob Daten aus Ihrer Organisation für externe Benutzer freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="d6106-110">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="d6106-111">Weitere Informationen zum Durchsuchen von Daten in einem Beweis Sätze finden Sie unter [Abfragen der Daten in Evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="d6106-111">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="d6106-112">Um Dokumente zu gruppieren und weitere Unterstützung für Ihre Überprüfung zu erhalten, wählen Sie auf der Registerkarte **Beweise** einen Beweissatz aus, und klicken Sie dann auf **Beweise verwalten**.</span><span class="sxs-lookup"><span data-stu-id="d6106-112">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="d6106-113">Klicken Sie in der **Analyse** Kachel auf **Analyse für die gesamte Gruppe neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d6106-113">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="d6106-114">Dadurch werden erweiterte Analysen wie doppelte Erkennung, e-Mail-Threading und Design Analyse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6106-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="d6106-115">Anschließend können Sie die allgemeinen Themen der Daten anzeigen und auch Dokumente per e-Mail-Threads, in der Nähe von Duplikaten und genaue Duplikate organisieren, um Ihre Untersuchung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d6106-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="d6106-116">Weitere Informationen finden Sie unter [Ausführen von Analysen, um schneller zu untersuchen](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="d6106-116">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="d6106-117">Anzeigen von Dokumenten in Evidence</span><span class="sxs-lookup"><span data-stu-id="d6106-117">View documents in evidence</span></span>

<span data-ttu-id="d6106-118">Mit den Daten Ermittlungen (Preview) können Sie Inhalte in verschiedenen Viewern anzeigen, wobei jeder Betrachter einen anderen Zweck hat.</span><span class="sxs-lookup"><span data-stu-id="d6106-118">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="d6106-119">Diese Viewer sind:</span><span class="sxs-lookup"><span data-stu-id="d6106-119">These viewers are:</span></span>

- <span data-ttu-id="d6106-120">Dateimetadaten</span><span class="sxs-lookup"><span data-stu-id="d6106-120">File metadata</span></span>
- <span data-ttu-id="d6106-121">Systemeigene Ansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-121">Native view</span></span>
- <span data-ttu-id="d6106-122">Text Ansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-122">Text view</span></span>
- <span data-ttu-id="d6106-123">Ansicht mit Anmerkungen versehen</span><span class="sxs-lookup"><span data-stu-id="d6106-123">Annotate view</span></span>

<span data-ttu-id="d6106-124">Um auf einen dieser Viewer zuzugreifen, wählen Sie einfach ein Dokument in einem Beweissatzes aus.</span><span class="sxs-lookup"><span data-stu-id="d6106-124">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="d6106-125">Dateimetadaten</span><span class="sxs-lookup"><span data-stu-id="d6106-125">File metadata</span></span>

<span data-ttu-id="d6106-126">In dieser Ansicht werden verschiedene Metadaten-Eigenschaften angezeigt, die mit dem ausgewählten Dokument verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="d6106-126">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="d6106-127">Sie können diese Ansicht aktivieren und deaktivieren, indem Sie auf **Datei Metadaten**klicken.</span><span class="sxs-lookup"><span data-stu-id="d6106-127">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="d6106-128">Wenn Sie ein Dokument überprüfen, können Sie die Datei Metadaten anzeigen und sich immer noch zwischen den verschiedenen Viewern ändern.</span><span class="sxs-lookup"><span data-stu-id="d6106-128">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="d6106-129">Im folgenden finden Sie ein Beispiel für die Datei Metadaten für ein Dokument.</span><span class="sxs-lookup"><span data-stu-id="d6106-129">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="d6106-130">Weitere Informationen zu den Metadaten-Feldern finden Sie unter [Document Metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="d6106-130">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![Datei Metadaten-Bereich](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="d6106-132">Systemeigene Ansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-132">Native view</span></span>

<span data-ttu-id="d6106-133">Der systemeigene Viewer zeigt die genaueste Ansicht eines Dokuments im systemeigenen Format an.</span><span class="sxs-lookup"><span data-stu-id="d6106-133">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="d6106-134">Native View wird für Hunderte von Dateitypen unterstützt und ist für die Anzeige von Dokumenten in der wahrsten nativen Umgebung möglich.</span><span class="sxs-lookup"><span data-stu-id="d6106-134">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="d6106-135">Für Microsoft Office Dateien verwendet der systemeigene Viewer die Webversion von Office-Apps.</span><span class="sxs-lookup"><span data-stu-id="d6106-135">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="d6106-136">Auf diese Weise können Sie Inhalte wie Kommentare in verschiedenen Office-Dokumenten, Formeln und ausgeblendeten Zeilen/Spalten in Excel und die Notizenansicht in PowerPoint anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6106-136">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="d6106-137">Systemeigene Ansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-137">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="d6106-138">Text Ansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-138">Text view</span></span>

<span data-ttu-id="d6106-139">Der Text Betrachter bietet eine Ansicht des extrahierten Texts einer Datei.</span><span class="sxs-lookup"><span data-stu-id="d6106-139">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="d6106-140">Eingebettete Bilder und Formatierungen werden ignoriert, aber diese Ansicht ist sehr nützlich, wenn Sie versuchen, den Inhalt eines Dokuments schnell zu überprüfen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="d6106-140">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="d6106-141">Die Text Ansicht umfasst auch die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="d6106-141">Text view also includes these features:</span></span>

  - <span data-ttu-id="d6106-142">Ein Leistungsindikator, der das verweisen auf bestimmte Teile eines Dokuments erleichtert.</span><span class="sxs-lookup"><span data-stu-id="d6106-142">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="d6106-143">Hervorheben von Suchtreffern, die Begriffe im Dokument sowie auf der Bildlaufleiste hervorheben</span><span class="sxs-lookup"><span data-stu-id="d6106-143">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="d6106-144">Eine diff-Ansicht bietet eine Vergleichsansicht, in der die Textunterschiede beim Anzeigen von Dokumenten mithilfe des Bereichs **nahe Duplikate** hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="d6106-144">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="d6106-145">**Beispiel für einen Leistungsindikator und eine Hervorhebung von Suchtreffern in Text und ScrollBar**</span><span class="sxs-lookup"><span data-stu-id="d6106-145">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="d6106-146">Text Ansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-146">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="d6106-147">**Beispiel für die diff-Ansicht**</span><span class="sxs-lookup"><span data-stu-id="d6106-147">**Example of the diff view**</span></span>

![<span data-ttu-id="d6106-148">Vergleichsansicht</span><span class="sxs-lookup"><span data-stu-id="d6106-148">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="d6106-149">Ansicht mit Anmerkungen versehen</span><span class="sxs-lookup"><span data-stu-id="d6106-149">Annotate view</span></span>

<span data-ttu-id="d6106-150">Die Ansicht Anmerkungen enthält Features, mit denen Sie während des Überprüfungsprozesses Markup für ein Dokument anwenden können. Dazu gehören die folgenden Tools:</span><span class="sxs-lookup"><span data-stu-id="d6106-150">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="d6106-151">**Area-Aktionen** – Sie können ein deckendes Feld im Dokument zeichnen, in dem vertrauliche Inhalte ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6106-151">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="d6106-152">**Bleistift** – Sie können frei Handzeichen für ein Dokument freigeben, um die Aufmerksamkeit auf bestimmte Teile des Inhalts zu lenken.</span><span class="sxs-lookup"><span data-stu-id="d6106-152">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="d6106-153">**Anmerkungen auswählen** – Sie können Anmerkungen in einem Dokument auswählen und löschen.</span><span class="sxs-lookup"><span data-stu-id="d6106-153">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="d6106-154">**Anmerkungs Transparenz umschalten** – Sie können die Transparenz von Anmerkungen umschalten (zwischen opak und halbtransparent), damit Sie den Inhalt hinter der Anmerkung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="d6106-154">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="d6106-155">Dies umfasst das Umschalten der Transparenz von Bleistift Anmerkungen und-Aktionen.</span><span class="sxs-lookup"><span data-stu-id="d6106-155">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="d6106-156">Die anmerkungsansicht bietet auch die folgende Navigationsfunktionalität:</span><span class="sxs-lookup"><span data-stu-id="d6106-156">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="d6106-157">**Vorherige Seite**, **Nächste Seite**, und **Navigieren Sie zu Seiten** Navigationssteuerelementen, die für mehrseitige Dokumente verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d6106-157">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="d6106-158">**Zoom** – erhöht oder verkleinert die Größe von Dokumenten in der Ansicht Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="d6106-158">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="d6106-159">**Drehen** – Dokumente im Uhrzeigersinn drehen.</span><span class="sxs-lookup"><span data-stu-id="d6106-159">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="d6106-160">**Suche** – suchen Sie nach Stichwörtern in einem Dokument, und verwenden Sie dann die vorherigen und nächsten Steuerelemente, um die Treffer (die hervorgehoben werden) im Dokument anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6106-160">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="d6106-161">**Beispiel für die Ansicht "anmerken"**</span><span class="sxs-lookup"><span data-stu-id="d6106-161">**Example of Annotate view**</span></span>

![Ansicht mit Anmerkungen versehen](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="d6106-163">Anmerkungen werden auf eine Kopie des Dokuments angewendet, die dem Beweissatz hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6106-163">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="d6106-164">Die ursprünglichen Dokumente im Live-Dienst werden nicht kommentiert.</span><span class="sxs-lookup"><span data-stu-id="d6106-164">The original documents in the live service aren't annotated.</span></span>
