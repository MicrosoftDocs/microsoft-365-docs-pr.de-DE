---
title: Erhalten relevanter Informationen zu einer Entität mit "Go Hunt"
description: Erfahren Sie, wie Sie das Suchtool verwenden, um mithilfe der erweiterten Suche schnell relevante Informationen zu einer Entität oder einem Ereignis zu erhalten.
keywords: Erweiterte Suche, Vorfall, Pivot, Entität, Suche, relevante Ereignisse, Bedrohungssuche, Cyberbedrohungssuche, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929505"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="d78b4-104">Schnelles Aufsuchen nach Entitäts- oder Ereignisinformationen mit Go Hunt</span><span class="sxs-lookup"><span data-stu-id="d78b4-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d78b4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d78b4-105">**Applies to:**</span></span>
- <span data-ttu-id="d78b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d78b4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d78b4-107">Mit der *Aktion "Suche los"* können Sie Ereignisse und verschiedene Entitätstypen mithilfe leistungsstarker, abfragebasierter [erweiterter Suchfunktionen schnell untersuchen.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d78b4-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="d78b4-108">Diese Aktion führt automatisch eine erweiterte Suchabfrage aus, um relevante Informationen zum ausgewählten Ereignis oder der ausgewählten Entität zu finden.</span><span class="sxs-lookup"><span data-stu-id="d78b4-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="d78b4-109">Die *Aktion "Sammelsuche"* ist in verschiedenen Abschnitten des Sicherheitscenters verfügbar, wenn Ereignis- oder Entitätsdetails angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d78b4-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="d78b4-110">Sie können z. B. die *Suche in* den folgenden Abschnitten verwenden:</span><span class="sxs-lookup"><span data-stu-id="d78b4-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="d78b4-111">Auf der [Vorfallseite](investigate-incidents.md#incident-overview)können Sie Details zu Benutzern, Geräten und vielen anderen Entitäten überprüfen, die einem Vorfall zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d78b4-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="d78b4-112">Wenn Sie eine Entität auswählen, erhalten Sie zusätzliche Informationen sowie verschiedene Aktionen, die Sie für diese Empfindlichkeit ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="d78b4-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="d78b4-113">Im folgenden Beispiel wird ein Postfach ausgewählt, in dem Details zum Postfach sowie die Option zum Aufsuchen nach weiteren Informationen zum Postfach angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d78b4-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Abbildung der Postfachdetails mit der Option "Sammelsuche"](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="d78b4-115">Auf der Vorfallseite können Sie auch auf eine Liste der Entitäten unter der Registerkarte "Nachweis" zugreifen. Das Auswählen einer dieser Entitäten bietet eine Möglichkeit, schnell nach Informationen zu dieser Entität zu finden.</span><span class="sxs-lookup"><span data-stu-id="d78b4-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Abbildung der ausgewählten Datei mit der Option "Suche los" auf der Registerkarte "Nachweis"](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="d78b4-117">Beim Anzeigen der Zeitachse für ein Gerät können Sie ein Ereignis auf der Zeitachse auswählen, um zusätzliche Informationen zu diesem Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d78b4-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="d78b4-118">Nachdem ein Ereignis ausgewählt wurde, erhalten Sie die Möglichkeit, andere relevante Ereignisse in der erweiterten Suche zu finden.</span><span class="sxs-lookup"><span data-stu-id="d78b4-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Abbildung der Ereignisdetails mit der Option "Lossuche"](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="d78b4-120">Wenn **Sie "Suche oder** Suche nach verwandten **Ereignissen"** auswählen, werden unterschiedliche Abfragen ausgeführt, je nachdem, ob Sie eine Entität oder ein Ereignis ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="d78b4-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="d78b4-121">Abfragen von Entitätsinformationen</span><span class="sxs-lookup"><span data-stu-id="d78b4-121">Query for entity information</span></span>
<span data-ttu-id="d78b4-122">Bei Verwendung *von Go Hunt* zum Abfragen von Informationen zu einem Benutzer, Gerät oder einem anderen Entitätstyp überprüft die Abfrage alle relevanten Schematabellen auf Alle Ereignisse, an denen diese Entität beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="d78b4-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="d78b4-123">Damit die Ergebnisse verwaltbar bleiben, ist die Abfrage auf etwa den gleichen Zeitraum wie die früheste Aktivität in den letzten 30 Tagen begrenzt, die die Entität umfasst und dem Vorfall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d78b4-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="d78b4-124">Hier ist ein Beispiel für die Suchabfrage für ein Gerät:</span><span class="sxs-lookup"><span data-stu-id="d78b4-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="d78b4-125">Unterstützte Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="d78b4-125">Supported entity types</span></span>
<span data-ttu-id="d78b4-126">Sie können *"Go Hunt"* verwenden, nachdem Sie einen der folgenden Entitätstypen ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="d78b4-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="d78b4-127">Dateien</span><span class="sxs-lookup"><span data-stu-id="d78b4-127">Files</span></span>
- <span data-ttu-id="d78b4-128">E-Mails</span><span class="sxs-lookup"><span data-stu-id="d78b4-128">Emails</span></span>
- <span data-ttu-id="d78b4-129">E-Mail-Cluster</span><span class="sxs-lookup"><span data-stu-id="d78b4-129">Email clusters</span></span>
- <span data-ttu-id="d78b4-130">Postfächer</span><span class="sxs-lookup"><span data-stu-id="d78b4-130">Mailboxes</span></span>
- <span data-ttu-id="d78b4-131">Benutzer</span><span class="sxs-lookup"><span data-stu-id="d78b4-131">Users</span></span>
- <span data-ttu-id="d78b4-132">Geräte</span><span class="sxs-lookup"><span data-stu-id="d78b4-132">Devices</span></span>
- <span data-ttu-id="d78b4-133">IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="d78b4-133">IP addresses</span></span>
- <span data-ttu-id="d78b4-134">URLs</span><span class="sxs-lookup"><span data-stu-id="d78b4-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="d78b4-135">Abfragen von Ereignisinformationen</span><span class="sxs-lookup"><span data-stu-id="d78b4-135">Query for event information</span></span>
<span data-ttu-id="d78b4-136">Bei Verwendung *von "Go Hunt"* zum Abfragen von Informationen zu einem Zeitachsenereignis überprüft die Abfrage alle relevanten Schematabellen auf andere Ereignisse zum Zeitpunkt des ausgewählten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="d78b4-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="d78b4-137">Die folgende Abfrage listet beispielsweise Ereignisse in verschiedenen Schematabellen auf, die im gleichen Zeitraum auf demselben Gerät aufgetreten sind:</span><span class="sxs-lookup"><span data-stu-id="d78b4-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="d78b4-138">Anpassen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="d78b4-138">Adjust the query</span></span>
<span data-ttu-id="d78b4-139">Mit einigen Kenntnissen der [Abfragesprache](advanced-hunting-query-language.md)können Sie die Abfrage an Ihre Bevorzugte anpassen.</span><span class="sxs-lookup"><span data-stu-id="d78b4-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="d78b4-140">Beispielsweise können Sie diese Zeile anpassen, die die Größe des Zeitfensters bestimmt:</span><span class="sxs-lookup"><span data-stu-id="d78b4-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="d78b4-141">Sie können nicht nur die Abfrage ändern, um relevantere Ergebnisse zu erhalten, sondern auch:</span><span class="sxs-lookup"><span data-stu-id="d78b4-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="d78b4-142">Anzeigen der Ergebnisse als Diagramme</span><span class="sxs-lookup"><span data-stu-id="d78b4-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="d78b4-143">Erstellen einer benutzerdefinierten Erkennungsregel</span><span class="sxs-lookup"><span data-stu-id="d78b4-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="d78b4-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d78b4-144">Related topics</span></span>
- [<span data-ttu-id="d78b4-145">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="d78b4-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d78b4-146">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d78b4-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d78b4-147">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="d78b4-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d78b4-148">Benutzerdefinierte Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="d78b4-148">Custom detection rules</span></span>](custom-detection-rules.md)
