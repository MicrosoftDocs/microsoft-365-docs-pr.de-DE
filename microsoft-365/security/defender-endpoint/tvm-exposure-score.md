---
title: Belichtungsergebnis in Bedrohungs- und Sicherheitsrisikomanagement
description: Die Bedrohungs- und Sicherheitsrisikomanagement Belichtungsergebnis spiegelt wider, wie anfällig Ihre Organisation für Cybersicherheitsbedrohungen ist.
keywords: Exposure Score, Microsoft Defender for Endpoint Exposure Score, Microsoft Defender for Endpoint tvm exposure score, organization exposure score, tvm organization exposure score, Bedrohungs- und Sicherheitsrisikomanagement, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcea240fe1dc0ce97a2800391320b04c39c84336
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934105"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="6eaa8-104">Belichtungsergebnis – Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="6eaa8-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6eaa8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6eaa8-105">**Applies to:**</span></span>

- [<span data-ttu-id="6eaa8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6eaa8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6eaa8-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="6eaa8-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6eaa8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6eaa8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6eaa8-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6eaa8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6eaa8-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="6eaa8-111">Ihr Belichtungsergebnis wird im [Threat and Sicherheitsrisikomanagement Dashboard](tvm-dashboard-insights.md) des Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="6eaa8-112">Es spiegelt wider, wie anfällig Ihre Organisation für Cybersicherheitsbedrohungen ist.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="6eaa8-113">Niedrige Belichtungszahl bedeutet, dass Ihre Geräte weniger anfällig für die Nutzung sind.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="6eaa8-114">Schnelles Verständnis und Identifizieren von hochrangigen Informationen zum Sicherheitsstatus in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="6eaa8-115">Erkennen und reagieren Sie auf Bereiche, die eine Untersuchung oder Aktion erfordern, um den aktuellen Status zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="6eaa8-116">Kommunizieren Sie mit Kollegen und der Verwaltung über die Auswirkungen von Sicherheitsbemühungen.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="6eaa8-117">Mit der Karte erhalten Sie eine hohe Ansicht des Belichtungsergebnistrends im Laufe der Zeit.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="6eaa8-118">Alle Spitzen im Diagramm geben Ihnen einen visuellen Hinweis auf eine hohe Bedrohung durch Cybersicherheit, die Sie weiter untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Belichtungsergebniskarte](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="6eaa8-120">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="6eaa8-120">How it works</span></span>

<span data-ttu-id="6eaa8-121">Die Belichtungsnote ist in die folgenden Ebenen aufgeschlüsselt:</span><span class="sxs-lookup"><span data-stu-id="6eaa8-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="6eaa8-122">0–29: Niedrige Belichtungszahl</span><span class="sxs-lookup"><span data-stu-id="6eaa8-122">0–29: low exposure score</span></span>
- <span data-ttu-id="6eaa8-123">30–69: mittlere Belichtungszahl</span><span class="sxs-lookup"><span data-stu-id="6eaa8-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="6eaa8-124">70–100: Hohe Belichtungszahl</span><span class="sxs-lookup"><span data-stu-id="6eaa8-124">70–100: high exposure score</span></span>

<span data-ttu-id="6eaa8-125">Sie können die Probleme basierend auf [](tvm-security-recommendation.md) priorisierten Sicherheitsempfehlungen beheben, um die Belichtungszahl zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="6eaa8-126">Jede Software hat Schwächen, die in Empfehlungen umgewandelt und basierend auf dem Risiko für die Organisation priorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="6eaa8-127">Verringern Der Bedrohungs- und Sicherheitsrisikorisiko</span><span class="sxs-lookup"><span data-stu-id="6eaa8-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="6eaa8-128">Verringern Sie Ihre Bedrohungs- und Sicherheitsrisikorisiken, indem Sie [Sicherheitsempfehlungen enfeinen.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="6eaa8-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="6eaa8-129">Machen Sie die größten Auswirkungen auf Ihre Belichtungsergebnis, indem Sie die wichtigsten Sicherheitsempfehlungen, die im Bedrohungs- und Sicherheitsrisikomanagement angezeigt [werden können, beh nnen.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="6eaa8-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6eaa8-130">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6eaa8-130">Related topics</span></span>

- [<span data-ttu-id="6eaa8-131">Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="6eaa8-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6eaa8-132">Microsoft-Sicherheitsbewertung für Geräte</span><span class="sxs-lookup"><span data-stu-id="6eaa8-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="6eaa8-133">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="6eaa8-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="6eaa8-134">Ablauf der Veranstaltung</span><span class="sxs-lookup"><span data-stu-id="6eaa8-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
