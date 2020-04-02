---
title: Massenerstellen und Veröffentlichen von Aufbewahrungsbeschriftungen mithilfe von PowerShell
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: In Office 365 können Sie Aufbewahrungsbezeichnungen verwenden, um einen Aufbewahrungszeitplan für Ihr Unternehmen zu implementieren. Mithilfe des bereitgestellten Skripts und der CSV-Dateien können Sie Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien per Massenvorgang mit PowerShell erstellen und veröffentlichen.
ms.openlocfilehash: e7b992b8464e5c505d048b5b945d154a770fd59c
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105977"
---
# <a name="bulk-create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="31b09-104">Massenerstellen und Veröffentlichen von Aufbewahrungsbeschriftungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="31b09-104">Bulk create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="31b09-105">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="31b09-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="31b09-p102">In Office 365 können Sie Aufbewahrungsbeschriftungen verwenden, um einen Aufbewahrungszeitplan für Ihre Organisation zu implementieren. Als Datensatzverwalter oder Compliance Officer müssen Sie vielleicht Hunderte von Aufbewahrungsbeschriftungen erstellen und veröffentlichen. Sie können hierfür die Benutzeroberfläche im Security &amp; Compliance Center verwenden, das einzelne Erstellen von Aufbewahrungsbeschriftungen ist aber sehr zeitaufwändig und ineffizient.</span><span class="sxs-lookup"><span data-stu-id="31b09-p102">In Office 365, you can use retention labels to implement a retention schedule for your organization. As a record manager or compliance officer, you might have hundreds of retention labels to create and publish. You can do this through the UI in the Security &amp; Compliance Center, but creating retention labels one at a time is time-consuming and inefficient.</span></span>
  
<span data-ttu-id="31b09-109">Mithilfe des unten bereitgestellten Skripts und der CSV-Dateien können Sie Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien per Massenvorgang erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="31b09-109">By using the script and .csv files provided below, you can bulk create retention labels and publish retention label policies.</span></span> <span data-ttu-id="31b09-110">Zuerst erstellen Sie eine Liste der Aufbewahrungsbezeichnungen und eine Liste der Aufbewahrungsbezeichnungsrichtlinien in Excel. Anschließend verwenden Sie PowerShell, um die Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien in diesen Listen per Massenvorgang zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="31b09-110">First you create a list of the retention labels and a list of the retention label policies in Excel, and then you use PowerShell to bulk create the retention labels and retention label policies in those lists.</span></span> <span data-ttu-id="31b09-111">Dies erleichtert es Ihnen, alle Aufbewahrungsbezeichnungen, die für Ihren Aufbewahrungszeitplan erforderlich sind, gleichzeitig zu erstellen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="31b09-111">This makes it easier to create and publish all of the retention labels that your retention schedule requires at one time.</span></span>
  
<span data-ttu-id="31b09-112">Weitere Informationen über Aufbewahrungsbeschriftungen finden Sie unter [Übersicht über Aufbewahrungsbeschriftungen ](labels.md).</span><span class="sxs-lookup"><span data-stu-id="31b09-112">For more information about retention labels, see [Overview of labels](labels.md).</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="31b09-113">Verzichtserklärung</span><span class="sxs-lookup"><span data-stu-id="31b09-113">Disclaimer</span></span>

<span data-ttu-id="31b09-p104">Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="31b09-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-creating-the-retention-labels"></a><span data-ttu-id="31b09-119">Schritt 1: Erstellen einer CSV-Datei zum Erstellen der Aufbewahrungsbeschriftungen</span><span class="sxs-lookup"><span data-stu-id="31b09-119">Step 1: Create a .csv file for creating the retention labels</span></span>

<span data-ttu-id="31b09-p105">Zunächst erstellen Sie eine CSV-Datei, die eine Liste Ihrer Aufbewahrungsbeschriftungen mit den jeweiligen Einstellungen enthält. Sie können das folgende Beispiel als Vorlage verwenden, indem Sie es in Excel kopieren (in Excel: Registerkarte \> **Daten** Registerkarte \> **Text in Spalten** \> **Getrennt** \> **Komma** \> **Allgemein**), und die Tabelle dann als CSV-Datei an einem leicht auffindbaren Speicherplatz speichern.</span><span class="sxs-lookup"><span data-stu-id="31b09-p105">First you create a .csv file that contains a list of your retention labels with their settings. You can use the sample below as a template by copying it into Excel, converting the text to columns (in Excel \> **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**), and then saving the worksheet as a .csv file in a location that's easy to find.</span></span>
  
