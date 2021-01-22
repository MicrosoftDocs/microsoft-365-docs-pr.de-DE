---
title: Behandeln von Fehlern bei der erweiterten Suche nach Microsoft 365 Defender
description: Verstehen von Fehlern, die bei verwendung der erweiterten Suche angezeigt werden
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schema, Kusto, Timeout, Ressourcen, Fehler, unbekannter Fehler, Grenzwerte, Kontingent, Parameter, Zuordnung
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929646"
---
# <a name="handle-advanced-hunting-errors"></a>Behandeln von Fehlern bei der erweiterten Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Bei der erweiterten Suche werden Fehler angezeigt, die bei Syntaxfehlern benachrichtigt werden sollen, und wenn Abfragen vordefinierte [Kontingente und Verwendungsparameter erreichen.](advanced-hunting-limits.md) In der folgenden Tabelle finden Sie Tipps zum Beheben oder Vermeiden von Fehlern.

| Fehlertyp | Ursache | Lösung | Beispiele für Fehlermeldungen |
|--|--|--|--|
| Syntaxfehler | Die Abfrage enthält unbekannte Namen, einschließlich Verweise auf nicht vorhandene Operatoren, Spalten, Funktionen oder Tabellen. | Stellen Sie sicher, dass Verweise auf [die Operatoren und Funktionen von Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) korrekt sind. Überprüfen [Sie das Schema](advanced-hunting-schema-tables.md) auf die richtigen Spalten, Funktionen und Tabellen für die erweiterte Suche. Schließen Sie variable Zeichenfolgen in Anführungszeichen ein, damit sie erkannt werden. Verwenden Sie beim Schreiben von Abfragen die Vorschläge zum automatischen Kompletieren IntelliSense. | `A recognition error occurred.` |
| Semantische Fehler | Während die Abfrage gültige Operator-, Spalten-, Funktions- oder Tabellennamen verwendet, gibt es Fehler in der Struktur und der resultierenden Logik. In einigen Fällen identifiziert die erweiterte Suche den spezifischen Operator, der den Fehler verursacht hat. | Überprüfen Sie auf Fehler in der Abfragestruktur. Anleitungen [finden Sie in der Kusto-Dokumentation.](https://docs.microsoft.com/azure/data-explorer/kusto/query/) Verwenden Sie beim Schreiben von Abfragen die Vorschläge zum automatischen Kompletieren IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Eine Abfrage kann nur innerhalb eines [begrenzten Zeitraums ausgeführt werden, bevor ein Timeout angezeigt wird.](advanced-hunting-limits.md) Dieser Fehler kann häufiger auftreten, wenn komplexe Abfragen ausgeführt werden. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-Drosselung | Abfragen im gleichen Mandanten haben [](advanced-hunting-limits.md) die CPU-Ressourcen überschritten, die basierend auf der Mandantengröße zugewiesen wurden. | Der Dienst überprüft die Auslastung der CPU-Ressource alle 15 Minuten und täglich und zeigt Warnungen an, wenn die Nutzung 10 % des zugewiesenen Kontingents überschreitet. Wenn Sie eine Auslastung von 100 % erreichen, blockiert der Dienst Abfragen bis nach dem nächsten täglichen oder 15-minütigen Zyklus. [Optimieren Sie Ihre Abfragen, um das Erreichen von CPU-Kontingenten zu vermeiden.](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Grenzwert für Ergebnisgröße überschritten  | Die Aggregatgröße des Ergebnissets für die Abfrage hat die maximale Größe überschritten. Dieser Fehler kann auftreten, wenn das Ergebnisset so groß ist, dass das Abschneiden an der Grenze von 10.000 Datensatz nicht auf eine akzeptable Größe reduziert werden kann. Ergebnisse mit mehreren Spalten mit anpassbarem Inhalt sind wahrscheinlicher von diesem Fehler betroffen. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Übermäßiger Ressourcenverbrauch | Die Abfrage hat übermäßig viele Ressourcen verbraucht und wurde beendet. In einigen Fällen identifiziert die erweiterte Suche den spezifischen Operator, der nicht optimiert wurde. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Unbekannte Fehler | Die Abfrage ist aus unbekanntem Grund fehlgeschlagen. | Führen Sie die Abfrage erneut aus. Wenden Sie sich über das Portal an Microsoft, wenn bei Abfragen weiterhin unbekannte Fehler angezeigt werden. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Verwandte Themen
- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Kontingente und Verwendungsparameter](advanced-hunting-limits.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Übersicht über die Kusto-Abfragesprache](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
