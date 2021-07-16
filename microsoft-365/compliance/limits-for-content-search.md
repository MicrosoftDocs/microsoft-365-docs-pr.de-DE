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
description: Erfahren Sie mehr über die Grenzwerte, die für die Inhaltssuche und die Core eDiscovery-Features im Microsoft 365 Compliance Center gelten.
ms.openlocfilehash: db0f24d66fd7dc23a82a5ededfcfbc4d9edabad7
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463985"
---
# <a name="limits-for-ediscovery-search"></a>Grenzwerte für die eDiscovery-Suche

Auf eDiscovery-Suchtools im Microsoft 365 Compliance Center werden verschiedene Grenzwerte angewendet. Dazu gehören Suchvorgänge, die auf der **Inhaltssuche-Seite** ausgeführt werden, und Suchvorgänge, die einem eDiscovery-Fall auf der **Core eDiscovery-Seite** zugeordnet sind. Diese Grenzwerte tragen dazu bei, den Status und die Qualität der für Organisationen bereitgestellten Dienste aufrechtzuerhalten. Es gibt auch Beschränkungen im Zusammenhang mit der Indizierung von E-Mail-Nachrichten in Exchange Online für die Suche. Sie können die Grenzwerte für eDiscovery-Suchvorgänge oder E-Mail-Indizierung nicht ändern, sollten sie jedoch beachten, damit Sie diese Grenzwerte bei der Planung, Ausführung und Problembehandlung von eDiscovery-Suchvorgängen berücksichtigen können.

Informationen zu Grenzwerten im Zusammenhang mit dem Advanced eDiscovery-Tool finden Sie [unter "Grenzwerte" in Advanced eDiscovery](limits-ediscovery20.md)

## <a name="search-limits"></a>Suchgrenzen

In der folgenden Tabelle sind die Suchgrenzwerte aufgeführt, wenn Sie das Inhaltssuchtool im Microsoft 365 Compliance Center und für Suchvorgänge verwenden, die einem Core eDiscovery-Fall zugeordnet sind.

<br>

****

