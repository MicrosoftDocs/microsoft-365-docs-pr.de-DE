---
title: Advanced eDiscovery-Beschränkungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Fallgrenzwerte, Indizierungsgrenzwerte und Suchgrenzwerte, die für die Advanced eDiscovery-Lösung in Microsoft 365 gelten.
ms.openlocfilehash: 051c1ce916fcb59ade19120bc25496101d501138
ms.sourcegitcommit: f40378013757d560d5566a11ad4e6f527c018cc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49796173"
---
# <a name="limits-in-advanced-ediscovery"></a>Grenzwerte in Advanced eDiscovery

In diesem Artikel werden die Grenzwerte in der Advanced eDiscovery-Lösung in Microsoft 365 beschrieben.

## <a name="case-and-review-set-limits"></a>Grenzwerte für Fall- und Überprüfungssatz

In der folgenden Tabelle sind die Grenzwerte für Fälle und Überprüfungssätze in Advanced eDiscovery aufgeführt.

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Gesamtanzahl der Dokumente, die einem Fall hinzugefügt werden können (für alle Überprüfungssätze in einem Fall).  <br/> |3 Million <br/> |
|Gesamtgröße der Datei pro Ladesatz. Dies schließt das Laden von Nicht-Office 365 in einen Überprüfungssatz ein.  <br/> |300 GB <br/> |
|Die Gesamtzahl der Daten, die pro Tag in alle Überprüfungssätze in der Organisation geladen wurden.<br/> |2 TB <br/> |
|Maximale Anzahl von Ladesätzen pro Fall.  <br/> |200 <br/> |
|Maximale Anzahl von Überprüfungssätzen pro Fall.  <br/> |20 <br/> |
|Maximale Anzahl von Taggruppen pro Fall.  <br/> |1000 <br/> |
|Maximale Anzahl von Tags pro Fall.  <br/> |1000 <br/> |
|||

## <a name="indexing-limits"></a>Indizierungsgrenzwerte

In der folgenden Tabelle sind die Indizierungsgrenzwerte in Advanced eDiscovery aufgeführt.

|**Beschreibung der Beschränkung**|**Grenzwert**|
  |:-----|:-----|
  |Maximale Anzahl von Zeichen, die aus einer einzelnen Datei extrahiert wurden.  <br/> |10 Millionen<sup>1</sup> <br/> |
  |Maximale Größe einer einzelnen Datei.   <br/> |100 MB<sup>1</sup> <br/> |
  |Maximale Tiefe der eingebetteten Elemente in einem Dokument.  <br/> |25<sup>1</sup> <br/> |
  |Maximale Größe von Dateien, die von der optischen Zeichenerkennung (Optical Character Recognition, OCR) verarbeitet werden.  <br/> |24 MB<sup>1</sup> <br/> 
  |Maximale Anzahl von Indizierungsaufträgen pro Organisation und Tag. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Suchgrenzen

