---
title: Dokument Verständnis Übersicht
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erhalten Sie einen Überblick über das Dokument Verständnis in Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294760"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="d6dbc-103">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="d6dbc-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="d6dbc-104">Document Understanding verwendet künstliche Intelligenz Modelle (AI), um die Klassifizierung von Dateien und die Extraktion von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="d6dbc-105">Es funktioniert am besten mit unstrukturierten Dokumenten wie Briefen oder Verträgen.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="d6dbc-106">Diese Dokumente müssen Text enthalten, der auf der Grundlage von Ausdrücken oder Mustern identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="d6dbc-107">Der identifizierte Text bestimmt sowohl den Typ der Datei (seine Klassifizierung) als auch die Inhalte, die extrahiert werden sollen (Extraktionsprogramme).</span><span class="sxs-lookup"><span data-stu-id="d6dbc-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="d6dbc-108">Dokument Understanding Models werden in einer SharePoint-Website mit dem Namen " *inhaltscenter*" erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="d6dbc-109">Bei Anwendung auf eine SharePoint-Dokumentbibliothek wird das Modell einem Inhaltstyp zugeordnet hat Spalten zum Speichern der extrahierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="d6dbc-110">Der Inhaltstyp, den Sie erstellen, wird im Inhaltstypen Katalog von SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="d6dbc-111">Sie können auch die Verwendung vorhandener Inhaltstypen für die Verwendung Ihres Schemas auswählen.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="d6dbc-112">Hinzufügen von *Klassifizierungen* und *Extraktionen* zu Ihrem Dokument Understanding Models to do the folgenden:</span><span class="sxs-lookup"><span data-stu-id="d6dbc-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="d6dbc-113">Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="d6dbc-114">Beispielsweise kann eine Klassifizierung "geschult" werden, um alle *Vertrags Erneuerungs* Dokumente zu identifizieren, die in die Bibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="d6dbc-115">Der Inhaltstyp "Vertragserneuerung" wird von Ihnen beim Erstellen ihrer Klassifizierung definiert.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="d6dbc-116">Extraktions Module ziehen Informationen aus diesen Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="d6dbc-117">Beispielsweise werden für alle in Ihrer Dokumentbibliothek identifizierten Vertrags Erneuerungs Dokumente in der Ansicht Spalten angezeigt, die auch den *Start Termin* und den  *Client* des Diensts für jedes Vertrags Erneuerungs Dokument anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="d6dbc-118">Mithilfe von Beispieldateien können Sie Ihre Klassifizierungen und Extraktoren in Ihrem Modell trainieren und testen.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="d6dbc-119">Beispieldateien bieten ihre Modellbeispiele, wonach Sie suchen müssen, wenn Sie versuchen, Daten aus Dateien zu identifizieren und daraus zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="d6dbc-120">Sie möchten beispielsweise Ihre Klassifizierungen und Extraktionsprogramme für die Vertragserneuerung mit Beispielen von Vertrags Erneuerungs Dokumenten trainieren, mit denen Ihr Unternehmen zusammenarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="d6dbc-121">Sie können auch Beispieldateien verwenden, um die Effektivität Ihres Modells zu testen.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="d6dbc-122">Verwenden Sie nach der Veröffentlichung Ihres Modells das inhaltscenter, um es auf eine beliebige SharePoint-Dokumentbibliothek anzuwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="d6dbc-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6dbc-123">See Also</span></span>
[<span data-ttu-id="d6dbc-124">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="d6dbc-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="d6dbc-125">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="d6dbc-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="d6dbc-126">[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="d6dbc-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="d6dbc-127">[Anwenden eines Modells](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="d6dbc-128">Unterschied zwischen einem Dokument Verständnis und einem Formular Verarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="d6dbc-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="d6dbc-129">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="d6dbc-129">Form processing overview</span></span>](form-processing-overview.md)
