---
title: Problembehandlung bei häufigen eDiscovery-Problemen
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
description: Erfahren Sie mehr über grundlegende Schritte zur Problembehandlung, die Sie zum Beheben gängiger Probleme in Office 365 eDiscovery ausführen können.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926545"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="c076b-103">Untersuchen, Beheben und Beheben gängiger eDiscovery-Probleme</span><span class="sxs-lookup"><span data-stu-id="c076b-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="c076b-104">In diesem Thema werden grundlegende Schritte zur Problembehandlung behandelt, mit deren Hilfe Sie Probleme identifizieren und beheben können, die bei einer eDiscovery-Suche oder an anderer Stelle im eDiscovery-Prozess auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c076b-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="c076b-105">Die Lösung einiger dieser Szenarien erfordert Hilfe vom Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="c076b-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="c076b-106">Informationen dazu, wann Sie den Microsoft-Support kontaktieren, sind in den Lösungsschritten enthalten.</span><span class="sxs-lookup"><span data-stu-id="c076b-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="c076b-107">Fehler/Problem: Mehrdeutiger Speicherort</span><span class="sxs-lookup"><span data-stu-id="c076b-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="c076b-108">Wenn Sie versuchen, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und im Exchange Online Protection (EOP)-Verzeichnis doppelte objekte vorhanden sind oder sich Konflikte mit derselben userID befinden, wird der fehler angezeigt: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="c076b-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-109">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-109">Resolution</span></span>

<span data-ttu-id="c076b-110">Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="c076b-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="c076b-111">Verbinden mit [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c076b-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c076b-112">Führen Sie den folgenden Befehl aus, um alle Instanzen des Benutzernamens abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c076b-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="c076b-113">Die Ausgabe für "useralias@contoso.com" würde der folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="c076b-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="c076b-114">Name</span><span class="sxs-lookup"><span data-stu-id="c076b-114">Name</span></span>|<span data-ttu-id="c076b-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="c076b-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="c076b-116">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="c076b-116">Alias, User</span></span>|<span data-ttu-id="c076b-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="c076b-117">MailUser</span></span>|
   > |<span data-ttu-id="c076b-118">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="c076b-118">Alias, User</span></span>|<span data-ttu-id="c076b-119">Benutzer</span><span class="sxs-lookup"><span data-stu-id="c076b-119">User</span></span>|

3. <span data-ttu-id="c076b-120">Wenn mehrere Benutzer zurückgegeben werden, suchen und beheben Sie das in Konflikt konfliktende Objekt.</span><span class="sxs-lookup"><span data-stu-id="c076b-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="c076b-121">Fehler/Problem: Suche schlägt an bestimmten Speicherorten fehl</span><span class="sxs-lookup"><span data-stu-id="c076b-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="c076b-122">Eine eDiscovery- oder Inhaltssuche kann den folgenden Fehler ergeben: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="c076b-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Fehler screenshot des suchspezifischen Speicherorts](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="c076b-124">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-124">Resolution</span></span>

<span data-ttu-id="c076b-125">Wenn dieser Fehler angezeigt wird, wird empfohlen, dass Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und dann die Suche nur an den fehlgeschlagenen Speicherorten erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c076b-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="c076b-126">Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) ein, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="c076b-127">Zeigen Sie in der PowerShell-Ausgabe die fehlgeschlagenen Speicherorte im Fehlerfeld oder in den Statusdetails im Fehler aus der Suchausgabe an.</span><span class="sxs-lookup"><span data-stu-id="c076b-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="c076b-128">Wiederholen Sie die eDiscovery-Suche nur an den fehlgeschlagenen Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="c076b-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="c076b-129">Wenn Sie diese Fehler weiterhin erhalten, finden Sie weitere Schritte zur Problembehandlung unter [Wiederholen](/Office365/SecurityCompliance/retry-failed-content-search) fehlgeschlagener Speicherorte.</span><span class="sxs-lookup"><span data-stu-id="c076b-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="c076b-130">Fehler/Problem: Datei nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="c076b-130">Error/issue: File not found</span></span>

