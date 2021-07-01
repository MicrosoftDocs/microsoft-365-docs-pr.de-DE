---
title: Deaktivieren des Zugriffs auf Microsoft 365 Dienste beim Zuweisen von Benutzerlizenzen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Erfahren Sie, wie Sie Benutzerkonten Lizenzen zuweisen und bestimmte Servicepläne gleichzeitig mithilfe von PowerShell für Microsoft 365 deaktivieren.
ms.openlocfilehash: ca5becb8709eeab7b5c535747ac93d36fefa0da8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228903"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="a6a80-103">Deaktivieren des Zugriffs auf Microsoft 365 Dienste beim Zuweisen von Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="a6a80-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="a6a80-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a6a80-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a6a80-105">Microsoft 365 Abonnements enthalten Servicepläne für einzelne Dienste.</span><span class="sxs-lookup"><span data-stu-id="a6a80-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="a6a80-106">Microsoft 365 Administratoren müssen beim Zuweisen von Lizenzen zu Benutzern häufig bestimmte Pläne deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6a80-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="a6a80-107">Mit den Anweisungen in diesem Artikel können Sie eine Microsoft 365-Lizenz zuweisen, während Sie bestimmte Servicepläne mithilfe von PowerShell für ein einzelnes Benutzerkonto oder mehrere Benutzerkonten deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a6a80-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a6a80-108">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="a6a80-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a6a80-109">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)her.</span><span class="sxs-lookup"><span data-stu-id="a6a80-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>


<span data-ttu-id="a6a80-110">Listen Sie als Nächstes die Lizenzpläne für Ihren Mandanten mit diesem Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="a6a80-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="a6a80-111">Rufen Sie als Nächstes den Anmeldenamen des Kontos ab, dem Sie eine Lizenz hinzufügen möchten, die auch als Benutzerprinzipalname (USER Principal Name, UPN) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a6a80-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="a6a80-112">Als Nächstes kompilieren Sie eine Liste der zu aktivierenden Dienste.</span><span class="sxs-lookup"><span data-stu-id="a6a80-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="a6a80-113">Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="a6a80-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="a6a80-114">Geben Sie für den folgenden Befehlsblock den Benutzerprinzipalnamen des Benutzerkontos, die SKU-Teilnummer und die Liste der Servicepläne ein, um den erläuternden Text und die Zeichen zu aktivieren und zu \< and > entfernen.</span><span class="sxs-lookup"><span data-stu-id="a6a80-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="a6a80-115">Führen Sie anschließend die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="a6a80-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a6a80-116">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6a80-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a6a80-117">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)her.</span><span class="sxs-lookup"><span data-stu-id="a6a80-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="a6a80-118">Führen Sie als Nächstes den folgenden Befehl aus, um Ihre aktuellen Abonnements anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="a6a80-118">Next, run this command to see your current subscriptions:</span></span>

