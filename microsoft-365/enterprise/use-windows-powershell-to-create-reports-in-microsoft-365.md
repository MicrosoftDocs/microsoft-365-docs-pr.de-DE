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
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um Berichte zu erstellen, die Sie nicht im Microsoft 365 Admin Center erstellen können.'
ms.openlocfilehash: 9e3b90dcdd32f80125175ad2e15a852db51e17f8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572741"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="f8dd5-103">Verwenden von PowerShell zum Erstellen von Berichten für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8dd5-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="f8dd5-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f8dd5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f8dd5-105">Viele verschiedene Berichte sind im Microsoft 365 Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f8dd5-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f8dd5-106">Aber diese Berichte liefern nur so viele Informationen, und manchmal brauchen Sie mehr.</span><span class="sxs-lookup"><span data-stu-id="f8dd5-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="f8dd5-107">Dann benötigen Sie PowerShell für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8dd5-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="f8dd5-108">In diesen Artikeln wird beschrieben, wie Sie PowerShell für Microsoft 365 verwenden, um Informationen von Ihrem Microsoft 365-Mandanten abzubekommen:</span><span class="sxs-lookup"><span data-stu-id="f8dd5-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="f8dd5-109">Erste Schritte mit der Berichterstellung mit PowerShell für Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="f8dd5-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="f8dd5-110">Warum Sie PowerShell für Microsoft 365 verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="f8dd5-110">Why you need to use PowerShell for Microsoft 365</span></span>](./why-you-need-to-use-microsoft-365-powershell.md)
    
    
- <span data-ttu-id="f8dd5-111">Berichte für Benutzerkonten und Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="f8dd5-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="f8dd5-112">Anzeigen Microsoft 365 Lizenzen und Dienste mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="f8dd5-113">Microsoft 365 lizenzierte und nicht lizenzierte Benutzer mit PowerShell anzeigen</span><span class="sxs-lookup"><span data-stu-id="f8dd5-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="f8dd5-114">Anzeigen Microsoft 365 Kontolizenz- und Servicedetails mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="f8dd5-115">Anzeigen Microsoft 365 Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="f8dd5-116">Berichte für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="f8dd5-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="f8dd5-117">Erste Schritte mit der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-117">Get started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="f8dd5-118">Get-SPOSiteGroup - Ruft alle Gruppen in einer angegebenen Websitesammlung ab</span><span class="sxs-lookup"><span data-stu-id="f8dd5-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](/powershell/module/sharepoint-online/get-spositegroup)
    
- <span data-ttu-id="f8dd5-119">Berichte für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f8dd5-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="f8dd5-120">Verwenden Exchange Online PowerShell zum Anzeigen von Postfach</span><span class="sxs-lookup"><span data-stu-id="f8dd5-120">Use Exchange Online PowerShell to display mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/use-powershell-to-display-mailbox-information)
    
    
## <a name="related-articles"></a><span data-ttu-id="f8dd5-121">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f8dd5-121">Related articles</span></span>

[<span data-ttu-id="f8dd5-122">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f8dd5-123">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8dd5-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f8dd5-124">Verwalten SharePoint mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f8dd5-125">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8dd5-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
