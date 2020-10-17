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
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um die Eigenschaften einzelner oder mehrerer Benutzerkonten in Ihrem Microsoft 365-Mandanten zu konfigurieren.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580928"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="06a6a-103">Konfigurieren der Eigenschaften von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a6a-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="06a6a-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="06a6a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="06a6a-105">Obwohl Sie das Microsoft 365 Admin Center zum Konfigurieren von Eigenschaften für die Benutzerkonten Ihres Microsoft 365-Mandanten verwenden können, können Sie auch PowerShell verwenden und einige Dinge tun, die das Microsoft 365 Admin Center nicht kann.</span><span class="sxs-lookup"><span data-stu-id="06a6a-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="06a6a-106">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="06a6a-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="06a6a-107">Verwenden Sie zum Konfigurieren von Eigenschaften für Benutzerkonten mit der Azure Active Directory PowerShell das [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)-Cmdlet und geben Sie die Eigenschaften an, die Sie festlegen bzw. ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="06a6a-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="06a6a-108">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="06a6a-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="06a6a-109">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="06a6a-109">Change properties for a specific user account</span></span>

<span data-ttu-id="06a6a-p101">Sie identifizieren das Konto mit dem **-ObjectID**-Parameter und legen bestimmte Eigenschaften mit weiteren Parametern fest bzw. ändern diese. Nachfolgend ist eine Liste der am häufigsten verwendeten Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="06a6a-p101">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters. Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="06a6a-112">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="06a6a-113">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="06a6a-114">-FacsimilieTelephoneNumber „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="06a6a-115">-GivenName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="06a6a-116">-Surname „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="06a6a-117">-Mobile „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="06a6a-118">-JobTitle „\<job title>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="06a6a-119">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="06a6a-120">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="06a6a-121">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="06a6a-122">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="06a6a-123">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="06a6a-124">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="06a6a-125">-TelephoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="06a6a-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="06a6a-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="06a6a-127">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="06a6a-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="06a6a-128">Informationen zu weiteren Parametern finden Sie unter [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).</span><span class="sxs-lookup"><span data-stu-id="06a6a-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) for additional parameters.</span></span>

>[!Note]
><span data-ttu-id="06a6a-129">Bevor Sie einem Benutzerkonto Lizenzen zuweisen können, müssen Sie einen Verwendungs Speicherort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-129">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="06a6a-130">Führen Sie den folgenden Befehl aus, um den Benutzerprinzipalnamen für Ihre Benutzerkonten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-130">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="06a6a-131">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="06a6a-131">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="06a6a-132">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-132">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-133">Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-133">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-134">Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.</span><span class="sxs-lookup"><span data-stu-id="06a6a-134">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="06a6a-135">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="06a6a-135">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="06a6a-136">Mit diesem Befehl werden alle Ihre Konten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="06a6a-136">This command will list all of your accounts.</span></span> <span data-ttu-id="06a6a-137">Wenn Sie den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzeigen möchten, geben Sie unten die **$username** Variable ein (Entfernen der \< and > Zeichen), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="06a6a-137">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="06a6a-138">In diesem Beispiel wird der Benutzerprinzipalname für das Benutzerkonto mit dem Anzeigename Caleb Sills angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06a6a-138">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="06a6a-p103">Mit der **$upn**-Variable können Sie Änderungen an den einzelnen Konten basierend auf deren Anzeigenamen vornehmen. Hier ist ein Beispiel für das Festlegen des Verwendungsstandorts von Belinda Newman in Frankreich. Dabei wird Ihr Anzeigenamen anstatt Ihres Benutzerprinzipalnamens verwendet:</span><span class="sxs-lookup"><span data-stu-id="06a6a-p103">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="06a6a-141">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="06a6a-141">Change properties for all user accounts</span></span>

<span data-ttu-id="06a6a-p104">Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination der Cmdlets **Get-AzureADUser** und **et-AzureADUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="06a6a-p104">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="06a6a-144">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="06a6a-144">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="06a6a-145">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-145">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-146">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="06a6a-146">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="06a6a-147">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="06a6a-147">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="06a6a-p105">Um die Eigenschaften für einen bestimmten Satz von Benutzerkonten zu ändern, können Sie eine Kombination der Cmdlets **Get-AzureADUser**, **Where** und **Set-AzureADUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in der Buchhaltungsabteilung in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="06a6a-p105">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets. The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="06a6a-150">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="06a6a-150">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="06a6a-151">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-151">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-152">Suchen Sie alle Benutzerkonten, deren Abteilungs Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-152">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-153">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="06a6a-153">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="06a6a-154">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a6a-154">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="06a6a-155">Um Eigenschaften für Benutzerkonten mit dem Microsoft Azure Active Directory Modul für Windows PowerShell zu konfigurieren, verwenden Sie das Cmdlet " **MsolUser** " und geben die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-155">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="06a6a-156">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="06a6a-156">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="06a6a-157">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-157">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="06a6a-158">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-158">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="06a6a-159">Ändern von Eigenschaften für ein bestimmtes Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="06a6a-159">Change properties for a specific user account</span></span>

