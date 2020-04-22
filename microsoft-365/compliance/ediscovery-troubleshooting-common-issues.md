---
title: Problembehandlung bei gängigen eDiscovery-Problemen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Untersuchen, beheben und beheben Sie häufige Probleme in eDiscovery.
siblings_only: true
ms.openlocfilehash: 5bcbe498cb650268dc8ff6f2b41a6201e75a8192
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631770"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="c9cdf-103">Untersuchen, beheben und Beheben allgemeiner eDiscovery-Probleme</span><span class="sxs-lookup"><span data-stu-id="c9cdf-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="c9cdf-104">In diesem Thema werden grundlegende Schritte zur Problembehandlung beschrieben, die Sie zum Identifizieren und Beheben von Problemen durchführen können, die während einer eDiscovery-Suche oder an einer anderen Stelle im eDiscovery-Prozess auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="c9cdf-105">Das Auflösen einiger dieser Szenarien erfordert Unterstützung durch den Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="c9cdf-106">Die Lösungsschritte enthalten Informationen zum Zeitpunkt der Kontaktaufnahme mit dem Microsoft-Support.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="c9cdf-107">Fehler/Problem: nicht eindeutiger Speicherort</span><span class="sxs-lookup"><span data-stu-id="c9cdf-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="c9cdf-108">Wenn Sie versuchen, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und es sich um doppelte oder widersprüchliche Objekte mit derselben UserID im Verzeichnis Exchange Online Protection (EoP) handelt, wird `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`dieser Fehler angezeigt:.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span> 

### <a name="resolution"></a><span data-ttu-id="c9cdf-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-109">Resolution</span></span>

<span data-ttu-id="c9cdf-110">Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="c9cdf-111">Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)her.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c9cdf-112">Führen Sie den folgenden Befehl aus, um alle Instanzen des Benutzernamens abzurufen:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="c9cdf-113">Die Ausgabe für "useralias@contoso.com" würde etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="c9cdf-114">Name</span><span class="sxs-lookup"><span data-stu-id="c9cdf-114">Name</span></span>  |<span data-ttu-id="c9cdf-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="c9cdf-115">RecipientType</span></span>  |
   > |---------|---------|
   > |<span data-ttu-id="c9cdf-116">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="c9cdf-116">Alias, User</span></span>     |<span data-ttu-id="c9cdf-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="c9cdf-117">MailUser</span></span>         |
   > |<span data-ttu-id="c9cdf-118">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="c9cdf-118">Alias, User</span></span>     |<span data-ttu-id="c9cdf-119">Benutzer</span><span class="sxs-lookup"><span data-stu-id="c9cdf-119">User</span></span>         |

3. <span data-ttu-id="c9cdf-120">Wenn mehrere Benutzer zurückgegeben werden, suchen und beheben Sie das Konflikt verursachende Objekt.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="c9cdf-121">Fehler/Problem: Suchfehler an bestimmten Speicherorten</span><span class="sxs-lookup"><span data-stu-id="c9cdf-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="c9cdf-122">Eine eDiscovery-oder Inhaltssuche kann den folgenden Fehler ergeben:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="c9cdf-123">Diese Suche wurde mit (#) Fehlern abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="c9cdf-124">Möchten Sie die Suche an den fehlgeschlagenen Speicherorten wiederholen?</span><span class="sxs-lookup"><span data-stu-id="c9cdf-124">Would you like to retry the search on the failed locations?</span></span>

