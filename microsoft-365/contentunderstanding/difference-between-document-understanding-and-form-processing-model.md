---
title: Unterschied zwischen Dokument verstehen und Formular Verarbeitungs Modellen (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Beschreibt den wesentlichen Unterschied zwischen Dokument Verständnis und Formular Verarbeitungs Modellen.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537148"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="b5631-103">Unterschied zwischen Dokument verstehen und Formular Verarbeitungs Modellen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="b5631-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="b5631-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="b5631-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b5631-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b5631-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b5631-106">Mit dem Inhalts Verständnis in Project Cortex können Sie Dokumente, die in SharePoint-Dokumentbibliotheken hochgeladen werden, identifizieren und klassifizieren sowie relevante Informationen aus jeder Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b5631-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="b5631-107">Wenn beispielsweise Dateien in eine SharePoint-Dokumentbibliothek hochgeladen werden, werden alle Dateien, die als Bestel *Lungen* identifiziert werden, als solche klassifiziert und in einer benutzerdefinierten Dokumentbibliotheksansicht angezeigt, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5631-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="b5631-108">Darüber hinaus können Sie bestimmte Informationen aus jeder Datei abrufen (beispielsweise *Bestellnummer* und *Summe*) und in einer Spalte in ihrer Dokumentbibliotheksansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b5631-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="b5631-109">Mit dem Inhalts Verständnis können Sie *Modelle* erstellen, um die benötigten Informationen zu identifizieren und zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b5631-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="b5631-110">Es gibt zwei Arten von Modellen, die verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="b5631-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="b5631-111">Dokument verstehen von Modellen</span><span class="sxs-lookup"><span data-stu-id="b5631-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="b5631-112">Formular Verarbeitungsmodelle</span><span class="sxs-lookup"><span data-stu-id="b5631-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="b5631-113">Während beide Modelle für gewöhnlich denselben Zweck verwendet werden, gibt es wesentliche Unterschiede, die sich auf die zu verwendenden Optionen auswirken.</span><span class="sxs-lookup"><span data-stu-id="b5631-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="b5631-114">Strukturierter Vergleich von unstrukturierten und semi-strukturierten Inhalten</span><span class="sxs-lookup"><span data-stu-id="b5631-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="b5631-115">Verwenden Sie Dokument Verständnis Modelle zum Identifizieren und Extrahieren von Daten aus unstrukturierten Dokumenten wie Briefen oder Verträgen, bei denen sich die Text Entitäten, die Sie extrahieren möchten, in Sätzen oder bestimmten Dokumentbereichen befinden.</span><span class="sxs-lookup"><span data-stu-id="b5631-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="b5631-116">Beispielsweise kann ein unstrukturiertes Dokument ein Vertrags Erneuerungs schreiben sein, das auf unterschiedliche Weise geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5631-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="b5631-117">Es gibt jedoch Informationen, die sich konsistent im Textkörper jedes Vertrags Erneuerungs Dokuments befinden, beispielsweise die Textzeichenfolge "Startdatum des Diensts", gefolgt von einem tatsächlichen Datum.</span><span class="sxs-lookup"><span data-stu-id="b5631-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="b5631-118">Verwenden Sie Formular Verarbeitungsmodelle, um Dateien zu identifizieren und Daten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen oder Rechnungen zu extrahieren, wobei Sie eindeutige Schlüssel/Wert-Paare (beispielsweise *Date: 10/1/2020*) \* oder Tabellendaten haben.</span><span class="sxs-lookup"><span data-stu-id="b5631-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="b5631-119">Als Beispiel wäre ein guter Kandidat für die Formularverarbeitung das Bestellformular eines Unternehmens, in dem die Clients ihre Informationen für bestimmte Felder angeben müssen, die sich im gleichen Bereich des Dokumentlayouts befinden, wie *Name*, *Telefonnummer*, *Gesamtkosten*usw.  Ein Steuerformular ist ein gutes Beispiel für ein strukturiertes Dokument.</span><span class="sxs-lookup"><span data-stu-id="b5631-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="b5631-120">Wo Sie erstellt werden</span><span class="sxs-lookup"><span data-stu-id="b5631-120">Where they are created</span></span>

<span data-ttu-id="b5631-121">Dokument Understanding Models werden in einer SharePoint-inhaltscenter-Website erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b5631-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="b5631-122">Sie müssen Zugriff auf eine inhaltscenter-Website haben, um ein Dokument Verständnis Modell zu erstellen oder eine auf eine SharePoint-Dokumentbibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b5631-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="b5631-123">Wenn Sie ein Dokument grundlegendes Modell erstellen, erstellen Sie einen neuen [SharePoint-Inhaltstyp](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) , der im Katalog der SharePoint-Inhaltstypen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b5631-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="b5631-124">Sie können optional vorhandene Inhaltstypen verwenden, um Ihr Modell bei Bedarf zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b5631-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="b5631-125">Formular Verarbeitungsmodelle werden im PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview)erstellt, die Erstellung wird jedoch direkt aus einer SharePoint-Dokumentbibliothek initiiert.</span><span class="sxs-lookup"><span data-stu-id="b5631-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="b5631-126">Die Erstellung von Formular Verarbeitungs Modellen muss in Ihrer Dokumentbibliothek aktiviert sein, damit ein Benutzer ein Formular Verarbeitungsmodell für diese erstellen kann, und ein Administrator kann dies im Inhalt Understanding admin settings tun.</span><span class="sxs-lookup"><span data-stu-id="b5631-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="b5631-127">Formular Verarbeitungsmodelle verwenden PowerAutomate-Flows, um Dateien zu verarbeiten, wenn Sie in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b5631-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="b5631-128">Formular Verarbeitungsmodelle erstellen auch neue [SharePoint-Inhaltstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), die auch im SharePoint-Inhaltstypen Katalog gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b5631-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="b5631-129">Wo Sie angewendet werden können</span><span class="sxs-lookup"><span data-stu-id="b5631-129">Where they can be applied</span></span>

<span data-ttu-id="b5631-130">Dokument Verständnis Modelle können auf verschiedene SharePoint-Dokumentbibliotheken angewendet werden, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="b5631-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="b5631-131">Sie können das inhaltscenter verwenden, um nicht nur ein Dokument grundlegendes Modell zu erstellen, sondern es auch auf verschiedene Dokumentbibliotheken anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b5631-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="b5631-132">Das inhaltscenter bietet eine zentralere Kontrolle darüber, wie Dokument Verständnis Modelle verwendet werden und wo Sie angewendet werden, da diese Informationen in ein inhaltscenter aufrollen müssen.</span><span class="sxs-lookup"><span data-stu-id="b5631-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="b5631-133">Formular Verarbeitungsmodelle können derzeit nur auf die SharePoint-Dokumentbibliothek angewendet werden, aus der Sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b5631-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="b5631-134">Dadurch kann jeder lizenzierte Benutzer, der Zugriff auf die Website hat, ein Formular Verarbeitungsmodell erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5631-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="b5631-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5631-135">See Also</span></span>
[<span data-ttu-id="b5631-136">Schulung: verbessern der Geschäftsleistung mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="b5631-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="b5631-137">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="b5631-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="b5631-138">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="b5631-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="b5631-139">Anwenden eines Dokument Verständnisses für das Modell</span><span class="sxs-lookup"><span data-stu-id="b5631-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="b5631-140">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="b5631-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



