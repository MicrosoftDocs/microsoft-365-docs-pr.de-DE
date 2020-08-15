---
title: Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um die Eigenschaften einzelner oder mehrerer Benutzerkonten in Ihrem Microsoft 365-Mandanten zu konfigurieren.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690248"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="f844f-103">Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f844f-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="f844f-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f844f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f844f-105">Obwohl Sie das Microsoft 365 Admin Center zum Konfigurieren von Eigenschaften für die Benutzerkonten Ihres Microsoft 365-Mandanten verwenden können, können Sie auch PowerShell verwenden und einige Dinge tun, die das Microsoft 365 Admin Center nicht kann.</span><span class="sxs-lookup"><span data-stu-id="f844f-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f844f-106">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="f844f-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f844f-107">Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten mit der Azure Active Directory PowerShell das [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)-Cmdlet und geben Sie die Eigenschaften an, die Sie festlegen bzw. ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f844f-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="f844f-108">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="f844f-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="f844f-109">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="f844f-109">Change properties for a specific user account</span></span>

<span data-ttu-id="f844f-p101">Sie identifizieren das Konto mit dem **-ObjectID**-Parameter und legen bestimmte Eigenschaften mit weiteren Parametern fest bzw. ändern diese. Nachfolgend ist eine Liste der am häufigsten verwendeten Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f844f-p101">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters. Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="f844f-112">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="f844f-113">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="f844f-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="f844f-114">-FacsimilieTelephoneNumber „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="f844f-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="f844f-115">-GivenName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="f844f-116">-Surname „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="f844f-117">-Mobile „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="f844f-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="f844f-118">-JobTitle „\<job title>"</span><span class="sxs-lookup"><span data-stu-id="f844f-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="f844f-119">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="f844f-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="f844f-120">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="f844f-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="f844f-121">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="f844f-122">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="f844f-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="f844f-123">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="f844f-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="f844f-124">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="f844f-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="f844f-125">-TelephoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="f844f-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="f844f-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="f844f-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="f844f-127">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="f844f-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="f844f-128">Informationen zu weiteren Parametern finden Sie unter [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="f844f-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="f844f-129">Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f844f-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="f844f-130">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="f844f-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f844f-131">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-132">Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-133">Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.</span><span class="sxs-lookup"><span data-stu-id="f844f-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="f844f-134">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="f844f-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="f844f-135">Mit diesem Befehl werden alle Ihre Konten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f844f-135">This command will list all of your accounts.</span></span> <span data-ttu-id="f844f-136">Wenn Sie den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzeigen möchten, geben Sie unten die **$username** Variable ein (Entfernen der \< and > Zeichen), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f844f-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f844f-137">In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigename Caleb Sills angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f844f-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f844f-p103">Mit der **$upn**-Variable können Sie Änderungen an den einzelnen Konten basierend auf deren Anzeigenamen vornehmen. Hier ist ein Beispiel für das Festlegen des Verwendungsstandorts von Belinda Newman in Frankreich. Dabei wird Ihr Anzeigenamen anstatt Ihres Benutzerprinzipalnamens verwendet:</span><span class="sxs-lookup"><span data-stu-id="f844f-p103">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="f844f-140">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f844f-140">Change properties for all user accounts</span></span>

<span data-ttu-id="f844f-p104">Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination der Cmdlets **Get-AzureADUser** und **et-AzureADUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="f844f-p104">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="f844f-143">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="f844f-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f844f-144">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-145">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f844f-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="f844f-146">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f844f-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="f844f-p105">Um die Eigenschaften für einen bestimmten Satz von Benutzerkonten zu ändern, können Sie eine Kombination der Cmdlets **Get-AzureADUser**, **Where** und **Set-AzureADUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in der Buchhaltungsabteilung in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="f844f-p105">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets. The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="f844f-149">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="f844f-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f844f-150">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-151">Suchen Sie alle Benutzerkonten, deren Abteilungs Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-152">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f844f-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f844f-153">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f844f-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f844f-154">Um Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory Modul für Windows PowerShell zu konfigurieren, verwenden Sie das Cmdlet " **MsolUser** " und geben die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f844f-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="f844f-155">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f844f-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="f844f-156">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="f844f-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f844f-157">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f844f-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="f844f-158">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="f844f-158">Change properties for a specific user account</span></span>

