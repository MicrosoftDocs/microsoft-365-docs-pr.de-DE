---
title: Erlernen der Abfragesprache für die erweiterte Suche in Microsoft Threat Protection
description: Erstellen Sie Ihre erste Suchabfrage für Bedrohungen, und erfahren Sie mehr über die allgemeinen Operatoren und andere Aspekte der Abfragesprache für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Sprache, lernen, erste Abfrage, Telemetrie, Ereignisse, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Operatoren, Datentypen, PowerShell-Download, Abfragebeispiel
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
ms.openlocfilehash: 15e298edfad2d04079322a070615a36bb5df64ad
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797852"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Erlernen der Abfragesprache für die erweiterte Suche

**Gilt für:**
- Microsoft Threat Protection

Die erweiterte Suche basiert auf der [Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/). Sie können die Kusto-Syntax und -Operatoren verwenden, um Abfragen zu erstellen, die Informationen im [Schema](advanced-hunting-schema-tables.md) suchen, die speziell für die erweiterte Suche strukturiert sind. Wenn Sie diese Konzepte besser verstehen möchten, führen Sie Ihre erste Abfrage aus.

## <a name="try-your-first-query"></a>Testen Ihrer ersten Abfrage

Wechseln Sie im Microsoft 365 Security Center zu **Hunting** , um die erste Abfrage auszuführen. Verwenden Sie das folgende Beispiel:

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

So sieht es in der erweiterten Suche aus.

![Bild der erweiterten Jagd Abfrage von Microsoft Threat Protection](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Beschreiben der Abfrage und angeben der zu durchsuchenden Tabellen
Ein kurzer Kommentar zum Anfang der Abfrage wurde hinzugefügt, um zu beschreiben, wofür er verwendet wird. Dies hilft, wenn Sie später entscheiden, die Abfrage zu speichern und für andere Personen in Ihrer Organisation freizugeben. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Die Abfrage selbst beginnt in der Regel mit einem Tabellennamen gefolgt von einer Reihe von Elementen, die mit einer Pipe (`|`) beginnen. In diesem Beispiel beginnen wir mit dem Erstellen einer Vereinigung von zwei Tabellen und fügen bei Bedarf weitergeleitete  `DeviceProcessEvents` `DeviceNetworkEvents` Elemente hinzu.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Festlegen des Zeitbereichs
Das erste piped-Element ist ein Zeitfilter, der auf die vorherigen sieben Tage beschränkt ist. Wenn Sie den Zeitabschnitt so eng wie möglich lassen, wird sichergestellt, dass Abfragen gut ausgeführt werden, überschaubare Ergebnisse zurückgeben und keine Zeitüberschreitungen auftreten.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Überprüfen bestimmter Prozesse
Auf den Zeitbereich folgt unmittelbar eine Suche nach Prozess Dateinamen, die die PowerShell-Anwendung darstellen.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Suchen nach bestimmten Befehlszeichenfolgen
Anschließend sucht die Abfrage nach Zeichenfolgen in Befehlszeilen, die in der Regel zum Herunterladen von Dateien mithilfe von PowerShell verwendet werden.

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

### <a name="customize-result-columns-and-length"></a>Anpassen von Ergebnisspalten und-Länge 
Da die Abfrage nun die zu suchenden Daten eindeutig identifiziert, können Sie Elemente hinzufügen, die definieren, wie die Ergebnisse aussehen. `project` gibt bestimmte Spalten zurück und `top` schränkt die Anzahl der Ergebnisse ein. Diese Operatoren tragen dazu bei, dass die Ergebnisse gut formatiert und relativ umfangreich und einfach zu verarbeiten sind.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Klicken Sie auf **Abfrage ausführen** aus, um die Ergebnisse anzuzeigen. Wählen Sie das Erweiterungssymbol oben rechts im Abfrage-Editor aus, um sich auf Ihre Jagd Abfrage und die Ergebnisse zu konzentrieren. 

![Bild des Expand-Steuerelements im Editor für erweiterte Jagd Abfragen](../../media/advanced-hunting-expand.png)

>[!TIP]
>Sie können Abfrageergebnisse als Diagramme anzeigen und Filter schnell anpassen. [Informationen zum Arbeiten mit Abfrageergebnissen finden Sie](advanced-hunting-query-results.md) unter Anleitung.

## <a name="learn-common-query-operators"></a>Erlernen allgemeiner Abfrageoperatoren

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

## <a name="understand-data-types"></a>Grundlegendes zu Datentypen

Daten in erweiterten Suchtabellen werden in der Regel in die folgenden Datentypen unterteilt.

| Datentyp | Beschreibung und Auswirkungen der Abfrage |
|--|--|
| `datetime` | Daten- und Zeitinformationen, die in der Regel Ereigniszeitstempel darstellen |
| `string` | Zeichenfolge |
| `bool` | „True“ oder „False“ |
| `int` | Ein numerischer 32-Bit-Wert.  |
| `long` | Ein numerischer 64-Bit-Wert. |

Weitere Informationen zu diesen Datentypen und deren Auswirkungen finden [Sie unter Kusto Scalar Data Types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Hilfe beim Schreiben von Abfragen
Nutzen Sie die folgenden Funktionen, um Abfragen schneller zu schreiben:
- **AutoSuggest** – beim Schreiben von Abfragen stellt Advanced Hunting Vorschläge von IntelliSense zur Verfügung. 
- **Schemastruktur** : eine Schemadarstellung, die die Liste der Tabellen und deren Spalten enthält, wird neben dem Arbeitsbereich bereitgestellt. Wenn Sie weitere Informationen erhalten möchten, zeigen Sie mit dem Mauszeiger auf ein Element. Doppelklicken Sie auf ein Element, um es im Abfrage-Editor einzufügen.
- **[Schema Referenz](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** – in-Portal-Referenz mit Tabellen-und Spaltenbeschreibungen sowie unterstützten Ereignistypen ( `ActionType` Werte) und Beispielabfragen

## <a name="work-with-multiple-queries-in-the-editor"></a>Arbeiten mit mehreren Abfragen im Editor
Der Abfrage-Editor kann als Scratch Pad für das Experimentieren mit mehreren Abfragen dienen. So verwenden Sie mehrere Abfragen:

- Trennen Sie jede Abfrage durch eine leere Textreihe.
- Platzieren Sie den Cursor auf einem beliebigen Teil einer Abfrage, um diese Abfrage vor dem Ausführen auszuwählen. Dadurch wird nur die ausgewählte Abfrage ausgeführt. Wenn Sie eine andere Abfrage ausführen möchten, bewegen Sie den Cursor entsprechend, und wählen Sie **Abfrage ausführen**aus.

![Bild des Abfrage-Editors mit mehreren Abfragen](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Verwenden von Beispielabfragen

Der Abschnitt **Erste Schritte** bietet einige einfache Abfragen mit häufig verwendeten Operatoren. Versuchen Sie, diese Abfragen auszuführen und kleine Änderungen daran vorzunehmen.

![Abbildung eines erweiterten Suchfensters](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Abgesehen von den einfachen Abfragebeispielen können Sie auch auf [freigegebene Abfragen](advanced-hunting-shared-queries.md) für bestimmte Szenarien zur Bedrohungssuche zugreifen. Erkunden Sie die freigegebenen Abfragen auf der linken Seite oder das GitHub-Abfragerepository.

## <a name="access-query-language-documentation"></a>Zugreifen auf die Dokumentation zur Abfragesprache

Weitere Informationen zur Kusto-Abfragesprache und zu unterstützten Operatoren finden Sie unter [Dokumentation zur Kusto-Abfragesprache](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
