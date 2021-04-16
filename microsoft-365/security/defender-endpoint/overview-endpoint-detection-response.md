---
title: Übersicht über Die Erkennungs- und Reaktionsfunktionen von Endpunkten
ms.reviewer: ''
description: Erfahren Sie mehr über die Funktionen für die Erkennung und Reaktion von Endpunkten in Microsoft Defender for Endpoint
keywords: microsoft defender für Endpunkt, Endpunkterkennung und -reaktion, Reaktion, Erkennung, Cybersicherheit, Schutz
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
ms.openlocfilehash: 138a6afde9e8c601fd41811928580644b85bf2e2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861719"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="228df-104">Übersicht über Die Erkennung und Reaktion von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="228df-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="228df-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="228df-105">**Applies to:**</span></span>
- [<span data-ttu-id="228df-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="228df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="228df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="228df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="228df-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="228df-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="228df-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="228df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="228df-110">Defender for Endpoint-Endpunkterkennungs- und -reaktionsfunktionen bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit und mit Aktionen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="228df-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="228df-111">Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="228df-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="228df-112">Wenn eine Bedrohung erkannt wird, werden im System Warnungen erstellt, die ein Analytiker untersuchen kann.</span><span class="sxs-lookup"><span data-stu-id="228df-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="228df-113">Benachrichtigungen, die auf die gleichen Angriffsmethoden oder den gleichen Angreifer zurückzuführen sind, werden in der Entität _Vorfall_ zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="228df-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="228df-114">Das Zusammenfassen von Benachrichtigungen erleichtert es Analytikern, Bedrohungen kollektiv zu untersuchen und darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="228df-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="228df-115">Inspiriert von der "Assume Breach"-Einstellung sammelt Defender for Endpoint kontinuierlich Verhaltenstelemetrie im Internet.</span><span class="sxs-lookup"><span data-stu-id="228df-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="228df-116">Dazu gehören Prozessinformationen, Netzwerkaktivitäten, tiefe Einblicke in den Kernel- und Speicher-Manager, Benutzeranmeldeaktivitäten, Registrierungs-und Dateisystemänderungen und andere.</span><span class="sxs-lookup"><span data-stu-id="228df-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="228df-117">Die Informationen werden sechs Monate gespeichert, sodass ein Analyst zum Anfang eines Angriffs zurückkehren kann.</span><span class="sxs-lookup"><span data-stu-id="228df-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="228df-118">Der Analytiker kann dann in unterschiedliche Ansichten wechseln und eine Untersuchung in mehreren Vektoren durchführen.</span><span class="sxs-lookup"><span data-stu-id="228df-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="228df-119">Die Antwortfunktionen bieten Ihnen die Möglichkeit, Bedrohungen zeitnah zu beheben, indem Sie auf die betroffenen Entitäten reagieren.</span><span class="sxs-lookup"><span data-stu-id="228df-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="228df-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="228df-120">Related topics</span></span>
- [<span data-ttu-id="228df-121">Dashboard für Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="228df-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="228df-122">Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="228df-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="228df-123">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="228df-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="228df-124">Geräteliste</span><span class="sxs-lookup"><span data-stu-id="228df-124">Devices list</span></span>](machines-view-overview.md)

