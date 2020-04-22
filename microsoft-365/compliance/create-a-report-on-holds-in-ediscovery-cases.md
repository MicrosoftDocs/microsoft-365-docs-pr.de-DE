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
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Verwenden Sie das Skript in diesem Artikel, um einen Bericht zu generieren, der Informationen zu allen Haltebereichen enthält, die eDiscovery-Fällen im Compliance Center in Office 365 oder Microsoft 365 zugeordnet sind.
ms.openlocfilehash: 263ac052f320a989b8843f2954a5df0933cdb2f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632250"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Erstellen eines Berichts zu Haltebereichen in eDiscovery-Fällen
  
Mit dem Skript in diesem Artikel können eDiscovery-Administratoren und eDiscovery-Manager einen Bericht generieren, der Informationen zu allen Haltebereichen enthält, die eDiscovery-Fällen im Compliance Center in Office 365 oder Microsoft 365 zugeordnet sind. Der Bericht enthält Informationen wie den Namen des Falls, dem ein Haltebereich zugeordnet ist, die Aufbewahrungsorte für Inhalte, die in der Warteschleife gespeichert werden, und ob der Haltebereich Abfrage basiert ist. Wenn es Fälle gibt, in denen keine Aufbewahrungspflicht besteht, erstellt das Skript einen zusätzlichen Bericht mit einer Liste von Fällen ohne Haltestatus.

Eine ausführliche Beschreibung der im Bericht enthaltenen Informationen finden Sie im Abschnitt [Weitere Informationen](#more-information) .
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Wenn Sie einen Bericht über alle eDiscovery-Fälle in Ihrer Organisation generieren möchten, müssen Sie ein eDiscovery-Administrator in Ihrer Organisation sein. Wenn Sie eDiscovery-Manager sind, enthält der Bericht nur Informationen zu den Fällen, auf die Sie zugreifen können. Weitere Informationen zu eDiscovery-Berechtigungen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
    
- Das Skript in diesem Artikel enthält eine minimale Fehlerbehandlung. Der Hauptzweck besteht darin, Schnellbericht über die Haltestatus zu erstellen, die den eDiscovery-Fällen in Ihrer Organisation zugeordnet sind.
    
- Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Schritt 1: Herstellen einer Verbindung mit der Security & Compliance Center PowerShell

Der erste Schritt besteht darin, eine Verbindung mit dem Security & Compliance Center für Ihre Organisation herzustellen.
  
1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `ConnectSCC.ps1`. 
    
      ```powershell
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben. 
    
3. Ausführen des Skripts; Zum Beispiel:

    ```powershell
    .\ConnectSCC.ps1
    ```

4. Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre e-Mail-Adresse und Ihr Kennwort ein, und klicken Sie auf **OK**. 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Schritt 2: Ausführen des Skripts zum Melden von Haltestatus für eDiscovery-Fälle

Nachdem Sie sich mit Security & Compliance Center PowerShell verbunden haben, besteht der nächste Schritt darin, das Skript zu erstellen und auszuführen, das Informationen über die eDiscovery-Fälle in Ihrer Organisation sammelt. 
  
1. Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: CaseHoldsReport. ps1. 
    
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

2. Wechseln Sie in der Windows PowerShell Sitzung, die in Schritt 1 geöffnet wurde, zu dem Ordner, in dem Sie das Skript gespeichert haben. 
    
3. Ausführen des Skripts; Zum Beispiel:

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    Das Skript fordert zur Eingabe eines Zielordners auf, in dem der Bericht gespeichert werden soll. 
    
4. Geben Sie den vollständigen Pfadnamen des Ordners ein, in dem der Bericht gespeichert werden soll, und drücken Sie dann die **Eingabe**Taste.
    
    > [!TIP]
    > Wenn Sie den Bericht in demselben Ordner speichern möchten, in dem sich das Skript befindet, geben Sie einen Punkt (".") ein, wenn Sie zur Eingabe eines Zielordners aufgefordert werden. Wenn Sie den Bericht in einem Unterordner im Ordner speichern möchten, in dem sich das Skript befindet, geben Sie einfach den Namen des Unterordners ein. 
  
    Das Skript beginnt mit der Erfassung von Informationen über alle eDiscovery-Fälle in Ihrer Organisation. Greifen Sie während der Ausführung des Skripts nicht auf die Berichtsdatei zu. Nachdem das Skript abgeschlossen ist, wird eine Bestätigungsmeldung in der Windows PowerShell-Sitzung angezeigt. Nachdem diese Meldung angezeigt wurde, können Sie auf den Bericht in dem Ordner zugreifen, den Sie in Schritt 4 angegeben haben. Der Datei Name für den Bericht lautet `CaseHoldsReport<DateTimeStamp>.csv`.

    Addtionly, erstellt das Skript auch einen Bericht mit einer Liste von Fällen, die keine Haltestatus haben. Der Datei Name für diesen Bericht lautet `CaseswithNoHolds<DateTimeStamp>.csv`.
    
    Hier sehen Sie ein Beispiel für das Ausführen des CaseHoldsReport. ps1-Skripts. 
    
    ![Die Ausgabe nach dem Ausführen des CaseHoldsReport. ps1-Skripts](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Weitere Informationen

Der Fall enthält den Bericht, der erstellt wird, wenn Sie das Skript in diesem Artikel ausführen, enthält die folgenden Informationen zu jedem Haltestatus. Wie bereits erläutert, müssen Sie ein eDiscovery-Administrator sein, um Informationen für alle Haltestatus in Ihrer Organisation zurückzugeben. Weitere Informationen zu Case Holds finden Sie unter [eDiscovery Cases](ediscovery-cases.md).
  
  - Der Name des Haltestatus und der Name des eDiscovery-Falls, dem der Haltebereich zugeordnet ist.
    
  - Gibt an, ob der eDiscovery-Fall aktiv oder geschlossen ist.
    
  - Gibt an, ob der Haltebereich aktiviert oder deaktiviert ist.
    
  - Die Elemente des eDiscovery-Falls, dem der Haltebereich zugeordnet ist. Case-Mitglieder können einen Fall anzeigen oder verwalten, je nachdem, welche eDiscovery-Berechtigungen Ihnen zugewiesen wurden.
    
  - Die Uhrzeit und das Datum, an dem der Fall erstellt wurde.
    
  - Wenn ein Fall geschlossen wird, die Person, die Sie geschlossen hat, und die Uhrzeit und das Datum, an dem Sie geschlossen wurde.
    
  - Die Speicherorte für Exchange-Postfächer und SharePoint-Websites, die gespeichert werden.
    
  - Wenn der Haltebereich Abfrage basiert ist, wird die Abfragesyntax.
    
  - Die Uhrzeit und das Datum, an dem der Speicher erstellt wurde, und die Person, die die Sperre erstellt hat.
    
  - Die Uhrzeit und das Datum, an dem der Haltestatus zuletzt geändert wurde, und die Person, die die Aufbewahrung geändert hat.
