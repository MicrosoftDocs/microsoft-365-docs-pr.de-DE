---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie die erweiterte Suche verwenden können, um benutzerdefinierte Erkennungen zu erstellen und Warnungen zu generieren.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bf635ed03cb0d99d54fc94b622bf244447b32a80
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935701"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="3277e-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="3277e-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3277e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3277e-105">**Applies to:**</span></span>
- <span data-ttu-id="3277e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3277e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3277e-107">Mit benutzerdefinierten Erkennungen können Sie proaktiv verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="3277e-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="3277e-108">Dies wird durch anpassbare Erkennungsregeln ermöglicht, die automatisch Warnungen auslösen, sowie Reaktionsaktionen.</span><span class="sxs-lookup"><span data-stu-id="3277e-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="3277e-109">Benutzerdefinierte Erkennungen funktionieren [mit](advanced-hunting-overview.md)der erweiterten Suche, die eine leistungsstarke, flexible Abfragesprache bietet, die eine breite Palette von Ereignis- und Systeminformationen aus Ihrem Netzwerk deckt.</span><span class="sxs-lookup"><span data-stu-id="3277e-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="3277e-110">Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3277e-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="3277e-111">Benutzerdefinierte Erkennungen bieten:</span><span class="sxs-lookup"><span data-stu-id="3277e-111">Custom detections provide:</span></span>
- <span data-ttu-id="3277e-112">Warnungen für regelbasierte Erkennungen, die aus erweiterten Suchabfragen erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="3277e-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="3277e-113">Automatische Reaktionsaktionen</span><span class="sxs-lookup"><span data-stu-id="3277e-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="3277e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3277e-114">See also</span></span>
- [<span data-ttu-id="3277e-115">Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="3277e-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="3277e-116">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3277e-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3277e-117">Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3277e-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
