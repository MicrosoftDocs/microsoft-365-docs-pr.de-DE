---
title: Grenzwerte für die Inhaltssuche und Core eDiscovery im Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Erfahren Sie mehr über die Grenzwerte, die für das Inhaltssuchfeature im Microsoft 365 Compliance Center gelten, z. B. die maximale Anzahl gleichzeitiger Suchen. Diese Suchgrenzwerte gelten auch für Suchen im Zusammenhang mit Core eDiscovery-Fällen.
ms.openlocfilehash: 23751fd62b2d96400d8184faa0d8d74b06b68906
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840492"
---
# <a name="limits-for-content-search"></a>Grenzwerte für die Inhaltssuche 
Verschiedene Grenzwerte gelten für das Tool für die Inhaltssuche im Microsoft 365 Compliance Center. Dazu gehören Auf der  Seite "Inhaltssuche" ausgeführte Suchen und Suchen, die einem eDiscovery-Fall auf der **Core eDiscovery-Seite zugeordnet** sind. Diese Grenzwerte helfen bei der Aufrechterhaltung der Integrität und Qualität der Dienste, die Organisationen bereitgestellt werden. Es gibt auch Einschränkungen im Zusammenhang mit der Indizierung von E-Mail-Nachrichten in Exchange Online für die Suche. Sie können die Grenzwerte für die Inhaltssuche oder die E-Mail-Indizierung nicht ändern, sie sollten jedoch berücksichtigt werden, damit Sie diese Grenzwerte bei der Planung, Ausführung und Problembehandlung von Inhaltssuchen berücksichtigen können.
  
## <a name="search-limits"></a>Suchgrenzen

In der folgenden Tabelle sind die Suchgrenzwerte für die Verwendung des Inhaltssuchtools im Microsoft 365 Compliance Center und für Suchen aufgeführt, die einem Core eDiscovery-Fall zugeordnet sind.
  