|Beschreibung der Beschränkung|Grenze|
|---|---|
|Die maximale Anzahl von Postfächern oder Websites, die in einer einzigen Suche durchsucht werden können|Keine Beschränkung <sup>1</sup>|
|Die maximale Anzahl von Suchvorgängen, die gleichzeitig in Ihrer Organisation ausgeführt werden können.|30|
|Die maximale Anzahl organisationsweiter Suchvorgänge, die gleichzeitig ausgeführt werden können.|3|
|Die maximale Anzahl von Suchvorgängen, die ein einzelner Benutzer gleichzeitig starten kann. Dieser Grenzwert wird höchstwahrscheinlich erreicht, wenn der Benutzer versucht, mehrere Suchvorgänge mithilfe des Befehls **"Get-ComplianceSearch \| Start-ComplianceSearch"** in Security & Compliance Center PowerShell zu starten.|10 |
|Die maximale Anzahl von Elementen pro Benutzerpostfach, die auf der Vorschauseite angezeigt werden, wenn inhaltssuchergebnisse in der Vorschau angezeigt werden.|100|
|Die maximale Anzahl von Elementen in allen Benutzerpostfächern, die bei der Vorschau der Suchergebnisse möglicherweise auf der Vorschauseite angezeigt werden können. Die neuesten Elemente werden angezeigt.|1.000 <sup>2</sup>|
|Die maximale Anzahl von Benutzerpostfächern, die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn es mehr als 1000 Postfächer gibt, die Inhalte enthalten, die der Suchabfrage entsprechen, stehen höchstens nur die obersten 1000 Postfächer mit den meisten Suchergebnissen für die Vorschau zur Verfügung.|1,000|
|Die maximale Anzahl von Elementen in SharePoint und OneDrive for Business Websites, die bei der Vorschau der Suchergebnisse auf der Vorschauseite angezeigt werden. Die neuesten Elemente werden angezeigt.|200|
|Die maximale Anzahl von Websites (in SharePoint und OneDrive for Business), die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn mehr als 200 Websites insgesamt Inhalte enthalten, die der Suchabfrage entsprechen, stehen nur die 200 wichtigsten Websites mit den meisten Suchergebnissen für die Vorschau zur Verfügung.|200|
|Die maximale Anzahl von Elementen pro Postfach für öffentliche Ordner, die auf der Vorschauseite angezeigt werden, wenn inhaltssuchergebnisse in der Vorschau angezeigt werden.|100|
|Die maximale Anzahl von Elementen in allen Postfächern für öffentliche Ordner, die auf der Vorschauseite angezeigt werden, wenn die Inhaltssuchergebnisse in der Vorschau angezeigt werden.|200|
|Die maximale Anzahl von Postfächern für öffentliche Ordner, die für Suchergebnisse in der Vorschau angezeigt werden können. Wenn es mehr als 500 Postfächer für öffentliche Ordner gibt, die Inhalte enthalten, die der Suchabfrage entsprechen, stehen nur die 500 obersten Postfächer für öffentliche Ordner mit den meisten Suchergebnissen für die Vorschau zur Verfügung.|500|
|Die maximale Anzahl von Zeichen für die Suchabfrage (einschließlich Operatoren und Bedingungen) für eine Suche. <p> **Hinweis:** Dieser Grenzwert wird wirksam, nachdem die Abfrage erweitert wurde, und enthält Zeichen aus der Stichwortabfrage, alle auf den Benutzer angewendeten Suchberechtigungsfilter und die URLs aller Websitespeicherorte. Dies bedeutet, dass die Abfrage für jedes der Schlüsselwörter erweitert wird. Wenn eine Suchabfrage beispielsweise 15 Schlüsselwörter und zusätzliche Parameter und Bedingungen aufweist, wird die Abfrage um 15 Mal erweitert, jeweils mit den anderen Parametern und Bedingungen in der Abfrage. Obwohl die Anzahl der Zeichen in der Suchabfrage unter dem Grenzwert liegen kann, kann die erweiterte Abfrage dazu beitragen, diesen Grenzwert zu überschreiten.|**Postfächer:** 10.000. <p> **Websites:** 4.000 beim Durchsuchen aller Websites oder 2.000 bei der Suche von bis zu 20 Websites. <sup>3</sup>|
|Maximale Anzahl von Varianten, die zurückgegeben werden, wenn ein Präfix-Platzhalter verwendet wird, um nach einem exakten Ausdruck in einer Suchabfrage zu suchen, oder wenn ein Präfix-Platzhalter und der **NEAR-Operator** vom Typ Boolean verwendet werden.|10.000 <sup>4</sup>|
|Die mindeste Anzahl von Alphazeichen für Präfix-Platzhalter; Beispielsweise `time*` , `one*` oder `set*` .|3|
|Die maximale Anzahl von Postfächern in einer Suche, in denen Sie Elemente löschen können, indem Sie eine "Suchen und Löschen"-Aktion ausführen (mithilfe des Befehls **"New-ComplianceSearchAction -Purge").** Wenn die Suche, für die Sie eine Bereinigungsaktion durchführen, mehr Quellpostfächer als diese Grenze aufweist, schlägt die Bereinigungsaktion fehl. Weitere Informationen zum Suchen und Löschen finden Sie unter Suchen nach und Löschen von [E-Mail-Nachrichten in Ihrer Organisation.](search-for-and-delete-messages-in-your-organization.md)|50.000|
|Die maximale Anzahl von Speicherorten in einer Suche, aus denen Sie Elemente exportieren können. Wenn die Suche, die Sie exportieren, mehr Speicherorte als diesen Grenzwert aufweist, schlägt der Export fehl. Weitere Informationen finden Sie unter [Exportieren von Inhaltssuchergebnissen.](export-search-results.md)|100,000|
|||

