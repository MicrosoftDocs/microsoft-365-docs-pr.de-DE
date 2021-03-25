---
title: Übersicht über Die Erkennungs- und Reaktionsfunktionen von Endpunkten
ms.reviewer: ''
description: Erfahren Sie mehr über die Funktionen zur Erkennung und Reaktion von Endpunkten in Microsoft Defender ATP
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068480"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="225cd-103">Übersicht über Die Erkennung und Reaktion von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="225cd-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="225cd-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="225cd-104">**Applies to:**</span></span>
- [<span data-ttu-id="225cd-105">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="225cd-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="225cd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="225cd-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="225cd-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="225cd-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="225cd-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="225cd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="225cd-109">Defender for Endpoint-Endpunkterkennungs- und -reaktionsfunktionen bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit und mit Aktionen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="225cd-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="225cd-110">Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="225cd-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="225cd-111">Wenn eine Bedrohung erkannt wird, werden im System Warnungen erstellt, die ein Analytiker untersuchen kann.</span><span class="sxs-lookup"><span data-stu-id="225cd-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="225cd-112">Benachrichtigungen, die auf die gleichen Angriffsmethoden oder den gleichen Angreifer zurückzuführen sind, werden in der Entität _Vorfall_ zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="225cd-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="225cd-113">Das Zusammenfassen von Benachrichtigungen erleichtert es Analytikern, Bedrohungen kollektiv zu untersuchen und darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="225cd-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="225cd-114">Inspiriert von der "Assume Breach"-Einstellung sammelt Defender for Endpoint kontinuierlich Verhaltenstelemetrie im Internet.</span><span class="sxs-lookup"><span data-stu-id="225cd-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="225cd-115">Dazu gehören Prozessinformationen, Netzwerkaktivitäten, tiefe Einblicke in den Kernel- und Speicher-Manager, Benutzeranmeldeaktivitäten, Registrierungs-und Dateisystemänderungen und andere.</span><span class="sxs-lookup"><span data-stu-id="225cd-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="225cd-116">Die Informationen werden sechs Monate gespeichert, sodass ein Analyst zum Anfang eines Angriffs zurückkehren kann.</span><span class="sxs-lookup"><span data-stu-id="225cd-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="225cd-117">Der Analytiker kann dann in unterschiedliche Ansichten wechseln und eine Untersuchung in mehreren Vektoren durchführen.</span><span class="sxs-lookup"><span data-stu-id="225cd-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="225cd-118">Die Antwortfunktionen bieten Ihnen die Möglichkeit, Bedrohungen zeitnah zu beheben, indem Sie auf die betroffenen Entitäten reagieren.</span><span class="sxs-lookup"><span data-stu-id="225cd-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="225cd-119">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="225cd-119">Related topics</span></span>
- [<span data-ttu-id="225cd-120">Dashboard für Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="225cd-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="225cd-121">Warteschlange für Vorfälle</span><span class="sxs-lookup"><span data-stu-id="225cd-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="225cd-122">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="225cd-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="225cd-123">Geräteliste</span><span class="sxs-lookup"><span data-stu-id="225cd-123">Devices list</span></span>](machines-view-overview.md)

