---
title: Behandeln von Fehlern bei der erweiterten Suche für Microsoft 365 Defender
description: Verstehen von Fehlern, die bei der Verwendung der erweiterten Suche angezeigt werden
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, timeout, resources, errors, unknown error, limits, quota, parameter, allocation
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
ms.openlocfilehash: 23123b2ee96e1aa2b20499e66a180ba65832ba40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917116"
---
# <a name="handle-advanced-hunting-errors"></a>Behandeln von Fehlern bei der erweiterten Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Bei der erweiterten Suche werden Fehler angezeigt, die bei Syntaxfehlern angezeigt werden sollen, und immer dann, wenn Abfragen vordefinierte [Kontingente und Verwendungsparameter treffen.](advanced-hunting-limits.md) In der folgenden Tabelle finden Sie Tipps zum Beheben oder Vermeiden von Fehlern.

| Fehlertyp | Ursache | Lösung | Beispiele für Fehlermeldungen |
|--|--|--|--|
| Syntaxfehler | Die Abfrage enthält nicht unbekannte Namen, einschließlich Verweise auf nicht vorhandene Operatoren, Spalten, Funktionen oder Tabellen. | Stellen Sie sicher, dass Verweise auf [Kusto-Operatoren und -Funktionen](/azure/data-explorer/kusto/query/) korrekt sind. Überprüfen [Sie das Schema](advanced-hunting-schema-tables.md) auf die richtigen erweiterten Spalten, Funktionen und Tabellen. Schließen Sie variable Zeichenfolgen in Anführungszeichen ein, damit sie erkannt werden. Verwenden Sie beim Schreiben ihrer Abfragen die Vorschläge für die automatische IntelliSense. | `A recognition error occurred.` |
| Semantische Fehler | Während die Abfrage gültige Operator-, Spalten-, Funktions- oder Tabellennamen verwendet, gibt es Fehler in der Struktur und der resultierenden Logik. In einigen Fällen identifiziert die erweiterte Suche den spezifischen Operator, der den Fehler verursacht hat. | Suchen Sie nach Fehlern in der Abfragestruktur. Anleitungen [finden Sie in der Kusto-Dokumentation.](/azure/data-explorer/kusto/query/) Verwenden Sie beim Schreiben ihrer Abfragen die Vorschläge für die automatische IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Eine Abfrage kann nur innerhalb eines [begrenzten Zeitraums ausgeführt werden, bevor ein Timeout angezeigt wird.](advanced-hunting-limits.md) Dieser Fehler kann häufiger auftreten, wenn komplexe Abfragen ausgeführt werden. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU-Einschränkung | Abfragen im gleichen Mandanten haben die CPU-Ressourcen [überschritten,](advanced-hunting-limits.md) die basierend auf der Mandantengröße zugewiesen wurden. | Der Dienst überprüft die CPU-Ressourcennutzung alle 15 Minuten und täglich und zeigt Warnungen an, nachdem die Verwendung 10 % des zugewiesenen Kontingents überschreitet. Wenn Sie eine Auslastung von 100 % erreichen, blockiert der Dienst Abfragen bis nach dem nächsten täglichen Oder 15-Minuten-Zyklus. [Optimieren Sie Ihre Abfragen, um das Erreichen von CPU-Kontingenten zu vermeiden.](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Grenzwert für die Ergebnisgröße überschritten  | Die Aggregatgröße des Ergebnissets für die Abfrage hat die maximale Größe überschritten. Dieser Fehler kann auftreten, wenn das Ergebnisset so groß ist, dass das Abschneiden an der Grenze von 10.000 Datensatz nicht auf eine akzeptable Größe reduziert werden kann. Ergebnisse mit mehreren Spalten mit ansehnlichem Inhalt sind wahrscheinlicher von diesem Fehler betroffen. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Übermäßiger Ressourcenverbrauch | Die Abfrage hat zu viele Ressourcen verbraucht und wurde nicht mehr abgeschlossen. In einigen Fällen identifiziert die erweiterte Suche den bestimmten Operator, der nicht optimiert wurde. | [Optimieren der Abfrage](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Unbekannte Fehler | Die Abfrage ist aus einem unbekannten Grund fehlgeschlagen. | Führen Sie die Abfrage erneut aus. Wenden Sie sich über das Portal an Microsoft, wenn Abfragen weiterhin unbekannte Fehler zurückgeben. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Verwandte Themen
- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Kontingente und Verwendungsparameter](advanced-hunting-limits.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Kusto Query Language (Übersicht)](/azure/data-explorer/kusto/query/)