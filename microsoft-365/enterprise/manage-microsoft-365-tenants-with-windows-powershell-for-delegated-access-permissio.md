---
title: Verwalten von Microsoft 365-Mandanten mit Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: In diesem Artikel erfahren Sie, wie Sie mit PowerShell für Microsoft 365 ihre Kundenmandanten verwalten.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690413"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="32f75-103">Verwalten von Microsoft 365-Mandanten mit Windows PowerShell für Partner mit Delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="32f75-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="32f75-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="32f75-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="32f75-105">Windows PowerShell ermöglicht es den Anbietern von Syndication-und Cloud Solution Providern (CSP), Kundenmandanten Einstellungen, die im Microsoft 365 Admin Center nicht verfügbar sind, einfach zu verwalten und zu melden.</span><span class="sxs-lookup"><span data-stu-id="32f75-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="32f75-106">Beachten Sie, dass für das Partneradministrator Konto die Berechtigung verwalten im Namen von (AOBO) erforderlich ist, um eine Verbindung mit dem Mandanten des Kunden herzustellen.</span><span class="sxs-lookup"><span data-stu-id="32f75-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>
  
<span data-ttu-id="32f75-107">DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP).</span><span class="sxs-lookup"><span data-stu-id="32f75-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="32f75-108">Häufig handelt es sich um Netzwerk- oder Telekom-Anbieter für andere Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="32f75-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="32f75-109">Sie bündeln Microsoft 365-Abonnements für Ihre Kunden in ihren Dienst angeboten.</span><span class="sxs-lookup"><span data-stu-id="32f75-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="32f75-110">Wenn Sie ein Microsoft 365-Abonnement verkaufen, werden Ihnen automatisch Administratoren im Namen von (AOBO) Berechtigungen für den Kundenmandanten erteilt, damit Sie den Kundenmandanten verwalten und melden können.</span><span class="sxs-lookup"><span data-stu-id="32f75-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="32f75-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="32f75-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="32f75-112">Für die Verfahren in diesem Thema müssen Sie eine Verbindung herstellen, um [eine Verbindung mit Microsoft 365 mit PowerShell](connect-to-microsoft-365-powershell.md)herzustellen.</span><span class="sxs-lookup"><span data-stu-id="32f75-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="32f75-113">Sie benötigen auch die Administratoranmeldeinformationen Ihres Partnermandanten.</span><span class="sxs-lookup"><span data-stu-id="32f75-113">You also need your partner tenant administrator credentials.</span></span>
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="32f75-114">Was möchten Sie machen?</span><span class="sxs-lookup"><span data-stu-id="32f75-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="32f75-115">Auflisten aller Mandanten-IDs</span><span class="sxs-lookup"><span data-stu-id="32f75-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="32f75-p103">Wenn Sie über mehr als 500 Mandanten verfügen, fügen Sie in die Cmdlet-Syntax entweder  _-All_ oder _-MaxResultsParameter_ ein. Dies gilt für andere Cmdlets mit einer umfangreichen Ausgabe, wie z. B. **Get-MsolUser**.</span><span class="sxs-lookup"><span data-stu-id="32f75-p103">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_. This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>
  
<span data-ttu-id="32f75-118">Führen Sie den folgenden Befehl aus, um alle Kundenmandanten-IDs aufzulisten, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="32f75-118">To list all customer tenant Ids that you have access to, run this command.</span></span>
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="32f75-119">Dies zeigt eine Liste aller Kundenmandanten nach **TenantId** geordnet an.</span><span class="sxs-lookup"><span data-stu-id="32f75-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="32f75-120">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="32f75-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="32f75-121">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="32f75-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="32f75-122">Abrufen einer Mandanten-ID mithilfe des Domänennamens</span><span class="sxs-lookup"><span data-stu-id="32f75-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="32f75-p105">Zum Abrufen der **TenantId** eines bestimmten Kundenmandanten nach Domänenname führen Sie den folgenden Befehl aus. Ersetzen Sie _<domänenname.onmicrosoft.com>_ durch den eigentlichen Domänennamen des gewünschten Kundenmandanten.</span><span class="sxs-lookup"><span data-stu-id="32f75-p105">To get the **TenantId** for a specific customer tenant by domain name, run this command. Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="32f75-125">Auflisten aller Domänen für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="32f75-125">List all domains for a tenant</span></span>

