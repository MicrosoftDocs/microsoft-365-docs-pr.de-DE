---
title: Abfrage bewährter Methoden für die erweiterte Suche
description: Erfahren Sie, wie Sie schnelle, effiziente und fehlerfreie Suchanfragen bei der Bedrohungssuche mit Hilfe der erweiterten Suche erstellen können.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Mdatp, Microsoft Defender Atp, wdatp-Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Timeout vermeiden, Befehlszeilen, Prozess-ID
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064392"
---
# <a name="advanced-hunting-query-best-practices"></a>Bewährte Methoden für Erweiterte Suchanfragen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Optimieren der Abfrageleistung

Wenden Sie diese Empfehlungen an, um Ergebnisse schneller zu erhalten und Timeouts beim Ausführen komplexer Abfragen zu vermeiden.

- Verwenden Sie beim Ausprobieren neuer Abfragen immer `limit`, um extrem große Resultset zu vermeiden. Sie können die Größe der Resultsets auch mithilfe von `count` bewerten.
- Verwenden Sie zunächst Zeitfilter. Im Idealfall beschränken Sie Ihre Abfragen auf sieben Tage.
- Setzen Sie Filter, die die meisten Daten zu Beginn der Abfrage entfernen sollen, direkt nach dem Zeitfilter.
- Verwenden Sie den Operator`has` anstatt`contains`, wenn Sie nach vollständigen Token suchen.
- Suchen Sie in einer bestimmten Spalte, anstatt Volltextsuchen über alle Spalten hinweg durchzuführen.
- Wenn Sie Tabellen zusammenfügen, geben Sie zuerst die Tabelle mit weniger Zeilen an.
- `project` nur die notwendigen Spalten aus den Tabellen, die Sie verknüpft haben.

>[!TIP]
>Weitere Informationen zur Verbesserung der Abfrageleistung finden Sie in[Bewährte Methoden für Kusto Anfragen](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Tipps und Probleme mit der Suchanfrage

### <a name="queries-with-process-ids"></a>Abfragen mit Prozess-IDs

Prozess-IDs (PIDs) werden in Windows für neue Prozesse wiederverwendet. Allein können sie nicht als eindeutige Identifikatoren für bestimmte Prozesse dienen. Um einen eindeutigen Bezeichner für einen Prozess auf einem bestimmten Gerät zu erhalten, verwenden Sie die Prozess-ID zusammen mit der Prozesserstellungszeit. Wenn Sie Daten mit Prozessen verbinden oder zusammenfassen, fügen Sie Spalten für die Geräte-ID (entweder oder ), die Prozess-ID ( oder ) und die `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` Prozesserstellungszeit ( oder `ProcessCreationTime` ) ein. `InitiatingProcessCreationTime`

Die folgende Beispielabfrage findet Prozesse, die über Port 445 (SMB) auf mehr als 10 IP-Adressen zugreifen und möglicherweise nach Dateifreigaben suchen.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Die Query fasst sowohl`InitiatingProcessId` als auch`InitiatingProcessCreationTime` zusammen, um einen einzelnen Prozess darzustellen, ohne mehrere Prozesse mit derselben Prozess-ID miteinander zu vermischen.

### <a name="queries-with-command-lines"></a>Abfragen mit Befehlszeilen

Befehlszeilen können variieren. Filtern Sie ggf. nach Dateinamen und führen Sie Fuzzyübereinstimmungen durch.

Es gibt zahlreiche Möglichkeiten, eine Befehlszeile zu erstellen, um eine Aufgabe auszuführen. Ein Angreifer könnte beispielsweise auf eine Bilddatei mit oder ohne Pfad, ohne Dateierweiterung, mit Umgebungsvariablen oder mit Anführungszeichen verweisen. Darüber hinaus kann der Angreifer auch die Reihenfolge der Parameter ändern oder mehrere Anführungszeichen und Leerzeichen hinzufügen.

Um dauerhaftere Abfragen über Befehlszeilen zu erstellen, führen Sie die folgenden Schritte aus:

- Identifizieren Sie die bekannten Prozesse (wie *net.exe* oder *psexec.exe*), indem Sie die Felder mit dem Dateinamen übereinstimmen, anstatt nach dem Befehlszeilenfeld zu filtern.
- Wenn Sie nach Befehlszeilenargumenten suchen, suchen Sie nicht nach einer genauen Übereinstimmung für mehrere unabhängige Argumente in einer bestimmten Reihenfolge. Verwenden Sie stattdessen reguläre Ausdrücke oder verwenden Sie mehrere separate enthaltene Operatoren.
- Verwenden Sie Übereinstimmungen zwischen Groß- und Kleinschreibung. Verwenden Sie z. B. `=~` , und anstelle von , `in~` `contains` `==` `in` und `contains_cs`
- Um die DOS-Befehlszeilenverschleierungstechniken abzuschwächen, sollten Sie Anführungszeichen entfernen, Kommas durch Leerzeichen ersetzen und mehrere aufeinanderfolgende Leerzeichen durch ein einziges Leerzeichen ersetzen. Beachten Sie, dass es komplexere DOS-Verschleierungstechniken gibt, die andere Ansätze erfordern, aber diese helfen die gängigsten zu beheben.

Die folgenden Beispiele zeigen verschiedene Möglichkeiten, eine Abfrage zu erstellen, die nach der Datei *net.exe* sucht, um den Dienst Windows Defender Firewall zu beenden:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Benutzerdefinierte Erkennungen – Übersicht](overview-custom-detections.md)
