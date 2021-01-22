---
title: Arbeiten mit Abfrageergebnissen für die erweiterte Suche in Microsoft 365 Defender
description: Nutzen der von der erweiterten Suche zurückgegebenen Abfrageergebnisse in Microsoft 365 Defender
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, Visualisierung, Diagramm, Filter, Drilldown
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932322"
---
# <a name="work-with-advanced-hunting-query-results"></a>Arbeiten mit Abfrageergebnissen für die erweiterte Suche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Während Sie Ihre [](advanced-hunting-overview.md) erweiterten Suchabfragen so erstellen können, dass sehr genaue Informationen zurückgegeben werden, können Sie auch mit den Abfrageergebnissen arbeiten, um weitere Einblicke zu erhalten und bestimmte Aktivitäten und Indikatoren zu untersuchen. Sie können die folgenden Aktionen für Die Abfrageergebnisse ausführen:

- Anzeigen von Ergebnissen als Tabelle oder Diagramm
- Exportieren von Tabellen und Diagrammen
- Drilldown zu detaillierten Entitätsinformationen
- Optimieren Sie Ihre Abfragen direkt aus den Ergebnissen, oder wenden Sie Filter an.

## <a name="view-query-results-as-a-table-or-chart"></a>Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm
Bei der erweiterten Suche werden Abfrageergebnisse standardmäßig als tabellarische Daten angezeigt. Sie können auch die gleichen Daten wie ein Diagramm anzeigen. Die erweiterte Suche unterstützt die folgenden Ansichten:

| Ansichtstyp | Beschreibung |
| -- | -- |
| **Table** | Zeigt die Abfrageergebnisse im tabellarischen Format an. |
| **Säulendiagramm** | Rendert eine Reihe eindeutiger Elemente auf der X-Achse als vertikale Balken, deren Höhen numerische Werte aus einem anderen Feld darstellen |
| **Gestapelte Säulendiagramm** | Rendert eine Reihe eindeutiger Elemente auf der X-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen |
| **Kreisdiagramm** | Rendert Abschnitts kreisdiagramme, die eindeutige Elemente darstellen. Die Größe jedes Kreises stellt numerische Werte aus einem anderen Feld dar. |
| **Donut (Diagramm)** | Rendert Abschnittsbögen, die eindeutige Elemente darstellen. Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar. |
| **Liniendiagramm** | Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und verbindet die zeichnungsierten Werte. |
| **Punkt (Punkt)-Diagramm** | Zeichnet numerische Werte für eine Reihe eindeutiger Elemente |
| **Flächendiagramm** | Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und füllt die Abschnitte unterhalb der dargestellten Werte. |

### <a name="construct-queries-for-effective-charts"></a>Erstellen von Abfragen für effektive Diagramme
Beim Rendern von Diagrammen werden bei der erweiterten Suche automatisch die für sie interessantsten Spalten und die zu aggregierenden numerischen Werte identifiziert. Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurück, die Sie visualisieren möchten. Hier sind einige Beispielabfragen und die resultierenden Diagramme.

#### <a name="alerts-by-severity"></a>Warnungen nach Schweregrad
Verwenden Sie den Operator, um eine numerische Anzahl der Werte zu `summarize` erhalten, die Sie diagrammen möchten. Die folgende Abfrage verwendet den Operator, um die Anzahl der Warnungen nach `summarize` Schweregrad zu erhalten.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Beim Rendern der Ergebnisse zeigt ein Säulendiagramm jeden Schweregradwert als separate Spalte an:

![Abbildung der Abfrageergebnisse der erweiterten Suche, die als Spaltendiagramm angezeigt werden. Abfrageergebnisse für Warnungen nach Schweregrad, ](../../media/advanced-hunting-column-chart.jpg)
 *angezeigt als Säulendiagramm*

#### <a name="alert-severity-by-operating-system"></a>Warnungsschweregrad nach Betriebssystem
Sie können den Operator auch `summarize` verwenden, um Ergebnisse für die Diagrammwerte aus mehreren Feldern vorzubereiten. Sie sollten beispielsweise wissen, wie Warnungsschweregrade auf alle Betriebssysteme verteilt sind. 

Die folgende Abfrage verwendet einen Operator, um Betriebssysteminformationen aus der Tabelle zu ziehen, und verwendet dann die Anzahl der Werte in der Tabelle und `join` `DeviceInfo` den `summarize` `OSPlatform` `Severity` Spalten:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Diese Ergebnisse werden am besten mithilfe eines gestapelten Säulendiagramms visualisiert:

