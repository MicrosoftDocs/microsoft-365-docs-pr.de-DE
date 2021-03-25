---
title: Erhalten relevanter Informationen zu einer Entität mit einer Go-Hunt
description: Erfahren Sie, wie Sie mithilfe des Suchtools schnell relevante Informationen zu einer Entität oder einem Ereignis mithilfe der erweiterten Suche abfragen können.
keywords: advanced hunting, incident, pivot, entity, go hunt, relevant events, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-maave
author: martyav
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fe3c204fe49f008cf5d9dd18b5066fa91dc6196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067952"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="527f9-104">Schnelle Suche nach Entitäts- oder Ereignisinformationen mit Go Hunt</span><span class="sxs-lookup"><span data-stu-id="527f9-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="527f9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="527f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="527f9-106">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="527f9-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="527f9-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="527f9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="527f9-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="527f9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


<span data-ttu-id="527f9-109">Mit der *Go-Hunt-Aktion* können Sie Ereignisse und verschiedene Entitätstypen mithilfe leistungsstarker abfragebasierter erweiterter [Suchfunktionen schnell](advanced-hunting-overview.md) untersuchen.</span><span class="sxs-lookup"><span data-stu-id="527f9-109">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="527f9-110">Mit dieser Aktion wird automatisch eine erweiterte Suchabfrage ausgeführt, um relevante Informationen zum ausgewählten Ereignis oder der ausgewählten Entität zu finden.</span><span class="sxs-lookup"><span data-stu-id="527f9-110">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="527f9-111">Die *Aktion zum Aufsuchen* ist in verschiedenen Abschnitten des Sicherheitscenters verfügbar, wenn Ereignis- oder Entitätsdetails angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="527f9-111">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="527f9-112">Sie können z. B. die *suche in* den folgenden Abschnitten verwenden:</span><span class="sxs-lookup"><span data-stu-id="527f9-112">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="527f9-113">Auf der [Seite Vorfall](investigate-incidents.md)können Sie Details zu Benutzern, Geräten und vielen anderen Entitäten überprüfen, die einem Vorfall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="527f9-113">In the [incident page](investigate-incidents.md), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="527f9-114">Wenn Sie eine Entität auswählen, erhalten Sie zusätzliche Informationen sowie verschiedene Aktionen, die Sie für diese Entität ausführen können.</span><span class="sxs-lookup"><span data-stu-id="527f9-114">When you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="527f9-115">Im folgenden Beispiel wird ein Gerät ausgewählt, das Details zum Gerät sowie die Option zum Aufsuchen nach weiteren Informationen zum Gerät enthält.</span><span class="sxs-lookup"><span data-stu-id="527f9-115">In the example below, a device is selected, showing details about the device as well the option to hunt for more information about the device.</span></span>

    ![Abbildung mit Gerätedetails mit der Option zum Aufsuchen](./images/go-hunt-device.png)

- <span data-ttu-id="527f9-117">Auf der Seite "Vorfall" können Sie auch auf eine Liste der Entitäten unter der Registerkarte Nachweis zugreifen. Das Auswählen einer dieser Entitäten bietet eine Möglichkeit, schnell nach Informationen zu dieser Entität zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="527f9-117">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Abbildung mit ausgewählter URL mit der Option zum Aufsuchen auf der Registerkarte Nachweise](./images/go-hunt-evidence-url.png)

- <span data-ttu-id="527f9-119">Beim Anzeigen der Zeitachse für ein Gerät können Sie ein Ereignis auf der Zeitachse auswählen, um zusätzliche Informationen zu diesem Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="527f9-119">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="527f9-120">Sobald ein Ereignis ausgewählt ist, erhalten Sie die Möglichkeit, nach anderen relevanten Ereignissen in der erweiterten Suche zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="527f9-120">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Abbildung mit Ereignisdetails mit der Option zum Aufsuchen](./images/go-hunt-event.png)

<span data-ttu-id="527f9-122">Wenn **Sie Go hunt** oder Hunt für **verwandte** Ereignisse auswählen, werden unterschiedliche Abfragen ausgeführt, je nachdem, ob Sie eine Entität oder ein Ereignis ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="527f9-122">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="527f9-123">Abfragen von Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="527f9-123">Query for entity information</span></span>

