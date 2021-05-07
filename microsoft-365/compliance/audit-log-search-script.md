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
description: Verwenden Sie ein PowerShell-Skript, das das Cmdlet "Search-UnifiedAuditLog" in Exchange Online ausführt, um das Audit-Protokoll zu durchsuchen. Dieses Skript ist für die Rückgabe einer großen Menge (bis zu 50.000) von Überwachungsdatensätzen optimiert. Das Skript exportiert diese Einträge in eine CSV-Datei, die Sie mithilfe von Power Query in Excel anzeigen oder transformieren können.
ms.openlocfilehash: df5e675e5e36603a73078bd5ecf5e64bc7a76f95
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939565"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Verwenden eines PowerShell-Skripts zum Durchsuchen des Überwachungsprotokolls

Sicherheit, Compliance und Überwachung haben heutzutage für IT-Administratoren oberste Priorität. Microsoft 365 umfasst mehrere integrierte Funktionen, die Organisationen in den Bereichen Sicherheit, Compliance und Überwachung unterstützen. Insbesondere die vereinheitlichte Überwachungsprotokollierung kann Ihnen dabei helfen, Sicherheitsvorfälle und Complianceprobleme zu untersuchen. Sie können Überwachungsprotokolle mithilfe der folgenden Methoden abrufen:

- [Mittels Office 365-Verwaltungsaktivitäts-API](/office/office-365-management-api/office-365-management-activity-api-reference)

- Über das [Überwachungsprotokoll-Suchtool](search-the-audit-log-in-security-and-compliance.md) im Microsoft 365 Compliance Center

- Mithilfe des [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)-Cmdlets in Exchange Online PowerShell

Wenn Sie regelmäßig Überwachungsprotokolle abrufen müssen, sollten Sie eine Lösung in Betracht ziehen, bei der die Office 365-Verwaltungsaktivitäts-API verwendet wird, da sie großen Organisationen die nötige Skalierbarkeit und Leistung bietet, um kontinuierlich Millionen von Überwachungsdatensätzen abzurufen. Mithilfe des Überwachungsprotokollsuche-Tools im Microsoft 365 Compliance Center können etwa Überwachungsdatensätze für bestimmte Vorgänge, die in kürzeren Zeiträumen auftreten, schnell gefunden werden. Bei Verwendung längerer Zeiträume im Überwachungsprotokoll-Suchtool werden insbesondere bei großen Organisationen u. U. zu viele Datensätze für eine einfache Verwaltung oder den Export zurückgegeben.

In Situationen, in denen Sie Überwachungsdaten für eine bestimmte Untersuchung oder einen Vorfall manuell abrufen müssen, insbesondere für längere Datumsbereiche in größeren Organisationen, ist die Verwendung des Cmdlets **Search-UnifiedAuditLog** möglicherweise die beste Option. Dieser Artikel umfasst ein PowerShell-Skript, das mithilfe des Cmdlets bis zu 50.000 Überwachungsdatensätze abruft und diese dann in eine CSV-Datei exportiert, die Sie mit Power Query in Excel für die Überprüfung formatieren können. Durch die Verwendung des in diesem Artikel beschriebenen Skripts wird auch die Wahrscheinlichkeit minimiert, dass es bei umfangreichen Überwachungsprotokollsuchen zu einer Zeitüberschreitung im Dienst kommt.

## <a name="before-you-run-the-script"></a>Vor dem Ausführen des Skripts

- Damit das Skript zum Zurückgeben von Überwachungsdatensätzen verwendet werden kann, muss die Überwachungsprotokollierung für Ihre Organisation aktiviert sein. Die Überwachungsprotokollierung ist für Microsoft 365- und Office 365 Enterprise-Organisationen standardmäßig aktiviert. Um zu überprüfen, ob die Überwachungsprotokollsuche für Ihre Organisation aktiviert ist, können Sie den folgenden Befehl in der Exchange Online-PowerShell ausführen:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  Der Wert `True` für die Eigenschaft **UnifiedAuditLogIngestionEnabled** gibt an, dass die Überwachungsprotokollsuche aktiviert ist.

- Ihnen muss in Exchange Online entweder die Rolle "Überwachungsprotokolle nur anzeigen" oder "Überwachungsprotokolle" zugewiesen sein, um das Skript ausführen zu können. Standardmäßig sind diese Rollen im Exchange Admin Center zugewiesen den Rollengruppen „Complianceverwaltung“ und „Organisationsverwaltung“ auf der Seite Berechtigungen. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Compliance Center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) im Abschnitt "Voraussetzungen für die Durchsuchung des Überwachungsprotokolls".