![Abbildung der Abfrageergebnisse der erweiterten Suche, die als gestapelte Diagramm angezeigt werden Abfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad, die als ](../../media/advanced-hunting-stacked-chart.jpg)
 *gestapeltes Diagramm angezeigt werden*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-E-Mails in den Top-Ten-Absenderdomänen
Wenn Es sich um eine Liste von Werten handelt, die nicht begrenzt ist, können Sie den Operator verwenden, um nur die Werte mit den meisten `Top` Instanzen zu diagrammieren. Um beispielsweise die zehn häufigsten Absenderdomänen mit den meisten Phishing-E-Mails zu erhalten, verwenden Sie die folgende Abfrage:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Verwenden Sie die Kreisdiagrammansicht, um die Verteilung in den top-Domänen effektiv zu zeigen:

![Abbildung der Abfrageergebnisse der erweiterten Suche, angezeigt als Kreisdiagramm Kreisdiagramm, das die Verteilung von Phishing-E-Mails über die Domänen ](../../media/advanced-hunting-pie-chart.jpg)
 *der obersten Absender hinweg zeigt*

#### <a name="file-activities-over-time"></a>Dateiaktivitäten im Laufe der Zeit
Wenn Sie den Operator mit der Funktion verwenden, können Sie im Laufe der Zeit nach Ereignissen mit einem `summarize` `bin()` bestimmten Indikator suchen. Die folgende Abfrage zählt Ereignisse, an denen die Datei beteiligt ist, in Intervallen von 30 Minuten, um Aktivitätsspitzen im Zusammenhang mit `invoice.doc` dieser Datei zu zeigen:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
Das folgende Liniendiagramm zeigt deutlich Zeiträume mit einer stärkeren Aktivität `invoice.doc` an: 

![Abbildung der Abfrageergebnisse der erweiterten Suche, die als Liniendiagramm angezeigt werden, das die Anzahl der Ereignisse mit einer Datei im Laufe der ](../../media/advanced-hunting-line-chart.jpg)
 *Zeit zeigt*


## <a name="export-tables-and-charts"></a>Exportieren von Tabellen und Diagrammen
Wählen Sie nach dem Ausführen einer Abfrage **"Exportieren"** aus, um die Ergebnisse in der lokalen Datei zu speichern. Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:

- **Tabellenansicht** – Die Abfrageergebnisse werden in tabellarischer Form als Microsoft Excel-Arbeitsmappe exportiert.
- **Jedes Diagramm** – die Abfrageergebnisse werden als ein JPEG-Bild des gerenderten Diagramms exportiert.

## <a name="drill-down-from-query-results"></a>Drilldown aus Abfrageergebnissen
Um einen Datensatz in den Abfrageergebnissen schnell zu überprüfen, wählen Sie die entsprechende Zeile aus, um den **Datensatzbereich "Überprüfen" zu** öffnen. Der Bereich enthält die folgenden Informationen basierend auf dem ausgewählten Datensatz:

- **Ressourcen** – zusammengefasste Ansicht der wichtigsten Objekte (Postfächer, Geräte und Benutzer), die in dem Datensatz enthalten sind, mit verfügbaren Informationen, z. B. Risiko- und Risikostufen
- **Prozessstruktur –** für Datensätze mit Prozessinformationen generiert und mithilfe verfügbarer kontextbezogener Informationen bereichert; Im Allgemeinen können Abfragen, die mehr Spalten zurückgeben, zu reichhaltigeren Prozessstrukturen führen.
- **Alle Details** – alle Werte aus den Spalten im Datensatz  

![Abbildung des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/inspect-record.png)

Wenn Sie weitere Informationen zu einer bestimmten Entität in Den Abfrageergebnissen anzeigen möchten, z. B. einen Computer, eine Datei, einen Benutzer, eine IP-Adresse oder eine URL, wählen Sie den Entitätsbezeichner aus, um eine detaillierte Profilseite für diese Entität zu öffnen.

## <a name="tweak-your-queries-from-the-results"></a>Optimieren von Abfragen aus den Ergebnissen
Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern. Sie können die folgenden Optionen für Folgendes verwenden:

- Explizites Suchen nach dem ausgewählten Wert (`==`)
- Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)
- Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with` 

![Abbildung des Ergebnissets für die erweiterte Suche](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtern der Abfrageergebnisse
Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets. Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.

Verfeinern Sie Die Abfrage, indem Sie die Schaltflächen für die Werte auswählen, die Sie ein- oder ausschließen möchten, und dann `+` `-` abfrage ausführen **auswählen.**

![Abbildung eines erweiterten Suchfilters](../../media/advanced-hunting-filter.png)

Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suche über Geräte, E-Mails, Apps und Identitäten hinweg](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
