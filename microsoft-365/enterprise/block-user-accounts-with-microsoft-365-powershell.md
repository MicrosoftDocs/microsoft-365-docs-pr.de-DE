---
title: Blockieren Microsoft 365 Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Verwenden von PowerShell zum Blockieren und Aufheben des Zugriffs auf Microsoft 365 Konten.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287221"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="06e2c-103">Blockieren Microsoft 365 Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06e2c-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="06e2c-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="06e2c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="06e2c-105">Wenn Sie den Zugriff auf ein Microsoft 365 Konto blockieren, verhindern Sie, dass jemand das Konto verwendet, um sich anzumelden und auf die Dienste und Daten in Ihrer Microsoft 365 Organisation zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="06e2c-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="06e2c-106">Sie können PowerShell verwenden, um den Zugriff auf einzelne oder mehrere Benutzerkonten zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="06e2c-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="06e2c-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="06e2c-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="06e2c-108">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)her.</span><span class="sxs-lookup"><span data-stu-id="06e2c-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="06e2c-109">Zugriff auf einzelne Benutzerkonten blockieren</span><span class="sxs-lookup"><span data-stu-id="06e2c-109">Block access to individual user accounts</span></span>

<span data-ttu-id="06e2c-110">Verwenden Sie die folgende Syntax, um ein einzelnes Benutzerkonto zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="06e2c-110">Use the following syntax to block an individual user account:</span></span>

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="06e2c-111">Der Parameter *"-ObjectID"* im Cmdlet **"Set-AzureAD"** akzeptiert entweder den Anmeldenamen des Kontos, der auch als Benutzerprinzipalname bezeichnet wird, oder die Objekt-ID des Kontos.</span><span class="sxs-lookup"><span data-stu-id="06e2c-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>

<span data-ttu-id="06e2c-112">In diesem Beispiel wird der Zugriff auf das Benutzerkonto *fabricec@litwareinc.com* blockiert.</span><span class="sxs-lookup"><span data-stu-id="06e2c-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="06e2c-113">Führen Sie zum Aufheben der Blockierung dieses Benutzerkontos den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="06e2c-113">To unblock this user account, run the following command:</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="06e2c-114">Verwenden Sie die folgenden Befehle, um den UPN des Benutzerkontos basierend auf dem Anzeigenamen des Benutzers anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="06e2c-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="06e2c-115">In diesem Beispiel wird der UpN des Benutzerkontos für den Benutzer  *Caleb Sills* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06e2c-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="06e2c-116">Verwenden Sie die folgenden Befehle, um ein Konto basierend auf dem Anzeigenamen des Benutzers zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="06e2c-116">To block an account based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="06e2c-117">Verwenden Sie den folgenden Befehl, um den Sperrstatus eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="06e2c-117">To check the blocked status of a user account use the following command:</span></span>

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="06e2c-118">Blockieren mehrerer Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="06e2c-118">Block multiple user accounts</span></span>

<span data-ttu-id="06e2c-119">Um den Zugriff für mehrere Benutzerkonten zu blockieren, erstellen Sie eine Textdatei mit einem Konto-Anmeldenamen in jeder Zeile wie folgt:</span><span class="sxs-lookup"><span data-stu-id="06e2c-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="06e2c-120">In den folgenden Befehlen lautet die Beispieltextdatei *"C:\My Documents\Accounts.txt".*</span><span class="sxs-lookup"><span data-stu-id="06e2c-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="06e2c-121">Ersetzen Sie diesen Dateinamen durch den Pfad und den Dateinamen ihrer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="06e2c-121">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="06e2c-122">Um den Zugriff auf die in der Textdatei aufgelisteten Konten zu blockieren, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="06e2c-122">To block access to the accounts listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

<span data-ttu-id="06e2c-123">Führen Sie den folgenden Befehl aus, um die Blockierung der in der Textdatei aufgeführten Konten aufzuheben:</span><span class="sxs-lookup"><span data-stu-id="06e2c-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="06e2c-124">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06e2c-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="06e2c-125">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)her.</span><span class="sxs-lookup"><span data-stu-id="06e2c-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="block-individual-user-accounts"></a><span data-ttu-id="06e2c-126">Blockieren einzelner Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="06e2c-126">Block individual user accounts</span></span>

<span data-ttu-id="06e2c-127">Verwenden Sie die folgende Syntax, um den Zugriff für ein einzelnes Benutzerkonto zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="06e2c-127">Use the following syntax to block access for an individual user account:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="06e2c-128">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets, die *Msol* im Namen haben.</span><span class="sxs-lookup"><span data-stu-id="06e2c-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="06e2c-129">Sie müssen diese Cmdlets über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="06e2c-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="06e2c-130">In diesem Beispiel wird der Zugriff auf das Benutzerkonto *fabricec \@ litwareinc.com* blockiert.</span><span class="sxs-lookup"><span data-stu-id="06e2c-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="06e2c-131">Führen Sie zum Aufheben der Blockierung des Benutzerkontos den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="06e2c-131">To unblock the user account, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="06e2c-132">Führen Sie den folgenden Befehl aus, um den Blockierten Status eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="06e2c-132">To check the blocked status of a user account run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="06e2c-133">Zugriff für mehrere Benutzerkonten blockieren</span><span class="sxs-lookup"><span data-stu-id="06e2c-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="06e2c-134">Erstellen Sie zunächst eine Textdatei mit einem Konto in jeder Zeile wie folgt:</span><span class="sxs-lookup"><span data-stu-id="06e2c-134">First, create a text file that contains one account on each line like this:</span></span>

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="06e2c-135">In den folgenden Befehlen lautet die Beispieltextdatei *"C:\My Documents\Accounts.txt".*</span><span class="sxs-lookup"><span data-stu-id="06e2c-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="06e2c-136">Ersetzen Sie diesen Dateinamen durch den Pfad und den Dateinamen ihrer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="06e2c-136">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="06e2c-137">Führen Sie den folgenden Befehl aus, um den Zugriff auf die in der Textdatei aufgeführten Konten zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="06e2c-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="06e2c-138">Um den Zugriff auf die in der Textdatei aufgelisteten Konten wieder freizugeben, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="06e2c-138">To unblock the accounts listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="06e2c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06e2c-139">See also</span></span>

[<span data-ttu-id="06e2c-140">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06e2c-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="06e2c-141">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06e2c-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="06e2c-142">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06e2c-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