> [!NOTE]
> <sup>1</sup> Obwohl Sie eine unbegrenzte Anzahl von Postfächern in einer einzigen Suche durchsuchen können, können Sie die exportierten Suchergebnisse nur aus maximal 100.000 Postfächern mithilfe des eDiscovery-Exporttools im Microsoft 365 Compliance Center herunterladen.
>
> <sup>2</sup> Der Zweck der Vorschauseite besteht darin, ein begrenztes Beispiel der Ergebnisse anzuzeigen. Selbst bei umfangreichen Suchvorgängen mit Tausenden von Ergebnissen kann und wird die Anzahl der Elemente, die auf der Vorschauseite angezeigt werden, viel kleiner als der maximal mögliche Wert von 1000 sein. Um die vollständigen Suchergebnisse anzuzeigen, müssen Sie die Ergebnisse exportieren.
>
> <sup>3</sup> Bei der Suche nach SharePoint und OneDrive for Business Speicherorten werden die Zeichen in den URLs der durchsuchten Websites mit diesem Grenzwert gezählt.
>
> <sup>4</sup> Für Nicht-Phrasenabfragen (ein Schlüsselwortwert, der keine doppelten Anführungszeichen verwendet) verwenden wir einen speziellen Präfixindex. Dies teilt uns mit, dass ein Wort in einem Dokument vorkommt, aber nicht an der Stelle, an der es im Dokument vorkommt. Um eine Begriffsabfrage (einen Schlüsselwortwert mit doppelten Anführungszeichen) auszuführen, müssen wir die Position im Dokument mit den Wörtern im Ausdruck vergleichen. Dies bedeutet, dass wir den Präfixindex nicht für Phrasenabfragen verwenden können. In diesem Fall erweitern wir die Abfrage intern mit allen möglichen Wörtern, auf die das Präfix erweitert wird. Kann z. `"time*"` B. bis zu `"time OR timer OR times OR timex OR timeboxed OR ..."` . Die maximale Anzahl von Varianten, in die das Wort erweitert werden kann (nicht die Anzahl der Dokumente, die der Abfrage entsprechen) ist 10.000. Es gibt keine Obergrenze für Ausdrücke, die keine Ausdrücke sind.

## <a name="search-times"></a>Suchzeiten

Microsoft sammelt Leistungsinformationen für Suchvorgänge, die von allen Organisationen ausgeführt werden. Obwohl sich die Komplexität einer Suchabfrage negativ auf die Suchzeiten auswirken kann, ist die Anzahl der durchsuchten Postfächer der Faktor, der die Suchdauer am stärksten beeinflusst. Obwohl Microsoft keinen Servicelevelvertrag für Suchzeiten bereitstellt, werden in der folgenden Tabelle die durchschnittlichen Suchzeiten für Sammlungssuchen basierend auf der Anzahl der in der Suche enthaltenen Postfächer aufgeführt.

<br>

****

|Anzahl Postfächer|Durchschnittliche Suchzeit|
|---|---|
|100|30 Sekunden|
|1.000|45 Sekunden|
|10.000|4 Minuten|
|25.000|10 Minuten|
|50.000|20 Minuten|
|100.000|25 Minuten|
|||

## <a name="export-limits"></a>Exportgrenzwerte

In der folgenden Tabelle sind die Grenzwerte beim Exportieren der Ergebnisse einer Inhaltssuche aufgeführt. Diese Grenzwerte gelten auch, wenn Sie Inhalte aus einem Core eDiscovery-Fall exportieren.

<br>

****

