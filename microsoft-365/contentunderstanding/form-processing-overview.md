---
title: Übersicht über die Formularverarbeitung (Vorschau)
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
description: Erfahren Sie mehr über die Formularverarbeitung in Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540058"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="d12f4-103">Übersicht über die Formularverarbeitung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d12f4-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="d12f4-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="d12f4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d12f4-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d12f4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d12f4-106">Project Cortex verwendet Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Formularverarbeitung zum Erstellen von Modellen in SharePoint-Dokumentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="d12f4-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="d12f4-107">Sie können die AI Builder-Formularverarbeitung zum Erstellen von AI-Modellen verwenden, die maschinelle Lerntechnologie zum Identifizieren und Extrahieren von Schlüssel/Wert-Paaren und Tabellendaten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen und Rechnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d12f4-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="d12f4-108">Unternehmen erhalten häufig Rechnungen in großen Mengen und aus einer Vielzahl von Quellen wie e-Mail, Fax, e-Mail oder persönlich.</span><span class="sxs-lookup"><span data-stu-id="d12f4-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="d12f4-109">Die Verarbeitung dieser Dokumente und die manuelle Eingabe in Ihre Datenbank kann sehr viel Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d12f4-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="d12f4-110">Durch die Verwendung von AI zum Extrahieren von Text, Schlüssel/Wert-Paaren und Tabellen aus Ihren Dokumenten wird dieser Prozess von der Formularverarbeitung automatisiert.</span><span class="sxs-lookup"><span data-stu-id="d12f4-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="d12f4-111">Sie können beispielsweise ein Formular Verarbeitungsmodell erstellen, mit dem alle Bestelldokumente identifiziert werden, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d12f4-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="d12f4-112">Und aus jeder Bestellung können Sie bestimmte Daten extrahieren und anzeigen, die für Sie wichtig sind, beispielsweise *Bestellnummer*, *Datum*oder *Gesamtkosten*.</span><span class="sxs-lookup"><span data-stu-id="d12f4-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="d12f4-113">Sie verwenden Beispieldateien, um Ihr Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d12f4-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="d12f4-114">Das Layout Ihres Dokuments wird durch Schulung Ihres Modells erlernt.</span><span class="sxs-lookup"><span data-stu-id="d12f4-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="d12f4-115">Für die ersten Schritte benötigen Sie nur fünf Formular Dokumente.</span><span class="sxs-lookup"><span data-stu-id="d12f4-115">You only need five form documents to get started.</span></span> <span data-ttu-id="d12f4-116">Im AI-Gebäude werden Ihre Beispieldateien für Schlüssel-Wert-Paare analysiert, und Sie können auch manuell erkennen, welche möglicherweise nicht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="d12f4-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="d12f4-117">Mit AI Builder können Sie die Genauigkeit Ihres Modells in ihren Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="d12f4-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="d12f4-118">Nachdem Sie Ihr Modell trainiert und veröffentlicht haben, erstellen Sie einen Power- [Automatisierungs Fluss](https://docs.microsoft.com/power-automate/getting-started) , der ausgeführt wird, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird und Daten extrahiert, die im Modell identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="d12f4-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="d12f4-119">Die extrahierten Daten werden in den Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d12f4-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="d12f4-120">Ein Office 365 Administrator muss die [Formularverarbeitung](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) für die SharePoint-Dokumentbibliothek aktivieren, damit Benutzer [ein Formular Verarbeitungsmodell](create-a-form-processing-model.md) in dieser erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d12f4-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="d12f4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d12f4-121">See Also</span></span>
  
[<span data-ttu-id="d12f4-122">Power Automation-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d12f4-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="d12f4-123">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="d12f4-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="d12f4-124">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="d12f4-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="d12f4-125">Schulung: verbessern der Geschäftsleistung mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="d12f4-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




