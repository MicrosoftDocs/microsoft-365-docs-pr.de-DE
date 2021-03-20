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
description: Verwenden Sie die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in SharePoint Online, um Dokumente zu ermitteln, die vertrauliche Daten im gesamten Mandanten enthalten.
ms.openlocfilehash: 9582974a26e0e112a6b3851494d057cad2010796
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906779"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten

Benutzer speicher häufig vertrauliche Daten wie Kreditkarten- und Sozialversicherungsnummer oder persönliche Daten auf ihren Websites, wodurch eine Organisation mit der Zeit beträchtlichen Datenverlustrisiken ausgesetzt sein kann. Auf Websites gespeicherte Dokumente – einschließlich OneDrive for #A0 – können für Personen außerhalb der Organisation freigegeben werden, die keinen Zugriff auf die Informationen haben sollten. Mit der Verhinderung von Datenverlust (Data Loss Prevention, DLP) in SharePoint Online können Sie Dokumente ermitteln, die vertrauliche Daten in Ihrem Mandanten enthalten. Nach der Ermittlung der Dokumente können Sie mit deren Besitzern zusammenarbeiten, um die Daten zu schützen. In diesem Thema wird das Erstellen einer Abfrage zur Suche nach vertraulichen Daten behandelt.
  
> [!NOTE]
> Elektronische Ermittlung oder eDiscovery und DLP sind Premiumfeatures, die [SharePoint Online Plan 2 erfordern.](https://go.microsoft.com/fwlink/?LinkId=510080) 
  
## <a name="forming-a-basic-dlp-query"></a>Erstellen einer einfachen DLP-Abfrage

Eine einfache DLP-Abfrage besteht aus drei Teilen: SensitiveType (Typ vertraulicher Informationen), Anzahlbereich und Konfidenzbereich. Wie in der folgenden Grafik dargestellt, **ist SensitiveType:" \<type\> erforderlich,** und beide **|\<count range\>** sind **|\<confidence range\>** optional. 
  
![Beispielabfrage unterteilt in erforderlich und optional](../media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>Typ vertraulicher Informationen - erforderlich

Was haben die einzelnen Teile zu bedeuten? SharePoint-DLP-Abfragen beginnen in der Regel mit der Eigenschaft und einem Informationstypnamen aus dem Inventar der vertraulichen  `SensitiveType:"` [Informationstypen](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)und enden mit einem  `"` . Sie können auch den Namen eines benutzerdefinierten vertraulichen [Informationstyps verwenden,](create-a-custom-sensitive-information-type.md) den Sie für Ihre Organisation erstellt haben. Angenommen, Sie suchen Dokumente mit Kreditkartennummern. In einer solchen Instanz würden Sie das folgende Format verwenden:  `SensitiveType:"Credit Card Number"` . Da Sie keinen Zählbereich oder Konfidenzbereich enthalten haben, gibt die Abfrage jedes Dokument zurück, in dem eine Kreditkartennummer erkannt wird. Dies ist einfachste Abfrage, die möglich ist und die die meisten Ergebnisse zurückgibt. Beachten Sie, dass Schreibung und Leerzeichen im Typ vertraulicher Informationen eine Rolle spielen. 
  
### <a name="ranges---optional"></a>Bereiche - optional

Bei den beiden nächsten Teilen handelt es sich um Bereiche. Lassen Sie uns also schnell untersuchen, wie ein Bereich aussieht. In SharePoint-DLP-Abfragen wird ein Basisbereich durch zwei Zahlen dargestellt, die durch zwei Punkte getrennt sind, was wie dies aussieht:  `[number]..[number]` . Wenn beispielsweise dieser Bereich verwendet wird, würden Zahlen zwischen  `10..20` 10 und 20 erfasst. Es gibt zahlreiche Bereichskombinationen, von denen einige in diesem Thema behandelt werden. 
  
Fügen wir der Abfrage einen Zählbereich hinzu. Sie können den Anzahlbereich verwenden, um die Anzahl der Vorkommen vertraulicher Informationen zu definieren, die ein Dokument enthalten muss, bevor es in die Abfrageergebnisse aufgenommen wird. Wenn Ihre Abfrage beispielsweise nur Dokumente zurückgeben soll, die genau fünf Kreditkartennummern enthalten, verwenden Sie folgende:  `SensitiveType:"Credit Card Number|5"` . Mithilfe eines Anzahlbereichs können Sie auch Dokumente mit hohem Risikopotenzial ermitteln. Angenommen, in Ihrer Organisation werden Dokumente mit mindestens fünf Kreditkartennummern als hohes Risiko eingestuft. Um Dokumente zu finden, die diesem Kriterium entsprechen, verwenden Sie diese Abfrage:  `SensitiveType:"Credit Card Number|5.."` . Alternativ können Sie Dokumente mit fünf oder weniger Kreditkartennummern mit dieser Abfrage finden:  `SensitiveType:"Credit Card Number|..5"` . 
  
#### <a name="confidence-range"></a>Konfidenzbereich

Mithilfe des Konfidenzbereichs wird schließlich der Grad an Konfidenz angegeben, zu dem der erkannte Typ vertraulicher Informationen ein Treffer ist. Die Werte für den Konfidenzbereich sind mit denen für den Anzahlbereich vergleichbar. Sie können eine Abfrage ohne Angabe eines Anzahlbereichs erstellen. Wenn Sie beispielsweise nach Dokumenten mit einer beliebigen Anzahl von Kreditkartennummern suchen möchten – solange der Konfidenzbereich 85 Prozent oder höher beträgt – verwenden Sie die folgende Abfrage:  `SensitiveType:"Credit Card Number|*|85.."` . 
  
> [!IMPORTANT]
> Das Sternchen ( `*` ) ist ein Platzhalterzeichen, das bedeutet, dass jeder Wert funktioniert. Sie können das Platzhalterzeichen ( ) entweder im Zählbereich oder im Konfidenzbereich verwenden, jedoch `*` nicht in einem vertraulichen Typ. 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Im eDiscovery Center stehen weitere Abfrageeigenschaften und Suchoperatoren zur Verfügung.

DLP in SharePoint führt auch die LastSensitiveContentScan-Eigenschaft ein, mit der Sie innerhalb eines bestimmten Zeitrahmens nach gescannten Dateien suchen können. Abfragebeispiele mit der  `LastSensitiveContentScan` Eigenschaft finden Sie in den [Beispielen](#examples-of-complex-queries) für komplexe Abfragen im nächsten Abschnitt. 
  
Sie können nicht nur DLP-spezifische Eigenschaften zum Erstellen einer Abfrage verwenden, sondern auch standardmäßige SharePoint eDiscovery-Sucheigenschaften wie  `Author` oder  `FileExtension` . Sie können Operatoren verwenden, um komplexe Abfragen zu erstellen. Eine Liste der verfügbaren Eigenschaften und Operatoren finden Sie im Blogbeitrag Verwenden von Sucheigenschaften und Operatoren [mit eDiscovery.](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) 
  
## <a name="examples-of-complex-queries"></a>Beispiele

In den folgenden Beispielen werden verschiedene vertrauliche Typen, Eigenschaften und Operatoren verwendet, um zu veranschaulichen, wie Sie Ihre Abfragen so verfeinern können, dass sie genau das finden, wofür Sie suchen.
  
|**Query**|**Erläuterung**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |Der Name mag seltsam erscheinen, da er so lang ist, aber er ist der richtige Name für diesen vertraulichen Typ. Achten Sie darauf, genaue Namen aus dem [Inventar vertraulicher Informationstypen zu verwenden.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) Sie können auch den Namen eines benutzerdefinierten vertraulichen [Informationstyps verwenden,](create-a-custom-sensitive-information-type.md) den Sie für Ihre Organisation erstellt haben.  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |Dadurch werden Dokumente mit mindestens einer Übereinstimmung mit dem vertraulichen Typ "Kreditkartennummer" zurückgegeben. Die Werte für jeden Bereich sind die jeweiligen Mindest- und Höchstwerte. Eine einfachere Möglichkeit zum Schreiben dieser Abfrage ist , aber wo  `SensitiveType:"Credit Card Number"` ist der Spaß daran?  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |Dadurch werden Dokumente mit 5 bis 25 Kreditkartennummern zurückgegeben, die zwischen dem 11. August 2018 und dem 13. August 2018 gescannt wurden.  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |Dadurch werden Dokumente mit 5 bis 25 Kreditkartennummern zurückgegeben, die zwischen dem 11. August 2018 und dem 13. August 2018 gescannt wurden. Dateien mit einer XLSX-Erweiterung sind nicht in den Abfrageergebnissen enthalten.  `FileExtension` ist eine von vielen Eigenschaften, die Sie in eine Abfrage hinzufügen können. Weitere Informationen finden Sie unter [Using Search Properties and Operators with eDiscovery](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery).  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |Diese Abfrage gibt Dokumente zurück, die entweder eine Kreditkartennummer oder US-Sozialversicherungsnummer enthalten.  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>Beispiele

Nicht alle Abfragen sind gleich. Die folgende Tabelle enthält Beispiele für Abfragen, die nicht mit DLP in SharePoint funktionieren, und beschreibt die Gründe.
  
|**Nicht unterstützte Abfrage**|**Grund**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |Sie müssen mindestens eine Zahl hinzufügen.  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" ist kein gültiger Typname für vertrauliche Daten. Nur Namen in den [Inventartypen für vertrauliche](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) Informationen funktionieren in DLP-Abfragen.  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |Null ist weder als Mindestwert noch als Maximalwert in einem Bereich gültig.  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |Es ist möglicherweise schwierig zu erkennen, aber zwischen "Credit" und "Card" gibt es zusätzlichen Leerraum, der die Abfrage ungültig macht. Verwenden Sie genaue Typennamen für vertrauliche Typen aus dem [Inventar vertraulicher Informationstypen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |Der Zwei-Period-Teil sollte nicht durch ein Leerzeichen getrennt werden.  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |Es gibt zu viele Pipetrennzeichen (|). Folgen Sie stattdessen diesem Format: `SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |Da Konfidenzwerte einen Prozentsatz darstellen, dürfen sie 100 nicht überschreiten. Wählen Sie einen Wert von 1 bis 100.  <br/> |
   
## <a name="for-more-information"></a>Weitere Informationen

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Ausführen einer Inhaltssuche](content-search.md)
- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
