---
title: Erstellen von Microsoft 365-Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Verwenden von PowerShell zum Erstellen einzelner oder mehrerer Microsoft 365-Benutzerkonten.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907564"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="6e500-103">Erstellen von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e500-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="6e500-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6e500-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6e500-105">Sie können PowerShell für Microsoft 365 verwenden, um Benutzerkonten effizient zu erstellen, einschließlich mehrerer Konten.</span><span class="sxs-lookup"><span data-stu-id="6e500-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="6e500-106">Wenn Sie Benutzerkonten in PowerShell erstellen, sind bestimmte Kontoeigenschaften immer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e500-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="6e500-107">Andere Eigenschaften sind nicht erforderlich, aber wichtig.</span><span class="sxs-lookup"><span data-stu-id="6e500-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="6e500-108">Informationen finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6e500-108">See the following table.</span></span>
  
|<span data-ttu-id="6e500-109">**Eigenschaftenname**</span><span class="sxs-lookup"><span data-stu-id="6e500-109">**Property name**</span></span>|<span data-ttu-id="6e500-110">**Erforderlich?**</span><span class="sxs-lookup"><span data-stu-id="6e500-110">**Required?**</span></span>|<span data-ttu-id="6e500-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6e500-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e500-112">**Anzeigename**</span><span class="sxs-lookup"><span data-stu-id="6e500-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="6e500-113">Ja</span><span class="sxs-lookup"><span data-stu-id="6e500-113">Yes</span></span>  <br/> |<span data-ttu-id="6e500-114">Dies ist der Anzeigename, der in Microsoft 365-Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e500-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="6e500-115">Beispiel: *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="6e500-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="6e500-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="6e500-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="6e500-117">Ja</span><span class="sxs-lookup"><span data-stu-id="6e500-117">Yes</span></span>  <br/> |<span data-ttu-id="6e500-118">Dies ist der Kontoname, der für die Anmeldung bei Microsoft 365-Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e500-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="6e500-119">*CalebS contoso.onmicrosoft.com \@*.</span><span class="sxs-lookup"><span data-stu-id="6e500-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="6e500-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="6e500-120">**FirstName**</span></span> <br/> |<span data-ttu-id="6e500-121">Nein</span><span class="sxs-lookup"><span data-stu-id="6e500-121">No</span></span>  <br/> ||
|<span data-ttu-id="6e500-122">**Nachname**</span><span class="sxs-lookup"><span data-stu-id="6e500-122">**LastName**</span></span> <br/> |<span data-ttu-id="6e500-123">Nein</span><span class="sxs-lookup"><span data-stu-id="6e500-123">No</span></span>  <br/> ||
|<span data-ttu-id="6e500-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="6e500-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="6e500-125">Nein</span><span class="sxs-lookup"><span data-stu-id="6e500-125">No</span></span>  <br/> |<span data-ttu-id="6e500-126">Dies ist der Lizenzierungsplan (auch als Lizenzplan oder SKU bezeichnet), aus dem dem Benutzerkonto eine verfügbare Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6e500-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="6e500-127">Die Lizenz definiert die Microsoft 365-Dienste, die für das Konto verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6e500-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="6e500-128">Sie müssen keine Lizenz einem Benutzer zuweisen, wenn Sie das Konto erstellen, aber das Konto muss über eine Lizenz für den Zugriff auf Microsoft 365-Dienste verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e500-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="6e500-129">Sie haben 30 Tage Zeit, um das Benutzerkonto zu lizenzieren, nachdem Sie es erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="6e500-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="6e500-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="6e500-130">**Password**</span></span> <br/> |<span data-ttu-id="6e500-131">Nein</span><span class="sxs-lookup"><span data-stu-id="6e500-131">No</span></span>  <br/> | <span data-ttu-id="6e500-132">Wenn Sie kein Kennwort angeben, wird dem Benutzerkonto ein zufälliges Kennwort zugewiesen, und das Kennwort wird in den Ergebnissen des Befehls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e500-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="6e500-133">Wenn Sie ein Kennwort angeben, muss es 8 bis 16 ASCII-Textzeichen der folgenden Typen sein: Kleinbuchstaben, Großbuchstaben, Zahlen und Symbole.</span><span class="sxs-lookup"><span data-stu-id="6e500-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="6e500-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="6e500-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="6e500-135">Nein</span><span class="sxs-lookup"><span data-stu-id="6e500-135">No</span></span>  <br/> |<span data-ttu-id="6e500-136">Dies ist ein gültiger ISO 3166-1-Alpha-2-Ländercode.</span><span class="sxs-lookup"><span data-stu-id="6e500-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="6e500-137">Beispiel: *USA* für die USA und *FR* für Frankreich.</span><span class="sxs-lookup"><span data-stu-id="6e500-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="6e500-138">Es ist wichtig, diesen Wert zur Verfügung zu stellen, da einige Microsoft 365-Dienste in bestimmten Ländern nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6e500-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="6e500-139">Sie können einem Benutzerkonto nur dann eine Lizenz zuweisen, wenn dieser Wert für das Konto konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6e500-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="6e500-140">Weitere Informationen finden Sie unter [Informationen zu Lizenzbeschränkungen](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="6e500-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="6e500-141">[Erfahren Sie, wie Sie Benutzerkonten mithilfe](../admin/add-users/add-users.md) des Microsoft 365 Admin Centers erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e500-141">[Learn how to create user accounts](../admin/add-users/add-users.md) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="6e500-142">Eine Liste der zusätzlichen Ressourcen finden Sie unter [Verwalten von Benutzern und Gruppen](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="6e500-142">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6e500-143">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="6e500-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6e500-144">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6e500-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="6e500-145">Nachdem Sie eine Verbindung hergestellt haben, verwenden Sie die folgende Syntax, um ein einzelnes Konto zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6e500-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="6e500-146">In diesem Beispiel wird ein Konto für den US-Benutzer *Caleb Sills erstellt:*</span><span class="sxs-lookup"><span data-stu-id="6e500-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6e500-147">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e500-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6e500-148">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="6e500-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="6e500-149">Erstellen eines einzelnen Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="6e500-149">Create an individual user account</span></span>

