---
title: DeviceAlertEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der DeviceAlertEvents-Tabelle des schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Defender for Endpoint, search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, severity, category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: bb2350fed5fadee359695743989e02a3b3e44fb2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935341"
---
# <a name="devicealertevents"></a><span data-ttu-id="c32c3-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="c32c3-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c32c3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c32c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="c32c3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c32c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="c32c3-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c32c3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c32c3-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c32c3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="c32c3-109">Die `DeviceAlertEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Warnungen im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="c32c3-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="c32c3-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c32c3-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c32c3-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="c32c3-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="c32c3-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c32c3-112">Column name</span></span> | <span data-ttu-id="c32c3-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c32c3-113">Data type</span></span> | <span data-ttu-id="c32c3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c32c3-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="c32c3-115">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-115">string</span></span> | <span data-ttu-id="c32c3-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="c32c3-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="c32c3-117">datetime</span><span class="sxs-lookup"><span data-stu-id="c32c3-117">datetime</span></span> | <span data-ttu-id="c32c3-118">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c32c3-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c32c3-119">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-119">string</span></span> | <span data-ttu-id="c32c3-120">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="c32c3-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c32c3-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c32c3-121">string</span></span> | <span data-ttu-id="c32c3-122">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="c32c3-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="c32c3-123">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-123">string</span></span> | <span data-ttu-id="c32c3-124">Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an</span><span class="sxs-lookup"><span data-stu-id="c32c3-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="c32c3-125">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-125">string</span></span> | <span data-ttu-id="c32c3-126">Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität</span><span class="sxs-lookup"><span data-stu-id="c32c3-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="c32c3-127">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-127">string</span></span> | <span data-ttu-id="c32c3-128">Titel der Warnung</span><span class="sxs-lookup"><span data-stu-id="c32c3-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="c32c3-129">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-129">string</span></span> | <span data-ttu-id="c32c3-130">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c32c3-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="c32c3-131">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-131">string</span></span> | <span data-ttu-id="c32c3-132">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c32c3-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="c32c3-133">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-133">string</span></span> | <span data-ttu-id="c32c3-134">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="c32c3-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="c32c3-135">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-135">string</span></span> | <span data-ttu-id="c32c3-136">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="c32c3-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="c32c3-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c32c3-137">string</span></span> | <span data-ttu-id="c32c3-138">MITRE ATT&CK-Techniken, die der Aktivität zugeordnet sind, die die Warnung ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="c32c3-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="c32c3-139">long</span><span class="sxs-lookup"><span data-stu-id="c32c3-139">long</span></span> | <span data-ttu-id="c32c3-140">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="c32c3-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c32c3-141">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden.</span><span class="sxs-lookup"><span data-stu-id="c32c3-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="c32c3-142">string</span><span class="sxs-lookup"><span data-stu-id="c32c3-142">string</span></span> | <span data-ttu-id="c32c3-143">Tabelle, die die Details des Ereignisses enthält</span><span class="sxs-lookup"><span data-stu-id="c32c3-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c32c3-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c32c3-144">Related topics</span></span>
- [<span data-ttu-id="c32c3-145">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c32c3-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c32c3-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c32c3-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c32c3-147">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c32c3-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
