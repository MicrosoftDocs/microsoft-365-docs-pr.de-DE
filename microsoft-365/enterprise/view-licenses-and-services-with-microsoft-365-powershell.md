---
title: Anzeigen von Microsoft 365-Lizenzen und -Diensten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Erläutert die Verwendung von PowerShell zum Anzeigen von Informationen zu Den Lizenzierungsplänen, Diensten und Lizenzen, die in Ihrer Microsoft 365-Organisation verfügbar sind.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924636"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="0f8a4-103">Anzeigen von Microsoft 365-Lizenzen und -Diensten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f8a4-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="0f8a4-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0f8a4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0f8a4-105">Jedes Microsoft 365-Abonnement besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="0f8a4-106">**Lizenzierungspläne** Diese werden auch als Lizenzpläne oder Microsoft 365-Pläne bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="0f8a4-107">Lizenzierungspläne definieren die Microsoft 365-Dienste, die Benutzern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="0f8a4-108">Ihr Microsoft 365-Abonnement kann mehrere Lizenzierungspläne enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="0f8a4-109">Ein Beispiel für einen Lizenzierungsplan wäre Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="0f8a4-110">**Dienste** Diese werden auch als Dienstpläne bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="0f8a4-111">Dienste sind die Microsoft 365-Produkte, -Features und -Funktionen, die in jedem Lizenzierungsplan verfügbar sind, z. B. Exchange Online und Microsoft 365 Apps for Enterprise (zuvor Office 365 ProPlus genannt).</span><span class="sxs-lookup"><span data-stu-id="0f8a4-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="0f8a4-112">Benutzern können mehrere verschiedene Lizenzen aus unterschiedlichen Lizenzierungsplänen zugewiesen sein, über die sie Zugriff auf unterschiedliche Dienste haben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="0f8a4-113">**Lizenzen** Jeder Lizenzierungsplan enthält die Anzahl der lizenzen, die Sie erworben haben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="0f8a4-114">Sie weisen Benutzern Lizenzen zu, damit sie die microsoft 365-Dienste verwenden können, die im Lizenzierungsplan definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="0f8a4-115">Jedes Benutzerkonto benötigt mindestens eine Lizenz aus einem Lizenzierungsplan, damit sie sich bei Microsoft 365 anmelden und die Dienste nutzen können.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="0f8a4-116">Sie können PowerShell für Microsoft 365 verwenden, um Details zu den verfügbaren Lizenzierungsplänen, Lizenzen und Diensten in Ihrer Microsoft 365-Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="0f8a4-117">Weitere Informationen zu den Produkten, Features und Diensten, die in verschiedenen Office 365-Abonnements verfügbar sind, finden Sie unter [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span><span class="sxs-lookup"><span data-stu-id="0f8a4-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="0f8a4-118">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="0f8a4-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="0f8a4-119">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="0f8a4-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="0f8a4-120">Führen Sie den folgenden Befehl aus, um Zusammenfassungsinformationen zu Ihren aktuellen Lizenzierungsplänen und den verfügbaren Lizenzen für jeden Plan anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="0f8a4-121">Die Ergebnisse enthalten:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-121">The results contain:</span></span>
  
- <span data-ttu-id="0f8a4-p105">**SkuPartNumber:** Zeigt die verfügbaren Lizenzierungspläne für Ihre Organisation an. `ENTERPRISEPACK` ist z. B. der Name des Lizenzplans für Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-p105">**SkuPartNumber:** Shows the available licensing plans for your organization. For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="0f8a4-124">**Enabled:**: Gibt die Anzahl der Lizenzen an, die Sie im Rahmen eines spezifischen Lizenzierungsplans erworben haben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="0f8a4-125">**ConsumedUnits**: Gibt die Anzahl der Lizenzen an, die Sie Benutzern aus einem bestimmten Lizenzierungsplan zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="0f8a4-126">Um Details zu den Microsoft 365-Diensten anzuzeigen, die in allen Lizenzplänen verfügbar sind, zeigen Sie zunächst eine Liste Ihrer Lizenzpläne an.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="0f8a4-127">Speichern Sie dann die Informationen zu den Lizenzplänen in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="0f8a4-128">Zeigen Sie die Dienste in einem spezifischen Lizenzplan an.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="0f8a4-129">\<index> ist eine ganze Zahl, die die Zeilennummer des Lizenzplans aus der Anzeige des Befehls `Get-AzureADSubscribedSku | Select SkuPartNumber` minus 1 angibt.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="0f8a4-130">Wenn die Anzeige des `Get-AzureADSubscribedSku | Select SkuPartNumber`-Befehls z.B. folgendermaßen lautet:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="0f8a4-131">Lautet der Befehl zum Anzeigen der Dienste für den Plan ENTERPRISEPREMIUM folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="0f8a4-p106">ENTERPRISEPREMIUM ist die dritte Zeile. Aus diesem Grund wird der Indexwert mit (3 - 1) oder 2 angegeben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-p106">ENTERPRISEPREMIUM is the third row. Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="0f8a4-134">Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="0f8a4-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0f8a4-135">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f8a4-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0f8a4-136">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="0f8a4-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="0f8a4-137">Ein PowerShell-Skript steht zur Verfügung, das die in diesem Thema erläuterten Verfahren automatisiert.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="0f8a4-138">Insbesondere können Sie mit dem Skript Dienste in Ihrer Microsoft 365-Organisation, einschließlich Sway, anzeigen und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="0f8a4-139">Weitere Informationen finden Sie unter [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0f8a4-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="0f8a4-140">Führen Sie den folgenden Befehl aus, um eine Übersicht über Ihre aktuellen Lizenzierungspläne und die in den einzelnen Plänen verfügbaren Lizenzen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="0f8a4-141">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="0f8a4-142">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="0f8a4-143">Die Ergebnisse enthalten die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="0f8a4-144">**AccountSkuId:** Zeigen Sie die verfügbaren Lizenzierungspläne für Ihre Organisation mithilfe der Syntax `<CompanyName>:<LicensingPlan>` an.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="0f8a4-145">_\<CompanyName>_ ist der Wert, den Sie bei der Registrierung bei Microsoft 365 angegeben haben und für Ihre Organisation eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="0f8a4-146">Der _\<LicensingPlan>_ Wert ist für alle gleich.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="0f8a4-147">Im Wert ist beispielsweise der Firmenname , und der Name des Lizenzierungsplans , der der `litwareinc:ENTERPRISEPACK`  `litwareinc`  `ENTERPRISEPACK` Systemname für Office 365 Enterprise E3 ist.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="0f8a4-148">**ActiveUnits**: Gibt die Anzahl der Lizenzen an, die Sie im Rahmen eines spezifischen Lizenzierungsplans erworben haben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="0f8a4-149">**WarningUnits**: Gibt die Anzahl der Lizenzen in einem Lizenzierungsplan an, die Sie nicht verlängert haben und die nach der 30-tägigen Toleranzperiode ablaufen werden.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="0f8a4-150">**ConsumedUnits**: Gibt die Anzahl der Lizenzen an, die Sie Benutzern aus einem bestimmten Lizenzierungsplan zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="0f8a4-151">Führen Sie den folgenden Befehl aus, um Details zu den Microsoft 365-Diensten anzuzeigen, die in allen Lizenzplänen verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="0f8a4-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="0f8a4-152">In der folgenden Tabelle sind die Microsoft 365-Dienstpläne und deren Anzeigenamen für die gängigsten Dienste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="0f8a4-153">Ihre individuelle Serviceplanliste sieht möglicherweise anders aus.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="0f8a4-154">**Dienstplan**</span><span class="sxs-lookup"><span data-stu-id="0f8a4-154">**Service plan**</span></span>|<span data-ttu-id="0f8a4-155">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0f8a4-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="0f8a4-156">Sway</span><span class="sxs-lookup"><span data-stu-id="0f8a4-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="0f8a4-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f8a4-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="0f8a4-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="0f8a4-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="0f8a4-159">Azure-Rechteverwaltung (Rights Management, RMS)</span><span class="sxs-lookup"><span data-stu-id="0f8a4-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="0f8a4-160">Microsoft 365 Apps for Enterprise *(zuvor Office 365 ProPlus genannt)*</span><span class="sxs-lookup"><span data-stu-id="0f8a4-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="0f8a4-161">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0f8a4-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="0f8a4-162">Office</span><span class="sxs-lookup"><span data-stu-id="0f8a4-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="0f8a4-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0f8a4-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="0f8a4-164">Exchange Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="0f8a4-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="0f8a4-165">Eine vollständige Liste von Lizenzplänen (auch bezeichnet als Produktnamen), deren enthaltenen Serviceplänen und die entsprechenden Anzeigenamen finden Sie unter [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="0f8a4-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="0f8a4-166">Verwenden Sie die folgende Syntax, um Details zu den Microsoft 365-Diensten anzuzeigen, die in einem bestimmten Lizenzierungsplan verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="0f8a4-167">In diesem Beispiel werden die Dienste gezeigt, die im Lizenzplan litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0f8a4-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="0f8a4-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f8a4-168">See also</span></span>

[<span data-ttu-id="0f8a4-169">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f8a4-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0f8a4-170">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f8a4-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0f8a4-171">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f8a4-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)