---
title: Teilweise indizierte Elemente in der Inhaltssuche und anderen eDiscovery-Tools
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
description: Erfahren Sie mehr über nicht indizierte Elemente in Exchange und SharePoint, die Sie in eine eDiscovery-Suche, die Sie im compliance center Microsoft 365 ausführen, enthalten können.
ms.openlocfilehash: 40995aa403686caadd5e35b6fa9c6ca20ee017ee
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994732"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Teilweise indizierte Elemente in eDiscovery

Eine eDiscovery-Suche, die Sie über das Microsoft 365 Compliance Center ausführen, enthält automatisch teilweise indizierte Elemente in den geschätzten Suchergebnissen, wenn Sie eine Suche ausführen. Teilweise indizierte Elemente Exchange Postfachelemente und Dokumente auf SharePoint- und OneDrive for Business-Websites, die aus einem bestimmten Grund nicht vollständig für die Suche indiziert wurden. In Exchange enthält ein teilweise indiziertes Element in der Regel eine Datei (eines Dateityps, der nicht indiziert werden kann), die an eine E-Mail-Nachricht angefügt ist. Hier sind einige weitere Gründe, warum Elemente nicht für die Suche indiziert werden können und als teilweise indizierte Elemente zurückgegeben werden, wenn Sie eine eDiscovery-Suche ausführen:
  
- Der Dateityp wird nicht erkannt oder wird nicht für die Indizierung unterstützt.

- Nachrichten verfügen über eine angefügte Datei ohne gültigen Handler, z. B. Bilddateien. Dies ist die häufigste Ursache für teilweise indizierte E-Mail-Elemente.

- Der Dateityp wird für die Indizierung unterstützt, aber es ist ein Indizierungsfehler für eine bestimmte Datei aufgetreten.

- Die E-Mail enthält zu viele Dateien im Anhang.

- Die an die E-Mail angehängte Datei ist zu groß.

- Eine Datei wurde mit Technologien von anderen Anbietern als Microsoft verschlüsselt.

- Eine Datei ist kennwortgeschützt.

> [!NOTE]
> Die meisten Organisationen verfügen über weniger als 1 % des Inhalts nach Volumen und weniger als 12 % nach Größe, die teilweise indiziert ist. Der Grund für den Unterschied zwischen Volumen und Größe ist, dass größere Dateien eine höhere Wahrscheinlichkeit haben, Inhalte zu enthalten, die nicht vollständig indiziert werden können.
  
