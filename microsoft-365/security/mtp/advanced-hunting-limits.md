---
title: Erweiterte Jagd Kontingente und Nutzungsparameter in Microsoft 365 Defender
description: Grundlegendes zu verschiedenen Kontingenten und Nutzungsparametern (Service Limits), mit denen der erweiterte Jagd Dienst reaktionsfähig bleibt
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, CPU-Grenze, Abfrage Grenzwert, Ressourcen, maximale Ergebnisse, Kontingent, Parameter, Zuweisung
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847368"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="27688-104">Erweiterte Jagd Kontingente und Nutzungsparameter</span><span class="sxs-lookup"><span data-stu-id="27688-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27688-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="27688-105">**Applies to:**</span></span>
- <span data-ttu-id="27688-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27688-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="27688-107">Um den Dienst leistungsfähig und reaktionsfähig zu halten, setzt Advanced Hunting verschiedene Kontingente und Nutzungsparameter (auch bekannt als "Service Limits").</span><span class="sxs-lookup"><span data-stu-id="27688-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="27688-108">Diese Kontingente und Parameter gelten für Abfragen, die manuell und durch [benutzerdefinierte Erkennungsregeln](custom-detection-rules.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27688-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="27688-109">Kunden, die regelmäßig mehrere Abfragen ausführen, sollten den Verbrauch nachverfolgen und [bewährte Methoden zur Optimierung anwenden](advanced-hunting-best-practices.md) , um Störungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="27688-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="27688-110">Lesen Sie die folgende Tabelle, um die vorhandenen Kontingente und Nutzungsparameter zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="27688-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="27688-111">Quota oder Parameter</span><span class="sxs-lookup"><span data-stu-id="27688-111">Quota or parameter</span></span> | <span data-ttu-id="27688-112">Größe</span><span class="sxs-lookup"><span data-stu-id="27688-112">Size</span></span> | <span data-ttu-id="27688-113">Aktualisierungszyklus</span><span class="sxs-lookup"><span data-stu-id="27688-113">Refresh cycle</span></span> | <span data-ttu-id="27688-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27688-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="27688-115">Datenbereich</span><span class="sxs-lookup"><span data-stu-id="27688-115">Data range</span></span> | <span data-ttu-id="27688-116">30 Tage</span><span class="sxs-lookup"><span data-stu-id="27688-116">30 days</span></span> | <span data-ttu-id="27688-117">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="27688-117">Every query</span></span> | <span data-ttu-id="27688-118">Jede Abfrage kann Daten von bis zu den letzten 30 Tagen nachschlagen.</span><span class="sxs-lookup"><span data-stu-id="27688-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="27688-119">Ergebnismenge</span><span class="sxs-lookup"><span data-stu-id="27688-119">Result set</span></span> | <span data-ttu-id="27688-120">10.000 Zeilen</span><span class="sxs-lookup"><span data-stu-id="27688-120">10,000 rows</span></span> | <span data-ttu-id="27688-121">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="27688-121">Every query</span></span> | <span data-ttu-id="27688-122">Jede Abfrage kann bis zu 10.000 Datensätze zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="27688-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="27688-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="27688-123">Timeout</span></span> | <span data-ttu-id="27688-124">10 Minuten</span><span class="sxs-lookup"><span data-stu-id="27688-124">10 minutes</span></span> | <span data-ttu-id="27688-125">Jede Abfrage</span><span class="sxs-lookup"><span data-stu-id="27688-125">Every query</span></span> | <span data-ttu-id="27688-126">Jede Abfrage kann bis zu 10 Minuten lang ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27688-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="27688-127">Wenn der Dienst nicht innerhalb von 10 Minuten abgeschlossen ist, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27688-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="27688-128">CPU-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="27688-128">CPU resources</span></span> | <span data-ttu-id="27688-129">Basierend auf der Mandanten Größe</span><span class="sxs-lookup"><span data-stu-id="27688-129">Based on tenant size</span></span> | <span data-ttu-id="27688-130">-Auf die Stunde und dann alle 15 Minuten</span><span class="sxs-lookup"><span data-stu-id="27688-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="27688-131">-Täglich um 12 Uhr</span><span class="sxs-lookup"><span data-stu-id="27688-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="27688-132">Der Dienst erzwingt das tägliche und das 15-minütige Kontingent separat.</span><span class="sxs-lookup"><span data-stu-id="27688-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="27688-133">Für jedes Kontingent wird bei jeder Ausführung einer Abfrage ein [Fehler angezeigt](advanced-hunting-errors.md) , und der Mandant hat mehr als 10% der zugeordneten Ressourcen verbraucht.</span><span class="sxs-lookup"><span data-stu-id="27688-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="27688-134">Abfragen werden blockiert, wenn der Mandant 100% bis nach dem nächsten täglichen oder 15-minütigen Zyklus erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="27688-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="27688-135">Eine separate Gruppe von Kontingenten und Parametern gilt für erweiterte Jagd Abfragen, die über die API ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27688-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="27688-136">Lesen Sie mehr über erweiterte Jagd-APIs</span><span class="sxs-lookup"><span data-stu-id="27688-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="27688-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="27688-137">Related topics</span></span>

- [<span data-ttu-id="27688-138">Bewährte Methoden für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="27688-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="27688-139">Behandeln von erweiterten Jagd Fehlern</span><span class="sxs-lookup"><span data-stu-id="27688-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="27688-140">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="27688-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="27688-141">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="27688-141">Custom detections overview</span></span>](custom-detections-overview.md)