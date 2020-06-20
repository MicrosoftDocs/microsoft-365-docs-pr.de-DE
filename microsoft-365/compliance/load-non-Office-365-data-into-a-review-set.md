---
title: Laden von nicht von Microsoft 365 Daten in einen Überprüfungs-Datensatz
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
description: In diesem Artikel erfahren Sie, wie Sie nicht von Microsoft 365 Daten in einen Überprüfungs für die Analyse in einem erweiterten eDiscovery-Fall importieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9b506edc55da1916ae908eaa7ca619ba7300f87
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815462"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="24c2a-103">Laden von nicht von Microsoft 365 Daten in einen Überprüfungs-Datensatz</span><span class="sxs-lookup"><span data-stu-id="24c2a-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="24c2a-104">Nicht alle Dokumente, die Sie in Advanced eDiscovery analysieren müssen, befinden sich in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24c2a-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="24c2a-105">Mit der nicht-Microsoft 365-datenimportfunktion in Advanced eDiscovery können Sie Dokumente, die sich nicht in Microsoft 365 befinden, in einen Überprüfungs-Datensatz hochladen.</span><span class="sxs-lookup"><span data-stu-id="24c2a-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="24c2a-106">In diesem Artikel erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente in Advanced eDiscovery for Analysis integrieren.</span><span class="sxs-lookup"><span data-stu-id="24c2a-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="24c2a-107">Anforderungen zum Hochladen nicht Office 365der Inhalte</span><span class="sxs-lookup"><span data-stu-id="24c2a-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="24c2a-108">Bei Verwendung des in diesem Artikel beschriebenen Features zum Hochladen nicht von Microsoft 365 ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="24c2a-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="24c2a-109">Allen Betreuern, denen kein Inhalt von Microsoft 365 zugeordnet werden soll, muss die entsprechende Lizenz zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="24c2a-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="24c2a-110">Weitere Informationen finden Sie unter [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="24c2a-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="24c2a-111">Ein vorhandener erweiterter eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="24c2a-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="24c2a-112">Verwalter müssen dem Fall hinzugefügt werden, bevor Sie Sie hochladen und den nicht von Microsoft 365 Daten zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="24c2a-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="24c2a-113">Nicht-Microsoft 365-Daten müssen einen Dateityp aufweisen, der von Advanced eDiscovery unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="24c2a-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="24c2a-114">Weitere Informationen finden Sie unter [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="24c2a-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="24c2a-115">Alle Dateien, die in einen Überprüfungs Sätze hochgeladen werden, müssen sich in Ordnern befinden, in denen jeder Ordner einer bestimmten Depotbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="24c2a-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="24c2a-116">Für die Namen dieser Ordner muss Folgendes Benennungsformat verwendet werden: *Alias@Domainname*.</span><span class="sxs-lookup"><span data-stu-id="24c2a-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="24c2a-117">Das Alias@Domainname muss der Microsoft 365-Alias und die Domäne des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="24c2a-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="24c2a-118">Sie können alle Alias@Domainname Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="24c2a-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="24c2a-119">Der Stammordner kann nur die Alias@Domainname Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="24c2a-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="24c2a-120">Lose Dateien im Stammordner werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24c2a-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="24c2a-121">Die Ordnerstruktur für die Daten, die nicht von Microsoft 365 hochgeladen werden sollen, würde dem folgenden Beispiel ähneln:</span><span class="sxs-lookup"><span data-stu-id="24c2a-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="24c2a-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="24c2a-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="24c2a-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="24c2a-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="24c2a-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="24c2a-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="24c2a-125">Dabei sind Abraham.McMahon@contoso.com, Jewell.Gordon@contoso.com und Staci.Gonzalez@contoso.com die SMTP-Adressen der Verwalter in dem Fall.</span><span class="sxs-lookup"><span data-stu-id="24c2a-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Ordnerstruktur eines nicht von Microsoft 365 Datenuploads](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="24c2a-127">Ein Konto, das der Rollengruppe "eDiscovery-Manager" zugewiesen ist (und als eDiscovery-Administrator hinzugefügt wurde).</span><span class="sxs-lookup"><span data-stu-id="24c2a-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="24c2a-128">Das AzCopy v 8.1-Tool, das auf einem Computer installiert ist, der Zugriff auf die Inhaltsordner Struktur nicht von Microsoft 365 hat.</span><span class="sxs-lookup"><span data-stu-id="24c2a-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="24c2a-129">Informationen zum Installieren von AzCopy finden Sie unter [übertragen von Daten mit der AzCopy v 8.1 unter Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="24c2a-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="24c2a-130">Stellen Sie sicher, dass Sie AzCopy im Standardspeicherort installieren, also **% Programme (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="24c2a-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="24c2a-131">Sie müssen AzCopy v 8.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="24c2a-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="24c2a-132">Andere Versionen von AzCopy funktionieren möglicherweise nicht, wenn nicht-Microsoft 365-Daten in Advanced eDiscovery geladen werden.</span><span class="sxs-lookup"><span data-stu-id="24c2a-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="24c2a-133">Hochladen von nicht-Microsoft 365-Inhalten in Erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="24c2a-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="24c2a-134">Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, und wechseln Sie zu dem Fall, in den die Daten nicht von Microsoft 365 hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="24c2a-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="24c2a-135">Klicken Sie auf **Überprüfungs Sätze**, und wählen Sie dann den Überprüfungs Satz aus, um die nicht von Microsoft 365 Daten hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="24c2a-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="24c2a-136">Wenn Sie keinen Überprüfungs Sätze haben, können Sie einen erstellen.</span><span class="sxs-lookup"><span data-stu-id="24c2a-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="24c2a-137">Klicken Sie in der Überprüfungsgruppe auf **Überarbeitungs Gruppe verwalten**, und klicken Sie dann auf der **Daten Kachel nicht von Microsoft 365** auf **Uploads anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="24c2a-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="24c2a-138">Klicken Sie auf **Dateien hochladen** , um den Datenimport-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="24c2a-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="24c2a-140">Im ersten Schritt des Assistenten wird ein sicherer von Microsoft bereitgestellter Azure-Speicherort für den Upload der Dateien vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="24c2a-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="24c2a-141">Wenn die Vorbereitung abgeschlossen ist, wird die Schaltfläche **Weiter: Dateien hochladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="24c2a-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Nicht-Microsoft-365-Import: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="24c2a-143">Klicken Sie auf **Weiter: Dateien hochladen**.</span><span class="sxs-lookup"><span data-stu-id="24c2a-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="24c2a-144">Führen Sie auf der Seite **Dateien hochladen** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24c2a-144">On the **Upload files** page, do the following:</span></span>

   ![Nicht-Microsoft 365 Import: Hochladen von Dateien](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="24c2a-146">a.</span><span class="sxs-lookup"><span data-stu-id="24c2a-146">a.</span></span> <span data-ttu-id="24c2a-147">Überprüfen Sie im Feld **Pfad zum Speicherort der Dateien** , oder geben Sie den Speicherort des Stammordners ein, in dem Sie die nicht von Microsoft 365 Daten gespeichert haben, die Sie hochladen möchten.</span><span class="sxs-lookup"><span data-stu-id="24c2a-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="24c2a-148">Wenn Sie beispielsweise den Speicherort der Beispieldateien im **Abschnitt bevor Sie beginnen**sehen möchten, geben Sie **%USERPROFILE\Downloads\nonO365**ein.</span><span class="sxs-lookup"><span data-stu-id="24c2a-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="24c2a-149">Durch Bereitstellen des richtigen Speicherorts wird sichergestellt, dass der im Feld unter dem Pfad angezeigte AzCopy-Befehl ordnungsgemäß aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="24c2a-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="24c2a-150">b.</span><span class="sxs-lookup"><span data-stu-id="24c2a-150">b.</span></span> <span data-ttu-id="24c2a-151">Klicken Sie auf in **Zwischenablage kopieren** , um den Befehl zu kopieren, der in dem Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="24c2a-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="24c2a-152">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, den Sie im vorherigen Schritt kopiert haben, und drücken Sie dann die **EINGABETASTE** , um den AzCopy-Befehl zu starten.</span><span class="sxs-lookup"><span data-stu-id="24c2a-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="24c2a-153">Nachdem Sie den Befehl gestartet haben, werden die nicht von Microsoft 365 Dateien an den Azure-Speicherort hochgeladen, der in Schritt 4 vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="24c2a-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Nicht-Microsoft 365 Import: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="24c2a-155">Wie bereits erwähnt, müssen Sie AzCopy v 8.1 verwenden, um den Befehl, der auf der Seite **Dateien hochladen** bereitgestellt wird, erfolgreich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="24c2a-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="24c2a-156">Wenn der angegebene AzCopy-Befehl fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="24c2a-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="24c2a-157">Wechseln Sie zurück zum Security & Compliance Center, und klicken Sie auf **Weiter: Dateien** im Assistenten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="24c2a-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="24c2a-158">Dadurch werden Verarbeitung, Textextraktion und Indizierung der nicht von Microsoft 365 Dateien initiiert, die in den Azure-Speicherort hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="24c2a-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="24c2a-159">Verfolgen Sie den Fortschritt der Verarbeitung der Dateien auf der Seite " **Prozessdateien** " oder auf der Registerkarte " **Aufträge** ", indem Sie einen Auftrag mit dem Namen **Hinzufügen von nicht-Microsoft 365-Daten zu einem Überprüfungs Satzes**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="24c2a-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="24c2a-160">Nachdem der Auftrag abgeschlossen ist, sind die neuen Dateien in der Überprüfungsgruppe verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24c2a-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Nicht-Microsoft 365-Import: Verarbeiten von Dateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="24c2a-162">Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.</span><span class="sxs-lookup"><span data-stu-id="24c2a-162">After the processing is finished, you can close the wizard.</span></span>
