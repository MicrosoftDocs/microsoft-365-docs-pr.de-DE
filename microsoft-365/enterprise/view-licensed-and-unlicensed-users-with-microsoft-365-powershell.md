---
title: Anzeigen lizenzierter und nicht lizenzierter Microsoft 365 benutzern mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: In diesem Artikel wird erläutert, wie Sie powerShell zum Anzeigen lizenzierter und nicht lizenzierter Microsoft 365 verwenden.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651384"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="9ca64-103">Anzeigen lizenzierter und nicht lizenzierter Microsoft 365 benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca64-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="9ca64-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9ca64-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9ca64-105">Benutzerkonten in Ihrer Microsoft 365 verfügen möglicherweise über einige, alle oder keine der verfügbaren Lizenzen, die ihnen aus den in Ihrer Organisation verfügbaren Lizenzierungsplänen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="9ca64-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="9ca64-106">Sie können PowerShell für Microsoft 365 verwenden, um die lizenzierten und nicht lizenzierten Benutzer in Ihrer Organisation schnell zu finden.</span><span class="sxs-lookup"><span data-stu-id="9ca64-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9ca64-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="9ca64-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9ca64-108">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="9ca64-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="9ca64-109">Führen Sie den folgenden Befehl aus, um die Liste aller Benutzerkonten in Ihrer Organisation anzeigen zu können, denen keine Lizenzierungspläne zugewiesen wurden (nicht lizenzierte Benutzer):</span><span class="sxs-lookup"><span data-stu-id="9ca64-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="9ca64-110">Führen Sie den folgenden Befehl aus, um die Liste aller Benutzerkonten in Ihrer Organisation anzeigen zu können, denen Ihre Lizenzierungspläne (lizenzierte Benutzer) zugewiesen wurden:</span><span class="sxs-lookup"><span data-stu-id="9ca64-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="9ca64-111">Verwenden Sie den Befehl, um alle Benutzer in Ihrem Abonnement `Get-AzureAdUser -All $true` auflisten.</span><span class="sxs-lookup"><span data-stu-id="9ca64-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9ca64-112">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca64-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9ca64-113">Stellen Sie [zunächst eine Verbindung zu Ihrem Microsoft 365 mandanten.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="9ca64-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="9ca64-114">Führen Sie den folgenden Befehl in PowerShell aus, um die Liste aller Benutzerkonten und deren Lizenzierungsstatus in Ihrer Organisation anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="9ca64-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="9ca64-115">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="9ca64-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9ca64-116">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="9ca64-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="9ca64-117">Führen Sie den folgenden Befehl aus, um die Liste aller nicht lizenzierten Benutzerkonten in Ihrer Organisation anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="9ca64-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="9ca64-118">Führen Sie den folgenden Befehl aus, um die Liste aller lizenzierten Benutzerkonten in Ihrer Organisation anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="9ca64-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="9ca64-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ca64-119">See also</span></span>

[<span data-ttu-id="9ca64-120">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca64-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9ca64-121">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca64-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9ca64-122">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ca64-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
