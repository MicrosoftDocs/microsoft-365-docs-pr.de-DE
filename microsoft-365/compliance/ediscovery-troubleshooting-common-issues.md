---
title: Troublshooting häufige eDiscovery-Probleme
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
description: Untersuchen, beheben und beheben Sie häufige Probleme in Office 365 eDiscovery.
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207292"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="d12c8-103">Untersuchen, beheben und Beheben allgemeiner eDiscovery-Probleme</span><span class="sxs-lookup"><span data-stu-id="d12c8-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="d12c8-104">In diesem Thema werden grundlegende Schritte zur Problembehandlung beschrieben, die Sie zum Identifizieren und Beheben von Problemen durchführen können, die während einer eDiscovery-Suche oder an einer anderen Stelle im eDiscovery-Prozess auftreten können.</span><span class="sxs-lookup"><span data-stu-id="d12c8-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="d12c8-105">Zum Beheben einiger dieser Szenarien benötigen Sie Hilfe von den Kunden Support Diensten (CSS).</span><span class="sxs-lookup"><span data-stu-id="d12c8-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="d12c8-106">Informationen zum Zeitpunkt der Kontaktaufnahme mit CSS sind in den Lösungsschritten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d12c8-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="d12c8-107">Fehler/Problem-mehrdeutiger Speicherort</span><span class="sxs-lookup"><span data-stu-id="d12c8-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="d12c8-108">Dieser Fehler wird angezeigt "die kompatibilitätssuche enthält den folgenden ungültigen `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` Speicherort, wenn Sie versucht haben, den Postfachspeicherort des Benutzers zur Suche hinzuzufügen, und es gibt doppelte oder widersprüchliche Objekte mit derselben Benutzer-ID im Exchange Online Schutz (EoP). Directory.</span><span class="sxs-lookup"><span data-stu-id="d12c8-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="d12c8-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-109">Resolution</span></span>

<span data-ttu-id="d12c8-110">Suchen Sie nach doppelten Benutzern oder Verteilerlisten mit derselben Benutzer-ID.</span><span class="sxs-lookup"><span data-stu-id="d12c8-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="d12c8-111">Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) her.</span><span class="sxs-lookup"><span data-stu-id="d12c8-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="d12c8-112">Rufen Sie alle Instanzen des Benutzernamens ab, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d12c8-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="d12c8-113">Die Ausgabe für "useralias@contoso.com" kann</span><span class="sxs-lookup"><span data-stu-id="d12c8-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="d12c8-114">Name</span><span class="sxs-lookup"><span data-stu-id="d12c8-114">Name</span></span>  |<span data-ttu-id="d12c8-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="d12c8-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="d12c8-116">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="d12c8-116">Alias, User</span></span>     |<span data-ttu-id="d12c8-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="d12c8-117">MailUser</span></span>         |
> |<span data-ttu-id="d12c8-118">Alias, Benutzer</span><span class="sxs-lookup"><span data-stu-id="d12c8-118">Alias, User</span></span>     |<span data-ttu-id="d12c8-119">Benutzer</span><span class="sxs-lookup"><span data-stu-id="d12c8-119">User</span></span>         |

3. <span data-ttu-id="d12c8-120">Wenn mehrere Benutzer zurückgegeben werden, suchen und beheben Sie das Konflikt verursachende Objekt.</span><span class="sxs-lookup"><span data-stu-id="d12c8-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="d12c8-121">Fehler/Problemsuche an bestimmten Speicherorten fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="d12c8-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="d12c8-122">Eine eDiscovery-oder Inhaltssuche kann den folgenden Fehler ergeben:</span><span class="sxs-lookup"><span data-stu-id="d12c8-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="d12c8-123">Diese Suche wurde mit (#) Fehlern abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d12c8-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="d12c8-124">Möchten Sie die Suche an den fehlgeschlagenen Speicherorten wiederholen?</span><span class="sxs-lookup"><span data-stu-id="d12c8-124">Would you like to retry the search on the failed locations?</span></span>

![Screenshot der suchspezifischen Position fails Fehler]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="d12c8-126">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-126">Resolution</span></span>

