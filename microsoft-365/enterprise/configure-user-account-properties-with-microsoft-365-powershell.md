---
title: Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Verwenden Sie PowerShell für Microsoft 365, um Eigenschaften für einzelne oder mehrere Benutzerkonten in Ihrem Microsoft 365-Mandanten zu konfigurieren.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754328"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="36b62-103">Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="36b62-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="36b62-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="36b62-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="36b62-105">Sie können das Microsoft 365 Admin Center verwenden, um Eigenschaften für die Benutzerkonten Ihres Microsoft 365-Mandanten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="36b62-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="36b62-106">In PowerShell können Sie dies auch tun, und einige andere Dinge, die Sie im Admin Center nicht tun können.</span><span class="sxs-lookup"><span data-stu-id="36b62-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="36b62-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="36b62-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="36b62-108">Verwenden Sie das Cmdlet "AzureADUser", um Eigenschaften für Benutzerkonten im Azure Active Directory PowerShell for Graph [**-**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) Modul zu konfigurieren, und geben Sie die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="36b62-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="36b62-109">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="36b62-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="36b62-110">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="36b62-110">Change properties for a specific user account</span></span>

<span data-ttu-id="36b62-111">Sie identifizieren das Konto mit dem Parameter *-objectID* und legen oder ändern bestimmte Eigenschaften mithilfe zusätzlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="36b62-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="36b62-112">Im folgenden finden Sie eine Liste der gebräuchlichsten Parameter:</span><span class="sxs-lookup"><span data-stu-id="36b62-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="36b62-113">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="36b62-114">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="36b62-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="36b62-115">-FacsimilieTelephoneNumber „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="36b62-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="36b62-116">-GivenName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="36b62-117">-Surname „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="36b62-118">-Mobile „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="36b62-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="36b62-119">-JobTitle „\<job title>"</span><span class="sxs-lookup"><span data-stu-id="36b62-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="36b62-120">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="36b62-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="36b62-121">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="36b62-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="36b62-122">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="36b62-123">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="36b62-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="36b62-124">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="36b62-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="36b62-125">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="36b62-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="36b62-126">-TelephoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="36b62-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="36b62-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="36b62-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="36b62-128">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="36b62-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="36b62-129">Weitere Parameter finden Sie unter [festlegen-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="36b62-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="36b62-130">Bevor Sie einem Benutzerkonto Lizenzen zuweisen können, müssen Sie einen Verwendungs Speicherort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="36b62-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="36b62-131">Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36b62-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="36b62-132">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="36b62-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="36b62-133">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-134">Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-135">Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.</span><span class="sxs-lookup"><span data-stu-id="36b62-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="36b62-136">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="36b62-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="36b62-137">Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36b62-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="36b62-138">Füllen Sie die *$username* Variable aus, und entfernen Sie die \< and > Zeichen:</span><span class="sxs-lookup"><span data-stu-id="36b62-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="36b62-139">In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigenamen " *Caleb Sills*" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36b62-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="36b62-140">Mithilfe einer *$UPN* Variablen können Sie Änderungen an einzelnen Konten basierend auf Ihrem Anzeigenamen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="36b62-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="36b62-141">Hier ist ein Beispiel, das den Verwendungsstandort von *Belinda Newman*auf Frankreich festlegt.</span><span class="sxs-lookup"><span data-stu-id="36b62-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="36b62-142">Sie gibt jedoch Ihren Anzeigenamen anstelle des Benutzerprinzipalnamens an:</span><span class="sxs-lookup"><span data-stu-id="36b62-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="36b62-143">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="36b62-143">Change properties for all user accounts</span></span>

<span data-ttu-id="36b62-144">Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination aus den Cmdlets **Get-AzureADUser** und **setAzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="36b62-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="36b62-145">Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in *Frankreich*geändert:</span><span class="sxs-lookup"><span data-stu-id="36b62-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="36b62-146">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="36b62-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="36b62-147">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-148">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="36b62-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="36b62-149">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="36b62-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="36b62-150">Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den Cmdlets " **Get-AzureADUser**", " **Where**" und " **Sets-AzureADUser** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="36b62-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="36b62-151">Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich*geändert:</span><span class="sxs-lookup"><span data-stu-id="36b62-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="36b62-152">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="36b62-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="36b62-153">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="36b62-154">Suchen Sie alle Benutzerkonten, deren *Abteilungs* Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-155">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="36b62-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="36b62-156">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36b62-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="36b62-157">Verwenden Sie das Cmdlet "MsolUser", um Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory **-** Modul für Windows PowerShell zu konfigurieren, und geben Sie die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="36b62-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="36b62-158">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="36b62-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="36b62-159">PowerShell Core unterstützt das Microsoft Azure Active Directory Modul für Windows PowerShell Modul und Cmdlets mit *MSOL* nicht in Ihrem Namen.</span><span class="sxs-lookup"><span data-stu-id="36b62-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="36b62-160">Führen Sie diese Cmdlets aus Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="36b62-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="36b62-161">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="36b62-161">Change properties for a specific user account</span></span>

<span data-ttu-id="36b62-162">Um Eigenschaften für ein bestimmtes Benutzerkonto zu konfigurieren, verwenden Sie das Cmdlet " [**MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) ", und geben Sie die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="36b62-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="36b62-163">Sie identifizieren das Konto mit dem Parameter " *-userPrincipalName* " und legen oder ändern bestimmte Eigenschaften mithilfe zusätzlicher Parameter.</span><span class="sxs-lookup"><span data-stu-id="36b62-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="36b62-164">Im folgenden finden Sie eine Liste der gebräuchlichsten Parameter.</span><span class="sxs-lookup"><span data-stu-id="36b62-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="36b62-165">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="36b62-166">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="36b62-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="36b62-167">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="36b62-168">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="36b62-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="36b62-169">-Fax „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="36b62-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="36b62-170">-FirstName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="36b62-171">-LastName „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="36b62-172">-MobilePhone „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="36b62-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="36b62-173">-Office „<Standort des Büros>"</span><span class="sxs-lookup"><span data-stu-id="36b62-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="36b62-174">-PhoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="36b62-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="36b62-175">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="36b62-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="36b62-176">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="36b62-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="36b62-177">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="36b62-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="36b62-178">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="36b62-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="36b62-179">-Title „\<title name>"</span><span class="sxs-lookup"><span data-stu-id="36b62-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="36b62-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="36b62-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="36b62-181">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="36b62-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="36b62-182">Weitere Parameter finden Sie unter [festlegen-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="36b62-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="36b62-183">Um die Benutzerprinzipalnamen aller Benutzer anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="36b62-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="36b62-184">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="36b62-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="36b62-185">Rufen Sie alle Informationen für die Benutzerkonten ab (**Get-MsolUser**), und senden Sie es an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-186">Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-187">Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.</span><span class="sxs-lookup"><span data-stu-id="36b62-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="36b62-188">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="36b62-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="36b62-189">Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36b62-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="36b62-190">Füllen Sie die *$username* Variable aus, und entfernen Sie die \< and > Zeichen.</span><span class="sxs-lookup"><span data-stu-id="36b62-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="36b62-191">In diesem Beispiel wird der Benutzerprinzipal Name für den Benutzernamens Caleb Sills angezeigt:</span><span class="sxs-lookup"><span data-stu-id="36b62-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="36b62-192">Mithilfe einer *$UPN* Variablen können Sie Änderungen an einzelnen Konten basierend auf Ihrem Anzeigenamen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="36b62-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="36b62-193">Hier ist ein Beispiel, das den Verwendungs Speicherort von *Belinda Newman*auf *Frankreich*festlegt, jedoch Ihren Anzeigenamen anstelle des Benutzerprinzipalnamens angibt:</span><span class="sxs-lookup"><span data-stu-id="36b62-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="36b62-194">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="36b62-194">Change properties for all user accounts</span></span>

<span data-ttu-id="36b62-195">Verwenden Sie eine Kombination aus den Cmdlets **Get-MsolUser** und **setMsolUser** , um die Eigenschaften für alle Benutzer zu ändern.</span><span class="sxs-lookup"><span data-stu-id="36b62-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="36b62-196">Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in *Frankreich*geändert:</span><span class="sxs-lookup"><span data-stu-id="36b62-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="36b62-197">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="36b62-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="36b62-198">Rufen Sie alle Informationen für die Benutzerkonten ab (**Get-MsolUser**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-199">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="36b62-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="36b62-200">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="36b62-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="36b62-201">Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den Cmdlets " **Get-MsolUser**", " **Where**" und " **Sets-MsolUser** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="36b62-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="36b62-202">Im folgenden Beispiel wird der Verwendungs Speicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich*geändert:</span><span class="sxs-lookup"><span data-stu-id="36b62-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="36b62-203">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="36b62-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="36b62-204">Rufen Sie alle Informationen für die Benutzerkonten ab (**Get-MsolUser**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-205">Suchen Sie nach allen Benutzerkonten, deren *Abteilungs* Eigenschaft auf "Buchhaltung" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="36b62-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="36b62-206">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="36b62-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="36b62-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36b62-207">See also</span></span>

[<span data-ttu-id="36b62-208">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="36b62-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="36b62-209">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="36b62-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="36b62-210">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36b62-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
