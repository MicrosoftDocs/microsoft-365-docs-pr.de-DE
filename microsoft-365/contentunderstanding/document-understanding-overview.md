---
title: Übersicht über das Dokumentenverständnis
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Hier erhalten Sie einen Überblick über das Dokumentverständnis-Feature in Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683823"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="e2a42-103">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="e2a42-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="e2a42-104">Das Dokumentverständnis-Feature verwendet KI-Modelle (künstliche Intelligenz), um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="e2a42-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="e2a42-105">Es eignet sich am besten für unstrukturierte Dokumente, z. B. Briefe oder Verträge.</span><span class="sxs-lookup"><span data-stu-id="e2a42-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="e2a42-106">Diese Dokumente müssen Text enthalten, der anhand von Phrasen oder Mustern erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2a42-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="e2a42-107">Der erkannte Text bestimmt sowohl den Dateityp (seine Klassifizierung) als auch das, was extrahiert werden soll (die Extraktoren).</span><span class="sxs-lookup"><span data-stu-id="e2a42-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="e2a42-108">Weitere Informationen zu Beispielszenarien für das Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="e2a42-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="e2a42-109">Dokumentverständnismodelle werden auf einer Art von SharePoint-Site namens *Inhaltscenter* erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e2a42-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="e2a42-110">Ein auf eine SharePoint-Dokumentbibliothek angewendetes Modell ist mit einem Inhaltstyp verknüpft und enthält Spalten zum Speichern der extrahierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="e2a42-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="e2a42-111">Der von Ihnen erstellte Inhaltstyp wird im SharePoint-Inhaltstypkatalog gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e2a42-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="e2a42-112">Sie können auch vorhandene Inhaltstypen verwenden, um deren Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2a42-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="e2a42-113">Schreibgeschützte oder versiegelte Inhaltstypen können nicht aktualisiert und somit nicht in einem Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2a42-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="e2a42-114">Sie können Ihren Dokumentverständnismodellen *Klassifizierungen* und *Extraktoren* für folgende Zwecke hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e2a42-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="e2a42-115">Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="e2a42-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="e2a42-116">So kann beispielsweise eine Klassifizierung "trainiert" werden, alle *Vertragsverlängerungsdokumente* zu erkennen, die in die Bibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="e2a42-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="e2a42-117">Der Inhaltstyp der Vertragsverlängerung wird von Ihnen bei der Erstellung der Klassifizierung definiert.</span><span class="sxs-lookup"><span data-stu-id="e2a42-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="e2a42-118">Extraktoren rufen Informationen aus diesen Dokumenten ab.</span><span class="sxs-lookup"><span data-stu-id="e2a42-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="e2a42-119">Beispielsweise werden in Ihrer Ansicht für alle Vertragsverlängerungsdokumente, die in der Dokumentbibliothek erkannt wurden, Spalten angezeigt, die auch das *Dienst-Startdatum* und den *Kunden* für das jeweilige Vertragsverlängerungsdokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2a42-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="e2a42-120">Sie können Beispieldateien verwenden, um Ihre Klassifizierungen und Extraktoren im Modell zu trainieren und zu testen.</span><span class="sxs-lookup"><span data-stu-id="e2a42-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="e2a42-121">Beispieldateien liefern Ihrem Modell Beispiele für das, wonach gesucht werden soll, wenn nach zu extrahierenden Daten in Dateien gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="e2a42-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="e2a42-122">So würden Sie beispielsweise Ihre Klassifizierungen und Extraktoren für Vertragsverlängerungen mit Beispielen für Vertragsverlängerungsdokumente trainieren, die in Ihrem Unternehmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2a42-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="e2a42-123">Sie können Beispieldateien auch dazu verwenden, die Effektivität Ihres Modells zu testen.</span><span class="sxs-lookup"><span data-stu-id="e2a42-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="e2a42-124">Nach dessen Veröffentlichung können Sie das Modell über das Inhaltscenter auf eine beliebige SharePoint-Dokumentbibliothek anwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="e2a42-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="e2a42-125">Dateieinschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2a42-125">File limitations</span></span>

