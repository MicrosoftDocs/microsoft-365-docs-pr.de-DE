---
title: Übersicht über die Formularverarbeitung
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Informationen zur Formularverarbeitung in Microsoft SharePoint Syntex
ms.openlocfilehash: 6c2cb2ee3c1fc621e7814f4603ad2e6f0b891701
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087403"
---
# <a name="form-processing-overview"></a><span data-ttu-id="8a365-103">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="8a365-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="8a365-105">Microsoft SharePoint Syntex verwendet die Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Formularverarbeitung, um Modelle in SharePoint-Dokumentbibliotheken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a365-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="8a365-106">Mithilfe der AI Builder-Formularverarbeitung können Sie KI-Modelle erstellen, die maschinelle Lerntechnologien nutzen, um Schlüsselwertpaare und Tabellendaten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen und Rechnungen zu identifizieren und extrahieren.</span><span class="sxs-lookup"><span data-stu-id="8a365-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="8a365-107">Unternehmen erhalten häufig viele Rechnungen aus einer Vielzahl von Quellen, z. B. per Post, Fax, E-Mail usw. Die Verarbeitung dieser Dokumente und die manuelle Eingabe der entsprechenden Daten in eine Datenbank können sehr viel Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="8a365-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="8a365-108">Die Formularverarbeitung automatisiert diesen Vorgang durch den Einsatz von künstlicher Intelligenz zum Extrahieren von Text, Schlüssel-/Wertpaaren und Tabellen aus Ihren Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="8a365-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a365-109">Weitere Informationen zu Beispielszenarien für die Formularverarbeitung finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="8a365-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="8a365-110">Sie können z. B. ein Formularverarbeitungsmodell erstellen, das alle Auftragsdokumente erkennt, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="8a365-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="8a365-111">Aus jedem Auftrag können dann bestimmte für Sie wichtige Daten extrahiert und angezeigt werden, z. B. *Auftragsnummer*, *Datum* oder *Gesamtbetrag*.</span><span class="sxs-lookup"><span data-stu-id="8a365-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Dokumentbibliotheksansicht](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="8a365-113">Um das Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen, werden Beispieldateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a365-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="8a365-114">Ihr Modell lernt durch das Trainieren den Aufbau Ihres Dokuments kennen.</span><span class="sxs-lookup"><span data-stu-id="8a365-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="8a365-115">Für den Anfang benötigen Sie nur fünf Formulare.</span><span class="sxs-lookup"><span data-stu-id="8a365-115">You only need five form documents to get started.</span></span> <span data-ttu-id="8a365-116">AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, darüber hinaus können Sie manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="8a365-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="8a365-117">Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="8a365-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="8a365-118">Für den Anfang benötigen Sie mindestens fünf Formulare.</span><span class="sxs-lookup"><span data-stu-id="8a365-118">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="8a365-119">AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, und Sie können dann manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="8a365-119">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="8a365-120">Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="8a365-120">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="8a365-121">Nachdem Sie das Modell trainiert und veröffentlicht haben, erstellt das Modell einen [Power Automation-Ablauf](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="8a365-121">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="8a365-122">Der Ablauf wird ausgeführt, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird, und extrahiert Daten, die im Modell erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="8a365-122">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="8a365-123">Die extrahierten Daten werden in Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a365-123">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="8a365-124">Damit Benutzer ein [Formularverarbeitungsmodell erstellen](create-a-form-processing-model.md) können, muss ein Office 365-Administrator die [Formularverarbeitung für die SharePoint-Dokumentbibliothek aktivieren](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding).</span><span class="sxs-lookup"><span data-stu-id="8a365-124">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="8a365-125">Sie können die Websites während des Setups oder nach dem Setup in den Verwaltungseinstellungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="8a365-125">You can select the sites during setup, or after setup in your management settings.</span></span>



## <a name="see-also"></a><span data-ttu-id="8a365-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a365-126">See Also</span></span>
  
[<span data-ttu-id="8a365-127">Power Automate-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="8a365-127">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="8a365-128">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="8a365-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="8a365-129">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="8a365-129">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="8a365-130">Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="8a365-130">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