```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="a6a80-119">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="a6a80-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="a6a80-120">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a6a80-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="a6a80-121">In dem vom  `Get-MsolAccountSku`-Befehl zurückgegebenen Ergebnis gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a6a80-121">In the display of the  `Get-MsolAccountSku` command:</span></span>

- <span data-ttu-id="a6a80-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span><span class="sxs-lookup"><span data-stu-id="a6a80-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="a6a80-123">Der \<OrganizationName> Wert, den Sie bei der Registrierung für Microsoft 365 angegeben haben, ist für Ihre Organisation eindeutig.</span><span class="sxs-lookup"><span data-stu-id="a6a80-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="a6a80-124">The \<Subscription> value is for a specific subscription.</span><span class="sxs-lookup"><span data-stu-id="a6a80-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="a6a80-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="a6a80-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>

- <span data-ttu-id="a6a80-126">**ActiveUnits** ist die Anzahl der Lizenzen, die Sie für das Abonnement erworben haben.</span><span class="sxs-lookup"><span data-stu-id="a6a80-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>

- <span data-ttu-id="a6a80-127">**WarningUnits** gibt die Anzahl der Lizenzen in einem Abonnement an, die Sie nicht verlängert haben und die nach der 30-tägigen Toleranzperiode ablaufen werden.</span><span class="sxs-lookup"><span data-stu-id="a6a80-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>

- <span data-ttu-id="a6a80-128">**ConsumedUnits** ist die Anzahl der Lizenzen, die Sie Benutzern für das Abonnement zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="a6a80-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>

<span data-ttu-id="a6a80-129">Notieren Sie sich die AccountSkuId für Ihr Microsoft 365 Abonnement, das die Benutzer enthält, die Sie lizenzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a6a80-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="a6a80-130">Stellen Sie außerdem sicher, dass genügend Lizenzen zum Zuweisen verfügbar sind (subtrahieren Sie **ConsumedUnits** von **ActiveUnits**).</span><span class="sxs-lookup"><span data-stu-id="a6a80-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits**).</span></span>

<span data-ttu-id="a6a80-131">Führen Sie als Nächstes diesen Befehl aus, um die Details zu den Microsoft 365 Serviceplänen anzuzeigen, die in allen Ihren Abonnements verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="a6a80-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="a6a80-132">Anhand der vom Befehl zurückgegebenen Ausgabe können Sie bestimmen, welche Servicepläne Sie beim Zuweisen von Lizenzen an Benutzer deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a6a80-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>

<span data-ttu-id="a6a80-133">Hier ist eine partielle Liste der Dienstpläne und der entsprechenden Microsoft 365 Dienste.</span><span class="sxs-lookup"><span data-stu-id="a6a80-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="a6a80-134">In der folgenden Tabelle sind die Microsoft 365 Servicepläne und deren Anzeigenamen für die gängigsten Dienste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6a80-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="a6a80-135">Ihre individuelle Serviceplanliste sieht möglicherweise anders aus.</span><span class="sxs-lookup"><span data-stu-id="a6a80-135">Your list of service plans might be different.</span></span>

|<span data-ttu-id="a6a80-136">**Dienstplan**</span><span class="sxs-lookup"><span data-stu-id="a6a80-136">**Service plan**</span></span>|<span data-ttu-id="a6a80-137">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a6a80-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="a6a80-138">Sway</span><span class="sxs-lookup"><span data-stu-id="a6a80-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="a6a80-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a6a80-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="a6a80-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="a6a80-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="a6a80-141">Azure-Rechteverwaltung (Rights Management, RMS)</span><span class="sxs-lookup"><span data-stu-id="a6a80-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="a6a80-142">Microsoft 365 Apps for Enterprise *(zuvor Office 365 ProPlus genannt)*</span><span class="sxs-lookup"><span data-stu-id="a6a80-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="a6a80-143">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a6a80-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="a6a80-144">Büro</span><span class="sxs-lookup"><span data-stu-id="a6a80-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="a6a80-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a6a80-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="a6a80-146">Exchange Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="a6a80-146">Exchange Online Plan 2</span></span>  <br/> |

<span data-ttu-id="a6a80-147">Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="a6a80-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="a6a80-148">Nachdem Sie festgelegt haben, dass AccountSkuId und die Servicepläne deaktiviert werden sollen, können Sie einem einzelnen oder mehreren Benutzern Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a6a80-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>

### <a name="for-a-single-user"></a><span data-ttu-id="a6a80-149">Für einen einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="a6a80-149">For a single user</span></span>

<span data-ttu-id="a6a80-150">Geben Sie für einen einzelnen Benutzer den Benutzerprinzipalnamen des Benutzerkontos, die AccountSkuId und die Liste der Dienstpläne ein, um den erläuternden Text und die Zeichen zu deaktivieren und zu \< and > entfernen.</span><span class="sxs-lookup"><span data-stu-id="a6a80-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="a6a80-151">Führen Sie anschließend die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="a6a80-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="a6a80-152">Hier ein Beispiel für einen Befehlsblock für das Konto namens „belindan@contoso.com“, für contoso:ENTERPRISEPACK-Lizenz, und die zu deaktivierenden Servicepläne lauten: RMS_S_ENTERPRISE, SCHLINGERN, INTUNE_O365 und YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="a6a80-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="a6a80-153">Für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="a6a80-153">For multiple users</span></span>

<span data-ttu-id="a6a80-p109">Erstellen Sie zum Ausführen dieser Aufgabe eine CSV-Textdatei mit den UserPrincipalName- und UsageLocation-Feldern. Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6a80-p109">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields. Here is an example:</span></span>

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="a6a80-156">Geben Sie als Nächstes den Speicherort für die CSV-Eingabe- und CSV-Ausgabedateien, die Konto-SKU-ID und die Liste der zu deaktivierenden Servicepläne ein, und führen Sie anschließend die resultierenden Befehle in der PowerShell-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="a6a80-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="a6a80-157">Dieser PowerShell-Befehlsblock:</span><span class="sxs-lookup"><span data-stu-id="a6a80-157">This PowerShell command block:</span></span>

- <span data-ttu-id="a6a80-158">Zeigt den Benutzerprinzipalnamen für jeden Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="a6a80-158">Displays the user principal name of each user.</span></span>

- <span data-ttu-id="a6a80-159">Weist jedem Benutzer die angepassten Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="a6a80-159">Assigns customized licenses to each user.</span></span>

- <span data-ttu-id="a6a80-160">Erstellt eine CSV-Datei mit allen Benutzern, die verarbeitet wurden, und zeigt den Status ihrer Lizenz an.</span><span class="sxs-lookup"><span data-stu-id="a6a80-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6a80-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6a80-161">See also</span></span>

[<span data-ttu-id="a6a80-162">Deaktivieren des Zugriffs auf Microsoft 365-Dienste mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6a80-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)

[<span data-ttu-id="a6a80-163">Deaktivieren des Zugriffs auf Sway mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6a80-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)

[<span data-ttu-id="a6a80-164">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6a80-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="a6a80-165">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6a80-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)