<span data-ttu-id="e2a42-126">Dokumentverständnismodelle nutzen die Technik der optischen Zeichenerkennung (OCR), um PDF-, Bild- und TIFF-Dateien zu scannen, und zwar sowohl beim Trainieren eines Modells mit Beispieldateien als auch beim Ausführen des Modells mit Dateien einer Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="e2a42-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="e2a42-127">Beachten Sie bitte die folgenden Unterschiede zwischen textbasierten Microsoft Office-Dateien und mit OCR gescannten Dateien (PDF, Bild oder TIFF):</span><span class="sxs-lookup"><span data-stu-id="e2a42-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="e2a42-128">Office-Dateien: Bei einer Länge von 64K Zeichen abgeschnitten (beim Training und beim Ausführen mit Dateien einer Dokumentbibliothek)</span><span class="sxs-lookup"><span data-stu-id="e2a42-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="e2a42-129">Mit OCR gescannte Dateien: Es besteht Limit von 20 Seiten.</span><span class="sxs-lookup"><span data-stu-id="e2a42-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="e2a42-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2a42-130">Requirements</span></span>

<span data-ttu-id="e2a42-131">Die OCR-Verarbeitung funktioniert am besten bei Dokumenten, die die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="e2a42-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="e2a42-132">JPG-, PNG- oder PDF-Format (Text oder Scan).</span><span class="sxs-lookup"><span data-stu-id="e2a42-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="e2a42-133">PDF-Dateien mit eingebettetem Text eignen sich besser, da bei Zeichenextraktion und -position keine Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="e2a42-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="e2a42-134">Wenn Ihre PDF-Dateien durch ein Kennwort gesperrt sind, müssen Sie die Sperre vor dem Senden entfernen.</span><span class="sxs-lookup"><span data-stu-id="e2a42-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="e2a42-135">Die kombinierte Dateigröße der für die Schulung verwendeten Dokumente pro Sammlung darf 50 MB nicht überschreiten, und PDF-Dokumente sollten nicht mehr als 500 Seiten haben.</span><span class="sxs-lookup"><span data-stu-id="e2a42-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="e2a42-136">Bei Bildern müssen Abmessungen zwischen 50 × 50 und 10.000 × 10.000 Pixel liegen.</span><span class="sxs-lookup"><span data-stu-id="e2a42-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e2a42-137">Bilder, die sehr breit sind oder seltsame Abmessungen haben (z. B. Grundrisse), werden im OCR-Prozess möglicherweise abgeschnitten und verlieren an Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="e2a42-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="e2a42-138">Bei PDF-Dateien dürfen die Abmessungen höchstens 17 x 17 Zoll betragen, was der Papiergröße „Legal“ oder A3 und kleiner entspricht.</span><span class="sxs-lookup"><span data-stu-id="e2a42-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="e2a42-139">Wenn von Papierdokumenten gescannt wird, sollte es sich bei den Scans um Bilder mit hoher Auflösung handeln.</span><span class="sxs-lookup"><span data-stu-id="e2a42-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="e2a42-140">Das lateinische Alphabet (englische Zeichen) müssen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2a42-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="e2a42-141">Der KI-Generator unterstützt derzeit die folgenden Arten von Eingabedaten für die Formularverarbeitung nicht:</span><span class="sxs-lookup"><span data-stu-id="e2a42-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="e2a42-142">– Kontrollkästchen oder Optionsfelder</span><span class="sxs-lookup"><span data-stu-id="e2a42-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="e2a42-143">– Signaturen</span><span class="sxs-lookup"><span data-stu-id="e2a42-143">- Signatures</span></span><br><span data-ttu-id="e2a42-144">– Ausfüllbare PDF-Dateien</span><span class="sxs-lookup"><span data-stu-id="e2a42-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="e2a42-145">Unterstützte Dateitypen</span><span class="sxs-lookup"><span data-stu-id="e2a42-145">Supported file types</span></span>

