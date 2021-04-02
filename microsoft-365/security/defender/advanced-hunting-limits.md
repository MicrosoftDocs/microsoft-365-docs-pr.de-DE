---
title: Erweiterte Kontingente und Verwendungsparameter in Microsoft 365 Defender
description: Verstehen verschiedener Kontingente und Verwendungsparameter (Dienstbeschränkungen), die den erweiterten Suchesdienst reaktionsfähig halten
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, CPU-Grenzwert, Abfragebeschränkung, Ressourcen, maximale Ergebnisse, Kontingent, Parameter, Zuordnung
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
ms.openlocfilehash: ca79abfa95feb65f98ec32ae8dbc0093e34d58e6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498431"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="3849e-104">Erweiterte Kontingente und Verwendungsparameter</span><span class="sxs-lookup"><span data-stu-id="3849e-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3849e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3849e-105">**Applies to:**</span></span>
- <span data-ttu-id="3849e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3849e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3849e-107">Um die Leistungsfähigkeit und Reaktionsfähigkeit des Diensts zu halten, legt die erweiterte Suche verschiedene Kontingente und Verwendungsparameter fest (auch als "Dienstbeschränkungen" bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="3849e-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="3849e-108">Diese Kontingente und Parameter gelten für Abfragen, die manuell und mit benutzerdefinierten [Erkennungsregeln ausgeführt werden.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="3849e-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="3849e-109">Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und bewährte Methoden zur Optimierung [anwenden,](advanced-hunting-best-practices.md) um Unterbrechungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="3849e-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="3849e-110">Informationen zu vorhandenen Kontingenten und Verwendungsparametern finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3849e-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="3849e-111">Kontingent oder Parameter</span><span class="sxs-lookup"><span data-stu-id="3849e-111">Quota or parameter</span></span> | <span data-ttu-id="3849e-112">Size</span><span class="sxs-lookup"><span data-stu-id="3849e-112">Size</span></span> | <span data-ttu-id="3849e-113">Aktualisierungszyklus</span><span class="sxs-lookup"><span data-stu-id="3849e-113">Refresh cycle</span></span> | <span data-ttu-id="3849e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3849e-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="3849e-115">Datenbereich</span><span class="sxs-lookup"><span data-stu-id="3849e-115">Data range</span></span> | <span data-ttu-id="3849e-116">30 Tage</span><span class="sxs-lookup"><span data-stu-id="3849e-116">30 days</span></span> | <span data-ttu-id="3849e-117">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="3849e-117">Every query</span></span> | <span data-ttu-id="3849e-118">Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschauen.</span><span class="sxs-lookup"><span data-stu-id="3849e-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="3849e-119">Ergebnissatz</span><span class="sxs-lookup"><span data-stu-id="3849e-119">Result set</span></span> | <span data-ttu-id="3849e-120">10.000 Zeilen</span><span class="sxs-lookup"><span data-stu-id="3849e-120">10,000 rows</span></span> | <span data-ttu-id="3849e-121">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="3849e-121">Every query</span></span> | <span data-ttu-id="3849e-122">Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3849e-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="3849e-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="3849e-123">Timeout</span></span> | <span data-ttu-id="3849e-124">10 Minuten</span><span class="sxs-lookup"><span data-stu-id="3849e-124">10 minutes</span></span> | <span data-ttu-id="3849e-125">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="3849e-125">Every query</span></span> | <span data-ttu-id="3849e-126">Jede Abfrage kann bis zu 10 Minuten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3849e-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="3849e-127">Wenn er nicht innerhalb von 10 Minuten abgeschlossen ist, zeigt der Dienst einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="3849e-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="3849e-128">CPU-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="3849e-128">CPU resources</span></span> | <span data-ttu-id="3849e-129">Basierend auf der Mandantengröße</span><span class="sxs-lookup"><span data-stu-id="3849e-129">Based on tenant size</span></span> | <span data-ttu-id="3849e-130">- Zur Stunde und dann alle 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="3849e-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="3849e-131">- Täglich um 12:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="3849e-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="3849e-132">Der Dienst erzwingt das tägliche und das 15-Minuten-Kontingent separat.</span><span class="sxs-lookup"><span data-stu-id="3849e-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="3849e-133">Für jedes Kontingent zeigt das [Portal](advanced-hunting-errors.md) einen Fehler an, wenn eine Abfrage ausgeführt wird und der Mandant mehr als 10 % der zugewiesenen Ressourcen verbraucht hat.</span><span class="sxs-lookup"><span data-stu-id="3849e-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="3849e-134">Abfragen werden blockiert, wenn der Mandant bis nach dem nächsten täglichen oder 15-minütigen Zyklus 100 % erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="3849e-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="3849e-135">Ein separater Satz von Kontingenten und Parametern gilt für erweiterte Suchabfragen, die über die API ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3849e-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="3849e-136">Informationen zu erweiterten ApIs für die Suche</span><span class="sxs-lookup"><span data-stu-id="3849e-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="3849e-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3849e-137">Related topics</span></span>

- [<span data-ttu-id="3849e-138">Bewährte Methoden für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3849e-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3849e-139">Behandeln von Fehlern bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="3849e-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="3849e-140">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="3849e-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3849e-141">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="3849e-141">Custom detections overview</span></span>](custom-detections-overview.md)