|Beschreibung der Beschränkung|Grenze|
|---|---|
|Maximale Menge an exportierbaren Daten aus einer einzigen Suche  <p> **Hinweis:** Wenn die Suchergebnisse größer als 2 TB sind, sollten Sie die Verwendung von Datumsbereichen oder anderen Filtertypen in Betracht ziehen, um die Gesamtgröße der Suchergebnisse zu verringern.|2 TB|
|Maximale Exportdauer für eine Organisation an einem einzigen Tag <p> **Hinweis:** Dieser Grenzwert wird täglich um 12:00 Uhr UTC zurückgesetzt.|2 TB|
|Maximale Anzahl gleichzeitiger Exporte, die gleichzeitig innerhalb Ihrer Organisation ausgeführt werden können <p> **Hinweis:** Ausführen einer **Exportanzahl nur für Berichte** mit gesamter Anzahl gleichzeitiger Exporte für Ihre Organisation. Wenn drei Benutzer jeweils drei Exporte ausführen, kann nur ein weiterer Export ausgeführt werden. Unabhängig davon, ob ein Bericht oder Suchergebnisse exportiert werden, können keine weiteren Exporte ausgeführt werden, bis ein Bericht abgeschlossen ist.|10 |
|Maximale Exporte, die ein einzelner Benutzer gleichzeitig ausführen kann|3|
|Maximale Anzahl von Postfächern für Suchergebnisse, die mit dem eDiscovery-Exporttool heruntergeladen werden können|100,000|
|Maximale Größe der PST-Datei, die exportiert werden kann <p> **Hinweis:** Wenn die Suchergebnisse aus dem Postfach eines Benutzers größer als 10 GB sind, werden die Suchergebnisse für das Postfach in zwei (oder mehr) separaten PST-Dateien exportiert. Wenn Sie alle Suchergebnisse in einer einzigen PST-Datei exportieren möchten, wird die PST-Datei in zusätzliche PST-Dateien gespuckt, wenn die Gesamtgröße der Suchergebnisse größer als 10 GB ist. Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows Registrierung auf dem Computer bearbeiten, den Sie zum Exportieren der Suchergebnisse verwenden. Siehe [Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen.](change-the-size-of-pst-files-when-exporting-results.md) Die Suchergebnisse aus einem bestimmten Postfach werden nur dann auf mehrere PST-Dateien aufgeteilt, wenn der Inhalt eines einzelnen Postfachs mehr als 10 GB beträgt. Wenn Sie die Suchergebnisse in einer PST-Datei exportieren möchten, die alle Nachrichten in einem einzigen Ordner enthält und die Suchergebnisse größer als 10 GB sind, werden die Elemente weiterhin in chronologischer Reihenfolge organisiert, sodass sie basierend auf dem Sendedatum in zusätzliche PST-Dateien gespuckt werden.|10 GB|
|Rate, mit der Suchergebnisse aus Postfächern und Websites an einen von Microsoft bereitgestellten Azure Storage Speicherort hochgeladen werden.|Maximal 2 GB pro Stunde|
|||

## <a name="indexing-limits-for-email-messages"></a>Indizierungsgrenzwerte für E-Mail-Nachrichten

In der folgenden Tabelle werden die Indizierungsgrenzwerte beschrieben, die dazu führen können, dass eine E-Mail-Nachricht als nicht indiziertes Element oder als teilweise indiziertes Element in den Ergebnissen einer Inhaltssuche zurückgegeben wird.

<br>

****

