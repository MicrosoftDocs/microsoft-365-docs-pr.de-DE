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
description: Erfahren Sie mehr über die Fall Limits, Indizierungs Grenzwerte und Such Grenzwerte, die für die erweiterte eDiscovery-Lösung in Microsoft 365 gelten.
ms.openlocfilehash: 5666bae5315586ed421ad8d6c748505cda8ae3e6
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778461"
---
# <a name="limits-in-advanced-ediscovery"></a>Grenzwerte in Advanced eDiscovery

In diesem Artikel werden die Grenzwerte für die erweiterte eDiscovery-Lösung in Microsoft 365 beschrieben.

## <a name="case-and-review-set-limits"></a>Grenzwerte für Fall-und Überprüfungs Sätze

In der folgenden Tabelle sind die Grenzwerte für Fälle und Überprüfungs Sätze in Advanced eDiscovery aufgeführt.

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Gesamtzahl der Dokumente, die einem Fall hinzugefügt werden können (für alle Überprüfungs Sätze in einem Fall).  <br/> |3 Million <br/> |
|Gesamtdateigröße pro Lastsatz. Dies umfasst das Laden von nicht Office 365 in einen Überprüfungs Satz.  <br/> |300 GB <br/> |
|Die Gesamtmenge an Daten, die in alle Überprüfungs Sätze in der Organisation pro Tag geladen wurden.<br/> |2 TB <br/> |
|Maximale Anzahl von Lasten Sätzen pro Fall.  <br/> |200 <br/> |
|Maximale Anzahl von Überprüfungs Sätzen pro Fall.  <br/> |20 <br/> |
|||

## <a name="indexing-limits"></a>Indizierungsgrenzwerte

In der folgenden Tabelle sind die Grenzwerte für die Indizierung in Advanced eDiscovery aufgeführt.

|**Beschreibung der Beschränkung**|**Grenzwert**|
  |:-----|:-----|
  |Maximale Anzahl von Zeichen, die aus einer einzelnen Datei extrahiert wurden.  <br/> |10 Millionen<sup>1</sup> <br/> |
  |Maximale Größe einer einzelnen Datei.   <br/> |100 MB<sup>1</sup> <br/> |
  |Maximale Tiefe eingebetteter Elemente in einem Dokument.  <br/> |25<sup>1</sup> <br/> |
  |Die maximale Größe der Datei, die durch die optische Zeichenerkennung (OCR) verarbeitet wird.  <br/> |24 MB<sup>1</sup> <br/> |  
|||

## <a name="search-limits"></a>Suchgrenzen

