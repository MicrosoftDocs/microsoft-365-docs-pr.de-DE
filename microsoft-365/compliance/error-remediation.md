---
title: Fehlerkorrektur beim Verarbeiten von Daten für eine Untersuchung
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
description: ''
ms.openlocfilehash: 524378ecb7ec7cd8285e7d1ccda5667aa6081f30
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074428"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="c3bce-102">Fehlerkorrektur beim Verarbeiten von Daten für eine Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c3bce-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="c3bce-103">Durch die Fehlerkorrektur können Ermittler Daten Probleme beheben, die verhindern, dass Daten Untersuchungen (Preview) die Inhalte ordnungsgemäß verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c3bce-103">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="c3bce-104">Beispielsweise können Dateien, die kennwortgeschützt sind, nicht verarbeitet werden, da die Dateien gesperrt oder verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="c3bce-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="c3bce-105">Mithilfe der Fehlerkorrektur können Ermittler Dateien mit solchen Fehlern herunterladen, den Kennwortschutz entfernen und die korrigierten Dateien hochladen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-105">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="c3bce-106">Verwenden Sie den folgenden Workflow, um Dateien mit Fehlern in Daten Ermittlungs Fällen (Vorschau) zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c3bce-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="c3bce-107">Erstellen einer Fehlerbehebungssitzung zum Beheben von Dateien mit Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="c3bce-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="c3bce-108">Wenn der Fehlerkorrektur-Assistent während des folgenden Verfahrens zu einem beliebigen Zeitpunkt geschlossen wird, können Sie auf der Registerkarte **Verarbeitung** zur Fehlerbehebungssitzung zurückkehren, indem Sie im Dropdownmenü **Ansicht** die Option **Fehler** Korrekturen auswählen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="c3bce-109">Wählen Sie auf der Registerkarte **Verarbeitung** in einer Datenermittlung im Dropdownmenü **Ansicht** die Option **Fehler** aus.</span><span class="sxs-lookup"><span data-stu-id="c3bce-109">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="c3bce-110">Wählen Sie die Fehler aus, die Sie korrigieren möchten, indem Sie auf das Optionsfeld neben dem Fehlertyp oder-Dateityp klicken.</span><span class="sxs-lookup"><span data-stu-id="c3bce-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="c3bce-111">Im folgenden Beispiel werden wir eine kennwortgeschützte Datei remediationieren.</span><span class="sxs-lookup"><span data-stu-id="c3bce-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="c3bce-112">Klicken Sie auf **+ neue Fehlerkorrektur**.</span><span class="sxs-lookup"><span data-stu-id="c3bce-112">Click **+ New error remediation**.</span></span>

    ![Fehlerbehebung](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="c3bce-114">Die Fehlerbehebungssitzung beginnt, beginnend mit einer Vorbereitungsphase, in der die Dateien mit Fehlern an einen sicheren Azure-Speicherort kopiert werden, damit Sie heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="c3bce-114">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![Vorbereiten der Fehlerbehebung](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="c3bce-116">Nachdem die Vorbereitung abgeschlossen ist, klicken Sie auf **Weiter: Dateien herunterladen** , um den Download fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Herunterladen von Dateien](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="c3bce-118">Geben Sie zum Herunterladen von Dateien den **Ziel Pfad für den Download**an.</span><span class="sxs-lookup"><span data-stu-id="c3bce-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="c3bce-119">Dies ist ein Pfad auf dem lokalen Computer, auf dem die Datei heruntergeladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3bce-119">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="c3bce-120">Der Standardpfad,%USERPROFILE%\Downloads\errors, verweist auf den Ordner "Downloads" des angemeldeten Benutzers; Dies kann bei Bedarf geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c3bce-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="c3bce-121">Es wird empfohlen, einen lokalen Dateipfad anstelle eines Remotenetzwerk Pfads zu verwenden, um eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-121">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3bce-122">Wenn Sie AzCopy nicht installiert haben, können Sie es von hier aus installieren:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="c3bce-122">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="c3bce-123">Kopieren Sie den vordefinierten Befehl **, indem Sie auf in Zwischenablage kopieren**klicken.</span><span class="sxs-lookup"><span data-stu-id="c3bce-123">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="c3bce-124">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="c3bce-124">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="c3bce-125">Die Dateien werden heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-125">The files will be downloaded.</span></span>

    ![Vorbereiten der Fehlerbehebung](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="c3bce-127">Wenn beim Ausführen dieses Befehls Probleme auftreten, lesen Sie [Troubleshooting AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="c3bce-127">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="c3bce-128">Nachdem Sie die Dateien heruntergeladen haben, können Sie Sie mit einem geeigneten Tool korrigieren.</span><span class="sxs-lookup"><span data-stu-id="c3bce-128">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="c3bce-129">Für kennwortgeschützte Dateien gibt es mehrere Kenn Wort Knack Tools, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c3bce-129">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="c3bce-130">Wenn Sie die Kennwörter für die Dateien kennen, können Sie Sie öffnen und den Kennwortschutz entfernen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-130">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="c3bce-131">Es ist wichtig, dass Sie die Verzeichnisstruktur und die Dateinamen der korrigierten Dateien beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c3bce-131">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="c3bce-132">Die Pfadnamen der heruntergeladenen Dateien und Ordner ermöglichen das Zuordnen der korrigierten Dateien zu den Originaldateien.</span><span class="sxs-lookup"><span data-stu-id="c3bce-132">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="c3bce-133">Wenn die Verzeichnisstruktur oder die Dateinamen geändert werden, erhalten Sie den folgenden Fehler: `Cannot apply Error Remediation to the current Evidenceset`.</span><span class="sxs-lookup"><span data-stu-id="c3bce-133">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="c3bce-134">Kehren Sie nun zu Daten Untersuchungen (Vorschau) zurück, und klicken Sie auf **Weiter: Dateien hochladen**.</span><span class="sxs-lookup"><span data-stu-id="c3bce-134">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="c3bce-135">Dadurch gelangen Sie zum nächsten Schritt, in dem Sie die Dateien jetzt hochladen können.</span><span class="sxs-lookup"><span data-stu-id="c3bce-135">This will move to the next step where you can now upload the files.</span></span>

    ![Hochladen von Dateien](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="c3bce-137">Geben Sie den Speicherort der korrigierten Dateien in das Textfeld **Pfad zum Speicherort der Dateien** ein, und klicken Sie dann auf **in Zwischenablage kopieren**.</span><span class="sxs-lookup"><span data-stu-id="c3bce-137">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="c3bce-138">Fügen Sie den Befehl in eine Windows-Eingabeaufforderung ein, und drücken **Sie die EINGABETASTE** , um die Dateien hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-138">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="c3bce-140">Kehren Sie schließlich zu Daten Untersuchungen (Vorschau) zurück, und klicken Sie auf **Weiter: Process files**.</span><span class="sxs-lookup"><span data-stu-id="c3bce-140">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="c3bce-141">Nach Abschluss der Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="c3bce-141">When processing is complete.</span></span>  <span data-ttu-id="c3bce-142">Sie können zum Arbeitsmappe zurückkehren und die korrigierte Datei anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3bce-142">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="c3bce-143">Was geschieht, wenn Dateien behoben werden</span><span class="sxs-lookup"><span data-stu-id="c3bce-143">What happens when files are remediated</span></span>

<span data-ttu-id="c3bce-144">Bei hochzuladenden Dateien werden die ursprünglichen Metadaten mit Ausnahme der folgenden Felder beibehalten:</span><span class="sxs-lookup"><span data-stu-id="c3bce-144">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="c3bce-145">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="c3bce-145">ExtractedTextSize</span></span>
- <span data-ttu-id="c3bce-146">HasText</span><span class="sxs-lookup"><span data-stu-id="c3bce-146">HasText</span></span>
- <span data-ttu-id="c3bce-147">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="c3bce-147">IsErrorRemediate</span></span>
- <span data-ttu-id="c3bce-148">Lade-Nr</span><span class="sxs-lookup"><span data-stu-id="c3bce-148">LoadId</span></span>
- <span data-ttu-id="c3bce-149">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="c3bce-149">ProcessingErrorMessage</span></span>
- <span data-ttu-id="c3bce-150">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="c3bce-150">ProcessingStatus</span></span>
- <span data-ttu-id="c3bce-151">Text</span><span class="sxs-lookup"><span data-stu-id="c3bce-151">Text</span></span>
- <span data-ttu-id="c3bce-152">WordCount</span><span class="sxs-lookup"><span data-stu-id="c3bce-152">WordCount</span></span>
- <span data-ttu-id="c3bce-153">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="c3bce-153">WorkingsetId</span></span>

<span data-ttu-id="c3bce-154">Eine Definition aller Document Metadata fields in Data Investigations (Preview) finden Sie unter [Document Metadata fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="c3bce-154">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
