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
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615864"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="4788f-103">Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="4788f-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4788f-104">Im folgenden Beispielskript können Microsoft Exchange Online Protection (EoP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Exchange Online PowerShell verwenden, um Konfigurationseinstellungen für Ihre Mandanten anzuzeigen und/oder anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4788f-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="4788f-105">So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:</span><span class="sxs-lookup"><span data-stu-id="4788f-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="4788f-106">Wenn Sie noch nicht vorhanden sind, [Installieren Sie das Modul Exchange Online v2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="4788f-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="4788f-107">Erstellen Sie mithilfe einer Tabellen Kalkulations-app (beispielsweise Excel) eine CSV-Datei mit den folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="4788f-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="4788f-108">Spalte username: das Konto, mit dem Sie eine Verbindung herstellen (beispielsweise `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="4788f-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="4788f-109">Cmdlet-Spalte: das auszuführende Cmdlet oder der Befehl (beispielsweise `Get-AcceptedDomain` oder `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="4788f-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="4788f-110">Die Datei sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4788f-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="4788f-111">Speichern Sie die CSV-Datei an einem Speicherort, der leicht zu finden ist (beispielsweise c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="4788f-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="4788f-112">Kopieren Sie das [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) -Skript in Editor, und speichern Sie die Datei an einem Speicherort, der leicht zu finden ist (beispielsweise c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="4788f-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="4788f-113">Führen Sie das Skript mit der folgenden Syntax aus:</span><span class="sxs-lookup"><span data-stu-id="4788f-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="4788f-114">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4788f-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="4788f-115">Jeder Mandant wird bei angemeldet, und das Skript wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4788f-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="4788f-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="4788f-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="4788f-117">Möglicherweise müssen Sie die `Connect-IPPSSession` im Skript entstehende Reihe so ändern, dass Sie mit Ihrer Umgebung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4788f-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="4788f-118">Beispielsweise erfordert Office 365 Deutschland einen anderen _ConnectionUri_ -Wert als der aktuelle Wert in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="4788f-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="4788f-119">Ausführliche Informationen finden Sie unter Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4788f-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
