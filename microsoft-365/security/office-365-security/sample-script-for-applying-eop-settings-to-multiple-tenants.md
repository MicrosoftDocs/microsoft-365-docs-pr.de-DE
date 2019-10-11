---
title: Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
description: Mit dem folgenden Beispielskript können Microsoft Exchange Online Protection (EOP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Konfigurationseinstellungen für ihre Mandanten mithilfe von Windows PowerShell anwenden.
ms.openlocfilehash: 17e63bada043bd03a3f3f1a9f2a27dced1a23422
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441252"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="aaf8a-103">Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="aaf8a-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="aaf8a-104">Mit dem folgenden Beispielskript können Microsoft Exchange Online Protection (EOP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Konfigurationseinstellungen für ihre Mandanten mithilfe von Windows PowerShell anwenden.</span><span class="sxs-lookup"><span data-stu-id="aaf8a-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="aaf8a-105">So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:</span><span class="sxs-lookup"><span data-stu-id="aaf8a-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="aaf8a-106">Erstellen Sie mithilfe einer Anwendung wie Excel eine CSV-Datei (zum Beispiel c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="aaf8a-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="aaf8a-107">Geben Sie in der CSV-Datei zwei Spaltennamen an: UserName und Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aaf8a-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="aaf8a-p101">Geben Sie für jede Zeile in der CSV-Datei den Administratornamen des Mandanten in die Spalte "UserName" und das für diesen Mandanten auszuführende Cmdlet in die Spalte "Cmdlet" ein. Verwenden Sie beispielsweise admin@contoso.com und Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="aaf8a-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="aaf8a-110">Kopieren Sie das Skript [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) in einen Editor wie Notepad, und speichern Sie die Datei dann an einem Speicherort (wie c:\scripts), an dem Sie PS1-Dateien leicht finden können.</span><span class="sxs-lookup"><span data-stu-id="aaf8a-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script to an editor like Notepad, and then save the file to a location (like c:\scripts) that makes .ps1 files easy to find.</span></span>

5. <span data-ttu-id="aaf8a-111">Führen Sie das Skript mit der folgenden Syntax aus:</span><span class="sxs-lookup"><span data-stu-id="aaf8a-111">Run the script by using the following syntax:</span></span>

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="aaf8a-112">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="aaf8a-112">Here's an example:</span></span>

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="aaf8a-113">Jeder Mandant wird angemeldet, und das Cmdlet wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aaf8a-113">Each tenant will be logged on to, and the cmdlet will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="aaf8a-114">Skript runcmdletonmultipletenants. ps1</span><span class="sxs-lookup"><span data-stu-id="aaf8a-114">RunCmdletOnMultipleTenants.ps1</span></span>

```Powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
