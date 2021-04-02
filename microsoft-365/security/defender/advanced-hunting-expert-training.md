---
title: Expertenschulungen für die erweiterte Suche erhalten
description: Kostenlose Schulungen und Anleitungen von Experten für die fortgeschrittene Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, language, training, scenarios, basic to advanced, videos, step-by-step
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
ms.openlocfilehash: 3aee0a210b9381174650a4a817be510bcfaa00c2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498529"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Expertenschulungen für die erweiterte Suche erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Steigern Sie Ihre Kenntnisse der erweiterten Suche schnell mit _Tracking the adversary_, einer Webcastreihe für neue Sicherheitsanalysten und erfahrene Bedrohungssucher. Die Reihe führt Sie durch die Grundlagen bis hin zum Erstellen eigener anspruchsvoller Abfragen. Beginnen Sie mit dem ersten Video zu Grundlagen, oder wechseln Sie zu erweiterten Videos, die Ihrem Erfahrungsniveau angepasst sind.

| Position | Beschreibung | Uhr | Abfragen | 
|--|--|--|--|
| Episode 1: KQL-Grundlagen | Diese Episode behandelt die Grundlagen der erweiterten Suche in Microsoft 365 Defender. Erfahren Sie mehr über verfügbare erweiterte Suchesdaten und grundlegende KQL-Syntax und Operatoren. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Folge 2: Beitritte | Erfahren Sie mehr über Daten in der erweiterten Suche und darüber, wie Sie Tabellen miteinander verbinden. Erfahren Sie mehr über , , und joins, und verstehen Sie die Nuancen der `inner` `outer` `unique` `semi` standardmäßigen Kusto-Verknüpfung. `innerunique` | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Folge 3: Zusammenfassen, Pivotieren und Visualisieren von Daten | Nachdem Sie nun gelernt haben, Daten zu filtern, zu bearbeiten und zu verbinden, ist es an der Zeit, zusammenzufassen, zu quantifizieren, zu pivotieren und zu visualisieren. In dieser Folge werden der `summarize` Operator und verschiedene Berechnungen erläutert, während zusätzliche Tabellen im Schema eingeführt werden. Außerdem lernen Sie, Datasets in Diagramme zu verwandeln, mit deren Hilfe Sie Einblicke gewinnen können. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Folge 4: Let's hunt! Anwenden von KQL auf die Vorfallverfolgung | In dieser Folge lernen Sie, einige Angreiferaktivitäten nachverfolgt zu haben. Wir verwenden unser verbessertes Verständnis von Kusto und der erweiterten Suche, um einen Angriff nachverfolgt zu haben. Erfahren Sie, welche Tricks in diesem Feld verwendet werden, einschließlich der ABCs der Cybersicherheit und wie Sie sie auf die Reaktion auf Vorfälle anwenden. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-Datei](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Erhalten Sie weitere Expertenschulungen mit *L33TSP3AK:* Erweiterte Suche in Microsoft 365 Defender , einer Webcastreihe für Analysten, die ihr technisches Wissen und ihre praktischen Fähigkeiten bei der Durchführung von Sicherheitsuntersuchungen mithilfe der erweiterten Suche in Microsoft 365 Defender erweitern wollen. 

| Position | Beschreibung | Uhr | Abfragen | 
|--|--|--|--|
| Episode 1  | In dieser Folge lernen Sie verschiedene bewährte Methoden beim Ausführen erweiterter Suchabfragen. Zu den behandelten Themen gehören: Optimieren Ihrer Abfragen, Verwenden der erweiterten Suche nach Ransomware, Behandeln von JSON als dynamischen Typ und Arbeiten mit externen Datenoperatoren. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [CSL-Datei](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Verwenden der CSL-Datei
Greifen Sie vor dem Starten einer Folge auf die entsprechende [Kusto-CSL-Datei auf GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) zu, und kopieren Sie deren Inhalte in den editor für erweiterte Suchabfragen. Während Sie eine Folge ansehen, können Sie die kopierten Inhalte verwenden, um dem Lautsprecher zu folgen und Abfragen ausführen. 

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

Die gleiche CSL-Datei enthält Abfragen vor und nach den Kommentaren, wie unten gezeigt. Wenn Sie eine bestimmte Abfrage mit [mehreren Abfragen im](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)Editor ausführen möchten, verschieben Sie den Cursor zu dieser Abfrage, und wählen Sie **Abfrage ausführen aus.**   

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
