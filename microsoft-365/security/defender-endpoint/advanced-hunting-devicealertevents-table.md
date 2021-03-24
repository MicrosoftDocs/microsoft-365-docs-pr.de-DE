---
title: DeviceAlertEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Benachrichtigungsgenerierungsereignissen in der DeviceAlertEvents-Tabelle des schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, DeviceAlertEvents, Warnung, Schweregrad, Kategorie
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
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: c22e4b754f9d28156c3d26c567581572e59d718d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064391"
---
# <a name="devicealertevents"></a><span data-ttu-id="9afae-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="9afae-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9afae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9afae-105">**Applies to:**</span></span>
- [<span data-ttu-id="9afae-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9afae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="9afae-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9afae-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9afae-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9afae-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="9afae-109">Die `DeviceAlertEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Warnungen im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="9afae-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="9afae-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9afae-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9afae-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="9afae-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="9afae-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="9afae-112">Column name</span></span> | <span data-ttu-id="9afae-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9afae-113">Data type</span></span> | <span data-ttu-id="9afae-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9afae-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="9afae-115">string</span><span class="sxs-lookup"><span data-stu-id="9afae-115">string</span></span> | <span data-ttu-id="9afae-116">Eindeutiger Bezeichner der Warnung</span><span class="sxs-lookup"><span data-stu-id="9afae-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="9afae-117">datetime</span><span class="sxs-lookup"><span data-stu-id="9afae-117">datetime</span></span> | <span data-ttu-id="9afae-118">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9afae-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9afae-119">string</span><span class="sxs-lookup"><span data-stu-id="9afae-119">string</span></span> | <span data-ttu-id="9afae-120">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="9afae-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9afae-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9afae-121">string</span></span> | <span data-ttu-id="9afae-122">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="9afae-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="9afae-123">string</span><span class="sxs-lookup"><span data-stu-id="9afae-123">string</span></span> | <span data-ttu-id="9afae-124">Zeigt die potenziellen Auswirkungen (hoch, mittel oder gering) des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität an</span><span class="sxs-lookup"><span data-stu-id="9afae-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="9afae-125">string</span><span class="sxs-lookup"><span data-stu-id="9afae-125">string</span></span> | <span data-ttu-id="9afae-126">Typ des in der Warnung angegebenen Bedrohungsindikators bzw. der in der Warnung angegebenen Sicherheitsverletzungsaktivität</span><span class="sxs-lookup"><span data-stu-id="9afae-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="9afae-127">string</span><span class="sxs-lookup"><span data-stu-id="9afae-127">string</span></span> | <span data-ttu-id="9afae-128">Titel der Warnung</span><span class="sxs-lookup"><span data-stu-id="9afae-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="9afae-129">string</span><span class="sxs-lookup"><span data-stu-id="9afae-129">string</span></span> | <span data-ttu-id="9afae-130">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9afae-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9afae-131">string</span><span class="sxs-lookup"><span data-stu-id="9afae-131">string</span></span> | <span data-ttu-id="9afae-132">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9afae-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="9afae-133">string</span><span class="sxs-lookup"><span data-stu-id="9afae-133">string</span></span> | <span data-ttu-id="9afae-134">URL oder vollqualifizierter Domänenname (FQDN), mit der bzw. dem eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="9afae-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="9afae-135">string</span><span class="sxs-lookup"><span data-stu-id="9afae-135">string</span></span> | <span data-ttu-id="9afae-136">IP-Adresse, mit der eine Verbindung hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="9afae-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="9afae-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9afae-137">string</span></span> | <span data-ttu-id="9afae-138">MITRE ATT&CK-Techniken, die der Aktivität zugeordnet sind, die die Warnung ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="9afae-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="9afae-139">long</span><span class="sxs-lookup"><span data-stu-id="9afae-139">long</span></span> | <span data-ttu-id="9afae-140">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="9afae-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9afae-141">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden.</span><span class="sxs-lookup"><span data-stu-id="9afae-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="9afae-142">string</span><span class="sxs-lookup"><span data-stu-id="9afae-142">string</span></span> | <span data-ttu-id="9afae-143">Tabelle, die die Details des Ereignisses enthält</span><span class="sxs-lookup"><span data-stu-id="9afae-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9afae-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9afae-144">Related topics</span></span>
- [<span data-ttu-id="9afae-145">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9afae-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9afae-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="9afae-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9afae-147">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="9afae-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
