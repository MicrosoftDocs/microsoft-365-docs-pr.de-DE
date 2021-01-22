---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft 365 Defender
description: Verstehen, wie Sie die erweiterte Suche verwenden können, um benutzerdefinierte Erkennungen zu erstellen und Warnungen zu generieren
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928808"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="2e614-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="2e614-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2e614-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2e614-105">**Applies to:**</span></span>
- <span data-ttu-id="2e614-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e614-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2e614-107">Mit benutzerdefinierten Erkennungen können Sie proaktiv verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="2e614-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="2e614-108">Dies wird durch anpassbare Erkennungsregeln ermöglicht, die automatisch Warnungen sowie Reaktionsaktionen auslösen.</span><span class="sxs-lookup"><span data-stu-id="2e614-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="2e614-109">Benutzerdefinierte Erkennungen funktionieren [bei](advanced-hunting-overview.md)der erweiterten Suche, die eine leistungsstarke, flexible Abfragesprache bietet, die eine breite Palette von Ereignis- und Systeminformationen aus Ihrem Netzwerk umfasst.</span><span class="sxs-lookup"><span data-stu-id="2e614-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="2e614-110">Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und bei Übereinstimmungen Reaktionsaktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="2e614-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="2e614-111">Benutzerdefinierte Erkennungen bieten:</span><span class="sxs-lookup"><span data-stu-id="2e614-111">Custom detections provide:</span></span>
- <span data-ttu-id="2e614-112">Warnungen für regelbasierte Erkennungen, die aus abfragen der erweiterten Suche erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="2e614-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="2e614-113">Automatische Antwortaktionen</span><span class="sxs-lookup"><span data-stu-id="2e614-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="2e614-114">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="2e614-114">Related topic</span></span>
- [<span data-ttu-id="2e614-115">Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="2e614-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="2e614-116">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="2e614-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