<span data-ttu-id="e2a42-146">Dokumentverständnismodelle unterstützen die folgenden Dateitypen:</span><span class="sxs-lookup"><span data-stu-id="e2a42-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="e2a42-147">DOC</span><span class="sxs-lookup"><span data-stu-id="e2a42-147">doc</span></span>
- <span data-ttu-id="e2a42-148">DOCX</span><span class="sxs-lookup"><span data-stu-id="e2a42-148">docx</span></span>
- <span data-ttu-id="e2a42-149">EML</span><span class="sxs-lookup"><span data-stu-id="e2a42-149">eml</span></span>
- <span data-ttu-id="e2a42-150">HEIC</span><span class="sxs-lookup"><span data-stu-id="e2a42-150">heic</span></span>
- <span data-ttu-id="e2a42-151">HEIF</span><span class="sxs-lookup"><span data-stu-id="e2a42-151">heif</span></span>
- <span data-ttu-id="e2a42-152">HTM</span><span class="sxs-lookup"><span data-stu-id="e2a42-152">htm</span></span>
- <span data-ttu-id="e2a42-153">HTML</span><span class="sxs-lookup"><span data-stu-id="e2a42-153">html</span></span>
- <span data-ttu-id="e2a42-154">JPEG</span><span class="sxs-lookup"><span data-stu-id="e2a42-154">jpeg</span></span>
- <span data-ttu-id="e2a42-155">JPG</span><span class="sxs-lookup"><span data-stu-id="e2a42-155">jpg</span></span>
- <span data-ttu-id="e2a42-156">MARKDOWN</span><span class="sxs-lookup"><span data-stu-id="e2a42-156">markdown</span></span>
- <span data-ttu-id="e2a42-157">MD</span><span class="sxs-lookup"><span data-stu-id="e2a42-157">md</span></span>
- <span data-ttu-id="e2a42-158">MSG</span><span class="sxs-lookup"><span data-stu-id="e2a42-158">msg</span></span>
- <span data-ttu-id="e2a42-159">PDF</span><span class="sxs-lookup"><span data-stu-id="e2a42-159">pdf</span></span>
- <span data-ttu-id="e2a42-160">PNG</span><span class="sxs-lookup"><span data-stu-id="e2a42-160">png</span></span>
- <span data-ttu-id="e2a42-161">PPT</span><span class="sxs-lookup"><span data-stu-id="e2a42-161">ppt</span></span>
- <span data-ttu-id="e2a42-162">PPTX</span><span class="sxs-lookup"><span data-stu-id="e2a42-162">pptx</span></span>
- <span data-ttu-id="e2a42-163">RTF</span><span class="sxs-lookup"><span data-stu-id="e2a42-163">rtf</span></span>
- <span data-ttu-id="e2a42-164">TIF</span><span class="sxs-lookup"><span data-stu-id="e2a42-164">tif</span></span>
- <span data-ttu-id="e2a42-165">TIFF</span><span class="sxs-lookup"><span data-stu-id="e2a42-165">tiff</span></span>
- <span data-ttu-id="e2a42-166">TXT</span><span class="sxs-lookup"><span data-stu-id="e2a42-166">txt</span></span>
- <span data-ttu-id="e2a42-167">XLS</span><span class="sxs-lookup"><span data-stu-id="e2a42-167">xls</span></span>
- <span data-ttu-id="e2a42-168">XLSX</span><span class="sxs-lookup"><span data-stu-id="e2a42-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="e2a42-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2a42-169">See Also</span></span>
[<span data-ttu-id="e2a42-170">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="e2a42-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e2a42-171">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="e2a42-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e2a42-172">Erstellen eines Inhaltscenters</span><span class="sxs-lookup"><span data-stu-id="e2a42-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="e2a42-173">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="e2a42-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="e2a42-174">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="e2a42-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="e2a42-175">Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen</span><span class="sxs-lookup"><span data-stu-id="e2a42-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="e2a42-176">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="e2a42-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="e2a42-177">Barrierefreiheitsmodus für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e2a42-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)