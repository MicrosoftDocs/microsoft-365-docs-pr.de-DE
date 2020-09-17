---
title: Behandeln von Fehlern in Advanced Hunting for Microsoft Threat Protection
description: Verstehen von Fehlern, die bei der erweiterten Suche angezeigt werden
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, Timeout, Ressourcen, Fehler, unbekannter Fehler
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
ms.openlocfilehash: 5bc49ddfa93a06bc8f3d84ce7b8492681ee65cb7
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950927"
---
# <a name="handle-advanced-hunting-errors"></a>Behandeln von erweiterten Jagd Fehlern

Erweiterte Suche zeigt Fehler an, die auf Syntaxfehler und bei Abfragen mit [vordefinierten Grenzwerten](advanced-hunting-limits.md)benachrichtigt werden. In der folgenden Tabelle finden Sie Tipps zum beheben oder vermeiden von Fehlern. 

| Fehlertyp | Ursache | Lösung | Beispiele für Fehlermeldungen |
|--|--|--|--|
| Syntax Fehler | Die Abfrage enthält unbekannte Namen, einschließlich verweisen auf nicht vorhandene Operatoren, Spalten, Funktionen oder Tabellen. | Stellen Sie sicher, dass Verweise auf [Kusto-Operatoren und-Funktionen](https://docs.microsoft.com/azure/data-explorer/kusto/query/) richtig sind. Überprüfen Sie [das Schema](advanced-hunting-schema-tables.md) auf die richtigen erweiterten Jagd Spalten,-Funktionen und-Tabellen. Schließen Sie Variablen Zeichenfolgen in Anführungszeichen ein, damit Sie erkannt werden. Verwenden Sie beim Schreiben Ihrer Abfragen die AutoVervollständigen-Vorschläge von IntelliSense. | `A recognition error occurred.` |
| Semantische Fehler | Während die Abfrage gültige Operator-, Spalten-, Funktions-oder Tabellennamen verwendet, gibt es Fehler in der Struktur und der resultierenden Logik. In einigen Fällen identifiziert Advanced Hunting den bestimmten Operator, der den Fehler verursacht hat. | Überprüfen Sie die Struktur der Abfrage auf Fehler. Anleitungen finden Sie in der [Kusto-Dokumentation](https://docs.microsoft.com/azure/data-explorer/kusto/query/) . Verwenden Sie beim Schreiben Ihrer Abfragen die AutoVervollständigen-Vorschläge von IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Eine Abfrage kann nur innerhalb eines [begrenzten Zeitraums ausgeführt werden, bevor ein Timeout](advanced-hunting-limits.md)auftritt. Dieser Fehler kann häufiger auftreten, wenn komplexe Abfragen ausgeführt werden. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-Drosselung | Abfragen in demselben Mandanten haben die [CPU-Ressourcen](advanced-hunting-limits.md) überschritten, die basierend auf der Mandanten Größe zugewiesen wurden. | Der Dienst überprüft die CPU-Ressourcenauslastung alle 15 Minuten und täglich und zeigt Warnungen an, wenn die Verwendung 10% des zugewiesenen Grenzwerts überschreitet. Wenn Sie 100% Auslastung erreichen, blockiert der Dienst Abfragen bis nach dem nächsten täglichen oder 15-minütigen Zyklus. [Optimieren der Abfragen, um die CPU-Grenzwerte zu vermeiden](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Grenzwert für Ergebnisgröße überschritten  | Die Aggregatgröße des Resultsets für die Abfrage hat den maximalen Grenzwert überschritten. Dieser Fehler kann auftreten, wenn das Resultset so groß ist, dass das Abschneiden am Grenzwert von 10.000-Datensätzen ihn nicht auf eine akzeptable Größe reduzieren kann. Ergebnisse, die mehrere Spalten mit beträchtlichem Inhalt aufweisen, werden durch diesen Fehler eher beeinträchtigt. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Übermäßiger Ressourcenverbrauch | Die Abfrage hat übermäßige Ressourcenmengen verbraucht und wurde nicht mehr abgeschlossen. In einigen Fällen identifiziert Advanced Hunting den bestimmten Operator, der nicht optimiert wurde. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Unbekannte Fehler | Die Abfrage ist aufgrund eines unbekannten Grundes fehlgeschlagen. | Versuchen Sie erneut, die Abfrage auszuführen. Wenden Sie sich an Microsoft über das Portal, wenn Abfragen weiterhin unbekannte Fehler zurückgeben. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Verwandte Themen
- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Diensteinschränkungen](advanced-hunting-limits.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Kusto-Abfragesprache (Übersicht)](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
