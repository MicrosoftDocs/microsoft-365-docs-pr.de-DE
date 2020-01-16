---
title: Tabelle "AlertEvents" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die Warnungserstellungsereignisse in der Tabelle "AlertEvents" des Schema "Erweiterte Suche".
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, alertevents, Warnung, Schweregrad, Kategorie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2d8c484f11e1384e1b98f05b907b043c33231f3f
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210080"
---
# <a name="alertevents"></a><span data-ttu-id="020e3-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="020e3-104">AlertEvents</span></span>

<span data-ttu-id="020e3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="020e3-105">**Applies to:**</span></span>
- <span data-ttu-id="020e3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="020e3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="020e3-107">Die Tabelle `AlertEvents` im Schema [Erweiterte Suche](advanced-hunting-overview.md) enthält Informationen zu Microsoft Defender ATP-Warnungen.</span><span class="sxs-lookup"><span data-stu-id="020e3-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="020e3-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="020e3-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="020e3-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="020e3-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="020e3-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="020e3-110">Column name</span></span> | <span data-ttu-id="020e3-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="020e3-111">Data type</span></span> | <span data-ttu-id="020e3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="020e3-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="020e3-113">string</span><span class="sxs-lookup"><span data-stu-id="020e3-113">string</span></span> | <span data-ttu-id="020e3-114">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="020e3-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="020e3-115">datetime</span><span class="sxs-lookup"><span data-stu-id="020e3-115">datetime</span></span> | <span data-ttu-id="020e3-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="020e3-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="020e3-117">string</span><span class="sxs-lookup"><span data-stu-id="020e3-117">string</span></span> | <span data-ttu-id="020e3-118">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="020e3-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="020e3-119">string</span><span class="sxs-lookup"><span data-stu-id="020e3-119">string</span></span> | <span data-ttu-id="020e3-120">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="020e3-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="020e3-121">string</span><span class="sxs-lookup"><span data-stu-id="020e3-121">string</span></span> | <span data-ttu-id="020e3-122">Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an</span><span class="sxs-lookup"><span data-stu-id="020e3-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="020e3-123">string</span><span class="sxs-lookup"><span data-stu-id="020e3-123">string</span></span> | <span data-ttu-id="020e3-124">Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität</span><span class="sxs-lookup"><span data-stu-id="020e3-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="020e3-125">string</span><span class="sxs-lookup"><span data-stu-id="020e3-125">string</span></span> | <span data-ttu-id="020e3-126">Titel der Warnung</span><span class="sxs-lookup"><span data-stu-id="020e3-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="020e3-127">string</span><span class="sxs-lookup"><span data-stu-id="020e3-127">string</span></span> | <span data-ttu-id="020e3-128">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="020e3-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="020e3-129">string</span><span class="sxs-lookup"><span data-stu-id="020e3-129">string</span></span> | <span data-ttu-id="020e3-130">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="020e3-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="020e3-131">string</span><span class="sxs-lookup"><span data-stu-id="020e3-131">string</span></span> | <span data-ttu-id="020e3-132">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="020e3-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="020e3-133">string</span><span class="sxs-lookup"><span data-stu-id="020e3-133">string</span></span> | <span data-ttu-id="020e3-134">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="020e3-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="020e3-135">long</span><span class="sxs-lookup"><span data-stu-id="020e3-135">long</span></span> | <span data-ttu-id="020e3-136">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="020e3-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="020e3-137">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte zusammen mit den Gerätename-und timestamp-Spalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="020e3-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="020e3-138">string</span><span class="sxs-lookup"><span data-stu-id="020e3-138">string</span></span> | <span data-ttu-id="020e3-139">Tabelle, die die Details des Ereignisses enthält</span><span class="sxs-lookup"><span data-stu-id="020e3-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="020e3-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="020e3-140">Related topics</span></span>
- [<span data-ttu-id="020e3-141">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="020e3-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="020e3-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="020e3-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="020e3-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="020e3-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="020e3-144">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="020e3-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="020e3-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="020e3-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="020e3-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="020e3-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
