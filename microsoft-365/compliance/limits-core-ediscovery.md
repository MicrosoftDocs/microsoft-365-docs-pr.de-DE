---
title: Grenzen im zentralen eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In diesem Artikel werden die Grenzwerte im zentralen eDiscovery-Fall in Microsoft 365 beschrieben.
ms.openlocfilehash: 4d91b81caee31e693ce29c6d8d629d563d973ae7
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551448"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="ff016-103">Grenzwerte in der zentralen eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ff016-103">Limits in core eDiscovery</span></span>

<span data-ttu-id="ff016-104">In der folgenden Tabelle sind die Grenzwerte für zentrale eDiscovery-Fälle und haltebereiche aufgelistet, die einem zentralen eDiscovery-Fall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ff016-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="ff016-105">Weitere Informationen zu Kern-eDiscovery finden Sie unter [Overview of Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="ff016-105">For more information about core eDiscovery, see [Overview of core eDiscovery](ediscovery-cases.md).</span></span>
    
  |<span data-ttu-id="ff016-106">**Beschreibung der Beschränkung**</span><span class="sxs-lookup"><span data-stu-id="ff016-106">**Description of limit**</span></span>|<span data-ttu-id="ff016-107">**Grenzwert**</span><span class="sxs-lookup"><span data-stu-id="ff016-107">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="ff016-108">Maximale Anzahl von Fällen für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="ff016-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="ff016-109">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="ff016-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="ff016-110">Maximale Anzahl von Fall Behältern für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="ff016-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="ff016-111">10.000</span><span class="sxs-lookup"><span data-stu-id="ff016-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="ff016-112">Maximale Anzahl von Postfächern in einem einzigen Aufbewahrungs Fall</span><span class="sxs-lookup"><span data-stu-id="ff016-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="ff016-113">1.000</span><span class="sxs-lookup"><span data-stu-id="ff016-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="ff016-114">Maximale Anzahl von SharePoint-und OneDrive für Unternehmen-Websites in einem einzigen Aufbewahrungs Fall</span><span class="sxs-lookup"><span data-stu-id="ff016-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="ff016-115">100</span><span class="sxs-lookup"><span data-stu-id="ff016-115">100</span></span>  <br/> |
  |<span data-ttu-id="ff016-116">Die maximale Anzahl von Fällen, die auf der zentralen eDiscovery-Startseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten Holds, suchen und Exportieren in einem Fall angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff016-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="ff016-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ff016-117"><sup>1</sup></span></span> |<span data-ttu-id="ff016-118">1.000</span><span class="sxs-lookup"><span data-stu-id="ff016-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="ff016-119"><sup>1</sup> Wenn Sie eine Liste mit mehr als 1.000 Fällen, Aufbewahrungen, Suchvorgängen oder Exporten anzeigen möchten, können Sie das entsprechende PowerShell-Cmdlet Office 365 Security & Compliance verwenden:</span><span class="sxs-lookup"><span data-stu-id="ff016-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlet:</span></span><br/> [<span data-ttu-id="ff016-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="ff016-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [<span data-ttu-id="ff016-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="ff016-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [<span data-ttu-id="ff016-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ff016-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [<span data-ttu-id="ff016-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="ff016-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)
