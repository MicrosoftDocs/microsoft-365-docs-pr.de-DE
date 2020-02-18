---
title: Erstellen eines Berichts über Aufbewahrungen in eDiscovery-Fällen in Office 365
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
ms.openlocfilehash: 8c426ff06bb0b2bafdfa91b9098b321994d558d7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077707"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="f79d6-103">Erstellen eines Berichts über Aufbewahrungen in eDiscovery-Fällen in Office 365</span><span class="sxs-lookup"><span data-stu-id="f79d6-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="f79d6-104">Mit dem Skript in diesem Artikel können eDiscovery-Administratoren und eDiscovery-Manager einen Bericht generieren, der Informationen zu allen Haltebereichen enthält, die eDiscovery-Fällen im Compliance Center in Office 365 oder Microsoft 365 zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f79d6-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="f79d6-105">Der Bericht enthält Informationen wie den Namen des Falls, dem ein Haltebereich zugeordnet ist, die Aufbewahrungsorte für Inhalte, die in der Warteschleife gespeichert werden, und ob der Haltebereich Abfrage basiert ist.</span><span class="sxs-lookup"><span data-stu-id="f79d6-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="f79d6-106">Wenn es Fälle gibt, in denen keine Aufbewahrungspflicht besteht, erstellt das Skript einen zusätzlichen Bericht mit einer Liste von Fällen ohne Haltestatus.</span><span class="sxs-lookup"><span data-stu-id="f79d6-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="f79d6-107">Eine ausführliche Beschreibung der im Bericht enthaltenen Informationen finden Sie im Abschnitt [Weitere Informationen](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="f79d6-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f79d6-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="f79d6-108">Before you begin</span></span>

- <span data-ttu-id="f79d6-109">Wenn Sie einen Bericht über alle eDiscovery-Fälle in Ihrer Organisation generieren möchten, müssen Sie ein eDiscovery-Administrator in Ihrer Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="f79d6-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="f79d6-110">Wenn Sie eDiscovery-Manager sind, enthält der Bericht nur Informationen zu den Fällen, auf die Sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f79d6-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="f79d6-111">Weitere Informationen zu eDiscovery-Berechtigungen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f79d6-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="f79d6-112">Das Skript in diesem Artikel enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="f79d6-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="f79d6-113">Der Hauptzweck besteht darin, Schnellbericht über die Haltestatus zu erstellen, die den eDiscovery-Fällen in Ihrer Organisation zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f79d6-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="f79d6-p104">Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f79d6-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="f79d6-119">Schritt 1: Herstellen einer Verbindung mit der Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="f79d6-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f79d6-120">Der erste Schritt besteht darin, eine Verbindung mit dem Security & Compliance Center für Ihre Organisation herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f79d6-120">The first step is to connect to the Security & Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="f79d6-121">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `ConnectSCC.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f79d6-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```powershell
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. <span data-ttu-id="f79d6-122">Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f79d6-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="f79d6-123">Ausführen des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f79d6-123">Run the script; for example:</span></span>

    ```powershell
    .\ConnectSCC.ps1
    ```

4. <span data-ttu-id="f79d6-124">Wenn Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden, geben Sie Ihre e-Mail-Adresse und Ihr Kennwort ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f79d6-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="f79d6-125">Schritt 2: Ausführen des Skripts zum Melden von Haltestatus für eDiscovery-Fälle</span><span class="sxs-lookup"><span data-stu-id="f79d6-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="f79d6-126">Nachdem Sie sich mit Security & Compliance Center PowerShell verbunden haben, besteht der nächste Schritt darin, das Skript zu erstellen und auszuführen, das Informationen über die eDiscovery-Fälle in Ihrer Organisation sammelt.</span><span class="sxs-lookup"><span data-stu-id="f79d6-126">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="f79d6-127">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: CaseHoldsReport. ps1.</span><span class="sxs-lookup"><span data-stu-id="f79d6-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="f79d6-128">Wechseln Sie in der Windows PowerShell Sitzung, die in Schritt 1 geöffnet wurde, zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f79d6-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="f79d6-129">Ausführen des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f79d6-129">Run the script; for example:</span></span>

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="f79d6-130">Das Skript fordert zur Eingabe eines Zielordners auf, in dem der Bericht gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f79d6-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="f79d6-131">Geben Sie den vollständigen Pfadnamen des Ordners ein, in dem der Bericht gespeichert werden soll, und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="f79d6-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f79d6-132">Wenn Sie den Bericht in demselben Ordner speichern möchten, in dem sich das Skript befindet, geben Sie einen Punkt (".") ein, wenn Sie zur Eingabe eines Zielordners aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="f79d6-132">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="f79d6-133">Wenn Sie den Bericht in einem Unterordner im Ordner speichern möchten, in dem sich das Skript befindet, geben Sie einfach den Namen des Unterordners ein.</span><span class="sxs-lookup"><span data-stu-id="f79d6-133">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="f79d6-134">Das Skript beginnt mit der Erfassung von Informationen über alle eDiscovery-Fälle in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f79d6-134">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="f79d6-135">Greifen Sie während der Ausführung des Skripts nicht auf die Berichtsdatei zu.</span><span class="sxs-lookup"><span data-stu-id="f79d6-135">Don't access the report file while the script is running.</span></span> <span data-ttu-id="f79d6-136">Nachdem das Skript abgeschlossen ist, wird eine Bestätigungsmeldung in der Windows PowerShell-Sitzung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f79d6-136">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="f79d6-137">Nachdem diese Meldung angezeigt wurde, können Sie auf den Bericht in dem Ordner zugreifen, den Sie in Schritt 4 angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f79d6-137">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="f79d6-138">Der Datei Name für den Bericht lautet `CaseHoldsReport<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="f79d6-138">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="f79d6-139">Addtionly, erstellt das Skript auch einen Bericht mit einer Liste von Fällen, die keine Haltestatus haben.</span><span class="sxs-lookup"><span data-stu-id="f79d6-139">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="f79d6-140">Der Datei Name für diesen Bericht lautet `CaseswithNoHolds<DateTimeStamp>.csv`.</span><span class="sxs-lookup"><span data-stu-id="f79d6-140">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="f79d6-141">Hier sehen Sie ein Beispiel für das Ausführen des CaseHoldsReport. ps1-Skripts.</span><span class="sxs-lookup"><span data-stu-id="f79d6-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![Die Ausgabe nach dem Ausführen des CaseHoldsReport. ps1-Skripts](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="f79d6-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f79d6-143">More information</span></span>

<span data-ttu-id="f79d6-144">Der Fall enthält den Bericht, der erstellt wird, wenn Sie das Skript in diesem Artikel ausführen, enthält die folgenden Informationen zu jedem Haltestatus.</span><span class="sxs-lookup"><span data-stu-id="f79d6-144">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="f79d6-145">Wie bereits erläutert, müssen Sie ein eDiscovery-Administrator sein, um Informationen für alle Haltestatus in Ihrer Organisation zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f79d6-145">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="f79d6-146">Weitere Informationen zu Case Holds finden Sie unter [eDiscovery Cases](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="f79d6-146">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="f79d6-147">Der Name des Haltestatus und der Name des eDiscovery-Falls, dem der Haltebereich zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f79d6-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="f79d6-148">Gibt an, ob der eDiscovery-Fall aktiv oder geschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f79d6-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="f79d6-149">Gibt an, ob der Haltebereich aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f79d6-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="f79d6-150">Die Elemente des eDiscovery-Falls, dem der Haltebereich zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f79d6-150">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="f79d6-151">Case-Mitglieder können einen Fall anzeigen oder verwalten, je nachdem, welche eDiscovery-Berechtigungen Ihnen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="f79d6-151">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="f79d6-152">Die Uhrzeit und das Datum, an dem der Fall erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f79d6-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="f79d6-153">Wenn ein Fall geschlossen wird, die Person, die Sie geschlossen hat, und die Uhrzeit und das Datum, an dem Sie geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="f79d6-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="f79d6-154">Die Speicherorte für Exchange-Postfächer und SharePoint-Websites, die gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f79d6-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="f79d6-155">Wenn der Haltebereich Abfrage basiert ist, wird die Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="f79d6-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="f79d6-156">Die Uhrzeit und das Datum, an dem der Speicher erstellt wurde, und die Person, die die Sperre erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="f79d6-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="f79d6-157">Die Uhrzeit und das Datum, an dem der Haltestatus zuletzt geändert wurde, und die Person, die die Aufbewahrung geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f79d6-157">The time and date the hold was last changed and the person who changed it.</span></span>
