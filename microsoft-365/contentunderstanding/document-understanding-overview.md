---
title: Dokument Verständnis Übersicht (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erhalten Sie einen Überblick über das Dokument Verständnis in Project Cortex.
ms.openlocfilehash: bdebc8a8726a7b9a77eb9a1095f83e937cf36cb1
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612714"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="c7e86-103">Dokument Verständnis Übersicht (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="c7e86-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="c7e86-104">Project Cortex befindet sich derzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="c7e86-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="c7e86-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c7e86-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="c7e86-106">Document Understanding verwendet AI-Modelle, um die Klassifizierung von Dateien und das Extrahieren von Informationen zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c7e86-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="c7e86-107">Es funktioniert am besten mit unstrukturierten Dokumenten wie Buchstaben oder Verträgen.</span><span class="sxs-lookup"><span data-stu-id="c7e86-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="c7e86-108">Die Dokumente sollten Text enthalten, der anhand von Ausdrücken oder Mustern identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7e86-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="c7e86-109">Der identifizierte Text kann sowohl den Typ der Datei (seine Klassifizierung) als auch die Inhalte bestimmen, die extrahiert werden sollen (Extraktoren).</span><span class="sxs-lookup"><span data-stu-id="c7e86-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="c7e86-110">Dokument Understanding Models werden in einer SharePoint-Website mit dem Namen "inhaltscenter" erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c7e86-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="c7e86-111">Bei Anwendung auf eine SharePoint-Dokumentbibliothek wird das Modell einem Inhaltstyp zugeordnet, der Spalten zum Speichern der extrahierten Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="c7e86-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="c7e86-112">Der Inhaltstyp, den Sie erstellen, wird im Inhaltstypen Katalog von SharePoint gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7e86-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="c7e86-113">Sie können auch vorhandene Inhaltstypen verwenden, um Ihr Schema zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7e86-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="c7e86-114">Sie können Ihrem Dokument *Klassifizierungen* und *Extraktions* Module hinzufügen, die die folgenden Schritte verstehen:</span><span class="sxs-lookup"><span data-stu-id="c7e86-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="c7e86-115">Klassifizierungen werden verwendet, um Dokumente zu identifizieren und zu klassifizieren, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="c7e86-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="c7e86-116">Beispielsweise kann eine Klassifizierung "geschult" werden, um alle *Vertrags Erneuerungs* Dokumente zu identifizieren, die in die Bibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="c7e86-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="c7e86-117">Der Inhaltstyp "Vertragserneuerung" wird von Ihnen beim Erstellen ihrer Klassifizierung definiert.</span><span class="sxs-lookup"><span data-stu-id="c7e86-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="c7e86-118">Extraktions Module ziehen Informationen aus diesen Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="c7e86-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="c7e86-119">Beispielsweise werden für alle Vertrags Erneuerungs Dokumente, die in Ihrer Dokumentbibliothek identifiziert werden, in ihrer Ansicht Spalten angezeigt, in denen auch das *Start Datum* und der *Client* des Diensts für jedes Vertrags Erneuerungs Dokument angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7e86-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="c7e86-120">Sie verwenden Beispieldateien, um Ihre Klassifizierungen und Extraktoren in Ihrem Modell zu trainieren und zu testen.</span><span class="sxs-lookup"><span data-stu-id="c7e86-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="c7e86-121">Beispieldateien bieten ihre Modellbeispiele, wonach Sie suchen müssen, wenn Sie versuchen, Daten aus Dateien zu identifizieren und daraus zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="c7e86-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="c7e86-122">Sie möchten beispielsweise Ihre Klassifizierungen und Extraktoren für die Vertragserneuerung mit Beispielen von Vertrags Erneuerungs Dokumenten trainieren, mit denen Ihr Unternehmen zusammenarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c7e86-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="c7e86-123">Sie können auch Beispieldateien verwenden, um die Effektivität Ihres Modells zu testen.</span><span class="sxs-lookup"><span data-stu-id="c7e86-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="c7e86-124">Verwenden Sie nach der Veröffentlichung Ihres Modells das inhaltscenter, um es auf eine beliebige SharePoint-Dokumentbibliothek anzuwenden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="c7e86-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="c7e86-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e86-125">See Also</span></span>
[<span data-ttu-id="c7e86-126">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="c7e86-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="c7e86-127">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="c7e86-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="c7e86-128">[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="c7e86-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="c7e86-129">[Anwenden eines Modells](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="c7e86-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="c7e86-130">Unterschied zwischen einem Dokument Verständnis und einem Formular Verarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="c7e86-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="c7e86-131">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="c7e86-131">Form processing overview</span></span>](form-processing-overview.md)




