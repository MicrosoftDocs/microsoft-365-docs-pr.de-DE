---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie die erweiterte Suche verwenden können, um benutzerdefinierte Erkennungen zu erstellen und Warnungen zu generieren.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft 365 Defender, microsoft 365, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto
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
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952536"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="9b563-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="9b563-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b563-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9b563-105">**Applies to:**</span></span>
- <span data-ttu-id="9b563-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b563-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="9b563-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9b563-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9b563-108">Mit benutzerdefinierten Erkennungen können Sie proaktiv verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="9b563-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="9b563-109">Dies wird durch anpassbare Erkennungsregeln ermöglicht, die automatisch Warnungen auslösen, sowie Reaktionsaktionen.</span><span class="sxs-lookup"><span data-stu-id="9b563-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="9b563-110">Benutzerdefinierte Erkennungen funktionieren [mit](advanced-hunting-overview.md)der erweiterten Suche, die eine leistungsstarke, flexible Abfragesprache bietet, die eine breite Palette von Ereignis- und Systeminformationen aus Ihrem Netzwerk deckt.</span><span class="sxs-lookup"><span data-stu-id="9b563-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="9b563-111">Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9b563-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="9b563-112">Benutzerdefinierte Erkennungen bieten:</span><span class="sxs-lookup"><span data-stu-id="9b563-112">Custom detections provide:</span></span>
- <span data-ttu-id="9b563-113">Warnungen für regelbasierte Erkennungen, die aus erweiterten Suchabfragen erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="9b563-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="9b563-114">Automatische Reaktionsaktionen</span><span class="sxs-lookup"><span data-stu-id="9b563-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="9b563-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b563-115">See also</span></span>
- [<span data-ttu-id="9b563-116">Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="9b563-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="9b563-117">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9b563-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9b563-118">Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b563-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