![Screenshot der suchspezifischen Speicherort Fehler](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="c9cdf-126">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-126">Resolution</span></span>

<span data-ttu-id="c9cdf-127">Wenn Sie diesen Fehler erhalten, wird empfohlen, dass Sie die Speicherorte überprüfen, die bei der Suche fehlgeschlagen sind, und die Suche dann nur für die fehlerhaften Speicherorte erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="c9cdf-128">Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-128">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. <span data-ttu-id="c9cdf-129">Zeigen Sie in der PowerShell-Ausgabe die fehlerhaften Speicherorte im Feld Fehler oder von den Statusdetails in dem Fehler aus der Suchausgabe an.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="c9cdf-130">Wiederholen Sie die eDiscovery-Suche nur auf den fehlerhaften Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="c9cdf-131">Wenn Sie diese Fehler weiterhin erhalten, finden Sie weitere Informationen zur Problembehandlung unter wieder [holen fehlgeschlagener Speicherorte](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) .</span><span class="sxs-lookup"><span data-stu-id="c9cdf-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="c9cdf-132">Fehler/Problem: Datei nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="c9cdf-132">Error/issue: File not found</span></span>

<span data-ttu-id="c9cdf-133">Wenn Sie eine eDiscovery-Suche durchführen, die SharePoint Online und ein Laufwerk für Geschäftsstandorte enthält, wird `File Not Found` möglicherweise die Fehlermeldung angezeigt, obwohl sich die Datei auf der Website befindet.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="c9cdf-134">Dieser Fehler tritt in den Export Warnungen und Errors. CSV oder Skip Items. CSV auf.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="c9cdf-135">Dies kann vorkommen, wenn die Datei nicht auf der Website gefunden werden kann oder wenn der Index veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-135">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="c9cdf-136">Hier ist der Text eines tatsächlichen Fehlers (mit Nachdruck hinzugefügt).</span><span class="sxs-lookup"><span data-stu-id="c9cdf-136">Here's the text of an actual error (with emphasis added).</span></span>
  
> <span data-ttu-id="c9cdf-137">28.06.2019 10:02:19_FailedToExportItem_Failed zum Herunterladen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="c9cdf-138">Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: Fehler beim Herunterladen aus dem Inhalts 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ Document.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="c9cdf-139">Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="c9cdf-140">ServerErrorCode:-2147024894---> Microsoft. SharePoint. Client. ServerException: die ***Datei wurde nicht gefunden***.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="c9cdf-141">unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---Ende der internen Ausnahmestapelüberwachung---</span><span class="sxs-lookup"><span data-stu-id="c9cdf-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="c9cdf-142">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-142">Resolution</span></span>

1. <span data-ttu-id="c9cdf-143">Überprüfen Sie die in der Suche identifizierte Position, um sicherzustellen, dass der Speicherort der Datei richtig ist und an den Suchpfaden hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="c9cdf-144">Verwenden Sie die Verfahren unter [Manuelles anfordern des Durchforstens und erneuten Indizierens einer Website, einer Bibliothek oder einer Liste](https://docs.microsoft.com/sharepoint/crawl-site-content) zum Neuindizieren der Website.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="c9cdf-145">Fehler/Problem: die Suche schlägt fehl, da der Empfänger nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="c9cdf-146">Bei einer eDiscovery `recipient not found`-Suche tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="c9cdf-147">Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EoP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="c9cdf-148">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-148">Resolution</span></span>

1. <span data-ttu-id="c9cdf-149">Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c9cdf-150">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der Benutzer mit Exchange Online Schutz synchronisiert ist:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-150">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. <span data-ttu-id="c9cdf-151">Es sollte ein e-Mail-Benutzerobjekt für die Benutzerfrage geben.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="c9cdf-152">Wenn Nothing zurückgegeben wird, überprüfen Sie das User-Objekt.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="c9cdf-153">Wenden Sie sich an den Microsoft-Support, wenn das Objekt nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="c9cdf-154">Fehler/Problem: das Exportieren von Suchergebnissen ist langsam</span><span class="sxs-lookup"><span data-stu-id="c9cdf-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="c9cdf-155">Beim Exportieren von Suchergebnissen aus der eDiscovery-oder Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="c9cdf-156">Sie können überprüfen, ob die Datenmenge heruntergeladen und möglicherweise die Exportgeschwindigkeit erhöht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="c9cdf-157">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-157">Resolution</span></span>

1.    <span data-ttu-id="c9cdf-158">Versuchen Sie es mit den Schritten im Artikel [increase Download speeds](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="c9cdf-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2.    <span data-ttu-id="c9cdf-159">Wenn Sie weiterhin Probleme haben, stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-159">If you still have issues, connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. <span data-ttu-id="c9cdf-160">Ermitteln Sie die Menge der Daten, die in den searchresults-und SearchStatistics-Parametern heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

5. <span data-ttu-id="c9cdf-161">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-161">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. <span data-ttu-id="c9cdf-162">Suchen Sie im Feld Ergebnisse die Daten, die exportiert wurden, und zeigen Sie alle aufgetretenen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

7. <span data-ttu-id="c9cdf-163">Überprüfen Sie die Datei Trace. log, die sich in dem Verzeichnis befindet, in das Sie den Inhalt exportiert haben, auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="c9cdf-164">Fehler/Problem: "Interner Serverfehler (500) aufgetreten"</span><span class="sxs-lookup"><span data-stu-id="c9cdf-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="c9cdf-165">Wenn eine eDiscovery-Suche ausgeführt wird und die Suche kontinuierlich fehlschlägt und Fehler wie "Internal Server Error (500)" aufgetreten sind, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicher Orten erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Interner Serverfehler 500 Screenshot](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="c9cdf-167">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-167">Resolution</span></span>

1. <span data-ttu-id="c9cdf-168">Unterbrechen Sie die Suche in kleinere suchen, und führen Sie die Suche erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="c9cdf-169">Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="c9cdf-170">Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-170">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. <span data-ttu-id="c9cdf-171">Überprüfen Sie die Ausgabe auf Ergebnisse und Fehler.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="c9cdf-172">Überprüfen Sie die Datei Trace. log.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-172">Examine the trace.log file.</span></span> <span data-ttu-id="c9cdf-173">Sie befindet sich im gleichen Ordner, in den Sie die Suchergebnisse exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-173">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="c9cdf-174">Wenden Sie sich an den Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="c9cdf-175">Fehler/Problem: hält keine Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="c9cdf-176">eDiscovery Case Hold Policy Sync-Verteilungsfehler.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="c9cdf-177">Der Fehler lautet:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-177">The error reads:</span></span>

> <span data-ttu-id="c9cdf-178">"Ressourcen: die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c9cdf-179">Es kann weitere 2 Stunden dauern, bis Sie den endgültigen Bereitstellungsstatus aktualisiert haben, also schauen Sie sich in ein paar Stunden zurück. "</span><span class="sxs-lookup"><span data-stu-id="c9cdf-179">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="c9cdf-180">Auflösung</span><span class="sxs-lookup"><span data-stu-id="c9cdf-180">Resolution</span></span>

1.    <span data-ttu-id="c9cdf-181">Stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) her, und führen Sie dann den folgenden Befehl für einen eDiscovery-Aufbewahrungs Fall aus:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-181">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    <span data-ttu-id="c9cdf-182">Führen Sie für eine Aufbewahrungsrichtlinie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-182">For a retention policy, run the following command:</span></span>

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. <span data-ttu-id="c9cdf-183">Überprüfen Sie den Wert im Parameter DistributionDetail auf Fehler wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-183">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>
 
   > <span data-ttu-id="c9cdf-184">Fehler: Ressourcen: die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-184">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="c9cdf-185">Es kann weitere 2 Stunden dauern, bis Sie den endgültigen Bereitstellungsstatus aktualisiert haben, also schauen Sie sich in ein paar Stunden zurück. "</span><span class="sxs-lookup"><span data-stu-id="c9cdf-185">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span> 
   
3. <span data-ttu-id="c9cdf-186">Versuchen Sie, den RetryDistribution-Parameter für die betreffende Richtlinie auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-186">Try running the RetryDistribution parameter on the policy in question:</span></span>
   
    
    <span data-ttu-id="c9cdf-187">Für eDiscovery Case Holds:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-187">For eDiscovery case holds:</span></span>

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    <span data-ttu-id="c9cdf-188">Für Aufbewahrungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="c9cdf-188">For retention policies:</span></span>

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. <span data-ttu-id="c9cdf-189">Wenden Sie sich an den Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9cdf-189">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9cdf-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9cdf-190">See Also</span></span>

- [<span data-ttu-id="c9cdf-191">Tipps zum Vermeiden von Inhaltsspeicherort Fehlern</span><span class="sxs-lookup"><span data-stu-id="c9cdf-191">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
