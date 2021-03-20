---
title: Erstellen eines Berichts zu Haltebereichen in eDiscovery-Fällen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einen Bericht generieren, der Informationen zu allen Haltefällen enthält, die eDiscovery-Fällen zugeordnet sind.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908409"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Erstellen eines Berichts zu Haltebereichen in eDiscovery-Fällen

Mit dem Skript in diesem Artikel können eDiscovery-Administratoren und eDiscovery-Manager einen Bericht generieren, der Informationen zu allen Speicher enthält, die eDiscovery-Fällen im Compliance Center in Office 365 oder Microsoft 365 zugeordnet sind. Der Bericht enthält Informationen, z. B. den Namen des Falls, dem ein Haltefall zugeordnet ist, die Inhaltspositionen, die in der Warteschleife platziert werden, und ob der Halteraum abfragebasierter Ist. Wenn es Fälle gibt, für die keine Haltefälle vorhanden sind, erstellt das Skript einen zusätzlichen Bericht mit einer Liste von Fällen ohne Halte.

Eine ausführliche [Beschreibung der](#more-information) im Bericht enthaltenen Informationen finden Sie im Abschnitt Weitere Informationen.

## <a name="admin-requirements-and-script-information"></a>Administratoranforderungen und Skriptinformationen

- Um einen Bericht zu allen eDiscovery-Fällen in Ihrer Organisation zu generieren, müssen Sie ein eDiscovery-Administrator in Ihrer Organisation sein. Wenn Sie ein eDiscovery-Manager sind, enthält der Bericht nur Informationen zu den Fällen, auf die Sie zugreifen können. Weitere Informationen zu eDiscovery-Berechtigungen finden Sie unter [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

- Das Skript in diesem Artikel hat eine minimale Fehlerbehandlung. Der Hauptzweck besteht in der schnellen Erstellung eines Berichts über die halte, die den eDiscovery-Fällen in Ihrer Organisation zugeordnet sind.

- Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Schritt 1: Herstellen einer Verbindung mit dem Security & Compliance Center PowerShell

Der erste Schritt besteht in der Verbindung mit Security & Compliance Center PowerShell für Ihre Organisation. Schrittweise Anleitungen erhalten Sie unter [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Schritt 2: Ausführen des Skripts zum Melden von Mit eDiscovery-Fällen verknüpften Haltefällen

Nachdem Sie eine Verbindung mit Security & Compliance Center PowerShell erstellt haben, besteht der nächste Schritt im Erstellen und Ausführen des Skripts, das Informationen zu den eDiscovery-Fällen in Ihrer Organisation sammelt.

1. Speichern Sie den folgenden Text in Windows PowerShell Skriptdatei, indem Sie das Dateinamensuffix .ps1 verwenden. Beispiel: CaseHoldsReport.ps1.

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. Wechseln Sie Windows PowerShell sitzung, die in Schritt 1 geöffnet wurde, zu dem Ordner, in dem Sie das Skript gespeichert haben.

3. Führen Sie das Skript aus. Zum Beispiel:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   Das Skript fordert einen Zielordner zum Speichern des Berichts auf.

4. Geben Sie den vollständigen Pfadnamen des Ordners ein, in dem der Bericht gespeichert werden soll, und drücken Sie dann die **EINGABETASTE**.

   > [!TIP]
   > Um den Bericht in dem Ordner zu speichern, in dem sich das Skript befindet, geben Sie einen Zeitraum (".") ein, wenn Sie zur Eingabe eines Zielordners aufgefordert werden. Geben Sie einfach den Namen des Unterordners ein, um den Bericht in einem Unterordner im Ordner zu speichern, in dem sich das Skript befindet.

   Das Skript beginnt, Informationen zu allen eDiscovery-Fällen in Ihrer Organisation zu sammeln. Greifen Sie während der Ausführung des Skripts nicht auf die Berichtsdatei zu. Nach Abschluss des Skripts wird eine Bestätigungsmeldung in der Windows PowerShell angezeigt. Nachdem diese Meldung angezeigt wurde, können Sie auf den Bericht in dem Ordner zugreifen, den Sie in Schritt 4 angegeben haben. Der Dateiname für den Bericht ist `CaseHoldsReport<DateTimeStamp>.csv` .

   Darüber hinaus erstellt das Skript auch einen Bericht mit einer Liste von Fällen, für die keine Haltefälle vorhanden sind. Der Dateiname für diesen Bericht ist `CaseswithNoHolds<DateTimeStamp>.csv` .

   Hier sehen Sie ein Beispiel für das Ausführen des CaseHoldsReport.ps1 Skripts.

   ![Die Ausgabe nach dem Ausführen des CaseHoldsReport.ps1 Skripts](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Weitere Informationen

Der Fall enthält einen Bericht, der erstellt wird, wenn Sie das Skript in diesem Artikel ausführen, und enthält die folgenden Informationen zu jedem Halteraum. Wie bereits erläutert, müssen Sie ein eDiscovery-Administrator sein, um Informationen für alle Halterechte in Ihrer Organisation zurücksennen zu können. Weitere Informationen zu Fallfällen finden Sie unter [eDiscovery-Fälle](./get-started-core-ediscovery.md).

- Der Name des Halteraums und der Name des eDiscovery-Falls, dem der Halteraum zugeordnet ist.

- Gibt an, ob der eDiscovery-Fall aktiv oder geschlossen ist.

- Gibt an, ob der Halteraum aktiviert oder deaktiviert ist.

- Die Member des eDiscovery-Falls, dem der Halteraum zugeordnet ist. Fallmitglieder können je nach den eDiscovery-Berechtigungen, denen sie zugewiesen wurden, einen Fall anzeigen oder verwalten.

- Die Uhrzeit und das Datum, an dem der Fall erstellt wurde.

- Wenn ein Fall geschlossen wird, die Person, die ihn geschlossen hat, sowie die Uhrzeit und das Datum, an dem er geschlossen wurde.

- Die Speicherorte von Exchange-Postfächern und SharePoint-Websites, die sich in der Warteschleife befinden.

- Wenn der Halteraum abfragebasierte ist, wird die Abfragesyntax verwendet.

- Die Uhrzeit und das Datum, an dem der Halteraum erstellt wurde, und die Person, die ihn erstellt hat.

- Die Uhrzeit und das Datum, an dem der Halteraum zuletzt geändert wurde, und die Person, die ihn geändert hat.