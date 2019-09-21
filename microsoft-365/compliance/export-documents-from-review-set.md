---
title: Exportieren von Dokumenten aus einem Prüfdateisatz
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: cf8b11fa82398ab8cfa3981064741d0dbf349f71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081437"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="2b640-102">Exportieren von Dokumenten aus einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="2b640-102">Export documents from a review set</span></span>

<span data-ttu-id="2b640-103">Sie können Inhalte für die Präsentation oder externe Überprüfung aus einem Überprüfungs Sätze mit einer der folgenden Methoden exportieren:</span><span class="sxs-lookup"><span data-stu-id="2b640-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="2b640-104">Dokumente herunterladen</span><span class="sxs-lookup"><span data-stu-id="2b640-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="2b640-105">Exportieren von Dokumenten</span><span class="sxs-lookup"><span data-stu-id="2b640-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="2b640-106">Herunterladen von Dokumenten aus einem Überprüfungspaket</span><span class="sxs-lookup"><span data-stu-id="2b640-106">Download documents from a review set</span></span>

<span data-ttu-id="2b640-107">Download bietet eine einfache Möglichkeit zum Herunterladen von Inhalten aus einer Überprüfungsgruppe im systemeigenen Format.</span><span class="sxs-lookup"><span data-stu-id="2b640-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="2b640-108">Es nutzt die Datentransfer Funktionen des Browsers, sodass nach dem Download eine Browser Ansage angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2b640-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="2b640-109">Mit dieser Methode heruntergeladene Dateien werden in eine Containerdatei gezippt und werden Dateien auf Elementebene sein.</span><span class="sxs-lookup"><span data-stu-id="2b640-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="2b640-110">Wenn Sie also eine Anlage auswählen, erhalten Sie automatisch die e-Mail-Adresse, die mit der Anlage eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2b640-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="2b640-111">Wenn Sie eine Excel-Kalkulationstabelle auswählen, die in ein Word-Dokument eingebettet wurde, erhalten Sie das Word-Dokument mit eingebettetem Excel-Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="2b640-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="2b640-112">Durch heruntergeladene Elemente wird das Datum der letzten Änderung beibehalten, das als Dateieigenschaft angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b640-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="2b640-113">Um Inhalte aus einem Überprüfungs herunterzuladen, wählen Sie zunächst die Dateien aus, die Sie herunterladen möchten, und klicken Sie dann im Menü Aktionen auf "herunterladen".</span><span class="sxs-lookup"><span data-stu-id="2b640-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![Screenshot einer automatisch generierten Computerbeschreibung](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="2b640-115">Exportieren von Dokumenten aus einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="2b640-115">Export documents from a review set</span></span>

<span data-ttu-id="2b640-116">Mit dem Export können Benutzer die Inhalte anpassen, die im Downloadpaket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2b640-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="2b640-117">Es stellt eine Konfigurationsseite mit den folgenden Einstellungen bereit:</span><span class="sxs-lookup"><span data-stu-id="2b640-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="2b640-118">Metadaten-Datei</span><span class="sxs-lookup"><span data-stu-id="2b640-118">Metadata file</span></span>

<span data-ttu-id="2b640-119">Dies kann als ihre "Laden Datei" betrachtet werden, die Metadaten enthält, die den exportierten Dateien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2b640-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="2b640-120">Eine Liste der in der Metadatendatei verfügbaren Felder \[finden\]Sie unter Link.</span><span class="sxs-lookup"><span data-stu-id="2b640-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="2b640-121">Diese Datei kann normalerweise von drei<sup>Remote</sup> Tools von Drittanbietern aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="2b640-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="2b640-122">Tag-Daten</span><span class="sxs-lookup"><span data-stu-id="2b640-122">Tag data</span></span>

<span data-ttu-id="2b640-123">Dieser Inhalt würde als Felder in der Metadatendatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2b640-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="2b640-124">Sie enthält alle in Überprüfungs Sätzen angewendeten Tag-Informationen.</span><span class="sxs-lookup"><span data-stu-id="2b640-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="2b640-125">Textdateien</span><span class="sxs-lookup"><span data-stu-id="2b640-125">Text files</span></span>

<span data-ttu-id="2b640-126">Text Dateien können für jede Datei generiert werden, die aus einem Überprüfungs Satz exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2b640-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="2b640-127">Häufig sind diese Dateien für Service Partner erforderlich, wenn Sie Daten<sup>in Drittanbieter</sup> -Tools nach Downstream aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="2b640-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="2b640-128">Behandelte Dateien</span><span class="sxs-lookup"><span data-stu-id="2b640-128">Redacted files</span></span>

<span data-ttu-id="2b640-129">Wenn während der Überprüfung redigierte PDFs generiert werden, stehen diese Dateien während des Exports zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2b640-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="2b640-130">Benutzer können entscheiden, ob Sie systemeigene Dateien exportieren oder natives ersetzen möchten, bei denen die in PDFs gebrannt wurden.</span><span class="sxs-lookup"><span data-stu-id="2b640-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="2b640-131">Exportspeicherort</span><span class="sxs-lookup"><span data-stu-id="2b640-131">Export Location</span></span>

<span data-ttu-id="2b640-132">Exportierte Inhalte werden entweder an ein von Microsoft bereitgestelltes Azure-BLOB zugestellt, oder das BLOB eines Kunden kann verwendet werden, wenn die Details beim Export angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2b640-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="2b640-133">Export Struktur</span><span class="sxs-lookup"><span data-stu-id="2b640-133">Export Structure</span></span>

<span data-ttu-id="2b640-134">Wenn Inhalte aus einem Überprüfungs Satzes exportiert werden, ist der Inhalt in der folgenden Struktur organisiert.</span><span class="sxs-lookup"><span data-stu-id="2b640-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="2b640-135">Stammordner – Download-ID</span><span class="sxs-lookup"><span data-stu-id="2b640-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="2b640-136">Exportieren\_der\_Datei "file. CSV = Metadata"</span><span class="sxs-lookup"><span data-stu-id="2b640-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="2b640-137">Summary. txt = eine Zusammenfassungsdatei mit Export Statistiken</span><span class="sxs-lookup"><span data-stu-id="2b640-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="2b640-138">Input\_oder Native\_files = enthält alle systemeigenen Dateien</span><span class="sxs-lookup"><span data-stu-id="2b640-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="2b640-139">Error\_files = enthält alle Fehler Dateien, die im Export enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2b640-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="2b640-140">ExtractionError – eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden</span><span class="sxs-lookup"><span data-stu-id="2b640-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="2b640-141">ProcessingError – Inhalte mit Verarbeitungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="2b640-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="2b640-142">Dieser Inhalt ist eine Elementebene, was bedeutet, dass bei einer Anlage ein Verarbeitungsfehler auftritt, wird die e-Mail-Nachricht, die die Anlage enthält, in diesen Ordner aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="2b640-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="2b640-143">Extrahierte\_Text\_Dateien = enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2b640-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>