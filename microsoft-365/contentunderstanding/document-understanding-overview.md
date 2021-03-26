---
title: Übersicht über das Dokumentenverständnis
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Hier erhalten Sie einen Überblick über das Dokumentverständnis-Feature in Microsoft SharePoint Syntex.
ms.openlocfilehash: 73e217e458fb9e1ccad8b64ffc81a6c9522a04f4
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222755"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="b0297-103">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="b0297-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="b0297-104">Das Dokumentverständnis-Feature verwendet KI-Modelle (künstliche Intelligenz), um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="b0297-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="b0297-105">Es eignet sich am besten für unstrukturierte Dokumente, z. B. Briefe oder Verträge.</span><span class="sxs-lookup"><span data-stu-id="b0297-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="b0297-106">Diese Dokumente müssen Text enthalten, der anhand von Phrasen oder Mustern erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0297-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="b0297-107">Der erkannte Text bestimmt sowohl den Dateityp (seine Klassifizierung) als auch das, was extrahiert werden soll (die Extraktoren).</span><span class="sxs-lookup"><span data-stu-id="b0297-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="b0297-108">Weitere Informationen zu Beispielszenarien für das Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="b0297-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="b0297-109">Dokumentverständnismodelle werden auf einer Art von SharePoint-Site namens *Inhaltscenter* erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b0297-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="b0297-110">Ein auf eine SharePoint-Dokumentbibliothek angewendetes Modell ist mit einem Inhaltstyp verknüpft und enthält Spalten zum Speichern der extrahierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="b0297-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="b0297-111">Der von Ihnen erstellte Inhaltstyp wird im SharePoint-Inhaltstypkatalog gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b0297-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="b0297-112">Sie können auch vorhandene Inhaltstypen verwenden, um deren Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0297-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="b0297-113">Schreibgeschützte oder versiegelte Inhaltstypen können nicht aktualisiert und somit nicht in einem Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0297-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="b0297-114">Sie können Ihren Dokumentverständnismodellen *Klassifizierungen* und *Extraktoren* für folgende Zwecke hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b0297-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="b0297-115">Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b0297-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="b0297-116">So kann beispielsweise eine Klassifizierung "trainiert" werden, alle *Vertragsverlängerungsdokumente* zu erkennen, die in die Bibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b0297-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="b0297-117">Der Inhaltstyp der Vertragsverlängerung wird von Ihnen bei der Erstellung der Klassifizierung definiert.</span><span class="sxs-lookup"><span data-stu-id="b0297-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="b0297-118">Extraktoren rufen Informationen aus diesen Dokumenten ab.</span><span class="sxs-lookup"><span data-stu-id="b0297-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="b0297-119">Beispielsweise werden in Ihrer Ansicht für alle Vertragsverlängerungsdokumente, die in der Dokumentbibliothek erkannt wurden, Spalten angezeigt, die auch das *Dienst-Startdatum* und den *Kunden* für das jeweilige Vertragsverlängerungsdokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0297-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="b0297-120">Sie können Beispieldateien verwenden, um Ihre Klassifizierungen und Extraktoren im Modell zu trainieren und zu testen.</span><span class="sxs-lookup"><span data-stu-id="b0297-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="b0297-121">Beispieldateien liefern Ihrem Modell Beispiele für das, wonach gesucht werden soll, wenn nach zu extrahierenden Daten in Dateien gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="b0297-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="b0297-122">So würden Sie beispielsweise Ihre Klassifizierungen und Extraktoren für Vertragsverlängerungen mit Beispielen für Vertragsverlängerungsdokumente trainieren, die in Ihrem Unternehmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0297-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="b0297-123">Sie können Beispieldateien auch dazu verwenden, die Effektivität Ihres Modells zu testen.</span><span class="sxs-lookup"><span data-stu-id="b0297-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="b0297-124">Nach dessen Veröffentlichung können Sie das Modell über das Inhaltscenter auf eine beliebige SharePoint-Dokumentbibliothek anwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="b0297-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="b0297-125">Dateieinschränkungen</span><span class="sxs-lookup"><span data-stu-id="b0297-125">File limitations</span></span>

