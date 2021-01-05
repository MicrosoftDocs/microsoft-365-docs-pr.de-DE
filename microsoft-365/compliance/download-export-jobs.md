---
title: Herunterladen von Exportaufträgen für einen erweiterten eDiscovery-Fall
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Installieren und verwenden Sie den Azure Storage Explorer zum Herunterladen von Dokumenten, die aus einer Überprüfungsgruppe in Advanced eDiscovery exportiert wurden.
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751292"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a><span data-ttu-id="cc938-103">Herunterladen von Exportaufträgen in einem erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="cc938-103">Download export jobs in an Advanced eDiscovery case</span></span>

<span data-ttu-id="cc938-104">Wenn Sie Dokumente aus einer Überprüfungsgruppe in einem erweiterten eDiscovery-Fall exportieren, werden die Dokumente in einen von Microsoft bereitgestellten Azure-Speicherort oder an einen Azure-Speicherort hochgeladen, der von Ihrer Organisation verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="cc938-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="cc938-105">Der Typ des verwendeten Azure-Speicherorts hängt davon ab, welche Option beim Exportieren der Dokumente ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc938-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span>

<span data-ttu-id="cc938-106">In diesem Artikel wird beschrieben, wie Sie mithilfe des Microsoft Azure Speicher-Explorers eine Verbindung mit einem Azure-Speicherort herstellen, um die exportierten Dokumente zu durchsuchen und herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="cc938-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="cc938-107">Weitere Informationen zum Azure Storage-Explorer finden Sie unter [Quick Start: Verwenden des Azure Storage Explorers](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span><span class="sxs-lookup"><span data-stu-id="cc938-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="cc938-108">Schritt 1: Installieren des Azure Storage-Explorers</span><span class="sxs-lookup"><span data-stu-id="cc938-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="cc938-109">Der erste Schritt besteht darin, den Azure Storage Explorer herunterzuladen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="cc938-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="cc938-110">Anweisungen finden Sie unter [Azure Storage Explorer Tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span><span class="sxs-lookup"><span data-stu-id="cc938-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="cc938-111">Mit diesem Tool können Sie in Schritt 3 eine Verbindung mit den exportierten Dokumenten herstellen und diese herunterladen.</span><span class="sxs-lookup"><span data-stu-id="cc938-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="cc938-112">Schritt 2: Abrufen der SAS-URL aus dem Exportauftrag</span><span class="sxs-lookup"><span data-stu-id="cc938-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="cc938-113">Der nächste Schritt besteht darin, die SAS-URL (Shared Access Signature) zu erhalten, die generiert wurde, als Sie den Exportauftrag zum [Exportieren von Dokumenten aus einem Überprüfungs Satz](export-documents-from-review-set.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cc938-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="cc938-114">Sie können die SAS-URL für Dokumente kopieren, die in einen von Microsoft bereitgestellten Azure-Speicherort oder einen von Ihrer Organisation verwalteten Azure-Speicherplatz hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="cc938-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="cc938-115">In beiden Fällen verwenden Sie die SAS-URL, um eine Verbindung mit dem Azure-Speicherort in Schritt 3 herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cc938-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="cc938-116">Wechseln Sie auf der Seite **Erweiterte eDiscovery** zu dem Fall, und klicken Sie dann auf die Registerkarte **Exporte** .</span><span class="sxs-lookup"><span data-stu-id="cc938-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="cc938-117">Klicken Sie auf der Registerkarte **Exporte** auf den Exportvorgang, den Sie herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="cc938-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="cc938-118">Kopieren Sie auf der Flyout-Seite unter **Standorte** die angezeigte SAS-URL.</span><span class="sxs-lookup"><span data-stu-id="cc938-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="cc938-119">Falls erforderlich, können Sie Sie in einer Datei speichern, damit Sie in Schritt 3 darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="cc938-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![Kopieren der unter Standorte angezeigten SAS-URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="cc938-121">Schritt 3: Herstellen einer Verbindung mit dem Azure-Speicherort</span><span class="sxs-lookup"><span data-stu-id="cc938-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="cc938-122">Im letzten Schritt wird der Azure-Speicher-Explorer und die SAS-URL verwendet, um eine Verbindung mit dem Azure-Speicherort herzustellen und die Dokumente herunterzuladen, die Sie auf einen lokalen Computer exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="cc938-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1. <span data-ttu-id="cc938-123">Öffnen Sie den Azure Storage Explorer, den Sie in Schritt 1 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="cc938-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="cc938-124">Klicken Sie auf das Symbol **Konto hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="cc938-124">Click the **Add account** icon.</span></span> <span data-ttu-id="cc938-125">Alternativ können Sie mit der rechten Maustaste auf **Speicherkonten** klicken.</span><span class="sxs-lookup"><span data-stu-id="cc938-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![Klicken Sie auf das Symbol Konto hinzufügen.](../media/AzureStorageConnect.png)

3. <span data-ttu-id="cc938-127">Klicken Sie auf der Seite **Verbindung mit Azure-Speicher herstellen** auf **einen SAS-URI (Shared Access Signature) verwenden** , und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="cc938-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![Klicken Sie auf SAS-URI (Shared Access Signature) verwenden, und klicken Sie dann auf Weiter.](../media/AzureStorageConnect2.png)

4. <span data-ttu-id="cc938-129">Klicken Sie auf der Seite **mit SAS-URI anfügen** in das Feld URI, und fügen Sie dann die SAS-URL ein, die Sie in Schritt 2 abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="cc938-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![Fügen Sie die SAS-URL in das Feld URI ein.](../media/AzureStorageConnect3.png)

    <span data-ttu-id="cc938-131">Beachten Sie, dass ein Teil der SAS-URL im Feld **Anzeigename** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc938-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="cc938-132">Dieser wird als Anzeigename des Containers verwendet, der unter den **Speicherkonten** erstellt wurde, nachdem Sie eine Verbindung mit dem Speicherort hergestellt haben.</span><span class="sxs-lookup"><span data-stu-id="cc938-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="cc938-133">Dieser Name besteht aus der ID des Advanced eDiscovery-Falls und aus einem eindeutigen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="cc938-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="cc938-134">Sie können den standardmäßigen Anzeigenamen beibehalten oder ändern.</span><span class="sxs-lookup"><span data-stu-id="cc938-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="cc938-135">Wenn Sie ihn ändern, muss der Anzeigename eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="cc938-135">If you change it, the display name must be unique.</span></span>

5. <span data-ttu-id="cc938-136">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cc938-136">Click **Next**.</span></span>

    <span data-ttu-id="cc938-137">Die Seite **Verbindungszusammenfassung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc938-137">The **Connection summary** page is displayed.</span></span>

    ![Klicken Sie auf der Seite Verbindungszusammenfassung auf verbinden, um eine Verbindung mit dem Azure-Speicherort herzustellen.](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="cc938-139">Überprüfen Sie auf der Seite zusammen **Fassung der Verbindung** die Verbindungsinformationen, und klicken Sie dann auf **verbinden**.</span><span class="sxs-lookup"><span data-stu-id="cc938-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span>

    <span data-ttu-id="cc938-140">Der Knoten **BLOB-Container** (unter **Speicherkonten**  >  **(angefügte Container)** \> wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cc938-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Exportieren von Aufträgen im Knoten BLOBs-Container](../media/AzureStorageConnect5.png)

    <span data-ttu-id="cc938-142">Sie enthält einen Container namens mit dem Anzeigenamen aus Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="cc938-142">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="cc938-143">Dieser Container enthält einen Ordner für jeden exportierten Auftrag, den Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cc938-143">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="cc938-144">Diese Ordner werden mit einer ID benannt, die der ID des Exportauftrags entspricht.</span><span class="sxs-lookup"><span data-stu-id="cc938-144">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="cc938-145">Diese Export-IDs (und der Name des Exports) finden Sie unter **Support Informationen** auf der Flyout-Seite für jeden auf der Registerkarte **Aufträge** aufgeführten **Vorbereitungs Daten für den Export** Auftrag.</span><span class="sxs-lookup"><span data-stu-id="cc938-145">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="cc938-146">Doppelklicken Sie auf den Exportauftrags Ordner, um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cc938-146">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="cc938-147">Eine Liste von Ordnern und Export Berichten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc938-147">A list of folders and export reports is displayed.</span></span>
   
    ![Der Exportordner enthält exportierte Dateien und exportiert Berichte](../media/AzureStorageConnect6.png)

   <span data-ttu-id="cc938-149">Der Exportauftrags Ordner enthält die folgenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="cc938-149">The export job folder contains the following items.</span></span> <span data-ttu-id="cc938-150">Die tatsächlichen Elemente im Exportordner werden durch die Exportoptionen bestimmt, die beim Erstellen des Exportauftrags konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="cc938-150">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="cc938-151">Weitere Informationen finden Sie unter [Exportieren von Dokumenten aus einem Überprüfungs Satzes](export-documents-from-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="cc938-151">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="cc938-152">Export_load_file.csv: Diese CSV-Datei ist ein Detail Exportbericht mit Informationen zu den einzelnen exportierten Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="cc938-152">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="cc938-153">Die Datei besteht aus einer Spalte für jede Metadata-Eigenschaft für ein Dokument.</span><span class="sxs-lookup"><span data-stu-id="cc938-153">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="cc938-154">Eine Liste und eine Beschreibung der Metadaten, die in diesem Bericht enthalten sind, finden Sie in der Spalte **exportierter Feldname** in der Tabelle in [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="cc938-154">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
    
    - <span data-ttu-id="cc938-155">Summary.txt: eine Textdatei, die eine Zusammenfassung des Exports einschließlich Export Statistiken enthält.</span><span class="sxs-lookup"><span data-stu-id="cc938-155">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="cc938-156">Extracted_text_files: dieser Ordner enthält eine Text Dateiversion jedes exportierten Dokuments.</span><span class="sxs-lookup"><span data-stu-id="cc938-156">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="cc938-157">NativeFiles: dieser Ordner enthält eine systemeigene Dateiversion jedes exportierten Dokuments.</span><span class="sxs-lookup"><span data-stu-id="cc938-157">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="cc938-158">Error_files: dieser Ordner enthält die folgenden Elemente, wenn der Exportauftrag Fehler Dateien enthält:</span><span class="sxs-lookup"><span data-stu-id="cc938-158">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="cc938-159">ExtractionError.csv: Diese CSV-Datei enthält die verfügbaren Metadaten für Dateien, die nicht ordnungsgemäß aus dem übergeordneten Element extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cc938-159">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="cc938-160">ProcessingError: dieser Ordner enthält Dokumente mit Verarbeitungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="cc938-160">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="cc938-161">Dieser Inhalt befindet sich auf einer Elementebene, was bedeutet, dass bei einer Anlage ein Verarbeitungsfehler vorliegt, das Dokument, das die Anlage enthält, ebenfalls in diesem Ordner enthalten sein wird.</span><span class="sxs-lookup"><span data-stu-id="cc938-161">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="cc938-162">Wenn Sie alle Inhalte im Export exportieren möchten, wählen Sie den Exportordner aus, und klicken Sie dann auf **Herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="cc938-162">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="cc938-163">Geben Sie den Speicherort an, an den Sie die exportierten Dateien herunterladen möchten, und klicken Sie dann auf Ordner auswählen.</span><span class="sxs-lookup"><span data-stu-id="cc938-163">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="cc938-164">Der Azure Storage Explorer startet den Exportvorgang.</span><span class="sxs-lookup"><span data-stu-id="cc938-164">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="cc938-165">Der Status des Herunterladens der exportierten Elemente wird im Bereich " **Aktivitäten** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc938-165">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="cc938-166">Nach Abschluss des Downloads wird eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc938-166">A message is displayed when the download is finished.</span></span>

    ![Eine Meldung wird angezeigt, wenn der Download abgeschlossen ist.](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="cc938-168">Statt den gesamten Exportauftrag herunterzuladen, können Sie bestimmte Elemente zum Herunterladen auswählen.</span><span class="sxs-lookup"><span data-stu-id="cc938-168">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="cc938-169">Anstatt Elemente herunterzuladen, können Sie auch auf ein Element doppelklicken, um es anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc938-169">And instead of downloading items, you can double-click an item to view it.</span></span>