<span data-ttu-id="d12c8-127">Wenn dieser Fehler auftritt, wird empfohlen, dass Sie die Speicherorte überprüfen, bei denen die Suche fehlgeschlagen ist, und führen Sie die Suche dann nur für die fehlerhaften Speicherorte erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d12c8-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="d12c8-128">Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)her.</span><span class="sxs-lookup"><span data-stu-id="d12c8-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="d12c8-129">Typ:</span><span class="sxs-lookup"><span data-stu-id="d12c8-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="d12c8-130">Zeigen Sie in der PowerShell-Ausgabe die fehlerhaften Speicherorte im Feld Fehler oder von den Statusdetails in dem Fehler aus der Suchausgabe an.</span><span class="sxs-lookup"><span data-stu-id="d12c8-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="d12c8-131">Wiederholen Sie die eDiscovery-Suche nur auf den fehlerhaften Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="d12c8-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="d12c8-132">Wenn diese Fehlermeldung weiterhin angezeigt wird, finden Sie weitere Informationen zur Problembehandlung unter wieder [holen fehlgeschlagener Speicherorte](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) .</span><span class="sxs-lookup"><span data-stu-id="d12c8-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="d12c8-133">Fehler/Problem Datei nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="d12c8-133">Error/issue file not found</span></span>

<span data-ttu-id="d12c8-134">Wenn Sie eine eDiscovery-Suche durchführen, die SharePoint Online und ein Laufwerk für Geschäftsstandorte enthält, wird `File Not Found` möglicherweise die Fehlermeldung angezeigt, obwohl sich die Datei auf der Website befindet.</span><span class="sxs-lookup"><span data-stu-id="d12c8-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="d12c8-135">Dieser Fehler tritt in den Export Warnungen und Errors. CSV oder Skipped Items. CSV auf, wenn die Datei nicht auf der Website gefunden werden kann oder der Index veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="d12c8-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="d12c8-136">Hier ist der Text eines tatsächlichen Fehlers, wobei der Schwerpunkt hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d12c8-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="d12c8-137">28.06.2019 10:02:19_FailedToExportItem_Failed zum Herunterladen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="d12c8-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="d12c8-138">Zusätzliche Diagnoseinformationen: Microsoft. Office. Compliance. EDiscovery. ExportWorker. Exceptions. ContentDownloadTemporaryFailure: Fehler beim Herunterladen aus dem Inhalts 6ea52149-91cd-4965-b5bb-82ca6a3ec9be vom Typ Document.</span><span class="sxs-lookup"><span data-stu-id="d12c8-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="d12c8-139">Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="d12c8-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="d12c8-140">ServerErrorCode:-2147024894---#a0 Microsoft. SharePoint. Client. ServerException: die ***Datei wurde nicht gefunden***.</span><span class="sxs-lookup"><span data-stu-id="d12c8-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="d12c8-141">unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponseStream (Stream responseStream) unter Microsoft. SharePoint. Client. ClientRequest. ProcessResponse ()---Ende der internen Ausnahmestapelüberwachung---</span><span class="sxs-lookup"><span data-stu-id="d12c8-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="d12c8-142">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-142">Resolution</span></span>

1. <span data-ttu-id="d12c8-143">Überprüfen Sie die in der Suche identifizierte Position, um sicherzustellen, dass der Speicherort der Datei richtig ist und an den Suchpfaden hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d12c8-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="d12c8-144">Verwenden Sie die Verfahren unter [Manuelles anfordern des Durchforstens und erneuten Indizierens einer Website, einer Bibliothek oder einer Liste](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) zum erneuten Indizieren der Website.</span><span class="sxs-lookup"><span data-stu-id="d12c8-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="d12c8-145">Fehler/Problemsuche fehlgeschlagen Empfänger nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="d12c8-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="d12c8-146">die eDiscovery-Suche schlägt `recipient not found`fehl mit dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="d12c8-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="d12c8-147">Dieser Fehler kann auftreten, wenn das Benutzerobjekt in Exchange Online Protection (EoP) nicht gefunden werden kann, da das Objekt nicht synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d12c8-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="d12c8-148">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-148">Resolution</span></span>

1. <span data-ttu-id="d12c8-149">Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)her.</span><span class="sxs-lookup"><span data-stu-id="d12c8-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="d12c8-150">Überprüfen Sie, ob das Benutzerobjekt mit Exchange Online Schutztyp synchronisiert ist:</span><span class="sxs-lookup"><span data-stu-id="d12c8-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="d12c8-151">Es sollte ein MailUser-Objekt für die Benutzerfrage geben.</span><span class="sxs-lookup"><span data-stu-id="d12c8-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="d12c8-152">Wenn Nothing zurückgegeben wird, überprüfen Sie das User-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d12c8-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="d12c8-153">Wenden Sie sich an CSS, wenn das Objekt nicht synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d12c8-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="d12c8-154">Fehler/Problem beim Exportieren der Suchergebnisse ist langsam</span><span class="sxs-lookup"><span data-stu-id="d12c8-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="d12c8-155">Beim Exportieren von Suchergebnissen aus der eDiscovery-oder Inhaltssuche im Security and Compliance Center dauert der Download länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="d12c8-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="d12c8-156">Sie können überprüfen, ob die Datenmenge heruntergeladen und möglicherweise die Exportgeschwindigkeit erhöht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d12c8-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="d12c8-157">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-157">Resolution</span></span>

