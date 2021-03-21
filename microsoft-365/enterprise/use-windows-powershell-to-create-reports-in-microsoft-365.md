---
title: Verwenden von PowerShell zum Erstellen von Berichten für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 1ea4d4ec-af89-496f-9678-701867f5a6fc
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um Berichte zu erstellen, die Sie im Microsoft 365 Admin Center nicht erstellen können.'
ms.openlocfilehash: 12cba74d114ea03804741335bd34ece403926033
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924696"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="c2920-103">Verwenden von PowerShell zum Erstellen von Berichten für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2920-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="c2920-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c2920-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c2920-105">Viele verschiedene Berichte sind im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2920-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c2920-106">Diese Berichte enthalten jedoch nur so viele Informationen, und manchmal benötigen Sie mehr.</span><span class="sxs-lookup"><span data-stu-id="c2920-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="c2920-107">Dann benötigen Sie PowerShell für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2920-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="c2920-108">In diesen Artikeln wird beschrieben, wie Sie PowerShell für Microsoft 365 verwenden, um Informationen von Ihrem Microsoft 365-Mandanten zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="c2920-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="c2920-109">Erste Schritte mit der Berichterstellung mit PowerShell für Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c2920-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="c2920-110">Warum Sie PowerShell für Microsoft 365 verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="c2920-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md#reveal)
    
    
- <span data-ttu-id="c2920-111">Berichte für Benutzerkonten und Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="c2920-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="c2920-112">Anzeigen von Microsoft 365-Lizenzen und -Diensten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c2920-113">Anzeigen von Microsoft 365-lizenzierten und nicht lizenzierten Benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c2920-114">Anzeigen von Microsoft 365-Kontolizenz- und Dienstdetails mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="c2920-115">Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="c2920-116">Berichte für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="c2920-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="c2920-117">Erste Schritte mit der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="c2920-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="c2920-118">Get-SPOSiteGroup – Ruft alle Gruppen in einer angegebenen Websitesammlung ab.</span><span class="sxs-lookup"><span data-stu-id="c2920-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="c2920-119">Berichte für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c2920-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="c2920-120">Verwenden von Exchange Online PowerShell zum Anzeigen von Postfächern</span><span class="sxs-lookup"><span data-stu-id="c2920-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="c2920-121">Verwandte Artikell</span><span class="sxs-lookup"><span data-stu-id="c2920-121">Related articlesl</span></span>

[<span data-ttu-id="c2920-122">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c2920-123">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2920-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c2920-124">Verwalten von SharePoint mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c2920-125">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2920-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
