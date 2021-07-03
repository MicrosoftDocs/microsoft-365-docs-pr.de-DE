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
ms.openlocfilehash: 04bf2e97dd2b5530838aef9fcb4b4467270d2d9d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287479"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Erstellen einer Abfrage zum Auffinden auf Websites gespeicherter vertraulicher Daten

Benutzer speicher häufig vertrauliche Daten wie Kreditkarten- und Sozialversicherungsnummer oder persönliche Daten auf ihren Websites, wodurch eine Organisation mit der Zeit beträchtlichen Datenverlustrisiken ausgesetzt sein kann. Dokumente, die auf Websites gespeichert sind , einschließlich OneDrive for Business Websites, können für Personen außerhalb der Organisation freigegeben werden, die keinen Zugriff auf die Informationen haben sollten. Mit der Verhinderung von Datenverlust (Data Loss Prevention, DLP) in SharePoint Online können Sie Dokumente ermitteln, die vertrauliche Daten in Ihrem gesamten Mandanten enthalten. Nach der Ermittlung der Dokumente können Sie mit deren Besitzern zusammenarbeiten, um die Daten zu schützen. In diesem Thema wird das Erstellen einer Abfrage zur Suche nach vertraulichen Daten behandelt.

> [!NOTE]
> Electronic Discovery oder eDiscovery und DLP sind Premium-Features, die [SharePoint Onlineplan 2](https://go.microsoft.com/fwlink/?LinkId=510080)erfordern.

## <a name="forming-a-basic-dlp-query"></a>Erstellen einer einfachen DLP-Abfrage

Eine einfache DLP-Abfrage besteht aus drei Teilen: SensitiveType (Typ vertraulicher Informationen), Anzahlbereich und Konfidenzbereich. Wie in der folgenden Grafik dargestellt, ist **SensitiveType:" \<type\> "** erforderlich, und beide **|\<count range\>** sind **|\<confidence range\>** optional.

![Beispielabfrage unterteilt in erforderlich und optional](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>Typ vertraulicher Informationen - erforderlich

Was haben die einzelnen Teile zu bedeuten? SharePoint DLP-Abfragen beginnen in der Regel mit der Eigenschaft `SensitiveType:"` und einem Informationstypnamen aus dem Bestand der [Typen vertraulicher Informationen](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)und enden mit einem `"` . Sie können auch den Namen eines [benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md) verwenden, den Sie für Ihre Organisation erstellt haben. Angenommen, Sie suchen Dokumente mit Kreditkartennummern. In einer solchen Instanz verwenden Sie das folgende Format:  `SensitiveType:"Credit Card Number"` . Da Sie weder den Zählungsbereich noch den Konfidenzbereich eingeschlossen haben, gibt die Abfrage jedes Dokument zurück, in dem eine Kreditkartennummer erkannt wird. Dies ist einfachste Abfrage, die möglich ist und die die meisten Ergebnisse zurückgibt. Beachten Sie, dass Schreibung und Leerzeichen im Typ vertraulicher Informationen eine Rolle spielen.

### <a name="ranges---optional"></a>Bereiche - optional

Die beiden nächsten Teile sind Bereiche. Lassen Sie uns also schnell untersuchen, wie ein Bereich aussieht. In SharePoint DLP-Abfragen wird ein einfacher Bereich durch zwei Zahlen dargestellt, die durch zwei Punkte getrennt sind, was wie folgt aussieht: `[number]..[number]` . Wenn z.  `10..20` B. dieser Bereich verwendet wird, werden Nummern zwischen 10 und 20 erfasst. Es gibt zahlreiche Bereichskombinationen, von denen einige in diesem Thema behandelt werden.

Fügen wir der Abfrage einen Zählungsbereich hinzu. Sie können den Zählungsbereich verwenden, um die Anzahl der Vorkommen vertraulicher Informationen zu definieren, die ein Dokument enthalten muss, bevor es in die Abfrageergebnisse aufgenommen wird. Wenn Ihre Abfrage beispielsweise nur Dokumente zurückgeben soll, die genau fünf Kreditkartennummern enthalten, verwenden Sie Folgendes:  `SensitiveType:"Credit Card Number|5"` . Mithilfe eines Anzahlbereichs können Sie auch Dokumente mit hohem Risikopotenzial ermitteln. Angenommen, in Ihrer Organisation werden Dokumente mit mindestens fünf Kreditkartennummern als hohes Risiko eingestuft. Um Dokumente zu finden, die dieses Kriterium erfüllen, verwenden Sie diese Abfrage:  `SensitiveType:"Credit Card Number|5.."` . Alternativ können Sie Dokumente mit fünf oder weniger Kreditkartennummern mithilfe der folgenden Abfrage finden:  `SensitiveType:"Credit Card Number|..5"` .

#### <a name="confidence-range"></a>Konfidenzbereich

Mithilfe des Konfidenzbereichs wird schließlich der Grad an Konfidenz angegeben, zu dem der erkannte Typ vertraulicher Informationen ein Treffer ist. Die Werte für den Konfidenzbereich sind mit denen für den Anzahlbereich vergleichbar. Sie können eine Abfrage ohne Angabe eines Anzahlbereichs erstellen. Wenn Sie z. B. nach Dokumenten mit einer beliebigen Anzahl von Kreditkartennummern suchen möchten – solange der Konfidenzbereich 85 % oder höher ist – verwenden Sie die folgende Abfrage:  `SensitiveType:"Credit Card Number|*|85.."` .

> [!IMPORTANT]
> Das Sternchen ( `*` ) ist ein Platzhalterzeichen, das bedeutet, dass ein beliebiger Wert funktioniert. Sie können das Platzhalterzeichen ( `*` ) entweder im Zählungsbereich oder im Konfidenzbereich verwenden, jedoch nicht in einem vertraulichen Typ.

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Im eDiscovery Center stehen weitere Abfrageeigenschaften und Suchoperatoren zur Verfügung.

DLP in SharePoint führt auch die LastSensitiveContentScan-Eigenschaft ein, mit der Sie nach Dateien suchen können, die innerhalb eines bestimmten Zeitrahmens gescannt wurden. Abfragebeispiele mit der  `LastSensitiveContentScan` Eigenschaft finden Sie in den [Beispielen für komplexe Abfragen](#examples-of-complex-queries) im nächsten Abschnitt.

Sie können nicht nur DLP-spezifische Eigenschaften verwenden, um eine Abfrage zu erstellen, sondern auch Standard-SharePoint eDiscovery-Sucheigenschaften wie `Author` oder `FileExtension` . Sie können Operatoren verwenden, um komplexe Abfragen zu erstellen. Eine Liste der verfügbaren Eigenschaften und Operatoren finden Sie im Blogbeitrag ["Verwenden von Sucheigenschaften und Operatoren mit eDiscovery".](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)

## <a name="examples-of-complex-queries"></a>Beispiele

In den folgenden Beispielen werden verschiedene Typen, Eigenschaften und Operatoren für vertrauliche Informationen verwendet, um zu veranschaulichen, wie Sie Ihre Abfragen optimieren können, um genau das zu finden, wonach Sie suchen.

<br>

****

|Abfrage|Erklärung|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|Der Name mag ungewöhnlich erscheinen, da er so lang ist, aber der richtige Name für diesen vertraulichen Typ ist. Stellen Sie sicher, dass Sie genaue Namen aus dem Inventar der [Typen vertraulicher Informationen](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)verwenden. Sie können auch den Namen eines [benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md) verwenden, den Sie für Ihre Organisation erstellt haben.|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|Dadurch werden Dokumente mit mindestens einer Übereinstimmung mit dem vertraulichen Typ "Kreditkartennummer" zurückgegeben. Die Werte für jeden Bereich sind die jeweiligen Mindest- und Höchstwerte. Eine einfachere Möglichkeit zum Schreiben dieser Abfrage ist  `SensitiveType:"Credit Card Number"` , aber wo ist der Spaß dabei?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|Dadurch werden Dokumente mit 5-25 Kreditkartennummern zurückgegeben, die vom 11. August 2018 bis zum 13. August 2018 gescannt wurden.|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|Dadurch werden Dokumente mit 5-25 Kreditkartennummern zurückgegeben, die vom 11. August 2018 bis zum 13. August 2018 gescannt wurden. Dateien mit einer XLSX-Erweiterung sind in den Abfrageergebnissen nicht enthalten.  `FileExtension` ist eine von vielen Eigenschaften, die Sie in eine Abfrage einschließen können. Weitere Informationen finden Sie unter [Verwenden von Sucheigenschaften und Operatoren mit eDiscovery.](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|Diese Abfrage gibt Dokumente zurück, die entweder eine Kreditkartennummer oder US-Sozialversicherungsnummer enthalten.|
|

## <a name="examples-of-queries-to-avoid"></a>Beispiele

Nicht alle Abfragen sind gleich. Die folgende Tabelle enthält Beispiele für Abfragen, die nicht mit DLP in SharePoint funktionieren, und beschreibt, warum.

<br>

****

|Nicht unterstützte Abfrage|Grund|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|Sie müssen mindestens eine Zahl hinzufügen.|
|`SensitiveType:"NotARule"`|"NotARule" ist kein gültiger Name des vertraulichen Typs. In DLP-Abfragen funktionieren nur Namen in der [Inventarisierung vertraulicher Informationstypen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)|
|`SensitiveType:"Credit Card Number|0"`|Null ist weder als Minimalwert noch als Maximalwert in einem Bereich gültig.|
|`SensitiveType:"Credit Card Number"`|Es ist möglicherweise schwierig zu sehen, aber es gibt zusätzliche Leerzeichen zwischen "Kredit" und "Karte", wodurch die Abfrage ungültig wird. Verwenden Sie genaue Namen vertraulicher Typen aus dem Bestand der [Typen vertraulicher Informationen.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)|
|`SensitiveType:"Credit Card Number|1. .3"`|Der zwei periodische Teil sollte nicht durch ein Leerzeichen getrennt werden.|
|`SensitiveType:"Credit Card Number| |1..|80.."`|Es gibt zu viele Pipe-Trennzeichen ( \| ). Folgen Sie stattdessen folgendem Format: `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|Da Konfidenzwerte einen Prozentsatz darstellen, dürfen sie 100 nicht überschreiten. Wählen Sie einen Wert von 1 bis 100.|
|

## <a name="for-more-information"></a>Weitere Informationen

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Ausführen einer Inhaltssuche](content-search.md)
- [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md)
