---
title: Arbeiten mit erweiterten Suchabfrageergebnissen in Microsoft 365 Defender
description: Nutzen der Abfrageergebnisse, die von der erweiterten Suche in Microsoft 365 Defender zurückgegeben werden
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, Visualisierung, Diagramm, Filter, Drilldown
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dd25d021d04dc5e8a831e327fedb16d28e32b32a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068271"
---
# <a name="work-with-advanced-hunting-query-results"></a>Arbeiten mit erweiterten Suchabfrageergebnissen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Während Sie Ihre [](advanced-hunting-overview.md) erweiterten Suchabfragen erstellen können, um sehr genaue Informationen zurück zu geben, können Sie auch mit den Abfrageergebnissen arbeiten, um weitere Einblicke zu erhalten und bestimmte Aktivitäten und Indikatoren zu untersuchen. Sie können die folgenden Aktionen für Die Abfrageergebnisse ausführen:

- Anzeigen von Ergebnissen als Tabelle oder Diagramm
- Exportieren von Tabellen und Diagrammen
- Drilldown zu detaillierten Entitätsinformationen
- Optimieren Sie Ihre Abfragen direkt aus den Ergebnissen, oder wenden Sie Filter an.

## <a name="view-query-results-as-a-table-or-chart"></a>Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm
Standardmäßig zeigt die erweiterte Suche Abfrageergebnisse als tabellarische Daten an. Sie können auch die gleichen Daten wie ein Diagramm anzeigen. Die erweiterte Suche unterstützt die folgenden Ansichten:

| Ansichtstyp | Beschreibung |
| -- | -- |
| **Table** | Zeigt die Abfrageergebnisse im tabellarischen Format an |
| **Säulendiagramm** | Rendert eine Reihe eindeutiger Elemente auf der X-Achse als vertikale Balken, deren Höhen numerische Werte aus einem anderen Feld darstellen |
| **Gestapelte Säulendiagramm** | Rendert eine Reihe eindeutiger Elemente auf der X-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen |
| **Kreisdiagramm** | Rendert Abschnitts-Kreise, die eindeutige Elemente darstellen. Die Größe der einzelnen Kreise stellt numerische Werte aus einem anderen Feld dar. |
| **Donut-Diagramm** | Rendert Abschnittsbögen, die eindeutige Elemente darstellen. Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar. |
| **Liniendiagramm** | Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und verbindet die plotten Werte. |
| **Punktdiagramm** | Zeichnet numerische Werte für eine Reihe eindeutiger Elemente |
| **Flächendiagramm** | Zeichnet numerische Werte für eine Reihe eindeutiger Elemente und füllt die Abschnitte unterhalb der dargestellten Werte aus. |

### <a name="construct-queries-for-effective-charts"></a>Erstellen von Abfragen für effektive Diagramme
Beim Rendern von Diagrammen identifiziert die erweiterte Suche automatisch die von Interesse interessierten Spalten und die numerischen Werte, die aggregiert werden sollen. Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurück zu geben, die visualisiert angezeigt werden möchten. Hier sind einige Beispielabfragen und die resultierenden Diagramme.

#### <a name="alerts-by-severity"></a>Warnungen nach Schweregrad
Verwenden Sie den Operator, um eine numerische Anzahl der Werte zu `summarize` erhalten, die Sie diagrammen möchten. Die folgende Abfrage verwendet den Operator, um die Anzahl der Warnungen nach `summarize` Schweregrad zu erhalten.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Beim Rendern der Ergebnisse zeigt ein Spaltendiagramm jeden Schweregrad als separate Spalte an:

![Abbildung der erweiterten Suchabfrageergebnisse, die als Spaltendiagramm angezeigt werden Abfrageergebnisse für Warnungen nach Schweregrad, die ](../../media/advanced-hunting-column-chart.jpg)
 *als Spaltendiagramm angezeigt werden*

#### <a name="alert-severity-by-operating-system"></a>Warnungsschweregrad nach Betriebssystem
Sie können den Operator auch `summarize` verwenden, um Ergebnisse für die Diagrammwerte aus mehreren Feldern vorzubereiten. Sie sollten beispielsweise wissen, wie Warnungsschweregrade auf betriebssystemübergreifend verteilt werden. 

Die folgende Abfrage verwendet einen Operator, um Betriebssysteminformationen aus der Tabelle zu ziehen, und verwendet dann die Anzahl von Werten in den Spalten und `join` `DeviceInfo` in den `summarize` `OSPlatform` `Severity` Spalten:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Diese Ergebnisse werden am besten mithilfe eines gestapelten Säulendiagramms visualisiert:

