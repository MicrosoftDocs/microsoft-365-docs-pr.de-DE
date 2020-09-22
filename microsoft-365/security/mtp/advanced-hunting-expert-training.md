---
title: Holen Sie sich Expert Training on Advanced Hunting
description: ﻿Kostenlose Schulungen und Anleitungen von erfahrenen Jagd Experten
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Sprache, Schulung, Szenarien, Basic to Advanced, Videos, Schritt für Schritt
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
ms.openlocfilehash: 7db1854534964928b622a7c2f47d07654472f048
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197965"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Holen Sie sich Expert Training on Advanced Hunting

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Steigern Sie Ihr Wissen über die erweiterte Suche schnell mit _der Verfolgung des Gegners_, einer Webcast-Reihe für neue Sicherheitsanalysten und erfahrene Bedrohungs Jäger. Die Reihe führt Sie durch die Grundlagen bis hin zum Erstellen Ihrer eigenen anspruchsvollen Abfragen. Beginnen Sie mit dem ersten Video über Fundamentaldaten, oder wechseln Sie zu fortgeschrittenen Videos, die Ihrem Erfahrungsniveau entsprechen.


| Titel | Beschreibung | Uhr | Abfragen | 
|--|--|--|--|
| Episode 1: KQL-Grundlagen | In dieser Episode werden die Grundlagen der erweiterten Suche in Microsoft Threat Protection behandelt. Erfahren Sie mehr über verfügbare erweiterte Jagd Daten und grundlegende KQL-Syntax und Operatoren. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episode 2: Joins | Weiterführende Informationen zu Daten in Advanced Hunting und zum gemeinsamen Verknüpfen von Tabellen. Erfahren Sie mehr über `inner` ,, `outer` `unique` und `semi` Joins, und verstehen Sie die Nuancen der standardmäßigen Kusto `innerunique` Join. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episode 3: zusammenfassen, pivotieren und Visualisieren von Daten | Nachdem Sie nun gelernt haben, Daten zu filtern, zu manipulieren und daran teilzunehmen, ist es an der Zeit, zusammenzufassen, zu quantifizieren, zu pivotieren und zu visualisieren. In dieser Episode `summarize` werden der Operator und verschiedene Berechnungen erläutert, während zusätzliche Tabellen im Schema eingeführt werden. Sie erfahren auch, wie Sie Datasets in Diagramme umwandeln können, die Sie beim Extrahieren von Einblicken unterstützen. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episode 4: Let es Hunt! Anwenden von KQL auf die Vorfall Verfolgung | In dieser Episode erfahren Sie, wie Sie einige Angreifer Aktivitäten verfolgen. Wir verwenden unser verbessertes Verständnis von Kusto und erweiterter Suche, um einen Angriff zu verfolgen. Hier finden Sie aktuelle Tricks, die im Feld verwendet werden, einschließlich des ABC von Cyber und deren Anwendung auf die Vorfall Antwort. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Verwenden der CSL-Datei
Greifen Sie vor dem Starten einer Episode auf die entsprechende [Kusto CSL-Datei auf GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) zu, und kopieren Sie den Inhalt in den erweiterten Suchabfrage-Editor. Wenn Sie eine Episode ansehen, können Sie den kopierten Inhalt verwenden, um dem Lautsprecher zu folgen und Abfragen auszuführen. 

Der folgende Auszug aus einer CSL-Datei zeigt eine umfassende Reihe von Anleitungen, die als Kommentare mit gekennzeichnet sind `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Die gleiche CSL-Datei enthält Abfragen vor und nach den Kommentaren, wie unten dargestellt. Wenn Sie eine bestimmte Abfrage mit [mehreren Abfragen im Editor](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)ausführen möchten, bewegen Sie den Cursor zu dieser Abfrage, und wählen Sie **Abfrage ausführen**aus.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Erlernen der Abfragesprache für die erweiterte Suche](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
