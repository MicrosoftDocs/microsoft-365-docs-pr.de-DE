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
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206554"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="bd54a-103">Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="bd54a-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bd54a-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="bd54a-104">**Applies to**</span></span>
-  [<span data-ttu-id="bd54a-105">Exchange Online Protection eigenständig</span><span class="sxs-lookup"><span data-stu-id="bd54a-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="bd54a-106">Mit dem folgenden Beispielskript können Microsoft Exchange Online Protection (EOP)-Administratoren, die mehrere Mandanten (Unternehmen) verwalten, Exchange Online PowerShell zum Anzeigen und/oder Anwenden von Konfigurationseinstellungen auf ihre Mandanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd54a-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="bd54a-107">So führen Sie ein Skript oder Cmdlet auf mehreren Mandanten aus:</span><span class="sxs-lookup"><span data-stu-id="bd54a-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="bd54a-108">Falls noch nicht, installieren Sie das [Exchange Online V2-Modul](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="bd54a-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="bd54a-109">Erstellen Sie mithilfe einer Tabellenkalkulations-App (z. B. Excel) eine .csv datei mit den folgenden Details:</span><span class="sxs-lookup"><span data-stu-id="bd54a-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="bd54a-110">Spalte "UserName": Das Konto, mit dem Sie eine Verbindung herstellen (z. B. `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="bd54a-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="bd54a-111">Cmdletspalte: Das auszuführende Cmdlet oder der auszuführende Befehl (z. B. `Get-AcceptedDomain` oder `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="bd54a-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="bd54a-112">Die Datei sieht wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="bd54a-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="bd54a-113">Speichern Sie .csv Datei an einem Speicherort, der leicht zu finden ist (z. B. c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="bd54a-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="bd54a-114">Kopieren Sie [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) skript in Editor, und speichern Sie die Datei dann an einem speicherort, der leicht zu finden ist (z. B. c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="bd54a-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="bd54a-115">Führen Sie das Skript mit der folgenden Syntax aus:</span><span class="sxs-lookup"><span data-stu-id="bd54a-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="bd54a-116">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bd54a-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="bd54a-117">Jeder Mandant ist bei angemeldet, und das Skript wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd54a-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="bd54a-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="bd54a-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="bd54a-119">Möglicherweise müssen Sie die Zeile `Connect-IPPSSession` im Skript an Ihre Umgebung ändern.</span><span class="sxs-lookup"><span data-stu-id="bd54a-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="bd54a-120">Beispielsweise erfordert Office 365 Deutschland einen anderen _ConnectionUri-Wert_ als der aktuelle Wert in einem Skript.</span><span class="sxs-lookup"><span data-stu-id="bd54a-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="bd54a-121">Weitere Informationen finden Sie unter Verbinden to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="bd54a-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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