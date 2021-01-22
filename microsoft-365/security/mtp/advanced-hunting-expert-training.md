---
title: Expertenschulungen zur erweiterten Suche erhalten
description: Kostenlose Schulungen und Anleitungen von Experten für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Suche nach Cyberbedrohungen, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Sprache, Schulung, Szenarien, einfach bis erweitert, Videos, Schritt-für-Schritt
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
ms.openlocfilehash: d7c2ccb12cb096359e558af9e1b4a962a9130be5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929634"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Expertenschulungen zur erweiterten Suche erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Steigern Sie Ihr Wissen über die erweiterte Suche schnell mit _tracking the adversary_, einer Webcastreihe für neue Sicherheitsanalysten und erfahrene Bedrohungsexperten. Die Reihe führt Sie durch die Grundlagen bis hin zum Erstellen eigener anspruchsvoller Abfragen. Beginnen Sie mit dem ersten Video mit grundlagen oder springen Sie zu fortgeschritteneren Videos, die Ihrem Erfahrungsgrad entsprechend sind.


| Titel | Beschreibung | Uhr | Abfragen | 
|--|--|--|--|
| Teil 1: Grundlagen zu KQL | In dieser Folge werden die Grundlagen der erweiterten Suche in Microsoft 365 Defender behandelt. Erfahren Sie mehr über die verfügbaren Daten zur erweiterten Suche sowie grundlegende #A0 und -Operatoren. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [DATEI "CSL"](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Teil 2: Beitritte | Erfahren Sie mehr über Daten bei der erweiterten Suche und das Verbinden von Tabellen. Erfahren Sie mehr über , und Verknüpfungen, und verstehen Sie die Nuancen der `inner` `outer` `unique` `semi` standardmäßigen `innerunique` Kusto-Verknüpfung. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [DATEI "CSL"](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Teil 3: Zusammenfassung, Pivotieren und Visualisieren von Daten | Nachdem Sie nun gelernt haben, Daten zu filtern, zu bearbeiten und zusammenzufassen, zu quantifizieren, zu pivotieren und zu visualisieren, ist es an der Zeit, Daten zusammenzufassen, zu quantifizieren, zu pivotieren und zu visualisieren. In diesem Abschnitt werden der `summarize` Operator und verschiedene Berechnungen erläutert, während zusätzliche Tabellen in das Schema eingeführt werden. Außerdem lernen Sie, Datasets in Diagramme zu verwandeln, die Ihnen beim Extrahieren von Einblicken helfen können. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Teil 4: Lassen Sie uns die Suche beginnen! Anwenden von KQL auf die Vorfallverfolgung | In dieser Folge lernen Sie, einige Angreiferaktivitäten nachverfolgt zu haben. Wir verwenden unser verbessertes Verständnis von Kusto und der erweiterten Suche, um einen Angriff nachverfolgt zu werden. Lernen Sie die tatsächlichen Tricks kennen, die in diesem Bereich verwendet werden, einschließlich der AbCs der Cybersicherheit und wie Sie sie auf die Reaktion auf Vorfälle anwenden. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Verwenden der CSL-Datei
Bevor Sie eine Folge starten, greifen Sie auf gitHub auf die entsprechende [Kusto-CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) zu, und kopieren Sie den Inhalt in den Abfrageeditor für die erweiterte Suche. Während Sie sich eine Folge ansehen, können Sie die kopierten Inhalte verwenden, um dem Sprecher zu folgen und Abfragen ausführen. 

Der folgende Auszug aus einer CSL-Datei zeigt einen umfassenden Satz von Anleitungen, die als Kommentare mit gekennzeichnet `//` sind.

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Die gleiche CSL-Datei enthält Abfragen vor und nach den Kommentaren, wie unten dargestellt. Wenn Sie eine bestimmte Abfrage mit mehreren Abfragen im [Editor](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)ausführen möchten, verschieben Sie den Cursor zu dieser Abfrage, und wählen Sie **"Abfrage ausführen" aus.**   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
