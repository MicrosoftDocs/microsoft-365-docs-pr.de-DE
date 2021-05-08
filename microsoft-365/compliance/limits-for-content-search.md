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
description: Erfahren Sie mehr über die grenzwerte für das Inhaltssuchfeature im Microsoft 365 Compliance Center, z. B. die maximale Anzahl gleichzeitiger Suchen. Diese Suchgrenzwerte gelten auch für Suchen, die Core eDiscovery-Fällen zugeordnet sind.
ms.openlocfilehash: e4cfc79d35b4dc6a22e8e7a872699d906b39a901
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244320"
---
# <a name="limits-for-content-search"></a>Grenzwerte für die Inhaltssuche 
Verschiedene Grenzwerte werden auf das Inhaltssuchtool im compliance center Microsoft 365 angewendet. Dazu gehören Auf der  Seite Inhaltssuche ausgeführte Suchen und Suchen, die einem eDiscovery-Fall auf der Seite **Core eDiscovery zugeordnet** sind. Diese Beschränkungen helfen, die Integrität und Qualität der für Organisationen bereitgestellten Dienste zu erhalten. Es gibt auch Einschränkungen im Zusammenhang mit der Indizierung von E-Mail-Nachrichten in Exchange Online Suche. Sie können die Grenzwerte für die Inhaltssuche oder die E-Mail-Indizierung nicht ändern, sie sollten jedoch beachten, damit Sie diese Einschränkungen bei der Planung, Ausführung und Problembehandlung von Inhaltssuchen berücksichtigen können.
  
## <a name="search-limits"></a>Suchgrenzen

In der folgenden Tabelle sind die Suchgrenzwerte für die Verwendung des Inhaltssuchtools im Microsoft 365 Compliance Center und für Suchen aufgeführt, die einem Core eDiscovery-Fall zugeordnet sind.
  
