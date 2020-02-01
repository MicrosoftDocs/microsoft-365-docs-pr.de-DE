---
title: Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Mit der Verhinderung von Datenverlust (Data Loss Prevention, DLP) in SharePoint Online können Sie Dokumente ermitteln, die vertrauliche Daten in Ihrem Mandanten enthalten. Nach der Ermittlung der Dokumente können Sie mit deren Besitzern zusammenarbeiten, um die Daten zu schützen. In diesem Thema wird das Erstellen einer Abfrage zur Suche nach vertraulichen Daten behandelt.
ms.openlocfilehash: e3750ee69a197de5e7e5c0ac9346124568b8d5f5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594546"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten

Benutzer speicher häufig vertrauliche Daten wie Kreditkarten- und Sozialversicherungsnummer oder persönliche Daten auf ihren Websites, wodurch eine Organisation mit der Zeit beträchtlichen Datenverlustrisiken ausgesetzt sein kann. Dokumente, die auf Websites gespeichert sind – einschließlich OneDrive für Unternehmen Websites – können für Personen außerhalb der Organisation freigegeben werden, die keinen Zugriff auf die Informationen haben sollten. Mit der Verhinderung von Datenverlust (Data Loss Prevention, DLP) in SharePoint Online können Sie Dokumente ermitteln, die vertrauliche Daten in Ihrem Mandanten enthalten. Nach der Ermittlung der Dokumente können Sie mit deren Besitzern zusammenarbeiten, um die Daten zu schützen. In diesem Thema wird das Erstellen einer Abfrage zur Suche nach vertraulichen Daten behandelt.
  