|Grenzwert für die Indizierung|Maximalwert|Beschreibung|
|---|---|---|
|Maximale Anlagengröße|150 MB|Die maximale Größe einer E-Mail-Anlage, die für die Indizierung analysiert wird. Anlagen, die größer als dieser Grenzwert sind, werden nicht für die Indizierung analysiert, und die Nachricht mit der Anlage wird als teilweise indiziert gekennzeichnet. <p> **Hinweis:** Die Analyse ist der Prozess, bei dem der Indizierungsdienst Text aus der Anlage extrahiert, unnötige Zeichen wie Satzzeichen und Leerzeichen entfernt und den Text dann in Wörter (in einem Prozess namens Tokenisierung) teilt, die dann im Index gespeichert werden.|
|Maximale Anzahl von Anlagen|250|Die maximale Anzahl von Dateien, die an eine E-Mail-Nachricht angefügt sind, die für die Indizierung analysiert wird. Wenn eine Nachricht mehr als 250 Anlagen enthält, werden die ersten 250 Anlagen analysiert und indiziert, und die Nachricht wird als teilweise indiziert markiert, da sie zusätzliche Anlagen hatte, die nicht analysiert wurden.|
|Maximale Anlagentiefe|30|Die maximale Anzahl geschachtelter Anlagen, die analysiert werden. Wenn an eine E-Mail-Nachricht beispielsweise eine weitere Nachricht angefügt ist und die angefügte Nachricht über ein angefügtes Word-Dokument verfügt, werden das Word-Dokument und die angefügte Nachricht indiziert. Dieses Verhalten gilt für bis zu 30 geschachtelte Anlagen.|
|Maximale Anzahl angefügter Bilder|0|Ein Bild, das an eine E-Mail-Nachricht angefügt ist, wird vom Parser übersprungen und nicht indiziert.|
|Maximale Zeitaufwand für die Analyse eines Elements|30 Sekunden|Es werden maximal 30 Sekunden für die Analyse eines Elements für die Indizierung aufgewendet. Wenn die Analysezeit 30 Sekunden überschreitet, wird das Element als teilweise indiziert markiert.|
|Maximale Parserausgabe|2 Millionen Zeichen|Die maximale Textausgabemenge des indizierten Parsers. Wenn der Parser beispielsweise 8 Millionen Zeichen aus einem Dokument extrahiert hat, werden nur die ersten 2 Millionen Zeichen indiziert.|
|Maximale Anzahl von Anmerkungstoken|2 Mio.|Wenn eine E-Mail-Nachricht indiziert wird, wird jedes Wort mit unterschiedlichen Verarbeitungsanweisungen kommentiert, die angeben, wie dieses Wort indiziert werden soll. Jeder Satz von Verarbeitungsanweisungen wird als Anmerkungstoken bezeichnet. Um die Dienstqualität in Office 365 aufrechtzuerhalten, gibt es ein Limit von 2 Millionen Anmerkungstoken für eine E-Mail-Nachricht.|
|Maximale Textkörpergröße im Index|67 Millionen Zeichen|Die Gesamtanzahl der Zeichen im Textkörper einer E-Mail-Nachricht und aller zugehörigen Anlagen. Wenn eine E-Mail-Nachricht indiziert wird, wird der gesamte Text im Nachrichtentext und in allen Anlagen in einer einzigen Zeichenfolge verkettet. Die maximale Größe dieser indizierten Zeichenfolge beträgt 67 Millionen Zeichen.|
|Maximale Anzahl eindeutiger Token im Textkörper|1 Million|Wie zuvor erläutert, sind Token das Ergebnis des Extrahierens von Text aus Inhalten, entfernen von Interpunktionszeichen und Leerzeichen und teilen sie dann in Wörter (so genannte Token), die im Index gespeichert sind. Beispielsweise enthält der Ausdruck `"cat, mouse, bird, dog, dog"` 5 Token. Aber nur 4 davon sind eindeutige Token. Es gibt ein Limit von 1 Million eindeutigen Token pro E-Mail-Nachricht, wodurch verhindert wird, dass der Index mit zufälligen Token zu groß wird.|
|||

## <a name="more-information"></a>Weitere Informationen

Es gibt zusätzliche Grenzwerte im Zusammenhang mit verschiedenen Aspekten der Suche nach Inhalten, z. B. der Inhaltsindizierung. Weitere Informationen zu diesen Grenzwerten finden Sie in den folgenden Themen:

- [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md)

- [Untersuchen teilweise indizierter Elemente in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Suchgrenzwerte für SharePoint Online](/sharepoint/search-limits)

Informationen zu Inhaltssuchen finden Sie unter:

- [Inhaltssuche in Microsoft 365](content-search.md)

- [Suchen nach Inhalten in einem Core eDiscovery-Fall](search-for-content-in-core-ediscovery.md)

- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)

Fallbeschränkungen im Zusammenhang mit Core eDiscovery und Advanced eDiscovery finden Sie unter:

- [Grenzwerte in Core eDiscovery](limits-core-ediscovery.md)

- [Grenzwerte in Advanced eDiscovery](limits-ediscovery20.md)
