---
title: Laden von nicht von Microsoft 365 stammenden Daten in einen Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In diesem Artikel erfahren Sie, wie Sie nicht von Microsoft 365 Daten in einen Überprüfungs für die Analyse in einem erweiterten eDiscovery-Fall importieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285861"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="9686e-103">Laden von nicht von Microsoft 365 stammenden Daten in einen Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="9686e-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="9686e-104">Nicht alle Dokumente, die Sie in Advanced eDiscovery analysieren müssen, befinden sich in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9686e-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="9686e-105">Mit dem Microsoft 365-Datenimport-Feature in Advanced eDiscovery können Sie Dokumente, die sich nicht in Microsoft 365 befinden, in einen Prüfdateisatz hochladen.</span><span class="sxs-lookup"><span data-stu-id="9686e-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="9686e-106">In diesem Artikel erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente in Advanced eDiscovery for Analysis integrieren.</span><span class="sxs-lookup"><span data-stu-id="9686e-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="9686e-107">Anforderungen zum Hochladen nicht Office 365der Inhalte</span><span class="sxs-lookup"><span data-stu-id="9686e-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="9686e-108">Bei Verwendung des in diesem Artikel beschriebenen Features zum Hochladen nicht von Microsoft 365 ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="9686e-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="9686e-109">Allen Betreuern, denen kein Inhalt von Microsoft 365 zugeordnet werden soll, muss die entsprechende Lizenz zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="9686e-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="9686e-110">Weitere Informationen finden Sie unter [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="9686e-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="9686e-111">Ein vorhandener erweiterter eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="9686e-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="9686e-112">Verwalter müssen dem Fall hinzugefügt werden, bevor Sie Sie hochladen und den nicht von Microsoft 365 Daten zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="9686e-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="9686e-113">Nicht von Microsoft 365 stammende Daten müssen einen Dateityp aufweisen, der von Advanced eDiscovery unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9686e-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="9686e-114">Weitere Informationen finden Sie unter [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="9686e-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="9686e-115">Alle Dateien, die in einen Prüfdateisatz hochgeladen werden, müssen sich in Ordnern befinden, wobei jeder Ordner einem bestimmten Verwahrer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9686e-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="9686e-116">Für die Namen dieser Ordner muss das folgende Namensformat verwendet werden: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="9686e-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="9686e-117">Bei „alias@domainname“ muss es sich um den Microsoft 365-Alias und die Domäne des Benutzers handeln.</span><span class="sxs-lookup"><span data-stu-id="9686e-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="9686e-118">Sie können alle Alias@Domainname Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="9686e-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="9686e-119">Der Stammordner kann nur die Alias@Domainname Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="9686e-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="9686e-120">Lose Dateien im Stammordner werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9686e-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="9686e-121">Die Ordnerstruktur für die Daten, die nicht von Microsoft 365 hochgeladen werden sollen, würde dem folgenden Beispiel ähneln:</span><span class="sxs-lookup"><span data-stu-id="9686e-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="9686e-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9686e-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="9686e-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9686e-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="9686e-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9686e-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="9686e-125">Dabei sind Abraham.McMahon@contoso.com, Jewell.Gordon@contoso.com und Staci.Gonzalez@contoso.com die SMTP-Adressen der Verwalter in dem Fall.</span><span class="sxs-lookup"><span data-stu-id="9686e-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Ordnerstruktur eines nicht von Microsoft 365 Datenuploads](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="9686e-127">Ein Konto, das der Rollengruppe "eDiscovery-Manager" zugewiesen ist (und als eDiscovery-Administrator hinzugefügt wurde).</span><span class="sxs-lookup"><span data-stu-id="9686e-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="9686e-128">Das AzCopy v 8.1-Tool, das auf einem Computer installiert ist, der Zugriff auf die Inhaltsordner Struktur nicht von Microsoft 365 hat.</span><span class="sxs-lookup"><span data-stu-id="9686e-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="9686e-129">Informationen zum Installieren von AzCopy finden Sie unter [übertragen von Daten mit der AzCopy v 8.1 unter Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="9686e-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="9686e-130">Stellen Sie sicher, dass Sie AzCopy im Standardspeicherort installieren, also **% Programme (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="9686e-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="9686e-131">Sie müssen AzCopy v 8.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="9686e-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="9686e-132">Andere Versionen von AzCopy funktionieren möglicherweise nicht, wenn nicht-Microsoft 365-Daten in Advanced eDiscovery geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9686e-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="9686e-133">Hochladen von nicht-Microsoft 365-Inhalten in Erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9686e-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="9686e-134">Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, und wechseln Sie zu dem Fall, in den die Daten nicht von Microsoft 365 hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9686e-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="9686e-135">Klicken Sie auf **Überprüfungs Sätze**, und wählen Sie dann den Überprüfungs Satz aus, um die nicht von Microsoft 365 Daten hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="9686e-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="9686e-136">Wenn Sie keinen Überprüfungs Sätze haben, können Sie einen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9686e-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="9686e-137">Klicken Sie im Prüfdateisatz auf **Prüfdateisatz verwalten**, und klicken Sie dann auf der Kachel **Nicht von Microsoft 365 stammende Daten** auf **Uploads anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9686e-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="9686e-138">Klicken Sie auf **Dateien hochladen**, um den Datenimport-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="9686e-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="9686e-140">Der erste Schritt im Assistenten bereitet einen von Microsoft bereitgestellten sicheren Azure-Speicherort vor, in den die Dateien hochgeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9686e-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="9686e-141">Wenn die Vorbereitung abgeschlossen ist, wird die Schaltfläche **Weiter: Dateien hochladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9686e-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Nicht-Microsoft-365-Import: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="9686e-143">Klicken Sie auf **Weiter: Dateien hochladen**.</span><span class="sxs-lookup"><span data-stu-id="9686e-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="9686e-144">Führen Sie auf der Seite **Dateien hochladen** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9686e-144">On the **Upload files** page, do the following:</span></span>

   ![Nicht-Microsoft 365 Import: Hochladen von Dateien](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="9686e-146">a.</span><span class="sxs-lookup"><span data-stu-id="9686e-146">a.</span></span> <span data-ttu-id="9686e-147">Überprüfen Sie im Feld **Pfad zum Speicherort der Dateien** , oder geben Sie den Speicherort des Stammordners ein, in dem Sie die nicht von Microsoft 365 Daten gespeichert haben, die Sie hochladen möchten.</span><span class="sxs-lookup"><span data-stu-id="9686e-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="9686e-148">Wenn Sie beispielsweise den Speicherort der Beispieldateien im **Abschnitt bevor Sie beginnen**sehen möchten, geben Sie **%USERPROFILE\Downloads\nonO365**ein.</span><span class="sxs-lookup"><span data-stu-id="9686e-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="9686e-149">Durch Bereitstellen des richtigen Speicherorts wird sichergestellt, dass der im Feld unter dem Pfad angezeigte AzCopy-Befehl ordnungsgemäß aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9686e-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="9686e-150">b.</span><span class="sxs-lookup"><span data-stu-id="9686e-150">b.</span></span> <span data-ttu-id="9686e-151">Klicken Sie auf in **Zwischenablage kopieren** , um den Befehl zu kopieren, der in dem Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9686e-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="9686e-152">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, den Sie im vorherigen Schritt kopiert haben, und drücken Sie dann die **EINGABETASTE** , um den AzCopy-Befehl zu starten.</span><span class="sxs-lookup"><span data-stu-id="9686e-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="9686e-153">Nachdem Sie den Befehl gestartet haben, werden die nicht von Microsoft 365 Dateien an den Azure-Speicherort hochgeladen, der in Schritt 4 vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="9686e-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Nicht-Microsoft 365 Import: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="9686e-155">Wie bereits erwähnt, müssen Sie AzCopy v 8.1 verwenden, um den Befehl, der auf der Seite **Dateien hochladen** bereitgestellt wird, erfolgreich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9686e-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="9686e-156">Wenn der angegebene AzCopy-Befehl fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="9686e-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="9686e-157">Wechseln Sie zurück zum Security & Compliance Center, und klicken Sie auf **Weiter: Dateien** im Assistenten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9686e-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="9686e-158">Die Verarbeitung, Textextraktion und Indizierung der nicht von Microsoft 365 stammenden Dateien, die in den Azure-Speicherort hochgeladen wurden, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="9686e-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="9686e-159">Verfolgen Sie den Fortschritt der Verarbeitung der Dateien auf der Seite " **Prozessdateien** " oder auf der Registerkarte " **Aufträge** ", indem Sie einen Auftrag mit dem Namen **Hinzufügen von nicht-Microsoft 365-Daten zu einem Überprüfungs Satzes**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9686e-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="9686e-160">Nachdem der Auftrag abgeschlossen ist, sind die neuen Dateien in der Überprüfungsgruppe verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9686e-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Nicht-Microsoft 365-Import: Verarbeiten von Dateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="9686e-162">Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.</span><span class="sxs-lookup"><span data-stu-id="9686e-162">After the processing is finished, you can close the wizard.</span></span>
