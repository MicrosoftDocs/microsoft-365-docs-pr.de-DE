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
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Schnelle Suche nach Entitäts- oder Ereignisinformationen mit Go Hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender
- Microsoft Defender für Endpunkt

Mit der *Go-Hunt-Aktion* können Sie Ereignisse und verschiedene Entitätstypen mithilfe leistungsstarker abfragebasierter erweiterter [Suchfunktionen schnell](advanced-hunting-overview.md) untersuchen. Mit dieser Aktion wird automatisch eine erweiterte Suchabfrage ausgeführt, um relevante Informationen zum ausgewählten Ereignis oder der ausgewählten Entität zu finden.

Die *Aktion zum Aufsuchen* ist in verschiedenen Abschnitten des Sicherheitscenters verfügbar, wenn Ereignis- oder Entitätsdetails angezeigt werden. Sie können z. B. die *suche in* den folgenden Abschnitten verwenden:

- Auf der [Seite Vorfall](investigate-incidents.md#summary)können Sie Details zu Benutzern, Geräten und vielen anderen Entitäten überprüfen, die einem Vorfall zugeordnet sind. Wenn Sie eine Entität auswählen, erhalten Sie zusätzliche Informationen sowie verschiedene Aktionen, die Sie für diese Entität ausführen können. Im folgenden Beispiel wird ein Postfach ausgewählt, das Details zum Postfach sowie die Option zum Aufsuchen nach weiteren Informationen zum Postfach enthält.

    ![Abbildung mit Postfachdetails mit der Option zum Aufsuchen](../../media/mtp-ah/go-hunt-email.png)

- Auf der Seite "Vorfall" können Sie auch auf eine Liste der Entitäten unter der Registerkarte Nachweis zugreifen. Das Auswählen einer dieser Entitäten bietet eine Möglichkeit, schnell nach Informationen zu dieser Entität zu fahnen.

    ![Abbildung der ausgewählten Datei mit der Option zum Aufsuchen auf der Registerkarte Nachweis](../../media/mtp-ah/go-hunt-evidence-file.png)


- Beim Anzeigen der Zeitachse für ein Gerät können Sie ein Ereignis auf der Zeitachse auswählen, um zusätzliche Informationen zu diesem Ereignis anzuzeigen. Sobald ein Ereignis ausgewählt ist, erhalten Sie die Möglichkeit, nach anderen relevanten Ereignissen in der erweiterten Suche zu fahnen.

    ![Abbildung mit Ereignisdetails mit der Option zum Aufsuchen](../../media/mtp-ah/go-hunt-event.png)

Wenn **Sie Go hunt** oder Hunt für **verwandte** Ereignisse auswählen, werden unterschiedliche Abfragen ausgeführt, je nachdem, ob Sie eine Entität oder ein Ereignis ausgewählt haben.

## <a name="query-for-entity-information"></a>Abfragen von Entitätsinformationen
Wenn Sie *go hunt* verwenden, um Informationen zu einem Benutzer, Gerät oder einem anderen Entitätstyp zu abfragen, überprüft die Abfrage alle relevanten Schematabellen auf Ereignisse, die diese Entität enthalten. Um die Ergebnisse verwaltbar zu halten, ist die Abfrage auf etwa den gleichen Zeitraum wie die früheste Aktivität in den letzten 30 Tagen begrenzt, die die Entität umfasst und dem Vorfall zugeordnet ist.

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
Sie können go *hunt verwenden,* nachdem Sie einen der folgenden Entitätstypen ausgewählt haben:

- Dateien
- E-Mails
- E-Mail-Cluster
- Postfächer
- Benutzer
- Geräte
- IP-Adressen
- URLs

## <a name="query-for-event-information"></a>Abfragen von Ereignisinformationen
Wenn Sie *go hunt* verwenden, um Informationen zu einem Zeitachsenereignis zu abfragen, überprüft die Abfrage alle relevanten Schematabellen auf andere Ereignisse zum Zeitpunkt des ausgewählten Ereignisses. In der folgenden Abfrage werden beispielsweise Ereignisse in verschiedenen Schematabellen aufgeführt, die rund um denselben Zeitraum auf demselben Gerät aufgetreten sind:

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
Mit einigen Kenntnissen der [Abfragesprache](advanced-hunting-query-language.md)können Sie die Abfrage an Ihre Präferenz anpassen. Beispielsweise können Sie diese Zeile anpassen, die die Größe des Zeitfensters bestimmt:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Zusätzlich zum Ändern der Abfrage, um relevantere Ergebnisse zu erhalten, können Sie auch:
- [Anzeigen der Ergebnisse als Diagramme](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Erstellen einer benutzerdefinierten Erkennungsregel](custom-detection-rules.md)

>[!NOTE]
>Einige Tabellen in diesem Artikel sind möglicherweise nicht in Microsoft Defender for Endpoint verfügbar. [Aktivieren Sie Microsoft 365 Defender,](m365d-enable.md) um bedrohungen mithilfe von weiteren Datenquellen nach Bedrohungen zu fahnen. Sie können Ihre erweiterten Suchworkflows von Microsoft Defender for Endpoint zu Microsoft 365 Defender verschieben, indem Sie die Schritte unter [Migrate advanced hunting queries from Microsoft Defender for Endpoint ausführen.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Regeln für die benutzerdefinierte Erkennung](custom-detection-rules.md)
