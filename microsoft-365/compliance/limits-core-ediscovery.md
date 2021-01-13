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
description: In diesem Artikel werden die Grenzwerte im eDiscovery-Kernfall in Microsoft 365 beschrieben.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799662"
---
# <a name="limits-in-core-ediscovery"></a><span data-ttu-id="d384c-103">Grenzwerte in Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d384c-103">Limits in Core eDiscovery</span></span>

<span data-ttu-id="d384c-104">In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Kernfälle und -Haltebereich aufgeführt, die einem eDiscovery-Kernfall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d384c-104">The following table lists the limits for core eDiscovery cases and holds associated with a core eDiscovery case.</span></span> <span data-ttu-id="d384c-105">Weitere Informationen zu Core eDiscovery finden Sie [unter Übersicht über Core eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="d384c-105">For more information about Core eDiscovery, see [Overview of Core eDiscovery](ediscovery-cases.md).</span></span>
    
  | <span data-ttu-id="d384c-106">Beschreibung der Beschränkung</span><span class="sxs-lookup"><span data-stu-id="d384c-106">Description of limit</span></span> | <span data-ttu-id="d384c-107">Grenze</span><span class="sxs-lookup"><span data-stu-id="d384c-107">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="d384c-108">Maximale Anzahl von Fällen für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="d384c-108">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="d384c-109">Keine Begrenzung</span><span class="sxs-lookup"><span data-stu-id="d384c-109">No limit</span></span>  <br/> |
  |<span data-ttu-id="d384c-110">Maximale Anzahl von Fall-Halte-Ins für eine Organisation</span><span class="sxs-lookup"><span data-stu-id="d384c-110">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="d384c-111">10.000</span><span class="sxs-lookup"><span data-stu-id="d384c-111">10,000</span></span>  <br/> |
  |<span data-ttu-id="d384c-112">Maximale Anzahl von Postfächern in einem Einzelfallspeicher</span><span class="sxs-lookup"><span data-stu-id="d384c-112">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="d384c-113">1,000</span><span class="sxs-lookup"><span data-stu-id="d384c-113">1,000</span></span>  <br/> |
  |<span data-ttu-id="d384c-114">Maximale Anzahl von SharePoint- und OneDrive for #A0 in einem #A1</span><span class="sxs-lookup"><span data-stu-id="d384c-114">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="d384c-115">100</span><span class="sxs-lookup"><span data-stu-id="d384c-115">100</span></span>  <br/> |
  |<span data-ttu-id="d384c-116">Die maximale Anzahl von Fällen, die auf der zentralen eDiscovery-Startseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten "Haltebereich", "Suchen" und "Exportieren" in einem Fall angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d384c-116">Maximum number of cases displayed on the core eDiscovery home page, and the maximum number of items displayed on the Holds, Searches, and Export tabs within a case.</span></span> <span data-ttu-id="d384c-117"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d384c-117"><sup>1</sup></span></span> |<span data-ttu-id="d384c-118">1,000</span><span class="sxs-lookup"><span data-stu-id="d384c-118">1,000</span></span>|
  |||

   > [!NOTE]
   > <span data-ttu-id="d384c-119"><sup>1</sup> Um eine Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten anzeigen zu können, können Sie die entsprechenden Office 365 Security & Compliance -PowerShell-Cmdlets verwenden:</span><span class="sxs-lookup"><span data-stu-id="d384c-119"><sup>1</sup> To view a list of more than 1,000 cases, holds, searches, or exports, you can use the corresponding Office 365 Security & Compliance PowerShell cmdlets:</span></span>
   > 
   > - [<span data-ttu-id="d384c-120">Get-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="d384c-120">Get-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [<span data-ttu-id="d384c-121">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="d384c-121">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [<span data-ttu-id="d384c-122">Get-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d384c-122">Get-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [<span data-ttu-id="d384c-123">Get-ComplianceSearchAction</span><span class="sxs-lookup"><span data-stu-id="d384c-123">Get-ComplianceSearchAction</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

<span data-ttu-id="d384c-124">Weitere Informationen zu Beschränkungen im Zusammenhang mit Inhaltssuchen und Exporten im Zusammenhang mit einem Core eDiscovery-Fall finden Sie unter "Grenzwerte für die Inhaltssuche" und ["Core eDiscovery".](limits-for-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="d384c-124">For more information about limits related to content searches and exports associated with a Core eDiscovery case, see [Limits for Content Search and Core eDiscovery](limits-for-content-search.md).</span></span>