<span data-ttu-id="06a6a-160">Verwenden Sie zum Konfigurieren der Eigenschaften für ein bestimmtes Benutzerkonto das [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))-Cmdlet und geben die Eigenschaften an, die festgelegt oder geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-160">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="06a6a-p107">Sie identifizieren das Konto mit dem **-UserPrincipalName**-Parameter und legen bestimmte Eigenschaften mit weiteren Parametern fest bzw. ändern diese. Nachfolgend ist eine Liste der am häufigsten verwendeten Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="06a6a-p107">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters. Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="06a6a-163">-City „\<city name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-163">-City "\<city name>"</span></span>
    
- <span data-ttu-id="06a6a-164">-Country „<Ländername>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-164">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="06a6a-165">-Department „\<department name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-165">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="06a6a-166">-DisplayName „<Vollständiger Benutzername>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-166">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="06a6a-167">-Fax „\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-167">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="06a6a-168">-FirstName „\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-168">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="06a6a-169">-LastName „\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-169">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="06a6a-170">-MobilePhone „\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-170">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="06a6a-171">-Office „<Standort des Büros>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-171">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="06a6a-172">-PhoneNumber „<Telefon Büro>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-172">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="06a6a-173">-PostalCode „\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-173">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="06a6a-174">-PreferredLanguage „\<language>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-174">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="06a6a-175">-State „<Bundesland/Kanton>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-175">-State "\<state name>"</span></span>
    
- <span data-ttu-id="06a6a-176">-StreetAddress „\<street address>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-176">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="06a6a-177">-Title „\<title name>"</span><span class="sxs-lookup"><span data-stu-id="06a6a-177">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="06a6a-178">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="06a6a-178">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="06a6a-179">Dies ist der zweistellige ISO 3166-1-Ländercode bzw. Regionscode (Alpha-2, A2).</span><span class="sxs-lookup"><span data-stu-id="06a6a-179">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="06a6a-180">Informationen zu weiteren Parametern finden Sie unter [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="06a6a-180">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="06a6a-181">Führen Sie den folgenden Befehl aus, um die Benutzerprinzipalnamen aller Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06a6a-181">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="06a6a-182">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="06a6a-182">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="06a6a-183">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-183">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-184">Sortieren Sie die Liste der Benutzerprinzipalnamen in alphabetischer Reihenfolge (**Sort userPrincipalName**), und senden Sie Sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-184">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-185">Zeigt nur die Benutzerprinzipalnamen-Eigenschaft für jedes Konto an (**Wählen Sie userPrincipalName**) aus.</span><span class="sxs-lookup"><span data-stu-id="06a6a-185">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="06a6a-186">Jeweils auf einem Bildschirm anzeigen (**More**).</span><span class="sxs-lookup"><span data-stu-id="06a6a-186">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="06a6a-187">Mit diesem Befehl werden alle Ihre Konten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="06a6a-187">This command will list all of your accounts.</span></span> <span data-ttu-id="06a6a-188">Wenn Sie den Benutzerprinzipalnamen für ein Konto basierend auf dem Anzeigenamen (vor-und Nachname) anzeigen möchten, geben Sie unten die **$username** Variable ein (Entfernen der \< and > Zeichen), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="06a6a-188">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="06a6a-189">In diesem Beispiel wird der Benutzerprinzipalname für den Benutzer namens Caleb Sills angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06a6a-189">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="06a6a-p109">Mit der **$upn** -Variable können Sie Änderungen an den einzelnen Konten basierend auf deren Anzeigenamen vornehmen. Hier ist ein Beispiel für das Festlegen des Verwendungsstandorts von Belinda Newman in Frankreich. Dabei wird Ihr Anzeigenamen anstatt Ihres Benutzerprinzipalnamens verwendet:</span><span class="sxs-lookup"><span data-stu-id="06a6a-p109">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="06a6a-192">Ändern von Eigenschaften für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="06a6a-192">Change properties for all user accounts</span></span>

<span data-ttu-id="06a6a-p110">Um die Eigenschaften für alle Benutzer zu ändern, können Sie eine Kombination der Cmdlets **Get-MsolUser** und **Set-MsolUser** verwenden. Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="06a6a-p110">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="06a6a-195">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="06a6a-195">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="06a6a-196">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-196">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-197">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="06a6a-197">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="06a6a-198">Ändern von Eigenschaften für bestimmte Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="06a6a-198">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="06a6a-199">Zum Ändern der Eigenschaften für eine bestimmte Gruppe von Benutzerkonten können Sie die Kombination aus den Cmdlets **Get-MsolUser**, **Where**und **setMsolUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="06a6a-199">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="06a6a-200">Im folgende Beispiel wird der Verwendungsstandort für alle Benutzer in der Buchhaltungsabteilung in Frankreich geändert:</span><span class="sxs-lookup"><span data-stu-id="06a6a-200">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="06a6a-201">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="06a6a-201">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="06a6a-202">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-202">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-203">Suchen Sie alle Benutzerkonten, deren Abteilungs Eigenschaft auf "Accounting" festgelegt ist (**wobei {$ _. Department-EQ "Accounting"}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="06a6a-203">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="06a6a-204">Legen Sie den Benutzerstandort auf Frankreich fest (**festlegen-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="06a6a-204">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>


## <a name="see-also"></a><span data-ttu-id="06a6a-205">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="06a6a-205">See also</span></span>

[<span data-ttu-id="06a6a-206">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a6a-206">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="06a6a-207">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a6a-207">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="06a6a-208">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06a6a-208">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