Die in diesem Abschnitt beschriebenen Grenzwerte stehen im  Zusammenhang mit der Verwendung des Suchtools auf der Registerkarte "Suchen" zum Sammeln von Daten für einen Fall. Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall in Advanced eDiscovery](collecting-data-for-ediscovery.md).

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Maximale Anzahl von Postfächern oder Websites, die in einer einzigen Suche durchsucht werden können.  <br/> |Keine Begrenzung  <br/> |
|Maximale Anzahl von Suchen, die gleichzeitig ausgeführt werden können.  <br/> |Keine Begrenzung  <br/> | 
|Maximale Anzahl von Suchen, die ein einzelner Benutzer gleichzeitig starten kann.  <br/> |10   <br/> | 
|Maximale Anzahl von Zeichen für eine Suchabfrage (einschließlich Operatoren und Bedingungen).  <br/> |**Postfächer**: 10.000<br/>**Websites**: 4.000 beim Durchsuchen aller Websites oder 2.000 beim Durchsuchen von bis zu 20 Websites <sup>2</sup> <br/> |
|Mindestanzahl von Alphazeichen für Präfix-Platzhalter; Beispiel: **1 \** _ oder _*festlegen \**_. <br/> |3   <br/> |  
|Maximale Anzahl von Zurückgegebenen Varianten, wenn ein Präfix als Platzhalter für die Suche nach einem exakten Ausdruck oder bei Verwendung eines Präfix-Platzhalters und des Booleschen Operators _ *NEAR** verwendet wird.  <br/> |10.000 <sup>3</sup> <br/> |
|Maximale Anzahl von Elementen pro Benutzerpostfach, die auf der Vorschauseite für Suchen angezeigt werden. Die neuesten Elemente werden angezeigt.   <br/> |100  <br/> |
|Maximale Anzahl von Elementen aus allen Postfächern, die auf der Vorschauseite für Suchen angezeigt werden.  <br/> |1,000  <br/> |
|Maximale Anzahl von Postfächern, für die eine Vorschau für Suchergebnisse angezeigt werden kann.  Wenn mehr als 1.000 Postfächer vorhanden sind, die Elemente enthalten, die der Suchabfrage entsprechen, stehen nur die 1.000 Postfächer mit den meisten Ergebnissen für die Vorschau zur Verfügung.<br/> |1,000  <br/> |
|Maximale Anzahl von Elementen aus SharePoint- und OneDrive for Business-Websites, die auf der Vorschauseite für Suchen angezeigt werden. Die neuesten Elemente werden angezeigt.  <br/> |200  <br/> |
|Maximale Anzahl von SharePoint- und OneDrive for Business-Websites, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn mehr als 200 Websites Elemente enthalten, die der Suchabfrage entsprechen, stehen nur die 200 websites mit den meisten Ergebnissen für die Vorschau zur Verfügung.  <br/> |200  <br/> |
|Maximale Anzahl von Elementen pro Postfach für öffentliche Ordner, die auf der Vorschauseite für Suchen angezeigt werden.  <br/> |100  <br/> |
|Maximale Anzahl von Elementen in allen Postfachelementen für öffentliche Ordner, die auf der Vorschauseite für Suchen angezeigt werden.  <br/> |200  <br/> |
|Maximale Anzahl von Postfächern für öffentliche Ordner, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn mehr als 500 Postfächer für öffentliche Ordner vorhanden sind, die Elemente enthalten, die der Suchabfrage entsprechen, stehen nur die 500 postfächer mit den meisten Ergebnissen für die Vorschau zur Verfügung.  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>Anzeigebeschränkungen

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Maximale Größe der Excel-Datei, die im systemeigenen Viewer angezeigt werden kann.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits"></a>Exportgrenzwerte

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Maximale Größe eines einzelnen Exports.|3 Millionen Dokumente oder 100 GB, je nach Kleinerem|
|Maximale Datenmenge an einem einzelnen Tag. | 2 TB |
|Maximale Anzahl gleichzeitiger Exporte in Ihrer Organisation. | 10 <sup>4</sup> |
|Maximale Anzahl gleichzeitiger Exporte pro Benutzer. | 3  |
|Maximale Größe einer einzelnen PST-Datei. | 10 GB |
|Maximale Anzahl gleichzeitiger Exporte pro Überprüfungssatz. | 1  |
|||

## <a name="review-set-download-limits"></a>Überprüfen der Downloadgrenzwerte

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Gesamtdateigröße oder maximale Anzahl von Dokumenten, die aus einem Überprüfungssatz heruntergeladen wurden.  <br/> |3 MB oder 50 Dokumente <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Jedes Element, das einen einzelnen Dateigrenzwert überschreitet, wird als Verarbeitungsfehler angezeigt.<br/>
> <sup>2</sup> Beim Durchsuchen von SharePoint- und OneDrive for #A0 werden die Zeichen in den URLs der durchsuchten Websites gegen diesen Grenzwert angezählt.<br/>
> <sup>3</sup> Für Abfragen ohne Ausdrücke (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) wird ein spezieller Präfixindex verwendet. Dies weist darauf hin, dass ein Wort in einem Dokument auftritt, aber nicht an der Stelle, an der es im Dokument auftritt. Für eine Ausdrucksabfrage (ein Schlüsselwortwert mit doppelten Anführungszeichen) müssen wir die Position im Dokument für die Wörter im Ausdruck vergleichen. Dies bedeutet, dass der Präfixindex nicht für Ausdrucksabfragen verwendet werden kann. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, zu der das Präfix erweitert wird. Beispielsweise kann **Zeit _ zu _ \* "Zeit ODER *Zeitgeber* ODER UhrzeitEN ODER Timex OR timeboxed OR ..." erweitert werden.** Der Grenzwert von 10.000 ist die maximale Anzahl von Varianten, auf die das Wort erweitert werden kann, nicht die Anzahl der Dokumente, die mit der Abfrage übereinstimmen. Es gibt keine Obergrenze für Ausdrücke, die keine Ausdrücke sind.<br/>
> <sup>4</sup> Dieser Grenzwert wird für alle eDiscovery-Tools freigegeben. Dies bedeutet, dass gleichzeitige Exporte in der Inhaltssuche, Core eDiscovery und Advanced eDiscovery auf diesen Grenzwert angewendet werden. <br/>
> <sup>5</sup> Dieser Grenzwert gilt für das Herunterladen ausgewählter Dokumente aus einem Überprüfungssatz. Sie gilt nicht für den Export von Dokumenten aus einem Überprüfungssatz. Weitere Informationen zum Herunterladen und Exportieren von Dokumenten finden Sie unter Exportieren von [Falldaten in Advanced eDiscovery](exporting-data-ediscover20.md). <br/>
> <sup>6</sup> Indizierungsgrenzwerte pro Organisation und Tag. Als Problemumgehung können Sie mehrere Verwahrer auswählen und dann auf **"Index** aktualisieren" klicken, um zu vermeiden, dass für jeden Verwahrer ein separater Indexauftrag erstellt wird. <br/>

