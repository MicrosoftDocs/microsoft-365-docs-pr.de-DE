---
title: Arbeiten mit erweiterten Jagd Abfrageergebnissen in Microsoft 365 Defender
description: Nutzen Sie die Abfrageergebnisse, die von Advanced Hunting in Microsoft 365 Defender zurückgegeben werden.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Microsoft Threat Protection, Visualisierung, Diagramm, Filter, Drilldown
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: de26989b9092b783a45d27ad2a529720d21169f8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844128"
---
# <a name="work-with-advanced-hunting-query-results"></a>Arbeiten mit erweiterten Jagd Abfrageergebnissen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Während Sie Ihre [erweiterten Jagd](advanced-hunting-overview.md) Abfragen erstellen können, um sehr genaue Informationen zurückzugeben, können Sie auch mit den Abfrageergebnissen zusammenarbeiten, um weitere Einblicke zu gewinnen und bestimmte Aktivitäten und Indikatoren zu untersuchen. Sie können die folgenden Aktionen für die Abfrageergebnisse ausführen:

- Anzeigen von Ergebnissen als Tabelle oder Diagramm
- Exportieren von Tabellen und Diagrammen
- Drilldown zu detaillierten Entitätsinformationen
- Optimieren der Abfragen direkt aus den Ergebnissen oder Anwenden von Filtern

## <a name="view-query-results-as-a-table-or-chart"></a>Anzeigen von Abfrageergebnissen als Tabelle oder Diagramm
Standardmäßig zeigt Advanced Hunting Abfrageergebnisse als tabellarische Daten an. Sie können auch dieselben Daten wie ein Diagramm anzeigen. Die erweiterte Suche unterstützt die folgenden Ansichten:

| Ansichtstyp | Beschreibung |
| -- | -- |
| **Table** | Zeigt die Abfrageergebnisse im tabellarischen Format an. |
| **Säulendiagramm** | Rendert eine Reihe von eindeutigen Elementen auf der x-Achse als vertikale Balken, deren Höhe numerische Werte aus einem anderen Feld darstellt. |
| **Gestapeltes Säulendiagramm** | Rendert eine Reihe von eindeutigen Elementen auf der x-Achse als gestapelte vertikale Balken, deren Höhen numerische Werte aus einem oder mehreren anderen Feldern darstellen. |
| **Kreisdiagramm** | Rendert Abschnitts Torten, die eindeutige Elemente darstellen. Die Größe jedes Kreises stellt numerische Werte aus einem anderen Feld dar. |
| **Donut-Diagramm** | Rendert Abschnitts Bögen, die eindeutige Elemente darstellen. Die Länge jedes Bogens stellt numerische Werte aus einem anderen Feld dar. |
| **Liniendiagramm** | Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen und verbindet die geplotteten Werte. |
| **Streudiagramm** | Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen. |
| **Flächendiagramm** | Zeichnet numerische Werte für eine Reihe von eindeutigen Elementen und füllt die Abschnitte unter den geplotteten Werten aus. |

### <a name="construct-queries-for-effective-charts"></a>Erstellen von Abfragen für effektive Diagramme
Beim Rendern von Diagrammen identifiziert die erweiterte Suche automatisch die relevanten Spalten und die zu aggregierenden numerischen Werte. Um aussagekräftige Diagramme zu erhalten, erstellen Sie Ihre Abfragen, um die spezifischen Werte zurückzugeben, die Sie visuell anzeigen möchten. Hier sind einige Beispielabfragen und die daraus resultierenden Diagramme.

#### <a name="alerts-by-severity"></a>Warnungen nach Schweregrad
Verwenden `summarize` Sie den-Operator, um eine numerische Anzahl der Werte zu erhalten, die Sie chartern möchten. In der folgenden Abfrage wird der `summarize` Operator verwendet, um die Anzahl der Warnungen nach Schweregrad abzurufen.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Beim Rendern der Ergebnisse zeigt ein Säulendiagramm jeden Schweregrad als separate Spalte an:

![Bild der erweiterten Jagd Abfrageergebnisse als Spalte Diagramm- ](../../media/advanced-hunting-column-chart.jpg)
 *Abfrageergebnisse für Warnungen nach Schweregrad angezeigt als Säulendiagramm*

#### <a name="alert-severity-by-operating-system"></a>Warnungsschweregrad nach Betriebssystem
Sie können auch den `summarize` -Operator verwenden, um Ergebnisse für Diagrammwerte aus mehreren Feldern vorzubereiten. Beispielsweise sollten Sie verstehen, wie Warnungs severities über Betriebssysteme verteilt werden (OS). 

In der folgenden Abfrage wird ein Operator verwendet, `join` um Betriebssysteminformationen aus der `DeviceInfo` Tabelle abzurufen, und verwendet dann `summarize` , um Werte in den `OSPlatform` Spalten und zu zählen `Severity` :

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Diese Ergebnisse werden am besten mit einem gestapelten Säulendiagramm visualisiert:

![Bild der erweiterten Suchabfrageergebnisse als gestapelte Diagramm ](../../media/advanced-hunting-stacked-chart.jpg)
 *Abfrageergebnisse für Warnungen nach Betriebssystem und Schweregrad angezeigt als gestapeltes Diagramm*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing-e-Mails in den oberen zehn Absenderdomänen
