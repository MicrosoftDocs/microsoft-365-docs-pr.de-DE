---
title: Deaktivieren des Zugriffs auf Microsoft 365 Mit PowerShell
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
description: In diesem Artikel erfahren Sie, wie Sie PowerShell verwenden, um den Zugriff auf Microsoft 365 Benutzern zu deaktivieren.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690508"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="f519c-103">Deaktivieren des Zugriffs auf Microsoft 365 Mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f519c-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="f519c-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f519c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f519c-105">Wenn einem Microsoft 365 eine Lizenz aus einem Lizenzierungsplan zugewiesen wird, werden Microsoft 365 dienste dem Benutzer über diese Lizenz zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="f519c-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="f519c-106">Sie können jedoch die Microsoft 365 steuern, auf die der Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="f519c-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="f519c-107">Auch wenn die Lizenz beispielsweise den Zugriff auf den SharePoint Onlinedienst zulässt, können Sie den Zugriff darauf deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f519c-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="f519c-108">Sie können PowerShell verwenden, um den Zugriff auf eine beliebige Anzahl von Diensten für einen bestimmten Lizenzierungsplan für:</span><span class="sxs-lookup"><span data-stu-id="f519c-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="f519c-109">ein einzelnes Konto</span><span class="sxs-lookup"><span data-stu-id="f519c-109">An individual account.</span></span>
- <span data-ttu-id="f519c-110">eine Gruppe von Konten</span><span class="sxs-lookup"><span data-stu-id="f519c-110">A group of accounts.</span></span>
- <span data-ttu-id="f519c-111">Alle Konten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f519c-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="f519c-112">Es gibt Microsoft 365 Dienstabhängigkeiten, die sie daran hindern können, einen angegebenen Dienst zu deaktivieren, wenn andere Dienste davon abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="f519c-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f519c-113">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f519c-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f519c-114">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="f519c-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="f519c-115">Verwenden Sie als Nächstes diesen Befehl, um Ihre verfügbaren Lizenzierungspläne, auch als AccountSkuIds bekannt, anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="f519c-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="f519c-116">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="f519c-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f519c-117">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f519c-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="f519c-118">Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f519c-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="f519c-119">Informationen zu den Ergebnissen vor und nach den Verfahren in diesem Thema finden Sie unter Anzeigen von [Kontolizenz- und Dienstdetails mit PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f519c-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="f519c-120">Ein PowerShell-Skript steht zur Verfügung, das die in diesem Thema erläuterten Verfahren automatisiert.</span><span class="sxs-lookup"><span data-stu-id="f519c-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="f519c-121">Insbesondere können Sie mit dem Skript Dienste in Ihrer organisation Microsoft 365, einschließlich Sway, anzeigen und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f519c-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="f519c-122">Weitere Informationen finden Sie unter [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f519c-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="f519c-123">Deaktivieren bestimmter Microsoft 365 für bestimmte Benutzer für einen bestimmten Lizenzierungsplan</span><span class="sxs-lookup"><span data-stu-id="f519c-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="f519c-124">Führen Sie die folgenden Schritte aus, um einen bestimmten Satz von Microsoft 365 für Benutzer für einen bestimmten Lizenzierungsplan zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f519c-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="f519c-125">Schritt 1: Identifizieren Sie die unerwünschten Dienste im Lizenzierungsplan mithilfe der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="f519c-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="f519c-126">Im folgenden Beispiel wird ein **LicenseOptions-Objekt** erstellt, das die Office- und SharePoint Onlinedienste im Lizenzierungsplan `litwareinc:ENTERPRISEPACK` namens (Office 365 Enterprise E3) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f519c-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="f519c-127">Schritt 2: Verwenden Sie **das LicenseOptions-Objekt** aus Schritt 1 für einen oder mehrere Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f519c-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="f519c-128">Wenn Sie ein neues Konto zu erstellen möchten, für das die Dienste deaktiviert sind, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f519c-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="f519c-129">Im folgenden Beispiel wird ein neues Konto für Allie Bellew erstellt, das die Lizenz zuerkennt und die in Schritt 1 beschriebenen Dienste deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f519c-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="f519c-130">Weitere Informationen zum Erstellen von Benutzerkonten in PowerShell für Microsoft 365 finden Sie unter Erstellen von Benutzerkonten [mit PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f519c-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="f519c-131">Verwenden Sie die folgende Syntax, um die Dienste für einen vorhandenen lizenzierten Benutzer zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f519c-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="f519c-132">In diesem Beispiel werden die Dienste für den Benutzer „BelindaN@litwareinc.com“ deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f519c-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="f519c-133">Um die in Schritt 1 beschriebenen Dienste für alle vorhandenen lizenzierten Benutzer zu deaktivieren, geben Sie den Namen Ihres Microsoft 365-Plans in der Anzeige des **Cmdlets Get-MsolAccountSku** an (z. B. **litwareinc:ENTERPRISEPACK**), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f519c-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="f519c-134">Wenn Sie das **Cmdlet Get-MsolUser** verwenden, ohne den _Parameter All_ zu verwenden, werden nur die ersten 500 Benutzerkonten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f519c-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="f519c-135">Verwenden Sie eine der folgenden Methoden, um die Dienste für eine Gruppe von vorhandenen Benutzern zu deaktivieren und die Benutzer zu identifizieren:</span><span class="sxs-lookup"><span data-stu-id="f519c-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="f519c-136">**Methode 1. Filtern der Konten basierend auf einem vorhandenen Kontoattribut**</span><span class="sxs-lookup"><span data-stu-id="f519c-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="f519c-137">Verwenden Sie hierzu die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f519c-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="f519c-138">Im folgenden Beispiel werden die Dienste für Benutzer in der Vertriebsabteilung in den USA deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f519c-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="f519c-139">**Methode 2: Verwenden einer Liste bestimmter Konten**</span><span class="sxs-lookup"><span data-stu-id="f519c-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="f519c-140">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f519c-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="f519c-141">Erstellen Sie eine Textdatei wie die folgende, die in jeder Zeile ein Konto enthält:</span><span class="sxs-lookup"><span data-stu-id="f519c-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="f519c-142">In diesem Beispiel ist die Textdatei C: \\ Meine \\ DokumenteAccounts.txt.</span><span class="sxs-lookup"><span data-stu-id="f519c-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="f519c-143">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f519c-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="f519c-144">Wenn Sie den Zugriff auf Dienste für mehrere Lizenzierungspläne deaktivieren möchten, wiederholen Sie die obigen Anweisungen für jeden Lizenzierungsplan, und stellen Sie sicher, dass:</span><span class="sxs-lookup"><span data-stu-id="f519c-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="f519c-145">Den Benutzerkonten wurde der Lizenzierungsplan zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f519c-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="f519c-146">Die zu deaktivierende Dienste sind im Lizenzierungsplan verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f519c-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="f519c-147">Informationen zum Deaktivieren Microsoft 365 Dienste für Benutzer, während Sie sie einem Lizenzierungsplan zuweisen, finden Sie unter [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f519c-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="f519c-148">Zuweisen aller Dienste in einem Lizenzierungsplan zu einem Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="f519c-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="f519c-149">Für Benutzerkonten, für die Dienste deaktiviert wurden, können Sie alle Dienste für einen bestimmten Lizenzierungsplan mit den folgenden Befehlen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f519c-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="f519c-150">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="f519c-150">Related topic</span></span>

[<span data-ttu-id="f519c-151">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f519c-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f519c-152">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f519c-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f519c-153">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f519c-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
