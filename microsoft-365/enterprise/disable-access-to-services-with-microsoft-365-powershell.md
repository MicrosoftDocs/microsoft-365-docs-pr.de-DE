---
title: Deaktivieren des Zugriffs auf Microsoft 365-Dienste mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um den Zugriff auf Microsoft 365-Dienste für Benutzer zu deaktivieren.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690508"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="94693-103">Deaktivieren des Zugriffs auf Microsoft 365-Dienste mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="94693-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="94693-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="94693-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94693-105">Wenn einem Microsoft 365-Konto eine Lizenz aus einem Lizenzierungs Plan zugewiesen wird, werden dem Benutzer die Microsoft 365-Dienste von dieser Lizenz zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="94693-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="94693-106">Sie können jedoch die Microsoft 365-Dienste steuern, auf die der Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="94693-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="94693-107">Beispielsweise können Sie den Zugriff darauf deaktivieren, auch wenn die Lizenz den Zugriff auf den SharePoint Online Dienst zulässt.</span><span class="sxs-lookup"><span data-stu-id="94693-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="94693-108">Sie können PowerShell verwenden, um den Zugriff auf eine beliebige Anzahl von Diensten für einen bestimmten Lizenzierungs Plan für zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="94693-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="94693-109">ein einzelnes Konto</span><span class="sxs-lookup"><span data-stu-id="94693-109">An individual account.</span></span>
- <span data-ttu-id="94693-110">eine Gruppe von Konten</span><span class="sxs-lookup"><span data-stu-id="94693-110">A group of accounts.</span></span>
- <span data-ttu-id="94693-111">Alle Konten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="94693-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="94693-112">Es gibt Microsoft 365-Dienstabhängigkeiten, die verhindern können, dass Sie einen bestimmten Dienst deaktivieren, wenn andere Dienste davon abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="94693-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="94693-113">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94693-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="94693-114">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="94693-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="94693-115">Verwenden Sie anschließend diesen Befehl, um die verfügbaren Lizenzierungs Pläne anzuzeigen, die auch als AccountSkuIds bezeichnet werden:</span><span class="sxs-lookup"><span data-stu-id="94693-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="94693-116">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="94693-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="94693-117">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="94693-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="94693-118">Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="94693-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="94693-119">Informationen zu den vor-und nach Ergebnissen der Verfahren in diesem Thema finden Sie unter [View Account License and Servicedetails with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="94693-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="94693-120">Ein PowerShell-Skript steht zur Verfügung, das die in diesem Thema erläuterten Verfahren automatisiert.</span><span class="sxs-lookup"><span data-stu-id="94693-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="94693-121">Insbesondere können Sie mit dem Skriptdienste in Ihrer Microsoft 365-Organisation anzeigen und deaktivieren, einschließlich Sway.</span><span class="sxs-lookup"><span data-stu-id="94693-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="94693-122">Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Sway mit PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="94693-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="94693-123">Deaktivieren bestimmter Microsoft 365-Dienste für bestimmte Benutzer für einen bestimmten Lizenzierungs Plan</span><span class="sxs-lookup"><span data-stu-id="94693-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="94693-124">Führen Sie die folgenden Schritte aus, um eine bestimmte Gruppe von Microsoft 365-Diensten für Benutzer für einen bestimmten Lizenzierungs Plan zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="94693-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="94693-125">Schritt 1: Identifizieren der unerwünschten Dienste im Lizenzierungs Plan mithilfe der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="94693-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="94693-126">Im folgenden Beispiel wird ein **licenseoptions** -Objekt erstellt, das die Office-und SharePoint Online-Dienste im Lizenzierungs Plan mit dem Namen `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="94693-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="94693-127">Schritt 2: Verwenden Sie das **licenseoptions** -Objekt aus Schritt 1 für einen oder mehrere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="94693-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="94693-128">Wenn Sie ein neues Konto zu erstellen möchten, für das die Dienste deaktiviert sind, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="94693-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="94693-129">Im folgenden Beispiel wird ein neues Konto für Allie Bellew erstellt, das die Lizenz zuweist und die in Schritt 1 beschriebenen Dienste deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="94693-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="94693-130">Weitere Informationen zum Erstellen von Benutzerkonten in PowerShell für Microsoft 365 finden Sie unter [Erstellen von Benutzerkonten mit PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="94693-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="94693-131">Verwenden Sie die folgende Syntax, um die Dienste für einen vorhandenen lizenzierten Benutzer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="94693-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="94693-132">In diesem Beispiel werden die Dienste für den Benutzer „BelindaN@litwareinc.com“ deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="94693-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="94693-133">Um die in Schritt 1 beschriebenen Dienste für alle vorhandenen lizenzierten Benutzer zu deaktivieren, geben Sie den Namen Ihres Microsoft 365-Plans in der Anzeige des Cmdlets **Get-MsolAccountSku** (wie **litwareinc: ENTERPRISEPACK**) ein, und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="94693-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="94693-134">Wenn Sie das Cmdlet **Get-MsolUser** ohne den Parameter _all_ verwenden, werden nur die ersten 500-Benutzerkonten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94693-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="94693-135">Verwenden Sie eine der folgenden Methoden, um die Dienste für eine Gruppe von vorhandenen Benutzern zu deaktivieren und die Benutzer zu identifizieren:</span><span class="sxs-lookup"><span data-stu-id="94693-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="94693-136">**Methode 1. Filtern der Konten basierend auf einem vorhandenen Kontoattribut**</span><span class="sxs-lookup"><span data-stu-id="94693-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="94693-137">Verwenden Sie hierzu die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="94693-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="94693-138">Im folgenden Beispiel werden die Dienste für Benutzer in der Vertriebsabteilung in den Vereinigten Staaten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="94693-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="94693-139">**Methode 2: Verwenden einer Liste bestimmter Konten**</span><span class="sxs-lookup"><span data-stu-id="94693-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="94693-140">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="94693-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="94693-141">Erstellen Sie eine Textdatei wie die folgende, die in jeder Zeile ein Konto enthält:</span><span class="sxs-lookup"><span data-stu-id="94693-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="94693-142">In diesem Beispiel lautet die Textdatei C: \\ My Documents \\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="94693-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="94693-143">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="94693-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="94693-144">Wenn Sie den Zugriff auf Dienste für mehrere Lizenzierungs Pläne deaktivieren möchten, wiederholen Sie die obigen Anweisungen für jeden Lizenzierungs Plan, um Folgendes sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="94693-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="94693-145">Die Benutzerkonten wurden mit dem Lizenzierungs Plan versehen.</span><span class="sxs-lookup"><span data-stu-id="94693-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="94693-146">Die zu deaktivierenden Dienste stehen im Lizenzierungs Plan zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="94693-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="94693-147">Informationen zum Deaktivieren von Microsoft 365-Diensten für Benutzer, während Sie Sie einem Lizenzierungs Plan zuweisen, finden Sie unter [Deaktivieren des Zugriffs auf Dienste beim Zuweisen von Benutzerlizenzen](disable-access-to-services-while-assigning-user-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="94693-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="94693-148">Zuweisen aller Dienste in einem Lizenzierungs Plan zu einem Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="94693-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="94693-149">Für Benutzerkonten, für die Dienste deaktiviert wurden, können Sie mit den folgenden Befehlen alle Dienste für einen bestimmten Lizenzierungs Plan aktivieren:</span><span class="sxs-lookup"><span data-stu-id="94693-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="94693-150">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="94693-150">Related topic</span></span>

[<span data-ttu-id="94693-151">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="94693-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="94693-152">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="94693-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="94693-153">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94693-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