1.  <span data-ttu-id="d12c8-158">Versuchen Sie es mit den Schritten im Artikel [increase Download speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span><span class="sxs-lookup"><span data-stu-id="d12c8-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="d12c8-159">Wenn Sie weiterhin Probleme haben, stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) her, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d12c8-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="d12c8-160">Ermitteln Sie die Menge der Daten, die in den searchresults-und SearchStatistics-Parametern heruntergeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d12c8-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="d12c8-161">Typ:</span><span class="sxs-lookup"><span data-stu-id="d12c8-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="d12c8-162">Suchen Sie im Feld Ergebnisse die Daten, die exportiert wurden, und zeigen Sie alle aufgetretenen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="d12c8-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="d12c8-163">Überprüfen Sie die Datei Trace. log, die sich in dem Verzeichnis befindet, in das Sie den Inhalt exportiert haben, auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="d12c8-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="d12c8-164">Fehler/Problem "Interner Serverfehler (500) aufgetreten"</span><span class="sxs-lookup"><span data-stu-id="d12c8-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="d12c8-165">Wenn eine eDiscovery-Suche ausgeführt wird und die Suche kontinuierlich fehlschlägt und Fehler wie "Internal Server Error (500)" aufgetreten sind, müssen Sie die Suche möglicherweise nur an bestimmten Postfachspeicher Orten erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="d12c8-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![Interner Serverfehler 500 Screenshot](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="d12c8-167">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-167">Resolution</span></span>

1. <span data-ttu-id="d12c8-168">Unterbrechen Sie die Suche in kleinere suchen, und führen Sie die Suche erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d12c8-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="d12c8-169">Versuchen Sie, einen kleineren Datumsbereich zu verwenden oder die Anzahl der durchsuchten Speicherorte zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="d12c8-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="d12c8-170">Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) her und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d12c8-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="d12c8-171">Überprüfen Sie die Ausgabe auf Ergebnisse und Fehler.</span><span class="sxs-lookup"><span data-stu-id="d12c8-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="d12c8-172">Überprüfen Sie die Datei Trace. log.</span><span class="sxs-lookup"><span data-stu-id="d12c8-172">Examine the trace.log file.</span></span> <span data-ttu-id="d12c8-173">Es befindet sich in demselben Ordner, an den Sie den Export gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="d12c8-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="d12c8-174">Wenden Sie sich an den Support CSS.</span><span class="sxs-lookup"><span data-stu-id="d12c8-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="d12c8-175">Fehler/Problem hält nicht synchronisiert</span><span class="sxs-lookup"><span data-stu-id="d12c8-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="d12c8-176">eDiscovery Case Hold Policy Sync-Verteilungsfehler.</span><span class="sxs-lookup"><span data-stu-id="d12c8-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="d12c8-177">Der Fehler lautet:</span><span class="sxs-lookup"><span data-stu-id="d12c8-177">The error reads:</span></span>

> <span data-ttu-id="d12c8-178">"Ressourcen: die Bereitstellung der Richtlinie dauert länger als erwartet.</span><span class="sxs-lookup"><span data-stu-id="d12c8-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="d12c8-179">Es kann weitere zwei Stunden dauern, bis der endgültige Bereitstellungsstatus aktualisiert wurde, daher sollten Sie sich in ein paar Stunden wieder einfinden. "</span><span class="sxs-lookup"><span data-stu-id="d12c8-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="d12c8-180">Auflösung</span><span class="sxs-lookup"><span data-stu-id="d12c8-180">Resolution</span></span>

1.  <span data-ttu-id="d12c8-181">Stellen Sie eine Verbindung mit [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) her und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d12c8-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="d12c8-182">Überprüfen Sie den Wert im Parameter Distributiondetail auf Fehler wie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="d12c8-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="d12c8-183">Wenn ein Fehler vorliegt, erstellen Sie eine Eskalation an PG, um eine manuelle erneute Synchronisierung für die Richtlinie zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="d12c8-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="d12c8-184">Wenden Sie sich an CSS.</span><span class="sxs-lookup"><span data-stu-id="d12c8-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="d12c8-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d12c8-185">See Also</span></span>
- [<span data-ttu-id="d12c8-186">Tipps zum Vermeiden von Inhaltsspeicherort Fehlern</span><span class="sxs-lookup"><span data-stu-id="d12c8-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)