- Das Ausführen des Skripts kann länger dauern. Wie lange es dauert, hängt vom Datumsbereich und von der Größe des Intervalls ab, für die das Skript Überwachungsdatensätze abrufen soll. Größere Datumsbereiche und kürzere Intervalle führen zu einer längeren Ausführungsdauer. Weitere Informationen zum Datumsbereich und zu den Intervallen finden Sie in der Tabelle in Schritt 2.

- Das in diesem Artikel bereitgestellte Beispielskript wird unter keinem Standardsupportprogramm oder -dienst von Microsoft unterstützt. Das Beispielskript wird WIE BESEHEN ohne jegliche Gewährleistung bereitgestellt. Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das mit der Verwendung oder Leistung des Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen. In keinem Fall haften Microsoft, seine Autoren oder eine andere Person, die an der Erstellung, Herstellung oder Zustellung/Verteilung des Skripts beteiligt ist, für Schäden jeglicher Art (einschließlich, aber nicht beschränkt auf Schäden durch verlorene Geschäftsgewinne, Geschäftsunterbrechung, Verlust von Geschäftsdaten oder andere finanzielle Verluste), die aus der Verwendung oder der Unfähigkeit der Verwendung des Beispielskripts oder der Dokumentation entstehen, selbst wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Schritt 1: Herstellen einer Verbindung mit Exchange Online PowerShell

Im ersten Schritt muss eine Verbindung mit Exchange Online PowerShell hergestellt werden. Sie können die Verbindung mithilfe der modernen Authentifizierung oder mittels mehrstufiger Authentifizierung herstellen. Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Schritt 2: Anpassen und Ausführen des Skripts zum Abrufen von Überwachungsdatensätzen

Nachdem eine Verbindung mit Exchange Online PowerShell hergestellt wurde, besteht der nächste Schritt im Erstellen, Anpassen und Ausführen des Skripts, um die Überwachungsdaten abzurufen. Die ersten sieben Zeilen im Skript für die Überwachungsprotokollsuche enthalten die folgenden Variablen, die Sie zum Konfigurieren der Suche ändern können. Eine Beschreibung dieser Variablen finden Sie in der Tabelle in Schritt 2.

1. Speichern Sie den folgenden Text in ein Windows PowerShell-Skript, indem Sie das Dateinamensuffix „.ps1“ verwenden. Beispiel: SearchAuditLog.ps1.

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
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
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
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
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

