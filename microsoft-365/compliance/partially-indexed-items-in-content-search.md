---
title: Teilweise indizierte Elemente in der Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Informationen zu nicht indizierten Elementen in Exchange und SharePoint, die Sie in eine Inhaltssuche einschließen können, die über das Security & Compliance Center ausgeführt wird.
ms.openlocfilehash: d4d9cfec03c4d7ca5af7ee68b077985ffb5d97dc
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358557"
---
# <a name="partially-indexed-items-in-content-search"></a>Teilweise indizierte Elemente in der Inhaltssuche

Eine Inhaltssuche, die Sie im Security & Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen. Teilweise indizierte Elemente sind Exchange-Postfachelemente und Dokumente in SharePoint und OneDrive für Unternehmen Websites, die aus irgendeinem Grund nicht vollständig für die Suche indiziert wurden. In Exchange enthält ein teilweise indiziertes Element normalerweise eine Datei (eines Dateityps, der nicht indiziert werden kann), die an eine e-Mail-Nachricht angefügt ist. Hier sind einige andere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine Suche ausführen: 
  
- Der Dateityp wird nicht erkannt oder wird nicht für die Indizierung unterstützt.
    
-  Nachrichten weisen eine angefügte Datei ohne einen gültigen Handler auf, beispielsweise Bilddateien; Dies ist die häufigste Ursache für teilweise indizierte e-Mail-Elemente. 
    
- Der Dateityp wird für die Indizierung unterstützt, aber es ist ein Indizierungsfehler für eine bestimmte Datei aufgetreten.
    
- Die E-Mail enthält zu viele Dateien im Anhang.
    
- Die an die E-Mail angehängte Datei ist zu groß.
    
- Eine Datei wurde mit Technologien von anderen Anbietern als Microsoft verschlüsselt.
    
- Eine Datei ist kennwortgeschützt.
    
> [!NOTE]
> Die meisten Organisationen haben weniger als 1% des Inhalts auf dem Datenträger und weniger als 12% nach der Größe, die teilweise indiziert ist. Der Grund für den Unterschied zwischen Volumen und Größe besteht darin, dass größere Dateien eine höhere Wahrscheinlichkeit enthalten, Inhalte zu enthalten, die nicht vollständig indiziert werden können. 
  