![Abbildung der erweiterten Suchabfrageergebnisse, die als gestapelte Diagrammabfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad angezeigt werden, die als ](../../media/advanced-hunting-stacked-chart.jpg)
 *gestapeltes Diagramm angezeigt werden*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-E-Mails in den top 10 Absenderdomänen
Wenn Sie es mit einer Liste von Werten zu tun haben, die nicht endlich ist, können Sie den Operator verwenden, um nur die Werte mit den meisten `Top` Instanzen zu diagrammieren. Um beispielsweise die zehn häufigsten Absenderdomänen mit den meisten Phishing-E-Mails zu erhalten, verwenden Sie die folgende Abfrage:

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
Verwenden Sie die Kreisdiagrammansicht, um die Verteilung über die obersten Domänen effektiv zu zeigen:

![Abbildung der erweiterten Suchabfrageergebnisse, die als Kreisdiagramm angezeigt werden Kreisdiagramm, das die Verteilung von Phishing-E-Mails ](../../media/advanced-hunting-pie-chart.jpg)
 *auf die Domänen mit den meisten Absendern zeigt*

#### <a name="file-activities-over-time"></a>Dateiaktivitäten im Laufe der Zeit
Mithilfe des Operators mit der Funktion können Sie im Laufe der Zeit nach Ereignissen mit `summarize` `bin()` einem bestimmten Indikator suchen. Die folgende Abfrage zählt Ereignisse, die die Datei in Intervallen von 30 Minuten enthalten, um Spitzen der Aktivität im Zusammenhang mit `invoice.doc` dieser Datei zu zeigen:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
Das folgende Liniendiagramm zeigt deutlich Zeiträume mit mehr Aktivität `invoice.doc` an: 

![Abbildung erweiterter Suchabfrageergebnisse, die als Liniendiagramm angezeigt werden Liniendiagramm mit der Anzahl der Ereignisse, die eine Datei im Laufe der ](../../media/advanced-hunting-line-chart.jpg)
 *Zeit enthalten*


## <a name="export-tables-and-charts"></a>Exportieren von Tabellen und Diagrammen
Wählen Sie nach dem Ausführen einer Abfrage **Exportieren** aus, um die Ergebnisse in der lokalen Datei zu speichern. Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:

- **Tabellenansicht** – Die Abfrageergebnisse werden in tabellarischer Form als Microsoft Excel-Arbeitsmappe exportiert.
- **Jedes Diagramm** – die Abfrageergebnisse werden als JPEG-Bild des gerenderten Diagramms exportiert.

## <a name="drill-down-from-query-results"></a>Drilldown aus Abfrageergebnissen
Um einen Datensatz in den Abfrageergebnissen schnell zu überprüfen, wählen Sie die entsprechende Zeile aus, um den **Datensatzbereich** überprüfen zu öffnen. Der Bereich stellt die folgenden Informationen basierend auf dem ausgewählten Datensatz zur Verfügung:

- **Assets** – zusammengefasste Ansicht der wichtigsten Objekte (Postfächer, Geräte und Benutzer), die in dem Datensatz enthalten sind, bereichert mit verfügbaren Informationen, z. B. Risiko- und Risikostufen
- **Prozessstruktur** – für Datensätze mit Prozessinformationen generiert und mithilfe verfügbarer Kontextinformationen bereichert; Im Allgemeinen können Abfragen, die mehr Spalten zurückgeben, zu reichhaltigeren Prozessstrukturen führen.
- **Alle Details** – alle Werte aus den Spalten im Datensatz  

![Bild des ausgewählten Datensatzes mit Bereich zum Überprüfen des Datensatzes](../../media/mtp-ah/inspect-record.png)

Wenn Sie weitere Informationen zu einer bestimmten Entität in Den Abfrageergebnissen anzeigen möchten, z. B. einen Computer, eine Datei, einen Benutzer, eine IP-Adresse oder eine URL, wählen Sie die Entitäts-ID aus, um eine detaillierte Profilseite für diese Entität zu öffnen.

## <a name="tweak-your-queries-from-the-results"></a>Optimieren von Abfragen aus den Ergebnissen
Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern. Sie können die folgenden Optionen für Folgendes verwenden:

- Explizites Suchen nach dem ausgewählten Wert (`==`)
- Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)
- Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with` 

![Abbildung des erweiterten Ergebnissets für die Suche](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtern der Abfrageergebnisse
Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets. Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.

Verfeinern Sie Ihre Abfrage, indem Sie die Schaltflächen oder für die Werte auswählen, die Sie ein- oder ausschließen möchten, und wählen Sie `+` `-` dann Abfrage ausführen **aus.**

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
