---
title: Beispielskript für EoP-Einstellungen – mehrere Mandanten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell Konfigurationseinstellungen auf Ihre Mandanten in Microsoft Exchange Online Protection (EoP) anwenden.
ms.openlocfilehash: b875a6c7ba53f459a73699b250ee5ed4a206f1b1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035930"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten

Mit dem folgenden Beispielskript können Microsoft Exchange Online Protection (EOP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Konfigurationseinstellungen für ihre Mandanten mithilfe von Windows PowerShell anwenden.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:

1. Erstellen Sie mithilfe einer Anwendung wie Excel eine CSV-Datei (zum Beispiel c:\scripts\inputfile.csv):

2. Geben Sie in der CSV-Datei zwei Spaltennamen an: UserName und Cmdlet.

3. Geben Sie für jede Zeile in der CSV-Datei den Administratornamen des Mandanten in die Spalte "UserName" und das für diesen Mandanten auszuführende Cmdlet in die Spalte "Cmdlet" ein. Verwenden Sie beispielsweise admin@contoso.com und Get-AcceptedDomain.

4. Kopieren Sie das Skript [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) in einen Editor wie Notepad, und speichern Sie die Datei dann an einem Speicherort (wie c:\scripts), an dem Sie PS1-Dateien leicht finden können.

5. Führen Sie das Skript mit der folgenden Syntax aus:

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier ein Beispiel:

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. Jeder Mandant wird angemeldet, und das Cmdlet wird ausgeführt.

## <a name="runcmdletonmultipletenantsps1"></a>Skript runcmdletonmultipletenants. ps1

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
