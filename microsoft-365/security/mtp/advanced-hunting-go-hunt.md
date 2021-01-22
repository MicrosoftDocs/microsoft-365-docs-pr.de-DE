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
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Schnelles Aufsuchen nach Entitäts- oder Ereignisinformationen mit Go Hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Mit der *Aktion "Suche los"* können Sie Ereignisse und verschiedene Entitätstypen mithilfe leistungsstarker, abfragebasierter [erweiterter Suchfunktionen schnell untersuchen.](advanced-hunting-overview.md) Diese Aktion führt automatisch eine erweiterte Suchabfrage aus, um relevante Informationen zum ausgewählten Ereignis oder der ausgewählten Entität zu finden.

Die *Aktion "Sammelsuche"* ist in verschiedenen Abschnitten des Sicherheitscenters verfügbar, wenn Ereignis- oder Entitätsdetails angezeigt werden. Sie können z. B. die *Suche in* den folgenden Abschnitten verwenden:

- Auf der [Vorfallseite](investigate-incidents.md#incident-overview)können Sie Details zu Benutzern, Geräten und vielen anderen Entitäten überprüfen, die einem Vorfall zugeordnet sind. Wenn Sie eine Entität auswählen, erhalten Sie zusätzliche Informationen sowie verschiedene Aktionen, die Sie für diese Empfindlichkeit ergreifen können. Im folgenden Beispiel wird ein Postfach ausgewählt, in dem Details zum Postfach sowie die Option zum Aufsuchen nach weiteren Informationen zum Postfach angezeigt werden.

    ![Abbildung der Postfachdetails mit der Option "Sammelsuche"](../../media/mtp-ah/go-hunt-email.png)

- Auf der Vorfallseite können Sie auch auf eine Liste der Entitäten unter der Registerkarte "Nachweis" zugreifen. Das Auswählen einer dieser Entitäten bietet eine Möglichkeit, schnell nach Informationen zu dieser Entität zu finden.

    ![Abbildung der ausgewählten Datei mit der Option "Suche los" auf der Registerkarte "Nachweis"](../../media/mtp-ah/go-hunt-evidence-file.png)


- Beim Anzeigen der Zeitachse für ein Gerät können Sie ein Ereignis auf der Zeitachse auswählen, um zusätzliche Informationen zu diesem Ereignis anzuzeigen. Nachdem ein Ereignis ausgewählt wurde, erhalten Sie die Möglichkeit, andere relevante Ereignisse in der erweiterten Suche zu finden.

    ![Abbildung der Ereignisdetails mit der Option "Lossuche"](../../media/mtp-ah/go-hunt-event.png)

Wenn **Sie "Suche oder** Suche nach verwandten **Ereignissen"** auswählen, werden unterschiedliche Abfragen ausgeführt, je nachdem, ob Sie eine Entität oder ein Ereignis ausgewählt haben.

## <a name="query-for-entity-information"></a>Abfragen von Entitätsinformationen
Bei Verwendung *von Go Hunt* zum Abfragen von Informationen zu einem Benutzer, Gerät oder einem anderen Entitätstyp überprüft die Abfrage alle relevanten Schematabellen auf Alle Ereignisse, an denen diese Entität beteiligt ist. Damit die Ergebnisse verwaltbar bleiben, ist die Abfrage auf etwa den gleichen Zeitraum wie die früheste Aktivität in den letzten 30 Tagen begrenzt, die die Entität umfasst und dem Vorfall zugeordnet ist.

Hier ist ein Beispiel für die Suchabfrage für ein Gerät:

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
### <a name="supported-entity-types"></a>Unterstützte Entitätstypen
Sie können *"Go Hunt"* verwenden, nachdem Sie einen der folgenden Entitätstypen ausgewählt haben:

- Dateien
- E-Mails
- E-Mail-Cluster
- Postfächer
- Benutzer
- Geräte
- IP-Adressen
- URLs

## <a name="query-for-event-information"></a>Abfragen von Ereignisinformationen
Bei Verwendung *von "Go Hunt"* zum Abfragen von Informationen zu einem Zeitachsenereignis überprüft die Abfrage alle relevanten Schematabellen auf andere Ereignisse zum Zeitpunkt des ausgewählten Ereignisses. Die folgende Abfrage listet beispielsweise Ereignisse in verschiedenen Schematabellen auf, die im gleichen Zeitraum auf demselben Gerät aufgetreten sind:

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

## <a name="adjust-the-query"></a>Anpassen der Abfrage
Mit einigen Kenntnissen der [Abfragesprache](advanced-hunting-query-language.md)können Sie die Abfrage an Ihre Bevorzugte anpassen. Beispielsweise können Sie diese Zeile anpassen, die die Größe des Zeitfensters bestimmt:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Sie können nicht nur die Abfrage ändern, um relevantere Ergebnisse zu erhalten, sondern auch:
- [Anzeigen der Ergebnisse als Diagramme](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Erstellen einer benutzerdefinierten Erkennungsregel](custom-detection-rules.md)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md)
