---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft Threat Protection
description: Grundlegendes zum Erstellen von benutzerdefinierten Erkennungen und Generieren von Benachrichtigungen mithilfe der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498351"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="5a773-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="5a773-104">Custom detections overview</span></span>

<span data-ttu-id="5a773-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5a773-105">**Applies to:**</span></span>
- <span data-ttu-id="5a773-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5a773-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5a773-107">Mit benutzerdefinierten Erkennungen können Sie proaktiv auf verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="5a773-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="5a773-108">Dies wird durch anpassbare Erkennungsregeln ermöglicht, die automatisch Warnungen und Reaktions Aktionen auslösen.</span><span class="sxs-lookup"><span data-stu-id="5a773-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="5a773-109">Benutzerdefinierte Erkennungen arbeiten mit [Advanced Hunting](advanced-hunting-overview.md), die eine leistungsstarke, flexible Abfragesprache bietet, die eine umfassende Reihe von Ereignis-und Systeminformationen aus Ihrem Netzwerk abdeckt.</span><span class="sxs-lookup"><span data-stu-id="5a773-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="5a773-110">Sie können festlegen, dass Sie in regelmäßigen Intervallen ausgeführt werden, indem Sie Warnungen generieren und Reaktions Aktionen ausführen, wenn Übereinstimmungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="5a773-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="5a773-111">Benutzerdefinierte Erkennungen stellen Folgendes bereit:</span><span class="sxs-lookup"><span data-stu-id="5a773-111">Custom detections provide:</span></span>
- <span data-ttu-id="5a773-112">Warnungen für regelbasierte Erkennungen, die aus erweiterten Jagd Abfragen erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="5a773-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="5a773-113">Automatische Antwort Aktionen</span><span class="sxs-lookup"><span data-stu-id="5a773-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="5a773-114">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="5a773-114">Related topic</span></span>
- [<span data-ttu-id="5a773-115">Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="5a773-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="5a773-116">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="5a773-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)