| Beschreibung der Beschränkung | Grenzwert |
|:-----|:-----|
|Die maximale Anzahl von Postfächern oder Websites, die in einer einzigen Suche durchsucht werden können  <br/> |Kein Grenzwert <sup>1</sup> <br/> |
|Die maximale Anzahl von Suchen, die gleichzeitig in Ihrer Organisation ausgeführt werden können.  <br/> |30  <br/> |
|Die maximale Anzahl von organisationsweiten Suchen, die gleichzeitig ausgeführt werden können. <br/> |3  <br/> |
|Die maximale Anzahl von Suchen, die ein einzelner Benutzer gleichzeitig starten kann. Dieser Grenzwert wird höchstwahrscheinlich erreicht, wenn der Benutzer versucht, mehrere Suchen mithilfe des **Befehls Get-ComplianceSearch \| Start-ComplianceSearch** in Security & Compliance Center PowerShell zu starten.  <br/> |10    <br/> |
|Die maximale Anzahl von Elementen pro Benutzerpostfach, die bei der Vorschau der Inhaltssuchergebnisse auf der Vorschauseite angezeigt werden.  <br/> |100  <br/> |
|Die maximale Anzahl von Elementen in allen Benutzerpostfächern, die bei der Vorschau der Suchergebnisse auf der Vorschauseite angezeigt werden. Die neuesten Elemente werden angezeigt.  <br/> |1,000  <br/> |
|Die maximale Anzahl von Benutzerpostfächern, die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn mehr als 1000 Postfächer mit Inhalten vorhanden sind, die mit der Suchabfrage übereinstimmen, stehen nur die 1000 Postfächer mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |1,000  <br/> |
|Die maximale Anzahl von Elementen in SharePoint und OneDrive for Business, die auf der Vorschauseite angezeigt werden, wenn die Suchergebnisse in der Vorschau angezeigt werden. Die neuesten Elemente werden angezeigt.  <br/> |200  <br/> |
|Die maximale Anzahl von Websites (in SharePoint und OneDrive for Business), die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn mehr als 200 Websites insgesamt Inhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 200 häufigsten Websites mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |200  <br/> |
|Die maximale Anzahl von Elementen pro Postfach für öffentliche Ordner, die bei der Vorschau der Inhaltssuchergebnisse auf der Vorschauseite angezeigt werden.  <br/> |100  <br/> |
|Die maximale Anzahl von Elementen in allen Postfächern für öffentliche Ordner, die auf der Vorschauseite angezeigt werden, wenn die Vorschau der Inhaltssuchergebnisse angezeigt wird.  <br/> |200  <br/> |
|Die maximale Anzahl von öffentlichen Postfächern, die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn mehr als 500 Postfächer für öffentliche Ordner vorhanden sind, die Inhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die 500 Postfächer für öffentliche Ordner mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |500  <br/> |
|Die maximale Anzahl von Zeichen für die Suchabfrage (einschließlich Operatoren und Bedingungen) für eine Suche.  <br/><br/> **Hinweis:** Dieser Grenzwert wird wirksam, nachdem die Abfrage erweitert wurde und Zeichen aus der Schlüsselwortabfrage, auf den Benutzer angewendete Suchberechtigungsfilter und die URLs aller Websitestandorte enthält. Dies bedeutet, dass die Abfrage für jedes Schlüsselwörter erweitert wird. Wenn eine Suchabfrage beispielsweise 15 Schlüsselwörter und zusätzliche Parameter und Bedingungen enthält, wird die Abfrage 15-mal erweitert, jeweils mit den anderen Parametern und Bedingungen in der Abfrage. Auch wenn die Anzahl der Zeichen in der Suchabfrage unter dem Grenzwert liegt, kann die erweiterte Abfrage dazu beitragen, diesen Grenzwert zu überschreiten.  <br/> |**Postfächer:** 10.000  <br/> **Websites:** 4.000 beim Durchsuchen aller Websites oder 2.000 beim Durchsuchen von bis zu 20 Websites <sup>2</sup> <br/> |
|Maximale Anzahl von Varianten, die zurückgegeben werden, wenn ein Präfix-Platzhalter zum Suchen nach einem exakten Ausdruck in einer Suchabfrage oder bei Verwendung eines Präfix-Platzhalters und des **NEAR** Boolean-Operators verwendet wird.  <br/> |10.000 <sup>3</sup> <br/> |
|Die Mindestanzahl von Alphazeichen für Präfix-Platzhalter. z. B.  `time*`  `one*` , oder  `set*` .  <br/> |3  <br/> |
|Die maximale Anzahl von Postfächern in einer Suche, in der Sie Elemente löschen können, indem Sie eine Aktion "Suchen und Löschen" ausführen (mithilfe des **Befehls New-ComplianceSearchAction -Purge).** Wenn die Suche, für die Sie eine Reinigungsaktion erstellen, über mehr Quellpostfächer verfügt als dieser Grenzwert, wird bei der Reinigungsaktion ein Fehler angezeigt. Weitere Informationen zum Suchen und Löschen finden Sie unter Suchen und Löschen von E-Mail-Nachrichten [in Ihrer Organisation.](search-for-and-delete-messages-in-your-organization.md)  <br/> |50.000  <br/> |
|Die maximale Anzahl von Speicherorten in einer Suche, aus der Sie Elemente exportieren können. Wenn die suche, die Sie exportieren, mehr Speicherorte als dieser Grenzwert hat, wird der Export fehlschlagen. Weitere Informationen finden Sie unter [Exportieren von Inhaltssuchergebnissen](export-search-results.md).  <br/> |100,000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Obwohl Sie eine unbegrenzte Anzahl von Postfächern in einer einzigen Suche durchsuchen können, können Sie die exportierten Suchergebnisse nur aus maximal 100.000 Postfächern mit dem eDiscovery Export Tool im Microsoft 365 Compliance Center herunterladen. <br/><br/> <sup>2</sup> Beim Durchsuchen SharePoint und OneDrive for Business werden die Zeichen in den URLs der websites, die durchsucht werden, auf diesen Grenzwert angerechnet. <br/><br/> <sup>3</sup> Für Abfragen ohne Ausdrücke (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) verwenden wir einen speziellen Präfixindex. Dies weist darauf hin, dass ein Wort in einem Dokument auftritt, aber nicht an dem Ort, an dem es im Dokument auftritt. Zum Ausführen einer Ausdrucksabfrage (ein Schlüsselwortwert mit doppelten Anführungszeichen) müssen wir die Position im Dokument für die Wörter im Ausdruck vergleichen. Dies bedeutet, dass der Präfixindex nicht für Phrasenabfragen verwendet werden kann. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, auf die das Präfix erweitert wird. kann z.  `"time*"` B. zu erweitert  `"time OR timer OR times OR timex OR timeboxed OR …"` werden. Die maximale Anzahl von Varianten, in die das Wort erweitert werden kann (nicht die Anzahl der Dokumente, die der Abfrage entsprechen) ist 10.000. Es gibt keine Obergrenze für nicht ausdrückefreie Ausdrücke. 
  
## <a name="search-times"></a>Suchzeiten
Microsoft sammelt Leistungsinformationen für Suchdurchsuchungen, die von allen Organisationen ausgeführt werden. Obwohl sich die Komplexität einer Suchabfrage negativ auf die Suchzeiten auswirken kann, ist die Anzahl der durchsuchten Postfächer der Faktor, der die Suchdauer am stärksten beeinflusst. Obwohl Microsoft keine Vereinbarung zum Servicelevel für Suchzeiten bietet, werden in der folgenden Tabelle die durchschnittlichen Suchzeiten für Sammlungssuchen basierend auf der Anzahl von Postfächern aufgeführt, die in der Suche enthalten sind.

