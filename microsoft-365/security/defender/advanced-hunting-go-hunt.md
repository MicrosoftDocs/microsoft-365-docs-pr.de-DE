---
title: Erhalten relevanter Informationen zu einer Entität mit einer Go-Hunt
description: Erfahren Sie, wie Sie mit dem Go-Hunt-Tool schnell relevante Informationen zu einer Entität oder einem Ereignis mithilfe der erweiterten Suche abfragen können.
keywords: advanced hunting, incident, pivot, entity, go hunt, relevant events, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952656"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="b2761-104">Schnelle Suche nach Entitäts- oder Ereignisinformationen mit Go Hunt</span><span class="sxs-lookup"><span data-stu-id="b2761-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2761-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b2761-105">**Applies to:**</span></span>
- <span data-ttu-id="b2761-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2761-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b2761-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2761-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="b2761-108">Mit der *Go-Hunt-Aktion* können Sie Ereignisse und verschiedene Entitätstypen mithilfe leistungsstarker abfragebasierter erweiterter [Suchfunktionen schnell](advanced-hunting-overview.md) untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b2761-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="b2761-109">Mit dieser Aktion wird automatisch eine erweiterte Suchabfrage ausgeführt, um relevante Informationen zum ausgewählten Ereignis oder der ausgewählten Entität zu finden.</span><span class="sxs-lookup"><span data-stu-id="b2761-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="b2761-110">Die *Aktion zum Aufsuchen* ist in verschiedenen Abschnitten des Sicherheitscenters verfügbar, wenn Ereignis- oder Entitätsdetails angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2761-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="b2761-111">Sie können z. B. die *suche in* den folgenden Abschnitten verwenden:</span><span class="sxs-lookup"><span data-stu-id="b2761-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="b2761-112">Auf der [Seite Vorfall](investigate-incidents.md#summary)können Sie Details zu Benutzern, Geräten und vielen anderen Entitäten überprüfen, die einem Vorfall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b2761-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="b2761-113">Wenn Sie eine Entität auswählen, erhalten Sie zusätzliche Informationen sowie verschiedene Aktionen, die Sie für diese Entität ausführen können.</span><span class="sxs-lookup"><span data-stu-id="b2761-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="b2761-114">Im folgenden Beispiel wird ein Postfach ausgewählt, das Details zum Postfach sowie die Option zum Aufsuchen nach weiteren Informationen zum Postfach enthält.</span><span class="sxs-lookup"><span data-stu-id="b2761-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Abbildung mit Postfachdetails mit der Option zum Aufsuchen](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="b2761-116">Auf der Seite "Vorfall" können Sie auch auf eine Liste der Entitäten unter der Registerkarte Nachweis zugreifen. Das Auswählen einer dieser Entitäten bietet eine Möglichkeit, schnell nach Informationen zu dieser Entität zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="b2761-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Abbildung der ausgewählten Datei mit der Option zum Aufsuchen auf der Registerkarte Nachweis](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="b2761-118">Beim Anzeigen der Zeitachse für ein Gerät können Sie ein Ereignis auf der Zeitachse auswählen, um zusätzliche Informationen zu diesem Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2761-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="b2761-119">Sobald ein Ereignis ausgewählt ist, erhalten Sie die Möglichkeit, nach anderen relevanten Ereignissen in der erweiterten Suche zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="b2761-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Abbildung mit Ereignisdetails mit der Option zum Aufsuchen](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="b2761-121">Wenn **Sie Go hunt** oder Hunt für **verwandte** Ereignisse auswählen, werden unterschiedliche Abfragen ausgeführt, je nachdem, ob Sie eine Entität oder ein Ereignis ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b2761-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="b2761-122">Abfragen von Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="b2761-122">Query for entity information</span></span>
<span data-ttu-id="b2761-123">Wenn Sie *go hunt* verwenden, um Informationen zu einem Benutzer, Gerät oder einem anderen Entitätstyp zu abfragen, überprüft die Abfrage alle relevanten Schematabellen auf Ereignisse, die diese Entität enthalten.</span><span class="sxs-lookup"><span data-stu-id="b2761-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="b2761-124">Um die Ergebnisse verwaltbar zu halten, ist die Abfrage auf etwa den gleichen Zeitraum wie die früheste Aktivität in den letzten 30 Tagen begrenzt, die die Entität umfasst und dem Vorfall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b2761-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="b2761-125">Hier ist ein Beispiel für die Suchabfrage für ein Gerät:</span><span class="sxs-lookup"><span data-stu-id="b2761-125">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="b2761-126">Unterstützte Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="b2761-126">Supported entity types</span></span>
<span data-ttu-id="b2761-127">Sie können go *hunt verwenden,* nachdem Sie einen der folgenden Entitätstypen ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="b2761-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="b2761-128">Dateien</span><span class="sxs-lookup"><span data-stu-id="b2761-128">Files</span></span>
- <span data-ttu-id="b2761-129">E-Mails</span><span class="sxs-lookup"><span data-stu-id="b2761-129">Emails</span></span>
- <span data-ttu-id="b2761-130">E-Mail-Cluster</span><span class="sxs-lookup"><span data-stu-id="b2761-130">Email clusters</span></span>
- <span data-ttu-id="b2761-131">Postfächer</span><span class="sxs-lookup"><span data-stu-id="b2761-131">Mailboxes</span></span>
- <span data-ttu-id="b2761-132">Benutzer</span><span class="sxs-lookup"><span data-stu-id="b2761-132">Users</span></span>
- <span data-ttu-id="b2761-133">Geräte</span><span class="sxs-lookup"><span data-stu-id="b2761-133">Devices</span></span>
- <span data-ttu-id="b2761-134">IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="b2761-134">IP addresses</span></span>
- <span data-ttu-id="b2761-135">URLs</span><span class="sxs-lookup"><span data-stu-id="b2761-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="b2761-136">Abfragen von Ereignisinformationen</span><span class="sxs-lookup"><span data-stu-id="b2761-136">Query for event information</span></span>
<span data-ttu-id="b2761-137">Wenn Sie *go hunt* verwenden, um Informationen zu einem Zeitachsenereignis zu abfragen, überprüft die Abfrage alle relevanten Schematabellen auf andere Ereignisse zum Zeitpunkt des ausgewählten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="b2761-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="b2761-138">In der folgenden Abfrage werden beispielsweise Ereignisse in verschiedenen Schematabellen aufgeführt, die rund um denselben Zeitraum auf demselben Gerät aufgetreten sind:</span><span class="sxs-lookup"><span data-stu-id="b2761-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="b2761-139">Anpassen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="b2761-139">Adjust the query</span></span>
<span data-ttu-id="b2761-140">Mit einigen Kenntnissen der [Abfragesprache](advanced-hunting-query-language.md)können Sie die Abfrage an Ihre Präferenz anpassen.</span><span class="sxs-lookup"><span data-stu-id="b2761-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="b2761-141">Beispielsweise können Sie diese Zeile anpassen, die die Größe des Zeitfensters bestimmt:</span><span class="sxs-lookup"><span data-stu-id="b2761-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="b2761-142">Zusätzlich zum Ändern der Abfrage, um relevantere Ergebnisse zu erhalten, können Sie auch:</span><span class="sxs-lookup"><span data-stu-id="b2761-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="b2761-143">Anzeigen der Ergebnisse als Diagramme</span><span class="sxs-lookup"><span data-stu-id="b2761-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="b2761-144">Erstellen einer benutzerdefinierten Erkennungsregel</span><span class="sxs-lookup"><span data-stu-id="b2761-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="b2761-145">Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender for Endpoint verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b2761-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b2761-146">[Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um bedrohungen mithilfe von weiteren Datenquellen nach Bedrohungen zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="b2761-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="b2761-147">Sie können Ihre erweiterten Suchworkflows von Microsoft Defender for Endpoint zu Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrate advanced hunting queries from Microsoft Defender for Endpoint ausführen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="b2761-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2761-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b2761-148">Related topics</span></span>
- [<span data-ttu-id="b2761-149">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b2761-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b2761-150">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="b2761-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b2761-151">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="b2761-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="b2761-152">Regeln für die benutzerdefinierte Erkennung</span><span class="sxs-lookup"><span data-stu-id="b2761-152">Custom detection rules</span></span>](custom-detection-rules.md)