Die in diesem Abschnitt beschriebenen Grenzwerte beziehen sich auf die Verwendung des Such Tools auf der Registerkarte **Suchen** zum Erfassen von Daten für einen Fall. Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall in Advanced eDiscovery](collecting-data-for-ediscovery.md).

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Maximale Anzahl von Postfächern oder Websites, die in einer einzigen Suche durchsucht werden können.  <br/> |Keine Begrenzung  <br/> |
|Maximale Anzahl von Suchvorgängen, die gleichzeitig ausgeführt werden können.  <br/> |Keine Begrenzung  <br/> | 
|Maximale Anzahl von Suchvorgängen, die ein einzelner Benutzer gleichzeitig starten kann.  <br/> |10   <br/> | 
|Maximale Anzahl von Zeichen für eine Suchabfrage (einschließlich Operatoren und Bedingungen).  <br/> |**Postfächer**: 10.000<br/>**Websites**: 4.000 beim Durchsuchen aller Websites oder 2.000 bei der Suche bis zu 20 Websites <sup>2</sup> <br/> |
|Minimale Anzahl von Alphazeichen für Präfix Platzhalter; Beispiel ** \* eins** oder **festgelegt \* **. <br/> |3  <br/> |  
|Maximale Anzahl von Varianten, die zurückgegeben werden, wenn Präfix Platzhalter verwendet wird, um nach einem exakten Ausdruck zu suchen oder wenn ein Präfix Platzhalter und der **near** -Boolesche Operator verwendet werden.  <br/> |10.000 <sup>3</sup> <br/> |
|Maximale Anzahl von Elementen pro Benutzerpostfach, die auf der Vorschauseite für Suchvorgänge angezeigt werden. Die neuesten Elemente werden angezeigt.   <br/> |100  <br/> |
|Maximale Anzahl von Elementen aus allen Postfächern, die auf der Vorschauseite für Suchvorgänge angezeigt werden.  <br/> |1.000  <br/> |
|Maximale Anzahl von Postfächern, für die eine Vorschau für Suchergebnisse angezeigt werden kann.  Wenn mehr als 1000 Postfächer vorhanden sind, die Elemente enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die obersten 1.000-Postfächer mit den meisten Ergebnissen für die Vorschau zur Verfügung.<br/> |1.000  <br/> |
|Maximale Anzahl von Elementen aus SharePoint und OneDrive für Unternehmen Websites, die auf der Vorschauseite für Suchvorgänge angezeigt werden. Die neuesten Elemente werden angezeigt.  <br/> |200  <br/> |
|Maximale Anzahl von SharePoint-und OneDrive für Unternehmen-Websites, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn es mehr als 200 Websites gibt, die Elemente enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die Top 200-Websites mit den meisten Ergebnissen für die Vorschau zur Verfügung.  <br/> |200  <br/> |
|Maximale Anzahl von Elementen pro Postfach für Öffentliche Ordner, die auf der Vorschauseite für Suchvorgänge angezeigt werden.  <br/> |100  <br/> |
|Maximale Anzahl von Elementen, die in allen Postfachelementen für Öffentliche Ordner gefunden werden, die auf der Vorschauseite für Suchvorgänge angezeigt werden.  <br/> |200  <br/> |
|Maximale Anzahl von Postfächern für Öffentliche Ordner, die in der Vorschau für Suchergebnisse angezeigt werden können. Wenn mehr als 500 Postfächer für Öffentliche Ordner vorhanden sind, die Elemente enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die obersten 500-Postfächer mit den meisten Ergebnissen für die Vorschau zur Verfügung.  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>Anzeigebeschränkungen

|**Beschreibung der Beschränkung**|**Grenzwert**|
  |:-----|:-----|
  |Maximale Größe der Excel-Datei, die im systemeigenen Viewer angezeigt werden kann.  <br/> |4 MB  <br/> |
|||

## <a name="review-set-download-limits"></a>Überprüfen der Grenzwerte für das Festlegen des Downloads

|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Gesamtdateigröße oder maximale Anzahl von Dokumenten, die von einem Überprüfungspaket heruntergeladen wurden.  <br/> |3 MB oder 50 Dokumente <sup>4</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> jedes Element, das einen einzelnen Datei Grenzwert überschreitet, wird als Verarbeitungsfehler angezeigt.<br/>
> <sup>2</sup> beim Durchsuchen von SharePoint-und OneDrive für Unternehmen-Speicherorte zählen die Zeichen in den URLs der gesuchten Websites auf diesen Grenzwert.<br/>
> <sup>3</sup> bei nicht-Phrase-Abfragen (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) wird ein spezieller Präfix Index verwendet. Dies weist darauf hin, dass ein Wort in einem Dokument auftritt, aber nicht dort, wo es im Dokument vorkommt. Um eine Phrasenabfrage (ein Stichwort Wert mit doppelten Anführungszeichen) durchführen zu können, müssen wir die Position im Dokument für die Wörter im Ausdruck vergleichen. Dies bedeutet, dass der Präfix Index für Phrase-Abfragen nicht verwendet werden kann. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, zu denen das Präfix erweitert wird. Beispielsweise kann **time \* ** auf **"Zeit oder Timer oder Uhrzeiten oder Timex oder Zeit verpackt oder..."** erweitert werden. Der Grenzwert von 10.000 ist die maximale Anzahl von Varianten, zu der das Wort erweitert werden kann, und nicht die Anzahl der Dokumente, die mit der Abfrage übereinstimmen. Für nicht-Phrasen-Ausdrücke gibt es keine Obergrenze.<br/>
> <sup>4</sup> dieser Grenzwert gilt für das Herunterladen ausgewählter Dokumente aus einem Überprüfungs Sätze. Sie gilt nicht für das Exportieren von Dokumenten aus einem Überprüfungspaket. Weitere Informationen zum herunterladen und Exportieren von Dokumenten finden Sie unter [Export Case Data in Advanced eDiscovery](exporting-data-ediscover20.md). <br/>