<span data-ttu-id="32f75-p106">Um alle Domänen für einen einzigen Kundenmandanten aufzurufen, führen Sie den folgenden Befehl aus. Ersetzen Sie  _<customer TenantId value>_ durch den eigentlichen Wert.</span><span class="sxs-lookup"><span data-stu-id="32f75-p106">To get all domains for any one customer tenant, run this command. Replace  _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="32f75-128">Wenn Sie zusätzliche Domänen registriert haben, werden alle Domänen zurückgegeben, die mit der **TenantId** des Kunden verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="32f75-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="32f75-129">Abrufen einer Zuordnung aller Mandanten und registrierten Domänen</span><span class="sxs-lookup"><span data-stu-id="32f75-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="32f75-130">In der vorherigen PowerShell für Microsoft 365-Befehle wurde gezeigt, wie Sie entweder Mandanten-IDs oder Domänen abrufen, jedoch nicht beides gleichzeitig und ohne eine eindeutige Zuordnung zwischen allen.</span><span class="sxs-lookup"><span data-stu-id="32f75-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="32f75-131">Mit diesem Befehl wird eine Auflistung aller ihrer Kundenmandanten-IDs und ihrer Domänen generiert.</span><span class="sxs-lookup"><span data-stu-id="32f75-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="32f75-132">Abrufen aller Benutzer für einen Mandanten</span><span class="sxs-lookup"><span data-stu-id="32f75-132">Get all users for a tenant</span></span>

<span data-ttu-id="32f75-p108">Hierdurch werden der **UserPrincipalName**, der **DisplayName** und der Status **isLicensed** für alle Benutzer eines bestimmten Mandanten angezeigt. Ersetzen Sie _<customer TenantId value>_ durch den eigentlichen Wert.</span><span class="sxs-lookup"><span data-stu-id="32f75-p108">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant. Replace _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="32f75-135">Abrufen aller Details eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="32f75-135">Get all details about a user</span></span>

<span data-ttu-id="32f75-p109">Wenn Sie alle Eigenschaften eines bestimmten Benutzers anzeigen möchten, führen Sie den folgenden Befehl aus:  Ersetzen Sie _<customer TenantId value>_ und _<user principal name value>_ durch die eigentlichen Werte.</span><span class="sxs-lookup"><span data-stu-id="32f75-p109">If you want to see all the properties of a particular user, run this command. Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="32f75-138">Hinzufügen von Benutzern, Festlegen von Optionen und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="32f75-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="32f75-139">Die Massenerstellung,-Konfiguration und-Lizenzierung von Microsoft 365-Benutzern ist besonders effizient durch die Verwendung von PowerShell für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32f75-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="32f75-140">In diesem zweistufigen Prozess erstellen Sie zuerst Einträge für alle Benutzer, die Sie in einer CSV-Datei (Comma-Separated Value) hinzufügen möchten, und importieren diese Datei dann mithilfe von PowerShell für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32f75-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span> 
  
#### <a name="create-a-csv-file"></a><span data-ttu-id="32f75-141">Erstellen einer CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="32f75-141">Create a CSV file</span></span>

<span data-ttu-id="32f75-142">Erstellen Sie eine CSV-Datei anhand dieses Formats:</span><span class="sxs-lookup"><span data-stu-id="32f75-142">Create a CSV file by using this format:</span></span>
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
<span data-ttu-id="32f75-143">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="32f75-143">where:</span></span>
  
- <span data-ttu-id="32f75-p111">**UsageLocation**: Der Wert hierfür ist der zweistellige ISO-Länder-/Regionscode des Benutzers. Die Länder-/Regioinscodes finden Sie auf der[ISO-Online-Browserplattform](https://go.microsoft.com/fwlink/p/?LinkId=532703). Der Code für die Vereinigten Staaten lautet z. B. „US", der Code für Brasilien „BR".</span><span class="sxs-lookup"><span data-stu-id="32f75-p111">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user. The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). For example, the code for the United States is US, and the code for Brazil is BR.</span></span> 
    
- <span data-ttu-id="32f75-p112">**LicenseAssignment**: Der Wert hierfür verwendet das folgende Format: `syndication-account:<PROVISIONING_ID>`. Wenn Sie Kundenmandantenbenutzern zum Beispiel O365_Business_Premium-Lizenzen zuweisen, sieht der Wert **LicenseAssignment** wie folgt aus: **syndication-account:O365_Business_Premium**. Sie finden die PROVISIONING_IDs im Syndication-Partnerportal, auf das Sie als Syndication- oder CSP-Partner Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="32f75-p112">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`. For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**. You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>
    
#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="32f75-150">Importieren der CSV-Datei und Erstellen der Benutzer</span><span class="sxs-lookup"><span data-stu-id="32f75-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="32f75-p113">Nachdem Sie die CSV-Datei erstellt haben, führen Sie den folgenden Befehl zum Erstellen von Benutzerkonten mit nicht ablaufenden Kennwörtern aus. Der Benutzer muss das Kennwort beim ersten Anmelden ändern, und es weist ihm die ausgewählte Lizenz zu. Achten Sie darauf, dass Sie den richtigen Namen der CSV-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="32f75-p113">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify. Be sure to substitute the correct CSV file name.</span></span>
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="32f75-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32f75-153">See also</span></span>

#### 

[<span data-ttu-id="32f75-154">Hilfe für Partner</span><span class="sxs-lookup"><span data-stu-id="32f75-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)

