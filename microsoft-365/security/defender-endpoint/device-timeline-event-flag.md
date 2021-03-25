---
title: Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen
description: Verwenden von Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen zum
keywords: Defender for Endpoint-Gerätezeitachse, Ereigniskennzeichen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165153"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="45749-104">Microsoft Defender for Endpoint-Gerätezeitachsenereigniskennzeichen</span><span class="sxs-lookup"><span data-stu-id="45749-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45749-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="45749-105">**Applies to:**</span></span>
- [<span data-ttu-id="45749-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="45749-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="45749-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45749-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="45749-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="45749-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45749-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="45749-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="45749-110">Ereigniskennzeichen in der Zeitachse des Defender for Endpoint-Geräts helfen Ihnen beim Filtern und Organisieren bestimmter Ereignisse, wenn Sie potenzielle Angriffe untersuchen.</span><span class="sxs-lookup"><span data-stu-id="45749-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="45749-111">Die Zeitachse des Defender for Endpoint-Geräts bietet eine chronologische Ansicht der Ereignisse und zugehörigen Warnungen, die auf einem Gerät beobachtet werden.</span><span class="sxs-lookup"><span data-stu-id="45749-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="45749-112">Diese Liste der Ereignisse bietet vollständige Sichtbarkeit aller Ereignisse, Dateien und IP-Adressen, die auf dem Gerät beobachtet werden.</span><span class="sxs-lookup"><span data-stu-id="45749-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="45749-113">Die Liste kann manchmal langwierig sein.</span><span class="sxs-lookup"><span data-stu-id="45749-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="45749-114">Gerätezeitachsenereigniskennzeichen helfen Ihnen beim Nachverfolgen von Ereignissen, die miteinander in Zusammenhang stehen könnten.</span><span class="sxs-lookup"><span data-stu-id="45749-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="45749-115">Nachdem Sie eine Gerätezeitachse durchgegangen sind, können Sie die bestimmten Ereignisse, die Sie gekennzeichnet haben, sortieren, filtern und exportieren.</span><span class="sxs-lookup"><span data-stu-id="45749-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="45749-116">Während der Navigation auf der Gerätezeitachse können Sie nach bestimmten Ereignissen suchen und filtern.</span><span class="sxs-lookup"><span data-stu-id="45749-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="45749-117">Sie können Ereigniskennzeichen festlegen, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="45749-117">You can set event flags by:</span></span> 

- <span data-ttu-id="45749-118">Hervorheben der wichtigsten Ereignisse</span><span class="sxs-lookup"><span data-stu-id="45749-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="45749-119">Markieren von Ereignissen, die einen tiefen Eintauchen erfordern</span><span class="sxs-lookup"><span data-stu-id="45749-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="45749-120">Erstellen einer zeitplansreinen Verletzung</span><span class="sxs-lookup"><span data-stu-id="45749-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="45749-121">Kennzeichnen eines Ereignisses</span><span class="sxs-lookup"><span data-stu-id="45749-121">Flag an event</span></span>
1. <span data-ttu-id="45749-122">Suchen des Ereignisses, das Sie kennzeichnen möchten</span><span class="sxs-lookup"><span data-stu-id="45749-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="45749-123">Klicken Sie in der Spalte Flag auf das Kennzeichensymbol.</span><span class="sxs-lookup"><span data-stu-id="45749-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="45749-124">![Abbildung des Gerätezeitachsenflags](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="45749-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="45749-125">Anzeigen gekennzeichneter Ereignisse</span><span class="sxs-lookup"><span data-stu-id="45749-125">View flagged events</span></span>  
1. <span data-ttu-id="45749-126">Aktivieren Sie im Abschnitt **Zeitachsenfilter** **die Option Gekennzeichnete Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="45749-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="45749-127">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="45749-127">Click **Apply**.</span></span> <span data-ttu-id="45749-128">Es werden nur gekennzeichnete Ereignisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45749-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="45749-129">Sie können zusätzliche Filter anwenden, indem Sie auf die Zeitleiste klicken.</span><span class="sxs-lookup"><span data-stu-id="45749-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="45749-130">Dadurch werden nur Ereignisse vor dem gekennzeichneten Ereignis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45749-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="45749-131">![Abbildung des Gerätezeitachsenflags mit Filter nach](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="45749-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