| Beschreibung der Beschränkung | Grenze |
|:-----|:-----|
|Die maximale Anzahl von Postfächern oder Websites, die in einer einzigen Suche durchsucht werden können  <br/> |No limit <sup>1</sup> <br/> |
|Die maximale Anzahl von Suchen, die gleichzeitig in Ihrer Organisation ausgeführt werden können.  <br/> |30  <br/> |
|Die maximale Anzahl von Suchen, die ein einzelner Benutzer gleichzeitig starten kann. Dieser Grenzwert ist höchstwahrscheinlich erreicht, wenn der Benutzer versucht, mehrere Suchen mithilfe des Befehls **"Get-ComplianceSearch \| Start-ComplianceSearch"** in Security & Compliance Center PowerShell zu starten.  <br/> |10   <br/> |
|Die maximale Anzahl von Elementen pro Benutzerpostfach, die bei der Vorschau der Inhaltssuchergebnisse auf der Vorschauseite angezeigt werden.  <br/> |100  <br/> |
|Die maximale Anzahl von Elementen in allen Benutzerpostfächern, die bei der Vorschau der Suchergebnisse auf der Vorschauseite angezeigt werden. Die neuesten Elemente werden angezeigt.  <br/> |1,000  <br/> |
|Die maximale Anzahl von Benutzerpostfächern, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn mehr als 1.000 Postfächer mit Inhalten vorhanden sind, die mit der Suchabfrage übereinstimmen, stehen nur die 1000 Postfächer mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |1,000  <br/> |
|Die maximale Anzahl von Elementen in SharePoint- und OneDrive for Business-Websites, die bei der Vorschau der Suchergebnisse auf der Vorschauseite angezeigt werden. Die neuesten Elemente werden angezeigt.  <br/> |200  <br/> |
|Die maximale Anzahl von Websites (in SharePoint und OneDrive for Business), die als Vorschau für Suchergebnisse angezeigt werden können. Wenn mehr als 200 Websites insgesamt Inhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 200 websites mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |200  <br/> |
|Die maximale Anzahl von Elementen pro Postfach für öffentliche Ordner, die bei der Vorschau der Inhaltssuchergebnisse auf der Vorschauseite angezeigt werden.  <br/> |100  <br/> |
|Die maximale Anzahl von Elementen in allen Postfächern für öffentliche Ordner, die bei der Vorschau der Inhaltssuchergebnisse auf der Vorschauseite angezeigt werden.  <br/> |200  <br/> |
|Die maximale Anzahl von öffentlichen Postfächern, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn mehr als 500 Postfächer für öffentliche Ordner vorhanden sind, die Inhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 500 Postfächer für öffentliche Ordner mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |500  <br/> |
|Die maximale Anzahl von Zeichen für die Suchabfrage (einschließlich Operatoren und Bedingungen) für eine Suche.  <br/><br/> **Hinweis:** Dieser Grenzwert wird nach dem Erweitern der Abfrage wirksam, was bedeutet, dass die Abfrage für jedes der Schlüsselwörter erweitert wird. Wenn eine Suchabfrage beispielsweise 15 Schlüsselwörter und zusätzliche Parameter und Bedingungen enthält, wird die Abfrage 15-mal erweitert, jeweils mit den anderen Parametern und Bedingungen in der Abfrage. Auch wenn die Anzahl der Zeichen in der Suchabfrage möglicherweise unter dem Grenzwert liegt, kann die erweiterte Abfrage dazu beitragen, diesen Grenzwert zu überschreiten.  <br/> |**Postfächer:** 10.000  <br/> **Websites:** 4.000 beim Durchsuchen aller Websites oder 2.000 beim Durchsuchen von bis zu 20 Websites <sup>2</sup> <br/> |
|Maximale Anzahl von Zurückgegebenen Varianten, wenn ein Präfix als Platzhalter verwendet wird, um in einer Suchabfrage nach einem exakten Ausdruck zu suchen, oder bei Verwendung eines Präfix-Platzhalters und des **NEAR** Boolean-Operators.  <br/> |10.000 <sup>3</sup> <br/> |
|Die Mindestanzahl von Alphazeichen für Präfix-Platzhalter; z. B.  `time*` ,  `one*` oder  `set*` .  <br/> |3   <br/> |
|Die maximale Anzahl von Postfächern in einer Suche, in der Sie Elemente löschen können, indem Sie eine Aktion "Suchen und Löschen" ausführen (mithilfe des Befehls **"New-ComplianceSearchAction -Purge").** Wenn die Suche, für die Sie eine Reinigungsaktion verwenden, mehr Quellpostfächer als dieser Grenzwert hat, kann die Bereinigungsaktion nicht mehr verwendet werden. Weitere Informationen zum Suchen und Löschen finden Sie unter Suchen nach und Löschen von [E-Mail-Nachrichten in Ihrer Organisation.](search-for-and-delete-messages-in-your-organization.md)  <br/> |50.000  <br/> |
|Die maximale Anzahl von Speicherorten in einer Suche, aus der Sie Elemente exportieren können. Wenn die zu exportierende Suche mehr Speicherorte als diese Grenze hat, kann der Export nicht ausgeführt werden. Weitere Informationen finden Sie unter [Exportieren von Inhaltssuchergebnissen.](export-search-results.md)  <br/> |100.000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Obwohl Sie eine unbegrenzte Anzahl von Postfächern in einer einzigen Suche durchsuchen können, können Sie die exportierten Suchergebnisse nur aus maximal 100.000 Postfächern mithilfe des eDiscovery-Exporttools im Microsoft 365 Compliance Center herunterladen. Um die Suchergebnisse aus mehr als 100.000 Postfächern herunterzuladen, müssen Sie Security & Compliance Center PowerShell verwenden. Weitere Informationen und ein Beispielskript finden Sie unter Exportieren von Ergebnissen aus mehr als [100.000 Postfächern.](export-search-results.md#exporting-results-from-more-than-100000-mailboxes) <br/><br/> <sup>2</sup> Beim Durchsuchen von SharePoint- und OneDrive for #A0 werden die Zeichen in den URLs der durchsuchten Websites gegen diesen Grenzwert gezählt. <br/><br/> <sup>3</sup> Für Abfragen ohne Ausdrücke (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) wird ein spezieller Präfixindex verwendet. Dies weist darauf hin, dass ein Wort in einem Dokument auftritt, aber nicht an der Stelle, an der es im Dokument auftritt. Für eine Ausdrucksabfrage (ein Schlüsselwortwert mit doppelten Anführungszeichen) müssen wir die Position im Dokument für die Wörter im Ausdruck vergleichen. Dies bedeutet, dass der Präfixindex nicht für Ausdrucksabfragen verwendet werden kann. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, zu der das Präfix erweitert wird. Kann z.  `"time*"` B. bis  `"time OR timer OR times OR timex OR timeboxed OR …"` erweitern. Die maximale Anzahl von Varianten, in die das Wort erweitert werden kann (nicht die Anzahl der Dokumente, die der Abfrage entsprechen) ist 10.000. Es gibt keine Obergrenze für Ausdrücke, die keine Ausdrücke sind. 
  
## <a name="export-limits"></a>Exportgrenzwerte
In der folgenden Tabelle sind die Grenzwerte beim Exportieren der Ergebnisse einer Inhaltssuche aufgeführt. Diese Grenzwerte gelten auch, wenn Sie Inhalte aus einem Core eDiscovery-Fall exportieren.

|Beschreibung der Beschränkung|Grenze|
|:-----|:-----|
|Maximale Menge an exportierbaren Daten aus einer einzelnen Suche  <br/><br/> **Hinweis:** Wenn die Suchergebnisse größer als 2 TB sind, erwägen Sie die Verwendung von Datumsbereichen oder anderen Filtertypen, um die Gesamtgröße der Suchergebnisse zu verringern. <br/>  |2 TB  <br/> | 
|Maximale Exportgeschwindigkeit einer Organisation an einem einzigen Tag <br/><br/> **Hinweis:** Dieser Grenzwert wird täglich um 12:00 Uhr UTC zurückgesetzt. <br/> |2 TB <br/> |
|Maximale Anzahl gleichzeitiger Exporte, die gleichzeitig in Ihrer Organisation ausgeführt werden können <br/><br/> **Hinweis:** Beim Ausführen **eines Berichtsexports** wird die Gesamtanzahl gleichzeitiger Exporte für Ihre Organisation ermittelt. Wenn drei Benutzer jeweils drei Exporte ausführen, kann nur ein anderer Export ausgeführt werden. Unabhängig davon, ob ein Bericht oder Suchergebnisse exportiert werden, können keine weiteren Exporte ausgeführt werden, bis einer abgeschlossen ist.   <br/> |10  <br/> |
|Maximale Exporte, die ein einzelner Benutzer gleichzeitig ausführen kann <br/> |3  <br/> |
|Maximale Anzahl von Postfächern für Suchergebnisse, die mit dem eDiscovery-Exporttool heruntergeladen werden können <br/><br/> **Hinweis:** Um die Suchergebnisse aus mehr als 100.000 Postfächern herunterzuladen, müssen Sie Security & Compliance Center PowerShell verwenden. Anweisungen finden Sie [unter Exportieren von Ergebnissen aus mehr als 100.000 Postfächern.](export-search-results.md#exporting-results-from-more-than-100000-mailboxes) <br/> | 100.000 <br/>|
|Maximale Größe der PST-Datei, die exportiert werden kann <br/><br/> **Hinweis:** Wenn die Suchergebnisse aus dem Postfach eines Benutzers größer als 10 GB sind, werden die Suchergebnisse für das Postfach in zwei (oder mehr) separate PST-Dateien exportiert. Wenn Sie alle Suchergebnisse in einer einzigen PST-Datei exportieren möchten, wird die PST-Datei in zusätzlichen PST-Dateien verkn nen, wenn die Gesamtgröße der Suchergebnisse größer als 10 GB ist. Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows-Registrierung auf dem Computer bearbeiten, den Sie zum Exportieren der Suchergebnisse verwenden. Siehe [Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen.](change-the-size-of-pst-files-when-exporting-results.md) Die Suchergebnisse aus einem bestimmten Postfach werden nicht auf mehrere PST-Dateien aufgeteilt, es sei denn, der Inhalt eines einzelnen Postfachs beträgt mehr als 10 GB. Wenn Sie die Suchergebnisse in einer PST-Datei exportieren möchten, die alle Nachrichten in einem einzigen Ordner enthält und die Suchergebnisse größer als 10 GB sind, sind die Elemente weiterhin in chronologischer Reihenfolge organisiert, sodass sie basierend auf dem Gesendeten Datum in zusätzlichen PST-Dateien verkn nnen.<br/> | 10 GB <br/> |
|Rate, mit der Suchergebnisse aus Postfächern und Websites an einen von Microsoft bereitgestellten Azure Storage-Speicherort hochgeladen werden. |Maximal 2 GB pro Stunde|
|||

## <a name="indexing-limits-for-email-messages"></a>Indizierungsgrenzwerte für E-Mail-Nachrichten

In der folgenden Tabelle werden die Indizierungsgrenzwerte beschrieben, die dazu führen können, dass eine E-Mail-Nachricht als nicht indiziertes Element oder ein teilweise indiziertes Element in den Ergebnissen einer Inhaltssuche zurückgegeben wird.
  
| Indizierungsgrenzwert | Maximalwert | Beschreibung |
|:-----|:-----|:-----|
|Maximale Anlagengröße|150 MB  <br/> |Die maximale Größe einer E-Mail-Anlage, die für die Indizierung analysiert wird. Alle Anlagen, die diesen Grenzwert überschreiten, werden nicht für die Indizierung analysiert, und die Nachricht mit der Anlage wird als teilweise indiziert markiert.  <br/> <br/>**Hinweis:** Die Analyse ist der Prozess, bei dem der Indizierungsdienst Text aus der Anlage extrahiert, unnötige Zeichen wie Interpunktion und Leerzeichen entfernt und dann den Text in Wörter aufteilt (in einem Prozess, der als Tokenisierung bezeichnet wird), die dann im Index gespeichert werden.           |
|Maximale Anzahl von Anlagen  <br/> |250  <br/> |Die maximale Anzahl von Dateien, die an eine E-Mail-Nachricht angefügt sind, die für die Indizierung analysiert wird. Wenn eine Nachricht mehr als 250 Anlagen enthält, werden die ersten 250 Anlagen analysiert und indiziert, und die Nachricht wird als teilweise indiziert markiert, da sie zusätzliche Anlagen enthält, die nicht analysiert wurden.  <br/> |
|Maximale Anlagentiefe  <br/> |30  <br/> |Die maximale Anzahl geschachtelter Anlagen, die analysiert werden. Wenn an eine E-Mail-Nachricht beispielsweise eine weitere Nachricht angefügt ist und die angefügte Nachricht über ein angefügtes Word-Dokument verfügt, werden das Word-Dokument und die angefügte Nachricht indiziert. Dieses Verhalten wird für bis zu 30 geschachtelte Anlagen fortgesetzt.  <br/> |
|Maximale Anzahl angefügter Bilder  <br/> |0  <br/> |Ein Bild, das an eine E-Mail-Nachricht angefügt ist, wird vom Parser übersprungen und nicht indiziert.  <br/> |
|Maximale Zeit für die Analyse eines Elements  <br/> |30 Sekunden  <br/> |Es werden maximal 30 Sekunden für die Analyse eines Elements für die Indizierung verwendet. Wenn die Analysezeit 30 Sekunden überschreitet, wird das Element als teilweise indiziert markiert.  <br/> |
|Maximale Parserausgabe  <br/> |2 Millionen Zeichen  <br/> |Die maximale Textausgabe des indizierten Parsers. Wenn der Parser beispielsweise 8 Millionen Zeichen aus einem Dokument extrahiert hat, werden nur die ersten 2 Millionen Zeichen indiziert.  <br/> |
|Maximale Anzahl von Anmerkungstoken  <br/> |2 Millionen  <br/> |Wenn eine E-Mail-Nachricht indiziert wird, wird jedes Wort mit unterschiedlichen Verarbeitungsanweisungen kommentiert, die angeben, wie dieses Wort indiziert werden soll. Jeder Satz von Verarbeitungsanweisungen wird als Anmerkungstoken bezeichnet. Zur Aufrechterhaltung der Dienstqualität in Office 365 gibt es eine Beschränkung von 2 Millionen Anmerkungstoken für eine E-Mail-Nachricht.  <br/> |
|Maximale Textgröße im Index  <br/> |67 Millionen Zeichen  <br/> |Die Gesamtzahl der Zeichen im Textkörper einer E-Mail-Nachricht und aller Anlagen. Wenn eine E-Mail-Nachricht indiziert wird, wird der text im Textkörper der Nachricht und in allen Anlagen zu einer einzelnen Zeichenfolge verkettet. Die maximale Größe dieser indizierten Zeichenfolge beträgt 67 Millionen Zeichen.  <br/> |
|Maximale Anzahl eindeutiger Token im Textkörper  <br/> |1 Mio.  <br/> |Wie bereits erläutert, sind Token das Ergebnis des Extrahierens von Text aus Inhalten, des Entfernens von Interpunktionszeichen und Leerzeichen und der anschließenden Aufteilung in Wörter (sogenannte Token), die im Index gespeichert sind. Der Ausdruck enthält beispielsweise  `"cat, mouse, bird, dog, dog"` 5 Token. Aber nur 4 davon sind eindeutige Token. Es gibt eine Grenze von 1 Million eindeutigen Token pro E-Mail-Nachricht, wodurch verhindert wird, dass der Index mit zufälligen Token zu groß wird.  <br/> |
|||
  
## <a name="more-information"></a>Weitere Informationen

Es gibt zusätzliche Grenzwerte im Zusammenhang mit verschiedenen Aspekten der Inhaltssuche, z. B. inhaltsindizierung. Weitere Informationen zu diesen Grenzwerten finden Sie in den folgenden Themen:

- [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md)

- [Untersuchen teilweise indizierter Elemente in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Suchgrenzwerte für SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits)

Informationen zu Inhaltssuchen finden Sie unter:
  
- [Inhaltssuche in Microsoft 365](content-search.md)

- [Suchen nach Inhalten in einem Core eDiscovery-Fall](search-for-content-in-core-ediscovery.md)

- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)

Fallbeschränkungen im Zusammenhang mit Core eDiscovery und Advanced eDiscovery finden Sie unter:

- [Grenzwerte in Core eDiscovery](limits-core-ediscovery.md)

- [Grenzwerte in Advanced eDiscovery](limits-ediscovery20.md)
