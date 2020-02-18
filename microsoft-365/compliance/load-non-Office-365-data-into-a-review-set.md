---
title: Laden von Nicht-Office 365-Daten in einen Prüfdateisatz
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
description: Importieren Sie nicht Office 365 Daten in einen Überprüfungs in einem erweiterten eDiscovery-Fall.
ms.openlocfilehash: ae5effafd8a208d3c03ce40e03c9da2b0ea6b8d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072207"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="4b029-103">Laden von Nicht-Office 365-Daten in einen Prüfdateisatz</span><span class="sxs-lookup"><span data-stu-id="4b029-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="4b029-104">Nicht alle Dokumente, die Sie in Advanced eDiscovery analysieren müssen, befinden sich in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b029-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="4b029-105">Mit der nicht Office 365 datenimportfunktion in Advanced eDiscovery können Sie Dokumente, die sich nicht in Office 365 befinden, in einen Überprüfungs-Datensatz hochladen.</span><span class="sxs-lookup"><span data-stu-id="4b029-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="4b029-106">In diesem Artikel erfahren Sie, wie Sie Ihre nicht-Office 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.</span><span class="sxs-lookup"><span data-stu-id="4b029-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="4b029-107">Advanced eDiscovery erfordert ein Microsoft 365-oder Office 365 E5-Abonnement für Ihre Organisation oder ein E3-Abonnement mit dem Add-on-Abonnement für erweiterte Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="4b029-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="4b029-108">Wenn Sie diesen Plan nicht haben und Advanced eDiscovery testen möchten, können Sie sich für eine Testversion von Office 365 Enterprise E5 anmelden.</span><span class="sxs-lookup"><span data-stu-id="4b029-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4b029-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="4b029-109">Before you begin</span></span>

