---
title: Verwenden eines PowerShell-Skripts zum Durchsuchen des Überwachungsprotokolls
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Verwenden eines PowerShell-Skripts, bei dem das Cmdlet "Search-UnifiedAuditLog" ausgeführt wird, um das Überwachungsprotokoll zu durchsuchen Dieses Skript ist für die Rückgabe großer Mengen (bis zu 50.000) von Überwachungsdatensätzen ausgelegt. Das Skript exportiert diese Einträge in eine CSV-Datei, die Sie mithilfe von Power Query in Excel anzeigen oder transformieren können.
ms.openlocfilehash: d4fcf59297747d0499f6616438299ad8cbe96d7f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094786"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="ddf6c-105">Verwenden eines PowerShell-Skripts zum Durchsuchen des Überwachungsprotokolls</span><span class="sxs-lookup"><span data-stu-id="ddf6c-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="ddf6c-106">Sicherheit, Compliance und Überwachung haben heutzutage für IT-Administratoren oberste Priorität.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="ddf6c-107">Microsoft 365 umfasst mehrere integrierte Funktionen, die Organisationen in den Bereichen Sicherheit, Compliance und Überwachung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="ddf6c-108">Insbesondere die vereinheitlichte Überwachungsprotokollierung kann Ihnen dabei helfen, Sicherheitsvorfälle und Complianceprobleme zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="ddf6c-109">Sie können Überwachungsprotokolle mithilfe der folgenden Methoden abrufen:</span><span class="sxs-lookup"><span data-stu-id="ddf6c-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="ddf6c-110">Mittels Office 365-Verwaltungsaktivitäts-API</span><span class="sxs-lookup"><span data-stu-id="ddf6c-110">The Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="ddf6c-111">Über das [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ddf6c-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="ddf6c-112">Mithilfe des [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)-Cmdlets in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddf6c-112">The [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="ddf6c-113">Wenn Sie regelmäßig Überwachungsprotokolle abrufen müssen, sollten Sie eine Lösung in Betracht ziehen, bei der die Office 365-Verwaltungsaktivitäts-API verwendet wird, da sie großen Organisationen die nötige Skalierbarkeit und Leistung bietet, um kontinuierlich Millionen von Überwachungsdatensätzen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="ddf6c-114">Mithilfe des Überwachungsprotokollsuche-Tools im Microsoft 365 Compliance Center können etwa Überwachungsdatensätze für bestimmte Vorgänge, die in kürzeren Zeiträumen auftreten, schnell gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="ddf6c-115">Bei Verwendung längerer Zeiträume im Überwachungsprotokoll-Suchtool werden insbesondere bei großen Organisationen u. U. zu viele Datensätze für eine einfache Verwaltung oder den Export zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="ddf6c-116">In Situationen, in denen Sie Überwachungsdaten für eine bestimmte Untersuchung oder einen Vorfall manuell abrufen müssen, insbesondere für längere Datumsbereiche in größeren Organisationen, ist die Verwendung des Cmdlets **Search-UnifiedAuditLog** möglicherweise die beste Option.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="ddf6c-117">Dieser Artikel umfasst ein PowerShell-Skript, das mithilfe des Cmdlets bis zu 50.000 Überwachungsdatensätze abruft und diese dann in eine CSV-Datei exportiert, die Sie mit Power Query in Excel für die Überprüfung formatieren können.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="ddf6c-118">Durch die Verwendung des in diesem Artikel beschriebenen Skripts wird auch die Wahrscheinlichkeit minimiert, dass es bei umfangreichen Überwachungsprotokollsuchen zu einer Zeitüberschreitung im Dienst kommt.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="ddf6c-119">Vor dem Ausführen des Skripts</span><span class="sxs-lookup"><span data-stu-id="ddf6c-119">Before you run the script</span></span>

- <span data-ttu-id="ddf6c-120">Damit das Skript zum Zurückgeben von Überwachungsdatensätzen verwendet werden kann, muss die Überwachungsprotokollierung für Ihre Organisation aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="ddf6c-121">Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="ddf6c-122">Um zu überprüfen, ob die Überwachungsprotokollsuche für Ihre Organisation aktiviert ist, können Sie den folgenden Befehl in der Exchange Online-PowerShell ausführen:</span><span class="sxs-lookup"><span data-stu-id="ddf6c-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  <span data-ttu-id="ddf6c-123">Der Wert `True` für die Eigenschaft **UnifiedAuditLogIngestionEnabled** gibt an, dass die Überwachungsprotokollsuche aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="ddf6c-124">Ihnen muss in Exchange Online entweder die Rolle "Überwachungsprotokolle nur anzeigen" oder "Überwachungsprotokolle" zugewiesen sein, um das Skript ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="ddf6c-125">Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="ddf6c-126">Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Compliance Center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) im Abschnitt "Voraussetzungen für die Durchsuchung des Überwachungsprotokolls".</span><span class="sxs-lookup"><span data-stu-id="ddf6c-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="ddf6c-127">Das Ausführen des Skripts kann länger dauern.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="ddf6c-128">Wie lange es dauert, hängt vom Datumsbereich und von der Größe des Intervalls ab, für die das Skript Überwachungsdatensätze abrufen soll.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="ddf6c-129">Größere Datumsbereiche und kürzere Intervalle führen zu einer längeren Ausführungsdauer.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="ddf6c-130">Weitere Informationen zum Datumsbereich und zu den Intervallen finden Sie in der Tabelle in Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="ddf6c-131">Das in diesem Artikel bereitgestellte Beispielskript wird unter keinem standardmäßigen Supportprogramm oder Dienst von Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="ddf6c-132">Das Beispielskript wird wie besehen ohne jegliche Gewährleistung zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="ddf6c-133">Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Marktgängigkeit oder Eignung für einen bestimmten Zweck aus.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="ddf6c-134">Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="ddf6c-135">In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung des Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung des Beispielskripts oder der Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="ddf6c-136">Schritt 1: Herstellen einer Verbindung mit Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddf6c-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="ddf6c-137">Im ersten Schritt muss eine Verbindung mit Exchange Online PowerShell hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="ddf6c-138">Sie können die Verbindung mithilfe der modernen Authentifizierung oder mittels mehrstufiger Authentifizierung herstellen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="ddf6c-139">Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ddf6c-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="ddf6c-140">Schritt 2: Anpassen und Ausführen des Skripts zum Abrufen von Überwachungsdatensätzen</span><span class="sxs-lookup"><span data-stu-id="ddf6c-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="ddf6c-141">Nachdem eine Verbindung mit Exchange Online PowerShell hergestellt wurde, besteht der nächste Schritt im Erstellen, Anpassen und Ausführen des Skripts, um die Überwachungsdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="ddf6c-142">Die ersten sieben Zeilen im Skript für die Überwachungsprotokollsuche enthalten die folgenden Variablen, die Sie zum Konfigurieren der Suche ändern können.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="ddf6c-143">Eine Beschreibung dieser Variablen finden Sie in der Tabelle in Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="ddf6c-144">Speichern Sie den nachstehenden Text in einer Windows PowerShell-Skriptdatei mit dem Dateinamensuffix ".ps1".</span><span class="sxs-lookup"><span data-stu-id="ddf6c-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="ddf6c-145">Beispiel: SearchAuditLog.ps1.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-145">For example, SearchAuditLog.ps1.</span></span>

```powershell
#Modify the values for the following variables to configure the audit log search.
$logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
$outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
[DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
[DateTime]$end = [DateTime]::UtcNow
$record = "AzureActiveDirectory"
$resultSize = 5000
$intervalMinutes = 60

#Start script
[DateTime]$currentStart = $start
[DateTime]$currentEnd = $start

Function Write-LogFile ([String]$Message)
{
    $final = [DateTime]::Now.ToString("s") + ":" + $Message
    $final | Out-File $logFile -Append
}

Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"

$totalCount = 0
while ($true)
{
    $currentEnd = $currentStart.AddMinutes($intervalMinutes)
    if ($currentEnd -gt $end)
    {
        $currentEnd = $end
    }

    if ($currentStart -eq $currentEnd)
    {
        break
    }

    $sessionID = [DateTime]::Now.ToString("s")
    Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    $currentCount = 0

    $sw = [Diagnostics.StopWatch]::StartNew()
    do
    {
        $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize

        if (($results | Measure-Object).Count -ne 0)
        {
            $results | export-csv -Path $outputFile -Append -NoTypeInformation

            $currentTotal = $results[0].ResultCount
            $totalCount += $results.Count
            $currentCount += $results.Count
            Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"

            if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
            {
                $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                Write-LogFile $message
                Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                ""
                break
            } 
        }
    }
    while (($results | Measure-Object).Count -ne 0)

    $currentStart = $currentEnd
}

Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green

```

2. <span data-ttu-id="ddf6c-146">Ändern Sie die in der folgenden Tabelle aufgeführten Variablen, um die Suchkriterien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="ddf6c-147">Das Skript enthält Beispielwerte für diese Variablen, die Sie aber (sofern nicht anders angegeben) Ihren Anforderungen entsprechend anpassen sollten.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   |<span data-ttu-id="ddf6c-148">Variable</span><span class="sxs-lookup"><span data-stu-id="ddf6c-148">Variable</span></span>|<span data-ttu-id="ddf6c-149">Beispielwert</span><span class="sxs-lookup"><span data-stu-id="ddf6c-149">Sample value</span></span>|<span data-ttu-id="ddf6c-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddf6c-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="ddf6c-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="ddf6c-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="ddf6c-152">Gibt den Namen und Speicherort für die Protokolldatei an, die Informationen über den Fortschritt der vom Skript ausgeführten Überwachungsprotokollsuche enthält.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span>|
   |`$outputFile`|<span data-ttu-id="ddf6c-153">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="ddf6c-153">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="ddf6c-154">Gibt den Namen und Speicherort der CSV-Datei an, die die vom Skript zurückgegebenen Überwachungsdatensätze enthält.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-154">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="ddf6c-155">`[DateTime]$start` und `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="ddf6c-155">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="ddf6c-158">Gibt den Datumsbereich für die Überwachungsprotokollsuche an.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-158">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="ddf6c-159">Das Skript gibt Datensätze für Überwachungsaktivitäten zurück, die innerhalb des angegebenen Datumsbereichs erfolgt sind.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-159">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="ddf6c-160">Wenn beispielsweise Aktivitäten zurückgeben werden sollen, die im Januar 2021 ausgeführt wurden, können Sie als Startdatum `"2021-01-01"` und als Enddatum `"2021-01-31"` angeben (achten Sie darauf, die Werte in doppelte Anführungszeichen zu setzen). Der Beispielwert im Skript gibt Datensätze für Aktivitäten zurück, die innerhalb der letzten 24 Stunden ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-160">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="ddf6c-161">Wenn der Wert keinen Zeitstempel enthält, wird der standardmäßige Zeitstempel "00:00 Uhr" (Mitternacht) für das angegebene Datum verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-161">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="ddf6c-162">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="ddf6c-162">"AzureActiveDirectory"</span></span>|<span data-ttu-id="ddf6c-163">Gibt den Datensatztyp der Überwachungsaktivitäten (auch als *Überwachungsvorgänge* bezeichnet) an, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-163">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="ddf6c-164">Diese Eigenschaft gibt den Dienst oder das Feature an, in dem eine Aktivität ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-164">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="ddf6c-165">Eine Liste der Datensatztypen, die Sie für diese Variable verwenden können, finden Sie unter [Überwachungsprotokolle: Datensatztypen](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span><span class="sxs-lookup"><span data-stu-id="ddf6c-165">For a list of record types that you can use for this variable, see [Audit log record type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="ddf6c-166">Sie können den Datensatztypnamen oder den ENUM-Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-166">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="ddf6c-167">**Tipp:** Verwenden Sie den Wert `$null` (ohne doppelte Anführungszeichen), wenn Überwachungsdatensätze für alle Datensatztypen zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-167">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="ddf6c-168">5000</span><span class="sxs-lookup"><span data-stu-id="ddf6c-168">5000</span></span>|<span data-ttu-id="ddf6c-169">Gibt die Anzahl von Ergebnissen an, die jedes Mal zurückgegeben werden, wenn das Cmdlet **Search-UnifiedAuditLog** durch das Skript aufgerufen wird (auch als *Resultset* bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="ddf6c-169">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="ddf6c-170">Der Wert 5.000 ist die vom Cmdlet unterstützte Höchstanzahl.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-170">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="ddf6c-171">Lassen Sie diesen Wert unverändert.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-171">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="ddf6c-172">60</span><span class="sxs-lookup"><span data-stu-id="ddf6c-172">60</span></span>|<span data-ttu-id="ddf6c-173">Um die Einschränkung von 5.000 zurückgegebenen Datensätzen einzuhalten, teilt diese Variable den angegebenen Datumsbereich in kleinere Zeitintervalle auf.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-173">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="ddf6c-174">Das Ausgabelimit des Befehls von 5 000 Datensätzen gilt dann für jedes Intervall, nicht für den gesamten Datumsbereich.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-174">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="ddf6c-175">Für die meisten Organisationen dürfte der Standardwert von 5 000 Datensätzen pro 60-Minuten-Intervall innerhalb des Datumsbereichs ausreichend sein.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-175">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="ddf6c-176">Sollte das Skript aber eine Fehlermeldung zurückgeben, die besagt „`maximum results limitation reached`“, verringern Sie das Zeitintervall (z. B.auf 30 Minuten oder sogar 15 Minuten), und führen Sie das Skript erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-176">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="ddf6c-177">Die meisten der in der vorherigen Tabelle aufgeführten Variablen entsprechen Parametern für das Cmdlet **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-177">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="ddf6c-178">Weitere Informationen zu diesen Parametern finden Sie unter [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span><span class="sxs-lookup"><span data-stu-id="ddf6c-178">For more information about these parameters, see [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="ddf6c-179">Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das geänderte Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-179">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="ddf6c-180">Führen Sie das Skript in Exchange Online PowerShell aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ddf6c-180">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="ddf6c-181">Während der Ausführung des Skripts werden Statusmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-181">The script displays progress messages while it's running.</span></span> <span data-ttu-id="ddf6c-182">Nach der Ausführung des Skripts werden die Protokolldatei und die CSV-Datei erstellt, die die Überwachungsdatensätze enthält, und diese in den Ordnern gespeichert, die durch die Variablen `$logFile` und `$outputFile` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-182">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddf6c-183">Bei jeder Ausführung dieses Skripts gilt ein Limit von maximal 50.000 zurückgegebenen Überwachungsdatensätzen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-183">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="ddf6c-184">Wenn Sie dieses Skript ausführen und 50.000 Ergebnisse zurückgegeben werden, wurden wahrscheinlich keine Überwachungsdatensätze für Aktivitäten einbezogen, die innerhalb dieses Datumsbereichs erfolgt sind.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-184">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="ddf6c-185">In diesem Fall empfehlen wir, den Datumsbereich in kleinere Abschnitte zu unterteilen und dann das Skript für jeden Datumsbereich erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-185">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="ddf6c-186">Wenn beispielsweise bei einem Datumsbereich von 90 Tagen 50.000 Ergebnisse zurückgegeben werden, können Sie das Skript zweimal ausführen, einmal für die ersten 45 Tage und dann erneut für die anderen 45 Tage des Datumsbereichs.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-186">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="ddf6c-187">Schritt 3: Formatieren und Anzeigen der Überwachungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="ddf6c-187">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="ddf6c-188">Nachdem Sie das Skript ausgeführt und die Überwachungsdatensätze in eine CSV-Datei exportiert haben, können Sie die CSV-Datei formatieren, um die Überprüfung und Analyse der Überwachungsdatensätze zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-188">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="ddf6c-189">Eine Methode hierfür besteht darin, mithilfe des Power Query-Features zum Transformieren in Excel jede Eigenschaft im JSON-Objekt in der Spalte **AuditData** in eine eigene Spalte aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="ddf6c-189">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="ddf6c-190">Schrittweise Anleitungen finden Sie unter "Schritt 2: Formatieren von exportierten Überwachungsprotokollen mithilfe des Power Query-Editors" in [Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span><span class="sxs-lookup"><span data-stu-id="ddf6c-190">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