|Anzahl Postfächer|Durchschnittliche Suchzeit|
|:-----|:-----|
|100|30 Sekunden|
|1.000|45 Sekunden|
|10.000|4 Minuten|
|25.000|10 Minuten|
|50.000|20 Minuten|
|100.000|25 Minuten|
|||

## <a name="export-limits"></a>Exportgrenzwerte
In der folgenden Tabelle sind die Grenzwerte beim Exportieren der Ergebnisse einer Inhaltssuche aufgeführt. Diese Grenzwerte gelten auch, wenn Sie Inhalte aus einem Core eDiscovery-Fall exportieren.

|Beschreibung der Beschränkung|Grenzwert|
|:-----|:-----|
|Maximale Menge exportierbarer Daten aus einer einzelnen Suche  <br/><br/> **Hinweis:** Wenn die Suchergebnisse größer als 2 TB sind, sollten Sie Datumsbereiche oder andere Filtertypen verwenden, um die Gesamtgröße der Suchergebnisse zu verringern. <br/>  |2 TB  <br/> | 
|Maximal kann eine Organisation an einem einzigen Tag exportieren <br/><br/> **Hinweis:** Dieser Grenzwert wird täglich um 12:00 Uhr UTC zurückgesetzt. <br/> |2 TB <br/> |
|Maximale Anzahl gleichzeitiger Exporte, die gleichzeitig in Ihrer Organisation ausgeführt werden können <br/><br/> **Hinweis:** Beim Ausführen **eines Nur-Berichts-Exports** wird die Gesamtzahl gleichzeitiger Exporte für Ihre Organisation ermittelt. Wenn drei Benutzer jeweils drei Exporte ausführen, kann nur ein weiterer Export ausgeführt werden. Unabhängig davon, ob ein Bericht oder Suchergebnisse exportiert werden, können keine weiteren Exporte ausgeführt werden, bis einer abgeschlossen ist.   <br/> |10   <br/> |
|Maximale Exporte, die ein einzelner Benutzer jederzeit ausführen kann <br/> |3 <br/> |
|Maximale Anzahl von Postfächern für Suchergebnisse, die mit dem eDiscovery-Exporttool heruntergeladen werden können <br/>| 100,000 <br/>|
|Maximale Größe der PST-Datei, die exportiert werden kann <br/><br/> **Hinweis:** Wenn die Suchergebnisse aus dem Postfach eines Benutzers größer als 10 GB sind, werden die Suchergebnisse für das Postfach in zwei (oder mehr) separate PST-Dateien exportiert. Wenn Sie alle Suchergebnisse in einer einzelnen PST-Datei exportieren möchten, wird die PST-Datei in zusätzliche PST-Dateien gespäht, wenn die Gesamtgröße der Suchergebnisse größer als 10 GB ist. Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows registrierung auf dem Computer bearbeiten, den Sie zum Exportieren der Suchergebnisse verwenden. Weitere [Informationen finden Sie unter Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen.](change-the-size-of-pst-files-when-exporting-results.md) Die Suchergebnisse eines bestimmten Postfachs werden nur dann auf mehrere PST-Dateien aufgeteilt, wenn der Inhalt eines einzelnen Postfachs mehr als 10 GB beträgt. Wenn Sie die Suchergebnisse in einer PST-Datei exportieren möchten, die alle Nachrichten in einem einzigen Ordner enthält und die Suchergebnisse größer als 10 GB sind, sind die Elemente weiterhin in chronologischer Reihenfolge organisiert, sodass sie basierend auf dem gesendeten Datum in zusätzliche PST-Dateien gespäht werden.<br/> | 10 GB <br/> |
|Rate, mit der Suchergebnisse aus Postfächern und Websites an einen von Microsoft bereitgestellten Speicherort Azure Storage werden. |Maximal 2 GB pro Stunde|
|||

## <a name="indexing-limits-for-email-messages"></a>Indizierungsgrenzwerte für E-Mail-Nachrichten

In der folgenden Tabelle werden die Indizierungsgrenzwerte beschrieben, die dazu führen können, dass eine E-Mail-Nachricht als nicht indiziertes Element oder teilweise indiziertes Element in den Ergebnissen einer Inhaltssuche zurückgegeben wird.
  
