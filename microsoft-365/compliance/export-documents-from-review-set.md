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
description: Erfahren Sie, wie Sie Inhalte aus einem Advanced eDiscovery Prüfdateisatz für Präsentationen oder externe Rezensionen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a174c147da6e424891508bad484f45f4a5d308b6
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461399"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="13e59-103">Exportieren von Dokumenten aus einem Prüfdateisatz in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="13e59-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="13e59-104">Mit dem Export können Benutzer den Inhalt anpassen, der im Downloadpaket enthalten ist, wenn Sie ein Dokument aus einem Prüfdateisatz in Advanced eDiscovery exportieren.</span><span class="sxs-lookup"><span data-stu-id="13e59-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="13e59-105">So exportieren Sie Dokumente aus einem Prüfdateisatz:</span><span class="sxs-lookup"><span data-stu-id="13e59-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="13e59-106">Öffnen Sie im Microsoft 365 Compliance Center die Advanced eDiscovery Fall, wählen Sie die Registerkarte **"Prüfdateisätze"** aus, und wählen Sie dann den Prüfdateisatz aus, den Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="13e59-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="13e59-107">Klicken Sie im Prüfdateisatz auf **"Aktion exportieren".**  >  </span><span class="sxs-lookup"><span data-stu-id="13e59-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="13e59-108">Das Exporttool zeigt die Flyoutseite mit den Einstellungen zum Konfigurieren des Exports an.</span><span class="sxs-lookup"><span data-stu-id="13e59-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="13e59-109">Einige Optionen sind standardmäßig ausgewählt, sie können jedoch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="13e59-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="13e59-110">Im folgenden Abschnitt finden Sie Beschreibungen der Exportoptionen, die Sie konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="13e59-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Konfigurationsoptionen für das Exportieren von Elementen aus einem Prüfdateisatz](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="13e59-112">Nachdem Sie den Export konfiguriert haben, klicken Sie auf **"Exportieren",** um den Exportvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="13e59-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="13e59-113">Abhängig von der Option, die Sie im Abschnitt **"Ausgabeoptionen"** ausgewählt haben, können Sie auf die Exportdateien durch direkten Download oder im Azure Storage Konto Ihrer Organisation zugreifen.</span><span class="sxs-lookup"><span data-stu-id="13e59-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="13e59-114">Exportaufträge werden für die Dauer des Falls beibehalten.</span><span class="sxs-lookup"><span data-stu-id="13e59-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="13e59-115">Sie müssen den Inhalt jedoch innerhalb von 30 Tagen nach Abschluss des Exportauftrags aus einem Exportauftrag herunterladen.</span><span class="sxs-lookup"><span data-stu-id="13e59-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="13e59-116">Exportoptionen</span><span class="sxs-lookup"><span data-stu-id="13e59-116">Export options</span></span>

<span data-ttu-id="13e59-117">Verwenden Sie die folgenden Optionen, um den Export zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13e59-117">Use the following options to configure the export.</span></span> <span data-ttu-id="13e59-118">Nicht alle Optionen sind für einige Ausgabeoptionen zulässig, vor allem der Export von Textdateien und redigierten PDFs ist beim Exportieren in das PST-Format nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="13e59-118">Not all options are allowed for some output options, most notably, export of text files and redacted PDFs are not allowed when exporting to the PST format.</span></span>

- <span data-ttu-id="13e59-119">**Exportname:** Name des Exportauftrags.</span><span class="sxs-lookup"><span data-stu-id="13e59-119">**Export name**: Name of the export job.</span></span> <span data-ttu-id="13e59-120">Dies wird verwendet, um die ZIP-Dateien zu benennen, die heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="13e59-120">This will be used to name the ZIP files that will be downloaded.</span></span>