<span data-ttu-id="6e500-150">Verwenden Sie die folgende Syntax, um ein einzelnes Konto zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6e500-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="6e500-151">PowerShell Core unterstützt das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets, die *Msol* im Namen haben, nicht.</span><span class="sxs-lookup"><span data-stu-id="6e500-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="6e500-152">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="6e500-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="6e500-153">Mit dem folgenden Befehl erhalten Sie eine Liste der Namen der Lizenzierungspläne:</span><span class="sxs-lookup"><span data-stu-id="6e500-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="6e500-154">In diesem Beispiel wird ein Konto für den US-Benutzer *Caleb Sills* erstellt und eine Lizenz aus dem `contoso:ENTERPRISEPACK` Lizenzierungsplan (Office 365 Enterprise E3) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6e500-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="6e500-155">Erstellen mehrerer Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="6e500-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="6e500-p108">Erstellen Sie eine durch Kommata getrennte Wertedatei (CSV), die die erforderlichen Informationen zum Benutzerkonto enthält. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e500-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="6e500-158">Die Spaltennamen und ihre Reihenfolge in der ersten Zeile der CSV-Datei sind beliebig.</span><span class="sxs-lookup"><span data-stu-id="6e500-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="6e500-159">Stellen Sie jedoch sicher, dass die Reihenfolge der Daten in der restlichen Datei der Reihenfolge der Spaltennamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="6e500-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="6e500-160">Verwenden Sie die Spaltennamen für die Parameterwerte im PowerShell für Microsoft 365-Befehl.</span><span class="sxs-lookup"><span data-stu-id="6e500-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="6e500-161">Sowohl exExchangeNoVersion als auch AD FS müssen dasselbe Token für denselben Benutzer anfordern, damit eine ordnungsgemäße Funktionalität für ein standortübergreifendes exExchangeNoVersion-Bereitstellungsszenario gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="6e500-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="6e500-162">In diesem Beispiel werden Benutzerkonten aus der Datei *C:\My Documents\NewAccounts.csv* erstellt und die Ergebnisse in einer Datei mit dem Namen *C:\My Documents\NewAccountResults.csvprotokolliert.*</span><span class="sxs-lookup"><span data-stu-id="6e500-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="6e500-163">Die Ergebnisse können Sie in der Ausgabedatei überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6e500-163">Review the output file to see the results.</span></span> <span data-ttu-id="6e500-164">Wir haben keine Kennwörter angegeben, daher sind die zufälligen Kennwörter, die Von Microsoft 365 generiert wurden, in der Ausgabedatei sichtbar.</span><span class="sxs-lookup"><span data-stu-id="6e500-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6e500-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e500-165">See also</span></span>

[<span data-ttu-id="6e500-166">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e500-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6e500-167">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e500-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6e500-168">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e500-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)