Für rechtliche Untersuchungen muss Ihre Organisation möglicherweise teilweise indizierte Elemente überprüfen. Sie können auch angeben, ob teilweise indizierte Elemente beim Exportieren von Suchergebnissen auf einen lokalen Computer oder beim Vorbereiten der Ergebnisse für die Analyse mit Advanced eDiscovery. Weitere Informationen finden Sie unter [Investigating partially indexed items in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Für die Suche nicht indizierte Dateitypen

Bestimmte Dateitypen wie Bitmap- oder MP3-Dateien enthalten keinen zu indizierenden Inhalt. Aus diesem Grund führen die Suchindizierungsserver in Exchange und SharePoint keine Volltextindizierung für diese Dateitypen durch. Diese Dateitypen werden als nicht unterstützte Dateitypen betrachtet. Es gibt außerdem Dateitypen, für die die Volltextindizierung deaktiviert wurde (entweder standardmäßig oder durch den Administrator). Nicht unterstützte und deaktivierte Dateitypen werden in Inhaltssuchen als nicht indizierte Elemente bezeichnet. Wie bereits erwähnt, können teilweise indizierte Elemente in den Satz von Suchergebnissen einbezogen werden, wenn Sie eine Suche ausführen, die Suchergebnisse auf einen lokalen Computer exportieren oder Suchergebnisse für die Suche Advanced eDiscovery.
  
Eine Liste von unterstützten und deaktivierten Dateiformaten finden Sie in den folgenden Themen:
  
- **Exchange**  -  [Dateiformate, die von der Exchange indiziert werden](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- **Exchange**  -  [Get-SearchDocumentFormat](/powershell/module/exchange/get-searchdocumentformat)

- **SharePoint**  -  [Standarddurchforstung von Dateinamenerweiterungen und analysierten Dateitypen in SharePoint](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Nachrichten und Dokumente mit teilweise indizierten Dateitypen können in Suchergebnissen zurückgegeben werden

Nicht jede E-Mail-Nachricht mit einer teilweise indizierten Dateianlage oder jedem teilweise indizierten SharePoint wird automatisch als teilweise indiziertes Element zurückgegeben. Der Grund dafür ist, dass andere Nachrichten- oder Dokumenteigenschaften, z. B. die **Subject-Eigenschaft** in E-Mail-Nachrichten und die **Title-** oder **Author-Eigenschaften** für Dokumente indiziert sind und durchsucht werden können. Beispielsweise gibt eine Stichwortsuche nach "financial" Elemente mit einer teilweise indizierten Dateianlage zurück, wenn dieses Schlüsselwort im Betreff einer E-Mail-Nachricht oder im Dateinamen oder Titel eines Dokuments angezeigt wird. Wenn das Schlüsselwort jedoch nur im Textkörper der Datei angezeigt wird, wird die Nachricht oder das Dokument als teilweise indiziertes Element zurückgegeben.
  
Ebenso werden Nachrichten mit teilweise indizierten Dateianlagen und Dokumente eines teilweise indizierten Dateityps in suchergebnissen eingeschlossen, wenn andere Nachrichten- oder Dokumenteigenschaften, die indiziert und durchsuchbar sind, die Suchkriterien erfüllen. Zu den Nachrichteneigenschaften, die für die Suche indiziert werden, gehören Sende- und Empfangsdatum, Absender und Empfänger, Dateiname von Anhängen sowie der Nachrichtentext. Zu den für die Suche indizierten Dokumenteigenschaften gehören erstellte und geänderte Daten. Auch wenn eine Nachrichtenanlage ein teilweise indiziertes Element sein kann, wird die Nachricht in die regulären Suchergebnisse eingeschlossen, wenn der Wert anderer Nachrichten- oder Dokumenteigenschaften den Suchkriterien entspricht.
  
Eine Liste der E-Mail- und Dokumenteigenschaften, nach der Sie mithilfe des Suchfeatures im Security & Compliance Center suchen können, finden Sie unter [Keyword queries and search conditions for eDiscovery](keyword-queries-and-search-conditions.md).
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Teilweise indizierte Elemente, die in den Suchergebnissen enthalten sind

Ihre Organisation muss möglicherweise zusätzliche Analysen für teilweise indizierte Elemente identifizieren und durchführen, um zu bestimmen, was sie sind, was sie enthalten und ob sie für eine bestimmte Untersuchung relevant sind. Wie bereits erläutert, werden die teilweise indizierten Elemente in den durchsuchten Inhaltsverzeichnissen automatisch in die geschätzten Suchergebnisse einbezogen. Sie haben die Möglichkeit, diese teilweise indizierten Elemente beim Exportieren von Suchergebnissen oder beim Vorbereiten der Suchergebnisse für Advanced eDiscovery.
  
Beachten Sie folgendes zu teilweise indizierten Elementen:
  
- Wenn Sie eine eDiscovery-Suche ausführen, werden die Gesamtanzahl und Größe teilweise indizierter Exchange-Elemente (die von der Suchabfrage zurückgegeben werden) in der Suchstatistik auf der Flyoutseite angezeigt und als nicht **indizierte** Elemente gekennzeichnet. Statistiken zu teilweise indizierten Elementen, die auf der Flyoutseite angezeigt werden, enthalten keine teilweise indizierten Elemente in SharePoint oder OneDrive.

- Wenn die Suche, aus der Sie Ergebnisse exportieren, eine Suche nach bestimmten Inhaltsstandorten oder allen Inhaltsstandorten in Ihrer Organisation war, werden nur die nicht indizierten Elemente aus Inhaltsverzeichnissen exportiert, die Elemente enthalten, die den Suchkriterien entsprechen. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Der Grund dafür ist, dass das Exportieren teilweise indizierter Elemente von vielen Speicherorten in der Organisation die Wahrscheinlichkeit von Exportfehlern erhöhen und die Zeit erhöhen kann, die zum Exportieren und Herunterladen der Suchergebnisse benötigt wird.

    Um teilweise indizierte Elemente aus allen Inhaltsverzeichnissen für eine Suche zu exportieren, konfigurieren Sie die Suche so, dass alle Elemente zurückgegeben werden (durch Entfernen von Schlüsselwörtern aus der Suchabfrage), und exportieren Sie dann nur teilweise indizierte Elemente, wenn Sie die Suchergebnisse exportieren (indem Sie auf Nur Elemente klicken, die ein nicht unbekanntes Format **haben,** verschlüsselt sind oder aus anderen Gründen unter Ausgabeoptionen nicht indiziert **wurden).**

- Wenn Sie alle Postfachelemente in die Suchergebnisse hinzufügen möchten oder eine Suchabfrage keine Schlüsselwörter angibt oder nur einen Datumsbereich angibt, werden teilweise indizierte Elemente möglicherweise nicht in die PST-Datei kopiert, die die teilweise indizierten Elemente enthält. Dies liegt daran, dass alle Elemente, einschließlich teilweise indizierter Elemente, automatisch in die regulären Suchergebnisse einbezogen werden.

- Teilweise indizierte Elemente können nicht in der Vorschau angezeigt werden. Sie müssen die Suchergebnisse exportieren, um teilweise indizierte Elemente anzeigen zu können, die von der Suche zurückgegeben werden.

Darüber hinaus werden teilweise indizierte Elemente aus SharePoint in einen Ordner namens **Uncrawlable** exportiert, wenn Sie Suchergebnisse exportieren und teilweise indizierte Elemente in den Export hinzufügen. Wenn Sie teilweise indizierte Exchange exportieren, werden sie unterschiedlich exportiert, je nachdem, ob die teilweise indizierten Elemente mit der Suchabfrage und der Konfiguration der Exporteinstellungen übereinstimmen. 

Die folgende Tabelle zeigt das Exportverhalten indizierter und teilweise indizierter Elemente und ob die einzelnen Elemente für die verschiedenen Exportkonfigurationseinstellungen enthalten sind.

|**Exportkonfiguration**|**Indizierte Elemente, die einer Suchabfrage entsprechen**|**Teilweise indizierte Elemente, die einer Suchabfrage entsprechen**|**Teilweise indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen**|
|:-----|:-----|:-----|:-----|
|Nur indizierte Elemente exportieren  <br/> |Exportiert<br/> |Exportiert (im Lieferumfang der indizierten Elemente enthalten, die exportiert werden)<br/>  |Nicht exportiert <br/>|
|Exportieren nur teilweise indizierter Elemente  <br/> |Nicht exportiert  <br/> |Exportiert (als teilweise indizierte Elemente)<br/> |Exportiert (als teilweise indizierte Elemente)|
|Exportieren indizierter und teilweise indizierter Elemente  <br/> |Exportiert<br/> |Exportiert (im Lieferumfang der indizierten Elemente enthalten, die exportiert werden)<br/>  |Exportiert (als teilweise indizierte Elemente)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Teilweise indizierte Elemente, die aus den Suchergebnissen ausgeschlossen werden

Wenn ein Element teilweise indiziert ist, aber nicht den Suchabfragekriterien entspricht, wird es nicht als teilweise indiziertes Element in die Suchergebnisse einbezogen. In anderen Worten wird das Element von den Suchergebnissen ausgeschlossen. Wenn Sie beim Exportieren der Ergebnisse einer Suche teilweise indizierte Elemente enthalten möchten, werden auch teilweise indizierte Elemente, die aus den Suchergebnissen ausgeschlossen wurden, nicht exportiert.
  
Eine Ausnahme von dieser Regel ist, wenn Sie einen abfragebasierten Halteraum erstellen, der einem eDiscovery-Fall zugeordnet ist. Wenn Sie einen abfragebasierten eDiscovery-Halteraum erstellen, werden alle teilweise indizierten Elemente in der Warteschleife platziert. Dies umfasst teilweise indizierte Elemente, die nicht den Suchabfragekriterien entsprechen. Weitere Informationen zum Erstellen von abfragebasierten eDiscovery-Speichern finden Sie unter [Create an eDiscovery hold](create-ediscovery-holds.md).
  
## <a name="indexing-limits-for-messages"></a>Indizierungsgrenzwerte für Nachrichten

In der folgenden Tabelle werden die Indizierungsgrenzwerte beschrieben, die dazu führen können, dass eine E-Mail-Nachricht als teilweise indiziertes Element in einer eDiscovery-Suche in einer Microsoft 365.
  
Eine Liste der Indizierungsgrenzwerte für SharePoint finden Sie unter [Search limits for SharePoint Online](/sharepoint/search-limits).
  
|**Indizierungsgrenzwert**|**Maximalwert**|**Beschreibung**|
|:-----|:-----|:-----|
|Maximale Anlagengröße (Excel Dateien)  <br/> |150 MB  <br/> |Die maximale Größe einer E-Mail-Anlage, die für die Indizierung analysiert wird. Jede Anlage, die diesen Grenzwert überschreitet, wird nicht für die Indizierung analysiert, und die Nachricht mit der Anlage wird als teilweise indiziert markiert.  <br/><br/> **Hinweis:** Die Analyse ist der Prozess, bei dem der Indizierungsdienst Text aus der Anlage extrahiert, unnötige Zeichen wie Interpunktion und Leerzeichen entfernt und den Text dann in Wörter (in einem Prozess namens Tokenisierung) teilt, die dann im Index gespeichert werden.           |
|Maximale Größe Excel Dateien  <br/> |4 MB  <br/> |Die maximale Größe einer Excel, die sich auf einer Website befindet oder an eine E-Mail-Nachricht angefügt ist, die für die Indizierung analysiert wird. Jede Excel, die größer als dieser Grenzwert ist, wird nicht analysiert, und die Datei oder die E-Mail-Nachricht mit der Dateianlage wird als nicht indiziert markiert.  <br/> |
|Maximale Anzahl von Anlagen  <br/> |250  <br/> |Die maximale Anzahl von Dateien, die an eine E-Mail-Nachricht angefügt sind und für die Indizierung analysiert werden. Wenn eine Nachricht mehr als 250 Anlagen enthält, werden die ersten 250 Anlagen analysiert und indiziert, und die Nachricht wird als teilweise indiziert markiert, da sie über zusätzliche Anlagen verfügt, die nicht analysiert wurden.  <br/> |
|Maximale Anlagentiefe  <br/> |30  <br/> |Die maximale Anzahl geschachtelter Anlagen, die analysiert werden. Wenn beispielsweise einer E-Mail-Nachricht eine weitere Nachricht angefügt ist und die angefügte Nachricht über ein angefügtes Word-Dokument verfügt, werden das Word-Dokument und die angefügte Nachricht indiziert. Dieses Verhalten wird für bis zu 30 geschachtelte Anlagen fortgesetzt.  <br/> |
|Maximale Anzahl angefügter Bilder  <br/> |0  <br/> |Ein Bild, das einer E-Mail-Nachricht zugeordnet ist, wird vom Parser übersprungen und nicht indiziert.  <br/> |
|Maximale Zeit für die Analyse eines Elements  <br/> |30 Sekunden  <br/> |Maximal 30 Sekunden dauert die Analyse eines Elements für die Indizierung. Wenn die Analysezeit 30 Sekunden überschreitet, wird das Element als teilweise indiziert markiert.  <br/> |
|Maximale Parserausgabe  <br/> |2 Millionen Zeichen  <br/> |Die maximale Textausgabe des indizierten Parsers. Wenn der Parser beispielsweise 8 Millionen Zeichen aus einem Dokument extrahiert hat, werden nur die ersten 2 Millionen Zeichen indiziert.  <br/> |
|Maximale Anmerkungstoken  <br/> |2 Mio.  <br/> |Wenn eine E-Mail-Nachricht indiziert wird, wird jedes Wort mit unterschiedlichen Verarbeitungsanweisungen kommentiert, die angeben, wie dieses Wort indiziert werden soll. Jeder Satz von Verarbeitungsanweisungen wird als Anmerkungstoken bezeichnet. Um die Dienstqualität in Office 365 zu erhalten, gibt es eine Grenze von 2 Millionen Anmerkungstoken für eine E-Mail-Nachricht.  <br/> |
|Maximale Textgröße im Index  <br/> |67 Millionen Zeichen  <br/> |Die Gesamtanzahl der Zeichen im Textkörper einer E-Mail-Nachricht und aller Anlagen. Wenn eine E-Mail-Nachricht indiziert wird, wird der ganze Text im Nachrichtentext und in allen Anlagen in einer einzelnen Zeichenfolge verkettet. Die maximale Größe dieser indizierten Zeichenfolge beträgt 67 Millionen Zeichen.  <br/> |
|Maximale Anzahl eindeutiger Token im Textkörper  <br/> |1 Million  <br/> |Wie bereits erläutert, sind Token das Ergebnis des Extrahierens von Text aus Inhalten, des Entfernens von Interpunktion und Leerzeichen und deren Aufteilung in Wörter (sogenannte Token), die im Index gespeichert sind. Der Ausdruck enthält beispielsweise  `"cat, mouse, bird, dog, dog"` 5 Token. Aber nur 4 davon sind eindeutige Token. Es gibt eine Grenze von 1 Million eindeutigen Token pro E-Mail-Nachricht, wodurch verhindert wird, dass der Index mit zufälligen Token zu groß wird.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Weitere Informationen zu teilweise indizierten Elementen

- Wie bereits erwähnt, kann eine Schlüsselwortsuche Ergebnisse zurückgeben, wenn dieses Schlüsselwort in den indizierten Metadaten angezeigt wird, da Nachrichten- und Dokumenteigenschaften und ihre Metadaten indiziert sind. Dieselbe Schlüsselwortsuche gibt jedoch möglicherweise nicht dasselbe Element zurück, wenn das Schlüsselwort nur im Inhalt eines Elements mit einem nicht unterstützten Dateityp angezeigt wird. In diesem Fall wird das Element als teilweise indiziertes Element zurückgegeben.

- Wenn ein teilweise indiziertes Element in den Suchergebnissen enthalten ist, weil es die Suchabfragekriterien erfüllt (und nicht ausgeschlossen wurde), wird es nicht als teilweise indiziertes Element in die geschätzte Suchstatistik einbezogen. Außerdem wird sie beim Exportieren von Suchergebnissen nicht in teilweise indizierte Elemente einbezogen.

- Obwohl ein Dateityp für die Indizierung unterstützt und indiziert wird, können Indizierungs- oder Suchfehler auftreten, die dazu führen, dass eine Datei als teilweise indiziertes Element zurückgegeben wird. Das Durchsuchen einer sehr großen Excel kann z. B. teilweise erfolgreich sein (da die ersten 4 MB indiziert sind), schlägt dann jedoch fehl, da die Dateigröße überschritten wird. In diesem Fall ist es möglich, dass dieselbe Datei mit den Suchergebnissen und als teilweise indiziertes Element zurückgegeben wird.

- Dateien, die [](encryption.md) mit Microsoft-Verschlüsselungstechnologien verschlüsselt sind und an eine E-Mail-Nachricht angefügt sind, die den Kriterien einer Suche entspricht, können in der Vorschau angezeigt werden und beim Exportieren entschlüsselt werden. Zu diesem Zeitpunkt werden Dateien, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt werden (und in SharePoint oder OneDrive for Business gespeichert werden), teilweise indiziert.

- Mit S/MIME verschlüsselte E-Mail-Nachrichten werden teilweise indiziert. Dazu gehören verschlüsselte Nachrichten mit oder ohne Dateianlagen.

- E-Mail-Nachrichten, die mithilfe von Azure Rights Management geschützt sind, werden indiziert und in die Suchergebnisse einbezogen, wenn sie mit der Suchabfrage übereinstimmen. Rechtegeschützte E-Mail-Nachrichten werden entschlüsselt und können in der Vorschau angezeigt und exportiert werden. Diese Funktionalität erfordert, dass Ihnen die Rolle RMS Decrypt zugewiesen ist, die standardmäßig der Rollengruppe eDiscover Manager zugewiesen ist.

## <a name="see-also"></a>Siehe auch

[Untersuchen teilweise indizierter Elemente in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)