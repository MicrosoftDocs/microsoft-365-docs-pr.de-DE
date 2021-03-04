---
title: Advanced eDiscovery-Beschränkungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Fallgrenzwerte, Indizierungsgrenzwerte und Suchgrenzwerte, die für die Advanced eDiscovery-Lösung in Microsoft 365 gelten.
ms.openlocfilehash: 9b36407868a0f426b71a0a551d2f702d0a20b777
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423436"
---
# <a name="limits-in-advanced-ediscovery"></a>Grenzwerte in Advanced eDiscovery

In diesem Artikel werden die Grenzwerte in der Advanced eDiscovery-Lösung in Microsoft 365 beschrieben.

## <a name="case-and-review-set-limits"></a>Grenzwerte für Fall- und Prüfungssatz

In der folgenden Tabelle sind die Grenzwerte für Fälle und Überprüfungssätze in Advanced eDiscovery aufgeführt.

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Gesamtanzahl der Dokumente, die einem Fall hinzugefügt werden können (für alle Überprüfungssätze in einem Fall).  <br/> |3 Million <br/> |
|Gesamtdateigröße pro Ladesatz. Dies umfasst das Laden von Nicht-Office 365 in einen Überprüfungssatz.  <br/> |300 GB <br/> |
|Die Gesamtzahl der Daten, die pro Tag in alle Überprüfungssätze in der Organisation geladen werden.<br/> |2 TB <br/> |
|Maximale Anzahl von Lastensätzen pro Fall.  <br/> |200 <br/> |
|Maximale Anzahl von Überprüfungssätzen pro Fall.  <br/> |20 <br/> |
|Maximale Anzahl von Taggruppen pro Fall.  <br/> |1000 <br/> |
|Maximale Anzahl von Tags pro Fall.  <br/> |1000 <br/> |
|||

## <a name="hold-limits"></a>Haltebeschränkungen

In der folgenden Tabelle sind die Grenzwerte für Haltewerte aufgeführt, die einem Advanced eDiscovery-Fall zugeordnet sind.

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Maximale Anzahl von Postfächern in einem einzelnen Fall. Dieser Grenzwert umfasst die gesamtzahl der Benutzerpostfächer und die Postfächer, die Microsoft 365-Gruppen, Microsoft Teams und Yammer zugeordnet sind. <br/> |1.000  <br/> |
|Maximale Anzahl von Websites in einem einzigen Fall. Dieser Grenzwert umfasst die gesamtzahl der OneDrive for #A0 und #A1 sowie die Websites, die Microsoft 365-Gruppen, Microsoft Teams und Yammer zugeordnet sind.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Indizierungsgrenzwerte

In der folgenden Tabelle sind die Indizierungsgrenzwerte in Advanced eDiscovery aufgeführt.

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Maximale Anzahl von Zeichen, die aus einer einzelnen Datei extrahiert werden.  <br/> |10 Millionen<sup>1</sup> <br/> |
|Maximale Größe einer einzelnen Datei.   <br/> |100 MB<sup>1</sup> <br/> |
|Maximale Tiefe der eingebetteten Elemente in einem Dokument.  <br/> |25<sup>1</sup> <br/> |
|Maximale Größe von Dateien, die von der optischen Zeichenerkennung (Optical Character Recognition, OCR) verarbeitet werden.  <br/> |24 MB<sup>1</sup> <br/> 
|Maximale Anzahl von Indizierungsaufträgen pro Organisation pro Tag. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Suchgrenzen

Die in diesem Abschnitt beschriebenen Grenzwerte stehen im  Zusammenhang mit der Verwendung des Suchtools auf der Registerkarte Suchen, um Daten für einen Fall zu sammeln. Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall in Advanced eDiscovery](collecting-data-for-ediscovery.md).

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Maximale Anzahl von Postfächern oder Websites, die in einer einzigen Suche durchsucht werden können. |Keine Begrenzung|
|Maximale Anzahl von Suchen, die gleichzeitig ausgeführt werden können. |Keine Begrenzung |
|Maximale Anzahl von Suchen, die ein einzelner Benutzer gleichzeitig starten kann. |10   | 
|Maximale Anzahl von Zeichen für eine Suchabfrage (einschließlich Operatoren und Bedingungen). |10.000 &nbsp; <sup>2</sup>|
|Mindestanzahl von Alphazeichen für Präfix-Platzhalter; beispiel: **ein \* *_* oder \* _ set**.|3  |  
|Maximale Anzahl von Varianten, die zurückgegeben werden, wenn ein Präfix-Platzhalter verwendet wird, um nach einem exakten Ausdruck zu suchen, oder wenn ein Präfix-Platzhalter und der **NEAR** Boolean-Operator verwendet werden. |10.000 &nbsp; <sup>3</sup>|
|Maximale Anzahl von Elementen pro Benutzerpostfach, die auf der Vorschauseite für Suchen angezeigt werden. Die neuesten Elemente werden angezeigt. |100|
|Maximale Anzahl von Elementen aus allen Postfächern, die auf der Vorschauseite für Suchen angezeigt werden.|1.000|
|Maximale Anzahl von Postfächern, die für Suchergebnisse in der Vorschau angezeigt werden können.  Wenn mehr als 1.000 Postfächer vorhanden sind, die Elemente enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 1.000 postfächer mit den meisten Ergebnissen für die Vorschau zur Verfügung.|1.000|
|Maximale Anzahl von Elementen aus SharePoint- und OneDrive for #A0 auf der Vorschauseite für Suchen. Die neuesten Elemente werden angezeigt. |200|
|Maximale Anzahl von SharePoint- und OneDrive for Business-Websites, die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn mehr als 200 Websites Elemente enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 200 häufigsten Websites mit den meisten Ergebnissen für die Vorschau zur Verfügung.|200|
|Maximale Anzahl von Elementen pro Postfach für öffentliche Ordner, die auf der Vorschauseite für Suchen angezeigt werden. |100|
|Maximale Anzahl von Elementen in allen Postfachelementen für öffentliche Ordner, die auf der Vorschauseite für Suchen angezeigt werden. |200|
|Maximale Anzahl von Postfächern für öffentliche Ordner, die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn mehr als 500 Postfächer für öffentliche Ordner vorhanden sind, die Elemente enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 500 postfächer mit den meisten Ergebnissen für die Vorschau zur Verfügung.|500|
|||

