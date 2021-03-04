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
description: Erfahren Sie, wie Sie Inhalte aus einem Bewertungssatz für Präsentationen oder externe Rezensionen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a2ca8e2f400d9f257549e59305d1fd56586185e2
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423646"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="19b78-103">Exportieren von Dokumenten aus einem Überprüfungssatz in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="19b78-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="19b78-104">Der Export ermöglicht Benutzern das Anpassen der Inhalte, die im Downloadpaket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="19b78-104">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="19b78-105">Das Exporttool bietet eine Konfigurationsseite mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="19b78-105">The Export tool provides a configuration page with the following settings:</span></span>

![Optionen zum Exportieren von Elementen aus einem Überprüfungssatz](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a><span data-ttu-id="19b78-107">Exportoptionen</span><span class="sxs-lookup"><span data-stu-id="19b78-107">Export options</span></span>

- <span data-ttu-id="19b78-108">Exportname: Name des Exportauftrags.</span><span class="sxs-lookup"><span data-stu-id="19b78-108">Export name: Name of the export job.</span></span>

- <span data-ttu-id="19b78-109">Beschreibung: Freitextfeld zum Hinzufügen einer Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="19b78-109">Description: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="19b78-110">Exportieren Sie diese Dokumente:</span><span class="sxs-lookup"><span data-stu-id="19b78-110">Export these documents:</span></span>

  - <span data-ttu-id="19b78-111">Nur ausgewählte Dokumente – Exportiert nur die aktuell ausgewählten Dokumente.</span><span class="sxs-lookup"><span data-stu-id="19b78-111">Selected documents only - Exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="19b78-112">Alle Dokumente im Überprüfungssatz – Exportiert alle Dokumente im Überprüfungssatz</span><span class="sxs-lookup"><span data-stu-id="19b78-112">All documents in the review set - Exports all documents in the review set</span></span>

- <span data-ttu-id="19b78-113">Metadaten</span><span class="sxs-lookup"><span data-stu-id="19b78-113">Metadata</span></span>
  
  - <span data-ttu-id="19b78-114">Datei laden : Diese Datei enthält Metadaten für jede Datei.</span><span class="sxs-lookup"><span data-stu-id="19b78-114">Load file - This file contains metadata for each file.</span></span> <span data-ttu-id="19b78-115">Weitere Informationen zu den enthaltenen Feldern finden Sie unter [Dokumentmetadatenfelder in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="19b78-115">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="19b78-116">Diese Datei kann in der Regel von eDiscovery-Tools von Drittanbietern aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="19b78-116">This file can typically be ingested by third-party eDiscovery tools.</span></span>
  
  - <span data-ttu-id="19b78-117">Tags : Wenn diese Option ausgewählt ist, werden Tagginginformationen in die Ladedatei aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="19b78-117">Tags - When selected, tagging information will be included in the load file.</span></span>

- <span data-ttu-id="19b78-118">Inhalt</span><span class="sxs-lookup"><span data-stu-id="19b78-118">Content</span></span>
  
  - <span data-ttu-id="19b78-119">Systemeigene Dateien : Aktivieren Sie dieses Kontrollkästchen, um die systemeigenen Dateien zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="19b78-119">Native files - Select this checkbox to include the native files.</span></span>
  
  - <span data-ttu-id="19b78-120">Unterhaltungsoptionen</span><span class="sxs-lookup"><span data-stu-id="19b78-120">Conversation options</span></span>
    
    - <span data-ttu-id="19b78-121">Unterhaltungsdateien – Exportiert rekonstruierte Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="19b78-121">Conversation files - Export reconstructed chat messages.</span></span> <span data-ttu-id="19b78-122">Dieses Format zeigt Unterhaltungen in einem Format an, das dem entspricht, was Benutzern in der systemeigenen Anwendung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="19b78-122">This format presents conversations in a form that resembles what users see in the native application.</span></span>
    
    - <span data-ttu-id="19b78-123">Einzelne Chatnachrichten – Exportieren Sie die ursprünglichen Unterhaltungsdateien, wie sie in Microsoft 365 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="19b78-123">Individual chat messages - Export the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="19b78-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="19b78-124">Options</span></span>

  - <span data-ttu-id="19b78-125">Textdateien : Schließen Sie extrahierte Textversionen systemeigener Dateien ein.</span><span class="sxs-lookup"><span data-stu-id="19b78-125">Text files - Include extracted text versions of native files.</span></span>
  
  - <span data-ttu-id="19b78-126">Ersetzen Sie redacted natives durch konvertierte PDFs: Wenn während der Überprüfung redaktierte PDF-Dateien generiert werden, sind diese Dateien für den Export verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19b78-126">Replace redacted natives with converted PDFs - If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="19b78-127">Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden, die redacted wurden (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Redactions enthalten.</span><span class="sxs-lookup"><span data-stu-id="19b78-127">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="19b78-128">Ausgabeoptionen (Exportierte Inhalte stehen entweder direkt über einen Webbrowser zum Herunterladen bereit oder können an ein Azure Storage-Konto gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="19b78-128">Output options (Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="19b78-129">Die ersten beiden Optionen ermöglichen den direkten Download.)</span><span class="sxs-lookup"><span data-stu-id="19b78-129">The first two options enable direct download.)</span></span>
  
  - <span data-ttu-id="19b78-130">Lose Dateien und PSTs (E-Mails werden psTs nach Möglichkeit hinzugefügt) – Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die Benutzer in ihren systemeigenen Anwendungen sehen.</span><span class="sxs-lookup"><span data-stu-id="19b78-130">Loose files and PSTs (email is added to PSTs when possible) - Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="19b78-131">Weitere Informationen finden Sie im Abschnitt [Lose-Dateien und PST-Exportstruktur.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="19b78-131">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="19b78-132">Verdichtete Verzeichnisstruktur – Dateien werden exportiert und im Download enthalten.</span><span class="sxs-lookup"><span data-stu-id="19b78-132">Condensed directory structure - Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="19b78-133">Verdichtete Verzeichnisstruktur, die in Ihr Azure Storage-Konto exportiert wurde – Dateien werden in das Azure Storage-Konto Ihrer Organisation exportiert.</span><span class="sxs-lookup"><span data-stu-id="19b78-133">Condensed directory structure exported to your Azure Storage account - Files are exported to your organization's Azure Storage account.</span></span>

## <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="19b78-134">Lose Dateien und PST-Exportstruktur</span><span class="sxs-lookup"><span data-stu-id="19b78-134">Loose files and PST export structure</span></span>

<span data-ttu-id="19b78-135">Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:</span><span class="sxs-lookup"><span data-stu-id="19b78-135">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="19b78-136">Stammordner – Dieser Ordner in ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="19b78-136">Root folder – This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="19b78-137">Export_load_file.csv - Metadatendatei.</span><span class="sxs-lookup"><span data-stu-id="19b78-137">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="19b78-138">Summary.csv – Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="19b78-138">Summary.csv - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="19b78-139">Exchange – Dieser Ordner enthält alle Inhalte aus Exchange im systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="19b78-139">Exchange - This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="19b78-140">Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.</span><span class="sxs-lookup"><span data-stu-id="19b78-140">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="19b78-141">SharePoint = Dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="19b78-141">SharePoint = This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="19b78-142">Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.</span><span class="sxs-lookup"><span data-stu-id="19b78-142">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

## <a name="condensed-directory-structure"></a><span data-ttu-id="19b78-143">Verdichtete Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="19b78-143">Condensed directory structure</span></span>

- <span data-ttu-id="19b78-144">Stammordner : Dieser Ordner heißt ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="19b78-144">Root folder - This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="19b78-145">Export_load_file.csv - Metadatendatei.</span><span class="sxs-lookup"><span data-stu-id="19b78-145">Export_load_file.csv - Metadata file.</span></span>
  
  - <span data-ttu-id="19b78-146">Summary.txt – Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="19b78-146">Summary.txt - A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="19b78-147">Input_or_native_files – Dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="19b78-147">Input_or_native_files - This folder contains all the native files that were exported.</span></span> <span data-ttu-id="19b78-148">Wenn Sie redacted PDF-Dateien exportieren, werden sie nicht in PST-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="19b78-148">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="19b78-149">Stattdessen werden sie einem getrennten Ordner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="19b78-149">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="19b78-150">Error_files – Dieser Ordner enthält die folgenden Fehlerdateien, wenn sie im Export enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="19b78-150">Error_files - This folder contains the following error files, if they are included in the export:</span></span>
    
    - <span data-ttu-id="19b78-151">ExtractionError.</span><span class="sxs-lookup"><span data-stu-id="19b78-151">ExtractionError.</span></span> <span data-ttu-id="19b78-152">Eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="19b78-152">A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>
    
    - <span data-ttu-id="19b78-153">ProcessingError – Diese Datei enthält eine Liste von Dokumenten mit Verarbeitungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="19b78-153">ProcessingError – This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="19b78-154">Dieser Inhalt ist Elementebene, d. h., wenn eine Anlage zu einem Verarbeitungsfehler geführt hat, wird die E-Mail-Nachricht, die die Anlage enthält, in diesem Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="19b78-154">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="19b78-155">Extracted_text_files – Dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="19b78-155">Extracted_text_files - This folder contains all of the extracted text files that were generated at processing.</span></span>

> [!NOTE]
> <span data-ttu-id="19b78-156">Exportaufträge werden für die Lebensdauer des Falls beibehalten.</span><span class="sxs-lookup"><span data-stu-id="19b78-156">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="19b78-157">Sie müssen den Inhalt jedoch innerhalb von 30 Tagen nach Abschluss des Exportauftrags aus einem Exportauftrag herunterladen.</span><span class="sxs-lookup"><span data-stu-id="19b78-157">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>
