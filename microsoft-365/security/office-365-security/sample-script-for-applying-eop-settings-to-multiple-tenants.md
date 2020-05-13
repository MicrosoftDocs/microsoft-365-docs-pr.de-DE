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
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209139"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten

Mit dem folgenden Beispielskript können Microsoft Exchange Online Protection (EOP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Konfigurationseinstellungen für ihre Mandanten mithilfe von Windows PowerShell anwenden.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:

1. Erstellen Sie mithilfe einer Anwendung wie Excel eine CSV-Datei (zum Beispiel c:\scripts\inputfile.csv):

2. Geben Sie in der CSV-Datei zwei Spaltennamen an: UserName und Cmdlet.

3. Geben Sie für jede Zeile in der CSV-Datei den Administratornamen des Mandanten in die Spalte "UserName" und das für diesen Mandanten auszuführende Cmdlet in die Spalte "Cmdlet" ein. Verwenden Sie beispielsweise admin@contoso.com und Get-AcceptedDomain.

4. Kopieren Sie das [Skript runcmdletonmultipletenants. ps1](#runcmdletonmultipletenantsps1) -Skript in Editor, und speichern Sie die Datei an einem Speicherort, der leicht zu finden ist (beispielsweise c:\Scripts).

5. Führen Sie das Skript mit der folgenden Syntax aus:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier ein Beispiel:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. Jeder Mandant wird bei angemeldet, und das Skript wird ausgeführt.

## <a name="runcmdletonmultipletenantsps1"></a>Skript runcmdletonmultipletenants. ps1

```powershell
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
