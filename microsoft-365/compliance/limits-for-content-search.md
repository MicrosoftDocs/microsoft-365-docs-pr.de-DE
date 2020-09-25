---
title: Grenzwerte für die Inhaltssuche im Security & Compliance Center
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
description: Erfahren Sie mehr über die Grenzwerte, die für die Inhaltssuche im Security & Compliance Center in Office 365 gelten, beispielsweise die maximale Anzahl gleichzeitiger Suchvorgänge.
ms.openlocfilehash: 678f3c9613096291b5c27d89ac2d756148dd7608
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269384"
---
# <a name="limits-for-content-search-in-the-security--compliance-center"></a>Grenzwerte für die Inhaltssuche im Security & Compliance Center

> [!NOTE]
> Die Grenzwerte in diesem Thema unterscheiden sich von den aktuellen Grenzwerten für in-Place-eDiscovery in Exchange Online und für das eDiscovery Center in SharePoint Online.
  
Auf das Feature für die Inhaltssuche im Security & Compliance Center werden verschiedene Einschränkungen angewendet. Dies umfasst Suchvorgänge, die auf der Seite für die **Inhaltssuche** ausgeführt werden, und Suchvorgänge, die einem eDiscovery-Fall zugeordnet sind. Diese Grenzwerte helfen, die Integrität und Qualität von Diensten zu gewährleisten, die Organisationen bereitgestellt werden. Es gibt auch Beschränkungen im Zusammenhang mit der Indizierung von e-Mail-Nachrichten in Exchange Online für die Suche. Die Grenzwerte für die Inhaltssuche oder die e-Mail-Indizierung können nicht geändert werden, aber Sie sollten sich dessen bewusst sein, damit Sie bei der Planung, Ausführung und Problembehandlung von Inhalts suchen diese Einschränkungen berücksichtigen können.
  
## <a name="content-search-limits"></a>Grenzwerte für die Inhaltssuche

In der folgenden Tabelle sind die Such Grenzwerte im Security & Compliance Center aufgeführt.
  
|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Die maximale Anzahl von Postfächern oder Websites, die in einer einzelnen Inhaltssuche durchsucht werden können  <br/> |Kein Grenzwert <sup>1</sup> <br/> |
|Die maximale Anzahl von Inhalts suchen, die in Ihrer Organisation gleichzeitig ausgeführt werden können.  <br/> |30  <br/> |
|Die maximale Anzahl von Inhalts suchen, die ein einzelner Benutzer gleichzeitig starten kann. Dieser Grenzwert wird wahrscheinlich getroffen, wenn der Benutzer versucht, mehrere Suchvorgänge mithilfe des Befehls **Get-ComplianceSearch \| Start-ComplianceSearch** in Security & Compliance Center PowerShell zu starten.  <br/> |10    <br/> |
|Die maximale Anzahl von Elementen pro Benutzerpostfach, die auf der Vorschauseite angezeigt werden, wenn Sie die Inhalts Suchergebnisse anzeigen.  <br/> |100  <br/> |
|Die maximale Anzahl von Elementen, die in allen Benutzerpostfächern gefunden werden, die auf der Vorschauseite angezeigt werden, wenn Sie die Inhalts Suchergebnisse anzeigen. Die neuesten Elemente werden angezeigt.  <br/> |1,000  <br/> |
|Die maximale Anzahl von Benutzerpostfächern, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn mehr als 1000 Postfächer vorhanden sind, die Inhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die obersten 1000-Postfächer mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |1,000  <br/> |
|Die maximale Anzahl von Elementen, die in SharePoint und OneDrive für Unternehmen Websites gefunden werden, die auf der Vorschauseite angezeigt werden, wenn Sie die Inhalts Suchergebnisse anzeigen. Die neuesten Elemente werden angezeigt.  <br/> |200  <br/> |
|Die maximale Anzahl von Websites (in SharePoint und OneDrive für Unternehmen), die in der Vorschau für Suchergebnisse angezeigt werden können. Wenn mehr als 200 Websites insgesamt Inhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die Top 200-Websites mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |200  <br/> |
|Die maximale Anzahl von Elementen pro Postfach für Öffentliche Ordner, die auf der Vorschauseite angezeigt werden, wenn Sie die Inhalts Suchergebnisse anzeigen.  <br/> |100  <br/> |
|Die maximale Anzahl von Elementen, die in allen Postfächern für Öffentliche Ordner gefunden werden, die auf der Vorschauseite angezeigt werden, wenn Sie die Inhalts Suchergebnisse anzeigen.  <br/> |200  <br/> |
|Die maximale Anzahl von öffentlichen Postfächern, für die eine Vorschau für Suchergebnisse angezeigt werden kann. Wenn mehr als 500 Postfächer für öffentliche Ordnerinhalte enthalten, die mit der Suchabfrage übereinstimmen, stehen nur die obersten 500-Postfächer für Öffentliche Ordner mit den meisten Suchergebnissen für die Vorschau zur Verfügung.  <br/> |500  <br/> |
|Die maximale Anzahl von Zeichen für die Suchabfrage (einschließlich Operatoren und Bedingungen) für eine Inhaltssuche.  <br/><br/> **Hinweis:** Dieser Grenzwert wird wirksam, nachdem die Abfrage erweitert wurde, was bedeutet, dass die Abfrage für jedes der Schlüsselwörter erweitert wird. Wenn beispielsweise eine Suchabfrage 15 Schlüsselwörter und zusätzliche Parameter und Bedingungen enthält, wird die Abfrage 15 Mal erweitert, wobei jeweils die anderen Parameter und Bedingungen in der Abfrage enthalten sind. Obwohl die Anzahl der Zeichen in der Suchabfrage möglicherweise unter dem Grenzwert liegt, ist dies die Erweiterte Abfrage, die dazu beitragen kann, diesen Grenzwert zu überschreiten.  <br/> |**Postfächer:** 10.000  <br/> **Websites:** 4.000 beim Durchsuchen aller Websites oder 2.000 bei der Suche bis zu 20 Websites <sup>2</sup> <br/> |
|Maximale Anzahl von Varianten, die zurückgegeben werden, wenn ein Präfix Platzhalter verwendet wird, um eine exakte Phrase in einer Suchabfrage oder bei Verwendung eines Präfix Platzhalters und des **near** Boolean-Operators zu suchen.  <br/> |10.000 <sup>3</sup> <br/> |
|Die minimale Anzahl von Alphazeichen für Präfix Platzhalter; beispielsweise,  `time*` ,  `one*` , oder  `set*` .  <br/> |3  <br/> |
|Die maximale Anzahl von Postfächern in einer Inhaltssuche, in der Sie Elemente löschen können, indem Sie die Aktion "suchen und löschen" ausführen (mit dem Befehl " **New-ComplianceSearchAction-Purge** "). Wenn die Inhaltssuche, für die Sie eine Löschaktion durchführen, mehr Quellpostfächer als diesen Grenzwert enthält, schlägt die Löschaktion fehl. Weitere Informationen zur Suche und Bereinigung finden Sie unter [Suchen nach und Löschen von e-Mail-Nachrichten in Ihrer Organisation](search-for-and-delete-messages-in-your-organization.md).  <br/> |50.000  <br/> |

