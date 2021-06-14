---
title: SharePoint Syntex-Dokumentverständnismodell-REST-API
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Überblick über die SharePoint Syntex-Dokumentverständnismodell-REST-API.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908089"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="a47af-103">SharePoint Syntex-Dokumentverständnismodell-REST-API</span><span class="sxs-lookup"><span data-stu-id="a47af-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="a47af-104">Sie können die SharePoint-REST-Schnittstelle verwenden, um eine Dokumentverständnismodell zu erstellen, das Modell auf eine oder mehrere Bibliotheken anzuwenden oder es von diesen zu entfernen, und um Informationen über das Modell zu erhalten oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a47af-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="a47af-105">Der REST-Dienst in SharePoint Online (sowie in lokalen Bereitstellungen von SharePoint 2016 und höher) erlaubt die Zusammenfassung mehrerer Anforderungen in einem einzigen Aufruf an den Service mittels der ODATA-Abfrageoption „$batch“.</span><span class="sxs-lookup"><span data-stu-id="a47af-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="a47af-106">Einzelheiten und Links zu Codebeispielen finden Sie unter [Durchführen von Batchanforderungen mit den REST-APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="a47af-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a47af-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a47af-107">Prerequisites</span></span>

<span data-ttu-id="a47af-108">Lesen Sie vor der Umsetzung der Beispiele in diesem Artikel zunächst die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="a47af-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="a47af-109">Grundlegendes zum SharePoint-REST-Dienst</span><span class="sxs-lookup"><span data-stu-id="a47af-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [<span data-ttu-id="a47af-110">Ausführen grundlegender Vorgänge unter Verwendung von SharePoint-REST-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="a47af-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a><span data-ttu-id="a47af-111">REST-Befehle</span><span class="sxs-lookup"><span data-stu-id="a47af-111">REST commands</span></span>

<span data-ttu-id="a47af-112">Die folgenden REST-Befehle stehen für die Arbeit mit Syntex-Dokumentverständnismodellen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a47af-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="a47af-113">[Modell erstellen](rest-createmodel-method.md) – Erstellt ein Modell und den zugehörigen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="a47af-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="a47af-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Ruft Informationen zu einem SharePoint Syntex-Dokumentverständnismodell ab oder aktualisiert diese.</span><span class="sxs-lookup"><span data-stu-id="a47af-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="a47af-115">[GetByTitle](rest-getbytitle-method.md) – Ruft Informationen zu einem SharePoint Syntex-Dokumentverständnismodell mittels dem Modelltitel ab oder aktualisiert diese.</span><span class="sxs-lookup"><span data-stu-id="a47af-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="a47af-116">[Modell anwenden](rest-applymodel-method.md) – Wendet ein trainiertes Dokumentverständnismodell auf eine oder mehrere Bibliotheken an (oder synchronisiert es).</span><span class="sxs-lookup"><span data-stu-id="a47af-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="a47af-117">[Modell- und Bibliotheksinformationen abrufen](rest-getmodelandlibraryinfo.md) – Ruft Informationen ab über das Modell und die Bibliothek, auf die es angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a47af-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="a47af-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Aktualisiert verfügbare Modelleinstellungen (zugehörige Aufbewahrungsbezeichnung und Modellbeschreibung) für eine SharePoint Syntex-Dokumentverständnismodell.</span><span class="sxs-lookup"><span data-stu-id="a47af-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="a47af-119">[BatchDelete](rest-batchdelete-method.md) – Entfernt ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a47af-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="a47af-120">[Erstellen einer Klassifizierungsanforderung](rest-createclassificationrequest.md) – Erstellt eine Anforderung zur Klassifizierung einer bestimmten Datei oder bestimmter Dateien mittels dem angewendeten Modell.</span><span class="sxs-lookup"><span data-stu-id="a47af-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="a47af-121">Szenarien</span><span class="sxs-lookup"><span data-stu-id="a47af-121">Scenarios</span></span>

<span data-ttu-id="a47af-122">Beachten Sie die folgenden Szenario-Beispiele, die sich nicht intuitiv aus dem Methodennamen ergeben.</span><span class="sxs-lookup"><span data-stu-id="a47af-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="a47af-123">Weitere Informationen finden Sie im jeweiligen Artikel.</span><span class="sxs-lookup"><span data-stu-id="a47af-123">For more information, see each article.</span></span>

<span data-ttu-id="a47af-124">Die Methode „Modell erstellen“ erstellt nur das Modellobjekt und den zugehörigen Inhaltstyp.</span><span class="sxs-lookup"><span data-stu-id="a47af-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="a47af-125">Sie müssen das Modell zuerst im Inhaltscenter trainieren, bevor es auf eine Bibliothek angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a47af-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="a47af-126">Die Methode „Modell anwenden“ wird verwendet, um das Modell auf der Zielbibliothek zu konfigurieren, um Dokumente zu klassifizieren und optional zusätzliche Informationen zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="a47af-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="a47af-127">Diese API unterstützt auch die Batch-Anwendung des Modells auf mehrere Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="a47af-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="a47af-128">Die Methode „Modell entfernen“ entfernt das Modell nur von einer oder mehreren Bibliotheken, auf die es zuvor angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a47af-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="a47af-129">Wenn Sie das Modell löschen wollen, müssen Sie es zuerst aus allen Bibliotheken entfernen, auf die es angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a47af-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="a47af-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a47af-130">See also</span></span>

[<span data-ttu-id="a47af-131">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="a47af-131">Document understanding overview</span></span>](../document-understanding-overview.md)

