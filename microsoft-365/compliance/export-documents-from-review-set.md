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
description: Erfahren Sie, wie Sie Inhalte aus einem Advanced eDiscovery-Überprüfungssatz für Präsentationen oder externe Rezensionen auswählen und exportieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581018"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="95602-103">Exportieren von Dokumenten aus einem Überprüfungssatz in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="95602-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="95602-104">Der Export ermöglicht Benutzern das Anpassen der Inhalte, die im Downloadpaket enthalten sind, wenn Sie ein Dokument aus einem Überprüfungssatz in Advanced eDiscovery exportieren.</span><span class="sxs-lookup"><span data-stu-id="95602-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="95602-105">So exportieren Sie Dokumente aus einem Überprüfungssatz:</span><span class="sxs-lookup"><span data-stu-id="95602-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="95602-106">Öffnen Sie im Microsoft 365 Compliance Center den Fall  Advanced eDiscovery, wählen Sie die Registerkarte Sätze überprüfen aus, und wählen Sie dann den Überprüfungssatz aus, den Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="95602-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="95602-107">Klicken Sie im Überprüfungssatz auf **Aktion**  >  **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="95602-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="95602-108">Das Exporttool zeigt die Flyoutseite mit den Einstellungen zum Konfigurieren des Exports an.</span><span class="sxs-lookup"><span data-stu-id="95602-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="95602-109">Einige Optionen sind standardmäßig ausgewählt, sie können jedoch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="95602-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="95602-110">Beschreibungen der Exportoptionen, die Sie konfigurieren können, finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="95602-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Konfigurationsoptionen zum Exportieren von Elementen aus einem Überprüfungssatz](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="95602-112">Nachdem Sie den Export konfiguriert haben, klicken Sie **auf Exportieren,** um den Exportvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="95602-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="95602-113">Abhängig von der Option,  die Sie im Abschnitt Ausgabeoptionen ausgewählt haben, können Sie auf die Exportdateien durch direkten Download oder im Azure Storage-Konto Ihrer Organisation zugreifen.</span><span class="sxs-lookup"><span data-stu-id="95602-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="95602-114">Exportaufträge werden für die Lebensdauer des Falls beibehalten.</span><span class="sxs-lookup"><span data-stu-id="95602-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="95602-115">Sie müssen den Inhalt jedoch innerhalb von 30 Tagen nach Abschluss des Exportauftrags aus einem Exportauftrag herunterladen.</span><span class="sxs-lookup"><span data-stu-id="95602-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="95602-116">Exportoptionen</span><span class="sxs-lookup"><span data-stu-id="95602-116">Export options</span></span>