- <span data-ttu-id="13e59-121">**Beschreibung:** Freitextfeld, in dem Sie eine Beschreibung hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="13e59-121">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="13e59-122">**Exportieren dieser Dokumente**</span><span class="sxs-lookup"><span data-stu-id="13e59-122">**Export these documents**</span></span>

  - <span data-ttu-id="13e59-123">Nur ausgewählte Dokumente: Diese Option exportiert nur die Dokumente, die derzeit ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="13e59-123">Selected documents only: This option exports only the documents that are currently selected.</span></span> <span data-ttu-id="13e59-124">Diese Option ist nur verfügbar, wenn Elemente in einem Prüfdateisatz ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="13e59-124">This option is only available when items are selected in a review set.</span></span>
  
  - <span data-ttu-id="13e59-125">Alle gefilterten Dokumente: Mit dieser Option werden die Dokumente in einem aktiven Filter exportiert.</span><span class="sxs-lookup"><span data-stu-id="13e59-125">All filtered documents: This option exports the documents in an active filter.</span></span> <span data-ttu-id="13e59-126">Diese Option ist nur verfügbar, wenn ein Filter auf den Prüfdateisatz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="13e59-126">This option is only available when a filter is applied to the review set.</span></span>
  
  - <span data-ttu-id="13e59-127">Alle Dokumente im Prüfdateisatz: Diese Option exportiert alle Dokumente im Prüfdateisatz.</span><span class="sxs-lookup"><span data-stu-id="13e59-127">All documents in the review set: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="13e59-128">**Ausgabeoptionen:** Exportierte Inhalte stehen entweder direkt über einen Webbrowser zum Download zur Verfügung oder können an ein Azure Storage Konto gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="13e59-128">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="13e59-129">Die ersten beiden Optionen ermöglichen den direkten Download.</span><span class="sxs-lookup"><span data-stu-id="13e59-129">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="13e59-130">Nur Berichte: Es werden nur die Zusammenfassungs- und Ladedatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="13e59-130">Reports only: Only the summary and load file are created.</span></span>
  
  - <span data-ttu-id="13e59-131">Lose Dateien und PSTs (E-Mails werden psTs nach Möglichkeit hinzugefügt): Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die von Benutzern in ihren systemeigenen Anwendungen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="13e59-131">Loose files and PSTs (email is added to PSTs when possible): Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="13e59-132">Weitere Informationen finden Sie im Abschnitt ["Lose Dateien und PST-Exportstruktur".](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="13e59-132">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="13e59-133">Komprimierte Verzeichnisstruktur: Dateien werden exportiert und im Download enthalten.</span><span class="sxs-lookup"><span data-stu-id="13e59-133">Condensed directory structure: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="13e59-134">Komprimierte Verzeichnisstruktur, die in Ihr Azure Storage-Konto exportiert wird: Dateien werden in das Azure Storage Konto Ihrer Organisation exportiert.</span><span class="sxs-lookup"><span data-stu-id="13e59-134">Condensed directory structure exported to your Azure Storage account: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="13e59-135">Für diese Option müssen Sie die URL für den Container in Ihrem Azure Storage konto angeben, in den die Dateien exportiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13e59-135">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="13e59-136">Sie müssen auch das SAS-Token (Shared Access Signature) für Ihr Azure Storage Konto bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="13e59-136">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="13e59-137">Weitere Informationen finden Sie unter [Exportieren von Dokumenten in einem Prüfdateisatz auf ein Azure Storage Konto.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="13e59-137">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

- <span data-ttu-id="13e59-138">**Include**</span><span class="sxs-lookup"><span data-stu-id="13e59-138">**Include**</span></span>
  
  - <span data-ttu-id="13e59-139">Tags: Wenn diese Option ausgewählt ist, sind die Tagginginformationen in der Ladedatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="13e59-139">Tags: When selected, tagging information is included in the load file.</span></span>
  
  - <span data-ttu-id="13e59-140">Textdateien: Diese Option enthält die extrahierten Textversionen systemeigener Dateien im Export.</span><span class="sxs-lookup"><span data-stu-id="13e59-140">Text files: This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="13e59-141">Ersetzen Sie redigierte Systemeigene durch konvertierte PDF-Dateien: Wenn bearbeitete PDF-Dateien während der Überprüfung generiert werden, stehen diese Dateien für den Export zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="13e59-141">Replace redacted natives with converted PDFs: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="13e59-142">Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden sollen, die bearbeitet wurden (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Aktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="13e59-142">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

<span data-ttu-id="13e59-143">In den folgenden Abschnitten wird die Ordnerstruktur für lose Dateien und komprimierte Verzeichnisstrukturoptionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="13e59-143">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span> <span data-ttu-id="13e59-144">Exporte werden in ZIP-Dateien mit einer maximalen Größe von nicht komprimierten Inhalten von 75 GB partitioniert.</span><span class="sxs-lookup"><span data-stu-id="13e59-144">Exports are partitioned into ZIP files with a maximum size of uncompressed content of 75 GB.</span></span> <span data-ttu-id="13e59-145">Wenn die Exportgröße kleiner als 75 GB ist, besteht der Export aus einer Zusammenfassungsdatei und einer einzelnen ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="13e59-145">If the export size is less than 75 GB, the export will consist of a summary file and a single ZIP file.</span></span> <span data-ttu-id="13e59-146">Bei Exporten mit mehr als 75 GB nicht komprimierten Daten werden mehrere ZIP-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="13e59-146">For exports larger than 75 GB of uncompressed data, multiple ZIP files will be created.</span></span> <span data-ttu-id="13e59-147">Nach dem Herunterladen können die ZIP-Dateien an einem einzigen Speicherort unkomprimiert werden, um den vollständigen Export neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="13e59-147">Once downloaded, the ZIP files can be uncompressed into a single location to recreate the full export.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="13e59-148">Lose Dateien und PST-Exportstruktur</span><span class="sxs-lookup"><span data-stu-id="13e59-148">Loose files and PST export structure</span></span>

<span data-ttu-id="13e59-149">Wenn Sie diese Exportoption auswählen, ist der exportierte Inhalt in der folgenden Struktur organisiert:</span><span class="sxs-lookup"><span data-stu-id="13e59-149">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="13e59-150">Summary.csv: Enthält eine Zusammenfassung der Inhalte, die aus dem Prüfdateisatz exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="13e59-150">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="13e59-151">Stammordner: Dieser Ordner mit dem Namen [Export Name] x von z.zip und wird für jede ZIP-Dateipartition wiederholt.</span><span class="sxs-lookup"><span data-stu-id="13e59-151">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="13e59-152">Export_load_file_x von z.csv: Die Metadatendatei.</span><span class="sxs-lookup"><span data-stu-id="13e59-152">Export_load_file_x of z.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="13e59-153">Warnungen und Fehler x von z.csv: Diese Datei enthält Informationen zu Fehlern, die beim Exportieren aus dem Prüfdateisatz aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="13e59-153">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>
  
  - <span data-ttu-id="13e59-154">Exchange: Dieser Ordner enthält alle Inhalte aus Exchange, die in PST-Dateien gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="13e59-154">Exchange: This folder contains all content from Exchange stored in PST files.</span></span> <span data-ttu-id="13e59-155">Bearbeitete PDF-Dateien können nicht in diese Option eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="13e59-155">Redacted PDF files cannot be included with this option.</span></span> <span data-ttu-id="13e59-156">Wenn eine Anlage im Prüfdateisatz ausgewählt ist, wird die übergeordnete E-Mail mit der angefügten Anlage exportiert.</span><span class="sxs-lookup"><span data-stu-id="13e59-156">If an attachment is selected in the review set, the parent email will be exported with the attachment attached.</span></span>
  
  - <span data-ttu-id="13e59-157">SharePoint: Dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="13e59-157">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="13e59-158">Bearbeitete PDF-Dateien können nicht in diese Option eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="13e59-158">Redacted PDF files cannot be included with this option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="13e59-159">Struktur des komprimierten Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="13e59-159">Condensed directory structure</span></span>

- <span data-ttu-id="13e59-160">Summary.csv: Enthält eine Zusammenfassung der Inhalte, die aus dem Prüfdateisatz exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="13e59-160">Summary.csv: Includes a summary of the content exported from the review set</span></span>

- <span data-ttu-id="13e59-161">Stammordner: Dieser Ordner mit dem Namen [Export Name] x von z.zip und wird für jede ZIP-Dateipartition wiederholt.</span><span class="sxs-lookup"><span data-stu-id="13e59-161">Root folder: This folder in named [Export Name] x of z.zip and will be repeated for each ZIP file partition.</span></span>
  
  - <span data-ttu-id="13e59-162">Export_load_file_x von z.csv: Die Metadatendatei und enthält auch den Speicherort jeder Datei, die in der ZIP-Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="13e59-162">Export_load_file_x of z.csv: The metadata file and also includes the location of each file that is stored in the ZIP file.</span></span>
  
  - <span data-ttu-id="13e59-163">Warnungen und Fehler x von z.csv: Diese Datei enthält Informationen zu Fehlern, die beim Exportieren aus dem Prüfdateisatz aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="13e59-163">Warnings and errors x of z.csv: This file includes information about errors encountered when trying to export from the review set.</span></span>

  - <span data-ttu-id="13e59-164">NativeFiles: Dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="13e59-164">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="13e59-165">Natives-Dateien werden durch redigierte PDFs ersetzt, wenn Sie die Option *"Redacted Natives durch konvertierte PDFs ersetzen"* ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="13e59-165">Natives files are replaced with redacted PDFs if you selected the *Replace redacted natives with converted PDFs* option.</span></span>
  
  - <span data-ttu-id="13e59-166">Error_files: Dieser Ordner enthält Dateien, deren Extraktion oder ein anderer Verarbeitungsfehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="13e59-166">Error_files: This folder contains files that had either extraction or other processing error.</span></span> <span data-ttu-id="13e59-167">Die Dateien werden in separaten Ordnern gespeichert, entweder ExtractionError oder ProcessingError.</span><span class="sxs-lookup"><span data-stu-id="13e59-167">The files will be placed into separate folders, either ExtractionError or ProcessingError.</span></span> <span data-ttu-id="13e59-168">Diese Dateien werden in der Ladedatei aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="13e59-168">These files are listed in the load file.</span></span>

  - <span data-ttu-id="13e59-169">Extracted_text_files: Dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="13e59-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a><span data-ttu-id="13e59-170">Komprimierte Verzeichnisstruktur, die in Ihr Azure Storage Konto exportiert wird</span><span class="sxs-lookup"><span data-stu-id="13e59-170">Condensed directory structure exported to your Azure Storage Account</span></span>

<span data-ttu-id="13e59-171">Diese Option verwendet die gleiche allgemeine Struktur wie die Struktur des *komprimierten Verzeichnisses.* Der Inhalt wird jedoch nicht gezippt, und die Daten werden in Ihrem Azure Storage-Konto gespeichert.</span><span class="sxs-lookup"><span data-stu-id="13e59-171">This option uses the same general structure as the *Condensed directory structure*, however the contents is not zipped and the data is saved to your Azure Storage account.</span></span> <span data-ttu-id="13e59-172">Diese Option wird in der Regel bei der Arbeit mit einem eDiscovery-Drittanbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="13e59-172">This option is generally used when working with a third-party eDiscovery provider.</span></span> <span data-ttu-id="13e59-173">Ausführliche Informationen zur Verwendung dieser Option finden Sie unter [Exportieren von Dokumenten in einem Prüfdateisatz, der auf ein Azure Storage Konto festgelegt ist.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="13e59-173">For details about how to use this option, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>