2. Ändern Sie die in der folgenden Tabelle aufgeführten Variablen, um die Suchkriterien zu konfigurieren. Das Skript enthält Beispielwerte für diese Variablen, die Sie aber (sofern nicht anders angegeben) Ihren Anforderungen entsprechend anpassen sollten.

   <br>

   ****

   |Variable|Beispielwert|Beschreibung|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|Gibt den Namen und Speicherort für die Protokolldatei an, die Informationen über den Fortschritt der vom Skript ausgeführten Überwachungsprotokollsuche enthält. Das Skript schreibt UTC-Zeitstempel in die Protokolldatei.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Gibt den Namen und Speicherort der CSV-Datei an, die die vom Skript zurückgegebenen Überwachungsdatensätze enthält.|
   |`[DateTime]$start` und `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Gibt den Datumsbereich für die Überwachungsprotokollsuche an. Das Skript gibt Datensätze für Überwachungsaktivitäten zurück, die innerhalb des angegebenen Datumsbereichs erfolgt sind. Wenn beispielsweise Aktivitäten zurückgeben werden sollen, die im Januar 2021 ausgeführt wurden, können Sie als Startdatum `"2021-01-01"` und als Enddatum `"2021-01-31"` angeben (achten Sie darauf, die Werte in doppelte Anführungszeichen zu setzen). Der Beispielwert im Skript gibt Datensätze für Aktivitäten zurück, die innerhalb der letzten 24 Stunden ausgeführt wurden. Wenn der Wert keinen Zeitstempel enthält, wird der standardmäßige Zeitstempel "00:00 Uhr" (Mitternacht) für das angegebene Datum verwendet.|
   |`$record`|"AzureActiveDirectory"|Gibt den Datensatztyp der Überwachungsaktivitäten (auch als *Überwachungsvorgänge* bezeichnet) an, nach dem gesucht werden soll. Diese Eigenschaft gibt den Dienst oder das Feature an, in dem eine Aktivität ausgelöst wurde. Eine Liste der Datensatztypen, die Sie für diese Variable verwenden können, finden Sie unter [Überwachungsprotokolle: Datensatztypen](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype). Sie können den Datensatztypnamen oder den ENUM-Wert verwenden. <br/><br/>**Tipp:** Verwenden Sie den Wert `$null` (ohne doppelte Anführungszeichen), wenn Überwachungsdatensätze für alle Datensatztypen zurückgegeben werden sollen.|
   |`$resultSize`|5000|Gibt die Anzahl von Ergebnissen an, die jedes Mal zurückgegeben werden, wenn das Cmdlet **Search-UnifiedAuditLog** durch das Skript aufgerufen wird (auch als *Resultset* bezeichnet). Der Wert 5.000 ist die vom Cmdlet unterstützte Höchstanzahl. Lassen Sie diesen Wert unverändert.|
   |`$intervalMinutes`|60|Um die Einschränkung von 5.000 zurückgegebenen Datensätzen einzuhalten, teilt diese Variable den angegebenen Datumsbereich in kleinere Zeitintervalle auf. Das Ausgabelimit des Befehls von 5 000 Datensätzen gilt dann für jedes Intervall, nicht für den gesamten Datumsbereich. Für die meisten Organisationen dürfte der Standardwert von 5 000 Datensätzen pro 60-Minuten-Intervall innerhalb des Datumsbereichs ausreichend sein. Sollte das Skript aber eine Fehlermeldung zurückgeben, die besagt „`maximum results limitation reached`“, verringern Sie das Zeitintervall (z. B.auf 30 Minuten oder sogar 15 Minuten), und führen Sie das Skript erneut aus.|
   ||||

   Die meisten der in der vorherigen Tabelle aufgeführten Variablen entsprechen Parametern für das Cmdlet **Search-UnifiedAuditLog**. Weitere Informationen zu diesen Parametern finden Sie unter [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).

3. Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das geänderte Skript gespeichert haben.

4. Führen Sie das Skript in Exchange Online PowerShell aus. Zum Beispiel:

   ```powershell
   .\SearchAuditLog.ps1
   ```

Während der Ausführung des Skripts werden Statusmeldungen angezeigt. Nach der Ausführung des Skripts werden die Protokolldatei und die CSV-Datei erstellt, die die Überwachungsdatensätze enthält, und diese in den Ordnern gespeichert, die durch die Variablen `$logFile` und `$outputFile` definiert sind.

> [!IMPORTANT]
> Bei jeder Ausführung dieses Skripts gilt ein Limit von maximal 50.000 zurückgegebenen Überwachungsdatensätzen. Wenn Sie dieses Skript ausführen und 50.000 Ergebnisse zurückgegeben werden, wurden wahrscheinlich keine Überwachungsdatensätze für Aktivitäten einbezogen, die innerhalb dieses Datumsbereichs erfolgt sind. In diesem Fall empfehlen wir, den Datumsbereich in kleinere Abschnitte zu unterteilen und dann das Skript für jeden Datumsbereich erneut auszuführen. Wenn beispielsweise bei einem Datumsbereich von 90 Tagen 50.000 Ergebnisse zurückgegeben werden, können Sie das Skript zweimal ausführen, einmal für die ersten 45 Tage und dann erneut für die anderen 45 Tage des Datumsbereichs.

## <a name="step-3-format-and-view-the-audit-records"></a>Schritt 3: Formatieren und Anzeigen der Überwachungsdatensätze

Nachdem Sie das Skript ausgeführt und die Überwachungsdatensätze in eine CSV-Datei exportiert haben, können Sie die CSV-Datei formatieren, um die Überprüfung und Analyse der Überwachungsdatensätze zu vereinfachen. Eine Methode hierfür besteht darin, mithilfe des Power Query-Features zum Transformieren in Excel jede Eigenschaft im JSON-Objekt in der Spalte **AuditData** in eine eigene Spalte aufzuteilen. Schrittweise Anleitungen finden Sie unter "Schritt 2: Formatieren von exportierten Überwachungsprotokollen mithilfe des Power Query-Editors" in [Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).
