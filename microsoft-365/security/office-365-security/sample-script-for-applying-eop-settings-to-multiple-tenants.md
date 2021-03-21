---
title: Beispielskript für EOP-Einstellungen – mehrere Mandanten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um Konfigurationseinstellungen auf Ihre Mandanten in Microsoft Exchange Online Protection (EOP) anzuwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928508"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

Mit dem folgenden Beispielskript können Microsoft Exchange Online Protection (EOP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Exchange Online PowerShell verwenden, um Konfigurationseinstellungen für ihre Mandanten ein- und/oder anzuwenden.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:

1. Falls noch nicht, installieren Sie [das Exchange Online V2-Modul](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Erstellen Sie mithilfe einer Tabellenkalkulations-App (z. B. Excel) eine CSV-Datei mit den folgenden Details:

   - Spalte "UserName": Das Konto, mit dem Sie eine Verbindung herstellen (z. B. `admin@contoso.onmicrosoft.com` ).
   - Cmdletspalte: Das auszuführende Cmdlet oder der auszuführende Befehl (z. B. `Get-AcceptedDomain` oder `Get-AcceptedDomain | FT Name` ).

   Die Datei sieht wie dies aus:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Speichern Sie die CSV-Datei an einem Speicherort, der leicht zu finden ist (z. B. c:\scripts\inputfile.csv).

4. Kopieren Sie [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) Skript in Editor, und speichern Sie die Datei dann an einem speicherort, der leicht zu finden ist (z. B. c:\scripts).

5. Führen Sie das Skript mit der folgenden Syntax aus:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier ein Beispiel:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Jeder Mandant ist bei angemeldet, und das Skript wird ausgeführt.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Möglicherweise müssen Sie die Zeile `Connect-IPPSSession` im Skript an Ihre Umgebung ändern. Beispielsweise erfordert Office 365 Deutschland einen anderen _ConnectionUri-Wert_ als der aktuelle Wert in einem Skript. Weitere Informationen finden Sie unter Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

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