<span data-ttu-id="f844f-159">Verwenden Sie zum Konfigurieren der Eigenschaften für ein bestimmtes Benutzerkonto das [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))-Cmdlet und geben die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f844f-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="f844f-p107">Sie identifizieren das Konto mit dem **-UserPrincipalName**-Parameter und legen bestimmte Eigenschaften mit weiteren Parametern fest bzw. ändern diese. Nachfolgend ist eine Liste der am häufigsten verwendeten Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f844f-p107">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters. Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="f844f-162">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="f844f-163">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="f844f-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="f844f-164">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="f844f-165">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="f844f-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="f844f-166">-Fax „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="f844f-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="f844f-167">-FirstName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="f844f-168">-LastName „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="f844f-169">-MobilePhone „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="f844f-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="f844f-170">-Office „<Standort des Büros>"</span><span class="sxs-lookup"><span data-stu-id="f844f-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="f844f-171">-PhoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="f844f-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="f844f-172">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="f844f-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="f844f-173">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="f844f-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="f844f-174">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="f844f-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="f844f-175">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="f844f-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="f844f-176">-Title „\<title name>"</span><span class="sxs-lookup"><span data-stu-id="f844f-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="f844f-177">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="f844f-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="f844f-178">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="f844f-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="f844f-179">Informationen zu weiteren Parametern finden Sie unter [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="f844f-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="f844f-180">Führen Sie den folgenden Befehl aus, um die Benutzerprinzipalnamen aller Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f844f-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="f844f-181">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="f844f-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f844f-182">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-183">Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-184">Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.</span><span class="sxs-lookup"><span data-stu-id="f844f-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="f844f-185">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="f844f-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="f844f-186">Mit diesem Befehl werden alle Ihre Konten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f844f-186">This command will list all of your accounts.</span></span> <span data-ttu-id="f844f-187">Wenn Sie den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzeigen möchten, geben Sie unten die **$username** Variable ein (Entfernen der \< and > Zeichen), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f844f-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f844f-188">In diesem Beispiel wird der Benutzerprinzipalname für den Benutzer namens Caleb Sills angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f844f-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="f844f-p109">Mit der **$upn** -Variable können Sie Änderungen an den einzelnen Konten basierend auf deren Anzeigenamen vornehmen. Hier ist ein Beispiel für das Festlegen des Verwendungsstandorts von Belinda Newman in Frankreich. Dabei wird Ihr Anzeigenamen anstatt Ihres Benutzerprinzipalnamens verwendet:</span><span class="sxs-lookup"><span data-stu-id="f844f-p109">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="f844f-191">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f844f-191">Change properties for all user accounts</span></span>

<span data-ttu-id="f844f-p110">Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination der Cmdlets **Get-MsolUser** und **Set-MsolUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="f844f-p110">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="f844f-194">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="f844f-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f844f-195">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-196">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f844f-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="f844f-197">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f844f-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="f844f-198">Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie die Kombination aus den Cmdlets **Get-MsolUser**, **Where**und **setMsolUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="f844f-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="f844f-199">Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in der Buchhaltungsabteilung in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="f844f-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="f844f-200">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="f844f-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="f844f-201">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-202">Suchen Sie alle Benutzerkonten, deren Abteilungs Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f844f-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="f844f-203">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="f844f-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="f844f-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f844f-204">See also</span></span>

[<span data-ttu-id="f844f-205">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f844f-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f844f-206">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f844f-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f844f-207">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f844f-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
