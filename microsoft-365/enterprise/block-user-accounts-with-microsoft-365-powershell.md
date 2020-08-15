---
title: Blockieren von Microsoft 365-Benutzerkonten mit PowerShell
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
description: In diesem Artikel wird erläutert, wie Sie den Zugriff auf Microsoft 365-Konten mithilfe von PowerShell blockieren und aufheben.
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690527"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="198d3-103">Blockieren von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="198d3-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="198d3-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="198d3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="198d3-105">Durch das Blockieren des Zugriffs auf ein Microsoft 365-Konto wird verhindert, dass sich Benutzer mit dem Konto anmelden und auf die Dienste und Daten in Ihrer Microsoft 365-Organisation zugreifen.</span><span class="sxs-lookup"><span data-stu-id="198d3-105">Blocking access to a Microsoft 365 account prevents anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="198d3-106">Sie können PowerShell verwenden, um den Zugriff auf einzelne und mehrere Benutzerkonten zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="198d3-106">You can use PowerShell to block access to individual and multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="198d3-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="198d3-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="198d3-108">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="198d3-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="198d3-109">Blockieren des Zugriffs auf einzelne Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="198d3-109">Block access to individual user accounts</span></span>

<span data-ttu-id="198d3-110">Verwenden Sie die folgende Syntax, um ein einzelnes Benutzerkonto zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="198d3-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="198d3-111">Der Parameter-ObjectID im Cmdlet "AzureAD" akzeptiert entweder den Konto Anmeldenamen, der auch als Benutzerprinzipalname bezeichnet wird, oder die Objekt-ID des Kontos.</span><span class="sxs-lookup"><span data-stu-id="198d3-111">The -ObjectID parameter in the Set-AzureAD cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span> 
  
<span data-ttu-id="198d3-112">Dieses Beispiel blockiert den Zugriff auf das Benutzerkonto „fabricec@litwareinc.com“.</span><span class="sxs-lookup"><span data-stu-id="198d3-112">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="198d3-113">Führen Sie zum Aufheben der Blockierung dieses Benutzerkontos den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="198d3-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="198d3-114">Verwenden Sie die folgenden Befehle, um den UPN des Benutzerkontos basierend auf dem Anzeigenamen des Benutzers anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="198d3-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="198d3-115">In diesem Beispiel wird das Benutzerkonto UPN für den Benutzernamens Caleb Sills angezeigt.</span><span class="sxs-lookup"><span data-stu-id="198d3-115">This example displays the user account UPN for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="198d3-116">Verwenden Sie die folgenden Befehle, um ein Konto basierend auf dem Anzeigenamen des Benutzers zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="198d3-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="198d3-117">Sie können den blockierten Status eines Benutzerkontos jederzeit überprüfen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="198d3-117">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="198d3-118">Blockieren des Zugriffs auf mehrere Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="198d3-118">Block access to multiple user accounts</span></span>

<span data-ttu-id="198d3-119">Um den Zugriff auf mehrere Benutzerkonten zu blockieren, erstellen Sie eine Textdatei mit einem Konto-Anmeldenamen in jeder Zeile wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="198d3-119">To block access to multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="198d3-120">In den folgenden Befehlen lautet die Beispieltextdatei C:\My Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="198d3-120">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="198d3-121">Ersetzen Sie dies durch den Pfad und den Dateinamen Ihrer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="198d3-121">Replace this with the path and file name of your text file.</span></span>
  
<span data-ttu-id="198d3-122">Um den Zugriff auf die in der Textdatei aufgelisteten Konten zu blockieren, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="198d3-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="198d3-123">Um den Zugriff auf die in der Textdatei aufgelisteten Konten wieder freizugeben, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="198d3-123">To unblock the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="198d3-124">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="198d3-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="198d3-125">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="198d3-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="198d3-126">Blockieren des Zugriffs auf einzelne Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="198d3-126">Block access to individual user accounts</span></span>

<span data-ttu-id="198d3-127">Verwenden Sie die folgende Syntax, um den Zugriff auf ein einzelnes Benutzerkonto zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="198d3-127">Use the following syntax to block access to an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="198d3-128">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="198d3-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="198d3-129">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="198d3-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="198d3-130">Dieses Beispiel blockiert den Zugriff auf das Benutzerkonto „fabricec@litwareinc.com“.</span><span class="sxs-lookup"><span data-stu-id="198d3-130">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="198d3-131">Führen Sie zum Aufheben der Blockierung des Benutzerkontos den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="198d3-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="198d3-132">Sie können den blockierten Status eines Benutzerkontos jederzeit überprüfen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="198d3-132">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="198d3-133">Blockieren des Zugriffs auf mehrere Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="198d3-133">Block access to multiple user accounts</span></span>

<span data-ttu-id="198d3-134">Erstellen Sie zunächst eine Textdatei mit einem Konto in jeder Zeile wie folgt:</span><span class="sxs-lookup"><span data-stu-id="198d3-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="198d3-135">In den folgenden Befehlen lautet die Beispieltextdatei C:\My Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="198d3-135">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="198d3-136">Ersetzen Sie dies durch den Pfad und den Dateinamen Ihrer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="198d3-136">Replace this with the path and file name of your text file.</span></span>
    
<span data-ttu-id="198d3-137">Um den Zugriff auf die in der Textdatei aufgelisteten Konten zu blockieren, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="198d3-137">To block access to the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="198d3-138">Um den Zugriff auf die in der Textdatei aufgelisteten Konten wieder freizugeben, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="198d3-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="198d3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="198d3-139">See also</span></span>

[<span data-ttu-id="198d3-140">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="198d3-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="198d3-141">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="198d3-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="198d3-142">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="198d3-142">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