| Indizierungsgrenzwert | Maximalwert | Beschreibung |
|:-----|:-----|:-----|
|Maximale Anlagengröße|150 MB  <br/> |Die maximale Größe einer E-Mail-Anlage, die für die Indizierung analysiert wird. Jede Anlage, die diesen Grenzwert überschreitet, wird nicht für die Indizierung analysiert, und die Nachricht mit der Anlage wird als teilweise indiziert markiert.  <br/> <br/>**Hinweis:** Die Analyse ist der Prozess, bei dem der Indizierungsdienst Text aus der Anlage extrahiert, unnötige Zeichen wie Interpunktion und Leerzeichen entfernt und den Text dann in Wörter (in einem Prozess namens Tokenisierung) teilt, die dann im Index gespeichert werden.           |
|Maximale Anzahl von Anlagen  <br/> |250  <br/> |Die maximale Anzahl von Dateien, die an eine E-Mail-Nachricht angefügt sind und für die Indizierung analysiert werden. Wenn eine Nachricht mehr als 250 Anlagen enthält, werden die ersten 250 Anlagen analysiert und indiziert, und die Nachricht wird als teilweise indiziert markiert, da sie über zusätzliche Anlagen verfügt, die nicht analysiert wurden.  <br/> |
|Maximale Anlagentiefe  <br/> |30  <br/> |Die maximale Anzahl geschachtelter Anlagen, die analysiert werden. Wenn beispielsweise einer E-Mail-Nachricht eine weitere Nachricht angefügt ist und die angefügte Nachricht über ein angefügtes Word-Dokument verfügt, werden das Word-Dokument und die angefügte Nachricht indiziert. Dieses Verhalten wird für bis zu 30 geschachtelte Anlagen fortgesetzt.  <br/> |
|Maximale Anzahl angefügter Bilder  <br/> |0  <br/> |Ein Bild, das einer E-Mail-Nachricht zugeordnet ist, wird vom Parser übersprungen und nicht indiziert.  <br/> |
|Maximale Zeit für die Analyse eines Elements  <br/> |30 Sekunden  <br/> |Maximal 30 Sekunden dauert die Analyse eines Elements für die Indizierung. Wenn die Analysezeit 30 Sekunden überschreitet, wird das Element als teilweise indiziert markiert.  <br/> |
|Maximale Parserausgabe  <br/> |2 Millionen Zeichen  <br/> |Die maximale Textausgabe des indizierten Parsers. Wenn der Parser beispielsweise 8 Millionen Zeichen aus einem Dokument extrahiert hat, werden nur die ersten 2 Millionen Zeichen indiziert.  <br/> |
|Maximale Anmerkungstoken  <br/> |2 Mio.  <br/> |Wenn eine E-Mail-Nachricht indiziert wird, wird jedes Wort mit unterschiedlichen Verarbeitungsanweisungen kommentiert, die angeben, wie dieses Wort indiziert werden soll. Jeder Satz von Verarbeitungsanweisungen wird als Anmerkungstoken bezeichnet. Um die Dienstqualität in Office 365 zu erhalten, gibt es eine Grenze von 2 Millionen Anmerkungstoken für eine E-Mail-Nachricht.  <br/> |
|Maximale Textgröße im Index  <br/> |67 Millionen Zeichen  <br/> |Die Gesamtanzahl der Zeichen im Textkörper einer E-Mail-Nachricht und aller Anlagen. Wenn eine E-Mail-Nachricht indiziert wird, wird der ganze Text im Nachrichtentext und in allen Anlagen in einer einzelnen Zeichenfolge verkettet. Die maximale Größe dieser indizierten Zeichenfolge beträgt 67 Millionen Zeichen.  <br/> |
|Maximale Anzahl eindeutiger Token im Textkörper  <br/> |1 Million  <br/> |Wie bereits erläutert, sind Token das Ergebnis des Extrahierens von Text aus Inhalten, des Entfernens von Interpunktion und Leerzeichen und deren Aufteilung in Wörter (sogenannte Token), die im Index gespeichert sind. Der Ausdruck enthält beispielsweise  `"cat, mouse, bird, dog, dog"` 5 Token. Aber nur 4 davon sind eindeutige Token. Es gibt eine Grenze von 1 Million eindeutigen Token pro E-Mail-Nachricht, wodurch verhindert wird, dass der Index mit zufälligen Token zu groß wird.  <br/> |
|||
  
## <a name="more-information"></a>Weitere Informationen

Es gibt zusätzliche Beschränkungen im Zusammenhang mit verschiedenen Aspekten der Inhaltssuche, z. B. inhaltsindizierung. Weitere Informationen zu diesen Grenzwerten finden Sie in den folgenden Themen:

- [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md)

- [Untersuchen teilweise indizierter Elemente in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Suchgrenzwerte für SharePoint Online](/sharepoint/search-limits)

Informationen zu Inhaltssuchen finden Sie unter:
  
- [Inhaltssuche in Microsoft 365](content-search.md)

- [Suchen nach Inhalten in einem Core eDiscovery-Fall](search-for-content-in-core-ediscovery.md)

- [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)

Fallbeschränkungen im Zusammenhang mit Core eDiscovery und Advanced eDiscovery finden Sie unter:

- [Grenzwerte in Core eDiscovery](limits-core-ediscovery.md)

- [Grenzwerte in Advanced eDiscovery](limits-ediscovery20.md)