> [!NOTE]
> <sup>1</sup> obwohl Sie eine unbegrenzte Anzahl von Postfächern in einer einzigen Suche durchsuchen können, können Sie die exportierten Suchergebnisse nur mit dem eDiscovery-Export Tool in Office 365 Security & Compliance Center oder dem Microsoft 365 Compliance Center von maximal 100.000 Postfächern herunterladen. Zum Herunterladen der Suchergebnisse aus mehr als 100.000 Postfächern müssen Sie Security & Compliance Center PowerShell verwenden. Weitere Informationen und ein Beispielskript finden Sie unter [Exportieren von Ergebnissen aus mehr als 100.000 Postfächern](export-search-results.md#exporting-results-from-more-than-100000-mailboxes). <br/><br/> <sup>2</sup> beim Durchsuchen von SharePoint-und OneDrive für Unternehmen-Speicherorte werden die Zeichen in den URLs der gesuchten Websites mit diesem Grenzwert berechnet. <br/><br/> <sup>3</sup> bei nicht-Phrase-Abfragen (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) wird ein spezieller Präfix Index verwendet. Dies weist darauf hin, dass ein Wort in einem Dokument auftritt, aber nicht dort, wo es im Dokument vorkommt. Um eine Phrasenabfrage (ein Stichwort Wert mit doppelten Anführungszeichen) durchführen zu können, müssen wir die Position im Dokument für die Wörter im Ausdruck vergleichen. Dies bedeutet, dass der Präfix Index für Phrase-Abfragen nicht verwendet werden kann. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, zu denen das Präfix erweitert wird. beispielsweise  `"time*"` kann auf erweitert werden  `"time OR timer OR times OR timex OR timeboxed OR …"` . Die maximale Anzahl von Varianten, in die das Wort erweitert werden kann (nicht die Anzahl der Dokumente, die der Abfrage entsprechen) ist 10.000. Für nicht-Phrasen-Ausdrücke gibt es keine Obergrenze. 
  
## <a name="indexing-limits-for-email-messages"></a>Indizierungs Grenzwerte für e-Mail-Nachrichten

In der folgenden Tabelle werden die Grenzwerte für die Indizierung beschrieben, die dazu führen können, dass eine e-Mail-Nachricht als nicht indexiertes Element oder ein teilweise indiziertes Element in den Ergebnissen einer Inhaltssuche zurückgegeben wird.
  
|**Indizierungs Grenzwert**|**Maximalwert**|**Beschreibung**|
|:-----|:-----|:-----|
|Maximale Anlagengröße|150 MB  <br/> |Die maximale Größe einer e-Mail-Anlage, die für die Indizierung analysiert wird. Alle Anlagen, die diesen Grenzwert überschreiten, werden nicht für die Indizierung analysiert, und die Nachricht mit der Anlage wird als teilweise indiziert markiert.  <br/> <br/>**Hinweis:** Die Analyse ist der Vorgang, bei dem der Indexdienst Text aus der Anlage extrahiert, unnötige Zeichen wie Interpunktion und Leerzeichen entfernt und dann den Text in Wörter (in einem Prozess namens "Tokenisierung") aufteilt, die dann im Index gespeichert werden.           |
|Maximale Anzahl von Anlagen  <br/> |250  <br/> |Die maximale Anzahl von Dateien, die an eine e-Mail-Nachricht angehängt werden, die für die Indizierung analysiert wird. Wenn eine Nachricht mehr als 250 Anlagen aufweist, werden die ersten 250-Anlagen analysiert und indiziert, und die Nachricht wird als teilweise indiziert gekennzeichnet, da Sie über zusätzliche Anlagen verfügt, die nicht analysiert wurden.  <br/> |
|Maximale Anlagen Tiefe  <br/> |30  <br/> |Die maximale Anzahl geschachtelter Anlagen, die analysiert werden. Wenn beispielsweise einer e-Mail-Nachricht eine andere Nachricht angefügt ist und die angefügte Nachricht ein angefügtes Word-Dokument enthält, wird das Word-Dokument und die angefügte Nachricht indiziert. Dieses Verhalten wird für bis zu 30 geschachtelte Anlagen fortgesetzt.  <br/> |
|Maximale Anzahl angefügter Bilder  <br/> |0  <br/> |Ein Bild, das an eine e-Mail-Nachricht angefügt ist, wird vom Parser übersprungen und nicht indiziert.  <br/> |
|Maximale Zeitaufwand für die Analyse eines Elements  <br/> |30 Sekunden  <br/> |Für die Analyse eines Elements zur Indizierung werden maximal 30 Sekunden verwendet. Wenn die Analysezeit 30 Sekunden überschreitet, wird das Element als teilweise indiziert markiert.  <br/> |
|Maximale Parser-Ausgabe  <br/> |2 Millionen Zeichen  <br/> |Die maximale Textausgabe des indizierten Parsers. Wenn der Parser beispielsweise 8 Millionen Zeichen aus einem Dokument extrahiert hat, werden nur die ersten 2 Millionen Zeichen indiziert.  <br/> |
|Maximale Anmerkungs Token  <br/> |2 Millionen  <br/> |Wenn eine e-Mail-Nachricht indiziert wird, wird jedes Wort mit unterschiedlichen Verarbeitungsanweisungen versehen, die angeben, wie dieses Wort indiziert werden soll. Jeder Sätze von Verarbeitungsanweisungen wird als Anmerkungs Token bezeichnet. Um die Dienstqualität in Office 365 beizubehalten, gibt es einen Grenzwert von 2 Millionen-Anmerkungs Token für eine e-Mail-Nachricht.  <br/> |
|Maximale Körpergröße im Index  <br/> |67 Millionen Zeichen  <br/> |Die Gesamtzahl der Zeichen im Textkörper einer e-Mail-Nachricht und aller Anlagen. Wenn eine e-Mail-Nachricht indiziert wird, wird der gesamte Text im Nachrichtentext und in allen Anlagen in einer einzigen Zeichenfolge verkettet. Die maximale Größe dieser Zeichenfolge, die indiziert wird, ist 67 Millionen Zeichen.  <br/> |
|Maximale Anzahl eindeutiger Token im Textkörper  <br/> |1 Mio.  <br/> |Wie bereits erläutert, sind Token das Ergebnis des Extrahierens von Text aus dem Inhalt, dem Entfernen von Satzzeichen und Leerzeichen und der anschließende Aufteilung in Wörter (sogenannte Token), die im Index gespeichert sind. Der Ausdruck enthält beispielsweise  `"cat, mouse, bird, dog, dog"` 5 Token. Aber nur 4 von diesen sind eindeutige Token. Es gibt ein Limit von 1 Million eindeutigen Token pro e-Mail-Nachricht, wodurch verhindert werden kann, dass der Index zu groß wird mit zufälligen Token.  <br/> |
  
## <a name="more-information"></a>Weitere Informationen

Es gibt zusätzliche Beschränkungen im Zusammenhang mit unterschiedlichen Aspekten der Inhaltssuche, beispielsweise Exportieren von Suchergebnissen und Inhaltsindizierung. Eine Beschreibung dieser Grenzwerte finden Sie in den folgenden Themen:
  
- [Exportieren von Inhaltssuchergebnissen ](export-search-results.md#export-limits)

- [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md)

- [Untersuchen von teilweise indizierten Elementen in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Such Grenzwerte für SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits)

Informationen zu Inhalts suchen finden Sie unter:
  
- [Inhaltssuche in Microsoft 365](content-search.md)

- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