Für rechtliche Untersuchungen muss Ihre Organisation möglicherweise teilweise indizierte Elemente überprüfen. Sie können auch angeben, ob teilweise indizierte Elemente beim Exportieren von Suchergebnissen auf einen lokalen Computer oder beim Vorbereiten der Ergebnisse für die Analyse mit Advanced eDiscovery angegeben werden sollen. Weitere Informationen finden Sie unter unter [Suchen von teilweise indizierten Elementen in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Für die Suche nicht indizierte Dateitypen

Bestimmte Dateitypen wie Bitmap- oder MP3-Dateien enthalten keinen zu indizierenden Inhalt. Folglich führen die Such Indizierungsserver in Exchange und SharePoint keine Volltextindizierung für diese Dateitypen aus. Diese Dateitypen werden als nicht unterstützte Dateitypen betrachtet. Es gibt außerdem Dateitypen, für die die Volltextindizierung deaktiviert wurde (entweder standardmäßig oder durch den Administrator). Nicht unterstützte und deaktivierte Dateitypen werden in Inhalts suchen als nicht indizierte Elemente bezeichnet. Wie bereits erwähnt, können teilweise indizierte Elemente in die Gruppe der Suchergebnisse einbezogen werden, wenn Sie eine Suche ausführen, die Suchergebnisse auf einen lokalen Computer exportieren oder Suchergebnisse für Advanced eDiscovery vorbereiten. 
  
Eine Liste von unterstützten und deaktivierten Dateiformaten finden Sie in den folgenden Themen:
  
- **Exchange**  -  [Von der Exchange-Suche indizierte Dateiformate](https://go.microsoft.com/fwlink/p/?LinkID=386618)
    
- **Exchange**  -  [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)
    
- **SharePoint**  -  [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
    

  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Nachrichten und Dokumente mit teilweise indizierten Dateitypen können in den Suchergebnissen zurückgegeben werden

Nicht jede e-Mail-Nachricht mit einer teilweise indizierten Dateianlage oder jedem teilweise indizierten SharePoint-Dokument wird automatisch als teilweise indiziertes Element zurückgegeben. Das liegt daran, dass andere Nachrichten-oder Dokumenteigenschaften, wie die **Subject** -Eigenschaft in e-Mail-Nachrichten und die Eigenschaften **Title** oder **Author** für Dokumente indiziert und zur Durchsuchung verfügbar sind. Eine Stichwortsuche für "Financial" gibt beispielsweise Elemente mit einer teilweise indizierten Dateianlage zurück, wenn dieses Stichwort im Betreff einer e-Mail-Nachricht oder im Dateinamen oder Titel eines Dokuments angezeigt wird. Wenn das Schlüsselwort jedoch nur im Textkörper der Datei angezeigt wird, wird die Nachricht oder das Dokument als teilweise indiziertes Element zurückgegeben. 
  
Ebenso werden Nachrichten mit teilweise indizierten Dateianlagen und Dokumenten eines teilweise indizierten Dateityps in Suchergebnisse eingeschlossen, wenn andere Nachrichten-oder Dokumenteigenschaften, die indiziert und durchsuchbar sind, die Suchkriterien erfüllen. Zu den Nachrichteneigenschaften, die für die Suche indiziert werden, gehören Sende- und Empfangsdatum, Absender und Empfänger, Dateiname von Anhängen sowie der Nachrichtentext. Zu den für die Suche indizierten Dokumenteigenschaften gehören erstellte und geänderte Daten. Obwohl eine Nachrichtenanlage möglicherweise ein teilweise indiziertes Element ist, wird die Nachricht in die regulären Suchergebnisse eingeschlossen, wenn der Wert anderer Nachrichten-oder Dokumenteigenschaften mit den Suchkriterien übereinstimmt.
  
Eine Liste der e-Mail-und Dokumenteigenschaften, nach denen Sie mithilfe der Suchfunktion im Security & Compliance Center suchen können, finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Teilweise indizierte Elemente, die in den Suchergebnissen enthalten sind

Ihre Organisation muss möglicherweise eine zusätzliche Analyse für teilweise indizierte Elemente identifizieren und ausführen, um zu bestimmen, was diese sind, was Sie enthalten und ob Sie für eine bestimmte Untersuchung relevant sind. Wie bereits erläutert, werden die teilweise indizierten Elemente in den durchsuchten Inhaltsspeicherorten automatisch in die geschätzten Suchergebnisse einbezogen. Sie haben die Möglichkeit, diese teilweise indizierten Elemente beim Exportieren von Suchergebnissen oder beim Vorbereiten der Suchergebnisse für Advanced eDiscovery einzubeziehen.
  
Beachten Sie bei teilweise indizierten Elementen Folgendes:
  
- Wenn Sie eine Inhaltssuche ausführen, werden die Gesamtzahl und die Größe der teilweise indizierten Exchange-Elemente (die von der Suchabfrage zurückgegeben werden) in Suchstatistiken im Detailbereich angezeigt und als **indizierte Elemente**gekennzeichnet. Beachten Sie, dass Statistiken zu teilweise indizierten Elementen, die im Detailbereich angezeigt werden, nicht teilweise indizierte Elemente in SharePoint oder OneDrive enthalten.
    
- Wenn es sich bei der Suche, aus der Sie Ergebnisse exportieren, um die Suche nach bestimmten Inhaltsspeicherorten oder um alle inhaltsspeicherorte in Ihrer Organisation handelt, werden nur die nicht indizierten Elemente aus Inhaltsspeicherorten exportiert, die Elemente enthalten, die mit den Suchkriterien übereinstimmen. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Der Grund hierfür ist, dass das Exportieren von teilweise indizierten Elementen aus vielen Orten in der Organisation die Wahrscheinlichkeit von Exportfehlern erhöht und die Zeit für den Export und den Download der Suchergebnisse erhöht.
    
    Um teilweise indizierte Elemente aus allen Inhaltsspeicherorten für eine Suche zu exportieren, konfigurieren Sie die Suche so, dass alle Elemente zurückgegeben werden (indem Sie Stichwörter aus der Suchabfrage entfernen), und exportieren Sie dann nur teilweise indizierte Elemente, wenn Sie die Suchergebnisse exportieren (indem Sie auf **nur Elemente mit einem unbekannten Format, verschlüsselt oder aus anderen Gründen** unter **Ausgabeoptionen**indiziert wurden).
    
- Wenn Sie alle Postfachelemente in die Suchergebnisse einschließen möchten oder wenn eine Suchabfrage keine Stichwörter oder nur einen Datumsbereich angibt, werden teilweise indizierte Elemente möglicherweise nicht in die PST-Datei kopiert, die die teilweise indizierten Elemente enthält. Dies liegt daran, dass alle Elemente, einschließlich der teilweise indizierten Elemente, automatisch in die regulären Suchergebnisse eingeschlossen werden.
    
- Teilweise indizierte Elemente stehen in der Vorschau nicht zur Verfügung. Sie müssen die Suchergebnisse exportieren, um teilweise indizierte Elemente anzuzeigen, die von der Suche zurückgegeben werden.

Wenn Sie außerdem Suchergebnisse exportieren und teilweise indizierte Elemente in den Export einschließen, werden teilweise indizierte Elemente aus SharePoint-Elementen in einen Ordner mit dem Namen "nicht **gecrawlt**" exportiert. Wenn Sie teilweise indizierte Exchange-Elemente exportieren, werden Sie unterschiedlich exportiert, je nachdem, ob die teilweise indizierten Elemente mit der Suchabfrage und der Konfiguration der Exporteinstellungen übereinstimmen. 

In der folgenden Tabelle ist das Export Verhalten von indizierten und teilweise indizierten Elementen dargestellt, und es wird angegeben, ob für die verschiedenen Konfigurationseinstellungen für den Export die einzelnen Elemente enthalten sind.

|**Export Konfiguration**|**Indizierte Elemente, die Suchabfrage entsprechen**|**Teilweise indizierte Elemente, die Suchabfrage entsprechen**|**Teilweise indizierte Elemente, die nicht mit Suchabfrage übereinstimmen**|
|:-----|:-----|:-----|:-----|
|Nur indizierte Elemente exportieren  <br/> |Exportiert<br/> |Exportiert (im Lieferumfang der indizierten Elemente enthalten, die exportiert werden)<br/>  |Nicht exportiert <br/>|
|Nur teilweise indizierte Elemente exportieren  <br/> |Nicht exportiert  <br/> |Exportiert (als teilweise indizierte Elemente)<br/> |Exportiert (als teilweise indizierte Elemente)|
|Exportieren von indizierten und teilweise indizierten Elementen  <br/> |Exportiert<br/> |Exportiert (im Lieferumfang der indizierten Elemente enthalten, die exportiert werden)<br/>  |Exportiert (als teilweise indizierte Elemente)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Teilweise indizierte Elemente, die aus den Suchergebnissen ausgeschlossen werden

Wenn ein Element teilweise indiziert ist, aber nicht den Suchabfrage Kriterien entspricht, wird es nicht als teilweise indiziertes Element in den Suchergebnissen enthalten. In anderen Worten wird das Element von den Suchergebnissen ausgeschlossen. Als Beispiel: Sie führen eine Suche ohne Schlüsselwörter oder Eigenschaften aus, weil Sie alle Inhalte einschließen möchten. Sie schließen jedoch einen Zeitraum für die Abfrage ein. Wenn ein teilweise indiziertes Element außerhalb dieses Datumsbereichs liegt, wird es nicht als teilweise indiziertes Element eingefügt. Datumsbereiche sind eine effektive Möglichkeit, teilweise indizierte Elemente aus Ihren Suchergebnissen auszuschließen.
  
Wenn Sie sich entschließen, teilweise indizierte Elemente beim Exportieren der Ergebnisse einer Suche einzubeziehen, werden teilweise indizierte Elemente, die aus den Suchergebnissen ausgeschlossen wurden, auch nicht exportiert.
  
Eine Ausnahme zu dieser Regel besteht darin, dass Sie einen abfragebasierten Haltebereich erstellen, der einem eDiscovery-Fall zugeordnet ist. Wenn Sie einen abfragebasierten eDiscovery-Speicher erstellen, werden alle teilweise indizierten Elemente in der Warteschleife gespeichert. Dies umfasst teilweise indizierte Elemente, die nicht mit den Suchabfrage Kriterien und teilweise indizierten Elementen übereinstimmen, die möglicherweise außerhalb einer Datumsbereichs Bedingung liegen. Weitere Informationen zum Erstellen von abfragebasierten eDiscovery-Archiven finden Sie unter [Erstellen eines eDiscovery-Haltestatus](create-ediscovery-holds.md).
  
## <a name="indexing-limits-for-messages-in-content-search"></a>Indizierungs Grenzwerte für Nachrichten in der Inhaltssuche

In der folgenden Tabelle werden die Grenzwerte für die Indizierung beschrieben, die möglicherweise dazu führen, dass eine e-Mail-Nachricht als teilweise indiziertes Element in einer Inhaltssuche in Office 365 zurückgegeben wird.
  
Eine Liste der Indizierungs Grenzwerte für SharePoint-Dokumente finden Sie unter [Such Grenzwerte für SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits).
  
|**Indizierungs Grenzwert**|**Maximalwert**|**Beschreibung**|
|:-----|:-----|:-----|
|Maximale Anlagengröße (ohne Excel-Dateien)  <br/> |150 MB  <br/> |Die maximale Größe einer e-Mail-Anlage, die für die Indizierung analysiert wird. Alle Anlagen, die diesen Grenzwert überschreiten, werden nicht für die Indizierung analysiert, und die Nachricht mit der Anlage wird als teilweise indiziert markiert.  <br/><br/> **Hinweis:** Die Analyse ist der Vorgang, bei dem der Indexdienst Text aus der Anlage extrahiert, unnötige Zeichen wie Interpunktion und Leerzeichen entfernt und dann den Text in Wörter (in einem Prozess namens "Tokenisierung") aufteilt, die dann im Index gespeichert werden.           |
|Maximale Größe von Excel-Dateien  <br/> |4 MB  <br/> |Die maximale Größe einer Excel-Datei, die sich auf einer Website befindet oder an eine e-Mail-Nachricht angefügt wird, die zur Indizierung analysiert wird. Jede Excel-Datei, die diesen Grenzwert überschreitet, wird nicht analysiert, und die Datei oder die e-Mail-Nachricht mit der Dateianlage wird als nicht indiziert markiert.  <br/> |
|Maximale Anzahl von Anlagen  <br/> |250  <br/> |Die maximale Anzahl von Dateien, die an eine e-Mail-Nachricht angehängt werden, die für die Indizierung analysiert wird. Wenn eine Nachricht mehr als 250 Anlagen aufweist, werden die ersten 250-Anlagen analysiert und indiziert, und die Nachricht wird als teilweise indiziert gekennzeichnet, da Sie über zusätzliche Anlagen verfügt, die nicht analysiert wurden.  <br/> |
|Maximale Anlagen Tiefe  <br/> |30  <br/> |Die maximale Anzahl geschachtelter Anlagen, die analysiert werden. Wenn beispielsweise einer e-Mail-Nachricht eine andere Nachricht angefügt ist und die angefügte Nachricht ein angefügtes Word-Dokument enthält, wird das Word-Dokument und die angefügte Nachricht indiziert. Dieses Verhalten wird für bis zu 30 geschachtelte Anlagen fortgesetzt.  <br/> |
|Maximale Anzahl angefügter Bilder  <br/> |0  <br/> |Ein Bild, das an eine e-Mail-Nachricht angefügt ist, wird vom Parser übersprungen und nicht indiziert.  <br/> |
|Maximale Zeitaufwand für die Analyse eines Elements  <br/> |30 Sekunden  <br/> |Für die Analyse eines Elements zur Indizierung werden maximal 30 Sekunden verwendet. Wenn die Analysezeit 30 Sekunden überschreitet, wird das Element als teilweise indiziert markiert.  <br/> |
|Maximale Parser-Ausgabe  <br/> |2 Millionen Zeichen  <br/> |Die maximale Textausgabe des indizierten Parsers. Wenn der Parser beispielsweise 8 Millionen Zeichen aus einem Dokument extrahiert hat, werden nur die ersten 2 Millionen Zeichen indiziert.  <br/> |
|Maximale Anmerkungs Token  <br/> |2 Millionen  <br/> |Wenn eine e-Mail-Nachricht indiziert wird, wird jedes Wort mit unterschiedlichen Verarbeitungsanweisungen versehen, die angeben, wie dieses Wort indiziert werden soll. Jeder Sätze von Verarbeitungsanweisungen wird als Anmerkungs Token bezeichnet. Um die Dienstqualität in Office 365 beizubehalten, gibt es einen Grenzwert von 2 Millionen-Anmerkungs Token für eine e-Mail-Nachricht.  <br/> |
|Maximale Körpergröße im Index  <br/> |67 Millionen Zeichen  <br/> |Die Gesamtzahl der Zeichen im Textkörper einer e-Mail-Nachricht und aller Anlagen. Wenn eine e-Mail-Nachricht indiziert wird, wird der gesamte Text im Nachrichtentext und in allen Anlagen in einer einzigen Zeichenfolge verkettet. Die maximale Größe dieser Zeichenfolge, die indiziert wird, ist 67 Millionen Zeichen.  <br/> |
|Maximale Anzahl eindeutiger Token im Textkörper  <br/> |1 Mio.  <br/> |Wie bereits erläutert, sind Token das Ergebnis des Extrahierens von Text aus dem Inhalt, dem Entfernen von Satzzeichen und Leerzeichen und der anschließende Aufteilung in Wörter (sogenannte Token), die im Index gespeichert sind. Der Ausdruck enthält beispielsweise  `"cat, mouse, bird, dog, dog"` 5 Token. Aber nur 4 von diesen sind eindeutige Token. Es gibt ein Limit von 1 Million eindeutigen Token pro e-Mail-Nachricht, wodurch verhindert werden kann, dass der Index zu groß wird mit zufälligen Token.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Weitere Informationen zu teilweise indizierten Elementen

- Wie bereits erwähnt, gibt eine Stichwortsuche möglicherweise Ergebnisse zurück, wenn das Schlüsselwort in den indizierten Metadaten angezeigt wird, da die Eigenschaften von Nachrichten und Dokumenten und deren Metadaten indiziert sind. Bei der gleichen Stichwortsuche wird jedoch möglicherweise nicht dasselbe Element zurückgegeben, wenn das Schlüsselwort nur im Inhalt eines Elements mit einem nicht unterstützten Dateityp angezeigt wird. In diesem Fall würde das Element als teilweise indiziertes Element zurückgegeben werden.

- Wenn ein teilweise indiziertes Element in den Suchergebnissen enthalten ist, da es die Suchabfrage Kriterien erfüllt (und nicht ausgeschlossen wurde), wird es nicht als teilweise indiziertes Element in die geschätzte Suchstatistik eingeschlossen. Außerdem wird es nicht in teilweise indizierten Elementen enthalten sein, wenn Sie Suchergebnisse exportieren.

- Obwohl ein Dateityp für die Indizierung unterstützt wird und indiziert wird, kann es Indizierungs-oder Suchfehler geben, die dazu führen, dass eine Datei als teilweise indiziertes Element zurückgegeben wird. Beispielsweise kann das Durchsuchen einer sehr großen Excel-Datei teilweise erfolgreich sein (da die ersten 4 MB indiziert sind), tritt dann jedoch ein Fehler auf, da die Dateigrößenbeschränkung überschritten wird. In diesem Fall ist es möglich, dass die gleiche Datei mit den Suchergebnissen und als teilweise indiziertes Element zurückgegeben wird.

- Mit Microsoft-Technologien verschlüsselte Dateianlagen werden indiziert und können durchsucht werden. Dateien, die mit nicht-Microsoft-Technologien verschlüsselt sind, sind teilweise indiziert.

- Mit S/MIME verschlüsselte e-Mail-Nachrichten sind teilweise indiziert. Dazu gehören verschlüsselte Nachrichten mit oder ohne Dateianlagen.

- Durch die Verwaltung von Informationsrechten (Information Rights Management, IRM) geschützte Nachrichten werden indiziert und daher in die Suchergebnisse eingeschlossen, wenn sie der Suchabfrage entsprechen.

## <a name="see-also"></a>Weitere Artikel

[Untersuchen von teilweise indizierten Elementen in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

