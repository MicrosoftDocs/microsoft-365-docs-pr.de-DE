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
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365 zum Erstellen von Berichten, die im Microsoft 365 Admin Center nicht erstellt werden können.'
ms.openlocfilehash: 10000f62b1d6a747cf0373623c6038b080666e1a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753978"
---
# <a name="use-powershell-to-create-reports-for-microsoft-365"></a><span data-ttu-id="4ea4e-103">Verwenden von PowerShell zum Erstellen von Berichten für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ea4e-103">Use PowerShell to create reports for Microsoft 365</span></span>

<span data-ttu-id="4ea4e-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4ea4e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4ea4e-105">Im Microsoft 365 Admin Center stehen viele verschiedene Berichte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4ea4e-105">Many different reports are available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4ea4e-106">Diese Berichte bieten jedoch nur so viele Informationen, und manchmal benötigen Sie mehr.</span><span class="sxs-lookup"><span data-stu-id="4ea4e-106">But these reports only provide so much information, and sometimes you need more.</span></span> <span data-ttu-id="4ea4e-107">Das ist, wenn Sie PowerShell für Microsoft 365 benötigen.</span><span class="sxs-lookup"><span data-stu-id="4ea4e-107">That's when you need PowerShell for Microsoft 365.</span></span>
  
<span data-ttu-id="4ea4e-108">In diesen Artikeln wird beschrieben, wie Sie mithilfe von PowerShell für Microsoft 365 Informationen von Ihrem Microsoft 365-Mandanten erhalten:</span><span class="sxs-lookup"><span data-stu-id="4ea4e-108">These articles describe how to use PowerShell for Microsoft 365 to get information from your Microsoft 365 tenant:</span></span>
  
- <span data-ttu-id="4ea4e-109">Erste Schritte mit der Berichterstellung mithilfe von PowerShell für Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="4ea4e-109">Get started with reporting using PowerShell for Microsoft 365:</span></span>
    
  - [<span data-ttu-id="4ea4e-110">Warum Sie PowerShell für Microsoft 365 verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="4ea4e-110">Why you need to use PowerShell for Microsoft 365</span></span>](https://technet.microsoft.com/library/dn568034.aspx#reveal)
    
    
- <span data-ttu-id="4ea4e-111">Berichte für Benutzerkonten und Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="4ea4e-111">Reports for user accounts and licenses:</span></span>
    
  - [<span data-ttu-id="4ea4e-112">Anzeigen von Microsoft 365-Lizenzen und-Diensten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-112">View Microsoft 365 licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="4ea4e-113">Anzeigen von Microsoft 365 lizenzierten und nicht lizenzierten Benutzern mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-113">View Microsoft 365 licensed and unlicensed users with PowerShell</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="4ea4e-114">Anzeigen von Microsoft 365-Konto Lizenz-und-Dienstdetails mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-114">View Microsoft 365 account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="4ea4e-115">Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-115">View Microsoft 365 user accounts with PowerShell</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
    
- <span data-ttu-id="4ea4e-116">Berichte für SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="4ea4e-116">Reports for SharePoint Online:</span></span>
    
  - [<span data-ttu-id="4ea4e-117">Erste Schritte mit der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-117">Get started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
    
  - [<span data-ttu-id="4ea4e-118">Get-SPOSiteGroup-Ruft alle Gruppen für eine angegebene Websitesammlung ab.</span><span class="sxs-lookup"><span data-stu-id="4ea4e-118">Get-SPOSiteGroup - Gets all the groups on a specified site collection</span></span>](https://technet.microsoft.com/library/122f4099-c78d-4cce-bab0-4343b04596ae.aspx)
    
- <span data-ttu-id="4ea4e-119">Berichte für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="4ea4e-119">Reports for Exchange Online:</span></span>
    
  - [<span data-ttu-id="4ea4e-120">Verwenden Exchange Online PowerShell zum Anzeigen von Postfächern</span><span class="sxs-lookup"><span data-stu-id="4ea4e-120">Use Exchange Online PowerShell to display mailbox</span></span>](https://technet.microsoft.com/library/13843002-56ca-4b75-81c5-84386522b01b.aspx)
    
    
## <a name="related-articlesl"></a><span data-ttu-id="4ea4e-121">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="4ea4e-121">Related articlesl</span></span>

[<span data-ttu-id="4ea4e-122">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-122">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4ea4e-123">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ea4e-123">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4ea4e-124">Verwalten von SharePoint mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-124">Manage SharePoint with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4ea4e-125">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ea4e-125">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  