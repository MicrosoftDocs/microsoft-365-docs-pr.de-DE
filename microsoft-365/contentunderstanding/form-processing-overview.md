---
title: Übersicht über die Formularverarbeitung
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
description: Informationen zur Formularverarbeitung in Microsoft SharePoint Syntex
ms.openlocfilehash: 4a6ecc9e6eaca6f0b61f8c04b67eabb29674f6bd
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242446"
---
# <a name="form-processing-overview"></a><span data-ttu-id="cd749-103">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="cd749-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="cd749-105">Microsoft SharePoint Syntex verwendet die Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Formularverarbeitung, um Modelle in SharePoint-Dokumentbibliotheken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd749-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="cd749-106">Mithilfe der AI Builder-Formularverarbeitung können Sie KI-Modelle erstellen, die maschinelle Lerntechnologien nutzen, um Schlüsselwertpaare und Tabellendaten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen und Rechnungen zu identifizieren und extrahieren.</span><span class="sxs-lookup"><span data-stu-id="cd749-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="cd749-107">Unternehmen erhalten häufig viele Rechnungen aus einer Vielzahl von Quellen, z. B. per Post, Fax, E-Mail usw. Die Verarbeitung dieser Dokumente und die manuelle Eingabe der entsprechenden Daten in eine Datenbank können sehr viel Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="cd749-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="cd749-108">Die Formularverarbeitung automatisiert diesen Vorgang durch den Einsatz von künstlicher Intelligenz zum Extrahieren von Text, Schlüssel-/Wertpaaren und Tabellen aus Ihren Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="cd749-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="cd749-109">Weitere Informationen zu Beispielszenarien für die Formularverarbeitung finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="cd749-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="cd749-110">Sie können z. B. ein Formularverarbeitungsmodell erstellen, das alle Auftragsdokumente erkennt, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="cd749-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="cd749-111">Aus jedem Auftrag können dann bestimmte für Sie wichtige Daten extrahiert und angezeigt werden, z. B. *Auftragsnummer*, *Datum* oder *Gesamtbetrag*.</span><span class="sxs-lookup"><span data-stu-id="cd749-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Dokumentbibliotheksansicht](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="cd749-113">Um das Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen, werden Beispieldateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd749-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="cd749-114">Ihr Modell lernt durch das Trainieren den Aufbau Ihres Dokuments kennen.</span><span class="sxs-lookup"><span data-stu-id="cd749-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="cd749-115">Für den Anfang benötigen Sie nur fünf Formulare.</span><span class="sxs-lookup"><span data-stu-id="cd749-115">You only need five form documents to get started.</span></span> <span data-ttu-id="cd749-116">AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, darüber hinaus können Sie manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="cd749-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="cd749-117">Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="cd749-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="cd749-118">Nachdem Sie das Modell trainiert und veröffentlicht haben, erstellt das Modell einen [Power Automation-Ablauf](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="cd749-118">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="cd749-119">Der Ablauf wird ausgeführt, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird, und extrahiert Daten, die im Modell erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="cd749-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="cd749-120">Die extrahierten Daten werden in Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd749-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="cd749-121">Damit Benutzer ein [Formularverarbeitungsmodell erstellen](create-a-form-processing-model.md) können, muss ein Office 365-Administrator die [Formularverarbeitung für die SharePoint-Dokumentbibliothek aktivieren](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding).</span><span class="sxs-lookup"><span data-stu-id="cd749-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="cd749-122">Sie können die Websites während des Setups oder nach dem Setup in den Verwaltungseinstellungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="cd749-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="cd749-123">Dateieinschränkungen</span><span class="sxs-lookup"><span data-stu-id="cd749-123">File limitations</span></span>

<span data-ttu-id="cd749-124">Wenn Sie das Formular zur Verarbeitung von Modellen verwenden, stellen Sie sicher, dass die [Anforderungen und die Einschränkungen der Dateinutzung](https://docs.microsoft.com/ai-builder/form-processing-model-requirements) eingetragen sind.</span><span class="sxs-lookup"><span data-stu-id="cd749-124">When using form processing models, make sure to note the [requirements and limitations for file usage](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span>



## <a name="see-also"></a><span data-ttu-id="cd749-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd749-125">See Also</span></span>
  
[<span data-ttu-id="cd749-126">Power Automate-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="cd749-126">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="cd749-127">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="cd749-127">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="cd749-128">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="cd749-128">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="cd749-129">Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="cd749-129">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
