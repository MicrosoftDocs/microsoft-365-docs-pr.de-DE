---
title: Erklärungstypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Weitere Informationen über Erklärungstypen in Microsoft SharePoint Syntex
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087643"
---
# <a name="introduction-to-explanation-types"></a>Einführung in Erklärungstypen

Erklärungen werden verwendet, um die Informationen zu definieren, die Sie in Ihren Dokumentverständnismodellen in Microsoft SharePoint Syntex bezeichnen und extrahieren möchten. Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungstyp auswählen. Dieser Artikel hilft Ihnen dabei, die verschiedenen Erklärungstypen und ihre Verwendung zu verstehen. 

   ![Erklärungstypen](../media/content-understanding/explanation-types.png) 
   
Die folgenden Erklärungstypen stehen zur Verfügung:

- **Begriffsliste**: Eine Liste von Wörtern, Phrasen, Zahlen oder anderen Zeichen, die Sie in dem Dokument oder der Information, die Sie extrahieren, verwenden können. Die Textzeichenfolge **Überweisender Arzt** ist zum Beispiel in allen Dokumenten "Ärztliche Überweisung" enthalten, die identifiziert werden.</br>

- **Musterliste**: Auflistung von Mustern aus Zahlen, Buchstaben oder anderen Zeichen, die Sie zur Identifizierung der Informationen, die extrahiert werden sollen, verwenden können. Sie können beispielsweise die **Telefonnummer** des überweisenden Arztes aus allen Dokumenten "Ärztliche Überweisung" extrahieren, die identifiziert werden.</br>

- **Näherung**: Beschreibt, wie nahe die Erklärungen beieinander liegen. Eine Musterliste *Straßennummer* liegt zum Beispiel direkt vor der Begriffsliste *Straßenname*, ohne Token dazwischen (Sie werden später in diesem Artikel mehr über Token erfahren). Die Verwendung des Näherungstyps erfordert, dass Sie mindestens zwei Erklärungen in Ihrem Modell haben, die Option ist ansonsten deaktiviert. 
 
## <a name="phrase-list"></a>Begriffsliste

Der Erklärungstyp "Begriffsliste" wird normalerweise verwendet, um ein Dokument durch Ihr Modell zu identifizieren und zu klassifizieren. Wie im Beispiel für die Bezeichnung *Überweisender Arzt* beschrieben, handelt es sich dabei um eine Folge von Wörtern, Phrasen, Zahlen oder Zeichen, die in den Dokumenten, die in den zu ermittelnden Dokumenten einheitlich vorkommen.

Dies ist zwar keine Voraussetzung, Sie können mit einer Erklärung aber bessere Erfolge erzielen, wenn die Phrase, die erfasst wird, sich immer an der selben Stelle in dem Dokument befindet. Beispielsweise kann sich die Bezeichnung *Überweisender Arzt* durchgängig im ersten Absatz des Dokuments befinden.

Wenn die Groß-/Kleinschreibung bei der Identifizierung Ihrer Bezeichnung beachtet werden muss, können Sie dies in Ihrer Erklärung mit dem Typ "Begriffsliste" angeben, indem Sie das Kontrollkästchen **Nur genaue Groß-/Kleinschreibung** aktivieren.

   ![Unterscheidung nach Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Musterlisten

Ein Musterlistentyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen aus einem Dokument identifiziert und extrahiert. Er wird in der Regel in verschiedenen Formaten dargestellt, wie z. B. Datum, Telefonnummern und Kreditkartennummern. Beispielsweise kann ein Datum in verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1.1.2020 usw.). Die Definition einer Musterliste macht Ihre Erklärung effizienter, indem sie alle möglichen Varianten der Daten erfasst, die Sie identifizieren und extrahieren möchten. 

Für das Beispiel **Telefonnummer** extrahieren Sie die Telefonnummer für jeden überweisenden Arzt aus allen Dokumenten "Ärztliche Überweisung", die von dem Modell identifiziert werden. Wenn Sie die Erklärung erstellen, wählen Sie den Musterlistentyp aus, um die verschiedenen Formate zuzulassen, von denen Sie ausgehen, dass sie zurückgegeben werden könnten.

   ![Musterliste "Telefonnummer"](../media/content-understanding/pattern-list.png)

Wählen Sie in diesem Beispiel das Kontrollkästchen **Beliebige Ziffer von 0-9** aus, um zu erkennen, dass es sich bei jedem in Ihrer Musterliste verwendeten „0“-Wert um eine beliebige Ziffer von 0 bis 9 handelt.

   ![Beliebige Ziffer von 0-9](../media/content-understanding/digit-identity.png)

Wenn Sie eine Musterliste erstellen, die Textzeichen enthält, wählen Sie in ähnlicher Weise das Kontrollkästchen **Beliebige Buchstaben von a-z** aus, um zu erkennen, dass es sich bei jedem in Ihrer Musterliste verwendeten "a" -Zeichen um ein beliebiges Zeichen zwischen "a" und "z" handelt.

Wenn Sie beispielsweise eine Musterliste **Datum** erstellen und sicherstellen möchten, dass ein Datumsformat wie z. B. *Jan 1, 2020* erkannt wird, müssen Sie Folgendes tun:
- Fügen Sie Ihrer Musterliste *aaa 0, 0000* und *aaa 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **Beliebiger Buchstabe von a-z** ausgewählt ist.

   ![Beliebiger Buchstabe von a-z](../media/content-understanding/any-letter.png)

Wenn für Ihre Musterliste die Berücksichtigung der Groß-/Kleinschreibung erforderlich ist, können Sie das Kontrollkästchen **Nur genaue Groß-/Kleinschreibung** aktivieren. Wenn für das Beispiel "Datum" der erste Buchstabe des Monats groß geschrieben sein soll, müssen Sie Folgendes tun:

