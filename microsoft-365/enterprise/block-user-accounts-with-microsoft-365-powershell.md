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
description: Verwenden von PowerShell zum Blockieren und Aufheben der Blockierung des Zugriffs auf Microsoft 365 Konten.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754680"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="8f417-103">Blockieren Microsoft 365 Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f417-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="8f417-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8f417-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8f417-105">Wenn Sie den Zugriff auf ein Microsoft 365 sperren, verhindern Sie, dass sich alle Personen mit dem Konto anmelden und auf die Dienste und Daten in Ihrer Microsoft 365 zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8f417-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="8f417-106">Sie können PowerShell verwenden, um den Zugriff auf einzelne oder mehrere Benutzerkonten zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="8f417-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8f417-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="8f417-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8f417-108">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="8f417-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="8f417-109">Blockieren des Zugriffs auf einzelne Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="8f417-109">Block access to individual user accounts</span></span>

<span data-ttu-id="8f417-110">Verwenden Sie die folgende Syntax, um ein einzelnes Benutzerkonto zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="8f417-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="8f417-111">Der *-ObjectID-Parameter* im **Cmdlet Set-AzureAD** akzeptiert entweder den Konto-Anmeldenamen, auch Als Benutzerprinzipalname bezeichnet, oder die Objekt-ID des Kontos.</span><span class="sxs-lookup"><span data-stu-id="8f417-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="8f417-112">In diesem Beispiel wird der Zugriff auf das Benutzerkonto *fabricec@litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="8f417-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="8f417-113">Führen Sie zum Aufheben der Blockierung dieses Benutzerkontos den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8f417-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="8f417-114">Verwenden Sie die folgenden Befehle, um den Benutzerkonto-UPN basierend auf dem Anzeigenamen des Benutzers anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8f417-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="8f417-115">In diesem Beispiel wird der Benutzerkonto-UPN für den Benutzer *Caleb Sills angezeigt.*</span><span class="sxs-lookup"><span data-stu-id="8f417-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="8f417-116">Verwenden Sie die folgenden Befehle, um ein Konto basierend auf dem Anzeigenamen des Benutzers zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="8f417-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="8f417-117">Verwenden Sie den folgenden Befehl, um den blockierten Status eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8f417-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="8f417-118">Blockieren mehrerer Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="8f417-118">Block multiple user accounts</span></span>

<span data-ttu-id="8f417-119">Um den Zugriff für mehrere Benutzerkonten zu blockieren, erstellen Sie eine Textdatei, die einen Konto-Anmeldenamen in jeder Zeile wie dies enthält:</span><span class="sxs-lookup"><span data-stu-id="8f417-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="8f417-120">In den folgenden Befehlen ist die Beispieltextdatei *C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="8f417-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="8f417-121">Ersetzen Sie diesen Dateinamen durch den Pfad und Dateinamen ihrer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="8f417-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="8f417-122">Um den Zugriff auf die in der Textdatei aufgelisteten Konten zu blockieren, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8f417-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="8f417-123">Führen Sie den folgenden Befehl aus, um die Blockierung der Konten zu aufheben, die in der Textdatei aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="8f417-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8f417-124">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f417-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8f417-125">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="8f417-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="8f417-126">Blockieren einzelner Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="8f417-126">Block individual user accounts</span></span>

<span data-ttu-id="8f417-127">Verwenden Sie die folgende Syntax, um den Zugriff für ein einzelnes Benutzerkonto zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="8f417-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="8f417-128">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory Modul für Windows PowerShell-Modul und Cmdlets, die *Msol* im Namen haben.</span><span class="sxs-lookup"><span data-stu-id="8f417-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="8f417-129">Sie müssen diese Cmdlets von einem Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f417-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="8f417-130">In diesem Beispiel wird der Zugriff auf das Benutzerkonto *fabricec \@ litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="8f417-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="8f417-131">Führen Sie zum Aufheben der Blockierung des Benutzerkontos den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8f417-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="8f417-132">Führen Sie den folgenden Befehl aus, um den blockierten Status eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8f417-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="8f417-133">Blockieren des Zugriffs für mehrere Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="8f417-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="8f417-134">Erstellen Sie zunächst eine Textdatei, die ein Konto in jeder Zeile wie dies enthält:</span><span class="sxs-lookup"><span data-stu-id="8f417-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="8f417-135">In den folgenden Befehlen ist die Beispieltextdatei *C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="8f417-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="8f417-136">Ersetzen Sie diesen Dateinamen durch den Pfad und Dateinamen ihrer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="8f417-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="8f417-137">Führen Sie den folgenden Befehl aus, um den Zugriff für die konten zu blockieren, die in der Textdatei aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="8f417-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="8f417-138">Um den Zugriff auf die in der Textdatei aufgelisteten Konten wieder freizugeben, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8f417-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="8f417-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f417-139">See also</span></span>

[<span data-ttu-id="8f417-140">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f417-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8f417-141">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f417-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8f417-142">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f417-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
