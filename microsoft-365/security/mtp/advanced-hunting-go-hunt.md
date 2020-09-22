---
title: Abrufen relevanter Informationen zu einer Entität mit Go Hunt
description: In diesem Artikel erfahren Sie, wie Sie mit dem Tool "Go Hunt" schnell relevante Informationen zu einer Entität oder einem Ereignis mithilfe der erweiterten Suche Abfragen können.
keywords: Erweiterte Jagd, Vorfall, Pivot, Entität, Go Hunt, relevante Ereignisse, Bedrohungs Suche, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 496deff5d2fda47b7ffac4bc87e98bf28e90ea50
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196965"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Schnelle Suche nach Entitäts-oder Ereignisinformationen mit Go Hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Mit der *Go Hunt* -Aktion können Sie schnell Ereignisse und verschiedene Entitätstypen mithilfe leistungsfähiger abfragebasierter [Erweiterter Jagd](advanced-hunting-overview.md) Funktionen untersuchen. Mit dieser Aktion wird automatisch eine erweiterte Suchabfrage ausgeführt, um relevante Informationen zu dem ausgewählten Ereignis oder der ausgewählten Entität zu finden.

Die *Go Hunt* -Aktion steht in verschiedenen Abschnitten des Sicherheitscenters zur Verfügung, wenn Ereignis-oder Entitäts Details angezeigt werden. Beispielsweise können Sie *Go Hunt* aus den folgenden Abschnitten verwenden:

- Auf der [Seite Vorfall](investigate-incidents.md#incident-overview)können Sie Details zu Benutzern, Geräten und vielen anderen Entitäten anzeigen, die einem Vorfall zugeordnet sind. Wenn Sie eine Entität auswählen, erhalten Sie zusätzliche Informationen sowie verschiedene Aktionen, die Sie für diese entitity ausführen können. Im folgenden Beispiel wird ein Postfach ausgewählt, in dem Details zu dem Postfach angezeigt werden, sowie die Option zum Durchsuchen weiterer Informationen zum Postfach.

    ![Bild mit Postfachdetails mit der Option "Go Hunt"](../../media/mtp-ah/go-hunt-email.png)

- Auf der Seite Vorfall können Sie auch auf eine Liste von Entitäten unter der Registerkarte Beweise zugreifen. Wenn Sie eine dieser Entitäten auswählen, können Sie schnell nach Informationen zu dieser Entität suchen.

    ![Bild mit ausgewählter Datei mit der Option "Go Hunt" auf der Registerkarte "Beweise"](../../media/mtp-ah/go-hunt-evidence-file.png)


- Wenn Sie die Zeitachse für ein Gerät anzeigen, können Sie ein Ereignis in der Zeitachse auswählen, um zusätzliche Informationen zu diesem Ereignis anzuzeigen. Nachdem ein Ereignis ausgewählt wurde, haben Sie die Möglichkeit, andere relevante Ereignisse in der erweiterten Suche zu übernehmen.

    ![Bild mit Ereignisdetails mit der Option "Go Hunt"](../../media/mtp-ah/go-hunt-event.png)

Durch Auswählen von **Go Hunt** oder **Hunt für verwandte Ereignisse** werden unterschiedliche Abfragen übergeben, je nachdem, ob Sie eine Entität oder ein Ereignis ausgewählt haben.

## <a name="query-for-entity-information"></a>Abfrage für Entitätsinformationen
Bei Verwendung von *Go Hunt* zum Abfragen von Informationen zu einem Benutzer, Gerät oder einem anderen Entitätstyp überprüft die Abfrage alle relevanten Schema Tabellen auf alle Ereignisse, die diese Entität betreffen. Um die Ergebnisse verwaltbar zu halten, wird die Abfrage auf den gleichen Zeitraum wie die früheste Aktivität in den letzten 30 Tagen beschränkt, die die Entität umfasst und dem Vorfall zugeordnet ist.

Hier ist ein Beispiel für die Go Hunt-Abfrage für ein Gerät:

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
Sie können *Go Hunt* verwenden, nachdem Sie einen dieser Entitätstypen ausgewählt haben:

- Dateien
- E-Mails
- E-Mail-Cluster
- Postfächer
- Benutzer
- Geräte
- IP-Adressen
- URLs

## <a name="query-for-event-information"></a>Abfragen von Ereignisinformationen
Bei Verwendung von *Go Hunt* zum Abfragen von Informationen zu einem zeitachsenereignis überprüft die Abfrage alle relevanten Schema Tabellen auf andere Ereignisse um den Zeitpunkt des ausgewählten Ereignisses. In der folgenden Abfrage werden beispielsweise Ereignisse in verschiedenen Schema Tabellen aufgelistet, die um denselben Zeitraum auf demselben Gerät aufgetreten sind:

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
Mit einigen Kenntnissen der [Abfragesprache](advanced-hunting-query-language.md)können Sie die Abfrage nach Ihren Wünschen anpassen. Sie können beispielsweise diese Reihe anpassen, die die Größe des Zeitfensters bestimmt:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Zusätzlich zum Ändern der Abfrage, um relevantere Ergebnisse zu erhalten, können Sie auch folgende Aufgaben durchführen:
- [Anzeigen der Ergebnisse als Diagramme](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Erstellen einer benutzerdefinierten Erkennungsregel](custom-detection-rules.md)

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Benutzerdefinierte Erkennungsregeln](custom-detection-rules.md)