<span data-ttu-id="31b09-122">Weitere Informationen zu den Parameterwerten für dieses Cmdlet finden Sie unter [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span><span class="sxs-lookup"><span data-stu-id="31b09-122">For more information about the parameter values for this cmdlet, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>
  
<span data-ttu-id="31b09-123">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="31b09-123">Notes:</span></span>
  
- <span data-ttu-id="31b09-124">Wenn Sie keine Quelldatei für das Erstellen von Aufbewahrungsbeschriftungen bereitstellen, fährt das Skript fort und fordert Sie auf, die Quelldatei zum Veröffentlichen von Aufbewahrungsbeschriftungen (siehe nächster Abschnitt) anzugeben. Das Skript veröffentlicht nur vorhandene Aufbewahrungsbeschriftungen.</span><span class="sxs-lookup"><span data-stu-id="31b09-124">If you don't provide a source file for creating retention labels, the script moves on and prompts you for the source file for publishing retention labels (see the next section), and the script will publish only existing retention labels.</span></span>
    
- <span data-ttu-id="31b09-p106">Wenn die CSV-Datei eine Aufbewahrungsbeschriftung mit demselben Namen wie eine bereits vorhandene Aufbewahrungsbeschriftung enthält, überspringt das Skript die Erstellung der Aufbewahrungsbeschriftung. Es werden keine doppelten Aufbewahrungsbeschriftungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="31b09-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="31b09-p107">Wenn Sie die Spaltenüberschrift ändern oder umbenennen, schlägt das Skript fehl. Das Skript benötigt eine CSV-Datei im hier dargestellten Format.</span><span class="sxs-lookup"><span data-stu-id="31b09-p107">If you change or rename the column headers, the script will fail. The script requires a .csv file in the format provided here.</span></span>
    
### <a name="sample-csv-file"></a><span data-ttu-id="31b09-129">CSV-Beispieldatei</span><span class="sxs-lookup"><span data-stu-id="31b09-129">Sample .csv file</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-publishing-the-labels"></a><span data-ttu-id="31b09-130">Schritt 2: Erstellen einer CSV-Datei zum Veröffentlichen der Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="31b09-130">Step 2: Create a .csv file for publishing the labels</span></span>

<span data-ttu-id="31b09-p108">Als Nächstes erstellen Sie eine CSV-Datei, die eine Liste von Aufbewahrungsbeschriftungsrichtlinien mit den jeweiligen Speicherorten sowie andere Einstellungen enthält. Sie können das folgende Beispiel als Vorlage verwenden, indem Sie es in Excel kopieren (in Excel: Registerkarte \> **Daten** Registerkarte \> **Text in Spalten** \> **Getrennt** \> **Komma** \> **Allgemein**), und die Tabelle dann als CSV-Datei an einem leicht auffindbaren Speicherplatz speichern.</span><span class="sxs-lookup"><span data-stu-id="31b09-p108">Next you create a .csv file that contains a list of retention label policies with their locations and other settings. You can use the sample below as a template by copying it into Excel, converting the text to columns (in Excel \> **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**), and then saving the worksheet as a .csv file in a location that's easy to find.</span></span>
  
<span data-ttu-id="31b09-133">Weitere Informationen zu den Parameterwerten für dieses Cmdlet finden Sie unter [New-RetentionCompliancePolicy](https://go.microsoft.com/fwlink/?linkid=866512).</span><span class="sxs-lookup"><span data-stu-id="31b09-133">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://go.microsoft.com/fwlink/?linkid=866512).</span></span>
  
<span data-ttu-id="31b09-134">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="31b09-134">Notes:</span></span>
  
- <span data-ttu-id="31b09-135">Wenn Sie keine Quelldatei zum Veröffentlichen von Aufbewahrungsbeschriftungen angeben, erstellt das Skript Aufbewahrungsbeschriftungen (siehe vorheriger Abschnitt), veröffentlicht sie aber nicht.</span><span class="sxs-lookup"><span data-stu-id="31b09-135">If you don't provide a source file for publishing retention labels, the script creates retention labels (see the previous section) but doesn't publish them.</span></span>
    
- <span data-ttu-id="31b09-p109">Wenn die CSV-Datei eine Aufbewahrungsbeschriftungsrichtlinie mit demselben Namen wie eine bereits vorhandene enthält, überspringt das Skript die Erstellung der Aufbewahrungsbeschriftungsrichtlinie. Es werden keine doppelten Aufbewahrungsbeschriftungsrichtlinien erstellt.</span><span class="sxs-lookup"><span data-stu-id="31b09-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="31b09-138">Das Skript veröffentlicht nur Aufbewahrungsbezeichnungen, die manuell auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="31b09-138">The script publishes only retention labels that are applied manually to content.</span></span> <span data-ttu-id="31b09-139">Dieses Skript unterstützt keine Aufbewahrungsbezeichnungen, die automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="31b09-139">This script doesn't support retention labels that are auto-applied to content.</span></span>
    
- <span data-ttu-id="31b09-p111">Wenn Sie die Spaltenüberschrift ändern oder umbenennen, schlägt das Skript fehl. Das Skript benötigt eine CSV-Datei im hier dargestellten Format.</span><span class="sxs-lookup"><span data-stu-id="31b09-p111">If you change or rename the column headers, the script will fail. The script requires a .csv file in the format provided here.</span></span>
    
### <a name="sample-csv-file"></a><span data-ttu-id="31b09-142">CSV-Beispieldatei</span><span class="sxs-lookup"><span data-stu-id="31b09-142">Sample .csv file</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="31b09-143">Schritt 3: Erstellen des Windows PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="31b09-143">Step 3: Create the PowerShell script</span></span>

<span data-ttu-id="31b09-p112">Kopieren Sie das PowerShell-Skript, und fügen Sie es in Editor ein. Speichern Sie die Datei an einem Ort, der leicht zu finden ist, mit dem Dateinamensuffix „.ps1“, z. B. \<Pfad\>CreateRetentionSchedule.ps1.</span><span class="sxs-lookup"><span data-stu-id="31b09-p112">Copy and paste the below PowerShell script into Notepad. Save the file by using a filename suffix of .ps1 in a location that's easy to find -- for example, \<path\>CreateRetentionSchedule.ps1.</span></span>
  
### <a name="powershell-script"></a><span data-ttu-id="31b09-146">PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="31b09-146">PowerShell script</span></span>

```
<#
. Steps: Import and Publish Compliance Tag
    ○ Load compliance tag csv file 
    ○ Validate csv file input
    ○ Create compliance tag
    ○ Create compliance policy
    ○ Publish compliance tag for the policy
    ○ Generate the log for tags creation
    ○ Generate the csv result for the tags created and published
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-connect-to-security-amp-compliance-center-powershell"></a><span data-ttu-id="31b09-147">Schritt 4: Herstellen einer Verbindung mit Security &amp; Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="31b09-147">Step 4: Connect to Security &amp; Compliance Center PowerShell</span></span>

<span data-ttu-id="31b09-148">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="31b09-148">Follow the steps here:</span></span>
  
- [<span data-ttu-id="31b09-149">Herstellen einer Verbindung mit Office 365 Security &amp; Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="31b09-149">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
## <a name="step-5-run-the-powershell-script-to-create-and-publish-the-retention-labels"></a><span data-ttu-id="31b09-150">Schritt 5: Ausführen des PowerShell Skripts zum Erstellen und Veröffentlichen der Aufbewahrungsbeschriftungen</span><span class="sxs-lookup"><span data-stu-id="31b09-150">Step 5: Run the PowerShell script to create and publish the retention labels</span></span>

<span data-ttu-id="31b09-151">Nachdem Sie eine Verbindung zu Security &amp; Compliance Center PowerShell hergestellt haben, führen Sie als Nächstes das Skript aus, das die Aufbewahrungsbeschriftungen erstellt und veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="31b09-151">After you've connected to Security &amp; Compliance Center PowerShell, next you run the script that creates and publishes the retention labels.</span></span>
  
1. <span data-ttu-id="31b09-152">Geben Sie in der Security &amp; Compliance Center PowerShell-Sitzung den Pfad gefolgt von den Zeichen .\ und dem Dateinamen des Skripts ein. Drücken Sie dann die EINGABETASTE, um das Skript auszuführen. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31b09-152">In the Security &amp; Compliance PowerShell session, enter the path, followed by the characters .\ and file name of the script, and then press ENTER to run the script - for example:</span></span>
    
  ```
  <path>.\CreateRetentionSchedule.ps1
  ```

    <span data-ttu-id="31b09-153">Sie werden aufgefordert, die Speicherorte der CSV-Dateien einzugeben, die Sie oben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="31b09-153">The script will prompt you for the locations of the .csv files that you created above.</span></span>
    
2. <span data-ttu-id="31b09-154">Geben Sie den Pfad gefolgt von den Zeichen .\ und dem Dateinamen der CSV-Datei ein. Drücken Sie dann die EINGABETASTE. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31b09-154">Enter the path, followed by the characters .\ and file name of the .csv file, and then press ENTER - for example:</span></span>
    
  ```
  <path>.\LabelsToCreate.csv
  ```

## <a name="step-6-view-the-log-file-with-the-results"></a><span data-ttu-id="31b09-155">Schritt 6: Anzeigen der Protokolldatei mit den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="31b09-155">Step 6: View the log file with the results</span></span>

<span data-ttu-id="31b09-p113">Wenn Sie das Skript ausführen, wird eine Protokolldatei generiert, in der jede Aktion sowie deren erfolgreiches oder fehlerhaftes Ausführen aufgezeichnet wird. Die Protokolldatei enthält alle Metadaten dazu, welche Aufbewahrungsbeschriftungen erstellt wurden und welche Aufbewahrungsbeschriftungen veröffentlicht wurden. Die Protokolldatei befindet sich an folgendem Speicherort. Beachten Sie, dass die Ziffern in dem Dateinamen variieren können.</span><span class="sxs-lookup"><span data-stu-id="31b09-p113">When you run the script, it generates a log file that records each action it took and whether the action succeeded or failed. The log file includes all metadata about the retention labels created and the retention labels published. You can find the log file at this location -- note that the digits in the file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


