---
title: Erweiterte Grenzwerte für die Suche in Microsoft Defender ATP
description: Verstehen verschiedener Dienstbeschränkungen, die den erweiterten Suchesdienst reaktionsfähig halten
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067944"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="ee20f-104">Erweiterte Grenzwerte für den Suchesdienst</span><span class="sxs-lookup"><span data-stu-id="ee20f-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee20f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ee20f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee20f-106">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ee20f-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ee20f-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ee20f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ee20f-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ee20f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="ee20f-109">Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Grenzwerte für Abfragen fest, die manuell und nach [benutzerdefinierten Erkennungsregeln ausgeführt werden.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="ee20f-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="ee20f-110">Informationen zu diesen Grenzwerten finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ee20f-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="ee20f-111">Grenze</span><span class="sxs-lookup"><span data-stu-id="ee20f-111">Limit</span></span> | <span data-ttu-id="ee20f-112">Size</span><span class="sxs-lookup"><span data-stu-id="ee20f-112">Size</span></span> | <span data-ttu-id="ee20f-113">Aktualisierungszyklus</span><span class="sxs-lookup"><span data-stu-id="ee20f-113">Refresh cycle</span></span> | <span data-ttu-id="ee20f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee20f-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="ee20f-115">Datenbereich</span><span class="sxs-lookup"><span data-stu-id="ee20f-115">Data range</span></span> | <span data-ttu-id="ee20f-116">30 Tage</span><span class="sxs-lookup"><span data-stu-id="ee20f-116">30 days</span></span> | <span data-ttu-id="ee20f-117">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="ee20f-117">Every query</span></span> | <span data-ttu-id="ee20f-118">Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen.</span><span class="sxs-lookup"><span data-stu-id="ee20f-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="ee20f-119">Ergebnissatz</span><span class="sxs-lookup"><span data-stu-id="ee20f-119">Result set</span></span> | <span data-ttu-id="ee20f-120">10.000 Zeilen</span><span class="sxs-lookup"><span data-stu-id="ee20f-120">10,000 rows</span></span> | <span data-ttu-id="ee20f-121">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="ee20f-121">Every query</span></span> | <span data-ttu-id="ee20f-122">Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ee20f-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="ee20f-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="ee20f-123">Timeout</span></span> | <span data-ttu-id="ee20f-124">10 Minuten</span><span class="sxs-lookup"><span data-stu-id="ee20f-124">10 minutes</span></span> | <span data-ttu-id="ee20f-125">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="ee20f-125">Every query</span></span> | <span data-ttu-id="ee20f-126">Jede Abfrage kann bis zu 10 Minuten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ee20f-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="ee20f-127">Wenn er nicht innerhalb von 10 Minuten abgeschlossen ist, zeigt der Dienst einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="ee20f-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="ee20f-128">CPU-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ee20f-128">CPU resources</span></span> | <span data-ttu-id="ee20f-129">Basierend auf der Mandantengröße</span><span class="sxs-lookup"><span data-stu-id="ee20f-129">Based on tenant size</span></span> | <span data-ttu-id="ee20f-130">- Zur Stunde und dann alle 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="ee20f-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="ee20f-131">- Täglich um 12:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="ee20f-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="ee20f-132">Der Dienst erzwingt den täglichen und den 15-Minuten-Grenzwert separat.</span><span class="sxs-lookup"><span data-stu-id="ee20f-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="ee20f-133">Für jeden Grenzwert zeigt das [Portal](advanced-hunting-errors.md) einen Fehler an, wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat.</span><span class="sxs-lookup"><span data-stu-id="ee20f-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="ee20f-134">Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten täglichen oder 15-minütigen Zyklus 100 % erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="ee20f-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="ee20f-135">Ein separater Satz von Grenzwerten gilt für erweiterte Suchabfragen, die über die API ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ee20f-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="ee20f-136">Informationen zu erweiterten ApIs für die Suche</span><span class="sxs-lookup"><span data-stu-id="ee20f-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="ee20f-137">Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und bewährte Methoden zur Optimierung anwenden, um Unterbrechungen zu minimieren, die sich aus der Überschreitung dieser Grenzwerte ergeben. [](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="ee20f-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee20f-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ee20f-138">Related topics</span></span>

- [<span data-ttu-id="ee20f-139">Bewährte Methoden für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ee20f-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ee20f-140">Behandeln von Fehlern bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="ee20f-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="ee20f-141">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ee20f-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ee20f-142">Regeln für benutzerdefinierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="ee20f-142">Custom detections rules</span></span>](custom-detection-rules.md)