<span data-ttu-id="c076b-131">Wenn Sie eine eDiscovery-Suche ausführen, die SharePoint Online- und One Drive For Business-Speicherorte enthält, wird möglicherweise der Fehler angezeigt, obwohl sich die Datei auf der `File Not Found` Website befindet.</span><span class="sxs-lookup"><span data-stu-id="c076b-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="c076b-132">Dieser Fehler ist in den Exportwarnungen und errors.csv oder übersprungen items.csv.</span><span class="sxs-lookup"><span data-stu-id="c076b-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="c076b-133">Dies kann auftreten, wenn die Datei nicht auf der Website gefunden werden kann oder der Index veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="c076b-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="c076b-134">Hier ist der Text eines tatsächlichen Fehlers (mit hinzugefügter Betonung).</span><span class="sxs-lookup"><span data-stu-id="c076b-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="c076b-135">28.06.2019 10:02:19_FailedToExportItem_Failed Inhalte herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c076b-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="c076b-136">Zusätzliche Diagnoseinformationen: Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Fehler beim Herunterladen von Inhalten 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ Document.</span><span class="sxs-lookup"><span data-stu-id="c076b-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="c076b-137">Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="c076b-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="c076b-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***Datei nicht gefunden***.</span><span class="sxs-lookup"><span data-stu-id="c076b-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="c076b-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="c076b-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-140">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-140">Resolution</span></span>

1. <span data-ttu-id="c076b-141">Überprüfen Sie den in der Suche identifizierten Speicherort, um sicherzustellen, dass der Speicherort der Datei korrekt ist und an den Suchspeicherorten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c076b-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="c076b-142">Verwenden Sie die Verfahren unter [Manuelles Anfordern](/sharepoint/crawl-site-content) der Durchforstung und erneuten Indizierung einer Website, Bibliothek oder Liste, um die Website neu zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="c076b-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="c076b-143">Fehler/Problem: Suche schlägt fehl, weil der Empfänger nicht gefunden wurde</span><span class="sxs-lookup"><span data-stu-id="c076b-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="c076b-144">Bei einer eDiscovery-Suche tritt ein Fehler auf, der `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="c076b-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="c076b-145">Dieser Fehler kann auftreten, wenn das Benutzerobjekt nicht in Exchange Online Protection (EOP) gefunden werden kann, da das Objekt nicht synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c076b-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-146">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-146">Resolution</span></span>

1. <span data-ttu-id="c076b-147">Stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="c076b-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c076b-148">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Protection synchronisiert ist:</span><span class="sxs-lookup"><span data-stu-id="c076b-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="c076b-149">Es sollte ein E-Mail-Benutzerobjekt für die Benutzerfrage sein.</span><span class="sxs-lookup"><span data-stu-id="c076b-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="c076b-150">Wenn nichts zurückgegeben wird, untersuchen Sie das Benutzerobjekt.</span><span class="sxs-lookup"><span data-stu-id="c076b-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="c076b-151">Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c076b-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="c076b-152">Fehler/Problem: Das Exportieren von Suchergebnissen ist langsam</span><span class="sxs-lookup"><span data-stu-id="c076b-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="c076b-153">Beim Exportieren von Suchergebnissen aus eDiscovery oder Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="c076b-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="c076b-154">Sie können überprüfen, wie viele Daten heruntergeladen werden sollen, und möglicherweise die Exportgeschwindigkeit erhöhen.</span><span class="sxs-lookup"><span data-stu-id="c076b-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-155">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-155">Resolution</span></span>

1. <span data-ttu-id="c076b-156">Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) ein, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="c076b-157">Suchen Sie die Datenmenge, die in den Parametern SearchResults und SearchStatistics heruntergeladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c076b-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="c076b-158">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="c076b-159">Suchen Sie im Ergebnisfeld nach den exportierten Daten, und zeigen Sie alle aufgetretenen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="c076b-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="c076b-160">Überprüfen Sie die Datei trace.log im Verzeichnis, in das Sie den Inhalt exportiert haben, auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="c076b-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="c076b-161">Wenn weiterhin Probleme auftreten, sollten Sie Suchen, die eine große Gruppe von Ergebnissen zurückgeben, in kleinere Suchen unterteilen.</span><span class="sxs-lookup"><span data-stu-id="c076b-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="c076b-162">Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um einen kleineren Satz von Ergebnissen zurückzukehren, die schneller heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="c076b-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="c076b-163">Fehler/Problem: "Interner Serverfehler (500) aufgetreten"</span><span class="sxs-lookup"><span data-stu-id="c076b-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="c076b-164">Wenn beim Ausführen einer eDiscovery-Suche der Fehler "Interner Serverfehler (500) aufgetreten" bei der Suche kontinuierlich fehlschlägt, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicherorten erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c076b-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Screenshot des internen Serverfehlers 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="c076b-166">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-166">Resolution</span></span>

1. <span data-ttu-id="c076b-167">Unterbrechen Sie die Suche in kleinere Suchen, und führen Sie die Suche erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c076b-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="c076b-168">Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="c076b-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="c076b-169">Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) ein, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="c076b-170">Untersuchen Sie die Ausgabe auf Ergebnisse und Fehler.</span><span class="sxs-lookup"><span data-stu-id="c076b-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="c076b-171">Untersuchen Sie die datei trace.log.</span><span class="sxs-lookup"><span data-stu-id="c076b-171">Examine the trace.log file.</span></span> <span data-ttu-id="c076b-172">Sie befindet sich in dem Ordner, in den Sie die Suchergebnisse exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="c076b-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="c076b-173">Wenden Sie sich an den Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c076b-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="c076b-174">Fehler/Problem: Halte halte nicht synchronisiert</span><span class="sxs-lookup"><span data-stu-id="c076b-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="c076b-175">eDiscovery Case Hold Policy Sync Distribution Fehler.</span><span class="sxs-lookup"><span data-stu-id="c076b-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="c076b-176">Der Fehler lautet:</span><span class="sxs-lookup"><span data-stu-id="c076b-176">The error reads:</span></span>

> <span data-ttu-id="c076b-177">"Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="c076b-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c076b-178">Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden."</span><span class="sxs-lookup"><span data-stu-id="c076b-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-179">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-179">Resolution</span></span>

1. <span data-ttu-id="c076b-180">Stellen Sie [eine Verbindung & Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) ein, und führen Sie dann den folgenden Befehl für eine eDiscovery-Fallsicherung aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="c076b-181">Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="c076b-182">Untersuchen Sie den Wert im Parameter DistributionDetail auf Fehler wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="c076b-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="c076b-183">Fehler: Ressourcen: Die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="c076b-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c076b-184">Es kann weitere 2 Stunden dauern, um den endgültigen Bereitstellungsstatus zu aktualisieren. Überprüfen Sie daher in ein paar Stunden."</span><span class="sxs-lookup"><span data-stu-id="c076b-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="c076b-185">Führen Sie den Parameter RetryDistribution für die richtlinie aus:</span><span class="sxs-lookup"><span data-stu-id="c076b-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="c076b-186">Für eDiscovery-Fälle gilt:</span><span class="sxs-lookup"><span data-stu-id="c076b-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="c076b-187">Für Aufbewahrungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="c076b-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="c076b-188">Wenden Sie sich an den Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c076b-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="c076b-189">Fehler: "Die bedingungsbedingte HTTP-Kopfzeile ist nicht erfüllt"</span><span class="sxs-lookup"><span data-stu-id="c076b-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="c076b-190">Beim Herunterladen von Suchergebnissen mithilfe des eDiscovery-Exporttools wird möglicherweise der folgende Fehler angezeigt: Dies ist ein vorübergehender Fehler, der in der Regel am `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage-Speicherort auftritt.</span><span class="sxs-lookup"><span data-stu-id="c076b-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-191">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-191">Resolution</span></span>

