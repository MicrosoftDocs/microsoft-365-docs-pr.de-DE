---
title: Übersicht über das Dokumentenverständnis
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Hier erhalten Sie einen Überblick über das Dokumentverständnis-Feature in Microsoft SharePoint Syntex.
ms.openlocfilehash: 5dd44a119dff6f5d194861c381fa28f76a6f0da7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701107"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="f539b-103">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="f539b-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="f539b-104">Das Dokumentverständnis-Feature verwendet KI-Modelle (künstliche Intelligenz), um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="f539b-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="f539b-105">Es eignet sich am besten für unstrukturierte Dokumente, z. B. Briefe oder Verträge.</span><span class="sxs-lookup"><span data-stu-id="f539b-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="f539b-106">Diese Dokumente müssen Text enthalten, der anhand von Phrasen oder Mustern erkannt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f539b-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="f539b-107">Der erkannte Text bestimmt sowohl den Dateityp (seine Klassifizierung) als auch das, was extrahiert werden soll (die Extraktoren).</span><span class="sxs-lookup"><span data-stu-id="f539b-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="f539b-108">Weitere Informationen zu Beispielszenarien für das Dokumentverständnis finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="f539b-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="f539b-109">Dokumentverständnismodelle werden auf einer Art von SharePoint-Site namens *Inhaltscenter* erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f539b-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="f539b-110">Ein auf eine SharePoint-Dokumentbibliothek angewendetes Modell ist mit einem Inhaltstyp verknüpft und enthält Spalten zum Speichern der extrahierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="f539b-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="f539b-111">Der von Ihnen erstellte Inhaltstyp wird im SharePoint-Inhaltstypkatalog gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f539b-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="f539b-112">Sie können auch vorhandene Inhaltstypen verwenden, um deren Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f539b-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="f539b-113">Schreibgeschützte oder versiegelte Inhaltstypen können nicht aktualisiert und somit nicht in einem Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f539b-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="f539b-114">Sie können Ihren Dokumentverständnismodellen *Klassifizierungen* und *Extraktoren* für folgende Zwecke hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f539b-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="f539b-115">Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f539b-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="f539b-116">So kann beispielsweise eine Klassifizierung "trainiert" werden, alle *Vertragsverlängerungsdokumente* zu erkennen, die in die Bibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f539b-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="f539b-117">Der Inhaltstyp der Vertragsverlängerung wird von Ihnen bei der Erstellung der Klassifizierung definiert.</span><span class="sxs-lookup"><span data-stu-id="f539b-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="f539b-118">Extraktoren rufen Informationen aus diesen Dokumenten ab.</span><span class="sxs-lookup"><span data-stu-id="f539b-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="f539b-119">Beispielsweise werden in Ihrer Ansicht für alle Vertragsverlängerungsdokumente, die in der Dokumentbibliothek erkannt wurden, Spalten angezeigt, die auch das *Dienst-Startdatum* und den *Kunden* für das jeweilige Vertragsverlängerungsdokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="f539b-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="f539b-120">Sie können Beispieldateien verwenden, um Ihre Klassifizierungen und Extraktoren im Modell zu trainieren und zu testen.</span><span class="sxs-lookup"><span data-stu-id="f539b-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="f539b-121">Beispieldateien liefern Ihrem Modell Beispiele für das, wonach gesucht werden soll, wenn nach zu extrahierenden Daten in Dateien gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="f539b-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="f539b-122">So würden Sie beispielsweise Ihre Klassifizierungen und Extraktoren für Vertragsverlängerungen mit Beispielen für Vertragsverlängerungsdokumente trainieren, die in Ihrem Unternehmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f539b-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="f539b-123">Sie können Beispieldateien auch dazu verwenden, die Effektivität Ihres Modells zu testen.</span><span class="sxs-lookup"><span data-stu-id="f539b-123">You can also use example files to test the effectiveness of your model.</span></span>

> [!NOTE]
> <span data-ttu-id="f539b-124">Wenn Sie OCR-Technologie (Optical Character Recognition) zum Scannen von Dokumenten verwenden, ist Syntex für das Modelltraining auf ein Limit von 15 Seiten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f539b-124">If you use optical character recognition (OCR) technology to scan documents, Syntex has a 15-page limit for model training.</span></span>

<span data-ttu-id="f539b-125">Nach dessen Veröffentlichung können Sie das Modell über das Inhaltscenter auf eine beliebige SharePoint-Dokumentbibliothek anwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="f539b-125">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f539b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f539b-126">See Also</span></span>
[<span data-ttu-id="f539b-127">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f539b-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="f539b-128">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="f539b-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f539b-129">Erstellen eines Inhaltscenters</span><span class="sxs-lookup"><span data-stu-id="f539b-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="f539b-130">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="f539b-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="f539b-131">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="f539b-131">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="f539b-132">Unterschied zwischen Dokumentverständnis- und Formularverarbeitungsmodellen</span><span class="sxs-lookup"><span data-stu-id="f539b-132">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="f539b-133">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="f539b-133">Form processing overview</span></span>](form-processing-overview.md)