<span data-ttu-id="b0297-126">Dokumentverständnismodelle nutzen die Technik der optischen Zeichenerkennung (OCR), um PDF-, Bild- und TIFF-Dateien zu scannen, und zwar sowohl beim Trainieren eines Modells mit Beispieldateien als auch beim Ausführen des Modells mit Dateien einer Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b0297-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="b0297-127">Beachten Sie bitte die folgenden Unterschiede zwischen textbasierten Microsoft Office-Dateien und mit OCR gescannten Dateien (PDF, Bild oder TIFF):</span><span class="sxs-lookup"><span data-stu-id="b0297-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="b0297-128">Office-Dateien: Bei einer Länge von 64K Zeichen werden diese abgeschnitten (beim Training und beim Ausführen mit Dateien einer Dokumentbibliothek)</span><span class="sxs-lookup"><span data-stu-id="b0297-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="b0297-129">Mit OCR gescannte Dateien: Es besteht Limit von 20 Seiten.</span><span class="sxs-lookup"><span data-stu-id="b0297-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="b0297-130">Unterstützte Dateitypen</span><span class="sxs-lookup"><span data-stu-id="b0297-130">Supported file types</span></span>

<span data-ttu-id="b0297-131">Dokumentverständnismodelle unterstützen die folgenden Dateitypen:</span><span class="sxs-lookup"><span data-stu-id="b0297-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="b0297-132">DOC</span><span class="sxs-lookup"><span data-stu-id="b0297-132">doc</span></span>
- <span data-ttu-id="b0297-133">DOCX</span><span class="sxs-lookup"><span data-stu-id="b0297-133">docx</span></span>
- <span data-ttu-id="b0297-134">EML</span><span class="sxs-lookup"><span data-stu-id="b0297-134">eml</span></span>
- <span data-ttu-id="b0297-135">HEIC</span><span class="sxs-lookup"><span data-stu-id="b0297-135">heic</span></span>
- <span data-ttu-id="b0297-136">HEIF</span><span class="sxs-lookup"><span data-stu-id="b0297-136">heif</span></span>
- <span data-ttu-id="b0297-137">HTM</span><span class="sxs-lookup"><span data-stu-id="b0297-137">htm</span></span>
- <span data-ttu-id="b0297-138">HTML</span><span class="sxs-lookup"><span data-stu-id="b0297-138">html</span></span>
- <span data-ttu-id="b0297-139">JPEG</span><span class="sxs-lookup"><span data-stu-id="b0297-139">jpeg</span></span>
- <span data-ttu-id="b0297-140">JPG</span><span class="sxs-lookup"><span data-stu-id="b0297-140">jpg</span></span>
- <span data-ttu-id="b0297-141">MARKDOWN</span><span class="sxs-lookup"><span data-stu-id="b0297-141">markdown</span></span>
- <span data-ttu-id="b0297-142">MD</span><span class="sxs-lookup"><span data-stu-id="b0297-142">md</span></span>
- <span data-ttu-id="b0297-143">MSG</span><span class="sxs-lookup"><span data-stu-id="b0297-143">msg</span></span>
- <span data-ttu-id="b0297-144">PDF</span><span class="sxs-lookup"><span data-stu-id="b0297-144">pdf</span></span>
- <span data-ttu-id="b0297-145">PNG</span><span class="sxs-lookup"><span data-stu-id="b0297-145">png</span></span>
- <span data-ttu-id="b0297-146">PPT</span><span class="sxs-lookup"><span data-stu-id="b0297-146">ppt</span></span>
- <span data-ttu-id="b0297-147">PPTX</span><span class="sxs-lookup"><span data-stu-id="b0297-147">pptx</span></span>
- <span data-ttu-id="b0297-148">RTF</span><span class="sxs-lookup"><span data-stu-id="b0297-148">rtf</span></span>
- <span data-ttu-id="b0297-149">TIF</span><span class="sxs-lookup"><span data-stu-id="b0297-149">tif</span></span>
- <span data-ttu-id="b0297-150">TIFF</span><span class="sxs-lookup"><span data-stu-id="b0297-150">tiff</span></span>
- <span data-ttu-id="b0297-151">TXT</span><span class="sxs-lookup"><span data-stu-id="b0297-151">txt</span></span>
- <span data-ttu-id="b0297-152">XLS</span><span class="sxs-lookup"><span data-stu-id="b0297-152">xls</span></span>
- <span data-ttu-id="b0297-153">XLSX</span><span class="sxs-lookup"><span data-stu-id="b0297-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="b0297-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0297-154">See Also</span></span>
[<span data-ttu-id="b0297-155">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="b0297-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="b0297-156">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="b0297-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="b0297-157">Erstellen eines Inhaltscenters</span><span class="sxs-lookup"><span data-stu-id="b0297-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="b0297-158">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="b0297-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="b0297-159">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="b0297-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="b0297-160">Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen</span><span class="sxs-lookup"><span data-stu-id="b0297-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="b0297-161">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="b0297-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="b0297-162">Barrierefreiheitsmodus für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b0297-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)