<span data-ttu-id="c076b-192">Um dieses Problem zu beheben, versuchen Sie es erneut, [die Suchergebnisse herunterzuladen,](export-search-results.md#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c076b-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="c076b-193">Fehler/Problem: Heruntergeladener Export zeigt keine Ergebnisse an</span><span class="sxs-lookup"><span data-stu-id="c076b-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="c076b-194">Nach einem erfolgreichen Export zeigt der abgeschlossene Download über das Exporttool keine Dateien in den Ergebnissen an.</span><span class="sxs-lookup"><span data-stu-id="c076b-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="c076b-195">Lösung</span><span class="sxs-lookup"><span data-stu-id="c076b-195">Resolution</span></span>

<span data-ttu-id="c076b-196">Dies ist ein clientseitiges Problem, und um es zu beheben, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c076b-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="c076b-197">Versuchen Sie, einen anderen Client/Computer zum Herunterladen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c076b-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="c076b-198">Stellen Sie sicher, dass Sie auf ein lokales Laufwerk herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c076b-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="c076b-199">Stellen Sie sicher, dass der Virenscanner nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c076b-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="c076b-200">Stellen Sie sicher, dass kein anderer Export in denselben Ordner oder übergeordneten Ordner heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="c076b-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="c076b-201">Wenn die vorherigen Schritte nicht funktioniert haben, deaktivieren Sie das Zipping und die Deduplizierung.</span><span class="sxs-lookup"><span data-stu-id="c076b-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="c076b-202">Wenn dies funktioniert, liegt das Problem an einem lokalen Virenscanner oder einem Datenträgerproblem.</span><span class="sxs-lookup"><span data-stu-id="c076b-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>