<span data-ttu-id="4b029-110">Bei Verwendung der in diesem Artikel beschriebenen Funktion "nicht Office 365 hochladen" müssen Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="4b029-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="4b029-111">Allen Betreuern, denen nicht Office 365 Inhalte zugeordnet werden sollen, muss eine E5-Lizenz oder eine E3-Lizenz mit einer Advanced Compliance-Add-on-Lizenz zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="4b029-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="4b029-112">Ein vorhandener erweiterter eDiscovery-Fall.</span><span class="sxs-lookup"><span data-stu-id="4b029-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="4b029-113">Verwalter müssen dem Fall hinzugefügt werden, bevor Sie Sie hochladen und den nicht Office 365-Daten zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="4b029-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="4b029-114">Nicht Office 365 Daten müssen einen Dateityp aufweisen, der von Advanced eDiscovery unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4b029-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="4b029-115">Weitere Informationen finden Sie unter [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="4b029-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="4b029-116">Alle Dateien, die in einen Überprüfungs Sätze hochgeladen werden, müssen sich in Ordnern befinden, in denen jeder Ordner einer bestimmten Depotbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4b029-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="4b029-117">Für die Namen dieser Ordner muss Folgendes Benennungsformat verwendet werden: *Alias@Domainname*.</span><span class="sxs-lookup"><span data-stu-id="4b029-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="4b029-118">Das Alias@Domainname muss der Office 365 Alias und die Domäne des Benutzers sein.</span><span class="sxs-lookup"><span data-stu-id="4b029-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="4b029-119">Sie können alle Alias@Domainname Ordner in einem Stammordner sammeln.</span><span class="sxs-lookup"><span data-stu-id="4b029-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="4b029-120">Der Stammordner kann nur die Alias@Domainname Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b029-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="4b029-121">Lose Dateien im Stammordner werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4b029-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="4b029-122">Die Ordnerstruktur für die nicht Office 365 Daten, die Sie hochladen möchten, würde dem folgenden Beispiel ähneln:</span><span class="sxs-lookup"><span data-stu-id="4b029-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="4b029-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b029-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="4b029-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b029-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="4b029-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b029-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="4b029-126">Dabei sind Abraham.McMahon@contoso.com, Jewell.Gordon@contoso.com und Staci.Gonzalez@contoso.com die SMTP-Adressen der Verwalter in dem Fall.</span><span class="sxs-lookup"><span data-stu-id="4b029-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Ordnerstruktur für nicht Office 365E Datenuploads](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="4b029-128">Ein Konto, das der Rollengruppe "eDiscovery-Manager" zugewiesen ist (und als eDiscovery-Administrator hinzugefügt wurde).</span><span class="sxs-lookup"><span data-stu-id="4b029-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="4b029-129">Das AzCopy v 8.1-Tool, das auf einem Computer installiert ist, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat.</span><span class="sxs-lookup"><span data-stu-id="4b029-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="4b029-130">Informationen zum Installieren von AzCopy finden Sie unter [übertragen von Daten mit der AzCopy v 8.1 unter Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="4b029-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="4b029-131">Stellen Sie sicher, dass Sie AzCopy im Standardspeicherort installieren, also **% Programme (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="4b029-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="4b029-132">Sie müssen AzCopy v 8.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b029-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="4b029-133">Andere Versionen von AzCopy funktionieren möglicherweise nicht, wenn nicht Office 365 Daten in Advanced eDiscovery geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4b029-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="4b029-134">Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4b029-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="4b029-135">Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, dann werden die nicht Office 365-Daten hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="4b029-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="4b029-136">Klicken Sie auf **Überprüfungs Sätze**, und wählen Sie dann den Überprüfungs Satz aus, an den die nicht Office 365 Daten hochgeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4b029-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="4b029-137">Wenn Sie keinen Überprüfungs Sätze haben, können Sie einen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b029-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="4b029-138">Klicken Sie in der Überprüfungsgruppe auf **Überarbeitungs Gruppe verwalten**, und klicken Sie dann auf der **Daten Kachel nicht Office 365** auf **Uploads anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="4b029-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="4b029-139">Klicken Sie auf **Dateien hochladen** , um den nicht Office 365 Datenimport-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="4b029-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="4b029-141">Im ersten Schritt des Assistenten wird ein sicherer von Microsoft bereitgestellter Azure-Speicherort für den Upload der Dateien vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="4b029-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="4b029-142">Wenn die Vorbereitung abgeschlossen ist, wird die Schaltfläche **Weiter: Dateien hochladen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4b029-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Nicht Office 365 Import: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="4b029-144">Klicken Sie auf **Weiter: Dateien hochladen**.</span><span class="sxs-lookup"><span data-stu-id="4b029-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="4b029-145">Führen Sie auf der Seite **Dateien hochladen** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4b029-145">On the **Upload files** page, do the following:</span></span>

   ![Nicht Office 365 Import: Hochladen von Dateien](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="4b029-147">a.</span><span class="sxs-lookup"><span data-stu-id="4b029-147">a.</span></span> <span data-ttu-id="4b029-148">Überprüfen Sie im Feld **Pfad zum Speicherort der Dateien** den Speicherort des Stammordners, in dem Sie die nicht Office 365 Daten, die Sie hochladen möchten, gespeichert haben, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="4b029-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="4b029-149">Wenn Sie beispielsweise den Speicherort der Beispieldateien im **Abschnitt bevor Sie beginnen**sehen möchten, geben Sie **%USERPROFILE\Downloads\nonO365**ein.</span><span class="sxs-lookup"><span data-stu-id="4b029-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="4b029-150">Durch Bereitstellen des richtigen Speicherorts wird sichergestellt, dass der im Feld unter dem Pfad angezeigte AzCopy-Befehl ordnungsgemäß aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4b029-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="4b029-151">b.</span><span class="sxs-lookup"><span data-stu-id="4b029-151">b.</span></span> <span data-ttu-id="4b029-152">Klicken Sie auf in **Zwischenablage kopieren** , um den Befehl zu kopieren, der in dem Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4b029-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="4b029-153">Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, den Sie im vorherigen Schritt kopiert haben, und drücken Sie dann die **EINGABETASTE** , um den AzCopy-Befehl zu starten.</span><span class="sxs-lookup"><span data-stu-id="4b029-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="4b029-154">Nachdem Sie den Befehl gestartet haben, werden die nicht Office 365 Dateien in den Azure-Speicherort hochgeladen, der in Schritt 4 vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="4b029-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Nicht Office 365 Import: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="4b029-156">Wie bereits erwähnt, müssen Sie AzCopy v 8.1 verwenden, um den Befehl, der auf der Seite **Dateien hochladen** bereitgestellt wird, erfolgreich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b029-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="4b029-157">Wenn der angegebene AzCopy-Befehl fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="4b029-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="4b029-158">Wechseln Sie zurück zum Security & Compliance Center, und klicken Sie auf **Weiter: Dateien** im Assistenten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4b029-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="4b029-159">Dadurch werden Verarbeitung, Textextraktion und Indizierung der nicht Office 365 Dateien initiiert, die in den Azure-Speicherort hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="4b029-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="4b029-160">Verfolgen Sie den Fortschritt der Verarbeitung nicht Office 365er Dateien auf der Seite **Prozessdateien** oder auf der Registerkarte **Aufträge** , indem Sie einen Auftrag mit dem Namen **Hinzufügen von nicht Office 365 Daten zu einem Überprüfungs Satzes**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b029-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="4b029-161">Nachdem der Auftrag abgeschlossen ist, sind die neuen Dateien in der Überprüfungsgruppe verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4b029-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![Nicht Office 365 Import: Verarbeiten von Dateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="4b029-163">Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.</span><span class="sxs-lookup"><span data-stu-id="4b029-163">After the processing is finished, you can close the wizard.</span></span>
