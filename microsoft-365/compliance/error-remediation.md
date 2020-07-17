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
description: In diesem Artikel erfahren Sie, wie Sie mithilfe der Fehlerbehebung Daten Probleme in Daten Untersuchungen (Preview) korrigieren können, die eine ordnungsgemäße Verarbeitung von Inhalten verhindern könnten.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: fe77f918a7471bf36df7727f890ea043976e44db
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817814"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="2c691-103">Fehlerkorrektur beim Verarbeiten von Daten für eine Untersuchung</span><span class="sxs-lookup"><span data-stu-id="2c691-103">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="2c691-104">Durch die Fehlerkorrektur können Ermittler Daten Probleme beheben, die verhindern, dass Daten Untersuchungen (Preview) die Inhalte ordnungsgemäß verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2c691-104">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="2c691-105">Beispielsweise können Dateien, die kennwortgeschützt sind, nicht verarbeitet werden, da die Dateien gesperrt oder verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="2c691-105">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="2c691-106">Mithilfe der Fehlerkorrektur können Ermittler Dateien mit solchen Fehlern herunterladen, den Kennwortschutz entfernen und die korrigierten Dateien hochladen.</span><span class="sxs-lookup"><span data-stu-id="2c691-106">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="2c691-107">Verwenden Sie den folgenden Workflow, um Dateien mit Fehlern in Daten Ermittlungs Fällen (Vorschau) zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2c691-107">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="2c691-108">Erstellen einer Fehlerbehebungssitzung zum Beheben von Dateien mit Verarbeitungsfehlern</span><span class="sxs-lookup"><span data-stu-id="2c691-108">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="2c691-109">Wenn der Fehlerkorrektur-Assistent während des folgenden Verfahrens zu einem beliebigen Zeitpunkt geschlossen wird, können Sie auf der Registerkarte **Verarbeitung** zur Fehlerbehebungssitzung zurückkehren, indem Sie im Dropdownmenü **Ansicht** die Option **Fehler** Korrekturen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2c691-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="2c691-110">Wählen Sie auf der Registerkarte **Verarbeitung** in einer Datenermittlung im Dropdownmenü **Ansicht** die Option **Fehler** aus.</span><span class="sxs-lookup"><span data-stu-id="2c691-110">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="2c691-111">Wählen Sie die Fehler aus, die Sie korrigieren möchten, indem Sie auf das Optionsfeld neben dem Fehlertyp oder-Dateityp klicken.</span><span class="sxs-lookup"><span data-stu-id="2c691-111">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="2c691-112">Im folgenden Beispiel werden wir eine kennwortgeschützte Datei remediationieren.</span><span class="sxs-lookup"><span data-stu-id="2c691-112">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="2c691-113">Klicken Sie auf **+ neue Fehlerkorrektur**.</span><span class="sxs-lookup"><span data-stu-id="2c691-113">Click **+ New error remediation**.</span></span>

    ![Fehlerbehebung](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="2c691-115">Die Fehlerbehebungssitzung beginnt, beginnend mit einer Vorbereitungsphase, in der die Dateien mit Fehlern an einen sicheren Azure-Speicherort kopiert werden, damit Sie heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="2c691-115">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![Vorbereiten der Fehlerbehebung](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="2c691-117">Nachdem die Vorbereitung abgeschlossen ist, klicken Sie auf **Weiter: Dateien herunterladen** , um den Download fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2c691-117">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Herunterladen von Dateien](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="2c691-119">Geben Sie zum Herunterladen von Dateien den **Ziel Pfad für den Download**an.</span><span class="sxs-lookup"><span data-stu-id="2c691-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="2c691-120">Dies ist ein Pfad auf dem lokalen Computer, auf dem die Datei heruntergeladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c691-120">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="2c691-121">Der Standardpfad,%USERPROFILE%\Downloads\errors, verweist auf den Ordner "Downloads" des angemeldeten Benutzers; Dies kann bei Bedarf geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2c691-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="2c691-122">Es wird empfohlen, einen lokalen Dateipfad anstelle eines Remotenetzwerk Pfads zu verwenden, um eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="2c691-122">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2c691-123">Wenn Sie AzCopy nicht installiert haben, gehen Sie zu [Erste Schritte mit AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) , um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2c691-123">If you haven't installed AzCopy, go to [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) to install it.</span></span>

6. <span data-ttu-id="2c691-124">Kopieren Sie den vordefinierten Befehl **, indem Sie auf in Zwischenablage kopieren**klicken.</span><span class="sxs-lookup"><span data-stu-id="2c691-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="2c691-125">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="2c691-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="2c691-126">Die Dateien werden heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="2c691-126">The files will be downloaded.</span></span>

    ![Vorbereiten der Fehlerbehebung](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="2c691-128">Wenn beim Ausführen dieses Befehls Probleme auftreten, lesen Sie [Troubleshooting AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="2c691-128">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="2c691-129">Nachdem Sie die Dateien heruntergeladen haben, können Sie Sie mit einem geeigneten Tool korrigieren.</span><span class="sxs-lookup"><span data-stu-id="2c691-129">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="2c691-130">Für kennwortgeschützte Dateien gibt es mehrere Kenn Wort Knack Tools, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c691-130">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="2c691-131">Wenn Sie die Kennwörter für die Dateien kennen, können Sie Sie öffnen und den Kennwortschutz entfernen.</span><span class="sxs-lookup"><span data-stu-id="2c691-131">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="2c691-132">Es ist wichtig, dass Sie die Verzeichnisstruktur und die Dateinamen der korrigierten Dateien beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2c691-132">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="2c691-133">Die Pfadnamen der heruntergeladenen Dateien und Ordner ermöglichen das Zuordnen der korrigierten Dateien zu den Originaldateien.</span><span class="sxs-lookup"><span data-stu-id="2c691-133">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="2c691-134">Wenn die Verzeichnisstruktur oder die Dateinamen geändert werden, erhalten Sie den folgenden Fehler: `Cannot apply Error Remediation to the current Evidenceset` .</span><span class="sxs-lookup"><span data-stu-id="2c691-134">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="2c691-135">Kehren Sie nun zu Daten Untersuchungen (Vorschau) zurück, und klicken Sie auf **Weiter: Dateien hochladen**.</span><span class="sxs-lookup"><span data-stu-id="2c691-135">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="2c691-136">Dadurch gelangen Sie zum nächsten Schritt, in dem Sie die Dateien jetzt hochladen können.</span><span class="sxs-lookup"><span data-stu-id="2c691-136">This will move to the next step where you can now upload the files.</span></span>

    ![Hochladen von Dateien](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="2c691-138">Geben Sie den Speicherort der korrigierten Dateien in das Textfeld **Pfad zum Speicherort der Dateien** ein, und klicken Sie dann auf **in Zwischenablage kopieren**.</span><span class="sxs-lookup"><span data-stu-id="2c691-138">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="2c691-139">Fügen Sie den Befehl in eine Windows-Eingabeaufforderung ein, und drücken **Sie die EINGABETASTE** , um die Dateien hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="2c691-139">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="2c691-141">Kehren Sie schließlich zu Daten Untersuchungen (Vorschau) zurück, und klicken Sie auf **Weiter: Process files**.</span><span class="sxs-lookup"><span data-stu-id="2c691-141">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="2c691-142">Nach Abschluss der Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="2c691-142">When processing is complete.</span></span>  <span data-ttu-id="2c691-143">Sie können zum Arbeitsmappe zurückkehren und die korrigierte Datei anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2c691-143">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="2c691-144">Was geschieht, wenn Dateien behoben werden</span><span class="sxs-lookup"><span data-stu-id="2c691-144">What happens when files are remediated</span></span>

<span data-ttu-id="2c691-145">Bei hochzuladenden Dateien werden die ursprünglichen Metadaten mit Ausnahme der folgenden Felder beibehalten:</span><span class="sxs-lookup"><span data-stu-id="2c691-145">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="2c691-146">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="2c691-146">ExtractedTextSize</span></span>
- <span data-ttu-id="2c691-147">HasText</span><span class="sxs-lookup"><span data-stu-id="2c691-147">HasText</span></span>
- <span data-ttu-id="2c691-148">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="2c691-148">IsErrorRemediate</span></span>
- <span data-ttu-id="2c691-149">Lade-Nr</span><span class="sxs-lookup"><span data-stu-id="2c691-149">LoadId</span></span>
- <span data-ttu-id="2c691-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="2c691-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="2c691-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="2c691-151">ProcessingStatus</span></span>
- <span data-ttu-id="2c691-152">Text</span><span class="sxs-lookup"><span data-stu-id="2c691-152">Text</span></span>
- <span data-ttu-id="2c691-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="2c691-153">WordCount</span></span>
- <span data-ttu-id="2c691-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="2c691-154">WorkingsetId</span></span>

<span data-ttu-id="2c691-155">Eine Definition aller Document Metadata fields in Data Investigations (Preview) finden Sie unter [Document Metadata fields](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="2c691-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
