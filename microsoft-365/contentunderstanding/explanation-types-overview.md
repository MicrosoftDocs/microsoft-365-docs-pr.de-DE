---
title: Erklärungstypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Weitere Informationen über Erklärungstypen in Microsoft SharePoint Syntex
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321797"
---
# <a name="introduction-to-explanation-types"></a>Einführung in Erklärungstypen

Erklärungen werden verwendet, um die Informationen zu definieren, die Sie in Ihren Document Understanding-Modellen in Microsoft SharePoint Syntex bezeichnen und extrahieren möchten. Wenn Sie eine Erklärung erstellen, müssen Sie einen Erklärungstyp auswählen. Dieser Artikel soll Ihnen helfen, die verschiedenen Erklärungstypen und ihre Verwendung besser zu verstehen. 

   ![Erklärungstypen](../media/content-understanding/explanation-types.png) 
   
Diese Erklärungstypen stehen zur Verfügung:

- **Begriffsliste**: Liste von Wörtern, Phrasen, Zahlen oder anderen Zeichen, die Sie in dem Dokument oder der Information, die Sie extrahieren, verwenden können. Zum Beispiel ist die Textzeichenfolge **Überweisender Arzt** in allen Dokumenten "Ärztliche Überweisung" enthalten, die Sie identifizieren.</br>

- **Musterliste**: Auflisten von Mustern aus Zahlen, Buchstaben oder anderen Zeichen, die Sie zur Identifizierung der Informationen, die Sie extrahieren, verwenden können. Sie können beispielsweise die **Telefonnummer** des überweisenden Arztes aus allen Dokumenten "Ärztliche Überweisung" extrahieren, die Sie identifizieren.</br>

- **Näherung**: Beschreibt, wie nahe die Erklärungen beieinander liegen. Zum Beispiel geht eine Musterliste *Straßennummer* direkt vor die Begriffsliste *Straßenname*, ohne Token dazwischen (Sie werden später in diesem Artikel mehr über Token erfahren). Die Verwendung des Näherungstyps erfordert, dass Sie mindestens zwei Erklärungen in Ihrem Modell haben, sonst wird die Option deaktiviert. 
 
## <a name="phrase-list"></a>Begriffsliste

Der Erklärungstyp "Begriffsliste" wird normalerweise verwendet, um ein Dokument durch Ihr Modell zu identifizieren und zu klassifizieren. Wie im Beispiel der Bezeichnung *Überweisender Arzt* beschrieben, handelt es sich dabei um eine Kette von Wörtern, Phrasen, Zahlen oder Zeichen, die in den Dokumenten, die Sie identifizieren, konsistent ist.

Auch wenn dies keine Voraussetzung ist, können Sie mit Ihrer Erklärung einen besseren Erfolg erzielen, wenn die Phrase, die Sie erfassen, sich an einer konsistenten Stelle in Ihrem Dokument befindet. Beispielsweise kann sich die Bezeichnung *Überweisender Arzt* durchgängig im ersten Absatz des Dokuments befinden.