- Fügen Sie Ihrer Musterliste *Aaa 0, 0000* und *Aaa 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **Nur genaue Groß-/Kleinschreibung** ausgewählt ist.

   ![Nur genaue Groß-/Kleinschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Statt eine Musterlistenerklärung manuell zu erstellen, verwenden Sie die [Erklärungsbibliothek](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates), um Musterlistenvorlagen für allgemeine Musterlisten zu verwenden, wie z. B. *Datum*, *Telefonnummer*, *Kreditkartennummer* usw.

## <a name="proximity"></a>Näherung 

Der Erklärungstyp "Näherung" hilft Ihrem Modell bei der Identifizierung von Daten, indem er definiert, wie nahe sich ein Datenelement neben einem anderen befindet. Beispielsweise haben Sie in Ihrem Modell zwei Erklärungen definiert, die sowohl die *Straßennummer* als auch die *Telefonnummer* des Kunden bezeichnen. 

Beachten Sie, dass die Telefonnummern von Kunden immer vor der Straßennummer stehen. 

Alex Wilburn<br>
555-555-5555<br>
Langgasse 18<br>
54123 Münchfeld<br>

Verwenden Sie die Näherungserklärung, um festzulegen, wie weit die Erklärung "Telefonnummer" entfernt ist, um die Straßennummer in Ihren Dokumenten besser identifizieren zu können.

   ![Näherungserklärung](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Was sind Token?

Um den Erklärungstyp "Näherung" verwenden zu können, müssen Sie verstehen, was ein Token ist, da die Anzahl der Token angibt, wie die Näherungserklärung den Abstand von einer Erklärung zur anderen misst. Ein Token ist eine kontinuierliche Reihe (ohne Leerzeichen oder Satzzeichen) von Buchstaben und Zahlen. 

Die folgende Tabelle zeigt Beispiele, wie die Anzahl der Token in einer Phrase ermittelt wird.

|Phrase|Anzahl von Token|Erklärung|
|--|--|--|
|`Dog`|1|Ein einzelnes Wort ohne Interpunktionszeichen oder Leerzeichen.|
|`RMT33W`|1|Eine Datensatz-Locator-Nummer. Sie kann Zahlen und Buchstaben beinhalten, jedoch keine Satzzeichen.|
|`425-555-5555`|5|Eine Telefonnummer. Jedes Satzzeichen stellt ein einzelnes Token dar; `425-555-5555` besteht also aus 5 Token:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurieren des Erklärungstyps "Näherung"

Konfigurieren Sie für das Beispiel die Näherungseinstellung, um den Bereich der Anzahl der Token in der *Telefonnummer*-Erklärung aus der *Straßenadressnummer*-Erklärung zu definieren. Beachten Sie, dass der Mindestbereich "0" ist, da es keine Token zwischen der Telefonnummer und der Straßenadressnummer gibt.

Einige Telefonnummern in den Beispieldokumenten sind jedoch mit *(Mobil)* ergänzt.

Nestor Wilke<br>
111-111-1111 (Mobil)<br>
Langgasse 18<br>
54123 Münchfeld<br>

Es gibt drei Token in *(Mobil)*:

|Phrase|Tokenzahl|
|--|--|
|(|1|
|Mobil|2|
|)|3|

Konfigurieren Sie die Einstellung für die Näherung so, dass sie einen Wert von 0 bis 3 aufweist.

   ![Beispiel einer Näherung](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a>Verwenden von Erklärungsvorlagen

Während Sie manuell verschiedene Musterlistenwerte für Ihre Erklärung hinzufügen können, kann es einfacher sein, die Vorlagen zu verwenden, die Ihnen in der Erklärungsbibliothek zur Verfügung gestellt werden.

Statt z. B. alle Varianten für *Datum* manuell hinzuzufügen, können Sie die Musterlistenvorlage für *Datum* verwenden, da diese bereits eine Reihe von Musterlistenwerten enthält:</br>

   ![Erklärungsbibliothek](../media/content-understanding/explanation-template.png)</br>
 
Die Erklärungsbibliothek enthält häufig verwendeten Musterlistenerklärungen, einschließlich:</br>

- Datum</br>
- Datum (numerisch)</br>
- Zeit</br>
- Zahl</br>
- Telefonnummer</br>
- PLZ</br>
- Erstes Wort des Satzes</br>
- Kreditkarte</br>
- Sozialversicherungsnummer</br>

Beachten Sie, dass die Erklärungsbibliothek auch Vorlagen für Begriffslistenerklärungen enthält:
- Ende des Satzes
- Währung

#### <a name="to-use-a-template-from-the-explanation-library"></a>Verwenden einer Vorlage aus der Erklärungsbibliothek

1. Wählen Sie im Abschnitt **Erklärungen** auf der Seite **Trainieren** Ihres Modells **Neu** aus und dann **Aus einer Vorlage**.</br>

   ![Aus Vorlage erstellen](../media/content-understanding/from-template.png)</br>

2.  Wählen Sie auf der Seite **Erklärungsvorlagen** die Erklärung aus, die Sie verwenden möchten, dann wählen Sie **Hinzufügen** aus.</br>

       ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)</br>

3. Die Informationen für die von Ihnen ausgewählte Vorlage sind auf der Seite **Erklärung erstellen** dargestellt. Bearbeiten Sie bei Bedarf den Namen der Erklärung, und fügen Sie Elemente zur Musterliste hinzu oder entfernen Sie diese.</br> 

   ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)</br>

4. Wählen Sie anschließend **Speichern**.
