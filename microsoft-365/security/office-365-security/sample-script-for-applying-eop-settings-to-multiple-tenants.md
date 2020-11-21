---
title: Beispielskript für EoP-Einstellungen – mehrere Mandanten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell Konfigurationseinstellungen auf Ihre Mandanten in Microsoft Exchange Online Protection (EoP) anwenden.
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376567"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Im folgenden Beispielskript können Microsoft Exchange Online Protection (EoP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Exchange Online PowerShell verwenden, um Konfigurationseinstellungen für Ihre Mandanten anzuzeigen und/oder anzuwenden.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:

1. Wenn Sie noch nicht vorhanden sind, [Installieren Sie das Modul Exchange Online v2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Erstellen Sie mithilfe einer Tabellen Kalkulations-app (beispielsweise Excel) eine CSV-Datei mit den folgenden Details:

   - Spalte username: das Konto, mit dem Sie eine Verbindung herstellen (beispielsweise `admin@contoso.onmicrosoft.com` ).
   - Cmdlet-Spalte: das auszuführende Cmdlet oder der Befehl (beispielsweise `Get-AcceptedDomain` oder `Get-AcceptedDomain | FT Name` ).

   Die Datei sieht wie folgt aus:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Speichern Sie die CSV-Datei an einem Speicherort, der leicht zu finden ist (beispielsweise c:\scripts\inputfile.csv).

4. Kopieren Sie das [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) -Skript in Editor, und speichern Sie die Datei an einem Speicherort, der leicht zu finden ist (beispielsweise c:\Scripts).

5. Führen Sie das Skript mit der folgenden Syntax aus:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier ein Beispiel:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Jeder Mandant wird bei angemeldet, und das Skript wird ausgeführt.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Möglicherweise müssen Sie die `Connect-IPPSSession` im Skript entstehende Reihe so ändern, dass Sie mit Ihrer Umgebung übereinstimmt. Beispielsweise erfordert Office 365 Deutschland einen anderen _ConnectionUri_ -Wert als der aktuelle Wert in einem Skript. Ausführliche Informationen finden Sie unter Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
  
# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
