---
title: Erlernen der Abfragesprache für die erweiterte Suche
description: Erstellen Sie Ihre erste Suchabfrage für Bedrohungen, und erfahren Sie mehr über die allgemeinen Operatoren und andere Aspekte der Abfragesprache für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, language, learn, first query, telemetry, events, telemetry, custom detections, schema, kusto, operators, data types
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: af612a051f133e4846e04033ab35ea39769d0193
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499544"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Erlernen der Abfragesprache für die erweiterte Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/). Sie können Kusto-Operatoren und -Anweisungen verwenden, um Abfragen zu erstellen, die Informationen in einem spezialisierten Schema [suchen.](advanced-hunting-schema-reference.md) Wenn Sie diese Konzepte besser verstehen möchten, führen Sie Ihre erste Abfrage aus.

## <a name="try-your-first-query"></a>Testen Ihrer ersten Abfrage

Wechseln Sie im Microsoft Defender Security Center zu **Erweiterte Suche,** um Ihre erste Abfrage ausführen. Verwenden Sie das folgende Beispiel:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```
**[Ausführen dieser Abfrage bei der erweiterten Suche](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Beschreiben der Abfrage und Angeben der zu durchsuchende Tabellen
Am Anfang der Abfrage wurde ein kurzer Kommentar hinzugefügt, um zu beschreiben, wofür er steht. Dieser Kommentar hilft Ihnen, wenn Sie später entscheiden, die Abfrage zu speichern und sie für andere Personen in Ihrer Organisation zu teilen.

```kusto
// Finds PowerShell execution events that could involve a download
```
Die Abfrage selbst beginnt in der Regel mit einem Tabellennamen gefolgt von mehreren Elementen, die mit einer Pipe beginnen ( `|` ). In diesem Beispiel erstellen wir zunächst eine Vereinigung von zwei Tabellen und und fügen bei Bedarf  `DeviceProcessEvents` `DeviceNetworkEvents` piped-Elemente hinzu.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Festlegen des Zeitbereichs
Das erste piped-Element ist ein Zeitfilter, der auf die vorherigen sieben Tage begrenzt ist. Durch die Begrenzung des Zeitbereichs können Sie sicherstellen, dass Abfragen gut ausgeführt werden, verwaltbare Ergebnisse zurückgeben und keine Zeit zu einem Zeitverlauf führen.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Überprüfen bestimmter Prozesse
Auf den Zeitraum folgt sofort eine Suche nach Prozessdateinamen, die die PowerShell-Anwendung darstellen.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Suchen nach bestimmten Befehlszeichenfolgen
Anschließend sucht die Abfrage nach Zeichenfolgen in Befehlszeilen, die normalerweise zum Herunterladen von Dateien mithilfe von PowerShell verwendet werden.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a>Anpassen von Ergebnisspalten und -längen 
Nachdem Ihre Abfrage nun die zu suchende Daten eindeutig identifiziert, können Sie definieren, wie die Ergebnisse aussehen. `project` gibt bestimmte Spalten zurück und `top` beschränkt die Anzahl der Ergebnisse. Diese Operatoren tragen dazu bei, sicherzustellen, dass die Ergebnisse gut formatiert und relativ groß und einfach zu verarbeiten sind.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Wählen **Sie Abfrage ausführen aus,** um die Ergebnisse zu sehen. Verwenden Sie das Erweiterungssymbol oben rechts im Abfrage-Editor, um sich auf Ihre Suchabfrage und die Ergebnisse zu konzentrieren. 

![Abbildung des Expand-Steuerelements im editor für erweiterte Suchabfragen](images/advanced-hunting-expand.png)

>[!TIP]
>Sie können Abfrageergebnisse als Diagramme anzeigen und Filter schnell anpassen. Informationen zum Arbeiten [mit Abfrageergebnissen](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Erlernen häufig verwendeter Operatoren für die erweiterte Suche

Sie haben gerade Ihre erste Abfrage ausgeführt und haben eine allgemeine Vorstellung von deren Komponenten. Es ist an der Zeit, ein wenig zurück zu fahren und einige Grundlagen zu erlernen. Die von der erweiterten Suche verwendete Kusto-Abfragesprache unterstützt eine Reihe von Operatoren, darunter die folgenden allgemeinen Operatoren.

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

Um ein Livebeispiel dieser Operatoren zu sehen, führen Sie sie im Abschnitt **Erste** Schritte auf der Seite erweiterte Suche aus.

## <a name="understand-data-types"></a>Verstehen von Datentypen

Die erweiterte Suche unterstützt Kusto-Datentypen, einschließlich der folgenden allgemeinen Typen:

| Datentyp | Beschreibung und Auswirkungen der Abfrage |
|--|--|
| `datetime` | Daten- und Zeitinformationen, die in der Regel Ereigniszeitstempel darstellen. [Siehe unterstützte Datums-/Uhrzeitformate](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Zeichenzeichenfolge in UTF-8, eingeschlossen in einfache Anführungszeichen ( `'` ) oder doppelte Anführungszeichen ( `"` ). [Weitere Informationen zu Zeichenfolgen](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Dieser Datentyp unterstützt `true` oder `false` zustände. [Siehe unterstützte Literale und Operatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32-Bit-Ganzzahl  |
| `long` | 64-Bit-Ganzzahl |

