---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft 365 Defender
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
ms.openlocfilehash: fe2b9f1b52fa2c8d9031bb58597992f3dda91520
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843912"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="be1b1-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="be1b1-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be1b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="be1b1-105">**Applies to:**</span></span>
- <span data-ttu-id="be1b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be1b1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="be1b1-107">Mit benutzerdefinierten Erkennungen können Sie proaktiv auf verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="be1b1-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="be1b1-108">Dies wird durch anpassbare Erkennungsregeln ermöglicht, die automatisch Warnungen und Reaktions Aktionen auslösen.</span><span class="sxs-lookup"><span data-stu-id="be1b1-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="be1b1-109">Benutzerdefinierte Erkennungen arbeiten mit [Advanced Hunting](advanced-hunting-overview.md), die eine leistungsstarke, flexible Abfragesprache bietet, die eine umfassende Reihe von Ereignis-und Systeminformationen aus Ihrem Netzwerk abdeckt.</span><span class="sxs-lookup"><span data-stu-id="be1b1-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="be1b1-110">Sie können festlegen, dass Sie in regelmäßigen Intervallen ausgeführt werden, indem Sie Warnungen generieren und Reaktions Aktionen ausführen, wenn Übereinstimmungen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="be1b1-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="be1b1-111">Benutzerdefinierte Erkennungen stellen Folgendes bereit:</span><span class="sxs-lookup"><span data-stu-id="be1b1-111">Custom detections provide:</span></span>
- <span data-ttu-id="be1b1-112">Warnungen für regelbasierte Erkennungen, die aus erweiterten Jagd Abfragen erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="be1b1-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="be1b1-113">Automatische Antwort Aktionen</span><span class="sxs-lookup"><span data-stu-id="be1b1-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="be1b1-114">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="be1b1-114">Related topic</span></span>
- [<span data-ttu-id="be1b1-115">Erstellen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="be1b1-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="be1b1-116">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="be1b1-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