<span data-ttu-id="95602-117">Verwenden Sie die folgenden Optionen, um den Export zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="95602-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="95602-118">**Exportname**: Name des Exportauftrags.</span><span class="sxs-lookup"><span data-stu-id="95602-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="95602-119">**Beschreibung**: Freitextfeld zum Hinzufügen einer Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="95602-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="95602-120">**Exportieren dieser Dokumente**</span><span class="sxs-lookup"><span data-stu-id="95602-120">**Export these documents**</span></span>

  - <span data-ttu-id="95602-121">**Nur ausgewählte Dokumente:** Mit dieser Option werden nur die aktuell ausgewählten Dokumente exportiert.</span><span class="sxs-lookup"><span data-stu-id="95602-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="95602-122">**Alle Dokumente im Überprüfungssatz:** Mit dieser Option werden alle Dokumente im Überprüfungssatz exportiert.</span><span class="sxs-lookup"><span data-stu-id="95602-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="95602-123">**Metadaten**</span><span class="sxs-lookup"><span data-stu-id="95602-123">**Metadata**</span></span>
  
  - <span data-ttu-id="95602-124">**Ladedatei**: Diese Datei enthält Metadaten für jede Datei.</span><span class="sxs-lookup"><span data-stu-id="95602-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="95602-125">Diese Datei kann in der Regel von eDiscovery-Tools von Drittanbietern aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="95602-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="95602-126">Weitere Informationen zu den enthaltenen Feldern finden Sie unter [Dokumentmetadatenfelder in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="95602-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="95602-127">**Tags**: Wenn diese Option ausgewählt ist, sind Tagginginformationen in der Ladedatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="95602-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="95602-128">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="95602-128">**Content**</span></span>
  
  - <span data-ttu-id="95602-129">**Systemeigene Dateien:** Aktivieren Sie dieses Kontrollkästchen, um die systemeigenen Dateien der Dokumente in den Prüfsatz zu setzen.</span><span class="sxs-lookup"><span data-stu-id="95602-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="95602-130">Wenn Sie systemeigene Dateien exportieren möchten, haben Sie die folgenden Optionen für den Export von Chatunterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="95602-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="95602-131">**Unterhaltungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="95602-131">**Conversation options**</span></span>

    - <span data-ttu-id="95602-132">**Unterhaltungsdateien:** Mit dieser Option werden rekonstruierte Chatunterhaltungen exportiert.</span><span class="sxs-lookup"><span data-stu-id="95602-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="95602-133">Dieses Format zeigt Unterhaltungen in einem Format an, das dem entspricht, was Benutzern in der systemeigenen Anwendung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="95602-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="95602-134">**Einzelne Chatnachrichten:** Mit dieser Option werden die ursprünglichen Unterhaltungsdateien exportiert, wie sie in Microsoft 365 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="95602-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="95602-135">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="95602-135">**Options**</span></span>

  - <span data-ttu-id="95602-136">**Textdateien**: – Diese Option enthält die extrahierten Textversionen systemeigener Dateien im Export.</span><span class="sxs-lookup"><span data-stu-id="95602-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="95602-137">**Ersetzen Sie redacted natives durch konvertierte PDFs:** Wenn während der Überprüfung redaktierte PDF-Dateien generiert werden, sind diese Dateien für den Export verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95602-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="95602-138">Sie können auswählen, dass nur die systemeigenen Dateien exportiert werden, die redacted wurden (indem Sie diese Option nicht auswählen), oder Sie können diese Option auswählen, um die PDF-Dateien zu exportieren, die die tatsächlichen Redactions enthalten.</span><span class="sxs-lookup"><span data-stu-id="95602-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="95602-139">**Ausgabeoptionen:** Exportierte Inhalte können entweder direkt über einen Webbrowser heruntergeladen oder an ein Azure Storage-Konto gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="95602-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="95602-140">Die ersten beiden Optionen ermöglichen den direkten Download.</span><span class="sxs-lookup"><span data-stu-id="95602-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="95602-141">**Lose Dateien und PSTs**(E-Mails werden psTs nach Möglichkeit hinzugefügt): Dateien werden in einem Format exportiert, das der ursprünglichen Verzeichnisstruktur ähnelt, die benutzer in ihren systemeigenen Anwendungen sehen.</span><span class="sxs-lookup"><span data-stu-id="95602-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="95602-142">Weitere Informationen finden Sie im Abschnitt [Lose-Dateien und PST-Exportstruktur.](#loose-files-and-pst-export-structure)</span><span class="sxs-lookup"><span data-stu-id="95602-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="95602-143">**Verdichtete Verzeichnisstruktur:** Dateien werden exportiert und im Download enthalten.</span><span class="sxs-lookup"><span data-stu-id="95602-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="95602-144">**Verdichtete Verzeichnisstruktur, die in Ihr Azure Storage-Konto** exportiert wurde: Dateien werden in das Azure Storage-Konto Ihrer Organisation exportiert.</span><span class="sxs-lookup"><span data-stu-id="95602-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="95602-145">Für diese Option müssen Sie die URL für den Container in Ihrem Azure Storage-Konto angeben, in den die Dateien exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="95602-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="95602-146">Sie müssen auch das SAS-Token (Shared Access Signature) für Ihr Azure Storage-Konto bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="95602-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="95602-147">Weitere Informationen finden Sie [unter Exportieren von Dokumenten in einem Überprüfungssatz auf ein Azure Storage-Konto](download-export-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="95602-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="95602-148">In den folgenden Abschnitten wird die Ordnerstruktur für lose Dateien und verkürzte Verzeichnisstrukturoptionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95602-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="95602-149">Lose Dateien und PST-Exportstruktur</span><span class="sxs-lookup"><span data-stu-id="95602-149">Loose files and PST export structure</span></span>

<span data-ttu-id="95602-150">Wenn Sie diese Exportoption auswählen, wird der exportierte Inhalt in der folgenden Struktur organisiert:</span><span class="sxs-lookup"><span data-stu-id="95602-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="95602-151">Stammordner: Dieser Ordner in ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="95602-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="95602-152">Export_load_file.csv: Die Metadatendatei.</span><span class="sxs-lookup"><span data-stu-id="95602-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="95602-153">Summary.csv: Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="95602-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="95602-154">Exchange: Dieser Ordner enthält alle Inhalte aus Exchange im systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="95602-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="95602-155">Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.</span><span class="sxs-lookup"><span data-stu-id="95602-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="95602-156">SharePoint: Dieser Ordner enthält alle systemeigenen Inhalte aus SharePoint in einem systemeigenen Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="95602-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="95602-157">Systemeigene Dateien werden durch redacted PDFs ersetzt, wenn Sie die Option **Redacted Natives durch konvertierte PDFs ersetzen ausgewählt** haben.</span><span class="sxs-lookup"><span data-stu-id="95602-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="95602-158">Verdichtete Verzeichnisstruktur</span><span class="sxs-lookup"><span data-stu-id="95602-158">Condensed directory structure</span></span>

- <span data-ttu-id="95602-159">Stammordner: Dieser Ordner heißt ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="95602-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="95602-160">Export_load_file.csv: Die Metadatendatei.</span><span class="sxs-lookup"><span data-stu-id="95602-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="95602-161">Summary.txt: Eine Zusammenfassungsdatei, die auch Exportstatistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="95602-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="95602-162">NativeFiles: Dieser Ordner enthält alle systemeigenen Dateien, die exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="95602-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="95602-163">Wenn Sie redacted PDF-Dateien exportieren, werden sie nicht in PST-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="95602-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="95602-164">Stattdessen werden sie einem getrennten Ordner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="95602-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="95602-165">Error_files: Dieser Ordner enthält die folgenden Fehlerdateien, wenn sie im Export enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="95602-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="95602-166">ExtractionError: Eine CSV-Datei, die alle verfügbaren Metadaten von Dateien enthält, die nicht ordnungsgemäß aus übergeordneten Dateien extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="95602-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="95602-167">ProcessingError: Diese Datei enthält eine Liste von Dokumenten mit Verarbeitungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="95602-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="95602-168">Dieser Inhalt ist Elementebene, d. h., wenn eine Anlage zu einem Verarbeitungsfehler geführt hat, wird die E-Mail-Nachricht, die die Anlage enthält, in diesem Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="95602-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="95602-169">Extracted_text_files: Dieser Ordner enthält alle extrahierten Textdateien, die bei der Verarbeitung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="95602-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