Weitere Informationen zu diesen Datentypen finden Sie [unter Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Hilfe beim Schreiben von Abfragen
Nutzen Sie die folgenden Funktionen, um Abfragen schneller zu schreiben:

- **Autouggest**– Beim Schreiben von Abfragen bietet die erweiterte Suche Vorschläge von IntelliSense.
- **Schemastruktur**– Eine Schemadarstellung, die die Liste der Tabellen und deren Spalten enthält, wird neben Ihrem Arbeitsbereich bereitgestellt. Wenn Sie weitere Informationen erhalten möchten, zeigen Sie mit dem Mauszeiger auf ein Element. Doppelklicken Sie auf ein Element, um es im Abfrage-Editor einzufügen.
- **[Schemareferenz](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**– In-Portal-Referenz mit Tabellen- und Spaltenbeschreibungen sowie unterstützten Ereignistypen ( `ActionType` Werte) und Beispielabfragen

## <a name="work-with-multiple-queries-in-the-editor"></a>Arbeiten mit mehreren Abfragen im Editor
Sie können den Abfrage-Editor verwenden, um mit mehreren Abfragen zu experimentieren. So verwenden Sie mehrere Abfragen:

- Trennen Sie jede Abfrage durch eine leere Zeile.
- Platzieren Sie den Cursor auf einem beliebigen Teil einer Abfrage, um diese Abfrage auszuwählen, bevor Sie sie ausführen. Dadurch wird nur die ausgewählte Abfrage ausgeführt. Wenn Sie eine andere Abfrage ausführen möchten, verschieben Sie den Cursor entsprechend, und wählen Sie **Abfrage ausführen aus.**

![Abbildung des erweiterten Abfrage-Editors für die Suche mit mehreren Abfragen ](images/ah-multi-query.png)
 _Abfrage-Editor mit mehreren Abfragen_

## <a name="use-sample-queries"></a>Verwenden von Beispielabfragen

Der Abschnitt **Erste Schritte** bietet einige einfache Abfragen mit häufig verwendeten Operatoren. Versuchen Sie, diese Abfragen auszuführen und kleine Änderungen daran vorzunehmen.

![Abbildung der Registerkarte "Erste Schritte bei der erweiterten Suche"](images/atp-advanced-hunting.png)

> [!NOTE]
> Abgesehen von den einfachen Abfragebeispielen können Sie auch auf [freigegebene Abfragen](advanced-hunting-shared-queries.md) für bestimmte Szenarien zur Bedrohungssuche zugreifen. Erkunden Sie die freigegebenen Abfragen auf der linken Seite der Seite oder im [GitHub-Abfragerepository](https://aka.ms/hunting-queries).

## <a name="access-comprehensive-query-language-reference"></a>Zugriff auf umfassende Abfragesprachenreferenz

Ausführliche Informationen zur Abfragesprache finden Sie unter [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-reference.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
