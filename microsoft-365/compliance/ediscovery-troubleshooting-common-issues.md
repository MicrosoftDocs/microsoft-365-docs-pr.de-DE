---
title: Behandeln allgemeiner eDiscovery-Probleme
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie mehr über grundlegende Schritte zur Problembehandlung, die Sie ausführen können, um allgemeine Probleme in Office 365 eDiscovery zu beheben.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26ca41774e1e09619fdf5e518258f8acf3a9d938
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809119"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="bf0b0-103">Untersuchen, Beheben und Beheben allgemeiner eDiscovery-Probleme</span><span class="sxs-lookup"><span data-stu-id="bf0b0-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="bf0b0-104">In diesem Thema werden grundlegende Schritte zur Problembehandlung behandelt, die Sie ausführen können, um Probleme zu identifizieren und zu beheben, die während einer eDiscovery-Suche oder an anderer Stelle im eDiscovery-Prozess auftreten können.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="bf0b0-105">Die Lösung einiger dieser Szenarien erfordert Hilfe vom Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="bf0b0-106">Informationen dazu, wann Sie den Microsoft-Support kontaktieren können, sind in den Lösungsschritten enthalten.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="bf0b0-107">Fehler/Problem: Mehrdeutiger Speicherort</span><span class="sxs-lookup"><span data-stu-id="bf0b0-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="bf0b0-108">Wenn Sie versuchen, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und es doppelte oder in Konflikt stehende Objekte mit derselben Benutzer-ID im Verzeichnis Exchange Online Protection (EOP) gibt, wird der folgende Fehler angezeigt: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="bf0b0-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-109">Resolution</span></span>