Wenn die Groß-/Kleinschreibung bei der Identifizierung Ihrer Bezeichnung beachtet werden muss, können Sie dies in Ihrer Erklärung mit dem Typ "Begriffsliste" angeben, indem Sie das Kontrollkästchen **Nur exakte Groß-/Kleinschreibung** aktivieren.

   ![Unterscheidung nach Groß-/Kleinschreibung](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Musterlisten

Ein Musterlistentyp ist besonders nützlich, wenn Sie eine Erklärung erstellen, die Informationen aus einem Dokument identifiziert und extrahiert. Sie wird in der Regel in verschiedenen Formaten dargestellt, wie z. B. Datum, Telefonnummern oder Kreditkartennummern. Beispielsweise kann ein Datum in verschiedenen Formaten angezeigt werden (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1.1.2020 usw.). Die Definition einer Musterliste macht Ihre Erklärung effizienter, indem sie alle möglichen Variationen in den Daten erfasst, die Sie zu identifizieren und zu extrahieren versuchen. 

Für das Beispiel **Telefonnummer** extrahieren Sie die Telefonnummer für jeden überweisenden Arzt aus allen Dokumenten "Ärztliche Überweisung", die das Modell identifiziert. Wenn Sie die Erklärung erstellen, wählen Sie den Musterlistentyp aus, um die verschiedenen Formate zuzulassen, von denen Sie erwarten können, dass sie zurückgegeben werden.

   ![Musterliste "Telefonnummer"](../media/content-understanding/pattern-list.png)

Für dieses Beispiel aktivieren Sie das Kontrollkästchen **Beliebige Ziffer von 0-9**. Wenn Sie dies aktivieren, wird jeder "0"-Wert, der in Ihrer Musterliste verwendet wird, als eine beliebige Ziffer von 0 bis 9 erkannt.

   ![Beliebige Ziffer von 0-9](../media/content-understanding/digit-identity.png)

Wenn Sie eine Musterliste erstellen, die Textzeichen enthält, aktivieren Sie in ähnlicher Weise das Kontrollkästchen **Jeder Buchstabe von a-z**. Wenn Sie dies aktivieren, wird jedes "a"-Zeichen, das in der Musterliste verwendet wird, als ein beliebiges Zeichen von "a" bis "z" erkannt.

Wenn Sie beispielsweise eine Musterliste **Datum** erstellen und sicherstellen möchten, dass ein Datumsformat wie z. B. *Jan 1, 2020* erkannt wird, müssen Sie Folgendes tun:
- Fügen Sie Ihrer Musterliste *aaa 0, 0000* und *aaa 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **Beliebiger Buchstabe von a-z** ausgewählt ist.

   ![Beliebiger Buchstabe von a-z](../media/content-understanding/any-letter.png)

Wenn Sie in Ihrer Musterliste Groß-/Kleinschreibungsanforderungen haben, haben Sie zusätzlich die Möglichkeit, das Kontrollkästchen **Nur genaue Groß-/Kleinschreibung** zu aktivieren. Wenn Sie für das Beispiel "Datum" den ersten Buchstaben des Monats groß schreiben möchten, müssen Sie Folgendes tun:

- Fügen Sie Ihrer Musterliste *Aaa 0, 0000* und *Aaa 00, 0000* hinzu.
- Stellen Sie sicher, dass auch **Nur genaue Groß-/Kleinschreibung** ausgewählt ist.

   ![Nur genaue Groß-/Kleinschreibung](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Statt die Erklärung der Musterliste manuell zu erstellen, verwenden Sie die [Erklärungsbibliothek](), um vorgefertigte Musterlistenvorlagen für allgemeine Musterlisten zu verwenden, wie z. B. *Datum*, *Telefonnummer*, *Kreditkartennummer* usw. 

## <a name="proximity"></a>Näherung 

Der Erklärungstyp "Näherung" hilft Ihrem Modell bei der Identifizierung von Daten, indem er definiert, wie nahe ein anderer Datenbestand an ihm liegt. Beispielsweise haben Sie in Ihrem Modell zwei Erklärungen definiert, die sowohl die *Straßennummer* als auch die *Telefonnummer* des Kunden bezeichnen. 

Außerdem stellen Sie fest, dass die Telefonnummern des Kunden immer vor der Straßennummer erscheinen. 

Alex Wilburn<br>
555-555-5555<br>
Langgasse 18<br>
54123 Münchfeld<br>

Verwenden Sie die Näherungserklärung, um festzulegen, wie weit die Erklärung "Telefonnummer" entfernt ist, um die Straßennummer in Ihren Dokumenten besser identifizieren zu können.

   ![Näherungserklärung](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Was sind Token?

Um den Erklärungstyp "Näherung" verwenden zu können, müssen Sie verstehen, was ein Token ist, da die Anzahl der Token angibt, wie die Näherungserklärung den Abstand von einer Erklärung zur anderen misst.  

Ein Token ist eine kontinuierliche Spanne (keine Leerzeichen oder Interpunktion) von Buchstaben und Zahlen. Ein Leerzeichen ist KEIN Token. Jedes Interpunktionszeichen ist ein Token. Die folgende Tabelle zeigt einige Beispiele für das Ermitteln der Anzahl von Token in einer Phrase.

|Phrase|Anzahl von Token|Erklärung|
|--|--|--|
|`Dog`|1|Ein einzelnes Wort ohne Interpunktionszeichen oder Leerzeichen.|
|`RMT33W`|1|Eine Datensatz-Locator-Nummer. Sie kann Zahlen und Buchstaben enthalten, hat aber keine Interpunktion.|
|`425-555-5555`|5|Eine Telefonnummer. Jedes Interpunktionszeichen ist ein einzelnes Token, sodass  `425-555-5555` 5 Tokens wären:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Konfigurieren des Erklärungstyps "Näherung"

Konfigurieren Sie für das Beispiel die Einstellung für die Näherung so, dass wir den Bereich der Anzahl der Token definieren können, die die Erklärung *Telefonnummer* aus der Erklärung *Straßennummer* enthält.

Sie sollten sehen, dass der Mindestbereich "0" ist, da es keine Token zwischen der Telefonnummer und der Straßennummer gibt.

Einige Telefonnummern in den Beispieldokumenten sind jedoch mit *(Mobil)* angehängt.

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

Sie können zwar manuell verschiedene Musterlistenwerte für Ihre Erklärung hinzufügen, es kann jedoch viel einfacher sein, die vorgefertigten Vorlagen zu verwenden, die Ihnen in der Erklärungsbibliothek zur Verfügung gestellt werden.

Statt z. B. alle Varianten für *Datum* manuell hinzuzufügen, können Sie die Musterlistenvorlage für* Datum* verwenden, die bereits eine Reihe von Musterlistenwerten enthält:</br>

   ![Erklärungsbibliothek](../media/content-understanding/explanation-template.png)</br>
 
Die Erklärungsbibliothek enthält eine Reihe von häufig verwendeten Musterlistenerklärungen, einschließlich:</br>

- Datum</br>
- Datum (numerisch)</br>
- Zeit</br>
- Zahl</br>
- Telefonnummer</br>
- PLZ</br>
- Erstes Wort des Satzes</br>
- Kreditkarte</br>
- Sozialversicherungsnummer</br>

Beachten Sie, dass die Erklärungsbibliothek auch Vorlagen für Begriffslistenerklärungen enthält, einschließlich:
- Ende des Satzes
- Währung

#### <a name="to-use-a-template-from-the-explanation-library"></a>Verwenden einer Vorlage aus der Erklärungsbibliothek

1. Wählen Sie im Abschnitt **Erklärungen** auf der Seite **Trainieren** Ihres Modells **Neu** aus und dann **Aus einer Vorlage**.</br>

   ![Aus Vorlage erstellen](../media/content-understanding/from-template.png)</br>

2.  Wählen Sie auf der Seite **Erklärungsvorlagen** die Erklärung aus, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen** aus.</br>

       ![Auswählen einer Vorlage](../media/content-understanding/phone-template.png)</br>

3. Die Informationen für die von Ihnen ausgewählte Vorlage werden auf der Seite **Erklärung erstellen** angezeigt. Bearbeiten Sie bei Bedarf den Namen der Erklärung und fügen Sie Elemente zur Musterliste hinzu oder entfernen Sie diese. </br> 

   ![Vorlage bearbeiten](../media/content-understanding/phone-template-live.png)</br>

4. Wählen Sie anschließend **Speichern**.