<span data-ttu-id="527f9-124">Wenn Sie *go hunt* verwenden, um Informationen zu einem Benutzer, Gerät oder einem anderen Entitätstyp zu abfragen, überprüft die Abfrage alle relevanten Schematabellen auf Ereignisse, die diese Entität enthalten.</span><span class="sxs-lookup"><span data-stu-id="527f9-124">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="527f9-125">Um die Ergebnisse verwaltbar zu halten, ist die Abfrage auf etwa den gleichen Zeitraum wie die früheste Aktivität in den letzten 30 Tagen begrenzt, die die Entität umfasst und dem Vorfall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="527f9-125">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="527f9-126">Hier ist ein Beispiel für die Suchabfrage für ein Gerät:</span><span class="sxs-lookup"><span data-stu-id="527f9-126">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```

### <a name="supported-entity-types"></a><span data-ttu-id="527f9-127">Unterstützte Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="527f9-127">Supported entity types</span></span>

<span data-ttu-id="527f9-128">Sie können go *hunt verwenden,* nachdem Sie einen der folgenden Entitätstypen ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="527f9-128">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="527f9-129">Dateien</span><span class="sxs-lookup"><span data-stu-id="527f9-129">Files</span></span>
- <span data-ttu-id="527f9-130">Benutzer</span><span class="sxs-lookup"><span data-stu-id="527f9-130">Users</span></span>
- <span data-ttu-id="527f9-131">Geräte</span><span class="sxs-lookup"><span data-stu-id="527f9-131">Devices</span></span>
- <span data-ttu-id="527f9-132">IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="527f9-132">IP addresses</span></span>
- <span data-ttu-id="527f9-133">URLs</span><span class="sxs-lookup"><span data-stu-id="527f9-133">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="527f9-134">Abfragen von Ereignisinformationen</span><span class="sxs-lookup"><span data-stu-id="527f9-134">Query for event information</span></span>

<span data-ttu-id="527f9-135">Wenn Sie *go hunt* verwenden, um Informationen zu einem Zeitachsenereignis zu abfragen, überprüft die Abfrage alle relevanten Schematabellen auf andere Ereignisse zum Zeitpunkt des ausgewählten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="527f9-135">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="527f9-136">In der folgenden Abfrage werden beispielsweise Ereignisse in verschiedenen Schematabellen aufgeführt, die rund um denselben Zeitraum auf demselben Gerät aufgetreten sind:</span><span class="sxs-lookup"><span data-stu-id="527f9-136">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected RegistryValueSet event
let selectedEventTimestamp = datetime(2020-10-06T21:40:25.3466868Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "a305b52049c4658ec63ae8b55becfe5954c654a4"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="527f9-137">Anpassen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="527f9-137">Adjust the query</span></span>

<span data-ttu-id="527f9-138">Mit einigen Kenntnissen der [Abfragesprache](advanced-hunting-query-language.md)können Sie die Abfrage an Ihre Präferenz anpassen.</span><span class="sxs-lookup"><span data-stu-id="527f9-138">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="527f9-139">Beispielsweise können Sie diese Zeile anpassen, die die Größe des Zeitfensters bestimmt:</span><span class="sxs-lookup"><span data-stu-id="527f9-139">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="527f9-140">Zusätzlich zum Ändern der Abfrage, um relevantere Ergebnisse zu erhalten, können Sie auch:</span><span class="sxs-lookup"><span data-stu-id="527f9-140">In addition to modifying the query to get more relevant results, you can also:</span></span>

- [<span data-ttu-id="527f9-141">Anzeigen der Ergebnisse als Diagramme</span><span class="sxs-lookup"><span data-stu-id="527f9-141">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="527f9-142">Erstellen einer benutzerdefinierten Erkennungsregel</span><span class="sxs-lookup"><span data-stu-id="527f9-142">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="527f9-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="527f9-143">Related topics</span></span>

- [<span data-ttu-id="527f9-144">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="527f9-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="527f9-145">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="527f9-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="527f9-146">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="527f9-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="527f9-147">Regeln für die benutzerdefinierte Erkennung</span><span class="sxs-lookup"><span data-stu-id="527f9-147">Custom detection rules</span></span>](custom-detection-rules.md)