Wenn es sich um eine Liste von Werten handelt, die nicht endlich sind, können Sie den `Top` Operator verwenden, um nur die Werte mit den meisten Instanzen zu chartern. Um beispielsweise die oberen zehn Absenderdomänen mit den meisten Phishing-e-Mails zu erhalten, verwenden Sie die folgende Abfrage:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Verwenden Sie die Kreisdiagrammansicht, um die Verteilung in den oberen Domänen effektiv anzuzeigen:

![Bild der erweiterten Hunting-Abfrageergebnisse als Kreisdiagramm angezeigt, das eine ](../../media/advanced-hunting-pie-chart.jpg)
 *Verteilung von Phishing-e-Mails über die oberen Absenderdomänen hinweg zeigt*

#### <a name="file-activities-over-time"></a>Dateiaktivitäten im Laufe der Zeit
Mithilfe des `summarize` Operators mit der `bin()` -Funktion können Sie über einen bestimmten Zeitraum nach Ereignissen suchen, bei denen ein bestimmter Indikator angezeigt wird. In der folgenden Abfrage werden Ereignisse gezählt, bei denen die Datei `invoice.doc` in 30 Minuten Intervallen angezeigt wird, um Spikes in Aktivitäten im Zusammenhang mit dieser Datei anzuzeigen:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
Im folgenden Diagramm werden die Zeiträume mit mehr Aktivität deutlich hervorgehoben `invoice.doc` , darunter: 

![Bild der erweiterten Hunting-Abfrageergebnisse als ](../../media/advanced-hunting-line-chart.jpg)
 *Diagramm Diagramm mit der Anzahl der Ereignisse angezeigt, die mit einer Datei im Laufe der Zeit* in Verbindung stehen


## <a name="export-tables-and-charts"></a>Exportieren von Tabellen und Diagrammen
Wählen Sie nach dem Ausführen einer Abfrage **Export** aus, um die Ergebnisse in der lokalen Datei zu speichern. Die ausgewählte Ansicht bestimmt, wie die Ergebnisse exportiert werden:

- **Tabellenansicht** – die Abfrageergebnisse werden als Microsoft Excel Arbeitsmappe in tabellarischer Form exportiert.
- **Beliebiges Diagramm** – die Abfrageergebnisse werden als JPEG-Bild des gerenderten Diagramms exportiert.

## <a name="drill-down-from-query-results"></a>Drilldown von Abfrageergebnissen
Wenn Sie einen Datensatz in Ihren Abfrageergebnissen schnell überprüfen möchten, wählen Sie die entsprechende Zeile aus, um die Registerkarte " **Daten Satz prüfen** " zu öffnen. Der Bereich enthält die folgenden Informationen basierend auf dem ausgewählten Datensatz:

- **Objekte** – zusammengefasste Ansicht der Hauptobjekte (Postfächer, Geräte und Benutzer), die im Datensatz gefunden wurden, mit verfügbaren Informationen wie Risiko-und Expositions Stufen angereichert
- **Prozessstruktur** – wird für Datensätze mit Prozessinformationen generiert und mithilfe von verfügbaren Kontextinformationen erweitert; im Allgemeinen können Abfragen, die mehr Spalten zurückgeben, zu umfangreicheren Prozessstrukturen führen.
- **Alle Details** – alle Werte aus den Spalten im Datensatz  

![Bild des ausgewählten Datensatzes mit dem Bereich für die Überprüfung des Datensatzes](../../media/mtp-ah/inspect-record.png)

Wenn Sie weitere Informationen zu einer bestimmten Entität in Ihren Abfrageergebnissen anzeigen möchten, beispielsweise einen Computer, eine Datei, einen Benutzer, eine IP-Adresse oder eine URL, wählen Sie den Entitäts Bezeichner aus, um eine detaillierte Profilseite für diese Entität zu öffnen.

## <a name="tweak-your-queries-from-the-results"></a>Optimieren von Abfragen aus den Ergebnissen
Klicken Sie mit der rechten Maustaste auf einen Wert im Resultset, um die Abfrage schnell zu erweitern. Sie können die folgenden Optionen für Folgendes verwenden:

- Explizites Suchen nach dem ausgewählten Wert (`==`)
- Ausschließen des ausgewählten Werts aus der Abfrage (`!=`)
- Abrufen weiterer erweiterter Operatoren zum Hinzufügen des Werts zu Ihrer Abfrage, z. B. `contains`, `starts with` und `ends with` 

![Bild des erweiterten Jagd Ergebnissatzes](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtern der Abfrageergebnisse
Die rechts angezeigten Filter bieten eine Zusammenfassung des Resultsets. Jede Spalte verfügt über einen eigenen Abschnitt, in dem die für diese Spalte und die Anzahl der Instanzen eindeutigen Werte aufgelistet werden.

Verfeinern Sie die Abfrage, indem `+` `-` Sie die Schaltflächen oder für die Werte auswählen, die Sie einschließen oder ausschließen möchten, und wählen Sie dann **Abfrage ausführen** aus.

![Abbildung eines erweiterten Suchfilters](../../media/advanced-hunting-filter.png)

Sobald der Filter zum Ändern der Abfrage angewendet und die Abfrage ausgeführt wurde, werden die Ergebnisse entsprechend aktualisiert.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Suchen auf Geräten, in E-Mails, Apps und Identitäten](advanced-hunting-query-emails-devices.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)
- [Benutzerdefinierte Erkennungen – Übersicht](custom-detections-overview.md)
