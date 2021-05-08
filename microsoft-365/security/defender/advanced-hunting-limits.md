---
title: Erweiterte Kontingente und Verwendungsparameter in Microsoft 365 Defender
description: Verstehen verschiedener Kontingente und Verwendungsparameter (Dienstbeschränkungen), die den erweiterten Suchesdienst reaktionsfähig halten
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245600"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="98c87-104">Erweiterte Kontingente und Verwendungsparameter</span><span class="sxs-lookup"><span data-stu-id="98c87-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="98c87-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="98c87-105">**Applies to:**</span></span>
- <span data-ttu-id="98c87-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98c87-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="98c87-107">Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Kontingente und Verwendungsparameter fest (auch als "Dienstbeschränkungen" bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="98c87-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="98c87-108">Diese Kontingente und Parameter gelten separat für Abfragen, die manuell ausgeführt werden, und für Abfragen, die mit benutzerdefinierten [Erkennungsregeln ausgeführt werden.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="98c87-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="98c87-109">Kunden, die regelmäßig mehrere Abfragen ausführen, sollten [](advanced-hunting-best-practices.md) diese Grenzwerte beachten und bewährte Optimierungsmethoden anwenden, um Unterbrechungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="98c87-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="98c87-110">Informationen zu vorhandenen Kontingenten und Verwendungsparametern finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="98c87-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="98c87-111">Kontingent oder Parameter</span><span class="sxs-lookup"><span data-stu-id="98c87-111">Quota or parameter</span></span> | <span data-ttu-id="98c87-112">Size</span><span class="sxs-lookup"><span data-stu-id="98c87-112">Size</span></span> | <span data-ttu-id="98c87-113">Aktualisierungszyklus</span><span class="sxs-lookup"><span data-stu-id="98c87-113">Refresh cycle</span></span> | <span data-ttu-id="98c87-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98c87-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="98c87-115">Datenbereich</span><span class="sxs-lookup"><span data-stu-id="98c87-115">Data range</span></span> | <span data-ttu-id="98c87-116">30 Tage</span><span class="sxs-lookup"><span data-stu-id="98c87-116">30 days</span></span> | <span data-ttu-id="98c87-117">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="98c87-117">Every query</span></span> | <span data-ttu-id="98c87-118">Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen.</span><span class="sxs-lookup"><span data-stu-id="98c87-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="98c87-119">Ergebnissatz</span><span class="sxs-lookup"><span data-stu-id="98c87-119">Result set</span></span> | <span data-ttu-id="98c87-120">10.000 Zeilen</span><span class="sxs-lookup"><span data-stu-id="98c87-120">10,000 rows</span></span> | <span data-ttu-id="98c87-121">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="98c87-121">Every query</span></span> | <span data-ttu-id="98c87-122">Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="98c87-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="98c87-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="98c87-123">Timeout</span></span> | <span data-ttu-id="98c87-124">10 Minuten</span><span class="sxs-lookup"><span data-stu-id="98c87-124">10 minutes</span></span> | <span data-ttu-id="98c87-125">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="98c87-125">Every query</span></span> | <span data-ttu-id="98c87-126">Jede Abfrage kann bis zu 10 Minuten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98c87-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="98c87-127">Wenn er nicht innerhalb von 10 Minuten abgeschlossen ist, zeigt der Dienst einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="98c87-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="98c87-128">CPU-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="98c87-128">CPU resources</span></span> | <span data-ttu-id="98c87-129">Basierend auf der Mandantengröße</span><span class="sxs-lookup"><span data-stu-id="98c87-129">Based on tenant size</span></span> | <span data-ttu-id="98c87-130">Alle 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="98c87-130">Every 15 minutes</span></span> | <span data-ttu-id="98c87-131">Das [Portal zeigt einen Fehler an,](advanced-hunting-errors.md) wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat.</span><span class="sxs-lookup"><span data-stu-id="98c87-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="98c87-132">Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten Zyklus von 15 Minuten 100 % erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="98c87-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="98c87-133">Ein separater Satz von Kontingenten und Parametern gilt für erweiterte Suchabfragen, die über die API ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98c87-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="98c87-134">Informationen zu erweiterten ApIs für die Suche</span><span class="sxs-lookup"><span data-stu-id="98c87-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="98c87-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="98c87-135">Related topics</span></span>

- [<span data-ttu-id="98c87-136">Bewährte Methoden für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="98c87-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="98c87-137">Behandeln von Fehlern bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="98c87-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="98c87-138">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="98c87-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98c87-139">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="98c87-139">Custom detections overview</span></span>](custom-detections-overview.md)