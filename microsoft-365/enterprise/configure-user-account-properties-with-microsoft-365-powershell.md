---
title: Konfigurieren Microsoft 365 Benutzerkontoeigenschaften mit PowerShell
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
description: Verwenden Sie PowerShell für Microsoft 365, um Eigenschaften einzelner oder mehrerer Benutzerkonten in Ihrem Mandanten Microsoft 365 konfigurieren.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911084"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="ccafe-103">Konfigurieren Microsoft 365 Benutzerkontoeigenschaften mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccafe-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="ccafe-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ccafe-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ccafe-105">Sie können das Microsoft 365 Admin Center verwenden, um Eigenschaften für die Benutzerkonten Ihres mandanten Microsoft 365 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccafe-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="ccafe-106">In PowerShell können Sie dies auch tun, sowie einige andere Dinge, die Sie im Admin Center nicht tun können.</span><span class="sxs-lookup"><span data-stu-id="ccafe-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ccafe-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="ccafe-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ccafe-108">Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten im Azure Active Directory PowerShell für Graph-Modul das [**Cmdlet Set-AzureADUser,**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) und geben Sie die eigenschaften an, die festgelegt oder geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="ccafe-109">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ccafe-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="ccafe-110">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="ccafe-110">Change properties for a specific user account</span></span>

<span data-ttu-id="ccafe-111">Sie identifizieren das Konto mit dem *-ObjectID-Parameter* und legen bestimmte Eigenschaften mithilfe zusätzlicher Parameter fest oder ändern sie.</span><span class="sxs-lookup"><span data-stu-id="ccafe-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="ccafe-112">Hier ist eine Liste der gängigsten Parameter:</span><span class="sxs-lookup"><span data-stu-id="ccafe-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="ccafe-113">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="ccafe-114">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="ccafe-115">-FacsimilieTelephoneNumber „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="ccafe-116">-GivenName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="ccafe-117">-Surname „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="ccafe-118">-Mobile „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="ccafe-119">-JobTitle „\<job title>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="ccafe-120">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="ccafe-121">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="ccafe-122">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="ccafe-123">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="ccafe-124">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="ccafe-125">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="ccafe-126">-TelephoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="ccafe-127">-UsageLocation " \<2-character country or region code> " "</span><span class="sxs-lookup"><span data-stu-id="ccafe-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="ccafe-128">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="ccafe-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="ccafe-129">Weitere Parameter finden Sie unter [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="ccafe-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="ccafe-130">Bevor Sie einem Benutzerkonto Lizenzen zuweisen können, müssen Sie einen Verwendungsspeicherort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="ccafe-131">Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="ccafe-132">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ccafe-133">Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-134">Sortieren Sie die Liste der Benutzerprinzipalnamen alphabetisch (**Sortieren von UserPrincipalName**) und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-135">Zeigt nur die User Principal Name-Eigenschaft für jedes Konto an (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="ccafe-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="ccafe-136">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="ccafe-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="ccafe-137">Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf seinem Anzeigenamen (Vor- und Nachname) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="ccafe-138">Füllen Sie die *$userName* aus, und entfernen Sie die \< and > Zeichen:</span><span class="sxs-lookup"><span data-stu-id="ccafe-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ccafe-139">In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigenamen *Caleb Sills angezeigt.*</span><span class="sxs-lookup"><span data-stu-id="ccafe-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ccafe-140">Mithilfe einer *$upn* können Sie änderungen an einzelnen Konten basierend auf ihrem Anzeigenamen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="ccafe-141">Hier ist ein Beispiel, das den Verwendungsspeicherort von *Belinda Newman* auf Frankreich legt.</span><span class="sxs-lookup"><span data-stu-id="ccafe-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="ccafe-142">Sie gibt jedoch ihren Anzeigenamen anstelle ihres Benutzerprinzipalnamens an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="ccafe-143">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ccafe-143">Change properties for all user accounts</span></span>

<span data-ttu-id="ccafe-144">Zum Ändern von Eigenschaften für alle Benutzer können Sie eine Kombination der **Cmdlets Get-AzureADUser** und **Set-AzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccafe-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="ccafe-145">Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in *Frankreich geändert:*</span><span class="sxs-lookup"><span data-stu-id="ccafe-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="ccafe-146">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ccafe-147">Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-148">Legen Sie den Benutzerspeicherort auf Frankreich (**Set-AzureADUser -UsageLocation "FR" ) festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="ccafe-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="ccafe-149">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ccafe-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="ccafe-150">Zum Ändern von Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den **Cmdlets Get-AzureADUser**, **Where** und **Set-AzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccafe-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="ccafe-151">Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich geändert:*</span><span class="sxs-lookup"><span data-stu-id="ccafe-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="ccafe-152">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ccafe-153">Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="ccafe-154">Suchen Sie alle Benutzerkonten, deren *Department-Eigenschaft* auf "Accounting" festgelegt ist (**Where {$_. Department -eq "Accounting"}**), und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-155">Legen Sie den Benutzerspeicherort auf Frankreich (**Set-AzureADUser -UsageLocation "FR" ) festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="ccafe-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ccafe-156">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccafe-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ccafe-157">Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory-Modul für Windows PowerShell das **Cmdlet Set-MsolUser,** und geben Sie die eigenschaften an, die festgelegt oder geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="ccafe-158">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ccafe-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="ccafe-159">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ccafe-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="ccafe-160">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="ccafe-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="ccafe-161">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="ccafe-161">Change properties for a specific user account</span></span>