## <a name="search-times"></a>Suchzeiten

Microsoft sammelt Leistungsinformationen für Suchdurchsuchungen, die von allen Organisationen ausgeführt werden. Obwohl sich die Komplexität einer Suchabfrage negativ auf die Suchzeiten auswirken kann, ist die Anzahl der durchsuchten Postfächer der Faktor, der die Suchdauer am stärksten beeinflusst. Obwohl Microsoft keine Vereinbarung zum Servicelevel für Suchzeiten bietet, werden in der folgenden Tabelle die durchschnittlichen Suchzeiten für Sammlungssuchen basierend auf der Anzahl von Postfächern aufgeführt, die in der Suche enthalten sind.
  
  |**Anzahl Postfächer**|**Durchschnittliche Suchzeit**|
  |:-----|:-----|
  |100  <br/> |30 Sekunden  <br/> |
  |1.000  <br/> |45 Sekunden  <br/> |
  |10.000  <br/> |4 Minuten  <br/> |
  |25.000  <br/> |10 Minuten  <br/> |
  |50.000  <br/> |20 Minuten  <br/> |
  |100.000  <br/> |25 Minuten  <br/> |
  |||

## <a name="viewer-limits"></a>Anzeigebeschränkungen

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Maximale Größe der Excel-Datei, die im systemeigenen Viewer angezeigt werden kann.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits"></a>Exportgrenzwerte

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Maximale Größe eines einzelnen Exports.|3 Millionen Dokumente oder 100 GB, je nach Kleiner|
|Maximale Datenmenge an einem einzigen Tag. | 2 TB |
|Maximale Anzahl gleichzeitiger Exporte in Ihrer Organisation. | 10 <sup>4</sup> |
|Maximale Anzahl gleichzeitiger Exporte pro Benutzer. | 3  |
|Maximale Größe einer einzelnen PST-Datei. | 10 GB |
|Maximale Anzahl gleichzeitiger Exporte pro Überprüfungssatz. | 1  |
|||

## <a name="review-set-download-limits"></a>Überprüfen von Festgelegten Downloadbeschränkungen

| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Gesamtdateigröße oder maximale Anzahl von Dokumenten, die aus einem Überprüfungssatz heruntergeladen wurden.  <br/> |3 MB oder 50 Dokumente <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Jedes Element, das einen einzelnen Dateigrenzwert überschreitet, wird als Verarbeitungsfehler angezeigt.
>
> <sup>2</sup> Bei der Suche nach SharePoint- und OneDrive for #A0 werden die Zeichen in den URLs der durchsuchten Websites auf diesen Grenzwert angezählt.
>
> <sup>3</sup> Für Abfragen ohne Ausdrücke (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) verwenden wir einen speziellen Präfixindex. Dies weist darauf hin, dass ein Wort in einem Dokument auftritt, aber nicht an dem Ort, an dem es im Dokument auftritt. Zum Ausführen einer Ausdrucksabfrage (ein Schlüsselwortwert mit doppelten Anführungszeichen) müssen wir die Position im Dokument für die Wörter im Ausdruck vergleichen. Dies bedeutet, dass der Präfixindex nicht für Phrasenabfragen verwendet werden kann. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, auf die das Präfix erweitert wird. z. **B. kann Zeit _ zu _ "Zeit- ODER Zeitgeber ODER Zeiten \* ODER Timex ODER timeboxed OR ..." erweitert werden.** Der Grenzwert von 10.000 ist die maximale Anzahl von Varianten, auf die das Wort erweitert werden kann, nicht die Anzahl der Dokumente, die mit der Abfrage übereinstimmen. Es gibt keine Obergrenze für nicht ausdrückefreie Ausdrücke.
>
> <sup>4</sup> Dieser Grenzwert wird für alle eDiscovery-Tools freigegeben. Dies bedeutet, dass gleichzeitige Exporte in inhaltssuche, Core eDiscovery und Advanced eDiscovery auf diesen Grenzwert angewendet werden.
>
> <sup>5</sup> Dieser Grenzwert gilt für das Herunterladen ausgewählter Dokumente aus einem Überprüfungssatz. Es gilt nicht für das Exportieren von Dokumenten aus einem Überprüfungssatz. Weitere Informationen zum Herunterladen und Exportieren von Dokumenten finden Sie unter [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).
>
> <sup>6</sup> Indizierungsgrenzwerte pro Organisation und Tag. Als Problemumgehung können Sie auf  der Registerkarte Datenquellen in einem Fall mehrere Custodians auswählen und dann auf **Index** aktualisieren klicken, um zu vermeiden, dass für jeden Custodian ein separater Indexauftrag erstellt wird. 
