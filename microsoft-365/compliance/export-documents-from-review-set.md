---
title: Exportieren von Dokumenten aus einem Prüfdateisatz
f1.keywords:
- NOCSH
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
description: Hier erfahren Sie, wie Sie Inhalte aus einer Überprüfungsgruppe für Präsentationen oder externe Überprüfungen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 855f1b8fef7a1df6ed86f058b71e5027851b5f0d
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399176"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="b9894-103">Exportieren von Dokumenten aus einem Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="b9894-103">Export documents from a review set</span></span>

<span data-ttu-id="b9894-104">Mit dem Export können Benutzer die Inhalte anpassen, die im Downloadpaket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b9894-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="b9894-105">Das Export-Tool stellt eine Konfigurationsseite mit den folgenden Einstellungen bereit:</span><span class="sxs-lookup"><span data-stu-id="b9894-105">The Export tool provides a configuration page with the following settings:</span></span>

![Optionen zum Exportieren von Elementen aus einer Überprüfungsgruppe](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="b9894-107">Exportoptionen</span><span class="sxs-lookup"><span data-stu-id="b9894-107">Export options</span></span>

- <span data-ttu-id="b9894-108">Export Name: Name des Exportauftrags.</span><span class="sxs-lookup"><span data-stu-id="b9894-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="b9894-109">Beschreibung: frei Text Feld, in dem Sie eine Beschreibung hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="b9894-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="b9894-110">Exportieren Sie diese Dokumente:</span><span class="sxs-lookup"><span data-stu-id="b9894-110">Export these documents:</span></span>

  - <span data-ttu-id="b9894-111">Nur ausgewählte Dokumente: exportiert nur die aktuell ausgewählten Dokumente.</span><span class="sxs-lookup"><span data-stu-id="b9894-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="b9894-112">Alle Dokumente in der Überprüfungsgruppe: exportiert alle Dokumente in der Überprüfungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="b9894-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="b9894-113">Metadaten</span><span class="sxs-lookup"><span data-stu-id="b9894-113">Metadata</span></span>
  
  - <span data-ttu-id="b9894-114">Datei laden – diese Datei enthält Metadaten für jede Datei.</span><span class="sxs-lookup"><span data-stu-id="b9894-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="b9894-115">Weitere Informationen dazu, welche Felder enthalten sind, finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) .</span><span class="sxs-lookup"><span data-stu-id="b9894-115">see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md) for more information about what fields are included.</span></span> <span data-ttu-id="b9894-116">Diese Datei kann normalerweise von den eDiscovery-Tools von Drittanbietern aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="b9894-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="b9894-117">Tags – Wenn diese Option ausgewählt ist, werden Markierungsinformationen in die Datei "Laden" eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b9894-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="b9894-118">Inhalt</span><span class="sxs-lookup"><span data-stu-id="b9894-118">Content</span></span>
  
  - <span data-ttu-id="b9894-119">Systemeigene Dateien: Aktivieren Sie dieses Kontrollkästchen, um die systemeigenen Dateien einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="b9894-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="b9894-120">Unterhaltungsoptionen</span><span class="sxs-lookup"><span data-stu-id="b9894-120">Conversation options</span></span>
    
    - <span data-ttu-id="b9894-121">Unterhaltungsdateien – exportieren Sie rekonstruierte Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="b9894-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="b9894-122">In diesem Format werden Unterhaltungen in einem Formular dargestellt, das den Benutzern in der systemeigenen Anwendung ähnelt.</span><span class="sxs-lookup"><span data-stu-id="b9894-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="b9894-123">Einzelne Chatnachrichten – exportieren Sie die ursprünglichen Unterhaltungsdateien so, wie Sie in Microsoft 365 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="b9894-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="b9894-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="b9894-124">Options</span></span>

  - <span data-ttu-id="b9894-125">Textdateien – enthalten extrahierten Textversionen von systemeigenen Dateien.</span><span class="sxs-lookup"><span data-stu-id="b9894-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="b9894-126">Ersetzen Sie die bearbeiteten natives durch konvertierte PDFs-wenn im Rahmen der Überprüfung die erstellten PDF-Dateien generiert werden, stehen diese Dateien für den Export zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b9894-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="b9894-127">Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden sollen (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Aktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b9894-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="b9894-128">Ausgabeoptionen (exportierte Inhalte stehen entweder direkt über einen Webbrowser herunter oder können an ein Azure-Speicherkonto gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9894-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="b9894-129">Die ersten beiden Optionen ermöglichen das direkte herunterladen.)</span><span class="sxs-lookup"><span data-stu-id="b9894-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="b9894-130">Loose files and PST (e-Mail wird zu PST hinzugefügt, wenn möglich) – Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die Benutzern in ihren systemeigenen Anwendungen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9894-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="b9894-131">Weitere Informationen finden Sie im Abschnitt [Loose files and PST Export Structure](#loose-files-and-pst-export-structure) .</span><span class="sxs-lookup"><span data-stu-id="b9894-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="b9894-132">Komprimierte Verzeichnisstruktur – Dateien werden exportiert und werden in den Download eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b9894-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="b9894-133">Komprimierte Verzeichnisstruktur, die in Ihr Azure-Speicherkonto exportiert wurde-Dateien werden in das Azure-Speicher-abrechnen Ihrer Organisation exportiert.</span><span class="sxs-lookup"><span data-stu-id="b9894-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage accouunt.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="b9894-134">Lose Dateien und PST-Exportstruktur</span><span class="sxs-lookup"><span data-stu-id="b9894-134">Loose files and PST export structure</span></span>

<span data-ttu-id="b9894-135">Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:</span><span class="sxs-lookup"><span data-stu-id="b9894-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="b9894-136">Stammordner – dieser Ordner mit dem Namen ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="b9894-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="b9894-137">Export_load_file.csv-Metadata-Datei.</span><span class="sxs-lookup"><span data-stu-id="b9894-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="b9894-138">Summary.csv-eine Zusammenfassungsdatei, die auch Export Statistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="b9894-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="b9894-139">Exchange – dieser Ordner enthält alle Inhalte aus Exchange im systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="b9894-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="b9894-140">Natives-Dateien werden durch redigierte PDFs ersetzt, wenn Sie die Option " **natives mit konvertierten PDFs ersetzen** " ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b9894-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="b9894-141">SharePoint = dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="b9894-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="b9894-142">Natives-Dateien werden durch redigierte PDFs ersetzt, wenn Sie die Option " **natives mit konvertierten PDFs ersetzen** " ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b9894-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="b9894-143">Komprimierte Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="b9894-143">Condensed directory structure</span></span>

- <span data-ttu-id="b9894-144">Stammordner-dieser Ordner hat den Namen ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="b9894-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="b9894-145">Export_load_file.csv-Metadata-Datei.</span><span class="sxs-lookup"><span data-stu-id="b9894-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="b9894-146">Summary.txt-eine Zusammenfassungsdatei, die auch Export Statistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="b9894-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="b9894-147">Input_or_native_files-dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9894-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="b9894-148">Wenn Sie redigierte PDF-Dateien exportieren, werden Sie nicht in PST-Dateien abgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9894-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="b9894-149">Stattdessen werden Sie einem getrennten Ordner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9894-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="b9894-150">Error_files-dieser Ordner enthält die folgenden Fehler Dateien, wenn Sie im Export enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="b9894-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="b9894-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="b9894-151">ExtractionError.</span></span> <span data-ttu-id="b9894-152">Eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9894-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="b9894-153">ProcessingError – diese Datei enthält eine Liste von Dokumenten mit Verarbeitungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="b9894-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="b9894-154">Dieser Inhalt ist auf Elementebene angegeben, was bedeutet, dass in diesem Ordner die e-Mail-Nachricht mit der Anlage enthalten ist, wenn eine Anlage zu einem Verarbeitungsfehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="b9894-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="b9894-155">Extracted_text_files-dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9894-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="b9894-156">Export Aufträge werden für die Lebensdauer des Falls aufbewahrt und können heruntergeladen werden, solange der Fall nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="b9894-156">Export jobs are retained for the life of the case and can be downloaded as long as the case isn't deleted.</span></span>