<span data-ttu-id="ccafe-162">Verwenden Sie zum Konfigurieren von Eigenschaften für ein bestimmtes Benutzerkonto das [**Cmdlet Set-MsolUser,**](/previous-versions/azure/dn194136(v=azure.100)) und geben Sie die eigenschaften an, die festgelegt oder geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="ccafe-163">Sie identifizieren das Konto mit dem *-UserPrincipalName-Parameter* und legen bestimmte Eigenschaften mithilfe zusätzlicher Parameter fest oder ändern sie.</span><span class="sxs-lookup"><span data-stu-id="ccafe-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="ccafe-164">Hier finden Sie eine Liste der gängigsten Parameter.</span><span class="sxs-lookup"><span data-stu-id="ccafe-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="ccafe-165">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="ccafe-166">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="ccafe-167">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="ccafe-168">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="ccafe-169">-Fax „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="ccafe-170">-FirstName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="ccafe-171">-LastName „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="ccafe-172">-MobilePhone „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="ccafe-173">-Office „<Standort des Büros>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="ccafe-174">-PhoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="ccafe-175">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="ccafe-176">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="ccafe-177">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="ccafe-178">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="ccafe-179">-Title „\<title name>"</span><span class="sxs-lookup"><span data-stu-id="ccafe-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="ccafe-180">-UsageLocation " \<2-character country or region code> " "</span><span class="sxs-lookup"><span data-stu-id="ccafe-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="ccafe-181">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="ccafe-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="ccafe-182">Weitere Parameter finden Sie unter [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="ccafe-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="ccafe-183">Führen Sie den folgenden Befehl aus, um die Benutzerprinzipalnamen aller Benutzer zu sehen:</span><span class="sxs-lookup"><span data-stu-id="ccafe-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="ccafe-184">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ccafe-185">Alle Informationen für die Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-186">Sortieren Sie die Liste der Benutzerprinzipalnamen alphabetisch (**Sortieren von UserPrincipalName**) und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-187">Zeigt nur die User Principal Name-Eigenschaft für jedes Konto an (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="ccafe-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="ccafe-188">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="ccafe-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="ccafe-189">Führen Sie die folgenden Befehle aus, um den Benutzerprinzipalnamen für ein Konto basierend auf seinem Anzeigenamen (Vor- und Nachname) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="ccafe-190">Geben Sie *die* $userName ein, und entfernen Sie die \< and > Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ccafe-191">In diesem Beispiel wird der Benutzerprinzipalname für den Benutzer namens Caleb Sills angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ccafe-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="ccafe-192">Mithilfe einer *$upn* können Sie änderungen an einzelnen Konten basierend auf ihrem Anzeigenamen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ccafe-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="ccafe-193">Im Folgenden sehen Sie ein Beispiel, in dem der Verwendungsspeicherort von *Belinda Newman* auf *Frankreich* festgelegt wird, aber ihr Anzeigename und nicht ihr Benutzerprinzipalname angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="ccafe-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="ccafe-194">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ccafe-194">Change properties for all user accounts</span></span>

<span data-ttu-id="ccafe-195">Verwenden Sie zum Ändern von Eigenschaften für alle Benutzer eine Kombination aus **den Cmdlets Get-MsolUser** und **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="ccafe-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="ccafe-196">Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in *Frankreich geändert:*</span><span class="sxs-lookup"><span data-stu-id="ccafe-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="ccafe-197">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ccafe-198">Alle Informationen für die Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-199">Legen Sie den Benutzerspeicherort auf Frankreich (**Set-MsolUser -UsageLocation "FR" ) festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="ccafe-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="ccafe-200">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ccafe-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="ccafe-201">Zum Ändern von Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie eine Kombination aus den **Cmdlets Get-MsolUser**, **Where** und **Set-MsolUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ccafe-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="ccafe-202">Im folgenden Beispiel wird der Verwendungsspeicherort für alle Benutzer in der Buchhaltungsabteilung in *Frankreich geändert:*</span><span class="sxs-lookup"><span data-stu-id="ccafe-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="ccafe-203">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="ccafe-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="ccafe-204">Alle Informationen für die Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-205">Suchen Sie alle Benutzerkonten, deren *Department-Eigenschaft* auf "Accounting" festgelegt ist (**Where {$_. Department -eq "Accounting"}**) und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="ccafe-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="ccafe-206">Legen Sie den Benutzerspeicherort auf Frankreich (**Set-MsolUser -UsageLocation "FR" ) festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="ccafe-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccafe-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccafe-207">See also</span></span>

[<span data-ttu-id="ccafe-208">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccafe-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ccafe-209">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccafe-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ccafe-210">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ccafe-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)