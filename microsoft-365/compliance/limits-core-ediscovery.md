---
title: Grenzwerte im eDiscovery-Kernfall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In diesem Artikel werden die Grenzen im eDiscovery-Kernfall in Microsoft 365 beschrieben.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423446"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="aa8f5-103">Grenzwerte in Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="aa8f5-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="aa8f5-104">In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Kernfälle und -Hüllen aufgeführt, die einem eDiscovery-Kernfall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="aa8f5-105">Weitere Informationen zu Core eDiscovery finden Sie [unter Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="aa8f5-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="aa8f5-106">Beschreibung der Beschränkung</span><span class="sxs-lookup"><span data-stu-id="aa8f5-106">Description of limit</span></span> | <span data-ttu-id="aa8f5-107">Grenze</span><span class="sxs-lookup"><span data-stu-id="aa8f5-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="aa8f5-108">Maximale Anzahl von Fällen für eine Organisation.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-108">Maximum number of cases for an organization.</span></span>  <br/> |<span data-ttu-id="aa8f5-109">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="aa8f5-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="aa8f5-110">Maximale Anzahl von Fällen für eine Organisation.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-110">Maximum number of case holds for an organization.</span></span>  <br/> |<span data-ttu-id="aa8f5-111">10.000</span><span class="sxs-lookup"><span data-stu-id="aa8f5-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="aa8f5-112">Maximale Anzahl von Postfächern in einem einzelnen Fall.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-112">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="aa8f5-113">Dieser Grenzwert umfasst die gesamtzahl der Benutzerpostfächer und die Postfächer, die Microsoft 365-Gruppen, Microsoft Teams und Yammer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-113">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="aa8f5-114">1.000</span><span class="sxs-lookup"><span data-stu-id="aa8f5-114">1,000</span></span>  <br/> |
  |<span data-ttu-id="aa8f5-115">Maximale Anzahl von Websites in einem einzigen Fall.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-115">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="aa8f5-116">Dieser Grenzwert umfasst die gesamtzahl der OneDrive for #A0 und #A1 sowie die Websites, die Microsoft 365-Gruppen, Microsoft Teams und Yammer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-116">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="aa8f5-117">100</span><span class="sxs-lookup"><span data-stu-id="aa8f5-117">100</span></span>  <br/> |
  |<span data-ttu-id="aa8f5-118">Maximale Anzahl von Fällen, die auf der eDiscovery-Hauptseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten Halte-, Such- und Exportregisterkarten in einem Fall angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aa8f5-118">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="aa8f5-119"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="aa8f5-119"><sup>1</sup></span></span> |<span data-ttu-id="aa8f5-120">1.000</span><span class="sxs-lookup"><span data-stu-id="aa8f5-120">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="aa8f5-121"><sup>1</sup> Zum Anzeigen einer Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten können Sie die entsprechenden Office 365 Security & Compliance-PowerShell-Cmdlets verwenden:</span><span class="sxs-lookup"><span data-stu-id="aa8f5-121"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="aa8f5-122">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="aa8f5-122">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="aa8f5-123">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="aa8f5-123">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="aa8f5-124">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="aa8f5-124">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="aa8f5-125">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="aa8f5-125">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="aa8f5-126">Weitere Informationen zu Beschränkungen im Zusammenhang mit Inhaltssuchen und -exporten im Zusammenhang mit einem Core eDiscovery-Fall finden Sie unter [Limits for Content Search und Core eDiscovery](limits-for-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="aa8f5-126">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>