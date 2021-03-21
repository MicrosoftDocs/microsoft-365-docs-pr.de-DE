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
ms.openlocfilehash: 84aeb7c4e3fc850e5e4c2336e576ff3bce3ecf4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928308"
---
# <a name="form-processing-overview"></a><span data-ttu-id="eec8c-103">Übersicht über die Formularverarbeitung</span><span class="sxs-lookup"><span data-stu-id="eec8c-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="eec8c-105">Microsoft SharePoint Syntex verwendet die Microsoft PowerApps [AI Builder](/ai-builder/overview) -Formularverarbeitung, um Modelle in SharePoint-Dokumentbibliotheken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eec8c-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="eec8c-106">Mithilfe der AI Builder-Formularverarbeitung können Sie KI-Modelle erstellen, die maschinelle Lerntechnologien nutzen, um Schlüsselwertpaare und Tabellendaten aus strukturierten oder teilstrukturierten Dokumenten wie Formularen und Rechnungen zu identifizieren und extrahieren.</span><span class="sxs-lookup"><span data-stu-id="eec8c-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="eec8c-107">Unternehmen erhalten häufig viele Rechnungen aus einer Vielzahl von Quellen, z. B. per Post, Fax, E-Mail usw. Die Verarbeitung dieser Dokumente und die manuelle Eingabe der entsprechenden Daten in eine Datenbank können sehr viel Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="eec8c-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="eec8c-108">Die Formularverarbeitung automatisiert diesen Vorgang durch den Einsatz von künstlicher Intelligenz zum Extrahieren von Text, Schlüssel-/Wertpaaren und Tabellen aus Ihren Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="eec8c-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="eec8c-109">Weitere Informationen zu Beispielszenarien für die Formularverarbeitung finden Sie unter [SharePoint Syntex – Leitfaden für die ersten Schritte](./adoption-getstarted.md#form-processing-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="eec8c-109">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="eec8c-110">Sie können z. B. ein Formularverarbeitungsmodell erstellen, das alle Auftragsdokumente erkennt, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="eec8c-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="eec8c-111">Aus jedem Auftrag können dann bestimmte für Sie wichtige Daten extrahiert und angezeigt werden, z. B. *Auftragsnummer*, *Datum* oder *Gesamtbetrag*.</span><span class="sxs-lookup"><span data-stu-id="eec8c-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Dokumentbibliotheksansicht](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="eec8c-113">Um das Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen, werden Beispieldateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="eec8c-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="eec8c-114">Ihr Modell lernt durch das Trainieren den Aufbau Ihres Dokuments kennen.</span><span class="sxs-lookup"><span data-stu-id="eec8c-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="eec8c-115">Für den Anfang benötigen Sie nur fünf Formulare.</span><span class="sxs-lookup"><span data-stu-id="eec8c-115">You only need five form documents to get started.</span></span> <span data-ttu-id="eec8c-116">AI Builder analysiert Ihre Beispieldateien auf Schlüssel-/Wertpaare, darüber hinaus können Sie manuell diejenigen ermitteln, die evtl. nicht erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="eec8c-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="eec8c-117">Im AI Builder können Sie die Genauigkeit Ihres Modells anhand Ihrer Beispieldateien testen.</span><span class="sxs-lookup"><span data-stu-id="eec8c-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="eec8c-118">Nachdem Sie das Modell trainiert und veröffentlicht haben, erstellt das Modell einen [Power Automation-Ablauf](/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="eec8c-118">After you train and publish your model, your model creates a [Power Automate Flow](/power-automate/getting-started).</span></span> <span data-ttu-id="eec8c-119">Der Ablauf wird ausgeführt, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird, und extrahiert Daten, die im Modell erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="eec8c-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="eec8c-120">Die extrahierten Daten werden in Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eec8c-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="eec8c-121">Damit Benutzer ein [Formularverarbeitungsmodell erstellen](create-a-form-processing-model.md) können, muss ein Office 365-Administrator die [Formularverarbeitung für die SharePoint-Dokumentbibliothek aktivieren](./set-up-content-understanding.md#to-set-up-content-understanding).</span><span class="sxs-lookup"><span data-stu-id="eec8c-121">An Office 365 admin needs to [enable Form processing](./set-up-content-understanding.md#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="eec8c-122">Sie können die Websites während des Setups oder nach dem Setup in den Verwaltungseinstellungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="eec8c-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="eec8c-123">Dateieinschränkungen</span><span class="sxs-lookup"><span data-stu-id="eec8c-123">File limitations</span></span>

<span data-ttu-id="eec8c-124">Wenn Sie das Formular zur Verarbeitung von Modellen verwenden, stellen Sie sicher, dass die [Anforderungen und die Einschränkungen der Dateinutzung](/ai-builder/form-processing-model-requirements) eingetragen sind.</span><span class="sxs-lookup"><span data-stu-id="eec8c-124">When using form processing models, make sure to note the [requirements and limitations for file usage](/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="eec8c-125">Multi-Geo-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="eec8c-125">Multi-Geo environments</span></span>

<span data-ttu-id="eec8c-126">Wenn sie SharePoint Syntex in einer [Microsoft 365 Multi-Geo-Umgebung](../enterprise/microsoft-365-multi-geo.md) aufsetzen, dann können Sie es nur für die Verwendung der Formularverarbeitung am zentralen Speicherort konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eec8c-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="eec8c-127">Wenn Sie die Formularverarbeitung in einem Satellitenstandort verwenden wollen, kontaktieren Sie den Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="eec8c-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="eec8c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eec8c-128">See Also</span></span>
  
[<span data-ttu-id="eec8c-129">Power Automate-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="eec8c-129">Power Automate documentation</span></span>](/power-automate/)

[<span data-ttu-id="eec8c-130">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="eec8c-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="eec8c-131">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="eec8c-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="eec8c-132">Schulungen: Verbessern der Geschäftsergebnisse mit AI Builder</span><span class="sxs-lookup"><span data-stu-id="eec8c-132">Training: Improve business performance with AI Builder</span></span>](/learn/paths/improve-business-performance-ai-builder/?source=learn)