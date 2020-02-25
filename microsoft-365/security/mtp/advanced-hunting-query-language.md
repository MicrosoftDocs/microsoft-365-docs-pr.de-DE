---
title: Erlernen der Abfragesprache für die erweiterte Suche in Microsoft Threat Protection
description: Erstellen Sie Ihre erste Suchabfrage für Bedrohungen, und erfahren Sie mehr über die allgemeinen Operatoren und andere Aspekte der Abfragesprache für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Sprache, lernen, erste Abfrage, Telemetrie, Ereignisse, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Operatoren, Datentypen
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
ms.openlocfilehash: eda9b893057afd54a644f0091bf4e1b421bd5439
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234694"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Erlernen der Abfragesprache für die erweiterte Suche

**Gilt für:**
- Microsoft Threat Protection



Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/). Sie können die Kusto-Syntax und -Operatoren verwenden, um Abfragen zu erstellen, die Informationen im [Schema](advanced-hunting-schema-tables.md) suchen, die speziell für die erweiterte Suche strukturiert sind. Wenn Sie diese Konzepte besser verstehen möchten, führen Sie Ihre erste Abfrage aus.

## <a name="try-your-first-query"></a>Testen Ihrer ersten Abfrage

Wechseln Sie im Microsoft 365 Security Center zu **Hunting**, um Ihre erste Abfrage auszuführen. Verwenden Sie das folgende Beispiel:

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

So sieht es in der erweiterten Suche aus.

![Abbildung einer erweiterten Suchabfrage in Microsoft Defender ATP](../../media/advanced-hunting-query-example.png)

Die Abfrage beginnt mit einem kurzen Kommentar, der beschreibt, wofür die Abfrage dient. Dies ist hilfreich, wenn Sie sich später entscheiden, Ihre Abfrage zu speichern und sie für andere Personen in Ihrer Organisation freizugeben.

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

Die Abfrage selbst beginnt in der Regel mit einem Tabellennamen gefolgt von einer Reihe von Elementen, die mit einer Pipe (`|`) beginnen. In diesem Beispiel beginnen wir, indem wir den Tabellennamen `DeviceProcessEvents` und bei Bedarf weitere Pipe-Elemente hinzufügen.

Das erste Pipe-Element ist ein Zeitfilter, der in der letzten sieben Tagen festgelegt wurde. Wenn Sie den Zeitabschnitt so eng wie möglich lassen, wird sichergestellt, dass Abfragen gut ausgeführt werden, überschaubare Ergebnisse zurückgeben und keine Zeitüberschreitungen auftreten.

```kusto
| where Timestamp > ago(7d)
```

Auf den Zeitabschnitt folgt sofort eine Suche nach Dateien, die die PowerShell-Anwendung darstellen.

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

Anschließend sucht die Abfrage nach Befehlszeilen, die in der Regeln mit PowerShell verwendet werden, um Dateien herunterzuladen.

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

Da die Abfrage nun die zu suchenden Daten eindeutig identifiziert, können Sie Elemente hinzufügen, die definieren, wie die Ergebnisse aussehen. `project` gibt bestimmte Spalten zurück, und `top` schränkt die Anzahl der Ergebnisse ein, sodass die Ergebnisse sinnvoll formatiert sind, eine angemessene Größe aufweisen und einfach zu verarbeiten sind.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Klicken Sie auf **Abfrage ausführen** aus, um die Ergebnisse anzuzeigen. Sie können die Bildschirmansicht erweitern, damit Sie sich auf Ihre Suchabfrage und die Ergebnisse konzentrieren können.

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Erlernen häufig verwendeter Operatoren für die erweiterte Suche

Da Sie nun Ihre erste Abfrage ausgeführt und eine allgemeine Vorstellung von deren Komponenten haben, gehen wir einen Schritt zurück und befassen uns mit ein paar Grundlagen. Die von der erweiterten Suche verwendete Kusto-Abfragesprache unterstützt eine Reihe von Operatoren, darunter die folgenden allgemeinen Operatoren.

| Operator | Beschreibung und Verwendung |
|--|--|
| `where` | Filtern einer Tabelle auf die Teilmenge von Zeilen, die einem Prädikat entsprechen. |
| `summarize` | Erstellen einer Tabelle, in der die Inhalte der Eingabetabelle gesammelt werden. |
| `join` | Zusammenführen der Zeilen von zwei Tabellen, um eine neue Tabelle zu erstellen, indem Werte der angegebenen Spalten aus jeder Tabelle zugeordnet werden. |
| `count` | Zurückgeben der Anzahl von Datensätzen im Eingabedatensatz. |
| `top` | Zurückgeben der ersten n Einträge, sortiert anhand der angegebenen Spalten. |
| `limit` | Zurückkehren nach oben zur angegebenen Zeilenanzahl. |
| `project` | Auswählen der Spalten, um neue berechnete Spalten aufzunehmen, umzubenennen, zu löschen oder einzufügen. |
| `extend` | Erstellen von berechneten Spalten und Anfügen an das Resultset. |
| `makeset` |  Zurückgeben eines dynamischen (JSON)-Arrays der Gruppe eindeutiger Werte, die der Ausdruck in der Gruppe verwendet. |
| `find` | Suchen von Zeilen, die mit einem Prädikat über eine Reihe von Tabellen hinweg übereinstimmen. |

Wenn Sie ein Beispiel für diese Operatoren sehen möchten, führen Sie diese im Abschnitt **Erste Schritte** in der erweiterten Suche aus.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Grundlegendes zu Datentypen und deren Auswirkungen auf die Abfragesyntax

Daten in erweiterten Suchtabellen werden in der Regel in die folgenden Datentypen unterteilt.

| Datentyp | Beschreibung und Auswirkungen der Abfrage |
|--|--|
| `datetime` | Daten- und Zeitinformationen, die in der Regel Ereigniszeitstempel darstellen |
| `string` | Zeichenfolge |
| `bool` | „True“ oder „False“ |
| `int` | Ein numerischer 32-Bit-Wert.  |
| `long` | Ein numerischer 64-Bit-Wert. |

## <a name="use-sample-queries"></a>Verwenden von Beispielabfragen

Der Abschnitt **Erste Schritte** bietet einige einfache Abfragen mit häufig verwendeten Operatoren. Versuchen Sie, diese Abfragen auszuführen und kleine Änderungen daran vorzunehmen.

![Abbildung eines erweiterten Suchfensters](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Abgesehen von den einfachen Abfragebeispielen können Sie auch auf [freigegebene Abfragen](advanced-hunting-shared-queries.md) für bestimmte Szenarien zur Bedrohungssuche zugreifen. Erkunden Sie die freigegebenen Abfragen auf der linken Seite oder das GitHub-Abfragerepository.

## <a name="access-query-language-documentation"></a>Zugreifen auf die Dokumentation zur Abfragesprache

Weitere Informationen zur Kusto-Abfragesprache und zu unterstützten Operatoren finden Sie unter [Dokumentation zur Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Verwandte Themen
- [Vorbeugende Suche nach Bedrohungen](advanced-hunting-overview.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche nach Bedrohungen auf Geräten und in E-Mails](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