<span data-ttu-id="bf0b0-110">Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="bf0b0-111">Verbinden zu [Security & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="bf0b0-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="bf0b0-112">Führen Sie den folgenden Befehl aus, um alle Instanzen des Benutzernamens abzurufen:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="bf0b0-113">Die Ausgabe für "useralias@contoso.com" würde etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="bf0b0-114">Name</span><span class="sxs-lookup"><span data-stu-id="bf0b0-114">Name</span></span>|<span data-ttu-id="bf0b0-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="bf0b0-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="bf0b0-116">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="bf0b0-116">Alias, User</span></span>|<span data-ttu-id="bf0b0-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="bf0b0-117">MailUser</span></span>|
   > |<span data-ttu-id="bf0b0-118">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="bf0b0-118">Alias, User</span></span>|<span data-ttu-id="bf0b0-119">Benutzer</span><span class="sxs-lookup"><span data-stu-id="bf0b0-119">User</span></span>|

3. <span data-ttu-id="bf0b0-120">Wenn mehrere Benutzer zurückgegeben werden, suchen Sie das in Konflikt stehende Objekt, und beheben Sie es.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="bf0b0-121">Fehler/Problem: Suche schlägt an bestimmten Speicherorten fehl</span><span class="sxs-lookup"><span data-stu-id="bf0b0-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="bf0b0-122">Eine eDiscovery- oder Inhaltssuche kann den folgenden Fehler liefern: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="bf0b0-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Screenshot des Fehlerfehlers für suchspezifischen Speicherort](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="bf0b0-124">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-124">Resolution</span></span>

<span data-ttu-id="bf0b0-125">Wenn dieser Fehler angezeigt wird, empfehlen wir, dass Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und die Suche dann nur für die fehlerhaften Speicherorte erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="bf0b0-126">Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="bf0b0-127">Zeigen Sie in der PowerShell-Ausgabe die fehlerhaften Speicherorte im Fehlerfeld oder die Statusdetails im Fehler aus der Suchausgabe an.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="bf0b0-128">Wiederholen Sie die eDiscovery-Suche nur für die fehlgeschlagenen Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="bf0b0-129">Wenn diese Fehler weiterhin angezeigt werden, finden Sie weitere Schritte zur Problembehandlung unter ["Fehlerwiederherstellung".](/Office365/SecurityCompliance/retry-failed-content-search)</span><span class="sxs-lookup"><span data-stu-id="bf0b0-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="bf0b0-130">Fehler/Problem: Datei nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="bf0b0-130">Error/issue: File not found</span></span>

<span data-ttu-id="bf0b0-131">Wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält, wird möglicherweise der Fehler angezeigt, `File Not Found` obwohl sich die Datei auf der Website befindet.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="bf0b0-132">Dieser Fehler wird in den Exportwarnungen angezeigt und items.csv errors.csv oder übersprungen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="bf0b0-133">Dies kann vorkommen, wenn die Datei auf der Website nicht gefunden werden kann oder wenn der Index veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="bf0b0-134">Hier sehen Sie den Text eines tatsächlichen Fehlers (mit hinzugefügter Hervorhebung).</span><span class="sxs-lookup"><span data-stu-id="bf0b0-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="bf0b0-135">28.06.2019 10:02:19_FailedToExportItem_Failed zum Herunterladen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="bf0b0-136">Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Fehler beim Herunterladen von Inhalt 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ "Document".</span><span class="sxs-lookup"><span data-stu-id="bf0b0-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="bf0b0-137">Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="bf0b0-138">ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Datei nicht gefunden.***</span><span class="sxs-lookup"><span data-stu-id="bf0b0-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="bf0b0-139">bei Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) bei Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- Ende der ablaufverfolgung des internen Ausnahmestapels ---</span><span class="sxs-lookup"><span data-stu-id="bf0b0-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-140">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-140">Resolution</span></span>

1. <span data-ttu-id="bf0b0-141">Überprüfen Sie den in der Suche identifizierten Speicherort, um sicherzustellen, dass der Speicherort der Datei korrekt ist und an den Suchspeicherorten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="bf0b0-142">Verwenden Sie die Verfahren bei [der manuellen Anforderung der Durchforstung und neuindizierung einer Website, einer Bibliothek oder einer Liste,](/sharepoint/crawl-site-content) um die Website neu zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="bf0b0-143">Fehler/Problem: Diese Datei wurde nicht exportiert, da sie nicht mehr vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="bf0b0-144">Die Datei wurde in die Anzahl der geschätzten Suchergebnisse einbezogen, da sie noch im Index aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="bf0b0-145">Die Datei wird schließlich aus dem Index entfernt und verursacht in Zukunft keinen Fehler.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="bf0b0-146">Dieser Fehler tritt möglicherweise auf, wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="bf0b0-147">eDiscovery basiert auf dem SPO-Index, um die Dateispeicherorte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-147">eDiscovery relies on teh SPO index to identify the file locations.</span></span> <span data-ttu-id="bf0b0-148">Wenn die Datei gelöscht wurde, der SPO-Index aber noch nicht aktualisiert wurde, tritt dieser Fehler möglicherweise auf.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-149">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-149">Resolution</span></span> 
<span data-ttu-id="bf0b0-150">Öffnen Sie den SPO-Speicherort, und stellen Sie sicher, dass diese Datei nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="bf0b0-151">Die vorgeschlagene Lösung besteht darin, die Website manuell neu zu indizieren oder zu warten, bis die Website durch den automatischen Hintergrundprozess neu indiziert wird.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="bf0b0-152">Fehler/Problem: Dieses Suchergebnis wurde nicht heruntergeladen, da es sich um einen Ordner oder ein anderes Artefakt handelt, der nicht von selbst heruntergeladen werden kann. Alle Elemente innerhalb des Ordners oder der Bibliothek werden heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-152">Error/issue: This search result was not downloaded as it is a folder or other artefact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="bf0b0-153">Dieser Fehler tritt möglicherweise auf, wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="bf0b0-154">Dies bedeutet, dass wir das im Index gemeldete Element ausprobieren und exportieren wollten, es sich jedoch als Ordner herausstellte, sodass wir es nicht exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="bf0b0-155">Wie im Fehler erwähnt, exportieren wir keine Ordnerelemente, sondern deren Inhalte.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="bf0b0-156">Fehler/Problem: Suche schlägt fehl, weil Empfänger nicht gefunden wird</span><span class="sxs-lookup"><span data-stu-id="bf0b0-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="bf0b0-157">Bei einer eDiscovery-Suche tritt ein Fehler `recipient not found` auf.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="bf0b0-158">Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EOP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-159">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-159">Resolution</span></span>

1. <span data-ttu-id="bf0b0-160">Stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="bf0b0-161">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Protection synchronisiert wird:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="bf0b0-162">Für die Benutzerfrage sollte ein E-Mail-Benutzerobjekt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="bf0b0-163">Wenn nichts zurückgegeben wird, untersuchen Sie das Benutzerobjekt.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="bf0b0-164">Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="bf0b0-165">Fehler/Problem: Das Exportieren von Suchergebnissen ist langsam</span><span class="sxs-lookup"><span data-stu-id="bf0b0-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="bf0b0-166">Beim Exportieren von Suchergebnissen aus eDiscovery oder inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-166">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="bf0b0-167">Sie können überprüfen, wie viele Daten heruntergeladen werden sollen, und möglicherweise die Exportgeschwindigkeit erhöhen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-168">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-168">Resolution</span></span>

1. <span data-ttu-id="bf0b0-169">Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="bf0b0-170">Suchen Sie die Datenmenge, die in den Parametern SearchResults und SearchStatistics heruntergeladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="bf0b0-171">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="bf0b0-172">Suchen Sie im Ergebnisfeld nach den exportierten Daten, und zeigen Sie alle aufgetretenen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="bf0b0-173">Überprüfen Sie die Datei "trace.log" im Verzeichnis, in das Sie den Inhalt exportiert haben, auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="bf0b0-174">Wenn weiterhin Probleme auftreten, sollten Sie Suchvorgänge, die eine große Gruppe von Ergebnissen zurückgeben, in kleinere Suchen unterteilen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="bf0b0-175">Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um eine kleinere Gruppe von Ergebnissen zurückzugeben, die schneller heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="bf0b0-176">Fehler/Problem: "Interner Serverfehler (500) aufgetreten"</span><span class="sxs-lookup"><span data-stu-id="bf0b0-176">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="bf0b0-177">Wenn beim Ausführen einer eDiscovery-Suche ein kontinuierlicher Fehler mit dem Fehler "Interner Serverfehler (500) aufgetreten" auftritt, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicherorten erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-177">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Screenshot des internen Serverfehlers 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="bf0b0-179">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-179">Resolution</span></span>

1. <span data-ttu-id="bf0b0-180">Teilen Sie die Suche in kleinere Suchvorgänge auf, und führen Sie die Suche erneut aus.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-180">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="bf0b0-181">Versuchen Sie, einen kleineren Datumsbereich zu verwenden, oder begrenzen Sie die Anzahl der durchsuchten Orte.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-181">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="bf0b0-182">Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-182">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="bf0b0-183">Überprüfen Sie die Ausgabe auf Ergebnisse und Fehler.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-183">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="bf0b0-184">Überprüfen Sie die Datei trace.log.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-184">Examine the trace.log file.</span></span> <span data-ttu-id="bf0b0-185">Er befindet sich in demselben Ordner, in den Sie die Suchergebnisse exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-185">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="bf0b0-186">Wenden Sie sich an den Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-186">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="bf0b0-187">Fehler/Problem: Haltebereiche werden nicht synchronisiert</span><span class="sxs-lookup"><span data-stu-id="bf0b0-187">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="bf0b0-188">eDiscovery Case Hold Policy Sync Distribution error.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-188">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="bf0b0-189">Der Fehler lautet:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-189">The error reads:</span></span>

> <span data-ttu-id="bf0b0-190">"Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-190">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="bf0b0-191">Es kann weitere 2 Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde. Schauen Sie sich also ein paar Stunden zurück."</span><span class="sxs-lookup"><span data-stu-id="bf0b0-191">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-192">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-192">Resolution</span></span>

1. <span data-ttu-id="bf0b0-193">Verbinden zu [Security & Compliance Center PowerShell,](/powershell/exchange/connect-to-scc-powershell) und führen Sie dann den folgenden Befehl für eine eDiscovery-Fallsperre aus:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-193">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="bf0b0-194">Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-194">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="bf0b0-195">Untersuchen Sie den Wert im Parameter DistributionDetail auf Fehler wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-195">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="bf0b0-196">Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-196">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="bf0b0-197">Es kann weitere 2 Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde. Schauen Sie sich also ein paar Stunden zurück."</span><span class="sxs-lookup"><span data-stu-id="bf0b0-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="bf0b0-198">Versuchen Sie, den RetryDistribution-Parameter für die betreffende Richtlinie auszuführen:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-198">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="bf0b0-199">Für eDiscovery-Fallarchive:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-199">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="bf0b0-200">Für Aufbewahrungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-200">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="bf0b0-201">Wenden Sie sich an den Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-201">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="bf0b0-202">Fehler: "Die mit http-bedingten Headern angegebene Bedingung ist nicht erfüllt"</span><span class="sxs-lookup"><span data-stu-id="bf0b0-202">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="bf0b0-203">Beim Herunterladen von Suchergebnissen mit dem eDiscovery-Exporttool wird möglicherweise der folgende Fehler angezeigt: Dies ist ein `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` vorübergehender Fehler, der in der Regel am Azure Storage-Speicherort auftritt.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-203">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-204">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-204">Resolution</span></span>

<span data-ttu-id="bf0b0-205">Um dieses Problem zu beheben, versuchen Sie erneut, [die Suchergebnisse herunterzuladen,](export-search-results.md#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-205">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="bf0b0-206">Fehler/Problem: Heruntergeladener Export zeigt keine Ergebnisse an</span><span class="sxs-lookup"><span data-stu-id="bf0b0-206">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="bf0b0-207">Nach einem erfolgreichen Export zeigt der abgeschlossene Download über das Exporttool keine Dateien in den Ergebnissen an.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-207">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="bf0b0-208">Lösung</span><span class="sxs-lookup"><span data-stu-id="bf0b0-208">Resolution</span></span>

<span data-ttu-id="bf0b0-209">Dies ist ein clientseitiges Problem, und um es zu beheben, versuchen Sie die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="bf0b0-209">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="bf0b0-210">Versuchen Sie, einen anderen Client/Computer zum Herunterladen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-210">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="bf0b0-211">Entfernen Sie alte Suchen, die nicht mehr benötigt werden, mit dem Cmdlet [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch].</span><span class="sxs-lookup"><span data-stu-id="bf0b0-211">Remove old searches that are no longer needed using [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch] cmdlet.</span></span>

3. <span data-ttu-id="bf0b0-212">Stellen Sie sicher, dass Sie auf ein lokales Laufwerk herunterladen.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-212">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="bf0b0-213">Stellen Sie sicher, dass der Virenscanner nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-213">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="bf0b0-214">Stellen Sie sicher, dass kein anderer Export in denselben Ordner oder einen übergeordneten Ordner heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-214">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="bf0b0-215">Wenn die vorherigen Schritte nicht funktioniert haben, deaktivieren Sie das Zipping und die Deduplizierung.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-215">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="bf0b0-216">Wenn dies funktioniert, liegt das Problem an einem lokalen Virenscanner oder einem Datenträgerproblem.</span><span class="sxs-lookup"><span data-stu-id="bf0b0-216">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