> [!NOTE]
> Electronic Discovery oder eDiscovery und DLP sind Premium Features, die [SharePoint Online Plan 2](https://go.microsoft.com/fwlink/?LinkId=510080)erfordern. 
  
## <a name="forming-a-basic-dlp-query"></a>Erstellen einer einfachen DLP-Abfrage

Eine einfache DLP-Abfrage besteht aus drei Teilen: SensitiveType (Typ vertraulicher Informationen), Anzahlbereich und Konfidenzbereich. Wie in der folgenden Grafik dargestellt, ist **sensitivtype:\<"\>Type"** erforderlich, und beide**|\<Zähl Bereichs\> ** -und**|\<Konfidenz\> Bereiche** sind optional. 
  
![Beispielabfrage unterteilt in Required und optional](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>Typ vertraulicher Informationen - erforderlich

Was haben die einzelnen Teile zu bedeuten? SharePoint DLP-Abfragen beginnen normalerweise mit der Eigenschaft `SensitiveType:"` und einem Informationstyp Namen aus dem [Verzeichnis vertraulicher Informationstypen](https://go.microsoft.com/fwlink/?LinkID=509999)und enden mit einem. `"` Sie können auch den Namen eines [benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md) verwenden, den Sie für Ihre Organisation erstellt haben. Angenommen, Sie suchen Dokumente mit Kreditkartennummern. In einer solchen Instanz verwenden Sie das folgende Format: `SensitiveType:"Credit Card Number"`. Da Sie den Zählbereich oder den Konfidenzbereich nicht eingeschlossen haben, gibt die Abfrage jedes Dokument zurück, in dem eine Kreditkartennummer erkannt wird. Dies ist einfachste Abfrage, die möglich ist und die die meisten Ergebnisse zurückgibt. Beachten Sie, dass Schreibung und Leerzeichen im Typ vertraulicher Informationen eine Rolle spielen. 
  
### <a name="ranges---optional"></a>Bereiche - optional

Beide der nächsten beiden Teile sind Bereiche, also lassen Sie uns schnell untersuchen, wie ein Bereich aussieht. In SharePoint-DLP-Abfragen wird ein grundlegender Bereich durch zwei Zahlen dargestellt, die durch zwei Punkte voneinander `[number]..[number]`getrennt sind, und sieht wie folgt aus:. Wenn `10..20` beispielsweise verwendet wird, würde dieser Bereich Zahlen von 10 bis 20 erfassen. Es gibt zahlreiche Bereichskombinationen, von denen einige in diesem Thema behandelt werden. 
  
Wir fügen der Abfrage einen Zählbereich hinzu. Sie können den count-Bereich verwenden, um die Anzahl der Vorkommen von vertraulichen Informationen zu definieren, die ein Dokument enthalten muss, bevor es in den Abfrageergebnissen enthalten ist. Wenn die Abfrage beispielsweise nur Dokumente zurückgeben soll, die genau fünf Kreditkartennummern enthalten, verwenden Sie Folgendes: `SensitiveType:"Credit Card Number|5"`. Mithilfe eines Anzahlbereichs können Sie auch Dokumente mit hohem Risikopotenzial ermitteln. Angenommen, in Ihrer Organisation werden Dokumente mit mindestens fünf Kreditkartennummern als hohes Risiko eingestuft. Um Dokumente zu finden, die dieses Kriterium erfüllen, verwenden Sie diese `SensitiveType:"Credit Card Number|5.."`Abfrage:. Alternativ können Sie mit dieser Abfrage Dokumente mit fünf oder weniger Kreditkartennummern finden: `SensitiveType:"Credit Card Number|..5"`. 
  
#### <a name="confidence-range"></a>Konfidenzbereich

Mithilfe des Konfidenzbereichs wird schließlich der Grad an Konfidenz angegeben, zu dem der erkannte Typ vertraulicher Informationen ein Treffer ist. Die Werte für den Konfidenzbereich sind mit denen für den Anzahlbereich vergleichbar. Sie können eine Abfrage ohne Angabe eines Anzahlbereichs erstellen. Wenn Sie beispielsweise nach Dokumenten mit einer beliebigen Anzahl von Kreditkartennummern suchen – solange der Konfidenzbereich 85 Prozent oder höher ist – verwenden Sie diese Abfrage: `SensitiveType:"Credit Card Number|*|85.."`. 
  
> [!IMPORTANT]
> Das Sternchen ( `*`) ist ein Platzhalterzeichen, das bedeutet, dass ein beliebiger Wert funktioniert. Sie können das Platzhalterzeichen ( `*`) entweder im Zählbereich oder im Konfidenzbereich verwenden, jedoch nicht in einem vertraulichen Typ. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Im eDiscovery Center stehen weitere Abfrageeigenschaften und Suchoperatoren zur Verfügung.

Mit DLP in SharePoint wird auch die LastSensitiveContentScan-Eigenschaft eingeführt, die Sie bei der Suche nach Dateien unterstützenkann, die innerhalb eines bestimmten Zeitrahmens gescannt wurden. Beispiel für Abfragebeispiele mit `LastSensitiveContentScan` der-Eigenschaft finden Sie in den [Beispielen für komplexe Abfragen](#examples-of-complex-queries) im nächsten Abschnitt. 
  
Sie können nicht nur DLP-spezifische Eigenschaften zum Erstellen einer Abfrage verwenden, sondern auch standardmäßige SharePoint-eDiscovery `Author` - `FileExtension`Sucheigenschaften wie oder. Sie können Operatoren verwenden, um komplexe Abfragen zu erstellen. Eine Liste der verfügbaren Eigenschaften und Operatoren finden Sie unter [using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) Blog Post. 
  
## <a name="examples-of-complex-queries"></a>Beispiele

In den folgenden Beispielen werden unterschiedliche vertrauliche Typen, Eigenschaften und Operatoren verwendet, um zu veranschaulichen, wie Sie Ihre Abfragen verfeinern können, um genau das zu finden, wonach Sie suchen.
  
|**Query**|**Erläuterung**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |Der Name mag seltsam erscheinen, weil er so lang ist, aber er ist der richtige Name für diesen vertraulichen Typ. Stellen Sie sicher, dass Sie genaue Namen aus dem [Lager für vertrauliche Informationstypen](https://go.microsoft.com/fwlink/?LinkID=509999)verwenden. Sie können auch den Namen eines [benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md) verwenden, den Sie für Ihre Organisation erstellt haben.  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |Dadurch werden Dokumente mit mindestens einer Übereinstimmung mit dem vertraulichen Typ "Kreditkartennummer" zurückgegeben. Die Werte für jeden Bereich sind die jeweiligen Mindest-und Höchstwerte. Eine einfachere Möglichkeit, diese Abfrage zu schreiben `SensitiveType:"Credit Card Number"`, ist, aber wo bleibt der Spaß daran?  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |Dadurch werden Dokumente mit 5-25 Kreditkartennummern zurückgegeben, die vom 11. August 2018 bis zum 13. August 2018 gescannt wurden.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |Dadurch werden Dokumente mit 5-25 Kreditkartennummern zurückgegeben, die vom 11. August 2018 bis zum 13. August 2018 gescannt wurden. Dateien mit einer XLSX-Erweiterung sind nicht in den Abfrageergebnissen enthalten.  `FileExtension`ist eine von vielen Eigenschaften, die Sie in eine Abfrage einschließen können. Weitere Informationen finden Sie unter [using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |Diese Abfrage gibt Dokumente zurück, die entweder eine Kreditkartennummer oder US-Sozialversicherungsnummer enthalten.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Beispiele

Nicht alle Abfragen sind gleich. In der folgenden Tabelle sind Beispiele für Abfragen aufgeführt, die nicht mit DLP in SharePoint funktionieren, und es wird beschrieben, warum.
  
|**Nicht unterstützte Abfrage**|**Grund**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |Sie müssen mindestens eine Zahl hinzufügen.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" ist kein gültiger Name für vertraulichen Typ. Nur Namen in den [Typen für vertrauliche Informationen](https://go.microsoft.com/fwlink/?LinkID=509999) funktionieren in DLP-Abfragen.  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |NULL ist weder als Minimalwert noch als Maximalwert in einem Bereich gültig.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Es ist möglicherweise schwer zu erkennen, aber es gibt zusätzlichen Leerraum zwischen "Kredit" und "Karte", wodurch die Abfrage ungültig wird. Verwenden Sie genaue vertrauliche Typnamen aus dem [Verzeichnis vertraulicher Informationstypen](https://go.microsoft.com/fwlink/?LinkID=509999).  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |Die zwei-Perioden-Teil sollte nicht durch ein Leerzeichengetrennt werden.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |Es gibt zu viele Pipe-Trennzeichen (|). Führen Sie stattdessen dieses Format aus:`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |Da Konfidenz Werte einen Prozentsatz darstellen, dürfen Sie nicht mehr als 100. Wählen Sie einen Wert von 1 bis 100.  <br/> |
   
## <a name="for-more-information"></a>Weitere Informationen

[Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)
  
[Ausführen einer Inhaltssuche](content-search.md)
  
[Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
  

