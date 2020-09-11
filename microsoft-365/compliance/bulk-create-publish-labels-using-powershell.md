---
title: Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen mithilfe von PowerShell
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
ms.custom:
- seo-marvel-apr2020
description: Weitere Informationen zum Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen mithilfe von PowerShell über die Befehlszeile, unabhängig vom Microsoft 365 Compliance Center.
ms.openlocfilehash: 5b8bb7a08c9794139e840d59f9238d858e15dd4e
ms.sourcegitcommit: 2b8c3fc39a7cbd4ca35e98dca430d2470cd2c925
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47426982"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="ea491-103">Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea491-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="ea491-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="ea491-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ea491-105">Nachdem Sie sich entschieden haben, [Aufbewahrungsbezeichnungen](retention.md) zu verwenden, um Dokumente und E-Mails in Microsoft 365 aufzubewahren oder zu löschen, ist Ihnen vielleicht klar geworden, dass Sie viele und möglicherweise Hunderte von Aufbewahrungsbezeichnungen erstellen und veröffentlichen müssen.</span><span class="sxs-lookup"><span data-stu-id="ea491-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="ea491-106">Die empfohlene Methode zur Erstellung von skalierbaren Aufbewahrungsbezeichnungen ist die Verwendung eines [Dateiplans](file-plan-manager.md) vom Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ea491-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ea491-107">Alternativ können Sie hierzu auch [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea491-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="ea491-108">Verwenden Sie die Informationen, Vorlagendateien und Beispiele sowie das Skript in diesem Artikel, um Ihnen bei der Massenerstellung von Aufbewahrungsbezeichnungen zu helfen und diese in Richtlinien für Aufbewahrungsbezeichnungen zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="ea491-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="ea491-109">Anschließend können die Aufbewahrungsbezeichnungen von [Administratoren und Benutzern angebracht werden](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="ea491-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="ea491-110">Die bereitgestellten Anweisungen unterstützen keine Aufbewahrungsbezeichnungen, die automatisch auf Inhalte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea491-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="ea491-111">Übersicht:</span><span class="sxs-lookup"><span data-stu-id="ea491-111">Overview:</span></span> 

1. <span data-ttu-id="ea491-112">Erstellen Sie in Excel eine Liste Ihrer Aufbewahrungsbezeichnungen und eine Liste ihrer Aufbewahrungsbezeichnungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ea491-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="ea491-113">Verwenden Sie PowerShell, um die Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien in diesen Listen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea491-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="ea491-114">Haftungsausschluss</span><span class="sxs-lookup"><span data-stu-id="ea491-114">Disclaimer</span></span>

<span data-ttu-id="ea491-115">Die in diesem Artikel bereitgestellten Beispielskripts werden von keinem standardmäßigen Supportprogramm oder Dienst von Microsoft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea491-115">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="ea491-116">Die Beispielskripts werden wie besehen ohne jegliche Garantie zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ea491-116">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="ea491-117">Microsoft schließt ferner alle konkludenten Gewährleistungen, einschließlich, aber nicht beschränkt auf konkludente Gewährleistungen der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus.</span><span class="sxs-lookup"><span data-stu-id="ea491-117">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="ea491-118">Das gesamte Risiko, das mit der Verwendung oder Leistung der Beispielskripts und der Dokumentation einhergeht, liegt bei Ihnen.</span><span class="sxs-lookup"><span data-stu-id="ea491-118">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="ea491-119">In keinem Fall sind Microsoft, seine Autoren oder an der Erstellung, Produktion oder Übermittlung der Skripts beteiligte Personen für Schäden jeglicher Art (einschließlich und ohne Einschränkung Schäden durch Verlust entgangener Gewinne, Geschäftsunterbrechungen, Verlust von Geschäftsinformationen oder andere geldliche Verluste) haftbar, die aus der Nutzung bzw. Unfähigkeit zur Nutzung der Beispielskripts oder Dokumentation entstehen, auch wenn Microsoft auf die Möglichkeit solcher Schäden hingewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ea491-119">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="ea491-120">Schritt 1: Erstellen einer CSV-Datei für die Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ea491-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="ea491-121">Kopieren Sie die folgende CSV-Beispieldatei für eine Vorlage und Beispieleinträge für vier verschiedene Aufbewahrungsbezeichnungen und fügen Sie sie in Excel ein.</span><span class="sxs-lookup"><span data-stu-id="ea491-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="ea491-122">Konvertieren Text in Spalten: Registerkarte **Daten** \> **Text in Spalten** \> **Mit Trennzeichen** \> **Komma** \> **Allgemein**</span><span class="sxs-lookup"><span data-stu-id="ea491-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="ea491-123">Ersetzen Sie die Beispiele durch Einträge für Ihre eigenen Aufbewahrungsbezeichnungen und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ea491-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="ea491-124">Weitere Informationen zu den Parameterwerten finden Sie unter [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span><span class="sxs-lookup"><span data-stu-id="ea491-124">For more information about the parameter values, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>

3. <span data-ttu-id="ea491-125">Speichern Sie das Arbeitsblatt als CSV-Datei an einem Ort, der für einen späteren Schritt leicht zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="ea491-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="ea491-126">Beispiel: C:\>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="ea491-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="ea491-127">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="ea491-127">Notes:</span></span>

- <span data-ttu-id="ea491-p106">Wenn die CSV-Datei eine Aufbewahrungsbeschriftung mit demselben Namen wie eine bereits vorhandene Aufbewahrungsbeschriftung enthält, überspringt das Skript die Erstellung der Aufbewahrungsbeschriftung. Es werden keine doppelten Aufbewahrungsbeschriftungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea491-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="ea491-130">Ändern oder benennen Sie die Spaltenüberschriften aus der mitgelieferten CSV-Beispieldatei nicht um, sonst schlägt das Skript fehl.</span><span class="sxs-lookup"><span data-stu-id="ea491-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="ea491-131">CSV-Beispieldatei für Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ea491-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="ea491-132">Schritt 2: Erstellen einer CSV-Datei für die Aufbewahrungsbezeichnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ea491-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="ea491-133">Kopieren Sie die folgende CSV-Beispieldatei für eine Vorlage und Beispieleinträge für vier verschiedene Aufbewahrungsbezeichnungsrichtlinien und fügen Sie sie in Excel ein.</span><span class="sxs-lookup"><span data-stu-id="ea491-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="ea491-134">Konvertieren Text in Spalten: Registerkarte **Daten** \> **Text in Spalten** \> **Mit Trennzeichen** \> **Komma** \> **Allgemein**</span><span class="sxs-lookup"><span data-stu-id="ea491-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="ea491-135">Ersetzen Sie die Beispiele durch Einträge für Ihre eigenen Aufbewahrungsbezeichnungsrichtlinien und deren Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ea491-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="ea491-136">Weitere Informationen zu den Parameterwerten für dieses Cmdlet finden Sie unter [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="ea491-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="ea491-137">Speichern Sie das Arbeitsblatt als CSV-Datei an einem Ort, der für einen späteren Schritt leicht zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="ea491-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="ea491-138">Beispiel: `<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="ea491-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="ea491-139">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="ea491-139">Notes:</span></span>
  
- <span data-ttu-id="ea491-p109">Wenn die CSV-Datei eine Aufbewahrungsbeschriftungsrichtlinie mit demselben Namen wie eine bereits vorhandene enthält, überspringt das Skript die Erstellung der Aufbewahrungsbeschriftungsrichtlinie. Es werden keine doppelten Aufbewahrungsbeschriftungsrichtlinien erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea491-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="ea491-142">Ändern oder benennen Sie die Spaltenüberschriften aus der mitgelieferten CSV-Beispieldatei nicht um, sonst schlägt das Skript fehl.</span><span class="sxs-lookup"><span data-stu-id="ea491-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="ea491-143">CSV-Beispieldatei für Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ea491-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="ea491-144">Schritt 3: Erstellen des Windows PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="ea491-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="ea491-145">Kopieren Sie das folgende PowerShell-Skript, und fügen Sie es in Editor ein.</span><span class="sxs-lookup"><span data-stu-id="ea491-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="ea491-146">Speichern Sie die Datei unter Verwendung der Dateinamenerweiterung **.ps1** an einem leicht auffindbaren Speicherort.</span><span class="sxs-lookup"><span data-stu-id="ea491-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="ea491-147">Beispiel: `<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="ea491-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="ea491-148">Hinweise:</span><span class="sxs-lookup"><span data-stu-id="ea491-148">Notes:</span></span>

- <span data-ttu-id="ea491-149">Das Skript fordert Sie auf, die beiden Quelldateien anzugeben, die Sie in den beiden vorherigen Schritten erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="ea491-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="ea491-150">Wenn Sie die Quelldatei zur Erstellung der Aufbewahrungsbezeichnungen nicht angeben, fährt das Skript mit der Erstellung der Aufbewahrungsbezeichnungsrichtlinien fort.</span><span class="sxs-lookup"><span data-stu-id="ea491-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="ea491-151">Wenn Sie die Quelldatei nicht angeben, um die Aufbewahrungsbezeichnungsrichtlinien zu erstellen, erstellt das Skript nur die Aufbewahrungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="ea491-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="ea491-152">Das Skript generiert eine Protokolldatei, in der jede Aktion, die ausgeführt wurde, aufgezeichnet wird und angegeben wird, ob die Aktion erfolgreich war oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ea491-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="ea491-153">Im letzten Schritt finden Sie Anweisungen zum Auffinden dieser Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="ea491-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="ea491-154">PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="ea491-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
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

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="ea491-155">Schritt 4: Ausführen des PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="ea491-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="ea491-156">Zuerst, [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea491-156">First, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="ea491-157">Führen Sie dann das Skript aus, durch das die Aufbewahrungsbezeichnungen erstellt und veröffentlicht werden:</span><span class="sxs-lookup"><span data-stu-id="ea491-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="ea491-158">Geben Sie in Ihrer Security & Compliance Center PowerShell-Sitzung den Pfad gefolgt von den Zeichen `.\` und dem Dateinamen des Skripts ein. Drücken Sie dann die EINGABETASTE, um das Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ea491-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="ea491-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea491-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="ea491-160">Das Skript fordert Sie auf, die Speicherorte der CSV-Dateien anzugeben, die Sie in den vorherigen Schritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ea491-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="ea491-161">Geben Sie den Pfad gefolgt von den Zeichen `.\` und dem Dateinamen der CSV-Datei ein. Drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="ea491-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="ea491-162">Beispiel: Bei der ersten Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="ea491-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="ea491-163">Schritt 5: Anzeigen der Protokolldatei mit den Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="ea491-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="ea491-164">Verwenden Sie die Protokolldatei, die das Skript erstellt hat, um die Ergebnisse zu überprüfen und alle Fehler zu identifizieren, die behoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ea491-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="ea491-165">Sie finden die Protokolldatei an folgenden Speicherort, wobei die Ziffern im Beispieldateinamen variieren.</span><span class="sxs-lookup"><span data-stu-id="ea491-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


